# _dynamic_atexit_destructor_for__s_bad_alloc__

- ea: `0x140001a00`
- end: `0x140001a1c`
- name: `_dynamic_atexit_destructor_for__s_bad_alloc__`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x140001a15`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_bad_alloc__()
{
  qword_1400036E0 = (__int64)&std::bad_alloc::`vftable';
  exception::~exception((exception *)&qword_1400036E0);
}

```

## disassembly

```asm
0x140001a00  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x140001a07  lea     rcx, qword_1400036E0
0x140001a0e  mov     cs:qword_1400036E0, rax
0x140001a15  jmp     cs:__imp_??1exception@@UEAA@XZ; exception::~exception(void)
```
