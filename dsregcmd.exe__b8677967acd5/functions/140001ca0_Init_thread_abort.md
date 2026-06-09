# _Init_thread_abort

- ea: `0x140001ca0`
- end: `0x140001cd3`
- name: `_Init_thread_abort`
- size: `51`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14002c4f2`
- `0x14002e5ca`
- `0x14002e66c`
- `0x14002e67e`
- `0x14002e6a2`
- `0x14002ebad`

## callees

- `0x140001db0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140001cc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140001cc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001cb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001cb0`

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
0x140001ca0  push    rbx
0x140001ca2  sub     rsp, 20h
0x140001ca6  mov     rbx, rcx
0x140001ca9  lea     rcx, CriticalSection; lpCriticalSection
0x140001cb0  call    cs:__imp_EnterCriticalSection
0x140001cb6  lea     rcx, CriticalSection; lpCriticalSection
0x140001cbd  mov     dword ptr [rbx], 0
0x140001cc3  call    cs:__imp_LeaveCriticalSection
0x140001cc9  add     rsp, 20h
0x140001ccd  pop     rbx
0x140001cce  jmp     _Init_thread_notify
```
