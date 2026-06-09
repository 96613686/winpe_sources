# Microsoft.Crm.ConfigurationDatabase.AuditHistory::CreateCompletedEntry_1

- ea: `0x4b230`
- end: `0x4b33e`
- name: `Microsoft.Crm.ConfigurationDatabase.AuditHistory::CreateCompletedEntry_1`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4b1e0`
- `0x4b200`

## callees

- `0x44400`
- `0x444f0`
- `0x44510`
- `0x4b230`
- `0x4b510`
- `0x4d7e0`
- `0x64b30`
- `0x64bf0`

## string_xrefs

- `0x4b2ab`: `CreatedOn`
- `0x4b2c6`: `CreatedOn`
- `0x4b326`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\AuditHistory.cs`
- `0x4b321`: `CreateCompletedEntry`

## pseudocode

```c

```

## disassembly

```asm
0x4b230  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x4b235  stloc.0
0x4b236  ldloc.0
0x4b237  ldarg.s  6
0x4b239  callvirt instance void Microsoft.Crm.SharedDatabase.IDatabaseService::set_DatacenterId(valuetype [mscorlib]System.Guid value)
0x4b23e  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4b243  stloc.1
0x4b244  ldloc.1
0x4b245  ldstr    aAuditentryid_0// "AuditEntryId"
0x4b24a  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4b24f  box      [mscorlib]System.Guid
0x4b254  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b259  ldloc.1
0x4b25a  ldstr    aOrganizationid_1// "OrganizationId"
0x4b25f  ldarg.s  5
0x4b261  box      [mscorlib]System.Guid
0x4b266  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b26b  ldloc.1
0x4b26c  ldstr    aObjectid_0// "ObjectId"
0x4b271  ldarg.0
0x4b272  box      [mscorlib]System.Guid
0x4b277  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b27c  ldloc.1
0x4b27d  ldstr    aObjecttype_0// "ObjectType"
0x4b282  ldarg.1
0x4b283  call     string Microsoft.Crm.ConfigurationDatabase.AuditHistory::TruncateTo40Characters(string input)
0x4b288  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b28d  ldloc.1
0x4b28e  ldstr    aOperation_1// "Operation"
0x4b293  ldarg.2
0x4b294  call     string Microsoft.Crm.ConfigurationDatabase.AuditHistory::TruncateTo40Characters(string input)
0x4b299  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b29e  ldloc.1
0x4b29f  ldstr    aDetails_0// "Details"
0x4b2a4  ldarg.3
0x4b2a5  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b2aa  ldloc.1
0x4b2ab  ldstr    aCreatedon// "CreatedOn"
0x4b2b0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4b2b5  box      [mscorlib]System.DateTime
0x4b2ba  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b2bf  ldloc.1
0x4b2c0  ldstr    aModifiedon// "ModifiedOn"
0x4b2c5  ldloc.1
0x4b2c6  ldstr    aCreatedon// "CreatedOn"
0x4b2cb  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4b2d0  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b2d5  ldloc.1
0x4b2d6  ldstr    aResult_0// "Result"
0x4b2db  ldarg.s  4
0x4b2dd  brtrue.s loc_4B2E2
0x4b2df  ldc.i4.2
0x4b2e0  br.s     loc_4B2E3
0x4b2e2  ldc.i4.1
0x4b2e3  box      [mscorlib]System.Int32
0x4b2e8  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b2ed  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0x4b2f2  stloc.2
0x4b2f3  ldloc.1
0x4b2f4  ldstr    aUsername_0// "UserName"
0x4b2f9  ldloc.2
0x4b2fa  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x4b2ff  call     string Microsoft.Crm.ConfigurationDatabase.AuditHistory::TruncateTo40Characters(string input)
0x4b304  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b309  leave.s  loc_4B315
0x4b30b  ldloc.2
0x4b30c  brfalse.s loc_4B314
0x4b30e  ldloc.2
0x4b30f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4b314  endfinally
0x4b315  ldloc.0
0x4b316  ldstr    aAudithistory// "AuditHistory"
0x4b31b  ldloc.1
0x4b31c  ldc.i4   0x9B
0x4b321  ldstr    aCreatecomplete// "CreateCompletedEntry"
0x4b326  ldstr    aDA1SSrcPlatfor_34// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4b32b  callvirt instance object Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4b330  pop
0x4b331  leave.s  loc_4B33D
0x4b333  ldloc.0
0x4b334  brfalse.s loc_4B33C
0x4b336  ldloc.0
0x4b337  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4b33c  endfinally
0x4b33d  ret
```
