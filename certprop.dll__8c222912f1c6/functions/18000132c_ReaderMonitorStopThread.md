# ReaderMonitorStopThread

- ea: `0x18000132c`
- end: `0x1800013bd`
- name: `ReaderMonitorStopThread`
- size: `145`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010c4`
- `0x180019fa4`

## callees

- `0x18000132c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800013a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800013a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000138e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000138e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001354`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001354`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001366`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001370`
- `WinSCard!SCardCancel` at `0x180001384`
- `WinSCard!SCardCancel` at `0x180001384`

## pseudocode

```c
__int64 __fastcall ReaderMonitorStopThread(__int64 a1)
{
  DWORD LastError; // edi
  void *v4; // rcx
  SCARDCONTEXT v5; // rcx
  struct _TP_CLEANUP_GROUP *v6; // rcx

  if ( !*(_DWORD *)(a1 + 216) )
    return 1359;
  LastError = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v4 = *(void **)(a1 + 240);
  if ( v4 && !SetEvent(v4) )
    LastError = GetLastError();
  v5 = *(_QWORD *)(a1 + 232);
  if ( v5 )
    SCardCancel(v5);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v6 = *(struct _TP_CLEANUP_GROUP **)(a1 + 208);
  if ( v6 )
    CloseThreadpoolCleanupGroupMembers(v6, 0, 0);
  return LastError;
}

```

## disassembly

```asm
0x18000132c  mov     [rsp+arg_0], rbx
0x180001331  mov     [rsp+arg_8], rsi
0x180001336  push    rdi
0x180001337  sub     rsp, 20h
0x18000133b  cmp     dword ptr [rcx+0D8h], 0
0x180001342  mov     rbx, rcx
0x180001345  jnz     short loc_18000134E
0x180001347  mov     eax, 54Fh
0x18000134c  jmp     short loc_1800013AD
0x18000134e  add     rcx, 30h ; '0'; lpCriticalSection
0x180001352  xor     edi, edi
0x180001354  call    cs:__imp_EnterCriticalSection
0x18000135a  mov     rcx, [rbx+0F0h]; hEvent
0x180001361  test    rcx, rcx
0x180001364  jz      short loc_180001378
0x180001366  call    cs:__imp_SetEvent
0x18000136c  test    eax, eax
0x18000136e  jnz     short loc_180001378
0x180001370  call    cs:__imp_GetLastError
0x180001376  mov     edi, eax
0x180001378  mov     rcx, [rbx+0E8h]; hContext
0x18000137f  test    rcx, rcx
0x180001382  jz      short loc_18000138A
0x180001384  call    cs:__imp_SCardCancel
0x18000138a  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000138e  call    cs:__imp_LeaveCriticalSection
0x180001394  mov     rcx, [rbx+0D0h]; ptpcg
0x18000139b  test    rcx, rcx
0x18000139e  jz      short loc_1800013AB
0x1800013a0  xor     r8d, r8d; pvCleanupContext
0x1800013a3  xor     edx, edx; fCancelPendingCallbacks
0x1800013a5  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800013ab  mov     eax, edi
0x1800013ad  mov     rbx, [rsp+28h+arg_0]
0x1800013b2  mov     rsi, [rsp+28h+arg_8]
0x1800013b7  add     rsp, 20h
0x1800013bb  pop     rdi
0x1800013bc  retn
```
