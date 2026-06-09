# _Init_thread_footer

- ea: `0x180004bfc`
- end: `0x180004c5c`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180020ef8`
- `0x180021688`
- `0x180021ec4`

## callees

- `0x180004cd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004c0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004c0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c4c`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_180032A78);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_180032A78);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180004bfc  push    rbx
0x180004bfe  sub     rsp, 20h
0x180004c02  mov     rbx, rcx
0x180004c05  lea     rcx, stru_180032A78; lpCriticalSection
0x180004c0c  call    cs:__imp_EnterCriticalSection
0x180004c12  mov     eax, cs:_Init_global_epoch
0x180004c18  lea     rcx, stru_180032A78; lpCriticalSection
0x180004c1f  mov     edx, cs:_tls_index
0x180004c25  inc     eax
0x180004c27  mov     cs:_Init_global_epoch, eax
0x180004c2d  mov     [rbx], eax
0x180004c2f  mov     rax, gs:58h
0x180004c38  mov     r9d, 4
0x180004c3e  mov     r8, [rax+rdx*8]
0x180004c42  mov     eax, cs:_Init_global_epoch
0x180004c48  mov     [r9+r8], eax
0x180004c4c  call    cs:__imp_LeaveCriticalSection
0x180004c52  add     rsp, 20h
0x180004c56  pop     rbx
0x180004c57  jmp     _Init_thread_notify
```
