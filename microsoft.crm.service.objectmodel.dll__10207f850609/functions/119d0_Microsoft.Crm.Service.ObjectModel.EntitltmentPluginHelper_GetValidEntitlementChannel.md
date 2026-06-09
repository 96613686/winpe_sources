# Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlementChannel

- ea: `0x119d0`
- end: `0x11b7b`
- name: `Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlementChannel`
- size: `427`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10830`
- `0x10900`
- `0x10b10`
- `0x11f70`

## callees

- `0x11470`
- `0x11510`
- `0x119d0`

## pseudocode

```c

```

## disassembly

```asm
0x119d0  ldarg.0
0x119d1  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x119d6  stloc.0
0x119d7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x119dc  stloc.1
0x119dd  ldarg.0
0x119de  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x119e3  ldstr    aTarget// "Target"
0x119e8  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x119ed  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x119f2  stloc.2
0x119f3  ldarg.1
0x119f4  brfalse.s loc_11A74
0x119f6  ldloc.2
0x119f7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x119fc  ldstr    aEntitlementid// "entitlementid"
0x11a01  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11a06  brtrue.s loc_11A74
0x11a08  ldloc.2
0x11a09  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11a0e  ldstr    aCaseorigincode// "caseorigincode"
0x11a13  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11a18  brfalse.s loc_11A74
0x11a1a  ldloc.2
0x11a1b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11a20  ldstr    aIncidentid// "incidentid"
0x11a25  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11a2a  unbox.any [mscorlib]System.Guid
0x11a2f  ldstr    aIncident// "Incident"
0x11a34  ldnull
0x11a35  ldc.i4.1
0x11a36  newarr   [mscorlib]System.String
0x11a3b  dup
0x11a3c  ldc.i4.0
0x11a3d  ldstr    aEntitlementid// "entitlementid"
0x11a42  stelem.ref
0x11a43  ldloc.0
0x11a44  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x11a49  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(valuetype [mscorlib]System.Guid id, string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x11a4e  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident
0x11a53  stloc.3
0x11a54  ldloc.3
0x11a55  ldstr    aEntitlementid// "entitlementid"
0x11a5a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11a5f  brfalse.s loc_11AB3
0x11a61  ldloc.3
0x11a62  ldstr    aEntitlementid// "entitlementid"
0x11a67  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11a6c  unbox.any [mscorlib]System.Guid
0x11a71  stloc.1
0x11a72  br.s     loc_11AB3
0x11a74  ldloc.2
0x11a75  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11a7a  ldstr    aEntitlementid// "entitlementid"
0x11a7f  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11a84  brfalse.s loc_11AB3
0x11a86  ldloc.2
0x11a87  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11a8c  ldstr    aEntitlementid// "entitlementid"
0x11a91  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11a96  brfalse.s loc_11AB3
0x11a98  ldloc.2
0x11a99  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11a9e  ldstr    aEntitlementid// "entitlementid"
0x11aa3  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11aa8  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x11aad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x11ab2  stloc.1
0x11ab3  ldloc.2
0x11ab4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11ab9  ldstr    aCaseorigincode// "caseorigincode"
0x11abe  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11ac3  brfalse.s loc_11AFD
0x11ac5  ldloc.2
0x11ac6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11acb  ldstr    aCaseorigincode// "caseorigincode"
0x11ad0  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11ad5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11ada  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x11adf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11ae4  brtrue.s loc_11AFD
0x11ae6  ldloc.1
0x11ae7  box      [mscorlib]System.Guid
0x11aec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11af1  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x11af6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11afb  brfalse.s loc_11AFF
0x11afd  ldnull
0x11afe  ret
0x11aff  ldstr    aEntitlementcha// "EntitlementChannel"
0x11b04  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x11b09  dup
0x11b0a  ldstr    aEntitlementid// "entitlementid"
0x11b0f  ldloca.s 1
0x11b11  constrained. [mscorlib]System.Guid
0x11b17  callvirt instance string [mscorlib]System.Object::ToString()
0x11b1c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x11b21  dup
0x11b22  ldstr    aChannel// "channel"
0x11b27  ldloc.2
0x11b28  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11b2d  ldstr    aCaseorigincode// "caseorigincode"
0x11b32  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11b37  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x11b3c  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x11b41  stloc.s  4
0x11b43  ldloca.s 4
0x11b45  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11b4a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11b4f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x11b54  ldc.i4.2
0x11b55  newarr   [mscorlib]System.String
0x11b5a  dup
0x11b5b  ldc.i4.0
0x11b5c  ldstr    aRemainingterms// "remainingterms"
0x11b61  stelem.ref
0x11b62  dup
0x11b63  ldc.i4.1
0x11b64  ldstr    aTotalterms// "totalterms"
0x11b69  stelem.ref
0x11b6a  ldloc.0
0x11b6b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x11b70  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x11b75  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementChannel
0x11b7a  ret
```
