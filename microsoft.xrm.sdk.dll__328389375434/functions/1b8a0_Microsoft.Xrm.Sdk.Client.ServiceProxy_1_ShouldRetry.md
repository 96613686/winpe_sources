# Microsoft.Xrm.Sdk.Client.ServiceProxy`1::ShouldRetry

- ea: `0x1b8a0`
- end: `0x1b8ef`
- name: `Microsoft.Xrm.Sdk.Client.ServiceProxy`1::ShouldRetry`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1b8a0`

## string_xrefs

- `0x1b8d5`: `BadContextToken`

## pseudocode

```c

```

## disassembly

```asm
0x1b8a0  ldarga.s 2
0x1b8a2  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1b8a7  brtrue.s loc_1B8E8
0x1b8a9  ldarg.1
0x1b8aa  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x1b8af  isinst   [System.ServiceModel]System.ServiceModel.FaultException
0x1b8b4  stloc.0
0x1b8b5  ldloc.0
0x1b8b6  brfalse.s loc_1B8E8
0x1b8b8  ldloc.0
0x1b8b9  callvirt instance class [System.ServiceModel]System.ServiceModel.FaultCode [System.ServiceModel]System.ServiceModel.FaultException::get_Code()
0x1b8be  callvirt instance bool [System.ServiceModel]System.ServiceModel.FaultCode::get_IsSenderFault()
0x1b8c3  brfalse.s loc_1B8E8
0x1b8c5  ldloc.0
0x1b8c6  callvirt instance class [System.ServiceModel]System.ServiceModel.FaultCode [System.ServiceModel]System.ServiceModel.FaultException::get_Code()
0x1b8cb  callvirt instance class [System.ServiceModel]System.ServiceModel.FaultCode [System.ServiceModel]System.ServiceModel.FaultCode::get_SubCode()
0x1b8d0  callvirt instance string [System.ServiceModel]System.ServiceModel.FaultCode::get_Name()
0x1b8d5  ldstr    aBadcontexttoke// "BadContextToken"
0x1b8da  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b8df  brfalse.s loc_1B8E8
0x1b8e1  ldc.i4.1
0x1b8e2  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1b8e7  ret
0x1b8e8  ldc.i4.0
0x1b8e9  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1b8ee  ret
```
