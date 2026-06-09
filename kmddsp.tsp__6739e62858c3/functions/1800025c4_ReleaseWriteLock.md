# ReleaseWriteLock

- ea: `0x1800025c4`
- end: `0x1800025f8`
- name: `ReleaseWriteLock`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e40`
- `0x1800021ac`
- `0x180002508`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800025d8`
- `KERNEL32!SetEvent` at `0x1800025d8`
- `KERNEL32!LeaveCriticalSection` at `0x1800025ec`

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
0x1800025c4  push    rbx
0x1800025c6  sub     rsp, 20h
0x1800025ca  mov     rbx, rcx
0x1800025cd  mov     dword ptr [rcx+30h], 0
0x1800025d4  mov     rcx, [rcx+28h]; hEvent
0x1800025d8  call    cs:__imp_SetEvent
0x1800025df  nop     dword ptr [rax+rax+00h]
0x1800025e4  mov     rcx, rbx
0x1800025e7  add     rsp, 20h
0x1800025eb  pop     rbx
0x1800025ec  jmp     cs:__imp_LeaveCriticalSection
```
