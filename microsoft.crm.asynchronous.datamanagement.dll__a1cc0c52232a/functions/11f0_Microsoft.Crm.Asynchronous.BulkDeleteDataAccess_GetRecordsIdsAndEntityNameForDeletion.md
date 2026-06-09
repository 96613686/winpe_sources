# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::GetRecordsIdsAndEntityNameForDeletion

- ea: `0x11f0`
- end: `0x1263`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::GetRecordsIdsAndEntityNameForDeletion`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1db0`

## callees

- `0x1f280`

## pseudocode

```c

```

## disassembly

```asm
0x11f0  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x11f5  stloc.0
0x11f6  ldloc.0
0x11f7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x11fc  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass9_0::recList
0x1201  ldloc.0
0x1202  ldsfld   string [mscorlib]System.String::Empty
0x1207  stfld    string <>c__DisplayClass9_0::_entityName
0x120c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1211  ldstr    aSelectTop1000R// "SELECT Top(1000) RecordId, EntityName F"...
0x1216  ldc.i4.2
0x1217  newarr   [mscorlib]System.Object
0x121c  dup
0x121d  ldc.i4.0
0x121e  ldarg.1
0x121f  stelem.ref
0x1220  dup
0x1221  ldc.i4.1
0x1222  ldarg.2
0x1223  box      [mscorlib]System.Int32
0x1228  stelem.ref
0x1229  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x122e  ldc.i4.1
0x122f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x1234  stloc.1
0x1235  ldarg.0
0x1236  ldloc.1
0x1237  ldloc.0
0x1238  ldftn    instance void <>c__DisplayClass9_0::<GetRecordsIdsAndEntityNameForDeletion>b__0(object[] values)
0x123e  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x1243  ldarg.0
0x1244  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x1249  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x124e  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor, valuetype [mscorlib]System.Guid)
0x1253  pop
0x1254  ldarg.3
0x1255  ldloc.0
0x1256  ldfld    string <>c__DisplayClass9_0::_entityName
0x125b  stind.ref
0x125c  ldloc.0
0x125d  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass9_0::recList
0x1262  ret
```
