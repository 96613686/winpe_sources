# Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::CheckThatOperationIsAllowedToExecute

- ea: `0xc20`
- end: `0xc86`
- name: `Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::CheckThatOperationIsAllowedToExecute`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xb40`
- `0xc20`
- `0x5a810`

## string_xrefs

- `0xc48`: `prvReadSqlEncryptionKey`
- `0xc50`: `prvReadSqlEncryptionKey`

## pseudocode

```c

```

## disassembly

```asm
0xc20  ldarg.1
0xc21  switch   loc_C38, loc_C40, loc_C48, loc_C50
0xc36  br.s     loc_C58
0xc38  ldstr    aPrvchangesqlen// "prvChangeSqlEncryptionKey"
0xc3d  stloc.0
0xc3e  br.s     loc_C63
0xc40  ldstr    aPrvrestoresqle// "prvRestoreSqlEncryptionKey"
0xc45  stloc.0
0xc46  br.s     loc_C63
0xc48  ldstr    aPrvreadsqlencr// "prvReadSqlEncryptionKey"
0xc4d  stloc.0
0xc4e  br.s     loc_C63
0xc50  ldstr    aPrvreadsqlencr// "prvReadSqlEncryptionKey"
0xc55  stloc.0
0xc56  br.s     loc_C63
0xc58  ldstr    aUnknonwOperati// "Unknonw OperationType"
0xc5d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string)
0xc62  throw
0xc63  ldarg.0
0xc64  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::get_Context()
0xc69  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xc6e  ldloc.0
0xc6f  ldarg.0
0xc70  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::get_Context()
0xc75  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xc7a  ldarg.0
0xc7b  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::get_Context()
0xc80  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc85  ret
```
