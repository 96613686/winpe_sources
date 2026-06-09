# Win32LiveSystemProvider::LoadPsApi(void)

- ea: `0x180400b10`
- end: `0x180400d21`
- name: `?LoadPsApi@Win32LiveSystemProvider@@IEAAJXZ`
- size: `529`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1803fe0ec`
- `0x1804017d0`

## callees

- `0x180400b10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400bf4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400c15`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400c36`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400cb2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400cd3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400cf4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400bf4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400c15`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400c36`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400cb2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400cd3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180400cf4`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180400b38`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180400b60`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180400c5d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180400b38`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180400b60`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180400c5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400bcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400c85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400bcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180400c85`

## string_xrefs

- `0x180400b57`: `api-ms-win-core-psapi-obsolete-l1-1-0.dll`
- `0x180400c56`: `api-ms-win-core-psapi-obsolete-l1-1-0.dll`
- `0x180400b2f`: `psapi.dll`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::LoadPsApi(Win32LiveSystemProvider *this)
{
  unsigned int v1; // ebx
  HMODULE Library; // rax
  signed int LastError; // eax
  HMODULE v5; // rcx
  signed int v6; // eax
  FARPROC ProcAddress; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx
  signed int v11; // eax
  FARPROC v12; // rax
  HMODULE v13; // rcx
  FARPROC v14; // rax
  HMODULE v15; // rcx
  FARPROC v16; // rax

  v1 = *((_DWORD *)this + 122);
  if ( v1 == 1 )
  {
    Library = LoadLibraryExA("psapi.dll", 0, 0);
    *((_QWORD *)this + 62) = Library;
    if ( Library )
      goto LABEL_19;
    Library = LoadLibraryExA("api-ms-win-core-psapi-obsolete-l1-1-0.dll", 0, 0);
    *((_QWORD *)this + 62) = Library;
    if ( Library )
      goto LABEL_19;
    v1 = -2147467259;
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2147467259;
    }
    v5 = (HMODULE)*((_QWORD *)this + 16);
    *((_DWORD *)this + 122) = LastError;
    if ( v5 )
    {
      ProcAddress = GetProcAddress(v5, "K32EnumProcessModules");
      v8 = (HMODULE)*((_QWORD *)this + 16);
      *((_QWORD *)this + 63) = ProcAddress;
      v9 = GetProcAddress(v8, "K32GetModuleFileNameExW");
      v10 = (HMODULE)*((_QWORD *)this + 16);
      *((_QWORD *)this + 64) = v9;
      *((_QWORD *)this + 65) = GetProcAddress(v10, "K32GetProcessMemoryInfo");
      v6 = 0;
    }
    else if ( GetLastError() )
    {
      v6 = GetLastError();
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    *((_DWORD *)this + 122) = v6;
    Library = LoadLibraryExA("api-ms-win-core-psapi-obsolete-l1-1-0.dll", 0, 0);
    *((_QWORD *)this + 62) = Library;
    if ( Library )
    {
LABEL_19:
      v12 = GetProcAddress(Library, "EnumProcessModules");
      v13 = (HMODULE)*((_QWORD *)this + 62);
      *((_QWORD *)this + 63) = v12;
      v14 = GetProcAddress(v13, "GetModuleFileNameExW");
      v15 = (HMODULE)*((_QWORD *)this + 62);
      *((_QWORD *)this + 64) = v14;
      v16 = GetProcAddress(v15, "GetProcessMemoryInfo");
      *((_DWORD *)this + 122) = 0;
      v1 = 0;
      *((_QWORD *)this + 65) = v16;
    }
    else
    {
      if ( GetLastError() )
      {
        v11 = GetLastError();
        v1 = v11;
        if ( v11 > 0 )
          v1 = (unsigned __int16)v11 | 0x80070000;
      }
      *((_DWORD *)this + 122) = v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180400b10  mov     [rsp+arg_0], rbx
0x180400b15  push    rdi
0x180400b16  sub     rsp, 20h
0x180400b1a  mov     ebx, [rcx+1E8h]
0x180400b20  mov     rdi, rcx
0x180400b23  cmp     ebx, 1
0x180400b26  jnz     loc_180400D13
0x180400b2c  xor     r8d, r8d; dwFlags
0x180400b2f  lea     rcx, aPsapiDll; "psapi.dll"
0x180400b36  xor     edx, edx; hFile
0x180400b38  call    cs:__imp_LoadLibraryExA
0x180400b3f  nop     dword ptr [rax+rax+00h]
0x180400b44  mov     [rdi+1F0h], rax
0x180400b4b  test    rax, rax
0x180400b4e  jnz     loc_180400CA8
0x180400b54  xor     r8d, r8d; dwFlags
0x180400b57  lea     rcx, aApiMsWinCorePs_0; "api-ms-win-core-psapi-obsolete-l1-1-0.d"...
0x180400b5e  xor     edx, edx; hFile
0x180400b60  call    cs:__imp_LoadLibraryExA
0x180400b67  nop     dword ptr [rax+rax+00h]
0x180400b6c  mov     [rdi+1F0h], rax
0x180400b73  test    rax, rax
0x180400b76  jnz     loc_180400CA8
0x180400b7c  call    cs:__imp_GetLastError
0x180400b83  nop     dword ptr [rax+rax+00h]
0x180400b88  mov     ebx, 80004005h
0x180400b8d  test    eax, eax
0x180400b8f  jz      short loc_180400BAB
0x180400b91  call    cs:__imp_GetLastError
0x180400b98  nop     dword ptr [rax+rax+00h]
0x180400b9d  test    eax, eax
0x180400b9f  jle     short loc_180400BAD
0x180400ba1  movzx   eax, ax
0x180400ba4  or      eax, 80070000h
0x180400ba9  jmp     short loc_180400BAD
0x180400bab  mov     eax, ebx
0x180400bad  mov     rcx, [rdi+80h]; hModule
0x180400bb4  mov     [rdi+1E8h], eax
0x180400bba  test    rcx, rcx
0x180400bbd  jnz     short loc_180400BED
0x180400bbf  call    cs:__imp_GetLastError
0x180400bc6  nop     dword ptr [rax+rax+00h]
0x180400bcb  test    eax, eax
0x180400bcd  jz      short loc_180400BE9
0x180400bcf  call    cs:__imp_GetLastError
0x180400bd6  nop     dword ptr [rax+rax+00h]
0x180400bdb  test    eax, eax
0x180400bdd  jle     short loc_180400C4B
0x180400bdf  movzx   eax, ax
0x180400be2  or      eax, 80070000h
0x180400be7  jmp     short loc_180400C4B
0x180400be9  mov     eax, ebx
0x180400beb  jmp     short loc_180400C4B
0x180400bed  lea     rdx, aK32enumprocess; "K32EnumProcessModules"
0x180400bf4  call    cs:__imp_GetProcAddress
0x180400bfb  nop     dword ptr [rax+rax+00h]
0x180400c00  mov     rcx, [rdi+80h]; hModule
0x180400c07  lea     rdx, aK32getmodulefi; "K32GetModuleFileNameExW"
0x180400c0e  mov     [rdi+1F8h], rax
0x180400c15  call    cs:__imp_GetProcAddress
0x180400c1c  nop     dword ptr [rax+rax+00h]
0x180400c21  mov     rcx, [rdi+80h]; hModule
0x180400c28  lea     rdx, aK32getprocessm; "K32GetProcessMemoryInfo"
0x180400c2f  mov     [rdi+200h], rax
0x180400c36  call    cs:__imp_GetProcAddress
0x180400c3d  nop     dword ptr [rax+rax+00h]
0x180400c42  mov     [rdi+208h], rax
0x180400c49  xor     eax, eax
0x180400c4b  xor     r8d, r8d; dwFlags
0x180400c4e  mov     [rdi+1E8h], eax
0x180400c54  xor     edx, edx; hFile
0x180400c56  lea     rcx, aApiMsWinCorePs_0; "api-ms-win-core-psapi-obsolete-l1-1-0.d"...
0x180400c5d  call    cs:__imp_LoadLibraryExA
0x180400c64  nop     dword ptr [rax+rax+00h]
0x180400c69  mov     [rdi+1F0h], rax
0x180400c70  test    rax, rax
0x180400c73  jnz     short loc_180400CA8
0x180400c75  call    cs:__imp_GetLastError
0x180400c7c  nop     dword ptr [rax+rax+00h]
0x180400c81  test    eax, eax
0x180400c83  jz      short loc_180400CA0
0x180400c85  call    cs:__imp_GetLastError
0x180400c8c  nop     dword ptr [rax+rax+00h]
0x180400c91  mov     ebx, eax
0x180400c93  test    eax, eax
0x180400c95  jle     short loc_180400CA0
0x180400c97  movzx   ebx, ax
0x180400c9a  or      ebx, 80070000h
0x180400ca0  mov     [rdi+1E8h], ebx
0x180400ca6  jmp     short loc_180400D13
0x180400ca8  lea     rdx, aEnumprocessmod; "EnumProcessModules"
0x180400caf  mov     rcx, rax; hModule
0x180400cb2  call    cs:__imp_GetProcAddress
0x180400cb9  nop     dword ptr [rax+rax+00h]
0x180400cbe  mov     rcx, [rdi+1F0h]; hModule
0x180400cc5  lea     rdx, aGetmodulefilen; "GetModuleFileNameExW"
0x180400ccc  mov     [rdi+1F8h], rax
0x180400cd3  call    cs:__imp_GetProcAddress
0x180400cda  nop     dword ptr [rax+rax+00h]
0x180400cdf  mov     rcx, [rdi+1F0h]; hModule
0x180400ce6  lea     rdx, aGetprocessmemo; "GetProcessMemoryInfo"
0x180400ced  mov     [rdi+200h], rax
0x180400cf4  call    cs:__imp_GetProcAddress
0x180400cfb  nop     dword ptr [rax+rax+00h]
0x180400d00  mov     dword ptr [rdi+1E8h], 0
0x180400d0a  xor     ebx, ebx
0x180400d0c  mov     [rdi+208h], rax
0x180400d13  mov     eax, ebx
0x180400d15  mov     rbx, [rsp+28h+arg_0]
0x180400d1a  add     rsp, 20h
0x180400d1e  pop     rdi
0x180400d1f  retn
```
