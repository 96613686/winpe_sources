# GetModuleNameA

- ea: `0x180049388`
- end: `0x18004941a`
- name: `GetModuleNameA`
- size: `146`
- prototype: `__int64 __fastcall(char *Filename)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800491f8`

## callees

- `0x180049388`
- `0x1800966e0`

## import_xrefs

- `msvcrt!_splitpath_s` at `0x18004940c`
- `msvcrt!_splitpath_s` at `0x18004940c`
- `KERNEL32!GetModuleFileNameA` at `0x1800493b3`
- `KERNEL32!GetModuleFileNameA` at `0x1800493b3`

## pseudocode

```c
errno_t __fastcall GetModuleNameA(char *Filename)
{
  CHAR Filenamea[272]; // [rsp+50h] [rbp-128h] BYREF

  if ( GetModuleFileNameA(0, Filenamea, 0x104u) )
    return _splitpath_s(Filenamea, 0, 0, 0, 0, Filename, 0x104u, 0, 0);
  else
    return -1;
}

```

## disassembly

```asm
0x180049388  push    rbx
0x18004938a  sub     rsp, 170h
0x180049391  mov     rax, cs:__security_cookie
0x180049398  xor     rax, rsp
0x18004939b  mov     [rsp+178h+var_18], rax
0x1800493a3  mov     rbx, rcx
0x1800493a6  lea     rdx, [rsp+178h+Filename]; lpFilename
0x1800493ab  xor     ecx, ecx; hModule
0x1800493ad  mov     r8d, 104h; nSize
0x1800493b3  call    cs:__imp_GetModuleFileNameA
0x1800493ba  nop     dword ptr [rax+rax+00h]
0x1800493bf  xor     ecx, ecx
0x1800493c1  test    eax, eax
0x1800493c3  jnz     short loc_1800493E2
0x1800493c5  or      eax, 0FFFFFFFFh
0x1800493c8  mov     rcx, [rsp+178h+var_18]
0x1800493d0  xor     rcx, rsp; StackCookie
0x1800493d3  call    __security_check_cookie
0x1800493d8  add     rsp, 170h
0x1800493df  pop     rbx
0x1800493e0  retn
0x1800493e2  mov     [rsp+178h+ExtCount], rcx; ExtCount
0x1800493e7  xor     r9d, r9d; Dir
0x1800493ea  mov     [rsp+178h+Ext], rcx; Ext
0x1800493ef  xor     r8d, r8d; DriveCount
0x1800493f2  mov     [rsp+178h+FilenameCount], 104h; FilenameCount
0x1800493fb  xor     edx, edx; Drive
0x1800493fd  mov     [rsp+178h+var_150], rbx; Filename
0x180049402  mov     [rsp+178h+DirCount], rcx; DirCount
0x180049407  lea     rcx, [rsp+178h+Filename]; FullPath
0x18004940c  call    cs:__imp__splitpath_s
0x180049413  nop     dword ptr [rax+rax+00h]
0x180049418  jmp     short loc_1800493C8
```
