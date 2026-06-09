# RasTriggerConnectionEx

- ea: `0x18008a200`
- end: `0x18008b1e0`
- name: `RasTriggerConnectionEx`
- size: `4064`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, char *, int, HRASCONN *, __int64, int, const wchar_t *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180089d50`

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
- `0x18007f21c`
- `0x180082fa0`
- `0x18008a200`
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

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008ab77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008ab77`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008a498`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008a957`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008a498`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008a957`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008b138`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008b138`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008a6b4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008a6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a6c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a6c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b142`
- `rasman!RasInitialize` at `0x18008a44c`
- `rasman!RasInitialize` at `0x18008a44c`

## pseudocode

```c
__int64 __fastcall RasTriggerConnectionEx(
        const wchar_t *a1,
        const wchar_t *a2,
        char *a3,
        int a4,
        HRASCONN *a5,
        __int64 a6,
        int a7,
        const wchar_t *a8)
{
  unsigned int v12; // eax
  unsigned int v13; // eax
  _DWORD *v14; // rcx
  unsigned int EntryPropertiesWrapper; // ebx
  __int64 v16; // rdx
  __int64 v17; // r9
  DWORD EntryEapInfo; // eax
  char *v19; // rax
  char *v20; // rsi
  unsigned int v21; // eax
  __int64 v22; // rax
  __int64 v23; // r9
  __int64 v24; // rdx
  const WCHAR *v25; // r15
  __int64 v26; // r9
  _DWORD *v27; // rbx
  DWORD LastError; // eax
  _QWORD *v29; // rcx
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  struct tagRASDIALPARAMSW *v32; // rax
  struct tagRASDIALPARAMSW *v33; // r12
  _QWORD *v34; // rcx
  _DWORD *v35; // r15
  _DWORD *v36; // r14
  __int64 v37; // r9
  _QWORD *v38; // rcx
  HLOCAL v39; // rax
  __int64 v40; // r11
  bool v41; // zf
  unsigned int EAPIdentityData; // eax
  int v43; // eax
  _QWORD *v44; // rcx
  HRASCONN *v45; // r13
  DWORD v46; // eax
  __int64 v47; // rax
  DWORD v48; // eax
  int v50; // [rsp+20h] [rbp-E0h]
  BOOL v52; // [rsp+48h] [rbp-B8h]
  _DWORD *v53; // [rsp+50h] [rbp-B0h]
  struct tagRASCREDENTIALSW v55; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Src[1034]; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int16 v57; // [rsp+8AAh] [rbp+7AAh]
  __int64 v58[266]; // [rsp+CF0h] [rbp+BF0h] BYREF

  if ( a1 && a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_qdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 782, (_DWORD)a3, (_DWORD)a3, a4, (__int64)a1, (__int64)a2);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 783, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, a3, a4);
  }
  memset_0(Src, 0, 0x848u);
  memset_0(v58, 0, 0x848u);
  v52 = 0;
  DebugInit();
  v12 = EnableAutoTracing();
  if ( v12
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 784, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v12);
  }
  v13 = EnableAutoWPPTracing();
  if ( !v13 )
    goto LABEL_21;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 785, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v13);
LABEL_21:
    v14 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !a2 || !a5 )
  {
    v17 = 87;
    EntryPropertiesWrapper = 87;
    if ( v14 != (_DWORD *)&WPP_GLOBAL_Control && (v14[7] & 0x800) != 0 && *((_BYTE *)v14 + 25) >= 2u )
    {
      v16 = 786;
      goto LABEL_243;
    }
    goto LABEL_244;
  }
  if ( !(unsigned int)IsPhoneBookPathValid(a3, a1) )
  {
    EntryPropertiesWrapper = 623;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 787;
LABEL_30:
      v17 = EntryPropertiesWrapper;
LABEL_243:
      WPP_SF_d(*((_QWORD *)v14 + 2), v16, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v17);
      v14 = WPP_GLOBAL_Control;
      goto LABEL_244;
    }
    goto LABEL_244;
  }
  if ( a4 && a3 == (char *)-1LL )
  {
    v17 = 87;
    EntryPropertiesWrapper = 87;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 788;
      goto LABEL_243;
    }
    goto LABEL_244;
  }
  *a5 = 0;
  EntryEapInfo = RasInitialize();
  EntryPropertiesWrapper = EntryEapInfo;
  if ( EntryEapInfo )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_244;
    }
    v16 = 789;
    goto LABEL_42;
  }
  v19 = (char *)GlobalAlloc(0x40u, 0x29D0u);
  v20 = v19;
  if ( !v19 )
  {
    v17 = 14;
    EntryPropertiesWrapper = 14;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 790;
      goto LABEL_243;
    }
    goto LABEL_244;
  }
  memset_0(v19, 0, 0x29D0u);
  *((_QWORD *)v20 + 1336) = a6;
  *((_DWORD *)v20 + 2650) = 1;
  *((_DWORD *)v20 + 2644) = a4;
  StringCchCopyW((STRSAFE_LPWSTR)v20 + 409, 0x105u, a1);
  StringCchCopyW((STRSAFE_LPWSTR)v20 + 152, 0x101u, a2);
  v21 = ComputeHashFromEntryName((LPCWSTR)v20 + 152);
  if ( v21 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 791, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v21);
    }
    v22 = StrDup(v20 + 304);
    *((_QWORD *)v20 + 1337) = v22;
    if ( !v22 )
    {
      v23 = 14;
      EntryPropertiesWrapper = 14;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_249;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_244;
      v24 = 792;
      goto LABEL_58;
    }
  }
  v25 = a1;
  *((_DWORD *)v20 + 2) = 6724;
  *((_DWORD *)v20 + 2639) = -777928482;
  EntryPropertiesWrapper = RasGetEntryPropertiesWrapper(a1, a2, v20 + 3680);
  if ( !EntryPropertiesWrapper )
  {
    v27 = v20 + 7728;
    v53 = v20 + 7728;
    if ( a7 )
    {
      if ( (*v27 & 0x4000000) == 0 )
      {
        v17 = 87;
        EntryPropertiesWrapper = 87;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 794;
          goto LABEL_243;
        }
        goto LABEL_244;
      }
    }
    else
    {
      v53 = v20 + 7728;
    }
    if ( (unsigned __int64)(a3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v52 = ImpersonateLoggedOnUser(a3);
      if ( !v52 )
      {
        LastError = GetLastError();
        EntryPropertiesWrapper = LastError;
        if ( LastError )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_249;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_244;
          v24 = 795;
LABEL_79:
          v23 = LastError;
LABEL_58:
          WPP_SF_d(*((_QWORD *)v14 + 2), v24, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v23);
LABEL_59:
          v14 = WPP_GLOBAL_Control;
          goto LABEL_244;
        }
LABEL_237:
        v45 = a5;
        goto LABEL_238;
      }
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        796,
        WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
        *((unsigned int *)v20 + 921));
      v29 = WPP_GLOBAL_Control;
    }
    if ( (*((_DWORD *)v20 + 921) & 0x20000) != 0 )
    {
      if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 && *((_BYTE *)v29 + 25) >= 5u )
        WPP_SF_(v29[2], 797, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      EntryEapInfo = GetEntryEapInfo(a3, v20 + 3680, a1, a2, v20 + 10532, v20 + 10520, v20 + 10564, v20 + 10620);
      EntryPropertiesWrapper = EntryEapInfo;
      if ( EntryEapInfo )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_244;
        }
        v16 = 798;
        goto LABEL_42;
      }
      v27 = v53;
      goto LABEL_113;
    }
    if ( (*((_DWORD *)v20 + 1932) & 0x8400000) != 0 )
    {
      if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 && *((_BYTE *)v29 + 25) >= 5u )
        WPP_SF_(v29[2], 799, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      *((_DWORD *)v20 + 2641) = 0;
      *((_DWORD *)v20 + 2650) = 0;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v31 = 800;
        goto LABEL_112;
      }
    }
    else
    {
      if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 && *((_BYTE *)v29 + 25) >= 5u )
        WPP_SF_(v29[2], 801, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      *((_DWORD *)v20 + 2641) = 2;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v31 = 802;
LABEL_112:
        WPP_SF_(v30[2], v31, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
LABEL_113:
        v30 = WPP_GLOBAL_Control;
      }
    }
    if ( (*((_DWORD *)v20 + 921) & 0x4000) != 0 )
    {
      if ( v30 != &WPP_GLOBAL_Control && (*((_DWORD *)v30 + 7) & 0x800) != 0 && *((_BYTE *)v30 + 25) >= 5u )
        WPP_SF_(v30[2], 803, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      *((_DWORD *)v20 + 2655) = 1;
      v30 = WPP_GLOBAL_Control;
    }
    if ( v30 != &WPP_GLOBAL_Control && (*((_DWORD *)v30 + 7) & 0x800) != 0 && *((_BYTE *)v30 + 25) >= 5u )
    {
      LOBYTE(v26) = *((_DWORD *)v20 + 2655) != 0;
      WPP_SF_c(v30[2], 804, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v26);
    }
    v32 = (struct tagRASDIALPARAMSW *)GlobalAlloc(0x40u, 0x848u);
    *((_QWORD *)v20 + 1303) = v32;
    v33 = v32;
    if ( !v32 )
    {
      v17 = 14;
      EntryPropertiesWrapper = 14;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 805;
        goto LABEL_243;
      }
      goto LABEL_244;
    }
    memset_0(v32, 0, 0x848u);
    if ( a8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 816, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      }
      StringCchCopyW(v33->szUserName, 0x101u, a8 + 4);
      StringCchCopyW(v33->szDomain, 0x10u, a8 + 518);
      StringCchCopyW(v33->szPassword, 0x101u, a8 + 261);
      EncodePasswordW(v40);
      *((_DWORD *)v20 + 2649) = (*v27 >> 25) & 1;
    }
    else
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 806, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        v34 = WPP_GLOBAL_Control;
      }
      if ( (*v27 & 0x2000000) != 0
        && (*((_DWORD *)v20 + 2641) == 2 && !*((_DWORD *)v20 + 2655) || (*v27 & 0x8000000) != 0) )
      {
        if ( v34 != &WPP_GLOBAL_Control && (*((_DWORD *)v34 + 7) & 0x800) != 0 && *((_BYTE *)v34 + 25) >= 5u )
          WPP_SF_(v34[2], 807, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        v35 = v20 + 10592;
        v36 = v20 + 10588;
        EntryEapInfo = FindEntryCredentials(
                         a1,
                         a2,
                         (__int64)Src,
                         (__int64)v58,
                         (__int64)(v20 + 10588),
                         (__int64)(v20 + 10592));
        EntryPropertiesWrapper = EntryEapInfo;
        if ( EntryEapInfo )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_244;
          }
          v16 = 808;
          goto LABEL_42;
        }
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          LOBYTE(v50) = *v35 != 0;
          LOBYTE(v37) = *v36 != 0;
          WPP_SF_cc(*((_QWORD *)WPP_GLOBAL_Control + 2), 809, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v37, v50);
          v38 = WPP_GLOBAL_Control;
        }
        if ( *v36 )
        {
          v27 = v53;
          if ( (*v53 & 0x8000000) != 0 )
          {
            if ( v38 != &WPP_GLOBAL_Control && (*((_DWORD *)v38 + 7) & 0x800) != 0 && *((_BYTE *)v38 + 25) >= 5u )
            {
              WPP_SF_(v38[2], 810, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
              v38 = WPP_GLOBAL_Control;
            }
            if ( v57 )
            {
              v39 = LocalAlloc(0x40u, 0x848u);
              *((_QWORD *)v20 + 1304) = v39;
              if ( !v39 )
              {
                LastError = GetLastError();
                EntryPropertiesWrapper = LastError;
                if ( LastError )
                {
                  v14 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    goto LABEL_249;
                  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    goto LABEL_244;
                  v24 = 811;
                  goto LABEL_79;
                }
                goto LABEL_237;
              }
              memcpy_0(v39, Src, 0x848u);
              **((_DWORD **)v20 + 1304) = 2120;
            }
            else if ( v38 != &WPP_GLOBAL_Control && (*((_DWORD *)v38 + 7) & 0x800) != 0 && *((_BYTE *)v38 + 25) >= 5u )
            {
              WPP_SF_(v38[2], 812, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            }
          }
          else
          {
            if ( v38 != &WPP_GLOBAL_Control && (*((_DWORD *)v38 + 7) & 0x800) != 0 && *((_BYTE *)v38 + 25) >= 5u )
              WPP_SF_(v38[2], 813, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            memcpy_0(v33, Src, 0x848u);
          }
          goto LABEL_165;
        }
        if ( !*v35 )
        {
          v27 = v53;
LABEL_165:
          v25 = a1;
          goto LABEL_166;
        }
        if ( v38 != &WPP_GLOBAL_Control && (*((_DWORD *)v38 + 7) & 0x800) != 0 && *((_BYTE *)v38 + 25) >= 5u )
          WPP_SF_(v38[2], 814, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        memset_0(v55.szUserName, 0, 0x424u);
        memcpy_0(v33, v58, 0x848u);
        v25 = a1;
        v55.dwSize = 1068;
        v55.dwMask = 7;
        EntryEapInfo = RasSetCredentialsW(a1, a2, &v55, 1);
        EntryPropertiesWrapper = EntryEapInfo;
        if ( EntryEapInfo )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_244;
          }
          v16 = 815;
LABEL_42:
          v17 = EntryEapInfo;
          goto LABEL_243;
        }
        v27 = v53;
      }
    }
LABEL_166:
    v33->dwSize = 2120;
    StringCchCopyW(v33->szEntryName, 0x101u, a2);
    StringCchCopyW(v33->szPhoneNumber, 0x81u, (STRSAFE_LPCWSTR)v20 + 1859);
    if ( *((_DWORD *)v20 + 2655) || *((_DWORD *)v20 + 2641) == 2 || (*v27 & 0x8000000) != 0 )
    {
      *((_DWORD *)v20 + 2650) = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 817, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, 0);
      }
    }
    v33->dwCallbackId = (ULONG_PTR)v20;
    v41 = *((_DWORD *)v20 + 2641) == 2;
    *((_DWORD *)v20 + 2612) = 60;
    *((_DWORD *)v20 + 2613) = 268435458;
    if ( !v41 && (*((_DWORD *)v20 + 921) & 0x20000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 818, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      }
      EAPIdentityData = AutoTriggerGetEAPIdentityData(0, v20 + 3680, v20);
      if ( EAPIdentityData )
      {
        if ( EAPIdentityData == 703 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 820, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
          }
        }
        else
        {
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                821,
                WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                EAPIdentityData);
              v44 = WPP_GLOBAL_Control;
            }
            if ( v44 != &WPP_GLOBAL_Control && (*((_DWORD *)v44 + 7) & 0x800) != 0 && *((_BYTE *)v44 + 25) >= 5u )
              WPP_SF_(v44[2], 822, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
          }
          *((_DWORD *)v20 + 2650) = 0;
        }
        *(_QWORD *)(v20 + 10484) = 0;
        *((_DWORD *)v20 + 2620) = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 819, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        }
        v43 = *((_DWORD *)v20 + 2636);
        *((_DWORD *)v20 + 2650) = 0;
        *((_DWORD *)v20 + 2620) = v43;
        *(_QWORD *)(v20 + 10484) = *(_QWORD *)(v20 + 10548);
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 823, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    }
    EncodePasswordW(v33->szPassword);
    v45 = a5;
    v46 = RasDialW((struct tagRASDIALEXTENSIONS *)(v20 + 10448), v25, v33, 2u, RasDialFunc2, a5);
    EntryPropertiesWrapper = v46;
    if ( v46
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 824, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v46);
    }
    EncodePasswordW(v33->szPassword);
    if ( EntryPropertiesWrapper )
      goto LABEL_59;
LABEL_238:
    v47 = ValidateHrasconn(*v45);
    *(_DWORD *)(v47 + 5600) = 2;
    *(_QWORD *)(v47 + 5624) = v20;
    *((_QWORD *)v20 + 1301) = *v45;
LABEL_248:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_249;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 793;
    goto LABEL_30;
  }
LABEL_244:
  if ( v14 != (_DWORD *)&WPP_GLOBAL_Control && (v14[7] & 0x800) != 0 && *((_BYTE *)v14 + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)v14 + 2), 825, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, EntryPropertiesWrapper);
    goto LABEL_248;
  }
LABEL_249:
  if ( v52 )
  {
    if ( RevertToSelf() )
      goto LABEL_256;
    v48 = GetLastError();
    EntryPropertiesWrapper = v48;
    if ( !v48 )
      goto LABEL_256;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return EntryPropertiesWrapper;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 826, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v48);
LABEL_256:
      v14 = WPP_GLOBAL_Control;
    }
  }
  if ( v14 != (_DWORD *)&WPP_GLOBAL_Control && (v14[7] & 0x800) != 0 && *((_BYTE *)v14 + 25) >= 6u )
    WPP_SF_d(*((_QWORD *)v14 + 2), 827, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, EntryPropertiesWrapper);
  return EntryPropertiesWrapper;
}

```

## disassembly

```asm
0x18008a200  mov     [rsp-8+arg_18], rbx
0x18008a205  push    rbp
0x18008a206  push    rsi
0x18008a207  push    rdi
0x18008a208  push    r12
0x18008a20a  push    r13
0x18008a20c  push    r14
0x18008a20e  push    r15
0x18008a210  lea     rbp, [rsp-1450h]
0x18008a218  mov     eax, 1550h
0x18008a21d  call    _alloca_probe
0x18008a222  sub     rsp, rax
0x18008a225  mov     rax, cs:__security_cookie
0x18008a22c  xor     rax, rsp
0x18008a22f  mov     [rbp+1480h+var_40], rax
0x18008a236  mov     rbx, [rbp+1480h+arg_20]
0x18008a23d  xor     esi, esi
0x18008a23f  mov     rax, [rbp+1480h+arg_38]
0x18008a246  mov     r15d, r9d
0x18008a249  mov     [rsp+1580h+pszSrc], rdx
0x18008a24e  mov     r14, r8
0x18008a251  mov     [rsp+1580h+var_1540], rcx
0x18008a256  mov     r12, rdx
0x18008a259  mov     [rsp+1580h+var_1520], rbx
0x18008a25e  mov     r13, rcx
0x18008a261  mov     [rsp+1580h+var_1518], rax
0x18008a266  test    rcx, rcx
0x18008a269  jz      short loc_18008A2B4
0x18008a26b  test    rdx, rdx
0x18008a26e  jz      short loc_18008A2B4
0x18008a270  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a277  lea     rdi, WPP_GLOBAL_Control
0x18008a27e  cmp     rcx, rdi
0x18008a281  jz      short loc_18008A2F3
0x18008a283  test    dword ptr [rcx+1Ch], 800h
0x18008a28a  jz      short loc_18008A2F3
0x18008a28c  cmp     byte ptr [rcx+19h], 6
0x18008a290  jb      short loc_18008A2F3
0x18008a292  mov     rcx, [rcx+10h]
0x18008a296  mov     edx, 30Eh
0x18008a29b  mov     [rsp+1580h+var_1550], r12
0x18008a2a0  mov     [rsp+1580h+var_1558], r13
0x18008a2a5  mov     dword ptr [rsp+1580h+var_1560], r9d
0x18008a2aa  mov     r9, r8
0x18008a2ad  call    WPP_SF_qdSS
0x18008a2b2  jmp     short loc_18008A2F3
0x18008a2b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a2bb  lea     rdi, WPP_GLOBAL_Control
0x18008a2c2  cmp     rcx, rdi
0x18008a2c5  jz      short loc_18008A2F3
0x18008a2c7  test    dword ptr [rcx+1Ch], 800h
0x18008a2ce  jz      short loc_18008A2F3
0x18008a2d0  cmp     byte ptr [rcx+19h], 6
0x18008a2d4  jb      short loc_18008A2F3
0x18008a2d6  mov     rcx, [rcx+10h]
0x18008a2da  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008a2e1  mov     edx, 30Fh
0x18008a2e6  mov     dword ptr [rsp+1580h+var_1560], r15d
0x18008a2eb  mov     r9, r14
0x18008a2ee  call    WPP_SF_qD
0x18008a2f3  xor     edx, edx; Val
0x18008a2f5  lea     rcx, [rbp+1480h+Src]; void *
0x18008a2fc  mov     r8d, 848h; Size
0x18008a302  call    memset_0
0x18008a307  xor     edx, edx; Val
0x18008a309  lea     rcx, [rbp+1480h+var_890]; void *
0x18008a310  mov     r8d, 848h; Size
0x18008a316  call    memset_0
0x18008a31b  mov     [rsp+1580h+var_1538], esi
0x18008a31f  call    DebugInit
0x18008a324  call    EnableAutoTracing
0x18008a329  test    eax, eax
0x18008a32b  jz      short loc_18008A360
0x18008a32d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a334  cmp     rcx, rdi
0x18008a337  jz      short loc_18008A360
0x18008a339  test    dword ptr [rcx+1Ch], 800h
0x18008a340  jz      short loc_18008A360
0x18008a342  cmp     byte ptr [rcx+19h], 2
0x18008a346  jb      short loc_18008A360
0x18008a348  mov     rcx, [rcx+10h]
0x18008a34c  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008a353  mov     edx, 310h
0x18008a358  mov     r9d, eax
0x18008a35b  call    WPP_SF_d
0x18008a360  call    EnableAutoWPPTracing
0x18008a365  test    eax, eax
0x18008a367  jz      short loc_18008A39C
0x18008a369  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a370  cmp     rcx, rdi
0x18008a373  jz      short loc_18008A3A3
0x18008a375  test    dword ptr [rcx+1Ch], 800h
0x18008a37c  jz      short loc_18008A3A3
0x18008a37e  cmp     byte ptr [rcx+19h], 2
0x18008a382  jb      short loc_18008A3A3
0x18008a384  mov     rcx, [rcx+10h]
0x18008a388  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008a38f  mov     edx, 311h
0x18008a394  mov     r9d, eax
0x18008a397  call    WPP_SF_d
0x18008a39c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a3a3  test    r13, r13
0x18008a3a6  jz      loc_18008B0C2
0x18008a3ac  test    r12, r12
0x18008a3af  jz      loc_18008B0C2
0x18008a3b5  test    rbx, rbx
0x18008a3b8  jz      loc_18008B0C2
0x18008a3be  mov     rdx, r13
0x18008a3c1  mov     rcx, r14
0x18008a3c4  call    IsPhoneBookPathValid
0x18008a3c9  test    eax, eax
0x18008a3cb  jnz     short loc_18008A406
0x18008a3cd  mov     ebx, 26Fh
0x18008a3d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a3d9  cmp     rcx, rdi
0x18008a3dc  jz      loc_18008B0FB
0x18008a3e2  test    dword ptr [rcx+1Ch], 800h
0x18008a3e9  jz      loc_18008B0FB
0x18008a3ef  cmp     byte ptr [rcx+19h], 2
0x18008a3f3  jb      loc_18008B0FB
0x18008a3f9  mov     edx, 313h
0x18008a3fe  mov     r9d, ebx
0x18008a401  jmp     loc_18008B0E4
0x18008a406  test    r15d, r15d
0x18008a409  jz      short loc_18008A449
0x18008a40b  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18008a40f  jnz     short loc_18008A449
0x18008a411  lea     r9d, [r14+58h]
0x18008a415  mov     ebx, r9d
0x18008a418  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a41f  cmp     rcx, rdi
0x18008a422  jz      loc_18008B0FB
0x18008a428  test    dword ptr [rcx+1Ch], 800h
0x18008a42f  jz      loc_18008B0FB
0x18008a435  cmp     byte ptr [rcx+19h], 2
0x18008a439  jb      loc_18008B0FB
0x18008a43f  mov     edx, 314h
0x18008a444  jmp     loc_18008B0E4
0x18008a449  mov     [rbx], rsi
0x18008a44c  call    cs:__imp_RasInitialize
0x18008a452  mov     ebx, eax
0x18008a454  test    eax, eax
0x18008a456  jz      short loc_18008A48C
0x18008a458  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a45f  cmp     rcx, rdi
0x18008a462  jz      loc_18008B0FB
0x18008a468  test    dword ptr [rcx+1Ch], 800h
0x18008a46f  jz      loc_18008B0FB
0x18008a475  cmp     byte ptr [rcx+19h], 2
0x18008a479  jb      loc_18008B0FB
0x18008a47f  mov     edx, 315h
0x18008a484  mov     r9d, eax
0x18008a487  jmp     loc_18008B0E4
0x18008a48c  mov     ebx, 29D0h
0x18008a491  mov     ecx, 40h ; '@'; uFlags
0x18008a496  mov     edx, ebx; dwBytes
0x18008a498  call    cs:__imp_GlobalAlloc
0x18008a49e  mov     rsi, rax
0x18008a4a1  test    rax, rax
0x18008a4a4  jnz     short loc_18008A4DE
0x18008a4a6  lea     r9d, [rax+0Eh]
0x18008a4aa  mov     ebx, r9d
0x18008a4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a4b4  cmp     rcx, rdi
0x18008a4b7  jz      loc_18008B0FB
0x18008a4bd  test    dword ptr [rcx+1Ch], 800h
0x18008a4c4  jz      loc_18008B0FB
0x18008a4ca  cmp     byte ptr [rcx+19h], 2
0x18008a4ce  jb      loc_18008B0FB
0x18008a4d4  mov     edx, 316h
0x18008a4d9  jmp     loc_18008B0E4
0x18008a4de  mov     r8, rbx; Size
0x18008a4e1  xor     edx, edx; Val
0x18008a4e3  mov     rcx, rsi; void *
0x18008a4e6  call    memset_0
0x18008a4eb  mov     rax, [rbp+1480h+arg_28]
0x18008a4f2  lea     rcx, [rsi+332h]; pszDest
0x18008a4f9  mov     r8, r13; pszSrc
0x18008a4fc  mov     [rsi+29C0h], rax
0x18008a503  mov     edx, 105h; cchDest
0x18008a508  mov     dword ptr [rsi+2968h], 1
0x18008a512  mov     [rsi+2950h], r15d
0x18008a519  call    StringCchCopyW
0x18008a51e  lea     rbx, [rsi+130h]
0x18008a525  mov     r8, r12; pszSrc
0x18008a528  mov     rcx, rbx; pszDest
0x18008a52b  mov     edx, 101h; cchDest
0x18008a530  call    StringCchCopyW
0x18008a535  lea     r15, [rsi+29C8h]
0x18008a53c  mov     rcx, rbx; pszString
0x18008a53f  mov     rdx, r15
0x18008a542  call    ComputeHashFromEntryName
0x18008a547  test    eax, eax
0x18008a549  jz      loc_18008A5E4
0x18008a54f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a556  cmp     rcx, rdi
0x18008a559  jz      short loc_18008A582
0x18008a55b  test    dword ptr [rcx+1Ch], 800h
0x18008a562  jz      short loc_18008A582
0x18008a564  cmp     byte ptr [rcx+19h], 2
0x18008a568  jb      short loc_18008A582
0x18008a56a  mov     rcx, [rcx+10h]
0x18008a56e  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008a575  mov     edx, 317h
0x18008a57a  mov     r9d, eax
0x18008a57d  call    WPP_SF_d
0x18008a582  mov     rcx, rbx
0x18008a585  call    StrDup
0x18008a58a  mov     [r15], rax
0x18008a58d  xor     r15d, r15d
0x18008a590  test    rax, rax
0x18008a593  jnz     short loc_18008A5E4
0x18008a595  lea     r9d, [r15+0Eh]
0x18008a599  mov     ebx, r9d
0x18008a59c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a5a3  cmp     rcx, rdi
0x18008a5a6  jz      loc_18008B131
0x18008a5ac  test    dword ptr [rcx+1Ch], 800h
0x18008a5b3  jz      loc_18008B0FE
0x18008a5b9  cmp     byte ptr [rcx+19h], 2
0x18008a5bd  jb      loc_18008B0FE
0x18008a5c3  mov     edx, 318h
0x18008a5c8  mov     rcx, [rcx+10h]
0x18008a5cc  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008a5d3  call    WPP_SF_d
0x18008a5d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a5df  jmp     loc_18008B0FE
0x18008a5e4  mov     r15, [rsp+1580h+var_1540]
0x18008a5e9  lea     r9, [rsi+8]
0x18008a5ed  lea     r13, [rsi+0E60h]
0x18008a5f4  mov     dword ptr [r9], 1A44h
0x18008a5fb  mov     r8, r13; Destination
0x18008a5fe  mov     dword ptr [rsi+293Ch], 0D1A1C0DEh
0x18008a608  mov     rcx, r15; LPCWSTR
0x18008a60b  mov     rdx, r12; LPCWSTR
0x18008a60e  call    RasGetEntryPropertiesWrapper
0x18008a613  mov     ebx, eax
0x18008a615  xor     eax, eax
0x18008a617  test    ebx, ebx
0x18008a619  jz      short loc_18008A64C
0x18008a61b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a622  cmp     rcx, rdi
0x18008a625  jz      loc_18008B0FB
0x18008a62b  test    dword ptr [rcx+1Ch], 800h
0x18008a632  jz      loc_18008B0FB
0x18008a638  cmp     byte ptr [rcx+19h], 2
0x18008a63c  jb      loc_18008B0FB
0x18008a642  mov     edx, 319h
0x18008a647  jmp     loc_18008A3FE
0x18008a64c  lea     rbx, [r13+0FD0h]
0x18008a653  mov     [rsp+1580h+var_1530], rbx
0x18008a658  cmp     [rbp+1480h+arg_30], eax
0x18008a65e  jz      short loc_18008A6A2
0x18008a660  test    dword ptr [rbx], 4000000h
0x18008a666  jnz     short loc_18008A6A7
0x18008a668  mov     r9d, 57h ; 'W'
0x18008a66e  mov     ebx, r9d
0x18008a671  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a678  cmp     rcx, rdi
0x18008a67b  jz      loc_18008B0FB
0x18008a681  test    dword ptr [rcx+1Ch], 800h
0x18008a688  jz      loc_18008B0FB
0x18008a68e  cmp     byte ptr [rcx+19h], 2
0x18008a692  jb      loc_18008B0FB
0x18008a698  mov     edx, 31Ah
0x18008a69d  jmp     loc_18008B0E4
0x18008a6a2  mov     [rsp+1580h+var_1530], rbx
0x18008a6a7  lea     rax, [r14-1]
0x18008a6ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008a6af  ja      short loc_18008A709
0x18008a6b1  mov     rcx, r14; hToken
0x18008a6b4  call    cs:__imp_ImpersonateLoggedOnUser
0x18008a6ba  mov     [rsp+1580h+var_1538], eax
0x18008a6be  test    eax, eax
0x18008a6c0  jnz     short loc_18008A709
0x18008a6c2  call    cs:__imp_GetLastError
0x18008a6c8  xor     r15d, r15d
0x18008a6cb  mov     ebx, eax
0x18008a6cd  test    eax, eax
0x18008a6cf  jz      loc_18008B096
0x18008a6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a6dc  cmp     rcx, rdi
0x18008a6df  jz      loc_18008B131
0x18008a6e5  test    dword ptr [rcx+1Ch], 800h
0x18008a6ec  jz      loc_18008B0FE
0x18008a6f2  cmp     byte ptr [rcx+19h], 2
0x18008a6f6  jb      loc_18008B0FE
0x18008a6fc  mov     edx, 31Bh
0x18008a701  mov     r9d, eax
0x18008a704  jmp     loc_18008A5C8
0x18008a709  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a710  mov     eax, 800h
0x18008a715  cmp     rcx, rdi
0x18008a718  jz      short loc_18008A74A
0x18008a71a  test    [rcx+1Ch], eax
0x18008a71d  jz      short loc_18008A74A
0x18008a71f  cmp     byte ptr [rcx+19h], 5
0x18008a723  jb      short loc_18008A74A
0x18008a725  mov     r9d, [r13+4]
0x18008a729  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
  ... truncated ...
```
