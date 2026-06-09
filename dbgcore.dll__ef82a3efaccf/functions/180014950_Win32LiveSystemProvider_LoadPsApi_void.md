# Win32LiveSystemProvider::LoadPsApi(void)

- ea: `0x180014950`
- end: `0x180014b06`
- name: `?LoadPsApi@Win32LiveSystemProvider@@IEAAJXZ`
- size: `438`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011e08`
- `0x1800153b0`

## callees

- `0x180014950`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014a10`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014a2b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014a46`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014aaa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014ac5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014ae0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014a10`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014a2b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014a46`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014aaa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014ac5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014ae0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180014978`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18001499a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180014a67`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180014978`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18001499a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180014a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a83`

## string_xrefs

- `0x18001496f`: `psapi.dll`
- `0x180014991`: `api-ms-win-core-psapi-obsolete-l1-1-0.dll`
- `0x180014a60`: `api-ms-win-core-psapi-obsolete-l1-1-0.dll`

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
0x180014950  mov     [rsp+arg_0], rbx
0x180014955  push    rdi
0x180014956  sub     rsp, 20h
0x18001495a  mov     ebx, [rcx+1E8h]
0x180014960  mov     rdi, rcx
0x180014963  cmp     ebx, 1
0x180014966  jnz     loc_180014AF9
0x18001496c  xor     r8d, r8d; dwFlags
0x18001496f  lea     rcx, aPsapiDll; "psapi.dll"
0x180014976  xor     edx, edx; hFile
0x180014978  call    cs:__imp_LoadLibraryExA
0x18001497e  mov     [rdi+1F0h], rax
0x180014985  test    rax, rax
0x180014988  jnz     loc_180014AA0
0x18001498e  xor     r8d, r8d; dwFlags
0x180014991  lea     rcx, aApiMsWinCorePs_0; "api-ms-win-core-psapi-obsolete-l1-1-0.d"...
0x180014998  xor     edx, edx; hFile
0x18001499a  call    cs:__imp_LoadLibraryExA
0x1800149a0  mov     [rdi+1F0h], rax
0x1800149a7  test    rax, rax
0x1800149aa  jnz     loc_180014AA0
0x1800149b0  call    cs:__imp_GetLastError
0x1800149b6  mov     ebx, 80004005h
0x1800149bb  test    eax, eax
0x1800149bd  jz      short loc_1800149D3
0x1800149bf  call    cs:__imp_GetLastError
0x1800149c5  test    eax, eax
0x1800149c7  jle     short loc_1800149D5
0x1800149c9  movzx   eax, ax
0x1800149cc  or      eax, 80070000h
0x1800149d1  jmp     short loc_1800149D5
0x1800149d3  mov     eax, ebx
0x1800149d5  mov     rcx, [rdi+80h]; hModule
0x1800149dc  mov     [rdi+1E8h], eax
0x1800149e2  test    rcx, rcx
0x1800149e5  jnz     short loc_180014A09
0x1800149e7  call    cs:__imp_GetLastError
0x1800149ed  test    eax, eax
0x1800149ef  jz      short loc_180014A05
0x1800149f1  call    cs:__imp_GetLastError
0x1800149f7  test    eax, eax
0x1800149f9  jle     short loc_180014A55
0x1800149fb  movzx   eax, ax
0x1800149fe  or      eax, 80070000h
0x180014a03  jmp     short loc_180014A55
0x180014a05  mov     eax, ebx
0x180014a07  jmp     short loc_180014A55
0x180014a09  lea     rdx, aK32enumprocess; "K32EnumProcessModules"
0x180014a10  call    cs:__imp_GetProcAddress
0x180014a16  mov     rcx, [rdi+80h]; hModule
0x180014a1d  lea     rdx, aK32getmodulefi; "K32GetModuleFileNameExW"
0x180014a24  mov     [rdi+1F8h], rax
0x180014a2b  call    cs:__imp_GetProcAddress
0x180014a31  mov     rcx, [rdi+80h]; hModule
0x180014a38  lea     rdx, aK32getprocessm; "K32GetProcessMemoryInfo"
0x180014a3f  mov     [rdi+200h], rax
0x180014a46  call    cs:__imp_GetProcAddress
0x180014a4c  mov     [rdi+208h], rax
0x180014a53  xor     eax, eax
0x180014a55  xor     r8d, r8d; dwFlags
0x180014a58  mov     [rdi+1E8h], eax
0x180014a5e  xor     edx, edx; hFile
0x180014a60  lea     rcx, aApiMsWinCorePs_0; "api-ms-win-core-psapi-obsolete-l1-1-0.d"...
0x180014a67  call    cs:__imp_LoadLibraryExA
0x180014a6d  mov     [rdi+1F0h], rax
0x180014a74  test    rax, rax
0x180014a77  jnz     short loc_180014AA0
0x180014a79  call    cs:__imp_GetLastError
0x180014a7f  test    eax, eax
0x180014a81  jz      short loc_180014A98
0x180014a83  call    cs:__imp_GetLastError
0x180014a89  mov     ebx, eax
0x180014a8b  test    eax, eax
0x180014a8d  jle     short loc_180014A98
0x180014a8f  movzx   ebx, ax
0x180014a92  or      ebx, 80070000h
0x180014a98  mov     [rdi+1E8h], ebx
0x180014a9e  jmp     short loc_180014AF9
0x180014aa0  lea     rdx, aEnumprocessmod; "EnumProcessModules"
0x180014aa7  mov     rcx, rax; hModule
0x180014aaa  call    cs:__imp_GetProcAddress
0x180014ab0  mov     rcx, [rdi+1F0h]; hModule
0x180014ab7  lea     rdx, aGetmodulefilen; "GetModuleFileNameExW"
0x180014abe  mov     [rdi+1F8h], rax
0x180014ac5  call    cs:__imp_GetProcAddress
0x180014acb  mov     rcx, [rdi+1F0h]; hModule
0x180014ad2  lea     rdx, aGetprocessmemo; "GetProcessMemoryInfo"
0x180014ad9  mov     [rdi+200h], rax
0x180014ae0  call    cs:__imp_GetProcAddress
0x180014ae6  mov     dword ptr [rdi+1E8h], 0
0x180014af0  xor     ebx, ebx
0x180014af2  mov     [rdi+208h], rax
0x180014af9  mov     eax, ebx
0x180014afb  mov     rbx, [rsp+28h+arg_0]
0x180014b00  add     rsp, 20h
0x180014b04  pop     rdi
0x180014b05  retn
```
