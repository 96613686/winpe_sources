# _UpdateAdapters_::_1_::dtor$2

- ea: `0x140011a52`
- end: `0x140011a5e`
- name: `_UpdateAdapters_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140006490`

## pseudocode

```c
__int64 __fastcall UpdateAdapters_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>::~com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>((__int64 *)(a2 + 144));
}

```

## disassembly

```asm
0x140011a52  lea     rcx, [rdx+90h]
0x140011a59  jmp     ??1?$com_ptr_t@UIDXGIAdapter1@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>::~com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>(void)
```
