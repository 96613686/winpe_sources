# Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsValid

- ea: `0xb20`
- end: `0xb8f`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsValid`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x3010`

## callees

- `0x180`
- `0x470`
- `0x490`
- `0xa90`

## string_xrefs

- `0xb7d`: `CompletionCallbackUri`

## pseudocode

```c

```

## disassembly

```asm
0xb20  ldarg.0
0xb21  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<class Microsoft.Xrm.Async.Bridges.OperationRequest>::get_Value()
0xb26  ldarg.0
0xb27  callvirt instance string class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<class Microsoft.Xrm.Async.Bridges.OperationRequest>::get_Name()
0xb2c  call     T0x2B000001
0xb31  call     T0x2B000002
0xb36  pop
0xb37  ldarg.0
0xb38  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<class Microsoft.Xrm.Async.Bridges.OperationRequest>::get_Value()
0xb3d  callvirt instance class Microsoft.Xrm.Async.Bridges.AsyncOperation Microsoft.Xrm.Async.Bridges.OperationRequest::get_AsyncOperation()
0xb42  ldstr    aAsyncoperation// "AsyncOperation"
0xb47  call     T0x2B000003
0xb4c  call     T0x2B000004
0xb51  pop
0xb52  ldarg.0
0xb53  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<class Microsoft.Xrm.Async.Bridges.OperationRequest>::get_Value()
0xb58  callvirt instance class Microsoft.Xrm.Async.Bridges.AsyncOperation Microsoft.Xrm.Async.Bridges.OperationRequest::get_AsyncOperation()
0xb5d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Async.Bridges.AsyncOperation::get_OrganizationId()
0xb62  ldstr    aOrganizationid// "OrganizationId"
0xb67  call     T0x2B00001E
0xb6c  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<valuetype [mscorlib]System.Guid> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<valuetype [mscorlib]System.Guid> arg)
0xb71  pop
0xb72  ldarg.0
0xb73  callvirt instance var<u1> class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<class Microsoft.Xrm.Async.Bridges.OperationRequest>::get_Value()
0xb78  callvirt instance class [System]System.Uri Microsoft.Xrm.Async.Bridges.OperationRequest::get_CompletionCallbackUri()
0xb7d  ldstr    aCompletioncall// "CompletionCallbackUri"
0xb82  call     T0x2B00000F
0xb87  call     T0x2B000010
0xb8c  pop
0xb8d  ldarg.0
0xb8e  ret
```
