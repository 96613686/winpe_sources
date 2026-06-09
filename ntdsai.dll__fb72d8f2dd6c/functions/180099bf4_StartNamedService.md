# StartNamedService

- ea: `0x180099bf4`
- end: `0x18009a82a`
- name: `StartNamedService`
- size: `3126`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18008d610`
- `0x18009ccd0`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x180030bd4`
- `0x180099bf4`
- `0x1800a1694`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a2ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a3b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a50e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a2ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a3b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a50e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a06b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a0dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a0e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a492`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a4fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a06b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a0dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a0e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a492`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a4fb`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18009a2ac`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18009a2ac`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180099d5c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180099d5c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180099c3b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180099c3b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009a615`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009a623`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009a615`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009a623`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009a0ab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009a4ce`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009a0ab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009a4ce`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180099e81`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18009a0c9`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18009a3ab`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18009a4ec`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180099e81`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18009a0c9`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18009a3ab`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18009a4ec`

## pseudocode

```c
__int64 __fastcall StartNamedService(const WCHAR *a1)
{
  SC_HANDLE v2; // rax
  int v3; // edi
  SC_HANDLE v4; // r13
  DWORD LastError; // r14d
  __int64 v6; // rdx
  __int64 v7; // rcx
  BOOL v8; // esi
  int v9; // eax
  SC_HANDLE v10; // r15
  __int64 v11; // rdx
  __int64 v12; // rcx
  BOOL v13; // esi
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  BOOL v19; // esi
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  BOOL v23; // esi
  int v24; // eax
  DWORD TickCount; // eax
  unsigned int v26; // esi
  DWORD v27; // r14d
  DWORD v28; // edx
  __int64 v29; // rdx
  __int64 v30; // rcx
  BOOL v31; // esi
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  BOOL v35; // esi
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  BOOL v39; // esi
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rcx
  BOOL v43; // esi
  int v44; // eax
  DWORD v45; // eax
  unsigned int v46; // esi
  DWORD v47; // r14d
  int v48; // ecx
  DWORD v49; // edx
  char v50; // r14
  __int64 v51; // rdx
  __int64 v52; // rcx
  BOOL v53; // esi
  int v54; // eax
  __int64 v55; // rdx
  __int64 v56; // rcx
  BOOL v57; // esi
  __int64 v58; // rdx
  __int64 v59; // rcx
  BOOL v60; // esi
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp-29h] BYREF
  BYTE Buffer[16]; // [rsp+58h] [rbp-21h] BYREF
  __int128 v64; // [rsp+68h] [rbp-11h]
  int v65; // [rsp+78h] [rbp-1h]

  v65 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v64 = 0;
  v2 = OpenSCManagerW(0, 0, 0xF003Fu);
  v3 = 1;
  v4 = v2;
  if ( v2 )
  {
    v10 = OpenServiceW(v2, a1, 0xF01FFu);
    if ( v10 )
    {
      if ( QueryServiceStatusEx(v10, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      {
        if ( ((*(_DWORD *)&Buffer[4] - 1) & 0xFFFFFFFD) != 0 )
        {
          LastError = 0;
          if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v22, v21)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v23 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v22, v21)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v22, v21)
              || (v24 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)) != 0 )
            {
              v24 = 1;
            }
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51186673,
              4,
              3,
              v24,
              v23,
              34,
              &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
              (__int64)a1);
          }
        }
        else
        {
LABEL_72:
          TickCount = GetTickCount();
          v26 = DWORD1(v64);
          v27 = TickCount;
          while ( *(_DWORD *)&Buffer[4] == 3 )
          {
            v28 = DWORD2(v64) / 0xA;
            if ( DWORD2(v64) / 0xA >= 0x3E8 )
            {
              if ( v28 > 0x2710 )
                v28 = 10000;
            }
            else
            {
              v28 = 1000;
            }
            Sleep(v28);
            if ( !QueryServiceStatusEx(v10, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
            {
              LastError = GetLastError();
              if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
                || (unsigned int)THStateCheckForTraceOverride(v34, v33)
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v34, v33)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
              {
                v35 = gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v34, v33)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
                if ( (unsigned int)THStateCheckForTraceOverride(v34, v33)
                  || (v36 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
                {
                  v36 = 1;
                }
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  51186705,
                  3,
                  3,
                  v36,
                  v35,
                  35,
                  &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
                  (__int64)a1,
                  LastError);
              }
              goto LABEL_180;
            }
            if ( DWORD1(v64) > v26 )
              goto LABEL_72;
            if ( GetTickCount() - v27 > DWORD2(v64) )
            {
              LastError = 258;
              if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
                || (unsigned int)THStateCheckForTraceOverride(v30, v29)
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
              {
                v31 = gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
                if ( (unsigned int)THStateCheckForTraceOverride(v30, v29)
                  || (v32 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
                {
                  v32 = 1;
                }
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  51186718,
                  3,
                  3,
                  v32,
                  v31,
                  36,
                  &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
                  (__int64)a1);
              }
              goto LABEL_180;
            }
          }
          if ( StartServiceW(v10, 0, 0) )
          {
            if ( QueryServiceStatusEx(v10, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
            {
LABEL_151:
              v45 = GetTickCount();
              v46 = DWORD1(v64);
              v47 = v45;
              while ( 1 )
              {
                v48 = *(_DWORD *)&Buffer[4];
                if ( *(_DWORD *)&Buffer[4] != 2 )
                  break;
                v49 = DWORD2(v64) / 0xA;
                if ( DWORD2(v64) / 0xA >= 0x3E8 )
                {
                  if ( v49 > 0x2710 )
                    v49 = 10000;
                }
                else
                {
                  v49 = 1000;
                }
                Sleep(v49);
                if ( !QueryServiceStatusEx(v10, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
                {
                  v50 = GetLastError();
                  if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
                    || (unsigned int)THStateCheckForTraceOverride(v52, v51)
                    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
                    || gfTraceToSecondProvider
                    && ((unsigned int)THStateCheckForTraceOverride(v52, v51)
                     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
                  {
                    v53 = gfTraceToSecondProvider
                       && ((unsigned int)THStateCheckForTraceOverride(v52, v51)
                        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
                    if ( (unsigned int)THStateCheckForTraceOverride(v52, v51)
                      || (v54 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
                    {
                      v54 = 1;
                    }
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      51186777,
                      3,
                      3,
                      v54,
                      v53,
                      39,
                      &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
                      (__int64)a1,
                      v50);
                  }
LABEL_178:
                  v48 = *(_DWORD *)&Buffer[4];
                  break;
                }
                if ( DWORD1(v64) > v46 )
                  goto LABEL_151;
                if ( GetTickCount() - v47 > DWORD2(v64) )
                  goto LABEL_178;
              }
              LastError = v48 != 4 ? 0x426 : 0;
            }
            else
            {
              LastError = GetLastError();
              if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
                || (unsigned int)THStateCheckForTraceOverride(v42, v41)
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v42, v41)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
              {
                v43 = gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v42, v41)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
                if ( (unsigned int)THStateCheckForTraceOverride(v42, v41)
                  || (v44 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
                {
                  v44 = 1;
                }
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  51186746,
                  3,
                  3,
                  v44,
                  v43,
                  38,
                  &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
                  (__int64)a1,
                  LastError);
              }
            }
          }
          else
          {
            LastError = GetLastError();
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
              || (unsigned int)THStateCheckForTraceOverride(v38, v37)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v38, v37)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
            {
              v39 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v38, v37)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
              if ( (unsigned int)THStateCheckForTraceOverride(v38, v37)
                || (v40 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
              {
                v40 = 1;
              }
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                51186730,
                3,
                3,
                v40,
                v39,
                37,
                &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
                (__int64)a1,
                LastError);
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
          || (unsigned int)THStateCheckForTraceOverride(v18, v17)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v18, v17)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
        {
          v19 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v18, v17)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
          if ( (unsigned int)THStateCheckForTraceOverride(v18, v17)
            || (v20 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
          {
            v20 = 1;
          }
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51186666,
            3,
            3,
            v20,
            v19,
            33,
            &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
            (__int64)a1,
            LastError);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v12, v11)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v12, v11)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
      {
        v13 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v12, v11)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
        if ( (unsigned int)THStateCheckForTraceOverride(v12, v11)
          || (v14 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
        {
          v14 = 1;
        }
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51186655,
          3,
          3,
          v14,
          v13,
          32,
          &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
          (__int64)a1,
          LastError);
      }
    }
LABEL_180:
    CloseServiceHandle(v4);
    if ( v10 )
      CloseServiceHandle(v10);
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
      || (unsigned int)THStateCheckForTraceOverride(v7, v6)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v7, v6)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
    {
      v8 = gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v7, v6)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
      if ( (unsigned int)THStateCheckForTraceOverride(v7, v6)
        || (v9 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
      {
        v9 = 1;
      }
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51186643,
        3,
        3,
        v9,
        v8,
        31,
        &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
        (__int64)a1,
        LastError);
    }
  }
  if ( LastError )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v59, v58)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v59, v58)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v60 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v59, v58)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v59, v58)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v3 = 0;
      }
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51186816,
        2,
        3,
        v3,
        v60,
        41,
        &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
        (__int64)a1,
        LastError);
    }
  }
  else if ( (unsigned int)THStateCheckForTraceOverride(v7, v6)
         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
         || gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v56, v55)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
  {
    v57 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v56, v55)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
    if ( !(unsigned int)THStateCheckForTraceOverride(v56, v55)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) )
    {
      v3 = 0;
    }
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51186813,
      4,
      3,
      v3,
      v57,
      40,
      &WPP_17642f48579431367eaf2b8a741d67ec_Traceguids,
      (__int64)a1);
  }
  return LastError;
}

```

## disassembly

```asm
0x180099bf4  push    rbp
0x180099bf6  push    rbx
0x180099bf7  push    rsi
0x180099bf8  push    rdi
0x180099bf9  push    r12
0x180099bfb  push    r13
0x180099bfd  push    r14
0x180099bff  push    r15
0x180099c01  lea     rbp, [rsp-1Fh]
0x180099c06  sub     rsp, 98h
0x180099c0d  mov     rax, cs:__security_cookie
0x180099c14  xor     rax, rsp
0x180099c17  mov     [rbp+57h+var_50], rax
0x180099c1b  xorps   xmm0, xmm0
0x180099c1e  xor     eax, eax
0x180099c20  mov     r12, rcx
0x180099c23  mov     [rbp+57h+var_58], eax
0x180099c26  xor     ecx, ecx; lpMachineName
0x180099c28  mov     [rbp+57h+var_80], eax
0x180099c2b  xor     edx, edx; lpDatabaseName
0x180099c2d  mov     r8d, 0F003Fh; dwDesiredAccess
0x180099c33  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180099c37  movups  [rbp+57h+var_68], xmm0
0x180099c3b  call    cs:__imp_OpenSCManagerW
0x180099c41  mov     edi, 1
0x180099c46  mov     r13, rax
0x180099c49  lea     r15d, [rdi+1]
0x180099c4d  test    rax, rax
0x180099c50  jnz     loc_180099D50
0x180099c56  call    cs:__imp_GetLastError
0x180099c5c  mov     r14d, eax
0x180099c5f  lea     ebx, [rdi+2]
0x180099c62  mov     ecx, ebx
0x180099c64  call    IncrementWPPPerfCountersForLevel
0x180099c69  test    eax, eax
0x180099c6b  jnz     short loc_180099CBE
0x180099c6d  call    THStateCheckForTraceOverride
0x180099c72  test    eax, eax
0x180099c74  jnz     short loc_180099CBE
0x180099c76  mov     r8d, ebx
0x180099c79  mov     edx, ebx
0x180099c7b  xor     ecx, ecx
0x180099c7d  call    CheckWPPLevelFlagsEnabledForProvider
0x180099c82  test    eax, eax
0x180099c84  jnz     short loc_180099CBE
0x180099c86  mov     eax, cs:gfTraceToSecondProvider
0x180099c8c  test    eax, eax
0x180099c8e  jz      loc_18009A62F
0x180099c94  call    THStateCheckForTraceOverride
0x180099c99  test    eax, eax
0x180099c9b  jnz     short loc_180099CBE
0x180099c9d  call    ThStateCheckIfTraceToSecondProvier
0x180099ca2  test    eax, eax
0x180099ca4  jz      loc_18009A62F
0x180099caa  mov     r8d, ebx
0x180099cad  mov     edx, ebx
0x180099caf  mov     ecx, edi
0x180099cb1  call    CheckWPPLevelFlagsEnabledForProvider
0x180099cb6  test    eax, eax
0x180099cb8  jz      loc_18009A62F
0x180099cbe  mov     eax, cs:gfTraceToSecondProvider
0x180099cc4  test    eax, eax
0x180099cc6  jz      short loc_180099CEE
0x180099cc8  call    THStateCheckForTraceOverride
0x180099ccd  test    eax, eax
0x180099ccf  jnz     short loc_180099CEA
0x180099cd1  call    ThStateCheckIfTraceToSecondProvier
0x180099cd6  test    eax, eax
0x180099cd8  jz      short loc_180099CEE
0x180099cda  mov     r8d, ebx
0x180099cdd  mov     edx, ebx
0x180099cdf  mov     ecx, edi
0x180099ce1  call    CheckWPPLevelFlagsEnabledForProvider
0x180099ce6  test    eax, eax
0x180099ce8  jz      short loc_180099CEE
0x180099cea  mov     esi, edi
0x180099cec  jmp     short loc_180099CF0
0x180099cee  xor     esi, esi
0x180099cf0  call    THStateCheckForTraceOverride
0x180099cf5  test    eax, eax
0x180099cf7  jnz     short loc_180099D09
0x180099cf9  mov     r8d, ebx
0x180099cfc  mov     edx, ebx
0x180099cfe  xor     ecx, ecx
0x180099d00  call    CheckWPPLevelFlagsEnabledForProvider
0x180099d05  test    eax, eax
0x180099d07  jz      short loc_180099D0B
0x180099d09  mov     eax, edi
0x180099d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180099d12  lea     r13, WPP_17642f48579431367eaf2b8a741d67ec_Traceguids
0x180099d19  mov     dword ptr [rsp+0D0h+var_88], r14d; char
0x180099d1e  mov     r9d, ebx; int
0x180099d21  mov     [rsp+0D0h+var_90], r12; __int64
0x180099d26  mov     r8d, ebx; int
0x180099d29  mov     [rsp+0D0h+var_98], r13; LPCGUID
0x180099d2e  mov     edx, 30D0BD3h; int
0x180099d33  mov     rcx, [rcx+10h]; int
0x180099d37  mov     [rsp+0D0h+var_A0], 1Fh; __int16
0x180099d3e  mov     [rsp+0D0h+var_A8], esi; int
0x180099d42  mov     dword ptr [rsp+0D0h+pcbBytesNeeded], eax; int
0x180099d46  call    WPP_SF_Sd
0x180099d4b  jmp     loc_18009A636
0x180099d50  mov     r8d, 0F01FFh; dwDesiredAccess
0x180099d56  mov     rdx, r12; lpServiceName
0x180099d59  mov     rcx, r13; hSCManager
0x180099d5c  call    cs:__imp_OpenServiceW
0x180099d62  mov     r15, rax
0x180099d65  test    rax, rax
0x180099d68  jnz     loc_180099E69
0x180099d6e  call    cs:__imp_GetLastError
0x180099d74  mov     r14d, eax
0x180099d77  lea     ebx, [r15+3]
0x180099d7b  mov     ecx, ebx
0x180099d7d  call    IncrementWPPPerfCountersForLevel
0x180099d82  test    eax, eax
0x180099d84  jnz     short loc_180099DD7
0x180099d86  call    THStateCheckForTraceOverride
0x180099d8b  test    eax, eax
0x180099d8d  jnz     short loc_180099DD7
0x180099d8f  mov     r8d, ebx
0x180099d92  mov     edx, ebx
0x180099d94  xor     ecx, ecx
0x180099d96  call    CheckWPPLevelFlagsEnabledForProvider
0x180099d9b  test    eax, eax
0x180099d9d  jnz     short loc_180099DD7
0x180099d9f  mov     eax, cs:gfTraceToSecondProvider
0x180099da5  test    eax, eax
0x180099da7  jz      loc_18009A612
0x180099dad  call    THStateCheckForTraceOverride
0x180099db2  test    eax, eax
0x180099db4  jnz     short loc_180099DD7
0x180099db6  call    ThStateCheckIfTraceToSecondProvier
0x180099dbb  test    eax, eax
0x180099dbd  jz      loc_18009A612
0x180099dc3  mov     r8d, ebx
0x180099dc6  mov     edx, ebx
0x180099dc8  mov     ecx, edi
0x180099dca  call    CheckWPPLevelFlagsEnabledForProvider
0x180099dcf  test    eax, eax
0x180099dd1  jz      loc_18009A612
0x180099dd7  mov     eax, cs:gfTraceToSecondProvider
0x180099ddd  test    eax, eax
0x180099ddf  jz      short loc_180099E07
0x180099de1  call    THStateCheckForTraceOverride
0x180099de6  test    eax, eax
0x180099de8  jnz     short loc_180099E03
0x180099dea  call    ThStateCheckIfTraceToSecondProvier
0x180099def  test    eax, eax
0x180099df1  jz      short loc_180099E07
0x180099df3  mov     r8d, ebx
0x180099df6  mov     edx, ebx
0x180099df8  mov     ecx, edi
0x180099dfa  call    CheckWPPLevelFlagsEnabledForProvider
0x180099dff  test    eax, eax
0x180099e01  jz      short loc_180099E07
0x180099e03  mov     esi, edi
0x180099e05  jmp     short loc_180099E09
0x180099e07  xor     esi, esi
0x180099e09  call    THStateCheckForTraceOverride
0x180099e0e  test    eax, eax
0x180099e10  jnz     short loc_180099E22
0x180099e12  mov     r8d, ebx
0x180099e15  mov     edx, ebx
0x180099e17  xor     ecx, ecx
0x180099e19  call    CheckWPPLevelFlagsEnabledForProvider
0x180099e1e  test    eax, eax
0x180099e20  jz      short loc_180099E24
0x180099e22  mov     eax, edi
0x180099e24  mov     dword ptr [rsp+0D0h+var_88], r14d; char
0x180099e29  lea     rdx, WPP_17642f48579431367eaf2b8a741d67ec_Traceguids
0x180099e30  mov     [rsp+0D0h+var_90], r12; __int64
0x180099e35  mov     [rsp+0D0h+var_98], rdx; LPCGUID
0x180099e3a  mov     edx, 30D0BDFh; int
0x180099e3f  mov     [rsp+0D0h+var_A0], 20h ; ' '; __int16
0x180099e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180099e4d  mov     r9d, ebx; int
0x180099e50  mov     [rsp+0D0h+var_A8], esi; int
0x180099e54  mov     r8d, ebx; int
0x180099e57  mov     dword ptr [rsp+0D0h+pcbBytesNeeded], eax; int
0x180099e5b  mov     rcx, [rcx+10h]; int
0x180099e5f  call    WPP_SF_Sd
0x180099e64  jmp     loc_18009A612
0x180099e69  lea     rax, [rbp+57h+var_80]
0x180099e6d  mov     r9d, 24h ; '$'; cbBufSize
0x180099e73  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180099e77  mov     [rsp+0D0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180099e7c  xor     edx, edx; InfoLevel
0x180099e7e  mov     rcx, r15; hService
0x180099e81  call    cs:__imp_QueryServiceStatusEx
0x180099e87  test    eax, eax
0x180099e89  jnz     loc_180099F6D
0x180099e8f  call    cs:__imp_GetLastError
0x180099e95  mov     r14d, eax
0x180099e98  mov     ebx, 3
0x180099e9d  mov     ecx, ebx
0x180099e9f  call    IncrementWPPPerfCountersForLevel
0x180099ea4  test    eax, eax
0x180099ea6  jnz     short loc_180099EF9
0x180099ea8  call    THStateCheckForTraceOverride
0x180099ead  test    eax, eax
0x180099eaf  jnz     short loc_180099EF9
0x180099eb1  mov     r8d, ebx
0x180099eb4  mov     edx, ebx
0x180099eb6  xor     ecx, ecx
0x180099eb8  call    CheckWPPLevelFlagsEnabledForProvider
0x180099ebd  test    eax, eax
0x180099ebf  jnz     short loc_180099EF9
0x180099ec1  mov     eax, cs:gfTraceToSecondProvider
0x180099ec7  test    eax, eax
0x180099ec9  jz      loc_18009A612
0x180099ecf  call    THStateCheckForTraceOverride
0x180099ed4  test    eax, eax
0x180099ed6  jnz     short loc_180099EF9
0x180099ed8  call    ThStateCheckIfTraceToSecondProvier
0x180099edd  test    eax, eax
0x180099edf  jz      loc_18009A612
0x180099ee5  mov     r8d, ebx
0x180099ee8  mov     edx, ebx
0x180099eea  mov     ecx, edi
0x180099eec  call    CheckWPPLevelFlagsEnabledForProvider
0x180099ef1  test    eax, eax
0x180099ef3  jz      loc_18009A612
0x180099ef9  mov     eax, cs:gfTraceToSecondProvider
0x180099eff  test    eax, eax
0x180099f01  jz      short loc_180099F29
0x180099f03  call    THStateCheckForTraceOverride
0x180099f08  test    eax, eax
0x180099f0a  jnz     short loc_180099F25
0x180099f0c  call    ThStateCheckIfTraceToSecondProvier
0x180099f11  test    eax, eax
0x180099f13  jz      short loc_180099F29
0x180099f15  mov     r8d, ebx
0x180099f18  mov     edx, ebx
0x180099f1a  mov     ecx, edi
0x180099f1c  call    CheckWPPLevelFlagsEnabledForProvider
0x180099f21  test    eax, eax
0x180099f23  jz      short loc_180099F29
0x180099f25  mov     esi, edi
0x180099f27  jmp     short loc_180099F2B
0x180099f29  xor     esi, esi
0x180099f2b  call    THStateCheckForTraceOverride
0x180099f30  test    eax, eax
0x180099f32  jnz     short loc_180099F44
0x180099f34  mov     r8d, ebx
0x180099f37  mov     edx, ebx
0x180099f39  xor     ecx, ecx
0x180099f3b  call    CheckWPPLevelFlagsEnabledForProvider
0x180099f40  test    eax, eax
0x180099f42  jz      short loc_180099F46
0x180099f44  mov     eax, edi
0x180099f46  mov     dword ptr [rsp+0D0h+var_88], r14d
0x180099f4b  lea     rdx, WPP_17642f48579431367eaf2b8a741d67ec_Traceguids
0x180099f52  mov     [rsp+0D0h+var_90], r12
0x180099f57  mov     [rsp+0D0h+var_98], rdx
0x180099f5c  mov     edx, 30D0BEAh
0x180099f61  mov     [rsp+0D0h+var_A0], 21h ; '!'
0x180099f68  jmp     loc_180099E46
0x180099f6d  mov     eax, dword ptr [rbp+57h+Buffer+4]
0x180099f70  dec     eax
0x180099f72  test    eax, 0FFFFFFFDh
0x180099f77  jz      loc_18009A06B
0x180099f7d  xor     r14d, r14d
0x180099f80  call    THStateCheckForTraceOverride
0x180099f85  lea     ebx, [r14+3]
0x180099f89  test    eax, eax
0x180099f8b  jnz     short loc_180099FD7
0x180099f8d  mov     r8d, ebx
0x180099f90  lea     edx, [rbx+1]
0x180099f93  xor     ecx, ecx
0x180099f95  call    CheckWPPLevelFlagsEnabledForProvider
0x180099f9a  test    eax, eax
0x180099f9c  jnz     short loc_180099FD7
0x180099f9e  mov     eax, cs:gfTraceToSecondProvider
0x180099fa4  test    eax, eax
0x180099fa6  jz      loc_18009A612
0x180099fac  call    THStateCheckForTraceOverride
0x180099fb1  test    eax, eax
0x180099fb3  jnz     short loc_180099FD7
0x180099fb5  call    ThStateCheckIfTraceToSecondProvier
0x180099fba  test    eax, eax
0x180099fbc  jz      loc_18009A612
0x180099fc2  mov     r8d, ebx
0x180099fc5  lea     edx, [rbx+1]
0x180099fc8  mov     ecx, edi
0x180099fca  call    CheckWPPLevelFlagsEnabledForProvider
0x180099fcf  test    eax, eax
0x180099fd1  jz      loc_18009A612
0x180099fd7  mov     eax, cs:gfTraceToSecondProvider
0x180099fdd  test    eax, eax
0x180099fdf  jz      short loc_18009A00A
0x180099fe1  call    THStateCheckForTraceOverride
0x180099fe6  test    eax, eax
0x180099fe8  jnz     short loc_18009A006
0x180099fea  call    ThStateCheckIfTraceToSecondProvier
0x180099fef  test    eax, eax
0x180099ff1  jz      short loc_18009A00A
0x180099ff3  mov     r8d, ebx
0x180099ff6  mov     edx, 4
0x180099ffb  mov     ecx, edi
0x180099ffd  call    CheckWPPLevelFlagsEnabledForProvider
  ... truncated ...
```
