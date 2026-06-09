# GetUpnFromScardCert(_SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS_DATA * const,ushort * *,ushort * *)

- ea: `0x180054ff4`
- end: `0x1800554d0`
- name: `?GetUpnFromScardCert@@YAJQEAU_SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS_DATA@@PEAPEAG1@Z`
- size: `1244`
- prototype: `__int64 __fastcall(struct _SEC_WINNT_AUTH_DATA_TYPE_SMARTCARD_CONTEXTS_DATA *const, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029650`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000b9b0`
- `0x18002b260`
- `0x180054ff4`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055349`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055349`
- `CRYPT32!CertGetNameStringW` at `0x18005505e`
- `CRYPT32!CertGetNameStringW` at `0x180055136`
- `CRYPT32!CertGetNameStringW` at `0x180055256`
- `CRYPT32!CertGetNameStringW` at `0x180055332`
- `CRYPT32!CertGetNameStringW` at `0x18005505e`
- `CRYPT32!CertGetNameStringW` at `0x180055136`
- `CRYPT32!CertGetNameStringW` at `0x180055256`
- `CRYPT32!CertGetNameStringW` at `0x180055332`
- `CRYPT32!CertCompareCertificateName` at `0x18005522d`
- `CRYPT32!CertCompareCertificateName` at `0x18005522d`

## string_xrefs

- `0x180055085`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800550eb`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005515c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800551b8`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005527d`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800552e3`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055397`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800553f4`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`

## pseudocode

```c
__int64 __fastcall GetUpnFromScardCert(PCCERT_CONTEXT *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  const unsigned __int16 *v5; // r15
  const wchar_t *v6; // rsi
  unsigned __int16 *v7; // rdi
  const CERT_CONTEXT *v8; // rcx
  DWORD NameStringW; // eax
  DWORD cchNameString; // r12d
  unsigned int v11; // ebx
  const char *v12; // r9
  WCHAR *v13; // rax
  const char *v14; // r9
  __int64 v15; // r8
  const char *v16; // rax
  const char *v17; // rax
  DWORD v18; // eax
  DWORD v19; // r12d
  const char *v20; // r9
  WCHAR *v21; // rax
  const char *v22; // r9
  __int64 v23; // r8
  __int64 v24; // rcx
  const wchar_t *v25; // r14
  const char *v26; // rax
  const char *v27; // rax
  unsigned __int16 *v28; // rax
  unsigned __int16 **v29; // rcx
  LPWSTR pszNameString; // [rsp+20h] [rbp-38h]
  LPWSTR pszNameStringa; // [rsp+20h] [rbp-38h]
  LPWSTR pszNameStringb; // [rsp+20h] [rbp-38h]
  LPWSTR pszNameStringc; // [rsp+20h] [rbp-38h]
  unsigned __int16 *v35[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v36; // [rsp+A0h] [rbp+48h] BYREF
  unsigned __int16 **v37; // [rsp+A8h] [rbp+50h]
  unsigned int v38; // [rsp+B0h] [rbp+58h] BYREF
  unsigned __int16 *v39; // [rsp+B8h] [rbp+60h] BYREF

  v37 = a2;
  v36 = 0;
  v38 = 0;
  v5 = 0;
  v35[0] = 0;
  v6 = 0;
  v39 = 0;
  v7 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( !a1 )
    goto LABEL_33;
  v8 = *a1;
  if ( !v8 )
    goto LABEL_33;
  NameStringW = CertGetNameStringW(v8, 8u, 0, 0, 0, 0);
  cchNameString = NameStringW;
  if ( NameStringW > 1 )
  {
    v11 = RtlULongLongToULong(2LL * NameStringW, &v36);
    if ( v11 )
    {
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(pszNameString) = 9920;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v12, pszNameString, "RtlDWordMult", &Class);
      return v11;
    }
    v13 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v36);
    v5 = v13;
    if ( !v13 )
    {
      v11 = -1073741801;
      v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(pszNameString) = 9926;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v14, pszNameString, "AllocateLsaHeap", &Class);
      return v11;
    }
    if ( CertGetNameStringW(*a1, 8u, 0, 0, v13, cchNameString) > 1 )
    {
      v11 = DuplicateString(v5, 0, v35);
      if ( v11 )
      {
        v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(pszNameStringa) = 9942;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v16, pszNameStringa, "DuplicateString", &Class);
LABEL_36:
        ((void (__fastcall *)(const unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v5);
        goto LABEL_37;
      }
      v11 = DuplicateString(v5, 1, &v39);
      if ( v11 )
      {
        v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(pszNameStringa) = 9948;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v17, pszNameStringa, "DuplicateString", &Class);
        v7 = v39;
        goto LABEL_36;
      }
      v7 = v39;
      if ( v39 )
      {
        if ( *v39 )
          goto LABEL_33;
      }
    }
  }
  if ( !CertCompareCertificateName(1u, &(*a1)->pCertInfo->Issuer, &(*a1)->pCertInfo->Subject) )
    goto LABEL_33;
  v18 = CertGetNameStringW(*a1, 3u, 0, "2.5.4.3", 0, 0);
  v19 = v18;
  if ( v18 <= 1 )
    goto LABEL_33;
  v11 = RtlULongLongToULong(2LL * v18, &v38);
  if ( v11 )
  {
    v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(pszNameStringb) = 9975;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v20, pszNameStringb, "RtlDWordMult", &Class);
    goto LABEL_35;
  }
  v21 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v38);
  v6 = v21;
  if ( !v21 )
  {
    v11 = -1073741801;
    v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(pszNameStringb) = 9981;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v23, v22, pszNameStringb, "AllocateLsaHeap", &Class);
    goto LABEL_35;
  }
  if ( CertGetNameStringW(*a1, 3u, 0, "2.5.4.3", v21, v19) <= 1 || !wcschr(v6, 0x40u) )
    goto LABEL_33;
  v24 = -1;
  do
    ++v24;
  while ( v6[v24] );
  do
    LODWORD(v24) = v24 - 1;
  while ( (int)v24 >= 0 && v6[(unsigned int)v24] != 47 );
  v25 = &v6[(int)v24];
  v11 = DuplicateString(v25 + 1, 0, v35);
  if ( !v11 )
  {
    v11 = DuplicateString(v25 + 1, 1, &v39);
    if ( v11 )
    {
      v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(pszNameStringc) = 10017;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v27, pszNameStringc, "DuplicateString", &Class);
      v7 = v39;
      goto LABEL_34;
    }
    v7 = v39;
LABEL_33:
    v28 = v35[0];
    v29 = v37;
    *a3 = v7;
    v7 = 0;
    v35[0] = 0;
    *v29 = v28;
    v11 = 0;
    if ( !v6 )
      goto LABEL_35;
    goto LABEL_34;
  }
  v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  LODWORD(pszNameStringc) = 10011;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v26, pszNameStringc, "DuplicateString", &Class);
LABEL_34:
  ((void (__fastcall *)(const wchar_t *))g_pLsaFunctionTable->FreeLsaHeap)(v6);
LABEL_35:
  if ( v5 )
    goto LABEL_36;
LABEL_37:
  if ( v35[0] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v7 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v7);
  return v11;
}

```

## disassembly

```asm
0x180054ff4  mov     [rsp-40h+arg_8], rdx
0x180054ff9  push    rbp
0x180054ffa  push    rbx
0x180054ffb  push    rsi
0x180054ffc  push    rdi
0x180054ffd  push    r12
0x180054fff  push    r13
0x180055001  push    r14
0x180055003  push    r15
0x180055005  mov     rbp, rsp
0x180055008  sub     rsp, 58h
0x18005500c  xor     r12d, r12d
0x18005500f  mov     r13, r8
0x180055012  mov     [rbp+arg_0], r12d
0x180055016  mov     r14, rcx
0x180055019  mov     [rbp+arg_10], r12d
0x18005501d  mov     r15d, r12d
0x180055020  mov     [rbp+var_18], r12
0x180055024  mov     esi, r12d
0x180055027  mov     [rbp+arg_18], r12
0x18005502b  mov     edi, r12d
0x18005502e  mov     [rdx], r12
0x180055031  mov     [r8], r12
0x180055034  test    rcx, rcx
0x180055037  jz      loc_180055443
0x18005503d  mov     rcx, [rcx]; pCertContext
0x180055040  test    rcx, rcx
0x180055043  jz      loc_180055443
0x180055049  mov     [rsp+58h+cchNameString], r12d; cchNameString
0x18005504e  lea     edx, [r12+8]; dwType
0x180055053  xor     r9d, r9d; pvTypePara
0x180055056  mov     [rsp+58h+pszNameString], r12; pszNameString
0x18005505b  xor     r8d, r8d; dwFlags
0x18005505e  call    cs:__imp_CertGetNameStringW
0x180055064  mov     r12d, eax
0x180055067  cmp     eax, 1
0x18005506a  jbe     loc_180055216
0x180055070  mov     ecx, r12d
0x180055073  lea     rdx, [rbp+arg_0]; unsigned int *
0x180055077  add     rcx, rcx; unsigned __int64
0x18005507a  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x18005507f  mov     ebx, eax
0x180055081  test    eax, eax
0x180055083  jz      short loc_1800550CA
0x180055085  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005508c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055091  mov     r9, rax
0x180055094  mov     r8d, ebx
0x180055097  lea     rax, Class
0x18005509e  mov     [rsp+58h+var_28], rax
0x1800550a3  lea     rax, aRtldwordmult; "RtlDWordMult"
0x1800550aa  mov     qword ptr [rsp+58h+cchNameString], rax
0x1800550af  mov     dword ptr [rsp+58h+pszNameString], 26C0h
0x1800550b7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800550be  xor     ecx, ecx
0x1800550c0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800550c5  jmp     loc_1800554BD
0x1800550ca  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800550d1  mov     ecx, [rbp+arg_0]
0x1800550d4  mov     rax, [rax+28h]
0x1800550d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550dd  mov     r15, rax
0x1800550e0  test    rax, rax
0x1800550e3  jnz     short loc_18005511F
0x1800550e5  mov     r8d, 0C0000017h
0x1800550eb  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800550f2  mov     ebx, r8d
0x1800550f5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800550fa  mov     r9, rax
0x1800550fd  lea     rax, Class
0x180055104  mov     [rsp+58h+var_28], rax
0x180055109  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180055110  mov     qword ptr [rsp+58h+cchNameString], rax
0x180055115  mov     dword ptr [rsp+58h+pszNameString], 26C6h
0x18005511d  jmp     short loc_1800550B7
0x18005511f  mov     rcx, [r14]; pCertContext
0x180055122  xor     r9d, r9d; pvTypePara
0x180055125  mov     [rsp+58h+cchNameString], r12d; cchNameString
0x18005512a  xor     r8d, r8d; dwFlags
0x18005512d  mov     [rsp+58h+pszNameString], r15; pszNameString
0x180055132  lea     edx, [r9+8]; dwType
0x180055136  call    cs:__imp_CertGetNameStringW
0x18005513c  cmp     eax, 1
0x18005513f  jbe     loc_180055216
0x180055145  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180055149  xor     edx, edx; int
0x18005514b  mov     rcx, r15; Src
0x18005514e  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x180055153  xor     r12d, r12d
0x180055156  mov     ebx, eax
0x180055158  test    eax, eax
0x18005515a  jz      short loc_1800551A1
0x18005515c  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055163  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055168  mov     r9, rax
0x18005516b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180055172  lea     rax, Class
0x180055179  mov     r8d, ebx
0x18005517c  mov     [rsp+58h+var_28], rax
0x180055181  xor     ecx, ecx
0x180055183  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x18005518a  mov     qword ptr [rsp+58h+cchNameString], rax
0x18005518f  mov     dword ptr [rsp+58h+pszNameString], 26D6h
0x180055197  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005519c  jmp     loc_180055479
0x1800551a1  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x1800551a5  mov     edx, 1; int
0x1800551aa  mov     rcx, r15; Src
0x1800551ad  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x1800551b2  mov     ebx, eax
0x1800551b4  test    eax, eax
0x1800551b6  jz      short loc_180055201
0x1800551b8  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800551bf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800551c4  mov     r9, rax
0x1800551c7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800551ce  lea     rax, Class
0x1800551d5  mov     r8d, ebx
0x1800551d8  mov     [rsp+58h+var_28], rax
0x1800551dd  xor     ecx, ecx
0x1800551df  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x1800551e6  mov     qword ptr [rsp+58h+cchNameString], rax
0x1800551eb  mov     dword ptr [rsp+58h+pszNameString], 26DCh
0x1800551f3  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800551f8  mov     rdi, [rbp+arg_18]
0x1800551fc  jmp     loc_180055479
0x180055201  mov     rdi, [rbp+arg_18]
0x180055205  test    rdi, rdi
0x180055208  jz      short loc_180055219
0x18005520a  cmp     r12w, [rdi]
0x18005520e  jnz     loc_180055443
0x180055214  jmp     short loc_180055219
0x180055216  xor     r12d, r12d
0x180055219  mov     rax, [r14]
0x18005521c  mov     ecx, 1; dwCertEncodingType
0x180055221  mov     rdx, [rax+18h]
0x180055225  lea     r8, [rdx+50h]; pCertName2
0x180055229  add     rdx, 30h ; '0'; pCertName1
0x18005522d  call    cs:__imp_CertCompareCertificateName
0x180055233  test    eax, eax
0x180055235  jz      loc_180055443
0x18005523b  mov     rcx, [r14]; pCertContext
0x18005523e  lea     r9, a2543; "2.5.4.3"
0x180055245  xor     r8d, r8d; dwFlags
0x180055248  mov     [rsp+58h+cchNameString], r12d; cchNameString
0x18005524d  mov     [rsp+58h+pszNameString], r12; pszNameString
0x180055252  lea     edx, [r8+3]; dwType
0x180055256  call    cs:__imp_CertGetNameStringW
0x18005525c  mov     r12d, eax
0x18005525f  cmp     eax, 1
0x180055262  jbe     loc_180055440
0x180055268  mov     ecx, r12d
0x18005526b  lea     rdx, [rbp+arg_10]; unsigned int *
0x18005526f  add     rcx, rcx; unsigned __int64
0x180055272  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x180055277  mov     ebx, eax
0x180055279  test    eax, eax
0x18005527b  jz      short loc_1800552C2
0x18005527d  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055284  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055289  mov     r9, rax
0x18005528c  mov     r8d, ebx
0x18005528f  lea     rax, Class
0x180055296  mov     [rsp+58h+var_28], rax
0x18005529b  lea     rax, aRtldwordmult; "RtlDWordMult"
0x1800552a2  mov     qword ptr [rsp+58h+cchNameString], rax
0x1800552a7  mov     dword ptr [rsp+58h+pszNameString], 26F7h
0x1800552af  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800552b6  xor     ecx, ecx
0x1800552b8  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800552bd  jmp     loc_180055474
0x1800552c2  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800552c9  mov     ecx, [rbp+arg_10]
0x1800552cc  mov     rax, [rax+28h]
0x1800552d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552d5  mov     rsi, rax
0x1800552d8  test    rax, rax
0x1800552db  jnz     short loc_180055317
0x1800552dd  mov     r8d, 0C0000017h
0x1800552e3  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800552ea  mov     ebx, r8d
0x1800552ed  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800552f2  mov     r9, rax
0x1800552f5  lea     rax, Class
0x1800552fc  mov     [rsp+58h+var_28], rax
0x180055301  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180055308  mov     qword ptr [rsp+58h+cchNameString], rax
0x18005530d  mov     dword ptr [rsp+58h+pszNameString], 26FDh
0x180055315  jmp     short loc_1800552AF
0x180055317  mov     rcx, [r14]; pCertContext
0x18005531a  lea     r9, a2543; "2.5.4.3"
0x180055321  xor     r8d, r8d; dwFlags
0x180055324  mov     [rsp+58h+cchNameString], r12d; cchNameString
0x180055329  mov     [rsp+58h+pszNameString], rsi; pszNameString
0x18005532e  lea     edx, [r8+3]; dwType
0x180055332  call    cs:__imp_CertGetNameStringW
0x180055338  cmp     eax, 1
0x18005533b  jbe     loc_180055440
0x180055341  mov     edx, 40h ; '@'; Ch
0x180055346  mov     rcx, rsi; Str
0x180055349  call    cs:__imp_wcschr
0x18005534f  xor     r12d, r12d
0x180055352  test    rax, rax
0x180055355  jz      loc_180055443
0x18005535b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005535f  inc     rcx
0x180055362  cmp     [rsi+rcx*2], r12w
0x180055367  jnz     short loc_18005535F
0x180055369  jmp     short loc_180055376
0x18005536b  mov     edx, 2Fh ; '/'
0x180055370  cmp     dx, [rsi+rcx*2]
0x180055374  jz      short loc_18005537B
0x180055376  sub     ecx, 1
0x180055379  jns     short loc_18005536B
0x18005537b  movsxd  rax, ecx
0x18005537e  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180055382  xor     edx, edx; int
0x180055384  lea     r14, [rsi+rax*2]
0x180055388  lea     rcx, [r14+2]; Src
0x18005538c  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x180055391  mov     ebx, eax
0x180055393  test    eax, eax
0x180055395  jz      short loc_1800553DC
0x180055397  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005539e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800553a3  mov     r9, rax
0x1800553a6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800553ad  lea     rax, Class
0x1800553b4  mov     r8d, ebx
0x1800553b7  mov     [rsp+58h+var_28], rax
0x1800553bc  xor     ecx, ecx
0x1800553be  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x1800553c5  mov     qword ptr [rsp+58h+cchNameString], rax
0x1800553ca  mov     dword ptr [rsp+58h+pszNameString], 271Bh
0x1800553d2  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800553d7  jmp     loc_180055461
0x1800553dc  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x1800553e0  mov     edx, 1; int
0x1800553e5  lea     rcx, [r14+2]; Src
0x1800553e9  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x1800553ee  mov     ebx, eax
0x1800553f0  test    eax, eax
0x1800553f2  jz      short loc_18005543A
0x1800553f4  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800553fb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055400  mov     r9, rax
0x180055403  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005540a  lea     rax, Class
0x180055411  mov     r8d, ebx
0x180055414  mov     [rsp+58h+var_28], rax
0x180055419  xor     ecx, ecx
0x18005541b  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x180055422  mov     qword ptr [rsp+58h+cchNameString], rax
0x180055427  mov     dword ptr [rsp+58h+pszNameString], 2721h
0x18005542f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180055434  mov     rdi, [rbp+arg_18]
0x180055438  jmp     short loc_180055461
0x18005543a  mov     rdi, [rbp+arg_18]
0x18005543e  jmp     short loc_180055443
0x180055440  xor     r12d, r12d
0x180055443  mov     rax, [rbp+var_18]
0x180055447  mov     rcx, [rbp+arg_8]
0x18005544b  mov     [r13+0], rdi
0x18005544f  mov     rdi, r12
0x180055452  mov     [rbp+var_18], r12
0x180055456  mov     [rcx], rax
0x180055459  mov     ebx, r12d
0x18005545c  test    rsi, rsi
0x18005545f  jz      short loc_180055474
0x180055461  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180055468  mov     rcx, rsi
0x18005546b  mov     rax, [rax+30h]
0x18005546f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055474  test    r15, r15
0x180055477  jz      short loc_18005548C
0x180055479  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180055480  mov     rcx, r15
0x180055483  mov     rax, [rax+30h]
0x180055487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005548c  mov     rcx, [rbp+var_18]
0x180055490  test    rcx, rcx
0x180055493  jz      short loc_1800554A5
0x180055495  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005549c  mov     rax, [rax+30h]
0x1800554a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554a5  test    rdi, rdi
0x1800554a8  jz      short loc_1800554BD
0x1800554aa  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800554b1  mov     rcx, rdi
0x1800554b4  mov     rax, [rax+30h]
0x1800554b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554bd  mov     eax, ebx
0x1800554bf  add     rsp, 58h
0x1800554c3  pop     r15
0x1800554c5  pop     r14
0x1800554c7  pop     r13
0x1800554c9  pop     r12
0x1800554cb  pop     rdi
0x1800554cc  pop     rsi
0x1800554cd  pop     rbx
  ... truncated ...
```
