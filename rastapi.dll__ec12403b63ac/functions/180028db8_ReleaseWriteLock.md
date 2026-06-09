# ReleaseWriteLock

- ea: `0x180028db8`
- end: `0x180028de1`
- name: `ReleaseWriteLock`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800281f0`
- `0x1800287d8`
- `0x180028c70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028dda`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028dcc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028dcc`

## pseudocode

```c
void __fastcall ReleaseWriteLock(struct _RTL_CRITICAL_SECTION *a1)
{
  a1[1].LockCount = 0;
  SetEvent(a1[1].DebugInfo);
  LeaveCriticalSection(a1);
}

```

## disassembly

```asm
0x180028db8  push    rbx
0x180028dba  sub     rsp, 20h
0x180028dbe  mov     rbx, rcx
0x180028dc1  mov     dword ptr [rcx+30h], 0
0x180028dc8  mov     rcx, [rcx+28h]; hEvent
0x180028dcc  call    cs:__imp_SetEvent
0x180028dd2  mov     rcx, rbx
0x180028dd5  add     rsp, 20h
0x180028dd9  pop     rbx
0x180028dda  jmp     cs:__imp_LeaveCriticalSection
```
