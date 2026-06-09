# SettingsChgMon_Initialize(void)

- ea: `0x18005df80`
- end: `0x18005e122`
- name: `?SettingsChgMon_Initialize@@YAJXZ`
- size: `418`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180055248`

## callees

- `0x18002f10c`
- `0x18005d580`
- `0x18005d5e0`
- `0x18005d6f0`
- `0x18005df80`
- `0x18005e128`
- `0x18005e754`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e0e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e10b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e0e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e10b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005e0c5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005e0c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005e100`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005e100`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005df8f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005df8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e058`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e080`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e058`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e080`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18005e02b`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18005e02b`

## pseudocode

```c
__int64 SettingsChgMon_Initialize(void)
{
  int Error; // ebx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  HANDLE Parameter; // [rsp+48h] [rbp+10h] BYREF

  if ( !InitializeCriticalSectionAndSpinCount(&g_csChgMonCritSect, 0) )
    goto LABEL_12;
  g_bChgMonCritSectInitialized = 1;
  Error = SettingsChgMon_InitializeThreadpool();
  if ( Error < 0 )
    goto LABEL_20;
  Error = CPreferenceChgMonitor::Initialize((CPreferenceChgMonitor *)&g_PreferenceChgMonitor);
  if ( Error < 0 )
    goto LABEL_20;
  Error = CPolicyChgMonitor::Initialize((CPolicyChgMonitor *)&g_PolicyChgMonitor);
  if ( Error < 0 )
    goto LABEL_20;
  Error = CPeerDistChgMonitor::Initialize((CPeerDistChgMonitor *)&g_PeerDistChgMonitor);
  if ( Error < 0 )
    goto LABEL_20;
  if ( !qword_1800B6D50 || !qword_1800B6DA8 || !qword_1800B6D68 )
    return (unsigned int)Error;
  g_htimerChgMonDelay = CreateWaitableTimerW(0, 1, 0);
  if ( !g_htimerChgMonDelay )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_20;
  }
  Parameter = CreateEventW(0, 1, 0, 0);
  if ( Parameter )
  {
    g_hevtStopChgMonitor = CreateEventW(0, 1, 0, 0);
    if ( g_hevtStopChgMonitor )
    {
      ThreadId = 0;
      g_hthdChgMonThread = CreateThread(0, 0, SettingsChgMon_ThreadProc, &Parameter, 0, &ThreadId);
      if ( g_hthdChgMonThread )
      {
        WaitForSingleObject(Parameter, 0xFFFFFFFF);
      }
      else
      {
        Error = ResultFromLastError();
        CloseHandle(g_hevtStopChgMonitor);
        g_hevtStopChgMonitor = 0;
      }
    }
    else
    {
      Error = ResultFromLastError();
    }
    CloseHandle(Parameter);
  }
  else
  {
LABEL_12:
    Error = ResultFromLastError();
  }
  if ( Error < 0 )
LABEL_20:
    SettingsChgMon_Uninitialize();
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18005df80  push    rbx
0x18005df82  sub     rsp, 30h
0x18005df86  xor     edx, edx; dwSpinCount
0x18005df88  lea     rcx, ?g_csChgMonCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005df8f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005df95  test    eax, eax
0x18005df97  jz      loc_18005E068
0x18005df9d  mov     cs:?g_bChgMonCritSectInitialized@@3HA, 1; int g_bChgMonCritSectInitialized
0x18005dfa7  call    ?SettingsChgMon_InitializeThreadpool@@YAJXZ; SettingsChgMon_InitializeThreadpool(void)
0x18005dfac  mov     ebx, eax
0x18005dfae  test    eax, eax
0x18005dfb0  js      loc_18005E115
0x18005dfb6  lea     rcx, ?g_PreferenceChgMonitor@@3VCPreferenceChgMonitor@@A; this
0x18005dfbd  call    ?Initialize@CPreferenceChgMonitor@@UEAAJXZ; CPreferenceChgMonitor::Initialize(void)
0x18005dfc2  mov     ebx, eax
0x18005dfc4  test    eax, eax
0x18005dfc6  js      loc_18005E115
0x18005dfcc  lea     rcx, ?g_PolicyChgMonitor@@3VCPolicyChgMonitor@@A; this
0x18005dfd3  call    ?Initialize@CPolicyChgMonitor@@UEAAJXZ; CPolicyChgMonitor::Initialize(void)
0x18005dfd8  mov     ebx, eax
0x18005dfda  test    eax, eax
0x18005dfdc  js      loc_18005E115
0x18005dfe2  lea     rcx, ?g_PeerDistChgMonitor@@3VCPeerDistChgMonitor@@A; this
0x18005dfe9  call    ?Initialize@CPeerDistChgMonitor@@UEAAJXZ; CPeerDistChgMonitor::Initialize(void)
0x18005dfee  mov     ebx, eax
0x18005dff0  test    eax, eax
0x18005dff2  js      loc_18005E115
0x18005dff8  cmp     cs:qword_1800B6D50, 0
0x18005e000  jz      loc_18005E11A
0x18005e006  cmp     cs:qword_1800B6DA8, 0
0x18005e00e  jz      loc_18005E11A
0x18005e014  cmp     cs:qword_1800B6D68, 0
0x18005e01c  jz      loc_18005E11A
0x18005e022  xor     r8d, r8d; lpTimerName
0x18005e025  xor     ecx, ecx; lpTimerAttributes
0x18005e027  lea     edx, [r8+1]; bManualReset
0x18005e02b  call    cs:__imp_CreateWaitableTimerW
0x18005e031  mov     cs:?g_htimerChgMonDelay@@3PEAXEA, rax; void * g_htimerChgMonDelay
0x18005e038  test    rax, rax
0x18005e03b  jnz     short loc_18005E04C
0x18005e03d  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005e042  mov     ebx, eax
0x18005e044  test    eax, eax
0x18005e046  js      loc_18005E115
0x18005e04c  xor     r9d, r9d; lpName
0x18005e04f  xor     r8d, r8d; bInitialState
0x18005e052  xor     ecx, ecx; lpEventAttributes
0x18005e054  lea     edx, [r9+1]; bManualReset
0x18005e058  call    cs:__imp_CreateEventW
0x18005e05e  mov     [rsp+38h+Parameter], rax
0x18005e063  test    rax, rax
0x18005e066  jnz     short loc_18005E074
0x18005e068  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005e06d  mov     ebx, eax
0x18005e06f  jmp     loc_18005E111
0x18005e074  xor     r9d, r9d; lpName
0x18005e077  xor     r8d, r8d; bInitialState
0x18005e07a  xor     ecx, ecx; lpEventAttributes
0x18005e07c  lea     edx, [r9+1]; bManualReset
0x18005e080  call    cs:__imp_CreateEventW
0x18005e086  mov     cs:?g_hevtStopChgMonitor@@3PEAXEA, rax; void * g_hevtStopChgMonitor
0x18005e08d  test    rax, rax
0x18005e090  jnz     short loc_18005E09B
0x18005e092  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005e097  mov     ebx, eax
0x18005e099  jmp     short loc_18005E106
0x18005e09b  lea     rax, [rsp+38h+ThreadId]
0x18005e0a0  mov     [rsp+38h+ThreadId], 0
0x18005e0a8  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18005e0ad  lea     r9, [rsp+38h+Parameter]; lpParameter
0x18005e0b2  lea     r8, ?SettingsChgMon_ThreadProc@@YAKPEAX@Z; lpStartAddress
0x18005e0b9  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18005e0c1  xor     edx, edx; dwStackSize
0x18005e0c3  xor     ecx, ecx; lpThreadAttributes
0x18005e0c5  call    cs:__imp_CreateThread
0x18005e0cb  mov     cs:?g_hthdChgMonThread@@3PEAXEA, rax; void * g_hthdChgMonThread
0x18005e0d2  test    rax, rax
0x18005e0d5  jnz     short loc_18005E0F8
0x18005e0d7  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005e0dc  mov     rcx, cs:?g_hevtStopChgMonitor@@3PEAXEA; hObject
0x18005e0e3  mov     ebx, eax
0x18005e0e5  call    cs:__imp_CloseHandle
0x18005e0eb  mov     cs:?g_hevtStopChgMonitor@@3PEAXEA, 0; void * g_hevtStopChgMonitor
0x18005e0f6  jmp     short loc_18005E106
0x18005e0f8  mov     rcx, [rsp+38h+Parameter]; hHandle
0x18005e0fd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005e100  call    cs:__imp_WaitForSingleObject
0x18005e106  mov     rcx, [rsp+38h+Parameter]; hObject
0x18005e10b  call    cs:__imp_CloseHandle
0x18005e111  test    ebx, ebx
0x18005e113  jns     short loc_18005E11A
0x18005e115  call    ?SettingsChgMon_Uninitialize@@YAXXZ; SettingsChgMon_Uninitialize(void)
0x18005e11a  mov     eax, ebx
0x18005e11c  add     rsp, 30h
0x18005e120  pop     rbx
0x18005e121  retn
```
