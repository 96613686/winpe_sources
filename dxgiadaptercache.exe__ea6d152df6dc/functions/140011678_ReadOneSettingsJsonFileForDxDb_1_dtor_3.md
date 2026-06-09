# _ReadOneSettingsJsonFileForDxDb_::_1_::dtor$3

- ea: `0x140011678`
- end: `0x140011684`
- name: `_ReadOneSettingsJsonFileForDxDb_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140006490`

## pseudocode

```c
__int64 __fastcall ReadOneSettingsJsonFileForDxDb_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>::~com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>((__int64 *)(a2 + 40));
}

```

## disassembly

```asm
0x140011678  lea     rcx, [rdx+28h]
0x14001167f  jmp     ??1?$com_ptr_t@UIDXGIAdapter1@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>::~com_ptr_t<IDXGIAdapter1,wil::err_exception_policy>(void)
```
