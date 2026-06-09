# VpnProfileActiveSettingsGet

- ea: `0x1800dfbdc`
- end: `0x1800e0a87`
- name: `VpnProfileActiveSettingsGet`
- size: `3755`
- prototype: `__int64 __fastcall(LPCWSTR, LPCWSTR)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cea20`
- `0x1800d9a60`
- `0x1800e0e34`

## callees

- `0x180005bfc`
- `0x180005c40`
- `0x18000ec50`
- `0x180068a80`
- `0x1800696dc`
- `0x1800ab634`
- `0x1800cf4f0`
- `0x1800d1364`
- `0x1800dbb2c`
- `0x1800dc1d0`
- `0x1800df9dc`
- `0x1800dfbdc`
- `0x1800e3ca0`
- `0x1800e3fac`
- `0x1800e4364`
- `0x1800e4534`
- `0x1800e8e7e`

## import_xrefs

- `msvcrt!tolower` at `0x1800e0607`
- `msvcrt!tolower` at `0x1800e07f3`
- `msvcrt!tolower` at `0x1800e0607`
- `msvcrt!tolower` at `0x1800e07f3`
- `fwpuclnt!FwpmGetAppIdFromFileName0` at `0x1800e0082`
- `fwpuclnt!FwpmGetAppIdFromFileName0` at `0x1800e0082`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800e02a3`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800e02a3`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasFreeEntryAdvancedProperties` at `0x1800e0a2b`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasFreeEntryAdvancedProperties` at `0x1800e0a2b`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800dfda3`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800dfee3`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800dfda3`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800dfee3`

## string_xrefs

- `0x1800e08ab`: `VpnStringCopy for szDnsSuffix`

## pseudocode

```c
__int64 __fastcall VpnProfileActiveSettingsGet(LPCWSTR a1, WCHAR *a2, __int64 a3, __int64 *a4)
{
  __int64 v8; // r12
  const char *v9; // rax
  const char *v10; // r9
  unsigned int EntryByName; // eax
  struct tagRASENTRYADVANCED *v12; // r13
  unsigned int v13; // edi
  __int64 v14; // r15
  const char *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  struct _LIST_ENTRY *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rax
  unsigned int v25; // eax
  __int64 v26; // r12
  unsigned int v27; // ebx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  __int64 v31; // rax
  char *v32; // rax
  const WCHAR *v33; // rbx
  DWORD AppIdFromFileName0; // eax
  unsigned int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rax
  void *v38; // r9
  struct _LIST_ENTRY *v39; // rcx
  void *v40; // rbx
  _WORD *v41; // rax
  __int64 v42; // r8
  unsigned __int64 v43; // rbx
  __int64 v44; // rax
  _WORD *v45; // rdx
  unsigned __int64 v46; // rbx
  _WORD *v47; // rcx
  __int64 v48; // rax
  _WORD *v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rdx
  unsigned int v53; // eax
  __int64 v54; // r14
  __int128 *v55; // rcx
  _OWORD *v56; // rax
  __int64 v57; // rdx
  __int128 v58; // xmm0
  __int64 v59; // r13
  __int64 v60; // r12
  __int64 v61; // rbx
  unsigned int v62; // eax
  __int64 v63; // rax
  __int64 v64; // rax
  _QWORD *v65; // r14
  int v66; // ebx
  int v67; // eax
  int v68; // ecx
  __int64 v69; // rbx
  __int16 v70; // ax
  int v71; // ebx
  int v72; // eax
  int v73; // ecx
  unsigned int v74; // eax
  unsigned int ExemptionNrptRules; // eax
  void *Src; // [rsp+30h] [rbp-40h]
  int v78; // [rsp+38h] [rbp-38h]
  struct tagRASENTRYW *v79; // [rsp+40h] [rbp-30h] BYREF
  FWP_BYTE_BLOB *appId; // [rsp+48h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-20h] BYREF
  struct tagRASENTRYADVANCED *v82; // [rsp+58h] [rbp-18h] BYREF
  struct tagRASENTRYADVANCED *v83; // [rsp+60h] [rbp-10h]
  LPVOID v84; // [rsp+68h] [rbp-8h]

  LODWORD(v8) = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    v9 = (const char *)a2;
    LODWORD(v10) = (_DWORD)a1;
    if ( !a2 )
      v9 = L"<NULL>";
    if ( !a1 )
      v10 = L"<NULL>";
    WPP_SF_SS(
      WPP_GLOBAL_Control[1].Flink,
      879,
      (unsigned int)&WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
      (_DWORD)v10,
      (__int64)v9);
  }
  v79 = 0;
  Src = 0;
  lpMem = 0;
  v82 = 0;
  appId = 0;
  *a4 = 0;
  EntryByName = VpnProfileGetEntryByName(a1, a2, a3, &v79, &v82);
  v12 = v82;
  v13 = EntryByName;
  v78 = EntryByName;
  v84 = v79;
  v83 = v82;
  if ( EntryByName )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 880, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, EntryByName);
    }
    v14 = 0;
    v15 = "VpnProfileGetEntryByName";
    v16 = v13;
LABEL_13:
    VpnReportError("VpnProfileActiveSettingsGet", v15, v16);
LABEL_232:
    if ( v13 )
      goto LABEL_233;
    v40 = 0;
    goto LABEL_236;
  }
  v17 = VpnAlloc(136);
  v14 = v17;
  if ( !v17 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 881, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
      v18 = WPP_GLOBAL_Control;
    }
    v13 = 14;
    if ( v18 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v18[1].Blink) & 1) == 0 )
      goto LABEL_233;
    v19 = 882;
LABEL_21:
    v20 = 14;
LABEL_22:
    WPP_SF_d(v18[1].Flink, v19, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v20);
    goto LABEL_233;
  }
  if ( (*((_BYTE *)v12 + 4) & 0x40) != 0 )
    *(_DWORD *)(v17 + 128) = 1;
  v21 = *((_QWORD *)v12 + 18);
  if ( v21 )
  {
    v22 = AppContainerDeriveSidFromMoniker(v21 + 4, a3);
    v78 = v22;
    v13 = v22;
    if ( v22 >= 0 )
    {
      v13 = 0;
      v78 = 0;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 883, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v22);
        v18 = WPP_GLOBAL_Control;
      }
      if ( (v13 & 0x1FFF0000) == 0x70000 )
      {
        v13 = (unsigned __int16)v13;
        v78 = (unsigned __int16)v13;
      }
      if ( v13 )
      {
        if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 1) != 0 )
        {
          v19 = 884;
          goto LABEL_36;
        }
        goto LABEL_233;
      }
    }
  }
  v23 = *((_DWORD *)v12 + 26);
  if ( !v23 )
  {
LABEL_62:
    v29 = *((_DWORD *)v84 + 873);
    if ( !v29 )
      v29 = 300;
    *(_DWORD *)(v14 + 124) = v29;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        889,
        &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
        *((unsigned int *)v12 + 30));
      v18 = WPP_GLOBAL_Control;
    }
    v30 = *((_DWORD *)v12 + 30);
    if ( !v30 )
      goto LABEL_120;
    v31 = VpnAlloc((unsigned int)(16 * v30));
    *(_QWORD *)(v14 + 48) = v31;
    if ( !v31 )
    {
      v13 = 14;
      v78 = 14;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_73;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 890, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
    }
    v18 = WPP_GLOBAL_Control;
LABEL_73:
    if ( !*(_QWORD *)(v14 + 48) )
    {
      v13 = 14;
      if ( v18 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v18[1].Blink) & 1) == 0 )
        goto LABEL_233;
      v19 = 891;
      goto LABEL_21;
    }
    v32 = (char *)*((_QWORD *)v12 + 16);
    v82 = (struct tagRASENTRYADVANCED *)v32;
    LODWORD(v79) = 0;
    if ( *((_DWORD *)v12 + 30) )
    {
      while ( 1 )
      {
        v33 = (const WCHAR *)(v32 + 8);
        AppIdFromFileName0 = FwpmGetAppIdFromFileName0((PCWSTR)v32 + 4, &appId);
        v78 = AppIdFromFileName0;
        v13 = AppIdFromFileName0;
        if ( !AppIdFromFileName0 )
          break;
        if ( AppIdFromFileName0 - 2 <= 1 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control[1].Flink,
              892,
              &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
              (unsigned int)v79,
              AppIdFromFileName0);
          }
          v35 = int_ConvertClassicAppPathToDevicePath(v33, (unsigned __int16 **)&lpMem);
          v78 = v35;
          v13 = v35;
          if ( v35 )
          {
            v39 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            {
              if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_Sd(
                  WPP_GLOBAL_Control[1].Flink,
                  895,
                  (unsigned int)&WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                  (_DWORD)v33,
                  v35);
                v39 = WPP_GLOBAL_Control;
              }
              if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v39[1].Blink) & 1) != 0 )
                WPP_SF_d(v39[1].Flink, 896, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v13);
            }
            v40 = lpMem;
            goto LABEL_234;
          }
          v36 = -1;
          Src = lpMem;
          do
            ++v36;
          while ( *((_WORD *)lpMem + v36) );
          *(_DWORD *)(*(_QWORD *)(v14 + 48) + 16LL * (unsigned int)v8) = 2 * v36 + 2;
          *(_QWORD *)(*(_QWORD *)(v14 + 48) + 16LL * (unsigned int)v8 + 8) = VpnAlloc(*(unsigned int *)(*(_QWORD *)(v14 + 48) + 16LL * (unsigned int)v8));
          if ( *(_QWORD *)(*(_QWORD *)(v14 + 48) + 16LL * (unsigned int)v8 + 8) )
          {
LABEL_93:
            v18 = WPP_GLOBAL_Control;
          }
          else
          {
            v13 = 14;
            v78 = 14;
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 893, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
              goto LABEL_93;
            }
          }
          v37 = *(_QWORD *)(v14 + 48);
          if ( !*(_QWORD *)(v37 + 16LL * (unsigned int)v8 + 8) )
          {
            v13 = 14;
            if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 1) != 0 )
            {
              v19 = 894;
              goto LABEL_21;
            }
            goto LABEL_233;
          }
          memcpy_0(*(void **)(v37 + 16LL * (unsigned int)v8 + 8), Src, *(unsigned int *)(v37 + 16LL * (unsigned int)v8));
          MprCommonFree(Src);
          Src = 0;
          lpMem = 0;
LABEL_103:
          LODWORD(v8) = v8 + 1;
          goto LABEL_104;
        }
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control[1].Flink,
            897,
            (unsigned int)&WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
            (_DWORD)v33,
            AppIdFromFileName0);
        }
LABEL_104:
        LODWORD(v79) = (_DWORD)v79 + 1;
        if ( (unsigned int)v79 >= *((_DWORD *)v12 + 30) )
          goto LABEL_119;
        v32 = (char *)v82 + 536;
        v82 = (struct tagRASENTRYADVANCED *)((char *)v82 + 536);
      }
      *(_DWORD *)(*(_QWORD *)(v14 + 48) + 16LL * (unsigned int)v8) = appId->size;
      *(_QWORD *)(*(_QWORD *)(v14 + 48) + 16LL * (unsigned int)v8 + 8) = VpnAlloc(appId->size);
      if ( !*(_QWORD *)(*(_QWORD *)(v14 + 48) + 16LL * (unsigned int)v8 + 8) )
      {
        v13 = 14;
        v78 = 14;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          goto LABEL_101;
        }
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 898, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
      }
      v18 = WPP_GLOBAL_Control;
LABEL_101:
      v38 = *(void **)(*(_QWORD *)(v14 + 48) + 16LL * (unsigned int)v8 + 8);
      if ( !v38 )
      {
        v13 = 14;
        if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 1) != 0 )
        {
          v19 = 899;
          goto LABEL_21;
        }
        goto LABEL_233;
      }
      memcpy_0(v38, appId->data, appId->size);
      FwpmFreeMemory0((void **)&appId);
      appId = 0;
      goto LABEL_103;
    }
LABEL_119:
    *(_DWORD *)(v14 + 40) = v8;
    LODWORD(v8) = 0;
    v18 = WPP_GLOBAL_Control;
LABEL_120:
    v41 = (_WORD *)*((_QWORD *)v12 + 17);
    if ( !v41 )
      goto LABEL_144;
    v42 = 0x7FFFFFFF;
    do
    {
      if ( !*v41 )
        break;
      ++v41;
      --v42;
    }
    while ( v42 );
    v43 = 2 * ((0x7FFFFFFF - v42) & ((unsigned __int128)-(__int128)(unsigned __int64)v42 >> 64) & -(__int64)(v42 != 0))
        + 2;
    v44 = VpnAlloc(v43);
    *(_QWORD *)(v14 + 56) = v44;
    if ( !v44 )
    {
      v13 = 14;
      v78 = 14;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_129;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 900, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
    }
    v18 = WPP_GLOBAL_Control;
LABEL_129:
    v45 = *(_WORD **)(v14 + 56);
    if ( !v45 )
    {
      v13 = 14;
      if ( v18 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v18[1].Blink) & 1) == 0 )
        goto LABEL_233;
      v19 = 901;
      goto LABEL_21;
    }
    v46 = v43 >> 1;
    if ( v46 )
    {
      if ( v46 <= 0x7FFFFFFF )
      {
        v47 = (_WORD *)*((_QWORD *)v12 + 17);
        v48 = 2147483646;
        do
        {
          if ( !v48 )
            break;
          if ( !*v47 )
            break;
          *v45++ = *v47++;
          --v48;
          --v46;
        }
        while ( v46 );
        v49 = v45 - 1;
        if ( v46 )
          v49 = v45;
        *v49 = 0;
      }
      else
      {
        *v45 = 0;
      }
      v18 = WPP_GLOBAL_Control;
    }
LABEL_144:
    if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 4) != 0 )
      WPP_SF_d(v18[1].Flink, 902, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, *((unsigned int *)v12 + 42));
    v50 = *((unsigned int *)v12 + 42);
    if ( !(_DWORD)v50 )
      goto LABEL_168;
    v51 = VpnAlloc(520 * v50);
    *(_QWORD *)(v14 + 72) = v51;
    if ( !v51 )
    {
      v13 = 14;
      v78 = 14;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_153;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 903, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
    }
    v18 = WPP_GLOBAL_Control;
LABEL_153:
    v52 = *(_QWORD *)(v14 + 72);
    if ( !v52 )
    {
      v13 = 14;
      if ( v18 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v18[1].Blink) & 1) == 0 )
        goto LABEL_233;
      v19 = 904;
      goto LABEL_21;
    }
    v53 = *((_DWORD *)v12 + 42);
    if ( v53 )
    {
      v54 = *((_QWORD *)v12 + 22);
      LODWORD(v79) = 0;
      do
      {
        v55 = (__int128 *)v54;
        v56 = (_OWORD *)(v52 + 520LL * (unsigned int)v8);
        v57 = 2;
        do
        {
          v58 = *v55;
          v55 += 8;
          *v56 = v58;
          v56 += 8;
          *(v56 - 7) = *(v55 - 7);
          *(v56 - 6) = *(v55 - 6);
          *(v56 - 5) = *(v55 - 5);
          *(v56 - 4) = *(v55 - 4);
          *(v56 - 3) = *(v55 - 3);
          *(v56 - 2) = *(v55 - 2);
          *(v56 - 1) = *(v55 - 1);
          --v57;
        }
        while ( v57 );
        v52 = *(_QWORD *)(v14 + 72);
        if ( *(_WORD *)(v52 + 520LL * (unsigned int)v8) )
        {
          LODWORD(v59) = 0;
          v60 = 520LL * (unsigned int)v8;
          do
          {
            v61 = v60 + 2LL * (unsigned int)v59;
            v59 = (unsigned int)(v59 + 1);
            *(_WORD *)(v61 + *(_QWORD *)(v14 + 72)) = tolower(*(unsigned __int16 *)(v52 + v61));
            v52 = *(_QWORD *)(v14 + 72);
          }
          while ( *(_WORD *)(v52 + 2 * v59 + v60) );
          v12 = v83;
          LODWORD(v8) = (_DWORD)v79;
        }
        v53 = *((_DWORD *)v12 + 42);
        LODWORD(v8) = v8 + 1;
        v54 = *(_QWORD *)(v54 + 512);
        LODWORD(v79) = v8;
      }
      while ( (unsigned int)v8 < v53 );
      v13 = v78;
      LODWORD(v8) = 0;
    }
    *(_DWORD *)(v14 + 64) = v53;
LABEL_168:
    v62 = *((_DWORD *)v12 + 38);
    if ( v62 )
    {
      v63 = VpnAlloc(8LL * v62);
      *(_QWORD *)(v14 + 88) = v63;
      if ( !v63 )
      {
        v13 = 14;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
LABEL_174:
          if ( !*(_QWORD *)(v14 + 88) )
          {
            v13 = 14;
            if ( v18 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v18[1].Blink) & 1) == 0 )
              goto LABEL_233;
            v19 = 906;
            goto LABEL_21;
          }
          v64 = VpnAlloc(24);
          *(_QWORD *)(v14 + 104) = v64;
          if ( !v64 )
          {
            v13 = 14;
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
            {
              goto LABEL_183;
            }
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 907, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
          }
          v18 = WPP_GLOBAL_Control;
LABEL_183:
          if ( *(_QWORD *)(v14 + 104) )
          {
            v65 = (_QWORD *)*((_QWORD *)v12 + 20);
            LODWORD(v79) = 0;
            if ( !*((_DWORD *)v12 + 38) )
              goto LABEL_200;
            do
            {
              v66 = VpnStringCopy(v65);
              if ( v66 < 0 )
              {
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control[1].Flink,
                    909,
                    &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                    (unsigned int)v66);
                }
                v67 = v66 & 0x1FFF0000;
                if ( (v66 & 0x1FFF0000) == 0x70000 )
                {
                  v68 = (unsigned __int16)v66;
                  v67 = 458752;
                }
                else
                {
                  v68 = v66;
                }
                if ( v68 )
                {
                  if ( v67 == 458752 )
                    v66 = (unsigned __int16)v66;
                  v15 = "VpnStringCopy for szDnsSuffix";
                  v16 = (unsigned int)v66;
                  goto LABEL_13;
                }
              }
              if ( *(_WORD *)v65 )
              {
                do
                {
                  v69 = (unsigned int)v8;
                  v70 = tolower(*((unsigned __int16 *)v65 + (unsigned int)v8));
                  v8 = (unsigned int)(v8 + 1);
                  *((_WORD *)v65 + v69) = v70;
                }
                while ( *((_WORD *)v65 + v8) );
                v12 = v83;
              }
              LODWORD(v8) = 0;
              v65 = (_QWORD *)v65[64];
              LODWORD(v79) = (_DWORD)v79 + 1;
            }
            while ( (unsigned int)v79 < *((_DWORD *)v12 + 38) );
LABEL_200:
            while ( 1 )
            {
              v71 = VpnStringBuild(
                      *(_QWORD *)(v14 + 104) + 8LL * (unsigned int)v8,
                      (&g_ExemptionEntry)[(unsigned int)v8],
                      v65);
              if ( v71 < 0 )
              {
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control[1].Flink,
                    910,
                    &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
                    (unsigned int)v71);
                }
                v72 = v71 & 0x1FFF0000;
                if ( (v71 & 0x1FFF0000) == 0x70000 )
                {
                  v73 = (unsigned __int16)v71;
                  v72 = 458752;
                }
                else
                {
                  v73 = v71;
                }
                if ( v73 )
                  break;
              }
              LODWORD(v8) = v8 + 1;
              if ( (unsigned int)v8 >= 3 )
              {
                *(_DWORD *)(v14 + 80) = *((_DWORD *)v12 + 38);
                *(_DWORD *)(v14 + 96) = 3;
                goto LABEL_213;
              }
            }
            if ( v72 == 458752 )
              v71 = (unsigned __int16)v71;
            v15 = "VpnStringBuild for szDnsSuffix";
            v16 = (unsigned int)v71;
            goto LABEL_13;
          }
          v13 = 14;
          if ( v18 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v18[1].Blink) & 1) == 0 )
            goto LABEL_233;
          v19 = 908;
          goto LABEL_21;
        }
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 905, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
      }
      v18 = WPP_GLOBAL_Control;
      goto LABEL_174;
    }
LABEL_213:
    if ( *((_DWORD *)v12 + 22) )
    {
      v74 = int_VpnProfileCopyNrptRules(a2, v12, (struct _VPNPROFILEACTIVESETTINGS *)v14);
      v13 = v74;
      if ( v74 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_233;
        if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 911, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v74);
          v18 = WPP_GLOBAL_Control;
        }
        if ( v18 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v18[1].Blink) & 1) == 0 )
          goto LABEL_233;
        v19 = 912;
        goto LABEL_36;
      }
      ExemptionNrptRules = int_VpnProfileCreateExemptionNrptRules((struct _VPNPROFILEACTIVESETTINGS *)v14);
      v13 = ExemptionNrptRules;
      if ( ExemptionNrptRules )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_233;
        if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Flink,
            913,
            &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
            ExemptionNrptRules);
          v18 = WPP_GLOBAL_Control;
        }
        if ( v18 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v18[1].Blink) & 1) == 0 )
          goto LABEL_233;
        v19 = 914;
LABEL_36:
        v20 = v13;
        goto LABEL_22;
      }
    }
    *(_DWORD *)(v14 + 132) = ProfileIsLockDown(a2, a1);
    *a4 = v14;
    goto LABEL_232;
  }
  v24 = VpnAlloc((unsigned int)(8 * v23));
  *(_QWORD *)(v14 + 32) = v24;
  if ( v24 )
    goto LABEL_43;
  v13 = 14;
  v78 = 14;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 885, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
LABEL_43:
    v18 = WPP_GLOBAL_Control;
  }
  if ( !*(_QWORD *)(v14 + 32) )
  {
    v13 = 14;
    if ( v18 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v18[1].Blink) & 1) == 0 )
      goto LABEL_233;
    v19 = 886;
    goto LABEL_21;
  }
  v25 = *((_DWORD *)v12 + 26);
  v26 = *((_QWORD *)v12 + 14);
  v27 = 0;
  if ( !v25 )
  {
LABEL_61:
    *(_DWORD *)(v14 + 24) = v25;
    LODWORD(v8) = 0;
    goto LABEL_62;
  }
  while ( 1 )
  {
    v28 = AppContainerDeriveSidFromMoniker(v26 + 8, *(_QWORD *)(v14 + 32) + 8LL * v27);
    v78 = v28;
    v13 = v28;
    if ( v28 < 0 )
      break;
    v13 = 0;
    v78 = 0;
LABEL_60:
    v25 = *((_DWORD *)v12 + 26);
    v26 += 536;
    if ( ++v27 >= v25 )
      goto LABEL_61;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 887, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v28);
    v18 = WPP_GLOBAL_Control;
  }
  if ( (v13 & 0x1FFF0000) == 0x70000 )
  {
    v13 = (unsigned __int16)v13;
    v78 = (unsigned __int16)v13;
  }
  if ( !v13 )
    goto LABEL_60;
  if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 1) != 0 )
  {
    v19 = 888;
    goto LABEL_36;
  }
LABEL_233:
  v40 = Src;
LABEL_234:
  VpnProfileActiveSettingsFree((LPVOID)v14);
LABEL_236:
  if ( v40 )
    MprCommonFree(v40);
  if ( v84 )
    MprCommonFree(v84);
  if ( v12 )
    RasFreeEntryAdvancedProperties(v12);
  if ( (v13 & 0x80000000) != 0
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 915, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x1800dfbdc  mov     rax, rsp
0x1800dfbdf  mov     [rax+18h], rbx
0x1800dfbe3  mov     [rax+20h], r9
0x1800dfbe7  mov     [rax+10h], rdx
0x1800dfbeb  mov     [rax+8], rcx
0x1800dfbef  push    rbp
0x1800dfbf0  push    rsi
0x1800dfbf1  push    rdi
0x1800dfbf2  push    r12
0x1800dfbf4  push    r13
0x1800dfbf6  push    r14
0x1800dfbf8  push    r15
0x1800dfbfa  mov     rbp, rsp
0x1800dfbfd  sub     rsp, 70h
0x1800dfc01  mov     r14, r9
0x1800dfc04  mov     rbx, r8
0x1800dfc07  mov     rdi, rdx
0x1800dfc0a  mov     rsi, rcx
0x1800dfc0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfc14  lea     r15, WPP_GLOBAL_Control
0x1800dfc1b  xor     r12d, r12d
0x1800dfc1e  cmp     rcx, r15
0x1800dfc21  jz      short loc_1800DFC5E
0x1800dfc23  test    byte ptr [rcx+1Ch], 8
0x1800dfc27  jz      short loc_1800DFC5E
0x1800dfc29  mov     rcx, [rcx+10h]
0x1800dfc2d  lea     rdx, aNull_4; "<NULL>"
0x1800dfc34  test    rdi, rdi
0x1800dfc37  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dfc3e  mov     rax, rdi
0x1800dfc41  mov     r9, rsi
0x1800dfc44  cmovz   rax, rdx
0x1800dfc48  test    rsi, rsi
0x1800dfc4b  mov     [rsp+70h+var_50], rax
0x1800dfc50  cmovz   r9, rdx
0x1800dfc54  mov     edx, 36Fh
0x1800dfc59  call    WPP_SF_SS
0x1800dfc5e  mov     rax, r12
0x1800dfc61  mov     [rbp+var_30], r12
0x1800dfc65  mov     [rbp+Src], rax
0x1800dfc69  lea     r9, [rbp+var_30]; struct tagRASENTRYW **
0x1800dfc6d  mov     [rbp+lpMem], rax
0x1800dfc71  mov     rdx, rdi; LPCWSTR
0x1800dfc74  lea     rax, [rbp+var_18]
0x1800dfc78  mov     [rbp+var_18], r12
0x1800dfc7c  mov     rcx, rsi; LPCWSTR
0x1800dfc7f  mov     [rsp+70h+var_50], rax; struct tagRASENTRYADVANCED **
0x1800dfc84  mov     [rbp+appId], r12
0x1800dfc88  mov     [r14], r12
0x1800dfc8b  call    ?VpnProfileGetEntryByName@@YAKPEBG0KPEAPEAUtagRASENTRYW@@PEAPEAUtagRASENTRYADVANCED@@@Z; VpnProfileGetEntryByName(ushort const *,ushort const *,ulong,tagRASENTRYW * *,tagRASENTRYADVANCED * *)
0x1800dfc90  mov     r13, [rbp+var_18]
0x1800dfc94  mov     edi, eax
0x1800dfc96  mov     [rbp+var_38], eax
0x1800dfc99  mov     rax, [rbp+var_30]
0x1800dfc9d  mov     [rbp+var_8], rax
0x1800dfca1  mov     [rbp+var_10], r13
0x1800dfca5  test    edi, edi
0x1800dfca7  jz      short loc_1800DFCF6
0x1800dfca9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfcb0  cmp     rcx, r15
0x1800dfcb3  jz      short loc_1800DFCD8
0x1800dfcb5  mov     esi, 1
0x1800dfcba  test    [rcx+1Ch], sil
0x1800dfcbe  jz      short loc_1800DFCD8
0x1800dfcc0  mov     rcx, [rcx+10h]
0x1800dfcc4  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dfccb  mov     edx, 370h
0x1800dfcd0  mov     r9d, edi
0x1800dfcd3  call    WPP_SF_d
0x1800dfcd8  mov     r15, r12
0x1800dfcdb  lea     rdx, aVpnprofilegete; "VpnProfileGetEntryByName"
0x1800dfce2  mov     r8d, edi
0x1800dfce5  lea     rcx, aVpnprofileacti_2; "VpnProfileActiveSettingsGet"
0x1800dfcec  call    VpnReportError
0x1800dfcf1  jmp     loc_1800E09EF
0x1800dfcf6  mov     ecx, 88h
0x1800dfcfb  call    VpnAlloc
0x1800dfd00  mov     r15, rax
0x1800dfd03  test    rax, rax
0x1800dfd06  jnz     short loc_1800DFD7A
0x1800dfd08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfd0f  lea     rbx, WPP_GLOBAL_Control
0x1800dfd16  lea     esi, [rax+1]
0x1800dfd19  lea     r14d, [rax+0Eh]
0x1800dfd1d  cmp     rcx, rbx
0x1800dfd20  jz      short loc_1800DFD47
0x1800dfd22  test    [rcx+1Ch], sil
0x1800dfd26  jz      short loc_1800DFD47
0x1800dfd28  mov     rcx, [rcx+10h]
0x1800dfd2c  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dfd33  mov     edx, 371h
0x1800dfd38  mov     r9d, r14d
0x1800dfd3b  call    WPP_SF_d
0x1800dfd40  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfd47  mov     edi, r14d
0x1800dfd4a  cmp     rcx, rbx
0x1800dfd4d  jz      loc_1800E09F3
0x1800dfd53  test    [rcx+1Ch], sil
0x1800dfd57  jz      loc_1800E09F3
0x1800dfd5d  mov     edx, 372h
0x1800dfd62  mov     r9d, r14d
0x1800dfd65  mov     rcx, [rcx+10h]
0x1800dfd69  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dfd70  call    WPP_SF_d
0x1800dfd75  jmp     loc_1800E09F3
0x1800dfd7a  test    byte ptr [r13+4], 40h
0x1800dfd7f  mov     esi, 1
0x1800dfd84  jz      short loc_1800DFD8C
0x1800dfd86  mov     [rax+80h], esi
0x1800dfd8c  mov     rcx, [r13+90h]
0x1800dfd93  test    rcx, rcx
0x1800dfd96  jz      loc_1800DFE2F
0x1800dfd9c  add     rcx, 4
0x1800dfda0  mov     rdx, rbx
0x1800dfda3  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x1800dfdaa  nop     dword ptr [rax+rax+00h]
0x1800dfdaf  mov     [rbp+var_38], eax
0x1800dfdb2  mov     edi, eax
0x1800dfdb4  test    eax, eax
0x1800dfdb6  jns     short loc_1800DFE28
0x1800dfdb8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfdbf  lea     r14, WPP_GLOBAL_Control
0x1800dfdc6  cmp     rcx, r14
0x1800dfdc9  jz      short loc_1800DFDF0
0x1800dfdcb  test    [rcx+1Ch], sil
0x1800dfdcf  jz      short loc_1800DFDF0
0x1800dfdd1  mov     rcx, [rcx+10h]
0x1800dfdd5  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dfddc  mov     edx, 373h
0x1800dfde1  mov     r9d, eax
0x1800dfde4  call    WPP_SF_d
0x1800dfde9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfdf0  mov     eax, edi
0x1800dfdf2  and     eax, 1FFF0000h
0x1800dfdf7  cmp     eax, 70000h
0x1800dfdfc  jnz     short loc_1800DFE04
0x1800dfdfe  movzx   edi, di
0x1800dfe01  mov     [rbp+var_38], edi
0x1800dfe04  test    edi, edi
0x1800dfe06  jz      short loc_1800DFE2F
0x1800dfe08  cmp     rcx, r14
0x1800dfe0b  jz      loc_1800E09F3
0x1800dfe11  test    [rcx+1Ch], sil
0x1800dfe15  jz      loc_1800E09F3
0x1800dfe1b  mov     edx, 374h
0x1800dfe20  mov     r9d, edi
0x1800dfe23  jmp     loc_1800DFD65
0x1800dfe28  mov     edi, r12d
0x1800dfe2b  mov     [rbp+var_38], r12d
0x1800dfe2f  mov     eax, [r13+68h]
0x1800dfe33  mov     r14d, 0Eh
0x1800dfe39  test    eax, eax
0x1800dfe3b  jz      loc_1800DFF8F
0x1800dfe41  shl     eax, 3
0x1800dfe44  mov     ecx, eax
0x1800dfe46  call    VpnAlloc
0x1800dfe4b  mov     [r15+20h], rax
0x1800dfe4f  test    rax, rax
0x1800dfe52  jnz     short loc_1800DFE8C
0x1800dfe54  mov     edi, r14d
0x1800dfe57  mov     [rbp+var_38], r14d
0x1800dfe5b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfe62  lea     rax, WPP_GLOBAL_Control
0x1800dfe69  cmp     rcx, rax
0x1800dfe6c  jz      short loc_1800DFE9A
0x1800dfe6e  test    [rcx+1Ch], sil
0x1800dfe72  jz      short loc_1800DFE9A
0x1800dfe74  mov     rcx, [rcx+10h]
0x1800dfe78  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dfe7f  mov     edx, 375h
0x1800dfe84  mov     r9d, r14d
0x1800dfe87  call    WPP_SF_d
0x1800dfe8c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dfe93  lea     rax, WPP_GLOBAL_Control
0x1800dfe9a  cmp     [r15+20h], r12
0x1800dfe9e  jnz     short loc_1800DFEC0
0x1800dfea0  mov     edi, r14d
0x1800dfea3  cmp     rcx, rax
0x1800dfea6  jz      loc_1800E09F3
0x1800dfeac  test    [rcx+1Ch], sil
0x1800dfeb0  jz      loc_1800E09F3
0x1800dfeb6  mov     edx, 376h
0x1800dfebb  jmp     loc_1800DFD62
0x1800dfec0  mov     eax, [r13+68h]
0x1800dfec4  xor     ecx, ecx
0x1800dfec6  mov     r12, [r13+70h]
0x1800dfeca  mov     ebx, ecx
0x1800dfecc  test    eax, eax
0x1800dfece  jz      loc_1800DFF88
0x1800dfed4  mov     rax, [r15+20h]
0x1800dfed8  mov     ecx, ebx
0x1800dfeda  lea     rdx, [rax+rcx*8]
0x1800dfede  lea     rcx, [r12+8]
0x1800dfee3  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x1800dfeea  nop     dword ptr [rax+rax+00h]
0x1800dfeef  xor     edx, edx
0x1800dfef1  mov     [rbp+var_38], eax
0x1800dfef4  mov     edi, eax
0x1800dfef6  test    eax, eax
0x1800dfef8  jns     short loc_1800DFF6E
0x1800dfefa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dff01  lea     r8, WPP_GLOBAL_Control
0x1800dff08  cmp     rcx, r8
0x1800dff0b  jz      short loc_1800DFF39
0x1800dff0d  test    [rcx+1Ch], sil
0x1800dff11  jz      short loc_1800DFF39
0x1800dff13  mov     rcx, [rcx+10h]
0x1800dff17  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dff1e  mov     edx, 377h
0x1800dff23  mov     r9d, eax
0x1800dff26  call    WPP_SF_d
0x1800dff2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dff32  lea     r8, WPP_GLOBAL_Control
0x1800dff39  mov     eax, edi
0x1800dff3b  and     eax, 1FFF0000h
0x1800dff40  cmp     eax, 70000h
0x1800dff45  jnz     short loc_1800DFF4D
0x1800dff47  movzx   edi, di
0x1800dff4a  mov     [rbp+var_38], edi
0x1800dff4d  test    edi, edi
0x1800dff4f  jz      short loc_1800DFF73
0x1800dff51  cmp     rcx, r8
0x1800dff54  jz      loc_1800E09F3
0x1800dff5a  test    [rcx+1Ch], sil
0x1800dff5e  jz      loc_1800E09F3
0x1800dff64  mov     edx, 378h
0x1800dff69  jmp     loc_1800DFE20
0x1800dff6e  mov     edi, edx
0x1800dff70  mov     [rbp+var_38], edx
0x1800dff73  mov     eax, [r13+68h]
0x1800dff77  add     r12, 218h
0x1800dff7e  add     ebx, esi
0x1800dff80  cmp     ebx, eax
0x1800dff82  jb      loc_1800DFED4
0x1800dff88  mov     [r15+18h], eax
0x1800dff8c  xor     r12d, r12d
0x1800dff8f  mov     rax, [rbp+var_8]
0x1800dff93  mov     ecx, 12Ch
0x1800dff98  mov     eax, [rax+0DA4h]
0x1800dff9e  test    eax, eax
0x1800dffa0  cmovz   eax, ecx
0x1800dffa3  mov     [r15+7Ch], eax
0x1800dffa7  lea     rbx, WPP_GLOBAL_Control
0x1800dffae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dffb5  cmp     rcx, rbx
0x1800dffb8  jz      short loc_1800DFFE0
0x1800dffba  test    byte ptr [rcx+1Ch], 4
0x1800dffbe  jz      short loc_1800DFFE0
0x1800dffc0  mov     r9d, [r13+78h]
0x1800dffc4  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dffcb  mov     rcx, [rcx+10h]
0x1800dffcf  mov     edx, 379h
0x1800dffd4  call    WPP_SF_d
0x1800dffd9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dffe0  mov     eax, [r13+78h]
0x1800dffe4  test    eax, eax
0x1800dffe6  jz      loc_1800E0391
0x1800dffec  shl     eax, 4
0x1800dffef  mov     ecx, eax
0x1800dfff1  call    VpnAlloc
0x1800dfff6  mov     [r15+30h], rax
0x1800dfffa  test    rax, rax
0x1800dfffd  jnz     short loc_1800E0030
0x1800dffff  mov     edi, r14d
0x1800e0002  mov     [rbp+var_38], r14d
0x1800e0006  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e000d  cmp     rcx, rbx
0x1800e0010  jz      short loc_1800E0037
0x1800e0012  test    [rcx+1Ch], sil
0x1800e0016  jz      short loc_1800E0037
0x1800e0018  mov     rcx, [rcx+10h]
0x1800e001c  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e0023  mov     edx, 37Ah
0x1800e0028  mov     r9d, r14d
0x1800e002b  call    WPP_SF_d
0x1800e0030  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e0037  cmp     [r15+30h], r12
0x1800e003b  jnz     short loc_1800E005D
0x1800e003d  mov     edi, r14d
0x1800e0040  cmp     rcx, rbx
0x1800e0043  jz      loc_1800E09F3
0x1800e0049  test    [rcx+1Ch], sil
0x1800e004d  jz      loc_1800E09F3
0x1800e0053  mov     edx, 37Bh
0x1800e0058  jmp     loc_1800DFD62
0x1800e005d  mov     rax, [r13+80h]
0x1800e0064  xor     ecx, ecx
0x1800e0066  mov     [rbp+var_18], rax
0x1800e006a  mov     dword ptr [rbp+var_30], ecx
0x1800e006d  cmp     [r13+78h], ecx
0x1800e0071  jbe     loc_1800E0383
0x1800e0077  lea     rbx, [rax+8]
0x1800e007b  mov     rcx, rbx; fileName
0x1800e007e  lea     rdx, [rbp+appId]; appId
0x1800e0082  call    cs:__imp_FwpmGetAppIdFromFileName0
0x1800e0089  nop     dword ptr [rax+rax+00h]
0x1800e008e  mov     [rbp+var_38], eax
0x1800e0091  mov     edi, eax
0x1800e0093  test    eax, eax
0x1800e0095  jz      loc_1800E01FF
  ... truncated ...
```
