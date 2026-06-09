# std::_Tree<std::_Tset_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WstringCaseInsensitiveCompare,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,0>>::~_Tree<std::_Tset_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WstringCaseInsensitiveCompare,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,0>>(void)

- ea: `0x18000b164`
- end: `0x18000b1cc`
- name: `??1?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b1d4`
- `0x18000c38c`

## callees

- `0x180001564`
- `0x180003648`
- `0x18000a904`
- `0x18000b164`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(
        void **a1)
{
  char *v2; // rdi
  char *v3; // rbx

  v2 = (char *)*((_QWORD *)*a1 + 1);
  while ( !v2[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring,void *>>>(
      a1,
      a1,
      *((_QWORD *)v2 + 2));
    v3 = v2;
    v2 = *(char **)v2;
    std::wstring::~wstring(v3 + 32);
    operator delete(v3, 0x40u);
  }
  operator delete(*a1, 0x40u);
}

```

## disassembly

```asm
0x18000b164  mov     [rsp+arg_8], rbx
0x18000b169  mov     [rsp+arg_10], rsi
0x18000b16e  push    rdi
0x18000b16f  sub     rsp, 20h
0x18000b173  mov     rax, [rcx]
0x18000b176  mov     rsi, rcx
0x18000b179  mov     rdi, [rax+8]
0x18000b17d  jmp     short loc_18000B1AA
0x18000b17f  mov     r8, [rdi+10h]
0x18000b183  mov     rdx, rsi
0x18000b186  mov     rcx, rsi
0x18000b189  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &,std::_Tree_node<std::wstring,void *> *)
0x18000b18e  mov     rbx, rdi
0x18000b191  mov     rdi, [rdi]
0x18000b194  lea     rcx, [rbx+20h]
0x18000b198  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b19d  mov     edx, 40h ; '@'; unsigned __int64
0x18000b1a2  mov     rcx, rbx; void *
0x18000b1a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b1aa  cmp     byte ptr [rdi+19h], 0
0x18000b1ae  jz      short loc_18000B17F
0x18000b1b0  mov     rcx, [rsi]; void *
0x18000b1b3  mov     edx, 40h ; '@'; unsigned __int64
0x18000b1b8  mov     rbx, [rsp+28h+arg_8]
0x18000b1bd  mov     rsi, [rsp+28h+arg_10]
0x18000b1c2  add     rsp, 20h
0x18000b1c6  pop     rdi
0x18000b1c7  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
