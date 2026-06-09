# extmatcha(char const *,char const *)

- ea: `0x180199704`
- end: `0x180199797`
- name: `?extmatcha@@YAHPEBD0@Z`
- size: `147`
- prototype: `__int64 __fastcall(const char *, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180196a50`

## callees

- `0x180199704`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__splitpath_s` at `0x18019975d`
- `api-ms-win-crt-private-l1-1-0!_o__splitpath_s` at `0x18019975d`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18019976b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18019976b`

## pseudocode

```c
_BOOL8 __fastcall extmatcha(const char *a1, const char *a2)
{
  char Ext[272]; // [rsp+50h] [rbp-128h] BYREF

  if ( !a1 )
    return 0;
  _splitpath_s(a1, 0, 0, 0, 0, 0, 0, Ext, 0x101u);
  return (unsigned int)_o__stricmp(Ext, a2) == 0;
}

```

## disassembly

```asm
0x180199704  push    rbx
0x180199706  sub     rsp, 170h
0x18019970d  mov     rax, cs:__security_cookie
0x180199714  xor     rax, rsp
0x180199717  mov     [rsp+178h+var_18], rax
0x18019971f  mov     rbx, rdx
0x180199722  test    rcx, rcx
0x180199725  jz      short loc_18019977C
0x180199727  mov     [rsp+178h+ExtCount], 101h; ExtCount
0x180199730  lea     rax, [rsp+178h+var_128]
0x180199735  mov     [rsp+178h+Ext], rax; Ext
0x18019973a  xor     r9d, r9d; Dir
0x18019973d  mov     [rsp+178h+FilenameCount], 0; FilenameCount
0x180199746  xor     r8d, r8d; DriveCount
0x180199749  mov     [rsp+178h+Filename], 0; Filename
0x180199752  xor     edx, edx; Drive
0x180199754  mov     [rsp+178h+DirCount], 0; DirCount
0x18019975d  call    cs:__imp__splitpath_s
0x180199763  mov     rdx, rbx
0x180199766  lea     rcx, [rsp+178h+var_128]
0x18019976b  call    cs:__imp__o__stricmp
0x180199771  xor     ecx, ecx
0x180199773  test    eax, eax
0x180199775  setz    cl
0x180199778  mov     eax, ecx
0x18019977a  jmp     short loc_18019977E
0x18019977c  xor     eax, eax
0x18019977e  mov     rcx, [rsp+178h+var_18]
0x180199786  xor     rcx, rsp; StackCookie
0x180199789  call    __security_check_cookie
0x18019978e  add     rsp, 170h
0x180199795  pop     rbx
0x180199796  retn
```
