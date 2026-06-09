# __scrt_dllmain_crt_thread_detach

- ea: `0x180001658`
- end: `0x18000166d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x180002218`

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
0x180001658  sub     rsp, 28h
0x18000165c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001661  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001666  mov     al, 1
0x180001668  add     rsp, 28h
0x18000166c  retn
```
