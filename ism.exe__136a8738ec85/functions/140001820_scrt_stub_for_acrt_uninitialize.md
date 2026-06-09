# __scrt_stub_for_acrt_uninitialize

- ea: `0x140001820`
- end: `0x140001823`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011b0`
- `0x1400014fc`
- `0x14000169c`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140001820  mov     al, 1
0x140001822  retn
```
