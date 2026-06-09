# __scrt_dllmain_crt_thread_detach

- ea: `0x1800016f8`
- end: `0x18000170d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x1800022f0`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _scrt_stub_for_acrt_uninitialize_critical();
  _scrt_stub_for_acrt_uninitialize_critical();
  return 1;
}

```

## disassembly

```asm
0x1800016f8  sub     rsp, 28h
0x1800016fc  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001701  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001706  mov     al, 1
0x180001708  add     rsp, 28h
0x18000170c  retn
```
