# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,unsigned __int64>>,0>>(void)

- ea: `0x1800081d8`
- end: `0x180008240`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(void **)`
- caller_count: `10`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008320`
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
- `0x180007dc0`
- `0x1800081d8`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(
        void **a1)
{
  char *v2; // rdi
  char *v3; // rbx

  v2 = (char *)*((_QWORD *)*a1 + 1);
  while ( !v2[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned __int64>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>>>(
      a1,
      a1,
      *((_QWORD *)v2 + 2));
    v3 = v2;
    v2 = *(char **)v2;
    std::wstring::~wstring(v3 + 32);
    operator delete(v3, 0x48u);
  }
  operator delete(*a1, 0x48u);
}

```

## disassembly

```asm
0x1800081d8  mov     [rsp+arg_8], rbx
0x1800081dd  mov     [rsp+arg_10], rsi
0x1800081e2  push    rdi
0x1800081e3  sub     rsp, 20h
0x1800081e7  mov     rax, [rcx]
0x1800081ea  mov     rsi, rcx
0x1800081ed  mov     rdi, [rax+8]
0x1800081f1  jmp     short loc_18000821E
0x1800081f3  mov     r8, [rdi+10h]
0x1800081f7  mov     rdx, rsi
0x1800081fa  mov     rcx, rsi
0x1800081fd  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned __int64>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>> &,std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *> *)
0x180008202  mov     rbx, rdi
0x180008205  mov     rdi, [rdi]
0x180008208  lea     rcx, [rbx+20h]
0x18000820c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008211  mov     edx, 48h ; 'H'; unsigned __int64
0x180008216  mov     rcx, rbx; void *
0x180008219  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000821e  cmp     byte ptr [rdi+19h], 0
0x180008222  jz      short loc_1800081F3
0x180008224  mov     rcx, [rsi]; void *
0x180008227  mov     edx, 48h ; 'H'; unsigned __int64
0x18000822c  mov     rbx, [rsp+28h+arg_8]
0x180008231  mov     rsi, [rsp+28h+arg_10]
0x180008236  add     rsp, 20h
0x18000823a  pop     rdi
0x18000823b  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
