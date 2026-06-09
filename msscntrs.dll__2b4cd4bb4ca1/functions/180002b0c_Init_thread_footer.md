# _Init_thread_footer

- ea: `0x180002b0c`
- end: `0x180002b6c`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d9bc`
- `0x18000df84`

## callees

- `0x180002be0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b5c`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_180021DA8);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_180021DA8);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180002b0c  push    rbx
0x180002b0e  sub     rsp, 20h
0x180002b12  mov     rbx, rcx
0x180002b15  lea     rcx, stru_180021DA8; lpCriticalSection
0x180002b1c  call    cs:__imp_EnterCriticalSection
0x180002b22  mov     eax, cs:_Init_global_epoch
0x180002b28  lea     rcx, stru_180021DA8; lpCriticalSection
0x180002b2f  mov     edx, cs:_tls_index
0x180002b35  inc     eax
0x180002b37  mov     cs:_Init_global_epoch, eax
0x180002b3d  mov     [rbx], eax
0x180002b3f  mov     rax, gs:58h
0x180002b48  mov     r9d, 4
0x180002b4e  mov     r8, [rax+rdx*8]
0x180002b52  mov     eax, cs:_Init_global_epoch
0x180002b58  mov     [r9+r8], eax
0x180002b5c  call    cs:__imp_LeaveCriticalSection
0x180002b62  add     rsp, 20h
0x180002b66  pop     rbx
0x180002b67  jmp     _Init_thread_notify
```
