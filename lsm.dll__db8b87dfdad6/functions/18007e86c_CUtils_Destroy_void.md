# CUtils::Destroy(void)

- ea: `0x18007e86c`
- end: `0x18007e9d6`
- name: `?Destroy@CUtils@@SAXXZ`
- size: `362`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002d804`
- `0x18004fde0`

## callees

- `0x1800074c0`
- `0x18004bd84`
- `0x18007e86c`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18007e882`
- `ntdll!RtlFreeSid` at `0x18007e89f`
- `ntdll!RtlFreeSid` at `0x18007e8bc`
- `ntdll!RtlFreeSid` at `0x18007e882`
- `ntdll!RtlFreeSid` at `0x18007e89f`
- `ntdll!RtlFreeSid` at `0x18007e8bc`
- `ntdll!RtlDeleteResource` at `0x18007e957`
- `ntdll!RtlDeleteResource` at `0x18007e957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e8d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e8f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e913`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e930`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e8d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e8f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e913`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e930`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18007e987`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18007e987`

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
0x18007e86c  mov     [rsp+arg_0], rbx
0x18007e871  push    rdi
0x18007e872  sub     rsp, 20h
0x18007e876  mov     rcx, cs:?pSystemSid@CUtils@@0PEAXEA; Sid
0x18007e87d  test    rcx, rcx
0x18007e880  jz      short loc_18007E893
0x18007e882  call    cs:__imp_RtlFreeSid
0x18007e888  mov     cs:?pSystemSid@CUtils@@0PEAXEA, 0; void * CUtils::pSystemSid
0x18007e893  mov     rcx, cs:?pAdminSid@CUtils@@0PEAXEA; Sid
0x18007e89a  test    rcx, rcx
0x18007e89d  jz      short loc_18007E8B0
0x18007e89f  call    cs:__imp_RtlFreeSid
0x18007e8a5  mov     cs:?pAdminSid@CUtils@@0PEAXEA, 0; void * CUtils::pAdminSid
0x18007e8b0  mov     rcx, cs:?pAnonymousSid@CUtils@@0PEAXEA; Sid
0x18007e8b7  test    rcx, rcx
0x18007e8ba  jz      short loc_18007E8CD
0x18007e8bc  call    cs:__imp_RtlFreeSid
0x18007e8c2  mov     cs:?pAnonymousSid@CUtils@@0PEAXEA, 0; void * CUtils::pAnonymousSid
0x18007e8cd  mov     rcx, cs:?pNetworkServiceSid@CUtils@@0PEAXEA; hMem
0x18007e8d4  test    rcx, rcx
0x18007e8d7  jz      short loc_18007E8EA
0x18007e8d9  call    cs:__imp_LocalFree
0x18007e8df  mov     cs:?pNetworkServiceSid@CUtils@@0PEAXEA, 0; void * CUtils::pNetworkServiceSid
0x18007e8ea  mov     rcx, cs:?pRdsMsSid@CUtils@@0PEAXEA; hMem
0x18007e8f1  test    rcx, rcx
0x18007e8f4  jz      short loc_18007E907
0x18007e8f6  call    cs:__imp_LocalFree
0x18007e8fc  mov     cs:?pRdsMsSid@CUtils@@0PEAXEA, 0; void * CUtils::pRdsMsSid
0x18007e907  mov     rcx, cs:?pAppContainerSid@CUtils@@0PEAXEA; hMem
0x18007e90e  test    rcx, rcx
0x18007e911  jz      short loc_18007E924
0x18007e913  call    cs:__imp_LocalFree
0x18007e919  mov     cs:?pAppContainerSid@CUtils@@0PEAXEA, 0; void * CUtils::pAppContainerSid
0x18007e924  mov     rcx, cs:?pLPACCapabilitySid@CUtils@@0PEAXEA; hMem
0x18007e92b  test    rcx, rcx
0x18007e92e  jz      short loc_18007E941
0x18007e930  call    cs:__imp_LocalFree
0x18007e936  mov     cs:?pLPACCapabilitySid@CUtils@@0PEAXEA, 0; void * CUtils::pLPACCapabilitySid
0x18007e941  mov     rbx, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA; CObjectTracker * g_pObjectTracker
0x18007e948  test    rbx, rbx
0x18007e94b  jz      short loc_18007E977
0x18007e94d  cmp     dword ptr [rbx+78h], 0
0x18007e951  jz      short loc_18007E95D
0x18007e953  lea     rcx, [rbx+18h]; Resource
0x18007e957  call    cs:__imp_RtlDeleteResource
0x18007e95d  mov     rcx, rbx; Block
0x18007e960  mov     dword ptr [rbx+78h], 0
0x18007e967  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007e96c  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, 0; CObjectTracker * g_pObjectTracker
0x18007e977  mov     rcx, cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA; TimerQueue
0x18007e97e  test    rcx, rcx
0x18007e981  jz      short loc_18007E9CB
0x18007e983  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18007e987  call    cs:__imp_DeleteTimerQueueEx
0x18007e98d  test    eax, eax
0x18007e98f  jnz     short loc_18007E9C0
0x18007e991  call    cs:__imp_GetLastError
0x18007e997  test    eax, eax
0x18007e999  jle     short loc_18007E9A3
0x18007e99b  movzx   eax, ax
0x18007e99e  or      eax, 80070000h
0x18007e9a3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 40h; ulong g_DebugTraceComponent
0x18007e9aa  jz      short loc_18007E9C0
0x18007e9ac  mov     r8d, eax
0x18007e9af  lea     rdx, aCopsmonitorbas_0; "COpsMonitorBase::Destroy() failed with "...
0x18007e9b6  mov     ecx, 2; int
0x18007e9bb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007e9c0  mov     cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA, 0; void * COpsMonitorBase::g_OpsMonitorTimeQueue
0x18007e9cb  mov     rbx, [rsp+28h+arg_0]
0x18007e9d0  add     rsp, 20h
0x18007e9d4  pop     rdi
0x18007e9d5  retn
```
