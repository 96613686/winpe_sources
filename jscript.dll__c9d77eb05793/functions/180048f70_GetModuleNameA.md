# GetModuleNameA

- ea: `0x180048f70`
- end: `0x180048ff5`
- name: `GetModuleNameA`
- size: `133`
- prototype: `__int64 __fastcall(char *Filename)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180048e00`

## callees

- `0x180048f70`
- `0x1800942d0`

## import_xrefs

- `msvcrt!_splitpath_s` at `0x180048fed`
- `msvcrt!_splitpath_s` at `0x180048fed`
- `KERNEL32!GetModuleFileNameA` at `0x180048f9b`
- `KERNEL32!GetModuleFileNameA` at `0x180048f9b`

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
0x180048f70  push    rbx
0x180048f72  sub     rsp, 170h
0x180048f79  mov     rax, cs:__security_cookie
0x180048f80  xor     rax, rsp
0x180048f83  mov     [rsp+178h+var_18], rax
0x180048f8b  mov     rbx, rcx
0x180048f8e  lea     rdx, [rsp+178h+Filename]; lpFilename
0x180048f93  xor     ecx, ecx; hModule
0x180048f95  mov     r8d, 104h; nSize
0x180048f9b  call    cs:__imp_GetModuleFileNameA
0x180048fa1  xor     ecx, ecx
0x180048fa3  test    eax, eax
0x180048fa5  jnz     short loc_180048FC3
0x180048fa7  or      eax, 0FFFFFFFFh
0x180048faa  mov     rcx, [rsp+178h+var_18]
0x180048fb2  xor     rcx, rsp; StackCookie
0x180048fb5  call    __security_check_cookie
0x180048fba  add     rsp, 170h
0x180048fc1  pop     rbx
0x180048fc2  retn
0x180048fc3  mov     [rsp+178h+ExtCount], rcx; ExtCount
0x180048fc8  xor     r9d, r9d; Dir
0x180048fcb  mov     [rsp+178h+Ext], rcx; Ext
0x180048fd0  xor     r8d, r8d; DriveCount
0x180048fd3  mov     [rsp+178h+FilenameCount], 104h; FilenameCount
0x180048fdc  xor     edx, edx; Drive
0x180048fde  mov     [rsp+178h+var_150], rbx; Filename
0x180048fe3  mov     [rsp+178h+DirCount], rcx; DirCount
0x180048fe8  lea     rcx, [rsp+178h+Filename]; FullPath
0x180048fed  call    cs:__imp__splitpath_s
0x180048ff3  jmp     short loc_180048FAA
```
