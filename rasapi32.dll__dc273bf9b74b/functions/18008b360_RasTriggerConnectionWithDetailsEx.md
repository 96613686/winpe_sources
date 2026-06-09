# RasTriggerConnectionWithDetailsEx

- ea: `0x18008b360`
- end: `0x18008c3ae`
- name: `RasTriggerConnectionWithDetailsEx`
- size: `4174`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, char *, int, __int64, _QWORD *, __int64, int, const wchar_t *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18008b1f0`

## callees

- `0x180009cb4`
- `0x180010d10`
- `0x1800203dc`
- `0x1800293d0`
- `0x18004e580`
- `0x18004e5c0`
- `0x18004e984`
- `0x180079500`
- `0x18007efdc`
- `0x18007f084`
- `0x18007f140`
- `0x18007f21c`
- `0x180082fa0`
- `0x18008b360`
- `0x18008fd64`
- `0x1800993e8`
- `0x1800a749c`
- `0x1800aeec0`
- `0x1800bbcf8`
- `0x1800bc148`
- `0x1800c21b0`
- `0x1800c282c`
- `0x1800c2f8c`
- `0x1800decee`
- `0x1800ded06`
- `0x1800ded50`
- `0x1800dee10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008bcd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008bcd7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008b5f8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008bab7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008b5f8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008bab7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008c306`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008c306`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008b814`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008b814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c310`
- `rasman!RasSetConnectionUserData` at `0x18008c23b`
- `rasman!RasSetConnectionUserData` at `0x18008c23b`
- `rasman!RasInitialize` at `0x18008b5ac`
- `rasman!RasInitialize` at `0x18008b5ac`

## pseudocode

```c
__int64 __fastcall RasTriggerConnectionWithDetailsEx(
        const wchar_t *a1,
        const wchar_t *a2,
        char *a3,
        int a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        int a8,
        const wchar_t *a9)
{
  _QWORD *v9; // rbx
  unsigned int v14; // eax
  unsigned int v15; // eax
  _DWORD *v16; // rcx
  unsigned int EntryPropertiesWrapper; // ebx
  __int64 v18; // rdx
  __int64 v19; // r9
  DWORD EntryEapInfo; // eax
  char *v21; // rax
  char *v22; // rsi
  unsigned int v23; // eax
  __int64 v24; // rax
  __int64 v25; // r9
  __int64 v26; // rdx
  const WCHAR *v27; // r15
  __int64 v28; // r9
  _DWORD *v29; // rbx
  DWORD LastError; // eax
  _QWORD *v31; // rcx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  struct tagRASDIALPARAMSW *v34; // rax
  struct tagRASDIALPARAMSW *v35; // r12
  _QWORD *v36; // rcx
  _DWORD *v37; // r15
  _DWORD *v38; // r14
  __int64 v39; // r9
  _QWORD *v40; // rcx
  HLOCAL v41; // rax
  __int64 v42; // r11
  bool v43; // zf
  unsigned int EAPIdentityData; // eax
  int v45; // eax
  _QWORD *v46; // rcx
  HRASCONN *v47; // r13
  DWORD v48; // eax
  __int64 v49; // rax
  DWORD v50; // eax
  int v52; // [rsp+20h] [rbp-E0h]
  BOOL v54; // [rsp+48h] [rbp-B8h]
  _DWORD *v55; // [rsp+50h] [rbp-B0h]
  HRASCONN *v57; // [rsp+60h] [rbp-A0h]
  const wchar_t *v58; // [rsp+68h] [rbp-98h]
  struct tagRASCREDENTIALSW v59; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Src[1034]; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int16 v61; // [rsp+8AAh] [rbp+7AAh]
  __int64 v62[266]; // [rsp+CF0h] [rbp+BF0h] BYREF

  v9 = a6;
  v57 = (HRASCONN *)a6;
  v58 = a9;
  if ( a1 && a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_qdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 828, (_DWORD)a3, (_DWORD)a3, a4, (__int64)a1, (__int64)a2);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 829, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, a3, a4);
  }
  memset_0(Src, 0, 0x848u);
  memset_0(v62, 0, 0x848u);
  v54 = 0;
  DebugInit();
  v14 = EnableAutoTracing();
  if ( v14
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 830, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v14);
  }
  v15 = EnableAutoWPPTracing();
  if ( !v15 )
    goto LABEL_21;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 831, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v15);
LABEL_21:
    v16 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !a2 || !v9 )
  {
    v19 = 87;
    EntryPropertiesWrapper = 87;
    if ( v16 != (_DWORD *)&WPP_GLOBAL_Control && (v16[7] & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 2u )
    {
      v18 = 832;
      goto LABEL_246;
    }
    goto LABEL_247;
  }
  if ( !(unsigned int)IsPhoneBookPathValid(a3, a1) )
  {
    EntryPropertiesWrapper = 623;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 833;
LABEL_30:
      v19 = EntryPropertiesWrapper;
LABEL_246:
      WPP_SF_d(*((_QWORD *)v16 + 2), v18, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v19);
      v16 = WPP_GLOBAL_Control;
      goto LABEL_247;
    }
    goto LABEL_247;
  }
  if ( a4 && a3 == (char *)-1LL )
  {
    v19 = 87;
    EntryPropertiesWrapper = 87;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 834;
      goto LABEL_246;
    }
    goto LABEL_247;
  }
  *v9 = 0;
  EntryEapInfo = RasInitialize();
  EntryPropertiesWrapper = EntryEapInfo;
  if ( EntryEapInfo )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_247;
    }
    v18 = 835;
    goto LABEL_42;
  }
  v21 = (char *)GlobalAlloc(0x40u, 0x29D0u);
  v22 = v21;
  if ( !v21 )
  {
    v19 = 14;
    EntryPropertiesWrapper = 14;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 836;
      goto LABEL_246;
    }
    goto LABEL_247;
  }
  memset_0(v21, 0, 0x29D0u);
  *((_QWORD *)v22 + 1336) = a7;
  *((_DWORD *)v22 + 2650) = 1;
  *((_DWORD *)v22 + 2644) = a4;
  StringCchCopyW((STRSAFE_LPWSTR)v22 + 409, 0x105u, a1);
  StringCchCopyW((STRSAFE_LPWSTR)v22 + 152, 0x101u, a2);
  v23 = ComputeHashFromEntryName((LPCWSTR)v22 + 152);
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 837, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v23);
    }
    v24 = StrDup(v22 + 304);
    *((_QWORD *)v22 + 1337) = v24;
    if ( !v24 )
    {
      v25 = 14;
      EntryPropertiesWrapper = 14;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_252;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_247;
      v26 = 838;
      goto LABEL_58;
    }
  }
  v27 = a1;
  *((_DWORD *)v22 + 2) = 6724;
  *((_DWORD *)v22 + 2639) = -777928482;
  EntryPropertiesWrapper = RasGetEntryPropertiesWrapper(a1, a2, v22 + 3680);
  if ( EntryPropertiesWrapper )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 839;
      goto LABEL_30;
    }
LABEL_247:
    if ( v16 != (_DWORD *)&WPP_GLOBAL_Control && (v16[7] & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)v16 + 2), 871, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, EntryPropertiesWrapper);
      goto LABEL_251;
    }
    goto LABEL_252;
  }
  v29 = v22 + 7728;
  v55 = v22 + 7728;
  if ( a8 )
  {
    if ( (*v29 & 0x4000000) == 0 )
    {
      v19 = 87;
      EntryPropertiesWrapper = 87;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = 840;
        goto LABEL_246;
      }
      goto LABEL_247;
    }
  }
  else
  {
    v55 = v22 + 7728;
  }
  if ( (unsigned __int64)(a3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v54 = ImpersonateLoggedOnUser(a3);
    if ( !v54 )
    {
      LastError = GetLastError();
      EntryPropertiesWrapper = LastError;
      if ( LastError )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_252;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_247;
        v26 = 841;
LABEL_79:
        v25 = LastError;
LABEL_58:
        WPP_SF_d(*((_QWORD *)v16 + 2), v26, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v25);
LABEL_59:
        v16 = WPP_GLOBAL_Control;
        goto LABEL_247;
      }
LABEL_237:
      v47 = v57;
      goto LABEL_238;
    }
  }
  v31 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      842,
      WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
      *((unsigned int *)v22 + 921));
    v31 = WPP_GLOBAL_Control;
  }
  if ( (*((_DWORD *)v22 + 921) & 0x20000) != 0 )
  {
    if ( v31 != &WPP_GLOBAL_Control && (*((_DWORD *)v31 + 7) & 0x800) != 0 && *((_BYTE *)v31 + 25) >= 5u )
      WPP_SF_(v31[2], 843, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    EntryEapInfo = GetEntryEapInfo(a3, v22 + 3680, a1, a2, v22 + 10532, v22 + 10520, v22 + 10564, v22 + 10620);
    EntryPropertiesWrapper = EntryEapInfo;
    if ( EntryEapInfo )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_247;
      }
      v18 = 844;
      goto LABEL_42;
    }
    v29 = v55;
    goto LABEL_113;
  }
  if ( (*((_DWORD *)v22 + 1932) & 0x8400000) != 0 )
  {
    if ( v31 != &WPP_GLOBAL_Control && (*((_DWORD *)v31 + 7) & 0x800) != 0 && *((_BYTE *)v31 + 25) >= 5u )
      WPP_SF_(v31[2], 845, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    *((_DWORD *)v22 + 2641) = 0;
    *((_DWORD *)v22 + 2650) = 0;
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v33 = 846;
      goto LABEL_112;
    }
  }
  else
  {
    if ( v31 != &WPP_GLOBAL_Control && (*((_DWORD *)v31 + 7) & 0x800) != 0 && *((_BYTE *)v31 + 25) >= 5u )
      WPP_SF_(v31[2], 847, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    *((_DWORD *)v22 + 2641) = 2;
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v33 = 848;
LABEL_112:
      WPP_SF_(v32[2], v33, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
LABEL_113:
      v32 = WPP_GLOBAL_Control;
    }
  }
  if ( (*((_DWORD *)v22 + 921) & 0x4000) != 0 )
  {
    if ( v32 != &WPP_GLOBAL_Control && (*((_DWORD *)v32 + 7) & 0x800) != 0 && *((_BYTE *)v32 + 25) >= 5u )
      WPP_SF_(v32[2], 849, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    *((_DWORD *)v22 + 2655) = 1;
    v32 = WPP_GLOBAL_Control;
  }
  if ( v32 != &WPP_GLOBAL_Control && (*((_DWORD *)v32 + 7) & 0x800) != 0 && *((_BYTE *)v32 + 25) >= 5u )
  {
    LOBYTE(v28) = *((_DWORD *)v22 + 2655) != 0;
    WPP_SF_c(v32[2], 850, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v28);
  }
  v34 = (struct tagRASDIALPARAMSW *)GlobalAlloc(0x40u, 0x848u);
  *((_QWORD *)v22 + 1303) = v34;
  v35 = v34;
  if ( !v34 )
  {
    v19 = 14;
    EntryPropertiesWrapper = 14;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 851;
      goto LABEL_246;
    }
    goto LABEL_247;
  }
  memset_0(v34, 0, 0x848u);
  if ( v58 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 862, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    }
    StringCchCopyW(v35->szUserName, 0x101u, v58 + 4);
    StringCchCopyW(v35->szDomain, 0x10u, v58 + 518);
    StringCchCopyW(v35->szPassword, 0x101u, v58 + 261);
    EncodePasswordW(v42);
    *((_DWORD *)v22 + 2649) = (*v29 >> 25) & 1;
  }
  else
  {
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 852, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      v36 = WPP_GLOBAL_Control;
    }
    if ( (*v29 & 0x2000000) != 0
      && (*((_DWORD *)v22 + 2641) == 2 && !*((_DWORD *)v22 + 2655) || (*v29 & 0x8000000) != 0) )
    {
      if ( v36 != &WPP_GLOBAL_Control && (*((_DWORD *)v36 + 7) & 0x800) != 0 && *((_BYTE *)v36 + 25) >= 5u )
        WPP_SF_(v36[2], 853, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      v37 = v22 + 10592;
      v38 = v22 + 10588;
      EntryEapInfo = FindEntryCredentials(
                       a1,
                       a2,
                       (__int64)Src,
                       (__int64)v62,
                       (__int64)(v22 + 10588),
                       (__int64)(v22 + 10592));
      EntryPropertiesWrapper = EntryEapInfo;
      if ( EntryEapInfo )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_247;
        }
        v18 = 854;
        goto LABEL_42;
      }
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LOBYTE(v52) = *v37 != 0;
        LOBYTE(v39) = *v38 != 0;
        WPP_SF_cc(*((_QWORD *)WPP_GLOBAL_Control + 2), 855, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v39, v52);
        v40 = WPP_GLOBAL_Control;
      }
      if ( *v38 )
      {
        v29 = v55;
        if ( (*v55 & 0x8000000) != 0 )
        {
          if ( v40 != &WPP_GLOBAL_Control && (*((_DWORD *)v40 + 7) & 0x800) != 0 && *((_BYTE *)v40 + 25) >= 5u )
          {
            WPP_SF_(v40[2], 856, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            v40 = WPP_GLOBAL_Control;
          }
          if ( v61 )
          {
            v41 = LocalAlloc(0x40u, 0x848u);
            *((_QWORD *)v22 + 1304) = v41;
            if ( !v41 )
            {
              LastError = GetLastError();
              EntryPropertiesWrapper = LastError;
              if ( LastError )
              {
                v16 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                  goto LABEL_252;
                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  goto LABEL_247;
                v26 = 857;
                goto LABEL_79;
              }
              goto LABEL_237;
            }
            memcpy_0(v41, Src, 0x848u);
            **((_DWORD **)v22 + 1304) = 2120;
          }
          else if ( v40 != &WPP_GLOBAL_Control && (*((_DWORD *)v40 + 7) & 0x800) != 0 && *((_BYTE *)v40 + 25) >= 5u )
          {
            WPP_SF_(v40[2], 858, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
          }
        }
        else
        {
          if ( v40 != &WPP_GLOBAL_Control && (*((_DWORD *)v40 + 7) & 0x800) != 0 && *((_BYTE *)v40 + 25) >= 5u )
            WPP_SF_(v40[2], 859, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
          memcpy_0(v35, Src, 0x848u);
        }
        goto LABEL_165;
      }
      if ( !*v37 )
      {
        v29 = v55;
LABEL_165:
        v27 = a1;
        goto LABEL_166;
      }
      if ( v40 != &WPP_GLOBAL_Control && (*((_DWORD *)v40 + 7) & 0x800) != 0 && *((_BYTE *)v40 + 25) >= 5u )
        WPP_SF_(v40[2], 860, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      memset_0(v59.szUserName, 0, 0x424u);
      memcpy_0(v35, v62, 0x848u);
      v27 = a1;
      v59.dwSize = 1068;
      v59.dwMask = 7;
      EntryEapInfo = RasSetCredentialsW(a1, a2, &v59, 1);
      EntryPropertiesWrapper = EntryEapInfo;
      if ( EntryEapInfo )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_247;
        }
        v18 = 861;
LABEL_42:
        v19 = EntryEapInfo;
        goto LABEL_246;
      }
      v29 = v55;
    }
  }
LABEL_166:
  v35->dwSize = 2120;
  StringCchCopyW(v35->szEntryName, 0x101u, a2);
  StringCchCopyW(v35->szPhoneNumber, 0x81u, (STRSAFE_LPCWSTR)v22 + 1859);
  if ( *((_DWORD *)v22 + 2655) || *((_DWORD *)v22 + 2641) == 2 || (*v29 & 0x8000000) != 0 )
  {
    *((_DWORD *)v22 + 2650) = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 863, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, 0);
    }
  }
  v35->dwCallbackId = (ULONG_PTR)v22;
  v43 = *((_DWORD *)v22 + 2641) == 2;
  *((_DWORD *)v22 + 2612) = 60;
  *((_DWORD *)v22 + 2613) = 268435458;
  if ( !v43 && (*((_DWORD *)v22 + 921) & 0x20000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 864, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    }
    EAPIdentityData = AutoTriggerGetEAPIdentityData(0, v22 + 3680, v22);
    if ( EAPIdentityData )
    {
      if ( EAPIdentityData == 703 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 866, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        }
      }
      else
      {
        v46 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              867,
              WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
              EAPIdentityData);
            v46 = WPP_GLOBAL_Control;
          }
          if ( v46 != &WPP_GLOBAL_Control && (*((_DWORD *)v46 + 7) & 0x800) != 0 && *((_BYTE *)v46 + 25) >= 5u )
            WPP_SF_(v46[2], 868, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        }
        *((_DWORD *)v22 + 2650) = 0;
      }
      *(_QWORD *)(v22 + 10484) = 0;
      *((_DWORD *)v22 + 2620) = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 865, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      }
      v45 = *((_DWORD *)v22 + 2636);
      *((_DWORD *)v22 + 2650) = 0;
      *((_DWORD *)v22 + 2620) = v45;
      *(_QWORD *)(v22 + 10484) = *(_QWORD *)(v22 + 10548);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 869, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
  }
  EncodePasswordW(v35->szPassword);
  v47 = v57;
  v48 = RasDialW((struct tagRASDIALEXTENSIONS *)(v22 + 10448), v27, v35, 2u, RasDialFunc2, v57);
  EntryPropertiesWrapper = v48;
  if ( v48
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 870, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v48);
  }
  EncodePasswordW(v35->szPassword);
  if ( EntryPropertiesWrapper )
    goto LABEL_59;
LABEL_238:
  v49 = ValidateHrasconn(*v47);
  *(_DWORD *)(v49 + 5600) = 2;
  *(_QWORD *)(v49 + 5624) = v22;
  *((_QWORD *)v22 + 1301) = *v47;
  RasSetConnectionUserData(*v47, 16, &a5);
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      872,
      WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
      (unsigned int)a5,
      HIDWORD(a5));
LABEL_251:
    v16 = WPP_GLOBAL_Control;
  }
LABEL_252:
  if ( v54 )
  {
    if ( RevertToSelf() )
      goto LABEL_259;
    v50 = GetLastError();
    EntryPropertiesWrapper = v50;
    if ( !v50 )
      goto LABEL_259;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return EntryPropertiesWrapper;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 873, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v50);
LABEL_259:
      v16 = WPP_GLOBAL_Control;
    }
  }
  if ( v16 != (_DWORD *)&WPP_GLOBAL_Control && (v16[7] & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 6u )
    WPP_SF_d(*((_QWORD *)v16 + 2), 874, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, EntryPropertiesWrapper);
  return EntryPropertiesWrapper;
}

```

## disassembly

```asm
0x18008b360  mov     [rsp-8+arg_18], rbx
0x18008b365  push    rbp
0x18008b366  push    rsi
0x18008b367  push    rdi
0x18008b368  push    r12
0x18008b36a  push    r13
0x18008b36c  push    r14
0x18008b36e  push    r15
0x18008b370  lea     rbp, [rsp-1450h]
0x18008b378  mov     eax, 1550h
0x18008b37d  call    _alloca_probe
0x18008b382  sub     rsp, rax
0x18008b385  mov     rax, cs:__security_cookie
0x18008b38c  xor     rax, rsp
0x18008b38f  mov     [rbp+1480h+var_40], rax
0x18008b396  mov     rbx, [rbp+1480h+arg_28]
0x18008b39d  xor     esi, esi
0x18008b39f  mov     rax, [rbp+1480h+arg_40]
0x18008b3a6  mov     r15d, r9d
0x18008b3a9  mov     [rsp+1580h+pszSrc], rdx
0x18008b3ae  mov     r14, r8
0x18008b3b1  mov     [rsp+1580h+var_1540], rcx
0x18008b3b6  mov     r12, rdx
0x18008b3b9  mov     [rsp+1580h+var_1520], rbx
0x18008b3be  mov     r13, rcx
0x18008b3c1  mov     [rsp+1580h+var_1518], rax
0x18008b3c6  test    rcx, rcx
0x18008b3c9  jz      short loc_18008B414
0x18008b3cb  test    rdx, rdx
0x18008b3ce  jz      short loc_18008B414
0x18008b3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b3d7  lea     rdi, WPP_GLOBAL_Control
0x18008b3de  cmp     rcx, rdi
0x18008b3e1  jz      short loc_18008B453
0x18008b3e3  test    dword ptr [rcx+1Ch], 800h
0x18008b3ea  jz      short loc_18008B453
0x18008b3ec  cmp     byte ptr [rcx+19h], 6
0x18008b3f0  jb      short loc_18008B453
0x18008b3f2  mov     rcx, [rcx+10h]
0x18008b3f6  mov     edx, 33Ch
0x18008b3fb  mov     [rsp+1580h+var_1550], r12
0x18008b400  mov     [rsp+1580h+var_1558], r13
0x18008b405  mov     dword ptr [rsp+1580h+var_1560], r9d
0x18008b40a  mov     r9, r8
0x18008b40d  call    WPP_SF_qdSS
0x18008b412  jmp     short loc_18008B453
0x18008b414  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b41b  lea     rdi, WPP_GLOBAL_Control
0x18008b422  cmp     rcx, rdi
0x18008b425  jz      short loc_18008B453
0x18008b427  test    dword ptr [rcx+1Ch], 800h
0x18008b42e  jz      short loc_18008B453
0x18008b430  cmp     byte ptr [rcx+19h], 6
0x18008b434  jb      short loc_18008B453
0x18008b436  mov     rcx, [rcx+10h]
0x18008b43a  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008b441  mov     edx, 33Dh
0x18008b446  mov     dword ptr [rsp+1580h+var_1560], r15d
0x18008b44b  mov     r9, r14
0x18008b44e  call    WPP_SF_qD
0x18008b453  xor     edx, edx; Val
0x18008b455  lea     rcx, [rbp+1480h+Src]; void *
0x18008b45c  mov     r8d, 848h; Size
0x18008b462  call    memset_0
0x18008b467  xor     edx, edx; Val
0x18008b469  lea     rcx, [rbp+1480h+var_890]; void *
0x18008b470  mov     r8d, 848h; Size
0x18008b476  call    memset_0
0x18008b47b  mov     [rsp+1580h+var_1538], esi
0x18008b47f  call    DebugInit
0x18008b484  call    EnableAutoTracing
0x18008b489  test    eax, eax
0x18008b48b  jz      short loc_18008B4C0
0x18008b48d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b494  cmp     rcx, rdi
0x18008b497  jz      short loc_18008B4C0
0x18008b499  test    dword ptr [rcx+1Ch], 800h
0x18008b4a0  jz      short loc_18008B4C0
0x18008b4a2  cmp     byte ptr [rcx+19h], 2
0x18008b4a6  jb      short loc_18008B4C0
0x18008b4a8  mov     rcx, [rcx+10h]
0x18008b4ac  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008b4b3  mov     edx, 33Eh
0x18008b4b8  mov     r9d, eax
0x18008b4bb  call    WPP_SF_d
0x18008b4c0  call    EnableAutoWPPTracing
0x18008b4c5  test    eax, eax
0x18008b4c7  jz      short loc_18008B4FC
0x18008b4c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b4d0  cmp     rcx, rdi
0x18008b4d3  jz      short loc_18008B503
0x18008b4d5  test    dword ptr [rcx+1Ch], 800h
0x18008b4dc  jz      short loc_18008B503
0x18008b4de  cmp     byte ptr [rcx+19h], 2
0x18008b4e2  jb      short loc_18008B503
0x18008b4e4  mov     rcx, [rcx+10h]
0x18008b4e8  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008b4ef  mov     edx, 33Fh
0x18008b4f4  mov     r9d, eax
0x18008b4f7  call    WPP_SF_d
0x18008b4fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b503  test    r13, r13
0x18008b506  jz      loc_18008C290
0x18008b50c  test    r12, r12
0x18008b50f  jz      loc_18008C290
0x18008b515  test    rbx, rbx
0x18008b518  jz      loc_18008C290
0x18008b51e  mov     rdx, r13
0x18008b521  mov     rcx, r14
0x18008b524  call    IsPhoneBookPathValid
0x18008b529  test    eax, eax
0x18008b52b  jnz     short loc_18008B566
0x18008b52d  mov     ebx, 26Fh
0x18008b532  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b539  cmp     rcx, rdi
0x18008b53c  jz      loc_18008C2C9
0x18008b542  test    dword ptr [rcx+1Ch], 800h
0x18008b549  jz      loc_18008C2C9
0x18008b54f  cmp     byte ptr [rcx+19h], 2
0x18008b553  jb      loc_18008C2C9
0x18008b559  mov     edx, 341h
0x18008b55e  mov     r9d, ebx
0x18008b561  jmp     loc_18008C2B2
0x18008b566  test    r15d, r15d
0x18008b569  jz      short loc_18008B5A9
0x18008b56b  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18008b56f  jnz     short loc_18008B5A9
0x18008b571  lea     r9d, [r14+58h]
0x18008b575  mov     ebx, r9d
0x18008b578  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b57f  cmp     rcx, rdi
0x18008b582  jz      loc_18008C2C9
0x18008b588  test    dword ptr [rcx+1Ch], 800h
0x18008b58f  jz      loc_18008C2C9
0x18008b595  cmp     byte ptr [rcx+19h], 2
0x18008b599  jb      loc_18008C2C9
0x18008b59f  mov     edx, 342h
0x18008b5a4  jmp     loc_18008C2B2
0x18008b5a9  mov     [rbx], rsi
0x18008b5ac  call    cs:__imp_RasInitialize
0x18008b5b2  mov     ebx, eax
0x18008b5b4  test    eax, eax
0x18008b5b6  jz      short loc_18008B5EC
0x18008b5b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b5bf  cmp     rcx, rdi
0x18008b5c2  jz      loc_18008C2C9
0x18008b5c8  test    dword ptr [rcx+1Ch], 800h
0x18008b5cf  jz      loc_18008C2C9
0x18008b5d5  cmp     byte ptr [rcx+19h], 2
0x18008b5d9  jb      loc_18008C2C9
0x18008b5df  mov     edx, 343h
0x18008b5e4  mov     r9d, eax
0x18008b5e7  jmp     loc_18008C2B2
0x18008b5ec  mov     ebx, 29D0h
0x18008b5f1  mov     ecx, 40h ; '@'; uFlags
0x18008b5f6  mov     edx, ebx; dwBytes
0x18008b5f8  call    cs:__imp_GlobalAlloc
0x18008b5fe  mov     rsi, rax
0x18008b601  test    rax, rax
0x18008b604  jnz     short loc_18008B63E
0x18008b606  lea     r9d, [rax+0Eh]
0x18008b60a  mov     ebx, r9d
0x18008b60d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b614  cmp     rcx, rdi
0x18008b617  jz      loc_18008C2C9
0x18008b61d  test    dword ptr [rcx+1Ch], 800h
0x18008b624  jz      loc_18008C2C9
0x18008b62a  cmp     byte ptr [rcx+19h], 2
0x18008b62e  jb      loc_18008C2C9
0x18008b634  mov     edx, 344h
0x18008b639  jmp     loc_18008C2B2
0x18008b63e  mov     r8, rbx; Size
0x18008b641  xor     edx, edx; Val
0x18008b643  mov     rcx, rsi; void *
0x18008b646  call    memset_0
0x18008b64b  mov     rax, [rbp+1480h+arg_30]
0x18008b652  lea     rcx, [rsi+332h]; pszDest
0x18008b659  mov     r8, r13; pszSrc
0x18008b65c  mov     [rsi+29C0h], rax
0x18008b663  mov     edx, 105h; cchDest
0x18008b668  mov     dword ptr [rsi+2968h], 1
0x18008b672  mov     [rsi+2950h], r15d
0x18008b679  call    StringCchCopyW
0x18008b67e  lea     rbx, [rsi+130h]
0x18008b685  mov     r8, r12; pszSrc
0x18008b688  mov     rcx, rbx; pszDest
0x18008b68b  mov     edx, 101h; cchDest
0x18008b690  call    StringCchCopyW
0x18008b695  lea     r15, [rsi+29C8h]
0x18008b69c  mov     rcx, rbx; pszString
0x18008b69f  mov     rdx, r15
0x18008b6a2  call    ComputeHashFromEntryName
0x18008b6a7  test    eax, eax
0x18008b6a9  jz      loc_18008B744
0x18008b6af  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b6b6  cmp     rcx, rdi
0x18008b6b9  jz      short loc_18008B6E2
0x18008b6bb  test    dword ptr [rcx+1Ch], 800h
0x18008b6c2  jz      short loc_18008B6E2
0x18008b6c4  cmp     byte ptr [rcx+19h], 2
0x18008b6c8  jb      short loc_18008B6E2
0x18008b6ca  mov     rcx, [rcx+10h]
0x18008b6ce  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008b6d5  mov     edx, 345h
0x18008b6da  mov     r9d, eax
0x18008b6dd  call    WPP_SF_d
0x18008b6e2  mov     rcx, rbx
0x18008b6e5  call    StrDup
0x18008b6ea  mov     [r15], rax
0x18008b6ed  xor     r15d, r15d
0x18008b6f0  test    rax, rax
0x18008b6f3  jnz     short loc_18008B744
0x18008b6f5  lea     r9d, [r15+0Eh]
0x18008b6f9  mov     ebx, r9d
0x18008b6fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b703  cmp     rcx, rdi
0x18008b706  jz      loc_18008C2FF
0x18008b70c  test    dword ptr [rcx+1Ch], 800h
0x18008b713  jz      loc_18008C2CC
0x18008b719  cmp     byte ptr [rcx+19h], 2
0x18008b71d  jb      loc_18008C2CC
0x18008b723  mov     edx, 346h
0x18008b728  mov     rcx, [rcx+10h]
0x18008b72c  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008b733  call    WPP_SF_d
0x18008b738  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b73f  jmp     loc_18008C2CC
0x18008b744  mov     r15, [rsp+1580h+var_1540]
0x18008b749  lea     r9, [rsi+8]
0x18008b74d  lea     r13, [rsi+0E60h]
0x18008b754  mov     dword ptr [r9], 1A44h
0x18008b75b  mov     r8, r13; Destination
0x18008b75e  mov     dword ptr [rsi+293Ch], 0D1A1C0DEh
0x18008b768  mov     rcx, r15; LPCWSTR
0x18008b76b  mov     rdx, r12; LPCWSTR
0x18008b76e  call    RasGetEntryPropertiesWrapper
0x18008b773  mov     ebx, eax
0x18008b775  xor     eax, eax
0x18008b777  test    ebx, ebx
0x18008b779  jz      short loc_18008B7AC
0x18008b77b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b782  cmp     rcx, rdi
0x18008b785  jz      loc_18008C2C9
0x18008b78b  test    dword ptr [rcx+1Ch], 800h
0x18008b792  jz      loc_18008C2C9
0x18008b798  cmp     byte ptr [rcx+19h], 2
0x18008b79c  jb      loc_18008C2C9
0x18008b7a2  mov     edx, 347h
0x18008b7a7  jmp     loc_18008B55E
0x18008b7ac  lea     rbx, [r13+0FD0h]
0x18008b7b3  mov     [rsp+1580h+var_1530], rbx
0x18008b7b8  cmp     [rbp+1480h+arg_38], eax
0x18008b7be  jz      short loc_18008B802
0x18008b7c0  test    dword ptr [rbx], 4000000h
0x18008b7c6  jnz     short loc_18008B807
0x18008b7c8  mov     r9d, 57h ; 'W'
0x18008b7ce  mov     ebx, r9d
0x18008b7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b7d8  cmp     rcx, rdi
0x18008b7db  jz      loc_18008C2C9
0x18008b7e1  test    dword ptr [rcx+1Ch], 800h
0x18008b7e8  jz      loc_18008C2C9
0x18008b7ee  cmp     byte ptr [rcx+19h], 2
0x18008b7f2  jb      loc_18008C2C9
0x18008b7f8  mov     edx, 348h
0x18008b7fd  jmp     loc_18008C2B2
0x18008b802  mov     [rsp+1580h+var_1530], rbx
0x18008b807  lea     rax, [r14-1]
0x18008b80b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008b80f  ja      short loc_18008B869
0x18008b811  mov     rcx, r14; hToken
0x18008b814  call    cs:__imp_ImpersonateLoggedOnUser
0x18008b81a  mov     [rsp+1580h+var_1538], eax
0x18008b81e  test    eax, eax
0x18008b820  jnz     short loc_18008B869
0x18008b822  call    cs:__imp_GetLastError
0x18008b828  xor     r15d, r15d
0x18008b82b  mov     ebx, eax
0x18008b82d  test    eax, eax
0x18008b82f  jz      loc_18008C1FC
0x18008b835  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b83c  cmp     rcx, rdi
0x18008b83f  jz      loc_18008C2FF
0x18008b845  test    dword ptr [rcx+1Ch], 800h
0x18008b84c  jz      loc_18008C2CC
0x18008b852  cmp     byte ptr [rcx+19h], 2
0x18008b856  jb      loc_18008C2CC
0x18008b85c  mov     edx, 349h
0x18008b861  mov     r9d, eax
0x18008b864  jmp     loc_18008B728
0x18008b869  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b870  mov     eax, 800h
0x18008b875  cmp     rcx, rdi
0x18008b878  jz      short loc_18008B8AA
0x18008b87a  test    [rcx+1Ch], eax
0x18008b87d  jz      short loc_18008B8AA
0x18008b87f  cmp     byte ptr [rcx+19h], 5
0x18008b883  jb      short loc_18008B8AA
0x18008b885  mov     r9d, [r13+4]
0x18008b889  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
  ... truncated ...
```
