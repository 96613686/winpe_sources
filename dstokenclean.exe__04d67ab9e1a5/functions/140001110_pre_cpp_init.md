# pre_cpp_init

- ea: `0x140001110`
- end: `0x140001159`
- name: `pre_cpp_init`
- size: `73`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!__wgetmainargs` at `0x140001148`
- `msvcrt!__wgetmainargs` at `0x140001148`

## pseudocode

```c
__int64 pre_cpp_init()
{
  __int64 result; // rax

  dword_140005164 = newmode;
  result = __wgetmainargs(
             &dword_140005148,
             &qword_140005150,
             &qword_140005158,
             (unsigned int)dowildcard,
             &dword_140005164);
  dword_14000514C = result;
  return result;
}

```

## disassembly

```asm
0x140001110  sub     rsp, 38h
0x140001114  mov     eax, cs:_newmode
0x14000111a  lea     r8, qword_140005158
0x140001121  mov     r9d, cs:_dowildcard
0x140001128  lea     rdx, qword_140005150
0x14000112f  mov     cs:dword_140005164, eax
0x140001135  lea     rcx, dword_140005148
0x14000113c  lea     rax, dword_140005164
0x140001143  mov     [rsp+38h+var_18], rax
0x140001148  call    cs:__imp___wgetmainargs
0x14000114e  mov     cs:dword_14000514C, eax
0x140001154  add     rsp, 38h
0x140001158  retn
```
