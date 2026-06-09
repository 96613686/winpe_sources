# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateRecordsAsProcessed

- ea: `0x14d0`
- end: `0x1538`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateRecordsAsProcessed`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1e80`
- `0x2ea0`

## string_xrefs

- `0x14d5`: `UPDATE {0} SET Processed=1 WHERE RecordId = @recordId AND QueryIndex=@queryIndex`

## pseudocode

```c

```

## disassembly

```asm
0x14d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14d5  ldstr    aUpdate0SetProc// "UPDATE {0} SET Processed=1 WHERE Record"...
0x14da  ldc.i4.1
0x14db  newarr   [mscorlib]System.Object
0x14e0  dup
0x14e1  ldc.i4.0
0x14e2  ldarg.1
0x14e3  stelem.ref
0x14e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14e9  ldc.i4.1
0x14ea  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x14ef  stloc.0
0x14f0  ldloc.0
0x14f1  ldstr    aRecordid// "@recordId"
0x14f6  ldarg.2
0x14f7  box      [mscorlib]System.Guid
0x14fc  ldloca.s 1
0x14fe  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1504  ldloc.1
0x1505  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x150a  ldloc.0
0x150b  ldstr    aQueryindex// "@queryIndex"
0x1510  ldarg.3
0x1511  box      [mscorlib]System.Int32
0x1516  ldloca.s 1
0x1518  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x151e  ldloc.1
0x151f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x1524  ldarg.0
0x1525  ldloc.0
0x1526  ldarg.0
0x1527  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x152c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1531  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x1536  pop
0x1537  ret
```
