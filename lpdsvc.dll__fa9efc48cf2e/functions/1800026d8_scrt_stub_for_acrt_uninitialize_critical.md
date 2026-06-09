# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800026d8`
- end: `0x1800026db`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ec4`
- `0x180001ef4`
- `0x180001f98`
- `0x180001fb4`
- `0x180002154`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800026d8  mov     al, 1
0x1800026da  retn
```
