# CProvClassContext::`scalar deleting destructor'(uint)

- ea: `0x180008dec`
- end: `0x180008e1b`
- name: `??_GCProvClassContext@@QEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CProvClassContext *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180008ef0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008e0c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008e0c`
- `KERNEL32!DeleteCriticalSection` at `0x180008e03`
- `KERNEL32!DeleteCriticalSection` at `0x180008e03`

## pseudocode

```c
CProvClassContext *__fastcall CProvClassContext::`scalar deleting destructor'(CProvClassContext *this)
{
  *(_QWORD *)this = &CProvClassContext::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008dec  push    rbx
0x180008dee  sub     rsp, 20h
0x180008df2  lea     rax, ??_7CProvClassContext@@6B@; const CProvClassContext::`vftable'
0x180008df9  mov     rbx, rcx
0x180008dfc  mov     [rcx], rax
0x180008dff  add     rcx, 8; lpCriticalSection
0x180008e03  call    cs:__imp_DeleteCriticalSection
0x180008e09  mov     rcx, rbx
0x180008e0c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008e12  mov     rax, rbx
0x180008e15  add     rsp, 20h
0x180008e19  pop     rbx
0x180008e1a  retn
```
