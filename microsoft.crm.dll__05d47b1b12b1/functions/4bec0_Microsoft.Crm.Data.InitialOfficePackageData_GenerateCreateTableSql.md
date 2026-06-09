# Microsoft.Crm.Data.InitialOfficePackageData::GenerateCreateTableSql

- ea: `0x4bec0`
- end: `0x4bec6`
- name: `Microsoft.Crm.Data.InitialOfficePackageData::GenerateCreateTableSql`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4b460`

## string_xrefs

- `0x4bec0`: `\nIF NOT EXISTS (SELECT name FROM sys.tables WHERE name='InitialOfficePackageData')\nBEGIN\n	CREATE TABLE [dbo].[InitialOfficePackageData](\n		[Id] [uniqueidentifier] NOT NULL,\n		[FileName] [nvarchar] (128)  NULL,\n		[FileContent] [varbinary] (max)  NULL,\n		[UploadStatus] [bit] NULL\n	 CONSTRAINT [PK_InitialOfficePackageData] PRIMARY KEY CLUSTERED \n	(\n		[Id] ASC\n	)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = O`

## pseudocode

```c

```

## disassembly

```asm
0x4bec0  ldstr    aIfNotExistsSel// "\r\nIF NOT EXISTS (SELECT name FROM sys"...
0x4bec5  ret
```
