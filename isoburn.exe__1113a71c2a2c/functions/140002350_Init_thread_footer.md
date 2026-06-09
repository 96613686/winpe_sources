# _Init_thread_footer

- ea: `0x140002350`
- end: `0x1400023b0`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006390`
- `0x140006570`

## callees

- `0x140002424`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140002360`
- `KERNEL32!EnterCriticalSection` at `0x140002360`
- `KERNEL32!LeaveCriticalSection` at `0x1400023a0`
- `KERNEL32!LeaveCriticalSection` at `0x1400023a0`

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
0x140002350  push    rbx
0x140002352  sub     rsp, 20h
0x140002356  mov     rbx, rcx
0x140002359  lea     rcx, CriticalSection; lpCriticalSection
0x140002360  call    cs:__imp_EnterCriticalSection
0x140002366  mov     eax, cs:_Init_global_epoch
0x14000236c  lea     rcx, CriticalSection; lpCriticalSection
0x140002373  mov     edx, cs:_tls_index
0x140002379  inc     eax
0x14000237b  mov     cs:_Init_global_epoch, eax
0x140002381  mov     [rbx], eax
0x140002383  mov     rax, gs:58h
0x14000238c  mov     r9d, 4
0x140002392  mov     r8, [rax+rdx*8]
0x140002396  mov     eax, cs:_Init_global_epoch
0x14000239c  mov     [r9+r8], eax
0x1400023a0  call    cs:__imp_LeaveCriticalSection
0x1400023a6  add     rsp, 20h
0x1400023aa  pop     rbx
0x1400023ab  jmp     _Init_thread_notify
```
