# _ReadJsonFile_::_1_::dtor$0

- ea: `0x140018bc7`
- end: `0x140018bd3`
- name: `_ReadJsonFile_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005cac`

## pseudocode

```c
__int64 __fastcall ReadJsonFile_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x140018bc7  lea     rcx, [rdx+38h]
0x140018bce  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
