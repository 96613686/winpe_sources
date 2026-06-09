# MimeOleGetFileInfoW

- ea: `0x18002dc70`
- end: `0x18002debe`
- name: `MimeOleGetFileInfoW`
- size: `590`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszPath@<rcx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180007ad0`
- `0x18002d940`
- `0x1800437a0`

## callees

- `0x18000910c`
- `0x18002d800`
- `0x18002dc70`
- `0x18002eacc`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszDupW` at `0x18002dd24`
- `MSOERT2!PszDupW` at `0x18002dd58`
- `MSOERT2!PszDupW` at `0x18002de40`
- `MSOERT2!PszDupW` at `0x18002de5a`
- `MSOERT2!PszDupW` at `0x18002de74`
- `MSOERT2!PszDupW` at `0x18002dd24`
- `MSOERT2!PszDupW` at `0x18002dd58`
- `MSOERT2!PszDupW` at `0x18002de40`
- `MSOERT2!PszDupW` at `0x18002de5a`
- `MSOERT2!PszDupW` at `0x18002de74`
- `MSOERT2!PszAllocW` at `0x18002ddc4`
- `MSOERT2!PszAllocW` at `0x18002ddc4`
- `MSOERT2!FIsEmptyW` at `0x18002dd3c`
- `MSOERT2!FIsEmptyW` at `0x18002dd3c`
- `SHLWAPI!PathFindFileNameW` at `0x18002dd07`
- `SHLWAPI!PathFindFileNameW` at `0x18002dd07`
- `SHLWAPI!PathFindExtensionW` at `0x18002dd13`
- `SHLWAPI!PathFindExtensionW` at `0x18002dd13`
- `SHELL32!SHGetFileInfoW` at `0x18002dd8a`
- `SHELL32!SHGetFileInfoW` at `0x18002dd8a`

## pseudocode

```c
__int64 __fastcall MimeOleGetFileInfoW(
        LPCWSTR pszPath,
        __int64 **a2,
        __int64 **a3,
        unsigned __int16 **a4,
        __int64 *a5,
        __int64 *a6)
{
  __int64 *v6; // r15
  LPWSTR FileNameW; // r13
  const WCHAR *ExtensionW; // r12
  __int64 v14; // rax
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // ebx
  unsigned __int16 *v20; // rax
  SHFILEINFOW psfi; // [rsp+40h] [rbp-318h] BYREF

  v6 = a5;
  memset_0(&psfi, 0, sizeof(psfi));
  if ( !pszPath )
    return 2147942487LL;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  FileNameW = PathFindFileNameW(pszPath);
  ExtensionW = PathFindExtensionW(pszPath);
  if ( a5 )
  {
    v14 = PszDupW(FileNameW);
    *a5 = v14;
    v6 = 0;
    if ( !v14 )
      goto LABEL_25;
  }
  if ( (unsigned int)FIsEmptyW(ExtensionW) )
  {
    v15 = -2147467259;
    goto LABEL_26;
  }
  if ( a6 )
  {
    v16 = PszDupW(ExtensionW);
    *a6 = v16;
    if ( !v16 )
    {
LABEL_25:
      v15 = -2147024882;
LABEL_26:
      if ( a2 )
      {
LABEL_33:
        if ( *a2 == v6 )
          *a2 = (__int64 *)PszDupW(L"application");
        goto LABEL_35;
      }
      goto LABEL_35;
    }
  }
  if ( a4 && SHGetFileInfoW(ExtensionW, 0x80u, &psfi, 0x2B8u, 0x610u) )
  {
    v17 = -1;
    v18 = -1;
    do
      ++v18;
    while ( psfi.szDisplayName[v18] != (_WORD)v6 );
    do
      ++v17;
    while ( psfi.szTypeName[v17] != (_WORD)v6 );
    v19 = v17 + v18 + 5;
    v20 = (unsigned __int16 *)PszAllocW(v19);
    *a4 = v20;
    if ( !v20 )
      goto LABEL_25;
    StringCchPrintfW(v20, v19, L"%s, (%s)", psfi.szDisplayName, psfi.szTypeName);
  }
  v15 = (unsigned int)v6;
  if ( a2 )
  {
    if ( a3 && (int)MimeOleGetExtContentTypeW(ExtensionW) >= 0 )
      v15 = MimeOleSplitContentType(0, a2, a3);
    goto LABEL_33;
  }
LABEL_35:
  if ( a3 && *a3 == v6 )
    *a3 = (__int64 *)PszDupW(L"octet-stream");
  if ( a4 )
  {
    if ( *a4 == (unsigned __int16 *)v6 )
      *a4 = (unsigned __int16 *)PszDupW(c_szEmptyW);
  }
  return v15;
}

```

## disassembly

```asm
0x18002dc70  push    rbx
0x18002dc72  push    rbp
0x18002dc73  push    rsi
0x18002dc74  push    rdi
0x18002dc75  push    r12
0x18002dc77  push    r13
0x18002dc79  push    r14
0x18002dc7b  push    r15
0x18002dc7d  sub     rsp, 318h
0x18002dc84  mov     rax, cs:__security_cookie
0x18002dc8b  xor     rax, rsp
0x18002dc8e  mov     [rsp+358h+var_58], rax
0x18002dc96  mov     r15, [rsp+358h+arg_20]
0x18002dc9e  mov     rdi, r8
0x18002dca1  mov     rbx, [rsp+358h+arg_28]
0x18002dca9  mov     rsi, rdx
0x18002dcac  mov     r12, rcx
0x18002dcaf  xor     edx, edx; Val
0x18002dcb1  mov     r8d, 2B8h; Size
0x18002dcb7  lea     rcx, [rsp+358h+psfi]; void *
0x18002dcbc  mov     r14, r9
0x18002dcbf  call    memset_0
0x18002dcc4  xor     eax, eax
0x18002dcc6  mov     [rsp+358h+var_328], rax
0x18002dccb  mov     ebp, eax
0x18002dccd  test    r12, r12
0x18002dcd0  jnz     short loc_18002DCDC
0x18002dcd2  mov     eax, 80070057h
0x18002dcd7  jmp     loc_18002DE9A
0x18002dcdc  test    rsi, rsi
0x18002dcdf  jz      short loc_18002DCE4
0x18002dce1  mov     [rsi], rax
0x18002dce4  test    rdi, rdi
0x18002dce7  jz      short loc_18002DCEC
0x18002dce9  mov     [rdi], rax
0x18002dcec  test    r14, r14
0x18002dcef  jz      short loc_18002DCF4
0x18002dcf1  mov     [r14], rax
0x18002dcf4  test    r15, r15
0x18002dcf7  jz      short loc_18002DCFC
0x18002dcf9  mov     [r15], rax
0x18002dcfc  test    rbx, rbx
0x18002dcff  jz      short loc_18002DD04
0x18002dd01  mov     [rbx], rax
0x18002dd04  mov     rcx, r12; pszPath
0x18002dd07  call    cs:__imp_PathFindFileNameW
0x18002dd0d  mov     rcx, r12; pszPath
0x18002dd10  mov     r13, rax
0x18002dd13  call    cs:__imp_PathFindExtensionW
0x18002dd19  mov     r12, rax
0x18002dd1c  test    r15, r15
0x18002dd1f  jz      short loc_18002DD39
0x18002dd21  mov     rcx, r13
0x18002dd24  call    cs:__imp_PszDupW
0x18002dd2a  mov     [r15], rax
0x18002dd2d  xor     r15d, r15d
0x18002dd30  test    rax, rax
0x18002dd33  jz      loc_18002DDD2
0x18002dd39  mov     rcx, r12
0x18002dd3c  call    cs:__imp_FIsEmptyW
0x18002dd42  test    eax, eax
0x18002dd44  jz      short loc_18002DD50
0x18002dd46  mov     ebx, 80004005h
0x18002dd4b  jmp     loc_18002DDD7
0x18002dd50  test    rbx, rbx
0x18002dd53  jz      short loc_18002DD66
0x18002dd55  mov     rcx, r12
0x18002dd58  call    cs:__imp_PszDupW
0x18002dd5e  mov     [rbx], rax
0x18002dd61  test    rax, rax
0x18002dd64  jz      short loc_18002DDD2
0x18002dd66  test    r14, r14
0x18002dd69  jz      loc_18002DE01
0x18002dd6f  mov     r9d, 2B8h; cbFileInfo
0x18002dd75  mov     [rsp+358h+uFlags], 610h; uFlags
0x18002dd7d  lea     r8, [rsp+358h+psfi]; psfi
0x18002dd82  mov     edx, 80h; dwFileAttributes
0x18002dd87  mov     rcx, r12; pszPath
0x18002dd8a  call    cs:__imp_SHGetFileInfoW
0x18002dd90  test    rax, rax
0x18002dd93  jz      short loc_18002DE01
0x18002dd95  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002dd99  lea     rdx, [rsp+358h+psfi.szDisplayName]
0x18002dd9e  mov     rcx, rax
0x18002dda1  inc     rcx
0x18002dda4  cmp     [rdx+rcx*2], r15w
0x18002dda9  jnz     short loc_18002DDA1
0x18002ddab  lea     rdx, [rsp+358h+psfi.szTypeName]
0x18002ddb3  inc     rax
0x18002ddb6  cmp     [rdx+rax*2], r15w
0x18002ddbb  jnz     short loc_18002DDB3
0x18002ddbd  lea     ebx, [rcx+5]
0x18002ddc0  add     ebx, eax
0x18002ddc2  mov     ecx, ebx
0x18002ddc4  call    cs:__imp_PszAllocW
0x18002ddca  mov     [r14], rax
0x18002ddcd  test    rax, rax
0x18002ddd0  jnz     short loc_18002DDDE
0x18002ddd2  mov     ebx, 8007000Eh
0x18002ddd7  test    rsi, rsi
0x18002ddda  jz      short loc_18002DE49
0x18002dddc  jmp     short loc_18002DE34
0x18002ddde  lea     rcx, [rsp+358h+psfi.szTypeName]
0x18002dde6  mov     edx, ebx; unsigned __int64
0x18002dde8  mov     qword ptr [rsp+358h+uFlags], rcx
0x18002dded  lea     r9, [rsp+358h+psfi.szDisplayName]
0x18002ddf2  mov     rcx, rax; unsigned __int16 *
0x18002ddf5  lea     r8, aSS_11; "%s, (%s)"
0x18002ddfc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002de01  mov     ebx, r15d
0x18002de04  test    rsi, rsi
0x18002de07  jz      short loc_18002DE49
0x18002de09  test    rdi, rdi
0x18002de0c  jz      short loc_18002DE34
0x18002de0e  lea     rdx, [rsp+358h+var_328]
0x18002de13  mov     rcx, r12; lpSubKey
0x18002de16  call    MimeOleGetExtContentTypeW
0x18002de1b  mov     rbp, [rsp+358h+var_328]
0x18002de20  test    eax, eax
0x18002de22  js      short loc_18002DE34
0x18002de24  mov     r8, rdi
0x18002de27  mov     rdx, rsi
0x18002de2a  mov     rcx, rbp
0x18002de2d  call    MimeOleSplitContentType
0x18002de32  mov     ebx, eax
0x18002de34  cmp     [rsi], r15
0x18002de37  jnz     short loc_18002DE49
0x18002de39  lea     rcx, STR_CNT_APPLICATIONW; "application"
0x18002de40  call    cs:__imp_PszDupW
0x18002de46  mov     [rsi], rax
0x18002de49  test    rdi, rdi
0x18002de4c  jz      short loc_18002DE63
0x18002de4e  cmp     [rdi], r15
0x18002de51  jnz     short loc_18002DE63
0x18002de53  lea     rcx, STR_SUB_OCTETSTREAMW; "octet-stream"
0x18002de5a  call    cs:__imp_PszDupW
0x18002de60  mov     [rdi], rax
0x18002de63  test    r14, r14
0x18002de66  jz      short loc_18002DE7D
0x18002de68  cmp     [r14], r15
0x18002de6b  jnz     short loc_18002DE7D
0x18002de6d  lea     rcx, c_szEmptyW
0x18002de74  call    cs:__imp_PszDupW
0x18002de7a  mov     [r14], rax
0x18002de7d  test    rbp, rbp
0x18002de80  jz      short loc_18002DE98
0x18002de82  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18002de89  mov     rdx, rbp
0x18002de8c  mov     rax, [rcx]
0x18002de8f  mov     rax, [rax+28h]
0x18002de93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de98  mov     eax, ebx
0x18002de9a  mov     rcx, [rsp+358h+var_58]
0x18002dea2  xor     rcx, rsp; StackCookie
0x18002dea5  call    __security_check_cookie
0x18002deaa  add     rsp, 318h
0x18002deb1  pop     r15
0x18002deb3  pop     r14
0x18002deb5  pop     r13
0x18002deb7  pop     r12
0x18002deb9  pop     rdi
0x18002deba  pop     rsi
0x18002debb  pop     rbp
0x18002debc  pop     rbx
0x18002debd  retn
```
