# __scrt_dllmain_crt_thread_detach

- ea: `0x18000b4f0`
- end: `0x18000b505`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b090`

## callees

- `0x18000c350`

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
0x18000b4f0  sub     rsp, 28h
0x18000b4f4  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b4f9  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b4fe  mov     al, 1
0x18000b500  add     rsp, 28h
0x18000b504  retn
```
