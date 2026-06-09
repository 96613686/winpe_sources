# Microsoft.Crm.Data.SolutionPackage::GenerateCreateTableSql

- ea: `0x4d330`
- end: `0x4d336`
- name: `Microsoft.Crm.Data.SolutionPackage::GenerateCreateTableSql`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4b460`

## string_xrefs

- `0x4d330`: `\nIF NOT EXISTS (SELECT name FROM sys.tables WHERE name='SolutionPackage')\nBEGIN\n	CREATE TABLE [dbo].[SolutionPackage](\n		[SolutionId] [uniqueidentifier] NOT NULL,\n		[State] [int] NOT NULL,\n		[QueueItemId] [uniqueidentifier] NOT NULL,\n		[InitiatorObjectId] [uniqueidentifier] NOT NULL,\n		[InitiatorCrmUserId] [uniqueidentifier] NOT NULL,\n		[PackageUrl] [nvarchar](max) NOT NULL,\n		[ErrorMessage] [nvarchar](max) NULL,\n		[UniqueName] [nvarchar](max) NOT NULL,\n		[Version] [nvarc`

## pseudocode

```c

```

## disassembly

```asm
0x4d330  ldstr    aIfNotExistsSel_3// "\r\nIF NOT EXISTS (SELECT name FROM sys"...
0x4d335  ret
```
