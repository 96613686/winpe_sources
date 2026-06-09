# Microsoft.Crm.Service.ObjectModel.CasePluginHelper::SetDefaultEntitlement

- ea: `0x115d0`
- end: `0x117a9`
- name: `Microsoft.Crm.Service.ObjectModel.CasePluginHelper::SetDefaultEntitlement`
- size: `473`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10830`
- `0x11f70`

## callees

- `0x11470`
- `0x115d0`
- `0x11b80`

## pseudocode

```c

```

## disassembly

```asm
0x115d0  ldsfld   string [mscorlib]System.String::Empty
0x115d5  stloc.0
0x115d6  ldsfld   string [mscorlib]System.String::Empty
0x115db  stloc.1
0x115dc  ldsfld   string [mscorlib]System.String::Empty
0x115e1  stloc.2
0x115e2  ldarg.0
0x115e3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x115e8  ldstr    aCustomerid// "customerid"
0x115ed  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x115f2  brfalse.s loc_1162F
0x115f4  ldarg.0
0x115f5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x115fa  ldstr    aCustomerid// "customerid"
0x115ff  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11604  brfalse.s loc_1162F
0x11606  ldarg.0
0x11607  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1160c  ldstr    aCustomerid// "customerid"
0x11611  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11616  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1161b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x11620  stloc.3
0x11621  ldloca.s 3
0x11623  constrained. [mscorlib]System.Guid
0x11629  callvirt instance string [mscorlib]System.Object::ToString()
0x1162e  stloc.2
0x1162f  ldarg.0
0x11630  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11635  ldstr    aPrimarycontact// "primarycontactid"
0x1163a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1163f  brfalse.s loc_1167C
0x11641  ldarg.0
0x11642  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11647  ldstr    aPrimarycontact// "primarycontactid"
0x1164c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11651  brfalse.s loc_1167C
0x11653  ldarg.0
0x11654  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11659  ldstr    aPrimarycontact// "primarycontactid"
0x1165e  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11663  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x11668  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1166d  stloc.3
0x1166e  ldloca.s 3
0x11670  constrained. [mscorlib]System.Guid
0x11676  callvirt instance string [mscorlib]System.Object::ToString()
0x1167b  stloc.0
0x1167c  ldarg.0
0x1167d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11682  ldstr    aProductid// "productid"
0x11687  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1168c  brfalse.s loc_116C9
0x1168e  ldarg.0
0x1168f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11694  ldstr    aProductid// "productid"
0x11699  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1169e  brfalse.s loc_116C9
0x116a0  ldarg.0
0x116a1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x116a6  ldstr    aProductid// "productid"
0x116ab  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x116b0  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x116b5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x116ba  stloc.3
0x116bb  ldloca.s 3
0x116bd  constrained. [mscorlib]System.Guid
0x116c3  callvirt instance string [mscorlib]System.Object::ToString()
0x116c8  stloc.1
0x116c9  ldarg.1
0x116ca  brfalse.s loc_11740
0x116cc  ldloc.2
0x116cd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x116d2  brfalse.s loc_11740
0x116d4  ldloc.0
0x116d5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x116da  brfalse.s loc_116E4
0x116dc  ldloc.1
0x116dd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x116e2  brtrue.s loc_11740
0x116e4  ldarg.2
0x116e5  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x116ea  stloc.s  4
0x116ec  ldarg.0
0x116ed  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x116f2  ldstr    aIncidentid// "incidentid"
0x116f7  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x116fc  unbox.any [mscorlib]System.Guid
0x11701  ldstr    aIncident// "Incident"
0x11706  ldnull
0x11707  ldc.i4.1
0x11708  newarr   [mscorlib]System.String
0x1170d  dup
0x1170e  ldc.i4.0
0x1170f  ldstr    aCustomerid// "customerid"
0x11714  stelem.ref
0x11715  ldloc.s  4
0x11717  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x1171c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(valuetype [mscorlib]System.Guid id, string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x11721  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident
0x11726  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x1172b  ldstr    aCustomerid// "customerid"
0x11730  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x11735  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x1173a  callvirt instance string [mscorlib]System.Object::ToString()
0x1173f  stloc.2
0x11740  ldloc.2
0x11741  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11746  brtrue.s loc_117A8
0x11748  ldloc.2
0x11749  ldloc.0
0x1174a  ldloc.1
0x1174b  ldarg.2
0x1174c  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetDefaultEntitlement(string customerId, string primaryContactId, string productId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext context)
0x11751  stloc.s  5
0x11753  ldloc.s  5
0x11755  brfalse.s loc_117A8
0x11757  ldarg.0
0x11758  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1175d  ldstr    aEntitlementid// "entitlementid"
0x11762  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11767  brfalse.s loc_1177E
0x11769  ldarg.0
0x1176a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1176f  ldstr    aEntitlementid// "entitlementid"
0x11774  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11779  ldnull
0x1177a  ceq
0x1177c  br.s     loc_1177F
0x1177e  ldc.i4.0
0x1177f  ldarg.1
0x11780  and
0x11781  brfalse.s loc_11796
0x11783  ldarg.0
0x11784  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11789  ldstr    aEntitlementid// "entitlementid"
0x1178e  ldloc.s  5
0x11790  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x11795  ret
0x11796  ldarg.0
0x11797  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1179c  ldstr    aEntitlementid// "entitlementid"
0x117a1  ldloc.s  5
0x117a3  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x117a8  ret
```
