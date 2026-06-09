# InitializeHttpServer

- ea: `0x180064a8c`
- end: `0x180064cd0`
- name: `InitializeHttpServer`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003ce4`

## callees

- `0x180061694`
- `0x180064a8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180064ba7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180064ba7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180064b02`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180064b02`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180064c03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180064c03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180064c26`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180064c26`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064bdb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180064bdb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180064c69`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180064c69`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064c7c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064c7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180064b4a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180064b4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064c51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064cbc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064c51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064cbc`

## string_xrefs

- `0x180064b2f`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

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
0x180064a8c  sub     rsp, 38h
0x180064a90  xorps   xmm0, xmm0
0x180064a93  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0
0x180064a9c  xorps   xmm1, xmm1
0x180064a9f  mov     cs:g_IpTlsSqmServerTimer, 0
0x180064aaa  xor     ecx, ecx; reserved
0x180064aac  mov     cs:stru_1800CC278.Version, 3
0x180064ab6  movdqu  cs:ptpp, xmm0
0x180064abe  mov     cs:stru_1800CC278.CleanupGroupCancelCallback, 0
0x180064ac9  movdqu  xmmword ptr cs:stru_1800CC278.Pool, xmm1
0x180064ad1  mov     cs:stru_1800CC278.FinalizationCallback, 0
0x180064adc  movdqu  xmmword ptr cs:stru_1800CC278.RaceDll, xmm0
0x180064ae4  mov     dword ptr cs:stru_1800CC278.u, 0
0x180064aee  mov     cs:stru_1800CC278.CallbackPriority, 1
0x180064af8  mov     cs:stru_1800CC278.Size, 48h ; 'H'
0x180064b02  call    cs:__imp_CreateThreadpool
0x180064b09  nop     dword ptr [rax+rax+00h]
0x180064b0e  mov     qword ptr cs:ptpp, rax
0x180064b15  test    rax, rax
0x180064b18  jnz     short loc_180064B4A
0x180064b1a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180064b21  jz      loc_180064BF7
0x180064b27  mov     [rsp+38h+var_18], 11B7h
0x180064b2f  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180064b36  xor     r8d, r8d
0x180064b39  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_MEMORY_FAILURE
0x180064b40  call    McTemplateU0psq_EventWriteTransfer
0x180064b45  jmp     loc_180064BF7
0x180064b4a  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180064b51  nop     dword ptr [rax+rax+00h]
0x180064b56  mov     qword ptr cs:ptpp+8, rax
0x180064b5d  test    rax, rax
0x180064b60  jnz     short loc_180064B79
0x180064b62  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x180064b69  jz      loc_180064BF7
0x180064b6f  mov     [rsp+38h+var_18], 11C2h
0x180064b77  jmp     short loc_180064B2F
0x180064b79  mov     rax, qword ptr cs:ptpp
0x180064b80  lea     rcx, stru_1800CC2D0; lpCriticalSection
0x180064b87  mov     cs:stru_1800CC278.Pool, rax
0x180064b8e  mov     rax, qword ptr cs:ptpp+8
0x180064b95  mov     cs:stru_1800CC278.CleanupGroup, rax
0x180064b9c  mov     cs:stru_1800CC278.CleanupGroupCancelCallback, 0
0x180064ba7  call    cs:__imp_InitializeCriticalSection
0x180064bae  nop     dword ptr [rax+rax+00h]
0x180064bb3  lea     rax, qword_1800CC268
0x180064bba  mov     cs:byte_1800CC2F8, 1
0x180064bc1  xor     r8d, r8d; pcbe
0x180064bc4  mov     cs:qword_1800CC270, rax
0x180064bcb  xor     edx, edx; pv
0x180064bcd  mov     cs:qword_1800CC268, rax
0x180064bd4  lea     rcx, IpTlsSqmServerData; pfnti
0x180064bdb  call    cs:__imp_CreateThreadpoolTimer
0x180064be2  nop     dword ptr [rax+rax+00h]
0x180064be7  mov     cs:g_IpTlsSqmServerTimer, rax
0x180064bee  test    rax, rax
0x180064bf1  jnz     loc_180064C97
0x180064bf7  mov     rcx, qword ptr cs:ptpp+8; ptpcg
0x180064bfe  test    rcx, rcx
0x180064c01  jz      short loc_180064C1A
0x180064c03  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180064c0a  nop     dword ptr [rax+rax+00h]
0x180064c0f  mov     qword ptr cs:ptpp+8, 0
0x180064c1a  mov     rcx, qword ptr cs:ptpp; ptpp
0x180064c21  test    rcx, rcx
0x180064c24  jz      short loc_180064C3D
0x180064c26  call    cs:__imp_CloseThreadpool
0x180064c2d  nop     dword ptr [rax+rax+00h]
0x180064c32  mov     qword ptr cs:ptpp, 0
0x180064c3d  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x180064c44  test    rcx, rcx
0x180064c47  jz      short loc_180064C93
0x180064c49  xor     r9d, r9d; msWindowLength
0x180064c4c  xor     r8d, r8d; msPeriod
0x180064c4f  xor     edx, edx; pftDueTime
0x180064c51  call    cs:__imp_SetThreadpoolTimer
0x180064c58  nop     dword ptr [rax+rax+00h]
0x180064c5d  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x180064c64  mov     edx, 1; fCancelPendingCallbacks
0x180064c69  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180064c70  nop     dword ptr [rax+rax+00h]
0x180064c75  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x180064c7c  call    cs:__imp_CloseThreadpoolTimer
0x180064c83  nop     dword ptr [rax+rax+00h]
0x180064c88  mov     cs:g_IpTlsSqmServerTimer, 0
0x180064c93  xor     al, al
0x180064c95  jmp     short loc_180064CCA
0x180064c97  mov     rcx, cs:g_IpTlsSqmServerTimer; pti
0x180064c9e  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180064ca3  xor     r9d, r9d; msWindowLength
0x180064ca6  mov     [rsp+38h+pftDueTime.dwHighDateTime], 0FFFFFFF7h
0x180064cae  mov     r8d, 36EE80h; msPeriod
0x180064cb4  mov     [rsp+38h+pftDueTime.dwLowDateTime], 9E3B9800h
0x180064cbc  call    cs:__imp_SetThreadpoolTimer
0x180064cc3  nop     dword ptr [rax+rax+00h]
0x180064cc8  mov     al, 1
0x180064cca  add     rsp, 38h
0x180064cce  retn
```
