# _TaskHelper::Init_::_1_::dtor$6

- ea: `0x140018f1c`
- end: `0x140018f28`
- name: `_TaskHelper::Init_::_1_::dtor$6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005cac`

## pseudocode

```c
__int64 __fastcall TaskHelper::Init_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 456));
}

```

## disassembly

```asm
0x140018f1c  lea     rcx, [rdx+1C8h]
0x140018f23  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
