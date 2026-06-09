# __scrt_dllmain_uninitialize_critical

- ea: `0x180001684`
- end: `0x180001698`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__vcrt_bool()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800012e8`

## callees

- `0x180002c74`
- `0x180005364`

## pseudocode

```c
__vcrt_bool _scrt_dllmain_uninitialize_critical()
{
  _scrt_stub_for_acrt_uninitialize_critical(0);
  return _vcrt_uninitialize_critical();
}

```

## disassembly

```asm
0x180001684  sub     rsp, 28h
0x180001688  xor     ecx, ecx
0x18000168a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000168f  add     rsp, 28h
0x180001693  jmp     __vcrt_uninitialize_critical
```
