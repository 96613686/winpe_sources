# AcquireLockExclusive

- ea: `0x180001a40`
- end: `0x180001ac1`
- name: `AcquireLockExclusive`
- size: `129`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002900`
- `0x1800089c0`
- `0x180008c00`
- `0x180008d00`
- `0x18000da50`

## callees

- `0x180001a40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001a49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001aae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001a49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001aae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001aa5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001aa5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180001a8d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180001a8d`

## pseudocode

```c
void __fastcall AcquireLockExclusive(LPCRITICAL_SECTION lpCriticalSection)
{
  DWORD CurrentThreadId; // eax
  int SpinCount; // edi
  HANDLE OwningThread; // rcx

  EnterCriticalSection(lpCriticalSection);
  while ( HIDWORD(lpCriticalSection[1].LockSemaphore) )
  {
    SpinCount = lpCriticalSection[1].SpinCount;
    if ( GetCurrentThreadId() == SpinCount )
      break;
    OwningThread = lpCriticalSection[1].OwningThread;
    LODWORD(lpCriticalSection[1].LockSemaphore) = 0;
    ResetEvent(OwningThread);
    LeaveCriticalSection(lpCriticalSection);
    WaitForSingleObject(lpCriticalSection[1].OwningThread, 0xFFFFFFFF);
    EnterCriticalSection(lpCriticalSection);
  }
  CurrentThreadId = GetCurrentThreadId();
  --HIDWORD(lpCriticalSection[1].LockSemaphore);
  LODWORD(lpCriticalSection[1].SpinCount) = CurrentThreadId;
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180001a40  push    rbx
0x180001a42  sub     rsp, 20h
0x180001a46  mov     rbx, rcx
0x180001a49  call    cs:__imp_EnterCriticalSection
0x180001a4f  cmp     dword ptr [rbx+44h], 0
0x180001a53  jnz     short loc_180001A70
0x180001a55  call    cs:__imp_GetCurrentThreadId
0x180001a5b  dec     dword ptr [rbx+44h]
0x180001a5e  mov     rcx, rbx
0x180001a61  mov     [rbx+48h], eax
0x180001a64  add     rsp, 20h
0x180001a68  pop     rbx
0x180001a69  jmp     cs:__imp_LeaveCriticalSection
0x180001a70  mov     [rsp+28h+arg_0], rdi
0x180001a75  mov     edi, [rbx+48h]
0x180001a78  call    cs:__imp_GetCurrentThreadId
0x180001a7e  cmp     eax, edi
0x180001a80  jz      short loc_180001ABA
0x180001a82  mov     rcx, [rbx+38h]; hEvent
0x180001a86  mov     dword ptr [rbx+40h], 0
0x180001a8d  call    cs:__imp_ResetEvent
0x180001a93  mov     rcx, rbx; lpCriticalSection
0x180001a96  call    cs:__imp_LeaveCriticalSection
0x180001a9c  mov     rcx, [rbx+38h]; hHandle
0x180001aa0  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180001aa5  call    cs:__imp_WaitForSingleObject
0x180001aab  mov     rcx, rbx; lpCriticalSection
0x180001aae  call    cs:__imp_EnterCriticalSection
0x180001ab4  cmp     dword ptr [rbx+44h], 0
0x180001ab8  jnz     short loc_180001A75
0x180001aba  mov     rdi, [rsp+28h+arg_0]
0x180001abf  jmp     short loc_180001A55
```
