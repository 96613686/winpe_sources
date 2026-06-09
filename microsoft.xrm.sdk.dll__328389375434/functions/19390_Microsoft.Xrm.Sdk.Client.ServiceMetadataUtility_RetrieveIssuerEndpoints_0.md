# Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveIssuerEndpoints_0

- ea: `0x19390`
- end: `0x19404`
- name: `Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveIssuerEndpoints_0`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x16900`

## callees

- `0x17890`
- `0x17940`
- `0x19090`
- `0x19320`
- `0x19390`
- `0x19410`

## pseudocode

```c

```

## disassembly

```asm
0x19390  ldarg.1
0x19391  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::get_Values()
0x19396  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::GetEnumerator()
0x1939b  stloc.0
0x1939c  br.s     loc_193E3
0x1939e  ldloca.s 0
0x193a0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::get_Current()
0x193a5  stloc.1
0x193a6  ldloc.1
0x193a7  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x193ac  call     class Microsoft.Xrm.Sdk.Client.IssuerEndpoint Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetIssuer(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding)
0x193b1  stloc.2
0x193b2  ldloc.2
0x193b3  brfalse.s loc_193DE
0x193b5  ldarg.2
0x193b6  brfalse.s loc_193D4
0x193b8  ldloc.2
0x193b9  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerMetadataAddress()
0x193be  ldnull
0x193bf  call     bool [System.ServiceModel]System.ServiceModel.EndpointAddress::op_Inequality(class [System.ServiceModel]System.ServiceModel.EndpointAddress, class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x193c4  brfalse.s loc_193D4
0x193c6  ldloc.2
0x193c7  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerMetadataAddress()
0x193cc  call     class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveIssuerEndpoints(class [System.ServiceModel]System.ServiceModel.EndpointAddress issuerMetadataAddress)
0x193d1  stloc.3
0x193d2  leave.s  loc_19402
0x193d4  ldarg.0
0x193d5  ldloc.2
0x193d6  call     class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveDefaultIssuerEndpoint(valuetype Microsoft.Xrm.Sdk.Client.AuthenticationProviderType authenticationProviderType, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint issuer)
0x193db  stloc.3
0x193dc  leave.s  loc_19402
0x193de  leave.s  loc_193E3
0x193e0  pop
0x193e1  leave.s  loc_193E3
0x193e3  ldloca.s 0
0x193e5  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::MoveNext()
0x193ea  brtrue.s loc_1939E
0x193ec  leave.s  loc_193FC
0x193ee  ldloca.s 0
0x193f0  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>
0x193f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x193fb  endfinally
0x193fc  newobj   instance void Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary::.ctor()
0x19401  ret
0x19402  ldloc.3
0x19403  ret
```
