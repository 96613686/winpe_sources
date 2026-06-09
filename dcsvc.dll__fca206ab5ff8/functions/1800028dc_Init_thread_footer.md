# _Init_thread_footer

- ea: `0x1800028dc`
- end: `0x18000293c`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e83c`

## callees

- `0x1800029b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800028ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800028ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000292c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000292c`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_18001B688);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_18001B688);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x1800028dc  push    rbx
0x1800028de  sub     rsp, 20h
0x1800028e2  mov     rbx, rcx
0x1800028e5  lea     rcx, stru_18001B688; lpCriticalSection
0x1800028ec  call    cs:__imp_EnterCriticalSection
0x1800028f2  mov     eax, cs:_Init_global_epoch
0x1800028f8  lea     rcx, stru_18001B688; lpCriticalSection
0x1800028ff  mov     edx, cs:_tls_index
0x180002905  inc     eax
0x180002907  mov     cs:_Init_global_epoch, eax
0x18000290d  mov     [rbx], eax
0x18000290f  mov     rax, gs:58h
0x180002918  mov     r9d, 4
0x18000291e  mov     r8, [rax+rdx*8]
0x180002922  mov     eax, cs:_Init_global_epoch
0x180002928  mov     [r9+r8], eax
0x18000292c  call    cs:__imp_LeaveCriticalSection
0x180002932  add     rsp, 20h
0x180002936  pop     rbx
0x180002937  jmp     _Init_thread_notify
```
