# __scrt_dllmain_crt_thread_detach

- ea: `0x180002040`
- end: `0x180002055`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001bf0`

## callees

- `0x180002b00`

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
0x180002040  sub     rsp, 28h
0x180002044  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002049  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000204e  mov     al, 1
0x180002050  add     rsp, 28h
0x180002054  retn
```
