# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>,0>>(void)

- ea: `0x180008248`
- end: `0x1800082af`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(void **)`
- caller_count: `10`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000832c`
- `0x1800083c8`
- `0x180008540`
- `0x1800085ac`
- `0x1800088dc`
- `0x180008fd8`
- `0x180009c20`
- `0x180009da4`
- `0x180009eac`
- `0x18000a400`

## callees

- `0x180001564`
- `0x180003648`
- `0x180007e20`
- `0x180008248`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(
        void **a1)
{
  char *v2; // r14
  char *v3; // rdi

  v2 = (char *)*((_QWORD *)*a1 + 1);
  while ( !v2[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      a1,
      a1,
      *((_QWORD *)v2 + 2));
    v3 = v2;
    v2 = *(char **)v2;
    std::wstring::~wstring(v3 + 64);
    std::wstring::~wstring(v3 + 32);
    operator delete(v3, 0x60u);
  }
  operator delete(*a1, 0x60u);
}

```

## disassembly

```asm
0x180008248  push    rbx
0x18000824a  push    rsi
0x18000824b  push    rdi
0x18000824c  push    r14
0x18000824e  sub     rsp, 28h
0x180008252  mov     rax, [rcx]
0x180008255  mov     rsi, rcx
0x180008258  mov     r14, [rax+8]
0x18000825c  jmp     short loc_180008292
0x18000825e  mov     r8, [r14+10h]
0x180008262  mov     rdx, rsi
0x180008265  mov     rcx, rsi
0x180008268  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x18000826d  mov     rdi, r14
0x180008270  mov     r14, [r14]
0x180008273  lea     rcx, [rdi+40h]
0x180008277  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000827c  lea     rcx, [rdi+20h]
0x180008280  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008285  mov     edx, 60h ; '`'; unsigned __int64
0x18000828a  mov     rcx, rdi; void *
0x18000828d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008292  cmp     byte ptr [r14+19h], 0
0x180008297  jz      short loc_18000825E
0x180008299  mov     rcx, [rsi]; void *
0x18000829c  mov     edx, 60h ; '`'; unsigned __int64
0x1800082a1  add     rsp, 28h
0x1800082a5  pop     r14
0x1800082a7  pop     rdi
0x1800082a8  pop     rsi
0x1800082a9  pop     rbx
0x1800082aa  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
