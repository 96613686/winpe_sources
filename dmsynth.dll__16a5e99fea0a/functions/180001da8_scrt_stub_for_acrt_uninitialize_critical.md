# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001da8`
- end: `0x180001dab`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016d4`
- `0x180001704`
- `0x1800017a8`
- `0x1800017c4`
- `0x180001964`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001da8  mov     al, 1
0x180001daa  retn
```
