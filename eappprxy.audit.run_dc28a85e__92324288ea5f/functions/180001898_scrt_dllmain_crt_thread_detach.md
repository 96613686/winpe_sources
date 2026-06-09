# __scrt_dllmain_crt_thread_detach

- ea: `0x180001898`
- end: `0x1800018ad`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001410`

## callees

- `0x180002290`

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
0x180001898  sub     rsp, 28h
0x18000189c  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018a1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018a6  mov     al, 1
0x1800018a8  add     rsp, 28h
0x1800018ac  retn
```
