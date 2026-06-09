# std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,int,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,int>>>::insert<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,int>,0>(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,int> &&)

- ea: `0x18000dc30`
- end: `0x18000dd5a`
- name: `??$insert@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@HUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@1@@Z`
- size: `298`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e0c8`
- `0x18000e188`

## callees

- `0x180001570`
- `0x180001f76`
- `0x18000c4e0`
- `0x18000c710`
- `0x18000db98`
- `0x18000dc30`

## pseudocode

```c
__int64 __fastcall std::map<std::wstring,int,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,int>>>::insert<std::pair<std::wstring,int>,0>(
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
    if ( a1[1] == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v12 = *a1;
    v15[0] = (unsigned __int64)a1;
    v13 = operator new(0x48u);
    v13[2] = 0;
    *((_QWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 7) = 0;
    v13[2] = *(_OWORD *)a3;
    v13[3] = *(_OWORD *)(a3 + 16);
    *(_QWORD *)(a3 + 16) = 0;
    *(_QWORD *)(a3 + 24) = 7;
    *(_WORD *)a3 = 0;
    *((_DWORD *)v13 + 16) = *(_DWORD *)(a3 + 32);
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
0x18000dc30  mov     rax, rsp
0x18000dc33  push    rsi
0x18000dc34  push    rdi
0x18000dc35  push    r14
0x18000dc37  sub     rsp, 60h
0x18000dc3b  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18000dc43  mov     [rax+20h], rbx
0x18000dc47  movaps  xmmword ptr [rax-28h], xmm6
0x18000dc4b  mov     rdi, r8
0x18000dc4e  mov     rsi, rdx
0x18000dc51  mov     r14, rcx
0x18000dc54  lea     rdx, [rax-58h]
0x18000dc58  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000dc5d  movups  xmm6, xmmword ptr [rax]
0x18000dc60  mov     rbx, [rax+10h]
0x18000dc64  cmp     byte ptr [rbx+19h], 0
0x18000dc68  jnz     short loc_18000DC97
0x18000dc6a  lea     rdx, [rbx+20h]
0x18000dc6e  cmp     qword ptr [rdx+18h], 7
0x18000dc73  jbe     short loc_18000DC78
0x18000dc75  mov     rdx, [rdx]; String2
0x18000dc78  cmp     qword ptr [rdi+18h], 7
0x18000dc7d  jbe     short loc_18000DC84
0x18000dc7f  mov     rcx, [rdi]
0x18000dc82  jmp     short loc_18000DC87
0x18000dc84  mov     rcx, rdi; String1
0x18000dc87  call    _wcsicmp
0x18000dc8c  test    eax, eax
0x18000dc8e  js      short loc_18000DC97
0x18000dc90  xor     al, al
0x18000dc92  jmp     loc_18000DD35
0x18000dc97  mov     rax, 38E38E38E38E38Eh
0x18000dca1  cmp     [r14+8], rax
0x18000dca5  jz      loc_18000DD54
0x18000dcab  mov     rbx, [r14]
0x18000dcae  mov     qword ptr [rsp+78h+var_58], r14
0x18000dcb3  mov     qword ptr [rsp+78h+var_58+8], 0
0x18000dcbc  mov     ecx, 48h ; 'H'; Size
0x18000dcc1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dcc6  mov     r8, rax
0x18000dcc9  xorps   xmm0, xmm0
0x18000dccc  movups  xmmword ptr [rax+20h], xmm0
0x18000dcd0  mov     qword ptr [rax+30h], 0
0x18000dcd8  mov     qword ptr [rax+38h], 0
0x18000dce0  movups  xmm0, xmmword ptr [rdi]
0x18000dce3  movups  xmmword ptr [rax+20h], xmm0
0x18000dce7  movups  xmm1, xmmword ptr [rdi+10h]
0x18000dceb  movups  xmmword ptr [rax+30h], xmm1
0x18000dcef  mov     qword ptr [rdi+10h], 0
0x18000dcf7  mov     qword ptr [rdi+18h], 7
0x18000dcff  xor     eax, eax
0x18000dd01  mov     [rdi], ax
0x18000dd04  mov     eax, [rdi+20h]
0x18000dd07  mov     [r8+40h], eax
0x18000dd0b  mov     [r8], rbx
0x18000dd0e  mov     [r8+8], rbx
0x18000dd12  mov     [r8+10h], rbx
0x18000dd16  mov     word ptr [r8+18h], 0
0x18000dd1d  movdqu  [rsp+78h+var_58], xmm6
0x18000dd23  lea     rdx, [rsp+78h+var_58]
0x18000dd28  mov     rcx, r14
0x18000dd2b  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x18000dd30  mov     rbx, rax
0x18000dd33  mov     al, 1
0x18000dd35  mov     [rsi], rbx
0x18000dd38  mov     [rsi+8], al
0x18000dd3b  mov     rax, rsi
0x18000dd3e  mov     rbx, [rsp+78h+arg_18]
0x18000dd46  movaps  xmm6, [rsp+78h+var_28]
0x18000dd4b  add     rsp, 60h
0x18000dd4f  pop     r14
0x18000dd51  pop     rdi
0x18000dd52  pop     rsi
0x18000dd53  retn
0x18000dd54  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
