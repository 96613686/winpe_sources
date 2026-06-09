# __scrt_dllmain_uninitialize_critical

- ea: `0x180012de8`
- end: `0x180012dfc`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012938`

## callees

- `0x180014b58`
- `0x1800183bc`

## pseudocode

```c
__vcrt_bool _scrt_dllmain_uninitialize_critical()
{
  _acrt_uninitialize_critical(0);
  return _vcrt_uninitialize_critical();
}

```

## disassembly

```asm
0x180012de8  sub     rsp, 28h
0x180012dec  xor     ecx, ecx; Terminating
0x180012dee  call    __acrt_uninitialize_critical
0x180012df3  add     rsp, 28h
0x180012df7  jmp     __vcrt_uninitialize_critical
```
