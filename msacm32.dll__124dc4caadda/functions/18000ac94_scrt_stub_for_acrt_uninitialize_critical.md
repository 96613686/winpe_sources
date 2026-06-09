# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000ac94`
- end: `0x18000ac97`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180009444`
- `0x180009474`
- `0x180009518`
- `0x180009534`
- `0x1800096d4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000ac94  mov     al, 1
0x18000ac96  retn
```
