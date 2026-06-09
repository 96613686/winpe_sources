# WriteRsaKeyToLegacyStore

- ea: `0x18005d3f4`
- end: `0x18005df8a`
- name: `WriteRsaKeyToLegacyStore`
- size: `2966`
- prototype: `__int64 __fastcall(__int64, unsigned int *, DWORD)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002a0c0`
- `0x18002b460`

## callees

- `0x180005848`
- `0x180007298`
- `0x1800086d0`
- `0x1800090c0`
- `0x18000af80`
- `0x18000d3d0`
- `0x180010530`
- `0x18001e4cc`
- `0x180038970`
- `0x1800398b0`
- `0x18005c848`
- `0x18005c920`
- `0x18005cf64`
- `0x18005d218`
- `0x18005d3f4`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005d49d`
- `ntdll!RtlInitUnicodeString` at `0x18005d49d`
- `ntdll!RtlFreeAnsiString` at `0x18005de88`
- `ntdll!RtlFreeAnsiString` at `0x18005de88`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18005d4ba`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18005d4ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ddf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ddf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005def5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005df10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005def5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005df10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005df45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005df45`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005dda8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005dda8`
- `bcrypt!BCryptExportKey` at `0x18005d53b`
- `bcrypt!BCryptExportKey` at `0x18005d61c`
- `bcrypt!BCryptExportKey` at `0x18005d53b`
- `bcrypt!BCryptExportKey` at `0x18005d61c`

## string_xrefs

- `0x18005d4e8`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18005dd70`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x18005de0b`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`

## pseudocode

```c
__int64 __fastcall WriteRsaKeyToLegacyStore(__int64 a1, unsigned int *a2, DWORD a3)
{
  size_t *v5; // rsi
  size_t *v6; // r14
  size_t *v7; // r12
  size_t *v8; // r15
  __int64 v9; // r9
  __int64 LastError; // rbx
  __int64 v11; // rcx
  _WORD *v12; // rdi
  void *v13; // rcx
  int LegacyUserDirectory; // eax
  __int64 v15; // rdx
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  size_t *v22; // rax
  __int64 v23; // rdx
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // rcx
  __int64 v26; // rcx
  unsigned __int64 v27; // rcx
  void *v28; // rsp
  void *v29; // rsp
  size_t *v30; // rax
  __int64 v31; // rdx
  unsigned __int64 v32; // rbx
  unsigned __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  void *v36; // rsp
  void *v37; // rsp
  size_t *v38; // rax
  size_t v39; // rax
  __int64 v40; // r10
  char *v41; // rcx
  size_t v42; // rax
  char *v43; // rcx
  __int64 v44; // r9
  char *v45; // rbx
  __int64 v46; // rcx
  unsigned int v47; // r11d
  __int64 v48; // r8
  __int64 v49; // rdx
  char *v50; // rbx
  unsigned int v51; // ecx
  unsigned int v52; // eax
  int v53; // r15d
  size_t v54; // rdi
  int v55; // edi
  int v56; // eax
  bool v57; // zf
  __int64 v58; // rdi
  unsigned __int64 v59; // rcx
  __int64 v60; // rcx
  unsigned __int64 v61; // rcx
  void *v62; // rsp
  void *v63; // rsp
  size_t *v64; // rax
  void *v65; // rdx
  size_t v66; // r8
  __int64 v67; // rbx
  char *v68; // rdi
  void *v69; // rdx
  size_t v70; // r8
  __int64 v71; // rbx
  unsigned int v72; // eax
  char *v73; // rdi
  void *v74; // rdx
  size_t v75; // r8
  __int64 v76; // rbx
  unsigned int v77; // eax
  char *v78; // rdi
  void *v79; // rdx
  size_t v80; // r8
  __int64 v81; // rbx
  unsigned int v82; // eax
  char *v83; // rdi
  void *v84; // rdx
  size_t v85; // r8
  __int64 v86; // rbx
  unsigned int v87; // eax
  void *v88; // rdx
  size_t v89; // r8
  __int64 v90; // rbx
  unsigned int v91; // eax
  char *v92; // rdi
  void *v93; // rdx
  size_t v94; // r8
  __int64 v95; // rbx
  void *v96; // rdx
  size_t v97; // r8
  __int64 v98; // rdx
  __int64 v99; // rdx
  _BYTE v101[32]; // [rsp+0h] [rbp-40h] BYREF
  size_t v102; // [rsp+40h] [rbp+0h] BYREF
  _WORD *v103; // [rsp+48h] [rbp+8h] BYREF
  ULONG pcbResult; // [rsp+50h] [rbp+10h] BYREF
  unsigned int v105; // [rsp+54h] [rbp+14h] BYREF
  unsigned int v106; // [rsp+58h] [rbp+18h]
  unsigned int v107; // [rsp+5Ch] [rbp+1Ch]
  unsigned int v108; // [rsp+60h] [rbp+20h]
  unsigned int v109; // [rsp+64h] [rbp+24h]
  unsigned int v110; // [rsp+68h] [rbp+28h]
  unsigned int v111; // [rsp+6Ch] [rbp+2Ch] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+70h] [rbp+30h]
  void *Src; // [rsp+78h] [rbp+38h]
  unsigned int v114; // [rsp+80h] [rbp+40h] BYREF
  void *v115; // [rsp+88h] [rbp+48h]
  void *v116; // [rsp+90h] [rbp+50h]
  void *v117; // [rsp+98h] [rbp+58h]
  void *v118; // [rsp+A0h] [rbp+60h]
  void *v119; // [rsp+A8h] [rbp+68h]
  void *v120; // [rsp+B0h] [rbp+70h]
  HLOCAL hMem; // [rsp+B8h] [rbp+78h] BYREF
  HLOCAL v122; // [rsp+C0h] [rbp+80h] BYREF
  void *v123; // [rsp+C8h] [rbp+88h]
  DWORD NumberOfBytesWritten; // [rsp+D0h] [rbp+90h] BYREF
  size_t Size; // [rsp+D8h] [rbp+98h]
  size_t v126; // [rsp+E0h] [rbp+A0h]
  HANDLE hFile; // [rsp+E8h] [rbp+A8h] BYREF
  struct _STRING AnsiString; // [rsp+F0h] [rbp+B0h] BYREF
  STRSAFE_LPCSTR pszSrc; // [rsp+100h] [rbp+C0h]
  char v130[32]; // [rsp+110h] [rbp+D0h] BYREF
  void *v131; // [rsp+130h] [rbp+F0h]
  unsigned int v132; // [rsp+138h] [rbp+F8h]
  void *v133; // [rsp+140h] [rbp+100h]
  int v134; // [rsp+148h] [rbp+108h]
  void *v135; // [rsp+150h] [rbp+110h]
  unsigned int v136; // [rsp+158h] [rbp+118h]
  void *v137; // [rsp+160h] [rbp+120h]
  unsigned int v138; // [rsp+168h] [rbp+128h]
  void *v139; // [rsp+170h] [rbp+130h]
  unsigned int v140; // [rsp+178h] [rbp+138h]
  void *v141; // [rsp+180h] [rbp+140h]
  unsigned int v142; // [rsp+188h] [rbp+148h]
  struct _UNICODE_STRING DestinationString; // [rsp+190h] [rbp+150h] BYREF
  wchar_t v144[112]; // [rsp+1A0h] [rbp+160h] BYREF

  nNumberOfBytesToWrite = a3;
  pcbResult = 0;
  v105 = 0;
  LODWORD(v102) = 0;
  hMem = 0;
  v111 = 0;
  v122 = 0;
  v114 = 0;
  AnsiString = 0;
  v5 = 0;
  v6 = 0;
  DestinationString = 0;
  v7 = 0;
  NumberOfBytesWritten = 0;
  v8 = 0;
  v103 = 0;
  hFile = (HANDLE)-1LL;
  memset_0(v130, 0, 0x80u);
  RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(a1 + 8));
  if ( RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u) < 0 )
  {
    AnsiString.Buffer = 0;
    v9 = 2761;
LABEL_3:
    LODWORD(LastError) = -2146893810;
    v11 = 2148073486LL;
LABEL_4:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", v9);
LABEL_5:
    v12 = v103;
    goto LABEL_112;
  }
  v13 = *(void **)(a1 + 112);
  pszSrc = AnsiString.Buffer;
  LODWORD(v123) = AnsiString.Length + 1;
  LegacyUserDirectory = BCryptExportKey(v13, 0, L"RSAPRIVATEBLOB", 0, 0, &pcbResult, 0);
  LODWORD(LastError) = LegacyUserDirectory;
  if ( LegacyUserDirectory < 0 )
  {
    v9 = 2784;
LABEL_8:
    v11 = (unsigned int)LegacyUserDirectory;
    goto LABEL_4;
  }
  v16 = pcbResult;
  if ( !pcbResult )
    goto LABEL_137;
  if ( pcbResult > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_137;
  v17 = pcbResult + g_ulAdditionalProbeSize + 8;
  if ( v17 < pcbResult || !(unsigned int)VerifyStackAvailable(v17, v15) )
    goto LABEL_137;
  v18 = v16 + 23;
  if ( v16 + 23 <= v16 + 8 )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
  v20 = alloca(v19);
  v21 = alloca(v19);
  v5 = &v102;
  if ( v101 == (_BYTE *)-64LL || (LODWORD(v102) = 1801679955, (v5 = (size_t *)&v103) == 0) )
  {
LABEL_137:
    if ( v16 + 8 >= v16 )
    {
      v22 = (size_t *)((__int64 (*)(void))g_pfnAllocate)();
      v5 = v22;
      if ( v22 )
      {
        *(_DWORD *)v22 = 1885431112;
        v5 = v22 + 1;
      }
    }
  }
  if ( !v5 )
  {
    v9 = 2793;
    goto LABEL_3;
  }
  LegacyUserDirectory = BCryptExportKey(
                          *(BCRYPT_KEY_HANDLE *)(a1 + 112),
                          0,
                          L"RSAPRIVATEBLOB",
                          (PUCHAR)v5,
                          pcbResult,
                          &pcbResult,
                          0);
  LODWORD(LastError) = LegacyUserDirectory;
  if ( LegacyUserDirectory < 0 )
  {
    v9 = 2807;
    goto LABEL_8;
  }
  LegacyUserDirectory = TranslateRsaBlobToBSafePublic((_DWORD)v5, pcbResult, 0, 0, (__int64)&v105);
  LODWORD(LastError) = LegacyUserDirectory;
  if ( LegacyUserDirectory < 0 )
  {
    v9 = 2824;
    goto LABEL_8;
  }
  v24 = v105;
  if ( !v105 )
    goto LABEL_138;
  if ( v105 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_138;
  v25 = v105 + g_ulAdditionalProbeSize + 8;
  if ( v25 < v105 || !(unsigned int)VerifyStackAvailable(v25, v23) )
    goto LABEL_138;
  v26 = v24 + 23;
  if ( v24 + 23 <= v24 + 8 )
    v26 = 0xFFFFFFFFFFFFFF0LL;
  v27 = v26 & 0xFFFFFFFFFFFFFFF0uLL;
  v28 = alloca(v27);
  v29 = alloca(v27);
  v6 = &v102;
  if ( v101 == (_BYTE *)-64LL || (LODWORD(v102) = 1801679955, (v6 = (size_t *)&v103) == 0) )
  {
LABEL_138:
    if ( v24 + 8 >= v24 )
    {
      v30 = (size_t *)((__int64 (*)(void))g_pfnAllocate)();
      v6 = v30;
      if ( v30 )
      {
        *(_DWORD *)v30 = 1885431112;
        v6 = v30 + 1;
      }
    }
  }
  if ( !v6 )
  {
    v9 = 2833;
    goto LABEL_3;
  }
  LegacyUserDirectory = TranslateRsaBlobToBSafePublic((_DWORD)v5, pcbResult, (_DWORD)v6, v105, (__int64)&v105);
  LODWORD(LastError) = LegacyUserDirectory;
  if ( LegacyUserDirectory < 0 )
  {
    v9 = 2845;
    goto LABEL_8;
  }
  LegacyUserDirectory = TranslateRsaBlobToBSafePrivate(v5, pcbResult, 0, 0, &v102);
  LODWORD(LastError) = LegacyUserDirectory;
  if ( LegacyUserDirectory < 0 )
  {
    v9 = 2862;
    goto LABEL_8;
  }
  v32 = (unsigned int)v102;
  if ( !(_DWORD)v102 )
    goto LABEL_139;
  if ( (unsigned int)v102 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_139;
  v33 = (unsigned int)v102 + g_ulAdditionalProbeSize + 8;
  if ( v33 < (unsigned int)v102 || !(unsigned int)VerifyStackAvailable(v33, v31) )
    goto LABEL_139;
  v34 = v32 + 23;
  if ( v32 + 23 <= v32 + 8 )
    v34 = 0xFFFFFFFFFFFFFF0LL;
  v35 = v34 & 0xFFFFFFFFFFFFFFF0uLL;
  v36 = alloca(v35);
  v37 = alloca(v35);
  v7 = &v102;
  if ( v101 == (_BYTE *)-64LL || (LODWORD(v102) = 1801679955, (v7 = (size_t *)&v103) == 0) )
  {
LABEL_139:
    if ( v32 + 8 >= v32 )
    {
      v38 = (size_t *)((__int64 (*)(void))g_pfnAllocate)();
      v7 = v38;
      if ( v38 )
      {
        *(_DWORD *)v38 = 1885431112;
        v7 = v38 + 1;
      }
    }
  }
  if ( !v7 )
  {
    v9 = 2871;
    goto LABEL_3;
  }
  LegacyUserDirectory = TranslateRsaBlobToBSafePrivate(v5, pcbResult, v7, (unsigned int)v102, &v102);
  LODWORD(LastError) = LegacyUserDirectory;
  if ( LegacyUserDirectory < 0 )
  {
    v9 = 2883;
    goto LABEL_8;
  }
  LegacyUserDirectory = EncryptLegacyRsaKey(*(_DWORD *)(a1 + 32), (_DWORD)v7, v102, (unsigned int)&hMem, (__int64)&v111);
  LODWORD(LastError) = LegacyUserDirectory;
  if ( LegacyUserDirectory )
  {
    v9 = 2901;
    goto LABEL_8;
  }
  LegacyUserDirectory = EncryptLegacyFlags(*(unsigned int *)(a1 + 32), (*(_DWORD *)(a1 + 36) >> 1) & 1, &v122, &v114);
  LODWORD(LastError) = LegacyUserDirectory;
  if ( LegacyUserDirectory )
  {
    v9 = 2918;
    goto LABEL_8;
  }
  if ( a2 )
  {
    v39 = a2[2];
    v40 = a2[3];
    Src = a2 + 10;
    v41 = (char *)a2 + v39 + 40;
    Size = v39;
    v42 = a2[7];
    v123 = v41;
    v43 = &v41[v42];
    v126 = v42;
    v107 = v40;
    if ( (_DWORD)v40 && (v44 = a2[4], (LODWORD(v102) = v44) != 0) )
    {
      v45 = &v43[v40];
      v115 = v43;
      v46 = a2[8];
      v116 = v45;
      v47 = v46;
      v108 = v46;
      v117 = &v45[v44];
      v43 = &v45[v44 + v46];
    }
    else
    {
      v47 = v136;
      LODWORD(v44) = v134;
      LODWORD(v40) = v132;
      v117 = v135;
      v115 = v131;
      v108 = v136;
      LODWORD(v102) = v134;
      v116 = v133;
      v107 = v132;
    }
    v48 = a2[5];
    v109 = v48;
    if ( (_DWORD)v48 && (v49 = a2[6], (v106 = v49) != 0) )
    {
      v50 = &v43[v48];
      v118 = v43;
      v51 = a2[9];
      v119 = v50;
      v52 = v51;
      v110 = v51;
      v120 = &v50[v49];
      LODWORD(v43) = v49 + (_DWORD)v50 + v51;
    }
    else
    {
      v52 = v142;
      v120 = v141;
      v49 = v140;
      v119 = v139;
      LODWORD(v48) = v138;
      v106 = v140;
      v109 = v138;
      v110 = v142;
      v118 = v137;
    }
    if ( nNumberOfBytesToWrite < (int)v43 - (int)a2 )
    {
      LODWORD(LastError) = -2146893779;
      goto LABEL_5;
    }
    LODWORD(v54) = Size;
    v53 = v126;
  }
  else
  {
    v53 = 20;
    v54 = (unsigned int)v123;
    v49 = v140;
    LODWORD(v48) = v138;
    v47 = v136;
    LODWORD(v44) = v134;
    LODWORD(v40) = v132;
    v120 = v141;
    v119 = v139;
    Src = (void *)pszSrc;
    v118 = v137;
    v117 = v135;
    v123 = (void *)(a1 + 176);
    v52 = v142;
    v116 = v133;
    Size = v54;
    v126 = 20;
    v110 = v142;
    v106 = v140;
    v109 = v138;
    v108 = v136;
    LODWORD(v102) = v134;
    v107 = v132;
    v115 = v131;
  }
  if ( *(_DWORD *)(a1 + 24) == 2 )
  {
    LODWORD(v40) = v105;
    LODWORD(v44) = v111;
    v47 = v114;
    v116 = hMem;
    v117 = v122;
    v107 = v105;
    v115 = v6;
    LODWORD(v102) = v111;
    v108 = v114;
  }
  else
  {
    LODWORD(v48) = v105;
    v49 = v111;
    v119 = hMem;
    v52 = v114;
    v110 = v114;
    v109 = v105;
    v118 = v6;
    v106 = v111;
    v120 = v122;
  }
  v55 = v54 + 40;
  v56 = v53 + v40 + v44 + v47 + v48 + v49 + v52;
  v8 = 0;
  v57 = v56 + v55 == 0;
  v58 = (unsigned int)(v56 + v55);
  nNumberOfBytesToWrite = v58;
  if ( v57 )
    goto LABEL_140;
  if ( (unsigned int)v58 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_140;
  v59 = (unsigned int)v58 + g_ulAdditionalProbeSize + 8;
  if ( v59 < (unsigned int)v58 || !(unsigned int)VerifyStackAvailable(v59, v49) )
    goto LABEL_140;
  v60 = v58 + 23;
  if ( v58 + 23 <= (unsigned __int64)(v58 + 8) )
    v60 = 0xFFFFFFFFFFFFFF0LL;
  v61 = v60 & 0xFFFFFFFFFFFFFFF0uLL;
  v62 = alloca(v61);
  v63 = alloca(v61);
  v8 = &v102;
  if ( v101 == (_BYTE *)-64LL || (LODWORD(v102) = 1801679955, (v8 = (size_t *)&v103) == 0) )
  {
LABEL_140:
    if ( v58 + 8 >= (unsigned __int64)(unsigned int)v58 )
    {
      v64 = (size_t *)((__int64 (*)(void))g_pfnAllocate)();
      v8 = v64;
      if ( v64 )
      {
        *(_DWORD *)v64 = 1885431112;
        v8 = v64 + 1;
      }
    }
  }
  if ( !v8 )
  {
    v9 = 3030;
    goto LABEL_3;
  }
  v65 = Src;
  *(_OWORD *)v8 = 0;
  *((_OWORD *)v8 + 1) = 0;
  v8[4] = 0;
  v66 = (unsigned int)Size;
  *(_DWORD *)v8 = 2;
  *((_DWORD *)v8 + 2) = v66;
  v67 = (unsigned int)v66;
  memcpy_0(v8 + 5, v65, v66);
  v68 = (char *)v8 + v67 + 40;
  v69 = v123;
  v70 = (unsigned int)v126;
  *((_DWORD *)v8 + 7) = v126;
  v71 = (unsigned int)v70;
  memcpy_0(v68, v69, v70);
  v72 = v107;
  v73 = &v68[v71];
  if ( v107 && (_DWORD)v102 )
  {
    v74 = v115;
    v75 = v107;
    *((_DWORD *)v8 + 3) = v107;
    v76 = v72;
    memcpy_0(v73, v74, v75);
    v77 = v102;
    v78 = &v73[v76];
    v79 = v116;
    v80 = (unsigned int)v102;
    *((_DWORD *)v8 + 4) = v102;
    v81 = v77;
    memcpy_0(v78, v79, v80);
    v82 = v108;
    v83 = &v78[v81];
    v84 = v117;
    v85 = v108;
    *((_DWORD *)v8 + 8) = v108;
    v86 = v82;
    memcpy_0(v83, v84, v85);
    v73 = &v83[v86];
  }
  v87 = v109;
  if ( v109 && v106 )
  {
    v88 = v118;
    v89 = v109;
    *((_DWORD *)v8 + 5) = v109;
    v90 = v87;
    memcpy_0(v73, v88, v89);
    v91 = v106;
    v92 = &v73[v90];
    v93 = v119;
    v94 = v106;
    *((_DWORD *)v8 + 6) = v106;
    v95 = v91;
    memcpy_0(v92, v93, v94);
    v96 = v120;
    v97 = v110;
    *((_DWORD *)v8 + 9) = v110;
    memcpy_0(&v92[v95], v96, v97);
  }
  LegacyUserDirectory = AddMachineGuidAndAppContainerSidHashToContainerNameA(pszSrc, *(_DWORD *)(a1 + 528), v144);
  LODWORD(LastError) = LegacyUserDirectory;
  if ( LegacyUserDirectory )
  {
    v9 = 3092;
    goto LABEL_8;
  }
  LegacyUserDirectory = GetLegacyUserDirectory(*(unsigned int *)(a1 + 32), 1, *(_QWORD *)(a1 + 72), &v103);
  LODWORD(LastError) = LegacyUserDirectory;
  if ( LegacyUserDirectory )
  {
    v9 = 3104;
    goto LABEL_8;
  }
  v12 = v103;
  LODWORD(LastError) = OpenFileInStorageArea(*(_DWORD *)(a1 + 32), 0x40000000u, v103, v144, &hFile);
  if ( (_DWORD)LastError )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_d3c89702f7ce32abfafe624753d31df6_Traceguids,
        (_DWORD)v12,
        (__int64)v144);
    DebugTraceError(
      (unsigned int)LastError,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
      3118);
  }
  else if ( WriteFile(hFile, v8, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
  {
    KspCryptAuditKeyFileOperation(1, v98, a1, v12, v144, 2459, 0);
    LODWORD(LastError) = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_d3c89702f7ce32abfafe624753d31df6_Traceguids,
        (_DWORD)v12,
        (__int64)v144);
    LastError = GetLastError();
    DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", 3126);
    KspCryptAuditKeyFileOperation(0, v99, a1, v12, v144, 2459, LastError);
  }
LABEL_112:
  if ( AnsiString.Buffer )
    RtlFreeAnsiString(&AnsiString);
  if ( v5 && *((_DWORD *)v5 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v6 && *((_DWORD *)v6 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v7 && *((_DWORD *)v7 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( hMem )
    LocalFree(hMem);
  if ( v122 )
    LocalFree(v122);
  if ( v8 && *((_DWORD *)v8 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  if ( v12 )
    MSCryptFree(v12);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18005d3f4  push    rbp
0x18005d3f6  push    rsi
0x18005d3f7  push    rdi
0x18005d3f8  push    r12
0x18005d3fa  push    r13
0x18005d3fc  push    r14
0x18005d3fe  push    r15
0x18005d400  sub     rsp, 290h
0x18005d407  lea     rbp, [rsp+40h]
0x18005d40c  mov     [rbp+280h+arg_10], rbx
0x18005d413  mov     rax, cs:__security_cookie
0x18005d41a  xor     rax, rbp
0x18005d41d  mov     [rbp+280h+var_40], rax
0x18005d424  xor     ebx, ebx
0x18005d426  mov     [rbp+280h+nNumberOfBytesToWrite], r8d
0x18005d42a  mov     rdi, rdx
0x18005d42d  mov     [rbp+280h+var_270], ebx
0x18005d430  mov     r13, rcx
0x18005d433  mov     [rbp+280h+var_26C], ebx
0x18005d436  xorps   xmm0, xmm0
0x18005d439  mov     dword ptr [rbp+280h+var_280], ebx
0x18005d43c  xorps   xmm1, xmm1
0x18005d43f  mov     [rbp+280h+hMem], rbx
0x18005d443  xor     edx, edx; Val
0x18005d445  mov     [rbp+280h+var_254], ebx
0x18005d448  mov     r8d, 80h; Size
0x18005d44e  mov     [rbp+280h+var_200], rbx
0x18005d455  lea     rcx, [rbp+280h+var_1B0]; void *
0x18005d45c  mov     [rbp+280h+var_240], ebx
0x18005d45f  movups  xmmword ptr [rbp+280h+AnsiString.Length], xmm0
0x18005d466  mov     esi, ebx
0x18005d468  mov     r14d, ebx
0x18005d46b  movups  xmmword ptr [rbp+280h+DestinationString.Length], xmm1
0x18005d472  mov     r12d, ebx
0x18005d475  mov     [rbp+280h+NumberOfBytesWritten], ebx
0x18005d47b  mov     r15d, ebx
0x18005d47e  mov     [rbp+280h+var_278], rbx
0x18005d482  mov     [rbp+280h+hFile], 0FFFFFFFFFFFFFFFFh
0x18005d48d  call    memset_0
0x18005d492  mov     rdx, [r13+8]; SourceString
0x18005d496  lea     rcx, [rbp+280h+DestinationString]; DestinationString
0x18005d49d  call    cs:__imp_RtlInitUnicodeString
0x18005d4a4  nop     dword ptr [rax+rax+00h]
0x18005d4a9  mov     r8b, 1; AllocateDestinationString
0x18005d4ac  lea     rdx, [rbp+280h+DestinationString]; SourceString
0x18005d4b3  lea     rcx, [rbp+280h+AnsiString]; DestinationString
0x18005d4ba  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18005d4c1  nop     dword ptr [rax+rax+00h]
0x18005d4c6  test    eax, eax
0x18005d4c8  jns     short loc_18005D4FD
0x18005d4ca  mov     [rbp+280h+AnsiString.Buffer], rbx
0x18005d4d1  mov     r9d, 0AC9h
0x18005d4d7  mov     ebx, 8009000Eh
0x18005d4dc  mov     ecx, 8009000Eh
0x18005d4e1  lea     rdx, aStatus; "Status"
0x18005d4e8  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005d4ef  call    DebugTraceError
0x18005d4f4  mov     rdi, [rbp+280h+var_278]
0x18005d4f8  jmp     loc_18005DE77
0x18005d4fd  mov     rax, [rbp+280h+AnsiString.Buffer]
0x18005d504  lea     r8, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18005d50b  mov     rcx, [r13+70h]; hKey
0x18005d50f  xor     r9d, r9d; pbOutput
0x18005d512  mov     [rbp+280h+pszSrc], rax
0x18005d519  xor     edx, edx; hExportKey
0x18005d51b  movzx   eax, [rbp+280h+AnsiString.Length]
0x18005d522  inc     eax
0x18005d524  mov     [rsp+2C0h+dwFlags], ebx; dwFlags
0x18005d528  mov     dword ptr [rbp+280h+var_1F8], eax
0x18005d52e  lea     rax, [rbp+280h+var_270]
0x18005d532  mov     [rsp+2C0h+pcbResult], rax; pcbResult
0x18005d537  mov     [rsp+2C0h+cbOutput], ebx; cbOutput
0x18005d53b  call    cs:__imp_BCryptExportKey
0x18005d542  nop     dword ptr [rax+rax+00h]
0x18005d547  mov     ebx, eax
0x18005d549  test    eax, eax
0x18005d54b  jns     short loc_18005D557
0x18005d54d  mov     r9d, 0AE0h
0x18005d553  mov     ecx, eax
0x18005d555  jmp     short loc_18005D4E1
0x18005d557  mov     ebx, [rbp+280h+var_270]
0x18005d55a  test    rbx, rbx
0x18005d55d  jz      short loc_18005D5C0
0x18005d55f  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18005d566  ja      short loc_18005D5C0
0x18005d568  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005d56f  add     rcx, 8
0x18005d573  add     rcx, rbx
0x18005d576  cmp     rcx, rbx
0x18005d579  jb      short loc_18005D5C0
0x18005d57b  call    VerifyStackAvailable
0x18005d580  test    eax, eax
0x18005d582  jz      short loc_18005D5C0
0x18005d584  lea     rax, [rbx+8]
0x18005d588  lea     rcx, [rax+0Fh]
0x18005d58c  cmp     rcx, rax
0x18005d58f  ja      short loc_18005D59B
0x18005d591  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005d59b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005d59f  mov     rax, rcx
0x18005d5a2  call    _alloca_probe
0x18005d5a7  sub     rsp, rcx
0x18005d5aa  lea     rsi, [rsp+2C0h+var_280]
0x18005d5af  test    rsi, rsi
0x18005d5b2  jz      short loc_18005D5C0
0x18005d5b4  mov     dword ptr [rsi], 6B637453h
0x18005d5ba  add     rsi, 8
0x18005d5be  jnz     short loc_18005D5E7
0x18005d5c0  lea     rcx, [rbx+8]
0x18005d5c4  cmp     rcx, rbx
0x18005d5c7  jb      short loc_18005D5E7
0x18005d5c9  mov     rax, cs:g_pfnAllocate
0x18005d5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d5d5  mov     rsi, rax
0x18005d5d8  test    rax, rax
0x18005d5db  jz      short loc_18005D5E7
0x18005d5dd  mov     dword ptr [rax], 70616548h
0x18005d5e3  add     rsi, 8
0x18005d5e7  test    rsi, rsi
0x18005d5ea  jnz     short loc_18005D5F7
0x18005d5ec  mov     r9d, 0AE9h
0x18005d5f2  jmp     loc_18005D4D7
0x18005d5f7  mov     rcx, [r13+70h]; hKey
0x18005d5fb  lea     rax, [rbp+280h+var_270]
0x18005d5ff  mov     [rsp+2C0h+dwFlags], r12d; dwFlags
0x18005d604  lea     r8, aRsaprivateblob; "RSAPRIVATEBLOB"
0x18005d60b  mov     [rsp+2C0h+pcbResult], rax; pcbResult
0x18005d610  mov     r9, rsi; pbOutput
0x18005d613  mov     eax, [rbp+280h+var_270]
0x18005d616  xor     edx, edx; hExportKey
0x18005d618  mov     [rsp+2C0h+cbOutput], eax; cbOutput
0x18005d61c  call    cs:__imp_BCryptExportKey
0x18005d623  nop     dword ptr [rax+rax+00h]
0x18005d628  mov     ebx, eax
0x18005d62a  test    eax, eax
0x18005d62c  jns     short loc_18005D639
0x18005d62e  mov     r9d, 0AF7h
0x18005d634  jmp     loc_18005D553
0x18005d639  mov     edx, [rbp+280h+var_270]
0x18005d63c  lea     rax, [rbp+280h+var_26C]
0x18005d640  xor     r9d, r9d
0x18005d643  mov     qword ptr [rsp+2C0h+cbOutput], rax
0x18005d648  xor     r8d, r8d
0x18005d64b  mov     rcx, rsi
0x18005d64e  call    TranslateRsaBlobToBSafePublic
0x18005d653  mov     ebx, eax
0x18005d655  test    eax, eax
0x18005d657  jns     short loc_18005D664
0x18005d659  mov     r9d, 0B08h
0x18005d65f  jmp     loc_18005D553
0x18005d664  mov     ebx, [rbp+280h+var_26C]
0x18005d667  test    rbx, rbx
0x18005d66a  jz      short loc_18005D6CE
0x18005d66c  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18005d673  ja      short loc_18005D6CE
0x18005d675  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005d67c  add     rcx, 8
0x18005d680  add     rcx, rbx
0x18005d683  cmp     rcx, rbx
0x18005d686  jb      short loc_18005D6CE
0x18005d688  call    VerifyStackAvailable
0x18005d68d  test    eax, eax
0x18005d68f  jz      short loc_18005D6CE
0x18005d691  lea     rax, [rbx+8]
0x18005d695  lea     rcx, [rax+0Fh]
0x18005d699  cmp     rcx, rax
0x18005d69c  ja      short loc_18005D6A8
0x18005d69e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005d6a8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005d6ac  mov     rax, rcx
0x18005d6af  call    _alloca_probe
0x18005d6b4  sub     rsp, rcx
0x18005d6b7  lea     r14, [rsp+2C0h+var_280]
0x18005d6bc  test    r14, r14
0x18005d6bf  jz      short loc_18005D6CE
0x18005d6c1  mov     dword ptr [r14], 6B637453h
0x18005d6c8  add     r14, 8
0x18005d6cc  jnz     short loc_18005D6F5
0x18005d6ce  lea     rcx, [rbx+8]
0x18005d6d2  cmp     rcx, rbx
0x18005d6d5  jb      short loc_18005D6F5
0x18005d6d7  mov     rax, cs:g_pfnAllocate
0x18005d6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d6e3  mov     r14, rax
0x18005d6e6  test    rax, rax
0x18005d6e9  jz      short loc_18005D6F5
0x18005d6eb  mov     dword ptr [rax], 70616548h
0x18005d6f1  add     r14, 8
0x18005d6f5  test    r14, r14
0x18005d6f8  jnz     short loc_18005D705
0x18005d6fa  mov     r9d, 0B11h
0x18005d700  jmp     loc_18005D4D7
0x18005d705  mov     r9d, [rbp+280h+var_26C]
0x18005d709  lea     rax, [rbp+280h+var_26C]
0x18005d70d  mov     edx, [rbp+280h+var_270]
0x18005d710  mov     r8, r14
0x18005d713  mov     rcx, rsi
0x18005d716  mov     qword ptr [rsp+2C0h+cbOutput], rax
0x18005d71b  call    TranslateRsaBlobToBSafePublic
0x18005d720  mov     ebx, eax
0x18005d722  test    eax, eax
0x18005d724  jns     short loc_18005D731
0x18005d726  mov     r9d, 0B1Dh
0x18005d72c  jmp     loc_18005D553
0x18005d731  mov     edx, [rbp+280h+var_270]
0x18005d734  lea     rax, [rbp+280h+var_280]
0x18005d738  xor     r9d, r9d
0x18005d73b  mov     qword ptr [rsp+2C0h+cbOutput], rax
0x18005d740  xor     r8d, r8d
0x18005d743  mov     rcx, rsi
0x18005d746  call    TranslateRsaBlobToBSafePrivate
0x18005d74b  mov     ebx, eax
0x18005d74d  test    eax, eax
0x18005d74f  jns     short loc_18005D75C
0x18005d751  mov     r9d, 0B2Eh
0x18005d757  jmp     loc_18005D553
0x18005d75c  mov     ebx, dword ptr [rbp+280h+var_280]
0x18005d75f  test    rbx, rbx
0x18005d762  jz      short loc_18005D7C7
0x18005d764  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18005d76b  ja      short loc_18005D7C7
0x18005d76d  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005d774  add     rcx, 8
0x18005d778  add     rcx, rbx
0x18005d77b  cmp     rcx, rbx
0x18005d77e  jb      short loc_18005D7C7
0x18005d780  call    VerifyStackAvailable
0x18005d785  test    eax, eax
0x18005d787  jz      short loc_18005D7C7
0x18005d789  lea     rax, [rbx+8]
0x18005d78d  lea     rcx, [rax+0Fh]
0x18005d791  cmp     rcx, rax
0x18005d794  ja      short loc_18005D7A0
0x18005d796  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005d7a0  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005d7a4  mov     rax, rcx
0x18005d7a7  call    _alloca_probe
0x18005d7ac  sub     rsp, rcx
0x18005d7af  lea     r12, [rsp+2C0h+var_280]
0x18005d7b4  test    r12, r12
0x18005d7b7  jz      short loc_18005D7C7
0x18005d7b9  mov     dword ptr [r12], 6B637453h
0x18005d7c1  add     r12, 8
0x18005d7c5  jnz     short loc_18005D7EE
0x18005d7c7  lea     rcx, [rbx+8]
0x18005d7cb  cmp     rcx, rbx
0x18005d7ce  jb      short loc_18005D7EE
0x18005d7d0  mov     rax, cs:g_pfnAllocate
0x18005d7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d7dc  mov     r12, rax
0x18005d7df  test    rax, rax
0x18005d7e2  jz      short loc_18005D7EE
0x18005d7e4  mov     dword ptr [rax], 70616548h
0x18005d7ea  add     r12, 8
0x18005d7ee  test    r12, r12
0x18005d7f1  jnz     short loc_18005D7FE
0x18005d7f3  mov     r9d, 0B37h
0x18005d7f9  jmp     loc_18005D4D7
0x18005d7fe  mov     r9d, dword ptr [rbp+280h+var_280]
0x18005d802  lea     rax, [rbp+280h+var_280]
0x18005d806  mov     edx, [rbp+280h+var_270]
0x18005d809  mov     r8, r12
0x18005d80c  mov     rcx, rsi
0x18005d80f  mov     qword ptr [rsp+2C0h+cbOutput], rax
0x18005d814  call    TranslateRsaBlobToBSafePrivate
0x18005d819  mov     ebx, eax
0x18005d81b  test    eax, eax
0x18005d81d  jns     short loc_18005D82A
0x18005d81f  mov     r9d, 0B43h
0x18005d825  jmp     loc_18005D553
0x18005d82a  mov     r8d, dword ptr [rbp+280h+var_280]
0x18005d82e  lea     rax, [rbp+280h+var_254]
0x18005d832  mov     ecx, [r13+20h]
0x18005d836  lea     r9, [rbp+280h+hMem]
0x18005d83a  mov     rdx, r12
0x18005d83d  mov     qword ptr [rsp+2C0h+cbOutput], rax
0x18005d842  call    EncryptLegacyRsaKey
0x18005d847  mov     ebx, eax
0x18005d849  test    eax, eax
0x18005d84b  jz      short loc_18005D858
0x18005d84d  mov     r9d, 0B55h
0x18005d853  jmp     loc_18005D553
0x18005d858  mov     edx, [r13+24h]
0x18005d85c  lea     r9, [rbp+280h+var_240]
0x18005d860  mov     ecx, [r13+20h]
0x18005d864  lea     r8, [rbp+280h+var_200]
0x18005d86b  shr     edx, 1
0x18005d86d  and     edx, 1
0x18005d870  call    EncryptLegacyFlags
0x18005d875  mov     ebx, eax
0x18005d877  test    eax, eax
0x18005d879  jz      short loc_18005D886
0x18005d87b  mov     r9d, 0B66h
0x18005d881  jmp     loc_18005D553
0x18005d886  test    rdi, rdi
0x18005d889  jz      loc_18005D9BF
0x18005d88f  mov     eax, [rdi+8]
0x18005d892  lea     rcx, [rdi+28h]
0x18005d896  mov     r10d, [rdi+0Ch]
0x18005d89a  mov     [rbp+280h+Src], rcx
  ... truncated ...
```
