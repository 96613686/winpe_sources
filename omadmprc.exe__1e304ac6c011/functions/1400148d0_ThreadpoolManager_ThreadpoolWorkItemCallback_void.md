# ThreadpoolManager::ThreadpoolWorkItemCallback(void *)

- ea: `0x1400148d0`
- end: `0x140014905`
- name: `?ThreadpoolWorkItemCallback@ThreadpoolManager@@CAXPEAX@Z`
- size: `53`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140017010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400148f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ThreadpoolManager::ThreadpoolWorkItemCallback(_QWORD *a1)
{
  ((void (__fastcall *)(_QWORD))*a1)(a1[1]);
  _InterlockedDecrement(&ThreadpoolManager::m_numberOfWorkQueued);
  operator delete(a1);
}

```

## disassembly

```asm
0x1400148d0  push    rbx
0x1400148d2  sub     rsp, 20h
0x1400148d6  mov     rbx, rcx
0x1400148d9  mov     [rsp+28h+arg_0], rcx
0x1400148de  mov     rcx, [rcx+8]
0x1400148e2  mov     rax, [rbx]
0x1400148e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400148ea  lock dec cs:?m_numberOfWorkQueued@ThreadpoolManager@@0JC; long volatile ThreadpoolManager::m_numberOfWorkQueued
0x1400148f1  mov     rcx, rbx
0x1400148f4  add     rsp, 20h
0x1400148f8  pop     rbx
0x1400148f9  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
