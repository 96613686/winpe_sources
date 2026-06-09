# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180004554`
- end: `0x180004557`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c48`
- `0x180003c78`
- `0x180003d1c`
- `0x180003d38`
- `0x180003ed8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180004554  mov     al, 1
0x180004556  retn
```
