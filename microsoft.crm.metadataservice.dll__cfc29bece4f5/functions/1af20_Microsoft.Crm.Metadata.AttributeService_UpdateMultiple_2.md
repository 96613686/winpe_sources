# Microsoft.Crm.Metadata.AttributeService::UpdateMultiple_2

- ea: `0x1af20`
- end: `0x1afbe`
- name: `Microsoft.Crm.Metadata.AttributeService::UpdateMultiple_2`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1aec0`
- `0x1af10`

## callees

- `0x1af20`
- `0x1e410`
- `0x5a810`

## string_xrefs

- `0x1af2f`: `prvWriteAttribute`
- `0x1af9d`: `AttributeService.Update caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1af20  ldarg.s  4
0x1af22  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1af27  pop
0x1af28  ldarg.s  4
0x1af2a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1af2f  ldstr    aPrvwriteattrib// "prvWriteAttribute"
0x1af34  ldarg.s  4
0x1af36  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1af3b  ldarg.s  4
0x1af3d  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1af42  ldarg.s  4
0x1af44  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x1af49  stloc.0
0x1af4a  ldarg.s  4
0x1af4c  ldarg.s  4
0x1af4e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1af53  ldc.i4.1
0x1af54  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x1af59  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x1af5e  stloc.1
0x1af5f  ldc.i4.0
0x1af60  stloc.2
0x1af61  br.s     loc_1AF7A
0x1af63  ldarg.1
0x1af64  ldloc.2
0x1af65  ldelem   [mscorlib]System.Guid
0x1af6a  ldarg.2
0x1af6b  ldloc.2
0x1af6c  ldelem.ref
0x1af6d  ldloc.1
0x1af6e  ldarg.3
0x1af6f  ldarg.s  4
0x1af71  call     void Microsoft.Crm.Metadata.AttributeService::UpdateInternal(valuetype [mscorlib]System.Guid attributeId, class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, bool mergeLabels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1af76  ldloc.2
0x1af77  ldc.i4.1
0x1af78  add
0x1af79  stloc.2
0x1af7a  ldloc.2
0x1af7b  ldarg.1
0x1af7c  ldlen
0x1af7d  conv.i4
0x1af7e  blt.s    loc_1AF63
0x1af80  ldloc.1
0x1af81  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x1af86  ldloc.0
0x1af87  brfalse.s loc_1AF90
0x1af89  ldarg.s  4
0x1af8b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x1af90  leave.s  loc_1AFBD
0x1af92  stloc.3
0x1af93  ldloc.3
0x1af94  ldarg.s  4
0x1af96  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1af9b  ldc.i4.s 0x19
0x1af9d  ldstr    aAttributeservi_1// "AttributeService.Update caught exceptio"...
0x1afa2  ldc.i4.1
0x1afa3  newarr   [mscorlib]System.Object
0x1afa8  dup
0x1afa9  ldc.i4.0
0x1afaa  ldloc.3
0x1afab  stelem.ref
0x1afac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1afb1  ldloc.0
0x1afb2  brfalse.s loc_1AFBB
0x1afb4  ldarg.s  4
0x1afb6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x1afbb  rethrow
0x1afbd  ret
```
