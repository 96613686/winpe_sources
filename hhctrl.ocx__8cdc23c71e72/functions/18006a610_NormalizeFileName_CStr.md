# NormalizeFileName(CStr &)

- ea: `0x18006a610`
- end: `0x18006a754`
- name: `?NormalizeFileName@@YA_NAEAVCStr@@@Z`
- size: `324`
- prototype: `bool __fastcall(struct CStr *this)`
- caller_count: `3`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800519d4`
- `0x180051bb8`
- `0x180068410`

## callees

- `0x180004224`
- `0x1800269d0`
- `0x180042da8`
- `0x180051e98`
- `0x180066cc0`
- `0x180068760`
- `0x180068790`
- `0x18006a610`
- `0x18006a7ac`
- `0x180075c90`

## import_xrefs

- `msvcrt!free` at `0x18006a6ad`
- `msvcrt!free` at `0x18006a6ad`
- `SHLWAPI!PathCanonicalizeA` at `0x18006a683`
- `SHLWAPI!PathCanonicalizeA` at `0x18006a683`
- `SHLWAPI!StrChrA` at `0x18006a65a`
- `SHLWAPI!StrChrA` at `0x18006a670`
- `SHLWAPI!StrChrA` at `0x18006a65a`
- `SHLWAPI!StrChrA` at `0x18006a670`
- `SHLWAPI!StrStrA` at `0x18006a71f`
- `SHLWAPI!StrStrA` at `0x18006a71f`

## pseudocode

```c
char __fastcall NormalizeFileName(void **this)
{
  unsigned __int64 v2; // rax
  const CHAR *v3; // rcx
  CHAR *i; // rax
  char *v5; // rdi
  HWND v6; // rcx
  struct CExCollection *CurrentCollection; // rax
  PSTR v8; // rax
  CHAR pszBuf[272]; // [rsp+20h] [rbp-128h] BYREF

  v2 = -1;
  v3 = (const CHAR *)*this;
  do
    ++v2;
  while ( v3[v2] );
  if ( v2 >= 0x104 )
    return 0;
  for ( i = StrChrA(v3, 0x2Fu); i; i = StrChrA(i, 0x2Fu) )
    *i = 92;
  if ( PathCanonicalizeA(pszBuf, (LPCSTR)*this) )
  {
    v5 = lcStrDup(pszBuf);
    if ( !v5 )
      OOM();
    if ( *this )
      free(*this);
    *this = v5;
  }
  if ( (unsigned int)IsCollectionFile((const char *)*this) )
  {
    GetCompiledName((PCSTR)*this, (struct CStr *)this);
    if ( !(unsigned int)FindThisFile(0, (const char *)*this, (struct CStr *)this, 0) )
      return 0;
    CurrentCollection = GetCurrentCollection(v6, (const char *)*this);
    if ( !CurrentCollection || !*((_QWORD *)CurrentCollection + 1) )
      return 0;
    CStr::operator=(this);
  }
  if ( !(unsigned int)IsCompiledHtmlFile((PCSTR)*this, (struct CStr *)this) )
    return 0;
  v8 = StrStrA((PCSTR)*this, "::");
  if ( v8 )
    *v8 = 0;
  return 1;
}

```

## disassembly

```asm
0x18006a610  push    rbx
0x18006a612  sub     rsp, 140h
0x18006a619  mov     rax, cs:__security_cookie
0x18006a620  xor     rax, rsp
0x18006a623  mov     [rsp+148h+var_18], rax
0x18006a62b  mov     rbx, rcx
0x18006a62e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18006a635  mov     rcx, [rcx]; pszStart
0x18006a638  inc     rax
0x18006a63b  cmp     byte ptr [rcx+rax], 0
0x18006a63f  jnz     short loc_18006A638
0x18006a641  mov     [rsp+148h+arg_8], rdi
0x18006a649  cmp     rax, 104h
0x18006a64f  jnb     loc_18006A731
0x18006a655  mov     edx, 2Fh ; '/'; wMatch
0x18006a65a  call    cs:__imp_StrChrA
0x18006a660  test    rax, rax
0x18006a663  jz      short loc_18006A67B
0x18006a665  mov     edx, 2Fh ; '/'; wMatch
0x18006a66a  mov     byte ptr [rax], 5Ch ; '\'
0x18006a66d  mov     rcx, rax; pszStart
0x18006a670  call    cs:__imp_StrChrA
0x18006a676  test    rax, rax
0x18006a679  jnz     short loc_18006A665
0x18006a67b  mov     rdx, [rbx]; pszPath
0x18006a67e  lea     rcx, [rsp+148h+pszBuf]; pszBuf
0x18006a683  call    cs:__imp_PathCanonicalizeA
0x18006a689  test    eax, eax
0x18006a68b  jz      short loc_18006A6B6
0x18006a68d  lea     rcx, [rsp+148h+pszBuf]; char *
0x18006a692  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x18006a697  mov     rdi, rax
0x18006a69a  test    rax, rax
0x18006a69d  jnz     short loc_18006A6A5
0x18006a69f  call    ?OOM@@YAXXZ; OOM(void)
0x18006a6a5  mov     rcx, [rbx]; Block
0x18006a6a8  test    rcx, rcx
0x18006a6ab  jz      short loc_18006A6B3
0x18006a6ad  call    cs:__imp_free
0x18006a6b3  mov     [rbx], rdi
0x18006a6b6  mov     rcx, [rbx]; char *
0x18006a6b9  call    ?IsCollectionFile@@YAHPEBD@Z; IsCollectionFile(char const *)
0x18006a6be  test    eax, eax
0x18006a6c0  jz      short loc_18006A706
0x18006a6c2  mov     rcx, [rbx]; pszFirst
0x18006a6c5  mov     rdx, rbx; struct CStr *
0x18006a6c8  call    ?GetCompiledName@@YAPEBDPEBDPEAVCStr@@@Z; GetCompiledName(char const *,CStr *)
0x18006a6cd  mov     rdx, [rbx]; char *
0x18006a6d0  xor     r9d, r9d; int
0x18006a6d3  mov     r8, rbx; struct CStr *
0x18006a6d6  xor     ecx, ecx; HWND
0x18006a6d8  call    ?FindThisFile@@YAHPEAUHWND__@@PEBDPEAVCStr@@H@Z; FindThisFile(HWND__ *,char const *,CStr *,int)
0x18006a6dd  test    eax, eax
0x18006a6df  jz      short loc_18006A731
0x18006a6e1  mov     rdx, [rbx]; char *
0x18006a6e4  call    ?GetCurrentCollection@@YAPEAVCExCollection@@PEAUHWND__@@PEBD@Z; GetCurrentCollection(HWND__ *,char const *)
0x18006a6e9  test    rax, rax
0x18006a6ec  jz      short loc_18006A731
0x18006a6ee  mov     rdx, [rax+8]
0x18006a6f2  test    rdx, rdx
0x18006a6f5  jz      short loc_18006A731
0x18006a6f7  mov     rdx, [rdx+88h]
0x18006a6fe  mov     rcx, rbx
0x18006a701  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18006a706  mov     rcx, [rbx]; pszStart
0x18006a709  mov     rdx, rbx; this
0x18006a70c  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x18006a711  test    eax, eax
0x18006a713  jz      short loc_18006A731
0x18006a715  mov     rcx, [rbx]; pszFirst
0x18006a718  lea     rdx, ?txtDoubleColonSep@@3QBDB; "::"
0x18006a71f  call    cs:__imp_StrStrA
0x18006a725  test    rax, rax
0x18006a728  jz      short loc_18006A72D
0x18006a72a  mov     byte ptr [rax], 0
0x18006a72d  mov     al, 1
0x18006a72f  jmp     short loc_18006A733
0x18006a731  xor     al, al
0x18006a733  mov     rdi, [rsp+148h+arg_8]
0x18006a73b  mov     rcx, [rsp+148h+var_18]
0x18006a743  xor     rcx, rsp; StackCookie
0x18006a746  call    __security_check_cookie
0x18006a74b  add     rsp, 140h
0x18006a752  pop     rbx
0x18006a753  retn
```
