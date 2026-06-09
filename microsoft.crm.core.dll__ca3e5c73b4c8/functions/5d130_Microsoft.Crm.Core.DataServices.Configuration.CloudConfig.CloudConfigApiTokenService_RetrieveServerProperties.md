# Microsoft.Crm.Core.DataServices.Configuration.CloudConfig.CloudConfigApiTokenService::RetrieveServerProperties

- ea: `0x5d130`
- end: `0x5d167`
- name: `Microsoft.Crm.Core.DataServices.Configuration.CloudConfig.CloudConfigApiTokenService::RetrieveServerProperties`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x64af0`

## string_xrefs

- `0x5d146`: `AppIdUri`
- `0x5d15c`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\CloudConfig\CloudConfigApiTokenService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x5d130  ldarg.1
0x5d131  ldstr    aAzureapplicati// "AzureApplication"
0x5d136  ldc.i4.3
0x5d137  newarr   [mscorlib]System.String
0x5d13c  dup
0x5d13d  ldc.i4.0
0x5d13e  ldstr    aClientid// "ClientId"
0x5d143  stelem.ref
0x5d144  dup
0x5d145  ldc.i4.1
0x5d146  ldstr    aAppiduri// "AppIdUri"
0x5d14b  stelem.ref
0x5d14c  dup
0x5d14d  ldc.i4.2
0x5d14e  ldstr    aDomain// "Domain"
0x5d153  stelem.ref
0x5d154  ldarg.3
0x5d155  ldc.i4.s 0x20
0x5d157  ldstr    aRetrieveserver// "RetrieveServerProperties"
0x5d15c  ldstr    aDA1SSrcPlatfor_41// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x5d161  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x5d166  ret
```
