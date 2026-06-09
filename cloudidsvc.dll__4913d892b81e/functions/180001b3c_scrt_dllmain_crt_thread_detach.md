# __scrt_dllmain_crt_thread_detach

- ea: `0x180001b3c`
- end: `0x180001b51`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800016e0`

## callees

- `0x1800025a4`

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
0x180001b3c  sub     rsp, 28h
0x180001b40  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001b45  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001b4a  mov     al, 1
0x180001b4c  add     rsp, 28h
0x180001b50  retn
```
