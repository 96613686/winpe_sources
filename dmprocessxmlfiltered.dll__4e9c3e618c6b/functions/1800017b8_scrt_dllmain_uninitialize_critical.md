# __scrt_dllmain_uninitialize_critical

- ea: `0x1800017b8`
- end: `0x1800017cc`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001308`

## callees

- `0x18000209c`

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
0x1800017b8  sub     rsp, 28h
0x1800017bc  xor     ecx, ecx
0x1800017be  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017c3  add     rsp, 28h
0x1800017c7  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
