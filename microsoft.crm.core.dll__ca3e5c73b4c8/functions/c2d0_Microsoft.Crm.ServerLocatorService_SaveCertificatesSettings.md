# Microsoft.Crm.ServerLocatorService::SaveCertificatesSettings

- ea: `0xc2d0`
- end: `0xc353`
- name: `Microsoft.Crm.ServerLocatorService::SaveCertificatesSettings`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x92c0`
- `0xc2d0`
- `0x4d750`
- `0x61910`
- `0x62440`

## string_xrefs

- `0xc2fa`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xc31d`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xc33b`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc2d0  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xc2d5  stloc.0
0xc2d6  ldarg.0
0xc2d7  ldstr    aCertificates// "Certificates"
0xc2dc  ldarg.1
0xc2dd  box      [mscorlib]System.Guid
0xc2e2  ldc.i4.1
0xc2e3  newarr   [mscorlib]System.String
0xc2e8  dup
0xc2e9  ldc.i4.0
0xc2ea  ldstr    aId// "Id"
0xc2ef  stelem.ref
0xc2f0  ldc.i4   0xE1A
0xc2f5  ldstr    aSavecertificat// "SaveCertificatesSettings"
0xc2fa  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc2ff  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc304  brfalse.s loc_C32A
0xc306  ldloc.0
0xc307  ldstr    aCertificates// "Certificates"
0xc30c  ldarg.1
0xc30d  box      [mscorlib]System.Guid
0xc312  ldarg.2
0xc313  ldc.i4   0xE1E
0xc318  ldstr    aSavecertificat// "SaveCertificatesSettings"
0xc31d  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc322  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, object id, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc327  pop
0xc328  leave.s  loc_C352
0xc32a  ldloc.0
0xc32b  ldstr    aCertificates// "Certificates"
0xc330  ldarg.2
0xc331  ldc.i4   0xE22
0xc336  ldstr    aSavecertificat// "SaveCertificatesSettings"
0xc33b  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc340  callvirt instance object Microsoft.Crm.SharedDatabase.DatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc345  pop
0xc346  leave.s  loc_C352
0xc348  ldloc.0
0xc349  brfalse.s loc_C351
0xc34b  ldloc.0
0xc34c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc351  endfinally
0xc352  ret
```
