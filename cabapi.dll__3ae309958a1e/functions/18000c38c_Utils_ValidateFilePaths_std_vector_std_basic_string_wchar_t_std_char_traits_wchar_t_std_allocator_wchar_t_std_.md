# Utils::ValidateFilePaths(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,bool,bool)

- ea: `0x18000c38c`
- end: `0x18000c484`
- name: `?ValidateFilePaths@Utils@@SAJAEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@_N1@Z`
- size: `248`
- prototype: `__int64 __fastcall(__int64 *, char, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180008fd8`

## callees

- `0x180001540`
- `0x180001570`
- `0x18000553c`
- `0x18000af44`
- `0x18000b164`
- `0x18000c060`
- `0x18000c38c`

## pseudocode

```c
__int64 __fastcall Utils::ValidateFilePaths(__int64 *a1, char a2, char a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rsi
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  _BYTE v14[16]; // [rsp+28h] [rbp-40h] BYREF
  __int128 v15; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v15 = 0;
  v6 = operator new(0x40u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *(_QWORD *)&v15 = v6;
  v7 = *a1;
  v8 = a1[1];
  while ( 1 )
  {
    if ( v7 == v8 )
    {
      v10 = 0;
      goto LABEL_8;
    }
    v9 = Utils::ValidateFilePath(v7, a3);
    v10 = v9;
    if ( v9 < 0 )
      break;
    if ( a2 )
    {
      std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::insert<0,0>(
        (__int64 *)&v15,
        (__int64)v14,
        v7);
      if ( !v14[8] )
      {
        v10 = -2145877285;
        v12 = 2149090011LL;
        v13 = 509;
        goto LABEL_10;
      }
    }
    v7 += 32;
  }
  v12 = (unsigned int)v9;
  v13 = 504;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\utils.cpp",
    (const char *)v12);
LABEL_8:
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>((void **)&v15);
  return v10;
}

```

## disassembly

```asm
0x18000c38c  mov     rax, rsp
0x18000c38f  push    rsi
0x18000c390  push    rdi
0x18000c391  push    r14
0x18000c393  sub     rsp, 50h
0x18000c397  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18000c39f  mov     [rax+10h], rbx
0x18000c3a3  mov     [rax+20h], rbp
0x18000c3a7  mov     rax, cs:__security_cookie
0x18000c3ae  xor     rax, rsp
0x18000c3b1  mov     [rsp+68h+var_20], rax
0x18000c3b6  mov     r14b, r8b
0x18000c3b9  mov     bpl, dl
0x18000c3bc  mov     rbx, rcx
0x18000c3bf  xorps   xmm0, xmm0
0x18000c3c2  movdqu  [rsp+68h+var_30], xmm0
0x18000c3c8  mov     ecx, 40h ; '@'; Size
0x18000c3cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c3d2  mov     [rax], rax
0x18000c3d5  mov     [rax+8], rax
0x18000c3d9  mov     [rax+10h], rax
0x18000c3dd  mov     word ptr [rax+18h], 101h
0x18000c3e3  mov     qword ptr [rsp+68h+var_30], rax
0x18000c3e8  mov     rdi, [rbx]
0x18000c3eb  mov     rsi, [rbx+8]
0x18000c3ef  jmp     short loc_18000C424
0x18000c3f1  mov     dl, r14b
0x18000c3f4  mov     rcx, rdi
0x18000c3f7  call    ?ValidateFilePath@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z; Utils::ValidateFilePath(std::wstring const &,bool)
0x18000c3fc  mov     ebx, eax
0x18000c3fe  test    eax, eax
0x18000c400  js      short loc_18000C479
0x18000c402  test    bpl, bpl
0x18000c405  jz      short loc_18000C420
0x18000c407  mov     r8, rdi
0x18000c40a  lea     rdx, [rsp+68h+var_40]
0x18000c40f  lea     rcx, [rsp+68h+var_30]
0x18000c414  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x18000c419  cmp     [rsp+68h+var_38], 0
0x18000c41e  jz      short loc_18000C459
0x18000c420  add     rdi, 20h ; ' '
0x18000c424  cmp     rdi, rsi
0x18000c427  jnz     short loc_18000C3F1
0x18000c429  xor     ebx, ebx
0x18000c42b  lea     rcx, [rsp+68h+var_30]
0x18000c430  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(void)
0x18000c435  mov     eax, ebx
0x18000c437  mov     rcx, [rsp+68h+var_20]
0x18000c43c  xor     rcx, rsp; StackCookie
0x18000c43f  call    __security_check_cookie
0x18000c444  lea     r11, [rsp+68h+var_18]
0x18000c449  mov     rbx, [r11+28h]
0x18000c44d  mov     rbp, [r11+38h]
0x18000c451  mov     rsp, r11
0x18000c454  pop     r14
0x18000c456  pop     rdi
0x18000c457  pop     rsi
0x18000c458  retn
0x18000c459  mov     ebx, 801882DBh
0x18000c45e  mov     r9d, ebx; char *
0x18000c461  mov     edx, 1FDh; void *
0x18000c466  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000c46d  mov     rcx, [rsp+68h]; this
0x18000c472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c477  jmp     short loc_18000C42B
0x18000c479  mov     r9d, eax
0x18000c47c  mov     edx, 1F8h
0x18000c481  jmp     short loc_18000C466
```
