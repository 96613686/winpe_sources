# Microsoft.Crm.Sandbox.WarmUpMockListener::Execute

- ea: `0x4a50`
- end: `0x4a82`
- name: `Microsoft.Crm.Sandbox.WarmUpMockListener::Execute`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x4a50`

## string_xrefs

- `0x4a51`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x4a50  ldarg.3
0x4a51  ldstr    aCreate// "Create"
0x4a56  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4a5b  brfalse.s loc_4A77
0x4a5d  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter::.ctor()
0x4a62  ldstr    aTest_0// "Test"
0x4a67  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4a6c  ldc.i4.1
0x4a6d  ldloca.s 0
0x4a6f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToFaultException(class [mscorlib]System.Exception, bool, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0x4a74  pop
0x4a75  ldloc.0
0x4a76  throw
0x4a77  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::.ctor()
0x4a7c  call     T0x2B00000A
0x4a81  ret
```
