# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800020b8`
- end: `0x1800020bb`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001610`
- `0x180001640`
- `0x1800016e4`
- `0x180001700`
- `0x1800018a0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800020b8  mov     al, 1
0x1800020ba  retn
```
