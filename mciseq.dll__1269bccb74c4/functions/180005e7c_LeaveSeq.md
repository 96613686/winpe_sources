# LeaveSeq

- ea: `0x180005e7c`
- end: `0x180005e9d`
- name: `LeaveSeq`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x18000160c`
- `0x180001810`
- `0x180001a44`
- `0x1800022c0`
- `0x1800024d0`
- `0x180002a90`
- `0x180002eac`
- `0x180005ea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e87`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005e96`

## pseudocode

```c
void LeaveSeq()
{
  LeaveCriticalSection(&SeqCritSec);
  Sleep(4u);
}

```

## disassembly

```asm
0x180005e7c  sub     rsp, 28h
0x180005e80  lea     rcx, SeqCritSec; lpCriticalSection
0x180005e87  call    cs:__imp_LeaveCriticalSection
0x180005e8d  mov     ecx, 4
0x180005e92  add     rsp, 28h
0x180005e96  jmp     cs:__imp_Sleep
```
