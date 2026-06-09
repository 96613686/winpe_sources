# CIISModuleFactory::Terminate(void)

- ea: `0x180002e10`
- end: `0x180002e70`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `96`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800010c8`
- `0x180002e10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002e29`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002e29`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180002e41`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180002e41`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  if ( IP_RESTRICTION_LIST::sm_fInitCritSec )
    DeleteCriticalSection(&IP_RESTRICTION_LIST::sm_csLazyInitialize);
  if ( IP_RESTRICTION_LIST::sm_hTimer )
  {
    DeleteTimerQueueTimer(0, IP_RESTRICTION_LIST::sm_hTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    IP_RESTRICTION_LIST::sm_hTimer = 0;
  }
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180002e10  push    rbx
0x180002e12  sub     rsp, 20h
0x180002e16  cmp     cs:?sm_fInitCritSec@IP_RESTRICTION_LIST@@0HA, 0; int IP_RESTRICTION_LIST::sm_fInitCritSec
0x180002e1d  mov     rbx, rcx
0x180002e20  jz      short loc_180002E2F
0x180002e22  lea     rcx, ?sm_csLazyInitialize@IP_RESTRICTION_LIST@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002e29  call    cs:__imp_DeleteCriticalSection
0x180002e2f  mov     rdx, cs:?sm_hTimer@IP_RESTRICTION_LIST@@0PEAXEA; Timer
0x180002e36  test    rdx, rdx
0x180002e39  jz      short loc_180002E52
0x180002e3b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180002e3f  xor     ecx, ecx; TimerQueue
0x180002e41  call    cs:__imp_DeleteTimerQueueTimer
0x180002e47  mov     cs:?sm_hTimer@IP_RESTRICTION_LIST@@0PEAXEA, 0; void * IP_RESTRICTION_LIST::sm_hTimer
0x180002e52  test    rbx, rbx
0x180002e55  jz      short loc_180002E6A
0x180002e57  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x180002e5e  mov     rcx, rbx; Block
0x180002e61  mov     [rbx+8], rax
0x180002e65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002e6a  add     rsp, 20h
0x180002e6e  pop     rbx
0x180002e6f  retn
```
