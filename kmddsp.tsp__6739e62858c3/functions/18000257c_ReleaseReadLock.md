# ReleaseReadLock

- ea: `0x18000257c`
- end: `0x1800025bb`
- name: `ReleaseReadLock`
- size: `63`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ca4`
- `0x180001d2c`
- `0x180001f48`
- `0x180001fe4`
- `0x180002494`
- `0x180002508`

## callees

- `0x18000257c`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000259b`
- `KERNEL32!SetEvent` at `0x18000259b`
- `KERNEL32!LeaveCriticalSection` at `0x1800025af`
- `KERNEL32!EnterCriticalSection` at `0x180002585`
- `KERNEL32!EnterCriticalSection` at `0x180002585`

## pseudocode

```c
void __fastcall ReleaseReadLock(struct _RTL_CRITICAL_SECTION *a1)
{
  EnterCriticalSection(a1);
  if ( a1[1].LockCount-- == 1 )
    SetEvent(a1[1].DebugInfo);
  LeaveCriticalSection(a1);
}

```

## disassembly

```asm
0x18000257c  push    rbx
0x18000257e  sub     rsp, 20h
0x180002582  mov     rbx, rcx
0x180002585  call    cs:__imp_EnterCriticalSection
0x18000258c  nop     dword ptr [rax+rax+00h]
0x180002591  add     dword ptr [rbx+30h], 0FFFFFFFFh
0x180002595  jnz     short loc_1800025A7
0x180002597  mov     rcx, [rbx+28h]; hEvent
0x18000259b  call    cs:__imp_SetEvent
0x1800025a2  nop     dword ptr [rax+rax+00h]
0x1800025a7  mov     rcx, rbx
0x1800025aa  add     rsp, 20h
0x1800025ae  pop     rbx
0x1800025af  jmp     cs:__imp_LeaveCriticalSection
```
