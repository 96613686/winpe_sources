# Microsoft.Crm.Metadata.AttributeService::Update_4

- ea: `0x1ada0`
- end: `0x1ae61`
- name: `Microsoft.Crm.Metadata.AttributeService::Update_4`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ad50`

## callees

- `0x18760`
- `0x1ada0`
- `0x1ae80`
- `0x23dc0`
- `0x5a810`

## string_xrefs

- `0x1adaf`: `prvWriteAttribute`
- `0x1ae40`: `AttributeService.Update caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1ada0  ldarg.s  5
0x1ada2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ada7  pop
0x1ada8  ldarg.s  5
0x1adaa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1adaf  ldstr    aPrvwriteattrib// "prvWriteAttribute"
0x1adb4  ldarg.s  5
0x1adb6  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1adbb  ldarg.s  5
0x1adbd  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1adc2  ldarg.s  5
0x1adc4  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x1adc9  stloc.0
0x1adca  ldarg.s  5
0x1adcc  ldc.i4.1
0x1adcd  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x1add2  stloc.1
0x1add3  ldarg.0
0x1add4  ldarg.1
0x1add5  ldarg.2
0x1add6  ldarg.s  5
0x1add8  ldarg.s  4
0x1adda  ldarg.3
0x1addb  call     instance void Microsoft.Crm.Metadata.AttributeService::UpdateNoPrivilegeChecks(valuetype [mscorlib]System.Guid attributeId, class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, bool mergeLabels)
0x1ade0  ldarg.s  4
0x1ade2  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x1ade7  ldarg.s  5
0x1ade9  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SolutionImportContext()
0x1adee  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x1adf3  ldc.i4.1
0x1adf4  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x1adf9  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x1adfe  brtrue.s loc_1AE13
0x1ae00  ldarg.2
0x1ae01  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1ae06  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1ae0b  ldarg.s  5
0x1ae0d  call     bool Microsoft.Crm.Metadata.AttributeService::TryRegenerateRollupProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attribute, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> attributesInSolution, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ae12  pop
0x1ae13  ldarg.s  5
0x1ae15  ldc.i4.4
0x1ae16  ldarg.1
0x1ae17  ldc.i4.2
0x1ae18  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x1ae1d  ldloc.0
0x1ae1e  brfalse.s loc_1AE27
0x1ae20  ldarg.s  5
0x1ae22  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x1ae27  leave.s  loc_1AE33
0x1ae29  ldloc.1
0x1ae2a  brfalse.s loc_1AE32
0x1ae2c  ldloc.1
0x1ae2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ae32  endfinally
0x1ae33  leave.s  loc_1AE60
0x1ae35  stloc.2
0x1ae36  ldloc.2
0x1ae37  ldarg.s  5
0x1ae39  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1ae3e  ldc.i4.s 0x19
0x1ae40  ldstr    aAttributeservi_1// "AttributeService.Update caught exceptio"...
0x1ae45  ldc.i4.1
0x1ae46  newarr   [mscorlib]System.Object
0x1ae4b  dup
0x1ae4c  ldc.i4.0
0x1ae4d  ldloc.2
0x1ae4e  stelem.ref
0x1ae4f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ae54  ldloc.0
0x1ae55  brfalse.s loc_1AE5E
0x1ae57  ldarg.s  5
0x1ae59  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x1ae5e  rethrow
0x1ae60  ret
```
