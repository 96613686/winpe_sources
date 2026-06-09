# _anonymous_namespace_::Utf8ToUtf16

- ea: `0x180021184`
- end: `0x180021367`
- name: `_anonymous_namespace_::Utf8ToUtf16`
- size: `483`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016e28`
- `0x18001cb44`
- `0x18001fb28`

## callees

- `0x180002490`
- `0x180008ad0`
- `0x180015c78`
- `0x180021184`
- `0x180022280`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002121a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800212d9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002121a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800212d9`

## string_xrefs

- `0x180021340`: `onecore\ds\security\cfl\api\lib\CflApiJson.h`
- `0x180021355`: `onecore\ds\security\cfl\api\lib\CflApiJson.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::Utf8ToUtf16(__int64 a1, __int64 *a2)
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
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\CflApiJson.h",
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
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\CflApiJson.h",
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
0x180021184  mov     [rsp-18h+arg_10], rbx
0x180021189  push    rbp
0x18002118a  push    rsi
0x18002118b  push    rdi
0x18002118c  mov     rbp, rsp
0x18002118f  sub     rsp, 70h
0x180021193  mov     rax, cs:__security_cookie
0x18002119a  xor     rax, rsp
0x18002119d  mov     [rbp+var_10], rax
0x1800211a1  mov     rsi, rdx
0x1800211a4  mov     rbx, rcx
0x1800211a7  mov     [rbp+var_38], rcx
0x1800211ab  xorps   xmm0, xmm0
0x1800211ae  cmp     qword ptr [rdx+10h], 0
0x1800211b3  jnz     short loc_1800211D2
0x1800211b5  movups  xmmword ptr [rcx], xmm0
0x1800211b8  mov     qword ptr [rcx+10h], 0
0x1800211c0  mov     qword ptr [rcx+18h], 7
0x1800211c8  xor     ecx, ecx
0x1800211ca  mov     [rbx], cx
0x1800211cd  jmp     loc_180021321
0x1800211d2  movups  xmmword ptr [rbp+Src], xmm0
0x1800211d6  mov     qword ptr [rbp+var_20], 0
0x1800211de  mov     qword ptr [rbp+var_20+8], 7
0x1800211e6  xor     eax, eax
0x1800211e8  mov     word ptr [rbp+Src], ax
0x1800211ec  cmp     qword ptr [rdx+18h], 0Fh
0x1800211f1  jbe     short loc_1800211F8
0x1800211f3  mov     r8, [rdx]
0x1800211f6  jmp     short loc_1800211FB
0x1800211f8  mov     r8, rsi; lpMultiByteStr
0x1800211fb  mov     [rsp+70h+cchWideChar], 0; cchWideChar
0x180021203  mov     [rsp+70h+lpWideCharStr], 0; lpWideCharStr
0x18002120c  mov     r9d, [rdx+10h]; cbMultiByte
0x180021210  mov     edx, 8; dwFlags
0x180021215  mov     ecx, 0FDE9h; CodePage
0x18002121a  call    cs:__imp_MultiByteToWideChar
0x180021220  mov     rcx, [rbp+18h]; this
0x180021224  test    eax, eax
0x180021226  jz      loc_180021355
0x18002122c  mov     rcx, qword ptr [rbp+var_20]
0x180021230  movsxd  r8, eax
0x180021233  cmp     r8, rcx
0x180021236  ja      short loc_180021253
0x180021238  mov     qword ptr [rbp+var_20], r8
0x18002123c  lea     rcx, [rbp+Src]
0x180021240  cmp     qword ptr [rbp+var_20+8], 7
0x180021245  cmova   rcx, [rbp+Src]
0x18002124a  xor     eax, eax
0x18002124c  mov     [rcx+r8*2], ax
0x180021251  jmp     short loc_1800212A0
0x180021253  mov     rdx, r8
0x180021256  sub     rdx, rcx
0x180021259  mov     rax, qword ptr [rbp+var_20+8]
0x18002125d  sub     rax, rcx
0x180021260  cmp     rdx, rax
0x180021263  ja      short loc_180021294
0x180021265  mov     qword ptr [rbp+var_20], r8
0x180021269  lea     r9, [rbp+Src]
0x18002126d  cmp     qword ptr [rbp+var_20+8], 7
0x180021272  cmova   r9, [rbp+Src]
0x180021277  lea     rdi, [r9+rcx*2]
0x18002127b  test    rdx, rdx
0x18002127e  jz      short loc_18002128B
0x180021280  xor     eax, eax
0x180021282  movzx   eax, ax
0x180021285  mov     rcx, rdx
0x180021288  rep stosw
0x18002128b  xor     eax, eax
0x18002128d  mov     [r9+r8*2], ax
0x180021292  jmp     short loc_1800212A0
0x180021294  mov     r9, rdx
0x180021297  lea     rcx, [rbp+Src]; Src
0x18002129b  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x1800212a0  mov     ecx, [rbp+var_20]
0x1800212a3  lea     rax, [rbp+Src]
0x1800212a7  cmp     qword ptr [rbp+var_20+8], 7
0x1800212ac  cmova   rax, [rbp+Src]
0x1800212b1  mov     r9d, [rsi+10h]; cbMultiByte
0x1800212b5  cmp     qword ptr [rsi+18h], 0Fh
0x1800212ba  jbe     short loc_1800212BF
0x1800212bc  mov     rsi, [rsi]
0x1800212bf  mov     rdi, [rbp+18h]
0x1800212c3  mov     [rsp+70h+cchWideChar], ecx; cchWideChar
0x1800212c7  mov     [rsp+70h+lpWideCharStr], rax; lpWideCharStr
0x1800212cc  mov     r8, rsi; lpMultiByteStr
0x1800212cf  mov     edx, 8; dwFlags
0x1800212d4  mov     ecx, 0FDE9h; CodePage
0x1800212d9  call    cs:__imp_MultiByteToWideChar
0x1800212df  test    eax, eax
0x1800212e1  jz      short loc_180021340
0x1800212e3  mov     qword ptr [rbx+10h], 0
0x1800212eb  mov     qword ptr [rbx+18h], 0
0x1800212f3  movups  xmm0, xmmword ptr [rbp+Src]
0x1800212f7  movups  xmmword ptr [rbx], xmm0
0x1800212fa  movups  xmm1, xmmword ptr [rbp+var_20]
0x1800212fe  movups  xmmword ptr [rbx+10h], xmm1
0x180021302  mov     qword ptr [rbp+var_20], 0
0x18002130a  mov     qword ptr [rbp+var_20+8], 7
0x180021312  xor     eax, eax
0x180021314  mov     word ptr [rbp+Src], ax
0x180021318  lea     rcx, [rbp+Src]
0x18002131c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021321  mov     rax, rbx
0x180021324  mov     rcx, [rbp+var_10]
0x180021328  xor     rcx, rsp; StackCookie
0x18002132b  call    __security_check_cookie
0x180021330  mov     rbx, [rsp+70h+arg_10]
0x180021338  add     rsp, 70h
0x18002133c  pop     rdi
0x18002133d  pop     rsi
0x18002133e  pop     rbp
0x18002133f  retn
0x180021340  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\api\\lib\\C"...
0x180021347  mov     edx, 1Dh; void *
0x18002134c  mov     rcx, rdi; this
0x18002134f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180021355  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\api\\lib\\C"...
0x18002135c  mov     edx, 19h; void *
0x180021361  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
