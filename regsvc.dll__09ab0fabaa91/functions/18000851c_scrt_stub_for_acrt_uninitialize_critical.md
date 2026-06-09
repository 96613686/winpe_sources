# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000851c`
- end: `0x18000851f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800078f8`
- `0x180007928`
- `0x1800079cc`
- `0x1800079e8`
- `0x180007b88`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000851c  mov     al, 1
0x18000851e  retn
```
