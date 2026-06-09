# Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::OnKeepAliveEvent

- ea: `0x4e8d0`
- end: `0x4e957`
- name: `Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::OnKeepAliveEvent`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1f510`
- `0x44400`
- `0x44510`
- `0x4d7e0`
- `0x4e8d0`
- `0x64b60`

## string_xrefs

- `0x4e90f`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LongConfigDbLock.cs`
- `0x4e93e`: `Unhandled error in LongConfigDbLock KeepAliveEvent : `

## pseudocode

```c

```

## disassembly

```asm
0x4e8d0  ldarg.0
0x4e8d1  ldfld    bool Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_disposed
0x4e8d6  brfalse.s loc_4E8DA
0x4e8d8  leave.s  loc_4E956
0x4e8da  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x4e8df  stloc.0
0x4e8e0  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4e8e5  stloc.1
0x4e8e6  ldloc.1
0x4e8e7  ldstr    aModifiedon// "ModifiedOn"
0x4e8ec  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4e8f1  box      [mscorlib]System.DateTime
0x4e8f6  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4e8fb  ldloc.0
0x4e8fc  ldstr    aSitelock// "SiteLock"
0x4e901  ldarg.0
0x4e902  ldfld    string Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockName
0x4e907  ldloc.1
0x4e908  ldc.i4.s 0x6D
0x4e90a  ldstr    aOnkeepaliveeve// "OnKeepAliveEvent"
0x4e90f  ldstr    aDA1SSrcPlatfor_38// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4e914  callvirt instance int32 Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string tableName, object id, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4e919  pop
0x4e91a  leave.s  loc_4E926
0x4e91c  ldloc.0
0x4e91d  brfalse.s loc_4E925
0x4e91f  ldloc.0
0x4e920  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e925  endfinally
0x4e926  leave.s  loc_4E956
0x4e928  stloc.2
0x4e929  ldloc.2
0x4e92a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4e92f  ldc.i4.s 0x30
0x4e931  ldstr    a0// "{0}"
0x4e936  ldc.i4.1
0x4e937  newarr   [mscorlib]System.Object
0x4e93c  dup
0x4e93d  ldc.i4.0
0x4e93e  ldstr    aUnhandledError// "Unhandled error in LongConfigDbLock Kee"...
0x4e943  ldloc.2
0x4e944  callvirt instance string [mscorlib]System.Object::ToString()
0x4e949  call     string [mscorlib]System.String::Concat(string, string)
0x4e94e  stelem.ref
0x4e94f  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x4e954  leave.s  loc_4E956
0x4e956  ret
```
