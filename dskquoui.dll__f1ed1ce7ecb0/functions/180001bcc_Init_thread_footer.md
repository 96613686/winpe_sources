# _Init_thread_footer

- ea: `0x180001bcc`
- end: `0x180001c2c`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012b10`
- `0x180014220`

## callees

- `0x180001ca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bdc`

## pseudocode

```c
int __fastcall Init_thread_footer(_DWORD *a1)
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
0x180001bcc  push    rbx
0x180001bce  sub     rsp, 20h
0x180001bd2  mov     rbx, rcx
0x180001bd5  lea     rcx, CriticalSection; lpCriticalSection
0x180001bdc  call    cs:__imp_EnterCriticalSection
0x180001be2  mov     eax, cs:_Init_global_epoch
0x180001be8  lea     rcx, CriticalSection; lpCriticalSection
0x180001bef  mov     edx, cs:_tls_index
0x180001bf5  inc     eax
0x180001bf7  mov     cs:_Init_global_epoch, eax
0x180001bfd  mov     [rbx], eax
0x180001bff  mov     rax, gs:58h
0x180001c08  mov     r9d, 4
0x180001c0e  mov     r8, [rax+rdx*8]
0x180001c12  mov     eax, cs:_Init_global_epoch
0x180001c18  mov     [r9+r8], eax
0x180001c1c  call    cs:__imp_LeaveCriticalSection
0x180001c22  add     rsp, 20h
0x180001c26  pop     rbx
0x180001c27  jmp     _Init_thread_notify
```
