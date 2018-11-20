# tmp
select to_varchar(statement_string), execution_count, total_execution_time,
 (select top 1 PARAMETERS from M_EXPENSIVE_STATEMENTS e where e.statement_hash = statement_hash order by statement_start_time desc) PARAMETERS
 from m_sql_plan_cache
 where statement_string like '%LOYD_MA_SPECATTR%' or statement_string like '%LOYD_MA_GENATTR%'
 order by total_execution_time desc;
 
 =======================================
 
