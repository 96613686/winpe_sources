# ExpandCanonicalSearchPaths(ushort * *,ushort *,ushort const *,bool)

- ea: `0x1800c0a28`
- end: `0x1800c0df1`
- name: `?ExpandCanonicalSearchPaths@@YAHPEAPEAGPEAGPEBG_N@Z`
- size: `969`
- prototype: `int(unsigned __int16 **, unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009d5ac`

## callees

- `0x180073230`
- `0x1800793cc`
- `0x18008e740`
- `0x18009428c`
- `0x1800986ec`
- `0x1800c0a28`
- `0x1800f0f40`
- `0x1800f2998`
- `0x1802e28f8`
- `0x1802e7dd4`
- `0x1804da4c0`
- `0x1804da880`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c0af5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c0cd6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c0af5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c0cd6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c0d87`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c0da1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c0db0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c0d87`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c0da1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c0db0`
- `api-ms-win-crt-string-l1-1-0!_wcslwr` at `0x1800c0b1e`
- `api-ms-win-crt-string-l1-1-0!_wcslwr` at `0x1800c0b1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c0aad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c0ae1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c0aad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c0ae1`
- `dbghelp!SymGetHomeDirectoryW` at `0x1800c0ba3`
- `dbghelp!SymGetHomeDirectoryW` at `0x1800c0ba3`

## string_xrefs

- `0x1800c0b4d`: `Set your symbol path to a symbol tree on the local machine.\n`
- `0x1800c0b41`: `Network paths are disallowed, symbol server is not available.\n`
- `0x1800c0c1e`: `cache*`
- `0x1800c0d0c`: `cache*`
- `0x1800c0c08`: `cache*%s`
- `0x1800c0c39`: `https://msdl.microsoft.com/download/symbols`

## pseudocode

```c
__int64 __fastcall ExpandCanonicalSearchPaths(unsigned __int16 **a1, unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rbx
  unsigned int v6; // r12d
  const unsigned __int16 *v8; // r14
  size_t v9; // rbx
  __int64 result; // rax
  wchar_t *v11; // rsi
  __int64 v12; // r8
  __int64 v13; // rdx
  unsigned int v14; // r14d
  void *v15; // rax
  void *v16; // rdi
  wchar_t *v17; // rbx
  int v18; // r13d
  int v19; // ebx
  void **v20; // rbx
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v22; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 *v23; // [rsp+38h] [rbp-C8h] BYREF
  void **v24; // [rsp+40h] [rbp-C0h]
  wchar_t Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v26[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR dir[264]; // [rsp+470h] [rbp+370h] BYREF

  v3 = -1;
  v5 = -1;
  v6 = 0;
  do
    ++v5;
  while ( a2[v5] );
  v8 = (const unsigned __int16 *)g_SymFixCachePath;
  v22 = v5;
  v23 = 0;
  if ( a3 )
    v8 = a3;
  v21 = 0;
  if ( a1 == (unsigned __int16 **)&g_SymbolSearchPath )
  {
    v24 = (void **)&g_SymbolSearchPathExpanded;
    GetSystemTimeAsFileTime(&g_PathSetTime);
    v6 = 0;
  }
  else
  {
    if ( a1 != &g_ExecutableImageSearchPath )
      return 1;
    v24 = (void **)&g_ExecutableImageSearchPathExpanded;
    GetSystemTimeAsFileTime(&g_PathSetTime);
  }
  v9 = 2LL * (unsigned int)(v5 + 1);
  result = (__int64)malloc(v9);
  v11 = (wchar_t *)result;
  if ( !result )
    return result;
  memmove((void *)result, a2, v9);
  _wcslwr(v11);
  Buffer[0] = 0;
  v26[0] = 0;
  if ( (g_EngOptions & 8) == 0 )
  {
    if ( !g_Target || !(unsigned int)SplitSrvPath(v11, &v22, &v23, &v21) )
      goto LABEL_29;
    if ( !v8 && !SymGetHomeDirectoryW(1u, dir, 0x105u) )
    {
      if ( (unsigned int)IsInternalPackage() )
        CatNStringW(v26, L"SRV**", v12, 261);
      goto LABEL_29;
    }
    if ( a3 )
    {
      if ( (unsigned int)IsInternalPackage() )
LABEL_23:
        PrintStringW(Buffer, 0x105u, (wchar_t *)L"cache*%s");
    }
    else
    {
      if ( !g_SymFixCachePath )
      {
        PrintStringW(Buffer, 0x105u, (wchar_t *)L"cache*");
        goto LABEL_25;
      }
      if ( (unsigned int)IsInternalPackage() )
        goto LABEL_23;
    }
LABEL_25:
    IsInternalPackage();
    if ( (unsigned int)IsInternalPackage() || !g_SymFixCachePath )
      PrintStringW(v26, 0x105u, (wchar_t *)L"SRV*%s");
    else
      PrintStringW(v26, 0x105u, (wchar_t *)L"SRV*%s*%s");
    goto LABEL_29;
  }
  ErrOut(L"Network paths are disallowed, symbol server is not available.\n");
  ErrOut(L"Set your symbol path to a symbol tree on the local machine.\n");
LABEL_29:
  v13 = -1;
  do
    ++v13;
  while ( Buffer[v13] );
  do
    ++v3;
  while ( v26[v3] );
  v14 = v13 + v3 + v21 + v22 + 6;
  v15 = malloc(2LL * v14);
  v16 = v15;
  if ( v15 )
  {
    memset(v15, 0, 2LL * v14);
    CopyNStringW(v16);
    v17 = wcsstr((const wchar_t *)v16, L"cache*");
    v18 = CopyNStringW(v16);
    if ( !v17 || a3 )
      v18 &= CatSrvPath((unsigned __int16 *)v16, Buffer, v14);
    v19 = v18 & CatSrvPath((unsigned __int16 *)v16, v26, v14);
    if ( ((unsigned int)CatSrvPath((unsigned __int16 *)v16, v23, v14) & v19) != 0 )
    {
      v20 = v24;
      if ( *v24 )
        free(*v24);
      *v20 = v16;
      v6 = 1;
    }
    else
    {
      free(v16);
    }
  }
  free(v11);
  return v6;
}

```

## disassembly

```asm
0x1800c0a28  mov     [rsp-8+arg_0], rbx
0x1800c0a2d  push    rbp
0x1800c0a2e  push    rsi
0x1800c0a2f  push    rdi
0x1800c0a30  push    r12
0x1800c0a32  push    r13
0x1800c0a34  push    r14
0x1800c0a36  push    r15
0x1800c0a38  lea     rbp, [rsp-590h]
0x1800c0a40  sub     rsp, 690h
0x1800c0a47  mov     rax, cs:__security_cookie
0x1800c0a4e  xor     rax, rsp
0x1800c0a51  mov     [rbp+5C0h+var_40], rax
0x1800c0a58  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c0a5c  mov     r15, r8
0x1800c0a5f  mov     rbx, rdi
0x1800c0a62  xor     r12d, r12d
0x1800c0a65  mov     r13, rdx
0x1800c0a68  inc     rbx
0x1800c0a6b  cmp     [rdx+rbx*2], r12w
0x1800c0a70  jnz     short loc_1800C0A68
0x1800c0a72  mov     r14, cs:?g_SymFixCachePath@@3PEAGEA; ushort * g_SymFixCachePath
0x1800c0a79  lea     rax, ?g_SymbolSearchPath@@3PEAGEA; ushort * g_SymbolSearchPath
0x1800c0a80  test    r15, r15
0x1800c0a83  mov     [rsp+6C0h+var_68C], ebx
0x1800c0a87  mov     [rsp+6C0h+var_688], r12
0x1800c0a8c  cmovnz  r14, r15
0x1800c0a90  mov     [rsp+6C0h+var_690], r12d
0x1800c0a95  cmp     rcx, rax
0x1800c0a98  jnz     short loc_1800C0ABE
0x1800c0a9a  lea     r12, ?g_SymbolSearchPathExpanded@@3PEAGEA; ushort * g_SymbolSearchPathExpanded
0x1800c0aa1  lea     rcx, ?g_PathSetTime@@3_KA; lpSystemTimeAsFileTime
0x1800c0aa8  mov     [rsp+6C0h+var_680], r12
0x1800c0aad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800c0ab4  nop     dword ptr [rax+rax+00h]
0x1800c0ab9  xor     r12d, r12d
0x1800c0abc  jmp     short loc_1800C0AED
0x1800c0abe  lea     rax, ?g_ExecutableImageSearchPath@@3PEAGEA; ushort * g_ExecutableImageSearchPath
0x1800c0ac5  cmp     rcx, rax
0x1800c0ac8  jnz     loc_1800C0DC1
0x1800c0ace  lea     rax, ?g_ExecutableImageSearchPathExpanded@@3PEAGEA; ushort * g_ExecutableImageSearchPathExpanded
0x1800c0ad5  lea     rcx, ?g_PathSetTime@@3_KA; lpSystemTimeAsFileTime
0x1800c0adc  mov     [rsp+6C0h+var_680], rax
0x1800c0ae1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800c0ae8  nop     dword ptr [rax+rax+00h]
0x1800c0aed  inc     ebx
0x1800c0aef  add     rbx, rbx
0x1800c0af2  mov     rcx, rbx; Size
0x1800c0af5  call    cs:__imp_malloc
0x1800c0afc  nop     dword ptr [rax+rax+00h]
0x1800c0b01  mov     rsi, rax
0x1800c0b04  test    rax, rax
0x1800c0b07  jz      loc_1800C0DC6
0x1800c0b0d  mov     r8, rbx; Size
0x1800c0b10  mov     rdx, r13; Src
0x1800c0b13  mov     rcx, rsi; void *
0x1800c0b16  call    memmove
0x1800c0b1b  mov     rcx, rsi; String
0x1800c0b1e  call    cs:__imp__wcslwr
0x1800c0b25  nop     dword ptr [rax+rax+00h]
0x1800c0b2a  test    byte ptr cs:?g_EngOptions@@3KA, 8; ulong g_EngOptions
0x1800c0b31  mov     [rsp+6C0h+Buffer], r12w
0x1800c0b37  mov     [rbp+5C0h+var_460], r12w
0x1800c0b3f  jz      short loc_1800C0B5E
0x1800c0b41  lea     rcx, aNetworkPathsAr; "Network paths are disallowed, symbol se"...
0x1800c0b48  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800c0b4d  lea     rcx, aSetYourSymbolP; "Set your symbol path to a symbol tree o"...
0x1800c0b54  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800c0b59  jmp     loc_1800C0C96
0x1800c0b5e  cmp     cs:?g_Target@@3PEAVTargetInfo@@EA, r12; TargetInfo * g_Target
0x1800c0b65  jz      loc_1800C0C96
0x1800c0b6b  lea     r9, [rsp+6C0h+var_690]; unsigned int *
0x1800c0b70  mov     rcx, rsi; Str
0x1800c0b73  lea     r8, [rsp+6C0h+var_688]; unsigned __int16 **
0x1800c0b78  lea     rdx, [rsp+6C0h+var_68C]; unsigned int *
0x1800c0b7d  call    ?SplitSrvPath@@YAHPEAGPEAKPEAPEAG1@Z; SplitSrvPath(ushort *,ulong *,ushort * *,ulong *)
0x1800c0b82  test    eax, eax
0x1800c0b84  jz      loc_1800C0C96
0x1800c0b8a  mov     r13d, 105h
0x1800c0b90  test    r14, r14
0x1800c0b93  jnz     short loc_1800C0BDC
0x1800c0b95  mov     r8d, r13d; size
0x1800c0b98  lea     rdx, [rbp+5C0h+dir]; dir
0x1800c0b9f  lea     ecx, [r14+1]; type
0x1800c0ba3  call    cs:__imp_SymGetHomeDirectoryW
0x1800c0baa  nop     dword ptr [rax+rax+00h]
0x1800c0baf  test    rax, rax
0x1800c0bb2  jnz     short loc_1800C0BDC
0x1800c0bb4  call    ?IsInternalPackage@@YAHXZ; IsInternalPackage(void)
0x1800c0bb9  test    eax, eax
0x1800c0bbb  jz      loc_1800C0C96
0x1800c0bc1  mov     r9d, r13d
0x1800c0bc4  lea     rdx, aSrv_0; "SRV**"
0x1800c0bcb  lea     rcx, [rbp+5C0h+var_460]
0x1800c0bd2  call    CatNStringW
0x1800c0bd7  jmp     loc_1800C0C96
0x1800c0bdc  test    r15, r15
0x1800c0bdf  jz      short loc_1800C0BEF
0x1800c0be1  call    ?IsInternalPackage@@YAHXZ; IsInternalPackage(void)
0x1800c0be6  test    eax, eax
0x1800c0be8  jz      short loc_1800C0C32
0x1800c0bea  mov     r9, r15
0x1800c0bed  jmp     short loc_1800C0C08
0x1800c0bef  cmp     cs:?g_SymFixCachePath@@3PEAGEA, r12; ushort * g_SymFixCachePath
0x1800c0bf6  jz      short loc_1800C0C1E
0x1800c0bf8  call    ?IsInternalPackage@@YAHXZ; IsInternalPackage(void)
0x1800c0bfd  test    eax, eax
0x1800c0bff  jz      short loc_1800C0C32
0x1800c0c01  mov     r9, cs:?g_SymFixCachePath@@3PEAGEA; ushort * g_SymFixCachePath
0x1800c0c08  lea     r8, aCacheS; "cache*%s"
0x1800c0c0f  mov     edx, r13d; BufferCount
0x1800c0c12  lea     rcx, [rsp+6C0h+Buffer]; Buffer
0x1800c0c17  call    PrintStringW
0x1800c0c1c  jmp     short loc_1800C0C32
0x1800c0c1e  lea     r8, aCache_0; "cache*"
0x1800c0c25  mov     edx, r13d; BufferCount
0x1800c0c28  lea     rcx, [rsp+6C0h+Buffer]; Buffer
0x1800c0c2d  call    PrintStringW
0x1800c0c32  call    ?IsInternalPackage@@YAHXZ; IsInternalPackage(void)
0x1800c0c37  test    eax, eax
0x1800c0c39  lea     rcx, aHttpsMsdlMicro; "https://msdl.microsoft.com/download/sym"...
0x1800c0c40  lea     rbx, aHttpsSymwebAzu; "https://symweb.azurefd.net"
0x1800c0c47  cmovz   rbx, rcx
0x1800c0c4b  call    ?IsInternalPackage@@YAHXZ; IsInternalPackage(void)
0x1800c0c50  test    eax, eax
0x1800c0c52  jnz     short loc_1800C0C7D
0x1800c0c54  mov     r9, cs:?g_SymFixCachePath@@3PEAGEA; ushort * g_SymFixCachePath
0x1800c0c5b  test    r9, r9
0x1800c0c5e  jz      short loc_1800C0C7D
0x1800c0c60  lea     r8, aSrvSS; "SRV*%s*%s"
0x1800c0c67  mov     [rsp+6C0h+var_6A0], rbx
0x1800c0c6c  mov     edx, r13d; BufferCount
0x1800c0c6f  lea     rcx, [rbp+5C0h+var_460]; Buffer
0x1800c0c76  call    PrintStringW
0x1800c0c7b  jmp     short loc_1800C0C96
0x1800c0c7d  mov     r9, rbx
0x1800c0c80  lea     r8, aSrvS; "SRV*%s"
0x1800c0c87  mov     edx, r13d; BufferCount
0x1800c0c8a  lea     rcx, [rbp+5C0h+var_460]; Buffer
0x1800c0c91  call    PrintStringW
0x1800c0c96  lea     rax, [rsp+6C0h+Buffer]
0x1800c0c9b  mov     rdx, rdi
0x1800c0c9e  inc     rdx
0x1800c0ca1  cmp     [rax+rdx*2], r12w
0x1800c0ca6  jnz     short loc_1800C0C9E
0x1800c0ca8  lea     rax, [rbp+5C0h+var_460]
0x1800c0caf  inc     rdi
0x1800c0cb2  cmp     [rax+rdi*2], r12w
0x1800c0cb7  jnz     short loc_1800C0CAF
0x1800c0cb9  mov     eax, [rsp+6C0h+var_690]
0x1800c0cbd  mov     r13d, [rsp+6C0h+var_68C]
0x1800c0cc2  add     eax, edi
0x1800c0cc4  add     eax, edx
0x1800c0cc6  lea     r14d, [r13+6]
0x1800c0cca  add     r14d, eax
0x1800c0ccd  mov     ebx, r14d
0x1800c0cd0  add     rbx, rbx
0x1800c0cd3  mov     rcx, rbx; Size
0x1800c0cd6  call    cs:__imp_malloc
0x1800c0cdd  nop     dword ptr [rax+rax+00h]
0x1800c0ce2  mov     rdi, rax
0x1800c0ce5  test    rax, rax
0x1800c0ce8  jz      loc_1800C0DAD
0x1800c0cee  mov     r8, rbx; Size
0x1800c0cf1  xor     edx, edx; Val
0x1800c0cf3  mov     rcx, rax; void *
0x1800c0cf6  call    memset
0x1800c0cfb  mov     r9d, r14d
0x1800c0cfe  mov     r8d, r13d
0x1800c0d01  mov     rdx, rsi
0x1800c0d04  mov     rcx, rdi; void *
0x1800c0d07  call    CopyNStringW
0x1800c0d0c  lea     rdx, aCache_0; "cache*"
0x1800c0d13  mov     rcx, rdi; Str
0x1800c0d16  call    wcsstr
0x1800c0d1b  mov     r9d, r14d
0x1800c0d1e  mov     r8d, r13d
0x1800c0d21  mov     rdx, rsi
0x1800c0d24  mov     rcx, rdi; void *
0x1800c0d27  mov     rbx, rax
0x1800c0d2a  call    CopyNStringW
0x1800c0d2f  mov     r13d, eax
0x1800c0d32  test    rbx, rbx
0x1800c0d35  jz      short loc_1800C0D3C
0x1800c0d37  test    r15, r15
0x1800c0d3a  jz      short loc_1800C0D4F
0x1800c0d3c  mov     r8d, r14d; unsigned int
0x1800c0d3f  lea     rdx, [rsp+6C0h+Buffer]; unsigned __int16 *
0x1800c0d44  mov     rcx, rdi; unsigned __int16 *
0x1800c0d47  call    ?CatSrvPath@@YAHPEAG0K@Z; CatSrvPath(ushort *,ushort *,ulong)
0x1800c0d4c  and     r13d, eax
0x1800c0d4f  mov     r8d, r14d; unsigned int
0x1800c0d52  lea     rdx, [rbp+5C0h+var_460]; unsigned __int16 *
0x1800c0d59  mov     rcx, rdi; unsigned __int16 *
0x1800c0d5c  call    ?CatSrvPath@@YAHPEAG0K@Z; CatSrvPath(ushort *,ushort *,ulong)
0x1800c0d61  mov     rdx, [rsp+6C0h+var_688]; unsigned __int16 *
0x1800c0d66  mov     ebx, eax
0x1800c0d68  mov     r8d, r14d; unsigned int
0x1800c0d6b  mov     rcx, rdi; unsigned __int16 *
0x1800c0d6e  and     ebx, r13d
0x1800c0d71  call    ?CatSrvPath@@YAHPEAG0K@Z; CatSrvPath(ushort *,ushort *,ulong)
0x1800c0d76  test    ebx, eax
0x1800c0d78  jz      short loc_1800C0D9E
0x1800c0d7a  mov     rbx, [rsp+6C0h+var_680]
0x1800c0d7f  mov     rcx, [rbx]; Block
0x1800c0d82  test    rcx, rcx
0x1800c0d85  jz      short loc_1800C0D93
0x1800c0d87  call    cs:__imp_free
0x1800c0d8e  nop     dword ptr [rax+rax+00h]
0x1800c0d93  mov     [rbx], rdi
0x1800c0d96  mov     r12d, 1
0x1800c0d9c  jmp     short loc_1800C0DAD
0x1800c0d9e  mov     rcx, rdi; Block
0x1800c0da1  call    cs:__imp_free
0x1800c0da8  nop     dword ptr [rax+rax+00h]
0x1800c0dad  mov     rcx, rsi; Block
0x1800c0db0  call    cs:__imp_free
0x1800c0db7  nop     dword ptr [rax+rax+00h]
0x1800c0dbc  mov     eax, r12d
0x1800c0dbf  jmp     short loc_1800C0DC6
0x1800c0dc1  mov     eax, 1
0x1800c0dc6  mov     rcx, [rbp+5C0h+var_40]
0x1800c0dcd  xor     rcx, rsp; StackCookie
0x1800c0dd0  call    __security_check_cookie
0x1800c0dd5  mov     rbx, [rsp+6C0h+arg_0]
0x1800c0ddd  add     rsp, 690h
0x1800c0de4  pop     r15
0x1800c0de6  pop     r14
0x1800c0de8  pop     r13
0x1800c0dea  pop     r12
0x1800c0dec  pop     rdi
0x1800c0ded  pop     rsi
0x1800c0dee  pop     rbp
0x1800c0def  retn
```
