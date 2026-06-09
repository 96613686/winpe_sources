# ActivateRouteRequest

- ea: `0x180010be0`
- end: `0x180011dc9`
- name: `ActivateRouteRequest`
- size: `4585`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005cf8`
- `0x18000c424`
- `0x180010be0`
- `0x180028c70`
- `0x18003028c`
- `0x180033b98`
- `0x1800342bc`
- `0x18004167c`
- `0x1800477bc`
- `0x1800492b4`
- `0x18006821c`
- `0x1800693d8`
- `0x180098468`
- `0x180098654`
- `0x1800e8e72`
- `0x1800e8e7e`
- `0x1800e8e96`
- `0x1800e8ef0`
- `0x1800e8fb0`

## import_xrefs

- `msvcrt!mbstowcs_s` at `0x180011b9f`
- `msvcrt!mbstowcs_s` at `0x180011b9f`
- `msvcrt!wcstombs_s` at `0x1800119dd`
- `msvcrt!wcstombs_s` at `0x1800119dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001170e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001170e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011c65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011c65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011bff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011bff`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800116fa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800116fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011347`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011347`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800114ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800114ba`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180011121`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180011121`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x180011412`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x180011596`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x1800115fc`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x180011412`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x180011596`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x1800115fc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001135d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001135d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800113b0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800113b0`
- `NduProv!__imp_NduOpenHandle` at `0x180011a8d`
- `NduProv!__imp_NduOpenHandle` at `0x180011a8d`
- `NduProv!__imp_NduRegisterVpnInnerInterface` at `0x180011aed`
- `NduProv!__imp_NduRegisterVpnInnerInterface` at `0x180011aed`

## pseudocode

```c
int __fastcall ActivateRouteRequest(__int64 a1, __int64 a2, wchar_t *a3)
{
  wchar_t *v3; // r14
  __int64 v4; // rdi
  struct _LIST_ENTRY *v5; // rbx
  struct _LIST_ENTRY **p_Flink; // rax
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // rdx
  DWORD LastError; // esi
  struct _LIST_ENTRY *v10; // r12
  int v11; // ecx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  struct _LIST_ENTRY *Flink; // rax
  bool v15; // zf
  unsigned int v16; // r13d
  __int64 v17; // rcx
  __int128 v18; // xmm0
  __int64 v19; // rcx
  int v20; // esi
  int v21; // eax
  struct _LIST_ENTRY *v22; // rcx
  __int64 v23; // r8
  struct _LIST_ENTRY *v24; // rax
  size_t v25; // rcx
  unsigned int v26; // edx
  int v27; // r8d
  __int64 v28; // rsi
  __int64 v29; // rbx
  HRESULT v30; // eax
  __int64 i; // rsi
  __int64 v32; // rax
  struct _LIST_ENTRY *v33; // rcx
  __int64 v34; // rdx
  struct _LIST_ENTRY **v35; // rdx
  int v36; // r8d
  struct _LIST_ENTRY *v37; // rcx
  int v38; // r15d
  int INetCfgLock; // eax
  struct _LIST_ENTRY *v40; // rcx
  struct _LIST_ENTRY *v41; // rcx
  unsigned __int16 v42; // ax
  __int64 v43; // rcx
  _QWORD *v44; // r15
  unsigned int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  struct _LIST_ENTRY *v48; // rcx
  struct _LIST_ENTRY *v49; // r9
  __int64 v50; // rdi
  unsigned int v51; // edi
  struct _LIST_ENTRY *v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // r9
  unsigned int v56; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v57; // [rsp+44h] [rbp-BCh] BYREF
  size_t PtNumOfCharConverted; // [rsp+48h] [rbp-B8h] BYREF
  int v59; // [rsp+50h] [rbp-B0h]
  int v60; // [rsp+54h] [rbp-ACh]
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  struct _LIST_ENTRY *v62; // [rsp+60h] [rbp-A0h]
  __int64 v63; // [rsp+68h] [rbp-98h]
  wchar_t *v64; // [rsp+70h] [rbp-90h]
  GUID pguid; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v66[16]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD lpsz[500]; // [rsp+A0h] [rbp-60h]
  __int64 OutBuffer; // [rsp+870h] [rbp+770h] BYREF
  wchar_t v69; // [rsp+878h] [rbp+778h]
  __int16 v70; // [rsp+87Ah] [rbp+77Ah]
  WCHAR WideCharStr[256]; // [rsp+87Ch] [rbp+77Ch] BYREF
  __int16 v72; // [rsp+A7Ch] [rbp+97Ch]
  wchar_t Src[4]; // [rsp+A7Eh] [rbp+97Eh] BYREF
  __int64 v74; // [rsp+A86h] [rbp+986h]
  unsigned int v75; // [rsp+C80h] [rbp+B80h]
  unsigned int v76; // [rsp+C84h] [rbp+B84h]
  unsigned int v77[6]; // [rsp+C88h] [rbp+B88h] BYREF
  unsigned __int64 v78; // [rsp+CA0h] [rbp+BA0h]
  __int128 v79; // [rsp+CA8h] [rbp+BA8h]
  int v80; // [rsp+CB8h] [rbp+BB8h]
  wchar_t pszDest[258]; // [rsp+CBCh] [rbp+BBCh] BYREF
  __int128 v82; // [rsp+EC0h] [rbp+DC0h]
  _BYTE Buf1[24]; // [rsp+1128h] [rbp+1028h] BYREF

  v3 = a3;
  v64 = a3;
  v4 = a1;
  v63 = a1;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 444, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  BytesReturned = 0;
  LODWORD(p_Flink) = (unsigned int)memset_0(&OutBuffer, 0, 0x8D0u);
  if ( !v4 )
  {
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 2u )
    {
      LODWORD(p_Flink) = WPP_SF_(v5[1].Flink, 446, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    }
    goto LABEL_237;
  }
  if ( *(_DWORD *)(v4 + 24) == 2 )
  {
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 2u )
    {
      LODWORD(p_Flink) = WPP_SF_q(v5[1].Flink, 445, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *(_QWORD *)v4);
    }
LABEL_237:
    *(_DWORD *)v3 = 615;
    v52 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return (int)p_Flink;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      LODWORD(p_Flink) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 447, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      v52 = WPP_GLOBAL_Control;
    }
    if ( v52 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v52[1].Blink) & 0x2000) == 0
      || BYTE1(v52[1].Blink) < 6u )
    {
      return (int)p_Flink;
    }
    v53 = 448;
    v54 = 615;
LABEL_245:
    LODWORD(p_Flink) = WPP_SF_d(v52[1].Flink, v53, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v54);
    return (int)p_Flink;
  }
  if ( *(_DWORD *)(v4 + 28) != 2 )
  {
    *(_DWORD *)v3 = 606;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        LODWORD(p_Flink) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 449, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v7[1].Blink) & 0x2000) != 0
        && BYTE1(v7[1].Blink) >= 6u )
      {
        v8 = 450;
LABEL_16:
        LODWORD(p_Flink) = WPP_SF_(v7[1].Flink, v8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        return (int)p_Flink;
      }
    }
    return (int)p_Flink;
  }
  p_Flink = *(struct _LIST_ENTRY ***)(v4 + 1048);
  LastError = 612;
  if ( p_Flink )
    v10 = p_Flink[4];
  else
    v10 = *(struct _LIST_ENTRY **)(v4 + 240);
  v62 = v10;
  if ( !v10 )
    goto LABEL_225;
  v11 = *(_DWORD *)v3;
  while ( 1 )
  {
    p_Flink = &v10[1].Flink->Flink;
    if ( *(_DWORD *)p_Flink == v11 )
      break;
    v10 = v10->Flink;
    v62 = v10;
    if ( !v10 )
      goto LABEL_225;
  }
  OutBuffer = *(_QWORD *)(v4 + 256);
  v12 = 0;
  v69 = *v3;
  v13 = *((_DWORD *)v3 + 136);
  if ( v13 > 0x4B8 )
    v13 = 1208;
  v76 = v13;
  memcpy_0(v77, v3 + 274, v13);
  LODWORD(v10[1].Flink[18].Flink) = *(_QWORD *)(v4 + 1064) != 0;
  Flink = v10[1].Flink;
  if ( LODWORD(Flink->Flink) != 2048 )
  {
    v15 = LODWORD(Flink->Flink) == 34525;
    v16 = 0;
    v57 = 0;
    if ( !v15 )
    {
LABEL_74:
      v23 = *(_QWORD *)(v4 + 1064);
      if ( !v23 )
        goto LABEL_111;
      v70 = 2 * MultiByteToWideChar(0xFDE9u, 0, (LPCCH)(v23 + 445), -1, WideCharStr, 256);
      v24 = v10[1].Flink;
      if ( LODWORD(v24->Flink) == 2048 || LODWORD(v24->Flink) == 34525 )
      {
        memset_0(pszDest, 0, 0x101u);
        StringCchCopyExW(pszDest, 0x101u, WideCharStr, 0, 0, 0xC00u);
      }
      v25 = 0;
      v26 = 0;
      PtNumOfCharConverted = 0;
      v56 = 0;
      if ( *((_DWORD *)v3 + 138) != 1 )
      {
        LODWORD(p_Flink) = RasPerAppTrafficRuleBlobToList(
                             (unsigned int)*(_QWORD *)(*(_QWORD *)(v4 + 1064) + 912LL)
                           + *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 1064) + 912LL) + 100LL),
                             *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 1064) + 912LL) + 56LL),
                             *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 1064) + 912LL) + 52LL),
                             (unsigned int)&PtNumOfCharConverted,
                             (__int64)&v56);
        v12 = (unsigned int)p_Flink;
        if ( (_DWORD)p_Flink )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            LODWORD(p_Flink) = WPP_SF_d(
                                 WPP_GLOBAL_Control[1].Flink,
                                 457,
                                 WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                 (unsigned int)p_Flink);
          }
          *(_DWORD *)v3 = v12;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
          {
            v8 = 458;
            goto LABEL_16;
          }
          return (int)p_Flink;
        }
        v25 = PtNumOfCharConverted;
        v26 = v56;
      }
      *(_DWORD *)(v4 + 1376) = 0;
      v27 = *((_DWORD *)v3 + 138);
      if ( v27 == 2 && (!v26 || !v25) )
      {
        if ( (unsigned int)LockDownPolicyExists() )
        {
          v59 = 1;
          pguid = 0;
          PtNumOfCharConverted = 0x100000000LL;
          v60 = -1;
          v28 = 0;
          v29 = 0;
          do
          {
            memset_0(&v66[v29 * 4], 0, 0x1F8u);
            LOWORD(lpsz[v29 + 69]) |= 1u;
            *(_WORD *)&v66[v29 * 4 + 8] = 545;
            *(_QWORD *)&lpsz[v29 + 2] = L"LockDownIsolationVPN";
            *(_QWORD *)&lpsz[v29 + 30] = &PtNumOfCharConverted;
            LOWORD(lpsz[v29 + 8]) = 256;
            *(_QWORD *)&lpsz[v29 + 4] = L"An interface container to allow traffic to flow over the VPN when a lockdown pro"
                                         "file is connected";
            lpsz[v29 + 28] = 2;
            lpsz[v29 + 58] = 0;
            *(_QWORD *)&lpsz[v29 + 60] = 0;
            lpsz[v29 + 6] = 0x7FFFFFFF;
            lpsz[v29 + 68] = 3;
            lpsz[v29 + 80] = 0x10000;
            *(_QWORD *)&lpsz[v29] = LocalAlloc(0x40u, 0x4Eu);
            v30 = CoCreateGuid(&pguid);
            if ( v30 < 0
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                463,
                WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                (unsigned int)v30);
            }
            StringFromGUID2(&pguid, *(LPOLESTR *)&lpsz[v29], 39);
            ++v28;
            v29 += 126;
          }
          while ( v28 != 2 );
          lpsz[7] = 1;
          v4 = v63;
          lpsz[133] = 2;
          LODWORD(p_Flink) = NetworkIsolationCreateInterfaceContainer(
                               *(_QWORD *)(v63 + 1064) + 144LL,
                               L"LockDownIsolationVPN",
                               L"An interface container to allow traffic to flow over the VPN when a lockdown profile is connected",
                               0,
                               3,
                               2,
                               v66);
          v3 = v64;
          v12 = (unsigned int)p_Flink;
          v10 = v62;
          v16 = v57;
          if ( (_DWORD)p_Flink )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              LODWORD(p_Flink) = WPP_SF_d(
                                   WPP_GLOBAL_Control[1].Flink,
                                   465,
                                   WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                   (unsigned int)p_Flink);
            }
            *(_DWORD *)v3 = v12;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v8 = 466;
              goto LABEL_16;
            }
            return (int)p_Flink;
          }
          *(_DWORD *)(v4 + 1376) = 1;
          for ( i = 0; i != 2; ++i )
            LocalFree(*(HLOCAL *)&lpsz[126 * i]);
        }
LABEL_111:
        if ( *(_DWORD *)(v4 + 1376) )
        {
          LODWORD(p_Flink) = RefCountNetworkIsolationContainers(1);
          v12 = (unsigned int)p_Flink;
          if ( (_DWORD)p_Flink )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              LODWORD(p_Flink) = WPP_SF_d(
                                   WPP_GLOBAL_Control[1].Flink,
                                   467,
                                   WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                   (unsigned int)p_Flink);
            }
            *(_DWORD *)v3 = v12;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v8 = 468;
              goto LABEL_16;
            }
            return (int)p_Flink;
          }
        }
        if ( DeviceIoControl(RasHubHandle, 0x12000Cu, &OutBuffer, 0x8D0u, &OutBuffer, 0x8D0u, &BytesReturned, 0) )
        {
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
          v37 = WPP_GLOBAL_Control;
          p_Flink = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 469, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, LastError);
            v37 = WPP_GLOBAL_Control;
            p_Flink = &WPP_GLOBAL_Control;
          }
          if ( LastError )
          {
            if ( v37 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v37[1].Blink) & 0x2000) != 0
              && BYTE1(v37[1].Blink) >= 2u )
            {
              LODWORD(p_Flink) = WPP_SF_sd(
                                   v37[1].Flink,
                                   475,
                                   (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                   (int)v4 + 8,
                                   LastError);
            }
LABEL_225:
            *(_DWORD *)v3 = LastError;
            v52 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
            {
              return (int)p_Flink;
            }
            v53 = 484;
            v54 = LastError;
            goto LABEL_245;
          }
        }
        if ( v16 == 2 && !*(_QWORD *)(v4 + 1064) )
        {
          PtNumOfCharConverted = 0;
          *(_QWORD *)&pguid.Data1 = 0;
          v57 = 0;
          v38 = 1;
          INetCfgLock = GetINetCfgLock(&PtNumOfCharConverted, &pguid, 0, &v57);
          if ( INetCfgLock >= 0 )
          {
            v40 = WPP_GLOBAL_Control;
          }
          else
          {
            v40 = WPP_GLOBAL_Control;
            v35 = &WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                471,
                WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                (unsigned __int16)INetCfgLock);
              v40 = WPP_GLOBAL_Control;
            }
            v38 = 0;
          }
          if ( v40 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v40[1].Blink) & 0x2000) != 0
            && BYTE1(v40[1].Blink) >= 4u )
          {
            WPP_SF_d(v40[1].Flink, 472, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *(unsigned int *)(v4 + 32));
            v40 = WPP_GLOBAL_Control;
          }
          if ( v38 )
          {
            if ( PtNumOfCharConverted )
            {
              LODWORD(v35) = pguid.Data1;
              if ( *(_QWORD *)&pguid.Data1 )
              {
                ReleaseINetCfgLock(PtNumOfCharConverted, *(_QWORD *)&pguid.Data1, v57);
                v40 = WPP_GLOBAL_Control;
              }
            }
          }
          if ( v12
            && v40 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v40[1].Blink) & 0x2000) != 0
            && BYTE1(v40[1].Blink) >= 2u )
          {
            WPP_SF_sd(v40[1].Flink, 473, (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v4 + 8, v12);
          }
          *(_OWORD *)(v4 + 1344) = v82;
        }
        LODWORD(v10[1].Flink[18].Flink) = 1;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_sqqdD(WPP_GLOBAL_Control[1].Flink, (_DWORD)v35, v36, v4 + 8, v4, OutBuffer, v69, 0);
        }
        v41 = v10[1].Flink;
        PtNumOfCharConverted = 0;
        if ( LODWORD(v41->Flink) == 2048 || LODWORD(v41->Flink) == 34525 )
        {
          memset_0((char *)&v41->Flink + 4, 0, 0x80u);
          v42 = 510;
          if ( (unsigned __int16)v72 <= 0x1FEu )
            v42 = v72;
          else
            v72 = 510;
          *(wchar_t *)((char *)Src + v42) = 0;
          wcstombs_s(&PtNumOfCharConverted, (char *)&v10[1].Flink->Flink + 4, 0x80u, Src, 0x100u);
          v43 = *(_QWORD *)(v4 + 1064);
          if ( v43 )
          {
            *(_DWORD *)(v43 + 852) = v75;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 476, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v75);
            }
          }
          if ( v16 == 2 )
          {
            *((_DWORD *)v3 + 131) = (v78 >> 24) & 0xFFFFFF;
            goto LABEL_211;
          }
          if ( v16 > 1 || *(_WORD *)(*(_QWORD *)(v4 + 1232) + 96LL) != 14 )
            goto LABEL_211;
          v44 = (_QWORD *)(v4 + 1368);
          if ( *(_QWORD *)(v4 + 1368) == -1 )
          {
            v12 = NduOpenHandle(v4 + 1368);
            if ( v12
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 477, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v12);
            }
            if ( *v44 == -1 )
              goto LABEL_211;
          }
          v45 = NduRegisterVpnInnerInterface(*v44, v78);
          v12 = v45;
          if ( !v45 )
            goto LABEL_206;
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
LABEL_207:
              if ( v48 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v48[1].Blink) & 0x2000) != 0
                && BYTE1(v48[1].Blink) >= 4u )
              {
                WPP_SF_iD(v48[1].Flink, v46, v47, v78, v12);
              }
              goto LABEL_211;
            }
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 478, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v45);
LABEL_206:
            v48 = WPP_GLOBAL_Control;
            goto LABEL_207;
          }
        }
LABEL_211:
        v49 = v10[1].Flink;
        LODWORD(v10->Blink) = 1;
        LODWORD(p_Flink) = mbstowcs_s(&PtNumOfCharConverted, v3 + 133, 0x80u, (const char *)&v49->Flink + 4, 0x80u);
        v50 = *(_QWORD *)(v4 + 1064);
        if ( v50 )
        {
          v51 = (*(_DWORD *)(v50 + 168) >> 1) & 1;
          if ( v10[1].Flink->Flink == (struct _LIST_ENTRY *)2048 && (v16 != 2 || !memcmp_0(Buf1, &GUID_NULL, 0x10u)) )
          {
            LeaveCriticalSection(&g_csSubmitRequest);
            v12 = DwBindServerToAdapter(v3 + 141, v51, v10[1].Flink->Flink);
            if ( v12
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 480, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v12);
            }
            EnterCriticalSection(&g_csSubmitRequest);
          }
          p_Flink = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
          {
            LODWORD(p_Flink) = WPP_SF_d(
                                 WPP_GLOBAL_Control[1].Flink,
                                 481,
                                 WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                 v12);
          }
        }
        goto LABEL_225;
      }
      v32 = *(_QWORD *)(v4 + 1064);
      if ( v27 == 1 )
      {
        LODWORD(p_Flink) = NetworkIsolationCreateInterfaceContainer(v32 + 144, WideCharStr, WideCharStr, 0, 7, 0, 0);
        v12 = (unsigned int)p_Flink;
        if ( (_DWORD)p_Flink )
        {
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_137;
          if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
LABEL_133:
            if ( v33 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v33[1].Blink) & 0x2000) != 0
              && BYTE1(v33[1].Blink) >= 2u )
            {
              LODWORD(p_Flink) = WPP_SF_d(v33[1].Flink, 461, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v12);
            }
LABEL_137:
            *(_DWORD *)v3 = v12;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v8 = 462;
              goto LABEL_16;
            }
            return (int)p_Flink;
          }
          v34 = 459;
LABEL_132:
          LODWORD(p_Flink) = WPP_SF_d(
                               v33[1].Flink,
                               v34,
                               WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                               (unsigned int)p_Flink);
          v33 = WPP_GLOBAL_Control;
          goto LABEL_133;
        }
      }
      else
      {
        LODWORD(p_Flink) = NetworkIsolationCreateInterfaceContainer(v32 + 144, WideCharStr, WideCharStr, 0, 7, v26, v25);
        v12 = (unsigned int)p_Flink;
        if ( (_DWORD)p_Flink )
        {
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_137;
          if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            goto LABEL_133;
          v34 = 460;
          goto LABEL_132;
        }
      }
      *(_DWORD *)(v4 + 1376) = 1;
      goto LABEL_111;
    }
  }
  v16 = v77[0];
  v57 = v77[0];
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control[1].Flink,
      451,
      (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
      v4 + 8,
      v77[0]);
  }
  if ( v16 <= 1 )
  {
    v17 = *((unsigned int *)v3 + 1);
    HIWORD(v78) = 23;
    v78 = (v17 << 24) ^ ((v17 << 24) ^ v78) & 0xFFFF000000000000uLL;
  }
  if ( v10[1].Flink->Flink == (struct _LIST_ENTRY *)34525 && v16 == 2 )
  {
    if ( *(_QWORD *)(v4 + 1064) )
      *((_DWORD *)v3 + 266) = 1;
    goto LABEL_50;
  }
  if ( v16 != 1 )
  {
LABEL_50:
    v19 = *(_QWORD *)(v4 + 1064);
    if ( v19 )
    {
      v72 = 16;
      *(_QWORD *)Src = *(_QWORD *)(v19 + 144);
      v74 = *(_QWORD *)(v19 + 152);
      *(_QWORD *)&pguid.Data1 = 0;
      PtNumOfCharConverted = 0;
      v56 = 0;
      if ( !g_RasMobileCore && (v16 != 2 || !memcmp_0(Buf1, &GUID_NULL, 0x10u)) )
      {
        v20 = 1;
        v21 = GetINetCfgLock(&pguid, &PtNumOfCharConverted, 0, &v56);
        if ( v21 >= 0 )
        {
          v22 = WPP_GLOBAL_Control;
        }
        else
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control[1].Flink,
              454,
              WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
              (unsigned __int16)v21);
            v22 = WPP_GLOBAL_Control;
          }
          v20 = 0;
        }
        if ( v22 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v22[1].Blink) & 0x2000) != 0
          && BYTE1(v22[1].Blink) >= 4u )
        {
          WPP_SF_(v22[1].Flink, 455, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        }
        v12 = DwAddLegacyKeysForInterface(Src);
        if ( v12
          && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 456, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v12);
        }
        if ( v20 && *(_QWORD *)&pguid.Data1 && PtNumOfCharConverted )
          ReleaseINetCfgLock(*(_QWORD *)&pguid.Data1, PtNumOfCharConverted, v56);
      }
    }
    goto LABEL_74;
  }
  *(_DWORD *)(*(_QWORD *)(v4 + 1064) + 172LL) = *((_DWORD *)v3 + 1);
  LODWORD(p_Flink) = SetCompartmentNetworkMapping(*(_QWORD *)(v4 + 1064) + 144LL, 1);
  v12 = (unsigned int)p_Flink;
  if ( !(_DWORD)p_Flink )
  {
    v18 = *(_OWORD *)(*(_QWORD *)(v4 + 1064) + 144LL);
    v80 = 1;
    v79 = v18;
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    LODWORD(p_Flink) = WPP_SF_d(
                         WPP_GLOBAL_Control[1].Flink,
                         452,
                         WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                         (unsigned int)p_Flink);
  }
  *(_DWORD *)v3 = v12;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v8 = 453;
    goto LABEL_16;
  }
  return (int)p_Flink;
}

```

## disassembly

```asm
0x180010be0  mov     [rsp-8+arg_8], rbx
0x180010be5  push    rbp
0x180010be6  push    rsi
0x180010be7  push    rdi
0x180010be8  push    r12
0x180010bea  push    r13
0x180010bec  push    r14
0x180010bee  push    r15
0x180010bf0  lea     rbp, [rsp-1050h]
0x180010bf8  mov     eax, 1150h
0x180010bfd  call    _alloca_probe
0x180010c02  sub     rsp, rax
0x180010c05  mov     rax, cs:__security_cookie
0x180010c0c  xor     rax, rsp
0x180010c0f  mov     [rbp+1080h+var_40], rax
0x180010c16  mov     r14, r8
0x180010c19  mov     [rsp+1180h+var_1110], r8
0x180010c1e  mov     rdi, rcx
0x180010c21  mov     [rsp+1180h+var_1118], rcx
0x180010c26  mov     rbx, cs:WPP_GLOBAL_Control
0x180010c2d  lea     rsi, WPP_GLOBAL_Control
0x180010c34  lea     r12, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180010c3b  mov     r13d, 2000h
0x180010c41  cmp     rbx, rsi
0x180010c44  jz      short loc_180010C6A
0x180010c46  test    [rbx+1Ch], r13d
0x180010c4a  jz      short loc_180010C6A
0x180010c4c  cmp     byte ptr [rbx+19h], 6
0x180010c50  jb      short loc_180010C6A
0x180010c52  mov     rcx, [rbx+10h]
0x180010c56  mov     edx, 1BCh
0x180010c5b  mov     r8, r12
0x180010c5e  call    WPP_SF_
0x180010c63  mov     rbx, cs:WPP_GLOBAL_Control
0x180010c6a  xor     r15d, r15d
0x180010c6d  lea     rcx, [rbp+1080h+OutBuffer]; void *
0x180010c74  xor     edx, edx; Val
0x180010c76  mov     [rsp+1180h+BytesReturned], r15d
0x180010c7b  mov     r8d, 8D0h; Size
0x180010c81  call    memset_0
0x180010c86  test    rdi, rdi
0x180010c89  jz      loc_180011D1F
0x180010c8f  cmp     dword ptr [rdi+18h], 2
0x180010c93  jz      loc_180011CF8
0x180010c99  cmp     dword ptr [rdi+1Ch], 2
0x180010c9d  jz      short loc_180010D0D
0x180010c9f  mov     dword ptr [r14], 25Eh
0x180010ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cad  cmp     rcx, rsi
0x180010cb0  jz      loc_180011D9E
0x180010cb6  test    [rcx+1Ch], r13d
0x180010cba  jz      short loc_180010CDA
0x180010cbc  cmp     byte ptr [rcx+19h], 2
0x180010cc0  jb      short loc_180010CDA
0x180010cc2  mov     rcx, [rcx+10h]
0x180010cc6  mov     edx, 1C1h
0x180010ccb  mov     r8, r12
0x180010cce  call    WPP_SF_
0x180010cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cda  cmp     rcx, rsi
0x180010cdd  jz      loc_180011D9E
0x180010ce3  test    [rcx+1Ch], r13d
0x180010ce7  jz      loc_180011D9E
0x180010ced  cmp     byte ptr [rcx+19h], 6
0x180010cf1  jb      loc_180011D9E
0x180010cf7  mov     edx, 1C2h
0x180010cfc  mov     r8, r12
0x180010cff  mov     rcx, [rcx+10h]
0x180010d03  call    WPP_SF_
0x180010d08  jmp     loc_180011D9E
0x180010d0d  mov     rax, [rdi+418h]
0x180010d14  mov     esi, 264h
0x180010d19  test    rax, rax
0x180010d1c  jnz     short loc_180010D27
0x180010d1e  mov     r12, [rdi+0F0h]
0x180010d25  jmp     short loc_180010D2B
0x180010d27  mov     r12, [rax+20h]
0x180010d2b  mov     [rsp+1180h+var_1120], r12
0x180010d30  test    r12, r12
0x180010d33  jz      loc_180011CB6
0x180010d39  mov     ecx, [r14]
0x180010d3c  mov     rax, [r12+10h]
0x180010d41  cmp     [rax], ecx
0x180010d43  jz      short loc_180010D58
0x180010d45  mov     r12, [r12]
0x180010d49  mov     [rsp+1180h+var_1120], r12
0x180010d4e  test    r12, r12
0x180010d51  jnz     short loc_180010D3C
0x180010d53  jmp     loc_180011CB6
0x180010d58  mov     rax, [rdi+100h]
0x180010d5f  lea     rdx, [r14+224h]; Src
0x180010d66  mov     [rbp+1080h+OutBuffer], rax
0x180010d6d  mov     ecx, 4B8h
0x180010d72  movzx   eax, word ptr [r14]
0x180010d76  mov     ebx, r15d
0x180010d79  mov     [rbp+1080h+var_908], ax
0x180010d80  mov     eax, [r14+220h]
0x180010d87  cmp     eax, ecx
0x180010d89  cmova   eax, ecx
0x180010d8c  lea     rcx, [rbp+1080h+var_4F8]; void *
0x180010d93  mov     r8d, eax; Size
0x180010d96  mov     [rbp+1080h+var_4FC], r8d
0x180010d9d  call    memcpy_0
0x180010da2  cmp     [rdi+428h], r15
0x180010da9  mov     ecx, r15d
0x180010dac  mov     rax, [r12+10h]
0x180010db1  mov     edx, 1
0x180010db6  setnz   cl
0x180010db9  mov     [rax+120h], ecx
0x180010dbf  mov     rax, [r12+10h]
0x180010dc4  cmp     dword ptr [rax], 800h
0x180010dca  jz      short loc_180010DE0
0x180010dcc  cmp     dword ptr [rax], 86DDh
0x180010dd2  mov     r13d, r15d
0x180010dd5  mov     [rsp+1180h+var_113C], r15d
0x180010dda  jnz     loc_1800110EB
0x180010de0  mov     r13d, [rbp+1080h+var_4F8]
0x180010de7  mov     [rsp+1180h+var_113C], r13d
0x180010dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180010df3  lea     rax, WPP_GLOBAL_Control
0x180010dfa  mov     esi, 2000h
0x180010dff  cmp     rcx, rax
0x180010e02  jz      short loc_180010E32
0x180010e04  test    [rcx+1Ch], esi
0x180010e07  jz      short loc_180010E32
0x180010e09  cmp     byte ptr [rcx+19h], 4
0x180010e0d  jb      short loc_180010E32
0x180010e0f  mov     rcx, [rcx+10h]
0x180010e13  lea     r9, [rdi+8]
0x180010e17  mov     edx, 1C3h
0x180010e1c  mov     dword ptr [rsp+1180h+lpWideCharStr], r13d
0x180010e21  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180010e28  call    WPP_SF_sd
0x180010e2d  mov     edx, 1
0x180010e32  cmp     r13d, edx
0x180010e35  ja      short loc_180010E78
0x180010e37  mov     ecx, [r14+4]
0x180010e3b  mov     eax, 17h
0x180010e40  mov     [rbp+1080h+var_4DA], ax
0x180010e47  mov     rdx, 0FFFF000000000000h
0x180010e51  mov     rax, [rbp+0BA0h]
0x180010e58  shl     rcx, 18h
0x180010e5c  xor     rax, rcx
0x180010e5f  and     rcx, 0FFFFFFFFFF000000h
0x180010e66  and     rax, rdx
0x180010e69  mov     edx, 1
0x180010e6e  xor     rax, rcx
0x180010e71  mov     [rbp+0BA0h], rax
0x180010e78  mov     rax, [r12+10h]
0x180010e7d  cmp     dword ptr [rax], 86DDh
0x180010e83  jnz     short loc_180010EA4
0x180010e85  cmp     r13d, 2
0x180010e89  jnz     short loc_180010EA4
0x180010e8b  cmp     [rdi+428h], r15
0x180010e92  jz      loc_180010F65
0x180010e98  mov     [r14+428h], edx
0x180010e9f  jmp     loc_180010F65
0x180010ea4  cmp     r13d, edx
0x180010ea7  jnz     loc_180010F65
0x180010ead  mov     rcx, [rdi+428h]
0x180010eb4  mov     eax, [r14+4]
0x180010eb8  mov     [rcx+0ACh], eax
0x180010ebe  mov     rcx, [rdi+428h]
0x180010ec5  add     rcx, 90h
0x180010ecc  call    SetCompartmentNetworkMapping
0x180010ed1  mov     ebx, eax
0x180010ed3  test    eax, eax
0x180010ed5  jz      short loc_180010F44
0x180010ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ede  lea     rdi, WPP_GLOBAL_Control
0x180010ee5  cmp     rcx, rdi
0x180010ee8  jz      short loc_180010F0D
0x180010eea  test    [rcx+1Ch], esi
0x180010eed  jz      short loc_180010F0D
0x180010eef  cmp     byte ptr [rcx+19h], 2
0x180010ef3  jb      short loc_180010F0D
0x180010ef5  mov     rcx, [rcx+10h]
0x180010ef9  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180010f00  mov     edx, 1C4h
0x180010f05  mov     r9d, eax
0x180010f08  call    WPP_SF_d
0x180010f0d  mov     [r14], ebx
0x180010f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f17  cmp     rcx, rdi
0x180010f1a  jz      loc_180011D9E
0x180010f20  test    [rcx+1Ch], esi
0x180010f23  jz      loc_180011D9E
0x180010f29  cmp     byte ptr [rcx+19h], 6
0x180010f2d  jb      loc_180011D9E
0x180010f33  mov     edx, 1C5h
0x180010f38  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180010f3f  jmp     loc_180010CFF
0x180010f44  mov     rax, [rdi+428h]
0x180010f4b  mov     edx, 1
0x180010f50  movups  xmm0, xmmword ptr [rax+90h]
0x180010f57  mov     [rbp+1080h+var_4C8], edx
0x180010f5d  movdqu  [rbp+1080h+var_4D8], xmm0
0x180010f65  mov     rcx, [rdi+428h]
0x180010f6c  test    rcx, rcx
0x180010f6f  jz      loc_1800110EB
0x180010f75  cmp     cs:g_RasMobileCore, r15d
0x180010f7c  mov     r9d, 10h
0x180010f82  mov     [rbp+1080h+var_704], r9w
0x180010f8a  mov     rax, [rcx+90h]
0x180010f91  mov     qword ptr [rbp+1080h+Src], rax
0x180010f98  mov     rax, [rcx+98h]
0x180010f9f  mov     [rbp+1080h+var_6FA], rax
0x180010fa6  mov     qword ptr [rsp+1180h+pguid.Data1], r15
0x180010fab  mov     [rsp+1180h+PtNumOfCharConverted], r15
0x180010fb0  mov     [rsp+1180h+var_1140], r15d
0x180010fb5  jnz     loc_1800110EB
0x180010fbb  cmp     r13d, 2
0x180010fbf  jnz     short loc_180010FE2
0x180010fc1  mov     r8d, r9d; Size
0x180010fc4  lea     rdx, GUID_NULL; Buf2
0x180010fcb  lea     rcx, [rbp+1080h+Buf1]; Buf1
0x180010fd2  call    memcmp_0
0x180010fd7  test    eax, eax
0x180010fd9  jnz     loc_1800110EB
0x180010fdf  lea     edx, [rax+1]
0x180010fe2  mov     esi, edx
0x180010fe4  lea     r9, [rsp+1180h+var_1140]
0x180010fe9  lea     rdx, [rsp+1180h+PtNumOfCharConverted]
0x180010fee  xor     r8d, r8d
0x180010ff1  lea     rcx, [rsp+1180h+pguid]
0x180010ff6  call    GetINetCfgLock
0x180010ffb  test    eax, eax
0x180010ffd  jns     short loc_180011046
0x180010fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180011006  lea     rdx, WPP_GLOBAL_Control
0x18001100d  cmp     rcx, rdx
0x180011010  jz      short loc_180011041
0x180011012  test    dword ptr [rcx+1Ch], 2000h
0x180011019  jz      short loc_180011041
0x18001101b  cmp     byte ptr [rcx+19h], 2
0x18001101f  jb      short loc_180011041
0x180011021  mov     rcx, [rcx+10h]
0x180011025  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18001102c  movzx   r9d, ax
0x180011030  mov     edx, 1C6h
0x180011035  call    WPP_SF_d
0x18001103a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011041  mov     esi, r15d
0x180011044  jmp     short loc_18001104D
0x180011046  mov     rcx, cs:WPP_GLOBAL_Control
0x18001104d  lea     rax, WPP_GLOBAL_Control
0x180011054  cmp     rcx, rax
0x180011057  jz      short loc_18001107D
0x180011059  test    dword ptr [rcx+1Ch], 2000h
0x180011060  jz      short loc_18001107D
0x180011062  cmp     byte ptr [rcx+19h], 4
0x180011066  jb      short loc_18001107D
0x180011068  mov     rcx, [rcx+10h]
0x18001106c  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180011073  mov     edx, 1C7h
0x180011078  call    WPP_SF_
0x18001107d  lea     rcx, [rbp+1080h+Src]
0x180011084  call    DwAddLegacyKeysForInterface
0x180011089  mov     ebx, eax
0x18001108b  test    eax, eax
0x18001108d  jz      short loc_1800110C9
0x18001108f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011096  lea     rax, WPP_GLOBAL_Control
0x18001109d  cmp     rcx, rax
0x1800110a0  jz      short loc_1800110C9
0x1800110a2  test    dword ptr [rcx+1Ch], 2000h
0x1800110a9  jz      short loc_1800110C9
0x1800110ab  cmp     byte ptr [rcx+19h], 2
0x1800110af  jb      short loc_1800110C9
0x1800110b1  mov     rcx, [rcx+10h]
0x1800110b5  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800110bc  mov     edx, 1C8h
0x1800110c1  mov     r9d, ebx
0x1800110c4  call    WPP_SF_d
0x1800110c9  test    esi, esi
0x1800110cb  jz      short loc_1800110EB
0x1800110cd  mov     rcx, qword ptr [rsp+1180h+pguid.Data1]
0x1800110d2  test    rcx, rcx
0x1800110d5  jz      short loc_1800110EB
0x1800110d7  mov     rdx, [rsp+1180h+PtNumOfCharConverted]
0x1800110dc  test    rdx, rdx
0x1800110df  jz      short loc_1800110EB
0x1800110e1  mov     r8d, [rsp+1180h+var_1140]
0x1800110e6  call    ReleaseINetCfgLock
0x1800110eb  mov     r8, [rdi+428h]
0x1800110f2  test    r8, r8
0x1800110f5  jz      loc_1800114CF
0x1800110fb  lea     rax, [rbp+1080h+WideCharStr]
0x180011102  mov     [rsp+1180h+cchWideChar], 100h; cchWideChar
0x18001110a  add     r8, 1BDh; lpMultiByteStr
0x180011111  mov     [rsp+1180h+lpWideCharStr], rax; lpWideCharStr
0x180011116  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001111a  xor     edx, edx; dwFlags
0x18001111c  mov     ecx, 0FDE9h; CodePage
0x180011121  call    cs:__imp_MultiByteToWideChar
0x180011128  nop     dword ptr [rax+rax+00h]
0x18001112d  add     ax, ax
0x180011130  mov     [rbp+1080h+var_906], ax
0x180011137  mov     rax, [r12+10h]
0x18001113c  cmp     dword ptr [rax], 800h
  ... truncated ...
```
