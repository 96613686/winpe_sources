# CWaitableOperation::Initialize(void)

- ea: `0x18005da30`
- end: `0x18005dad1`
- name: `?Initialize@CWaitableOperation@@QEAAJXZ`
- size: `161`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d6ac`

## callees

- `0x18002f10c`
- `0x18005da30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005da5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005da5d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005da43`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005da43`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005daae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005daae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005da91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005da91`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005da74`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005da74`

## pseudocode

```c
__int64 __fastcall CWaitableOperation::Initialize(struct _RTL_CRITICAL_SECTION *pv)
{
  int Error; // ebx
  PTP_WAIT ThreadpoolWait; // rax
  HANDLE EventW; // rax

  if ( InitializeCriticalSectionAndSpinCount(pv + 1, 0) )
  {
    LODWORD(pv[2].DebugInfo) = 1;
    Error = 0;
    EnterCriticalSection(&g_csChgMonCritSect);
    ThreadpoolWait = CreateThreadpoolWait(CWaitableOperation::WaitCallback, pv, &g_ChgMonTpCbkEnv);
    pv->OwningThread = ThreadpoolWait;
    if ( !ThreadpoolWait )
      Error = ResultFromLastError();
    LeaveCriticalSection(&g_csChgMonCritSect);
  }
  else
  {
    Error = ResultFromLastError();
  }
  if ( Error >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    pv->LockSemaphore = EventW;
    if ( !EventW )
      return (unsigned int)ResultFromLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18005da30  mov     [rsp+arg_0], rbx
0x18005da35  push    rdi
0x18005da36  sub     rsp, 20h
0x18005da3a  mov     rdi, rcx
0x18005da3d  xor     edx, edx; dwSpinCount
0x18005da3f  add     rcx, 28h ; '('; lpCriticalSection
0x18005da43  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005da49  test    eax, eax
0x18005da4b  jz      short loc_18005DA99
0x18005da4d  lea     rcx, ?g_csChgMonCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005da54  mov     dword ptr [rdi+50h], 1
0x18005da5b  xor     ebx, ebx
0x18005da5d  call    cs:__imp_EnterCriticalSection
0x18005da63  lea     r8, ?g_ChgMonTpCbkEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18005da6a  mov     rdx, rdi; pv
0x18005da6d  lea     rcx, ?WaitCallback@CWaitableOperation@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005da74  call    cs:__imp_CreateThreadpoolWait
0x18005da7a  mov     [rdi+10h], rax
0x18005da7e  test    rax, rax
0x18005da81  jnz     short loc_18005DA8A
0x18005da83  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005da88  mov     ebx, eax
0x18005da8a  lea     rcx, ?g_csChgMonCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005da91  call    cs:__imp_LeaveCriticalSection
0x18005da97  jmp     short loc_18005DAA0
0x18005da99  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005da9e  mov     ebx, eax
0x18005daa0  test    ebx, ebx
0x18005daa2  js      short loc_18005DAC4
0x18005daa4  xor     r9d, r9d; lpName
0x18005daa7  xor     r8d, r8d; bInitialState
0x18005daaa  xor     edx, edx; bManualReset
0x18005daac  xor     ecx, ecx; lpEventAttributes
0x18005daae  call    cs:__imp_CreateEventW
0x18005dab4  mov     [rdi+18h], rax
0x18005dab8  test    rax, rax
0x18005dabb  jnz     short loc_18005DAC4
0x18005dabd  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005dac2  mov     ebx, eax
0x18005dac4  mov     eax, ebx
0x18005dac6  mov     rbx, [rsp+28h+arg_0]
0x18005dacb  add     rsp, 20h
0x18005dacf  pop     rdi
0x18005dad0  retn
```
