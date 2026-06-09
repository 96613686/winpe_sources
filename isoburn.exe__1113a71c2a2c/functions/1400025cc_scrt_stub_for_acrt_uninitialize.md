# __scrt_stub_for_acrt_uninitialize

- ea: `0x1400025cc`
- end: `0x1400025cf`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001d00`
- `0x140002010`
- `0x1400021b0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x1400025cc  mov     al, 1
0x1400025ce  retn
```
