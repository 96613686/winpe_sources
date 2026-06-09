# Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::.ctor_5

- ea: `0xe60`
- end: `0xf27`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::.ctor_5`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xe20`
- `0xe40`

## callees

- `0xe60`
- `0x15b0`
- `0x1850`

## string_xrefs

- `0xe7c`: `ID3226: SecurityMode of IssuedTokenBinding must be SecurityMode.Message or SecurityMode.TransportWithMessageCredential. But actual value is '{0}'.`
- `0xead`: `ID3267: Bearer KeyType is not supported with WSTrustFeb2005 version of WSTrust. Consider using WSTrust13 instead.`

## pseudocode

```c

```

## disassembly

```asm
0xe60  ldarg.0
0xe61  ldarg.3
0xe62  ldarg.s  4
0xe64  call     instance void Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::.ctor(valuetype [System.ServiceModel]System.ServiceModel.SecurityMode securityMode, class [System.ServiceModel]System.ServiceModel.Security.TrustVersion trustVersion)
0xe69  ldarg.0
0xe6a  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement>::.ctor()
0xe6f  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement> Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_claimTypeRequirements
0xe74  ldc.i4.2
0xe75  ldarg.3
0xe76  beq.s    loc_E9B
0xe78  ldc.i4.3
0xe79  ldarg.3
0xe7a  beq.s    loc_E9B
0xe7c  ldstr    aId3226Security// "ID3226: SecurityMode of IssuedTokenBind"...
0xe81  ldc.i4.1
0xe82  newarr   [mscorlib]System.Object
0xe87  dup
0xe88  ldc.i4.0
0xe89  ldarg.3
0xe8a  box      [System.ServiceModel]System.ServiceModel.SecurityMode
0xe8f  stelem.ref
0xe90  call     string Microsoft.Crm.Protocols.WSTrust.Bindings.ClientExceptionHelper::GetString(string value, object[] args)
0xe95  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xe9a  throw
0xe9b  ldarg.0
0xe9c  ldfld    valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_keyType
0xea1  ldc.i4.2
0xea2  bne.un.s loc_EC3
0xea4  ldarg.s  4
0xea6  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrustFeb2005()
0xeab  bne.un.s loc_EC3
0xead  ldstr    aId3267BearerKe// "ID3267: Bearer KeyType is not supported"...
0xeb2  ldc.i4.0
0xeb3  newarr   [mscorlib]System.Object
0xeb8  call     string Microsoft.Crm.Protocols.WSTrust.Bindings.ClientExceptionHelper::GetString(string value, object[] args)
0xebd  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xec2  throw
0xec3  ldarg.0
0xec4  ldarg.s  5
0xec6  stfld    valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_keyType
0xecb  ldarg.0
0xecc  ldarg.s  6
0xece  stfld    class [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_algorithmSuite
0xed3  ldarg.0
0xed4  ldarg.s  7
0xed6  stfld    string Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_tokenType
0xedb  ldarg.0
0xedc  ldarg.1
0xedd  stfld    class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_issuerBinding
0xee2  ldarg.0
0xee3  ldarg.2
0xee4  stfld    class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_issuerAddress
0xee9  ldarg.0
0xeea  ldarg.s  9
0xeec  stfld    class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_issuerMetadataAddress
0xef1  ldarg.s  8
0xef3  brfalse.s loc_F26
0xef5  ldarg.s  8
0xef7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement>::GetEnumerator()
0xefc  stloc.0
0xefd  br.s     loc_F12
0xeff  ldloc.0
0xf00  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement>::get_Current()
0xf05  stloc.1
0xf06  ldarg.0
0xf07  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement> Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_claimTypeRequirements
0xf0c  ldloc.1
0xf0d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement>::Add(var<u1>)
0xf12  ldloc.0
0xf13  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf18  brtrue.s loc_EFF
0xf1a  leave.s  loc_F26
0xf1c  ldloc.0
0xf1d  brfalse.s loc_F25
0xf1f  ldloc.0
0xf20  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf25  endfinally
0xf26  ret
```
