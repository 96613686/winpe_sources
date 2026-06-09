# std::bad_alloc::bad_alloc(std::bad_alloc const &)

- ea: `0x140001844`
- end: `0x140001866`
- name: `??0bad_alloc@std@@QEAA@AEBV01@@Z`
- size: `34`
- prototype: `__int64 __fastcall(std::bad_alloc *__hidden this, const struct std::bad_alloc *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400018e0`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x14000184d`
- `msvcrt!??0exception@@QEAA@AEBV0@@Z` at `0x14000184d`

## pseudocode

```c
std::bad_alloc *__fastcall std::bad_alloc::bad_alloc(std::bad_alloc *this, const struct std::bad_alloc *a2)
{
  exception::exception(this, a2);
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  return this;
}

```

## disassembly

```asm
0x140001844  push    rbx
0x140001846  sub     rsp, 20h
0x14000184a  mov     rbx, rcx
0x14000184d  call    cs:__imp_??0exception@@QEAA@AEBV0@@Z; exception::exception(exception const &)
0x140001853  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14000185a  mov     [rbx], rax
0x14000185d  mov     rax, rbx
0x140001860  add     rsp, 20h
0x140001864  pop     rbx
0x140001865  retn
```
