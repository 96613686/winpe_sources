# Microsoft.Crm.CrmKeyService::InternalUpdate

- ea: `0x38d00`
- end: `0x38e2a`
- name: `Microsoft.Crm.CrmKeyService::InternalUpdate`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x38c40`

## callees

- `0x1f4b0`
- `0x38d00`
- `0x3b6a0`
- `0x3b740`
- `0x3b750`
- `0x44400`
- `0x44510`
- `0x44780`
- `0x44800`
- `0x44d80`
- `0x44da0`
- `0x44db0`
- `0x4d750`
- `0x62440`

## string_xrefs

- `0x38d5e`: `CreatedOn`
- `0x38dec`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeyService.cs`
- `0x38de7`: `InternalUpdate`
- `0x38e0c`: `{0} entry updated : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x38d00  ldarg.0
0x38d01  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.IAuditableConfigurationEntity::get_SettingsBag()
0x38d06  callvirt instance bool Microsoft.Crm.Data.PropertyBag::get_IsModified()
0x38d0b  brtrue.s loc_38D0E
0x38d0d  ret
0x38d0e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38d13  ldc.i4.s 0x14
0x38d15  ldstr    aUpdating0Entry// "Updating {0} entry : {1}"
0x38d1a  ldc.i4.2
0x38d1b  newarr   [mscorlib]System.Object
0x38d20  dup
0x38d21  ldc.i4.0
0x38d22  ldarg.0
0x38d23  callvirt instance string Microsoft.Crm.IAuditableConfigurationEntity::get_TableName()
0x38d28  stelem.ref
0x38d29  dup
0x38d2a  ldc.i4.1
0x38d2b  ldarg.0
0x38d2c  stelem.ref
0x38d2d  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x38d32  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x38d37  stloc.0
0x38d38  ldarg.0
0x38d39  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.IAuditableConfigurationEntity::get_SettingsBag()
0x38d3e  callvirt instance class [mscorlib]System.Collections.IEnumerable Microsoft.Crm.Data.PropertyBag::get_PropertyEntries()
0x38d43  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x38d48  stloc.1
0x38d49  br.s     loc_38DAC
0x38d4b  ldloc.1
0x38d4c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x38d51  unbox.any Microsoft.Crm.Data.PropertyEntry
0x38d56  stloc.2
0x38d57  ldloca.s 2
0x38d59  call     instance string Microsoft.Crm.Data.PropertyEntry::get_Name()
0x38d5e  ldstr    aCreatedon// "CreatedOn"
0x38d63  ldc.i4.5
0x38d64  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x38d69  brtrue.s loc_38DAC
0x38d6b  ldarg.1
0x38d6c  brfalse.s loc_38D84
0x38d6e  ldloc.0
0x38d6f  ldloca.s 2
0x38d71  call     instance string Microsoft.Crm.Data.PropertyEntry::get_Name()
0x38d76  ldloca.s 2
0x38d78  call     instance object Microsoft.Crm.Data.PropertyEntry::get_Value()
0x38d7d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x38d82  br.s     loc_38DAC
0x38d84  ldloca.s 2
0x38d86  call     instance valuetype Microsoft.Crm.Data.PropertyState Microsoft.Crm.Data.PropertyEntry::get_State()
0x38d8b  ldc.i4.8
0x38d8c  beq.s    loc_38D98
0x38d8e  ldloca.s 2
0x38d90  call     instance valuetype Microsoft.Crm.Data.PropertyState Microsoft.Crm.Data.PropertyEntry::get_State()
0x38d95  ldc.i4.4
0x38d96  bne.un.s loc_38DAC
0x38d98  ldloc.0
0x38d99  ldloca.s 2
0x38d9b  call     instance string Microsoft.Crm.Data.PropertyEntry::get_Name()
0x38da0  ldloca.s 2
0x38da2  call     instance object Microsoft.Crm.Data.PropertyEntry::get_Value()
0x38da7  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x38dac  ldloc.1
0x38dad  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x38db2  brtrue.s loc_38D4B
0x38db4  leave.s  loc_38DC7
0x38db6  ldloc.1
0x38db7  isinst   [mscorlib]System.IDisposable
0x38dbc  stloc.3
0x38dbd  ldloc.3
0x38dbe  brfalse.s loc_38DC6
0x38dc0  ldloc.3
0x38dc1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38dc6  endfinally
0x38dc7  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x38dcc  stloc.s  4
0x38dce  ldloc.s  4
0x38dd0  ldarg.0
0x38dd1  callvirt instance string Microsoft.Crm.IAuditableConfigurationEntity::get_TableName()
0x38dd6  ldarg.0
0x38dd7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IAuditableConfigurationEntity::get_Id()
0x38ddc  box      [mscorlib]System.Guid
0x38de1  ldloc.0
0x38de2  ldc.i4   0xE9
0x38de7  ldstr    aInternalupdate_1// "InternalUpdate"
0x38dec  ldstr    aDA1SSrcPlatfor_19// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x38df1  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, object id, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x38df6  pop
0x38df7  leave.s  loc_38E05
0x38df9  ldloc.s  4
0x38dfb  brfalse.s loc_38E04
0x38dfd  ldloc.s  4
0x38dff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38e04  endfinally
0x38e05  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38e0a  ldc.i4.s 0x14
0x38e0c  ldstr    a0EntryUpdated1// "{0} entry updated : {1}"
0x38e11  ldc.i4.2
0x38e12  newarr   [mscorlib]System.Object
0x38e17  dup
0x38e18  ldc.i4.0
0x38e19  ldarg.0
0x38e1a  callvirt instance string Microsoft.Crm.IAuditableConfigurationEntity::get_TableName()
0x38e1f  stelem.ref
0x38e20  dup
0x38e21  ldc.i4.1
0x38e22  ldarg.0
0x38e23  stelem.ref
0x38e24  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x38e29  ret
```
