# MDnsProbeAnnounceTask::Init(void)

- ea: `0x1800527fc`
- end: `0x180052888`
- name: `?Init@MDnsProbeAnnounceTask@@SAKXZ`
- size: `140`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180040280`

## callees

- `0x1800527fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005282f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005282f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052850`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005285b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005285b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180052821`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180052821`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180052845`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180052845`

## pseudocode

```c
__int64 MDnsProbeAnnounceTask::Init(void)
{
  DWORD LastError; // ebx
  HANDLE EventW; // rdi
  struct _TP_TIMER *ThreadpoolTimer; // rax

  LastError = 0;
  if ( MDnsProbeAnnounceTask::s_fInitialized )
  {
    return 1247;
  }
  else
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(MDnsProbeAnnounceTask::TimerCallback, 0, 0);
      if ( ThreadpoolTimer )
      {
        MDnsProbeAnnounceTask::s_hProbeAnnounceStop = EventW;
        MDnsProbeAnnounceTask::s_pTimer = ThreadpoolTimer;
        MDnsProbeAnnounceTask::s_fInitialized = 1;
      }
      else
      {
        LastError = GetLastError();
        CloseHandle(EventW);
      }
    }
    else
    {
      return GetLastError();
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800527fc  mov     [rsp+arg_0], rbx
0x180052801  push    rdi
0x180052802  sub     rsp, 20h
0x180052806  xor     ebx, ebx
0x180052808  cmp     cs:?s_fInitialized@MDnsProbeAnnounceTask@@0HA, ebx; int MDnsProbeAnnounceTask::s_fInitialized
0x18005280e  jz      short loc_180052817
0x180052810  mov     ebx, 4DFh
0x180052815  jmp     short loc_18005287B
0x180052817  xor     r9d, r9d; lpName
0x18005281a  xor     r8d, r8d; bInitialState
0x18005281d  xor     edx, edx; bManualReset
0x18005281f  xor     ecx, ecx; lpEventAttributes
0x180052821  call    cs:__imp_CreateEventW
0x180052827  mov     rdi, rax
0x18005282a  test    rax, rax
0x18005282d  jnz     short loc_180052839
0x18005282f  call    cs:__imp_GetLastError
0x180052835  mov     ebx, eax
0x180052837  jmp     short loc_18005287B
0x180052839  xor     r8d, r8d; pcbe
0x18005283c  lea     rcx, ?TimerCallback@MDnsProbeAnnounceTask@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180052843  xor     edx, edx; pv
0x180052845  call    cs:__imp_CreateThreadpoolTimer
0x18005284b  test    rax, rax
0x18005284e  jnz     short loc_180052863
0x180052850  call    cs:__imp_GetLastError
0x180052856  mov     rcx, rdi; hObject
0x180052859  mov     ebx, eax
0x18005285b  call    cs:__imp_CloseHandle
0x180052861  jmp     short loc_18005287B
0x180052863  mov     cs:?s_hProbeAnnounceStop@MDnsProbeAnnounceTask@@0PEAXEA, rdi; void * MDnsProbeAnnounceTask::s_hProbeAnnounceStop
0x18005286a  mov     cs:?s_pTimer@MDnsProbeAnnounceTask@@0PEAU_TP_TIMER@@EA, rax; _TP_TIMER * MDnsProbeAnnounceTask::s_pTimer
0x180052871  mov     cs:?s_fInitialized@MDnsProbeAnnounceTask@@0HA, 1; int MDnsProbeAnnounceTask::s_fInitialized
0x18005287b  mov     eax, ebx
0x18005287d  mov     rbx, [rsp+28h+arg_0]
0x180052882  add     rsp, 20h
0x180052886  pop     rdi
0x180052887  retn
```
