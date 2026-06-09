# __scrt_dllmain_uninitialize_critical

- ea: `0x18000303c`
- end: `0x180003050`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002c38`

## callees

- `0x180003ac8`

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
0x18000303c  sub     rsp, 28h
0x180003040  xor     ecx, ecx
0x180003042  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003047  add     rsp, 28h
0x18000304b  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
