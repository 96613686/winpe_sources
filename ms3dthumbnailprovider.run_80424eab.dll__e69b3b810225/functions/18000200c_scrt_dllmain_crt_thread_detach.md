# __scrt_dllmain_crt_thread_detach

- ea: `0x18000200c`
- end: `0x180002021`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001b80`

## callees

- `0x1800029c0`

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
0x18000200c  sub     rsp, 28h
0x180002010  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002015  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000201a  mov     al, 1
0x18000201c  add     rsp, 28h
0x180002020  retn
```
