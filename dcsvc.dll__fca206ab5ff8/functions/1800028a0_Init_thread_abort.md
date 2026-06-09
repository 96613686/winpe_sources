# _Init_thread_abort

- ea: `0x1800028a0`
- end: `0x1800028d3`
- name: `_Init_thread_abort`
- size: `51`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011e11`

## callees

- `0x1800029b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800028b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800028b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800028c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800028c3`

## pseudocode

```c
__int64 __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&stru_18001B688);
  *a1 = 0;
  LeaveCriticalSection(&stru_18001B688);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x1800028a0  push    rbx
0x1800028a2  sub     rsp, 20h
0x1800028a6  mov     rbx, rcx
0x1800028a9  lea     rcx, stru_18001B688; lpCriticalSection
0x1800028b0  call    cs:__imp_EnterCriticalSection
0x1800028b6  lea     rcx, stru_18001B688; lpCriticalSection
0x1800028bd  mov     dword ptr [rbx], 0
0x1800028c3  call    cs:__imp_LeaveCriticalSection
0x1800028c9  add     rsp, 20h
0x1800028cd  pop     rbx
0x1800028ce  jmp     _Init_thread_notify
```
