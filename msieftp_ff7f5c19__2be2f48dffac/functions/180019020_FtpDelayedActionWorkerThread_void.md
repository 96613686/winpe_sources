# FtpDelayedActionWorkerThread(void *)

- ea: `0x180019020`
- end: `0x180019101`
- name: `?FtpDelayedActionWorkerThread@@YAKPEAX@Z`
- size: `225`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180019020`
- `0x1800191b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001904a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019095`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001904a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019095`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019071`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800190b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800190f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019071`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800190b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800190f2`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800190fa`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800190fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800190da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800190e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800190da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800190e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019066`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019066`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001908c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001908c`

## pseudocode

```c
void __fastcall __noreturn FtpDelayedActionWorkerThread(PVOID Parameter)
{
  signed int v1; // ebx
  int v2; // ebx

  g_fBackgroundThreadStarted = 1;
  while ( 1 )
  {
    EnterCriticalSection(&g_csDll);
    if ( (_UNKNOWN *)g_gti == &g_gti )
    {
      v1 = 600000;
    }
    else
    {
      v2 = *(_DWORD *)(g_gti + 24LL);
      v1 = v2 - GetTickCount();
    }
    LeaveCriticalSection(&g_csDll);
    if ( v1 > 0 )
      WaitForMultipleObjects(1u, &g_hFlushDelayedActionsEvent, 0, v1);
    EnterCriticalSection(&g_csDll);
    if ( (_UNKNOWN *)g_gti == &g_gti || !g_gti || !*(_QWORD *)(g_gti + 16LL) )
    {
      CloseHandle((HANDLE)_InterlockedExchange64((volatile __int64 *)&g_hthWorker, 0));
      CloseHandle((HANDLE)_InterlockedExchange64((volatile __int64 *)&g_hFlushDelayedActionsEvent, 0));
      LeaveCriticalSection(&g_csDll);
      ExitThread(0);
    }
    LeaveCriticalSection(&g_csDll);
    TriggerDelayedAction(*(struct GLOBALTIMEOUTINFO ***)(g_gti + 16LL));
  }
}

```

## disassembly

```asm
0x180019020  mov     [rsp+arg_0], rbx
0x180019025  mov     [rsp+arg_8], rsi
0x18001902a  push    rdi
0x18001902b  sub     rsp, 20h
0x18001902f  mov     cs:?g_fBackgroundThreadStarted@@3HA, 1; int g_fBackgroundThreadStarted
0x180019039  lea     rdi, g_csDll
0x180019040  lea     rsi, ?g_gti@@3UGLOBALTIMEOUTINFO@@A; GLOBALTIMEOUTINFO g_gti
0x180019047  mov     rcx, rdi; lpCriticalSection
0x18001904a  call    cs:__imp_EnterCriticalSection
0x180019050  mov     rbx, cs:?g_gti@@3UGLOBALTIMEOUTINFO@@A; GLOBALTIMEOUTINFO g_gti
0x180019057  cmp     rbx, rsi
0x18001905a  jnz     short loc_180019063
0x18001905c  mov     ebx, 927C0h
0x180019061  jmp     short loc_18001906E
0x180019063  mov     ebx, [rbx+18h]
0x180019066  call    cs:__imp_GetTickCount
0x18001906c  sub     ebx, eax
0x18001906e  mov     rcx, rdi; lpCriticalSection
0x180019071  call    cs:__imp_LeaveCriticalSection
0x180019077  test    ebx, ebx
0x180019079  jle     short loc_180019092
0x18001907b  xor     r8d, r8d; bWaitAll
0x18001907e  lea     rdx, ?g_hFlushDelayedActionsEvent@@3PEAXEA; lpHandles
0x180019085  mov     r9d, ebx; dwMilliseconds
0x180019088  lea     ecx, [r8+1]; nCount
0x18001908c  call    cs:__imp_WaitForMultipleObjects
0x180019092  mov     rcx, rdi; lpCriticalSection
0x180019095  call    cs:__imp_EnterCriticalSection
0x18001909b  mov     rax, cs:?g_gti@@3UGLOBALTIMEOUTINFO@@A; GLOBALTIMEOUTINFO g_gti
0x1800190a2  cmp     rax, rsi
0x1800190a5  jz      short loc_1800190D1
0x1800190a7  test    rax, rax
0x1800190aa  jz      short loc_1800190D1
0x1800190ac  cmp     qword ptr [rax+10h], 0
0x1800190b1  jz      short loc_1800190D1
0x1800190b3  mov     rcx, rdi; lpCriticalSection
0x1800190b6  call    cs:__imp_LeaveCriticalSection
0x1800190bc  mov     rcx, cs:?g_gti@@3UGLOBALTIMEOUTINFO@@A; GLOBALTIMEOUTINFO g_gti
0x1800190c3  mov     rcx, [rcx+10h]; struct GLOBALTIMEOUTINFO **
0x1800190c7  call    ?TriggerDelayedAction@@YAXPEAPEAUGLOBALTIMEOUTINFO@@@Z; TriggerDelayedAction(GLOBALTIMEOUTINFO * *)
0x1800190cc  jmp     loc_180019047
0x1800190d1  xor     ecx, ecx
0x1800190d3  xchg    rcx, cs:?g_hthWorker@@3PEAXEA; hObject
0x1800190da  call    cs:__imp_CloseHandle
0x1800190e0  xor     ecx, ecx
0x1800190e2  xchg    rcx, cs:?g_hFlushDelayedActionsEvent@@3PEAXEA; hObject
0x1800190e9  call    cs:__imp_CloseHandle
0x1800190ef  mov     rcx, rdi; lpCriticalSection
0x1800190f2  call    cs:__imp_LeaveCriticalSection
0x1800190f8  xor     ecx, ecx; dwExitCode
0x1800190fa  call    cs:__imp_ExitThread
```
