# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CreateIndexOnTempTable

- ea: `0x11b0`
- end: `0x11e4`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CreateIndexOnTempTable`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## string_xrefs

- `0x11b5`: `IF NOT EXISTS (SELECT 1 FROM sysindexes WHERE id=object_id('{0}') AND name='idx_RecordId_QueryIndex')\n									CREATE CLUSTERED INDEX [idx_RecordId_QueryIndex] ON {0}(RecordId, QueryIndex)`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11b5  ldstr    aIfNotExistsSel_1// "IF NOT EXISTS (SELECT 1 FROM sysindexes"...
0x11ba  ldc.i4.1
0x11bb  newarr   [mscorlib]System.Object
0x11c0  dup
0x11c1  ldc.i4.0
0x11c2  ldarg.1
0x11c3  stelem.ref
0x11c4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11c9  ldc.i4.1
0x11ca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x11cf  stloc.0
0x11d0  ldarg.0
0x11d1  ldloc.0
0x11d2  ldarg.0
0x11d3  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x11d8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x11dd  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x11e2  pop
0x11e3  ret
```
