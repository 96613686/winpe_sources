# Microsoft.Crm.Data.InitialSolutionInfo::GenerateCreateTableSql

- ea: `0x4d070`
- end: `0x4d076`
- name: `Microsoft.Crm.Data.InitialSolutionInfo::GenerateCreateTableSql`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4b460`

## string_xrefs

- `0x4d070`: `\nIF NOT EXISTS (SELECT name FROM sys.tables WHERE name='InitialSolutionInfo')\nBEGIN\n	CREATE TABLE [dbo].[InitialSolutionInfo](\n		[UniqueName] [nvarchar] (128) NOT NULL,\n		[DeleteStatus] [nvarchar] (max) NULL,\n		[DeleteSuccessful] [bit] NOT NULL\n	 CONSTRAINT [PK_InitialSolutionInfo] PRIMARY KEY CLUSTERED \n	(\n		[UniqueName] ASC\n	)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]\n	) ON [PRIMARY]`

## pseudocode

```c

```

## disassembly

```asm
0x4d070  ldstr    aIfNotExistsSel_0// "\r\nIF NOT EXISTS (SELECT name FROM sys"...
0x4d075  ret
```
