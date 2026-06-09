# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::GetRecordsIdsAndEntityNameForDeletionForIndependentEntities

- ea: `0x15e0`
- end: `0x1672`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::GetRecordsIdsAndEntityNameForDeletionForIndependentEntities`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x2de0`

## callees

- `0x1f2d0`

## pseudocode

```c

```

## disassembly

```asm
0x15e0  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x15e5  stloc.0
0x15e6  ldloc.0
0x15e7  ldnull
0x15e8  stfld    object[] <>c__DisplayClass16_0::row
0x15ed  ldloc.0
0x15ee  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object[]>::.ctor()
0x15f3  stfld    class [mscorlib]System.Collections.Generic.List`1<object[]> <>c__DisplayClass16_0::returnValue
0x15f8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15fd  ldstr    aWith0OrderedBy// "WITH [{0} ORDERED BY ROWID] AS \r\n\t\t"...
0x1602  ldc.i4.1
0x1603  newarr   [mscorlib]System.Object
0x1608  dup
0x1609  ldc.i4.0
0x160a  ldarg.1
0x160b  stelem.ref
0x160c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1611  ldc.i4.1
0x1612  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x1617  stloc.1
0x1618  ldloc.1
0x1619  ldstr    aNextrow// "@nextRow"
0x161e  ldarg.2
0x161f  box      [mscorlib]System.Int32
0x1624  ldloca.s 2
0x1626  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x162c  ldloc.2
0x162d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x1632  ldloc.1
0x1633  ldstr    aLastrow// "@lastRow"
0x1638  ldarg.3
0x1639  box      [mscorlib]System.Int32
0x163e  ldloca.s 2
0x1640  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1646  ldloc.2
0x1647  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x164c  ldarg.0
0x164d  ldloc.1
0x164e  ldloc.0
0x164f  ldftn    instance void <>c__DisplayClass16_0::<GetRecordsIdsAndEntityNameForDeletionForIndependentEntities>b__0(object[] values)
0x1655  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x165a  ldarg.0
0x165b  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x1660  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1665  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor, valuetype [mscorlib]System.Guid)
0x166a  pop
0x166b  ldloc.0
0x166c  ldfld    class [mscorlib]System.Collections.Generic.List`1<object[]> <>c__DisplayClass16_0::returnValue
0x1671  ret
```
