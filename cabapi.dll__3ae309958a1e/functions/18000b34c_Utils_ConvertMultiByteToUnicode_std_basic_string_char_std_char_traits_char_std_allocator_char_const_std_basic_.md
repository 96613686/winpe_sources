# Utils::ConvertMultiByteToUnicode(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *)

- ea: `0x18000b34c`
- end: `0x18000b4b9`
- name: `?ConvertMultiByteToUnicode@Utils@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z`
- size: `365`
- prototype: `__int64 __fastcall(const CHAR *lpMultiByteStr, __int64)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c8e0`
- `0x18000ccc0`
- `0x18000cee0`
- `0x18000d200`
- `0x18000d340`
- `0x18000d590`

## callees

- `0x180001540`
- `0x180002e54`
- `0x180005514`
- `0x18000553c`
- `0x18000b24c`
- `0x18000b34c`
- `0x18000c728`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b3fb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b45d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b3fb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b45d`

## pseudocode

```c
__int64 __fastcall Utils::ConvertMultiByteToUnicode(const CHAR *lpMultiByteStr, __int64 a2)
{
  unsigned int LastError; // ebx
  _WORD *v5; // rcx
  const CHAR *v6; // r8
  unsigned __int64 v7; // rsi
  int v8; // eax
  const char *v9; // r9
  int v10; // ebp
  __int64 v11; // rdx
  int lpWideCharStr; // [rsp+20h] [rbp-58h]
  LPWSTR v14[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v15; // [rsp+48h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a2 )
  {
    *(_QWORD *)(a2 + 16) = 0;
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v5 = (_WORD *)a2;
    else
      v5 = *(_WORD **)a2;
    *v5 = 0;
    *(_OWORD *)v14 = 0;
    v15 = 0;
    if ( *((_QWORD *)lpMultiByteStr + 2) )
    {
      if ( *((_QWORD *)lpMultiByteStr + 3) <= 0xFu )
        v6 = lpMultiByteStr;
      else
        v6 = *(const CHAR **)lpMultiByteStr;
      v7 = -1;
      v8 = MultiByteToWideChar(0xFDE9u, 0, v6, -1, 0, 0);
      v10 = v8;
      if ( !v8 )
      {
        v11 = 97;
LABEL_12:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v11,
                      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\utils.cpp",
                      v9);
LABEL_20:
        std::vector<wchar_t>::~vector<wchar_t>((char **)v14);
        return LastError;
      }
      std::vector<wchar_t>::resize(v14, v8);
      if ( *((_QWORD *)lpMultiByteStr + 3) > 0xFu )
        lpMultiByteStr = *(const CHAR **)lpMultiByteStr;
      if ( MultiByteToWideChar(
             0xFDE9u,
             0,
             lpMultiByteStr,
             -1,
             v14[0],
             (signed __int64)(v15 - (unsigned __int64)v14[0]) >> 1) != v10 )
      {
        v11 = 108;
        goto LABEL_12;
      }
      do
        ++v7;
      while ( v14[0][v7] );
      std::wstring::_Assign<wchar_t>((void **)a2, v14[0], v7);
    }
    LastError = 0;
    goto LABEL_20;
  }
  LastError = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4C,
    (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\utils.cpp",
    (const char *)0x80004003LL,
    lpWideCharStr);
  return LastError;
}

```

## disassembly

```asm
0x18000b34c  mov     rax, rsp
0x18000b34f  push    rsi
0x18000b350  push    rdi
0x18000b351  push    r14
0x18000b353  sub     rsp, 60h
0x18000b357  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18000b35f  mov     [rax+18h], rbx
0x18000b363  mov     [rax+20h], rbp
0x18000b367  mov     rax, cs:__security_cookie
0x18000b36e  xor     rax, rsp
0x18000b371  mov     [rsp+78h+var_28], rax
0x18000b376  mov     rdi, rdx
0x18000b379  mov     rbx, rcx
0x18000b37c  xor     r14d, r14d
0x18000b37f  test    rdx, rdx
0x18000b382  jnz     short loc_18000B3A5
0x18000b384  mov     rcx, [rsp+78h]; this
0x18000b389  mov     ebx, 80004003h
0x18000b38e  mov     r9d, ebx; char *
0x18000b391  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000b398  lea     edx, [rdi+4Ch]; void *
0x18000b39b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3a0  jmp     loc_18000B495
0x18000b3a5  mov     [rdx+10h], r14
0x18000b3a9  cmp     qword ptr [rdx+18h], 7
0x18000b3ae  jbe     short loc_18000B3B5
0x18000b3b0  mov     rcx, [rdx]
0x18000b3b3  jmp     short loc_18000B3B8
0x18000b3b5  mov     rcx, rdi
0x18000b3b8  mov     [rcx], r14w
0x18000b3bc  xorps   xmm0, xmm0
0x18000b3bf  movdqu  xmmword ptr [rsp+78h+var_40], xmm0
0x18000b3c5  mov     [rsp+78h+var_30], r14
0x18000b3ca  cmp     [rbx+10h], r14
0x18000b3ce  jz      loc_18000B488
0x18000b3d4  cmp     qword ptr [rbx+18h], 0Fh
0x18000b3d9  jbe     short loc_18000B3E0
0x18000b3db  mov     r8, [rbx]
0x18000b3de  jmp     short loc_18000B3E3
0x18000b3e0  mov     r8, rbx; lpMultiByteStr
0x18000b3e3  mov     [rsp+78h+cchWideChar], r14d; cchWideChar
0x18000b3e8  mov     [rsp+78h+lpWideCharStr], r14; lpWideCharStr
0x18000b3ed  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000b3f1  mov     r9d, esi; cbMultiByte
0x18000b3f4  xor     edx, edx; dwFlags
0x18000b3f6  mov     ecx, 0FDE9h; CodePage
0x18000b3fb  call    cs:__imp_MultiByteToWideChar
0x18000b401  movsxd  rbp, eax
0x18000b404  test    eax, eax
0x18000b406  jnz     short loc_18000B420
0x18000b408  lea     edx, [rsi+62h]; void *
0x18000b40b  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000b412  mov     rcx, [rsp+78h]; this
0x18000b417  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b41c  mov     ebx, eax
0x18000b41e  jmp     short loc_18000B48B
0x18000b420  mov     rdx, rbp
0x18000b423  lea     rcx, [rsp+78h+var_40]
0x18000b428  call    ?resize@?$vector@_WV?$allocator@_W@std@@@std@@QEAAX_K@Z; std::vector<wchar_t>::resize(unsigned __int64)
0x18000b42d  mov     rcx, [rsp+78h+var_40]
0x18000b432  mov     rax, [rsp+78h+var_30]
0x18000b437  sub     rax, rcx
0x18000b43a  sar     rax, 1
0x18000b43d  cmp     qword ptr [rbx+18h], 0Fh
0x18000b442  jbe     short loc_18000B447
0x18000b444  mov     rbx, [rbx]
0x18000b447  mov     [rsp+78h+cchWideChar], eax; cchWideChar
0x18000b44b  mov     [rsp+78h+lpWideCharStr], rcx; lpWideCharStr
0x18000b450  mov     r9d, esi; cbMultiByte
0x18000b453  mov     r8, rbx; lpMultiByteStr
0x18000b456  xor     edx, edx; dwFlags
0x18000b458  mov     ecx, 0FDE9h; CodePage
0x18000b45d  call    cs:__imp_MultiByteToWideChar
0x18000b463  cmp     eax, ebp
0x18000b465  jz      short loc_18000B46E
0x18000b467  mov     edx, 6Ch ; 'l'
0x18000b46c  jmp     short loc_18000B40B
0x18000b46e  mov     rdx, [rsp+78h+var_40]
0x18000b473  inc     rsi
0x18000b476  cmp     [rdx+rsi*2], r14w
0x18000b47b  jnz     short loc_18000B473
0x18000b47d  mov     r8, rsi
0x18000b480  mov     rcx, rdi
0x18000b483  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000b488  mov     ebx, r14d
0x18000b48b  lea     rcx, [rsp+78h+var_40]
0x18000b490  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x18000b495  mov     eax, ebx
0x18000b497  mov     rcx, [rsp+78h+var_28]
0x18000b49c  xor     rcx, rsp; StackCookie
0x18000b49f  call    __security_check_cookie
0x18000b4a4  lea     r11, [rsp+78h+var_18]
0x18000b4a9  mov     rbx, [r11+30h]
0x18000b4ad  mov     rbp, [r11+38h]
0x18000b4b1  mov     rsp, r11
0x18000b4b4  pop     r14
0x18000b4b6  pop     rdi
0x18000b4b7  pop     rsi
0x18000b4b8  retn
```
