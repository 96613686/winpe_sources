# _std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____CNDFHelperClass___std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CNDFHelperClass______0___::_Copy_nodes_std::integral_constant_bool_0____::_1_::catch$0

- ea: `0x180013b64`
- end: `0x180013b88`
- name: `_std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____CNDFHelperClass___std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CNDFHelperClass______0___::_Copy_nodes_std::integral_constant_bool_0____::_1_::catch$0`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f9c`
- `0x18000a27c`

## pseudocode

```c
void __fastcall __noreturn std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____CNDFHelperClass___std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CNDFHelperClass______0___::_Copy_nodes_std::integral_constant_bool_0____::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Erase(
    *(_QWORD *)(a2 + 80),
    *(_QWORD *)(a2 + 88));
  throw;
}

```

## disassembly

```asm
0x180013b64  mov     [rsp+arg_8], rdx
0x180013b69  push    rbp
0x180013b6a  sub     rsp, 20h
0x180013b6e  mov     rbp, rdx
0x180013b71  mov     rdx, [rbp+58h]
0x180013b75  mov     rcx, [rbp+50h]
0x180013b79  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,CNDFHelperClass *>,void *> *)
0x180013b7e  xor     edx, edx; pThrowInfo
0x180013b80  xor     ecx, ecx; pExceptionObject
0x180013b82  call    _CxxThrowException_0
```
