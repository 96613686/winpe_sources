# _Init_thread_footer

- ea: `0x18000214c`
- end: `0x1800021ac`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009d10`
- `0x18000ad80`
- `0x18000ae80`

## callees

- `0x180002220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000215c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000215c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000219c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000219c`

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
0x18000214c  push    rbx
0x18000214e  sub     rsp, 20h
0x180002152  mov     rbx, rcx
0x180002155  lea     rcx, CriticalSection; lpCriticalSection
0x18000215c  call    cs:__imp_EnterCriticalSection
0x180002162  mov     eax, cs:_Init_global_epoch
0x180002168  lea     rcx, CriticalSection; lpCriticalSection
0x18000216f  mov     edx, cs:_tls_index
0x180002175  inc     eax
0x180002177  mov     cs:_Init_global_epoch, eax
0x18000217d  mov     [rbx], eax
0x18000217f  mov     rax, gs:58h
0x180002188  mov     r9d, 4
0x18000218e  mov     r8, [rax+rdx*8]
0x180002192  mov     eax, cs:_Init_global_epoch
0x180002198  mov     [r9+r8], eax
0x18000219c  call    cs:__imp_LeaveCriticalSection
0x1800021a2  add     rsp, 20h
0x1800021a6  pop     rbx
0x1800021a7  jmp     _Init_thread_notify
```
