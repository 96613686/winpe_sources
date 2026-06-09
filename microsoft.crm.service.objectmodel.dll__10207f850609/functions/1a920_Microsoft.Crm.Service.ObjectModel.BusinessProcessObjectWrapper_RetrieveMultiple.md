# Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::RetrieveMultiple

- ea: `0x1a920`
- end: `0x1aa25`
- name: `Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::RetrieveMultiple`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a720`
- `0x1a920`
- `0x1aa30`

## string_xrefs

- `0x1aa07`: `Service Telemetry Error:  {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1a920  ldarg.0
0x1a921  ldarg.1
0x1a922  ldarg.2
0x1a923  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a928  stloc.0
0x1a929  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1a92e  stloc.1
0x1a92f  ldarg.0
0x1a930  ldloc.0
0x1a931  ldloc.1
0x1a932  ldarg.2
0x1a933  ldc.i4.0
0x1a934  newarr   [mscorlib]System.Object
0x1a939  callvirt instance bool Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::CollectTelemetry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection entities, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> data, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, object[] messageParams)
0x1a93e  brfalse  loc_1A9F9
0x1a943  ldloc.1
0x1a944  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::OrganizationId
0x1a949  ldarg.1
0x1a94a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.Expression::get_OrganizationId()
0x1a94f  stloc.2
0x1a950  ldloca.s 2
0x1a952  constrained. [mscorlib]System.Guid
0x1a958  callvirt instance string [mscorlib]System.Object::ToString()
0x1a95d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a962  ldloc.0
0x1a963  brfalse.s loc_1A9B0
0x1a965  ldloc.1
0x1a966  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Result
0x1a96b  ldc.i4.1
0x1a96c  stloc.3
0x1a96d  ldloca.s 3
0x1a96f  constrained. ResultType
0x1a975  callvirt instance string [mscorlib]System.Object::ToString()
0x1a97a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a97f  ldarg.1
0x1a980  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x1a985  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x1a98a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a98f  stloc.2
0x1a990  ldloca.s 2
0x1a992  constrained. [mscorlib]System.Guid
0x1a998  callvirt instance string [mscorlib]System.Object::ToString()
0x1a99d  ldarg.2
0x1a99e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x1a9a3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x1a9a8  ldloc.1
0x1a9a9  call     void Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::PushTelemetry(string entityLogicalName, string id, string operationName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> AdditionalData)
0x1a9ae  br.s     loc_1A9F9
0x1a9b0  ldloc.1
0x1a9b1  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Result
0x1a9b6  ldc.i4.0
0x1a9b7  stloc.3
0x1a9b8  ldloca.s 3
0x1a9ba  constrained. ResultType
0x1a9c0  callvirt instance string [mscorlib]System.Object::ToString()
0x1a9c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a9ca  ldarg.1
0x1a9cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x1a9d0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x1a9d5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a9da  stloc.2
0x1a9db  ldloca.s 2
0x1a9dd  constrained. [mscorlib]System.Guid
0x1a9e3  callvirt instance string [mscorlib]System.Object::ToString()
0x1a9e8  ldarg.2
0x1a9e9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x1a9ee  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x1a9f3  ldloc.1
0x1a9f4  call     void Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::PushTelemetry(string entityLogicalName, string id, string operationName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> AdditionalData)
0x1a9f9  leave.s  loc_1AA23
0x1a9fb  stloc.s  4
0x1a9fd  ldloc.s  4
0x1a9ff  ldarg.2
0x1aa00  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1aa05  ldc.i4.s 0x14
0x1aa07  ldstr    aServiceTelemet// "Service Telemetry Error:  {0}"
0x1aa0c  ldc.i4.1
0x1aa0d  newarr   [mscorlib]System.Object
0x1aa12  dup
0x1aa13  ldc.i4.0
0x1aa14  ldloc.s  4
0x1aa16  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1aa1b  stelem.ref
0x1aa1c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1aa21  leave.s  loc_1AA23
0x1aa23  ldloc.0
0x1aa24  ret
```
