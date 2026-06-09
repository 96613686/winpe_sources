# _Init_thread_abort

- ea: `0x180001b90`
- end: `0x180001bc3`
- name: `_Init_thread_abort`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001dd85`
- `0x18001dd97`
- `0x18001deb7`
- `0x18001dec9`

## callees

- `0x180001ca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001bb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001bb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ba0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ba0`

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
0x180001b90  push    rbx
0x180001b92  sub     rsp, 20h
0x180001b96  mov     rbx, rcx
0x180001b99  lea     rcx, CriticalSection; lpCriticalSection
0x180001ba0  call    cs:__imp_EnterCriticalSection
0x180001ba6  lea     rcx, CriticalSection; lpCriticalSection
0x180001bad  mov     dword ptr [rbx], 0
0x180001bb3  call    cs:__imp_LeaveCriticalSection
0x180001bb9  add     rsp, 20h
0x180001bbd  pop     rbx
0x180001bbe  jmp     _Init_thread_notify
```
