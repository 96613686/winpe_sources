# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000559c`
- end: `0x18000559f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004a78`
- `0x180004aa8`
- `0x180004b4c`
- `0x180004b68`
- `0x180004d08`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000559c  mov     al, 1
0x18000559e  retn
```
