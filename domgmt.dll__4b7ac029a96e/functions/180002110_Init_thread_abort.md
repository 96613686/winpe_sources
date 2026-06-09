# _Init_thread_abort

- ea: `0x180002110`
- end: `0x180002143`
- name: `_Init_thread_abort`
- size: `51`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dc7c`

## callees

- `0x180002220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002120`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002120`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002133`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002133`

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
0x180002110  push    rbx
0x180002112  sub     rsp, 20h
0x180002116  mov     rbx, rcx
0x180002119  lea     rcx, CriticalSection; lpCriticalSection
0x180002120  call    cs:__imp_EnterCriticalSection
0x180002126  lea     rcx, CriticalSection; lpCriticalSection
0x18000212d  mov     dword ptr [rbx], 0
0x180002133  call    cs:__imp_LeaveCriticalSection
0x180002139  add     rsp, 20h
0x18000213d  pop     rbx
0x18000213e  jmp     _Init_thread_notify
```
