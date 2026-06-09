# Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::CreateTempTable

- ea: `0x60d10`
- end: `0x60d8e`
- name: `Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::CreateTempTable`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x8f1a0`

## callees

- `0x60d10`
- `0x66af0`
- `0x66b00`

## string_xrefs

- `0x60d22`: `create table #CascadeCollectAssign(id INT IDENTITY(1,1) PRIMARY KEY CLUSTERED, objectid UNIQUEIDENTIFIER NOT NULL, objecttype INT NOT NULL, parentobjectid UNIQUEIDENTIFIER NOT NULL, parentobjecttype INT NOT NULL, cascading INT DEFAULT 0 NOT NULL, level INT DEFAULT 0 NOT NULL\n							UNIQUE (objecttype, id))`
- `0x60d2e`: `create table #CascadeCollectReparent(id INT IDENTITY(1,1) PRIMARY KEY CLUSTERED, objectid UNIQUEIDENTIFIER NOT NULL, objecttype INT NOT NULL, ownerid uniqueidentifier, owneridtype int, parentobjectid UNIQUEIDENTIFIER, parentobjecttype int not null, level int default 0 not null)`
- `0x60d36`: `create table #CascadeCollect(id INT IDENTITY(1,1) PRIMARY KEY CLUSTERED, objectid UNIQUEIDENTIFIER NOT NULL, objecttype INT NOT NULL, tablecolumnname sysname, basetablename sysname)`
- `0x60d6a`: `CreateTempTable`

## pseudocode

```c

```

## disassembly

```asm
0x60d10  ldarg.0
0x60d11  ldfld    bool Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::bIsTmpTblCreated
0x60d16  brtrue.s loc_60D8D
0x60d18  ldsfld   string [mscorlib]System.String::Empty
0x60d1d  stloc.0
0x60d1e  ldarg.1
0x60d1f  ldc.i4.2
0x60d20  bne.un.s loc_60D2A
0x60d22  ldstr    aCreateTableCas// "create table #CascadeCollectAssign(id I"...
0x60d27  stloc.0
0x60d28  br.s     loc_60D3C
0x60d2a  ldarg.1
0x60d2b  ldc.i4.5
0x60d2c  bne.un.s loc_60D36
0x60d2e  ldstr    aCreateTableCas_0// "create table #CascadeCollectReparent(id"...
0x60d33  stloc.0
0x60d34  br.s     loc_60D3C
0x60d36  ldstr    aCreateTableCas_1// "create table #CascadeCollect(id INT IDE"...
0x60d3b  stloc.0
0x60d3c  ldarg.0
0x60d3d  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::context
0x60d42  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x60d47  ldloc.0
0x60d48  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x60d4d  stloc.1
0x60d4e  ldloc.1
0x60d4f  ldarg.0
0x60d50  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::context
0x60d55  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x60d5a  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x60d5f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x60d64  ldloc.1
0x60d65  ldc.i4   0xF8
0x60d6a  ldstr    aCreatetemptabl// "CreateTempTable"
0x60d6f  ldstr    aDA1SSrcManaged_14// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x60d74  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x60d79  pop
0x60d7a  leave.s  loc_60D86
0x60d7c  ldloc.1
0x60d7d  brfalse.s loc_60D85
0x60d7f  ldloc.1
0x60d80  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60d85  endfinally
0x60d86  ldarg.0
0x60d87  ldc.i4.1
0x60d88  stfld    bool Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::bIsTmpTblCreated
0x60d8d  ret
```
