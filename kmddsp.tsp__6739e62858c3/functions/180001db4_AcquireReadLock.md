# AcquireReadLock

- ea: `0x180001db4`
- end: `0x180001de0`
- name: `AcquireReadLock`
- size: `44`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ca4`
- `0x180001d2c`
- `0x180001f48`
- `0x180001fe4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180001dd4`
- `KERNEL32!EnterCriticalSection` at `0x180001dbd`
- `KERNEL32!EnterCriticalSection` at `0x180001dbd`

## pseudocode

```c
void __fastcall AcquireReadLock(struct _RTL_CRITICAL_SECTION *a1)
{
  EnterCriticalSection(a1);
  ++a1[1].LockCount;
  LeaveCriticalSection(a1);
}

```

## disassembly

```asm
0x180001db4  push    rbx
0x180001db6  sub     rsp, 20h
0x180001dba  mov     rbx, rcx
0x180001dbd  call    cs:__imp_EnterCriticalSection
0x180001dc4  nop     dword ptr [rax+rax+00h]
0x180001dc9  inc     dword ptr [rbx+30h]
0x180001dcc  mov     rcx, rbx
0x180001dcf  add     rsp, 20h
0x180001dd3  pop     rbx
0x180001dd4  jmp     cs:__imp_LeaveCriticalSection
```
