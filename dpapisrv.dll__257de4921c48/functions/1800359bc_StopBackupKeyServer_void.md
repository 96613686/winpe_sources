# StopBackupKeyServer(void)

- ea: `0x1800359bc`
- end: `0x180035aa8`
- name: `?StopBackupKeyServer@@YAKXZ`
- size: `236`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800283c4`

## callees

- `0x180008300`
- `0x18001d810`
- `0x180030414`
- `0x1800359bc`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIf` at `0x1800359e7`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800359e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180035a3e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180035a3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035a13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035a13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180035a2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180035a2b`

## pseudocode

```c
__int64 StopBackupKeyServer(void)
{
  unsigned int v0; // ebx
  int v1; // ecx
  int v2; // r8d
  _BYTE v4[16]; // [rsp+30h] [rbp-28h] BYREF

  v0 = 0;
  if ( g_fBackupKeyServerStarted )
  {
    v0 = RpcServerUnregisterIf(qword_18003FD60, 0, 0);
    g_fBackupKeyServerStarted = 0;
  }
  if ( CPreferredKeys::s_renewTimer )
  {
    SetThreadpoolTimer(CPreferredKeys::s_renewTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(CPreferredKeys::s_renewTimer, 1);
    CloseThreadpoolTimer(CPreferredKeys::s_renewTimer);
    CPreferredKeys::s_renewTimer = 0;
  }
  CPreferredKeys::CPreferredKey::Clean((CPreferredKeys::CPreferredKey *)&CPreferredKeys::s_preferredKey);
  CPreferredKeys::CPreferredKey::Clean((CPreferredKeys::CPreferredKey *)&CPreferredKeys::s_preferredKeyW2K);
  if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v1, (unsigned int)ETW_LOG_BACKUPKEYSVC_STOPPED, v2, 1, (__int64)v4);
  return v0;
}

```

## disassembly

```asm
0x1800359bc  push    rbx
0x1800359be  sub     rsp, 50h
0x1800359c2  mov     rax, cs:__security_cookie
0x1800359c9  xor     rax, rsp
0x1800359cc  mov     [rsp+58h+var_18], rax
0x1800359d1  xor     ebx, ebx
0x1800359d3  cmp     cs:?g_fBackupKeyServerStarted@@3HA, ebx; int g_fBackupKeyServerStarted
0x1800359d9  jz      short loc_1800359FF
0x1800359db  xor     r8d, r8d; WaitForCallsToComplete
0x1800359de  lea     rcx, qword_18003FD60; IfSpec
0x1800359e5  xor     edx, edx; MgrTypeUuid
0x1800359e7  call    cs:__imp_RpcServerUnregisterIf
0x1800359ee  nop     dword ptr [rax+rax+00h]
0x1800359f3  mov     ebx, eax
0x1800359f5  mov     cs:?g_fBackupKeyServerStarted@@3HA, 0; int g_fBackupKeyServerStarted
0x1800359ff  mov     rcx, cs:?s_renewTimer@CPreferredKeys@@0PEAU_TP_TIMER@@EA; pti
0x180035a06  test    rcx, rcx
0x180035a09  jz      short loc_180035A55
0x180035a0b  xor     r9d, r9d; msWindowLength
0x180035a0e  xor     r8d, r8d; msPeriod
0x180035a11  xor     edx, edx; pftDueTime
0x180035a13  call    cs:__imp_SetThreadpoolTimer
0x180035a1a  nop     dword ptr [rax+rax+00h]
0x180035a1f  mov     rcx, cs:?s_renewTimer@CPreferredKeys@@0PEAU_TP_TIMER@@EA; pti
0x180035a26  mov     edx, 1; fCancelPendingCallbacks
0x180035a2b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180035a32  nop     dword ptr [rax+rax+00h]
0x180035a37  mov     rcx, cs:?s_renewTimer@CPreferredKeys@@0PEAU_TP_TIMER@@EA; pti
0x180035a3e  call    cs:__imp_CloseThreadpoolTimer
0x180035a45  nop     dword ptr [rax+rax+00h]
0x180035a4a  mov     cs:?s_renewTimer@CPreferredKeys@@0PEAU_TP_TIMER@@EA, 0; _TP_TIMER * CPreferredKeys::s_renewTimer
0x180035a55  lea     rcx, ?s_preferredKey@CPreferredKeys@@0VCPreferredKey@1@A; this
0x180035a5c  call    ?Clean@CPreferredKey@CPreferredKeys@@AEAAXXZ; CPreferredKeys::CPreferredKey::Clean(void)
0x180035a61  lea     rcx, ?s_preferredKeyW2K@CPreferredKeys@@0VCPreferredKey@1@A; this
0x180035a68  call    ?Clean@CPreferredKey@CPreferredKeys@@AEAAXXZ; CPreferredKeys::CPreferredKey::Clean(void)
0x180035a6d  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 1
0x180035a74  jz      short loc_180035A92
0x180035a76  lea     rax, [rsp+58h+var_28]
0x180035a7b  mov     r9d, 1
0x180035a81  lea     rdx, ETW_LOG_BACKUPKEYSVC_STOPPED
0x180035a88  mov     [rsp+58h+var_38], rax
0x180035a8d  call    McGenEventWrite_EtwEventWriteTransfer
0x180035a92  mov     eax, ebx
0x180035a94  mov     rcx, [rsp+58h+var_18]
0x180035a99  xor     rcx, rsp; StackCookie
0x180035a9c  call    __security_check_cookie
0x180035aa1  add     rsp, 50h
0x180035aa5  pop     rbx
0x180035aa6  retn
```
