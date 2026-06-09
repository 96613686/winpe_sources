# _ATL::CComObject_CNDFHelperClassRegistry_::CComObject_CNDFHelperClassRegistry__::_1_::dtor$3

- ea: `0x180013c0f`
- end: `0x180013c22`
- name: `_ATL::CComObject_CNDFHelperClassRegistry_::CComObject_CNDFHelperClassRegistry__::_1_::dtor$3`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800056b8`

## pseudocode

```c
__int64 __fastcall ATL::CComObject_CNDFHelperClassRegistry_::CComObject_CNDFHelperClassRegistry__::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return std::map<std::wstring,CNDFHelperClass *>::~map<std::wstring,CNDFHelperClass *>(*(_QWORD *)(a2 + 48) + 600LL);
}

```

## disassembly

```asm
0x180013c0f  mov     rcx, [rdx+30h]
0x180013c16  add     rcx, 258h
0x180013c1d  jmp     ??1?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,CNDFHelperClass *>::~map<std::wstring,CNDFHelperClass *>(void)
```
