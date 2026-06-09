# std::_Hash<stdext::_Hmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Try_emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x180023ed4`
- end: `0x180023fc4`
- name: `??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `240`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800251d0`
- `0x180029240`

## callees

- `0x1800109b0`
- `0x180014c60`
- `0x180017aec`
- `0x180018778`
- `0x18001d3bc`
- `0x18001d3f0`
- `0x18001d584`
- `0x18001d604`
- `0x180023b94`
- `0x180023ed4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rsi
  char *v7; // r15
  __int64 v9; // [rsp+30h] [rbp-28h] BYREF
  char *v10; // [rsp+38h] [rbp-20h]
  __int128 v11; // [rsp+40h] [rbp-18h] BYREF
  __int64 v12; // [rsp+90h] [rbp+38h] BYREF

  v6 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(a1, a3);
  std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
    a1,
    &v11,
    a3,
    v6);
  if ( *((_QWORD *)&v11 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v11 + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Check_max_size(a1);
    v9 = a1 + 8;
    v7 = (char *)operator new(0x50u);
    v10 = v7;
    v12 = a3;
    ____0V__tuple___QEAV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std__V__tuple___V_1__0A___Z_S___pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std__AEAA_AEAV__tuple___QEAV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
      v7 + 16,
      &v12);
    if ( (unsigned __int8)std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Rehash_for_1(a1);
      v11 = *(_OWORD *)std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
                         a1,
                         &v11,
                         v7 + 16,
                         v6);
    }
    v10 = 0;
    *(_QWORD *)a2 = std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      v11,
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(&v9);
  }
  return a2;
}

```

## disassembly

```asm
0x180023ed4  push    rbp
0x180023ed6  push    rbx
0x180023ed7  push    rsi
0x180023ed8  push    rdi
0x180023ed9  push    r14
0x180023edb  push    r15
0x180023edd  mov     rbp, rsp
0x180023ee0  sub     rsp, 58h
0x180023ee4  mov     r14, r8
0x180023ee7  mov     rbx, rdx
0x180023eea  mov     rdi, rcx
0x180023eed  mov     rdx, r8
0x180023ef0  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x180023ef5  mov     rsi, rax
0x180023ef8  mov     r9, rax
0x180023efb  mov     r8, r14
0x180023efe  lea     rdx, [rbp+var_18]
0x180023f02  mov     rcx, rdi
0x180023f05  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180023f0a  mov     rcx, qword ptr [rbp+var_18+8]
0x180023f0e  test    rcx, rcx
0x180023f11  jz      short loc_180023F1F
0x180023f13  mov     [rbx], rcx
0x180023f16  mov     byte ptr [rbx+8], 0
0x180023f1a  jmp     loc_180023FB3
0x180023f1f  mov     rcx, rdi
0x180023f22  call    ?_Check_max_size@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEBAXXZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Check_max_size(void)
0x180023f27  lea     rax, [rdi+8]
0x180023f2b  mov     [rbp+var_28], rax
0x180023f2f  mov     [rbp+var_20], 0
0x180023f37  mov     ecx, 50h ; 'P'; Size
0x180023f3c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023f41  mov     r15, rax
0x180023f44  mov     [rbp+var_20], rax
0x180023f48  mov     [rbp+arg_0], r14
0x180023f4c  lea     rdx, [rbp+arg_0]
0x180023f50  lea     rcx, [rax+10h]
0x180023f54  call    ??$?0V?$tuple@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$tuple@$$V@1@$0A@$$Z$S@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@AEAA@AEAV?$tuple@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEAV?$tuple@$$V@1@U?$integer_sequence@_K$0A@@1@U?$integer_sequence@_K$S@1@@Z
0x180023f59  nop
0x180023f5a  mov     rcx, rdi
0x180023f5d  call    ?_Check_rehash_required_1@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEBA_NXZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Check_rehash_required_1(void)
0x180023f62  test    al, al
0x180023f64  jz      short loc_180023F89
0x180023f66  mov     rcx, rdi
0x180023f69  call    ?_Rehash_for_1@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEAAXXZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Rehash_for_1(void)
0x180023f6e  mov     r9, rsi
0x180023f71  lea     r8, [r15+10h]
0x180023f75  lea     rdx, [rbp+var_18]
0x180023f79  mov     rcx, rdi
0x180023f7c  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180023f81  movups  xmm0, xmmword ptr [rax]
0x180023f84  movdqu  [rbp+var_18], xmm0
0x180023f89  mov     [rbp+var_20], 0
0x180023f91  mov     r9, r15
0x180023f94  mov     r8, qword ptr [rbp+var_18]
0x180023f98  mov     rdx, rsi
0x180023f9b  mov     rcx, rdi
0x180023f9e  call    ?_Insert_new_node_before@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x180023fa3  mov     [rbx], rax
0x180023fa6  mov     byte ptr [rbx+8], 1
0x180023faa  lea     rcx, [rbp+var_28]
0x180023fae  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(void)
0x180023fb3  mov     rax, rbx
0x180023fb6  add     rsp, 58h
0x180023fba  pop     r15
0x180023fbc  pop     r14
0x180023fbe  pop     rdi
0x180023fbf  pop     rsi
0x180023fc0  pop     rbx
0x180023fc1  pop     rbp
0x180023fc2  retn
```
