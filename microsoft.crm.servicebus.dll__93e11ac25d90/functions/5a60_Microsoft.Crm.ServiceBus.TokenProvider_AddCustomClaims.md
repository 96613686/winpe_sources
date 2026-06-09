# Microsoft.Crm.ServiceBus.TokenProvider::AddCustomClaims

- ea: `0x5a60`
- end: `0x5b86`
- name: `Microsoft.Crm.ServiceBus.TokenProvider::AddCustomClaims`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x5750`

## callees

- `0x1610`
- `0x5570`
- `0x5a60`

## string_xrefs

- `0x5ac5`: `Claim type must be a valid uri`
- `0x5ad1`: `http://schemas.microsoft.com/xrm`

## pseudocode

```c

```

## disassembly

```asm
0x5a60  ldarg.1
0x5a61  ldstr    aSaml2assertion// "saml2Assertion"
0x5a66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5a6b  ldarg.0
0x5a6c  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5a71  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_ClaimCollection()
0x5a76  brtrue.s loc_5A79
0x5a78  ret
0x5a79  ldarg.0
0x5a7a  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5a7f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_ClaimCollection()
0x5a84  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x5a89  ldc.i4.s 0x14
0x5a8b  ble.s    loc_5A98
0x5a8d  ldstr    aClaimCollectio// "Claim collection size too large."
0x5a92  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5a97  throw
0x5a98  ldarg.0
0x5a99  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5a9e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_ClaimCollection()
0x5aa3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x5aa8  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::GetEnumerator()
0x5aad  stloc.0
0x5aae  br.s     loc_5B0C
0x5ab0  ldloca.s 0
0x5ab2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::get_Current()
0x5ab7  stloc.1
0x5ab8  ldnull
0x5ab9  stloc.2
0x5aba  ldloc.1
0x5abb  ldc.i4.1
0x5abc  ldloca.s 2
0x5abe  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x5ac3  brtrue.s loc_5AD0
0x5ac5  ldstr    aClaimTypeMustB// "Claim type must be a valid uri"
0x5aca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5acf  throw
0x5ad0  ldloc.1
0x5ad1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm"
0x5ad6  ldc.i4.5
0x5ad7  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x5adc  brfalse.s loc_5AE9
0x5ade  ldstr    aClaimTypeCanno// "Claim type cannot have a CRM system pre"...
0x5ae3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5ae8  throw
0x5ae9  ldarg.0
0x5aea  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5aef  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_ClaimCollection()
0x5af4  ldloc.1
0x5af5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x5afa  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5aff  brfalse.s loc_5B0C
0x5b01  ldstr    aAllSpecifiedCl// "All specified claim must have a value"
0x5b06  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5b0b  throw
0x5b0c  ldloca.s 0
0x5b0e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::MoveNext()
0x5b13  brtrue.s loc_5AB0
0x5b15  leave.s  loc_5B25
0x5b17  ldloca.s 0
0x5b19  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>
0x5b1f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b24  endfinally
0x5b25  ldarg.0
0x5b26  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5b2b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_ClaimCollection()
0x5b30  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x5b35  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::GetEnumerator()
0x5b3a  stloc.0
0x5b3b  br.s     loc_5B6C
0x5b3d  ldloca.s 0
0x5b3f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::get_Current()
0x5b44  stloc.3
0x5b45  ldarg.1
0x5b46  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Statement> [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::get_Statements()
0x5b4b  ldloc.3
0x5b4c  ldarg.0
0x5b4d  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5b52  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_ClaimCollection()
0x5b57  ldloc.3
0x5b58  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x5b5d  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Attribute::.ctor(string, string)
0x5b62  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2AttributeStatement::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Attribute)
0x5b67  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Statement>::Add(var<u1>)
0x5b6c  ldloca.s 0
0x5b6e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::MoveNext()
0x5b73  brtrue.s loc_5B3D
0x5b75  leave.s  loc_5B85
0x5b77  ldloca.s 0
0x5b79  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>
0x5b7f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b84  endfinally
0x5b85  ret
```
