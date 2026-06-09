# Microsoft.Crm.Sdk.ServiceDescription::GetTypes

- ea: `0x8b60`
- end: `0x8b76`
- name: `Microsoft.Crm.Sdk.ServiceDescription::GetTypes`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8ad0`
- `0x8b50`

## callees

- `0x105a0`

## pseudocode

```c

```

## disassembly

```asm
0x8b60  ldc.i4.s 0xFE
0x8b62  newobj   instance void <GetTypes>d__27::.ctor(int32 <>1__state)
0x8b67  dup
0x8b68  ldarg.0
0x8b69  stfld    class Microsoft.Crm.Sdk.ServiceDescription <GetTypes>d__27::<>4__this
0x8b6e  dup
0x8b6f  ldarg.1
0x8b70  stfld    string <GetTypes>d__27::<>3__interfaceName
0x8b75  ret
```
