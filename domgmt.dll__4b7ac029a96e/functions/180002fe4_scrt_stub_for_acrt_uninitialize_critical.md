# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002fe4`
- end: `0x180002fe7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001c50`
- `0x180001c80`
- `0x180001d24`
- `0x180001d40`
- `0x180001ee0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002fe4  mov     al, 1
0x180002fe6  retn
```
