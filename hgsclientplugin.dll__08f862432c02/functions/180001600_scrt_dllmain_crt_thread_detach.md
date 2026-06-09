# __scrt_dllmain_crt_thread_detach

- ea: `0x180001600`
- end: `0x180001615`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011b0`

## callees

- `0x18000206c`

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
0x180001600  sub     rsp, 28h
0x180001604  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001609  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000160e  mov     al, 1
0x180001610  add     rsp, 28h
0x180001614  retn
```
