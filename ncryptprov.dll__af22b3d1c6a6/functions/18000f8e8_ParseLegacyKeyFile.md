# ParseLegacyKeyFile

- ea: `0x18000f8e8`
- end: `0x18001052a`
- name: `ParseLegacyKeyFile`
- size: `3138`
- prototype: `__int64 __fastcall(__int64, int, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e1d4`
- `0x1800115b0`

## callees

- `0x1800086d0`
- `0x18000af80`
- `0x18000b250`
- `0x18000bdd0`
- `0x18000d3d0`
- `0x18000def0`
- `0x18000f8e8`
- `0x180010ad0`
- `0x180010d68`
- `0x18001652c`
- `0x1800398b0`
- `0x18006190c`
- `0x180061ad8`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000fb6b`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000fb6b`
- `ntdll!RtlFreeUnicodeString` at `0x18000ff8b`
- `ntdll!RtlFreeUnicodeString` at `0x18000ff8b`
- `ntdll!RtlInitAnsiString` at `0x18000fb54`
- `ntdll!RtlInitAnsiString` at `0x18000fb54`
- `bcrypt!BCryptImportKeyPair` at `0x18000fdac`
- `bcrypt!BCryptImportKeyPair` at `0x18000fdac`

## string_xrefs

- `0x18000f99a`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18000fc9d`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18000fe1e`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18000fe3e`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18000fe8c`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18000ffc5`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180010038`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x1800101f0`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180010267`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180010405`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`

## pseudocode

```c
__int64 __fastcall ParseLegacyKeyFile(__int64 a1, int a2, unsigned int *a3, unsigned int a4)
{
  unsigned int *v5; // rdi
  unsigned int v6; // eax
  ULONG v7; // esi
  unsigned int v8; // ecx
  unsigned int LegacyUIPolicies; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // r10
  unsigned int v12; // eax
  __int64 v13; // r11
  unsigned int v14; // ecx
  __int64 v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // r13
  unsigned int v18; // ecx
  ULONG v19; // r14d
  unsigned int v20; // eax
  __int64 v21; // r12
  __int64 v22; // r9
  bool v23; // zf
  ULONG v24; // eax
  __int64 v25; // rcx
  char *v26; // r14
  int v27; // edx
  int v28; // edx
  unsigned int v29; // esi
  const WCHAR *v30; // rcx
  unsigned int v31; // eax
  __int64 v32; // rdx
  char *v33; // rax
  unsigned __int64 v34; // rbx
  unsigned __int64 v35; // rcx
  __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  void *v38; // rsp
  void *v39; // rsp
  const char *v40; // rdx
  NTSTATUS v41; // eax
  PWSTR Buffer; // rax
  int v43; // edx
  int v44; // r8d
  void *v45; // rax
  __int64 v46; // rdx
  int v47; // r8d
  ULONG v48; // edi
  unsigned int v49; // eax
  unsigned int *v50; // rdi
  unsigned int v51; // esi
  __int64 v52; // r13
  unsigned int v53; // r14d
  unsigned int v54; // esi
  _QWORD *v55; // rcx
  int v56; // edx
  int v57; // edx
  int v58; // edx
  int v59; // edx
  unsigned int v60; // esi
  ULONG v61; // eax
  int v62; // edx
  int v63; // r8d
  unsigned int v64; // ecx
  __int64 v65; // r9
  __int64 v66; // rcx
  unsigned __int64 v68; // rbx
  unsigned __int64 v69; // rcx
  unsigned int *v70; // rax
  char *v71; // rax
  char *v72; // r13
  __int64 v73; // rcx
  void *v74; // rsp
  void *v75; // rsp
  unsigned int *v76; // r9
  unsigned int *v77; // rcx
  char *v78; // rdx
  char *v79; // rax
  __int64 v80; // r9
  __int64 v81; // rcx
  int v82; // edx
  int v83; // edx
  void *v84; // rax
  __int64 v85; // r13
  __int64 v86; // rdx
  __int64 v87; // rsi
  unsigned __int64 v88; // rbx
  unsigned __int64 v89; // rcx
  __int64 v90; // rcx
  unsigned __int64 v91; // rcx
  void *v92; // rsp
  void *v93; // rsp
  unsigned int *v94; // rax
  unsigned int v95; // eax
  __int64 v96; // r9
  __int64 v97; // r13
  __int64 v98; // rdx
  __int64 v99; // rsi
  unsigned __int64 v100; // rbx
  unsigned __int64 v101; // rcx
  __int64 v102; // rcx
  unsigned __int64 v103; // rcx
  void *v104; // rsp
  void *v105; // rsp
  unsigned int *v106; // rax
  _BYTE v107[32]; // [rsp+0h] [rbp-40h] BYREF
  PUCHAR pbInput; // [rsp+20h] [rbp-20h]
  ULONG cbInput[2]; // [rsp+28h] [rbp-18h]
  ULONG dwFlags; // [rsp+30h] [rbp-10h]
  unsigned int v111; // [rsp+40h] [rbp+0h] BYREF
  ULONG v112; // [rsp+44h] [rbp+4h]
  int v113; // [rsp+48h] [rbp+8h] BYREF
  PCSZ SourceString; // [rsp+50h] [rbp+10h]
  ULONG v115; // [rsp+58h] [rbp+18h]
  int v116; // [rsp+5Ch] [rbp+1Ch] BYREF
  __int64 v117; // [rsp+60h] [rbp+20h]
  LPCWSTR pszBlobType; // [rsp+68h] [rbp+28h]
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp+38h] BYREF
  void *Src; // [rsp+88h] [rbp+48h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+90h] [rbp+50h] BYREF
  void *v122; // [rsp+98h] [rbp+58h]
  __int64 v123; // [rsp+A0h] [rbp+60h]
  unsigned int v124; // [rsp+A8h] [rbp+68h]
  __int64 v125; // [rsp+ACh] [rbp+6Ch] BYREF
  struct _STRING DestinationString; // [rsp+B8h] [rbp+78h] BYREF

  v122 = 0;
  v5 = a3;
  phKey = 0;
  v115 = 0;
  v111 = 0;
  v116 = 0;
  v113 = 0;
  DestinationString = 0;
  UnicodeString = 0;
  if ( !a3 )
  {
    LegacyUIPolicies = -2146893811;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_79;
    dwFlags = 1255;
    *(_QWORD *)cbInput = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c";
    LODWORD(pbInput) = -2146893811;
LABEL_97:
    WPP_SF_sDsd(v10[2], a2, (_DWORD)a3, (unsigned int)"Status", (char)pbInput, *(__int64 *)cbInput, dwFlags);
    goto LABEL_79;
  }
  if ( a4 < 0x28 )
  {
    v80 = 1263;
LABEL_120:
    LegacyUIPolicies = -2146893821;
    v81 = 2148073475LL;
LABEL_122:
    DebugTraceError(v81, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", v80);
    goto LABEL_79;
  }
  a3 = (unsigned int *)a3[6];
  v6 = (_DWORD)a3 + 40;
  if ( (unsigned int)a3 >= 0xFFFFFFD8 )
    goto LABEL_5;
  v7 = v5[9];
  v8 = v7 + v6;
  if ( v7 + v6 < v6 )
    goto LABEL_5;
  v11 = v5[5];
  v12 = v11 + v8;
  if ( (unsigned int)v11 + v8 < v8 )
    goto LABEL_5;
  v13 = v5[2];
  v14 = v13 + v12;
  if ( (unsigned int)v13 + v12 < v12 )
    goto LABEL_5;
  v15 = v5[7];
  v16 = v15 + v14;
  if ( (unsigned int)v15 + v14 < v14
    || (v17 = v5[4], v18 = v16 + v17, v16 + (unsigned int)v17 < v16)
    || (v19 = v5[8], v112 = v19, v20 = v18 + v19, v18 + v19 < v18)
    || (v21 = v5[3], (unsigned int)v21 + v20 < v20) )
  {
LABEL_5:
    LegacyUIPolicies = -2146893821;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_79;
    dwFlags = 1286;
    *(_QWORD *)cbInput = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c";
    LODWORD(pbInput) = -2146893821;
    goto LABEL_97;
  }
  if ( a4 < (unsigned int)v21 + v20 )
  {
    v80 = 1279;
    goto LABEL_120;
  }
  v22 = (__int64)v5 + v15 + v13 + 40;
  v23 = *(_DWORD *)(a1 + 24) == 2;
  v117 = v22;
  if ( v23 )
  {
    v56 = a2 - 1;
    if ( !v56 )
      goto LABEL_59;
    v57 = v56 - 1;
    if ( !v57 )
      goto LABEL_59;
    v58 = v57 - 1;
    if ( v58 )
    {
      v59 = v58 - 9;
      if ( !v59 )
      {
LABEL_59:
        v29 = 196609;
        pszBlobType = L"RSAPUBLICBLOB";
LABEL_60:
        v24 = v112;
        Src = (void *)(v21 + v22);
        v26 = (char *)(v22 + v21 + v17);
        *(_DWORD *)(a1 + 40) = 2;
        goto LABEL_20;
      }
      v82 = v59 - 1;
      if ( v82 && v82 != 5 )
      {
        LegacyUIPolicies = -2146893804;
        goto LABEL_79;
      }
    }
    v29 = 196611;
    pszBlobType = L"DSAPUBLICBLOB";
    goto LABEL_60;
  }
  v24 = v7;
  v112 = v7;
  v25 = v22 + (unsigned int)v17 + (_DWORD)v21 + v19;
  LODWORD(v21) = v11;
  v117 = v25;
  LODWORD(v17) = (_DWORD)a3;
  v26 = (char *)a3 + v25 + v11;
  Src = (void *)(v25 + v11);
  v27 = a2 - 1;
  if ( v27 && (v28 = v27 - 11) != 0 )
  {
    v83 = v28 - 1;
    if ( v83 && v83 != 5 )
    {
      LegacyUIPolicies = -2146893804;
      v80 = 1368;
      v81 = 2148073492LL;
      goto LABEL_122;
    }
    v29 = 196610;
    v30 = L"DHPUBLICBLOB";
  }
  else
  {
    v29 = 196609;
    v30 = L"RSAPUBLICBLOB";
  }
  pszBlobType = v30;
LABEL_20:
  if ( !(_DWORD)v21 || !(_DWORD)v17 || !v24 )
  {
    LegacyUIPolicies = -2146893811;
    goto LABEL_79;
  }
  v31 = FinishNewKeyObject(v29, a1);
  LegacyUIPolicies = v31;
  if ( v31 )
  {
    v80 = 1388;
    v81 = v31;
    goto LABEL_122;
  }
  v33 = 0;
  v34 = v5[2] + 1LL;
  SourceString = 0;
  if ( v34 <= g_ulMaxStackAllocSize )
  {
    v35 = v34 + g_ulAdditionalProbeSize + 8;
    if ( v35 >= v34 )
    {
      if ( (unsigned int)VerifyStackAvailable(v35, v32) )
      {
        v36 = v34 + 23;
        if ( v34 + 23 <= v34 + 8 )
          v36 = 0xFFFFFFFFFFFFFF0LL;
        v37 = v36 & 0xFFFFFFFFFFFFFFF0uLL;
        v38 = alloca(v37);
        v39 = alloca(v37);
        v33 = (char *)&v111;
        SourceString = (PCSZ)&v111;
        if ( v107 != (_BYTE *)-64LL )
        {
          v111 = 1801679955;
          v33 = (char *)&v113;
          SourceString = (PCSZ)&v113;
          if ( &v113 )
            goto LABEL_31;
        }
      }
      else
      {
        v33 = (char *)SourceString;
      }
    }
  }
  if ( v34 + 8 >= v34 )
  {
    v79 = (char *)((__int64 (*)(void))g_pfnAllocate)();
    SourceString = v79;
    if ( !v79 )
      goto LABEL_121;
    *(_DWORD *)v79 = 1885431112;
    v33 = v79 + 8;
    SourceString = v33;
  }
LABEL_31:
  if ( !v33 )
  {
LABEL_121:
    LegacyUIPolicies = -2146893810;
    v80 = 1408;
    v81 = 2148073486LL;
    goto LABEL_122;
  }
  memcpy_0(v33, v5 + 10, v5[2]);
  v40 = SourceString;
  SourceString[v5[2]] = 0;
  RtlInitAnsiString(&DestinationString, v40);
  v41 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
  if ( v41 < 0 )
  {
    DebugTraceError((unsigned int)v41, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", 1424);
    LegacyUIPolicies = -2146893810;
    goto LABEL_53;
  }
  Buffer = UnicodeString.Buffer;
  do
  {
    v43 = *(PWSTR)((char *)Buffer + *(_QWORD *)(a1 + 8) - (unsigned __int64)UnicodeString.Buffer);
    v44 = *Buffer - v43;
    if ( v44 )
      break;
    ++Buffer;
  }
  while ( v43 );
  if ( v44 )
  {
    MSCryptFree(*(_QWORD *)(a1 + 8));
    v84 = (void *)SafeAllocaAllocateFromHeap(UnicodeString.Length + 2LL);
    *(_QWORD *)(a1 + 8) = v84;
    if ( !v84 )
    {
      v65 = 1438;
      goto LABEL_136;
    }
    memcpy_0(v84, UnicodeString.Buffer, UnicodeString.Length + 2LL);
  }
  v45 = (void *)SafeAllocaAllocateFromHeap((unsigned int)v17);
  *(_QWORD *)(a1 + 256) = v45;
  if ( !v45 )
  {
    LegacyUIPolicies = -2146893810;
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_53;
    dwFlags = 1456;
    goto LABEL_73;
  }
  memcpy_0(v45, Src, (unsigned int)v17);
  *(_DWORD *)(a1 + 264) = v17;
  LegacyUIPolicies = ExtractLegacyUIPolicies(a1);
  if ( LegacyUIPolicies )
  {
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      dwFlags = 1469;
      *(_QWORD *)cbInput = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c";
      LODWORD(pbInput) = LegacyUIPolicies;
      goto LABEL_74;
    }
    goto LABEL_53;
  }
  if ( ((unsigned __int8)v26 & 0xF) != 0 )
  {
    v48 = v112;
    v71 = (char *)SafeAllocaAllocateFromHeap(v112);
    v122 = v71;
    v72 = v71;
    if ( !v71 )
    {
      v65 = 1484;
      goto LABEL_136;
    }
    memcpy_0(v71, v26, v48);
    v26 = v72;
  }
  else
  {
    v48 = v112;
  }
  v49 = UnprotectExportabilityFlag(*(unsigned int *)(a1 + 32), v26, v48, &v116);
  LegacyUIPolicies = v49;
  if ( v49 )
  {
    v65 = 1499;
    goto LABEL_141;
  }
  v50 = 0;
  v112 = 0;
  if ( v116 )
    *(_DWORD *)(a1 + 36) = 3;
  v51 = v29 - 196609;
  if ( v51 )
  {
    v60 = v51 - 1;
    if ( v60 )
    {
      if ( v60 != 1 )
      {
LABEL_63:
        v61 = v115;
        goto LABEL_64;
      }
      v85 = v117;
      v49 = ConvertLegacyDsaFileToPublicBlob(v117, (unsigned int)v21, &v113, 0, 0, &v111);
      LegacyUIPolicies = v49;
      if ( v49 )
      {
        v65 = 1605;
        goto LABEL_141;
      }
      v87 = v111;
      v88 = v111;
      if ( !v111 )
        goto LABEL_179;
      if ( v111 > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_179;
      v89 = v111 + g_ulAdditionalProbeSize + 8;
      if ( v89 < v111 || !(unsigned int)VerifyStackAvailable(v89, v86) )
        goto LABEL_179;
      v90 = v87 + 23;
      if ( v87 + 23 <= (unsigned __int64)(v87 + 8) )
        v90 = 0xFFFFFFFFFFFFFF0LL;
      v91 = v90 & 0xFFFFFFFFFFFFFFF0uLL;
      v92 = alloca(v91);
      v93 = alloca(v91);
      v50 = &v111;
      if ( v107 == (_BYTE *)-64LL || (v111 = 1801679955, (v50 = (unsigned int *)&v113) == 0) )
      {
LABEL_179:
        if ( v87 + 8 >= v88 )
        {
          v94 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
          v50 = v94;
          if ( v94 )
          {
            *v94 = 1885431112;
            v50 = v94 + 2;
          }
        }
      }
      if ( !v50 )
      {
        v65 = 1613;
        goto LABEL_136;
      }
      v95 = ConvertLegacyDsaFileToPublicBlob(v85, (unsigned int)v21, &v113, v50, v87, &v111);
      LegacyUIPolicies = v95;
      if ( v95 )
      {
        v96 = 1626;
LABEL_159:
        DebugTraceError(v95, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", v96);
LABEL_67:
        if ( *(v50 - 2) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
        goto LABEL_53;
      }
      v112 = 8;
      goto LABEL_161;
    }
    v97 = v117;
    v49 = ConvertLegacyDhFileToPublicBlob(v117, (unsigned int)v21, &v113, 0, 0, &v111);
    LegacyUIPolicies = v49;
    if ( !v49 )
    {
      v99 = v111;
      v100 = v111;
      if ( !v111 )
        goto LABEL_180;
      if ( v111 > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_180;
      v101 = v111 + g_ulAdditionalProbeSize + 8;
      if ( v101 < v111 || !(unsigned int)VerifyStackAvailable(v101, v98) )
        goto LABEL_180;
      v102 = v99 + 23;
      if ( v99 + 23 <= (unsigned __int64)(v99 + 8) )
        v102 = 0xFFFFFFFFFFFFFF0LL;
      v103 = v102 & 0xFFFFFFFFFFFFFFF0uLL;
      v104 = alloca(v103);
      v105 = alloca(v103);
      v50 = &v111;
      if ( v107 == (_BYTE *)-64LL || (v111 = 1801679955, (v50 = (unsigned int *)&v113) == 0) )
      {
LABEL_180:
        if ( v99 + 8 >= v100 )
        {
          v106 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
          v50 = v106;
          if ( v106 )
          {
            *v106 = 1885431112;
            v50 = v106 + 2;
          }
        }
      }
      if ( v50 )
      {
        v95 = ConvertLegacyDhFileToPublicBlob(v97, (unsigned int)v21, &v113, v50, v99, &v111);
        LegacyUIPolicies = v95;
        if ( v95 )
        {
          v96 = 1668;
          goto LABEL_159;
        }
LABEL_161:
        *(_DWORD *)(a1 + 28) = v113;
        v61 = v111;
LABEL_64:
        LegacyUIPolicies = BCryptImportKeyPair(
                             *(BCRYPT_ALG_HANDLE *)(a1 + 88),
                             0,
                             pszBlobType,
                             &phKey,
                             (PUCHAR)v50,
                             v61,
                             v112);
        if ( LegacyUIPolicies )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v62,
              v63,
              (unsigned int)"Status",
              LegacyUIPolicies,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
              154);
        }
        else
        {
          *(_QWORD *)(a1 + 104) = phKey;
        }
        if ( !v50 )
          goto LABEL_53;
        goto LABEL_67;
      }
      v65 = 1655;
LABEL_136:
      LegacyUIPolicies = -2146893810;
      v66 = 2148073486LL;
      goto LABEL_71;
    }
    v65 = 1647;
LABEL_141:
    v66 = v49;
    goto LABEL_71;
  }
  if ( (unsigned int)v21 >= 0x14 )
  {
    v52 = v117;
    v53 = *(_DWORD *)(v117 + 8);
    v123 = *(_QWORD *)v117;
    v125 = *(_QWORD *)(v117 + 12);
    v54 = (v53 + 7) >> 3;
    v124 = v53;
    if ( (unsigned int)v21 < v54 + 20 )
    {
      LegacyUIPolicies = -2146893821;
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        dwFlags = 1543;
LABEL_50:
        *(_QWORD *)cbInput = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c";
        LODWORD(pbInput) = -2146893821;
LABEL_74:
        WPP_SF_sDsd(v55[2], v46, v47, (unsigned int)"Status", (char)pbInput, *(__int64 *)cbInput, dwFlags);
        goto LABEL_53;
      }
      goto LABEL_53;
    }
    v64 = v54 + 28;
    v115 = v54 + 28;
    if ( v54 + 28 < v54 + 24 )
    {
      LegacyUIPolicies = -2146893821;
      v65 = 1558;
      v66 = 2148073475LL;
LABEL_71:
      DebugTraceError(v66, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", v65);
      goto LABEL_53;
    }
    v68 = v64;
    if ( v64 > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_181;
    v69 = v64 + g_ulAdditionalProbeSize + 8;
    if ( v69 < v68 || !(unsigned int)VerifyStackAvailable(v69, v46) )
      goto LABEL_181;
    v73 = v68 + 23;
    if ( v68 + 23 <= v68 + 8 )
      v73 = 0xFFFFFFFFFFFFFF0LL;
    v74 = alloca(v73 & 0xFFFFFFFFFFFFFFF0uLL);
    v75 = alloca(v73 & 0xFFFFFFFFFFFFFFF0uLL);
    v50 = &v111;
    if ( v107 == (_BYTE *)-64LL || (v111 = 1801679955, (v50 = (unsigned int *)&v113) == 0) )
    {
LABEL_181:
      if ( v68 + 8 >= v68 )
      {
        v70 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
        v50 = v70;
        if ( v70 )
        {
          *v70 = 1885431112;
          v50 = v70 + 2;
        }
      }
    }
    if ( v50 )
    {
      v76 = v50 + 6;
      *v50 = 826364754;
      v77 = (unsigned int *)((char *)v50 + 27);
      v50[1] = v53;
      v50[2] = 4;
      v78 = (char *)&v125 + 4;
      v50[3] = v54;
      *((_QWORD *)v50 + 2) = 0;
      while ( v77 >= v76 )
      {
        *(_BYTE *)v77 = *v78;
        v77 = (unsigned int *)((char *)v77 - 1);
        ++v78;
      }
      ReverseMemCopy((char *)v76 + v50[2], v52 + 20, v54);
      *(_DWORD *)(a1 + 28) = v53;
      goto LABEL_63;
    }
    LegacyUIPolicies = -2146893810;
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_53;
    dwFlags = 1567;
LABEL_73:
    *(_QWORD *)cbInput = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c";
    LODWORD(pbInput) = -2146893810;
    goto LABEL_74;
  }
  LegacyUIPolicies = -2146893821;
  v55 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    dwFlags = 1523;
    goto LABEL_50;
  }
LABEL_53:
  if ( *((_DWORD *)SourceString - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_79:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v122 )
    MSCryptFree(v122);
  return LegacyUIPolicies;
}

```

## disassembly

```asm
0x18000f8e8  push    rbp
0x18000f8ea  push    rsi
0x18000f8eb  push    rdi
0x18000f8ec  push    r12
0x18000f8ee  push    r13
0x18000f8f0  push    r14
0x18000f8f2  push    r15
0x18000f8f4  sub     rsp, 0D0h
0x18000f8fb  lea     rbp, [rsp+40h]
0x18000f900  mov     [rbp+0C0h+arg_8], rbx
0x18000f907  mov     rax, cs:__security_cookie
0x18000f90e  xor     rax, rbp
0x18000f911  mov     [rbp+0C0h+var_38], rax
0x18000f918  mov     r15, rcx
0x18000f91b  xorps   xmm0, xmm0
0x18000f91e  xor     ecx, ecx
0x18000f920  xorps   xmm1, xmm1
0x18000f923  mov     [rbp+0C0h+var_68], rcx
0x18000f927  mov     rdi, r8
0x18000f92a  mov     [rbp+0C0h+phKey], rcx
0x18000f92e  mov     [rbp+0C0h+var_A8], ecx
0x18000f931  mov     [rbp+0C0h+var_C0], ecx
0x18000f934  mov     [rbp+0C0h+var_A4], ecx
0x18000f937  mov     [rbp+0C0h+var_B8], ecx
0x18000f93a  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x18000f93e  movups  xmmword ptr [rbp+0C0h+UnicodeString.Length], xmm1
0x18000f942  test    r8, r8
0x18000f945  jz      loc_18001000A
0x18000f94b  cmp     r9d, 28h ; '('
0x18000f94f  jb      loc_1800101BF
0x18000f955  mov     r8d, [r8+18h]
0x18000f959  lea     eax, [r8+28h]
0x18000f95d  cmp     eax, 28h ; '('
0x18000f960  jb      short loc_18000F96C
0x18000f962  mov     esi, [rdi+24h]
0x18000f965  lea     ecx, [rsi+rax]
0x18000f968  cmp     ecx, eax
0x18000f96a  jnb     short loc_18000F9B3
0x18000f96c  mov     ebx, 80090003h
0x18000f971  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f978  lea     rax, WPP_GLOBAL_Control
0x18000f97f  cmp     rcx, rax
0x18000f982  jz      loc_18000FEBA
0x18000f988  test    byte ptr [rcx+1Ch], 1
0x18000f98c  jz      loc_18000FEBA
0x18000f992  mov     [rsp+100h+dwFlags], 506h
0x18000f99a  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f9a1  mov     qword ptr [rsp+100h+cbInput], rax
0x18000f9a6  mov     dword ptr [rsp+100h+pbInput], 80090003h
0x18000f9ae  jmp     loc_18001004C
0x18000f9b3  mov     r10d, [rdi+14h]
0x18000f9b7  lea     eax, [r10+rcx]
0x18000f9bb  cmp     eax, ecx
0x18000f9bd  jb      short loc_18000F96C
0x18000f9bf  mov     r11d, [rdi+8]
0x18000f9c3  lea     ecx, [r11+rax]
0x18000f9c7  cmp     ecx, eax
0x18000f9c9  jb      short loc_18000F96C
0x18000f9cb  mov     ebx, [rdi+1Ch]
0x18000f9ce  lea     eax, [rbx+rcx]
0x18000f9d1  cmp     eax, ecx
0x18000f9d3  jb      short loc_18000F96C
0x18000f9d5  mov     r13d, [rdi+10h]
0x18000f9d9  lea     ecx, [rax+r13]
0x18000f9dd  cmp     ecx, eax
0x18000f9df  jb      short loc_18000F96C
0x18000f9e1  mov     r14d, [rdi+20h]
0x18000f9e5  mov     [rbp+0C0h+var_BC], r14d
0x18000f9e9  lea     eax, [rcx+r14]
0x18000f9ed  cmp     eax, ecx
0x18000f9ef  jb      loc_18000F96C
0x18000f9f5  mov     r12d, [rdi+0Ch]
0x18000f9f9  lea     ecx, [r12+rax]
0x18000f9fd  cmp     ecx, eax
0x18000f9ff  jb      loc_18000F96C
0x18000fa05  cmp     r9d, ecx
0x18000fa08  jb      loc_1800101C7
0x18000fa0e  lea     rcx, [r11+28h]
0x18000fa12  mov     r11d, 30001h
0x18000fa18  lea     r9, [rdi+rbx]
0x18000fa1c  add     r9, rcx
0x18000fa1f  cmp     dword ptr [r15+18h], 2
0x18000fa24  mov     [rbp+0C0h+var_A0], r9
0x18000fa28  jz      loc_18000FCFD
0x18000fa2e  lea     ecx, [r12+r14]
0x18000fa32  mov     eax, esi
0x18000fa34  add     ecx, r13d
0x18000fa37  mov     [rbp+0C0h+var_BC], eax
0x18000fa3a  add     rcx, r9
0x18000fa3d  mov     r12d, r10d
0x18000fa40  mov     [rbp+0C0h+var_A0], rcx
0x18000fa44  mov     r13d, r8d
0x18000fa47  lea     r14, [rcx+r8]
0x18000fa4b  add     r14, r10
0x18000fa4e  lea     r9, [rcx+r10]
0x18000fa52  mov     [rbp+0C0h+Src], r9
0x18000fa56  sub     edx, 1
0x18000fa59  jz      short loc_18000FA64
0x18000fa5b  sub     edx, 0Bh
0x18000fa5e  jnz     loc_18001022A
0x18000fa64  mov     esi, r11d
0x18000fa67  lea     rcx, aRsapublicblob; "RSAPUBLICBLOB"
0x18000fa6e  mov     [rbp+0C0h+pszBlobType], rcx
0x18000fa72  test    r12d, r12d
0x18000fa75  jz      loc_18000FEB5
0x18000fa7b  test    r13d, r13d
0x18000fa7e  jz      loc_18000FEB5
0x18000fa84  test    eax, eax
0x18000fa86  jz      loc_18000FEB5
0x18000fa8c  mov     rdx, r15
0x18000fa8f  mov     ecx, esi
0x18000fa91  call    FinishNewKeyObject
0x18000fa96  mov     ebx, eax
0x18000fa98  test    eax, eax
0x18000fa9a  jnz     loc_180010257
0x18000faa0  mov     ebx, [rdi+8]
0x18000faa3  xor     eax, eax
0x18000faa5  inc     rbx
0x18000faa8  mov     [rbp+0C0h+SourceString], rax
0x18000faac  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000fab3  ja      loc_180010129
0x18000fab9  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000fac0  add     rcx, 8
0x18000fac4  add     rcx, rbx
0x18000fac7  cmp     rcx, rbx
0x18000faca  jb      loc_180010129
0x18000fad0  call    VerifyStackAvailable
0x18000fad5  test    eax, eax
0x18000fad7  jz      loc_180010125
0x18000fadd  lea     rax, [rbx+8]
0x18000fae1  lea     rcx, [rax+0Fh]
0x18000fae5  cmp     rcx, rax
0x18000fae8  ja      short loc_18000FAF4
0x18000faea  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000faf4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000faf8  mov     rax, rcx
0x18000fafb  call    _alloca_probe
0x18000fb00  sub     rsp, rcx
0x18000fb03  lea     rax, [rsp+100h+var_C0]
0x18000fb08  mov     [rbp+0C0h+SourceString], rax
0x18000fb0c  test    rax, rax
0x18000fb0f  jz      loc_180010129
0x18000fb15  mov     dword ptr [rax], 6B637453h
0x18000fb1b  add     rax, 8
0x18000fb1f  mov     [rbp+0C0h+SourceString], rax
0x18000fb23  jz      loc_180010129
0x18000fb29  test    rax, rax
0x18000fb2c  jz      loc_1800101D9
0x18000fb32  mov     r8d, [rdi+8]; Size
0x18000fb36  lea     rdx, [rdi+28h]; Src
0x18000fb3a  mov     rcx, rax; void *
0x18000fb3d  call    memcpy_0
0x18000fb42  mov     rcx, [rbp+0C0h+SourceString]
0x18000fb46  mov     eax, [rdi+8]
0x18000fb49  mov     rdx, rcx; SourceString
0x18000fb4c  mov     byte ptr [rax+rcx], 0
0x18000fb50  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x18000fb54  call    cs:__imp_RtlInitAnsiString
0x18000fb5b  nop     dword ptr [rax+rax+00h]
0x18000fb60  mov     r8b, 1; AllocateDestinationString
0x18000fb63  lea     rdx, [rbp+0C0h+DestinationString]; SourceString
0x18000fb67  lea     rcx, [rbp+0C0h+UnicodeString]; DestinationString
0x18000fb6b  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18000fb72  nop     dword ptr [rax+rax+00h]
0x18000fb77  mov     ecx, eax
0x18000fb79  test    eax, eax
0x18000fb7b  js      loc_180010261
0x18000fb81  mov     rcx, [r15+8]
0x18000fb85  mov     rax, [rbp+0C0h+UnicodeString.Buffer]
0x18000fb89  mov     r9, rcx
0x18000fb8c  sub     r9, rax
0x18000fb8f  movzx   r8d, word ptr [rax]
0x18000fb93  movzx   edx, word ptr [rax+r9]
0x18000fb98  sub     r8d, edx
0x18000fb9b  jnz     short loc_18000FBA5
0x18000fb9d  add     rax, 2
0x18000fba1  test    edx, edx
0x18000fba3  jnz     short loc_18000FB8F
0x18000fba5  test    r8d, r8d
0x18000fba8  jnz     loc_180010284
0x18000fbae  mov     ecx, r13d
0x18000fbb1  mov     ebx, r13d
0x18000fbb4  call    SafeAllocaAllocateFromHeap
0x18000fbb9  mov     [r15+100h], rax
0x18000fbc0  test    rax, rax
0x18000fbc3  jz      loc_18000FCB6
0x18000fbc9  mov     rdx, [rbp+0C0h+Src]; Src
0x18000fbcd  mov     r8d, ebx; Size
0x18000fbd0  mov     rcx, rax; void *
0x18000fbd3  call    memcpy_0
0x18000fbd8  mov     rcx, r15
0x18000fbdb  mov     [r15+108h], r13d
0x18000fbe2  call    ExtractLegacyUIPolicies
0x18000fbe7  mov     ebx, eax
0x18000fbe9  test    eax, eax
0x18000fbeb  jnz     loc_18000FF9C
0x18000fbf1  test    r14b, 0Fh
0x18000fbf5  jnz     loc_18000FFDA
0x18000fbfb  mov     edi, [rbp+0C0h+var_BC]
0x18000fbfe  mov     ecx, [r15+20h]
0x18000fc02  lea     r9, [rbp+0C0h+var_A4]
0x18000fc06  mov     r8d, edi
0x18000fc09  mov     rdx, r14
0x18000fc0c  call    UnprotectExportabilityFlag
0x18000fc11  mov     ebx, eax
0x18000fc13  test    eax, eax
0x18000fc15  jnz     loc_1800102DE
0x18000fc1b  xor     edi, edi
0x18000fc1d  mov     [rbp+0C0h+var_BC], edi
0x18000fc20  cmp     [rbp+0C0h+var_A4], edi
0x18000fc23  jnz     loc_1800102F3
0x18000fc29  sub     esi, 30001h
0x18000fc2f  jnz     loc_18000FD79
0x18000fc35  cmp     r12d, 14h
0x18000fc39  jb      loc_180010061
0x18000fc3f  mov     r13, [rbp+0C0h+var_A0]
0x18000fc43  mov     r14d, [r13+8]
0x18000fc47  mov     rax, [r13+0]
0x18000fc4b  mov     [rbp+0C0h+var_60], rax
0x18000fc4f  mov     rax, [r13+0Ch]
0x18000fc53  lea     esi, [r14+7]
0x18000fc57  mov     [rbp+0C0h+var_54], rax
0x18000fc5b  shr     esi, 3
0x18000fc5e  mov     [rbp+0C0h+var_58], r14d
0x18000fc62  lea     eax, [rsi+14h]
0x18000fc65  cmp     eax, 14h
0x18000fc68  jb      loc_18000FD46
0x18000fc6e  cmp     r12d, eax
0x18000fc71  jnb     loc_18000FDF4
0x18000fc77  mov     ebx, 80090003h
0x18000fc7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc83  lea     rax, WPP_GLOBAL_Control
0x18000fc8a  cmp     rcx, rax
0x18000fc8d  jz      short loc_18000FCD8
0x18000fc8f  test    byte ptr [rcx+1Ch], 1
0x18000fc93  jz      short loc_18000FCD8
0x18000fc95  mov     [rsp+100h+dwFlags], 607h
0x18000fc9d  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fca4  mov     qword ptr [rsp+100h+cbInput], rax
0x18000fca9  mov     dword ptr [rsp+100h+pbInput], 80090003h
0x18000fcb1  jmp     loc_18000FE52
0x18000fcb6  mov     ebx, 8009000Eh
0x18000fcbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcc2  lea     rax, WPP_GLOBAL_Control
0x18000fcc9  cmp     rcx, rax
0x18000fccc  jz      short loc_18000FCD8
0x18000fcce  test    byte ptr [rcx+1Ch], 1
0x18000fcd2  jnz     loc_18000FE36
0x18000fcd8  mov     rcx, [rbp+0C0h+SourceString]
0x18000fcdc  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18000fce0  cmp     dword ptr [rcx], 70616548h
0x18000fce6  jnz     loc_18000FEBA
0x18000fcec  mov     rax, cs:g_pfnFree
0x18000fcf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcf8  jmp     loc_18000FEBA
0x18000fcfd  sub     edx, 1
0x18000fd00  jz      short loc_18000FD19
0x18000fd02  sub     edx, 1
0x18000fd05  jz      short loc_18000FD19
0x18000fd07  sub     edx, 1
0x18000fd0a  jz      loc_180010215
0x18000fd10  sub     edx, 9
0x18000fd13  jnz     loc_180010201
0x18000fd19  lea     rax, aRsapublicblob; "RSAPUBLICBLOB"
0x18000fd20  mov     esi, r11d
0x18000fd23  mov     [rbp+0C0h+pszBlobType], rax
0x18000fd27  mov     eax, [rbp+0C0h+var_BC]
0x18000fd2a  lea     r10, [r12+r9]
0x18000fd2e  lea     r14, [r12+r13]
0x18000fd32  mov     [rbp+0C0h+Src], r10
0x18000fd36  add     r14, r9
0x18000fd39  mov     dword ptr [r15+28h], 2
0x18000fd41  jmp     loc_18000FA72
0x18000fd46  mov     ebx, 80090003h
0x18000fd4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd52  lea     rax, WPP_GLOBAL_Control
0x18000fd59  cmp     rcx, rax
0x18000fd5c  jz      loc_18000FCD8
0x18000fd62  test    byte ptr [rcx+1Ch], 1
0x18000fd66  jz      loc_18000FCD8
0x18000fd6c  mov     [rsp+100h+dwFlags], 600h
0x18000fd74  jmp     loc_18000FC9D
0x18000fd79  sub     esi, 1
0x18000fd7c  jz      loc_180010435
0x18000fd82  cmp     esi, 1
0x18000fd85  jz      loc_180010300
0x18000fd8b  mov     eax, [rbp+0C0h+var_A8]
0x18000fd8e  mov     ecx, [rbp+0C0h+var_BC]
0x18000fd91  lea     r9, [rbp+0C0h+phKey]; phKey
0x18000fd95  mov     r8, [rbp+0C0h+pszBlobType]; pszBlobType
0x18000fd99  xor     edx, edx; hImportKey
0x18000fd9b  mov     [rsp+100h+dwFlags], ecx; dwFlags
0x18000fd9f  mov     rcx, [r15+58h]; hAlgorithm
0x18000fda3  mov     [rsp+100h+cbInput], eax; cbInput
0x18000fda7  mov     [rsp+100h+pbInput], rdi; pbInput
0x18000fdac  call    cs:__imp_BCryptImportKeyPair
0x18000fdb3  nop     dword ptr [rax+rax+00h]
0x18000fdb8  mov     ebx, eax
0x18000fdba  test    eax, eax
0x18000fdbc  jnz     loc_18000FE67
  ... truncated ...
```
