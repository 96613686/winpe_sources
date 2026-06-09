# Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::Execute

- ea: `0x4f10`
- end: `0x4fa9`
- name: `Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::Execute`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1450`
- `0x4f10`
- `0x4fb0`
- `0x50e0`
- `0x52c0`

## string_xrefs

- `0x4f3f`: `Invalid contract type found in Service Bus brokered messageclient {0}`
- `0x4f86`: `Exception occurred when sending data to Service bus  {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4f10  ldarg.0
0x4f11  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x4f16  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Contract()
0x4f1b  stloc.0
0x4f1c  ldloc.0
0x4f1d  ldc.i4.5
0x4f1e  sub
0x4f1f  ldc.i4.1
0x4f20  ble.un.s loc_4F28
0x4f22  ldloc.0
0x4f23  ldc.i4.7
0x4f24  beq.s    loc_4F31
0x4f26  br.s     loc_4F3A
0x4f28  ldarg.0
0x4f29  ldarg.1
0x4f2a  call     instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::SendMessage(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context)
0x4f2f  br.s     loc_4F68
0x4f31  ldarg.0
0x4f32  ldarg.1
0x4f33  call     instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::SendEventData(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context)
0x4f38  br.s     loc_4F68
0x4f3a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4f3f  ldstr    aInvalidContrac// "Invalid contract type found in Service "...
0x4f44  ldc.i4.1
0x4f45  newarr   [mscorlib]System.Object
0x4f4a  dup
0x4f4b  ldc.i4.0
0x4f4c  ldarg.0
0x4f4d  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x4f52  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Contract()
0x4f57  box      ContractType
0x4f5c  stelem.ref
0x4f5d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4f62  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4f67  throw
0x4f68  leave.s  loc_4FA7
0x4f6a  stloc.1
0x4f6b  ldloc.1
0x4f6c  ldarg.1
0x4f6d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x4f72  ldc.i4.s 0x2F
0x4f74  ldstr    a0// "{0}"
0x4f79  ldc.i4.1
0x4f7a  newarr   [mscorlib]System.Object
0x4f7f  dup
0x4f80  ldc.i4.0
0x4f81  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4f86  ldstr    aExceptionOccur_0// "Exception occurred when sending data to"...
0x4f8b  ldc.i4.1
0x4f8c  newarr   [mscorlib]System.Object
0x4f91  dup
0x4f92  ldc.i4.0
0x4f93  ldloc.1
0x4f94  callvirt instance string [mscorlib]System.Object::ToString()
0x4f99  stelem.ref
0x4f9a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4f9f  stelem.ref
0x4fa0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4fa5  ldloc.1
0x4fa6  throw
0x4fa7  ldnull
0x4fa8  ret
```
