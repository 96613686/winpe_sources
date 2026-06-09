# Microsoft.Crm.Metadata.OptionSetService::Delete_1

- ea: `0x4b5c0`
- end: `0x4b66c`
- name: `Microsoft.Crm.Metadata.OptionSetService::Delete_1`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x4b5a0`
- `0x60950`

## callees

- `0x4b5c0`
- `0x4b960`
- `0x5a810`

## string_xrefs

- `0x4b5ee`: `prvDeleteOptionSet`
- `0x4b64c`: `OptionSetService.Delete caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4b5c0  ldarg.1
0x4b5c1  ldstr    aOptionsetid_0// "optionSetId"
0x4b5c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x4b5cb  ldarg.2
0x4b5cc  ldstr    aMetadatahelper// "metadataHelper"
0x4b5d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4b5d6  ldarg.3
0x4b5d7  ldstr    aContext// "context"
0x4b5dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4b5e1  ldarg.3
0x4b5e2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4b5e7  pop
0x4b5e8  ldarg.3
0x4b5e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4b5ee  ldstr    aPrvdeleteoptio// "prvDeleteOptionSet"
0x4b5f3  ldarg.3
0x4b5f4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4b5f9  ldarg.3
0x4b5fa  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4b5ff  ldarg.3
0x4b600  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x4b605  stloc.0
0x4b606  ldarg.1
0x4b607  ldarg.3
0x4b608  call     void Microsoft.Crm.Metadata.OptionSetService::ValidateForDelete(valuetype [mscorlib]System.Guid optionSetId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4b60d  ldarg.3
0x4b60e  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4b613  stloc.1
0x4b614  ldloc.1
0x4b615  ldarg.1
0x4b616  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_OptionSetId(valuetype [mscorlib]System.Guid)
0x4b61b  ldarg.2
0x4b61c  ldloc.1
0x4b61d  ldc.i4.2
0x4b61e  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IOptionSetDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType)
0x4b623  ldarg.2
0x4b624  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x4b629  ldarg.1
0x4b62a  ldc.i4.s 9
0x4b62c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker::.ctor(valuetype [mscorlib]System.Guid, int32)
0x4b631  ldarg.3
0x4b632  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentHelper::DeleteFromAllSolutions(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4b637  ldloc.0
0x4b638  brfalse.s loc_4B640
0x4b63a  ldarg.3
0x4b63b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x4b640  leave.s  loc_4B66B
0x4b642  stloc.2
0x4b643  ldloc.2
0x4b644  ldarg.3
0x4b645  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4b64a  ldc.i4.s 0x19
0x4b64c  ldstr    aOptionsetservi_1// "OptionSetService.Delete caught exceptio"...
0x4b651  ldc.i4.1
0x4b652  newarr   [mscorlib]System.Object
0x4b657  dup
0x4b658  ldc.i4.0
0x4b659  ldloc.2
0x4b65a  stelem.ref
0x4b65b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4b660  ldloc.0
0x4b661  brfalse.s loc_4B669
0x4b663  ldarg.3
0x4b664  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x4b669  rethrow
0x4b66b  ret
```
