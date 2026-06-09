# Microsoft.Crm.Sandbox.OrganizationWorkerList::IncrementReadyCounter

- ea: `0x1000`
- end: `0x100d`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::IncrementReadyCounter`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xd80`

## pseudocode

```c

```

## disassembly

```asm
0x1000  ldarg.0
0x1001  ldflda   int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_orgReadyBucketsCount
0x1006  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x100b  pop
0x100c  ret
```
