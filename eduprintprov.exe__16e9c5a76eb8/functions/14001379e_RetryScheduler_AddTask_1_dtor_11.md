# _RetryScheduler::AddTask_::_1_::dtor$11

- ea: `0x14001379e`
- end: `0x1400137aa`
- name: `_RetryScheduler::AddTask_::_1_::dtor$11`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140010198`

## pseudocode

```c
__int64 __fastcall RetryScheduler::AddTask_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 128));
}

```

## disassembly

```asm
0x14001379e  lea     rcx, [rdx+80h]
0x1400137a5  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
