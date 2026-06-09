# PlatformAgnostic::DateTime::TryLoadLibrary

- ea: `0x180495198`
- end: `0x180495239`
- name: `PlatformAgnostic::DateTime::TryLoadLibrary`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1803c62b4`
- `0x180495120`

## callees

- `0x180495198`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1804951b9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1804951ff`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1804951b9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1804951ff`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1804951da`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180495220`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1804951da`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180495220`

## string_xrefs

- `0x1804951f2`: `kernel32.dll`
- `0x1804951ac`: `api-ms-win-core-timezone-l1-1-0.dll`

## pseudocode

```c
__int64 PlatformAgnostic::DateTime::TryLoadLibrary()
{
  HMODULE Library; // rax
  HMODULE v1; // rax

  if ( !qword_180740D90 )
  {
    Library = LoadLibraryExW(L"api-ms-win-core-timezone-l1-1-0.dll", 0, 0x800u);
    if ( Library && _InterlockedCompareExchange64(&qword_180740D90, (signed __int64)Library, 0) )
      FreeLibrary(Library);
    if ( !qword_180740D90 )
    {
      v1 = LoadLibraryExW(L"kernel32.dll", 0, 0x800u);
      if ( v1 )
      {
        if ( _InterlockedCompareExchange64(&qword_180740D90, (signed __int64)v1, 0) )
          FreeLibrary(v1);
      }
    }
  }
  return qword_180740D90;
}

```

## disassembly

```asm
0x180495198  sub     rsp, 28h
0x18049519c  cmp     cs:qword_180740D90, 0
0x1804951a4  jnz     loc_18049522C
0x1804951aa  xor     edx, edx; hFile
0x1804951ac  lea     rcx, aApiMsWinCoreTi_0; "api-ms-win-core-timezone-l1-1-0.dll"
0x1804951b3  mov     r8d, 800h; dwFlags
0x1804951b9  call    cs:__imp_LoadLibraryExW
0x1804951c0  nop     dword ptr [rax+rax+00h]
0x1804951c5  mov     rcx, rax; hLibModule
0x1804951c8  test    rax, rax
0x1804951cb  jz      short loc_1804951E6
0x1804951cd  xor     eax, eax
0x1804951cf  lock cmpxchg cs:qword_180740D90, rcx
0x1804951d8  jz      short loc_1804951E6
0x1804951da  call    cs:__imp_FreeLibrary
0x1804951e1  nop     dword ptr [rax+rax+00h]
0x1804951e6  cmp     cs:qword_180740D90, 0
0x1804951ee  jnz     short loc_18049522C
0x1804951f0  xor     edx, edx; hFile
0x1804951f2  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1804951f9  mov     r8d, 800h; dwFlags
0x1804951ff  call    cs:__imp_LoadLibraryExW
0x180495206  nop     dword ptr [rax+rax+00h]
0x18049520b  mov     rcx, rax; hLibModule
0x18049520e  test    rax, rax
0x180495211  jz      short loc_18049522C
0x180495213  xor     eax, eax
0x180495215  lock cmpxchg cs:qword_180740D90, rcx
0x18049521e  jz      short loc_18049522C
0x180495220  call    cs:__imp_FreeLibrary
0x180495227  nop     dword ptr [rax+rax+00h]
0x18049522c  mov     rax, cs:qword_180740D90
0x180495233  add     rsp, 28h
0x180495237  retn
```
