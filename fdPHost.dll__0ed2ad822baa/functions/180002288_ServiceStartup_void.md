# ServiceStartup(void)

- ea: `0x180002288`
- end: `0x1800024ff`
- name: `?ServiceStartup@@YAJXZ`
- size: `631`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800021f0`

## callees

- `0x180002288`
- `0x18000284c`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000236f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000236f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002341`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002341`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000232e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002460`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000232e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002460`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800023a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002400`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800023a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002353`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800022f5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800024ec`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800022f5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800024ec`

## pseudocode

```c
__int64 ServiceStartup(void)
{
  int Instance; // ebx
  signed int LastError; // eax
  signed int v2; // eax
  int v3; // edi
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids);
  ServiceStatus.dwServiceType = 48;
  Instance = 0;
  ServiceStatus.dwCurrentState = 2;
  *(_OWORD *)&ServiceStatus.dwControlsAccepted = 0;
  ServiceStatus.dwWaitHint = 0;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    LastError = GetLastError();
    Instance = LastError;
    if ( LastError > 0 )
      Instance = (unsigned __int16)LastError | 0x80070000;
  }
  g_arydwRegister = 0;
  if ( !Instance )
  {
    EnterCriticalSection(&g_hServiceStopEventLock);
    g_hServiceStopEvent = CreateEventW(0, 1, 0, 0);
    if ( !g_hServiceStopEvent )
    {
      v2 = GetLastError();
      Instance = v2;
      if ( v2 > 0 )
        Instance = (unsigned __int16)v2 | 0x80070000;
    }
    LeaveCriticalSection(&g_hServiceStopEventLock);
    if ( !Instance )
    {
      ppv = 0;
      Instance = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
      if ( Instance >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      if ( !Instance )
      {
        Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &IID_IContextCallback, &g_pIContextCallback);
        if ( !Instance )
        {
          Instance = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)g_pIContextCallback + 24LL))(
                       g_pIContextCallback,
                       ConnectCallback,
                       0,
                       &IID_IContextCallback,
                       5,
                       0);
          if ( !Instance )
          {
            if ( g_pSvchostGlobalData
              && (EnterCriticalSection(&g_hServiceStopEventLock),
                  v3 = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_pSvchostGlobalData
                        + 24))(
                         &g_hServiceStopCallback,
                         L"fdPHost",
                         g_hServiceStopEvent,
                         ServiceStopCallback,
                         0,
                         8),
                  LeaveCriticalSection(&g_hServiceStopEventLock),
                  v3) )
            {
              if ( v3 > 0 )
                return (unsigned __int16)v3 | 0x80070000;
              else
                return (unsigned int)v3;
            }
            else
            {
              ServiceStatus.dwCurrentState = 4;
              ServiceStatus.dwControlsAccepted = 129;
              SetServiceStatus(hServiceStatus, &ServiceStatus);
            }
          }
        }
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180002288  mov     [rsp+arg_8], rbx
0x18000228d  push    rdi
0x18000228e  sub     rsp, 40h
0x180002292  mov     rcx, cs:WPP_GLOBAL_Control
0x180002299  lea     rax, WPP_GLOBAL_Control
0x1800022a0  cmp     rcx, rax
0x1800022a3  jz      short loc_1800022C0
0x1800022a5  cmp     byte ptr [rcx+19h], 4
0x1800022a9  jb      short loc_1800022C0
0x1800022ab  mov     rcx, [rcx+10h]
0x1800022af  lea     r8, WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids
0x1800022b6  mov     edx, 18h
0x1800022bb  call    WPP_SF_s
0x1800022c0  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800022c7  lea     rdx, ServiceStatus; lpServiceStatus
0x1800022ce  xorps   xmm0, xmm0
0x1800022d1  mov     cs:ServiceStatus.dwServiceType, 30h ; '0'
0x1800022db  xor     ebx, ebx
0x1800022dd  mov     cs:ServiceStatus.dwCurrentState, 2
0x1800022e7  movdqu  xmmword ptr cs:ServiceStatus.dwControlsAccepted, xmm0
0x1800022ef  mov     cs:ServiceStatus.dwWaitHint, ebx
0x1800022f5  call    cs:__imp_SetServiceStatus
0x1800022fb  test    eax, eax
0x1800022fd  jnz     short loc_180002314
0x1800022ff  call    cs:__imp_GetLastError
0x180002305  mov     ebx, eax
0x180002307  test    eax, eax
0x180002309  jle     short loc_180002314
0x18000230b  movzx   ebx, ax
0x18000230e  or      ebx, 80070000h
0x180002314  mov     cs:?g_arydwRegister@@3PAKA, 0; ulong near * g_arydwRegister
0x18000231f  test    ebx, ebx
0x180002321  jnz     loc_1800024F2
0x180002327  lea     rcx, ?g_hServiceStopEventLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000232e  call    cs:__imp_EnterCriticalSection
0x180002334  lea     edi, [rbx+1]
0x180002337  xor     r9d, r9d; lpName
0x18000233a  mov     edx, edi; bManualReset
0x18000233c  xor     r8d, r8d; bInitialState
0x18000233f  xor     ecx, ecx; lpEventAttributes
0x180002341  call    cs:__imp_CreateEventW
0x180002347  mov     cs:?g_hServiceStopEvent@@3PEAXEA, rax; void * g_hServiceStopEvent
0x18000234e  test    rax, rax
0x180002351  jnz     short loc_180002368
0x180002353  call    cs:__imp_GetLastError
0x180002359  mov     ebx, eax
0x18000235b  test    eax, eax
0x18000235d  jle     short loc_180002368
0x18000235f  movzx   ebx, ax
0x180002362  or      ebx, 80070000h
0x180002368  lea     rcx, ?g_hServiceStopEventLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000236f  call    cs:__imp_LeaveCriticalSection
0x180002375  test    ebx, ebx
0x180002377  jnz     loc_1800024F2
0x18000237d  lea     rax, [rsp+48h+arg_0]
0x180002382  mov     [rsp+48h+arg_0], 0
0x18000238b  lea     r9, IID_IGlobalOptions; riid
0x180002392  mov     [rsp+48h+ppv], rax; ppv
0x180002397  mov     r8d, edi; dwClsContext
0x18000239a  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800023a1  xor     edx, edx; pUnkOuter
0x1800023a3  call    cs:__imp_CoCreateInstance
0x1800023a9  mov     ebx, eax
0x1800023ab  test    eax, eax
0x1800023ad  js      short loc_1800023D9
0x1800023af  mov     rcx, [rsp+48h+arg_0]
0x1800023b4  mov     r8, rdi
0x1800023b7  mov     rdx, [rcx]
0x1800023ba  mov     rax, [rdx+18h]
0x1800023be  mov     edx, 5
0x1800023c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c8  mov     rcx, [rsp+48h+arg_0]
0x1800023cd  mov     rax, [rcx]
0x1800023d0  mov     rax, [rax+10h]
0x1800023d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d9  test    ebx, ebx
0x1800023db  jnz     loc_1800024F2
0x1800023e1  lea     rax, ?g_pIContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * g_pIContextCallback
0x1800023e8  mov     r8d, edi; dwClsContext
0x1800023eb  lea     r9, IID_IContextCallback; riid
0x1800023f2  mov     [rsp+48h+ppv], rax; ppv
0x1800023f7  xor     edx, edx; pUnkOuter
0x1800023f9  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180002400  call    cs:__imp_CoCreateInstance
0x180002406  mov     ebx, eax
0x180002408  test    eax, eax
0x18000240a  jnz     loc_1800024F2
0x180002410  mov     rcx, cs:?g_pIContextCallback@@3PEAUIContextCallback@@EA; IContextCallback * g_pIContextCallback
0x180002417  lea     r9, IID_IContextCallback
0x18000241e  mov     [rsp+48h+var_20], 0
0x180002427  lea     rdx, ?ConnectCallback@@YAJPEAUtagComCallData@@@Z; ConnectCallback(tagComCallData *)
0x18000242e  xor     r8d, r8d
0x180002431  mov     dword ptr [rsp+48h+ppv], 5
0x180002439  mov     rax, [rcx]
0x18000243c  mov     rax, [rax+18h]
0x180002440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002445  mov     ebx, eax
0x180002447  test    eax, eax
0x180002449  jnz     loc_1800024F2
0x18000244f  cmp     cs:?g_pSvchostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, 0; _SVCHOST_GLOBAL_DATA * g_pSvchostGlobalData
0x180002457  jz      short loc_1800024CA
0x180002459  lea     rcx, ?g_hServiceStopEventLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002460  call    cs:__imp_EnterCriticalSection
0x180002466  mov     rax, cs:?g_pSvchostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostGlobalData
0x18000246d  lea     r9, ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x180002474  mov     r8, cs:?g_hServiceStopEvent@@3PEAXEA; void * g_hServiceStopEvent
0x18000247b  lea     rdx, ServiceName; "fdPHost"
0x180002482  mov     dword ptr [rsp+48h+var_20], 8
0x18000248a  lea     rcx, ?g_hServiceStopCallback@@3PEAXEA; void * g_hServiceStopCallback
0x180002491  mov     [rsp+48h+ppv], 0
0x18000249a  mov     rax, [rax+0C0h]
0x1800024a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024a6  lea     rcx, ?g_hServiceStopEventLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800024ad  mov     edi, eax
0x1800024af  call    cs:__imp_LeaveCriticalSection
0x1800024b5  test    edi, edi
0x1800024b7  jz      short loc_1800024CA
0x1800024b9  jg      short loc_1800024BF
0x1800024bb  mov     ebx, edi
0x1800024bd  jmp     short loc_1800024F2
0x1800024bf  movzx   ebx, di
0x1800024c2  or      ebx, 80070000h
0x1800024c8  jmp     short loc_1800024F2
0x1800024ca  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800024d1  lea     rdx, ServiceStatus; lpServiceStatus
0x1800024d8  mov     cs:ServiceStatus.dwCurrentState, 4
0x1800024e2  mov     cs:ServiceStatus.dwControlsAccepted, 81h
0x1800024ec  call    cs:__imp_SetServiceStatus
0x1800024f2  mov     eax, ebx
0x1800024f4  mov     rbx, [rsp+48h+arg_8]
0x1800024f9  add     rsp, 40h
0x1800024fd  pop     rdi
0x1800024fe  retn
```
