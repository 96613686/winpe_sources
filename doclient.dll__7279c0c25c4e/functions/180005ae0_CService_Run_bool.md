# CService::Run(bool)

- ea: `0x180005ae0`
- end: `0x180005e19`
- name: `?Run@CService@@UEAAJ_N@Z`
- size: `825`
- prototype: `__int64 __fastcall(CService *__hidden this, bool)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005ae0`
- `0x1800066b0`
- `0x18000696c`
- `0x180008450`
- `0x180029854`
- `0x18007d730`
- `0x18007e368`
- `0x180097c04`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005b53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005b53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cb6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005be0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005be0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005c48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005c48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005c55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005c55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bfc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bfc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c97`
- `api-ms-win-core-processthreads-l1-1-3!GetProcessInformation` at `0x180005b6b`
- `api-ms-win-core-processthreads-l1-1-3!GetProcessInformation` at `0x180005b6b`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180005cad`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180005cad`

## string_xrefs

- `0x180005b0b`: `*** Starting DO service ***`
- `0x180005b18`: `CService::Run`
- `0x180005b31`: `** Service was started due to trigger event **`
- `0x180005ce1`: `Service is Idle but is still referenced by external objects (external lock-count = %u)`
- `0x180005d70`: `*** Service out of Run loop. Exiting... ***`
- `0x180005e07`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CService::Run(CService *this, bool a2)
{
  HANDLE CurrentProcess; // rax
  int v5; // ebp
  DWORD v6; // eax
  const char *v7; // r9
  __int64 v8; // r14
  bool v9; // bl
  RTL_SRWLOCK *v10; // rdi
  PVOID Ptr; // rbx
  __int64 v12; // rcx
  unsigned int v14; // eax
  int v15; // eax
  int v17; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  LogMessage(4u, "CService::Run", 0x91u, "*** Starting DO service ***");
  if ( a2 )
    LogMessage(5u, "CService::Run", 0x94u, "** Service was started due to trigger event **");
  v17 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)GetProcessInformation(CurrentProcess, 7, &v17) && v17 != 2 )
  {
    LogMessage(2u, "CService::Run", 0x9Cu, "TelemetryAssert (%s): %s", "info.ProtectionLevel == 0x00000002", "Failed");
    DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
  }
  v5 = CDeliveryOptimizationManager::Init(
         *((CDeliveryOptimizationManager **)this + 5),
         a2,
         *((struct IDoUsageCallback **)this + 7));
  if ( v5 < 0 )
  {
    CService::_OnStop((CService *)((char *)this - 8));
    v15 = 0;
    if ( v5 != -2133848063 )
      v15 = v5;
    v5 = v15;
  }
  else
  {
    while ( 1 )
    {
      v6 = WaitForSingleObjectEx(*((HANDLE *)this + 4), 0x493E0u, 0);
      if ( v6 != 258 )
        break;
      v8 = *((_QWORD *)this + 5);
      AcquireSRWLockExclusive((PSRWLOCK)(v8 + 16));
      if ( ++*(_DWORD *)(v8 + 28) == 1 )
        _InterlockedExchange((volatile __int32 *)(v8 + 24), 0);
      ReleaseSRWLockExclusive((PSRWLOCK)(v8 + 16));
      v9 = 0;
      if ( CDeliveryOptimizationManager::_WaitForInit((CDeliveryOptimizationManager *)v8, 0) >= 0
        && *(int *)(v8 + 8) >= 0
        && !g_fIsShutdownInProgress )
      {
        v10 = *(RTL_SRWLOCK **)(v8 + 40);
        AcquireSRWLockShared(v10);
        Ptr = v10[2].Ptr;
        ReleaseSRWLockShared(v10);
        v9 = !Ptr && CCore::IsIdle(*(CCore **)(v8 + 176));
        v12 = *(_QWORD *)(v8 + 176);
        if ( v12 )
          CCoreUsageNotifier::NotifyManagerState(*(CCoreUsageNotifier **)(v12 + 296), !v9);
      }
      AcquireSRWLockExclusive((PSRWLOCK)(v8 + 16));
      if ( (*(_DWORD *)(v8 + 28))-- == 1 )
      {
        *(_DWORD *)(v8 + 24) = 1;
        WakeByAddressAll((PVOID)(v8 + 24));
      }
      ReleaseSRWLockExclusive((PSRWLOCK)(v8 + 16));
      if ( v9 )
      {
        v14 = *((_DWORD *)this + 29);
        if ( v14 >= 2 )
          LogMessage(
            5u,
            "CService::Run",
            0xB8u,
            "Service is Idle but is still referenced by external objects (external lock-count = %u)",
            v14 - 1);
        else
          CService::_OnStop((CService *)((char *)this - 8));
      }
    }
    if ( v6 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xAD8,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    if ( CService::_svcStatusInfo.dwCurrentState != 3 )
    {
      LogMessage(
        2u,
        "CService::Run",
        0xAAu,
        "TelemetryAssert (%s): %s",
        "_svcStatusInfo.dwCurrentState == 0x00000003",
        "Failed");
      DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
    }
  }
  CService::_Shutdown((CService *)((char *)this - 8), 1);
  LogResult(4u, "CService::Run", 0xCBu, v5, "*** Service out of Run loop. Exiting... ***");
  if ( v5 < 0 )
  {
    LogMessage(
      2u,
      "CService::Run",
      0xCCu,
      "TelemetryAssert (%s): %s (0x%x, 0x%x)",
      "(((HRESULT)(hr)) >= 0)",
      "Failed",
      v5,
      0);
    DOTelemetryAssertTriggered(v5, 0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005ae0  mov     [rsp+arg_10], rbx
0x180005ae5  mov     [rsp+arg_18], rbp
0x180005aea  push    rsi
0x180005aeb  push    rdi
0x180005aec  push    r13
0x180005aee  push    r14
0x180005af0  push    r15
0x180005af2  sub     rsp, 60h
0x180005af6  mov     rax, cs:__security_cookie
0x180005afd  xor     rax, rsp
0x180005b00  mov     [rsp+88h+var_38], rax
0x180005b05  mov     dil, dl
0x180005b08  mov     r15, rcx
0x180005b0b  lea     r9, aStartingDoServ; "*** Starting DO service ***"
0x180005b12  mov     r8d, 91h; unsigned int
0x180005b18  lea     r13, aCserviceRun; "CService::Run"
0x180005b1f  mov     rdx, r13; char *
0x180005b22  mov     ecx, 4; unsigned __int8
0x180005b27  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180005b2c  test    dil, dil
0x180005b2f  jz      short loc_180005B4B
0x180005b31  lea     r9, aServiceWasStar; "** Service was started due to trigger e"...
0x180005b38  mov     r8d, 94h; unsigned int
0x180005b3e  mov     rdx, r13; char *
0x180005b41  mov     ecx, 5; unsigned __int8
0x180005b46  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180005b4b  mov     [rsp+88h+var_40], 0
0x180005b53  call    cs:__imp_GetCurrentProcess
0x180005b59  mov     rcx, rax
0x180005b5c  mov     r9d, 4
0x180005b62  lea     r8, [rsp+88h+var_40]
0x180005b67  lea     edx, [r9+3]
0x180005b6b  call    cs:__imp_GetProcessInformation
0x180005b71  lea     r14, aFailed; "Failed"
0x180005b78  or      esi, 0FFFFFFFFh
0x180005b7b  test    eax, eax
0x180005b7d  jz      short loc_180005BBA
0x180005b7f  cmp     [rsp+88h+var_40], 2
0x180005b84  jz      short loc_180005BBA
0x180005b86  mov     [rsp+88h+var_60], r14
0x180005b8b  lea     rax, aInfoProtection; "info.ProtectionLevel == 0x00000002"
0x180005b92  mov     [rsp+88h+var_68], rax
0x180005b97  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x180005b9e  mov     r8d, 9Ch; unsigned int
0x180005ba4  mov     rdx, r13; char *
0x180005ba7  mov     ecx, 2; unsigned __int8
0x180005bac  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180005bb1  mov     edx, esi; unsigned int
0x180005bb3  mov     ecx, esi; unsigned int
0x180005bb5  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x180005bba  mov     r8, [r15+38h]; struct IDoUsageCallback *
0x180005bbe  mov     dl, dil; bool
0x180005bc1  mov     rcx, [r15+28h]; this
0x180005bc5  call    ?Init@CDeliveryOptimizationManager@@QEAAJ_NPEAVIDoUsageCallback@@@Z; CDeliveryOptimizationManager::Init(bool,IDoUsageCallback *)
0x180005bca  mov     ebp, eax
0x180005bcc  test    eax, eax
0x180005bce  js      loc_180005D4F
0x180005bd4  xor     r8d, r8d; bAlertable
0x180005bd7  mov     edx, 493E0h; dwMilliseconds
0x180005bdc  mov     rcx, [r15+20h]; hHandle
0x180005be0  call    cs:__imp_WaitForSingleObjectEx
0x180005be6  cmp     eax, 102h
0x180005beb  jnz     loc_180005D00
0x180005bf1  mov     r14, [r15+28h]
0x180005bf5  lea     rsi, [r14+10h]
0x180005bf9  mov     rcx, rsi; SRWLock
0x180005bfc  call    cs:__imp_AcquireSRWLockExclusive
0x180005c02  inc     dword ptr [rsi+0Ch]
0x180005c05  cmp     dword ptr [rsi+0Ch], 1
0x180005c09  jnz     short loc_180005C10
0x180005c0b  xor     eax, eax
0x180005c0d  xchg    eax, [rsi+8]
0x180005c10  mov     [rsp+88h+var_48], rsi
0x180005c15  mov     rcx, rsi; SRWLock
0x180005c18  call    cs:__imp_ReleaseSRWLockExclusive
0x180005c1e  nop
0x180005c1f  xor     bl, bl
0x180005c21  xor     edx, edx; unsigned int
0x180005c23  mov     rcx, r14; this
0x180005c26  call    ?_WaitForInit@CDeliveryOptimizationManager@@AEBAJI@Z; CDeliveryOptimizationManager::_WaitForInit(uint)
0x180005c2b  test    eax, eax
0x180005c2d  js      short loc_180005C94
0x180005c2f  cmp     dword ptr [r14+8], 0
0x180005c34  jl      short loc_180005C94
0x180005c36  mov     al, cs:?g_fIsShutdownInProgress@@3U?$atomic@_N@std@@A; std::atomic<bool> g_fIsShutdownInProgress
0x180005c3c  nop
0x180005c3d  test    al, al
0x180005c3f  jnz     short loc_180005C94
0x180005c41  mov     rdi, [r14+28h]
0x180005c45  mov     rcx, rdi; SRWLock
0x180005c48  call    cs:__imp_AcquireSRWLockShared
0x180005c4e  mov     rbx, [rdi+10h]
0x180005c52  mov     rcx, rdi; SRWLock
0x180005c55  call    cs:__imp_ReleaseSRWLockShared
0x180005c5b  test    rbx, rbx
0x180005c5e  jnz     short loc_180005C74
0x180005c60  mov     rcx, [r14+0B0h]; this
0x180005c67  call    ?IsIdle@CCore@@QEBA_NXZ; CCore::IsIdle(void)
0x180005c6c  test    al, al
0x180005c6e  jz      short loc_180005C74
0x180005c70  mov     bl, 1
0x180005c72  jmp     short loc_180005C76
0x180005c74  xor     bl, bl
0x180005c76  mov     rcx, [r14+0B0h]
0x180005c7d  test    rcx, rcx
0x180005c80  jz      short loc_180005C94
0x180005c82  mov     dl, bl
0x180005c84  xor     dl, 1; bool
0x180005c87  mov     rcx, [rcx+128h]; this
0x180005c8e  call    ?NotifyManagerState@CCoreUsageNotifier@@QEAAX_N@Z; CCoreUsageNotifier::NotifyManagerState(bool)
0x180005c93  nop
0x180005c94  mov     rcx, rsi; SRWLock
0x180005c97  call    cs:__imp_AcquireSRWLockExclusive
0x180005c9d  sub     dword ptr [rsi+0Ch], 1
0x180005ca1  jnz     short loc_180005CB3
0x180005ca3  lea     rcx, [rsi+8]; Address
0x180005ca7  mov     dword ptr [rcx], 1
0x180005cad  call    cs:__imp_WakeByAddressAll
0x180005cb3  mov     rcx, rsi; SRWLock
0x180005cb6  call    cs:__imp_ReleaseSRWLockExclusive
0x180005cbc  test    bl, bl
0x180005cbe  jz      loc_180005BD4
0x180005cc4  mov     eax, [r15+74h]
0x180005cc8  cmp     eax, 2
0x180005ccb  jnb     short loc_180005CDB
0x180005ccd  lea     rcx, [r15-8]; this
0x180005cd1  call    ?_OnStop@CService@@AEAAXXZ; CService::_OnStop(void)
0x180005cd6  jmp     loc_180005BD4
0x180005cdb  dec     eax
0x180005cdd  mov     dword ptr [rsp+88h+var_68], eax
0x180005ce1  lea     r9, aServiceIsIdleB; "Service is Idle but is still referenced"...
0x180005ce8  mov     r8d, 0B8h; unsigned int
0x180005cee  mov     rdx, r13; char *
0x180005cf1  mov     ecx, 5; unsigned __int8
0x180005cf6  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180005cfb  jmp     loc_180005BD4
0x180005d00  test    eax, eax
0x180005d02  jnz     loc_180005DFF
0x180005d08  lea     r14, aFailed; "Failed"
0x180005d0f  cmp     cs:?_svcStatusInfo@CService@@0U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS CService::_svcStatusInfo ...
0x180005d16  jz      short loc_180005D65
0x180005d18  mov     [rsp+88h+var_60], r14
0x180005d1d  lea     rax, aSvcstatusinfoD; "_svcStatusInfo.dwCurrentState == 0x0000"...
0x180005d24  mov     [rsp+88h+var_68], rax
0x180005d29  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x180005d30  mov     r8d, 0AAh; unsigned int
0x180005d36  mov     rdx, r13; char *
0x180005d39  mov     ecx, 2; unsigned __int8
0x180005d3e  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180005d43  or      ecx, 0FFFFFFFFh; unsigned int
0x180005d46  mov     edx, ecx; unsigned int
0x180005d48  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x180005d4d  jmp     short loc_180005D65
0x180005d4f  lea     rcx, [r15-8]; this
0x180005d53  call    ?_OnStop@CService@@AEAAXXZ; CService::_OnStop(void)
0x180005d58  xor     eax, eax
0x180005d5a  cmp     ebp, 80D01001h
0x180005d60  cmovnz  eax, ebp
0x180005d63  mov     ebp, eax
0x180005d65  lea     rcx, [r15-8]; this
0x180005d69  mov     dl, 1; bool
0x180005d6b  call    ?_Shutdown@CService@@AEAAX_N@Z; CService::_Shutdown(bool)
0x180005d70  lea     rax, aServiceOutOfRu; "*** Service out of Run loop. Exiting..."...
0x180005d77  mov     [rsp+88h+var_68], rax; char *
0x180005d7c  mov     r9d, ebp; int
0x180005d7f  mov     r8d, 0CBh; unsigned int
0x180005d85  mov     rdx, r13; char *
0x180005d88  mov     ecx, 4; unsigned __int8
0x180005d8d  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x180005d92  test    ebp, ebp
0x180005d94  jns     short loc_180005DD7
0x180005d96  mov     [rsp+88h+var_50], 0
0x180005d9f  mov     [rsp+88h+var_58], ebp
0x180005da3  mov     [rsp+88h+var_60], r14
0x180005da8  lea     rax, aHresultHr0; "(((HRESULT)(hr)) >= 0)"
0x180005daf  mov     [rsp+88h+var_68], rax
0x180005db4  lea     r9, aTelemetryasser_0; "TelemetryAssert (%s): %s (0x%x, 0x%x)"
0x180005dbb  mov     r8d, 0CCh; unsigned int
0x180005dc1  mov     rdx, r13; char *
0x180005dc4  mov     ecx, 2; unsigned __int8
0x180005dc9  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180005dce  xor     edx, edx; unsigned int
0x180005dd0  mov     ecx, ebp; unsigned int
0x180005dd2  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x180005dd7  mov     eax, ebp
0x180005dd9  mov     rcx, [rsp+88h+var_38]
0x180005dde  xor     rcx, rsp; StackCookie
0x180005de1  call    __security_check_cookie
0x180005de6  lea     r11, [rsp+88h+var_28]
0x180005deb  mov     rbx, [r11+40h]
0x180005def  mov     rbp, [r11+48h]
0x180005df3  mov     rsp, r11
0x180005df6  pop     r15
0x180005df8  pop     r14
0x180005dfa  pop     r13
0x180005dfc  pop     rdi
0x180005dfd  pop     rsi
0x180005dfe  retn
0x180005dff  mov     rcx, [rsp+88h]; this
0x180005e07  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180005e0e  mov     edx, 0AD8h; void *
0x180005e13  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
