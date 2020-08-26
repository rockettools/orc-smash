# orc-smash

Orc Smash is a tool that can be used to combine multiple orc files into a smaller number of files. For example, converting 100's of files into 10. Having a smaller number of ORC files can have many benifits:
 * Less HDFS overhead.
 * Better compression.
 * Fewer indexes to check when searching.
 
Fewer ORCs can have unintended side effects, so be careful to tune output file count appropriately. Issues that might arise:
 * Suboptimal division of labor in your query layer due to file counts < worker counts
 * Decreased hdfs throughput due to file counts < hdfs datanodes.
