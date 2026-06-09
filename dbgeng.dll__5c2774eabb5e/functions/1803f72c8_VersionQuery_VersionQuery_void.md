# VersionQuery::VersionQuery(void)

- ea: `0x1803f72c8`
- end: `0x1803f7381`
- name: `??0VersionQuery@@QEAA@XZ`
- size: `185`
- prototype: `VersionQuery *__fastcall(VersionQuery *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1803fb8e0`

## callees

- `0x1803f72c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1803f72f5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1803f7315`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1803f72f5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1803f7315`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1803f7333`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1803f734d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1803f7367`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1803f7333`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1803f734d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1803f7367`

## string_xrefs

- `0x1803f730c`: `version.dll`
- `0x1803f72ee`: `api-ms-win-core-version-l1-1-0.dll`

## pseudocode

```c
VersionQuery *__fastcall VersionQuery::VersionQuery(VersionQuery *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v4; // rcx
  FARPROC v5; // rax
  HMODULE v6; // rcx

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  Library = LoadLibraryExW(L"api-ms-win-core-version-l1-1-0.dll", 0, 0);
  *(_QWORD *)this = Library;
  if ( Library || (Library = LoadLibraryExW(L"version.dll", 0, 0), (*(_QWORD *)this = Library) != 0) )
  {
    ProcAddress = GetProcAddress(Library, "GetFileVersionInfoSizeExW");
    v4 = *(HMODULE *)this;
    *((_QWORD *)this + 1) = ProcAddress;
    v5 = GetProcAddress(v4, "GetFileVersionInfoExW");
    v6 = *(HMODULE *)this;
    *((_QWORD *)this + 2) = v5;
    *((_QWORD *)this + 3) = GetProcAddress(v6, "VerQueryValueW");
  }
  return this;
}

```

## disassembly

```asm
0x1803f72c8  push    rbx
0x1803f72ca  sub     rsp, 20h
0x1803f72ce  mov     rbx, rcx
0x1803f72d1  mov     qword ptr [rcx+8], 0
0x1803f72d9  mov     qword ptr [rcx+10h], 0
0x1803f72e1  xor     r8d, r8d; dwFlags
0x1803f72e4  mov     qword ptr [rcx+18h], 0
0x1803f72ec  xor     edx, edx; hFile
0x1803f72ee  lea     rcx, aApiMsWinCoreVe_0; "api-ms-win-core-version-l1-1-0.dll"
0x1803f72f5  call    cs:__imp_LoadLibraryExW
0x1803f72fc  nop     dword ptr [rax+rax+00h]
0x1803f7301  mov     [rbx], rax
0x1803f7304  test    rax, rax
0x1803f7307  jnz     short loc_1803F7329
0x1803f7309  xor     r8d, r8d; dwFlags
0x1803f730c  lea     rcx, aVersionDll; "version.dll"
0x1803f7313  xor     edx, edx; hFile
0x1803f7315  call    cs:__imp_LoadLibraryExW
0x1803f731c  nop     dword ptr [rax+rax+00h]
0x1803f7321  mov     [rbx], rax
0x1803f7324  test    rax, rax
0x1803f7327  jz      short loc_1803F7377
0x1803f7329  lea     rdx, aGetfileversion_2; "GetFileVersionInfoSizeExW"
0x1803f7330  mov     rcx, rax; hModule
0x1803f7333  call    cs:__imp_GetProcAddress
0x1803f733a  nop     dword ptr [rax+rax+00h]
0x1803f733f  mov     rcx, [rbx]; hModule
0x1803f7342  lea     rdx, aGetfileversion; "GetFileVersionInfoExW"
0x1803f7349  mov     [rbx+8], rax
0x1803f734d  call    cs:__imp_GetProcAddress
0x1803f7354  nop     dword ptr [rax+rax+00h]
0x1803f7359  mov     rcx, [rbx]; hModule
0x1803f735c  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x1803f7363  mov     [rbx+10h], rax
0x1803f7367  call    cs:__imp_GetProcAddress
0x1803f736e  nop     dword ptr [rax+rax+00h]
0x1803f7373  mov     [rbx+18h], rax
0x1803f7377  mov     rax, rbx
0x1803f737a  add     rsp, 20h
0x1803f737e  pop     rbx
0x1803f737f  retn
```
