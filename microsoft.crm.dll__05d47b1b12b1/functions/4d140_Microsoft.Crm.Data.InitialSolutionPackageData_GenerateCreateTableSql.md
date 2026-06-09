# Microsoft.Crm.Data.InitialSolutionPackageData::GenerateCreateTableSql

- ea: `0x4d140`
- end: `0x4d146`
- name: `Microsoft.Crm.Data.InitialSolutionPackageData::GenerateCreateTableSql`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4b460`

## string_xrefs

- `0x4d140`: `\nIF NOT EXISTS (SELECT name FROM sys.tables WHERE name='InitialSolutionPackageData')\nBEGIN\n	CREATE TABLE [dbo].[InitialSolutionPackageData](\n		[RecordId] [uniqueidentifier] NOT NULL,\n		[EntityName] [nvarchar] (128) NOT NULL\n	 CONSTRAINT [PK_InitialSolutionPackageData] PRIMARY KEY CLUSTERED \n	(\n		[RecordId] ASC\n	)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]\n	) ON [PRIMARY]\nEND\n\nIF NOT`

## pseudocode

```c

```

## disassembly

```asm
0x4d140  ldstr    aIfNotExistsSel_1// "\r\nIF NOT EXISTS (SELECT name FROM sys"...
0x4d145  ret
```
