# I_CryptGetOIDInfoFromCNGKey(_CNG_NCRYPT_OR_BCRYPT_KEY *)

- ea: `0x1800e26cc`
- end: `0x1800e2f22`
- name: `?I_CryptGetOIDInfoFromCNGKey@@YAPEBU_CRYPT_OID_INFO@@PEAU_CNG_NCRYPT_OR_BCRYPT_KEY@@@Z`
- size: `2134`
- prototype: `const struct _CRYPT_OID_INFO *__fastcall(struct _CNG_NCRYPT_OR_BCRYPT_KEY *)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180070274`
- `0x1800ddea4`
- `0x180109b90`

## callees

- `0x180009da0`
- `0x180028d60`
- `0x18002a7d8`
- `0x1800bec20`
- `0x1800e26cc`
- `0x180111390`
- `0x1801113cc`
- `0x180115040`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2975`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e296f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e2efe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e296f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e2efe`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2828`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2857`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2ace`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2c02`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2c31`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2e3f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2828`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2857`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2ace`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2c02`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2c31`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800e2e3f`
- `ncrypt!NCryptGetProperty` at `0x1800e2728`
- `ncrypt!NCryptGetProperty` at `0x1800e27f3`
- `ncrypt!NCryptGetProperty` at `0x1800e2898`
- `ncrypt!NCryptGetProperty` at `0x1800e295b`
- `ncrypt!NCryptGetProperty` at `0x1800e29ce`
- `ncrypt!NCryptGetProperty` at `0x1800e2a91`
- `ncrypt!NCryptGetProperty` at `0x1800e2728`
- `ncrypt!NCryptGetProperty` at `0x1800e27f3`
- `ncrypt!NCryptGetProperty` at `0x1800e2898`
- `ncrypt!NCryptGetProperty` at `0x1800e295b`
- `ncrypt!NCryptGetProperty` at `0x1800e29ce`
- `ncrypt!NCryptGetProperty` at `0x1800e2a91`
- `bcrypt!BCryptGetProperty` at `0x1800e2af7`
- `bcrypt!BCryptGetProperty` at `0x1800e2bcd`
- `bcrypt!BCryptGetProperty` at `0x1800e2c72`
- `bcrypt!BCryptGetProperty` at `0x1800e2d53`
- `bcrypt!BCryptGetProperty` at `0x1800e2e1a`
- `bcrypt!BCryptGetProperty` at `0x1800e2af7`
- `bcrypt!BCryptGetProperty` at `0x1800e2bcd`
- `bcrypt!BCryptGetProperty` at `0x1800e2c72`
- `bcrypt!BCryptGetProperty` at `0x1800e2d53`
- `bcrypt!BCryptGetProperty` at `0x1800e2e1a`

## pseudocode

```c
PCCRYPT_OID_INFO __fastcall I_CryptGetOIDInfoFromCNGKey(struct _CNG_NCRYPT_OR_BCRYPT_KEY *a1)
{
  DWORD *v1; // rsi
  DWORD *v2; // rdi
  bool v3; // zf
  void *v5; // rcx
  NTSTATUS Property; // eax
  __int64 v7; // rdx
  DWORD *p_cbOutput; // rbx
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  DWORD *v15; // rax
  NTSTATUS v16; // r15d
  __int64 v17; // rdx
  unsigned __int64 v18; // r14
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  DWORD *v24; // rax
  NTSTATUS v25; // eax
  DWORD v26; // ecx
  DWORD LastError; // r15d
  PCCRYPT_OID_INFO OIDInfo; // r14
  __int64 v29; // rdx
  unsigned __int64 v30; // r14
  unsigned __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned __int64 v33; // rcx
  void *v34; // rsp
  void *v35; // rsp
  DWORD *v36; // rax
  DWORD v37; // r8d
  DWORD *v38; // rdx
  DWORD v39; // ecx
  __int64 v40; // rdx
  unsigned __int64 v41; // r14
  unsigned __int64 v42; // rcx
  __int64 v43; // rcx
  unsigned __int64 v44; // rcx
  void *v45; // rsp
  void *v46; // rsp
  DWORD *v47; // rax
  __int64 v48; // rdx
  unsigned __int64 v49; // r14
  unsigned __int64 v50; // rcx
  __int64 v51; // rcx
  unsigned __int64 v52; // rcx
  void *v53; // rsp
  void *v54; // rsp
  DWORD *v55; // rax
  ULONG v56; // r9d
  DWORD *v57; // rax
  const WCHAR *v58; // rdx
  UCHAR *v59; // r8
  __int64 v60; // rdx
  unsigned __int64 v61; // r14
  unsigned __int64 v62; // rcx
  __int64 v63; // rcx
  unsigned __int64 v64; // rcx
  void *v65; // rsp
  void *v66; // rsp
  DWORD *v67; // rax
  void *ParameterSetAlgorithmName; // rax
  void *v69; // r15
  _BYTE v71[32]; // [rsp+0h] [rbp-30h] BYREF
  DWORD *pcbResult; // [rsp+20h] [rbp-10h]
  DWORD dwFlags; // [rsp+28h] [rbp-8h]
  DWORD cbOutput; // [rsp+30h] [rbp+0h] BYREF
  DWORD v75; // [rsp+34h] [rbp+4h] BYREF
  DWORD v76; // [rsp+38h] [rbp+8h] BYREF
  struct _CNG_NCRYPT_OR_BCRYPT_KEY *v77; // [rsp+40h] [rbp+10h]

  v1 = 0;
  v77 = a1;
  v2 = 0;
  dwFlags = 0;
  cbOutput = 0;
  v76 = 0;
  v3 = *(_DWORD *)a1 == 0;
  pcbResult = &cbOutput;
  v5 = (void *)*((_QWORD *)a1 + 1);
  v75 = 0;
  if ( v3 )
  {
    Property = BCryptGetProperty(v5, L"AlgorithmName", 0, 0, pcbResult, dwFlags);
    if ( !Property )
    {
      p_cbOutput = 0;
      v41 = cbOutput + 2LL;
      if ( v41 > g_ulMaxStackAllocSize )
        goto LABEL_122;
      v42 = v41 + g_ulAdditionalProbeSize + 8;
      if ( v42 < v41 || !(unsigned int)VerifyStackAvailable(v42, v40) )
        goto LABEL_122;
      v43 = v41 + 23;
      if ( v41 + 23 <= v41 + 8 )
        v43 = 0xFFFFFFFFFFFFFF0LL;
      v44 = v43 & 0xFFFFFFFFFFFFFFF0uLL;
      v45 = alloca(v44);
      v46 = alloca(v44);
      p_cbOutput = &cbOutput;
      if ( v71 == (_BYTE *)-48LL || (cbOutput = 1801679955, (p_cbOutput = &v76) == 0) )
      {
LABEL_122:
        if ( v41 + 8 >= v41 )
        {
          v47 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_cbOutput = v47;
          if ( v47 )
          {
            *v47 = 1885431112;
            p_cbOutput = v47 + 2;
          }
        }
      }
      if ( p_cbOutput )
      {
        v16 = BCryptGetProperty(
                *((BCRYPT_HANDLE *)a1 + 1),
                L"AlgorithmName",
                (PUCHAR)p_cbOutput,
                cbOutput,
                &cbOutput,
                0);
        if ( v16 )
          goto LABEL_33;
        if ( CompareStringW(0x409u, 1u, (PCNZWCH)p_cbOutput, -1, L"ECDSA", -1) == 2
          || CompareStringW(0x409u, 1u, (PCNZWCH)p_cbOutput, -1, L"ECDH", -1) == 2 )
        {
          v16 = BCryptGetProperty(*((BCRYPT_HANDLE *)v77 + 1), L"ECCCurveName", 0, 0, &v76, 0);
          if ( v16 )
            goto LABEL_33;
          v61 = v76;
          if ( !v76 )
            goto LABEL_123;
          if ( v76 > (unsigned __int64)g_ulMaxStackAllocSize )
            goto LABEL_123;
          v62 = v76 + g_ulAdditionalProbeSize + 8;
          if ( v62 < v76 || !(unsigned int)VerifyStackAvailable(v62, v60) )
            goto LABEL_123;
          v63 = v61 + 23;
          if ( v61 + 23 <= v61 + 8 )
            v63 = 0xFFFFFFFFFFFFFF0LL;
          v64 = v63 & 0xFFFFFFFFFFFFFFF0uLL;
          v65 = alloca(v64);
          v66 = alloca(v64);
          v1 = &cbOutput;
          if ( v71 == (_BYTE *)-48LL || (cbOutput = 1801679955, (v1 = &v76) == 0) )
          {
LABEL_123:
            if ( v61 + 8 >= v61 )
            {
              v67 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
              v1 = v67;
              if ( v67 )
              {
                *v67 = 1885431112;
                v1 = v67 + 2;
              }
            }
          }
          if ( !v1 )
            goto LABEL_33;
          v56 = v76;
          v57 = &v76;
          dwFlags = 0;
          v58 = L"ECCCurveName";
          v59 = (UCHAR *)v1;
        }
        else
        {
          if ( !(unsigned int)I_CryptIsCNGPQAlgorithm(p_cbOutput) )
            goto LABEL_53;
          v16 = BCryptGetProperty(*((BCRYPT_HANDLE *)v77 + 1), L"ParameterSetName", 0, 0, &v75, 0);
          if ( v16 )
            goto LABEL_33;
          v49 = v75;
          if ( !v75 )
            goto LABEL_124;
          if ( v75 > (unsigned __int64)g_ulMaxStackAllocSize )
            goto LABEL_124;
          v50 = v75 + g_ulAdditionalProbeSize + 8;
          if ( v50 < v75 || !(unsigned int)VerifyStackAvailable(v50, v48) )
            goto LABEL_124;
          v51 = v49 + 23;
          if ( v49 + 23 <= v49 + 8 )
            v51 = 0xFFFFFFFFFFFFFF0LL;
          v52 = v51 & 0xFFFFFFFFFFFFFFF0uLL;
          v53 = alloca(v52);
          v54 = alloca(v52);
          v2 = &cbOutput;
          if ( v71 == (_BYTE *)-48LL || (cbOutput = 1801679955, (v2 = &v76) == 0) )
          {
LABEL_124:
            if ( v49 + 8 >= v49 )
            {
              v55 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
              v2 = v55;
              if ( v55 )
              {
                *v55 = 1885431112;
                v2 = v55 + 2;
              }
            }
          }
          if ( !v2 )
            goto LABEL_33;
          v56 = v75;
          v57 = &v75;
          dwFlags = 0;
          v58 = L"ParameterSetName";
          v59 = (UCHAR *)v2;
        }
        v25 = BCryptGetProperty(*((BCRYPT_HANDLE *)v77 + 1), v58, v59, v56, v57, dwFlags);
        goto LABEL_32;
      }
LABEL_68:
      v26 = -2147024882;
      goto LABEL_34;
    }
LABEL_56:
    p_cbOutput = 0;
    v26 = Property;
    goto LABEL_34;
  }
  Property = NCryptGetProperty((NCRYPT_HANDLE)v5, L"Algorithm Name", 0, 0, pcbResult, dwFlags);
  if ( Property )
    goto LABEL_56;
  p_cbOutput = 0;
  v9 = cbOutput + 2LL;
  if ( v9 > g_ulMaxStackAllocSize )
    goto LABEL_125;
  v10 = v9 + g_ulAdditionalProbeSize + 8;
  if ( v10 < v9 || !(unsigned int)VerifyStackAvailable(v10, v7) )
    goto LABEL_125;
  v11 = v9 + 23;
  if ( v9 + 23 <= v9 + 8 )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  p_cbOutput = &cbOutput;
  if ( v71 == (_BYTE *)-48LL || (cbOutput = 1801679955, (p_cbOutput = &v76) == 0) )
  {
LABEL_125:
    if ( v9 + 8 >= v9 )
    {
      v15 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_cbOutput = v15;
      if ( v15 )
      {
        *v15 = 1885431112;
        p_cbOutput = v15 + 2;
      }
    }
  }
  if ( !p_cbOutput )
    goto LABEL_68;
  v16 = NCryptGetProperty(*((_QWORD *)a1 + 1), L"Algorithm Name", (PBYTE)p_cbOutput, cbOutput, &cbOutput, 0);
  if ( !v16 )
  {
    if ( CompareStringW(0x409u, 1u, (PCNZWCH)p_cbOutput, -1, L"ECDSA", -1) == 2
      || CompareStringW(0x409u, 1u, (PCNZWCH)p_cbOutput, -1, L"ECDH", -1) == 2 )
    {
      v16 = NCryptGetProperty(*((_QWORD *)v77 + 1), L"ECCCurveName", 0, 0, &v76, 0);
      if ( v16 )
        goto LABEL_33;
      v30 = v76;
      if ( !v76 )
        goto LABEL_126;
      if ( v76 > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_126;
      v31 = v76 + g_ulAdditionalProbeSize + 8;
      if ( v31 < v76 || !(unsigned int)VerifyStackAvailable(v31, v29) )
        goto LABEL_126;
      v32 = v30 + 23;
      if ( v30 + 23 <= v30 + 8 )
        v32 = 0xFFFFFFFFFFFFFF0LL;
      v33 = v32 & 0xFFFFFFFFFFFFFFF0uLL;
      v34 = alloca(v33);
      v35 = alloca(v33);
      v1 = &cbOutput;
      if ( v71 == (_BYTE *)-48LL || (cbOutput = 1801679955, (v1 = &v76) == 0) )
      {
LABEL_126:
        if ( v30 + 8 >= v30 )
        {
          v36 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          v1 = v36;
          if ( v36 )
          {
            *v36 = 1885431112;
            v1 = v36 + 2;
          }
        }
      }
      if ( !v1 )
        goto LABEL_33;
      v16 = NCryptGetProperty(*((_QWORD *)v77 + 1), L"ECCCurveName", (PBYTE)v1, v76, &v76, 0);
      if ( v16 )
        goto LABEL_33;
      goto LABEL_53;
    }
    if ( !(unsigned int)I_CryptIsCNGPQAlgorithm(p_cbOutput) )
      goto LABEL_53;
    v16 = NCryptGetProperty(*((_QWORD *)v77 + 1), L"ParameterSetName", 0, 0, &v75, 0);
    if ( v16 )
      goto LABEL_33;
    v18 = v75;
    if ( !v75 )
      goto LABEL_127;
    if ( v75 > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_127;
    v19 = v75 + g_ulAdditionalProbeSize + 8;
    if ( v19 < v75 || !(unsigned int)VerifyStackAvailable(v19, v17) )
      goto LABEL_127;
    v20 = v18 + 23;
    if ( v18 + 23 <= v18 + 8 )
      v20 = 0xFFFFFFFFFFFFFF0LL;
    v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
    v22 = alloca(v21);
    v23 = alloca(v21);
    v2 = &cbOutput;
    if ( v71 == (_BYTE *)-48LL || (cbOutput = 1801679955, (v2 = &v76) == 0) )
    {
LABEL_127:
      if ( v18 + 8 >= v18 )
      {
        v24 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v2 = v24;
        if ( v24 )
        {
          *v24 = 1885431112;
          v2 = v24 + 2;
        }
      }
    }
    if ( !v2 )
      goto LABEL_33;
    v25 = NCryptGetProperty(*((_QWORD *)v77 + 1), L"ParameterSetName", (PBYTE)v2, v75, &v75, 0);
LABEL_32:
    v16 = v25;
    if ( v25 )
      goto LABEL_33;
LABEL_53:
    if ( CompareStringW(0x409u, 1u, (PCNZWCH)p_cbOutput, -1, L"ECDSA", -1) == 2 )
    {
      v37 = 1073741827;
      v38 = v1;
      v39 = -2147483646;
    }
    else if ( CompareStringW(0x409u, 1u, (PCNZWCH)p_cbOutput, -1, L"ECDH", -1) == 2 )
    {
      v37 = 1073741827;
      v38 = v1;
      v39 = 1073741826;
    }
    else
    {
      if ( v2 )
      {
        ParameterSetAlgorithmName = (void *)I_CryptMakeParameterSetAlgorithmName(
                                              (unsigned __int16 *)p_cbOutput,
                                              (unsigned __int16 *)v2);
        v69 = ParameterSetAlgorithmName;
        if ( !ParameterSetAlgorithmName )
          goto LABEL_35;
        OIDInfo = CryptFindOIDInfo(5u, ParameterSetAlgorithmName, 3u);
        PkiDefaultCryptFree(v69);
        goto LABEL_109;
      }
      v37 = 3;
      v38 = p_cbOutput;
      v39 = 5;
    }
    OIDInfo = CryptFindOIDInfo(v39, v38, v37);
LABEL_109:
    LastError = 0;
    if ( OIDInfo )
      goto LABEL_36;
    v26 = -2146889726;
    goto LABEL_34;
  }
LABEL_33:
  v26 = v16;
LABEL_34:
  SetLastError(v26);
LABEL_35:
  LastError = GetLastError();
  OIDInfo = 0;
LABEL_36:
  if ( p_cbOutput && *(p_cbOutput - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v1 && *(v1 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v2 && *(v2 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( LastError )
    SetLastError(LastError);
  return OIDInfo;
}

```

## disassembly

```asm
0x1800e26cc  push    rbp
0x1800e26ce  push    rbx
0x1800e26cf  push    rsi
0x1800e26d0  push    rdi
0x1800e26d1  push    r12
0x1800e26d3  push    r14
0x1800e26d5  push    r15
0x1800e26d7  sub     rsp, 60h
0x1800e26db  lea     rbp, [rsp+30h]
0x1800e26e0  mov     rax, cs:__security_cookie
0x1800e26e7  xor     rax, rbp
0x1800e26ea  mov     [rbp+60h+var_40], rax
0x1800e26ee  xor     esi, esi
0x1800e26f0  mov     [rbp+60h+var_50], rcx
0x1800e26f4  xor     edi, edi
0x1800e26f6  mov     [rsp+90h+dwFlags], esi; dwFlags
0x1800e26fa  xor     r9d, r9d; cbOutput
0x1800e26fd  mov     [rbp+60h+cbOutput], esi
0x1800e2700  xor     r8d, r8d; pbOutput
0x1800e2703  mov     [rbp+60h+var_58], esi
0x1800e2706  cmp     [rcx], esi
0x1800e2708  lea     rax, [rbp+60h+cbOutput]
0x1800e270c  mov     r15, rcx
0x1800e270f  mov     [rsp+90h+pcbResult], rax; pcbResult
0x1800e2714  mov     rcx, [rcx+8]; hObject
0x1800e2718  mov     [rbp+60h+var_5C], esi
0x1800e271b  jz      loc_1800E2AF0
0x1800e2721  lea     rdx, aAlgorithmName; "Algorithm Name"
0x1800e2728  call    cs:__imp_NCryptGetProperty
0x1800e272e  test    eax, eax
0x1800e2730  jnz     loc_1800E2B01
0x1800e2736  mov     r14d, [rbp+60h+cbOutput]
0x1800e273a  xor     ebx, ebx
0x1800e273c  add     r14, 2
0x1800e2740  mov     r12, 0FFFFFFFFFFFFFF0h
0x1800e274a  cmp     r14, cs:g_ulMaxStackAllocSize
0x1800e2751  ja      short loc_1800E27A4
0x1800e2753  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800e275a  add     rcx, 8
0x1800e275e  add     rcx, r14
0x1800e2761  cmp     rcx, r14
0x1800e2764  jb      short loc_1800E27A4
0x1800e2766  call    VerifyStackAvailable
0x1800e276b  test    eax, eax
0x1800e276d  jz      short loc_1800E27A4
0x1800e276f  lea     rax, [r14+8]
0x1800e2773  lea     rcx, [rax+0Fh]
0x1800e2777  cmp     rcx, rax
0x1800e277a  ja      short loc_1800E277F
0x1800e277c  mov     rcx, r12
0x1800e277f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800e2783  mov     rax, rcx
0x1800e2786  call    _alloca_probe
0x1800e278b  sub     rsp, rcx
0x1800e278e  lea     rbx, [rsp+90h+cbOutput]
0x1800e2793  test    rbx, rbx
0x1800e2796  jz      short loc_1800E27A4
0x1800e2798  mov     dword ptr [rbx], 6B637453h
0x1800e279e  add     rbx, 8
0x1800e27a2  jnz     short loc_1800E27CB
0x1800e27a4  lea     rcx, [r14+8]
0x1800e27a8  cmp     rcx, r14
0x1800e27ab  jb      short loc_1800E27CB
0x1800e27ad  mov     rax, cs:g_pfnAllocate
0x1800e27b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e27b9  mov     rbx, rax
0x1800e27bc  test    rax, rax
0x1800e27bf  jz      short loc_1800E27CB
0x1800e27c1  mov     dword ptr [rax], 70616548h
0x1800e27c7  add     rbx, 8
0x1800e27cb  test    rbx, rbx
0x1800e27ce  jz      loc_1800E2BA4
0x1800e27d4  mov     r9d, [rbp+60h+cbOutput]; cbOutput
0x1800e27d8  lea     rax, [rbp+60h+cbOutput]
0x1800e27dc  mov     rcx, [r15+8]; hObject
0x1800e27e0  lea     rdx, aAlgorithmName; "Algorithm Name"
0x1800e27e7  mov     [rsp+90h+dwFlags], esi; dwFlags
0x1800e27eb  mov     r8, rbx; pbOutput
0x1800e27ee  mov     [rsp+90h+pcbResult], rax; pcbResult
0x1800e27f3  call    cs:__imp_NCryptGetProperty
0x1800e27f9  mov     r15d, eax
0x1800e27fc  test    eax, eax
0x1800e27fe  jnz     loc_1800E296C
0x1800e2804  or      r14d, 0FFFFFFFFh
0x1800e2808  lea     rax, aEcdsa; "ECDSA"
0x1800e280f  mov     [rsp+90h+dwFlags], r14d; cchCount2
0x1800e2814  lea     edx, [r15+1]; dwCmpFlags
0x1800e2818  mov     r9d, r14d; cchCount1
0x1800e281b  mov     [rsp+90h+pcbResult], rax; lpString2
0x1800e2820  mov     r8, rbx; lpString1
0x1800e2823  mov     ecx, 409h; Locale
0x1800e2828  call    cs:__imp_CompareStringW
0x1800e282e  lea     r15, aEcdh; "ECDH"
0x1800e2835  cmp     eax, 2
0x1800e2838  jz      loc_1800E29AC
0x1800e283e  mov     [rsp+90h+dwFlags], r14d; cchCount2
0x1800e2843  lea     edx, [r14+2]; dwCmpFlags
0x1800e2847  mov     r9d, r14d; cchCount1
0x1800e284a  mov     [rsp+90h+pcbResult], r15; lpString2
0x1800e284f  mov     r8, rbx; lpString1
0x1800e2852  mov     ecx, 409h; Locale
0x1800e2857  call    cs:__imp_CompareStringW
0x1800e285d  cmp     eax, 2
0x1800e2860  jz      loc_1800E29AC
0x1800e2866  mov     rcx, rbx; pvKey
0x1800e2869  call    I_CryptIsCNGPQAlgorithm
0x1800e286e  test    eax, eax
0x1800e2870  jz      loc_1800E2AAD
0x1800e2876  mov     rcx, [rbp+60h+var_50]
0x1800e287a  lea     rax, [rbp+60h+var_5C]
0x1800e287e  mov     [rsp+90h+dwFlags], esi; dwFlags
0x1800e2882  lea     rdx, aParametersetna; "ParameterSetName"
0x1800e2889  xor     r9d, r9d; cbOutput
0x1800e288c  mov     [rsp+90h+pcbResult], rax; pcbResult
0x1800e2891  xor     r8d, r8d; pbOutput
0x1800e2894  mov     rcx, [rcx+8]; hObject
0x1800e2898  call    cs:__imp_NCryptGetProperty
0x1800e289e  mov     r15d, eax
0x1800e28a1  test    eax, eax
0x1800e28a3  jnz     loc_1800E296C
0x1800e28a9  mov     r14d, [rbp+60h+var_5C]
0x1800e28ad  test    r14, r14
0x1800e28b0  jz      short loc_1800E290C
0x1800e28b2  cmp     r14, cs:g_ulMaxStackAllocSize
0x1800e28b9  ja      short loc_1800E290C
0x1800e28bb  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800e28c2  add     rcx, 8
0x1800e28c6  add     rcx, r14
0x1800e28c9  cmp     rcx, r14
0x1800e28cc  jb      short loc_1800E290C
0x1800e28ce  call    VerifyStackAvailable
0x1800e28d3  test    eax, eax
0x1800e28d5  jz      short loc_1800E290C
0x1800e28d7  lea     rax, [r14+8]
0x1800e28db  lea     rcx, [rax+0Fh]
0x1800e28df  cmp     rcx, rax
0x1800e28e2  ja      short loc_1800E28E7
0x1800e28e4  mov     rcx, r12
0x1800e28e7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800e28eb  mov     rax, rcx
0x1800e28ee  call    _alloca_probe
0x1800e28f3  sub     rsp, rcx
0x1800e28f6  lea     rdi, [rsp+90h+cbOutput]
0x1800e28fb  test    rdi, rdi
0x1800e28fe  jz      short loc_1800E290C
0x1800e2900  mov     dword ptr [rdi], 6B637453h
0x1800e2906  add     rdi, 8
0x1800e290a  jnz     short loc_1800E2933
0x1800e290c  lea     rcx, [r14+8]
0x1800e2910  cmp     rcx, r14
0x1800e2913  jb      short loc_1800E2933
0x1800e2915  mov     rax, cs:g_pfnAllocate
0x1800e291c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2921  mov     rdi, rax
0x1800e2924  test    rax, rax
0x1800e2927  jz      short loc_1800E2933
0x1800e2929  mov     dword ptr [rax], 70616548h
0x1800e292f  add     rdi, 8
0x1800e2933  test    rdi, rdi
0x1800e2936  jz      short loc_1800E296C
0x1800e2938  mov     r9d, [rbp+60h+var_5C]; cbOutput
0x1800e293c  lea     rax, [rbp+60h+var_5C]
0x1800e2940  mov     [rsp+90h+dwFlags], esi; dwFlags
0x1800e2944  lea     rdx, aParametersetna; "ParameterSetName"
0x1800e294b  mov     [rsp+90h+pcbResult], rax; pcbResult
0x1800e2950  mov     r8, rdi; pbOutput
0x1800e2953  mov     rax, [rbp+60h+var_50]
0x1800e2957  mov     rcx, [rax+8]; hObject
0x1800e295b  call    cs:__imp_NCryptGetProperty
0x1800e2961  mov     r15d, eax
0x1800e2964  test    eax, eax
0x1800e2966  jz      loc_1800E2AA2
0x1800e296c  mov     ecx, r15d; dwErrCode
0x1800e296f  call    cs:__imp_SetLastError
0x1800e2975  call    cs:__imp_GetLastError
0x1800e297b  mov     r15d, eax
0x1800e297e  xor     r14d, r14d
0x1800e2981  test    rbx, rbx
0x1800e2984  jz      loc_1800E2EBF
0x1800e298a  lea     rcx, [rbx-8]
0x1800e298e  mov     ebx, 70616548h
0x1800e2993  cmp     [rcx], ebx
0x1800e2995  jnz     loc_1800E2EC4
0x1800e299b  mov     rax, cs:g_pfnFree
0x1800e29a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e29a7  jmp     loc_1800E2EC4
0x1800e29ac  lea     rax, [rbp+60h+var_58]
0x1800e29b0  mov     [rsp+90h+dwFlags], esi; dwFlags
0x1800e29b4  mov     [rsp+90h+pcbResult], rax; pcbResult
0x1800e29b9  lea     rdx, aEcccurvename; "ECCCurveName"
0x1800e29c0  mov     rax, [rbp+60h+var_50]
0x1800e29c4  xor     r9d, r9d; cbOutput
0x1800e29c7  xor     r8d, r8d; pbOutput
0x1800e29ca  mov     rcx, [rax+8]; hObject
0x1800e29ce  call    cs:__imp_NCryptGetProperty
0x1800e29d4  mov     r15d, eax
0x1800e29d7  test    eax, eax
0x1800e29d9  jnz     short loc_1800E296C
0x1800e29db  mov     r14d, [rbp+60h+var_58]
0x1800e29df  test    r14, r14
0x1800e29e2  jz      short loc_1800E2A3E
0x1800e29e4  cmp     r14, cs:g_ulMaxStackAllocSize
0x1800e29eb  ja      short loc_1800E2A3E
0x1800e29ed  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800e29f4  add     rcx, 8
0x1800e29f8  add     rcx, r14
0x1800e29fb  cmp     rcx, r14
0x1800e29fe  jb      short loc_1800E2A3E
0x1800e2a00  call    VerifyStackAvailable
0x1800e2a05  test    eax, eax
0x1800e2a07  jz      short loc_1800E2A3E
0x1800e2a09  lea     rax, [r14+8]
0x1800e2a0d  lea     rcx, [rax+0Fh]
0x1800e2a11  cmp     rcx, rax
0x1800e2a14  ja      short loc_1800E2A19
0x1800e2a16  mov     rcx, r12
0x1800e2a19  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800e2a1d  mov     rax, rcx
0x1800e2a20  call    _alloca_probe
0x1800e2a25  sub     rsp, rcx
0x1800e2a28  lea     rsi, [rsp+90h+cbOutput]
0x1800e2a2d  test    rsi, rsi
0x1800e2a30  jz      short loc_1800E2A3E
0x1800e2a32  mov     dword ptr [rsi], 6B637453h
0x1800e2a38  add     rsi, 8
0x1800e2a3c  jnz     short loc_1800E2A65
0x1800e2a3e  lea     rcx, [r14+8]
0x1800e2a42  cmp     rcx, r14
0x1800e2a45  jb      short loc_1800E2A65
0x1800e2a47  mov     rax, cs:g_pfnAllocate
0x1800e2a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2a53  mov     rsi, rax
0x1800e2a56  test    rax, rax
0x1800e2a59  jz      short loc_1800E2A65
0x1800e2a5b  mov     dword ptr [rax], 70616548h
0x1800e2a61  add     rsi, 8
0x1800e2a65  test    rsi, rsi
0x1800e2a68  jz      loc_1800E296C
0x1800e2a6e  mov     r9d, [rbp+60h+var_58]; cbOutput
0x1800e2a72  lea     rax, [rbp+60h+var_58]
0x1800e2a76  mov     [rsp+90h+dwFlags], edi; dwFlags
0x1800e2a7a  lea     rdx, aEcccurvename; "ECCCurveName"
0x1800e2a81  mov     [rsp+90h+pcbResult], rax; pcbResult
0x1800e2a86  mov     r8, rsi; pbOutput
0x1800e2a89  mov     rax, [rbp+60h+var_50]
0x1800e2a8d  mov     rcx, [rax+8]; hObject
0x1800e2a91  call    cs:__imp_NCryptGetProperty
0x1800e2a97  mov     r15d, eax
0x1800e2a9a  test    eax, eax
0x1800e2a9c  jnz     loc_1800E296C
0x1800e2aa2  lea     r15, aEcdh; "ECDH"
0x1800e2aa9  or      r14d, 0FFFFFFFFh
0x1800e2aad  lea     rax, aEcdsa; "ECDSA"
0x1800e2ab4  mov     [rsp+90h+dwFlags], r14d; cchCount2
0x1800e2ab9  mov     r9d, r14d; cchCount1
0x1800e2abc  mov     [rsp+90h+pcbResult], rax; lpString2
0x1800e2ac1  mov     r8, rbx; lpString1
0x1800e2ac4  mov     edx, 1; dwCmpFlags
0x1800e2ac9  mov     ecx, 409h; Locale
0x1800e2ace  call    cs:__imp_CompareStringW
0x1800e2ad4  cmp     eax, 2
0x1800e2ad7  jnz     loc_1800E2E25
0x1800e2add  mov     r8d, 40000003h
0x1800e2ae3  mov     rdx, rsi
0x1800e2ae6  mov     ecx, 80000002h
0x1800e2aeb  jmp     loc_1800E2EA1
0x1800e2af0  lea     rdx, aAlgorithmname; "AlgorithmName"
0x1800e2af7  call    cs:__imp_BCryptGetProperty
0x1800e2afd  test    eax, eax
0x1800e2aff  jz      short loc_1800E2B0A
0x1800e2b01  xor     ebx, ebx
0x1800e2b03  mov     ecx, eax
0x1800e2b05  jmp     loc_1800E296F
0x1800e2b0a  mov     r14d, [rbp+60h+cbOutput]
0x1800e2b0e  xor     ebx, ebx
0x1800e2b10  add     r14, 2
0x1800e2b14  mov     r12, 0FFFFFFFFFFFFFF0h
0x1800e2b1e  cmp     r14, cs:g_ulMaxStackAllocSize
0x1800e2b25  ja      short loc_1800E2B78
0x1800e2b27  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800e2b2e  add     rcx, 8
0x1800e2b32  add     rcx, r14
0x1800e2b35  cmp     rcx, r14
0x1800e2b38  jb      short loc_1800E2B78
0x1800e2b3a  call    VerifyStackAvailable
0x1800e2b3f  test    eax, eax
0x1800e2b41  jz      short loc_1800E2B78
0x1800e2b43  lea     rax, [r14+8]
0x1800e2b47  lea     rcx, [rax+0Fh]
0x1800e2b4b  cmp     rcx, rax
0x1800e2b4e  ja      short loc_1800E2B53
0x1800e2b50  mov     rcx, r12
0x1800e2b53  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800e2b57  mov     rax, rcx
0x1800e2b5a  call    _alloca_probe
0x1800e2b5f  sub     rsp, rcx
0x1800e2b62  lea     rbx, [rsp+90h+cbOutput]
0x1800e2b67  test    rbx, rbx
0x1800e2b6a  jz      short loc_1800E2B78
0x1800e2b6c  mov     dword ptr [rbx], 6B637453h
  ... truncated ...
```
