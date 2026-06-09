# _WinSqmGetProc(char const *)

- ea: `0x1800f2218`
- end: `0x1800f2281`
- name: `?_WinSqmGetProc@@YAP6A_JXZPEBD@Z`
- size: `105`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180070bc4`
- `0x1800f2164`

## callees

- `0x1800f2218`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800f225a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800f225a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f226a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800f226a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800f223f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800f223f`

## string_xrefs

- `0x1800f2238`: `Ntdll.dll`

## pseudocode

```c
FARPROC __fastcall _WinSqmGetProc(LPCSTR lpProcName)
{
  __int64 v1; // rbx
  HMODULE LibraryW; // rax

  v1 = 0;
  if ( dword_1801C4480 )
  {
    if ( hModule )
      return GetProcAddress(hModule, lpProcName);
    LibraryW = LoadLibraryW(L"Ntdll.dll");
    if ( LibraryW )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hModule, (signed __int64)LibraryW, 0) )
        FreeLibrary(LibraryW);
      return GetProcAddress(hModule, lpProcName);
    }
  }
  return (FARPROC)v1;
}

```

## disassembly

```asm
0x1800f2218  mov     [rsp+arg_0], rbx
0x1800f221d  push    rdi
0x1800f221e  sub     rsp, 20h
0x1800f2222  xor     ebx, ebx
0x1800f2224  mov     rdi, rcx
0x1800f2227  cmp     cs:dword_1801C4480, ebx
0x1800f222d  jz      short loc_1800F2273
0x1800f222f  cmp     cs:hModule, rbx
0x1800f2236  jnz     short loc_1800F2260
0x1800f2238  lea     rcx, aNtdllDll; "Ntdll.dll"
0x1800f223f  call    cs:__imp_LoadLibraryW
0x1800f2245  mov     rcx, rax; hLibModule
0x1800f2248  test    rax, rax
0x1800f224b  jz      short loc_1800F2273
0x1800f224d  xor     eax, eax
0x1800f224f  lock cmpxchg cs:hModule, rcx
0x1800f2258  jz      short loc_1800F2260
0x1800f225a  call    cs:__imp_FreeLibrary
0x1800f2260  mov     rcx, cs:hModule; hModule
0x1800f2267  mov     rdx, rdi; lpProcName
0x1800f226a  call    cs:__imp_GetProcAddress
0x1800f2270  mov     rbx, rax
0x1800f2273  mov     rax, rbx
0x1800f2276  mov     rbx, [rsp+28h+arg_0]
0x1800f227b  add     rsp, 20h
0x1800f227f  pop     rdi
0x1800f2280  retn
```
