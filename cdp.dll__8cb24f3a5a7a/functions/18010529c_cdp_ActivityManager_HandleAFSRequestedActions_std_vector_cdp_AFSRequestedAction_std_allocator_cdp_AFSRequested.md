# cdp::ActivityManager::HandleAFSRequestedActions(std::vector<cdp::AFSRequestedAction,std::allocator<cdp::AFSRequestedAction>> const &)

- ea: `0x18010529c`
- end: `0x180105582`
- name: `?HandleAFSRequestedActions@ActivityManager@cdp@@AEAAXAEBV?$vector@UAFSRequestedAction@cdp@@V?$allocator@UAFSRequestedAction@cdp@@@std@@@std@@@Z`
- size: `742`
- prototype: `__int64 __fastcall(cdp::ActivityManager *this)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800738a0`
- `0x180145cb8`

## callees

- `0x1800110f8`
- `0x18001ee70`
- `0x180042f74`
- `0x18008dbc0`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800f6608`
- `0x1800fa708`
- `0x18010529c`
- `0x180143248`
- `0x1801bb95c`
- `0x1801bba90`
- `0x1801e6484`
- `0x1801fcb36`
- `0x1802f1118`
- `0x1802f2440`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010547d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801054ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010547d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801054ff`
- `msvcp_win!_Mtx_unlock` at `0x1801053a6`
- `msvcp_win!_Mtx_unlock` at `0x1801053a6`

## string_xrefs

- `0x1801054a3`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180105525`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18010537b`: `{"text":"ActivityManager - Configuring HomeCloud (redirect): %s"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cdp::ActivityManager::HandleAFSRequestedActions(cdp::ActivityManager *this, char **a2)
{
  char v3; // bl
  char v4; // r12
  char *v5; // rdi
  char *v6; // r13
  const char *v7; // rdx
  __int64 v8; // r9
  char v9; // al
  char *v10; // rax
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  const char *v21; // [rsp+30h] [rbp-39h] BYREF
  int v22; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v23[24]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE pExceptionObject[104]; // [rsp+58h] [rbp-11h] BYREF
  char *v25; // [rsp+D8h] [rbp+6Fh] BYREF
  char *CurrentThreadId; // [rsp+E0h] [rbp+77h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = *a2;
  v6 = a2[1];
  while ( v5 != v6 )
  {
    if ( !v3 )
    {
      if ( *v5 == 2 )
      {
        v7 = "{\"text\":\"Server asked to retry. Waiting for %u milli seconds\"}";
        goto LABEL_18;
      }
      if ( *v5 == 3 )
      {
        if ( !*((_DWORD *)v5 + 10) )
        {
          v21 = "..\\activitymanager.cpp";
          v22 = 3414;
          LODWORD(v25) = -2147418113;
          CurrentThreadId = (char *)GetCurrentThreadId();
          Log<long &,char const * &,int &,unsigned __int64>(
            v11,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
            (unsigned int)&v25,
            (unsigned int)&v21,
            (__int64)&v22,
            (__int64)&CurrentThreadId);
          v12 = cdp::ExceptionStackFromSourceLocationInfo(v23, &v21);
          v15 = cdp::ErrorCodeToString(2147549183LL, v13, v14, v12);
          ConnectedDevices::Exception::Exception(pExceptionObject, 2147549183LL, v15);
          throw (ConnectedDevices::Exception *)pExceptionObject;
        }
        Log<int const &>(this, "{\"text\":\"Server asked to retry after %u seconds. Waiting...\"}", (_DWORD)v5 + 40);
        LOBYTE(v8) = *((_QWORD *)v5 + 6) != 0;
        cdp::ActivityManager::StartRetryTimer(this, 1000 * *((_DWORD *)v5 + 10), *((unsigned int *)v5 + 11), v8);
        cdp::ActivityThrottling::HandleNewThrottleRule((cdp::ActivityManager *)((char *)this + 1800));
        goto LABEL_19;
      }
    }
    v9 = *v5;
    if ( *v5 == 6 )
    {
      if ( !*((_QWORD *)v5 + 3) )
      {
        v21 = "..\\activitymanager.cpp";
        v22 = 3423;
        LODWORD(v25) = -2147418113;
        CurrentThreadId = (char *)GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v16,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v25,
          (unsigned int)&v21,
          (__int64)&v22,
          (__int64)&CurrentThreadId);
        v17 = cdp::ExceptionStackFromSourceLocationInfo(v23, &v21);
        v20 = cdp::ErrorCodeToString(2147549183LL, v18, v19, v17);
        ConnectedDevices::Exception::Exception(pExceptionObject, 2147549183LL, v20);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      CurrentThreadId = (char *)this + 296;
      std::_Mutex_base::lock((cdp::ActivityManager *)((char *)this + 296));
      if ( *((_QWORD *)v5 + 4) <= 0xFu )
        v10 = v5 + 8;
      else
        v10 = (char *)*((_QWORD *)v5 + 1);
      v25 = v10;
      Log<unsigned __int64 &>(
        3,
        "{\"text\":\"ActivityManager - Configuring HomeCloud (redirect): %s\"}",
        (const char *)&v25);
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 62) + 56LL))(*((_QWORD *)this + 62), v5 + 8);
      _Mtx_unlock((cdp::ActivityManager *)((char *)this + 296));
      goto LABEL_29;
    }
    if ( !v3 && v9 == 5 )
    {
      v7 = "{\"text\":\"Failed to authenticate. Waiting for %u milli seconds\"}";
LABEL_18:
      v25 = (char *)*((_QWORD *)this + 189);
      Log<unsigned short const *>(this, v7, &v25);
      cdp::ActivityManager::StartRetryTimer(this, *((_QWORD *)this + 189), *((unsigned int *)v5 + 11), 0);
LABEL_19:
      v3 = 1;
      goto LABEL_30;
    }
    if ( v9 == 1 )
    {
      Log<>(3, "{\"text\":\"Server asked to retry (no wait)\"}");
      goto LABEL_30;
    }
    if ( !v4 && v9 == 4 )
    {
      cdp::ActivityManager::HandleAFSClipboardBackOff(this, (const struct cdp::AFSRequestedAction *)v5);
      v4 = 1;
      goto LABEL_30;
    }
    if ( v9 == 7 )
    {
      cdp::ActivityManager::HandleAFSStrongAuthRequirement(this);
      goto LABEL_30;
    }
    if ( v9 == 8 )
    {
      Log<>(3, "{\"text\":\"Server asked to refresh the subscription\"}");
      cdp::ActivityFeedSubscriptionManager::EnqueueSubscriptionUpdateRequest(*((_QWORD *)this + 94), 10);
LABEL_29:
      cdp::ActivityManager::ScheduleCheckForWork(this);
    }
LABEL_30:
    v5 += 64;
  }
}

```

## disassembly

```asm
0x18010529c  mov     [rsp-8+arg_0], rbx
0x1801052a1  push    rbp
0x1801052a2  push    rsi
0x1801052a3  push    rdi
0x1801052a4  push    r12
0x1801052a6  push    r13
0x1801052a8  push    r14
0x1801052aa  push    r15
0x1801052ac  lea     rbp, [rsp-27h]
0x1801052b1  sub     rsp, 90h
0x1801052b8  mov     rsi, rcx
0x1801052bb  xor     bl, bl
0x1801052bd  xor     r12b, r12b
0x1801052c0  mov     rdi, [rdx]
0x1801052c3  mov     r13, [rdx+8]
0x1801052c7  cmp     rdi, r13
0x1801052ca  jz      loc_180105567
0x1801052d0  test    bl, bl
0x1801052d2  jnz     short loc_18010533B
0x1801052d4  cmp     byte ptr [rdi], 2
0x1801052d7  jnz     short loc_1801052E5
0x1801052d9  lea     rdx, aTextServerAske_1; "{\"text\":\"Server asked to retry. Wait"...
0x1801052e0  jmp     loc_1801053C0
0x1801052e5  cmp     byte ptr [rdi], 3
0x1801052e8  jnz     short loc_18010533B
0x1801052ea  lea     r14, [rdi+28h]
0x1801052ee  cmp     dword ptr [r14], 0
0x1801052f2  jz      loc_180105463
0x1801052f8  mov     r8, r14
0x1801052fb  lea     rdx, aTextServerAske_3; "{\"text\":\"Server asked to retry after"...
0x180105302  call    ??$Log@AEBH@@YAXW4CDPLogLevel@@PEBDAEBH@Z; Log<int const &>(CDPLogLevel,char const *,int const &)
0x180105307  cmp     qword ptr [rdi+30h], 0
0x18010530c  setnz   r9b
0x180105310  imul    eax, [r14], 3E8h
0x180105317  movsxd  rdx, eax
0x18010531a  mov     r8d, [rdi+2Ch]
0x18010531e  mov     rcx, rsi
0x180105321  call    ?StartRetryTimer@ActivityManager@cdp@@AEAAXV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@I_N@Z; cdp::ActivityManager::StartRetryTimer(std::chrono::duration<__int64,std::ratio<1,1000>>,uint,bool)
0x180105326  lea     rcx, [rsi+708h]; this
0x18010532d  lea     rdx, [rdi+30h]
0x180105331  call    ?HandleNewThrottleRule@ActivityThrottling@cdp@@QEAAXAEBV?$shared_ptr@UAFSThrottleRule@cdp@@@std@@@Z; cdp::ActivityThrottling::HandleNewThrottleRule(std::shared_ptr<cdp::AFSThrottleRule> const &)
0x180105336  jmp     loc_1801053EA
0x18010533b  mov     al, [rdi]
0x18010533d  cmp     al, 6
0x18010533f  jnz     short loc_1801053B1
0x180105341  cmp     qword ptr [rdi+18h], 0
0x180105346  jz      loc_1801054E5
0x18010534c  lea     r15, [rsi+128h]
0x180105353  mov     [rbp+57h+arg_10], r15
0x180105357  mov     rcx, r15; this
0x18010535a  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18010535f  nop
0x180105360  lea     r14, [rdi+8]
0x180105364  cmp     qword ptr [rdi+20h], 0Fh
0x180105369  jbe     short loc_180105370
0x18010536b  mov     rax, [r14]
0x18010536e  jmp     short loc_180105373
0x180105370  mov     rax, r14
0x180105373  mov     [rbp+57h+arg_8], rax
0x180105377  lea     r8, [rbp+57h+arg_8]
0x18010537b  lea     rdx, aTextActivityma_13; "{\"text\":\"ActivityManager - Configuri"...
0x180105382  mov     ecx, 3
0x180105387  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x18010538c  mov     rcx, [rsi+1F0h]
0x180105393  mov     rax, [rcx]
0x180105396  mov     rdx, r14
0x180105399  mov     rax, [rax+38h]
0x18010539d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801053a2  nop
0x1801053a3  mov     rcx, r15; _Mtx_t
0x1801053a6  call    cs:__imp__Mtx_unlock
0x1801053ac  jmp     loc_180105452
0x1801053b1  test    bl, bl
0x1801053b3  jnz     short loc_1801053EE
0x1801053b5  cmp     al, 5
0x1801053b7  jnz     short loc_1801053EE
0x1801053b9  lea     rdx, aTextFailedToAu_0; "{\"text\":\"Failed to authenticate. Wai"...
0x1801053c0  mov     rax, [rsi+5E8h]
0x1801053c7  lea     r8, [rbp+57h+arg_8]
0x1801053cb  mov     [rbp+57h+arg_8], rax
0x1801053cf  call    ??$Log@PEBG@@YAXW4CDPLogLevel@@PEBD$$QEAPEBG@Z; Log<ushort const *>(CDPLogLevel,char const *,ushort const * &&)
0x1801053d4  xor     r9d, r9d
0x1801053d7  mov     r8d, [rdi+2Ch]
0x1801053db  mov     rdx, [rsi+5E8h]
0x1801053e2  mov     rcx, rsi
0x1801053e5  call    ?StartRetryTimer@ActivityManager@cdp@@AEAAXV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@I_N@Z; cdp::ActivityManager::StartRetryTimer(std::chrono::duration<__int64,std::ratio<1,1000>>,uint,bool)
0x1801053ea  mov     bl, 1
0x1801053ec  jmp     short loc_18010545A
0x1801053ee  cmp     al, 1
0x1801053f0  jnz     short loc_180105405
0x1801053f2  lea     rdx, aTextServerAske; "{\"text\":\"Server asked to retry (no w"...
0x1801053f9  mov     ecx, 3
0x1801053fe  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180105403  jmp     short loc_18010545A
0x180105405  test    r12b, r12b
0x180105408  jnz     short loc_18010541E
0x18010540a  cmp     al, 4
0x18010540c  jnz     short loc_18010541E
0x18010540e  mov     rdx, rdi; struct cdp::AFSRequestedAction *
0x180105411  mov     rcx, rsi; this
0x180105414  call    ?HandleAFSClipboardBackOff@ActivityManager@cdp@@AEAAXAEBUAFSRequestedAction@2@@Z; cdp::ActivityManager::HandleAFSClipboardBackOff(cdp::AFSRequestedAction const &)
0x180105419  mov     r12b, 1
0x18010541c  jmp     short loc_18010545A
0x18010541e  cmp     al, 7
0x180105420  jnz     short loc_18010542C
0x180105422  mov     rcx, rsi; this
0x180105425  call    ?HandleAFSStrongAuthRequirement@ActivityManager@cdp@@AEAAXXZ; cdp::ActivityManager::HandleAFSStrongAuthRequirement(void)
0x18010542a  jmp     short loc_18010545A
0x18010542c  cmp     al, 8
0x18010542e  jnz     short loc_18010545A
0x180105430  lea     rdx, aTextServerAske_0; "{\"text\":\"Server asked to refresh the"...
0x180105437  mov     ecx, 3
0x18010543c  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180105441  mov     edx, 0Ah
0x180105446  mov     rcx, [rsi+2F0h]
0x18010544d  call    ?EnqueueSubscriptionUpdateRequest@ActivityFeedSubscriptionManager@cdp@@QEAAXW4CDPDeviceRegistrationReason@@@Z; cdp::ActivityFeedSubscriptionManager::EnqueueSubscriptionUpdateRequest(CDPDeviceRegistrationReason)
0x180105452  mov     rcx, rsi; this
0x180105455  call    ?ScheduleCheckForWork@ActivityManager@cdp@@QEAAXXZ; cdp::ActivityManager::ScheduleCheckForWork(void)
0x18010545a  add     rdi, 40h ; '@'
0x18010545e  jmp     loc_1801052C7
0x180105463  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x18010546a  mov     [rbp+57h+var_90], rax
0x18010546e  mov     [rbp+57h+var_88], 0D56h
0x180105475  mov     ebx, 8000FFFFh
0x18010547a  mov     dword ptr [rbp+57h+arg_8], ebx
0x18010547d  call    cs:__imp_GetCurrentThreadId
0x180105483  mov     eax, eax
0x180105485  mov     [rbp+57h+arg_10], rax
0x180105489  lea     rax, [rbp+57h+arg_10]
0x18010548d  mov     [rsp+0C0h+var_98], rax
0x180105492  lea     rax, [rbp+57h+var_88]
0x180105496  mov     [rsp+0C0h+var_A0], rax
0x18010549b  lea     r9, [rbp+57h+var_90]
0x18010549f  lea     r8, [rbp+57h+arg_8]
0x1801054a3  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801054aa  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801054af  lea     rdx, [rbp+57h+var_90]
0x1801054b3  lea     rcx, [rbp+57h+var_80]
0x1801054b7  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801054bc  mov     r9, rax
0x1801054bf  mov     ecx, ebx
0x1801054c1  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801054c6  mov     r8, rax
0x1801054c9  mov     edx, ebx
0x1801054cb  lea     rcx, [rbp+57h+pExceptionObject]
0x1801054cf  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801054d4  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801054db  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801054df  call    _CxxThrowException_0
0x1801054e5  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1801054ec  mov     [rbp+57h+var_90], rax
0x1801054f0  mov     [rbp+57h+var_88], 0D5Fh
0x1801054f7  mov     ebx, 8000FFFFh
0x1801054fc  mov     dword ptr [rbp+57h+arg_8], ebx
0x1801054ff  call    cs:__imp_GetCurrentThreadId
0x180105505  mov     eax, eax
0x180105507  mov     [rbp+57h+arg_10], rax
0x18010550b  lea     rax, [rbp+57h+arg_10]
0x18010550f  mov     [rsp+0C0h+var_98], rax
0x180105514  lea     rax, [rbp+57h+var_88]
0x180105518  mov     [rsp+0C0h+var_A0], rax
0x18010551d  lea     r9, [rbp+57h+var_90]
0x180105521  lea     r8, [rbp+57h+arg_8]
0x180105525  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18010552c  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180105531  lea     rdx, [rbp+57h+var_90]
0x180105535  lea     rcx, [rbp+57h+var_80]
0x180105539  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18010553e  mov     r9, rax
0x180105541  mov     ecx, ebx
0x180105543  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180105548  mov     r8, rax
0x18010554b  mov     edx, ebx
0x18010554d  lea     rcx, [rbp+57h+pExceptionObject]
0x180105551  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180105556  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18010555d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180105561  call    _CxxThrowException_0
0x180105567  mov     rbx, [rsp+0C0h+arg_0]
0x18010556f  add     rsp, 90h
0x180105576  pop     r15
0x180105578  pop     r14
0x18010557a  pop     r13
0x18010557c  pop     r12
0x18010557e  pop     rdi
0x18010557f  pop     rsi
0x180105580  pop     rbp
0x180105581  retn
```
