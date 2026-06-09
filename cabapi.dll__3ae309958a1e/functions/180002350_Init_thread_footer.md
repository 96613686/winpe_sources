# _Init_thread_footer

- ea: `0x180002350`
- end: `0x1800023b0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180013040`
- `0x180013774`

## callees

- `0x180002424`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002360`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002360`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&CriticalSection);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180002350  push    rbx
0x180002352  sub     rsp, 20h
0x180002356  mov     rbx, rcx
0x180002359  lea     rcx, CriticalSection; lpCriticalSection
0x180002360  call    cs:__imp_EnterCriticalSection
0x180002366  mov     eax, cs:_Init_global_epoch
0x18000236c  lea     rcx, CriticalSection; lpCriticalSection
0x180002373  mov     edx, cs:_tls_index
0x180002379  inc     eax
0x18000237b  mov     cs:_Init_global_epoch, eax
0x180002381  mov     [rbx], eax
0x180002383  mov     rax, gs:58h
0x18000238c  mov     r9d, 4
0x180002392  mov     r8, [rax+rdx*8]
0x180002396  mov     eax, cs:_Init_global_epoch
0x18000239c  mov     [r9+r8], eax
0x1800023a0  call    cs:__imp_LeaveCriticalSection
0x1800023a6  add     rsp, 20h
0x1800023aa  pop     rbx
0x1800023ab  jmp     _Init_thread_notify
```
