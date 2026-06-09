# __scrt_dllmain_uninitialize_critical

- ea: `0x1800079cc`
- end: `0x1800079e0`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007528`

## callees

- `0x18000851c`

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
0x1800079cc  sub     rsp, 28h
0x1800079d0  xor     ecx, ecx
0x1800079d2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800079d7  add     rsp, 28h
0x1800079db  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
