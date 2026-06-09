# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002ec4`
- end: `0x180002ec7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002320`
- `0x180002350`
- `0x1800023f4`
- `0x180002410`
- `0x1800025b0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002ec4  mov     al, 1
0x180002ec6  retn
```
