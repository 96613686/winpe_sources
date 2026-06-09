# __scrt_dllmain_uninitialize_critical

- ea: `0x18000959c`
- end: `0x1800095b0`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800090f8`

## callees

- `0x180009bec`

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
0x18000959c  sub     rsp, 28h
0x1800095a0  xor     ecx, ecx
0x1800095a2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800095a7  add     rsp, 28h
0x1800095ab  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
