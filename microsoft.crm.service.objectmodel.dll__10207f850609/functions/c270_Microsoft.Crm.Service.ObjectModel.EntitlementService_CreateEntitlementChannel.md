# Microsoft.Crm.Service.ObjectModel.EntitlementService::CreateEntitlementChannel

- ea: `0xc270`
- end: `0xc35c`
- name: `Microsoft.Crm.Service.ObjectModel.EntitlementService::CreateEntitlementChannel`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xb480`
- `0xc270`

## string_xrefs

- `0xc2c3`: `EntitlementTemplateChannel`
- `0xc2b4`: `entitlementtemplatechannelid`

## pseudocode

```c

```

## disassembly

```asm
0xc270  ldarg.1
0xc271  brfalse  loc_C35B
0xc276  ldarg.1
0xc277  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xc27c  ldc.i4.0
0xc27d  ble      loc_C35B
0xc282  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomizationService::.ctor()
0xc287  stloc.0
0xc288  ldarg.1
0xc289  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xc28e  stloc.1
0xc28f  br       loc_C33A
0xc294  ldloc.1
0xc295  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc29a  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xc29f  stloc.2
0xc2a0  newobj   instance void Microsoft.Crm.Service.ObjectModel.EntitlementChannelService::.ctor()
0xc2a5  stloc.3
0xc2a6  ldarg.2
0xc2a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xc2ac  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel::.ctor(valuetype [mscorlib]System.Guid)
0xc2b1  stloc.s  4
0xc2b3  ldloc.2
0xc2b4  ldstr    aEntitlementtem_2// "entitlementtemplatechannelid"
0xc2b9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xc2be  unbox.any [mscorlib]System.Guid
0xc2c3  ldstr    aEntitlementtem_0// "EntitlementTemplateChannel"
0xc2c8  ldarg.2
0xc2c9  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc2ce  stloc.s  5
0xc2d0  ldloc.2
0xc2d1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xc2d6  ldstr    aTotalterms// "totalterms"
0xc2db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xc2e0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xc2e5  brfalse.s loc_C33A
0xc2e7  ldloc.2
0xc2e8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xc2ed  ldstr    aChannel// "channel"
0xc2f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xc2f7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xc2fc  brfalse.s loc_C33A
0xc2fe  ldnull
0xc2ff  stloc.s  6
0xc301  ldloc.0
0xc302  ldloc.s  5
0xc304  ldloc.s  4
0xc306  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0xc30b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xc310  ldc.i4.1
0xc311  ldarg.2
0xc312  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomizationService::InitializeFrom(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TargetFieldType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc317  stloc.s  6
0xc319  ldloc.s  6
0xc31b  ldstr    aEntitlementid// "entitlementid"
0xc320  ldarg.3
0xc321  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xc326  box      [mscorlib]System.Guid
0xc32b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xc330  ldloc.3
0xc331  ldloc.s  6
0xc333  ldarg.2
0xc334  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc339  pop
0xc33a  ldloc.1
0xc33b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc340  brtrue   loc_C294
0xc345  leave.s  loc_C35B
0xc347  ldloc.1
0xc348  isinst   [mscorlib]System.IDisposable
0xc34d  stloc.s  7
0xc34f  ldloc.s  7
0xc351  brfalse.s loc_C35A
0xc353  ldloc.s  7
0xc355  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc35a  endfinally
0xc35b  ret
```
