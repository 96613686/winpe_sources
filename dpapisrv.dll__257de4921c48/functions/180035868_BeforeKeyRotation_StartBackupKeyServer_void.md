# BeforeKeyRotation::StartBackupKeyServer(void)

- ea: `0x180035868`
- end: `0x1800359b3`
- name: `?StartBackupKeyServer@BeforeKeyRotation@@YAKXZ`
- size: `331`
- prototype: `unsigned int __fastcall(BeforeKeyRotation *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800280a8`

## callees

- `0x180007f10`
- `0x180008300`
- `0x18000fd40`
- `0x180013f2c`
- `0x18001d810`
- `0x180032730`
- `0x180035868`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003592e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003592e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18003591e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18003591e`
- `ntdll!RtlInitializeCriticalSection` at `0x180035888`
- `ntdll!RtlInitializeCriticalSection` at `0x180035888`

## string_xrefs

- `0x1800358a0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BeforeKeyRotation::StartBackupKeyServer(BeforeKeyRotation *this)
{
  NTSTATUS v1; // eax
  DWORD v2; // ebx
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  DWORD LastError; // eax
  _BYTE v8[16]; // [rsp+30h] [rbp-28h] BYREF

  v1 = RtlInitializeCriticalSection(&BeforeKeyRotation::g_csInitialization);
  v2 = v1;
  if ( v1 < 0 )
  {
    DebugTraceError((unsigned int)v1, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 4407);
    return v2;
  }
  BeforeKeyRotation::g_fcsInitializationSetup = 1;
  if ( (unsigned int)IsDomainController() )
  {
    v4 = InitializeBackupKeyServer();
    if ( v4 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_9f8a772c59583afc3e8e74227050d313_Traceguids, v4);
      if ( !QueueUserWorkItem((LPTHREAD_START_ROUTINE)QueueInitBackupKeyServerThreadFunc, 0, 0x10u) )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            14,
            WPP_9f8a772c59583afc3e8e74227050d313_Traceguids,
            LastError);
        return v2;
      }
    }
    if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v5, (__int64)ETW_LOG_BACKUPKEYSVC_STARTED, v6, 1, (__int64)v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180035868  mov     [rsp+arg_0], rbx
0x18003586d  push    rsi
0x18003586e  sub     rsp, 50h
0x180035872  mov     rax, cs:__security_cookie
0x180035879  xor     rax, rsp
0x18003587c  mov     [rsp+58h+var_18], rax
0x180035881  lea     rcx, ?g_csInitialization@BeforeKeyRotation@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180035888  call    cs:__imp_RtlInitializeCriticalSection
0x18003588f  nop     dword ptr [rax+rax+00h]
0x180035894  mov     ebx, eax
0x180035896  test    eax, eax
0x180035898  jns     short loc_1800358BC
0x18003589a  mov     r9d, 1137h
0x1800358a0  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800358a7  lea     rdx, aStatus; "Status"
0x1800358ae  mov     ecx, eax
0x1800358b0  call    DebugTraceError
0x1800358b5  mov     eax, ebx
0x1800358b7  jmp     loc_18003599A
0x1800358bc  mov     cs:?g_fcsInitializationSetup@BeforeKeyRotation@@3HA, 1; int BeforeKeyRotation::g_fcsInitializationSetup
0x1800358c6  call    IsDomainController
0x1800358cb  test    eax, eax
0x1800358cd  jz      loc_180035998
0x1800358d3  call    ?InitializeBackupKeyServer@@YAKXZ; InitializeBackupKeyServer(void)
0x1800358d8  test    eax, eax
0x1800358da  jz      loc_180035973
0x1800358e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358e7  lea     rsi, WPP_GLOBAL_Control
0x1800358ee  cmp     rcx, rsi
0x1800358f1  jz      short loc_180035911
0x1800358f3  test    byte ptr [rcx+1Ch], 2
0x1800358f7  jz      short loc_180035911
0x1800358f9  mov     rcx, [rcx+10h]
0x1800358fd  lea     r8, WPP_9f8a772c59583afc3e8e74227050d313_Traceguids
0x180035904  mov     edx, 0Dh
0x180035909  mov     r9d, eax
0x18003590c  call    WPP_SF_d
0x180035911  xor     edx, edx; Context
0x180035913  lea     rcx, ?QueueInitBackupKeyServerThreadFunc@@YAKPEAX@Z; Function
0x18003591a  lea     r8d, [rdx+10h]; Flags
0x18003591e  call    cs:__imp_QueueUserWorkItem
0x180035925  nop     dword ptr [rax+rax+00h]
0x18003592a  test    eax, eax
0x18003592c  jnz     short loc_180035973
0x18003592e  call    cs:__imp_GetLastError
0x180035935  nop     dword ptr [rax+rax+00h]
0x18003593a  mov     ebx, eax
0x18003593c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035943  cmp     rcx, rsi
0x180035946  jz      loc_1800358B5
0x18003594c  test    byte ptr [rcx+1Ch], 1
0x180035950  jz      loc_1800358B5
0x180035956  mov     rcx, [rcx+10h]
0x18003595a  lea     r8, WPP_9f8a772c59583afc3e8e74227050d313_Traceguids
0x180035961  mov     edx, 0Eh
0x180035966  mov     r9d, eax
0x180035969  call    WPP_SF_d
0x18003596e  jmp     loc_1800358B5
0x180035973  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 1
0x18003597a  jz      short loc_180035998
0x18003597c  lea     rax, [rsp+58h+var_28]
0x180035981  mov     r9d, 1
0x180035987  lea     rdx, ETW_LOG_BACKUPKEYSVC_STARTED
0x18003598e  mov     [rsp+58h+var_38], rax
0x180035993  call    McGenEventWrite_EtwEventWriteTransfer
0x180035998  xor     eax, eax
0x18003599a  mov     rcx, [rsp+58h+var_18]
0x18003599f  xor     rcx, rsp; StackCookie
0x1800359a2  call    __security_check_cookie
0x1800359a7  mov     rbx, [rsp+58h+arg_0]
0x1800359ac  add     rsp, 50h
0x1800359b0  pop     rsi
0x1800359b1  retn
```
