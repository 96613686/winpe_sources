# Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::DecreaseOrIncreaseChannelTerms

- ea: `0x11370`
- end: `0x11444`
- name: `Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::DecreaseOrIncreaseChannelTerms`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10bc0`
- `0x111d0`

## callees

- `0x11350`
- `0x11370`
- `0x11510`

## pseudocode

```c

```

## disassembly

```asm
0x11370  ldarg.1
0x11371  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11376  ldstr    aCaseorigincode// "caseorigincode"
0x1137b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11380  brfalse  loc_11443
0x11385  ldarg.2
0x11386  brfalse  loc_11443
0x1138b  ldarg.2
0x1138c  ldstr    aAllocationtype// "allocationtypecode"
0x11391  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11396  unbox.any [mscorlib]System.Int32
0x1139b  brtrue   loc_11443
0x113a0  ldarg.2
0x113a1  ldstr    aDecreaseremain// "decreaseremainingon"
0x113a6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x113ab  unbox.any [mscorlib]System.Int32
0x113b0  ldc.i4.1
0x113b1  bne.un   loc_11443
0x113b6  ldstr    aEntitlementcha// "EntitlementChannel"
0x113bb  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x113c0  dup
0x113c1  ldstr    aEntitlementid// "entitlementid"
0x113c6  ldarg.2
0x113c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x113cc  ldstr    aEntitlementid// "entitlementid"
0x113d1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x113d6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x113db  callvirt instance string [mscorlib]System.Object::ToString()
0x113e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x113e5  dup
0x113e6  ldstr    aChannel// "channel"
0x113eb  ldarg.1
0x113ec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x113f1  ldstr    aCaseorigincode// "caseorigincode"
0x113f6  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x113fb  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x11400  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x11405  stloc.1
0x11406  ldloca.s 1
0x11408  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1140d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11412  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x11417  ldc.i4.1
0x11418  newarr   [mscorlib]System.String
0x1141d  dup
0x1141e  ldc.i4.0
0x1141f  ldstr    aRemainingterms// "remainingterms"
0x11424  stelem.ref
0x11425  ldarg.s  5
0x11427  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x1142c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x11431  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel
0x11436  stloc.0
0x11437  ldarg.0
0x11438  ldloc.0
0x11439  ldarg.3
0x1143a  ldarg.s  4
0x1143c  ldarg.s  5
0x1143e  call     instance void Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::ValidateAndDecreaseOrIncreaseChannelTerms(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel channel, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext pipelineContext)
0x11443  ret
```
