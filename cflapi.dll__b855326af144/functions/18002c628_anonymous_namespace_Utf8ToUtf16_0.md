# _anonymous_namespace_::Utf8ToUtf16_0

- ea: `0x18002c628`
- end: `0x18002c80b`
- name: `_anonymous_namespace_::Utf8ToUtf16_0`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028cc4`
- `0x18002b264`

## callees

- `0x180002490`
- `0x180008ad0`
- `0x180015c78`
- `0x180022280`
- `0x18002c628`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c6be`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c77d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c6be`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002c77d`

## string_xrefs

- `0x18002c7e4`: `onecore\ds\security\cfl\api\lib\CflApiJsonNew.h`
- `0x18002c7f9`: `onecore\ds\security\cfl\api\lib\CflApiJsonNew.h`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::Utf8ToUtf16_0(__int64 a1, __int64 *a2)
{
  __int64 *v2; // rsi
  const CHAR *v4; // r8
  int v5; // eax
  const char *v6; // r9
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  _WORD *v9; // rdi
  __int64 i; // rcx
  WCHAR *lpWideCharStr; // rax
  int v12; // r9d
  __int64 v13; // rdx
  __int64 v14; // r8
  const char *v15; // r9
  LPWSTR Src[2]; // [rsp+40h] [rbp-30h] BYREF
  int cchWideChar[4]; // [rsp+50h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v2 = a2;
  if ( a2[2] )
  {
    *(_OWORD *)Src = 0;
    *(_QWORD *)cchWideChar = 0;
    *(_QWORD *)&cchWideChar[2] = 7;
    LOWORD(Src[0]) = 0;
    if ( (unsigned __int64)a2[3] <= 0xF )
      v4 = (const CHAR *)a2;
    else
      v4 = (const CHAR *)*a2;
    v5 = MultiByteToWideChar(0xFDE9u, 8u, v4, *((_DWORD *)a2 + 4), 0, 0);
    if ( !v5 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x19,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\CflApiJsonNew.h",
        v6);
    v7 = *(_QWORD *)cchWideChar;
    if ( (unsigned __int64)v5 > *(_QWORD *)cchWideChar )
    {
      v8 = v5 - *(_QWORD *)cchWideChar;
      if ( v8 > *(_QWORD *)&cchWideChar[2] - *(_QWORD *)cchWideChar )
      {
        std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(Src);
      }
      else
      {
        *(_QWORD *)cchWideChar = v5;
        v9 = (_WORD *)Src + v7;
        if ( v8 )
        {
          for ( i = v5 - v7; i; --i )
            *v9++ = 0;
        }
        *((_WORD *)Src + v5) = 0;
      }
    }
    else
    {
      *(_QWORD *)cchWideChar = v5;
      *((_WORD *)Src + v5) = 0;
    }
    lpWideCharStr = (WCHAR *)Src;
    if ( *(_QWORD *)&cchWideChar[2] > 7u )
      lpWideCharStr = Src[0];
    v12 = *((_DWORD *)v2 + 4);
    if ( (unsigned __int64)v2[3] > 0xF )
      v2 = (__int64 *)*v2;
    if ( !MultiByteToWideChar(0xFDE9u, 8u, (LPCCH)v2, v12, lpWideCharStr, cchWideChar[0]) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\CflApiJsonNew.h",
        v15);
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)Src;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)cchWideChar;
    *(_QWORD *)cchWideChar = 0;
    *(_QWORD *)&cchWideChar[2] = 7;
    LOWORD(Src[0]) = 0;
    std::wstring::~wstring(Src, v13, v14);
  }
  else
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 7;
    *(_WORD *)a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18002c628  mov     [rsp-18h+arg_10], rbx
0x18002c62d  push    rbp
0x18002c62e  push    rsi
0x18002c62f  push    rdi
0x18002c630  mov     rbp, rsp
0x18002c633  sub     rsp, 70h
0x18002c637  mov     rax, cs:__security_cookie
0x18002c63e  xor     rax, rsp
0x18002c641  mov     [rbp+var_10], rax
0x18002c645  mov     rsi, rdx
0x18002c648  mov     rbx, rcx
0x18002c64b  mov     [rbp+var_38], rcx
0x18002c64f  xorps   xmm0, xmm0
0x18002c652  cmp     qword ptr [rdx+10h], 0
0x18002c657  jnz     short loc_18002C676
0x18002c659  movups  xmmword ptr [rcx], xmm0
0x18002c65c  mov     qword ptr [rcx+10h], 0
0x18002c664  mov     qword ptr [rcx+18h], 7
0x18002c66c  xor     ecx, ecx
0x18002c66e  mov     [rbx], cx
0x18002c671  jmp     loc_18002C7C5
0x18002c676  movups  xmmword ptr [rbp+Src], xmm0
0x18002c67a  mov     qword ptr [rbp+var_20], 0
0x18002c682  mov     qword ptr [rbp+var_20+8], 7
0x18002c68a  xor     eax, eax
0x18002c68c  mov     word ptr [rbp+Src], ax
0x18002c690  cmp     qword ptr [rdx+18h], 0Fh
0x18002c695  jbe     short loc_18002C69C
0x18002c697  mov     r8, [rdx]
0x18002c69a  jmp     short loc_18002C69F
0x18002c69c  mov     r8, rsi; lpMultiByteStr
0x18002c69f  mov     [rsp+70h+cchWideChar], 0; cchWideChar
0x18002c6a7  mov     [rsp+70h+lpWideCharStr], 0; lpWideCharStr
0x18002c6b0  mov     r9d, [rdx+10h]; cbMultiByte
0x18002c6b4  mov     edx, 8; dwFlags
0x18002c6b9  mov     ecx, 0FDE9h; CodePage
0x18002c6be  call    cs:__imp_MultiByteToWideChar
0x18002c6c4  mov     rcx, [rbp+18h]; this
0x18002c6c8  test    eax, eax
0x18002c6ca  jz      loc_18002C7F9
0x18002c6d0  mov     rcx, qword ptr [rbp+var_20]
0x18002c6d4  movsxd  r8, eax
0x18002c6d7  cmp     r8, rcx
0x18002c6da  ja      short loc_18002C6F7
0x18002c6dc  mov     qword ptr [rbp+var_20], r8
0x18002c6e0  lea     rcx, [rbp+Src]
0x18002c6e4  cmp     qword ptr [rbp+var_20+8], 7
0x18002c6e9  cmova   rcx, [rbp+Src]
0x18002c6ee  xor     eax, eax
0x18002c6f0  mov     [rcx+r8*2], ax
0x18002c6f5  jmp     short loc_18002C744
0x18002c6f7  mov     rdx, r8
0x18002c6fa  sub     rdx, rcx
0x18002c6fd  mov     rax, qword ptr [rbp+var_20+8]
0x18002c701  sub     rax, rcx
0x18002c704  cmp     rdx, rax
0x18002c707  ja      short loc_18002C738
0x18002c709  mov     qword ptr [rbp+var_20], r8
0x18002c70d  lea     r9, [rbp+Src]
0x18002c711  cmp     qword ptr [rbp+var_20+8], 7
0x18002c716  cmova   r9, [rbp+Src]
0x18002c71b  lea     rdi, [r9+rcx*2]
0x18002c71f  test    rdx, rdx
0x18002c722  jz      short loc_18002C72F
0x18002c724  xor     eax, eax
0x18002c726  movzx   eax, ax
0x18002c729  mov     rcx, rdx
0x18002c72c  rep stosw
0x18002c72f  xor     eax, eax
0x18002c731  mov     [r9+r8*2], ax
0x18002c736  jmp     short loc_18002C744
0x18002c738  mov     r9, rdx
0x18002c73b  lea     rcx, [rbp+Src]; Src
0x18002c73f  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x18002c744  mov     ecx, [rbp+var_20]
0x18002c747  lea     rax, [rbp+Src]
0x18002c74b  cmp     qword ptr [rbp+var_20+8], 7
0x18002c750  cmova   rax, [rbp+Src]
0x18002c755  mov     r9d, [rsi+10h]; cbMultiByte
0x18002c759  cmp     qword ptr [rsi+18h], 0Fh
0x18002c75e  jbe     short loc_18002C763
0x18002c760  mov     rsi, [rsi]
0x18002c763  mov     rdi, [rbp+18h]
0x18002c767  mov     [rsp+70h+cchWideChar], ecx; cchWideChar
0x18002c76b  mov     [rsp+70h+lpWideCharStr], rax; lpWideCharStr
0x18002c770  mov     r8, rsi; lpMultiByteStr
0x18002c773  mov     edx, 8; dwFlags
0x18002c778  mov     ecx, 0FDE9h; CodePage
0x18002c77d  call    cs:__imp_MultiByteToWideChar
0x18002c783  test    eax, eax
0x18002c785  jz      short loc_18002C7E4
0x18002c787  mov     qword ptr [rbx+10h], 0
0x18002c78f  mov     qword ptr [rbx+18h], 0
0x18002c797  movups  xmm0, xmmword ptr [rbp+Src]
0x18002c79b  movups  xmmword ptr [rbx], xmm0
0x18002c79e  movups  xmm1, xmmword ptr [rbp+var_20]
0x18002c7a2  movups  xmmword ptr [rbx+10h], xmm1
0x18002c7a6  mov     qword ptr [rbp+var_20], 0
0x18002c7ae  mov     qword ptr [rbp+var_20+8], 7
0x18002c7b6  xor     eax, eax
0x18002c7b8  mov     word ptr [rbp+Src], ax
0x18002c7bc  lea     rcx, [rbp+Src]
0x18002c7c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c7c5  mov     rax, rbx
0x18002c7c8  mov     rcx, [rbp+var_10]
0x18002c7cc  xor     rcx, rsp; StackCookie
0x18002c7cf  call    __security_check_cookie
0x18002c7d4  mov     rbx, [rsp+70h+arg_10]
0x18002c7dc  add     rsp, 70h
0x18002c7e0  pop     rdi
0x18002c7e1  pop     rsi
0x18002c7e2  pop     rbp
0x18002c7e3  retn
0x18002c7e4  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cfl\\api\\lib\\C"...
0x18002c7eb  mov     edx, 1Dh; void *
0x18002c7f0  mov     rcx, rdi; this
0x18002c7f3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002c7f9  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cfl\\api\\lib\\C"...
0x18002c800  mov     edx, 19h; void *
0x18002c805  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
