# _Init_thread_footer

- ea: `0x140003150`
- end: `0x1400031b0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140027858`
- `0x14002793c`

## callees

- `0x140003224`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400031a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400031a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003160`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003160`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&CriticalSection);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 304LL) = Init_global_epoch;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x140003150  push    rbx
0x140003152  sub     rsp, 20h
0x140003156  mov     rbx, rcx
0x140003159  lea     rcx, CriticalSection; lpCriticalSection
0x140003160  call    cs:__imp_EnterCriticalSection
0x140003166  mov     eax, cs:_Init_global_epoch
0x14000316c  lea     rcx, CriticalSection; lpCriticalSection
0x140003173  mov     edx, cs:_tls_index
0x140003179  inc     eax
0x14000317b  mov     cs:_Init_global_epoch, eax
0x140003181  mov     [rbx], eax
0x140003183  mov     rax, gs:58h
0x14000318c  mov     r9d, 130h
0x140003192  mov     r8, [rax+rdx*8]
0x140003196  mov     eax, cs:_Init_global_epoch
0x14000319c  mov     [r9+r8], eax
0x1400031a0  call    cs:__imp_LeaveCriticalSection
0x1400031a6  add     rsp, 20h
0x1400031aa  pop     rbx
0x1400031ab  jmp     _Init_thread_notify
```
