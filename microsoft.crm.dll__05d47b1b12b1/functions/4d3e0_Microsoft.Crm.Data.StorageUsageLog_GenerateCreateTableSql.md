# Microsoft.Crm.Data.StorageUsageLog::GenerateCreateTableSql

- ea: `0x4d3e0`
- end: `0x4d3e6`
- name: `Microsoft.Crm.Data.StorageUsageLog::GenerateCreateTableSql`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4b460`

## string_xrefs

- `0x4d3e0`: `\nIF NOT EXISTS (SELECT name FROM sys.tables WHERE name='StorageUsageLog')\nBEGIN\n	CREATE TABLE [dbo].[StorageUsageLog](\n		[LogId] [uniqueidentifier] NOT NULL,\n		[CreatedOn] [datetime] NOT NULL,\n		[DataSizeMB] [int] NOT NULL,\n		[IndexSizeMB] [int] NOT NULL,\n	 CONSTRAINT [PK_StorageUsageLog] PRIMARY KEY CLUSTERED \n	(\n		[LogId] ASC\n	)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]\n	) ON [PRIM`

## pseudocode

```c

```

## disassembly

```asm
0x4d3e0  ldstr    aIfNotExistsSel_4// "\r\nIF NOT EXISTS (SELECT name FROM sys"...
0x4d3e5  ret
```
