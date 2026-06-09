# __scrt_stub_for_acrt_uninitialize

- ea: `0x140001810`
- end: `0x140001813`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011d0`
- `0x1400014f8`
- `0x140001698`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140001810  mov     al, 1
0x140001812  retn
```
