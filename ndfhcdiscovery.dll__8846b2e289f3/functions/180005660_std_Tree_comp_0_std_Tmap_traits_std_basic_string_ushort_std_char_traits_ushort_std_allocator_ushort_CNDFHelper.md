# std::_Tree_comp<0,std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CNDFHelperClass *,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CNDFHelperClass *>>,0>>::~_Tree_comp<0,std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CNDFHelperClass *,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CNDFHelperClass *>>,0>>(void)

- ea: `0x180005660`
- end: `0x18000566a`
- name: `??1?$_Tree_comp@$0A@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013c28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005663`

## pseudocode

```c
void __fastcall std::_Tree_comp<0,std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::~_Tree_comp<0,std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>(
        void **a1)
{
  operator delete(*a1);
}

```

## disassembly

```asm
0x180005660  mov     rcx, [rcx]
0x180005663  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
