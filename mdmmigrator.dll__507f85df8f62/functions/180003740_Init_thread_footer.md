# _Init_thread_footer

- ea: `0x180003740`
- end: `0x1800037a0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001dce8`

## callees

- `0x180003814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003790`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003750`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003750`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_18002B5C8);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_18002B5C8);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180003740  push    rbx
0x180003742  sub     rsp, 20h
0x180003746  mov     rbx, rcx
0x180003749  lea     rcx, stru_18002B5C8; lpCriticalSection
0x180003750  call    cs:__imp_EnterCriticalSection
0x180003756  mov     eax, cs:_Init_global_epoch
0x18000375c  lea     rcx, stru_18002B5C8; lpCriticalSection
0x180003763  mov     edx, cs:_tls_index
0x180003769  inc     eax
0x18000376b  mov     cs:_Init_global_epoch, eax
0x180003771  mov     [rbx], eax
0x180003773  mov     rax, gs:58h
0x18000377c  mov     r9d, 4
0x180003782  mov     r8, [rax+rdx*8]
0x180003786  mov     eax, cs:_Init_global_epoch
0x18000378c  mov     [r9+r8], eax
0x180003790  call    cs:__imp_LeaveCriticalSection
0x180003796  add     rsp, 20h
0x18000379a  pop     rbx
0x18000379b  jmp     _Init_thread_notify
```
