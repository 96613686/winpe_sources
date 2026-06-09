# Microsoft.Crm.Sandbox.OrganizationWorkerList::DecrementReadyCounter

- ea: `0x1020`
- end: `0x102d`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::DecrementReadyCounter`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xdd0`

## pseudocode

```c

```

## disassembly

```asm
0x1020  ldarg.0
0x1021  ldflda   int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_orgReadyBucketsCount
0x1026  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x102b  pop
0x102c  ret
```
