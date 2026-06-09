# __scrt_stub_for_acrt_uninitialize

- ea: `0x140002430`
- end: `0x140002433`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001e10`
- `0x140002124`
- `0x1400022c4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140002430  mov     al, 1
0x140002432  retn
```
