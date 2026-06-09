# Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateSecurityBindingElement

- ea: `0x11e0`
- end: `0x12e4`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateSecurityBindingElement`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0xf30`
- `0x11e0`
- `0x17f0`
- `0x1810`
- `0x1850`

## string_xrefs

- `0x12a4`: `ID3226: SecurityMode of IssuedTokenBinding must be SecurityMode.Message or SecurityMode.TransportWithMessageCredential. But actual value is '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x11e0  ldarg.0
0x11e1  ldfld    string Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_tokenType
0x11e6  ldarg.0
0x11e7  ldfld    class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_issuerAddress
0x11ec  ldarg.0
0x11ed  ldfld    class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_issuerBinding
0x11f2  newobj   instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::.ctor(string, class [System.ServiceModel]System.ServiceModel.EndpointAddress, class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x11f7  dup
0x11f8  ldarg.0
0x11f9  ldfld    valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_keyType
0x11fe  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::set_KeyType(valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType)
0x1203  dup
0x1204  ldarg.0
0x1205  ldfld    class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_issuerMetadataAddress
0x120a  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::set_IssuerMetadataAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x120f  stloc.1
0x1210  ldarg.0
0x1211  ldfld    valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_keyType
0x1216  brtrue.s loc_122B
0x1218  ldloc.1
0x1219  ldarg.0
0x121a  ldfld    class [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_algorithmSuite
0x121f  callvirt instance int32 [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite::get_DefaultSymmetricKeyLength()
0x1224  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::set_KeySize(int32)
0x1229  br.s     loc_1232
0x122b  ldloc.1
0x122c  ldc.i4.0
0x122d  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::set_KeySize(int32)
0x1232  ldarg.0
0x1233  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement> Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_claimTypeRequirements
0x1238  brfalse.s loc_126F
0x123a  ldarg.0
0x123b  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement> Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_claimTypeRequirements
0x1240  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement>::GetEnumerator()
0x1245  stloc.2
0x1246  br.s     loc_125B
0x1248  ldloc.2
0x1249  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement>::get_Current()
0x124e  stloc.3
0x124f  ldloc.1
0x1250  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement> [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_ClaimTypeRequirements()
0x1255  ldloc.3
0x1256  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.ClaimTypeRequirement>::Add(var<u1>)
0x125b  ldloc.2
0x125c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1261  brtrue.s loc_1248
0x1263  leave.s  loc_126F
0x1265  ldloc.2
0x1266  brfalse.s loc_126E
0x1268  ldloc.2
0x1269  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x126e  endfinally
0x126f  ldarg.0
0x1270  ldarg.0
0x1271  ldfld    class [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_algorithmSuite
0x1276  ldarg.0
0x1277  call     instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_TrustVersion()
0x127c  ldarg.0
0x127d  ldfld    valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_keyType
0x1282  ldloca.s 1
0x1284  call     instance void Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::AddAlgorithmParameters(class [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite algorithmSuite, class [System.ServiceModel]System.ServiceModel.Security.TrustVersion trustVersion, valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType keyType, class [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters& issuedParameters)
0x1289  ldc.i4.2
0x128a  ldarg.0
0x128b  call     instance valuetype [System.ServiceModel]System.ServiceModel.SecurityMode Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_SecurityMode()
0x1290  bne.un.s loc_129B
0x1292  ldloc.1
0x1293  call     class [System.ServiceModel]System.ServiceModel.Channels.SymmetricSecurityBindingElement [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::CreateIssuedTokenForCertificateBindingElement(class [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters)
0x1298  stloc.0
0x1299  br.s     loc_12CF
0x129b  ldc.i4.3
0x129c  ldarg.0
0x129d  call     instance valuetype [System.ServiceModel]System.ServiceModel.SecurityMode Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_SecurityMode()
0x12a2  beq.s    loc_12C8
0x12a4  ldstr    aId3226Security// "ID3226: SecurityMode of IssuedTokenBind"...
0x12a9  ldc.i4.1
0x12aa  newarr   [mscorlib]System.Object
0x12af  dup
0x12b0  ldc.i4.0
0x12b1  ldarg.0
0x12b2  call     instance valuetype [System.ServiceModel]System.ServiceModel.SecurityMode Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_SecurityMode()
0x12b7  box      [System.ServiceModel]System.ServiceModel.SecurityMode
0x12bc  stelem.ref
0x12bd  call     string Microsoft.Crm.Protocols.WSTrust.Bindings.ClientExceptionHelper::GetString(string value, object[] args)
0x12c2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x12c7  throw
0x12c8  ldloc.1
0x12c9  call     class [System.ServiceModel]System.ServiceModel.Channels.TransportSecurityBindingElement [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::CreateIssuedTokenOverTransportBindingElement(class [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters)
0x12ce  stloc.0
0x12cf  ldloc.0
0x12d0  ldarg.0
0x12d1  ldfld    class [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::_algorithmSuite
0x12d6  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::set_DefaultAlgorithmSuite(class [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite)
0x12db  ldloc.0
0x12dc  ldc.i4.1
0x12dd  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::set_IncludeTimestamp(bool)
0x12e2  ldloc.0
0x12e3  ret
```
