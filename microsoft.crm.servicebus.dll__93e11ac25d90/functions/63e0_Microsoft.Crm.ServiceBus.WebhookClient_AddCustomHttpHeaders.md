# Microsoft.Crm.ServiceBus.WebhookClient::AddCustomHttpHeaders

- ea: `0x63e0`
- end: `0x6477`
- name: `Microsoft.Crm.ServiceBus.WebhookClient::AddCustomHttpHeaders`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x6c10`

## callees

- `0x1cf0`
- `0x1d30`
- `0x1d50`
- `0x61c0`
- `0x6330`
- `0x63e0`

## string_xrefs

- `0x6432`: `Received exception when adding custom http headers: for OrgId:{0}, serviceEndpointId: {1}, name: {2}, exception:{3}`

## pseudocode

```c

```

## disassembly

```asm
0x63e0  ldarg.0
0x63e1  ldarg.2
0x63e2  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_AuthValue()
0x63e7  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.WebhookClient::ExtractKeyValuePairs(string inputXml)
0x63ec  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x63f1  stloc.0
0x63f2  br.s     loc_6415
0x63f4  ldloca.s 0
0x63f6  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x63fb  stloc.1
0x63fc  ldarg.1
0x63fd  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x6402  ldloca.s 1
0x6404  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x6409  ldloca.s 1
0x640b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x6410  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x6415  ldloca.s 0
0x6417  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x641c  brtrue.s loc_63F4
0x641e  leave.s  loc_642E
0x6420  ldloca.s 0
0x6422  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x6428  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x642d  endfinally
0x642e  leave.s  loc_6476
0x6430  stloc.2
0x6431  ldarg.0
0x6432  ldstr    aReceivedExcept_1// "Received exception when adding custom h"...
0x6437  ldc.i4.4
0x6438  newarr   [mscorlib]System.Object
0x643d  dup
0x643e  ldc.i4.0
0x643f  ldarg.3
0x6440  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x6445  box      [mscorlib]System.Guid
0x644a  stelem.ref
0x644b  dup
0x644c  ldc.i4.1
0x644d  ldarg.2
0x644e  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0x6453  stelem.ref
0x6454  dup
0x6455  ldc.i4.2
0x6456  ldarg.2
0x6457  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Name()
0x645c  stelem.ref
0x645d  dup
0x645e  ldc.i4.3
0x645f  ldloc.2
0x6460  callvirt instance string [mscorlib]System.Object::ToString()
0x6465  stelem.ref
0x6466  call     string [mscorlib]System.String::Format(string, object[])
0x646b  ldc.i4   0x80050203
0x6470  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.ServiceBus.WebhookClient::GetCrmExceptionWithInnerException(string message, int32 errorCode)
0x6475  throw
0x6476  ret
```
