# Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::RetrieveMultipleCore

- ea: `0x1ab40`
- end: `0x1ac0d`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::RetrieveMultipleCore`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ac80`

## callees

- `0x7ad0`
- `0x1a050`
- `0x1ab40`

## pseudocode

```c

```

## disassembly

```asm
0x1ab40  ldloca.s 0
0x1ab42  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1ab48  ldc.i4.0
0x1ab49  stloc.1
0x1ab4a  ldarg.0
0x1ab4b  newobj   instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::.ctor(class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy proxy)
0x1ab50  stloc.2
0x1ab51  ldarg.0
0x1ab52  call     instance class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceChannel()
0x1ab57  callvirt instance var<u1> class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_Channel()
0x1ab5c  ldarg.1
0x1ab5d  callvirt instance class Microsoft.Xrm.Sdk.EntityCollection Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class Microsoft.Xrm.Sdk.Query.QueryBase query)
0x1ab62  stloc.3
0x1ab63  leave    loc_1AC0B
0x1ab68  ldloc.2
0x1ab69  brfalse.s loc_1AB71
0x1ab6b  ldloc.2
0x1ab6c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ab71  endfinally
0x1ab72  stloc.s  4
0x1ab74  ldc.i4.1
0x1ab75  stloc.1
0x1ab76  ldarg.0
0x1ab77  ldloc.s  4
0x1ab79  ldloc.0
0x1ab7a  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::ShouldRetry(class [System.ServiceModel]System.ServiceModel.Security.MessageSecurityException, valuetype [mscorlib]System.Nullable`1<bool>)
0x1ab7f  stloc.0
0x1ab80  ldloca.s 0
0x1ab82  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1ab87  brtrue.s loc_1AB8B
0x1ab89  rethrow
0x1ab8b  leave.s  loc_1ABF4
0x1ab8d  pop
0x1ab8e  ldc.i4.1
0x1ab8f  stloc.1
0x1ab90  ldarg.0
0x1ab91  ldloc.0
0x1ab92  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1ab97  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1ab9c  stloc.0
0x1ab9d  ldloca.s 0
0x1ab9f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1aba4  brtrue.s loc_1ABA8
0x1aba6  rethrow
0x1aba8  leave.s  loc_1ABF4
0x1abaa  pop
0x1abab  ldc.i4.1
0x1abac  stloc.1
0x1abad  ldarg.0
0x1abae  ldloc.0
0x1abaf  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1abb4  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1abb9  stloc.0
0x1abba  ldloca.s 0
0x1abbc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1abc1  brtrue.s loc_1ABC5
0x1abc3  rethrow
0x1abc5  leave.s  loc_1ABF4
0x1abc7  stloc.s  5
0x1abc9  ldc.i4.1
0x1abca  stloc.1
0x1abcb  ldarg.0
0x1abcc  ldloc.s  5
0x1abce  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1abd3  ldloc.0
0x1abd4  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(class Microsoft.Xrm.Sdk.BaseServiceFault, valuetype [mscorlib]System.Nullable`1<bool>)
0x1abd9  stloc.0
0x1abda  ldloca.s 0
0x1abdc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1abe1  brtrue.s loc_1ABE5
0x1abe3  rethrow
0x1abe5  leave.s  loc_1ABF4
0x1abe7  pop
0x1abe8  ldc.i4.1
0x1abe9  stloc.1
0x1abea  rethrow
0x1abec  ldarg.0
0x1abed  ldloc.1
0x1abee  callvirt instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::CloseChannel(bool)
0x1abf3  endfinally
0x1abf4  ldloca.s 0
0x1abf6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1abfb  brfalse.s loc_1AC09
0x1abfd  ldloca.s 0
0x1abff  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1ac04  brtrue   loc_1AB48
0x1ac09  ldnull
0x1ac0a  ret
0x1ac0b  ldloc.3
0x1ac0c  ret
```
