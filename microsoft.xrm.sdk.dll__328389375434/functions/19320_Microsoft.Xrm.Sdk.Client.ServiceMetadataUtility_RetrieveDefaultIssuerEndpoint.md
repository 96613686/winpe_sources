# Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveDefaultIssuerEndpoint

- ea: `0x19320`
- end: `0x19384`
- name: `Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveDefaultIssuerEndpoint`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x19390`

## callees

- `0x17820`
- `0x17850`
- `0x17860`
- `0x17870`
- `0x17880`
- `0x178b0`
- `0x17940`
- `0x19320`

## pseudocode

```c

```

## disassembly

```asm
0x19320  newobj   instance void Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary::.ctor()
0x19325  stloc.0
0x19326  ldarg.1
0x19327  brfalse.s loc_19382
0x19329  ldarg.1
0x1932a  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerAddress()
0x1932f  ldnull
0x19330  call     bool [System.ServiceModel]System.ServiceModel.EndpointAddress::op_Inequality(class [System.ServiceModel]System.ServiceModel.EndpointAddress, class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x19335  brfalse.s loc_19382
0x19337  ldarg.0
0x19338  ldc.i4.2
0x19339  beq.s    loc_19341
0x1933b  ldarg.0
0x1933c  ldc.i4.4
0x1933d  beq.s    loc_19345
0x1933f  br.s     loc_19349
0x19341  ldc.i4.2
0x19342  stloc.1
0x19343  br.s     loc_1934B
0x19345  ldc.i4.1
0x19346  stloc.1
0x19347  br.s     loc_1934B
0x19349  ldc.i4.2
0x1934a  stloc.1
0x1934b  ldloc.0
0x1934c  ldloca.s 1
0x1934e  constrained. Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType
0x19354  callvirt instance string [mscorlib]System.Object::ToString()
0x19359  newobj   instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::.ctor()
0x1935e  dup
0x1935f  ldloc.1
0x19360  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_CredentialType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x19365  dup
0x19366  ldarg.1
0x19367  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerAddress()
0x1936c  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress value)
0x19371  dup
0x19372  ldarg.1
0x19373  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerBinding()
0x19378  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerBinding(class [System.ServiceModel]System.ServiceModel.Channels.Binding value)
0x1937d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::Add(var<u1>, !!T0)
0x19382  ldloc.0
0x19383  ret
```
