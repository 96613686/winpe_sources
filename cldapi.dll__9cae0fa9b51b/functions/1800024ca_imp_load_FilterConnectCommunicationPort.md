# __imp_load_FilterConnectCommunicationPort

- ea: `0x1800024ca`
- end: `0x1800024d6`
- name: `__imp_load_FilterConnectCommunicationPort`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002427`

## import_xrefs

- `FLTLIB!FilterConnectCommunicationPort` at `0x1800024ca`

## pseudocode

```c
__int64 load_FilterConnectCommunicationPort()
{
  return _tailMerge_fltlib_dll();
}

```

## disassembly

```asm
0x1800024ca  lea     rax, __imp_FilterConnectCommunicationPort
0x1800024d1  jmp     __tailMerge_fltlib_dll
```
