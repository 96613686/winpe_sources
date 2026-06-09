# _UpdateAdapters_::_1_::dtor$3

- ea: `0x140011a64`
- end: `0x140011a70`
- name: `_UpdateAdapters_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140006490`

## pseudocode

```c
__int64 __fastcall UpdateAdapters_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>::~com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>((__int64 *)(a2 + 104));
}

```

## disassembly

```asm
0x140011a64  lea     rcx, [rdx+68h]
0x140011a6b  jmp     ??1?$com_ptr_t@UIDXGIAdapter1@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>::~com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>(void)
```
