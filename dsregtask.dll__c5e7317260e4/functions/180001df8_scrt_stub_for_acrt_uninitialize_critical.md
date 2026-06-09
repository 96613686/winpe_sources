# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001df8`
- end: `0x180001dfb`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001510`
- `0x180001540`
- `0x1800015e4`
- `0x180001600`
- `0x1800017a0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001df8  mov     al, 1
0x180001dfa  retn
```
