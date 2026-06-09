# Microsoft.Crm.ServiceBus.WebhookClient::AddMandatoryHttpHeaders

- ea: `0x6350`
- end: `0x63bc`
- name: `Microsoft.Crm.ServiceBus.WebhookClient::AddMandatoryHttpHeaders`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6c10`

## callees

- `0x1b50`

## pseudocode

```c

```

## disassembly

```asm
0x6350  ldarg.1
0x6351  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x6356  ldstr    aXMsDynamicsOrg// "x-ms-dynamics-organization"
0x635b  ldarg.2
0x635c  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_OrganizationName()
0x6361  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x6366  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x636b  ldarg.1
0x636c  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x6371  ldstr    aXMsDynamicsEnt// "x-ms-dynamics-entity-name"
0x6376  ldarg.3
0x6377  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_PrimaryEntityName()
0x637c  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x6381  ldarg.1
0x6382  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x6387  ldstr    aXMsDynamicsReq// "x-ms-dynamics-request-name"
0x638c  ldarg.3
0x638d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_MessageName()
0x6392  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x6397  ldarg.1
0x6398  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x639d  ldstr    aXMsCorrelation// "x-ms-correlation-request-id"
0x63a2  ldarg.3
0x63a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_CorrelationId()
0x63a8  stloc.0
0x63a9  ldloca.s 0
0x63ab  constrained. [mscorlib]System.Guid
0x63b1  callvirt instance string [mscorlib]System.Object::ToString()
0x63b6  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x63bb  ret
```
