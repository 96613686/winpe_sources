# __imp_load_FveOpenVolumeByHandle

- ea: `0x180003fc5`
- end: `0x180003fd1`
- name: `__imp_load_FveOpenVolumeByHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003eec`

## import_xrefs

- `FVEAPI!FveOpenVolumeByHandle` at `0x180003fc5`

## pseudocode

```c
__int64 load_FveOpenVolumeByHandle()
{
  return _tailMerge_fveapi_dll();
}

```

## disassembly

```asm
0x180003fc5  lea     rax, __imp_FveOpenVolumeByHandle
0x180003fcc  jmp     __tailMerge_fveapi_dll
```
