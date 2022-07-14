# VariantPrioritization


This file shares all the preprocessing steps and workflows to reproduce the research conducted in the dissertation

<h2> Scoring large VCFs with nCER scores </h2>

Pre-requisites for scoring a VCF file with nCER scores:
- => Python 3
- GNU Paralllel: To download GNU parallel please refer to the following link http://git.savannah.gnu.org/cgit/parallel.git/tree/README

This folder has all the documents and scripts required for scoring your VCF file with nCER scores. The contents of the folder include the following:

1. all_vars_sample.vcf is a sample VCF file with chromosome, position, ID (ignore values in this column in the sample), reference and alternative which are tab separated. 
2. The folder contains 23 txt files for all scores chromosome wise.
3. A file called 'file_links.txt' has a list of links from where the files were downloaded. I have also created a bash script that automatically uses the file_links text file to download all the 23 txt files in your working directory. which then need to be unzipped for use.
4. A bash script called run_ncer.sh which takes a VCF file (all_vars_sample.vcf provided as a sample- ensure it is in this format, you can leave a field blank such as the 3rd column as long as it is tab separated) and scores all the variants using native grep and GNU parallel and saves them in a file called ncer_scores.txt
5. The run_ncer.sh also uses a python script which combines the scores text file with the actual VCF file and returns the final format you need. This will be something like:
chromosome\tposition\tID\treference\talternative\tncer_score

NOTE: nCER scores are calculated using a 0 position format and therefore some adjustments to the VCF positions and nCER positions need to be made. This has been taken care of in the scripts and is just to aprise you of the situation. 

To read the original github of the authors please visit: https://github.com/TelentiLab/ncER_datasets
The publication for nCER is here: https://www.nature.com/articles/s41467-019-13212-3

<h2> Scoring your VCF file with ReMM scores </h2>


