# _anonymous_namespace_::Utf16ToUtf8_0

- ea: `0x18002c4a4`
- end: `0x18002c622`
- name: `_anonymous_namespace_::Utf16ToUtf8_0`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028cc4`
- `0x18002b264`

## callees

- `0x180002490`
- `0x180008a68`
- `0x180022280`
- `0x180025c30`
- `0x18002c4a4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002c53d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002c5a1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002c53d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002c5a1`

## string_xrefs

- `0x18002c5fb`: `onecore\ds\security\cfl\api\lib\CflApiJsonNew.h`
- `0x18002c610`: `onecore\ds\security\cfl\api\lib\CflApiJsonNew.h`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::Utf16ToUtf8_0(__int64 a1, __int64 *a2)
{
  __int64 *v2; // rdi
  const WCHAR *v4; // r8
  int v5; // eax
  const char *v6; // r9
  CHAR *lpMultiByteStr; // rax
  int v8; // r9d
  const char *v9; // r9
  LPSTR v11[2]; // [rsp+50h] [rbp-30h] BYREF
  int cbMultiByte[4]; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v2 = a2;
  if ( a2[2] )
  {
    *(_OWORD *)v11 = 0;
    *(_QWORD *)cbMultiByte = 0;
    *(_QWORD *)&cbMultiByte[2] = 15;
    LOBYTE(v11[0]) = 0;
    if ( (unsigned __int64)a2[3] <= 7 )
      v4 = (const WCHAR *)a2;
    else
      v4 = (const WCHAR *)*a2;
    v5 = WideCharToMultiByte(0xFDE9u, 0x80u, v4, *((_DWORD *)a2 + 4), 0, 0, 0, 0);
    if ( !v5 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\CflApiJsonNew.h",
        v6);
    std::string::resize(v11, v5, 0);
    lpMultiByteStr = (CHAR *)v11;
    if ( *(_QWORD *)&cbMultiByte[2] > 0xFu )
      lpMultiByteStr = v11[0];
    v8 = *((_DWORD *)v2 + 4);
    if ( (unsigned __int64)v2[3] > 7 )
      v2 = (__int64 *)*v2;
    if ( !WideCharToMultiByte(0xFDE9u, 0x80u, (LPCWCH)v2, v8, lpMultiByteStr, cbMultiByte[0], 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\CflApiJsonNew.h",
        v9);
    *(_OWORD *)a1 = *(_OWORD *)v11;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)cbMultiByte;
    *(_QWORD *)cbMultiByte = 0;
    *(_QWORD *)&cbMultiByte[2] = 15;
    LOBYTE(v11[0]) = 0;
    std::string::~string(v11);
  }
  else
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 15;
    *(_BYTE *)a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18002c4a4  mov     [rsp-18h+arg_10], rbx
0x18002c4a9  mov     [rsp-18h+arg_18], rdi
0x18002c4ae  push    rbp
0x18002c4af  push    r14
0x18002c4b1  push    r15
0x18002c4b3  mov     rbp, rsp
0x18002c4b6  sub     rsp, 80h
0x18002c4bd  mov     rax, cs:__security_cookie
0x18002c4c4  xor     rax, rsp
0x18002c4c7  mov     [rbp+var_10], rax
0x18002c4cb  mov     rdi, rdx
0x18002c4ce  mov     rbx, rcx
0x18002c4d1  mov     [rbp+var_38], rcx
0x18002c4d5  xor     r15d, r15d
0x18002c4d8  xorps   xmm0, xmm0
0x18002c4db  cmp     [rdx+10h], r15
0x18002c4df  jnz     short loc_18002C4F8
0x18002c4e1  movups  xmmword ptr [rcx], xmm0
0x18002c4e4  mov     [rcx+10h], r15
0x18002c4e8  mov     qword ptr [rcx+18h], 0Fh
0x18002c4f0  mov     [rcx], r15b
0x18002c4f3  jmp     loc_18002C5D3
0x18002c4f8  movups  xmmword ptr [rbp+var_30], xmm0
0x18002c4fc  mov     qword ptr [rbp+var_20], r15
0x18002c500  mov     qword ptr [rbp+var_20+8], 0Fh
0x18002c508  mov     byte ptr [rbp+var_30], r15b
0x18002c50c  cmp     qword ptr [rdx+18h], 7
0x18002c511  jbe     short loc_18002C518
0x18002c513  mov     r8, [rdx]
0x18002c516  jmp     short loc_18002C51B
0x18002c518  mov     r8, rdi; lpWideCharStr
0x18002c51b  mov     [rsp+80h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18002c520  mov     [rsp+80h+lpDefaultChar], r15; lpDefaultChar
0x18002c525  mov     [rsp+80h+cbMultiByte], r15d; cbMultiByte
0x18002c52a  mov     [rsp+80h+lpMultiByteStr], r15; lpMultiByteStr
0x18002c52f  mov     r9d, [rdx+10h]; cchWideChar
0x18002c533  mov     edx, 80h; dwFlags
0x18002c538  mov     ecx, 0FDE9h; CodePage
0x18002c53d  call    cs:__imp_WideCharToMultiByte
0x18002c543  mov     rcx, [rbp+18h]; this
0x18002c547  test    eax, eax
0x18002c549  jz      loc_18002C610
0x18002c54f  movsxd  rdx, eax
0x18002c552  xor     r8d, r8d
0x18002c555  lea     rcx, [rbp+var_30]
0x18002c559  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x18002c55e  mov     ecx, [rbp+var_20]
0x18002c561  lea     rax, [rbp+var_30]
0x18002c565  cmp     qword ptr [rbp+var_20+8], 0Fh
0x18002c56a  cmova   rax, [rbp+var_30]
0x18002c56f  mov     r9d, [rdi+10h]; cchWideChar
0x18002c573  cmp     qword ptr [rdi+18h], 7
0x18002c578  jbe     short loc_18002C57D
0x18002c57a  mov     rdi, [rdi]
0x18002c57d  mov     r14, [rbp+18h]
0x18002c581  mov     [rsp+80h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18002c586  mov     [rsp+80h+lpDefaultChar], r15; lpDefaultChar
0x18002c58b  mov     [rsp+80h+cbMultiByte], ecx; cbMultiByte
0x18002c58f  mov     [rsp+80h+lpMultiByteStr], rax; lpMultiByteStr
0x18002c594  mov     r8, rdi; lpWideCharStr
0x18002c597  mov     edx, 80h; dwFlags
0x18002c59c  mov     ecx, 0FDE9h; CodePage
0x18002c5a1  call    cs:__imp_WideCharToMultiByte
0x18002c5a7  test    eax, eax
0x18002c5a9  jz      short loc_18002C5FB
0x18002c5ab  movups  xmm0, xmmword ptr [rbp+var_30]
0x18002c5af  movups  xmmword ptr [rbx], xmm0
0x18002c5b2  movups  xmm1, xmmword ptr [rbp+var_20]
0x18002c5b6  movups  xmmword ptr [rbx+10h], xmm1
0x18002c5ba  mov     qword ptr [rbp+var_20], r15
0x18002c5be  mov     qword ptr [rbp+var_20+8], 0Fh
0x18002c5c6  mov     byte ptr [rbp+var_30], r15b
0x18002c5ca  lea     rcx, [rbp+var_30]
0x18002c5ce  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002c5d3  mov     rax, rbx
0x18002c5d6  mov     rcx, [rbp+var_10]
0x18002c5da  xor     rcx, rsp; StackCookie
0x18002c5dd  call    __security_check_cookie
0x18002c5e2  lea     r11, [rsp+80h+var_s0]
0x18002c5ea  mov     rbx, [r11+30h]
0x18002c5ee  mov     rdi, [r11+38h]
0x18002c5f2  mov     rsp, r11
0x18002c5f5  pop     r15
0x18002c5f7  pop     r14
0x18002c5f9  pop     rbp
0x18002c5fa  retn
0x18002c5fb  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cfl\\api\\lib\\C"...
0x18002c602  mov     edx, 35h ; '5'; void *
0x18002c607  mov     rcx, r14; this
0x18002c60a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002c610  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cfl\\api\\lib\\C"...
0x18002c617  mov     edx, 30h ; '0'; void *
0x18002c61c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
