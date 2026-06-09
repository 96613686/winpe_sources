# CUtils::Destroy(void)

- ea: `0x18008333c`
- end: `0x1800834e3`
- name: `?Destroy@CUtils@@SAXXZ`
- size: `423`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f7c0`
- `0x1800533ec`

## callees

- `0x1800077a0`
- `0x18004f174`
- `0x18008333c`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180083352`
- `ntdll!RtlFreeSid` at `0x180083375`
- `ntdll!RtlFreeSid` at `0x180083398`
- `ntdll!RtlFreeSid` at `0x180083352`
- `ntdll!RtlFreeSid` at `0x180083375`
- `ntdll!RtlFreeSid` at `0x180083398`
- `ntdll!RtlDeleteResource` at `0x180083451`
- `ntdll!RtlDeleteResource` at `0x180083451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083497`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800833bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800833de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083401`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083424`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800833bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800833de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083401`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083424`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180083487`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180083487`

## pseudocode

```c
void CUtils::Destroy(void)
{
  _DWORD *v0; // rbx
  signed int LastError; // eax

  if ( CUtils::pSystemSid )
  {
    RtlFreeSid(CUtils::pSystemSid);
    CUtils::pSystemSid = 0;
  }
  if ( CUtils::pAdminSid )
  {
    RtlFreeSid(CUtils::pAdminSid);
    CUtils::pAdminSid = 0;
  }
  if ( CUtils::pAnonymousSid )
  {
    RtlFreeSid(CUtils::pAnonymousSid);
    CUtils::pAnonymousSid = 0;
  }
  if ( CUtils::pNetworkServiceSid )
  {
    LocalFree(CUtils::pNetworkServiceSid);
    CUtils::pNetworkServiceSid = 0;
  }
  if ( CUtils::pRdsMsSid )
  {
    LocalFree(CUtils::pRdsMsSid);
    CUtils::pRdsMsSid = 0;
  }
  if ( CUtils::pAppContainerSid )
  {
    LocalFree(CUtils::pAppContainerSid);
    CUtils::pAppContainerSid = 0;
  }
  if ( CUtils::pLPACCapabilitySid )
  {
    LocalFree(CUtils::pLPACCapabilitySid);
    CUtils::pLPACCapabilitySid = 0;
  }
  v0 = g_pObjectTracker;
  if ( g_pObjectTracker )
  {
    if ( *((_DWORD *)g_pObjectTracker + 30) )
      RtlDeleteResource((PRTL_RESOURCE)((char *)g_pObjectTracker + 24));
    v0[30] = 0;
    operator delete(v0);
    g_pObjectTracker = 0;
  }
  if ( COpsMonitorBase::g_OpsMonitorTimeQueue )
  {
    if ( !DeleteTimerQueueEx(COpsMonitorBase::g_OpsMonitorTimeQueue, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( (g_DebugTraceComponent & 0x40) != 0 )
        _DbgPrintMessage(2, "COpsMonitorBase::Destroy() failed with 0x%08x", LastError);
    }
    COpsMonitorBase::g_OpsMonitorTimeQueue = 0;
  }
}

```

## disassembly

```asm
0x18008333c  mov     [rsp+arg_0], rbx
0x180083341  push    rdi
0x180083342  sub     rsp, 20h
0x180083346  mov     rcx, cs:?pSystemSid@CUtils@@0PEAXEA; Sid
0x18008334d  test    rcx, rcx
0x180083350  jz      short loc_180083369
0x180083352  call    cs:__imp_RtlFreeSid
0x180083359  nop     dword ptr [rax+rax+00h]
0x18008335e  mov     cs:?pSystemSid@CUtils@@0PEAXEA, 0; void * CUtils::pSystemSid
0x180083369  mov     rcx, cs:?pAdminSid@CUtils@@0PEAXEA; Sid
0x180083370  test    rcx, rcx
0x180083373  jz      short loc_18008338C
0x180083375  call    cs:__imp_RtlFreeSid
0x18008337c  nop     dword ptr [rax+rax+00h]
0x180083381  mov     cs:?pAdminSid@CUtils@@0PEAXEA, 0; void * CUtils::pAdminSid
0x18008338c  mov     rcx, cs:?pAnonymousSid@CUtils@@0PEAXEA; Sid
0x180083393  test    rcx, rcx
0x180083396  jz      short loc_1800833AF
0x180083398  call    cs:__imp_RtlFreeSid
0x18008339f  nop     dword ptr [rax+rax+00h]
0x1800833a4  mov     cs:?pAnonymousSid@CUtils@@0PEAXEA, 0; void * CUtils::pAnonymousSid
0x1800833af  mov     rcx, cs:?pNetworkServiceSid@CUtils@@0PEAXEA; hMem
0x1800833b6  test    rcx, rcx
0x1800833b9  jz      short loc_1800833D2
0x1800833bb  call    cs:__imp_LocalFree
0x1800833c2  nop     dword ptr [rax+rax+00h]
0x1800833c7  mov     cs:?pNetworkServiceSid@CUtils@@0PEAXEA, 0; void * CUtils::pNetworkServiceSid
0x1800833d2  mov     rcx, cs:?pRdsMsSid@CUtils@@0PEAXEA; hMem
0x1800833d9  test    rcx, rcx
0x1800833dc  jz      short loc_1800833F5
0x1800833de  call    cs:__imp_LocalFree
0x1800833e5  nop     dword ptr [rax+rax+00h]
0x1800833ea  mov     cs:?pRdsMsSid@CUtils@@0PEAXEA, 0; void * CUtils::pRdsMsSid
0x1800833f5  mov     rcx, cs:?pAppContainerSid@CUtils@@0PEAXEA; hMem
0x1800833fc  test    rcx, rcx
0x1800833ff  jz      short loc_180083418
0x180083401  call    cs:__imp_LocalFree
0x180083408  nop     dword ptr [rax+rax+00h]
0x18008340d  mov     cs:?pAppContainerSid@CUtils@@0PEAXEA, 0; void * CUtils::pAppContainerSid
0x180083418  mov     rcx, cs:?pLPACCapabilitySid@CUtils@@0PEAXEA; hMem
0x18008341f  test    rcx, rcx
0x180083422  jz      short loc_18008343B
0x180083424  call    cs:__imp_LocalFree
0x18008342b  nop     dword ptr [rax+rax+00h]
0x180083430  mov     cs:?pLPACCapabilitySid@CUtils@@0PEAXEA, 0; void * CUtils::pLPACCapabilitySid
0x18008343b  mov     rbx, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x180083442  test    rbx, rbx
0x180083445  jz      short loc_180083477
0x180083447  cmp     dword ptr [rbx+78h], 0
0x18008344b  jz      short loc_18008345D
0x18008344d  lea     rcx, [rbx+18h]; Resource
0x180083451  call    cs:__imp_RtlDeleteResource
0x180083458  nop     dword ptr [rax+rax+00h]
0x18008345d  mov     rcx, rbx; Block
0x180083460  mov     dword ptr [rbx+78h], 0
0x180083467  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008346c  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, 0; CObjectTracker * g_pObjectTracker
0x180083477  mov     rcx, cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA; TimerQueue
0x18008347e  test    rcx, rcx
0x180083481  jz      short loc_1800834D7
0x180083483  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180083487  call    cs:__imp_DeleteTimerQueueEx
0x18008348e  nop     dword ptr [rax+rax+00h]
0x180083493  test    eax, eax
0x180083495  jnz     short loc_1800834CC
0x180083497  call    cs:__imp_GetLastError
0x18008349e  nop     dword ptr [rax+rax+00h]
0x1800834a3  test    eax, eax
0x1800834a5  jle     short loc_1800834AF
0x1800834a7  movzx   eax, ax
0x1800834aa  or      eax, 80070000h
0x1800834af  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 40h; ulong g_DebugTraceComponent
0x1800834b6  jz      short loc_1800834CC
0x1800834b8  mov     r8d, eax
0x1800834bb  lea     rdx, aCopsmonitorbas_0; "COpsMonitorBase::Destroy() failed with "...
0x1800834c2  mov     ecx, 2; int
0x1800834c7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800834cc  mov     cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA, 0; void * COpsMonitorBase::g_OpsMonitorTimeQueue
0x1800834d7  mov     rbx, [rsp+28h+arg_0]
0x1800834dc  add     rsp, 20h
0x1800834e0  pop     rdi
0x1800834e1  retn
```
