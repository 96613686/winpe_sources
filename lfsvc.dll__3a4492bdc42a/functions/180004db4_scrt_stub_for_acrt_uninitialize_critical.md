# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180004db4`
- end: `0x180004db7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004404`
- `0x180004434`
- `0x1800044d8`
- `0x1800044f4`
- `0x180004694`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180004db4  mov     al, 1
0x180004db6  retn
```
