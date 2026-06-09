# __scrt_stub_for_acrt_uninitialize

- ea: `0x140001880`
- end: `0x140001883`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011c0`
- `0x140001518`
- `0x1400016b8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140001880  mov     al, 1
0x140001882  retn
```
