# __scrt_dllmain_uninitialize_critical

- ea: `0x18000168c`
- end: `0x1800016a0`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011e8`

## callees

- `0x180001e0c`

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
0x18000168c  sub     rsp, 28h
0x180001690  xor     ecx, ecx
0x180001692  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001697  add     rsp, 28h
0x18000169b  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
