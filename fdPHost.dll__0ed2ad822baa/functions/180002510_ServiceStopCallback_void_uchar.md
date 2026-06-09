# ServiceStopCallback(void *,uchar)

- ea: `0x180002510`
- end: `0x18000270b`
- name: `?ServiceStopCallback@@YAXPEAXE@Z`
- size: `507`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800021f0`

## callees

- `0x180002510`
- `0x18000284c`
- `0x180002a00`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002690`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002653`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800025a5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800026d8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800025a5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800026d8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002567`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002567`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800026a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800026a2`
- `KERNEL32!UnregisterWait` at `0x180002637`
- `KERNEL32!UnregisterWait` at `0x180002637`

## pseudocode

```c
void __fastcall ServiceStopCallback(void *a1)
{
  char i; // al

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids);
  _m_prefetchw((const void *)&g_ServiceControlFlags);
  for ( i = _InterlockedOr(&g_ServiceControlFlags, 1u); (i & 2) != 0; i = _InterlockedOr(&g_ServiceControlFlags, 1u) )
  {
    Sleep(0x32u);
    _m_prefetchw((const void *)&g_ServiceControlFlags);
  }
  ServiceStatus.dwCurrentState = 3;
  SetServiceStatus(hServiceStatus, &ServiceStatus);
  if ( g_pIContextCallback )
  {
    if ( (*(unsigned int (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)g_pIContextCallback + 24LL))(
           g_pIContextCallback,
           DisconnectCallback,
           0,
           &IID_IContextCallback,
           5,
           0)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pIContextCallback + 16LL))(g_pIContextCallback);
    g_pIContextCallback = 0;
  }
  if ( g_hServiceStopCallback )
  {
    if ( !UnregisterWait(g_hServiceStopCallback)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      GetLastError();
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28);
    }
    g_hServiceStopCallback = 0;
  }
  EnterCriticalSection(&g_hServiceStopEventLock);
  if ( g_hServiceStopEvent )
  {
    CloseHandle(g_hServiceStopEvent);
    g_hServiceStopEvent = 0;
  }
  LeaveCriticalSection(&g_hServiceStopEventLock);
  ServiceStatus.dwCurrentState = 1;
  SetServiceStatus(hServiceStatus, &ServiceStatus);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids);
}

```

## disassembly

```asm
0x180002510  push    rdi
0x180002512  sub     rsp, 40h
0x180002516  mov     rcx, cs:WPP_GLOBAL_Control
0x18000251d  lea     rdi, WPP_GLOBAL_Control
0x180002524  cmp     rcx, rdi
0x180002527  jz      short loc_180002544
0x180002529  cmp     byte ptr [rcx+19h], 4
0x18000252d  jb      short loc_180002544
0x18000252f  mov     rcx, [rcx+10h]
0x180002533  lea     r8, WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids
0x18000253a  mov     edx, 1Ah
0x18000253f  call    WPP_SF_s
0x180002544  prefetchw byte ptr cs:?g_ServiceControlFlags@@3JC; long volatile g_ServiceControlFlags
0x18000254b  mov     eax, cs:?g_ServiceControlFlags@@3JC; long volatile g_ServiceControlFlags
0x180002551  mov     ecx, eax
0x180002553  or      ecx, 1
0x180002556  lock cmpxchg cs:?g_ServiceControlFlags@@3JC, ecx; long volatile g_ServiceControlFlags
0x18000255e  jnz     short loc_180002551
0x180002560  jmp     short loc_180002589
0x180002562  mov     ecx, 32h ; '2'; dwMilliseconds
0x180002567  call    cs:__imp_Sleep
0x18000256d  prefetchw byte ptr cs:?g_ServiceControlFlags@@3JC; long volatile g_ServiceControlFlags
0x180002574  mov     eax, cs:?g_ServiceControlFlags@@3JC; long volatile g_ServiceControlFlags
0x18000257a  mov     ecx, eax
0x18000257c  or      ecx, 1
0x18000257f  lock cmpxchg cs:?g_ServiceControlFlags@@3JC, ecx; long volatile g_ServiceControlFlags
0x180002587  jnz     short loc_18000257A
0x180002589  test    al, 2
0x18000258b  jnz     short loc_180002562
0x18000258d  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180002594  lea     rdx, ServiceStatus; lpServiceStatus
0x18000259b  mov     cs:ServiceStatus.dwCurrentState, 3
0x1800025a5  call    cs:__imp_SetServiceStatus
0x1800025ab  mov     rcx, cs:?g_pIContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * g_pIContextCallback
0x1800025b2  test    rcx, rcx
0x1800025b5  jz      short loc_18000262B
0x1800025b7  mov     rax, [rcx]
0x1800025ba  lea     r9, IID_IContextCallback
0x1800025c1  mov     [rsp+48h+var_20], 0
0x1800025ca  lea     rdx, ?DisconnectCallback@@YAJPEAUtagComCallData@@@Z; DisconnectCallback(tagComCallData *)
0x1800025d1  xor     r8d, r8d
0x1800025d4  mov     [rsp+48h+var_28], 5
0x1800025dc  mov     rax, [rax+18h]
0x1800025e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e5  test    eax, eax
0x1800025e7  jz      short loc_18000260D
0x1800025e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025f0  cmp     rcx, rdi
0x1800025f3  jz      short loc_18000260D
0x1800025f5  cmp     byte ptr [rcx+19h], 3
0x1800025f9  jb      short loc_18000260D
0x1800025fb  mov     rcx, [rcx+10h]
0x1800025ff  mov     edx, 1Bh
0x180002604  mov     [rsp+48h+var_28], eax
0x180002608  call    WPP_SF_sd
0x18000260d  mov     rcx, cs:?g_pIContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * g_pIContextCallback
0x180002614  mov     rax, [rcx]
0x180002617  mov     rax, [rax+10h]
0x18000261b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002620  mov     cs:?g_pIContextCallback@@3PEAUIContextCallback@@EA, 0; IContextCallback * g_pIContextCallback
0x18000262b  mov     rcx, cs:?g_hServiceStopCallback@@3PEAXEA; WaitHandle
0x180002632  test    rcx, rcx
0x180002635  jz      short loc_180002689
0x180002637  call    cs:__imp_UnregisterWait
0x18000263d  test    eax, eax
0x18000263f  jnz     short loc_18000267E
0x180002641  mov     rax, cs:WPP_GLOBAL_Control
0x180002648  cmp     rax, rdi
0x18000264b  jz      short loc_18000267E
0x18000264d  cmp     byte ptr [rax+19h], 3
0x180002651  jb      short loc_18000267E
0x180002653  call    cs:__imp_GetLastError
0x180002659  test    eax, eax
0x18000265b  jle     short loc_180002665
0x18000265d  movzx   eax, ax
0x180002660  or      eax, 80070000h
0x180002665  mov     rcx, cs:WPP_GLOBAL_Control
0x18000266c  mov     edx, 1Ch
0x180002671  mov     [rsp+48h+var_28], eax
0x180002675  mov     rcx, [rcx+10h]
0x180002679  call    WPP_SF_sd
0x18000267e  mov     cs:?g_hServiceStopCallback@@3PEAXEA, 0; void * g_hServiceStopCallback
0x180002689  lea     rcx, ?g_hServiceStopEventLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002690  call    cs:__imp_EnterCriticalSection
0x180002696  mov     rcx, cs:?g_hServiceStopEvent@@3PEAXEA; hObject
0x18000269d  test    rcx, rcx
0x1800026a0  jz      short loc_1800026B3
0x1800026a2  call    cs:__imp_CloseHandle
0x1800026a8  mov     cs:?g_hServiceStopEvent@@3PEAXEA, 0; void * g_hServiceStopEvent
0x1800026b3  lea     rcx, ?g_hServiceStopEventLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800026ba  call    cs:__imp_LeaveCriticalSection
0x1800026c0  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800026c7  lea     rdx, ServiceStatus; lpServiceStatus
0x1800026ce  mov     cs:ServiceStatus.dwCurrentState, 1
0x1800026d8  call    cs:__imp_SetServiceStatus
0x1800026de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026e5  cmp     rcx, rdi
0x1800026e8  jz      short loc_180002705
0x1800026ea  cmp     byte ptr [rcx+19h], 4
0x1800026ee  jb      short loc_180002705
0x1800026f0  mov     rcx, [rcx+10h]
0x1800026f4  lea     r8, WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids
0x1800026fb  mov     edx, 1Dh
0x180002700  call    WPP_SF_s
0x180002705  add     rsp, 40h
0x180002709  pop     rdi
0x18000270a  retn
```
