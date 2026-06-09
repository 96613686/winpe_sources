# _RetryScheduler::AddTask_::_1_::dtor$16

- ea: `0x1400137d4`
- end: `0x1400137e0`
- name: `_RetryScheduler::AddTask_::_1_::dtor$16`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140010198`

## pseudocode

```c
__int64 __fastcall RetryScheduler::AddTask_::_1_::dtor_16(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 152));
}

```

## disassembly

```asm
0x1400137d4  lea     rcx, [rdx+98h]
0x1400137db  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
