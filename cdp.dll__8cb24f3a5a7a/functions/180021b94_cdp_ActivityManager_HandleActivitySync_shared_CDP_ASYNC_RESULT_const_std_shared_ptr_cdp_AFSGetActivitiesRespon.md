# cdp::ActivityManager::HandleActivitySync(shared::CDP_ASYNC_RESULT const &,std::shared_ptr<cdp::AFSGetActivitiesResponse> const &)

- ea: `0x180021b94`
- end: `0x180021f27`
- name: `?HandleActivitySync@ActivityManager@cdp@@AEAAXAEBUCDP_ASYNC_RESULT@shared@@AEBV?$shared_ptr@UAFSGetActivitiesResponse@cdp@@@std@@@Z`
- size: `915`
- prototype: `__int64 __fastcall(cdp::ActivityManager *this)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1802f3510`

## callees

- `0x180010ee0`
- `0x1800110f8`
- `0x180021b94`
- `0x180021f30`
- `0x180030190`
- `0x18004bac4`
- `0x18004e170`
- `0x18008dbc0`
- `0x18008e88c`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800fdedc`
- `0x180143248`
- `0x180145cb8`
- `0x1801990c0`
- `0x18019fe3c`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021cac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021d61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021cac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021d61`
- `msvcp_win!_Mtx_unlock` at `0x180021c6d`
- `msvcp_win!_Mtx_unlock` at `0x180021c6d`

## string_xrefs

- `0x180021cdd`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180021d92`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall cdp::ActivityManager::HandleActivitySync(
        cdp::ActivityManager *this,
        __int64 a2,
        const struct cdp::AFSRequestedAction **a3)
{
  const struct cdp::AFSRequestedAction *v5; // r8
  _BYTE *v6; // r8
  unsigned __int8 v7; // al
  int v8; // eax
  int v9; // esi
  int v10; // ecx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rdi
  void (__fastcall *v21)(__int64, const char **, int *, _QWORD, int, _QWORD *, const char *, _QWORD, _QWORD); // rsi
  _QWORD *v22; // rbx
  cdp::ActivityManager **v24; // rax
  _BYTE v25[32]; // [rsp+0h] [rbp-158h] BYREF
  int v26; // [rsp+50h] [rbp-108h] BYREF
  cdp::ActivityManager **CurrentThreadId; // [rsp+58h] [rbp-100h] BYREF
  int v28; // [rsp+60h] [rbp-F8h]
  cdp::ActivityManager **v29; // [rsp+68h] [rbp-F0h] BYREF
  cdp::ActivityManager *v30; // [rsp+70h] [rbp-E8h] BYREF
  cdp::ActivityManager *v31; // [rsp+78h] [rbp-E0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-D8h] BYREF
  _BYTE v33[56]; // [rsp+B8h] [rbp-A0h] BYREF
  const char *v34; // [rsp+F0h] [rbp-68h] BYREF
  _DWORD v35[6]; // [rsp+F8h] [rbp-60h] BYREF
  _QWORD v36[4]; // [rsp+110h] [rbp-48h] BYREF

  try
  {
    v28 = 0;
    v30 = this;
    v29 = &v30;
    v5 = *a3;
    if ( *(_BYTE *)v5 )
    {
      v31 = this;
      CurrentThreadId = &v31;
      cdp::ActivityManager::HandleAFSRequestedAction(this, v5);
      if ( (unsigned __int8)(*(_BYTE *)*a3 - 1) <= 2u )
      {
        v34 = (char *)this + 296;
        std::_Mutex_base::lock((cdp::ActivityManager *)((char *)this + 296));
        v6 = (char *)this + 632;
        v7 = *((_BYTE *)this + 632);
        if ( v7 <= 1u )
        {
          v8 = (unsigned __int8)(v7 + 1);
          *v6 = v8;
          v26 = v8 - 1;
          Log<unsigned char &,int>(
            3,
            "{\"text\":\"Incrementing _pendingActivitiesSyncCount, as AFS requested retry. Now %hhu, was %hhu.\"}",
            (_DWORD)v6,
            (unsigned int)&v26);
          if ( *(_BYTE *)*a3 == 1 )
          {
            Log<>(3, "{\"text\":\"Scheduling syncing activities with AFS (retry immediate).\"}");
            cdp::ActivityManager::ScheduleCheckForWorkWithLockHeld(this);
          }
        }
        _Mtx_unlock((cdp::ActivityManager *)((char *)this + 296));
      }
      ScopeWarden__lambda_8a457bee76c05b0966766cfe6344a420___::_ScopeWarden__lambda_8a457bee76c05b0966766cfe6344a420___(&CurrentThreadId);
    }
    else
    {
      v9 = *(_DWORD *)(a2 + 4);
      if ( v9 < 0 )
      {
        v34 = "..\\activitymanager.cpp";
        v35[0] = 3922;
        v26 = v9;
        CurrentThreadId = (cdp::ActivityManager **)GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v10,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v26,
          (unsigned int)&v34,
          (__int64)v35,
          (__int64)&CurrentThreadId);
        v11 = cdp::ExceptionStackFromSourceLocationInfo(v36, &v34);
        v14 = cdp::ErrorCodeToString((unsigned int)v9, v12, v13, v11);
        ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v9, v14);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      if ( !*((_QWORD *)v5 + 10) )
      {
        v34 = "..\\activitymanager.cpp";
        v35[0] = 3923;
        v26 = -2147418113;
        CurrentThreadId = (cdp::ActivityManager **)GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v15,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v26,
          (unsigned int)&v34,
          (__int64)v35,
          (__int64)&CurrentThreadId);
        v16 = cdp::ExceptionStackFromSourceLocationInfo(v36, &v34);
        v19 = cdp::ErrorCodeToString(2147549183LL, v17, v18, v16);
        ConnectedDevices::Exception::Exception(v33, 2147549183LL, v19);
        throw (ConnectedDevices::Exception *)v33;
      }
      cdp::ActivityManager::FinalizeSync(this, (__int64)v5 + 128);
      if ( *((_BYTE *)*a3 + 120) && *((_QWORD *)*a3 + 12) != *((_QWORD *)*a3 + 13) )
      {
        std::string::string(
          v36,
          "Previous request did timeout, with partial sync. Schedule another sync for rest of the activities");
        Log<std::string const &>(4, "{\"text\":\"%s\"}", (const char *)v36);
        cdp::ActivityManager::EnqueueSyncActivitiesRequest(this, 0);
        v20 = *((_QWORD *)this + 60);
        v21 = *(void (__fastcall **)(__int64, const char **, int *, _QWORD, int, _QWORD *, const char *, _QWORD, _QWORD))(*(_QWORD *)v20 + 64LL);
        v22 = v36;
        if ( v36[3] > 0xFu )
          v22 = (_QWORD *)v36[0];
        v26 = 0;
        std::string::string(&v34, "ActivityStore.DeltaSync");
        v21(v20, &v34, &v26, 0, 1, v22, qword_1803986E0, 0, 0);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v34);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v36);
      }
    }
    v29 = 0;
  }
  catch ( ... )
  {
    LODWORD(v24) = GetCurrentThreadId();
    CurrentThreadId = v24;
    v26 = 3943;
    cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
      (unsigned int)v25 + 96,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\""
                    ":\"Failed during HandleActivitySync\"}",
      (unsigned int)"..\\activitymanager.cpp",
      (unsigned int)v25 + 80,
      (__int64)&CurrentThreadId);
  }
  return ScopeWarden__lambda_b4a033d32d0d67d1cd680f47143c3028___::_ScopeWarden__lambda_b4a033d32d0d67d1cd680f47143c3028___(&v29);
}

```

## disassembly

```asm
0x180021b94  push    rbx
0x180021b96  push    rsi
0x180021b97  push    rdi
0x180021b98  sub     rsp, 140h
0x180021b9f  mov     rax, cs:__security_cookie
0x180021ba6  xor     rax, rsp
0x180021ba9  mov     [rsp+158h+var_28], rax
0x180021bb1  mov     rdi, r8
0x180021bb4  mov     rbx, rcx
0x180021bb7  mov     [rsp+158h+var_F8], 0
0x180021bbf  mov     [rsp+158h+var_E8], rcx
0x180021bc4  lea     rax, [rsp+158h+var_E8]
0x180021bc9  mov     [rsp+158h+var_F0], rax
0x180021bce  mov     r8, [r8]
0x180021bd1  cmp     byte ptr [r8], 0
0x180021bd5  jz      loc_180021C83
0x180021bdb  mov     [rsp+158h+var_E0], rcx
0x180021be0  lea     rax, [rsp+158h+var_E0]
0x180021be5  mov     [rsp+158h+var_100], rax
0x180021bea  mov     rdx, r8; struct cdp::AFSRequestedAction *
0x180021bed  call    ?HandleAFSRequestedAction@ActivityManager@cdp@@AEAAXAEBUAFSRequestedAction@2@@Z; cdp::ActivityManager::HandleAFSRequestedAction(cdp::AFSRequestedAction const &)
0x180021bf2  mov     rax, [rdi]
0x180021bf5  mov     cl, [rax]
0x180021bf7  dec     cl
0x180021bf9  cmp     cl, 2
0x180021bfc  ja      short loc_180021C74
0x180021bfe  lea     rsi, [rbx+128h]
0x180021c05  mov     [rsp+158h+var_68], rsi
0x180021c0d  mov     rcx, rsi; this
0x180021c10  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180021c15  nop
0x180021c16  lea     r8, [rbx+278h]
0x180021c1d  mov     al, [r8]
0x180021c20  cmp     al, 1
0x180021c22  ja      short loc_180021C6A
0x180021c24  inc     al
0x180021c26  movzx   eax, al
0x180021c29  mov     [r8], al
0x180021c2c  dec     eax
0x180021c2e  mov     [rsp+158h+var_108], eax
0x180021c32  lea     r9, [rsp+158h+var_108]
0x180021c37  lea     rdx, aTextIncrementi; "{\"text\":\"Incrementing _pendingActivi"...
0x180021c3e  mov     ecx, 3
0x180021c43  call    ??$Log@AEAEH@@YAXW4CDPLogLevel@@PEBDAEAE$$QEAH@Z; Log<uchar &,int>(CDPLogLevel,char const *,uchar &,int &&)
0x180021c48  mov     rax, [rdi]
0x180021c4b  cmp     byte ptr [rax], 1
0x180021c4e  jnz     short loc_180021C6A
0x180021c50  lea     rdx, aTextScheduling_7; "{\"text\":\"Scheduling syncing activiti"...
0x180021c57  mov     ecx, 3
0x180021c5c  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180021c61  mov     rcx, rbx; this
0x180021c64  call    ?ScheduleCheckForWorkWithLockHeld@ActivityManager@cdp@@AEAAXXZ; cdp::ActivityManager::ScheduleCheckForWorkWithLockHeld(void)
0x180021c69  nop
0x180021c6a  mov     rcx, rsi; _Mtx_t
0x180021c6d  call    cs:__imp__Mtx_unlock
0x180021c73  nop
0x180021c74  lea     rcx, [rsp+158h+var_100]
0x180021c79  call    ScopeWarden__lambda_8a457bee76c05b0966766cfe6344a420______ScopeWarden__lambda_8a457bee76c05b0966766cfe6344a420___
0x180021c7e  jmp     loc_180021EF7
0x180021c83  mov     esi, [rdx+4]
0x180021c86  test    esi, esi
0x180021c88  jns     loc_180021D2F
0x180021c8e  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x180021c95  mov     [rsp+158h+var_68], rax
0x180021c9d  mov     [rsp+158h+var_60], 0F52h
0x180021ca8  mov     [rsp+158h+var_108], esi
0x180021cac  call    cs:__imp_GetCurrentThreadId
0x180021cb2  mov     eax, eax
0x180021cb4  mov     [rsp+158h+var_100], rax
0x180021cb9  lea     rax, [rsp+158h+var_100]
0x180021cbe  mov     [rsp+158h+var_130], rax
0x180021cc3  lea     rax, [rsp+158h+var_60]
0x180021ccb  mov     [rsp+158h+var_138], rax
0x180021cd0  lea     r9, [rsp+158h+var_68]
0x180021cd8  lea     r8, [rsp+158h+var_108]
0x180021cdd  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180021ce4  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180021ce9  lea     rdx, [rsp+158h+var_68]
0x180021cf1  lea     rcx, [rsp+158h+var_48]
0x180021cf9  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180021cfe  mov     r9, rax
0x180021d01  mov     ecx, esi
0x180021d03  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180021d08  mov     r8, rax
0x180021d0b  mov     edx, esi
0x180021d0d  lea     rcx, [rsp+158h+pExceptionObject]
0x180021d15  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180021d1a  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180021d21  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180021d29  call    _CxxThrowException_0
0x180021d2f  lea     rdx, [r8+40h]
0x180021d33  cmp     qword ptr [rdx+10h], 0
0x180021d38  jnz     loc_180021DE4
0x180021d3e  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x180021d45  mov     [rsp+158h+var_68], rax
0x180021d4d  mov     [rsp+158h+var_60], 0F53h
0x180021d58  mov     ebx, 8000FFFFh
0x180021d5d  mov     [rsp+158h+var_108], ebx
0x180021d61  call    cs:__imp_GetCurrentThreadId
0x180021d67  mov     eax, eax
0x180021d69  mov     [rsp+158h+var_100], rax
0x180021d6e  lea     rax, [rsp+158h+var_100]
0x180021d73  mov     [rsp+158h+var_130], rax
0x180021d78  lea     rax, [rsp+158h+var_60]
0x180021d80  mov     [rsp+158h+var_138], rax
0x180021d85  lea     r9, [rsp+158h+var_68]
0x180021d8d  lea     r8, [rsp+158h+var_108]
0x180021d92  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180021d99  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180021d9e  lea     rdx, [rsp+158h+var_68]
0x180021da6  lea     rcx, [rsp+158h+var_48]
0x180021dae  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180021db3  mov     r9, rax
0x180021db6  mov     ecx, ebx
0x180021db8  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180021dbd  mov     r8, rax
0x180021dc0  mov     edx, ebx
0x180021dc2  lea     rcx, [rsp+158h+var_A0]
0x180021dca  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180021dcf  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180021dd6  lea     rcx, [rsp+158h+var_A0]; pExceptionObject
0x180021dde  call    _CxxThrowException_0
0x180021de4  lea     rax, [r8+80h]
0x180021deb  lea     r9, [r8+60h]
0x180021def  mov     [rsp+158h+var_138], rax; __int64
0x180021df4  mov     r8b, [r8+79h]
0x180021df8  call    ?FinalizeSync@ActivityManager@cdp@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N$$QEAV?$vector@UActivityData@shared@@V?$allocator@UActivityData@shared@@@std@@@4@0@Z; cdp::ActivityManager::FinalizeSync(std::string const &,bool,std::vector<shared::ActivityData> &&,std::string const &)
0x180021dfd  mov     rcx, [rdi]
0x180021e00  cmp     byte ptr [rcx+78h], 0
0x180021e04  jz      loc_180021EF7
0x180021e0a  mov     rax, [rcx+68h]
0x180021e0e  cmp     [rcx+60h], rax
0x180021e12  jz      loc_180021EF7
0x180021e18  lea     rdx, aPreviousReques; "Previous request did timeout, with part"...
0x180021e1f  lea     rcx, [rsp+158h+var_48]
0x180021e27  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180021e2c  nop
0x180021e2d  lea     r8, [rsp+158h+var_48]
0x180021e35  lea     rdx, aTextS; "{\"text\":\"%s\"}"
0x180021e3c  mov     ecx, 4
0x180021e41  call    ??$Log@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@@YAXW4CDPLogLevel@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Log<std::string const &>(CDPLogLevel,char const *,std::string const &)
0x180021e46  xor     edx, edx; bool
0x180021e48  mov     rcx, rbx; this
0x180021e4b  call    ?EnqueueSyncActivitiesRequest@ActivityManager@cdp@@QEAAX_N@Z; cdp::ActivityManager::EnqueueSyncActivitiesRequest(bool)
0x180021e50  mov     rdi, [rbx+1E0h]
0x180021e57  mov     rax, [rdi]
0x180021e5a  mov     rsi, [rax+40h]
0x180021e5e  lea     rbx, [rsp+158h+var_48]
0x180021e66  cmp     [rsp+158h+var_30], 0Fh
0x180021e6f  cmova   rbx, [rsp+158h+var_48]
0x180021e78  mov     [rsp+158h+var_108], 0
0x180021e80  lea     rdx, ?ActivityStoreDeltaSync@MetricsIdentifier@shared@@2QBDB; "ActivityStore.DeltaSync"
0x180021e87  lea     rcx, [rsp+158h+var_68]
0x180021e8f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180021e94  nop
0x180021e95  mov     [rsp+158h+var_118], 0
0x180021e9e  mov     [rsp+158h+var_120], 0
0x180021ea7  lea     rax, qword_1803986E0
0x180021eae  mov     [rsp+158h+var_128], rax
0x180021eb3  mov     [rsp+158h+var_130], rbx
0x180021eb8  mov     dword ptr [rsp+158h+var_138], 1
0x180021ec0  xor     r9d, r9d
0x180021ec3  lea     r8, [rsp+158h+var_108]
0x180021ec8  lea     rdx, [rsp+158h+var_68]
0x180021ed0  mov     rcx, rdi
0x180021ed3  mov     rax, rsi
0x180021ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021edb  nop
0x180021edc  lea     rcx, [rsp+158h+var_68]; void *
0x180021ee4  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180021ee9  nop
0x180021eea  lea     rcx, [rsp+158h+var_48]; void *
0x180021ef2  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180021ef7  mov     [rsp+158h+var_F0], 0
0x180021f00  jmp     short $+2
0x180021f02  lea     rcx, [rsp+158h+var_F0]
0x180021f07  call    ScopeWarden__lambda_b4a033d32d0d67d1cd680f47143c3028______ScopeWarden__lambda_b4a033d32d0d67d1cd680f47143c3028___
0x180021f0c  mov     rcx, [rsp+158h+var_28]
0x180021f14  xor     rcx, rsp; StackCookie
0x180021f17  call    __security_check_cookie
0x180021f1c  add     rsp, 140h
0x180021f23  pop     rdi
0x180021f24  pop     rsi
0x180021f25  pop     rbx
0x180021f26  retn
```
