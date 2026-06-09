# Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlementId

- ea: `0x11c70`
- end: `0x11d8e`
- name: `Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlementId`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x11890`

## callees

- `0x11470`
- `0x11c70`

## pseudocode

```c

```

## disassembly

```asm
0x11c70  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11c75  stloc.0
0x11c76  ldarg.2
0x11c77  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11c7c  stobj    [mscorlib]System.Guid
0x11c81  ldarg.1
0x11c82  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11c87  ldstr    aEntitlementid// "entitlementid"
0x11c8c  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11c91  brfalse.s loc_11CC6
0x11c93  ldarg.1
0x11c94  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11c99  ldstr    aEntitlementid// "entitlementid"
0x11c9e  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11ca3  brfalse.s loc_11CC6
0x11ca5  ldarg.2
0x11ca6  ldarg.1
0x11ca7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11cac  ldstr    aEntitlementid// "entitlementid"
0x11cb1  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11cb6  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x11cbb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x11cc0  stobj    [mscorlib]System.Guid
0x11cc5  ret
0x11cc6  ldarg.s  4
0x11cc8  brfalse.s loc_11CFF
0x11cca  ldarg.0
0x11ccb  brfalse.s loc_11CFF
0x11ccd  ldarg.0
0x11cce  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11cd3  ldstr    aEntitlementid// "entitlementid"
0x11cd8  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11cdd  brfalse  loc_11D67
0x11ce2  ldarg.0
0x11ce3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11ce8  ldstr    aEntitlementid// "entitlementid"
0x11ced  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11cf2  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x11cf7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x11cfc  stloc.0
0x11cfd  br.s     loc_11D67
0x11cff  ldarg.s  4
0x11d01  brfalse.s loc_11D67
0x11d03  ldarg.3
0x11d04  ldind.ref
0x11d05  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_Stage()
0x11d0a  ldc.i4.s 0x14
0x11d0c  bne.un.s loc_11D67
0x11d0e  ldarg.1
0x11d0f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11d14  ldstr    aIncidentid// "incidentid"
0x11d19  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11d1e  unbox.any [mscorlib]System.Guid
0x11d23  ldstr    aIncident// "Incident"
0x11d28  ldnull
0x11d29  ldc.i4.1
0x11d2a  newarr   [mscorlib]System.String
0x11d2f  dup
0x11d30  ldc.i4.0
0x11d31  ldstr    aEntitlementid// "entitlementid"
0x11d36  stelem.ref
0x11d37  ldarg.3
0x11d38  ldind.ref
0x11d39  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x11d3e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(valuetype [mscorlib]System.Guid id, string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x11d43  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident
0x11d48  stloc.1
0x11d49  ldloc.1
0x11d4a  ldstr    aEntitlementid// "entitlementid"
0x11d4f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11d54  brfalse.s loc_11D67
0x11d56  ldloc.1
0x11d57  ldstr    aEntitlementid// "entitlementid"
0x11d5c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11d61  unbox.any [mscorlib]System.Guid
0x11d66  stloc.0
0x11d67  ldloc.0
0x11d68  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11d6d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11d72  brfalse.s loc_11D8D
0x11d74  ldarg.1
0x11d75  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11d7a  ldstr    aEntitlementid// "entitlementid"
0x11d7f  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11d84  brtrue.s loc_11D8D
0x11d86  ldarg.2
0x11d87  ldloc.0
0x11d88  stobj    [mscorlib]System.Guid
0x11d8d  ret
```
