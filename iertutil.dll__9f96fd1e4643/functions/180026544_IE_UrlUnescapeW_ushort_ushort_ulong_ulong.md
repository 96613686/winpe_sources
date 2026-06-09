# IE_UrlUnescapeW(ushort *,ushort *,ulong *,ulong)

- ea: `0x180026544`
- end: `0x180026608`
- name: `?IE_UrlUnescapeW@@YAJPEAG0PEAKK@Z`
- size: `196`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800261b4`
- `0x1800263c0`

## callees

- `0x180025200`
- `0x180026544`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026600`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026600`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800265e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800265e0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800265a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800265a9`

## string_xrefs

- `0x180026599`: `API-MS-WIN-CORE-URL-L1-1-0.DLL`
- `0x180026592`: `API-MS-WIN-DOWNLEVEL-SHLWAPI-L1-1-0.DLL`

## pseudocode

```c
__int64 __fastcall IE_UrlUnescapeW(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int *a3, unsigned int a4)
{
  FARPROC ProcAddress; // rax
  HMODULE v10; // rcx
  bool v11; // al
  const WCHAR *v12; // rcx
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18029A858;
  if ( qword_18029A858 )
    return ((__int64 (__fastcall *)(unsigned __int16 *, unsigned __int16 *, unsigned int *, _QWORD))ProcAddress)(
             a1,
             a2,
             a3,
             a4);
  v10 = qword_18029A850;
  if ( qword_18029A850 )
    goto LABEL_11;
  v11 = IsOs_Win8OrGreater();
  v12 = L"API-MS-WIN-CORE-URL-L1-1-0.DLL";
  if ( !v11 )
    v12 = L"API-MS-WIN-DOWNLEVEL-SHLWAPI-L1-1-0.DLL";
  Library = LoadLibraryExW(v12, 0, 0);
  if ( Library )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&qword_18029A850, (signed __int64)Library, 0) )
      FreeLibrary(Library);
  }
  v10 = qword_18029A850;
  if ( qword_18029A850 )
  {
LABEL_11:
    ProcAddress = GetProcAddress(v10, "UrlUnescapeW");
    qword_18029A858 = (__int64)ProcAddress;
    if ( ProcAddress )
      return ((__int64 (__fastcall *)(unsigned __int16 *, unsigned __int16 *, unsigned int *, _QWORD))ProcAddress)(
               a1,
               a2,
               a3,
               a4);
  }
  else
  {
    qword_18029A858 = 0;
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180026544  push    rbx
0x180026546  push    rbp
0x180026547  push    rsi
0x180026548  push    rdi
0x180026549  sub     rsp, 38h
0x18002654d  mov     rax, cs:qword_18029A858
0x180026554  mov     ebx, r9d
0x180026557  mov     rdi, r8
0x18002655a  mov     rsi, rdx
0x18002655d  mov     rbp, rcx
0x180026560  test    rax, rax
0x180026563  jz      short loc_18002657F
0x180026565  mov     r9d, ebx
0x180026568  mov     r8, rdi
0x18002656b  mov     rdx, rsi
0x18002656e  mov     rcx, rbp
0x180026571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026576  add     rsp, 38h
0x18002657a  pop     rdi
0x18002657b  pop     rsi
0x18002657c  pop     rbp
0x18002657d  pop     rbx
0x18002657e  retn
0x18002657f  mov     rcx, cs:qword_18029A850; hModule
0x180026586  test    rcx, rcx
0x180026589  jnz     short loc_1800265D9
0x18002658b  call    ?IsOs_Win8OrGreater@@YA_NXZ; IsOs_Win8OrGreater(void)
0x180026590  test    al, al
0x180026592  lea     rdx, LibFileName; "API-MS-WIN-DOWNLEVEL-SHLWAPI-L1-1-0.DLL"
0x180026599  lea     rcx, aApiMsWinCoreUr; "API-MS-WIN-CORE-URL-L1-1-0.DLL"
0x1800265a0  cmovz   rcx, rdx; lpLibFileName
0x1800265a4  xor     r8d, r8d; dwFlags
0x1800265a7  xor     edx, edx; hFile
0x1800265a9  call    cs:__imp_LoadLibraryExW
0x1800265af  mov     rcx, rax; hLibModule
0x1800265b2  test    rax, rax
0x1800265b5  jz      short loc_1800265C4
0x1800265b7  xor     eax, eax
0x1800265b9  lock cmpxchg cs:qword_18029A850, rcx
0x1800265c2  jnz     short loc_180026600
0x1800265c4  mov     rcx, cs:qword_18029A850
0x1800265cb  test    rcx, rcx
0x1800265ce  jnz     short loc_1800265D9
0x1800265d0  mov     cs:qword_18029A858, rcx
0x1800265d7  jmp     short loc_1800265F6
0x1800265d9  lea     rdx, aUrlunescapew; "UrlUnescapeW"
0x1800265e0  call    cs:__imp_GetProcAddress
0x1800265e6  mov     cs:qword_18029A858, rax
0x1800265ed  test    rax, rax
0x1800265f0  jnz     loc_180026565
0x1800265f6  mov     eax, 80004001h
0x1800265fb  jmp     loc_180026576
0x180026600  call    cs:__imp_FreeLibrary
0x180026606  jmp     short loc_1800265C4
```
