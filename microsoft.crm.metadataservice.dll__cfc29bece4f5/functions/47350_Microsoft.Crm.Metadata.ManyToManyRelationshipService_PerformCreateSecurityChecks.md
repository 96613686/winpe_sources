# Microsoft.Crm.Metadata.ManyToManyRelationshipService::PerformCreateSecurityChecks

- ea: `0x47350`
- end: `0x4737f`
- name: `Microsoft.Crm.Metadata.ManyToManyRelationshipService::PerformCreateSecurityChecks`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x5a810`

## string_xrefs

- `0x4736d`: `prvReadRelationship`
- `0x47356`: `prvCreateRelationship`

## pseudocode

```c

```

## disassembly

```asm
0x47350  ldarg.1
0x47351  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x47356  ldstr    aPrvcreaterelat// "prvCreateRelationship"
0x4735b  ldarg.1
0x4735c  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x47361  ldarg.1
0x47362  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x47367  ldarg.1
0x47368  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4736d  ldstr    aPrvreadrelatio// "prvReadRelationship"
0x47372  ldarg.1
0x47373  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x47378  ldarg.1
0x47379  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4737e  ret
```
