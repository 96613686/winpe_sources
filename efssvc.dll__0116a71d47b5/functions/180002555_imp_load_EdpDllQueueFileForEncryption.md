# __imp_load_EdpDllQueueFileForEncryption

- ea: `0x180002555`
- end: `0x180002561`
- name: `__imp_load_EdpDllQueueFileForEncryption`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllQueueFileForEncryption` at `0x180002555`

## pseudocode

```c
__int64 load_EdpDllQueueFileForEncryption()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002555  lea     rax, __imp_EdpDllQueueFileForEncryption
0x18000255c  jmp     __tailMerge_efscore_dll
```
