# Microsoft.Crm.ServiceBus.TokenProvider::AddSystemClaims

- ea: `0x5970`
- end: `0x5a55`
- name: `Microsoft.Crm.ServiceBus.TokenProvider::AddSystemClaims`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x5750`

## callees

- `0x1490`
- `0x14b0`
- `0x14d0`
- `0x1510`
- `0x5570`
- `0x5970`

## pseudocode

```c

```

## disassembly

```asm
0x5970  ldarg.1
0x5971  ldstr    aSaml2assertion// "saml2Assertion"
0x5976  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x597b  ldarg.1
0x597c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Statement> [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::get_Statements()
0x5981  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::Organization
0x5986  ldarg.0
0x5987  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x598c  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_OrganizationName()
0x5991  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x5996  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Attribute::.ctor(string, string)
0x599b  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2AttributeStatement::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Attribute)
0x59a0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Statement>::Add(var<u1>)
0x59a5  ldarg.0
0x59a6  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x59ab  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_UserInfo()
0x59b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x59b5  brtrue.s loc_59E1
0x59b7  ldarg.1
0x59b8  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Statement> [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::get_Statements()
0x59bd  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::User
0x59c2  ldarg.0
0x59c3  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x59c8  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_UserInfo()
0x59cd  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x59d2  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Attribute::.ctor(string, string)
0x59d7  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2AttributeStatement::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Attribute)
0x59dc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Statement>::Add(var<u1>)
0x59e1  ldarg.0
0x59e2  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x59e7  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_InitiatingUserInfo()
0x59ec  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x59f1  brtrue.s loc_5A1D
0x59f3  ldarg.1
0x59f4  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Statement> [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::get_Statements()
0x59f9  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::InitiatingUser
0x59fe  ldarg.0
0x59ff  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5a04  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_InitiatingUserInfo()
0x5a09  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x5a0e  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Attribute::.ctor(string, string)
0x5a13  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2AttributeStatement::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Attribute)
0x5a18  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Statement>::Add(var<u1>)
0x5a1d  ldarg.0
0x5a1e  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5a23  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_AssemblyName()
0x5a28  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a2d  brtrue.s loc_5A54
0x5a2f  ldarg.1
0x5a30  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Statement> [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::get_Statements()
0x5a35  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::PluginAssembly
0x5a3a  ldarg.0
0x5a3b  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5a40  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_AssemblyName()
0x5a45  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Attribute::.ctor(string, string)
0x5a4a  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2AttributeStatement::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Attribute)
0x5a4f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Statement>::Add(var<u1>)
0x5a54  ret
```
