# Utils::ConvertUnicodeToMultiByte(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> *)

- ea: `0x18000b658`
- end: `0x18000b844`
- name: `?ConvertUnicodeToMultiByte@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z`
- size: `492`
- prototype: `__int64 __fastcall(const WCHAR *lpWideCharStr, _QWORD *)`
- caller_count: `7`
- callee_count: `9`
- tags: ``

## callers

- `0x1800085ac`
- `0x1800088dc`
- `0x180008fd8`
- `0x18000a09c`
- `0x18000a400`
- `0x18000c8e0`
- `0x18000d7f0`

## callees

- `0x180001540`
- `0x180001fd6`
- `0x180005514`
- `0x18000553c`
- `0x18000ab80`
- `0x18000acb0`
- `0x18000b1e0`
- `0x18000b658`
- `0x180013e04`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b715`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b7af`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b715`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b7af`

## pseudocode

```c
__int64 __fastcall Utils::ConvertUnicodeToMultiByte(const WCHAR *lpWideCharStr, _QWORD *a2)
{
  _QWORD *v2; // rdi
  LPCWCH v3; // r14
  unsigned int LastError; // ebx
  size_t *v5; // r15
  _BYTE *v6; // rax
  const WCHAR *v7; // r8
  size_t v8; // rsi
  int v9; // eax
  const char *v10; // r9
  __int64 v11; // r12
  __int64 v12; // rdx
  __int64 v13; // r8
  LPSTR v14; // r9
  int lpMultiByteStr; // [rsp+20h] [rbp-50h]
  LPSTR v17[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v18; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v2 = a2;
  v3 = lpWideCharStr;
  if ( a2 )
  {
    v5 = a2 + 2;
    a2[2] = 0;
    if ( a2[3] <= 0xFu )
      v6 = a2;
    else
      v6 = (_BYTE *)*a2;
    *v6 = 0;
    *(_OWORD *)v17 = 0;
    v18 = 0;
    if ( *((_QWORD *)lpWideCharStr + 2) )
    {
      if ( *((_QWORD *)lpWideCharStr + 3) <= 7u )
        v7 = lpWideCharStr;
      else
        v7 = *(const WCHAR **)lpWideCharStr;
      v8 = -1;
      v9 = WideCharToMultiByte(0xFDE9u, 0, v7, -1, 0, 0, 0, 0);
      v11 = v9;
      if ( !v9 )
      {
        v12 = 46;
LABEL_22:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v12,
                      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\utils.cpp",
                      v10);
LABEL_31:
        std::vector<char>::~vector<char>(v17);
        return LastError;
      }
      if ( (LPSTR)v9 >= (LPSTR)(v17[1] - v17[0]) )
      {
        if ( (LPSTR)v9 > (LPSTR)(v17[1] - v17[0]) )
        {
          if ( v9 <= v18 - (unsigned __int64)v17[0] )
          {
            memset_0(v17[1], 0, v9 - (unsigned __int64)(v17[1] - v17[0]));
            v17[1] = &v17[0][v11];
          }
          else
          {
            std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(v17, v9, v9);
          }
        }
      }
      else
      {
        v17[1] = &v17[0][v9];
      }
      if ( *((_QWORD *)v3 + 3) > 7u )
        v3 = *(LPCWCH *)v3;
      if ( WideCharToMultiByte(0xFDE9u, 0, v3, -1, v17[0], v18 - LODWORD(v17[0]), 0, 0) != (_DWORD)v11 )
      {
        v12 = 59;
        goto LABEL_22;
      }
      v14 = v17[0];
      do
        ++v8;
      while ( v17[0][v8] );
      if ( v8 > v2[3] )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_D_01_AEAAAEAV01_QEBD0_Z_PEBD_Z(
          v2,
          v8,
          v13,
          v17[0]);
      }
      else
      {
        if ( v2[3] > 0xFu )
          v2 = (_QWORD *)*v2;
        *v5 = v8;
        memmove_0(v2, v14, v8);
        *((_BYTE *)v2 + v8) = 0;
      }
    }
    LastError = 0;
    goto LABEL_31;
  }
  LastError = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x17,
    (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\utils.cpp",
    (const char *)0x80004003LL,
    lpMultiByteStr);
  return LastError;
}

```

## disassembly

```asm
0x18000b658  mov     rax, rsp
0x18000b65b  push    rbp
0x18000b65c  push    rsi
0x18000b65d  push    rdi
0x18000b65e  push    r12
0x18000b660  push    r13
0x18000b662  push    r14
0x18000b664  push    r15
0x18000b666  mov     rbp, rsp
0x18000b669  sub     rsp, 70h
0x18000b66d  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18000b675  mov     [rax+18h], rbx
0x18000b679  mov     rax, cs:__security_cookie
0x18000b680  xor     rax, rsp
0x18000b683  mov     [rbp+var_10], rax
0x18000b687  mov     rdi, rdx
0x18000b68a  mov     r14, rcx
0x18000b68d  xor     r13d, r13d
0x18000b690  test    rdx, rdx
0x18000b693  jnz     short loc_18000B6B5
0x18000b695  mov     rcx, [rbp+38h]; this
0x18000b699  mov     ebx, 80004003h
0x18000b69e  mov     r9d, ebx; char *
0x18000b6a1  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000b6a8  lea     edx, [rdi+17h]; void *
0x18000b6ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6b0  jmp     loc_18000B81E
0x18000b6b5  lea     r15, [rdx+10h]
0x18000b6b9  mov     [r15], r13
0x18000b6bc  cmp     qword ptr [rdx+18h], 0Fh
0x18000b6c1  jbe     short loc_18000B6C8
0x18000b6c3  mov     rax, [rdx]
0x18000b6c6  jmp     short loc_18000B6CB
0x18000b6c8  mov     rax, rdi
0x18000b6cb  mov     [rax], r13b
0x18000b6ce  xorps   xmm0, xmm0
0x18000b6d1  movdqu  xmmword ptr [rbp+var_28], xmm0
0x18000b6d6  mov     [rbp+var_18], r13
0x18000b6da  cmp     [rcx+10h], r13
0x18000b6de  jz      loc_18000B812
0x18000b6e4  cmp     qword ptr [rcx+18h], 7
0x18000b6e9  jbe     short loc_18000B6F0
0x18000b6eb  mov     r8, [rcx]
0x18000b6ee  jmp     short loc_18000B6F3
0x18000b6f0  mov     r8, r14; lpWideCharStr
0x18000b6f3  mov     [rsp+70h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000b6f8  mov     [rsp+70h+lpDefaultChar], r13; lpDefaultChar
0x18000b6fd  mov     [rsp+70h+cbMultiByte], r13d; cbMultiByte
0x18000b702  mov     [rsp+70h+lpMultiByteStr], r13; lpMultiByteStr
0x18000b707  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000b70b  mov     r9d, esi; cchWideChar
0x18000b70e  xor     edx, edx; dwFlags
0x18000b710  mov     ecx, 0FDE9h; CodePage
0x18000b715  call    cs:__imp_WideCharToMultiByte
0x18000b71b  movsxd  r12, eax
0x18000b71e  test    eax, eax
0x18000b720  jnz     short loc_18000B72A
0x18000b722  lea     edx, [rsi+2Fh]
0x18000b725  jmp     loc_18000B7BF
0x18000b72a  mov     rdx, [rbp+var_28]
0x18000b72e  mov     r9, [rbp+var_28+8]
0x18000b732  mov     rcx, r9
0x18000b735  sub     rcx, rdx
0x18000b738  mov     r8, r12
0x18000b73b  cmp     r12, rcx
0x18000b73e  jnb     short loc_18000B74A
0x18000b740  lea     rax, [r12+rdx]
0x18000b744  mov     [rbp+var_28+8], rax
0x18000b748  jmp     short loc_18000B77B
0x18000b74a  jbe     short loc_18000B77B
0x18000b74c  mov     rax, [rbp+var_18]
0x18000b750  sub     rax, rdx
0x18000b753  cmp     r8, rax
0x18000b756  jbe     short loc_18000B766
0x18000b758  mov     rdx, r8
0x18000b75b  lea     rcx, [rbp+var_28]
0x18000b75f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000b764  jmp     short loc_18000B77B
0x18000b766  sub     r8, rcx; Size
0x18000b769  lea     rbx, [r8+r9]
0x18000b76d  xor     edx, edx; Val
0x18000b76f  mov     rcx, r9; void *
0x18000b772  call    memset_0
0x18000b777  mov     [rbp+var_28+8], rbx
0x18000b77b  mov     rcx, [rbp+var_28]
0x18000b77f  mov     rax, [rbp+var_18]
0x18000b783  cmp     qword ptr [r14+18h], 7
0x18000b788  jbe     short loc_18000B78D
0x18000b78a  mov     r14, [r14]
0x18000b78d  sub     eax, ecx
0x18000b78f  mov     [rsp+70h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000b794  mov     [rsp+70h+lpDefaultChar], r13; lpDefaultChar
0x18000b799  mov     [rsp+70h+cbMultiByte], eax; cbMultiByte
0x18000b79d  mov     [rsp+70h+lpMultiByteStr], rcx; lpMultiByteStr
0x18000b7a2  mov     r9d, esi; cchWideChar
0x18000b7a5  mov     r8, r14; lpWideCharStr
0x18000b7a8  xor     edx, edx; dwFlags
0x18000b7aa  mov     ecx, 0FDE9h; CodePage
0x18000b7af  call    cs:__imp_WideCharToMultiByte
0x18000b7b5  cmp     eax, r12d
0x18000b7b8  jz      short loc_18000B7D3
0x18000b7ba  mov     edx, 3Bh ; ';'; void *
0x18000b7bf  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000b7c6  mov     rcx, [rbp+38h]; this
0x18000b7ca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b7cf  mov     ebx, eax
0x18000b7d1  jmp     short loc_18000B815
0x18000b7d3  mov     r9, [rbp+var_28]
0x18000b7d7  inc     rsi
0x18000b7da  cmp     [r9+rsi], r13b
0x18000b7de  jnz     short loc_18000B7D7
0x18000b7e0  cmp     rsi, [rdi+18h]
0x18000b7e4  ja      short loc_18000B807
0x18000b7e6  cmp     qword ptr [rdi+18h], 0Fh
0x18000b7eb  jbe     short loc_18000B7F0
0x18000b7ed  mov     rdi, [rdi]
0x18000b7f0  mov     [r15], rsi
0x18000b7f3  mov     r8, rsi; Size
0x18000b7f6  mov     rdx, r9; Src
0x18000b7f9  mov     rcx, rdi; void *
0x18000b7fc  call    memmove_0
0x18000b801  mov     [rsi+rdi], r13b
0x18000b805  jmp     short loc_18000B812
0x18000b807  mov     rdx, rsi
0x18000b80a  mov     rcx, rdi
0x18000b80d  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV23@QEBD_K@Z@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@D@01@AEAAAEAV01@QEBD0@Z@PEBD@Z; std::string::_Reallocate_for<`std::string::_Assign<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *>(unsigned __int64,`std::string::_Assign<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *)
0x18000b812  mov     ebx, r13d
0x18000b815  lea     rcx, [rbp+var_28]
0x18000b819  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18000b81e  mov     eax, ebx
0x18000b820  mov     rcx, [rbp+var_10]
0x18000b824  xor     rcx, rsp; StackCookie
0x18000b827  call    __security_check_cookie
0x18000b82c  mov     rbx, [rsp+70h+arg_10]
0x18000b834  add     rsp, 70h
0x18000b838  pop     r15
0x18000b83a  pop     r14
0x18000b83c  pop     r13
0x18000b83e  pop     r12
0x18000b840  pop     rdi
0x18000b841  pop     rsi
0x18000b842  pop     rbp
0x18000b843  retn
```
