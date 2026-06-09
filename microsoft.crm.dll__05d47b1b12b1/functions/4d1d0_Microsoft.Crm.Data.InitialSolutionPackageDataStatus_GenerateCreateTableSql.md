# Microsoft.Crm.Data.InitialSolutionPackageDataStatus::GenerateCreateTableSql

- ea: `0x4d1d0`
- end: `0x4d1d6`
- name: `Microsoft.Crm.Data.InitialSolutionPackageDataStatus::GenerateCreateTableSql`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4b460`

## string_xrefs

- `0x4d1d0`: `\nIF NOT EXISTS (SELECT name FROM sys.tables WHERE name='InitialSolutionPackageDataStatus')\nBEGIN\n	CREATE TABLE [dbo].[InitialSolutionPackageDataStatus](\n		[Id] [uniqueidentifier] NOT NULL,\n		[DataRemovalAttempted] [bit] NOT NULL\n	 CONSTRAINT [PK_InitialSolutionPackageDataStatus] PRIMARY KEY CLUSTERED \n	(\n		[Id] ASC\n	)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]\n	) ON [PRIMARY]\nEND\n\nI`

## pseudocode

```c

```

## disassembly

```asm
0x4d1d0  ldstr    aIfNotExistsSel_2// "\r\nIF NOT EXISTS (SELECT name FROM sys"...
0x4d1d5  ret
```
