# HashTableBase::~HashTableBase(void)

- ea: `0x180026df0`
- end: `0x180026e18`
- name: `??1HashTableBase@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(HashTableBase *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026d68`

## callees

- `0x180026e20`

## import_xrefs

- `msvcrt!free` at `0x180026e02`
- `msvcrt!free` at `0x180026e02`
- `KERNEL32!DeleteCriticalSection` at `0x180026e11`

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
0x180026df0  push    rbx
0x180026df2  sub     rsp, 20h
0x180026df6  mov     rbx, rcx
0x180026df9  call    ?clear@HashTableBase@@QEAAXXZ; HashTableBase::clear(void)
0x180026dfe  mov     rcx, [rbx+8]; Block
0x180026e02  call    cs:__imp_free
0x180026e08  lea     rcx, [rbx+18h]
0x180026e0c  add     rsp, 20h
0x180026e10  pop     rbx
0x180026e11  jmp     cs:__imp_DeleteCriticalSection
```
