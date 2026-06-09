# PcDeregisterQoSProviderComplete

- ea: `0x14000feb0`
- end: `0x14000febf`
- name: `PcDeregisterQoSProviderComplete`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001edb0`

## callees

- `0x14000c8c8`

## pseudocode

```c
__int64 PcDeregisterQoSProviderComplete()
{
  return PcpDereferenceDriver();
}

```

## disassembly

```asm
0x14000feb0  sub     rsp, 28h
0x14000feb4  call    PcpDereferenceDriver
0x14000feb9  add     rsp, 28h
0x14000febd  retn
```
