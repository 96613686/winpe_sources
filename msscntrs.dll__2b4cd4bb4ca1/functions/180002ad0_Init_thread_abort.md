# _Init_thread_abort

- ea: `0x180002ad0`
- end: `0x180002b03`
- name: `_Init_thread_abort`
- size: `51`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016256`

## callees

- `0x180002be0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ae0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ae0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002af3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002af3`

## pseudocode

```c
__int64 __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&stru_180021DA8);
  *a1 = 0;
  LeaveCriticalSection(&stru_180021DA8);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180002ad0  push    rbx
0x180002ad2  sub     rsp, 20h
0x180002ad6  mov     rbx, rcx
0x180002ad9  lea     rcx, stru_180021DA8; lpCriticalSection
0x180002ae0  call    cs:__imp_EnterCriticalSection
0x180002ae6  lea     rcx, stru_180021DA8; lpCriticalSection
0x180002aed  mov     dword ptr [rbx], 0
0x180002af3  call    cs:__imp_LeaveCriticalSection
0x180002af9  add     rsp, 20h
0x180002afd  pop     rbx
0x180002afe  jmp     _Init_thread_notify
```
