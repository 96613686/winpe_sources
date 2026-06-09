# DuplicateString(ushort const *,int,ushort * *)

- ea: `0x18000b9b0`
- end: `0x18000bd8e`
- name: `?DuplicateString@@YAJPEBGHPEAPEAG@Z`
- size: `990`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, int, unsigned __int16 **)`
- caller_count: `24`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000498c`
- `0x180004e80`
- `0x180008060`
- `0x18000c730`
- `0x18000d000`
- `0x18000db68`
- `0x180018a20`
- `0x180020b10`
- `0x180022f80`
- `0x180029650`
- `0x18002feb4`
- `0x180032998`
- `0x180034e20`
- `0x180037240`
- `0x180040fe4`
- `0x180047c70`
- `0x18004d294`
- `0x18004e7b0`
- `0x18004f600`
- `0x180052978`
- `0x180054ff4`
- `0x18005c644`
- `0x18005e654`
- `0x18005ea48`

## callees

- `0x180007fc0`
- `0x180009a10`
- `0x18000a600`
- `0x18000b9b0`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd52`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18000ba1d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18000bbc3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18000ba1d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18000bbc3`

## string_xrefs

- `0x18000ba4e`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000bae1`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000bc2c`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000bc63`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000bc97`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000bce2`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000bd0f`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000bd61`: `onecore\ds\ext\cloudap\dll\utils.cpp`

## pseudocode

```c
__int64 __fastcall DuplicateString(const unsigned __int16 *Src, int a2, unsigned __int16 **a3)
{
  char v3; // al
  __int64 v6; // rbx
  unsigned int cchDest; // r14d
  unsigned int LastError; // ebx
  const UCHAR *v9; // rax
  char v10; // cl
  const UCHAR *v11; // rdx
  bool v12; // zf
  const UCHAR *v13; // rax
  char v14; // cl
  const UCHAR *v15; // r8
  __int64 v16; // r10
  int v17; // edx
  const char *v18; // rcx
  const char *v19; // r9
  unsigned __int16 *v21; // rax
  unsigned __int64 v22; // rbx
  unsigned __int16 *v23; // rax
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // rax
  const char *v27; // r9
  LPWSTR lpDestStr; // [rsp+20h] [rbp-68h]
  LPWSTR lpDestStrb; // [rsp+20h] [rbp-68h]
  LPWSTR lpDestStra; // [rsp+20h] [rbp-68h]

  v3 = g_ulTestFlags;
  *a3 = 0;
  if ( (v3 & 2) != 0 )
  {
    LastError = DuplicateStringPreRS2(Src, a2, a3);
    if ( LastError )
    {
      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v24, 84, "DuplicateStringPreRS2", &Class);
    }
    goto LABEL_23;
  }
  if ( !Src )
    return 0;
  v6 = -1;
  if ( a2 )
  {
    cchDest = LCMapStringEx(&Class, 0x100u, Src, -1, 0, 0, 0, 0, 0);
    if ( cchDest )
    {
      if ( 2 * (unsigned __int64)cchDest > 0xFFFFFFFF )
      {
        LastError = -1073741675;
        v9 = "";
        while ( 1 )
        {
          v10 = *(v9 - 1);
          v11 = v9--;
          v12 = v10 == 92;
          if ( v10 == 92 )
            break;
          if ( v9 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
          {
            v12 = v10 == 92;
            break;
          }
        }
        if ( v12 )
          v9 = v11;
        LODWORD(lpDestStr) = 124;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v9, lpDestStr, "RtlDWordMult", &Class);
        goto LABEL_13;
      }
      v21 = (unsigned __int16 *)((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
      *a3 = v21;
      if ( !v21 )
      {
        LastError = -1073741801;
        v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(lpDestStr) = 130;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v26, lpDestStr, "AllocateLsaHeap", &Class);
        goto LABEL_13;
      }
      if ( LCMapStringEx(&Class, 0x100u, Src, -1, v21, cchDest, 0, 0, 0) )
        return 0;
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(lpDestStra) = 145;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v27, lpDestStra, "LCMapStringEx", &Class);
    }
    else
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(lpDestStr) = 118;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v25, lpDestStr, "LCMapStringEx", &Class);
    }
LABEL_23:
    if ( (LastError & 0x80000000) == 0 )
      return LastError;
LABEL_13:
    if ( *a3 )
      ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
    return LastError;
  }
  do
    ++v6;
  while ( Src[v6] );
  if ( (int)v6 + 1 < (unsigned int)v6 )
  {
    LastError = -1073741675;
    v13 = "";
    do
    {
      v14 = *(v13 - 1);
      v15 = v13--;
    }
    while ( v14 != 92 && v13 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
    v12 = v14 == 92;
    v16 = 0;
    v17 = 39;
    v18 = "RtlDWordAdd";
    if ( v12 )
      v13 = v15;
    goto LABEL_22;
  }
  v22 = 2LL * (unsigned int)(v6 + 1);
  if ( v22 > 0xFFFFFFFF )
  {
    LastError = -1073741675;
    v13 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    v17 = 42;
    v18 = "RtlDWordMult";
LABEL_22:
    WPPTraceLogA(v16, "0x%08x %s:%u : %s:%ws", LastError, v13, v17, v18, &Class);
    v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(lpDestStrb) = 101;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v19, lpDestStrb, "DuplicateStringPreRS2", &Class);
    goto LABEL_23;
  }
  v23 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned int)v22);
  *a3 = v23;
  if ( !v23 )
  {
    LastError = -1073741801;
    v13 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    v17 = 48;
    v18 = "AllocateLsaHeap";
    goto LABEL_22;
  }
  memcpy_0(v23, Src, (unsigned int)v22);
  return 0;
}

```

## disassembly

```asm
0x18000b9b0  push    rbx
0x18000b9b2  push    rbp
0x18000b9b3  push    rsi
0x18000b9b4  push    rdi
0x18000b9b5  push    r14
0x18000b9b7  push    r15
0x18000b9b9  sub     rsp, 58h
0x18000b9bd  mov     eax, cs:?g_ulTestFlags@@3KA; ulong g_ulTestFlags
0x18000b9c3  xor     r15d, r15d
0x18000b9c6  mov     [r8], r15
0x18000b9c9  mov     rsi, r8
0x18000b9cc  mov     rdi, rcx
0x18000b9cf  test    al, 2
0x18000b9d1  jnz     loc_18000BC54
0x18000b9d7  test    rcx, rcx
0x18000b9da  jz      loc_18000BBD1
0x18000b9e0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b9e7  test    edx, edx
0x18000b9e9  jz      loc_18000BAC0
0x18000b9ef  mov     [rsp+88h+sortHandle], r15; sortHandle
0x18000b9f4  lea     rbp, Class
0x18000b9fb  mov     [rsp+88h+lpReserved], r15; lpReserved
0x18000ba00  mov     r8, rcx; lpSrcStr
0x18000ba03  mov     [rsp+88h+lpVersionInformation], r15; lpVersionInformation
0x18000ba08  mov     r9d, ebx; cchSrc
0x18000ba0b  mov     [rsp+88h+cchDest], r15d; cchDest
0x18000ba10  mov     edx, 100h; dwMapFlags
0x18000ba15  mov     rcx, rbp; lpLocaleName
0x18000ba18  mov     [rsp+88h+lpDestStr], r15; lpDestStr
0x18000ba1d  call    cs:__imp_LCMapStringEx
0x18000ba23  mov     r14d, eax
0x18000ba26  test    eax, eax
0x18000ba28  jz      loc_18000BCBF
0x18000ba2e  mov     ecx, r14d
0x18000ba31  mov     eax, 0FFFFFFFFh
0x18000ba36  add     rcx, rcx
0x18000ba39  cmp     rcx, rax
0x18000ba3c  jbe     loc_18000BB80
0x18000ba42  mov     ebx, 0C0000095h
0x18000ba47  lea     rax, pbInput+24h; ""
0x18000ba4e  lea     rdi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000ba55  movzx   ecx, byte ptr [rax-1]
0x18000ba59  mov     rdx, rax
0x18000ba5c  dec     rax
0x18000ba5f  cmp     cl, 5Ch ; '\'
0x18000ba62  jz      short loc_18000BA6C
0x18000ba64  cmp     rax, rdi
0x18000ba67  ja      short loc_18000BA55
0x18000ba69  cmp     cl, 5Ch ; '\'
0x18000ba6c  mov     [rsp+88h+lpVersionInformation], rbp
0x18000ba71  lea     rcx, aRtldwordmult; "RtlDWordMult"
0x18000ba78  mov     qword ptr [rsp+88h+cchDest], rcx
0x18000ba7d  cmovz   rax, rdx
0x18000ba81  mov     dword ptr [rsp+88h+lpDestStr], 7Ch ; '|'
0x18000ba89  mov     r9, rax
0x18000ba8c  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ba93  mov     r8d, ebx
0x18000ba96  xor     ecx, ecx
0x18000ba98  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000ba9d  mov     rcx, [rsi]
0x18000baa0  test    rcx, rcx
0x18000baa3  jz      loc_18000BB7C
0x18000baa9  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000bab0  mov     rax, [rax+30h]
0x18000bab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bab9  jmp     loc_18000BB7C
0x18000bac0  inc     rbx
0x18000bac3  cmp     [rcx+rbx*2], r15w
0x18000bac8  jnz     short loc_18000BAC0
0x18000baca  lea     eax, [rbx+1]
0x18000bacd  cmp     eax, ebx
0x18000bacf  jnb     loc_18000BBE1
0x18000bad5  mov     ebx, 0C0000095h
0x18000bada  lea     rax, pbInput+24h; ""
0x18000bae1  lea     rdi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000bae8  movzx   ecx, byte ptr [rax-1]
0x18000baec  mov     r8, rax
0x18000baef  dec     rax
0x18000baf2  cmp     cl, 5Ch ; '\'
0x18000baf5  jz      short loc_18000BAFC
0x18000baf7  cmp     rax, rdi
0x18000bafa  ja      short loc_18000BAE8
0x18000bafc  cmp     cl, 5Ch ; '\'
0x18000baff  mov     r10, r15
0x18000bb02  mov     edx, 27h ; '''
0x18000bb07  lea     rcx, aRtldwordadd; "RtlDWordAdd"
0x18000bb0e  cmovz   rax, r8
0x18000bb12  lea     rbp, Class
0x18000bb19  mov     r9, rax
0x18000bb1c  mov     [rsp+88h+lpVersionInformation], rbp
0x18000bb21  mov     r8, rbp
0x18000bb24  mov     qword ptr [rsp+88h+cchDest], rcx
0x18000bb29  mov     r8d, ebx
0x18000bb2c  mov     dword ptr [rsp+88h+lpDestStr], edx
0x18000bb30  mov     rcx, r10
0x18000bb33  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000bb3a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000bb3f  mov     rcx, rdi; char *
0x18000bb42  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000bb47  mov     [rsp+88h+lpVersionInformation], rbp
0x18000bb4c  mov     r9, rax
0x18000bb4f  lea     rax, aDuplicatestrin_0; "DuplicateStringPreRS2"
0x18000bb56  mov     qword ptr [rsp+88h+cchDest], rax
0x18000bb5b  mov     dword ptr [rsp+88h+lpDestStr], 65h ; 'e'
0x18000bb63  mov     r8d, ebx
0x18000bb66  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000bb6d  xor     ecx, ecx
0x18000bb6f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000bb74  test    ebx, ebx
0x18000bb76  js      loc_18000BA9D
0x18000bb7c  mov     eax, ebx
0x18000bb7e  jmp     short loc_18000BBD4
0x18000bb80  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000bb87  mov     rax, [rax+28h]
0x18000bb8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb90  mov     [rsi], rax
0x18000bb93  test    rax, rax
0x18000bb96  jz      loc_18000BD0F
0x18000bb9c  mov     [rsp+88h+sortHandle], r15; sortHandle
0x18000bba1  mov     r9d, ebx; cchSrc
0x18000bba4  mov     [rsp+88h+lpReserved], r15; lpReserved
0x18000bba9  mov     r8, rdi; lpSrcStr
0x18000bbac  mov     [rsp+88h+lpVersionInformation], r15; lpVersionInformation
0x18000bbb1  mov     edx, 100h; dwMapFlags
0x18000bbb6  mov     [rsp+88h+cchDest], r14d; cchDest
0x18000bbbb  mov     rcx, rbp; lpLocaleName
0x18000bbbe  mov     [rsp+88h+lpDestStr], rax; lpDestStr
0x18000bbc3  call    cs:__imp_LCMapStringEx
0x18000bbc9  test    eax, eax
0x18000bbcb  jz      loc_18000BD3E
0x18000bbd1  mov     eax, r15d
0x18000bbd4  add     rsp, 58h
0x18000bbd8  pop     r15
0x18000bbda  pop     r14
0x18000bbdc  pop     rdi
0x18000bbdd  pop     rsi
0x18000bbde  pop     rbp
0x18000bbdf  pop     rbx
0x18000bbe0  retn
0x18000bbe1  mov     ebx, eax
0x18000bbe3  mov     eax, 0FFFFFFFFh
0x18000bbe8  add     rbx, rbx
0x18000bbeb  cmp     rbx, rax
0x18000bbee  ja      short loc_18000BC2C
0x18000bbf0  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000bbf7  mov     ecx, ebx
0x18000bbf9  mov     rax, [rax+28h]
0x18000bbfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc02  mov     [rsi], rax
0x18000bc05  test    rax, rax
0x18000bc08  jz      loc_18000BC97
0x18000bc0e  mov     r8d, ebx; Size
0x18000bc11  mov     rdx, rdi; Src
0x18000bc14  mov     rcx, rax; void *
0x18000bc17  call    memcpy_0
0x18000bc1c  mov     eax, r15d
0x18000bc1f  add     rsp, 58h
0x18000bc23  pop     r15
0x18000bc25  pop     r14
0x18000bc27  pop     rdi
0x18000bc28  pop     rsi
0x18000bc29  pop     rbp
0x18000bc2a  pop     rbx
0x18000bc2b  retn
0x18000bc2c  lea     rdi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000bc33  mov     ebx, 0C0000095h
0x18000bc38  mov     rcx, rdi; char *
0x18000bc3b  mov     r10, r15
0x18000bc3e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000bc43  mov     edx, 2Ah ; '*'; int
0x18000bc48  lea     rcx, aRtldwordmult; "RtlDWordMult"
0x18000bc4f  jmp     loc_18000BB12
0x18000bc54  call    ?DuplicateStringPreRS2@@YAJPEBGHPEAPEAG@Z; DuplicateStringPreRS2(ushort const *,int,ushort * *)
0x18000bc59  mov     ebx, eax
0x18000bc5b  test    eax, eax
0x18000bc5d  jz      loc_18000BB74
0x18000bc63  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000bc6a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000bc6f  mov     r9, rax
0x18000bc72  lea     rbp, Class
0x18000bc79  mov     [rsp+88h+lpVersionInformation], rbp
0x18000bc7e  lea     rax, aDuplicatestrin_0; "DuplicateStringPreRS2"
0x18000bc85  mov     qword ptr [rsp+88h+cchDest], rax
0x18000bc8a  mov     dword ptr [rsp+88h+lpDestStr], 54h ; 'T'
0x18000bc92  jmp     loc_18000BB63
0x18000bc97  lea     rdi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000bc9e  mov     ebx, 0C0000017h
0x18000bca3  mov     rcx, rdi; char *
0x18000bca6  mov     r10, r15
0x18000bca9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000bcae  mov     edx, 30h ; '0'
0x18000bcb3  lea     rcx, aAllocatelsahea_3; "AllocateLsaHeap"
0x18000bcba  jmp     loc_18000BB12
0x18000bcbf  call    cs:__imp_GetLastError
0x18000bcc5  test    eax, eax
0x18000bcc7  jg      short loc_18000BCD3
0x18000bcc9  call    cs:__imp_GetLastError
0x18000bccf  mov     ebx, eax
0x18000bcd1  jmp     short loc_18000BCE2
0x18000bcd3  call    cs:__imp_GetLastError
0x18000bcd9  movzx   ebx, ax
0x18000bcdc  or      ebx, 0C0070000h
0x18000bce2  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000bce9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000bcee  mov     [rsp+88h+lpVersionInformation], rbp
0x18000bcf3  mov     r9, rax
0x18000bcf6  lea     rax, aLcmapstringex; "LCMapStringEx"
0x18000bcfd  mov     qword ptr [rsp+88h+cchDest], rax
0x18000bd02  mov     dword ptr [rsp+88h+lpDestStr], 76h ; 'v'
0x18000bd0a  jmp     loc_18000BB63
0x18000bd0f  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000bd16  mov     ebx, 0C0000017h
0x18000bd1b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000bd20  mov     [rsp+88h+lpVersionInformation], rbp
0x18000bd25  lea     rcx, aAllocatelsahea_3; "AllocateLsaHeap"
0x18000bd2c  mov     qword ptr [rsp+88h+cchDest], rcx
0x18000bd31  mov     dword ptr [rsp+88h+lpDestStr], 82h
0x18000bd39  jmp     loc_18000BA89
0x18000bd3e  call    cs:__imp_GetLastError
0x18000bd44  test    eax, eax
0x18000bd46  jg      short loc_18000BD52
0x18000bd48  call    cs:__imp_GetLastError
0x18000bd4e  mov     ebx, eax
0x18000bd50  jmp     short loc_18000BD61
0x18000bd52  call    cs:__imp_GetLastError
0x18000bd58  movzx   ebx, ax
0x18000bd5b  or      ebx, 0C0070000h
0x18000bd61  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000bd68  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000bd6d  mov     [rsp+88h+lpVersionInformation], rbp
0x18000bd72  mov     r9, rax
0x18000bd75  lea     rax, aLcmapstringex; "LCMapStringEx"
0x18000bd7c  mov     qword ptr [rsp+88h+cchDest], rax
0x18000bd81  mov     dword ptr [rsp+88h+lpDestStr], 91h
0x18000bd89  jmp     loc_18000BB63
```
