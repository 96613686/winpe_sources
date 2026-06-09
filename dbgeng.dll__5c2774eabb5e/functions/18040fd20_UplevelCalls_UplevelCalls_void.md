# UplevelCalls::UplevelCalls(void)

- ea: `0x18040fd20`
- end: `0x18040fe34`
- name: `??0UplevelCalls@@QEAA@XZ`
- size: `276`
- prototype: `UplevelCalls *__fastcall(UplevelCalls *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1803fc9e0`

## callees

- `0x18040fd20`
- `0x18040fe3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18040fd64`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18040fd64`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040fd87`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040fda1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040fdbc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040fdd7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040fdf2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040fd87`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040fda1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040fdbc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040fdd7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040fdf2`

## string_xrefs

- `0x18040fd5d`: `dbghelp.dll`
- `0x18040fde7`: `SymFunctionTableAccess64AccessRoutines`

## pseudocode

```c
UplevelCalls *__fastcall UplevelCalls::UplevelCalls(UplevelCalls *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v4; // rcx
  FARPROC v5; // rax
  HMODULE v6; // rcx
  FARPROC v7; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  bool v12; // zf

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  Library = LoadLibraryExW(L"dbghelp.dll", 0, 0);
  *((_QWORD *)this + 5) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "StackWalk64");
    v4 = (HMODULE)*((_QWORD *)this + 5);
    *(_QWORD *)this = ProcAddress;
    v5 = GetProcAddress(v4, "SymInitialize");
    v6 = (HMODULE)*((_QWORD *)this + 5);
    *((_QWORD *)this + 1) = v5;
    v7 = GetProcAddress(v6, "SymCleanup");
    v8 = (HMODULE)*((_QWORD *)this + 5);
    *((_QWORD *)this + 2) = v7;
    v9 = GetProcAddress(v8, "SymRegisterFunctionEntryCallback64");
    v10 = (HMODULE)*((_QWORD *)this + 5);
    *((_QWORD *)this + 3) = v9;
    v11 = GetProcAddress(v10, "SymFunctionTableAccess64AccessRoutines");
    v12 = *(_QWORD *)this == 0;
    *((_QWORD *)this + 4) = v11;
    if ( v12 || !*((_QWORD *)this + 1) || !*((_QWORD *)this + 2) || !*((_QWORD *)this + 3) || !v11 )
      UplevelCalls::CleanupStackWalk(this);
  }
  return this;
}

```

## disassembly

```asm
0x18040fd20  push    rbx
0x18040fd22  sub     rsp, 20h
0x18040fd26  mov     rbx, rcx
0x18040fd29  mov     qword ptr [rcx], 0
0x18040fd30  mov     qword ptr [rcx+8], 0
0x18040fd38  xor     r8d, r8d; dwFlags
0x18040fd3b  mov     qword ptr [rcx+10h], 0
0x18040fd43  xor     edx, edx; hFile
0x18040fd45  mov     qword ptr [rcx+18h], 0
0x18040fd4d  mov     qword ptr [rcx+20h], 0
0x18040fd55  mov     qword ptr [rcx+28h], 0
0x18040fd5d  lea     rcx, aDbghelpDll_0; "dbghelp.dll"
0x18040fd64  call    cs:__imp_LoadLibraryExW
0x18040fd6b  nop     dword ptr [rax+rax+00h]
0x18040fd70  mov     [rbx+28h], rax
0x18040fd74  test    rax, rax
0x18040fd77  jz      loc_18040FE2A
0x18040fd7d  lea     rdx, aStackwalk64; "StackWalk64"
0x18040fd84  mov     rcx, rax; hModule
0x18040fd87  call    cs:__imp_GetProcAddress
0x18040fd8e  nop     dword ptr [rax+rax+00h]
0x18040fd93  mov     rcx, [rbx+28h]; hModule
0x18040fd97  lea     rdx, aSyminitialize; "SymInitialize"
0x18040fd9e  mov     [rbx], rax
0x18040fda1  call    cs:__imp_GetProcAddress
0x18040fda8  nop     dword ptr [rax+rax+00h]
0x18040fdad  mov     rcx, [rbx+28h]; hModule
0x18040fdb1  lea     rdx, aSymcleanup; "SymCleanup"
0x18040fdb8  mov     [rbx+8], rax
0x18040fdbc  call    cs:__imp_GetProcAddress
0x18040fdc3  nop     dword ptr [rax+rax+00h]
0x18040fdc8  mov     rcx, [rbx+28h]; hModule
0x18040fdcc  lea     rdx, aSymregisterfun; "SymRegisterFunctionEntryCallback64"
0x18040fdd3  mov     [rbx+10h], rax
0x18040fdd7  call    cs:__imp_GetProcAddress
0x18040fdde  nop     dword ptr [rax+rax+00h]
0x18040fde3  mov     rcx, [rbx+28h]; hModule
0x18040fde7  lea     rdx, aSymfunctiontab; "SymFunctionTableAccess64AccessRoutines"
0x18040fdee  mov     [rbx+18h], rax
0x18040fdf2  call    cs:__imp_GetProcAddress
0x18040fdf9  nop     dword ptr [rax+rax+00h]
0x18040fdfe  cmp     qword ptr [rbx], 0
0x18040fe02  mov     [rbx+20h], rax
0x18040fe06  jz      short loc_18040FE22
0x18040fe08  cmp     qword ptr [rbx+8], 0
0x18040fe0d  jz      short loc_18040FE22
0x18040fe0f  cmp     qword ptr [rbx+10h], 0
0x18040fe14  jz      short loc_18040FE22
0x18040fe16  cmp     qword ptr [rbx+18h], 0
0x18040fe1b  jz      short loc_18040FE22
0x18040fe1d  test    rax, rax
0x18040fe20  jnz     short loc_18040FE2A
0x18040fe22  mov     rcx, rbx; this
0x18040fe25  call    ?CleanupStackWalk@UplevelCalls@@AEAAXXZ; UplevelCalls::CleanupStackWalk(void)
0x18040fe2a  mov     rax, rbx
0x18040fe2d  add     rsp, 20h
0x18040fe31  pop     rbx
0x18040fe32  retn
```
