# std::bad_alloc::~bad_alloc(void)

- ea: `0x14000186c`
- end: `0x14000187d`
- name: `??1bad_alloc@std@@UEAA@XZ`
- size: `17`
- prototype: `void __fastcall(std::bad_alloc *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x140001876`

## pseudocode

```c
void __fastcall std::bad_alloc::~bad_alloc(std::bad_alloc *this)
{
  *(_QWORD *)this = &std::bad_alloc::`vftable';
  exception::~exception(this);
}

```

## disassembly

```asm
0x14000186c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x140001873  mov     [rcx], rax
0x140001876  jmp     cs:__imp_??1exception@@UEAA@XZ; exception::~exception(void)
```
