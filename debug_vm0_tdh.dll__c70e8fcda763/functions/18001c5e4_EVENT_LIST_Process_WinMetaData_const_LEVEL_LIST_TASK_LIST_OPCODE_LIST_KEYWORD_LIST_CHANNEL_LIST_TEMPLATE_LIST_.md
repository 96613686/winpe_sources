# EVENT_LIST::Process(WinMetaData const &,LEVEL_LIST &,TASK_LIST &,OPCODE_LIST &,KEYWORD_LIST &,CHANNEL_LIST &,TEMPLATE_LIST &,TASK_LIST::TASK_ENTRY_MAP &,std::map<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,TEMPLATE_ENTRY *,std::less<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>>,std::allocator<std::pair<std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const,TEMPLATE_ENTRY *>>> &,ETW_PROVIDER_ENTRY &)

- ea: `0x18001c5e4`
- end: `0x18001c75b`
- name: `?Process@EVENT_LIST@@QEAAXAEBVWinMetaData@@AEAVLEVEL_LIST@@AEAVTASK_LIST@@AEAVOPCODE_LIST@@AEAVKEYWORD_LIST@@AEAVCHANNEL_LIST@@AEAVTEMPLATE_LIST@@AEAUTASK_ENTRY_MAP@4@AEAV?$map@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@@2@@std@@AEAVETW_PROVIDER_ENTRY@@@Z`
- size: `375`
- prototype: `__int64 __usercall@<rax>(EVENT_LIST *this@<rcx>, __int64, __int64, __int64, int, __int64, __int64, struct ETW_PROVIDER_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180018eb8`

## callees

- `0x18001ac70`
- `0x18001b340`
- `0x18001c5e4`
- `0x18002d5d8`
- `0x18002ecc0`
- `0x18003104c`
- `0x180031c88`
- `0x180031cb8`
- `0x180032a6c`
- `0x180033df0`
- `0x1800353f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EVENT_LIST::Process(
        EVENT_LIST *this,
        struct WinMetaData *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        CHANNEL_LIST *a7,
        int a8,
        __int64 a9,
        __int64 a10,
        unsigned int ***a11)
{
  __int64 v15; // rcx
  struct ETW_PROVIDER_ENTRY *v16; // rdi
  unsigned int **v17; // rbx
  unsigned int **v18; // r14
  unsigned int *v19; // rdx
  __int64 v20; // rax
  __int64 v22; // [rsp+40h] [rbp-71h]
  _BYTE v23[16]; // [rsp+60h] [rbp-51h] BYREF
  _BYTE v24[16]; // [rsp+70h] [rbp-41h] BYREF
  _BYTE v25[16]; // [rsp+80h] [rbp-31h] BYREF
  _BYTE v26[16]; // [rsp+90h] [rbp-21h] BYREF
  _BYTE v27[80]; // [rsp+A0h] [rbp-11h] BYREF

  std::set<unsigned __int64>::set<unsigned __int64>(v24);
  std::set<std::wstring_view>::set<std::wstring_view>(v23);
  v16 = (struct ETW_PROVIDER_ENTRY *)a11;
  v17 = a11[55];
  v18 = a11[56];
  while ( v17 != v18 )
  {
    EVENT_LIST::ValidateEntry(v15, a2, *v17, a3, a4, a5, a6, a7, v22, a9, a10, (__int64)v16);
    a11 = (unsigned int ***)(**v17 | ((unsigned __int64)*((unsigned __int8 *)*v17 + 4) << 32));
    std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::_Emplace<unsigned __int64 const &>(
      v24,
      v25,
      &a11);
    v19 = *v17;
    if ( !v25[8] )
      ThrowWithFormatMessage(-1073221846, *v19, *((unsigned __int8 *)v19 + 4));
    if ( *((_QWORD *)v19 + 31) )
    {
      v20 = std::wstring::operator std::wstring_view(v19 + 58, v26);
      if ( !*(_BYTE *)(std::_Tree<std::_Tset_traits<std::wstring_view,std::less<std::wstring_view>,std::allocator<std::wstring_view>,0>>::insert<0,0>(
                         v23,
                         v27,
                         v20)
                     + 8) )
        ThrowWithFormatMessage(-1073221845);
    }
    ++v17;
  }
  EVENT_LIST::CreateMessageIdForEvents(this, v16);
  std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring_view,void *>>>(
    v23,
    v23);
  return std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::~_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>(v24);
}

```

## disassembly

```asm
0x18001c5e4  push    rbp
0x18001c5e6  push    rbx
0x18001c5e7  push    rsi
0x18001c5e8  push    rdi
0x18001c5e9  push    r12
0x18001c5eb  push    r13
0x18001c5ed  push    r14
0x18001c5ef  push    r15
0x18001c5f1  lea     rbp, [rsp-7]
0x18001c5f6  sub     rsp, 0B8h
0x18001c5fd  mov     r15, r9
0x18001c600  mov     r12, r8
0x18001c603  mov     r13, rdx
0x18001c606  mov     rsi, rcx
0x18001c609  lea     rcx, [rbp+3Fh+var_80]
0x18001c60d  call    ??0?$set@_KU?$less@_K@std@@V?$allocator@_K@2@@std@@QEAA@XZ; std::set<unsigned __int64>::set<unsigned __int64>(void)
0x18001c612  nop
0x18001c613  lea     rcx, [rbp+3Fh+var_90]
0x18001c617  call    ??0?$set@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring_view>::set<std::wstring_view>(void)
0x18001c61c  nop
0x18001c61d  mov     rdi, [rbp+3Fh+arg_50]
0x18001c624  mov     rbx, [rdi+1B8h]
0x18001c62b  mov     r14, [rdi+1C0h]
0x18001c632  cmp     rbx, r14
0x18001c635  jz      loc_18001C724
0x18001c63b  mov     [rsp+0F0h+var_98], rdi
0x18001c640  mov     rax, [rbp+3Fh+arg_48]
0x18001c647  mov     [rsp+0F0h+var_A0], rax
0x18001c64c  mov     rax, [rbp+3Fh+arg_40]
0x18001c653  mov     [rsp+0F0h+var_A8], rax
0x18001c658  mov     rax, [rbp+3Fh+arg_30]
0x18001c65c  mov     [rsp+0F0h+var_B8], rax
0x18001c661  mov     rax, [rbp+3Fh+arg_28]
0x18001c665  mov     [rsp+0F0h+var_C0], rax
0x18001c66a  mov     rax, [rbp+3Fh+arg_20]
0x18001c66e  mov     [rsp+0F0h+var_C8], rax
0x18001c673  mov     [rsp+0F0h+var_D0], r15
0x18001c678  mov     r9, r12
0x18001c67b  mov     r8, [rbx]
0x18001c67e  mov     rdx, r13
0x18001c681  call    ?ValidateEntry@EVENT_LIST@@AEAAXAEBVWinMetaData@@PEAVEVENT_ENTRY@@AEAVLEVEL_LIST@@AEAVTASK_LIST@@AEAVOPCODE_LIST@@AEAVKEYWORD_LIST@@AEAVCHANNEL_LIST@@AEAVTEMPLATE_LIST@@AEAUTASK_ENTRY_MAP@5@AEAV?$map@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@@2@@std@@AEAVETW_PROVIDER_ENTRY@@@Z; EVENT_LIST::ValidateEntry(WinMetaData const &,EVENT_ENTRY *,LEVEL_LIST &,TASK_LIST &,OPCODE_LIST &,KEYWORD_LIST &,CHANNEL_LIST &,TEMPLATE_LIST &,TASK_LIST::TASK_ENTRY_MAP &,std::map<std::wstring_view,TEMPLATE_ENTRY *> &,ETW_PROVIDER_ENTRY &)
0x18001c686  mov     rax, [rbx]
0x18001c689  movzx   ecx, byte ptr [rax+4]
0x18001c68d  shl     rcx, 20h
0x18001c691  mov     eax, [rax]
0x18001c693  or      rcx, rax
0x18001c696  mov     [rbp+3Fh+arg_50], rcx
0x18001c69d  lea     r8, [rbp+3Fh+arg_50]
0x18001c6a4  lea     rdx, [rbp+3Fh+var_70]
0x18001c6a8  lea     rcx, [rbp+3Fh+var_80]
0x18001c6ac  call    ??$_Emplace@AEB_K@?$_Tree@V?$_Tset_traits@_KU?$less@_K@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@_KPEAX@std@@_N@1@AEB_K@Z; std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::_Emplace<unsigned __int64 const &>(unsigned __int64 const &)
0x18001c6b1  mov     rdx, [rbx]
0x18001c6b4  cmp     [rbp+3Fh+var_68], 0
0x18001c6b8  jz      short loc_18001C712
0x18001c6ba  cmp     qword ptr [rdx+0F8h], 0
0x18001c6c2  jz      short loc_18001C6EA
0x18001c6c4  lea     rcx, [rdx+0E8h]
0x18001c6cb  lea     rdx, [rbp+3Fh+var_60]
0x18001c6cf  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18001c6d4  mov     r8, rax
0x18001c6d7  lea     rdx, [rbp+3Fh+var_50]
0x18001c6db  lea     rcx, [rbp+3Fh+var_90]
0x18001c6df  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring_view,std::less<std::wstring_view>,std::allocator<std::wstring_view>,0>>::insert<0,0>(std::wstring_view &&)
0x18001c6e4  cmp     byte ptr [rax+8], 0
0x18001c6e8  jz      short loc_18001C6F3
0x18001c6ea  add     rbx, 8
0x18001c6ee  jmp     loc_18001C632
0x18001c6f3  mov     rdx, [rbx]
0x18001c6f6  add     rdx, 0E8h
0x18001c6fd  cmp     qword ptr [rdx+18h], 7
0x18001c702  jbe     short loc_18001C707
0x18001c704  mov     rdx, [rdx]
0x18001c707  mov     ecx, 0C007EF2Bh; int
0x18001c70c  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001c712  movzx   r8d, byte ptr [rdx+4]
0x18001c717  mov     edx, [rdx]
0x18001c719  mov     ecx, 0C007EF2Ah; int
0x18001c71e  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001c724  mov     rdx, rdi; struct ETW_PROVIDER_ENTRY *
0x18001c727  mov     rcx, rsi; this
0x18001c72a  call    ?CreateMessageIdForEvents@EVENT_LIST@@AEAAXAEAVETW_PROVIDER_ENTRY@@@Z; EVENT_LIST::CreateMessageIdForEvents(ETW_PROVIDER_ENTRY &)
0x18001c72f  nop
0x18001c730  lea     rdx, [rbp+3Fh+var_90]
0x18001c734  lea     rcx, [rbp+3Fh+var_90]
0x18001c738  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring_view,void *>>>(std::allocator<std::_Tree_node<std::wstring_view,void *>> &)
0x18001c73d  nop
0x18001c73e  lea     rcx, [rbp+3Fh+var_80]
0x18001c742  call    ??1?$_Tree@V?$_Tset_traits@_KU?$less@_K@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::~_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>(void)
0x18001c747  add     rsp, 0B8h
0x18001c74e  pop     r15
0x18001c750  pop     r14
0x18001c752  pop     r13
0x18001c754  pop     r12
0x18001c756  pop     rdi
0x18001c757  pop     rsi
0x18001c758  pop     rbx
0x18001c759  pop     rbp
0x18001c75a  retn
```
