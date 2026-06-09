# Microsoft.Crm.Sdk.ServiceDescription::GetRelevantResponses

- ea: `0x8720`
- end: `0x8736`
- name: `Microsoft.Crm.Sdk.ServiceDescription::GetRelevantResponses`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x75b0`

## callees

- `0x103f0`

## pseudocode

```c

```

## disassembly

```asm
0x8720  ldc.i4.s 0xFE
0x8722  newobj   instance void <GetRelevantResponses>d__12::.ctor(int32 <>1__state)
0x8727  dup
0x8728  ldarg.0
0x8729  stfld    class [mscorlib]System.Collections.IDictionary <GetRelevantResponses>d__12::<>3__requests
0x872e  dup
0x872f  ldarg.1
0x8730  stfld    bool <GetRelevantResponses>d__12::<>3__includePrivate
0x8735  ret
```
