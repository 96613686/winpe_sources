# __scrt_dllmain_crt_thread_detach

- ea: `0x180001740`
- end: `0x180001755`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x1800020d8`

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
0x180001740  sub     rsp, 28h
0x180001744  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001749  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000174e  mov     al, 1
0x180001750  add     rsp, 28h
0x180001754  retn
```
