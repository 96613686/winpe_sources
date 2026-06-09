# __scrt_dllmain_crt_thread_detach

- ea: `0x180001748`
- end: `0x18000175d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011f0`

## callees

- `0x180002328`

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
0x180001748  sub     rsp, 28h
0x18000174c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001751  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001756  mov     al, 1
0x180001758  add     rsp, 28h
0x18000175c  retn
```
