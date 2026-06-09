# __scrt_dllmain_uninitialize_critical

- ea: `0x1800016fc`
- end: `0x180001710`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001258`

## callees

- `0x1800020ec`

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
0x1800016fc  sub     rsp, 28h
0x180001700  xor     ecx, ecx
0x180001702  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001707  add     rsp, 28h
0x18000170b  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
