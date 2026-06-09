# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ImpersonateUserForSLAWorkflows

- ea: `0x126d0`
- end: `0x1274c`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ImpersonateUserForSLAWorkflows`
- size: `124`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x10900`
- `0x12350`
- `0x12fe0`
- `0x13290`

## callees

- `0x126d0`

## pseudocode

```c

```

## disassembly

```asm
0x126d0  ldnull
0x126d1  stloc.0
0x126d2  ldarg.3
0x126d3  brfalse.s loc_126FB
0x126d5  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PublishHelper::.ctor()
0x126da  ldarg.2
0x126db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_OrganizationId()
0x126e0  ldarg.2
0x126e1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x126e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PublishHelper::GetOrganizationSystemUserId(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x126eb  stloc.1
0x126ec  ldarg.0
0x126ed  ldloc.1
0x126ee  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x126f3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x126f8  stloc.0
0x126f9  br.s     loc_1274A
0x126fb  ldarg.1
0x126fc  brfalse.s loc_12738
0x126fe  ldarg.1
0x126ff  ldstr    aOwnerid// "ownerid"
0x12704  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x12709  brfalse.s loc_12738
0x1270b  ldarg.0
0x1270c  ldarg.1
0x1270d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x12712  ldstr    aOwnerid// "ownerid"
0x12717  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x1271c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x12721  callvirt instance string [mscorlib]System.Object::ToString()
0x12726  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1272b  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x12730  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x12735  stloc.0
0x12736  br.s     loc_1274A
0x12738  ldarg.0
0x12739  ldarg.2
0x1273a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InitiatingUserId()
0x1273f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x12744  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x12749  stloc.0
0x1274a  ldloc.0
0x1274b  ret
```
