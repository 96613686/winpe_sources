# InitializeHttpServer

- ea: `0x180064aac`
- end: `0x180064cf0`
- name: `InitializeHttpServer`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003cf4`

## callees

- `0x1800616b4`
- `0x180064aac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180064bc7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180064bc7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180064b22`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180064b22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180064c23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180064c23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180064c46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180064c46`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064bfb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064bfb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180064c89`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180064c89`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064c9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064c9c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180064b6a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180064b6a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064c71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064cdc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064c71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064cdc`

## string_xrefs

- `0x180064b4f`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c
char InitializeHttpServer()
{
  int v0; // ecx
  int v1; // ecx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  pftDueTime = 0;
  g_IpTlsSqmServerTimer = 0;
  stru_1800CC278.Version = 3;
  *(_OWORD *)&ptpp = 0;
  stru_1800CC278.CleanupGroupCancelCallback = 0;
  *(_OWORD *)&stru_1800CC278.Pool = 0;
  stru_1800CC278.FinalizationCallback = 0;
  *(_OWORD *)&stru_1800CC278.RaceDll = 0;
  stru_1800CC278.u.Flags = 0;
  stru_1800CC278.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  stru_1800CC278.Size = 72;
  ptpp = CreateThreadpool(0);
  if ( ptpp )
  {
    *(&ptpp + 1) = CreateThreadpoolCleanupGroup();
    if ( *(&ptpp + 1) )
    {
      *(_OWORD *)&stru_1800CC278.Pool = *(_OWORD *)&ptpp;
      stru_1800CC278.CleanupGroupCancelCallback = 0;
      InitializeCriticalSection(&stru_1800CC2D0);
      byte_1800CC2F8 = 1;
      qword_1800CC270 = (__int64)&qword_1800CC268;
      qword_1800CC268 = (__int64)&qword_1800CC268;
      g_IpTlsSqmServerTimer = CreateThreadpoolTimer(IpTlsSqmServerData, 0, 0);
      if ( g_IpTlsSqmServerTimer )
      {
        pftDueTime.dwHighDateTime = -9;
        pftDueTime.dwLowDateTime = -1640261632;
        SetThreadpoolTimer(g_IpTlsSqmServerTimer, &pftDueTime, 0x36EE80u, 0);
        return 1;
      }
    }
    else if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
    {
      McTemplateU0psq_EventWriteTransfer(
        v1,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
        0,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        194);
    }
  }
  else if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
  {
    McTemplateU0psq_EventWriteTransfer(
      v0,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE,
      0,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      183);
  }
  if ( *(&ptpp + 1) )
  {
    CloseThreadpoolCleanupGroup(*(&ptpp + 1));
    *(&ptpp + 1) = 0;
  }
  if ( ptpp )
  {
    CloseThreadpool(ptpp);
    ptpp = 0;
  }
  if ( g_IpTlsSqmServerTimer )
  {
    SetThreadpoolTimer(g_IpTlsSqmServerTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(g_IpTlsSqmServerTimer, 1);
    CloseThreadpoolTimer(g_IpTlsSqmServerTimer);
    g_IpTlsSqmServerTimer = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180064aac  sub     rsp, 38h
0x180064ab0  xorps   xmm0, xmm0
0x180064ab3  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0
0x180064abc  xorps   xmm1, xmm1
0x180064abf  mov     cs:g_IpTlsSqmServerTimer, 0
0x180064aca  xor     ecx, ecx; reserved
0x180064acc  mov     cs:stru_1800CC278.Version, 3
0x180064ad6  movdqu  cs:ptpp, xmm0
0x180064ade  mov     cs:stru_1800CC278.CleanupGroupCancelCallback, 0
0x180064ae9  movdqu  xmmword ptr cs:stru_1800CC278.Pool, xmm1
0x180064af1  mov     cs:stru_1800CC278.FinalizationCallback, 0
0x180064afc  movdqu  xmmword ptr cs:stru_1800CC278.RaceDll, xmm0
0x180064b04  mov     dword ptr cs:stru_1800CC278.u, 0
0x180064b0e  mov     cs:stru_1800CC278.CallbackPriority, 1
0x180064b18  mov     cs:stru_1800CC278.Size, 48h ; 'H'
0x180064b22  call    cs:__imp_CreateThreadpool
0x180064b29  nop     dword ptr [rax+rax+00h]
0x180064b2e  mov     qword ptr cs:ptpp, rax
0x180064b35  test    rax, rax
0x180064b38  jnz     short loc_180064B6A
0x180064b3a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180064b41  jz      loc_180064C17
0x180064b47  mov     [rsp+38h+var_18], 11B7h
0x180064b4f  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180064b56  xor     r8d, r8d
0x180064b59  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180064b60  call    McTemplateU0psq_EventWriteTransfer
0x180064b65  jmp     loc_180064C17
0x180064b6a  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180064b71  nop     dword ptr [rax+rax+00h]
0x180064b76  mov     qword ptr cs:ptpp+8, rax
0x180064b7d  test    rax, rax
0x180064b80  jnz     short loc_180064B99
0x180064b82  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180064b89  jz      loc_180064C17
0x180064b8f  mov     [rsp+38h+var_18], 11C2h
0x180064b97  jmp     short loc_180064B4F
0x180064b99  mov     rax, qword ptr cs:ptpp
0x180064ba0  lea     rcx, stru_1800CC2D0; lpCriticalSection
0x180064ba7  mov     cs:stru_1800CC278.Pool, rax
0x180064bae  mov     rax, qword ptr cs:ptpp+8
0x180064bb5  mov     cs:stru_1800CC278.CleanupGroup, rax
0x180064bbc  mov     cs:stru_1800CC278.CleanupGroupCancelCallback, 0
0x180064bc7  call    cs:__imp_InitializeCriticalSection
0x180064bce  nop     dword ptr [rax+rax+00h]
0x180064bd3  lea     rax, qword_1800CC268
0x180064bda  mov     cs:byte_1800CC2F8, 1
0x180064be1  xor     r8d, r8d; pcbe
0x180064be4  mov     cs:qword_1800CC270, rax
0x180064beb  xor     edx, edx; pv
0x180064bed  mov     cs:qword_1800CC268, rax
0x180064bf4  lea     rcx, IpTlsSqmServerData; pfnti
0x180064bfb  call    cs:__imp_CreateThreadpoolTimer
0x180064c02  nop     dword ptr [rax+rax+00h]
0x180064c07  mov     cs:g_IpTlsSqmServerTimer, rax
0x180064c0e  test    rax, rax
0x180064c11  jnz     loc_180064CB7
0x180064c17  mov     rcx, qword ptr cs:ptpp+8; ptpcg
0x180064c1e  test    rcx, rcx
0x180064c21  jz      short loc_180064C3A
0x180064c23  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180064c2a  nop     dword ptr [rax+rax+00h]
0x180064c2f  mov     qword ptr cs:ptpp+8, 0
0x180064c3a  mov     rcx, qword ptr cs:ptpp; ptpp
0x180064c41  test    rcx, rcx
0x180064c44  jz      short loc_180064C5D
0x180064c46  call    cs:__imp_CloseThreadpool
0x180064c4d  nop     dword ptr [rax+rax+00h]
0x180064c52  mov     qword ptr cs:ptpp, 0
0x180064c5d  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x180064c64  test    rcx, rcx
0x180064c67  jz      short loc_180064CB3
0x180064c69  xor     r9d, r9d; msWindowLength
0x180064c6c  xor     r8d, r8d; msPeriod
0x180064c6f  xor     edx, edx; pftDueTime
0x180064c71  call    cs:__imp_SetThreadpoolTimer
0x180064c78  nop     dword ptr [rax+rax+00h]
0x180064c7d  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x180064c84  mov     edx, 1; fCancelPendingCallbacks
0x180064c89  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180064c90  nop     dword ptr [rax+rax+00h]
0x180064c95  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x180064c9c  call    cs:__imp_CloseThreadpoolTimer
0x180064ca3  nop     dword ptr [rax+rax+00h]
0x180064ca8  mov     cs:g_IpTlsSqmServerTimer, 0
0x180064cb3  xor     al, al
0x180064cb5  jmp     short loc_180064CEA
0x180064cb7  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x180064cbe  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180064cc3  xor     r9d, r9d; msWindowLength
0x180064cc6  mov     [rsp+38h+pftDueTime.dwHighDateTime], 0FFFFFFF7h
0x180064cce  mov     r8d, 36EE80h; msPeriod
0x180064cd4  mov     [rsp+38h+pftDueTime.dwLowDateTime], 9E3B9800h
0x180064cdc  call    cs:__imp_SetThreadpoolTimer
0x180064ce3  nop     dword ptr [rax+rax+00h]
0x180064ce8  mov     al, 1
0x180064cea  add     rsp, 38h
0x180064cee  retn
```
