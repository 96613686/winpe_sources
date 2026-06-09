# std::_Hash<stdext::_Hmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::emplace<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &)

- ea: `0x180017e94`
- end: `0x180017f9e`
- name: `??$emplace@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180028e40`

## callees

- `0x180004a70`
- `0x1800109b0`
- `0x180014c60`
- `0x180017aec`
- `0x180017e94`
- `0x180018778`
- `0x18001d3bc`
- `0x18001d3f0`
- `0x18001d584`
- `0x18001d604`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring const,std::wstring> &>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rsi
  char *v7; // r15
  __int64 v9; // [rsp+20h] [rbp-58h] BYREF
  char *v10; // [rsp+28h] [rbp-50h]
  _OWORD v11[4]; // [rsp+30h] [rbp-48h] BYREF

  v6 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(a1, a3);
  std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
    a1,
    v11,
    a3,
    v6);
  if ( *((_QWORD *)&v11[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v11[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Check_max_size(a1);
    v9 = a1 + 8;
    v7 = (char *)operator new(0x50u);
    v10 = v7;
    std::wstring::wstring(v7 + 16, a3);
    std::wstring::wstring(v7 + 48, a3 + 32);
    if ( (unsigned __int8)std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Check_rehash_required_1(a1) )
    {
      std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Rehash_for_1(a1);
      v11[0] = *(_OWORD *)std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
                            a1,
                            v11,
                            v7 + 16,
                            v6);
    }
    v10 = 0;
    *(_QWORD *)a2 = std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      *(_QWORD *)&v11[0],
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(&v9);
  }
  return a2;
}

```

## disassembly

```asm
0x180017e94  push    rbx
0x180017e96  push    rbp
0x180017e97  push    rsi
0x180017e98  push    rdi
0x180017e99  push    r14
0x180017e9b  push    r15
0x180017e9d  sub     rsp, 48h
0x180017ea1  mov     rbp, r8
0x180017ea4  mov     rbx, rdx
0x180017ea7  mov     rdi, rcx
0x180017eaa  mov     rdx, r8
0x180017ead  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x180017eb2  mov     rsi, rax
0x180017eb5  mov     r9, rax
0x180017eb8  mov     r8, rbp
0x180017ebb  lea     rdx, [rsp+78h+var_48]
0x180017ec0  mov     rcx, rdi
0x180017ec3  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180017ec8  mov     rcx, qword ptr [rsp+78h+var_48+8]
0x180017ecd  test    rcx, rcx
0x180017ed0  jz      short loc_180017EDE
0x180017ed2  mov     [rbx], rcx
0x180017ed5  mov     byte ptr [rbx+8], 0
0x180017ed9  jmp     loc_180017F8D
0x180017ede  mov     rcx, rdi
0x180017ee1  call    ?_Check_max_size@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEBAXXZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Check_max_size(void)
0x180017ee6  lea     rax, [rdi+8]
0x180017eea  mov     [rsp+78h+var_58], rax
0x180017eef  mov     [rsp+78h+var_50], 0
0x180017ef8  mov     ecx, 50h ; 'P'; Size
0x180017efd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017f02  mov     r15, rax
0x180017f05  mov     [rsp+78h+var_50], rax
0x180017f0a  lea     r14, [rax+10h]
0x180017f0e  mov     [rsp+78h+arg_0], r14
0x180017f16  mov     rdx, rbp
0x180017f19  mov     rcx, r14
0x180017f1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017f21  nop
0x180017f22  lea     rdx, [rbp+20h]
0x180017f26  lea     rcx, [r14+20h]
0x180017f2a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017f2f  nop
0x180017f30  mov     rcx, rdi
0x180017f33  call    ?_Check_rehash_required_1@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEBA_NXZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Check_rehash_required_1(void)
0x180017f38  test    al, al
0x180017f3a  jz      short loc_180017F60
0x180017f3c  mov     rcx, rdi
0x180017f3f  call    ?_Rehash_for_1@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEAAXXZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Rehash_for_1(void)
0x180017f44  mov     r9, rsi
0x180017f47  mov     r8, r14
0x180017f4a  lea     rdx, [rsp+78h+var_48]
0x180017f4f  mov     rcx, rdi
0x180017f52  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180017f57  movups  xmm0, xmmword ptr [rax]
0x180017f5a  movdqu  [rsp+78h+var_48], xmm0
0x180017f60  mov     [rsp+78h+var_50], 0
0x180017f69  mov     r9, r15
0x180017f6c  mov     r8, qword ptr [rsp+78h+var_48]
0x180017f71  mov     rdx, rsi
0x180017f74  mov     rcx, rdi
0x180017f77  call    ?_Insert_new_node_before@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x180017f7c  mov     [rbx], rax
0x180017f7f  mov     byte ptr [rbx+8], 1
0x180017f83  lea     rcx, [rsp+78h+var_58]
0x180017f88  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(void)
0x180017f8d  mov     rax, rbx
0x180017f90  add     rsp, 48h
0x180017f94  pop     r15
0x180017f96  pop     r14
0x180017f98  pop     rdi
0x180017f99  pop     rsi
0x180017f9a  pop     rbp
0x180017f9b  pop     rbx
0x180017f9c  retn
```
