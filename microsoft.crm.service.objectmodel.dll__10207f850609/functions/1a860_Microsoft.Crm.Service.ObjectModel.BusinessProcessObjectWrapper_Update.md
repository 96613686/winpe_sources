# Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::Update

- ea: `0x1a860`
- end: `0x1a919`
- name: `Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::Update`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7e20`

## callees

- `0x1a720`
- `0x1a860`
- `0x1aa30`

## string_xrefs

- `0x1a8fc`: `Service Telemetry Error:  {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1a860  ldarg.0
0x1a861  ldarg.1
0x1a862  ldarg.2
0x1a863  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a868  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1a86d  stloc.0
0x1a86e  ldarg.1
0x1a86f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_OrganizationId()
0x1a874  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(valuetype [mscorlib]System.Guid)
0x1a879  stloc.1
0x1a87a  ldloc.1
0x1a87b  ldarg.1
0x1a87c  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x1a881  pop
0x1a882  ldarg.0
0x1a883  ldloc.1
0x1a884  ldloc.0
0x1a885  ldarg.2
0x1a886  ldc.i4.0
0x1a887  newarr   [mscorlib]System.Object
0x1a88c  callvirt instance bool Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::CollectTelemetry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection entities, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> data, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, object[] messageParams)
0x1a891  brfalse.s loc_1A8EE
0x1a893  ldloc.0
0x1a894  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Result
0x1a899  ldc.i4.1
0x1a89a  stloc.2
0x1a89b  ldloca.s 2
0x1a89d  constrained. ResultType
0x1a8a3  callvirt instance string [mscorlib]System.Object::ToString()
0x1a8a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a8ad  ldloc.0
0x1a8ae  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::OrganizationId
0x1a8b3  ldarg.1
0x1a8b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_OrganizationId()
0x1a8b9  stloc.3
0x1a8ba  ldloca.s 3
0x1a8bc  constrained. [mscorlib]System.Guid
0x1a8c2  callvirt instance string [mscorlib]System.Object::ToString()
0x1a8c7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a8cc  ldarg.1
0x1a8cd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x1a8d2  ldarg.1
0x1a8d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x1a8d8  callvirt instance string [mscorlib]System.Object::ToString()
0x1a8dd  ldarg.2
0x1a8de  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x1a8e3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x1a8e8  ldloc.0
0x1a8e9  call     void Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::PushTelemetry(string entityLogicalName, string id, string operationName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> AdditionalData)
0x1a8ee  leave.s  loc_1A918
0x1a8f0  stloc.s  4
0x1a8f2  ldloc.s  4
0x1a8f4  ldarg.2
0x1a8f5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1a8fa  ldc.i4.s 0x14
0x1a8fc  ldstr    aServiceTelemet// "Service Telemetry Error:  {0}"
0x1a901  ldc.i4.1
0x1a902  newarr   [mscorlib]System.Object
0x1a907  dup
0x1a908  ldc.i4.0
0x1a909  ldloc.s  4
0x1a90b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1a910  stelem.ref
0x1a911  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a916  leave.s  loc_1A918
0x1a918  ret
```
