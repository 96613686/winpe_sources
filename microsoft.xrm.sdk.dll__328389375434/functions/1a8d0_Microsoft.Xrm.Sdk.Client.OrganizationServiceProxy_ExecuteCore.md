# Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::ExecuteCore

- ea: `0x1a8d0`
- end: `0x1a99d`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::ExecuteCore`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ac50`

## callees

- `0x7aa0`
- `0x1a050`
- `0x1a8d0`

## pseudocode

```c

```

## disassembly

```asm
0x1a8d0  ldloca.s 0
0x1a8d2  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1a8d8  ldc.i4.0
0x1a8d9  stloc.1
0x1a8da  ldarg.0
0x1a8db  newobj   instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::.ctor(class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy proxy)
0x1a8e0  stloc.2
0x1a8e1  ldarg.0
0x1a8e2  call     instance class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceChannel()
0x1a8e7  callvirt instance var<u1> class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_Channel()
0x1a8ec  ldarg.1
0x1a8ed  callvirt instance class Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Xrm.Sdk.IOrganizationService::Execute(class Microsoft.Xrm.Sdk.OrganizationRequest request)
0x1a8f2  stloc.3
0x1a8f3  leave    loc_1A99B
0x1a8f8  ldloc.2
0x1a8f9  brfalse.s loc_1A901
0x1a8fb  ldloc.2
0x1a8fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a901  endfinally
0x1a902  stloc.s  4
0x1a904  ldc.i4.1
0x1a905  stloc.1
0x1a906  ldarg.0
0x1a907  ldloc.s  4
0x1a909  ldloc.0
0x1a90a  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::ShouldRetry(class [System.ServiceModel]System.ServiceModel.Security.MessageSecurityException, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a90f  stloc.0
0x1a910  ldloca.s 0
0x1a912  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a917  brtrue.s loc_1A91B
0x1a919  rethrow
0x1a91b  leave.s  loc_1A984
0x1a91d  pop
0x1a91e  ldc.i4.1
0x1a91f  stloc.1
0x1a920  ldarg.0
0x1a921  ldloc.0
0x1a922  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a927  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a92c  stloc.0
0x1a92d  ldloca.s 0
0x1a92f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a934  brtrue.s loc_1A938
0x1a936  rethrow
0x1a938  leave.s  loc_1A984
0x1a93a  pop
0x1a93b  ldc.i4.1
0x1a93c  stloc.1
0x1a93d  ldarg.0
0x1a93e  ldloc.0
0x1a93f  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a944  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a949  stloc.0
0x1a94a  ldloca.s 0
0x1a94c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a951  brtrue.s loc_1A955
0x1a953  rethrow
0x1a955  leave.s  loc_1A984
0x1a957  stloc.s  5
0x1a959  ldc.i4.1
0x1a95a  stloc.1
0x1a95b  ldarg.0
0x1a95c  ldloc.s  5
0x1a95e  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1a963  ldloc.0
0x1a964  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(class Microsoft.Xrm.Sdk.BaseServiceFault, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a969  stloc.0
0x1a96a  ldloca.s 0
0x1a96c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a971  brtrue.s loc_1A975
0x1a973  rethrow
0x1a975  leave.s  loc_1A984
0x1a977  pop
0x1a978  ldc.i4.1
0x1a979  stloc.1
0x1a97a  rethrow
0x1a97c  ldarg.0
0x1a97d  ldloc.1
0x1a97e  callvirt instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::CloseChannel(bool)
0x1a983  endfinally
0x1a984  ldloca.s 0
0x1a986  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1a98b  brfalse.s loc_1A999
0x1a98d  ldloca.s 0
0x1a98f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1a994  brtrue   loc_1A8D8
0x1a999  ldnull
0x1a99a  ret
0x1a99b  ldloc.3
0x1a99c  ret
```
