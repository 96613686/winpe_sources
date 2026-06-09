# I_EncodeCNGECCParameters(_CRYPT_OID_INFO const *,_CNG_NCRYPT_OR_BCRYPT_KEY *,ulong,uchar * *,ulong *)

- ea: `0x1800ddea4`
- end: `0x1800de22a`
- name: `?I_EncodeCNGECCParameters@@YAHPEBU_CRYPT_OID_INFO@@PEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@KPEAPEAEPEAK@Z`
- size: `902`
- prototype: `int(const struct _CRYPT_OID_INFO *, struct _CNG_NCRYPT_OR_BCRYPT_KEY *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800aabc8`
- `0x180109b90`

## callees

- `0x180025cf0`
- `0x18002a7d8`
- `0x1800b81dc`
- `0x1800bec20`
- `0x1800ddea4`
- `0x1800e26cc`
- `0x180115040`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de1da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800de1d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800de207`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800de1d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800de207`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ddf1e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ddf5e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ddf1e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ddf5e`
- `ncrypt!NCryptGetProperty` at `0x1800ddfac`
- `ncrypt!NCryptGetProperty` at `0x1800de075`
- `ncrypt!NCryptGetProperty` at `0x1800ddfac`
- `ncrypt!NCryptGetProperty` at `0x1800de075`
- `bcrypt!BCryptGetProperty` at `0x1800de0bd`
- `bcrypt!BCryptGetProperty` at `0x1800de18c`
- `bcrypt!BCryptGetProperty` at `0x1800de0bd`
- `bcrypt!BCryptGetProperty` at `0x1800de18c`

## pseudocode

```c
__int64 __fastcall I_EncodeCNGECCParameters(
        const struct _CRYPT_OID_INFO *a1,
        struct _CNG_NCRYPT_OR_BCRYPT_KEY *a2,
        DWORD a3,
        unsigned __int8 **a4,
        unsigned int *pcbEncoded)
{
  DWORD *p_pcbResult; // rbx
  const struct _CRYPT_OID_INFO *v9; // rdi
  PCCRYPT_OID_INFO OIDInfoFromCNGKey; // rax
  void *v11; // rcx
  SECURITY_STATUS Property; // eax
  __int64 v13; // rdx
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  DWORD *v20; // rax
  DWORD LastError; // edi
  unsigned int v22; // esi
  __int64 v23; // rdx
  DWORD v24; // ecx
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  void *v29; // rsp
  void *v30; // rsp
  DWORD *v31; // rax
  _BYTE v33[32]; // [rsp+0h] [rbp-40h] BYREF
  PCNZWCH lpString2; // [rsp+20h] [rbp-20h]
  int cchCount2[2]; // [rsp+28h] [rbp-18h]
  DWORD pcbResult; // [rsp+40h] [rbp+0h] BYREF
  __int64 v37; // [rsp+48h] [rbp+8h] BYREF
  __int128 pvStructInfo; // [rsp+50h] [rbp+10h] BYREF

  p_pcbResult = 0;
  pcbResult = 0;
  v9 = a1;
  pvStructInfo = 0;
  if ( !a4 || !pcbEncoded )
  {
    v24 = -2147024809;
    goto LABEL_43;
  }
  if ( a1 )
  {
    if ( CompareStringW(0x409u, 1u, (PCNZWCH)a1[1].pszOID, -1, L"CryptOIDInfoECCParameters", -1) != 2 )
    {
      OIDInfoFromCNGKey = I_CryptGetOIDInfoFromCNGKey(a2);
      v9 = OIDInfoFromCNGKey;
      if ( !OIDInfoFromCNGKey )
        goto LABEL_44;
      if ( CompareStringW(0x409u, 1u, (PCNZWCH)OIDInfoFromCNGKey[1].pszOID, -1, L"CryptOIDInfoECCParameters", -1) != 2 )
        goto LABEL_40;
    }
    if ( v9 )
      return CryptEncodeObjectEx(a3, (LPCSTR)0x49, &v9->pszOID, 0x8000u, &PkiEncodePara, a4, pcbEncoded);
  }
  if ( !(unsigned int)IsGenericECCAlgorithm(a2) )
  {
LABEL_40:
    v24 = -2146889726;
    goto LABEL_43;
  }
  v11 = (void *)*((_QWORD *)a2 + 1);
  cchCount2[0] = 0;
  lpString2 = (PCNZWCH)&pcbResult;
  if ( *(_DWORD *)a2 )
  {
    Property = NCryptGetProperty((NCRYPT_HANDLE)v11, L"ECCParameters", 0, 0, (DWORD *)lpString2, cchCount2[0]);
    if ( !Property )
    {
      v14 = pcbResult + 2LL;
      if ( v14 > g_ulMaxStackAllocSize )
        goto LABEL_52;
      v15 = v14 + g_ulAdditionalProbeSize + 8;
      if ( v15 < v14 || !(unsigned int)VerifyStackAvailable(v15, v13) )
        goto LABEL_52;
      v16 = v14 + 23;
      if ( v14 + 23 <= v14 + 8 )
        v16 = 0xFFFFFFFFFFFFFF0LL;
      v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
      v18 = alloca(v17);
      v19 = alloca(v17);
      p_pcbResult = &pcbResult;
      if ( v33 == (_BYTE *)-64LL || (pcbResult = 1801679955, (p_pcbResult = (DWORD *)&v37) == 0) )
      {
LABEL_52:
        if ( v14 + 8 >= v14 )
        {
          v20 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcbResult = v20;
          if ( v20 )
          {
            *v20 = 1885431112;
            p_pcbResult = v20 + 2;
          }
        }
      }
      if ( p_pcbResult )
      {
        Property = NCryptGetProperty(
                     *((_QWORD *)a2 + 1),
                     L"ECCParameters",
                     (PBYTE)p_pcbResult,
                     pcbResult,
                     &pcbResult,
                     0);
        goto LABEL_23;
      }
      goto LABEL_38;
    }
  }
  else
  {
    Property = BCryptGetProperty(v11, L"ECCParameters", 0, 0, (ULONG *)lpString2, cchCount2[0]);
    if ( !Property )
    {
      v25 = pcbResult + 2LL;
      if ( v25 > g_ulMaxStackAllocSize )
        goto LABEL_53;
      v26 = v25 + g_ulAdditionalProbeSize + 8;
      if ( v26 < v25 || !(unsigned int)VerifyStackAvailable(v26, v23) )
        goto LABEL_53;
      v27 = v25 + 23;
      if ( v25 + 23 <= v25 + 8 )
        v27 = 0xFFFFFFFFFFFFFF0LL;
      v28 = v27 & 0xFFFFFFFFFFFFFFF0uLL;
      v29 = alloca(v28);
      v30 = alloca(v28);
      p_pcbResult = &pcbResult;
      if ( v33 == (_BYTE *)-64LL || (pcbResult = 1801679955, (p_pcbResult = (DWORD *)&v37) == 0) )
      {
LABEL_53:
        if ( v25 + 8 >= v25 )
        {
          v31 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_pcbResult = v31;
          if ( v31 )
          {
            *v31 = 1885431112;
            p_pcbResult = v31 + 2;
          }
        }
      }
      if ( p_pcbResult )
      {
        Property = BCryptGetProperty(
                     *((BCRYPT_HANDLE *)a2 + 1),
                     L"ECCParameters",
                     (PUCHAR)p_pcbResult,
                     pcbResult,
                     &pcbResult,
                     0);
LABEL_23:
        if ( !Property )
        {
          LastError = 0;
          LODWORD(pvStructInfo) = pcbResult;
          *((_QWORD *)&pvStructInfo + 1) = p_pcbResult;
          v22 = CryptEncodeObjectEx(a3, (LPCSTR)0x55, &pvStructInfo, 0x8000u, &PkiEncodePara, a4, pcbEncoded);
          goto LABEL_45;
        }
        goto LABEL_26;
      }
LABEL_38:
      v24 = -2147024882;
      goto LABEL_43;
    }
  }
LABEL_26:
  v24 = Property;
LABEL_43:
  SetLastError(v24);
LABEL_44:
  LastError = GetLastError();
  v22 = 0;
  if ( p_pcbResult )
  {
LABEL_45:
    if ( *(p_pcbResult - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  if ( LastError )
    SetLastError(LastError);
  return v22;
}

```

## disassembly

```asm
0x1800ddea4  push    rbp
0x1800ddea6  push    rbx
0x1800ddea7  push    rsi
0x1800ddea8  push    rdi
0x1800ddea9  push    r12
0x1800ddeab  push    r14
0x1800ddead  push    r15
0x1800ddeaf  sub     rsp, 70h
0x1800ddeb3  lea     rbp, [rsp+40h]
0x1800ddeb8  mov     rax, cs:__security_cookie
0x1800ddebf  xor     rax, rbp
0x1800ddec2  mov     [rbp+60h+var_40], rax
0x1800ddec6  xor     ebx, ebx
0x1800ddec8  xorps   xmm0, xmm0
0x1800ddecb  mov     [rbp+60h+pcbResult], ebx
0x1800ddece  mov     r15, r9
0x1800dded1  mov     r12d, r8d
0x1800dded4  mov     rsi, rdx
0x1800dded7  mov     rdi, rcx
0x1800ddeda  movups  [rbp+60h+pvStructInfo], xmm0
0x1800ddede  test    r9, r9
0x1800ddee1  jz      loc_1800DE1CF
0x1800ddee7  mov     r14, [rbp+60h+arg_20]
0x1800ddeee  test    r14, r14
0x1800ddef1  jz      loc_1800DE1CF
0x1800ddef7  test    rcx, rcx
0x1800ddefa  jz      short loc_1800DDF76
0x1800ddefc  mov     r8, [rdi+38h]; lpString1
0x1800ddf00  lea     rcx, String2; "CryptOIDInfoECCParameters"
0x1800ddf07  or      eax, 0FFFFFFFFh
0x1800ddf0a  lea     edx, [rbx+1]; dwCmpFlags
0x1800ddf0d  mov     [rsp+0A0h+cchCount2], eax; cchCount2
0x1800ddf11  mov     r9d, eax; cchCount1
0x1800ddf14  mov     [rsp+0A0h+lpString2], rcx; lpString2
0x1800ddf19  mov     ecx, 409h; Locale
0x1800ddf1e  call    cs:__imp_CompareStringW
0x1800ddf24  cmp     eax, 2
0x1800ddf27  jz      short loc_1800DDF6D
0x1800ddf29  mov     rcx, rsi; struct _CNG_NCRYPT_OR_BCRYPT_KEY *
0x1800ddf2c  call    ?I_CryptGetOIDInfoFromCNGKey@@YAPEBU_CRYPT_OID_INFO@@PEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@@Z; I_CryptGetOIDInfoFromCNGKey(_CNG_NCRYPT_OR_BCRYPT_KEY *)
0x1800ddf31  mov     rdi, rax
0x1800ddf34  test    rax, rax
0x1800ddf37  jz      loc_1800DE1DA
0x1800ddf3d  mov     r8, [rdi+38h]; lpString1
0x1800ddf41  lea     rax, String2; "CryptOIDInfoECCParameters"
0x1800ddf48  or      r9d, 0FFFFFFFFh; cchCount1
0x1800ddf4c  lea     edx, [rbx+1]; dwCmpFlags
0x1800ddf4f  mov     [rsp+0A0h+cchCount2], r9d; cchCount2
0x1800ddf54  mov     ecx, 409h; Locale
0x1800ddf59  mov     [rsp+0A0h+lpString2], rax; lpString2
0x1800ddf5e  call    cs:__imp_CompareStringW
0x1800ddf64  cmp     eax, 2
0x1800ddf67  jnz     loc_1800DE197
0x1800ddf6d  test    rdi, rdi
0x1800ddf70  jnz     loc_1800DE19E
0x1800ddf76  mov     rcx, rsi; struct _CNG_NCRYPT_OR_BCRYPT_KEY *
0x1800ddf79  call    ?IsGenericECCAlgorithm@@YAHPEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@@Z; IsGenericECCAlgorithm(_CNG_NCRYPT_OR_BCRYPT_KEY *)
0x1800ddf7e  test    eax, eax
0x1800ddf80  jz      loc_1800DE197
0x1800ddf86  mov     rcx, [rsi+8]; hObject
0x1800ddf8a  lea     rax, [rbp+60h+pcbResult]
0x1800ddf8e  xor     r9d, r9d; cbOutput
0x1800ddf91  mov     [rsp+0A0h+cchCount2], ebx; dwFlags
0x1800ddf95  xor     r8d, r8d; pbOutput
0x1800ddf98  mov     [rsp+0A0h+lpString2], rax; pcbResult
0x1800ddf9d  lea     rdx, aEccparameters; "ECCParameters"
0x1800ddfa4  cmp     [rsi], ebx
0x1800ddfa6  jz      loc_1800DE0BD
0x1800ddfac  call    cs:__imp_NCryptGetProperty
0x1800ddfb2  test    eax, eax
0x1800ddfb4  jnz     loc_1800DE0C7
0x1800ddfba  mov     edi, [rbp+60h+pcbResult]
0x1800ddfbd  add     rdi, 2
0x1800ddfc1  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800ddfc8  ja      short loc_1800DE022
0x1800ddfca  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800ddfd1  add     rcx, 8
0x1800ddfd5  add     rcx, rdi
0x1800ddfd8  cmp     rcx, rdi
0x1800ddfdb  jb      short loc_1800DE022
0x1800ddfdd  call    VerifyStackAvailable
0x1800ddfe2  test    eax, eax
0x1800ddfe4  jz      short loc_1800DE022
0x1800ddfe6  lea     rax, [rdi+8]
0x1800ddfea  lea     rcx, [rax+0Fh]
0x1800ddfee  cmp     rcx, rax
0x1800ddff1  ja      short loc_1800DDFFD
0x1800ddff3  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800ddffd  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800de001  mov     rax, rcx
0x1800de004  call    _alloca_probe
0x1800de009  sub     rsp, rcx
0x1800de00c  lea     rbx, [rsp+0A0h+pcbResult]
0x1800de011  test    rbx, rbx
0x1800de014  jz      short loc_1800DE022
0x1800de016  mov     dword ptr [rbx], 6B637453h
0x1800de01c  add     rbx, 8
0x1800de020  jnz     short loc_1800DE049
0x1800de022  lea     rcx, [rdi+8]
0x1800de026  cmp     rcx, rdi
0x1800de029  jb      short loc_1800DE049
0x1800de02b  mov     rax, cs:g_pfnAllocate
0x1800de032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de037  mov     rbx, rax
0x1800de03a  test    rax, rax
0x1800de03d  jz      short loc_1800DE049
0x1800de03f  mov     dword ptr [rax], 70616548h
0x1800de045  add     rbx, 8
0x1800de049  test    rbx, rbx
0x1800de04c  jz      loc_1800DE162
0x1800de052  mov     r9d, [rbp+60h+pcbResult]; cbOutput
0x1800de056  lea     rax, [rbp+60h+pcbResult]
0x1800de05a  mov     rcx, [rsi+8]; hObject
0x1800de05e  lea     rdx, aEccparameters; "ECCParameters"
0x1800de065  mov     [rsp+0A0h+cchCount2], 0; dwFlags
0x1800de06d  mov     r8, rbx; pbOutput
0x1800de070  mov     [rsp+0A0h+lpString2], rax; pcbResult
0x1800de075  call    cs:__imp_NCryptGetProperty
0x1800de07b  test    eax, eax
0x1800de07d  jnz     short loc_1800DE0C7
0x1800de07f  mov     eax, [rbp+60h+pcbResult]
0x1800de082  lea     r8, [rbp+60h+pvStructInfo]; pvStructInfo
0x1800de086  xor     edi, edi
0x1800de088  mov     dword ptr [rbp+60h+pvStructInfo], eax
0x1800de08b  mov     [rsp+0A0h+pcbEncoded], r14; pcbEncoded
0x1800de090  lea     rax, PkiEncodePara
0x1800de097  mov     qword ptr [rsp+0A0h+cchCount2], r15; pvEncoded
0x1800de09c  mov     r9d, 8000h; dwFlags
0x1800de0a2  mov     ecx, r12d; dwCertEncodingType
0x1800de0a5  mov     qword ptr [rbp+60h+pvStructInfo+8], rbx
0x1800de0a9  lea     edx, [rdi+55h]; lpszStructType
0x1800de0ac  mov     [rsp+0A0h+lpString2], rax; pEncodePara
0x1800de0b1  call    CryptEncodeObjectEx
0x1800de0b6  mov     esi, eax
0x1800de0b8  jmp     loc_1800DE1E9
0x1800de0bd  call    cs:__imp_BCryptGetProperty
0x1800de0c3  test    eax, eax
0x1800de0c5  jz      short loc_1800DE0CE
0x1800de0c7  mov     ecx, eax
0x1800de0c9  jmp     loc_1800DE1D4
0x1800de0ce  mov     edi, [rbp+60h+pcbResult]
0x1800de0d1  add     rdi, 2
0x1800de0d5  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800de0dc  ja      short loc_1800DE136
0x1800de0de  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800de0e5  add     rcx, 8
0x1800de0e9  add     rcx, rdi
0x1800de0ec  cmp     rcx, rdi
0x1800de0ef  jb      short loc_1800DE136
0x1800de0f1  call    VerifyStackAvailable
0x1800de0f6  test    eax, eax
0x1800de0f8  jz      short loc_1800DE136
0x1800de0fa  lea     rax, [rdi+8]
0x1800de0fe  lea     rcx, [rax+0Fh]
0x1800de102  cmp     rcx, rax
0x1800de105  ja      short loc_1800DE111
0x1800de107  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800de111  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800de115  mov     rax, rcx
0x1800de118  call    _alloca_probe
0x1800de11d  sub     rsp, rcx
0x1800de120  lea     rbx, [rsp+0A0h+pcbResult]
0x1800de125  test    rbx, rbx
0x1800de128  jz      short loc_1800DE136
0x1800de12a  mov     dword ptr [rbx], 6B637453h
0x1800de130  add     rbx, 8
0x1800de134  jnz     short loc_1800DE15D
0x1800de136  lea     rcx, [rdi+8]
0x1800de13a  cmp     rcx, rdi
0x1800de13d  jb      short loc_1800DE15D
0x1800de13f  mov     rax, cs:g_pfnAllocate
0x1800de146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de14b  mov     rbx, rax
0x1800de14e  test    rax, rax
0x1800de151  jz      short loc_1800DE15D
0x1800de153  mov     dword ptr [rax], 70616548h
0x1800de159  add     rbx, 8
0x1800de15d  test    rbx, rbx
0x1800de160  jnz     short loc_1800DE169
0x1800de162  mov     ecx, 8007000Eh
0x1800de167  jmp     short loc_1800DE1D4
0x1800de169  mov     r9d, [rbp+60h+pcbResult]; cbOutput
0x1800de16d  lea     rax, [rbp+60h+pcbResult]
0x1800de171  mov     rcx, [rsi+8]; hObject
0x1800de175  lea     rdx, aEccparameters; "ECCParameters"
0x1800de17c  mov     [rsp+0A0h+cchCount2], 0; dwFlags
0x1800de184  mov     r8, rbx; pbOutput
0x1800de187  mov     [rsp+0A0h+lpString2], rax; pcbResult
0x1800de18c  call    cs:__imp_BCryptGetProperty
0x1800de192  jmp     loc_1800DE07B
0x1800de197  mov     ecx, 80091002h
0x1800de19c  jmp     short loc_1800DE1D4
0x1800de19e  mov     [rsp+0A0h+pcbEncoded], r14; pcbEncoded
0x1800de1a3  lea     rax, PkiEncodePara
0x1800de1aa  mov     qword ptr [rsp+0A0h+cchCount2], r15; pvEncoded
0x1800de1af  lea     r8, [rdi+8]; pvStructInfo
0x1800de1b3  mov     edx, 49h ; 'I'; lpszStructType
0x1800de1b8  mov     [rsp+0A0h+lpString2], rax; pEncodePara
0x1800de1bd  mov     r9d, 8000h; dwFlags
0x1800de1c3  mov     ecx, r12d; dwCertEncodingType
0x1800de1c6  call    CryptEncodeObjectEx
0x1800de1cb  mov     esi, eax
0x1800de1cd  jmp     short loc_1800DE20D
0x1800de1cf  mov     ecx, 80070057h; dwErrCode
0x1800de1d4  call    cs:__imp_SetLastError
0x1800de1da  call    cs:__imp_GetLastError
0x1800de1e0  mov     edi, eax
0x1800de1e2  xor     esi, esi
0x1800de1e4  test    rbx, rbx
0x1800de1e7  jz      short loc_1800DE201
0x1800de1e9  lea     rcx, [rbx-8]
0x1800de1ed  cmp     dword ptr [rcx], 70616548h
0x1800de1f3  jnz     short loc_1800DE201
0x1800de1f5  mov     rax, cs:g_pfnFree
0x1800de1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de201  test    edi, edi
0x1800de203  jz      short loc_1800DE20D
0x1800de205  mov     ecx, edi; dwErrCode
0x1800de207  call    cs:__imp_SetLastError
0x1800de20d  mov     eax, esi
0x1800de20f  mov     rcx, [rbp+60h+var_40]
0x1800de213  xor     rcx, rbp; StackCookie
0x1800de216  call    __security_check_cookie
0x1800de21b  lea     rsp, [rbp+30h]
0x1800de21f  pop     r15
0x1800de221  pop     r14
0x1800de223  pop     r12
0x1800de225  pop     rdi
0x1800de226  pop     rsi
0x1800de227  pop     rbx
0x1800de228  pop     rbp
0x1800de229  retn
```
