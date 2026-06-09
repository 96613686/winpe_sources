# IE_PathCreateFromUrlW(ushort const *,ushort *,ulong *,ulong)

- ea: `0x180023ccc`
- end: `0x180023d91`
- name: `?IE_PathCreateFromUrlW@@YAJPEBGPEAGPEAKK@Z`
- size: `197`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027178`
- `0x180028940`

## callees

- `0x180023ccc`
- `0x180025200`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023d89`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023d89`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023d5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023d5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023d31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023d31`

## string_xrefs

- `0x180023d58`: `PathCreateFromUrlW`
- `0x180023d21`: `API-MS-WIN-CORE-URL-L1-1-0.DLL`
- `0x180023d1a`: `API-MS-WIN-DOWNLEVEL-SHLWAPI-L1-1-0.DLL`

## pseudocode

```c
__int64 __fastcall IE_PathCreateFromUrlW(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int a4)
{
  FARPROC ProcAddress; // rax
  HMODULE v10; // rcx
  bool v11; // al
  const WCHAR *v12; // rcx
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18029A838;
  if ( qword_18029A838 )
    return ((__int64 (__fastcall *)(const unsigned __int16 *, unsigned __int16 *, unsigned int *, _QWORD))ProcAddress)(
             a1,
             a2,
             a3,
             a4);
  v10 = hModule;
  if ( hModule )
    goto LABEL_10;
  v11 = IsOs_Win8OrGreater();
  v12 = L"API-MS-WIN-CORE-URL-L1-1-0.DLL";
  if ( !v11 )
    v12 = L"API-MS-WIN-DOWNLEVEL-SHLWAPI-L1-1-0.DLL";
  Library = LoadLibraryExW(v12, 0, 0);
  if ( Library )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hModule, (signed __int64)Library, 0) )
      FreeLibrary(Library);
  }
  v10 = hModule;
  if ( hModule )
  {
LABEL_10:
    ProcAddress = GetProcAddress(v10, "PathCreateFromUrlW");
    qword_18029A838 = (__int64)ProcAddress;
    if ( ProcAddress )
      return ((__int64 (__fastcall *)(const unsigned __int16 *, unsigned __int16 *, unsigned int *, _QWORD))ProcAddress)(
               a1,
               a2,
               a3,
               a4);
  }
  else
  {
    qword_18029A838 = 0;
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180023ccc  push    rbx
0x180023cce  push    rbp
0x180023ccf  push    rsi
0x180023cd0  push    rdi
0x180023cd1  sub     rsp, 38h
0x180023cd5  mov     rax, cs:qword_18029A838
0x180023cdc  mov     ebx, r9d
0x180023cdf  mov     rdi, r8
0x180023ce2  mov     rsi, rdx
0x180023ce5  mov     rbp, rcx
0x180023ce8  test    rax, rax
0x180023ceb  jz      short loc_180023D07
0x180023ced  mov     r9d, ebx
0x180023cf0  mov     r8, rdi
0x180023cf3  mov     rdx, rsi
0x180023cf6  mov     rcx, rbp
0x180023cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cfe  add     rsp, 38h
0x180023d02  pop     rdi
0x180023d03  pop     rsi
0x180023d04  pop     rbp
0x180023d05  pop     rbx
0x180023d06  retn
0x180023d07  mov     rcx, cs:hModule
0x180023d0e  test    rcx, rcx
0x180023d11  jnz     short loc_180023D58
0x180023d13  call    ?IsOs_Win8OrGreater@@YA_NXZ; IsOs_Win8OrGreater(void)
0x180023d18  test    al, al
0x180023d1a  lea     rdx, LibFileName; "API-MS-WIN-DOWNLEVEL-SHLWAPI-L1-1-0.DLL"
0x180023d21  lea     rcx, aApiMsWinCoreUr; "API-MS-WIN-CORE-URL-L1-1-0.DLL"
0x180023d28  cmovz   rcx, rdx; lpLibFileName
0x180023d2c  xor     r8d, r8d; dwFlags
0x180023d2f  xor     edx, edx; hFile
0x180023d31  call    cs:__imp_LoadLibraryExW
0x180023d37  mov     rcx, rax; hLibModule
0x180023d3a  test    rax, rax
0x180023d3d  jz      short loc_180023D4C
0x180023d3f  xor     eax, eax
0x180023d41  lock cmpxchg cs:hModule, rcx
0x180023d4a  jnz     short loc_180023D89
0x180023d4c  mov     rcx, cs:hModule; hModule
0x180023d53  test    rcx, rcx
0x180023d56  jz      short loc_180023D7C
0x180023d58  lea     rdx, ProcName; "PathCreateFromUrlW"
0x180023d5f  call    cs:__imp_GetProcAddress
0x180023d65  mov     cs:qword_18029A838, rax
0x180023d6c  test    rax, rax
0x180023d6f  jnz     loc_180023CED
0x180023d75  mov     eax, 80004001h
0x180023d7a  jmp     short loc_180023CFE
0x180023d7c  mov     cs:qword_18029A838, 0
0x180023d87  jmp     short loc_180023D75
0x180023d89  call    cs:__imp_FreeLibrary
0x180023d8f  jmp     short loc_180023D4C
```
