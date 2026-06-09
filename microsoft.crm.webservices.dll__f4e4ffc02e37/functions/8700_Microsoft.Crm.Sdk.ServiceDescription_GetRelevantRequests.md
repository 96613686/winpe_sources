# Microsoft.Crm.Sdk.ServiceDescription::GetRelevantRequests

- ea: `0x8700`
- end: `0x8716`
- name: `Microsoft.Crm.Sdk.ServiceDescription::GetRelevantRequests`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x72c0`

## callees

- `0x10240`

## pseudocode

```c

```

## disassembly

```asm
0x8700  ldc.i4.s 0xFE
0x8702  newobj   instance void <GetRelevantRequests>d__11::.ctor(int32 <>1__state)
0x8707  dup
0x8708  ldarg.0
0x8709  stfld    class [mscorlib]System.Collections.IDictionary <GetRelevantRequests>d__11::<>3__requests
0x870e  dup
0x870f  ldarg.1
0x8710  stfld    bool <GetRelevantRequests>d__11::<>3__includePrivate
0x8715  ret
```
