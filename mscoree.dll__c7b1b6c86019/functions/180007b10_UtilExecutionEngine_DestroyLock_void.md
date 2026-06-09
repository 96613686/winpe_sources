# UtilExecutionEngine::DestroyLock(void *)

- ea: `0x180007b10`
- end: `0x180007b2f`
- name: `?DestroyLock@UtilExecutionEngine@@EEAAXPEAX@Z`
- size: `31`
- prototype: `void(UtilExecutionEngine *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f264`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007b1c`
- `KERNEL32!DeleteCriticalSection` at `0x180007b1c`

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
0x180007b10  push    rbx
0x180007b12  sub     rsp, 20h
0x180007b16  mov     rcx, rdx; lpCriticalSection
0x180007b19  mov     rbx, rdx
0x180007b1c  call    cs:__imp_DeleteCriticalSection
0x180007b22  mov     rcx, rbx
0x180007b25  add     rsp, 20h
0x180007b29  pop     rbx
0x180007b2a  jmp     free
```
