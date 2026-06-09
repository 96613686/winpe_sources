# pre_cpp_init

- ea: `0x140001170`
- end: `0x1400011b9`
- name: `pre_cpp_init`
- size: `73`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!__wgetmainargs` at `0x1400011a8`
- `msvcrt!__wgetmainargs` at `0x1400011a8`

## pseudocode

```c
__int64 pre_cpp_init()
{
  __int64 result; // rax

  dword_140003144 = newmode;
  result = __wgetmainargs(
             &dword_140003128,
             &qword_140003130,
             &qword_140003138,
             (unsigned int)dowildcard,
             &dword_140003144);
  dword_14000312C = result;
  return result;
}

```

## disassembly

```asm
0x140001170  sub     rsp, 38h
0x140001174  mov     eax, cs:_newmode
0x14000117a  lea     r8, qword_140003138
0x140001181  mov     r9d, cs:_dowildcard
0x140001188  lea     rdx, qword_140003130
0x14000118f  mov     cs:dword_140003144, eax
0x140001195  lea     rcx, dword_140003128
0x14000119c  lea     rax, dword_140003144
0x1400011a3  mov     [rsp+38h+var_18], rax
0x1400011a8  call    cs:__imp___wgetmainargs
0x1400011ae  mov     cs:dword_14000312C, eax
0x1400011b4  add     rsp, 38h
0x1400011b8  retn
```
