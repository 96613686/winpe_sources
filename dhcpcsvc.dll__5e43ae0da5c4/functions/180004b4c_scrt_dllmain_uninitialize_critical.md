# __scrt_dllmain_uninitialize_critical

- ea: `0x180004b4c`
- end: `0x180004b60`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800046a8`

## callees

- `0x18000559c`

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
0x180004b4c  sub     rsp, 28h
0x180004b50  xor     ecx, ecx
0x180004b52  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004b57  add     rsp, 28h
0x180004b5b  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
