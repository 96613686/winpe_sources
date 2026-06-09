# _Init_thread_abort

- ea: `0x180004bc0`
- end: `0x180004bf3`
- name: `_Init_thread_abort`
- size: `51`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18002343e`
- `0x180023450`
- `0x180023462`
- `0x180023474`
- `0x180023486`
- `0x1800234c9`

## callees

- `0x180004cd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004bd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004bd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004be3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004be3`

## pseudocode

```c
__int64 __fastcall Init_thread_abort(_DWORD *a1)
{
  EnterCriticalSection(&stru_180032A78);
  *a1 = 0;
  LeaveCriticalSection(&stru_180032A78);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x180004bc0  push    rbx
0x180004bc2  sub     rsp, 20h
0x180004bc6  mov     rbx, rcx
0x180004bc9  lea     rcx, stru_180032A78; lpCriticalSection
0x180004bd0  call    cs:__imp_EnterCriticalSection
0x180004bd6  lea     rcx, stru_180032A78; lpCriticalSection
0x180004bdd  mov     dword ptr [rbx], 0
0x180004be3  call    cs:__imp_LeaveCriticalSection
0x180004be9  add     rsp, 20h
0x180004bed  pop     rbx
0x180004bee  jmp     _Init_thread_notify
```
