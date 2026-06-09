# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002328`
- end: `0x18000232b`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001718`
- `0x180001748`
- `0x1800017ec`
- `0x180001808`
- `0x1800019a8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002328  mov     al, 1
0x18000232a  retn
```
