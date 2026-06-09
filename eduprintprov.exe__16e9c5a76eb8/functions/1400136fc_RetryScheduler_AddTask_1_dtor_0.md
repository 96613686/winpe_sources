# _RetryScheduler::AddTask_::_1_::dtor$0

- ea: `0x1400136fc`
- end: `0x140013708`
- name: `_RetryScheduler::AddTask_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140010198`

## pseudocode

```c
__int64 __fastcall RetryScheduler::AddTask_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 496));
}

```

## disassembly

```asm
0x1400136fc  lea     rcx, [rdx+1F0h]
0x140013703  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
