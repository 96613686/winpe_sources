# UtilExecutionEngine::DestroyLock(void *)

- ea: `0x18003c020`
- end: `0x18003c041`
- name: `?DestroyLock@UtilExecutionEngine@@EEAAXPEAX@Z`
- size: `33`
- prototype: `void __fastcall(UtilExecutionEngine *this, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18003c02c`
- `KERNEL32!DeleteCriticalSection` at `0x18003c02c`
- `ucrtbase_clr0400!free` at `0x18003c03a`

## pseudocode

```c
void __fastcall UtilExecutionEngine::DestroyLock(UtilExecutionEngine *this, struct _RTL_CRITICAL_SECTION *a2)
{
  DeleteCriticalSection(a2);
  free(a2);
}

```

## disassembly

```asm
0x18003c020  push    rbx
0x18003c022  sub     rsp, 20h
0x18003c026  mov     rcx, rdx; lpCriticalSection
0x18003c029  mov     rbx, rdx
0x18003c02c  call    cs:__imp_DeleteCriticalSection
0x18003c032  mov     rcx, rbx
0x18003c035  add     rsp, 20h
0x18003c039  pop     rbx
0x18003c03a  jmp     cs:__imp_free
```
