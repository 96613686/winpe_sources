# Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::RetrieveCore

- ea: `0x1a660`
- end: `0x1a72f`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::RetrieveCore`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ac20`

## callees

- `0x7a70`
- `0x1a050`
- `0x1a660`

## pseudocode

```c

```

## disassembly

```asm
0x1a660  ldloca.s 0
0x1a662  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1a668  ldc.i4.0
0x1a669  stloc.1
0x1a66a  ldarg.0
0x1a66b  newobj   instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::.ctor(class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy proxy)
0x1a670  stloc.2
0x1a671  ldarg.0
0x1a672  call     instance class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceChannel()
0x1a677  callvirt instance var<u1> class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_Channel()
0x1a67c  ldarg.1
0x1a67d  ldarg.2
0x1a67e  ldarg.3
0x1a67f  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string entityName, valuetype [mscorlib]System.Guid id, class Microsoft.Xrm.Sdk.Query.ColumnSet columnSet)
0x1a684  stloc.3
0x1a685  leave    loc_1A72D
0x1a68a  ldloc.2
0x1a68b  brfalse.s loc_1A693
0x1a68d  ldloc.2
0x1a68e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a693  endfinally
0x1a694  stloc.s  4
0x1a696  ldc.i4.1
0x1a697  stloc.1
0x1a698  ldarg.0
0x1a699  ldloc.s  4
0x1a69b  ldloc.0
0x1a69c  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::ShouldRetry(class [System.ServiceModel]System.ServiceModel.Security.MessageSecurityException, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a6a1  stloc.0
0x1a6a2  ldloca.s 0
0x1a6a4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a6a9  brtrue.s loc_1A6AD
0x1a6ab  rethrow
0x1a6ad  leave.s  loc_1A716
0x1a6af  pop
0x1a6b0  ldc.i4.1
0x1a6b1  stloc.1
0x1a6b2  ldarg.0
0x1a6b3  ldloc.0
0x1a6b4  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a6b9  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a6be  stloc.0
0x1a6bf  ldloca.s 0
0x1a6c1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a6c6  brtrue.s loc_1A6CA
0x1a6c8  rethrow
0x1a6ca  leave.s  loc_1A716
0x1a6cc  pop
0x1a6cd  ldc.i4.1
0x1a6ce  stloc.1
0x1a6cf  ldarg.0
0x1a6d0  ldloc.0
0x1a6d1  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a6d6  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a6db  stloc.0
0x1a6dc  ldloca.s 0
0x1a6de  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a6e3  brtrue.s loc_1A6E7
0x1a6e5  rethrow
0x1a6e7  leave.s  loc_1A716
0x1a6e9  stloc.s  5
0x1a6eb  ldc.i4.1
0x1a6ec  stloc.1
0x1a6ed  ldarg.0
0x1a6ee  ldloc.s  5
0x1a6f0  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1a6f5  ldloc.0
0x1a6f6  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(class Microsoft.Xrm.Sdk.BaseServiceFault, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a6fb  stloc.0
0x1a6fc  ldloca.s 0
0x1a6fe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a703  brtrue.s loc_1A707
0x1a705  rethrow
0x1a707  leave.s  loc_1A716
0x1a709  pop
0x1a70a  ldc.i4.1
0x1a70b  stloc.1
0x1a70c  rethrow
0x1a70e  ldarg.0
0x1a70f  ldloc.1
0x1a710  callvirt instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::CloseChannel(bool)
0x1a715  endfinally
0x1a716  ldloca.s 0
0x1a718  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1a71d  brfalse.s loc_1A72B
0x1a71f  ldloca.s 0
0x1a721  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1a726  brtrue   loc_1A668
0x1a72b  ldnull
0x1a72c  ret
0x1a72d  ldloc.3
0x1a72e  ret
```
