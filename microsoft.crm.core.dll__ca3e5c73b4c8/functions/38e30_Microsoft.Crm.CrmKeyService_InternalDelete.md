# Microsoft.Crm.CrmKeyService::InternalDelete

- ea: `0x38e30`
- end: `0x38eb1`
- name: `Microsoft.Crm.CrmKeyService::InternalDelete`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x38c60`

## callees

- `0x1f4b0`
- `0x38e30`
- `0x3b6a0`
- `0x3b740`
- `0x4d750`
- `0x62560`

## string_xrefs

- `0x38e76`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeyService.cs`
- `0x38e71`: `InternalDelete`
- `0x38e93`: `{0} entry deleted : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x38e30  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38e35  ldc.i4.s 0x14
0x38e37  ldstr    aDeleting0Entry// "Deleting {0} entry : {1}"
0x38e3c  ldc.i4.2
0x38e3d  newarr   [mscorlib]System.Object
0x38e42  dup
0x38e43  ldc.i4.0
0x38e44  ldarg.0
0x38e45  callvirt instance string Microsoft.Crm.IAuditableConfigurationEntity::get_TableName()
0x38e4a  stelem.ref
0x38e4b  dup
0x38e4c  ldc.i4.1
0x38e4d  ldarg.0
0x38e4e  stelem.ref
0x38e4f  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x38e54  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x38e59  stloc.0
0x38e5a  ldloc.0
0x38e5b  ldarg.0
0x38e5c  callvirt instance string Microsoft.Crm.IAuditableConfigurationEntity::get_TableName()
0x38e61  ldarg.0
0x38e62  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IAuditableConfigurationEntity::get_Id()
0x38e67  box      [mscorlib]System.Guid
0x38e6c  ldc.i4   0xF9
0x38e71  ldstr    aInternaldelete// "InternalDelete"
0x38e76  ldstr    aDA1SSrcPlatfor_19// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x38e7b  callvirt instance void Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string tableName, object id, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x38e80  leave.s  loc_38E8C
0x38e82  ldloc.0
0x38e83  brfalse.s loc_38E8B
0x38e85  ldloc.0
0x38e86  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38e8b  endfinally
0x38e8c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38e91  ldc.i4.s 0x14
0x38e93  ldstr    a0EntryDeleted1// "{0} entry deleted : {1}"
0x38e98  ldc.i4.2
0x38e99  newarr   [mscorlib]System.Object
0x38e9e  dup
0x38e9f  ldc.i4.0
0x38ea0  ldarg.0
0x38ea1  callvirt instance string Microsoft.Crm.IAuditableConfigurationEntity::get_TableName()
0x38ea6  stelem.ref
0x38ea7  dup
0x38ea8  ldc.i4.1
0x38ea9  ldarg.0
0x38eaa  stelem.ref
0x38eab  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x38eb0  ret
```
