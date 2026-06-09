# HashTableBase::~HashTableBase(void)

- ea: `0x18002d7d8`
- end: `0x18002d800`
- name: `??1HashTableBase@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(HashTableBase *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180020fdc`
- `0x18002d750`

## callees

- `0x18002d808`

## import_xrefs

- `msvcrt!free` at `0x18002d7ea`
- `msvcrt!free` at `0x18002d7ea`
- `KERNEL32!DeleteCriticalSection` at `0x18002d7f9`

## pseudocode

```c
void __fastcall HashTableBase::~HashTableBase(HashTableBase *this)
{
  HashTableBase::clear(this);
  free(*((void **)this + 1));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x18002d7d8  push    rbx
0x18002d7da  sub     rsp, 20h
0x18002d7de  mov     rbx, rcx
0x18002d7e1  call    ?clear@HashTableBase@@QEAAXXZ; HashTableBase::clear(void)
0x18002d7e6  mov     rcx, [rbx+8]; Block
0x18002d7ea  call    cs:__imp_free
0x18002d7f0  lea     rcx, [rbx+18h]
0x18002d7f4  add     rsp, 20h
0x18002d7f8  pop     rbx
0x18002d7f9  jmp     cs:__imp_DeleteCriticalSection
```
