# _ATL::CComObject_CNDFHelperClassRegistry_::CComObject_CNDFHelperClassRegistry__::_1_::dtor$2

- ea: `0x180013bf6`
- end: `0x180013c09`
- name: `_ATL::CComObject_CNDFHelperClassRegistry_::CComObject_CNDFHelperClassRegistry__::_1_::dtor$2`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800056b8`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CNDFHelperClassRegistry_::CComObject_CNDFHelperClassRegistry__::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return std::map<std::wstring,CNDFHelperClass *>::~map<std::wstring,CNDFHelperClass *>(*(_QWORD *)(a2 + 48) + 584LL);
}

```

## disassembly

```asm
0x180013bf6  mov     rcx, [rdx+30h]
0x180013bfd  add     rcx, 248h
0x180013c04  jmp     ??1?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,CNDFHelperClass *>::~map<std::wstring,CNDFHelperClass *>(void)
```
