# CreateFtpPidlFromFtpWirePath(char const *,ulong *,_ITEMIDLIST * *,int,int)

- ea: `0x18001b614`
- end: `0x18001b70a`
- name: `?CreateFtpPidlFromFtpWirePath@@YAJPEBDPEAKPEAPEFAU_ITEMIDLIST@@HH@Z`
- size: `246`
- prototype: `__int64 __fastcall(const char *, unsigned int *, struct _ITEMIDLIST **, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cbfc`
- `0x18001b614`
- `0x18001bc60`

## callees

- `0x18001b614`
- `0x18001b710`
- `0x180026ef0`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x18001b6be`
- `SHELL32!__imp_ILCombine` at `0x18001b6be`
- `SHELL32!__imp_ILFree` at `0x18001b6cf`
- `SHELL32!__imp_ILFree` at `0x18001b6e7`
- `SHELL32!__imp_ILFree` at `0x18001b6cf`
- `SHELL32!__imp_ILFree` at `0x18001b6e7`
- `KERNEL32!lstrcmpA` at `0x18001b651`
- `KERNEL32!lstrcmpA` at `0x18001b651`

## pseudocode

```c
__int64 __fastcall CreateFtpPidlFromFtpWirePath(const char *a1, const ITEMIDLIST *a2, struct _ITEMIDLIST **a3)
{
  bool v4; // zf
  unsigned int *v6; // rdx
  int v7; // r9d
  signed int FtpPidlFromFtpWirePathHelper; // ebx
  struct _ITEMIDLIST *v9; // rax
  ITEMIDLIST *v10; // rcx
  struct _ITEMIDLIST *v11; // rbx
  int v13; // [rsp+20h] [rbp-28h]
  LPCITEMIDLIST pidl1; // [rsp+50h] [rbp+8h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+58h] [rbp+10h] BYREF
  PCSTR pszStart; // [rsp+60h] [rbp+18h] BYREF

  pidl2 = a2;
  *a3 = 0;
  v4 = *a1 == 0;
  pszStart = 0;
  pidl1 = 0;
  if ( v4 || !lstrcmpA(a1, "/") )
    return 0;
  FtpPidlFromFtpWirePathHelper = CreateFtpPidlFromFtpWirePathHelper(
                                   a1,
                                   v6,
                                   a3,
                                   v7,
                                   v13,
                                   (struct _ITEMIDLIST **)&pidl1,
                                   (char **)&pszStart);
  if ( FtpPidlFromFtpWirePathHelper >= 0 && pszStart )
  {
    pidl2 = 0;
    FtpPidlFromFtpWirePathHelper = CreateFtpPidlFromFtpWirePath(pszStart, 0, (struct _ITEMIDLIST **)&pidl2, 1, 1);
    if ( FtpPidlFromFtpWirePathHelper >= 0 )
    {
      v9 = ILCombine(pidl1, pidl2);
      v10 = (ITEMIDLIST *)pidl2;
      v11 = v9;
      *a3 = v9;
      ILFree(v10);
      FtpPidlFromFtpWirePathHelper = v11 == 0 ? 0x8007000E : 0;
    }
    ILFree((LPITEMIDLIST)pidl1);
    Str_SetPtrA(&pszStart, 0);
  }
  return (unsigned int)FtpPidlFromFtpWirePathHelper;
}

```

## disassembly

```asm
0x18001b614  mov     rax, rsp
0x18001b617  mov     [rax+20h], rbx
0x18001b61b  mov     [rax+10h], rdx
0x18001b61f  push    rdi
0x18001b620  sub     rsp, 40h
0x18001b624  mov     qword ptr [r8], 0
0x18001b62b  mov     rdi, r8
0x18001b62e  cmp     byte ptr [rcx], 0
0x18001b631  mov     rbx, rcx
0x18001b634  mov     qword ptr [rax+18h], 0
0x18001b63c  mov     qword ptr [rax+8], 0
0x18001b644  jz      loc_18001B6FD
0x18001b64a  lea     rdx, asc_18002B6C8; "/"
0x18001b651  call    cs:__imp_lstrcmpA
0x18001b657  test    eax, eax
0x18001b659  jz      loc_18001B6FD
0x18001b65f  lea     rax, [rsp+48h+pszStart]
0x18001b664  mov     r8, rdi; struct _ITEMIDLIST **
0x18001b667  mov     [rsp+48h+var_18], rax; char **
0x18001b66c  mov     rcx, rbx; pszStart
0x18001b66f  lea     rax, [rsp+48h+pidl1]
0x18001b674  mov     [rsp+48h+var_20], rax; struct _ITEMIDLIST **
0x18001b679  call    ?CreateFtpPidlFromFtpWirePathHelper@@YAJPEBDPEAKPEAPEFAU_ITEMIDLIST@@HH2PEAPEAD@Z; CreateFtpPidlFromFtpWirePathHelper(char const *,ulong *,_ITEMIDLIST * *,int,int,_ITEMIDLIST * *,char * *)
0x18001b67e  mov     ebx, eax
0x18001b680  test    eax, eax
0x18001b682  js      short loc_18001B6F9
0x18001b684  mov     rcx, [rsp+48h+pszStart]; char *
0x18001b689  test    rcx, rcx
0x18001b68c  jz      short loc_18001B6F9
0x18001b68e  mov     r9d, 1; int
0x18001b694  mov     [rsp+48h+pidl2], 0
0x18001b69d  lea     r8, [rsp+48h+pidl2]; struct _ITEMIDLIST **
0x18001b6a2  mov     [rsp+48h+var_28], r9d; int
0x18001b6a7  xor     edx, edx; unsigned int *
0x18001b6a9  call    ?CreateFtpPidlFromFtpWirePath@@YAJPEBDPEAKPEAPEFAU_ITEMIDLIST@@HH@Z; CreateFtpPidlFromFtpWirePath(char const *,ulong *,_ITEMIDLIST * *,int,int)
0x18001b6ae  mov     ebx, eax
0x18001b6b0  test    eax, eax
0x18001b6b2  js      short loc_18001B6E2
0x18001b6b4  mov     rdx, [rsp+48h+pidl2]; pidl2
0x18001b6b9  mov     rcx, [rsp+48h+pidl1]; pidl1
0x18001b6be  call    cs:__imp_ILCombine
0x18001b6c4  mov     rcx, [rsp+48h+pidl2]; pidl
0x18001b6c9  mov     rbx, rax
0x18001b6cc  mov     [rdi], rax
0x18001b6cf  call    cs:__imp_ILFree
0x18001b6d5  neg     rbx
0x18001b6d8  sbb     ebx, ebx
0x18001b6da  not     ebx
0x18001b6dc  and     ebx, 8007000Eh
0x18001b6e2  mov     rcx, [rsp+48h+pidl1]; pidl
0x18001b6e7  call    cs:__imp_ILFree
0x18001b6ed  xor     edx, edx
0x18001b6ef  lea     rcx, [rsp+48h+pszStart]
0x18001b6f4  call    Str_SetPtrA
0x18001b6f9  mov     eax, ebx
0x18001b6fb  jmp     short loc_18001B6FF
0x18001b6fd  xor     eax, eax
0x18001b6ff  mov     rbx, [rsp+48h+arg_18]
0x18001b704  add     rsp, 40h
0x18001b708  pop     rdi
0x18001b709  retn
```
