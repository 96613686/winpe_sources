# Microsoft.Crm.ServiceBus.RouterService::ExecuteInternal

- ea: `0x4120`
- end: `0x42da`
- name: `Microsoft.Crm.ServiceBus.RouterService::ExecuteInternal`
- size: `442`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x420`
- `0x3ff0`

## callees

- `0x1b30`
- `0x1bb0`
- `0x4120`
- `0x4440`
- `0x4450`
- `0x47d0`

## string_xrefs

- `0x4136`: `ServiceBusPostError`
- `0x4156`: `Service bus post error internal test. System job expected to fail.`
- `0x4161`: `Service bus post error external test. System job expected to be retried.`
- `0x416d`: `DisableServiceBusPost`
- `0x425d`: `Service Endpoint not found.  Retry the action or contact your System Administrator for additional help.`

## pseudocode

```c

```

## disassembly

```asm
0x4120  ldarg.1
0x4121  ldstr    aContext// "context"
0x4126  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x412b  ldarg.2
0x412c  ldstr    aEndpointinfo// "endpointInfo"
0x4131  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4136  ldstr    aServicebuspost// "ServiceBusPostError"
0x413b  ldc.i4.0
0x413c  box      [mscorlib]System.Int32
0x4141  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x4146  unbox.any [mscorlib]System.Int32
0x414b  stloc.0
0x414c  ldloc.0
0x414d  ldc.i4.1
0x414e  beq.s    loc_4156
0x4150  ldloc.0
0x4151  ldc.i4.2
0x4152  beq.s    loc_4161
0x4154  br.s     loc_416C
0x4156  ldstr    aServiceBusPost// "Service bus post error internal test. S"...
0x415b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4160  throw
0x4161  ldstr    aServiceBusPost_0// "Service bus post error external test. S"...
0x4166  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x416b  throw
0x416c  ldc.i4.0
0x416d  ldstr    aDisableservice// "DisableServiceBusPost"
0x4172  ldc.i4.0
0x4173  box      [mscorlib]System.Int32
0x4178  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x417d  unbox.any [mscorlib]System.Int32
0x4182  clt
0x4184  brtrue.s loc_41B7
0x4186  ldarg.2
0x4187  call     class Microsoft.Crm.ServiceBus.ServiceBusClientBase Microsoft.Crm.ServiceBus.ServiceBusClientManager::RetrieveReadyClient(class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x418c  stloc.1
0x418d  ldarg.2
0x418e  callvirt instance bool Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ValidateOnly()
0x4193  brfalse.s loc_419E
0x4195  ldloc.1
0x4196  ldarg.2
0x4197  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::Validate(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x419c  br.s     loc_41AB
0x419e  ldloc.1
0x419f  ldarg.1
0x41a0  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusClientBase::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context)
0x41a5  stloc.2
0x41a6  leave    loc_42D8
0x41ab  leave.s  loc_41B7
0x41ad  ldloc.1
0x41ae  brfalse.s loc_41B6
0x41b0  ldloc.1
0x41b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41b6  endfinally
0x41b7  ldnull
0x41b8  stloc.2
0x41b9  leave    loc_42D8
0x41be  stloc.3
0x41bf  ldarg.2
0x41c0  brtrue.s loc_41C9
0x41c2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x41c7  br.s     loc_41CF
0x41c9  ldarg.2
0x41ca  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_OrganizationId()
0x41cf  stloc.s  4
0x41d1  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter Microsoft.Crm.ServiceBus.RouterService::_exceptionConverter
0x41d6  ldloc.3
0x41d7  ldc.i4.1
0x41d8  ldloca.s 5
0x41da  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToFaultException(class [mscorlib]System.Exception, bool, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0x41df  brfalse.s loc_41E4
0x41e1  ldloc.s  5
0x41e3  throw
0x41e4  ldloc.3
0x41e5  ldloc.s  4
0x41e7  ldc.i4.s 0x2F
0x41e9  ldstr    a0// "{0}"
0x41ee  ldc.i4.1
0x41ef  newarr   [mscorlib]System.Object
0x41f4  dup
0x41f5  ldc.i4.0
0x41f6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x41fb  ldstr    aUnexpectedExce_0// "UNEXPECTED: exception not converted: {0"...
0x4200  ldc.i4.1
0x4201  newarr   [mscorlib]System.Object
0x4206  dup
0x4207  ldc.i4.0
0x4208  ldloc.3
0x4209  stelem.ref
0x420a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x420f  stelem.ref
0x4210  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4215  rethrow
0x4217  pop
0x4218  rethrow
0x421a  stloc.s  6
0x421c  ldloc.s  6
0x421e  isinst   [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.MessagingEntityNotFoundException
0x4223  brfalse.s loc_4268
0x4225  ldloc.s  6
0x4227  ldarg.1
0x4228  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x422d  ldc.i4.s 0x2F
0x422f  ldstr    a0// "{0}"
0x4234  ldc.i4.1
0x4235  newarr   [mscorlib]System.Object
0x423a  dup
0x423b  ldc.i4.0
0x423c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4241  ldstr    aEndpointNotFou// "Endpoint not found: System job will be "...
0x4246  ldc.i4.1
0x4247  newarr   [mscorlib]System.Object
0x424c  dup
0x424d  ldc.i4.0
0x424e  ldloc.s  6
0x4250  stelem.ref
0x4251  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4256  stelem.ref
0x4257  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x425c  ldc.i4.1
0x425d  ldstr    aServiceEndpoin// "Service Endpoint not found.  Retry the "...
0x4262  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OperationStatus, string)
0x4267  throw
0x4268  ldarg.2
0x4269  brtrue.s loc_4272
0x426b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4270  br.s     loc_4278
0x4272  ldarg.2
0x4273  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_OrganizationId()
0x4278  stloc.s  7
0x427a  ldloc.s  6
0x427c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4281  ldloc.s  6
0x4283  ldc.i4   0x80044175
0x4288  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x428d  stloc.s  8
0x428f  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter Microsoft.Crm.ServiceBus.RouterService::_exceptionConverter
0x4294  ldloc.s  8
0x4296  ldc.i4.1
0x4297  ldloca.s 9
0x4299  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToFaultException(class [mscorlib]System.Exception, bool, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0x429e  brfalse.s loc_42A3
0x42a0  ldloc.s  9
0x42a2  throw
0x42a3  ldloc.s  6
0x42a5  ldloc.s  7
0x42a7  ldc.i4.s 0x2F
0x42a9  ldstr    a0// "{0}"
0x42ae  ldc.i4.1
0x42af  newarr   [mscorlib]System.Object
0x42b4  dup
0x42b5  ldc.i4.0
0x42b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42bb  ldstr    aUnexpectedExce_0// "UNEXPECTED: exception not converted: {0"...
0x42c0  ldc.i4.1
0x42c1  newarr   [mscorlib]System.Object
0x42c6  dup
0x42c7  ldc.i4.0
0x42c8  ldloc.s  6
0x42ca  stelem.ref
0x42cb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42d0  stelem.ref
0x42d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x42d6  rethrow
0x42d8  ldloc.2
0x42d9  ret
```
