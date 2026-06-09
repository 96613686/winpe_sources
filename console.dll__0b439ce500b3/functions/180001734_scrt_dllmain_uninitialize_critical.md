# __scrt_dllmain_uninitialize_critical

- ea: `0x180001734`
- end: `0x180001748`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001398`

## callees

- `0x1800030f8`

## pseudocode

```c
__int64 _scrt_dllmain_uninitialize_critical()
{
  __int64 v0; // rcx

  _scrt_stub_for_acrt_uninitialize_critical(0);
  return _scrt_stub_for_acrt_uninitialize_critical(v0);
}

```

## disassembly

```asm
0x180001734  sub     rsp, 28h
0x180001738  xor     ecx, ecx
0x18000173a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000173f  add     rsp, 28h
0x180001743  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
