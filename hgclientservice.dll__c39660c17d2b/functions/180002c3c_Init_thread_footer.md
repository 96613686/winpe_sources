# _Init_thread_footer

- ea: `0x180002c3c`
- end: `0x180002c9c`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800136a4`

## callees

- `0x180002d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c4c`

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
0x180002c3c  push    rbx
0x180002c3e  sub     rsp, 20h
0x180002c42  mov     rbx, rcx
0x180002c45  lea     rcx, CriticalSection; lpCriticalSection
0x180002c4c  call    cs:__imp_EnterCriticalSection
0x180002c52  mov     eax, cs:_Init_global_epoch
0x180002c58  lea     rcx, CriticalSection; lpCriticalSection
0x180002c5f  mov     edx, cs:_tls_index
0x180002c65  inc     eax
0x180002c67  mov     cs:_Init_global_epoch, eax
0x180002c6d  mov     [rbx], eax
0x180002c6f  mov     rax, gs:58h
0x180002c78  mov     r9d, 4
0x180002c7e  mov     r8, [rax+rdx*8]
0x180002c82  mov     eax, cs:_Init_global_epoch
0x180002c88  mov     [r9+r8], eax
0x180002c8c  call    cs:__imp_LeaveCriticalSection
0x180002c92  add     rsp, 20h
0x180002c96  pop     rbx
0x180002c97  jmp     _Init_thread_notify
```
