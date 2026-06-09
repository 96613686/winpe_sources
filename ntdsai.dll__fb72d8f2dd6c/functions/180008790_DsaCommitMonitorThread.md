# DsaCommitMonitorThread

- ea: `0x180008790`
- end: `0x180009369`
- name: `DsaCommitMonitorThread`
- size: `3033`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180008790`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x180017d1c`
- `0x18001e090`
- `0x180030af8`
- `0x180030b60`
- `0x18003ca38`
- `0x18003e2e0`
- `0x18047b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d39`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180008d65`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180008d65`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180008f9d`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180008f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008992`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008992`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fa6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008854`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800090e3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008854`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800090e3`
- `api-ms-win-core-psapi-l1-1-0!K32GetPerformanceInfo` at `0x18000882d`
- `api-ms-win-core-psapi-l1-1-0!K32GetPerformanceInfo` at `0x18000882d`
- `KERNEL32!Thread32Next` at `0x180008fb4`
- `KERNEL32!Thread32Next` at `0x180008fb4`
- `KERNEL32!Thread32First` at `0x180008ae8`
- `KERNEL32!Thread32First` at `0x180008ae8`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1800089ad`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1800089ad`

## pseudocode

```c
__int64 __fastcall DsaCommitMonitorThread(PVOID Parameter)
{
  SIZE_T v1; // rbx
  __int64 v2; // rcx
  void *v3; // rbp
  __int64 v4; // rdx
  __int64 v5; // rcx
  BOOL v6; // edi
  int v7; // eax
  HANDLE Toolhelp32Snapshot; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  BOOL v11; // esi
  BOOL v12; // edi
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  BOOL v16; // esi
  BOOL v17; // edi
  __int64 v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rcx
  BOOL v21; // ebx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  HANDLE v25; // rdi
  __int64 v26; // rdx
  __int64 v27; // rcx
  BOOL v28; // ebx
  BOOL v29; // ecx
  __int64 v30; // rdx
  __int64 v31; // rcx
  BOOL v32; // ebx
  BOOL v33; // ecx
  DWORD LastError; // edi
  __int64 v35; // rdx
  __int64 v36; // rcx
  BOOL v37; // ebx
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  BOOL v41; // ebx
  int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rcx
  BOOL v47; // ebx
  int v48; // eax
  THREADENTRY32 te; // [rsp+50h] [rbp-C8h] BYREF
  _PERFORMANCE_INFORMATION pPerformanceInformation; // [rsp+70h] [rbp-A8h] BYREF

  while ( 1 )
  {
    memset(&pPerformanceInformation, 0, sizeof(pPerformanceInformation));
    if ( eServiceShutdown )
      break;
    v1 = (unsigned int)dword_180527FA0;
    if ( (unsigned int)dword_180527FA0 >= 0x64
      && K32GetPerformanceInfo(&pPerformanceInformation, 0x68u)
      && 100 * pPerformanceInformation.CommitTotal / pPerformanceInformation.PhysicalTotal >= v1 )
    {
      v3 = 0;
      if ( (unsigned int)THStateCheckForTraceOverride(
                           v2,
                           100 * pPerformanceInformation.CommitTotal % pPerformanceInformation.PhysicalTotal)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v5, v4)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
      {
        v6 = gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v5, v4)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
        if ( (unsigned int)THStateCheckForTraceOverride(v5, v4)
          || (v7 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)) != 0 )
        {
          v7 = 1;
        }
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50470980,
          4,
          3,
          v7,
          v6,
          21,
          (__int64)&WPP_ba0c72d2232039fe186a7cc7ebf2a95c_Traceguids);
      }
      while ( 1 )
      {
        te.dwSize = 28;
        memset(&te.cntUsage, 0, 24);
        if ( v3 )
          CloseHandle(v3);
        if ( eServiceShutdown )
          break;
        Toolhelp32Snapshot = CreateToolhelp32Snapshot(4u, 0);
        v3 = Toolhelp32Snapshot;
        if ( Toolhelp32Snapshot == (HANDLE)-1LL )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v10, v9)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v10, v9)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
          {
            v11 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v10, v9)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
            v12 = (unsigned int)THStateCheckForTraceOverride(v10, v9)
               || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3);
            v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            GetLastError();
            WPP_SF__ATTRTYP_LOG_(
              v13,
              50471004,
              2,
              3,
              v12,
              v11,
              22,
              (__int64)&WPP_ba0c72d2232039fe186a7cc7ebf2a95c_Traceguids);
          }
        }
        else if ( Thread32First(Toolhelp32Snapshot, &te) )
        {
          if ( (unsigned int)SetPrivilege()
            && ((unsigned int)IncrementWPPPerfCountersForLevel(2)
             || (unsigned int)THStateCheckForTraceOverride(v20, v19)
             || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
             || gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v20, v19)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3))) )
          {
            v21 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v20, v19)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v20, v19)
              || (v22 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)) != 0 )
            {
              v22 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50471029,
              2,
              3,
              v22,
              v21,
              24,
              (__int64)&WPP_ba0c72d2232039fe186a7cc7ebf2a95c_Traceguids);
          }
          do
          {
            if ( te.th32ThreadID
              && te.th32ThreadID != GetCurrentThreadId()
              && te.th32OwnerProcessID == GetCurrentProcessId() )
            {
              v25 = OpenThread(2u, 0, te.th32ThreadID);
              if ( v25 )
              {
                if ( (unsigned int)THStateCheckForTraceOverride(v24, v23)
                  || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
                  || gfTraceToSecondProvider
                  && ((unsigned int)THStateCheckForTraceOverride(v31, v30)
                   || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                   && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
                {
                  v32 = gfTraceToSecondProvider
                     && ((unsigned int)THStateCheckForTraceOverride(v31, v30)
                      || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                      && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
                  v33 = (unsigned int)THStateCheckForTraceOverride(v31, v30)
                     || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3);
                  WPP_SF__ATTRTYP_LOG_(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    50471051,
                    4,
                    3,
                    v33,
                    v32,
                    26,
                    (__int64)&WPP_ba0c72d2232039fe186a7cc7ebf2a95c_Traceguids);
                }
                SuspendThread(v25);
                CloseHandle(v25);
              }
              else
              {
                GetLastError();
                if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                  || (unsigned int)THStateCheckForTraceOverride(v27, v26)
                  || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
                  || gfTraceToSecondProvider
                  && ((unsigned int)THStateCheckForTraceOverride(v27, v26)
                   || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                   && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
                {
                  v28 = gfTraceToSecondProvider
                     && ((unsigned int)THStateCheckForTraceOverride(v27, v26)
                      || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                      && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
                  v29 = (unsigned int)THStateCheckForTraceOverride(v27, v26)
                     || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3);
                  WPP_SF__ATTRTYP_LOG_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    50471045,
                    2,
                    3,
                    v29,
                    v28,
                    25,
                    (__int64)&WPP_ba0c72d2232039fe186a7cc7ebf2a95c_Traceguids);
                }
              }
            }
          }
          while ( Thread32Next(v3, &te) );
          LastError = GetLastError();
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v36, v35)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v36, v35)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
          {
            v37 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v36, v35)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v36, v35)
              || (v38 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)) != 0 )
            {
              v38 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50471064,
              2,
              3,
              v38,
              v37,
              27,
              (__int64)&WPP_ba0c72d2232039fe186a7cc7ebf2a95c_Traceguids);
          }
          if ( LastError == 18 )
          {
            if ( (unsigned int)THStateCheckForTraceOverride(v36, v35)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v40, v39)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
            {
              v41 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v40, v39)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
              if ( (unsigned int)THStateCheckForTraceOverride(v40, v39)
                || (v42 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)) != 0 )
              {
                v42 = 1;
              }
              WPP_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                50471076,
                4,
                3,
                v42,
                v41,
                28,
                &WPP_ba0c72d2232039fe186a7cc7ebf2a95c_Traceguids);
            }
            ((void (__fastcall *)(__int64))pFnJetConfigureProcessForCrashDump)(1);
            if ( (unsigned int)THStateCheckForTraceOverride(v44, v43)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v46, v45)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
            {
              v47 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v46, v45)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
              if ( (unsigned int)THStateCheckForTraceOverride(v46, v45)
                || (v48 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)) != 0 )
              {
                v48 = 1;
              }
              WPP_SF__ATTRTYP_LOG_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                50471083,
                4,
                3,
                v48,
                v47,
                29,
                (__int64)&WPP_ba0c72d2232039fe186a7cc7ebf2a95c_Traceguids);
            }
            RaiseDsaExcept(0xE0010009, 1);
            return 0;
          }
        }
        else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
               || (unsigned int)THStateCheckForTraceOverride(v15, v14)
               || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
               || gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v15, v14)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v16 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v15, v14)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
          v17 = (unsigned int)THStateCheckForTraceOverride(v15, v14)
             || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3);
          v18 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          GetLastError();
          WPP_SF__ATTRTYP_LOG_(
            v18,
            50471014,
            2,
            3,
            v17,
            v16,
            23,
            (__int64)&WPP_ba0c72d2232039fe186a7cc7ebf2a95c_Traceguids);
        }
        Sleep(0xC8u);
      }
      return 0;
    }
    Sleep(0xC8u);
  }
  return 0;
}

```

## disassembly

```asm
0x180008790  mov     r11, rsp
0x180008793  sub     rsp, 118h
0x18000879a  mov     rax, cs:__security_cookie
0x1800087a1  xor     rax, rsp
0x1800087a4  mov     [rsp+118h+var_38], rax
0x1800087ac  mov     [r11+8], rbx
0x1800087b0  mov     [r11+10h], rbp
0x1800087b4  mov     [r11+18h], rsi
0x1800087b8  mov     [r11-8], rdi
0x1800087bc  mov     [r11-10h], r12
0x1800087c0  mov     [r11-18h], r13
0x1800087c4  mov     [r11-20h], r14
0x1800087c8  mov     [r11-28h], r15
0x1800087cc  nop     dword ptr [rax+00h]
0x1800087d0  xorps   xmm0, xmm0
0x1800087d3  xor     eax, eax
0x1800087d5  mov     qword ptr [rsp+118h+pPerformanceInformation.ThreadCount], rax
0x1800087dd  mov     eax, cs:eServiceShutdown
0x1800087e3  movups  xmmword ptr [rsp+118h+pPerformanceInformation.cb], xmm0
0x1800087e8  movups  xmmword ptr [rsp+118h+pPerformanceInformation.CommitLimit], xmm0
0x1800087f0  movups  xmmword ptr [rsp+118h+pPerformanceInformation.PhysicalTotal], xmm0
0x1800087f8  movups  xmmword ptr [rsp+118h+pPerformanceInformation.SystemCache], xmm0
0x180008800  movups  xmmword ptr [rsp+118h+pPerformanceInformation.KernelPaged], xmm0
0x180008808  movups  xmmword ptr [rsp+118h+pPerformanceInformation.PageSize], xmm0
0x180008810  test    eax, eax
0x180008812  jnz     loc_18000930F
0x180008818  mov     ebx, cs:dword_180527FA0
0x18000881e  cmp     ebx, 64h ; 'd'
0x180008821  jb      short loc_18000884F
0x180008823  mov     edx, 68h ; 'h'; cb
0x180008828  lea     rcx, [rsp+118h+pPerformanceInformation]; pPerformanceInformation
0x18000882d  call    cs:__imp_K32GetPerformanceInfo
0x180008833  test    eax, eax
0x180008835  jz      short loc_18000884F
0x180008837  imul    rax, [rsp+118h+pPerformanceInformation.CommitTotal], 64h ; 'd'
0x18000883d  xor     edx, edx
0x18000883f  div     [rsp+118h+pPerformanceInformation.PhysicalTotal]
0x180008847  mov     rsi, rax
0x18000884a  cmp     rax, rbx
0x18000884d  jnb     short loc_18000885F
0x18000884f  mov     ecx, 0C8h; dwMilliseconds
0x180008854  call    cs:__imp_Sleep
0x18000885a  jmp     loc_1800087D0
0x18000885f  xor     ebp, ebp
0x180008861  call    THStateCheckForTraceOverride
0x180008866  lea     r14, WPP_ba0c72d2232039fe186a7cc7ebf2a95c_Traceguids
0x18000886d  test    eax, eax
0x18000886f  jnz     short loc_1800088C8
0x180008871  mov     edx, 4
0x180008876  xor     ecx, ecx
0x180008878  mov     r8d, 3
0x18000887e  call    CheckWPPLevelFlagsEnabledForProvider
0x180008883  test    eax, eax
0x180008885  jnz     short loc_1800088C8
0x180008887  mov     eax, cs:gfTraceToSecondProvider
0x18000888d  test    eax, eax
0x18000888f  jz      loc_180008968
0x180008895  call    THStateCheckForTraceOverride
0x18000889a  test    eax, eax
0x18000889c  jnz     short loc_1800088C8
0x18000889e  call    ThStateCheckIfTraceToSecondProvier
0x1800088a3  test    eax, eax
0x1800088a5  jz      loc_180008968
0x1800088ab  mov     edx, 4
0x1800088b0  mov     ecx, 1
0x1800088b5  mov     r8d, 3
0x1800088bb  call    CheckWPPLevelFlagsEnabledForProvider
0x1800088c0  test    eax, eax
0x1800088c2  jz      loc_180008968
0x1800088c8  mov     eax, cs:gfTraceToSecondProvider
0x1800088ce  test    eax, eax
0x1800088d0  jz      short loc_180008904
0x1800088d2  call    THStateCheckForTraceOverride
0x1800088d7  test    eax, eax
0x1800088d9  jnz     short loc_1800088FD
0x1800088db  call    ThStateCheckIfTraceToSecondProvier
0x1800088e0  test    eax, eax
0x1800088e2  jz      short loc_180008904
0x1800088e4  mov     edx, 4
0x1800088e9  mov     ecx, 1
0x1800088ee  mov     r8d, 3
0x1800088f4  call    CheckWPPLevelFlagsEnabledForProvider
0x1800088f9  test    eax, eax
0x1800088fb  jz      short loc_180008904
0x1800088fd  mov     edi, 1
0x180008902  jmp     short loc_180008906
0x180008904  xor     edi, edi
0x180008906  call    THStateCheckForTraceOverride
0x18000890b  test    eax, eax
0x18000890d  jnz     short loc_180008925
0x18000890f  mov     edx, 4
0x180008914  xor     ecx, ecx
0x180008916  mov     r8d, 3
0x18000891c  call    CheckWPPLevelFlagsEnabledForProvider
0x180008921  test    eax, eax
0x180008923  jz      short loc_18000892A
0x180008925  mov     eax, 1
0x18000892a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008931  mov     edx, 3022044h
0x180008936  mov     [rsp+118h+var_D0], ebx
0x18000893a  mov     r9d, 3
0x180008940  mov     [rsp+118h+var_D8], rsi
0x180008945  mov     r8d, 4
0x18000894b  mov     [rsp+118h+var_E0], r14
0x180008950  mov     rcx, [rcx+10h]
0x180008954  mov     [rsp+118h+var_E8], 15h
0x18000895b  mov     [rsp+118h+var_F0], edi
0x18000895f  mov     [rsp+118h+var_F8], eax
0x180008963  call    WPP_SF_qD
0x180008968  mov     esi, 19h
0x18000896d  mov     r15d, 1Ch
0x180008973  mov     qword ptr [rsp+118h+te.tpDeltaPri], 0
0x18000897c  xorps   xmm0, xmm0
0x18000897f  mov     [rsp+118h+te.dwSize], r15d
0x180008984  movdqu  xmmword ptr [rsp+118h+te.cntUsage], xmm0
0x18000898a  test    rbp, rbp
0x18000898d  jz      short loc_180008998
0x18000898f  mov     rcx, rbp; hObject
0x180008992  call    cs:__imp_CloseHandle
0x180008998  mov     eax, cs:eServiceShutdown
0x18000899e  test    eax, eax
0x1800089a0  jnz     loc_18000930F
0x1800089a6  xor     edx, edx; th32ProcessID
0x1800089a8  mov     ecx, 4; dwFlags
0x1800089ad  call    cs:__imp_CreateToolhelp32Snapshot
0x1800089b3  mov     rbp, rax
0x1800089b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800089ba  jnz     loc_180008AE0
0x1800089c0  mov     ecx, 2
0x1800089c5  call    IncrementWPPPerfCountersForLevel
0x1800089ca  test    eax, eax
0x1800089cc  jnz     short loc_180008A2E
0x1800089ce  call    THStateCheckForTraceOverride
0x1800089d3  test    eax, eax
0x1800089d5  jnz     short loc_180008A2E
0x1800089d7  mov     edx, 2
0x1800089dc  xor     ecx, ecx
0x1800089de  mov     r8d, 3
0x1800089e4  call    CheckWPPLevelFlagsEnabledForProvider
0x1800089e9  test    eax, eax
0x1800089eb  jnz     short loc_180008A2E
0x1800089ed  mov     eax, cs:gfTraceToSecondProvider
0x1800089f3  test    eax, eax
0x1800089f5  jz      loc_1800090DE
0x1800089fb  call    THStateCheckForTraceOverride
0x180008a00  test    eax, eax
0x180008a02  jnz     short loc_180008A2E
0x180008a04  call    ThStateCheckIfTraceToSecondProvier
0x180008a09  test    eax, eax
0x180008a0b  jz      loc_1800090DE
0x180008a11  mov     edx, 2
0x180008a16  mov     ecx, 1
0x180008a1b  mov     r8d, 3
0x180008a21  call    CheckWPPLevelFlagsEnabledForProvider
0x180008a26  test    eax, eax
0x180008a28  jz      loc_1800090DE
0x180008a2e  mov     eax, cs:gfTraceToSecondProvider
0x180008a34  test    eax, eax
0x180008a36  jz      short loc_180008A6A
0x180008a38  call    THStateCheckForTraceOverride
0x180008a3d  test    eax, eax
0x180008a3f  jnz     short loc_180008A63
0x180008a41  call    ThStateCheckIfTraceToSecondProvier
0x180008a46  test    eax, eax
0x180008a48  jz      short loc_180008A6A
0x180008a4a  mov     edx, 2
0x180008a4f  mov     ecx, 1
0x180008a54  mov     r8d, 3
0x180008a5a  call    CheckWPPLevelFlagsEnabledForProvider
0x180008a5f  test    eax, eax
0x180008a61  jz      short loc_180008A6A
0x180008a63  mov     esi, 1
0x180008a68  jmp     short loc_180008A6C
0x180008a6a  xor     esi, esi
0x180008a6c  call    THStateCheckForTraceOverride
0x180008a71  test    eax, eax
0x180008a73  jnz     short loc_180008A8F
0x180008a75  mov     edx, 2
0x180008a7a  xor     ecx, ecx
0x180008a7c  mov     r8d, 3
0x180008a82  call    CheckWPPLevelFlagsEnabledForProvider
0x180008a87  test    eax, eax
0x180008a89  jnz     short loc_180008A8F
0x180008a8b  xor     edi, edi
0x180008a8d  jmp     short loc_180008A94
0x180008a8f  mov     edi, 1
0x180008a94  mov     rax, cs:WPP_GLOBAL_Control
0x180008a9b  mov     rbx, [rax+10h]
0x180008a9f  call    cs:__imp_GetLastError
0x180008aa5  mov     dword ptr [rsp+118h+var_D8], eax
0x180008aa9  mov     edx, 302205Ch
0x180008aae  mov     [rsp+118h+var_E0], r14
0x180008ab3  mov     r9d, 3
0x180008ab9  mov     [rsp+118h+var_E8], 16h
0x180008ac0  mov     r8d, 2
0x180008ac6  mov     [rsp+118h+var_F0], esi
0x180008aca  mov     rcx, rbx
0x180008acd  mov     [rsp+118h+var_F8], edi
0x180008ad1  call    WPP_SF__ATTRTYP_LOG_
0x180008ad6  mov     esi, 19h
0x180008adb  jmp     loc_1800090DE
0x180008ae0  lea     rdx, [rsp+118h+te]; lpte
0x180008ae5  mov     rcx, rbp; hSnapshot
0x180008ae8  call    cs:__imp_Thread32First
0x180008aee  test    eax, eax
0x180008af0  jnz     loc_180008C16
0x180008af6  mov     ecx, 2
0x180008afb  call    IncrementWPPPerfCountersForLevel
0x180008b00  test    eax, eax
0x180008b02  jnz     short loc_180008B64
0x180008b04  call    THStateCheckForTraceOverride
0x180008b09  test    eax, eax
0x180008b0b  jnz     short loc_180008B64
0x180008b0d  mov     edx, 2
0x180008b12  xor     ecx, ecx
0x180008b14  mov     r8d, 3
0x180008b1a  call    CheckWPPLevelFlagsEnabledForProvider
0x180008b1f  test    eax, eax
0x180008b21  jnz     short loc_180008B64
0x180008b23  mov     eax, cs:gfTraceToSecondProvider
0x180008b29  test    eax, eax
0x180008b2b  jz      loc_1800090DE
0x180008b31  call    THStateCheckForTraceOverride
0x180008b36  test    eax, eax
0x180008b38  jnz     short loc_180008B64
0x180008b3a  call    ThStateCheckIfTraceToSecondProvier
0x180008b3f  test    eax, eax
0x180008b41  jz      loc_1800090DE
0x180008b47  mov     edx, 2
0x180008b4c  mov     ecx, 1
0x180008b51  mov     r8d, 3
0x180008b57  call    CheckWPPLevelFlagsEnabledForProvider
0x180008b5c  test    eax, eax
0x180008b5e  jz      loc_1800090DE
0x180008b64  mov     eax, cs:gfTraceToSecondProvider
0x180008b6a  test    eax, eax
0x180008b6c  jz      short loc_180008BA0
0x180008b6e  call    THStateCheckForTraceOverride
0x180008b73  test    eax, eax
0x180008b75  jnz     short loc_180008B99
0x180008b77  call    ThStateCheckIfTraceToSecondProvier
0x180008b7c  test    eax, eax
0x180008b7e  jz      short loc_180008BA0
0x180008b80  mov     edx, 2
0x180008b85  mov     ecx, 1
0x180008b8a  mov     r8d, 3
0x180008b90  call    CheckWPPLevelFlagsEnabledForProvider
0x180008b95  test    eax, eax
0x180008b97  jz      short loc_180008BA0
0x180008b99  mov     esi, 1
0x180008b9e  jmp     short loc_180008BA2
0x180008ba0  xor     esi, esi
0x180008ba2  call    THStateCheckForTraceOverride
0x180008ba7  test    eax, eax
0x180008ba9  jnz     short loc_180008BC5
0x180008bab  mov     edx, 2
0x180008bb0  xor     ecx, ecx
0x180008bb2  mov     r8d, 3
0x180008bb8  call    CheckWPPLevelFlagsEnabledForProvider
0x180008bbd  test    eax, eax
0x180008bbf  jnz     short loc_180008BC5
0x180008bc1  xor     edi, edi
0x180008bc3  jmp     short loc_180008BCA
0x180008bc5  mov     edi, 1
0x180008bca  mov     rax, cs:WPP_GLOBAL_Control
0x180008bd1  mov     rbx, [rax+10h]
0x180008bd5  call    cs:__imp_GetLastError
0x180008bdb  mov     dword ptr [rsp+118h+var_D8], eax
0x180008bdf  mov     edx, 3022066h
0x180008be4  mov     [rsp+118h+var_E0], r14
0x180008be9  mov     r9d, 3
0x180008bef  mov     [rsp+118h+var_E8], 17h
0x180008bf6  mov     r8d, 2
0x180008bfc  mov     [rsp+118h+var_F0], esi
0x180008c00  mov     rcx, rbx
0x180008c03  mov     [rsp+118h+var_F8], edi
0x180008c07  call    WPP_SF__ATTRTYP_LOG_
0x180008c0c  mov     esi, 19h
0x180008c11  jmp     loc_1800090DE
0x180008c16  call    SetPrivilege
0x180008c1b  mov     edi, eax
0x180008c1d  test    eax, eax
0x180008c1f  jz      loc_180008D2E
0x180008c25  mov     ecx, 2
0x180008c2a  call    IncrementWPPPerfCountersForLevel
0x180008c2f  test    eax, eax
0x180008c31  jnz     short loc_180008C93
0x180008c33  call    THStateCheckForTraceOverride
0x180008c38  test    eax, eax
0x180008c3a  jnz     short loc_180008C93
0x180008c3c  mov     edx, 2
0x180008c41  xor     ecx, ecx
0x180008c43  mov     r8d, 3
0x180008c49  call    CheckWPPLevelFlagsEnabledForProvider
0x180008c4e  test    eax, eax
0x180008c50  jnz     short loc_180008C93
0x180008c52  mov     eax, cs:gfTraceToSecondProvider
0x180008c58  test    eax, eax
0x180008c5a  jz      loc_180008D2E
0x180008c60  call    THStateCheckForTraceOverride
  ... truncated ...
```
