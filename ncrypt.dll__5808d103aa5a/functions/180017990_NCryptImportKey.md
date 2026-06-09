# NCryptImportKey

- ea: `0x180017990`
- end: `0x1800182bc`
- name: `NCryptImportKey`
- size: `2348`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_PROV_HANDLE hProvider, NCRYPT_KEY_HANDLE hImportKey, LPCWSTR pszBlobType, NCryptBufferDesc *pParameterList, NCRYPT_KEY_HANDLE *phKey, PBYTE pbData, DWORD cbData, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `24`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180001044`
- `0x180009cd0`
- `0x18000a650`
- `0x18000a670`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000cb50`
- `0x18000e120`
- `0x180010684`
- `0x180011cb0`
- `0x1800144b0`
- `0x180015c4c`
- `0x180015e8c`
- `0x180017990`
- `0x180018350`
- `0x180018e18`
- `0x18001ca50`
- `0x18001cb84`
- `0x18001f145`
- `0x18001f175`
- `0x18001f18d`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x180017a96`
- `ntdll!RtlDllShutdownInProgress` at `0x180017a96`

## string_xrefs

- `0x180017a69`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180017bcf`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180017c2b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800180d9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180018102`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180018183`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptImportKey(
        NCRYPT_PROV_HANDLE hProvider,
        NCRYPT_KEY_HANDLE hImportKey,
        LPCWSTR pszBlobType,
        NCryptBufferDesc *pParameterList,
        NCRYPT_KEY_HANDLE *phKey,
        PBYTE pbData,
        DWORD cbData,
        DWORD dwFlags)
{
  __int64 v8; // rsi
  _QWORD *v11; // r12
  __int64 *v12; // rdi
  int v13; // r8d
  __int64 v14; // r13
  unsigned int v15; // ebx
  __int64 v16; // rdx
  DWORD v17; // esi
  __int64 v18; // r9
  __int64 v19; // rcx
  int v20; // eax
  unsigned int v21; // eax
  unsigned __int64 v22; // rbx
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  __int64 *v27; // rax
  PBYTE v28; // rbx
  unsigned __int64 v29; // rbx
  __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  void *v32; // rsp
  void *v33; // rsp
  __int64 *v34; // rax
  unsigned __int64 v35; // rbx
  __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  void *v38; // rsp
  void *v39; // rsp
  __int64 *v40; // rax
  __int64 v41; // r15
  __int64 v42; // rax
  _QWORD *i; // rax
  __int64 v44; // rdx
  unsigned int v45; // eax
  int v46; // r9d
  _BYTE *v47; // rax
  __int64 v48; // rdx
  const wchar_t *v49; // rdx
  int v50; // r8d
  _BYTE v52[32]; // [rsp+0h] [rbp-50h] BYREF
  unsigned int v53; // [rsp+50h] [rbp+0h] BYREF
  __int64 v54; // [rsp+58h] [rbp+8h] BYREF
  PBYTE v55; // [rsp+60h] [rbp+10h] BYREF
  unsigned int v56; // [rsp+68h] [rbp+18h] BYREF
  int v57; // [rsp+6Ch] [rbp+1Ch] BYREF
  __int64 v58; // [rsp+70h] [rbp+20h] BYREF
  __int64 v59; // [rsp+78h] [rbp+28h] BYREF
  NCRYPT_KEY_HANDLE v60; // [rsp+80h] [rbp+30h]
  _BYTE v61[32]; // [rsp+90h] [rbp+40h] BYREF
  __int64 *v62; // [rsp+B0h] [rbp+60h]
  __int64 v63; // [rsp+B8h] [rbp+68h]
  __int64 *v64; // [rsp+C0h] [rbp+70h]
  __int64 v65; // [rsp+C8h] [rbp+78h]
  unsigned int *v66; // [rsp+D0h] [rbp+80h]
  __int64 v67; // [rsp+D8h] [rbp+88h]
  char v68[16]; // [rsp+E0h] [rbp+90h] BYREF
  char v69[16]; // [rsp+F0h] [rbp+A0h] BYREF
  char v70[16]; // [rsp+100h] [rbp+B0h] BYREF
  PBYTE *v71; // [rsp+110h] [rbp+C0h]
  __int64 v72; // [rsp+118h] [rbp+C8h]
  char v73[16]; // [rsp+120h] [rbp+D0h] BYREF
  __int64 *v74; // [rsp+130h] [rbp+E0h]
  __int64 v75; // [rsp+138h] [rbp+E8h]
  char v76[16]; // [rsp+140h] [rbp+F0h] BYREF
  _WORD v77[512]; // [rsp+150h] [rbp+100h] BYREF

  v8 = 0;
  v60 = hImportKey;
  v59 = (__int64)phKey;
  v55 = pbData;
  v54 = 0;
  v11 = 0;
  v53 = 0;
  v12 = 0;
  v56 = 0;
  v58 = (__int64)pParameterList;
  memset_0(v77, 0, sizeof(v77));
  v57 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v13, hProvider, (__int64)pszBlobType, dwFlags);
  if ( !pszBlobType || !phKey )
  {
    v14 = 0;
    v15 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 3025);
    goto LABEL_8;
  }
  v14 = ValidateAndReferenceProvider(hProvider);
  if ( v14 )
  {
    if ( v60 )
    {
      v54 = ValidateClientKeyHandle(v60);
      v8 = v54;
      if ( !v54 )
      {
        v15 = -2146893786;
        DebugTraceError(
          2148073510LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
          3045);
LABEL_108:
        DereferenceProvider(v14);
        goto LABEL_8;
      }
    }
    Feature_PKCS11_Shielded_Secrets__private_ReportDeviceUsage();
    v17 = cbData;
    if ( !wcscmp_0(pszBlobType, L"PUBLICBLOB") )
    {
      if ( cbData < 0x14 )
      {
        v15 = -2146893785;
        v18 = 3078;
        v19 = 2148073511LL;
LABEL_23:
        DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v18);
        v8 = v54;
        goto LABEL_108;
      }
      v20 = *((_DWORD *)pbData + 2);
      switch ( v20 )
      {
        case 826364754:
          pszBlobType = L"CAPIPUBLICBLOB";
          break;
        case 827544388:
LABEL_28:
          pszBlobType = L"CAPIDSAPUBLICBLOB";
          break;
        case 860374016:
          pszBlobType = L"CAPIDHPUBLICBLOB";
          break;
        case 861098820:
          goto LABEL_28;
        default:
          break;
      }
    }
    if ( !wcscmp_0(pszBlobType, L"CAPIPUBLICBLOB") )
    {
      v21 = ConvertLegacyRsaPublicBlob(pbData, cbData, 0, 0, &v53, 0);
      v15 = v21;
      if ( v21 )
      {
        v18 = 3113;
LABEL_34:
        v19 = v21;
        goto LABEL_23;
      }
      v22 = v53;
      if ( !v53
        || v53 > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)v53 + g_ulAdditionalProbeSize + 8 < v53
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_124;
      }
      v23 = v22 + 23;
      if ( v22 + 23 <= v22 + 8 )
        v23 = 0xFFFFFFFFFFFFFF0LL;
      v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
      v25 = alloca(v24);
      v26 = alloca(v24);
      v12 = (__int64 *)&v53;
      if ( v52 == (_BYTE *)-80LL || (v53 = 1801679955, (v12 = &v54) == 0) )
      {
LABEL_124:
        if ( v22 + 8 >= v22 )
        {
          v27 = (__int64 *)((__int64 (*)(void))g_pfnAllocate)();
          v12 = v27;
          if ( v27 )
          {
            *(_DWORD *)v27 = 1885431112;
            v12 = v27 + 1;
          }
        }
      }
      if ( !v12 )
      {
        v18 = 3121;
LABEL_48:
        v15 = -2146893810;
        v19 = 2148073486LL;
        goto LABEL_23;
      }
      v21 = ConvertLegacyRsaPublicBlob(pbData, cbData, v12, v53, &v53, &v56);
      v15 = v21;
      if ( v21 )
      {
        v18 = 3134;
        goto LABEL_34;
      }
      v17 = v53;
      pszBlobType = L"RSAPUBLICBLOB";
      v28 = (PBYTE)v12;
      v55 = (PBYTE)v12;
    }
    else if ( !wcscmp_0(pszBlobType, L"CAPIDSAPUBLICBLOB") || !wcscmp_0(pszBlobType, L"V2CAPIDSAPUBLICBLOB") )
    {
      v21 = ConvertLegacyDsaPublicBlob(pbData, cbData, 0, 0, &v53);
      v15 = v21;
      if ( v21 )
      {
        v18 = 3153;
        goto LABEL_34;
      }
      v35 = v53;
      if ( !v53
        || v53 > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)v53 + g_ulAdditionalProbeSize + 8 < v53
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_125;
      }
      v36 = v35 + 23;
      if ( v35 + 23 <= v35 + 8 )
        v36 = 0xFFFFFFFFFFFFFF0LL;
      v37 = v36 & 0xFFFFFFFFFFFFFFF0uLL;
      v38 = alloca(v37);
      v39 = alloca(v37);
      v12 = (__int64 *)&v53;
      if ( v52 == (_BYTE *)-80LL || (v53 = 1801679955, (v12 = &v54) == 0) )
      {
LABEL_125:
        if ( v35 + 8 >= v35 )
        {
          v40 = (__int64 *)((__int64 (*)(void))g_pfnAllocate)();
          v12 = v40;
          if ( v40 )
          {
            *(_DWORD *)v40 = 1885431112;
            v12 = v40 + 1;
          }
        }
      }
      if ( !v12 )
      {
        v18 = 3161;
        goto LABEL_48;
      }
      v21 = ConvertLegacyDsaPublicBlob(pbData, cbData, v12, v53, &v53);
      v15 = v21;
      if ( v21 )
      {
        v18 = 3173;
        goto LABEL_34;
      }
      v17 = v53;
      pszBlobType = L"DSAPUBLICBLOB";
      v28 = (PBYTE)v12;
      v55 = (PBYTE)v12;
    }
    else if ( !wcscmp_0(pszBlobType, L"CAPIDHPUBLICBLOB") )
    {
      v21 = ConvertLegacyDhPublicBlob(pbData, cbData, 0, 0, &v53);
      v15 = v21;
      if ( v21 )
      {
        v18 = 3191;
        goto LABEL_34;
      }
      v29 = v53;
      if ( !v53
        || v53 > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)v53 + g_ulAdditionalProbeSize + 8 < v53
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_126;
      }
      v30 = v29 + 23;
      if ( v29 + 23 <= v29 + 8 )
        v30 = 0xFFFFFFFFFFFFFF0LL;
      v31 = v30 & 0xFFFFFFFFFFFFFFF0uLL;
      v32 = alloca(v31);
      v33 = alloca(v31);
      v12 = (__int64 *)&v53;
      if ( v52 == (_BYTE *)-80LL || (v53 = 1801679955, (v12 = &v54) == 0) )
      {
LABEL_126:
        if ( v29 + 8 >= v29 )
        {
          v34 = (__int64 *)((__int64 (*)(void))g_pfnAllocate)();
          v12 = v34;
          if ( v34 )
          {
            *(_DWORD *)v34 = 1885431112;
            v12 = v34 + 1;
          }
        }
      }
      if ( !v12 )
      {
        v18 = 3199;
        goto LABEL_48;
      }
      v21 = ConvertLegacyDhPublicBlob(pbData, cbData, v12, v53, &v53);
      v15 = v21;
      if ( v21 )
      {
        v18 = 3211;
        goto LABEL_34;
      }
      v17 = v53;
      pszBlobType = L"DHPUBLICBLOB";
      v28 = (PBYTE)v12;
      v55 = (PBYTE)v12;
    }
    else
    {
      v28 = pbData;
    }
    v41 = 48;
    v42 = SafeAllocaAllocateFromHeap(48);
    v11 = (_QWORD *)v42;
    if ( v42 )
    {
      *(_OWORD *)v42 = 0;
      *(_OWORD *)(v42 + 16) = 0;
      *(_OWORD *)(v42 + 32) = 0;
      *(_DWORD *)v42 = 1145307138;
      *(_QWORD *)(v42 + 8) = v14;
      for ( i = (_QWORD *)(v42 + 16); ; i = v11 + 2 )
      {
        v44 = v60 ? *(_QWORD *)(v54 + 16) : 0LL;
        v45 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPCWSTR, __int64, _QWORD *, PBYTE, DWORD, DWORD))(v14 + 160))(
                *(_QWORD *)(v14 + 272),
                v44,
                pszBlobType,
                v58,
                i,
                v28,
                v17,
                dwFlags);
        v15 = v45;
        if ( v45 != -2146893778 )
          break;
        if ( (dwFlags & 0x40) != 0 )
        {
          v15 = -2146893790;
          DebugTraceError(
            2148073506LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            3260);
          goto LABEL_105;
        }
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(v14 + 192))(
                *(_QWORD *)(v14 + 272),
                0,
                L"NCryptImportKey",
                0);
        if ( v15 )
          goto LABEL_104;
        v28 = v55;
      }
      if ( !v45 )
      {
        v8 = v54;
        v15 = 0;
        *(_QWORD *)v59 = v11;
        goto LABEL_8;
      }
LABEL_104:
      DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 3278);
      EtwLogNCryptOperationFailed(13, *(_QWORD *)(v11[1] + 280LL), v11[3], v46, v15);
LABEL_105:
      v47 = v11;
      do
      {
        *v47++ = 0;
        --v41;
      }
      while ( v41 );
      MSCryptFree(v11);
      v8 = v54;
      goto LABEL_108;
    }
    v18 = 3230;
    goto LABEL_48;
  }
  v15 = -2146893786;
  DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 3034);
LABEL_8:
  if ( (unsigned int)Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline() && !RtlDllShutdownInProgress() )
  {
    v53 = 0;
    if ( v11 && v14 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _WORD *, int, unsigned int *, _DWORD))(v14 + 56))(
        *(_QWORD *)(v14 + 272),
        v11[2],
        L"Algorithm Name",
        v77,
        1024,
        &v53,
        0);
      (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *, int *, int, unsigned int *, _DWORD))(v14 + 56))(
        *(_QWORD *)(v14 + 272),
        v11[2],
        L"Length",
        &v57,
        4,
        &v53,
        0);
    }
    if ( (unsigned int)dword_18002A078 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18002A078, 0x400000000000LL) )
    {
      v59 = 1;
      v62 = &v59;
      v64 = &v58;
      v66 = &v56;
      v63 = 8;
      v58 = 0x1000000;
      v65 = 8;
      v56 = v15;
      v67 = 4;
      if ( v14 )
        v16 = *(_QWORD *)(v14 + 280);
      else
        v16 = 0;
      tlgCreate1Sz_wchar_t(v68, v16);
      if ( v8 )
        v48 = *(_QWORD *)(v8 + 24);
      else
        v48 = 0;
      tlgCreate1Sz_wchar_t(v69, v48);
      tlgCreate1Sz_wchar_t(v70, pszBlobType);
      v49 = v77;
      LODWORD(v55) = dwFlags;
      v71 = &v55;
      if ( !v77[0] )
        v49 = L"UNKNOWN";
      v72 = 4;
      tlgCreate1Sz_wchar_t(v73, v49);
      LODWORD(v54) = v57;
      v74 = &v54;
      v75 = 4;
      tlgCreate1Sz_wchar_t(v76, g_processImageNameNcrypt);
      tlgWriteAgg((unsigned int)v61, (unsigned int)byte_180024449, v50, 12, (__int64)v61);
    }
  }
  if ( v12 && *((_DWORD *)v12 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return NormalizeNteStatus(v15);
}

```

## disassembly

```asm
0x180017990  push    rbp
0x180017992  push    rbx
0x180017993  push    rsi
0x180017994  push    rdi
0x180017995  push    r12
0x180017997  push    r13
0x180017999  push    r14
0x18001799b  push    r15
0x18001799d  sub     rsp, 568h
0x1800179a4  lea     rbp, [rsp+50h]
0x1800179a9  mov     rax, cs:__security_cookie
0x1800179b0  xor     rax, rbp
0x1800179b3  mov     [rbp+550h+var_50], rax
0x1800179ba  mov     r13, [rbp+550h+phKey]
0x1800179c1  xor     esi, esi
0x1800179c3  mov     r15, [rbp+550h+pbData]
0x1800179ca  mov     r14, r8
0x1800179cd  mov     [rbp+550h+var_520], rdx
0x1800179d1  mov     rbx, rcx
0x1800179d4  xor     edx, edx; Val
0x1800179d6  mov     [rbp+550h+var_528], r13
0x1800179da  mov     r8d, 400h; Size
0x1800179e0  mov     [rbp+550h+var_540], r15
0x1800179e4  lea     rcx, [rbp+550h+var_450]; void *
0x1800179eb  mov     [rbp+550h+var_548], rsi
0x1800179ef  xor     r12d, r12d
0x1800179f2  mov     [rbp+550h+var_550], esi
0x1800179f5  xor     edi, edi
0x1800179f7  mov     [rbp+550h+var_538], esi
0x1800179fa  mov     [rbp+550h+var_530], r9
0x1800179fe  call    memset_0
0x180017a03  mov     [rbp+550h+var_534], esi
0x180017a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a0d  lea     rax, WPP_GLOBAL_Control
0x180017a14  cmp     rcx, rax
0x180017a17  jz      short loc_180017A3D
0x180017a19  test    byte ptr [rcx+1Ch], 4
0x180017a1d  jz      short loc_180017A3D
0x180017a1f  mov     eax, [rbp+550h+dwFlags]
0x180017a25  lea     edx, [rsi+1Bh]
0x180017a28  mov     rcx, [rcx+10h]
0x180017a2c  mov     r9, rbx
0x180017a2f  mov     dword ptr [rsp+5A0h+var_578], eax
0x180017a33  mov     [rsp+5A0h+var_580], r14
0x180017a38  call    WPP_SF_PSD
0x180017a3d  test    r14, r14
0x180017a40  jz      loc_180018180
0x180017a46  test    r13, r13
0x180017a49  jz      loc_180018180
0x180017a4f  mov     rcx, rbx
0x180017a52  call    ValidateAndReferenceProvider
0x180017a57  mov     r13, rax
0x180017a5a  test    rax, rax
0x180017a5d  jnz     loc_180017BAC
0x180017a63  mov     r9d, 0BDAh
0x180017a69  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017a70  lea     rdx, aStatus; "Status"
0x180017a77  mov     ecx, 80090026h
0x180017a7c  mov     ebx, 80090026h
0x180017a81  call    DebugTraceError
0x180017a86  xor     r15d, r15d
0x180017a89  call    Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline
0x180017a8e  test    eax, eax
0x180017a90  jz      loc_180018275
0x180017a96  call    cs:__imp_RtlDllShutdownInProgress
0x180017a9c  test    al, al
0x180017a9e  jnz     loc_180018275
0x180017aa4  mov     [rbp+550h+var_550], r15d
0x180017aa8  test    r12, r12
0x180017aab  jz      short loc_180017B21
0x180017aad  test    r13, r13
0x180017ab0  jz      short loc_180017B21
0x180017ab2  mov     rdx, [r12+10h]
0x180017ab7  lea     rax, [rbp+550h+var_550]
0x180017abb  mov     rcx, [r13+110h]
0x180017ac2  lea     r9, [rbp+550h+var_450]
0x180017ac9  mov     [rsp+5A0h+var_570], r15d
0x180017ace  lea     r8, aAlgorithmName; "Algorithm Name"
0x180017ad5  mov     [rsp+5A0h+var_578], rax
0x180017ada  mov     rax, [r13+38h]
0x180017ade  mov     dword ptr [rsp+5A0h+var_580], 400h
0x180017ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aeb  mov     rdx, [r12+10h]
0x180017af0  lea     rax, [rbp+550h+var_550]
0x180017af4  mov     rcx, [r13+110h]
0x180017afb  lea     r9, [rbp+550h+var_534]
0x180017aff  mov     [rsp+5A0h+var_570], r15d
0x180017b04  lea     r8, aLength; "Length"
0x180017b0b  mov     [rsp+5A0h+var_578], rax
0x180017b10  mov     rax, [r13+38h]
0x180017b14  mov     dword ptr [rsp+5A0h+var_580], 4
0x180017b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b21  mov     eax, cs:dword_18002A078
0x180017b27  cmp     eax, 5
0x180017b2a  jbe     loc_180018275
0x180017b30  mov     rdx, 400000000000h
0x180017b3a  lea     rcx, dword_18002A078
0x180017b41  call    _tlgKeywordOn
0x180017b46  test    al, al
0x180017b48  jz      loc_180018275
0x180017b4e  mov     [rbp+550h+var_528], 1
0x180017b56  lea     rax, [rbp+550h+var_528]
0x180017b5a  mov     [rbp+550h+var_4F0], rax
0x180017b5e  lea     rax, [rbp+550h+var_530]
0x180017b62  mov     [rbp+550h+var_4E0], rax
0x180017b66  lea     rax, [rbp+550h+var_538]
0x180017b6a  mov     [rbp+550h+var_4D0], rax
0x180017b71  mov     [rbp+550h+var_4E8], 8
0x180017b79  mov     [rbp+550h+var_530], 1000000h
0x180017b81  mov     [rbp+550h+var_4D8], 8
0x180017b89  mov     [rbp+550h+var_538], ebx
0x180017b8c  mov     [rbp+550h+var_4C8], 4
0x180017b97  test    r13, r13
0x180017b9a  jz      loc_1800181AE
0x180017ba0  mov     rdx, [r13+118h]
0x180017ba7  jmp     loc_1800181B1
0x180017bac  mov     rax, [rbp+550h+var_520]
0x180017bb0  test    rax, rax
0x180017bb3  jz      short loc_180017BF1
0x180017bb5  mov     rcx, rax
0x180017bb8  call    ValidateClientKeyHandle
0x180017bbd  mov     [rbp+550h+var_548], rax
0x180017bc1  mov     rsi, rax
0x180017bc4  test    rax, rax
0x180017bc7  jnz     short loc_180017BF1
0x180017bc9  mov     r9d, 0BE5h
0x180017bcf  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017bd6  lea     rdx, aStatus; "Status"
0x180017bdd  mov     ecx, 80090026h
0x180017be2  mov     ebx, 80090026h
0x180017be7  call    DebugTraceError
0x180017bec  jmp     loc_18001815D
0x180017bf1  call    Feature_PKCS11_Shielded_Secrets__private_ReportDeviceUsage
0x180017bf6  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180017bfd  mov     rcx, r14; String1
0x180017c00  call    wcscmp_0
0x180017c05  mov     esi, [rbp+550h+cbData]
0x180017c0b  lea     rdx, aCapipublicblob; "CAPIPUBLICBLOB"
0x180017c12  test    eax, eax
0x180017c14  jnz     short loc_180017C7C
0x180017c16  cmp     esi, 14h
0x180017c19  jnb     short loc_180017C47
0x180017c1b  mov     ebx, 80090027h
0x180017c20  mov     r9d, 0C06h
0x180017c26  mov     ecx, 80090027h
0x180017c2b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017c32  lea     rdx, aStatus; "Status"
0x180017c39  call    DebugTraceError
0x180017c3e  mov     rsi, [rbp+550h+var_548]
0x180017c42  jmp     loc_18001815D
0x180017c47  mov     eax, [r15+8]
0x180017c4b  cmp     eax, 31415352h
0x180017c50  jz      short loc_180017C79
0x180017c52  cmp     eax, 31535344h
0x180017c57  jz      short loc_180017C67
0x180017c59  cmp     eax, 33484400h
0x180017c5e  jz      short loc_180017C70
0x180017c60  cmp     eax, 33535344h
0x180017c65  jnz     short loc_180017C7C
0x180017c67  lea     r14, aCapidsapublicb; "CAPIDSAPUBLICBLOB"
0x180017c6e  jmp     short loc_180017C7C
0x180017c70  lea     r14, aCapidhpublicbl; "CAPIDHPUBLICBLOB"
0x180017c77  jmp     short loc_180017C7C
0x180017c79  mov     r14, rdx
0x180017c7c  mov     rcx, r14; String1
0x180017c7f  call    wcscmp_0
0x180017c84  test    eax, eax
0x180017c86  jnz     loc_180017DB1
0x180017c8c  lea     rax, [rbp+550h+var_550]
0x180017c90  mov     [rsp+5A0h+var_578], rdi
0x180017c95  xor     r9d, r9d
0x180017c98  mov     [rsp+5A0h+var_580], rax
0x180017c9d  xor     r8d, r8d
0x180017ca0  mov     edx, esi
0x180017ca2  mov     rcx, r15
0x180017ca5  call    ConvertLegacyRsaPublicBlob
0x180017caa  mov     ebx, eax
0x180017cac  test    eax, eax
0x180017cae  jz      short loc_180017CBD
0x180017cb0  mov     r9d, 0C29h
0x180017cb6  mov     ecx, eax
0x180017cb8  jmp     loc_180017C2B
0x180017cbd  mov     ebx, [rbp+550h+var_550]
0x180017cc0  test    rbx, rbx
0x180017cc3  jz      short loc_180017D26
0x180017cc5  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180017ccc  ja      short loc_180017D26
0x180017cce  mov     rcx, cs:g_ulAdditionalProbeSize
0x180017cd5  add     rcx, 8
0x180017cd9  add     rcx, rbx
0x180017cdc  cmp     rcx, rbx
0x180017cdf  jb      short loc_180017D26
0x180017ce1  call    VerifyStackAvailable
0x180017ce6  test    eax, eax
0x180017ce8  jz      short loc_180017D26
0x180017cea  lea     rax, [rbx+8]
0x180017cee  lea     rcx, [rax+0Fh]
0x180017cf2  cmp     rcx, rax
0x180017cf5  ja      short loc_180017D01
0x180017cf7  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180017d01  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180017d05  mov     rax, rcx
0x180017d08  call    __chkstk_0
0x180017d0d  sub     rsp, rcx
0x180017d10  lea     rdi, [rsp+5A0h+var_550]
0x180017d15  test    rdi, rdi
0x180017d18  jz      short loc_180017D26
0x180017d1a  mov     dword ptr [rdi], 6B637453h
0x180017d20  add     rdi, 8
0x180017d24  jnz     short loc_180017D4D
0x180017d26  lea     rcx, [rbx+8]
0x180017d2a  cmp     rcx, rbx
0x180017d2d  jb      short loc_180017D4D
0x180017d2f  mov     rax, cs:g_pfnAllocate
0x180017d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d3b  mov     rdi, rax
0x180017d3e  test    rax, rax
0x180017d41  jz      short loc_180017D4D
0x180017d43  mov     dword ptr [rax], 70616548h
0x180017d49  add     rdi, 8
0x180017d4d  test    rdi, rdi
0x180017d50  jnz     short loc_180017D67
0x180017d52  mov     r9d, 0C31h
0x180017d58  mov     ebx, 8009000Eh
0x180017d5d  mov     ecx, 8009000Eh
0x180017d62  jmp     loc_180017C2B
0x180017d67  mov     r9d, [rbp+550h+var_550]
0x180017d6b  lea     rax, [rbp+550h+var_538]
0x180017d6f  mov     [rsp+5A0h+var_578], rax
0x180017d74  mov     r8, rdi
0x180017d77  lea     rax, [rbp+550h+var_550]
0x180017d7b  mov     edx, esi
0x180017d7d  mov     rcx, r15
0x180017d80  mov     [rsp+5A0h+var_580], rax
0x180017d85  call    ConvertLegacyRsaPublicBlob
0x180017d8a  mov     ebx, eax
0x180017d8c  test    eax, eax
0x180017d8e  jz      short loc_180017D9B
0x180017d90  mov     r9d, 0C3Eh
0x180017d96  jmp     loc_180017CB6
0x180017d9b  mov     esi, [rbp+550h+var_550]
0x180017d9e  lea     r14, pszBlobType; "RSAPUBLICBLOB"
0x180017da5  mov     rbx, rdi
0x180017da8  mov     [rbp+550h+var_540], rbx
0x180017dac  jmp     loc_18001800C
0x180017db1  lea     rdx, aCapidsapublicb; "CAPIDSAPUBLICBLOB"
0x180017db8  mov     rcx, r14; String1
0x180017dbb  call    wcscmp_0
0x180017dc0  test    eax, eax
0x180017dc2  jz      loc_180017F01
0x180017dc8  lea     rdx, aV2capidsapubli; "V2CAPIDSAPUBLICBLOB"
0x180017dcf  mov     rcx, r14; String1
0x180017dd2  call    wcscmp_0
0x180017dd7  test    eax, eax
0x180017dd9  jz      loc_180017F01
0x180017ddf  lea     rdx, aCapidhpublicbl; "CAPIDHPUBLICBLOB"
0x180017de6  mov     rcx, r14; String1
0x180017de9  call    wcscmp_0
0x180017dee  test    eax, eax
0x180017df0  jnz     loc_180018009
0x180017df6  lea     rax, [rbp+550h+var_550]
0x180017dfa  xor     r9d, r9d
0x180017dfd  xor     r8d, r8d
0x180017e00  mov     [rsp+5A0h+var_580], rax
0x180017e05  mov     edx, esi
0x180017e07  mov     rcx, r15
0x180017e0a  call    ConvertLegacyDhPublicBlob
0x180017e0f  mov     ebx, eax
0x180017e11  test    eax, eax
0x180017e13  jz      short loc_180017E20
0x180017e15  mov     r9d, 0C77h
0x180017e1b  jmp     loc_180017CB6
0x180017e20  mov     ebx, [rbp+550h+var_550]
0x180017e23  test    rbx, rbx
0x180017e26  jz      short loc_180017E89
0x180017e28  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180017e2f  ja      short loc_180017E89
0x180017e31  mov     rcx, cs:g_ulAdditionalProbeSize
0x180017e38  add     rcx, 8
0x180017e3c  add     rcx, rbx
0x180017e3f  cmp     rcx, rbx
0x180017e42  jb      short loc_180017E89
0x180017e44  call    VerifyStackAvailable
0x180017e49  test    eax, eax
0x180017e4b  jz      short loc_180017E89
0x180017e4d  lea     rax, [rbx+8]
0x180017e51  lea     rcx, [rax+0Fh]
0x180017e55  cmp     rcx, rax
0x180017e58  ja      short loc_180017E64
0x180017e5a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180017e64  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180017e68  mov     rax, rcx
0x180017e6b  call    __chkstk_0
0x180017e70  sub     rsp, rcx
0x180017e73  lea     rdi, [rsp+5A0h+var_550]
0x180017e78  test    rdi, rdi
0x180017e7b  jz      short loc_180017E89
0x180017e7d  mov     dword ptr [rdi], 6B637453h
0x180017e83  add     rdi, 8
0x180017e87  jnz     short loc_180017EB0
  ... truncated ...
```
