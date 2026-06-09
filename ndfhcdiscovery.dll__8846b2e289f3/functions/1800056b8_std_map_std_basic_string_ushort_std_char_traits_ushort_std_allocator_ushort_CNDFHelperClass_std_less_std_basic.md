# std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CNDFHelperClass *,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CNDFHelperClass *>>>::~map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CNDFHelperClass *,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CNDFHelperClass *>>>(void)

- ea: `0x1800056b8`
- end: `0x1800056eb`
- name: `??1?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@QEAA@XZ`
- size: `51`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180013bf6`
- `0x180013c0f`
- `0x180013d77`
- `0x180013d89`
- `0x180013df7`
- `0x180013e09`

## callees

- `0x18000a6c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800056d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800056d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::map<std::wstring,CNDFHelperClass *>::~map<std::wstring,CNDFHelperClass *>(__int64 ***a1)
{
  __int64 *v2; // [rsp+30h] [rbp+8h] BYREF

  std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(
    a1,
    &v2,
    **a1,
    (__int64 *)*a1);
  operator delete(*a1);
}

```

## disassembly

```asm
0x1800056b8  push    rbx
0x1800056ba  sub     rsp, 20h
0x1800056be  mov     rbx, rcx
0x1800056c1  mov     r8, [rcx]
0x1800056c4  mov     r9, r8
0x1800056c7  mov     r8, [r8]
0x1800056ca  lea     rdx, [rsp+28h+arg_0]
0x1800056cf  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CNDFHelperClass *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CNDFHelperClass *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CNDFHelperClass *>>>>)
0x1800056d4  mov     rcx, [rbx]
0x1800056d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800056de  nop     dword ptr [rax+rax+00h]
0x1800056e3  nop
0x1800056e4  add     rsp, 20h
0x1800056e8  pop     rbx
0x1800056e9  retn
```
