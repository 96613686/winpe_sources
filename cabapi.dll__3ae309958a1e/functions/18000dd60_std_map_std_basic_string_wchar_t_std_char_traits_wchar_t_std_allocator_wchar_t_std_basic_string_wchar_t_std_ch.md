# std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>>::insert<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,0>(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> &&)

- ea: `0x18000dd60`
- end: `0x18000deb3`
- name: `??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@1@@Z`
- size: `339`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e0c8`

## callees

- `0x180001570`
- `0x180001f76`
- `0x18000c4e0`
- `0x18000c710`
- `0x18000db98`
- `0x18000dd60`

## pseudocode

```c
__int64 __fastcall std::map<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>>::insert<std::pair<std::wstring,std::wstring>,0>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // rax
  __int128 v7; // xmm6
  __int64 inserted; // rbx
  const wchar_t *v9; // rdx
  const wchar_t *v10; // rcx
  char v11; // al
  __int64 v12; // rbx
  _OWORD *v13; // rax
  _OWORD v15[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v16; // [rsp+40h] [rbp-38h]

  v16 = -2;
  v6 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
         (__int64)a1,
         v15,
         a3);
  v7 = *(_OWORD *)v6;
  inserted = v6[2];
  if ( *(_BYTE *)(inserted + 25) )
    goto LABEL_9;
  v9 = (const wchar_t *)(inserted + 32);
  if ( *(_QWORD *)(inserted + 56) > 7u )
    v9 = *(const wchar_t **)v9;
  v10 = *(_QWORD *)(a3 + 24) <= 7u ? (const wchar_t *)a3 : *(const wchar_t **)a3;
  if ( wcsicmp(v10, v9) < 0 )
  {
LABEL_9:
    if ( a1[1] == 0x2AAAAAAAAAAAAAALL )
      std::_Throw_tree_length_error();
    v12 = *a1;
    v15[0] = (unsigned __int64)a1;
    v13 = operator new(0x60u);
    v13[2] = 0;
    *((_QWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 7) = 0;
    v13[2] = *(_OWORD *)a3;
    v13[3] = *(_OWORD *)(a3 + 16);
    *(_QWORD *)(a3 + 16) = 0;
    *(_QWORD *)(a3 + 24) = 7;
    *(_WORD *)a3 = 0;
    v13[4] = 0;
    *((_QWORD *)v13 + 10) = 0;
    *((_QWORD *)v13 + 11) = 0;
    v13[4] = *(_OWORD *)(a3 + 32);
    v13[5] = *(_OWORD *)(a3 + 48);
    *(_QWORD *)(a3 + 48) = 0;
    *(_QWORD *)(a3 + 56) = 7;
    *(_WORD *)(a3 + 32) = 0;
    *(_QWORD *)v13 = v12;
    *((_QWORD *)v13 + 1) = v12;
    *((_QWORD *)v13 + 2) = v12;
    *((_WORD *)v13 + 12) = 0;
    v15[0] = v7;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(
                 a1,
                 v15,
                 v13);
    v11 = 1;
  }
  else
  {
    v11 = 0;
  }
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v11;
  return a2;
}

```

## disassembly

```asm
0x18000dd60  mov     rax, rsp
0x18000dd63  push    rsi
0x18000dd64  push    rdi
0x18000dd65  push    r14
0x18000dd67  sub     rsp, 60h
0x18000dd6b  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18000dd73  mov     [rax+20h], rbx
0x18000dd77  movaps  xmmword ptr [rax-28h], xmm6
0x18000dd7b  mov     rdi, r8
0x18000dd7e  mov     rsi, rdx
0x18000dd81  mov     r14, rcx
0x18000dd84  lea     rdx, [rax-58h]
0x18000dd88  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000dd8d  movups  xmm6, xmmword ptr [rax]
0x18000dd90  mov     rbx, [rax+10h]
0x18000dd94  cmp     byte ptr [rbx+19h], 0
0x18000dd98  jnz     short loc_18000DDC7
0x18000dd9a  lea     rdx, [rbx+20h]
0x18000dd9e  cmp     qword ptr [rdx+18h], 7
0x18000dda3  jbe     short loc_18000DDA8
0x18000dda5  mov     rdx, [rdx]; String2
0x18000dda8  cmp     qword ptr [rdi+18h], 7
0x18000ddad  jbe     short loc_18000DDB4
0x18000ddaf  mov     rcx, [rdi]
0x18000ddb2  jmp     short loc_18000DDB7
0x18000ddb4  mov     rcx, rdi; String1
0x18000ddb7  call    _wcsicmp
0x18000ddbc  test    eax, eax
0x18000ddbe  js      short loc_18000DDC7
0x18000ddc0  xor     al, al
0x18000ddc2  jmp     loc_18000DE8E
0x18000ddc7  mov     rax, 2AAAAAAAAAAAAAAh
0x18000ddd1  cmp     [r14+8], rax
0x18000ddd5  jz      loc_18000DEAD
0x18000dddb  mov     rbx, [r14]
0x18000ddde  mov     qword ptr [rsp+78h+var_58], r14
0x18000dde3  mov     qword ptr [rsp+78h+var_58+8], 0
0x18000ddec  mov     ecx, 60h ; '`'; Size
0x18000ddf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ddf6  mov     r8, rax
0x18000ddf9  xorps   xmm0, xmm0
0x18000ddfc  movups  xmmword ptr [rax+20h], xmm0
0x18000de00  mov     qword ptr [rax+30h], 0
0x18000de08  mov     qword ptr [rax+38h], 0
0x18000de10  movups  xmm0, xmmword ptr [rdi]
0x18000de13  movups  xmmword ptr [rax+20h], xmm0
0x18000de17  movups  xmm1, xmmword ptr [rdi+10h]
0x18000de1b  movups  xmmword ptr [rax+30h], xmm1
0x18000de1f  mov     qword ptr [rdi+10h], 0
0x18000de27  mov     qword ptr [rdi+18h], 7
0x18000de2f  xor     eax, eax
0x18000de31  mov     [rdi], ax
0x18000de34  xorps   xmm0, xmm0
0x18000de37  movups  xmmword ptr [r8+40h], xmm0
0x18000de3c  mov     [r8+50h], rax
0x18000de40  mov     [r8+58h], rax
0x18000de44  movups  xmm0, xmmword ptr [rdi+20h]
0x18000de48  movups  xmmword ptr [r8+40h], xmm0
0x18000de4d  movups  xmm1, xmmword ptr [rdi+30h]
0x18000de51  movups  xmmword ptr [r8+50h], xmm1
0x18000de56  mov     [rdi+30h], rax
0x18000de5a  mov     qword ptr [rdi+38h], 7
0x18000de62  mov     [rdi+20h], ax
0x18000de66  mov     [r8], rbx
0x18000de69  mov     [r8+8], rbx
0x18000de6d  mov     [r8+10h], rbx
0x18000de71  mov     [r8+18h], ax
0x18000de76  movdqu  [rsp+78h+var_58], xmm6
0x18000de7c  lea     rdx, [rsp+78h+var_58]
0x18000de81  mov     rcx, r14
0x18000de84  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x18000de89  mov     rbx, rax
0x18000de8c  mov     al, 1
0x18000de8e  mov     [rsi], rbx
0x18000de91  mov     [rsi+8], al
0x18000de94  mov     rax, rsi
0x18000de97  mov     rbx, [rsp+78h+arg_18]
0x18000de9f  movaps  xmm6, [rsp+78h+var_28]
0x18000dea4  add     rsp, 60h
0x18000dea8  pop     r14
0x18000deaa  pop     rdi
0x18000deab  pop     rsi
0x18000deac  retn
0x18000dead  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
