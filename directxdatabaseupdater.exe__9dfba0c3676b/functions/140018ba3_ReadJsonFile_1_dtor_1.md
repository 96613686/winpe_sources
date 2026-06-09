# _ReadJsonFile_::_1_::dtor$1

- ea: `0x140018ba3`
- end: `0x140018baf`
- name: `_ReadJsonFile_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005cac`

## pseudocode

```c
__int64 __fastcall ReadJsonFile_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x140018ba3  lea     rcx, [rdx+30h]
0x140018baa  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
