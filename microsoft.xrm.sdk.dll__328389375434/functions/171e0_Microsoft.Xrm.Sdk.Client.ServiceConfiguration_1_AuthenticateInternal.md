# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateInternal

- ea: `0x171e0`
- end: `0x172a7`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateInternal`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7d90`
- `0x15600`
- `0x15630`
- `0x15680`
- `0x171e0`
- `0x17810`

## pseudocode

```c

```

## disassembly

```asm
0x171e0  ldarg.0
0x171e1  call     instance valuetype Microsoft.Xrm.Sdk.Client.AuthenticationProviderType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_AuthenticationType()
0x171e6  ldc.i4.2
0x171e7  beq.s    loc_171F4
0x171e9  ldarg.0
0x171ea  call     instance valuetype Microsoft.Xrm.Sdk.Client.AuthenticationProviderType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_AuthenticationType()
0x171ef  ldc.i4.4
0x171f0  ceq
0x171f2  br.s     loc_171F5
0x171f4  ldc.i4.1
0x171f5  ldstr    aAuthenticateIs// "Authenticate is not supported when not "...
0x171fa  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::Assert(bool condition, string message)
0x171ff  ldarg.0
0x17200  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ClaimsEnabledService()
0x17205  brfalse  loc_172A3
0x1720a  ldarg.1
0x1720b  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpoint Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_IssuerEndpoint()
0x17210  callvirt instance valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_CredentialType()
0x17215  ldc.i4.2
0x17216  bne.un   loc_1729B
0x1721b  ldc.i4.0
0x1721c  stloc.0
0x1721d  ldc.i4.0
0x1721e  stloc.1
0x1721f  nop
0x17220  ldarg.0
0x17221  ldarg.1
0x17222  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::Issue(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x17227  stloc.2
0x17228  leave.s  loc_172A5
0x1722a  pop
0x1722b  ldc.i4.0
0x1722c  stloc.0
0x1722d  ldarg.1
0x1722e  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_IssuerEndpoints()
0x17233  ldc.i4.6
0x17234  stloc.3
0x17235  ldloca.s 3
0x17237  constrained. Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType
0x1723d  callvirt instance string [mscorlib]System.Object::ToString()
0x17242  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::ContainsKey(var<u1>)
0x17247  brfalse.s loc_17259
0x17249  ldarg.1
0x1724a  ldc.i4.6
0x1724b  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x17250  ldloc.1
0x17251  ldc.i4.1
0x17252  add
0x17253  dup
0x17254  stloc.1
0x17255  ldc.i4.2
0x17256  clt
0x17258  stloc.0
0x17259  leave.s  loc_17296
0x1725b  pop
0x1725c  ldloc.1
0x1725d  ldc.i4.1
0x1725e  add
0x1725f  dup
0x17260  stloc.1
0x17261  ldc.i4.2
0x17262  clt
0x17264  stloc.0
0x17265  leave.s  loc_17296
0x17267  pop
0x17268  ldarg.1
0x17269  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_IssuerEndpoints()
0x1726e  ldc.i4.6
0x1726f  stloc.3
0x17270  ldloca.s 3
0x17272  constrained. Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType
0x17278  callvirt instance string [mscorlib]System.Object::ToString()
0x1727d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::ContainsKey(var<u1>)
0x17282  brfalse.s loc_17294
0x17284  ldarg.1
0x17285  ldc.i4.6
0x17286  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x1728b  ldloc.1
0x1728c  ldc.i4.1
0x1728d  add
0x1728e  dup
0x1728f  stloc.1
0x17290  ldc.i4.2
0x17291  clt
0x17293  stloc.0
0x17294  leave.s  loc_17296
0x17296  ldloc.0
0x17297  brtrue.s loc_1721F
0x17299  br.s     loc_172A3
0x1729b  ldarg.0
0x1729c  ldarg.1
0x1729d  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::Issue(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x172a2  ret
0x172a3  ldnull
0x172a4  ret
0x172a5  ldloc.2
0x172a6  ret
```
