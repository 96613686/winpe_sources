# _RetryScheduler::AddTask_::_1_::dtor$7

- ea: `0x140013768`
- end: `0x140013774`
- name: `_RetryScheduler::AddTask_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140010198`

## pseudocode

```c
__int64 __fastcall RetryScheduler::AddTask_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 136));
}

```

## disassembly

```asm
0x140013768  lea     rcx, [rdx+88h]
0x14001376f  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
