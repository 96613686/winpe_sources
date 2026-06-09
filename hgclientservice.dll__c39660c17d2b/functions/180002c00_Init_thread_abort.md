# _Init_thread_abort

- ea: `0x180002c00`
- end: `0x180002c33`
- name: `_Init_thread_abort`
- size: `51`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800166b2`

## callees

- `0x180002d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c10`

## pseudocode

```c
__int64 __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&CriticalSection);
  *a1 = 0;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180002c00  push    rbx
0x180002c02  sub     rsp, 20h
0x180002c06  mov     rbx, rcx
0x180002c09  lea     rcx, CriticalSection; lpCriticalSection
0x180002c10  call    cs:__imp_EnterCriticalSection
0x180002c16  lea     rcx, CriticalSection; lpCriticalSection
0x180002c1d  mov     dword ptr [rbx], 0
0x180002c23  call    cs:__imp_LeaveCriticalSection
0x180002c29  add     rsp, 20h
0x180002c2d  pop     rbx
0x180002c2e  jmp     _Init_thread_notify
```
