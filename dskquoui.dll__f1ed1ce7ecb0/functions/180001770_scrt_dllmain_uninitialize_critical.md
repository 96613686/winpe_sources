# __scrt_dllmain_uninitialize_critical

- ea: `0x180001770`
- end: `0x180001784`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012f8`

## callees

- `0x180002368`

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
0x180001770  sub     rsp, 28h
0x180001774  xor     ecx, ecx
0x180001776  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000177b  add     rsp, 28h
0x18000177f  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
