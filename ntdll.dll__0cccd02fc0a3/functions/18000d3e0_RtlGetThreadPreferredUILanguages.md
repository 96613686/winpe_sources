# RtlGetThreadPreferredUILanguages

- ea: `0x18000d3e0`
- end: `0x18000e15a`
- name: `RtlGetThreadPreferredUILanguages`
- size: `3450`
- prototype: ``
- caller_count: `4`
- callee_count: `27`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ca60`
- `0x180044bc0`
- `0x180055360`
- `0x18005d8e0`

## callees

- `0x180009060`
- `0x180009d60`
- `0x18000acb0`
- `0x18000b730`
- `0x18000c3f0`
- `0x18000d03c`
- `0x18000d3e0`
- `0x18000e160`
- `0x18000e650`
- `0x18000e7c0`
- `0x18000ecac`
- `0x18000ede4`
- `0x18000ee60`
- `0x180010eb0`
- `0x1800159b0`
- `0x18001861c`
- `0x18001b984`
- `0x1800535c0`
- `0x180053ab0`
- `0x180054eb0`
- `0x180054f80`
- `0x1800d9e10`
- `0x1800d9ed0`
- `0x1800ffe7c`
- `0x18012c830`
- `0x180162000`
- `0x180163a80`

## pseudocode

```c
__int64 __fastcall RtlGetThreadPreferredUILanguages(unsigned int a1, _DWORD *a2, wchar_t *a3, _DWORD *a4)
{
  __int64 v4; // r12
  char v5; // r15
  unsigned int v6; // ebx
  _WORD *MergedPrefLanguages; // rsi
  __int64 v8; // r13
  bool v9; // r14
  signed int v10; // edi
  __int64 result; // rax
  int v12; // r14d
  __int64 v13; // rdi
  _DWORD *v14; // r9
  unsigned int v15; // r12d
  char v16; // di
  int v17; // r8d
  unsigned __int16 v18; // r15
  unsigned int v19; // r10d
  int v20; // ebx
  unsigned __int16 *v21; // rdx
  int v22; // ecx
  _WORD *v23; // r14
  unsigned int v24; // r14d
  int v25; // eax
  size_t v26; // r12
  unsigned int v27; // ecx
  unsigned int v28; // r14d
  wchar_t *v29; // r11
  __int64 v30; // rdx
  _DWORD *v31; // rax
  int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rcx
  wchar_t *v35; // rcx
  size_t v36; // rdx
  unsigned int v37; // r14d
  __int64 v38; // r15
  __int64 Heap_0; // rax
  __int64 v40; // rax
  void *v41; // rcx
  __int64 v42; // r12
  void *v43; // r15
  int v44; // eax
  __int64 v45; // rcx
  void *v46; // r14
  signed int v47; // eax
  unsigned int v48; // ecx
  signed int v49; // eax
  int v50; // eax
  int v51; // edx
  __int64 *v52; // r12
  __int64 v53; // rax
  __int64 v54; // rax
  _DWORD *v55; // rcx
  __int64 v56; // rax
  const wchar_t *v57; // rcx
  size_t v58; // rax
  __int64 v59; // [rsp+20h] [rbp-E0h]
  __int64 v60; // [rsp+30h] [rbp-D0h]
  char v61; // [rsp+50h] [rbp-B0h] BYREF
  bool v62; // [rsp+51h] [rbp-AFh]
  char v63; // [rsp+52h] [rbp-AEh]
  __int64 v64; // [rsp+58h] [rbp-A8h] BYREF
  char v65; // [rsp+60h] [rbp-A0h]
  int v66; // [rsp+64h] [rbp-9Ch] BYREF
  int v67; // [rsp+68h] [rbp-98h]
  unsigned int v68; // [rsp+6Ch] [rbp-94h]
  unsigned int v69; // [rsp+70h] [rbp-90h]
  wchar_t *String1; // [rsp+78h] [rbp-88h]
  void *PreferredLanguages; // [rsp+80h] [rbp-80h]
  __int64 v72; // [rsp+88h] [rbp-78h]
  __int64 v73; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h] BYREF
  int v75; // [rsp+A0h] [rbp-60h]
  __int128 v76; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD *v77; // [rsp+B8h] [rbp-48h]
  __int64 v78; // [rsp+C0h] [rbp-40h]
  wchar_t *String2[2]; // [rsp+C8h] [rbp-38h] BYREF
  size_t v80; // [rsp+D8h] [rbp-28h]
  _DWORD *v81; // [rsp+E0h] [rbp-20h]
  _WORD v82[16]; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t String[4]; // [rsp+108h] [rbp+8h] BYREF
  __int16 v84; // [rsp+110h] [rbp+10h]

  v4 = 0;
  v77 = a4;
  v5 = 0;
  String1 = a3;
  v81 = a2;
  v75 = 0;
  v78 = 0;
  v6 = a1;
  v64 = 0;
  MergedPrefLanguages = 0;
  v63 = 0;
  v8 = 0;
  v9 = (a1 & 0x30) == 48;
  v62 = v9;
  if ( a4 )
    v75 = *a4;
  if ( (a1 & 0xFFFEFC83) != 0 )
    goto LABEL_181;
  if ( (a1 & 8) != 0 )
  {
    if ( (a1 & 4) != 0 )
    {
      v10 = -1073741811;
      goto LABEL_114;
    }
  }
  else if ( (a1 & 4) == 0 )
  {
    v6 = a1 | 8;
  }
  if ( (v6 & 0x10000) != 0 )
  {
    if ( (v6 & 0x40) != 0 )
    {
      v10 = -1073741811;
      goto LABEL_114;
    }
    if ( (v6 & 0x30) != 0 )
      goto LABEL_181;
    v6 |= 0x30u;
  }
  if ( (v6 & 0x40) == 0 )
  {
    if ( (v6 & 0x10) == 0 && (v6 & 0x20) == 0 )
      v6 |= 0x20u;
    goto LABEL_16;
  }
  if ( (v6 & 0x10) != 0 )
  {
LABEL_181:
    v10 = -1073741811;
    goto LABEL_114;
  }
  if ( (v6 & 0x20) != 0 )
  {
    v10 = -1073741811;
    goto LABEL_114;
  }
LABEL_16:
  if ( !a4 )
  {
    v10 = -1073741811;
    goto LABEL_114;
  }
  if ( *a4 && !a3 )
    return (unsigned int)-1073741811;
  if ( (v6 & 0x300) == 0x300 )
  {
    v10 = -1073741811;
    goto LABEL_114;
  }
  result = RtlpCreateProcessRegistryInfo(&v64);
  if ( (int)result < 0 )
    return result;
  if ( !v9 )
    goto LABEL_146;
  v8 = v64;
  if ( *(_DWORD *)(v64 + 12) != MEMORY[0x7FFE03A4] && (int)RtlUpdateProcessRegistryInfo() >= 0 )
  {
    v64 = 0;
    v10 = RtlpCreateProcessRegistryInfo(&v64);
    if ( v10 < 0 )
    {
      v8 = v64;
      goto LABEL_114;
    }
LABEL_146:
    v8 = v64;
  }
  v69 = 0;
  v73 = 0;
  PreferredLanguages = 0;
  if ( (v6 & 0x10000) != 0 )
  {
    v61 = 0;
    if ( *(_DWORD *)(v8 + 12) != MEMORY[0x7FFE03A4] )
    {
      v64 = 0;
      v50 = RtlpMuiRegCreateAndLoadRegistryInfo(&v64);
      v8 = v64;
      v10 = v50;
      if ( v50 >= 0 )
      {
        v52 = (__int64 *)(v64 + 56);
        v5 = 1;
        v63 = 1;
        if ( !*(_QWORD *)(v64 + 56)
          && (v10 = RtlpMuiRegLoadPreferredUILanguages(v64, v51, 0, 3, &v61, (__int64 *)(v64 + 56)), v10 < 0)
          && !v61
          || !*(_QWORD *)(v8 + 64)
          && (v61 = 0, v10 = RtlpMuiRegLoadPreferredUILanguages(v8, v51, 1u, 3, &v61, (__int64 *)(v8 + 64)), v10 < 0)
          && !v61 )
        {
LABEL_114:
          if ( String1 && v75 )
          {
            if ( v75 == 1 )
              *String1 = 0;
            else
              *(_DWORD *)String1 = 0;
          }
          goto LABEL_79;
        }
        v53 = *(_QWORD *)(v8 + 64);
        v4 = *v52;
        v12 = v6 & 0x40;
        v61 = 0;
        v72 = v53;
        goto LABEL_164;
      }
      goto LABEL_113;
    }
  }
  else if ( NtCurrentTeb()->PreferredLanguages )
  {
    PreferredLanguages = NtCurrentTeb()->PreferredLanguages;
  }
  v12 = v6 & 0x40;
  if ( (v6 & 0x40) == 0 )
  {
    v10 = InitializeTEBUserLangList(0, v8);
    if ( v10 >= 0 )
    {
      v72 = *(_QWORD *)NtCurrentTeb()->UserPrefLanguages;
      v73 = *((_QWORD *)NtCurrentTeb()->UserPrefLanguages + 1)
          ? *((_QWORD *)NtCurrentTeb()->UserPrefLanguages + 1)
          : *(_QWORD *)(v8 + 48);
      v10 = RtlpSetProcUserMachineLangList(v8, 0);
      if ( v10 >= 0 )
      {
        v4 = *(_QWORD *)(v8 + 56);
        v13 = v72;
        goto LABEL_32;
      }
    }
LABEL_113:
    v5 = 0;
    goto LABEL_114;
  }
  v13 = 0;
  v72 = 0;
LABEL_32:
  if ( !NtCurrentTeb()->MergedPrefLanguages )
  {
    v61 = 0;
    if ( v62 && !PreferredLanguages )
    {
      v54 = *(_QWORD *)(v8 + 96);
      if ( v54 )
      {
        if ( v13 && (*(_BYTE *)(v13 + 40) & 0x40) != 0 && *(char *)(v54 + 40) >= 0 )
        {
          MergedPrefLanguages = *(_WORD **)(v8 + 96);
          NtCurrentTeb()->MuiGeneration = *(_DWORD *)(v8 + 16);
          goto LABEL_37;
        }
      }
    }
LABEL_121:
    if ( (v6 & 0x10000) == 0 )
    {
      RtlpInitMuiCriticalSection();
      RtlEnterCriticalSection(RegistryInfoCritSect);
      v38 = RtlpMuiRegDupLanguageList(*(_QWORD *)(v8 + 72));
      v78 = v38;
      v69 = *(_DWORD *)(v8 + 16);
      RtlLeaveCriticalSection(RegistryInfoCritSect);
LABEL_123:
      if ( !v8 )
      {
        v10 = -1073741811;
        goto LABEL_148;
      }
      Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 214);
      MergedPrefLanguages = (_WORD *)Heap_0;
      if ( Heap_0 )
      {
        *(_DWORD *)Heap_0 = 214;
        *(_DWORD *)(Heap_0 + 4) = 1638400;
        *(_BYTE *)(Heap_0 + 8) = 0;
        *(_QWORD *)(Heap_0 + 24) = Heap_0 + 64;
        *(_DWORD *)(Heap_0 + 40) = 0;
        *(_QWORD *)(Heap_0 + 16) = v8;
      }
      else
      {
        MergedPrefLanguages = 0;
      }
      v64 = (__int64)MergedPrefLanguages;
      if ( !MergedPrefLanguages )
      {
        v10 = -1073741801;
        goto LABEL_78;
      }
      if ( v12 )
      {
        v49 = LdrpMergeLangFallbackLists(v6, v8, &v64, PreferredLanguages, 0, v72, v4, v73, 0);
        MergedPrefLanguages = (_WORD *)v64;
        v10 = v49;
      }
      else
      {
        v40 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 214);
        v41 = (void *)v40;
        if ( v40 )
        {
          *(_DWORD *)v40 = 214;
          *(_DWORD *)(v40 + 4) = 1638400;
          *(_BYTE *)(v40 + 8) = 0;
          *(_QWORD *)(v40 + 24) = v40 + 64;
          *(_DWORD *)(v40 + 40) = 0;
          *(_QWORD *)(v40 + 16) = v8;
        }
        else
        {
          v41 = 0;
        }
        v60 = v4;
        v42 = v72;
        Src = v41;
        v59 = v38;
        v43 = PreferredLanguages;
        v44 = LdrpMergeLangFallbackLists(v6, v8, &Src, PreferredLanguages, v59, v72, v60, v73, 0);
        v46 = Src;
        v10 = v44;
        if ( v44 >= 0 )
        {
          LOBYTE(v45) = v62 || (v6 & 0x10) != 0;
          v47 = RtlpAddNeutralsToMergedList(v45, v8, Src, &v64);
          MergedPrefLanguages = (_WORD *)v64;
          v10 = v47;
        }
        RtlpMuiRegFreeLanguageList(v46);
        PreferredLanguages = v43;
        v72 = v42;
      }
      if ( v10 < 0 )
        goto LABEL_148;
      goto LABEL_37;
    }
LABEL_164:
    v38 = 0;
    goto LABEL_123;
  }
  v61 = 1;
  if ( !v62 )
    goto LABEL_121;
  if ( *((char *)NtCurrentTeb()->MergedPrefLanguages + 40) < 0 || NtCurrentTeb()->MuiGeneration != *(_DWORD *)(v8 + 16) )
  {
    v61 = 0;
    RtlpMuiRegFreeLanguageList(NtCurrentTeb()->MergedPrefLanguages);
    NtCurrentTeb()->MergedPrefLanguages = 0;
    goto LABEL_121;
  }
  MergedPrefLanguages = NtCurrentTeb()->MergedPrefLanguages;
LABEL_37:
  if ( !MergedPrefLanguages )
  {
    v10 = 0;
    v55 = v77;
    if ( String1 )
    {
      if ( *v77 < 2u )
        v10 = -1073741789;
      else
        *(_DWORD *)String1 = 0;
    }
    *v55 = 2;
    goto LABEL_73;
  }
  v14 = v77;
  v15 = 0;
  v16 = 0;
  LODWORD(v64) = 0;
  v17 = 0;
  v65 = 0;
  v18 = 0;
  v67 = 0;
  v19 = *v77;
  v68 = *v77;
  if ( !MergedPrefLanguages[2] )
    goto LABEL_67;
  v20 = v6 & 4;
  do
  {
    memset(v82, 0, 28);
    v21 = (unsigned __int16 *)(*((_QWORD *)MergedPrefLanguages + 3) + 6LL * v18);
    if ( !v21 || !v8 )
      goto LABEL_65;
    v22 = *v21;
    if ( v22 == 1 )
    {
      v82[2] = v21[2];
LABEL_44:
      v23 = v82;
      goto LABEL_45;
    }
    v23 = 0;
    v32 = v22 - 2;
    if ( v32 )
    {
      if ( v32 == 1 )
      {
        v82[3] = v21[2];
        goto LABEL_44;
      }
    }
    else
    {
      v23 = (_WORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 24) + 16LL) + 28LL * (__int16)v21[2]);
    }
LABEL_45:
    if ( v20 )
    {
      *(_QWORD *)String = 0;
      v84 = 0;
      v66 = 0;
      v76 = 0;
      if ( !v23 )
        goto LABEL_155;
      if ( v23[2] )
      {
        v24 = (unsigned __int16)v23[2];
      }
      else
      {
        v56 = (__int16)v23[3];
        if ( (__int16)v56 <= 0 )
        {
          v25 = -1073741595;
          goto LABEL_63;
        }
        v57 = (const wchar_t *)(*(_QWORD *)(*(_QWORD *)(v8 + 32) + 24LL)
                              + 2LL * *(__int16 *)(*(_QWORD *)(*(_QWORD *)(v8 + 32) + 16LL) + 2 * v56));
        *((_QWORD *)&v76 + 1) = v57;
        if ( v57 )
        {
          v58 = 2 * wcslen(v57);
          if ( v58 >= 0xFFFE )
            LOWORD(v58) = -4;
          LOWORD(v76) = v58;
          WORD1(v76) = v58 + 2;
        }
        if ( !(unsigned __int8)RtlCultureNameToLCID(&v76, &v66) )
        {
          v17 = v67;
LABEL_155:
          v25 = -1073741811;
          goto LABEL_63;
        }
        v24 = v66;
      }
      v25 = RtlIntegerToUnicode(v24, 16, 4294967292LL, String);
      v66 = v25;
      if ( v25 < 0 )
        goto LABEL_112;
      DWORD1(v76) = 0;
      *((_QWORD *)&v76 + 1) = String;
      v26 = 2 * wcslen(String);
      if ( v26 >= 0xFFFE )
        LOWORD(v26) = -4;
      LOWORD(v76) = v26;
      WORD1(v76) = v26 + 2;
      v27 = v64;
      if ( v24 == 4096 || !(_DWORD)v64 || (unsigned int)v64 > v68 )
        goto LABEL_57;
      if ( !(unsigned __int8)RtlpLangNameInMultiSzString_Size(String1, String) )
      {
        v27 = v64;
LABEL_57:
        LODWORD(v64) = v27 + ((unsigned __int16)v26 >> 1);
        v28 = v64 + 1;
        if ( String1 && v27 < v28 )
        {
          if ( v28 < v68 )
          {
            memmove(&String1[v27], String, (unsigned __int16)v26);
            String1[(unsigned int)v64] = 0;
            goto LABEL_61;
          }
LABEL_171:
          v25 = -1073741789;
        }
        else
        {
          if ( v28 >= v68 && String1 )
            goto LABEL_171;
LABEL_61:
          v25 = v66;
        }
        v17 = v67;
        v15 = v28;
        LODWORD(v64) = v28;
        goto LABEL_63;
      }
      v15 = v64;
      v25 = v66;
      v17 = v67;
    }
    else
    {
      *(_OWORD *)String2 = 0;
      if ( !v23 )
        goto LABEL_155;
      *(_QWORD *)&v76 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 170);
      if ( (_QWORD)v76 )
      {
        v33 = (__int16)v23[3];
        if ( (__int16)v33 <= 0 )
        {
          String2[1] = (wchar_t *)v76;
          v34 = (unsigned __int16)v23[2];
          LODWORD(String2[0]) = 11141120;
          if ( (unsigned __int8)RtlLCIDToCultureName(v34, String2) )
          {
            v35 = String2[1];
            Src = String2[1];
            goto LABEL_92;
          }
          v66 = -1073741595;
LABEL_111:
          RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v76);
          v25 = v66;
LABEL_112:
          v17 = v67;
          goto LABEL_63;
        }
        v35 = (wchar_t *)(*(_QWORD *)(*(_QWORD *)(v8 + 32) + 24LL)
                        + 2LL * *(__int16 *)(*(_QWORD *)(*(_QWORD *)(v8 + 32) + 16LL) + 2 * v33));
        Src = v35;
        if ( v35 )
        {
          v36 = 2 * wcslen(v35);
          if ( v36 >= 0xFFFE )
            v36 = 65532;
          WORD1(String2[0]) = v36 + 2;
          v35 = (wchar_t *)Src;
        }
        else
        {
LABEL_92:
          v36 = LOWORD(String2[0]);
        }
        v80 = v36;
        v66 = 0;
        if ( v15 && v15 <= v68 )
        {
          if ( (unsigned __int8)RtlpLangNameInMultiSzString_Size(String1, v35) )
            goto LABEL_111;
          LOWORD(v36) = v80;
        }
        LODWORD(v64) = v15 + ((unsigned __int16)v36 >> 1);
        v37 = v64 + 1;
        if ( String1 && v15 < v37 )
        {
          if ( v37 < v68 )
          {
            memmove(&String1[v15], Src, (unsigned __int16)v36);
            String1[(unsigned int)v64] = 0;
            goto LABEL_110;
          }
        }
        else if ( v37 < v68 || !String1 )
        {
          goto LABEL_110;
        }
        v66 = -1073741789;
LABEL_110:
        v15 = v37;
        LODWORD(v64) = v37;
        goto LABEL_111;
      }
      v17 = v67;
      v25 = -1073741801;
    }
LABEL_63:
    if ( v25 >= 0 )
      goto LABEL_64;
    if ( v25 == -1073741789 )
    {
      v65 = 1;
LABEL_64:
      v67 = ++v17;
    }
LABEL_65:
    ++v18;
  }
  while ( v18 < MergedPrefLanguages[2] );
  v14 = v77;
  v19 = v68;
  v16 = v65;
LABEL_67:
  v29 = String1;
  if ( String1 )
  {
    if ( v15 >= v19 )
      v16 = 1;
    else
      String1[v15] = 0;
  }
  v30 = v15 + 1;
  if ( !v17 )
  {
    if ( v29 )
    {
      if ( (unsigned int)v30 >= v19 )
        v16 = 1;
      else
        v29[v30] = 0;
    }
    LODWORD(v30) = v15 + 2;
  }
  v31 = v81;
  *v14 = v30;
  v10 = v16 != 0 ? 0xC0000023 : 0;
  if ( v31 )
    *v31 = v17;
LABEL_73:
  if ( ((int)(v10 + 0x80000000) < 0 || v10 == -1073741789) && v62 )
  {
    if ( !MergedPrefLanguages[22] )
      RtlpComputeLangListCheckSum(MergedPrefLanguages);
    if ( !v61 )
    {
      if ( (MergedPrefLanguages[20] & 0x40) == 0 )
      {
        RtlpMUIRegPatchLicenseInfortmation(MergedPrefLanguages);
        if ( !PreferredLanguages && (*(_BYTE *)(v72 + 40) & 0x40) != 0 && v73 == *(_QWORD *)(v8 + 48) )
          RtlpSetProcMergedLangList(v8, MergedPrefLanguages);
      }
      v48 = v69;
      NtCurrentTeb()->MergedPrefLanguages = MergedPrefLanguages;
      NtCurrentTeb()->MuiGeneration = v48;
    }
    goto LABEL_78;
  }
LABEL_148:
  if ( MergedPrefLanguages )
  {
    if ( MergedPrefLanguages == NtCurrentTeb()->MergedPrefLanguages )
      NtCurrentTeb()->MergedPrefLanguages = 0;
    RtlpMuiRegFreeLanguageList(MergedPrefLanguages);
  }
LABEL_78:
  v5 = v63;
  if ( v10 < 0 )
    goto LABEL_114;
LABEL_79:
  if ( v5 && v8 )
    RtlpMuiFreeLangRegistryInfo(v8);
  if ( v78 )
  {
    if ( (*(_BYTE *)(v78 + 40) & 0x40) == 0 )
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v78);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000d3e0  mov     [rsp-8+arg_0], rbx
0x18000d3e5  push    rbp
0x18000d3e6  push    rsi
0x18000d3e7  push    rdi
0x18000d3e8  push    r12
0x18000d3ea  push    r13
0x18000d3ec  push    r14
0x18000d3ee  push    r15
0x18000d3f0  lea     rbp, [rsp-20h]
0x18000d3f5  sub     rsp, 120h
0x18000d3fc  mov     rax, cs:__security_cookie
0x18000d403  xor     rax, rsp
0x18000d406  mov     [rbp+50h+var_38], rax
0x18000d40a  xor     r12d, r12d
0x18000d40d  mov     [rbp+50h+var_98], r9
0x18000d411  xor     r15b, r15b
0x18000d414  mov     [rsp+150h+String1], r8
0x18000d419  mov     eax, ecx
0x18000d41b  mov     [rbp+50h+var_70], rdx
0x18000d41f  and     eax, 30h
0x18000d422  mov     [rbp+50h+var_B0], r12d
0x18000d426  mov     [rbp+50h+var_90], r12
0x18000d42a  mov     ebx, ecx
0x18000d42c  mov     [rsp+150h+var_F8], r12
0x18000d431  mov     esi, r12d
0x18000d434  mov     [rsp+150h+var_FE], r15b
0x18000d439  mov     r13d, r12d
0x18000d43c  cmp     al, 30h ; '0'
0x18000d43e  jz      loc_18000E089
0x18000d444  xor     r14b, r14b
0x18000d447  mov     [rsp+150h+var_FF], r14b
0x18000d44c  test    r9, r9
0x18000d44f  jz      short loc_18000D457
0x18000d451  mov     eax, [r9]
0x18000d454  mov     [rbp+50h+var_B0], eax
0x18000d457  test    ebx, 0FFFEFC83h
0x18000d45d  jnz     loc_18000DF5B
0x18000d463  mov     eax, ebx
0x18000d465  and     eax, 4
0x18000d468  test    bl, 8
0x18000d46b  jz      short loc_18000D47B
0x18000d46d  test    eax, eax
0x18000d46f  jz      short loc_18000D482
0x18000d471  mov     edi, 0C000000Dh
0x18000d476  jmp     loc_18000DAC3
0x18000d47b  test    eax, eax
0x18000d47d  jnz     short loc_18000D482
0x18000d47f  or      ebx, 8
0x18000d482  bt      ebx, 10h
0x18000d486  jb      loc_18000DF8A
0x18000d48c  mov     ecx, ebx
0x18000d48e  and     ecx, 10h
0x18000d491  bt      ebx, 6
0x18000d495  jb      short loc_18000D4A7
0x18000d497  test    ecx, ecx
0x18000d499  jnz     short loc_18000D4BA
0x18000d49b  mov     eax, ebx
0x18000d49d  and     eax, 20h
0x18000d4a0  jnz     short loc_18000D4BA
0x18000d4a2  or      ebx, 20h
0x18000d4a5  jmp     short loc_18000D4BA
0x18000d4a7  test    ecx, ecx
0x18000d4a9  jnz     loc_18000DF5B
0x18000d4af  mov     eax, ebx
0x18000d4b1  and     eax, 20h
0x18000d4b4  jnz     loc_18000E128
0x18000d4ba  test    r9, r9
0x18000d4bd  jz      loc_18000E132
0x18000d4c3  cmp     [r9], esi
0x18000d4c6  jbe     short loc_18000D4D1
0x18000d4c8  test    r8, r8
0x18000d4cb  jz      loc_18000E13C
0x18000d4d1  mov     eax, ebx
0x18000d4d3  and     eax, 300h
0x18000d4d8  cmp     eax, 300h
0x18000d4dd  jz      loc_18000E146
0x18000d4e3  lea     rcx, [rsp+150h+var_F8]
0x18000d4e8  call    RtlpCreateProcessRegistryInfo
0x18000d4ed  test    eax, eax
0x18000d4ef  js      loc_18000D8ED
0x18000d4f5  test    r14b, r14b
0x18000d4f8  jz      loc_18000DD95
0x18000d4fe  mov     r13, [rsp+150h+var_F8]
0x18000d503  mov     eax, ds:7FFE03A4h
0x18000d50a  cmp     [r13+0Ch], eax
0x18000d50e  jnz     loc_18000DD6F
0x18000d514  mov     r15d, ebx
0x18000d517  mov     [rsp+150h+var_E0], r12d
0x18000d51c  mov     [rbp+50h+var_C0], r12
0x18000d520  mov     [rbp+50h+var_D0], r12
0x18000d524  and     r15d, 10000h
0x18000d52b  jnz     loc_18000DE43
0x18000d531  mov     rax, gs:30h
0x18000d53a  cmp     [rax+17D0h], rsi
0x18000d541  jz      short loc_18000D557
0x18000d543  mov     rax, gs:30h
0x18000d54c  mov     rcx, [rax+17D0h]
0x18000d553  mov     [rbp+50h+var_D0], rcx
0x18000d557  mov     r14d, ebx
0x18000d55a  and     r14d, 40h
0x18000d55e  jnz     loc_18000DAFE
0x18000d564  mov     rdx, r13
0x18000d567  xor     ecx, ecx
0x18000d569  call    InitializeTEBUserLangList
0x18000d56e  mov     edi, eax
0x18000d570  test    eax, eax
0x18000d572  js      loc_18000DAC0
0x18000d578  mov     rax, gs:30h
0x18000d581  mov     rcx, [rax+17D8h]
0x18000d588  mov     rax, [rcx]
0x18000d58b  mov     [rbp+50h+var_C8], rax
0x18000d58f  mov     rax, gs:30h
0x18000d598  mov     rcx, [rax+17D8h]
0x18000d59f  cmp     [rcx+8], rsi
0x18000d5a3  jz      loc_18000DAF1
0x18000d5a9  mov     rax, gs:30h
0x18000d5b2  mov     rcx, [rax+17D8h]
0x18000d5b9  mov     r12, [rcx+8]
0x18000d5bd  mov     [rbp+50h+var_C0], r12
0x18000d5c1  xor     edx, edx
0x18000d5c3  mov     rcx, r13
0x18000d5c6  call    RtlpSetProcUserMachineLangList
0x18000d5cb  mov     edi, eax
0x18000d5cd  test    eax, eax
0x18000d5cf  js      loc_18000DAC0
0x18000d5d5  mov     r12, [r13+38h]
0x18000d5d9  mov     rdi, [rbp+50h+var_C8]
0x18000d5dd  mov     rax, gs:30h
0x18000d5e6  cmp     [rax+17E0h], rsi
0x18000d5ed  jz      loc_18000DB0A
0x18000d5f3  mov     [rsp+150h+var_100], 1
0x18000d5f8  cmp     [rsp+150h+var_FF], sil
0x18000d5fd  jz      loc_18000DB1A
0x18000d603  mov     rax, gs:30h
0x18000d60c  mov     rcx, [rax+17E0h]
0x18000d613  test    byte ptr [rcx+28h], 80h
0x18000d617  jnz     loc_18000DD00
0x18000d61d  mov     rcx, gs:30h
0x18000d626  mov     eax, [r13+10h]
0x18000d62a  cmp     [rcx+1798h], eax
0x18000d630  jnz     loc_18000DD00
0x18000d636  mov     rax, gs:30h
0x18000d63f  mov     rsi, [rax+17E0h]
0x18000d646  test    rsi, rsi
0x18000d649  jz      loc_18000DFA2
0x18000d64f  mov     r9, [rbp+50h+var_98]
0x18000d653  xor     r12d, r12d
0x18000d656  xor     dil, dil
0x18000d659  mov     dword ptr [rsp+150h+var_F8], r12d
0x18000d65e  xor     r8d, r8d
0x18000d661  mov     [rsp+150h+var_F0], dil
0x18000d666  xor     r15d, r15d
0x18000d669  mov     [rsp+150h+var_E8], r8d
0x18000d66e  mov     r10d, [r9]
0x18000d671  xor     eax, eax
0x18000d673  mov     [rsp+150h+var_E4], r10d
0x18000d678  cmp     ax, [rsi+4]
0x18000d67c  jnb     loc_18000D834
0x18000d682  and     ebx, 4
0x18000d685  mov     edi, 0C000000Dh
0x18000d68a  mov     r9d, 0AAh
0x18000d690  movzx   eax, r15w
0x18000d694  xorps   xmm0, xmm0
0x18000d697  movups  xmmword ptr [rbp+50h+var_68], xmm0
0x18000d69b  movups  xmmword ptr [rbp+50h+var_68+0Ch], xmm0
0x18000d69f  lea     rcx, [rax+rax*2]
0x18000d6a3  mov     rax, [rsi+18h]
0x18000d6a7  lea     rdx, [rax+rcx*2]
0x18000d6ab  test    rdx, rdx
0x18000d6ae  jz      loc_18000D817
0x18000d6b4  test    r13, r13
0x18000d6b7  jz      loc_18000D817
0x18000d6bd  movzx   ecx, word ptr [rdx]
0x18000d6c0  cmp     ecx, 1
0x18000d6c3  jnz     loc_18000D915
0x18000d6c9  movzx   eax, word ptr [rdx+4]
0x18000d6cd  mov     [rbp+50h+var_68+4], ax
0x18000d6d1  lea     r14, [rbp+50h+var_68]
0x18000d6d5  test    ebx, ebx
0x18000d6d7  jz      loc_18000D937
0x18000d6dd  xor     eax, eax
0x18000d6df  mov     qword ptr [rbp+50h+String], rax
0x18000d6e3  mov     [rbp+50h+var_40], ax
0x18000d6e7  mov     [rsp+150h+var_EC], eax
0x18000d6eb  movups  [rbp+50h+var_A8], xmm0
0x18000d6ef  test    r14, r14
0x18000d6f2  jz      loc_18000DE11
0x18000d6f8  movzx   eax, word ptr [r14+4]
0x18000d6fd  test    ax, ax
0x18000d700  jz      loc_18000E091
0x18000d706  mov     r14d, eax
0x18000d709  lea     r9, [rbp+50h+String]
0x18000d70d  mov     edx, 10h
0x18000d712  mov     r8d, 0FFFFFFFCh
0x18000d718  mov     ecx, r14d
0x18000d71b  call    RtlIntegerToUnicode
0x18000d720  mov     [rsp+150h+var_EC], eax
0x18000d724  test    eax, eax
0x18000d726  js      loc_18000DAB0
0x18000d72c  lea     rax, [rbp+50h+String]
0x18000d730  mov     dword ptr [rbp+50h+var_A8+4], 0
0x18000d737  lea     rcx, [rbp+50h+String]; String
0x18000d73b  mov     qword ptr [rbp+50h+var_A8+8], rax
0x18000d73f  call    wcslen
0x18000d744  mov     r12, rax
0x18000d747  mov     eax, 0FFFCh
0x18000d74c  add     r12, r12
0x18000d74f  cmp     r12, 0FFFEh
0x18000d756  cmovnb  r12, rax
0x18000d75a  mov     word ptr [rbp+50h+var_A8], r12w
0x18000d75f  lea     ecx, [r12+2]
0x18000d764  mov     word ptr [rbp+50h+var_A8+2], cx
0x18000d768  mov     ecx, dword ptr [rsp+150h+var_F8]
0x18000d76c  cmp     r14d, 1000h
0x18000d773  jz      short loc_18000D79C
0x18000d775  test    ecx, ecx
0x18000d777  jz      short loc_18000D79C
0x18000d779  cmp     ecx, [rsp+150h+var_E4]
0x18000d77d  ja      short loc_18000D79C
0x18000d77f  mov     r8d, ecx
0x18000d782  lea     rdx, [rbp+50h+String]; String2
0x18000d786  mov     rcx, [rsp+150h+String1]; String1
0x18000d78b  call    RtlpLangNameInMultiSzString_Size
0x18000d790  test    al, al
0x18000d792  jnz     loc_18000DDE0
0x18000d798  mov     ecx, dword ptr [rsp+150h+var_F8]
0x18000d79c  mov     rdx, [rsp+150h+String1]
0x18000d7a1  movzx   eax, r12w
0x18000d7a5  shr     eax, 1
0x18000d7a7  add     eax, ecx
0x18000d7a9  mov     dword ptr [rsp+150h+var_F8], eax
0x18000d7ad  lea     r14d, [rax+1]
0x18000d7b1  test    rdx, rdx
0x18000d7b4  jz      loc_18000DED6
0x18000d7ba  cmp     ecx, r14d
0x18000d7bd  jnb     loc_18000DED6
0x18000d7c3  cmp     r14d, [rsp+150h+var_E4]
0x18000d7c8  jnb     loc_18000DEEA
0x18000d7ce  mov     eax, ecx
0x18000d7d0  movzx   r8d, r12w; Size
0x18000d7d4  lea     rcx, [rdx+rax*2]; void *
0x18000d7d8  lea     rdx, [rbp+50h+String]; Src
0x18000d7dc  call    memmove
0x18000d7e1  mov     ecx, dword ptr [rsp+150h+var_F8]
0x18000d7e5  xor     eax, eax
0x18000d7e7  mov     rdx, [rsp+150h+String1]
0x18000d7ec  mov     [rdx+rcx*2], ax
0x18000d7f0  mov     eax, [rsp+150h+var_EC]
0x18000d7f4  mov     r8d, [rsp+150h+var_E8]
0x18000d7f9  mov     r12d, r14d
0x18000d7fc  mov     dword ptr [rsp+150h+var_F8], r14d
0x18000d801  mov     r9d, 0AAh
0x18000d807  test    eax, eax
0x18000d809  js      loc_18000E109
0x18000d80f  inc     r8d
0x18000d812  mov     [rsp+150h+var_E8], r8d
0x18000d817  inc     r15w
0x18000d81b  cmp     r15w, [rsi+4]
0x18000d820  jb      loc_18000D690
0x18000d826  mov     r9, [rbp+50h+var_98]
0x18000d82a  mov     r10d, [rsp+150h+var_E4]
0x18000d82f  movzx   edi, [rsp+150h+var_F0]
0x18000d834  mov     r11, [rsp+150h+String1]
0x18000d839  test    r11, r11
0x18000d83c  jz      short loc_18000D851
0x18000d83e  cmp     r12d, r10d
0x18000d841  jnb     loc_18000E06F
0x18000d847  mov     ecx, r12d
0x18000d84a  xor     eax, eax
0x18000d84c  mov     [r11+rcx*2], ax
0x18000d851  lea     edx, [r12+1]
0x18000d856  test    r8d, r8d
0x18000d859  jz      loc_18000DEBA
0x18000d85f  mov     rax, [rbp+50h+var_70]
0x18000d863  neg     dil
0x18000d866  mov     [r9], edx
0x18000d869  sbb     edi, edi
0x18000d86b  and     edi, 0C0000023h
0x18000d871  test    rax, rax
0x18000d874  jz      short loc_18000D879
0x18000d876  mov     [rax], r8d
0x18000d879  mov     ecx, 80000000h
0x18000d87e  lea     eax, [rdi+rcx]
0x18000d881  test    ecx, eax
0x18000d883  jz      loc_18000D9A7
0x18000d889  cmp     [rsp+150h+var_FF], 0
0x18000d88e  jz      loc_18000DDA4
0x18000d894  cmp     word ptr [rsi+2Ch], 0
0x18000d899  jnz     short loc_18000D8A3
0x18000d89b  mov     rcx, rsi
0x18000d89e  call    RtlpComputeLangListCheckSum
0x18000d8a3  cmp     [rsp+150h+var_100], 0
0x18000d8a8  jz      loc_18000DCB5
0x18000d8ae  movzx   r15d, [rsp+150h+var_FE]
0x18000d8b4  test    edi, edi
0x18000d8b6  js      loc_18000DAC3
0x18000d8bc  test    r15b, r15b
0x18000d8bf  jnz     loc_18000E059
0x18000d8c5  mov     rax, [rbp+50h+var_90]
0x18000d8c9  test    rax, rax
  ... truncated ...
```
