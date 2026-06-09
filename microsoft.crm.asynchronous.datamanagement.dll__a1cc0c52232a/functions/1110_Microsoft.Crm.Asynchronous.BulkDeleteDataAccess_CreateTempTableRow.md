# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CreateTempTableRow

- ea: `0x1110`
- end: `0x11a9`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CreateTempTableRow`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1ba0`

## string_xrefs

- `0x1115`: `IF NOT EXISTS \n							(SELECT 1 FROM\n								BulkDeleteFailureBase INNER JOIN\n								AsyncOperationBase\n								ON\n								BulkDeleteFailureBase.AsyncOperationId = AsyncOperationBase.AsyncOperationId\n								WHERE\n								BulkDeleteFailureBase.RegardingObjectId = @recordId\n								AND\n								AsyncOperationBase.CorrelationId = @correlationId\n							)\n						INSERT INTO {0} (RecordId, EntityName, QueryIndex) VALUES (@recordId, @entityName, @queryIndex)`

## pseudocode

```c

```

## disassembly

```asm
0x1110  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1115  ldstr    aIfNotExistsSel_0// "IF NOT EXISTS \r\n\t\t\t\t\t\t\t(SELECT"...
0x111a  ldc.i4.1
0x111b  newarr   [mscorlib]System.Object
0x1120  dup
0x1121  ldc.i4.0
0x1122  ldarg.1
0x1123  stelem.ref
0x1124  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1129  ldc.i4.1
0x112a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x112f  stloc.0
0x1130  ldloc.0
0x1131  ldstr    aRecordid// "@recordId"
0x1136  ldarg.2
0x1137  box      [mscorlib]System.Guid
0x113c  ldloca.s 1
0x113e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1144  ldloc.1
0x1145  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x114a  ldloc.0
0x114b  ldstr    aEntityname// "@entityName"
0x1150  ldarg.3
0x1151  ldloca.s 1
0x1153  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1159  ldloc.1
0x115a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x115f  ldloc.0
0x1160  ldstr    aQueryindex// "@queryIndex"
0x1165  ldarg.s  4
0x1167  box      [mscorlib]System.Int32
0x116c  ldloca.s 1
0x116e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1174  ldloc.1
0x1175  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x117a  ldloc.0
0x117b  ldstr    aCorrelationid// "@correlationId"
0x1180  ldarg.s  5
0x1182  box      [mscorlib]System.Guid
0x1187  ldloca.s 1
0x1189  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x118f  ldloc.1
0x1190  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x1195  ldarg.0
0x1196  ldloc.0
0x1197  ldarg.0
0x1198  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x119d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x11a2  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x11a7  pop
0x11a8  ret
```
