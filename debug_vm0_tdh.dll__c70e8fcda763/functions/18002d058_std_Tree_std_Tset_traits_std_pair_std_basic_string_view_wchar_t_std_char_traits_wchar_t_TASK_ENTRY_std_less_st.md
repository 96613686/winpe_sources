# std::_Tree<std::_Tset_traits<std::pair<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,TASK_ENTRY *>,std::less<std::pair<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,TASK_ENTRY *>>,std::allocator<std::pair<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,TASK_ENTRY *>>,0>>::_Emplace<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,TASK_ENTRY * const &>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,TASK_ENTRY * const &)

- ea: `0x18002d058`
- end: `0x18002d1a6`
- name: `??$_Emplace@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBQEAVTASK_ENTRY@@@?$_Tree@V?$_Tset_traits@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@U?$less@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@@2@V?$allocator@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@PEAX@std@@_N@1@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBQEAVTASK_ENTRY@@@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180019bd4`

## callees

- `0x1800207e4`
- `0x18002d058`
- `0x180032964`
- `0x180033df0`
- `0x180033e98`
- `0x18003c534`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002d14f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002d14f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Tree<std::_Tset_traits<std::pair<std::wstring_view,TASK_ENTRY *>,std::less<std::pair<std::wstring_view,TASK_ENTRY *>>,std::allocator<std::pair<std::wstring_view,TASK_ENTRY *>>,0>>::_Emplace<std::wstring &,TASK_ENTRY * const &>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 *v8; // rdi
  _QWORD *v9; // r12
  char *v10; // r13
  __int64 *v11; // rdi
  __int64 *v12; // rbx
  unsigned int v13; // esi
  _QWORD *v14; // rbp
  _QWORD *v16; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v17; // [rsp+28h] [rbp-50h]

  v8 = (__int64 *)*a1;
  v16 = a1;
  v9 = operator new(0x38u);
  v17 = v9;
  v10 = (char *)(v9 + 4);
  std::wstring::operator std::wstring_view(a3, v9 + 4);
  v9[6] = *a4;
  *v9 = v8;
  v9[1] = v8;
  v9[2] = v8;
  *((_WORD *)v9 + 12) = 0;
  v11 = (__int64 *)*a1;
  v12 = *(__int64 **)(*a1 + 8LL);
  v13 = 0;
  if ( *((_BYTE *)v12 + 25) )
  {
    v14 = *(_QWORD **)(*a1 + 8LL);
  }
  else
  {
    do
    {
      v14 = v12;
      if ( (unsigned __int8)std::less<std::pair<std::wstring_view,TASK_ENTRY *>>::operator()(0, v12 + 4, v10) )
      {
        v13 = 0;
        v12 = (__int64 *)v12[2];
      }
      else
      {
        v13 = 1;
        v11 = v12;
        v12 = (__int64 *)*v12;
      }
    }
    while ( !*((_BYTE *)v12 + 25) );
  }
  if ( *((_BYTE *)v11 + 25)
    || (unsigned __int8)std::less<std::pair<std::wstring_view,TASK_ENTRY *>>::operator()(0, v10, v11 + 4) )
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Xlength_error("map/set too long");
    v17 = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>((__int64)&v16);
    v16 = v14;
    v17 = (_QWORD *)v13;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<unsigned __int64>>::_Insert_node(a1, &v16, v9);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v11;
    *(_BYTE *)(a2 + 8) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>((__int64)&v16);
  }
  return a2;
}

```

## disassembly

```asm
0x18002d058  push    rbx
0x18002d05a  push    rbp
0x18002d05b  push    rsi
0x18002d05c  push    rdi
0x18002d05d  push    r12
0x18002d05f  push    r13
0x18002d061  push    r14
0x18002d063  push    r15
0x18002d065  sub     rsp, 38h
0x18002d069  mov     rsi, r9
0x18002d06c  mov     rbx, r8
0x18002d06f  mov     r14, rdx
0x18002d072  mov     r15, rcx
0x18002d075  mov     rdi, [rcx]
0x18002d078  mov     [rsp+78h+var_58], rcx
0x18002d07d  mov     [rsp+78h+var_50], 0
0x18002d086  mov     ecx, 38h ; '8'; Size
0x18002d08b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d090  mov     r12, rax
0x18002d093  mov     [rsp+78h+var_50], rax
0x18002d098  lea     r13, [rax+20h]
0x18002d09c  mov     rdx, r13
0x18002d09f  mov     rcx, rbx
0x18002d0a2  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18002d0a7  mov     rcx, [rsi]
0x18002d0aa  mov     [r13+10h], rcx
0x18002d0ae  mov     [r12], rdi
0x18002d0b2  mov     [r12+8], rdi
0x18002d0b7  mov     [r12+10h], rdi
0x18002d0bc  xor     ecx, ecx
0x18002d0be  mov     [r12+18h], cx
0x18002d0c4  mov     rdi, [r15]
0x18002d0c7  mov     rbx, [rdi+8]
0x18002d0cb  mov     esi, ecx
0x18002d0cd  xor     eax, eax
0x18002d0cf  mov     [rsp+78h+arg_0], rax
0x18002d0d7  cmp     [rbx+19h], cl
0x18002d0da  jnz     short loc_18002D10B
0x18002d0dc  mov     rbp, rbx
0x18002d0df  lea     rdx, [rbx+20h]
0x18002d0e3  mov     r8, r13
0x18002d0e6  call    ??R?$less@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@@std@@QEBA_NAEBU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@1@0@Z; std::less<std::pair<std::wstring_view,TASK_ENTRY *>>::operator()(std::pair<std::wstring_view,TASK_ENTRY *> const &,std::pair<std::wstring_view,TASK_ENTRY *> const &)
0x18002d0eb  xor     ecx, ecx
0x18002d0ed  test    al, al
0x18002d0ef  jz      short loc_18002D0F9
0x18002d0f1  mov     esi, ecx
0x18002d0f3  mov     rbx, [rbx+10h]
0x18002d0f7  jmp     short loc_18002D104
0x18002d0f9  mov     esi, 1
0x18002d0fe  mov     rdi, rbx
0x18002d101  mov     rbx, [rbx]
0x18002d104  cmp     [rbx+19h], cl
0x18002d107  jz      short loc_18002D0DC
0x18002d109  jmp     short loc_18002D10E
0x18002d10b  mov     rbp, rbx
0x18002d10e  cmp     [rdi+19h], cl
0x18002d111  jnz     short loc_18002D138
0x18002d113  lea     r8, [rdi+20h]
0x18002d117  mov     rdx, r13
0x18002d11a  call    ??R?$less@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@@std@@QEBA_NAEBU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@1@0@Z; std::less<std::pair<std::wstring_view,TASK_ENTRY *>>::operator()(std::pair<std::wstring_view,TASK_ENTRY *> const &,std::pair<std::wstring_view,TASK_ENTRY *> const &)
0x18002d11f  xor     ecx, ecx
0x18002d121  test    al, al
0x18002d123  jnz     short loc_18002D138
0x18002d125  mov     [r14], rdi
0x18002d128  mov     [r14+8], cl
0x18002d12c  lea     rcx, [rsp+78h+var_58]
0x18002d131  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>(void)
0x18002d136  jmp     short loc_18002D192
0x18002d138  mov     rax, 492492492492492h
0x18002d142  cmp     [r15+8], rax
0x18002d146  jnz     short loc_18002D156
0x18002d148  lea     rcx, aMapSetTooLong; "map/set too long"
0x18002d14f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002d156  mov     [rsp+78h+var_50], rcx
0x18002d15b  lea     rcx, [rsp+78h+var_58]
0x18002d160  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>(void)
0x18002d165  mov     [rsp+78h+var_58], rbp
0x18002d16a  mov     dword ptr [rsp+78h+var_50], esi
0x18002d16e  mov     rax, [rsp+78h+arg_0]
0x18002d176  mov     dword ptr [rsp+78h+var_50+4], eax
0x18002d17a  mov     r8, r12
0x18002d17d  lea     rdx, [rsp+78h+var_58]
0x18002d182  mov     rcx, r15
0x18002d185  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@_K@std@@@std@@QEAAPEAU?$_Tree_node@_KPEAX@2@U?$_Tree_id@PEAU?$_Tree_node@_KPEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<unsigned __int64>>::_Insert_node(std::_Tree_id<std::_Tree_node<unsigned __int64,void *> *>,std::_Tree_node<unsigned __int64,void *> * const)
0x18002d18a  mov     [r14], rax
0x18002d18d  mov     byte ptr [r14+8], 1
0x18002d192  mov     rax, r14
0x18002d195  add     rsp, 38h
0x18002d199  pop     r15
0x18002d19b  pop     r14
0x18002d19d  pop     r13
0x18002d19f  pop     r12
0x18002d1a1  pop     rdi
0x18002d1a2  pop     rsi
0x18002d1a3  pop     rbp
0x18002d1a4  pop     rbx
0x18002d1a5  retn
```
