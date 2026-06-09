# Microsoft.Crm.CrmKeyService::InternalCreate

- ea: `0x38c80`
- end: `0x38cfd`
- name: `Microsoft.Crm.CrmKeyService::InternalCreate`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x38c10`

## callees

- `0x1f4b0`
- `0x38c80`
- `0x3b740`
- `0x3b750`
- `0x4d750`
- `0x61910`

## string_xrefs

- `0x38cbc`: `InternalCreate`
- `0x38cc1`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeyService.cs`
- `0x38cdf`: `{0} entry created : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x38c80  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38c85  ldc.i4.s 0x14
0x38c87  ldstr    aCreating0Entry// "Creating {0} entry : {1}"
0x38c8c  ldc.i4.2
0x38c8d  newarr   [mscorlib]System.Object
0x38c92  dup
0x38c93  ldc.i4.0
0x38c94  ldarg.0
0x38c95  callvirt instance string Microsoft.Crm.IAuditableConfigurationEntity::get_TableName()
0x38c9a  stelem.ref
0x38c9b  dup
0x38c9c  ldc.i4.1
0x38c9d  ldarg.0
0x38c9e  stelem.ref
0x38c9f  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x38ca4  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x38ca9  stloc.0
0x38caa  ldloc.0
0x38cab  ldarg.0
0x38cac  callvirt instance string Microsoft.Crm.IAuditableConfigurationEntity::get_TableName()
0x38cb1  ldarg.0
0x38cb2  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.IAuditableConfigurationEntity::get_SettingsBag()
0x38cb7  ldc.i4   0xBF
0x38cbc  ldstr    aInternalcreate// "InternalCreate"
0x38cc1  ldstr    aDA1SSrcPlatfor_19// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x38cc6  callvirt instance object Microsoft.Crm.SharedDatabase.DatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x38ccb  pop
0x38ccc  leave.s  loc_38CD8
0x38cce  ldloc.0
0x38ccf  brfalse.s loc_38CD7
0x38cd1  ldloc.0
0x38cd2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38cd7  endfinally
0x38cd8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38cdd  ldc.i4.s 0x14
0x38cdf  ldstr    a0EntryCreated1// "{0} entry created : {1}"
0x38ce4  ldc.i4.2
0x38ce5  newarr   [mscorlib]System.Object
0x38cea  dup
0x38ceb  ldc.i4.0
0x38cec  ldarg.0
0x38ced  callvirt instance string Microsoft.Crm.IAuditableConfigurationEntity::get_TableName()
0x38cf2  stelem.ref
0x38cf3  dup
0x38cf4  ldc.i4.1
0x38cf5  ldarg.0
0x38cf6  stelem.ref
0x38cf7  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x38cfc  ret
```
