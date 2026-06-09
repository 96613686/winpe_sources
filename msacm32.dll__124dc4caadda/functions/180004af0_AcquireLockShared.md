# AcquireLockShared

- ea: `0x180004af0`
- end: `0x180004b64`
- name: `AcquireLockShared`
- size: `116`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180002540`
- `0x180002900`
- `0x180002b00`
- `0x180002e70`
- `0x180007ef0`
- `0x180008160`
- `0x1800089c0`
- `0x18000ad3c`
- `0x18000b8d0`
- `0x18000bca0`
- `0x18000c130`
- `0x18000cfe0`
- `0x18000d7b0`

## callees

- `0x180004af0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004b57`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004b57`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004b3f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004b3f`

## pseudocode

```c
void __fastcall AcquireLockShared(LPCRITICAL_SECTION lpCriticalSection)
{
  int LockSemaphore_high; // eax
  int SpinCount; // edi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  while ( 1 )
  {
    EnterCriticalSection(lpCriticalSection);
    LockSemaphore_high = HIDWORD(lpCriticalSection[1].LockSemaphore);
    if ( LockSemaphore_high >= 0 )
    {
      HIDWORD(lpCriticalSection[1].LockSemaphore) = LockSemaphore_high + 1;
      goto LABEL_3;
    }
    SpinCount = lpCriticalSection[1].SpinCount;
    if ( SpinCount == GetCurrentThreadId() )
      break;
    DebugInfo = lpCriticalSection[1].DebugInfo;
    lpCriticalSection[1].LockCount = 0;
    ResetEvent(DebugInfo);
    LeaveCriticalSection(lpCriticalSection);
    WaitForSingleObject(lpCriticalSection[1].DebugInfo, 0xFFFFFFFF);
  }
  --HIDWORD(lpCriticalSection[1].LockSemaphore);
LABEL_3:
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180004af0  push    rbx
0x180004af2  sub     rsp, 20h
0x180004af6  mov     rbx, rcx
0x180004af9  mov     [rsp+28h+arg_0], rdi
0x180004afe  mov     rcx, rbx; lpCriticalSection
0x180004b01  call    cs:__imp_EnterCriticalSection
0x180004b07  mov     eax, [rbx+44h]
0x180004b0a  test    eax, eax
0x180004b0c  js      short loc_180004B27
0x180004b0e  inc     eax
0x180004b10  mov     [rbx+44h], eax
0x180004b13  mov     rcx, rbx
0x180004b16  mov     rdi, [rsp+28h+arg_0]
0x180004b1b  add     rsp, 20h
0x180004b1f  pop     rbx
0x180004b20  jmp     cs:__imp_LeaveCriticalSection
0x180004b27  mov     edi, [rbx+48h]
0x180004b2a  call    cs:__imp_GetCurrentThreadId
0x180004b30  cmp     edi, eax
0x180004b32  jz      short loc_180004B5F
0x180004b34  mov     rcx, [rbx+28h]; hEvent
0x180004b38  mov     dword ptr [rbx+30h], 0
0x180004b3f  call    cs:__imp_ResetEvent
0x180004b45  mov     rcx, rbx; lpCriticalSection
0x180004b48  call    cs:__imp_LeaveCriticalSection
0x180004b4e  mov     rcx, [rbx+28h]; hHandle
0x180004b52  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180004b57  call    cs:__imp_WaitForSingleObject
0x180004b5d  jmp     short loc_180004AFE
0x180004b5f  dec     dword ptr [rbx+44h]
0x180004b62  jmp     short loc_180004B13
```
