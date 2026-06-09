# Microsoft.Crm.ServiceBus.TokenClientBehaviorStrategy::GetTokenProvider

- ea: `0x3ac0`
- end: `0x3b5d`
- name: `Microsoft.Crm.ServiceBus.TokenClientBehaviorStrategy::GetTokenProvider`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a60`

## callees

- `0x1550`
- `0x1570`
- `0x1590`
- `0x15b0`
- `0x3a30`
- `0x3ac0`
- `0x5590`
- `0x5750`

## pseudocode

```c

```

## disassembly

```asm
0x3ac0  ldarg.0
0x3ac1  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::get_EndpointInfo()
0x3ac6  callvirt instance valuetype AuthenticationType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_AuthType()
0x3acb  stloc.0
0x3acc  ldloc.0
0x3acd  ldc.i4.1
0x3ace  sub
0x3acf  switch   loc_3AE2, loc_3AF9, loc_3B15
0x3ae0  br.s     loc_3B26
0x3ae2  ldarg.0
0x3ae3  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::get_EndpointInfo()
0x3ae8  newobj   instance void Microsoft.Crm.ServiceBus.TokenProvider::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x3aed  ldc.i4.1
0x3aee  callvirt instance string Microsoft.Crm.ServiceBus.TokenProvider::RetrieveTokenString(bool fromServiceBusScope)
0x3af3  call     class [Microsoft.ServiceBus]Microsoft.ServiceBus.TokenProvider [Microsoft.ServiceBus]Microsoft.ServiceBus.TokenProvider::CreateSamlTokenProvider(string)
0x3af8  ret
0x3af9  ldarg.0
0x3afa  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::get_EndpointInfo()
0x3aff  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_SASKeyName()
0x3b04  ldarg.0
0x3b05  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::get_EndpointInfo()
0x3b0a  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_SASKey()
0x3b0f  call     class [Microsoft.ServiceBus]Microsoft.ServiceBus.TokenProvider [Microsoft.ServiceBus]Microsoft.ServiceBus.TokenProvider::CreateSharedAccessSignatureTokenProvider(string, string)
0x3b14  ret
0x3b15  ldarg.0
0x3b16  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::get_EndpointInfo()
0x3b1b  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_SASToken()
0x3b20  call     class [Microsoft.ServiceBus]Microsoft.ServiceBus.TokenProvider [Microsoft.ServiceBus]Microsoft.ServiceBus.TokenProvider::CreateSharedAccessSignatureTokenProvider(string)
0x3b25  ret
0x3b26  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b2b  ldstr    aInvalidAuthent// "Invalid Authentication Mode :{0}"
0x3b30  ldc.i4.1
0x3b31  newarr   [mscorlib]System.Object
0x3b36  dup
0x3b37  ldc.i4.0
0x3b38  ldarg.0
0x3b39  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.AuthClientBehaviorStrategy::get_EndpointInfo()
0x3b3e  callvirt instance valuetype AuthenticationType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_AuthType()
0x3b43  stloc.0
0x3b44  ldloca.s 0
0x3b46  constrained. AuthenticationType
0x3b4c  callvirt instance string [mscorlib]System.Object::ToString()
0x3b51  stelem.ref
0x3b52  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3b57  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3b5c  throw
```
