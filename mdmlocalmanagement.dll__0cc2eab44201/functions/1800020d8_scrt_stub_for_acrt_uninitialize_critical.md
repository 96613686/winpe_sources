# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800020d8`
- end: `0x1800020db`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001710`
- `0x180001740`
- `0x1800017e4`
- `0x180001800`
- `0x1800019a0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800020d8  mov     al, 1
0x1800020da  retn
```
