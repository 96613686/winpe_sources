# Microsoft.Crm.Metadata.AttributeService::Create_2

- ea: `0x1a7d0`
- end: `0x1a8b0`
- name: `Microsoft.Crm.Metadata.AttributeService::Create_2`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a7b0`

## callees

- `0x184e0`
- `0x18760`
- `0x1a7d0`
- `0x1c120`
- `0x21220`
- `0x23e60`
- `0x5a810`

## string_xrefs

- `0x1a7f9`: `prvReadAttribute`
- `0x1a7df`: `prvCreateAttribute`
- `0x1a88d`: `AttributeService.Create caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1a7d0  ldarg.s  4
0x1a7d2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a7d7  pop
0x1a7d8  ldarg.s  4
0x1a7da  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1a7df  ldstr    aPrvcreateattri// "prvCreateAttribute"
0x1a7e4  ldarg.s  4
0x1a7e6  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a7eb  ldarg.s  4
0x1a7ed  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a7f2  ldarg.s  4
0x1a7f4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1a7f9  ldstr    aPrvreadattribu// "prvReadAttribute"
0x1a7fe  ldarg.s  4
0x1a800  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a805  ldarg.s  4
0x1a807  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a80c  ldarg.s  4
0x1a80e  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x1a813  stloc.0
0x1a814  ldarg.s  4
0x1a816  ldc.i4.1
0x1a817  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x1a81c  stloc.2
0x1a81d  ldarg.2
0x1a81e  ldarg.1
0x1a81f  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::set_EntityId(valuetype [mscorlib]System.Guid value)
0x1a824  ldarg.2
0x1a825  ldarg.3
0x1a826  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x1a82b  ldc.i4.0
0x1a82c  ceq
0x1a82e  ldarg.s  4
0x1a830  ldarg.3
0x1a831  call     void Microsoft.Crm.Metadata.AttributeService::ValidateForCreate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, bool validateSchemaName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1a836  ldarg.2
0x1a837  ldarg.3
0x1a838  ldarg.s  4
0x1a83a  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a83f  stloc.1
0x1a840  ldarg.3
0x1a841  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x1a846  ldarg.2
0x1a847  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1a84c  ldarg.s  4
0x1a84e  ldc.i4.0
0x1a84f  call     void Microsoft.Crm.Metadata.AttributeService::SetRollupProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attribute, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool IsInstallOrPatch)
0x1a854  ldarg.s  4
0x1a856  ldc.i4.4
0x1a857  ldloc.1
0x1a858  ldc.i4.2
0x1a859  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x1a85e  ldloc.0
0x1a85f  brfalse.s loc_1A868
0x1a861  ldarg.s  4
0x1a863  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x1a868  ldarg.2
0x1a869  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1a86e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x1a873  stloc.3
0x1a874  leave.s  loc_1A8AE
0x1a876  ldloc.2
0x1a877  brfalse.s loc_1A87F
0x1a879  ldloc.2
0x1a87a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a87f  endfinally
0x1a880  stloc.s  4
0x1a882  ldloc.s  4
0x1a884  ldarg.s  4
0x1a886  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1a88b  ldc.i4.s 0x19
0x1a88d  ldstr    aAttributeservi// "AttributeService.Create caught exceptio"...
0x1a892  ldc.i4.1
0x1a893  newarr   [mscorlib]System.Object
0x1a898  dup
0x1a899  ldc.i4.0
0x1a89a  ldloc.s  4
0x1a89c  stelem.ref
0x1a89d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a8a2  ldloc.0
0x1a8a3  brfalse.s loc_1A8AC
0x1a8a5  ldarg.s  4
0x1a8a7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x1a8ac  rethrow
0x1a8ae  ldloc.3
0x1a8af  ret
```
