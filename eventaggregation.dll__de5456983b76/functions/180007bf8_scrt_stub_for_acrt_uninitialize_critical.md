# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180007bf8`
- end: `0x180007bfb`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180007498`
- `0x1800074c8`
- `0x18000756c`
- `0x180007588`
- `0x180007728`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180007bf8  mov     al, 1
0x180007bfa  retn
```
