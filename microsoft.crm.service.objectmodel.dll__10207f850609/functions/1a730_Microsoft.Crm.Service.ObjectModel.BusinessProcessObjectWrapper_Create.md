# Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::Create

- ea: `0x1a730`
- end: `0x1a85d`
- name: `Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::Create`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x7e00`

## callees

- `0x1a720`
- `0x1a730`
- `0x1aa30`

## string_xrefs

- `0x1a83f`: `Service Telemetry Error:  {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1a730  ldarg.0
0x1a731  ldarg.1
0x1a732  ldarg.2
0x1a733  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a738  stloc.0
0x1a739  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1a73e  stloc.1
0x1a73f  ldarg.1
0x1a740  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_OrganizationId()
0x1a745  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(valuetype [mscorlib]System.Guid)
0x1a74a  stloc.2
0x1a74b  ldloc.2
0x1a74c  ldarg.1
0x1a74d  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x1a752  pop
0x1a753  ldarg.0
0x1a754  ldloc.2
0x1a755  ldloc.1
0x1a756  ldarg.2
0x1a757  ldc.i4.0
0x1a758  newarr   [mscorlib]System.Object
0x1a75d  callvirt instance bool Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::CollectTelemetry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection entities, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> data, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, object[] messageParams)
0x1a762  brfalse  loc_1A831
0x1a767  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a76c  stloc.s  4
0x1a76e  ldloca.s 4
0x1a770  constrained. [mscorlib]System.Guid
0x1a776  callvirt instance string [mscorlib]System.Object::ToString()
0x1a77b  stloc.3
0x1a77c  ldloc.0
0x1a77d  brfalse.s loc_1A7D2
0x1a77f  ldloc.1
0x1a780  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Result
0x1a785  ldc.i4.1
0x1a786  stloc.s  5
0x1a788  ldloca.s 5
0x1a78a  constrained. ResultType
0x1a790  callvirt instance string [mscorlib]System.Object::ToString()
0x1a795  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a79a  ldloc.1
0x1a79b  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::OrganizationId
0x1a7a0  ldloc.0
0x1a7a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_OrganizationId()
0x1a7a6  stloc.s  4
0x1a7a8  ldloca.s 4
0x1a7aa  constrained. [mscorlib]System.Guid
0x1a7b0  callvirt instance string [mscorlib]System.Object::ToString()
0x1a7b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a7ba  ldloc.0
0x1a7bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x1a7c0  stloc.s  4
0x1a7c2  ldloca.s 4
0x1a7c4  constrained. [mscorlib]System.Guid
0x1a7ca  callvirt instance string [mscorlib]System.Object::ToString()
0x1a7cf  stloc.3
0x1a7d0  br.s     loc_1A819
0x1a7d2  ldloc.1
0x1a7d3  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::Result
0x1a7d8  ldc.i4.0
0x1a7d9  stloc.s  5
0x1a7db  ldloca.s 5
0x1a7dd  constrained. ResultType
0x1a7e3  callvirt instance string [mscorlib]System.Object::ToString()
0x1a7e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a7ed  ldloc.1
0x1a7ee  ldsfld   string Microsoft.Crm.Service.ObjectModel.Telemetry.TelemetryDataConstants::OrganizationId
0x1a7f3  ldarg.1
0x1a7f4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_OrganizationId()
0x1a7f9  stloc.s  4
0x1a7fb  ldloca.s 4
0x1a7fd  constrained. [mscorlib]System.Guid
0x1a803  callvirt instance string [mscorlib]System.Object::ToString()
0x1a808  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a80d  ldarg.1
0x1a80e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x1a813  callvirt instance string [mscorlib]System.Object::ToString()
0x1a818  stloc.3
0x1a819  ldarg.1
0x1a81a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x1a81f  ldloc.3
0x1a820  ldarg.2
0x1a821  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x1a826  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x1a82b  ldloc.1
0x1a82c  call     void Microsoft.Crm.Service.ObjectModel.BusinessProcessObjectWrapper::PushTelemetry(string entityLogicalName, string id, string operationName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> AdditionalData)
0x1a831  leave.s  loc_1A85B
0x1a833  stloc.s  6
0x1a835  ldloc.s  6
0x1a837  ldarg.2
0x1a838  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1a83d  ldc.i4.s 0x14
0x1a83f  ldstr    aServiceTelemet// "Service Telemetry Error:  {0}"
0x1a844  ldc.i4.1
0x1a845  newarr   [mscorlib]System.Object
0x1a84a  dup
0x1a84b  ldc.i4.0
0x1a84c  ldloc.s  6
0x1a84e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1a853  stelem.ref
0x1a854  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a859  leave.s  loc_1A85B
0x1a85b  ldloc.0
0x1a85c  ret
```
