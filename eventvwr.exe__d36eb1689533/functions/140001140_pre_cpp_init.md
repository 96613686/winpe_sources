# pre_cpp_init

- ea: `0x140001140`
- end: `0x140001189`
- name: `pre_cpp_init`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!__getmainargs` at `0x140001178`
- `msvcrt!__getmainargs` at `0x140001178`

## pseudocode

```c
__int64 pre_cpp_init()
{
  __int64 result; // rax

  dword_1400060C4 = newmode;
  result = __getmainargs(&argc, &argv, &envp, (unsigned int)dowildcard, &dword_1400060C4);
  dword_1400060AC = result;
  return result;
}

```

## disassembly

```asm
0x140001140  sub     rsp, 38h
0x140001144  mov     eax, cs:_newmode
0x14000114a  lea     r8, envp
0x140001151  mov     r9d, cs:_dowildcard
0x140001158  lea     rdx, argv
0x14000115f  mov     cs:dword_1400060C4, eax
0x140001165  lea     rcx, argc
0x14000116c  lea     rax, dword_1400060C4
0x140001173  mov     [rsp+38h+var_18], rax
0x140001178  call    cs:__imp___getmainargs
0x14000117e  mov     cs:dword_1400060AC, eax
0x140001184  add     rsp, 38h
0x140001188  retn
```
