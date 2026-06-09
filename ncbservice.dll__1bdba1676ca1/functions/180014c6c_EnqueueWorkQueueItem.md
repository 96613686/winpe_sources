# EnqueueWorkQueueItem

- ea: `0x180014c6c`
- end: `0x180014d27`
- name: `EnqueueWorkQueueItem`
- size: `187`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011af8`

## callees

- `0x180014c6c`
- `0x18001c4e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ce3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ce3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014d14`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014d14`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180014cae`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180014cae`

## pseudocode

```c
__int64 __fastcall EnqueueWorkQueueItem(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _RTL_CRITICAL_SECTION *a2,
        void *a3)
{
  BOOL v6; // eax
  unsigned int v7; // esi
  LPCRITICAL_SECTION *SpinCount; // rcx

  if ( !(unsigned __int8)RoReferenceEx(&lpCriticalSection[1]) )
    return 0;
  EnterCriticalSection(lpCriticalSection);
  if ( LODWORD(lpCriticalSection[1].OwningThread) )
  {
    v7 = 1;
    goto LABEL_4;
  }
  v6 = TrySubmitThreadpoolCallback(
         WorkQueueCallback,
         lpCriticalSection,
         (PTP_CALLBACK_ENVIRON)lpCriticalSection[2].DebugInfo);
  LODWORD(lpCriticalSection[1].OwningThread) = v6;
  v7 = v6;
  if ( v6 )
  {
LABEL_4:
    a2->OwningThread = lpCriticalSection;
    a2->LockSemaphore = a3;
    SpinCount = (LPCRITICAL_SECTION *)lpCriticalSection[1].SpinCount;
    if ( *SpinCount != (LPCRITICAL_SECTION)&lpCriticalSection[1].LockSemaphore )
      __fastfail(3u);
    a2->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&lpCriticalSection[1].LockSemaphore;
    *(_QWORD *)&a2->LockCount = SpinCount;
    *SpinCount = a2;
    lpCriticalSection[1].SpinCount = (ULONG_PTR)a2;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( !v7 && _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[1], 0xFFFFFFFE) == 3 )
    SetEvent(*(HANDLE *)&lpCriticalSection[1].LockCount);
  return v7;
}

```

## disassembly

```asm
0x180014c6c  push    rbx
0x180014c6e  push    rbp
0x180014c6f  push    rsi
0x180014c70  push    rdi
0x180014c71  push    r14
0x180014c73  sub     rsp, 20h
0x180014c77  mov     rbx, rcx
0x180014c7a  mov     r14, r8
0x180014c7d  add     rcx, 28h ; '('
0x180014c81  mov     rdi, rdx
0x180014c84  call    RoReferenceEx
0x180014c89  test    al, al
0x180014c8b  jz      loc_180014D1C
0x180014c91  mov     rcx, rbx; lpCriticalSection
0x180014c94  call    cs:__imp_EnterCriticalSection
0x180014c9a  cmp     dword ptr [rbx+38h], 0
0x180014c9e  jnz     short loc_180014CFA
0x180014ca0  mov     r8, [rbx+50h]; pcbe
0x180014ca4  lea     rcx, WorkQueueCallback; pfns
0x180014cab  mov     rdx, rbx; pv
0x180014cae  call    cs:__imp_TrySubmitThreadpoolCallback
0x180014cb4  mov     [rbx+38h], eax
0x180014cb7  mov     esi, eax
0x180014cb9  test    eax, eax
0x180014cbb  jz      short loc_180014CE0
0x180014cbd  lea     rax, [rbx+40h]
0x180014cc1  mov     [rdi+10h], rbx
0x180014cc5  mov     [rdi+18h], r14
0x180014cc9  mov     rcx, [rax+8]
0x180014ccd  cmp     [rcx], rax
0x180014cd0  jnz     short loc_180014D20
0x180014cd2  mov     [rdi], rax
0x180014cd5  mov     [rdi+8], rcx
0x180014cd9  mov     [rcx], rdi
0x180014cdc  mov     [rax+8], rdi
0x180014ce0  mov     rcx, rbx; lpCriticalSection
0x180014ce3  call    cs:__imp_LeaveCriticalSection
0x180014ce9  test    esi, esi
0x180014ceb  jz      short loc_180014D01
0x180014ced  mov     eax, esi
0x180014cef  add     rsp, 20h
0x180014cf3  pop     r14
0x180014cf5  pop     rdi
0x180014cf6  pop     rsi
0x180014cf7  pop     rbp
0x180014cf8  pop     rbx
0x180014cf9  retn
0x180014cfa  mov     esi, 1
0x180014cff  jmp     short loc_180014CBD
0x180014d01  mov     ecx, 0FFFFFFFEh
0x180014d06  lock xadd [rbx+28h], ecx
0x180014d0b  cmp     ecx, 3
0x180014d0e  jnz     short loc_180014CED
0x180014d10  mov     rcx, [rbx+30h]; hEvent
0x180014d14  call    cs:__imp_SetEvent
0x180014d1a  jmp     short loc_180014CED
0x180014d1c  xor     eax, eax
0x180014d1e  jmp     short loc_180014CEF
0x180014d20  mov     ecx, 3
0x180014d25  int     29h; Win8: RtlFailFast(ecx)
```
