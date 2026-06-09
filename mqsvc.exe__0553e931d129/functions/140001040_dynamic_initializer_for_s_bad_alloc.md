# _dynamic_initializer_for__s_bad_alloc__

- ea: `0x140001040`
- end: `0x14000107c`
- name: `_dynamic_initializer_for__s_bad_alloc__`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000174c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x140001058`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x140001058`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int dynamic_initializer_for__s_bad_alloc__()
{
  exception::exception((exception *)&qword_1400036E0, &std::_bad_alloc_Message, 1);
  qword_1400036E0 = (__int64)&std::bad_alloc::`vftable';
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__s_bad_alloc__);
}

```

## disassembly

```asm
0x140001040  sub     rsp, 28h
0x140001044  mov     r8d, 1
0x14000104a  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x140001051  lea     rcx, qword_1400036E0
0x140001058  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x14000105e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x140001065  mov     cs:qword_1400036E0, rax
0x14000106c  lea     rcx, _dynamic_atexit_destructor_for__s_bad_alloc__
0x140001073  add     rsp, 28h
0x140001077  jmp     atexit
```
