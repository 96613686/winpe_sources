# SetSymbolSearchPath(ProcessInfo *,int)

- ea: `0x18009d40c`
- end: `0x18009d5a5`
- name: `?SetSymbolSearchPath@@YAXPEAVProcessInfo@@H@Z`
- size: `409`
- prototype: `void __fastcall(struct ProcessInfo *, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800e1080`
- `0x180285fd8`
- `0x18039cb60`
- `0x1803a69d0`
- `0x1803a6eb0`

## callees

- `0x1800727b8`
- `0x18009d40c`
- `0x18009d5ac`
- `0x1800c12b8`
- `0x1802e2974`

## import_xrefs

- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x18009d42f`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x18009d445`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x18009d45b`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x18009d42f`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x18009d445`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x18009d45b`
- `dbghelp!SymGetOptions` at `0x18009d506`
- `dbghelp!SymGetOptions` at `0x18009d506`

## string_xrefs

- `0x18009d428`: `_NT_EXECUTABLE_IMAGE_PATH`
- `0x18009d480`: `Set symbol search path`
- `0x18009d451`: `_NT_ALT_SYMBOL_PATH`
- `0x18009d43b`: `_NT_SYMBOL_PATH`
- `0x18009d541`: `Symbol search path is: `
- `0x18009d58b`: `Executable search path is: %s\n`
- `0x18009d573`: `****************************************************************************\n* Symbol loading may be unreliable without a symbol search path.           *\n* Use .symfix to have the debugger choose a symbol path.                   *\n* After setting your symbol path, use .reload to refresh symbol locations. *\n****************************************************************************\n`

## pseudocode

```c
void __fastcall SetSymbolSearchPath(struct ProcessInfo *a1, int a2)
{
  wchar_t *v3; // rbp
  wchar_t *v4; // rsi
  wchar_t *v5; // rdi
  int v6; // r9d
  const unsigned __int16 *v7; // rcx
  bool v8; // [rsp+28h] [rbp-50h]
  bool v9; // [rsp+38h] [rbp-40h]

  if ( (g_SymOptions & 0x1000) != 0 )
  {
    v5 = 0;
    v4 = 0;
    goto LABEL_5;
  }
  v3 = _wgetenv(L"_NT_EXECUTABLE_IMAGE_PATH");
  v4 = _wgetenv(L"_NT_SYMBOL_PATH");
  v5 = _wgetenv(L"_NT_ALT_SYMBOL_PATH");
  if ( !v3 )
LABEL_5:
    v3 = (wchar_t *)&strIn;
  ChangePath(&g_ExecutableImageSearchPath, v3, 0, 1, 1, 0, L"Set symbol search path", v9);
  if ( v4 )
    ChangeAllSymPaths(v4, 0, 1, 1, 0, v8);
  if ( v5 )
    ChangeAllSymPaths(v5, 0, 1, 1, 0, v8);
  if ( !v4 && !v5 )
  {
    if ( (g_EngOptions & 8) != 0 || g_SymbolSearchPath && *g_SymbolSearchPath || (SymGetOptions() & 0x40000000) != 0 )
    {
      v6 = 1;
      v7 = &strIn;
    }
    else
    {
      v6 = 0;
      v7 = L"srv*";
    }
    ChangeAllSymPaths(v7, 0, 1, v6, 0, v8);
  }
  if ( a2 )
  {
    dprintf(L"Symbol search path is: ");
    if ( *g_SymbolSearchPath )
    {
      dprintf(L"%s\n");
    }
    else
    {
      dprintf(L"*** Invalid ***\n");
      WarnOut(
        L"****************************************************************************\n"
         "* Symbol loading may be unreliable without a symbol search path.           *\n"
         "* Use .symfix to have the debugger choose a symbol path.                   *\n"
         "* After setting your symbol path, use .reload to refresh symbol locations. *\n"
         "****************************************************************************\n");
    }
    if ( g_ExecutableImageSearchPath )
      dprintf(L"Executable search path is: %s\n");
  }
}

```

## disassembly

```asm
0x18009d40c  push    rbx
0x18009d40e  push    rbp
0x18009d40f  push    rsi
0x18009d410  push    rdi
0x18009d411  push    r14
0x18009d413  push    r15
0x18009d415  sub     rsp, 48h
0x18009d419  test    cs:?g_SymOptions@@3KA, 1000h; ulong g_SymOptions
0x18009d423  mov     r14d, edx
0x18009d426  jnz     short loc_18009D473
0x18009d428  lea     rcx, aNtExecutableIm; "_NT_EXECUTABLE_IMAGE_PATH"
0x18009d42f  call    cs:__imp__wgetenv
0x18009d436  nop     dword ptr [rax+rax+00h]
0x18009d43b  lea     rcx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x18009d442  mov     rbp, rax
0x18009d445  call    cs:__imp__wgetenv
0x18009d44c  nop     dword ptr [rax+rax+00h]
0x18009d451  lea     rcx, aNtAltSymbolPat; "_NT_ALT_SYMBOL_PATH"
0x18009d458  mov     rsi, rax
0x18009d45b  call    cs:__imp__wgetenv
0x18009d462  nop     dword ptr [rax+rax+00h]
0x18009d467  xor     ebx, ebx
0x18009d469  mov     rdi, rax
0x18009d46c  test    rbp, rbp
0x18009d46f  jz      short loc_18009D479
0x18009d471  jmp     short loc_18009D480
0x18009d473  xor     ebx, ebx
0x18009d475  mov     edi, ebx
0x18009d477  mov     esi, ebx
0x18009d479  lea     rbp, strIn
0x18009d480  lea     rax, aSetSymbolSearc; "Set symbol search path"
0x18009d487  mov     r15d, 1
0x18009d48d  mov     [rsp+78h+var_48], rax; unsigned __int16 *
0x18009d492  lea     rcx, ?g_ExecutableImageSearchPath@@3PEAGEA; unsigned __int16 **
0x18009d499  mov     dword ptr [rsp+78h+var_50], ebx; bool
0x18009d49d  mov     r9d, r15d; int
0x18009d4a0  xor     r8d, r8d; unsigned __int16 *
0x18009d4a3  mov     [rsp+78h+var_58], r15d; int
0x18009d4a8  mov     rdx, rbp; unsigned __int16 *
0x18009d4ab  call    ?ChangePath@@YAJPEAPEAGPEBG1HHK1_N@Z; ChangePath(ushort * *,ushort const *,ushort const *,int,int,ulong,ushort const *,bool)
0x18009d4b0  test    rsi, rsi
0x18009d4b3  jz      short loc_18009D4C9
0x18009d4b5  mov     r9d, r15d; int
0x18009d4b8  mov     [rsp+78h+var_58], ebx; unsigned int
0x18009d4bc  mov     r8d, r15d; int
0x18009d4bf  xor     edx, edx; unsigned __int16 *
0x18009d4c1  mov     rcx, rsi; unsigned __int16 *
0x18009d4c4  call    ?ChangeAllSymPaths@@YAJPEBG0HHK_N@Z; ChangeAllSymPaths(ushort const *,ushort const *,int,int,ulong,bool)
0x18009d4c9  test    rdi, rdi
0x18009d4cc  jz      short loc_18009D4E2
0x18009d4ce  mov     r9d, r15d; int
0x18009d4d1  mov     [rsp+78h+var_58], ebx; unsigned int
0x18009d4d5  mov     r8d, r15d; int
0x18009d4d8  xor     edx, edx; unsigned __int16 *
0x18009d4da  mov     rcx, rdi; unsigned __int16 *
0x18009d4dd  call    ?ChangeAllSymPaths@@YAJPEBG0HHK_N@Z; ChangeAllSymPaths(ushort const *,ushort const *,int,int,ulong,bool)
0x18009d4e2  test    rsi, rsi
0x18009d4e5  jnz     short loc_18009D53C
0x18009d4e7  test    rdi, rdi
0x18009d4ea  jnz     short loc_18009D53C
0x18009d4ec  test    byte ptr cs:?g_EngOptions@@3KA, 8; ulong g_EngOptions
0x18009d4f3  jnz     short loc_18009D524
0x18009d4f5  mov     rax, cs:?g_SymbolSearchPath@@3PEAGEA; ushort * g_SymbolSearchPath
0x18009d4fc  test    rax, rax
0x18009d4ff  jz      short loc_18009D506
0x18009d501  cmp     [rax], bx
0x18009d504  jnz     short loc_18009D524
0x18009d506  call    cs:__imp_SymGetOptions
0x18009d50d  nop     dword ptr [rax+rax+00h]
0x18009d512  bt      eax, 1Eh
0x18009d516  jb      short loc_18009D524
0x18009d518  xor     r9d, r9d
0x18009d51b  lea     rcx, UserSearchPath; "srv*"
0x18009d522  jmp     short loc_18009D52E
0x18009d524  mov     r9d, r15d; int
0x18009d527  lea     rcx, strIn; unsigned __int16 *
0x18009d52e  mov     r8d, r15d; int
0x18009d531  mov     [rsp+78h+var_58], ebx; unsigned int
0x18009d535  xor     edx, edx; unsigned __int16 *
0x18009d537  call    ?ChangeAllSymPaths@@YAJPEBG0HHK_N@Z; ChangeAllSymPaths(ushort const *,ushort const *,int,int,ulong,bool)
0x18009d53c  test    r14d, r14d
0x18009d53f  jz      short loc_18009D597
0x18009d541  lea     rcx, aSymbolSearchPa; "Symbol search path is: "
0x18009d548  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x18009d54d  mov     rdx, cs:?g_SymbolSearchPath@@3PEAGEA; ushort * g_SymbolSearchPath
0x18009d554  cmp     [rdx], bx
0x18009d557  jz      short loc_18009D567
0x18009d559  lea     rcx, aS_35; "%s\n"
0x18009d560  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x18009d565  jmp     short loc_18009D57F
0x18009d567  lea     rcx, aInvalid_2; "*** Invalid ***\n"
0x18009d56e  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x18009d573  lea     rcx, asc_1806540B0; "***************************************"...
0x18009d57a  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x18009d57f  mov     rdx, cs:?g_ExecutableImageSearchPath@@3PEAGEA; ushort * g_ExecutableImageSearchPath
0x18009d586  test    rdx, rdx
0x18009d589  jz      short loc_18009D597
0x18009d58b  lea     rcx, aExecutableSear; "Executable search path is: %s\n"
0x18009d592  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x18009d597  add     rsp, 48h
0x18009d59b  pop     r15
0x18009d59d  pop     r14
0x18009d59f  pop     rdi
0x18009d5a0  pop     rsi
0x18009d5a1  pop     rbp
0x18009d5a2  pop     rbx
0x18009d5a3  retn
```
