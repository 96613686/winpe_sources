# __scrt_dllmain_crt_thread_detach

- ea: `0x180001664`
- end: `0x180001679`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001df4`

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
0x180001664  sub     rsp, 28h
0x180001668  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000166d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001672  mov     al, 1
0x180001674  add     rsp, 28h
0x180001678  retn
```
