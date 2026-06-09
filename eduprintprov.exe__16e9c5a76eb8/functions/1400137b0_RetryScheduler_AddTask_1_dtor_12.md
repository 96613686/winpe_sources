# _RetryScheduler::AddTask_::_1_::dtor$12

- ea: `0x1400137b0`
- end: `0x1400137bc`
- name: `_RetryScheduler::AddTask_::_1_::dtor$12`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140010198`

## pseudocode

```c
__int64 __fastcall RetryScheduler::AddTask_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 520));
}

```

## disassembly

```asm
0x1400137b0  lea     rcx, [rdx+208h]
0x1400137b7  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
