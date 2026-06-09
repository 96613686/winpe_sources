# _IsPropsysLoadedFromDotLocal(void)

- ea: `0x180021fb4`
- end: `0x180022068`
- name: `?_IsPropsysLoadedFromDotLocal@@YAHXZ`
- size: `180`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180021d88`

## callees

- `0x180021fb4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180021ff7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180021ff7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180022021`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180022021`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180022004`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180022004`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180022011`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180022011`

## pseudocode

```c
__int64 _IsPropsysLoadedFromDotLocal(void)
{
  unsigned int v0; // ecx
  const WCHAR *ExtensionW; // rax
  __int64 v3; // rax

  if ( g_tbIsPropsysLoadedFromDotLocal )
  {
    v0 = 1;
    if ( g_tbIsPropsysLoadedFromDotLocal != 1 )
      return 0;
  }
  else
  {
    if ( !GetModuleFileNameW(g_hinst, &g_szPropsysPathDotLocal, 0x104u)
      || !PathRemoveFileSpecW(&g_szPropsysPathDotLocal)
      || (ExtensionW = PathFindExtensionW(&g_szPropsysPathDotLocal), StrCmpICW(ExtensionW, L".local")) )
    {
      g_tbIsPropsysLoadedFromDotLocal = 2;
      g_szPropsysPathDotLocal = 0;
      return 0;
    }
    v0 = 1;
    v3 = -1;
    g_tbIsPropsysLoadedFromDotLocal = 1;
    do
      ++v3;
    while ( *(&g_szPropsysPathDotLocal + v3) );
    *(&g_szPropsysPathDotLocal + v3) = 92;
    word_1800F17F6 = 0;
  }
  return v0;
}

```

## disassembly

```asm
0x180021fb4  mov     [rsp+arg_0], rbx
0x180021fb9  push    rdi
0x180021fba  sub     rsp, 20h
0x180021fbe  mov     eax, cs:?g_tbIsPropsysLoadedFromDotLocal@@3W4TRIBIT@@A; TRIBIT g_tbIsPropsysLoadedFromDotLocal
0x180021fc4  xor     ebx, ebx
0x180021fc6  test    eax, eax
0x180021fc8  jz      short loc_180021FE0
0x180021fca  lea     ecx, [rbx+1]
0x180021fcd  cmp     eax, ecx
0x180021fcf  jz      short loc_180021FD3
0x180021fd1  mov     ecx, ebx
0x180021fd3  mov     rbx, [rsp+28h+arg_0]
0x180021fd8  mov     eax, ecx
0x180021fda  add     rsp, 20h
0x180021fde  pop     rdi
0x180021fdf  retn
0x180021fe0  mov     rcx, cs:g_hinst; hModule
0x180021fe7  lea     rdi, ?g_szPropsysPathDotLocal@@3PAGA; ushort near * g_szPropsysPathDotLocal
0x180021fee  mov     rdx, rdi; lpFilename
0x180021ff1  mov     r8d, 104h; nSize
0x180021ff7  call    cs:__imp_GetModuleFileNameW
0x180021ffd  test    eax, eax
0x180021fff  jz      short loc_18002202B
0x180022001  mov     rcx, rdi; pszPath
0x180022004  call    cs:__imp_PathRemoveFileSpecW
0x18002200a  test    eax, eax
0x18002200c  jz      short loc_18002202B
0x18002200e  mov     rcx, rdi; pszPath
0x180022011  call    cs:__imp_PathFindExtensionW
0x180022017  mov     rcx, rax; pszStr1
0x18002201a  lea     rdx, aLocal_0; ".local"
0x180022021  call    cs:__imp_StrCmpICW
0x180022027  test    eax, eax
0x180022029  jz      short loc_18002203E
0x18002202b  mov     cs:?g_tbIsPropsysLoadedFromDotLocal@@3W4TRIBIT@@A, 2; TRIBIT g_tbIsPropsysLoadedFromDotLocal
0x180022035  mov     cs:?g_szPropsysPathDotLocal@@3PAGA, bx; ushort near * g_szPropsysPathDotLocal
0x18002203c  jmp     short loc_180021FD1
0x18002203e  mov     ecx, 1
0x180022043  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022047  mov     cs:?g_tbIsPropsysLoadedFromDotLocal@@3W4TRIBIT@@A, ecx; TRIBIT g_tbIsPropsysLoadedFromDotLocal
0x18002204d  inc     rax
0x180022050  cmp     [rdi+rax*2], bx
0x180022054  jnz     short loc_18002204D
0x180022056  mov     word ptr [rdi+rax*2], 5Ch ; '\'
0x18002205c  mov     cs:word_1800F17F6, bx
0x180022063  jmp     loc_180021FD3
```
