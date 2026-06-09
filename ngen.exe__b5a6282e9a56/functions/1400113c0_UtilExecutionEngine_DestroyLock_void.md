# UtilExecutionEngine::DestroyLock(void *)

- ea: `0x1400113c0`
- end: `0x1400113e1`
- name: `?DestroyLock@UtilExecutionEngine@@EEAAXPEAX@Z`
- size: `33`
- prototype: `void __fastcall(UtilExecutionEngine *this, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400113cc`
- `KERNEL32!DeleteCriticalSection` at `0x1400113cc`
- `ucrtbase_clr0400!free` at `0x1400113da`

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
0x1400113c0  push    rbx
0x1400113c2  sub     rsp, 20h
0x1400113c6  mov     rcx, rdx; lpCriticalSection
0x1400113c9  mov     rbx, rdx
0x1400113cc  call    cs:__imp_DeleteCriticalSection
0x1400113d2  mov     rcx, rbx
0x1400113d5  add     rsp, 20h
0x1400113d9  pop     rbx
0x1400113da  jmp     cs:__imp_free
```
