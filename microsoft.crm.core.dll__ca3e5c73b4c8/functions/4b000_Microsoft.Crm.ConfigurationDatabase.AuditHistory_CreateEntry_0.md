# Microsoft.Crm.ConfigurationDatabase.AuditHistory::CreateEntry_0

- ea: `0x4b000`
- end: `0x4b0ec`
- name: `Microsoft.Crm.ConfigurationDatabase.AuditHistory::CreateEntry_0`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4b0f0`

## callees

- `0x44400`
- `0x44510`
- `0x4b000`
- `0x4b510`
- `0x4d7e0`
- `0x64b30`

## string_xrefs

- `0x4b06c`: `CreatedOn`
- `0x4b0ce`: `CreateEntry`
- `0x4b0d3`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\AuditHistory.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4b000  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x4b005  stloc.0
0x4b006  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4b00b  stloc.1
0x4b00c  ldloc.1
0x4b00d  ldstr    aAuditentryid_0// "AuditEntryId"
0x4b012  ldarg.1
0x4b013  box      [mscorlib]System.Guid
0x4b018  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b01d  ldloc.1
0x4b01e  ldstr    aObjectid_0// "ObjectId"
0x4b023  ldarg.2
0x4b024  box      [mscorlib]System.Guid
0x4b029  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b02e  ldloc.1
0x4b02f  ldstr    aObjecttype_0// "ObjectType"
0x4b034  ldarg.3
0x4b035  call     string Microsoft.Crm.ConfigurationDatabase.AuditHistory::TruncateTo40Characters(string input)
0x4b03a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b03f  ldloc.1
0x4b040  ldstr    aOperation_1// "Operation"
0x4b045  ldarg.s  4
0x4b047  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b04c  ldloc.1
0x4b04d  ldstr    aOperation_1// "Operation"
0x4b052  ldarg.s  4
0x4b054  call     string Microsoft.Crm.ConfigurationDatabase.AuditHistory::TruncateTo40Characters(string input)
0x4b059  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b05e  ldloc.1
0x4b05f  ldstr    aDetails_0// "Details"
0x4b064  ldarg.s  5
0x4b066  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b06b  ldloc.1
0x4b06c  ldstr    aCreatedon// "CreatedOn"
0x4b071  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4b076  box      [mscorlib]System.DateTime
0x4b07b  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b080  ldloc.1
0x4b081  ldstr    aModifiedon// "ModifiedOn"
0x4b086  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4b08b  box      [mscorlib]System.DateTime
0x4b090  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b095  ldloc.1
0x4b096  ldstr    aUsername_0// "UserName"
0x4b09b  ldarg.s  6
0x4b09d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b0a2  ldloc.1
0x4b0a3  ldstr    aUsername_0// "UserName"
0x4b0a8  ldarg.s  6
0x4b0aa  call     string Microsoft.Crm.ConfigurationDatabase.AuditHistory::TruncateTo40Characters(string input)
0x4b0af  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b0b4  ldloc.1
0x4b0b5  ldstr    aResult_0// "Result"
0x4b0ba  ldc.i4.0
0x4b0bb  box      [mscorlib]System.Int32
0x4b0c0  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4b0c5  ldloc.0
0x4b0c6  ldstr    aAudithistory// "AuditHistory"
0x4b0cb  ldloc.1
0x4b0cc  ldc.i4.s 0x4B
0x4b0ce  ldstr    aCreateentry// "CreateEntry"
0x4b0d3  ldstr    aDA1SSrcPlatfor_34// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4b0d8  callvirt instance object Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4b0dd  pop
0x4b0de  leave.s  loc_4B0EA
0x4b0e0  ldloc.0
0x4b0e1  brfalse.s loc_4B0E9
0x4b0e3  ldloc.0
0x4b0e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4b0e9  endfinally
0x4b0ea  ldarg.1
0x4b0eb  ret
```
