# Microsoft.Crm.ServiceBus.TokenProvider::CreateTokenRequestBody

- ea: `0x5b90`
- end: `0x5bfc`
- name: `Microsoft.Crm.ServiceBus.TokenProvider::CreateTokenRequestBody`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x55a0`

## callees

- `0x13d0`
- `0x13f0`
- `0x1410`
- `0x5570`
- `0x5750`
- `0x5c00`

## pseudocode

```c

```

## disassembly

```asm
0x5b90  ldarg.0
0x5b91  ldarg.0
0x5b92  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5b97  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Scheme()
0x5b9c  ldarg.0
0x5b9d  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5ba2  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_SolutionName()
0x5ba7  ldarg.0
0x5ba8  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5bad  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Path()
0x5bb2  call     class [System]System.Uri [Microsoft.ServiceBus]Microsoft.ServiceBus.ServiceBusEnvironment::CreateServiceUri(string, string, string)
0x5bb7  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x5bbc  call     instance string Microsoft.Crm.ServiceBus.TokenProvider::NormalizeAppliesToUri(string appliesTo)
0x5bc1  stloc.0
0x5bc2  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0x5bc7  dup
0x5bc8  ldstr    aWrapScope// "wrap_scope"
0x5bcd  ldarg.0
0x5bce  ldloc.0
0x5bcf  call     instance string Microsoft.Crm.ServiceBus.TokenProvider::NormalizeAppliesToUri(string appliesTo)
0x5bd4  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x5bd9  dup
0x5bda  ldstr    aWrapAssertionF// "wrap_assertion_format"
0x5bdf  ldstr    aSaml// "SAML"
0x5be4  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x5be9  dup
0x5bea  ldstr    aWrapAssertion// "wrap_assertion"
0x5bef  ldarg.0
0x5bf0  ldarg.1
0x5bf1  call     instance string Microsoft.Crm.ServiceBus.TokenProvider::RetrieveTokenString(bool fromServiceBusScope)
0x5bf6  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x5bfb  ret
```
