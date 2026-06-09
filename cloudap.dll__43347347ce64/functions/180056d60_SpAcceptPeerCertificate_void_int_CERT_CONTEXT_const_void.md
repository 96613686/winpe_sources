# SpAcceptPeerCertificate(void *,int,_CERT_CONTEXT const *,void * *)

- ea: `0x180056d60`
- end: `0x18005719e`
- name: `?SpAcceptPeerCertificate@@YAJPEAXHPEBU_CERT_CONTEXT@@PEAPEAX@Z`
- size: `1086`
- prototype: `__int64 __fastcall(void *, int, const struct _CERT_CONTEXT *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18000ce50`
- `0x18000e900`
- `0x18000ee60`
- `0x18002c3f0`
- `0x180042410`
- `0x180056d60`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056f94`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180056f76`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180056f76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005715e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005715e`

## string_xrefs

- `0x180056ddf`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180056e37`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180056eb0`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180056f00`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180056fa3`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005701c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005707c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800570d5`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180056fbe`: `ConvertSidToStringSid`
- `0x180056f1b`: `MakeTokenInformationV2`

## pseudocode

```c
__int64 __fastcall SpAcceptPeerCertificate(void *a1, unsigned int a2, const struct _CERT_CONTEXT *a3, void **a4)
{
  struct _ApPluginPkg *v7; // r14
  _QWORD *v8; // rdi
  unsigned __int16 *v9; // rsi
  unsigned int TokenInformationV2; // ebx
  const char *v11; // r9
  const char *v12; // rax
  __int64 (__fastcall *v13)(_QWORD, _QWORD, const struct _CERT_CONTEXT *, struct _APPLUGIN_USER_INFO **); // rax
  const char *v14; // r9
  const char *v15; // r9
  LPWSTR v16; // rbx
  const char *v17; // r9
  __int64 v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // r13d
  unsigned __int16 *v21; // rax
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  __int64 v26; // [rsp+20h] [rbp-49h]
  struct _LSA_TOKEN_INFORMATION_V1 *v27; // [rsp+40h] [rbp-29h] BYREF
  struct _APPLUGIN_USER_INFO *v28; // [rsp+48h] [rbp-21h] BYREF
  struct _ApPluginPkg *v29; // [rsp+50h] [rbp-19h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-11h] BYREF
  struct _GUID v31; // [rsp+60h] [rbp-9h] BYREF

  v29 = 0;
  v27 = 0;
  v28 = 0;
  StringSid = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v31 = 0;
  if ( !a1 || !a4 )
  {
    TokenInformationV2 = -1073741811;
    goto LABEL_35;
  }
  *a4 = 0;
  TokenInformationV2 = (*((__int64 (__fastcall **)(void *, struct _GUID *))g_pLsaIdProvHostFunctionTable + 10))(
                         a1,
                         &v31);
  if ( TokenInformationV2 )
  {
    v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", TokenInformationV2, v11, 8934, "GetProvInfo", &Class);
    goto LABEL_35;
  }
  TokenInformationV2 = RefPackage(&v31, &v29);
  if ( TokenInformationV2 )
  {
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", TokenInformationV2, v12, 8937, "RefPackage", &Class);
    v7 = v29;
    goto LABEL_35;
  }
  v7 = v29;
  v13 = (__int64 (__fastcall *)(_QWORD, _QWORD, const struct _CERT_CONTEXT *, struct _APPLUGIN_USER_INFO **))*((_QWORD *)v29 + 28);
  if ( !v13 )
  {
    TokenInformationV2 = -1073741822;
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225474LL, v24, 8951, "Not Implemented", &Class);
    goto LABEL_35;
  }
  TokenInformationV2 = v13(*((_QWORD *)v29 + 1), a2, a3, &v28);
  if ( TokenInformationV2 )
  {
    v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", TokenInformationV2, v14, 8946, "AcceptPeerCertificate", &Class);
    goto LABEL_35;
  }
  if ( a2 )
  {
LABEL_32:
    TokenInformationV2 = 0;
    v8 = 0;
    v9 = 0;
    goto LABEL_35;
  }
  TokenInformationV2 = MakeTokenInformationV2(v28, &v27);
  if ( TokenInformationV2 )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", TokenInformationV2, v15, 8960, "MakeTokenInformationV2", &Class);
    goto LABEL_35;
  }
  v8 = (_QWORD *)((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(24);
  if ( !v8 )
  {
    TokenInformationV2 = -1073741670;
    goto LABEL_35;
  }
  v16 = (LPWSTR)*((_QWORD *)v28 + 8);
  if ( v16 && *v16 )
  {
LABEL_24:
    v18 = -1;
    v19 = -1;
    do
      ++v19;
    while ( v16[v19] );
    do
      ++v18;
    while ( *((_WORD *)v7 + v18 + 12) );
    v20 = 2 * (v19 + v18) + 4;
    v21 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v20);
    v9 = v21;
    if ( !v21 )
    {
      TokenInformationV2 = -1073741801;
      v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v22, 8997, "AllocateLsaHeap", &Class);
      goto LABEL_35;
    }
    TokenInformationV2 = RtlStringCchPrintfW(v21, (unsigned __int64)v20 >> 1, L"%ws\\%ws", (char *)v7 + 24, v16);
    if ( TokenInformationV2 )
    {
      v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v26) = 9001;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", TokenInformationV2, v23, v26, "RtlStringCchPrintfW", &Class);
      goto LABEL_35;
    }
    v8[1] = v27;
    v8[2] = v9;
    *(_DWORD *)v8 = 2;
    *a4 = v8;
    v27 = 0;
    goto LABEL_32;
  }
  if ( ConvertSidToStringSidW(*((PSID *)v28 + 2), &StringSid) )
  {
    v16 = StringSid;
    goto LABEL_24;
  }
  if ( (int)GetLastError() > 0 )
    TokenInformationV2 = (unsigned __int16)GetLastError() | 0xC0070000;
  else
    TokenInformationV2 = GetLastError();
  v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", TokenInformationV2, v17, 8979, "ConvertSidToStringSid", &Class);
LABEL_35:
  DerefPackage(v7);
  if ( v27 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v8 )
    ((void (__fastcall *)(_QWORD *))g_pLsaFunctionTable->FreeLsaHeap)(v8);
  FreeUserInfo(v28);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v9 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v9);
  return TokenInformationV2;
}

```

## disassembly

```asm
0x180056d60  push    rbp
0x180056d62  push    rbx
0x180056d63  push    rsi
0x180056d64  push    rdi
0x180056d65  push    r12
0x180056d67  push    r13
0x180056d69  push    r14
0x180056d6b  push    r15
0x180056d6d  lea     rbp, [rsp-1Fh]
0x180056d72  sub     rsp, 88h
0x180056d79  mov     rax, cs:__security_cookie
0x180056d80  xor     rax, rsp
0x180056d83  mov     [rbp+57h+var_50], rax
0x180056d87  xor     eax, eax
0x180056d89  xorps   xmm0, xmm0
0x180056d8c  mov     [rbp+57h+var_70], rax
0x180056d90  mov     r12, r9
0x180056d93  mov     [rbp+57h+var_80], rax
0x180056d97  mov     r13, r8
0x180056d9a  mov     [rbp+57h+var_78], rax
0x180056d9e  mov     r15d, edx
0x180056da1  mov     [rbp+57h+StringSid], rax
0x180056da5  mov     r14d, eax
0x180056da8  mov     edi, eax
0x180056daa  mov     esi, eax
0x180056dac  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180056db0  test    rcx, rcx
0x180056db3  jz      loc_18005710E
0x180056db9  test    r9, r9
0x180056dbc  jz      loc_18005710E
0x180056dc2  mov     [r9], rax
0x180056dc5  lea     rdx, [rbp+57h+var_60]
0x180056dc9  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180056dd0  mov     rax, [rax+50h]
0x180056dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056dd9  mov     ebx, eax
0x180056ddb  test    eax, eax
0x180056ddd  jz      short loc_180056E24
0x180056ddf  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056de6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180056deb  mov     r9, rax
0x180056dee  lea     rax, Class
0x180056df5  mov     [rsp+0C0h+var_90], rax
0x180056dfa  lea     rax, aGetprovinfo; "GetProvInfo"
0x180056e01  mov     [rsp+0C0h+var_98], rax
0x180056e06  mov     dword ptr [rsp+0C0h+var_A0], 22E6h
0x180056e0e  mov     r8d, ebx
0x180056e11  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180056e18  xor     ecx, ecx
0x180056e1a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180056e1f  jmp     loc_180057113
0x180056e24  lea     rdx, [rbp+57h+var_70]; struct _ApPluginPkg **
0x180056e28  lea     rcx, [rbp+57h+var_60]; struct _GUID *
0x180056e2c  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x180056e31  mov     ebx, eax
0x180056e33  test    eax, eax
0x180056e35  jz      short loc_180056E80
0x180056e37  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056e3e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180056e43  mov     r9, rax
0x180056e46  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180056e4d  lea     rax, Class
0x180056e54  mov     r8d, ebx
0x180056e57  mov     [rsp+0C0h+var_90], rax
0x180056e5c  xor     ecx, ecx
0x180056e5e  lea     rax, aRefpackage; "RefPackage"
0x180056e65  mov     [rsp+0C0h+var_98], rax
0x180056e6a  mov     dword ptr [rsp+0C0h+var_A0], 22E9h
0x180056e72  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180056e77  mov     r14, [rbp+57h+var_70]
0x180056e7b  jmp     loc_180057113
0x180056e80  mov     r14, [rbp+57h+var_70]
0x180056e84  mov     rax, [r14+0E0h]
0x180056e8b  test    rax, rax
0x180056e8e  jz      loc_1800570D5
0x180056e94  mov     rcx, [r14+8]
0x180056e98  lea     r9, [rbp+57h+var_78]
0x180056e9c  mov     r8, r13
0x180056e9f  mov     edx, r15d
0x180056ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ea7  xor     r13d, r13d
0x180056eaa  mov     ebx, eax
0x180056eac  test    eax, eax
0x180056eae  jz      short loc_180056EE4
0x180056eb0  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056eb7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180056ebc  mov     r9, rax
0x180056ebf  lea     rax, Class
0x180056ec6  mov     [rsp+0C0h+var_90], rax
0x180056ecb  lea     rax, aAcceptpeercert; "AcceptPeerCertificate"
0x180056ed2  mov     [rsp+0C0h+var_98], rax
0x180056ed7  mov     dword ptr [rsp+0C0h+var_A0], 22F2h
0x180056edf  jmp     loc_180056E0E
0x180056ee4  test    r15d, r15d
0x180056ee7  jnz     loc_1800570CA
0x180056eed  mov     rcx, [rbp+57h+var_78]; struct _APPLUGIN_USER_INFO *
0x180056ef1  lea     rdx, [rbp+57h+var_80]; struct _LSA_TOKEN_INFORMATION_V1 **
0x180056ef5  call    ?MakeTokenInformationV2@@YAJPEAU_APPLUGIN_USER_INFO@@PEAPEAU_LSA_TOKEN_INFORMATION_V1@@@Z; MakeTokenInformationV2(_APPLUGIN_USER_INFO *,_LSA_TOKEN_INFORMATION_V1 * *)
0x180056efa  mov     ebx, eax
0x180056efc  test    eax, eax
0x180056efe  jz      short loc_180056F34
0x180056f00  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056f07  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180056f0c  mov     r9, rax
0x180056f0f  lea     rax, Class
0x180056f16  mov     [rsp+0C0h+var_90], rax
0x180056f1b  lea     rax, aMaketokeninfor; "MakeTokenInformationV2"
0x180056f22  mov     [rsp+0C0h+var_98], rax
0x180056f27  mov     dword ptr [rsp+0C0h+var_A0], 2300h
0x180056f2f  jmp     loc_180056E0E
0x180056f34  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180056f3b  mov     ecx, 18h
0x180056f40  mov     rax, [rax+28h]
0x180056f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f49  mov     rdi, rax
0x180056f4c  test    rax, rax
0x180056f4f  jnz     short loc_180056F5B
0x180056f51  mov     ebx, 0C000009Ah
0x180056f56  jmp     loc_180057113
0x180056f5b  mov     rcx, [rbp+57h+var_78]
0x180056f5f  mov     rbx, [rcx+40h]
0x180056f63  test    rbx, rbx
0x180056f66  jz      short loc_180056F6E
0x180056f68  cmp     r13w, [rbx]
0x180056f6c  jnz     short loc_180056FDB
0x180056f6e  mov     rcx, [rcx+10h]; Sid
0x180056f72  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180056f76  call    cs:__imp_ConvertSidToStringSidW
0x180056f7c  test    eax, eax
0x180056f7e  jnz     short loc_180056FD7
0x180056f80  call    cs:__imp_GetLastError
0x180056f86  test    eax, eax
0x180056f88  jg      short loc_180056F94
0x180056f8a  call    cs:__imp_GetLastError
0x180056f90  mov     ebx, eax
0x180056f92  jmp     short loc_180056FA3
0x180056f94  call    cs:__imp_GetLastError
0x180056f9a  movzx   ebx, ax
0x180056f9d  or      ebx, 0C0070000h
0x180056fa3  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180056faa  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180056faf  mov     r9, rax
0x180056fb2  lea     rax, Class
0x180056fb9  mov     [rsp+0C0h+var_90], rax
0x180056fbe  lea     rax, aConvertsidtost; "ConvertSidToStringSid"
0x180056fc5  mov     [rsp+0C0h+var_98], rax
0x180056fca  mov     dword ptr [rsp+0C0h+var_A0], 2313h
0x180056fd2  jmp     loc_180056E0E
0x180056fd7  mov     rbx, [rbp+57h+StringSid]
0x180056fdb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180056fdf  mov     rcx, rax
0x180056fe2  inc     rcx
0x180056fe5  cmp     [rbx+rcx*2], r13w
0x180056fea  jnz     short loc_180056FE2
0x180056fec  inc     rax
0x180056fef  cmp     [r14+rax*2+18h], r13w
0x180056ff5  jnz     short loc_180056FEC
0x180056ff7  add     eax, ecx
0x180056ff9  lea     r13d, ds:4[rax*2]
0x180057001  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180057008  mov     ecx, r13d
0x18005700b  mov     rax, [rax+28h]
0x18005700f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057014  mov     rsi, rax
0x180057017  test    rax, rax
0x18005701a  jnz     short loc_180057055
0x18005701c  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057023  mov     ebx, 0C0000017h
0x180057028  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005702d  mov     r9, rax
0x180057030  lea     rax, Class
0x180057037  mov     [rsp+0C0h+var_90], rax
0x18005703c  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180057043  mov     [rsp+0C0h+var_98], rax
0x180057048  mov     dword ptr [rsp+0C0h+var_A0], 2325h
0x180057050  jmp     loc_180056E0E
0x180057055  mov     edx, r13d
0x180057058  lea     r9, [r14+18h]
0x18005705c  shr     rdx, 1; unsigned __int64
0x18005705f  lea     r8, aWsWs_1; "%ws\\%ws"
0x180057066  mov     rcx, rsi; unsigned __int16 *
0x180057069  mov     [rsp+0C0h+var_A0], rbx
0x18005706e  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057073  xor     r13d, r13d
0x180057076  mov     ebx, eax
0x180057078  test    eax, eax
0x18005707a  jz      short loc_1800570B0
0x18005707c  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180057083  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180057088  mov     r9, rax
0x18005708b  lea     rax, Class
0x180057092  mov     [rsp+0C0h+var_90], rax
0x180057097  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18005709e  mov     [rsp+0C0h+var_98], rax
0x1800570a3  mov     dword ptr [rsp+0C0h+var_A0], 2329h
0x1800570ab  jmp     loc_180056E0E
0x1800570b0  mov     rax, [rbp+57h+var_80]
0x1800570b4  mov     [rdi+8], rax
0x1800570b8  mov     [rdi+10h], rsi
0x1800570bc  mov     dword ptr [rdi], 2
0x1800570c2  mov     [r12], rdi
0x1800570c6  mov     [rbp+57h+var_80], r13
0x1800570ca  mov     ebx, r13d
0x1800570cd  mov     rdi, r13
0x1800570d0  mov     rsi, r13
0x1800570d3  jmp     short loc_180057113
0x1800570d5  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800570dc  mov     ebx, 0C0000002h
0x1800570e1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800570e6  mov     r9, rax
0x1800570e9  lea     rax, Class
0x1800570f0  mov     [rsp+0C0h+var_90], rax
0x1800570f5  lea     rax, aNotImplemented; "Not Implemented"
0x1800570fc  mov     [rsp+0C0h+var_98], rax
0x180057101  mov     dword ptr [rsp+0C0h+var_A0], 22F7h
0x180057109  jmp     loc_180056E0E
0x18005710e  mov     ebx, 0C000000Dh
0x180057113  mov     rcx, r14; struct _ApPluginPkg *
0x180057116  call    ?DerefPackage@@YAXPEAU_ApPluginPkg@@@Z; DerefPackage(_ApPluginPkg *)
0x18005711b  mov     rcx, [rbp+57h+var_80]
0x18005711f  test    rcx, rcx
0x180057122  jz      short loc_180057134
0x180057124  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005712b  mov     rax, [rax+30h]
0x18005712f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057134  test    rdi, rdi
0x180057137  jz      short loc_18005714C
0x180057139  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180057140  mov     rcx, rdi
0x180057143  mov     rax, [rax+30h]
0x180057147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005714c  mov     rcx, [rbp+57h+var_78]; struct _APPLUGIN_USER_INFO *
0x180057150  call    ?FreeUserInfo@@YAXPEAU_APPLUGIN_USER_INFO@@@Z; FreeUserInfo(_APPLUGIN_USER_INFO *)
0x180057155  mov     rcx, [rbp+57h+StringSid]; hMem
0x180057159  test    rcx, rcx
0x18005715c  jz      short loc_180057164
0x18005715e  call    cs:__imp_LocalFree
0x180057164  test    rsi, rsi
0x180057167  jz      short loc_18005717C
0x180057169  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180057170  mov     rcx, rsi
0x180057173  mov     rax, [rax+30h]
0x180057177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005717c  mov     eax, ebx
0x18005717e  mov     rcx, [rbp+57h+var_50]
0x180057182  xor     rcx, rsp; StackCookie
0x180057185  call    __security_check_cookie
0x18005718a  add     rsp, 88h
0x180057191  pop     r15
0x180057193  pop     r14
0x180057195  pop     r13
0x180057197  pop     r12
0x180057199  pop     rdi
0x18005719a  pop     rsi
0x18005719b  pop     rbx
0x18005719c  pop     rbp
0x18005719d  retn
```
