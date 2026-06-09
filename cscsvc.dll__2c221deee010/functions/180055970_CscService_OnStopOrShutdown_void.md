# CscService_OnStopOrShutdown(void)

- ea: `0x180055970`
- end: `0x180055a86`
- name: `?CscService_OnStopOrShutdown@@YAXXZ`
- size: `278`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180023340`

## callees

- `0x18000f5d4`
- `0x180036394`
- `0x180055970`
- `0x180055b70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800559b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055a54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800559b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055a54`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180055a30`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180055a30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800559ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800559ea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800559dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800559dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055a01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055a01`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18005598e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18005598e`

## pseudocode

```c
void CscService_OnStopOrShutdown(void)
{
  DWORD LastError; // eax
  DWORD v1; // eax

  g_CscServiceInfo.dwCurrentState = 3;
  if ( !SetServiceStatus(hServiceStatus, &g_CscServiceInfo)
    && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids, LastError);
  }
  SetEvent(g_hevtStop);
  EnterCriticalSection(&g_csDone);
  g_bDone = 1;
  LeaveCriticalSection(&g_csDone);
  CscService_TaskBegin(1);
  g_hthdPreShutdownCleanup = CreateThread(0, 0, CscService_PreShutdownCleanupThreadProc, 0, 0, 0);
  if ( !g_hthdPreShutdownCleanup )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v1 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids, v1);
    }
    CscService_PreShutdownCleanupThreadProc(0);
  }
}

```

## disassembly

```asm
0x180055970  push    rdi
0x180055972  sub     rsp, 30h
0x180055976  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x18005597d  lea     rdx, ?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A; lpServiceStatus
0x180055984  mov     cs:?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A.dwCurrentState, 3; CSC_SERVICE_INFO g_CscServiceInfo ...
0x18005598e  call    cs:__imp_SetServiceStatus
0x180055994  lea     rdi, WPP_GLOBAL_Control
0x18005599b  test    eax, eax
0x18005599d  jnz     short loc_1800559D6
0x18005599f  mov     rax, cs:WPP_GLOBAL_Control
0x1800559a6  cmp     rax, rdi
0x1800559a9  jz      short loc_1800559D6
0x1800559ab  test    byte ptr [rax+1Ch], 2
0x1800559af  jz      short loc_1800559D6
0x1800559b1  call    cs:__imp_GetLastError
0x1800559b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800559be  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x1800559c5  mov     edx, 64h ; 'd'
0x1800559ca  mov     r9d, eax
0x1800559cd  mov     rcx, [rcx+10h]
0x1800559d1  call    WPP_SF_d
0x1800559d6  mov     rcx, cs:?g_hevtStop@@3PEAXEA; hEvent
0x1800559dd  call    cs:__imp_SetEvent
0x1800559e3  lea     rcx, ?g_csDone@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800559ea  call    cs:__imp_EnterCriticalSection
0x1800559f0  lea     rcx, ?g_csDone@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800559f7  mov     cs:?g_bDone@@3HA, 1; int g_bDone
0x180055a01  call    cs:__imp_LeaveCriticalSection
0x180055a07  mov     ecx, 1; int
0x180055a0c  call    ?CscService_TaskBegin@@YAJH@Z; CscService_TaskBegin(int)
0x180055a11  xor     r9d, r9d; lpParameter
0x180055a14  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180055a1d  lea     r8, ?CscService_PreShutdownCleanupThreadProc@@YAKPEAX@Z; lpStartAddress
0x180055a24  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180055a2c  xor     edx, edx; dwStackSize
0x180055a2e  xor     ecx, ecx; lpThreadAttributes
0x180055a30  call    cs:__imp_CreateThread
0x180055a36  mov     cs:?g_hthdPreShutdownCleanup@@3PEAXEA, rax; void * g_hthdPreShutdownCleanup
0x180055a3d  test    rax, rax
0x180055a40  jnz     short loc_180055A80
0x180055a42  mov     rax, cs:WPP_GLOBAL_Control
0x180055a49  cmp     rax, rdi
0x180055a4c  jz      short loc_180055A79
0x180055a4e  test    byte ptr [rax+1Ch], 8
0x180055a52  jz      short loc_180055A79
0x180055a54  call    cs:__imp_GetLastError
0x180055a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180055a61  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x180055a68  mov     edx, 65h ; 'e'
0x180055a6d  mov     r9d, eax
0x180055a70  mov     rcx, [rcx+10h]
0x180055a74  call    WPP_SF_d
0x180055a79  xor     ecx, ecx; Parameter
0x180055a7b  call    ?CscService_PreShutdownCleanupThreadProc@@YAKPEAX@Z; CscService_PreShutdownCleanupThreadProc(void *)
0x180055a80  add     rsp, 30h
0x180055a84  pop     rdi
0x180055a85  retn
```
