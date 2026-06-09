# Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::UpdateOldEntitlementTerms

- ea: `0x111d0`
- end: `0x1127a`
- name: `Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::UpdateOldEntitlementTerms`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10bc0`

## callees

- `0x111d0`
- `0x11310`
- `0x11370`
- `0x11470`

## pseudocode

```c

```

## disassembly

```asm
0x111d0  ldarg.1
0x111d1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x111d6  ldstr    aEntitlementid// "entitlementid"
0x111db  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x111e0  brfalse  loc_11279
0x111e5  ldarg.1
0x111e6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x111eb  ldstr    aEntitlementid// "entitlementid"
0x111f0  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x111f5  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x111fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x111ff  ldstr    aEntitlement// "Entitlement"
0x11204  ldnull
0x11205  ldc.i4.6
0x11206  newarr   [mscorlib]System.String
0x1120b  dup
0x1120c  ldc.i4.0
0x1120d  ldstr    aRemainingterms// "remainingterms"
0x11212  stelem.ref
0x11213  dup
0x11214  ldc.i4.1
0x11215  ldstr    aTotalterms// "totalterms"
0x1121a  stelem.ref
0x1121b  dup
0x1121c  ldc.i4.2
0x1121d  ldstr    aDecreaseremain// "decreaseremainingon"
0x11222  stelem.ref
0x11223  dup
0x11224  ldc.i4.3
0x11225  ldstr    aAllocationtype// "allocationtypecode"
0x1122a  stelem.ref
0x1122b  dup
0x1122c  ldc.i4.4
0x1122d  ldstr    aSlaid// "slaid"
0x11232  stelem.ref
0x11233  dup
0x11234  ldc.i4.5
0x11235  ldstr    aOwnerid// "ownerid"
0x1123a  stelem.ref
0x1123b  ldarg.2
0x1123c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x11241  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(valuetype [mscorlib]System.Guid id, string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x11246  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement
0x1124b  stloc.0
0x1124c  ldloc.0
0x1124d  brfalse.s loc_11279
0x1124f  ldarg.0
0x11250  ldloc.0
0x11251  ldc.i4.1
0x11252  ldarg.2
0x11253  call     instance void Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::ValidateAndDecreaseOrIncreaseTerms(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement entitlement, bool isIncrease, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x11258  ldarg.1
0x11259  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1125e  ldstr    aCaseorigincode// "caseorigincode"
0x11263  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11268  brfalse.s loc_11279
0x1126a  ldarg.0
0x1126b  ldarg.1
0x1126c  ldloc.0
0x1126d  ldc.i4.1
0x1126e  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::One
0x11273  ldarg.2
0x11274  call     instance void Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::DecreaseOrIncreaseChannelTerms(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement entitlement, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x11279  ret
```
