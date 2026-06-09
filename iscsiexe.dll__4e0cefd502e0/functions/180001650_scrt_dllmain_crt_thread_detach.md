# __scrt_dllmain_crt_thread_detach

- ea: `0x180001650`
- end: `0x180001665`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800010a0`

## callees

- `0x180001ddc`

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
0x180001650  sub     rsp, 28h
0x180001654  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001659  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000165e  mov     al, 1
0x180001660  add     rsp, 28h
0x180001664  retn
```
