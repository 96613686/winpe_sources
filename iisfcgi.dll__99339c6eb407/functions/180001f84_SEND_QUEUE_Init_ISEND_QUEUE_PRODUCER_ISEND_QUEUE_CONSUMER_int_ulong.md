# SEND_QUEUE::Init(ISEND_QUEUE_PRODUCER *,ISEND_QUEUE_CONSUMER *,int,ulong)

- ea: `0x180001f84`
- end: `0x180001ffb`
- name: `?Init@SEND_QUEUE@@QEAAJPEAVISEND_QUEUE_PRODUCER@@PEAVISEND_QUEUE_CONSUMER@@HK@Z`
- size: `119`
- prototype: `__int64 __fastcall(SEND_QUEUE *__hidden this, struct ISEND_QUEUE_PRODUCER *, struct ISEND_QUEUE_CONSUMER *, int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005294`

## callees

- `0x180001f84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fb2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001fd6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001fd6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180001fa8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180001fa8`

## pseudocode

```c
signed int __fastcall SEND_QUEUE::Init(
        struct _RTL_CRITICAL_SECTION *this,
        struct _RTL_CRITICAL_SECTION_DEBUG *a2,
        struct ISEND_QUEUE_CONSUMER *a3,
        LONG a4,
        unsigned int a5)
{
  signed int result; // eax
  HANDLE EventW; // rax

  this->DebugInfo = a2;
  LODWORD(this[2].OwningThread) = a5;
  *(_QWORD *)&this->LockCount = a3;
  this[2].RecursionCount = a4;
  if ( InitializeCriticalSectionAndSpinCount(this + 1, 0x3E8u)
    && (LODWORD(this[2].DebugInfo) = 1, EventW = CreateEventW(0, 1, 0, 0), (*(_QWORD *)&this[3].LockCount = EventW) != 0) )
  {
    result = 0;
    this->SpinCount = (ULONG_PTR)&this->LockSemaphore;
    this->LockSemaphore = &this->LockSemaphore;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180001f84  push    rbx
0x180001f86  sub     rsp, 20h
0x180001f8a  mov     eax, [rsp+28h+arg_20]
0x180001f8e  mov     rbx, rcx
0x180001f91  mov     [rcx], rdx
0x180001f94  mov     edx, 3E8h; dwSpinCount
0x180001f99  mov     [rcx+60h], eax
0x180001f9c  mov     [rcx+8], r8
0x180001fa0  mov     [rcx+5Ch], r9d
0x180001fa4  add     rcx, 28h ; '('; lpCriticalSection
0x180001fa8  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180001fae  test    eax, eax
0x180001fb0  jnz     short loc_180001FC6
0x180001fb2  call    cs:__imp_GetLastError
0x180001fb8  test    eax, eax
0x180001fba  jle     short loc_180001FF5
0x180001fbc  movzx   eax, ax
0x180001fbf  or      eax, 80070000h
0x180001fc4  jmp     short loc_180001FF5
0x180001fc6  mov     edx, 1; bManualReset
0x180001fcb  xor     r9d, r9d; lpName
0x180001fce  xor     r8d, r8d; bInitialState
0x180001fd1  mov     [rbx+50h], edx
0x180001fd4  xor     ecx, ecx; lpEventAttributes
0x180001fd6  call    cs:__imp_CreateEventW
0x180001fdc  mov     [rbx+80h], rax
0x180001fe3  test    rax, rax
0x180001fe6  jz      short loc_180001FB2
0x180001fe8  lea     rcx, [rbx+18h]
0x180001fec  xor     eax, eax
0x180001fee  mov     [rcx+8], rcx
0x180001ff2  mov     [rcx], rcx
0x180001ff5  add     rsp, 20h
0x180001ff9  pop     rbx
0x180001ffa  retn
```
