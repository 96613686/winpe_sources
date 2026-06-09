# DeriveKeyFromSecret(ushort const *,uchar *,ulong,ulong,uchar * *)

- ea: `0x180033b7c`
- end: `0x180033d74`
- name: `?DeriveKeyFromSecret@@YAJPEBGPEAEKKPEAPEAE@Z`
- size: `504`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 *, ULONG, unsigned int, unsigned __int8 **)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e130`
- `0x180024bb0`
- `0x18003c598`
- `0x18003cd70`
- `0x18005f84c`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180022f40`
- `0x1800293c0`
- `0x180033b7c`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180033d3c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180033d3c`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x180033c8c`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x180033c8c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180033bd1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180033bd1`

## string_xrefs

- `0x180033bdd`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180033c20`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180033c98`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180033cdc`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x180033bf8`: `BCryptOpenAlgorithmProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeriveKeyFromSecret(
        const unsigned __int16 *a1,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned int a4,
        unsigned __int8 **a5)
{
  unsigned __int8 **v5; // r14
  unsigned __int8 *v6; // rbx
  __int64 cbDerivedKey; // rsi
  unsigned int v10; // edi
  const char *v11; // r9
  UCHAR *pbDerivedKey; // rax
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // rax
  bool v17; // zf
  __int64 v18; // rax
  unsigned __int8 *v19; // rcx
  __int64 cbSalt; // [rsp+20h] [rbp-68h]
  BCRYPT_ALG_HANDLE hPrf; // [rsp+90h] [rbp+8h] BYREF

  v5 = a5;
  v6 = 0;
  cbDerivedKey = a4;
  hPrf = 0;
  if ( a5 && a4 )
  {
    *a5 = 0;
    v10 = BCryptOpenAlgorithmProvider(&hPrf, L"SHA256", 0, 8u);
    if ( v10 )
    {
      v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v11, 409, "BCryptOpenAlgorithmProvider", &Class);
    }
    else
    {
      pbDerivedKey = (UCHAR *)AllocateMemory((unsigned int)cbDerivedKey);
      v6 = pbDerivedKey;
      if ( pbDerivedKey )
      {
        v10 = BCryptDeriveKeyPBKDF2(hPrf, a2, a3, 0, 0, 0x2710u, pbDerivedKey, cbDerivedKey, 0);
        if ( v10 )
        {
          v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
          LODWORD(cbSalt) = 430;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v14, cbSalt, "BCryptDeriveKeyPBKDF2", &Class);
        }
        else
        {
          *v5 = v6;
          v6 = 0;
        }
      }
      else
      {
        v10 = -1073741801;
        v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v13, 416, "AllocateMemory", &Class);
      }
    }
  }
  else
  {
    v10 = -1073741811;
    v15 = "";
    while ( 1 )
    {
      v16 = v15--;
      v17 = *v15 == 92;
      if ( *v15 == 92 )
        break;
      if ( v15 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp" )
      {
        v17 = *v15 == 92;
        break;
      }
    }
    if ( v17 )
      v15 = v16;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v15, 391, "InvalidArgs", &Class);
  }
  if ( hPrf )
    BCryptCloseAlgorithmProvider(hPrf, 0);
  if ( v6 )
  {
    v18 = cbDerivedKey;
    v19 = v6;
    if ( (_DWORD)cbDerivedKey )
    {
      do
      {
        *v19++ = 0;
        --v18;
      }
      while ( v18 );
    }
    FreeMemory(v6);
  }
  return v10;
}

```

## disassembly

```asm
0x180033b7c  mov     rax, rsp
0x180033b7f  mov     [rax+8], rcx
0x180033b83  push    rbx
0x180033b84  push    rbp
0x180033b85  push    rsi
0x180033b86  push    rdi
0x180033b87  push    r14
0x180033b89  push    r15
0x180033b8b  sub     rsp, 58h
0x180033b8f  mov     r14, [rsp+88h+arg_20]
0x180033b97  xor     ebx, ebx
0x180033b99  mov     esi, r9d
0x180033b9c  mov     ebp, r8d
0x180033b9f  mov     qword ptr [rax+8], 0
0x180033ba7  mov     r15, rdx
0x180033baa  test    r14, r14
0x180033bad  jz      loc_180033CD0
0x180033bb3  test    r9d, r9d
0x180033bb6  jz      loc_180033CD0
0x180033bbc  lea     r9d, [rbx+8]; dwFlags
0x180033bc0  mov     [r14], rbx
0x180033bc3  xor     r8d, r8d; pszImplementation
0x180033bc6  lea     rdx, pszAlgId; "SHA256"
0x180033bcd  lea     rcx, [rax+8]; phAlgorithm
0x180033bd1  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180033bd7  mov     edi, eax
0x180033bd9  test    eax, eax
0x180033bdb  jz      short loc_180033C11
0x180033bdd  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180033be4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180033be9  mov     r9, rax
0x180033bec  lea     rax, Class
0x180033bf3  mov     [rsp+88h+pbDerivedKey], rax
0x180033bf8  lea     rax, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x180033bff  mov     [rsp+88h+cIterations], rax
0x180033c04  mov     dword ptr [rsp+88h+cbSalt], 199h
0x180033c0c  jmp     loc_180033D1C
0x180033c11  mov     ecx, esi; uBytes
0x180033c13  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x180033c18  mov     rbx, rax
0x180033c1b  test    rax, rax
0x180033c1e  jnz     short loc_180033C59
0x180033c20  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180033c27  mov     edi, 0C0000017h
0x180033c2c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180033c31  mov     r9, rax
0x180033c34  lea     rax, Class
0x180033c3b  mov     [rsp+88h+pbDerivedKey], rax
0x180033c40  lea     rax, aAllocatememory; "AllocateMemory"
0x180033c47  mov     [rsp+88h+cIterations], rax
0x180033c4c  mov     dword ptr [rsp+88h+cbSalt], 1A0h
0x180033c54  jmp     loc_180033D1C
0x180033c59  mov     rcx, [rsp+88h+hPrf]; hPrf
0x180033c61  xor     r9d, r9d; pbSalt
0x180033c64  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180033c6c  mov     r8d, ebp; cbPassword
0x180033c6f  mov     [rsp+88h+cbDerivedKey], esi; cbDerivedKey
0x180033c73  mov     rdx, r15; pbPassword
0x180033c76  mov     [rsp+88h+pbDerivedKey], rbx; pbDerivedKey
0x180033c7b  mov     [rsp+88h+cIterations], 2710h; cIterations
0x180033c84  mov     dword ptr [rsp+88h+cbSalt], 0; cbSalt
0x180033c8c  call    cs:__imp_BCryptDeriveKeyPBKDF2
0x180033c92  mov     edi, eax
0x180033c94  test    eax, eax
0x180033c96  jz      short loc_180033CC9
0x180033c98  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180033c9f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180033ca4  mov     r9, rax
0x180033ca7  lea     rax, Class
0x180033cae  mov     [rsp+88h+pbDerivedKey], rax
0x180033cb3  lea     rax, aBcryptderiveke; "BCryptDeriveKeyPBKDF2"
0x180033cba  mov     [rsp+88h+cIterations], rax
0x180033cbf  mov     dword ptr [rsp+88h+cbSalt], 1AEh
0x180033cc7  jmp     short loc_180033D1C
0x180033cc9  mov     [r14], rbx
0x180033ccc  xor     ebx, ebx
0x180033cce  jmp     short loc_180033D2D
0x180033cd0  mov     edi, 0C000000Dh
0x180033cd5  lea     r9, aOnecoreDsExtCl_3+3Eh; ""
0x180033cdc  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180033ce3  mov     rax, r9
0x180033ce6  dec     r9
0x180033ce9  cmp     byte ptr [r9], 5Ch ; '\'
0x180033ced  jz      short loc_180033CF8
0x180033cef  cmp     r9, rcx
0x180033cf2  ja      short loc_180033CE3
0x180033cf4  cmp     byte ptr [r9], 5Ch ; '\'
0x180033cf8  cmovz   r9, rax
0x180033cfc  lea     rax, Class
0x180033d03  mov     [rsp+88h+pbDerivedKey], rax
0x180033d08  lea     rax, aInvalidargs; "InvalidArgs"
0x180033d0f  mov     [rsp+88h+cIterations], rax
0x180033d14  mov     dword ptr [rsp+88h+cbSalt], 187h
0x180033d1c  mov     r8d, edi
0x180033d1f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180033d26  xor     ecx, ecx
0x180033d28  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180033d2d  mov     rcx, [rsp+88h+hPrf]; hAlgorithm
0x180033d35  test    rcx, rcx
0x180033d38  jz      short loc_180033D42
0x180033d3a  xor     edx, edx; dwFlags
0x180033d3c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180033d42  test    rbx, rbx
0x180033d45  jz      short loc_180033D65
0x180033d47  mov     rax, rsi
0x180033d4a  mov     rcx, rbx
0x180033d4d  test    esi, esi
0x180033d4f  jz      short loc_180033D5D
0x180033d51  mov     byte ptr [rcx], 0
0x180033d54  inc     rcx
0x180033d57  sub     rax, 1
0x180033d5b  jnz     short loc_180033D51
0x180033d5d  mov     rcx, rbx; void *
0x180033d60  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x180033d65  mov     eax, edi
0x180033d67  add     rsp, 58h
0x180033d6b  pop     r15
0x180033d6d  pop     r14
0x180033d6f  pop     rdi
0x180033d70  pop     rsi
0x180033d71  pop     rbp
0x180033d72  pop     rbx
0x180033d73  retn
```
