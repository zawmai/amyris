# Fauxlizer 5000

The Fantasy Analytics lab at Amyris has just acquired a new instrument, the Fauxlizer 5000.The instrument produces, as its output, a schematized comma-separated value file, consisting of a column header followed by one or more rows of data.

The Fauxlizer 5k is an excellent piece of hardware, but unfortunately the software that runs on the instrument is buggy and sometimes it produces output files that are corrupted: rows may be truncated, the header may be missing or malformed, the values in a row may be in the wrong order, etc. 

## Input File Example

experiment_name, sample_id, fauxness, category_guess

exp_1, 129, 0.56, ambiguous

exp_2, 34, 0.039, real

control, 0, 1.0, fake

## Assumptions and Constrains
- No comma characters will appear in the files besides the delimiters
- Only use python standard libraries
- Do not use Pandas, Numpy, or Scipy

## Your task is to write a Python API with the following abilities:
- Parse and validate a Fauxlizer data file, rejecting invalid data files.
- Provide a summary of the data in the file in JSON format.
- Return a particular row of data in several formats:
  - Fauxlizer's native csv format
  - JSON
  - A Python in-memory representation

## Examples of valid and corrupt Fauxlizer datasets
https://s3.amazonaws.com/codility-frontend-prod/media/custom_task_static/amyris/data.zip.

## Fauxlizer output format column descriptions:

- experiment_name: Unconstrained string name of the experiment (assume no commas). Should not be empty.
- sample_id: Positive numeric integer ID of the sample under test.
- fauxness: A floating-point value on the range [0.0, 1.0] (inclusive).
- category_guess: A string enum value chosen from the set {"real", "fake", "ambiguous"}.

## Guidelines

Don't worry too much about the computational efficiency of your solution. Please ask questions if you need clarification on the prompt or the requirements for your solution. You may use whatever development environment, tools, and references that you use in your day-to-day development, but please do not ask anyone else for help or share the contents of the prompt or your solution.
