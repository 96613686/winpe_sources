# Win32LiveSystemProvider::GetClrEnum(ushort *,ICLRDataTarget *,ICLRDataEnumMemoryRegions * *)

- ea: `0x1803feaa0`
- end: `0x1803fec58`
- name: `?GetClrEnum@Win32LiveSystemProvider@@UEAAJPEAGPEAUICLRDataTarget@@PEAPEAUICLRDataEnumMemoryRegions@@@Z`
- size: `440`
- prototype: `int(Win32LiveSystemProvider *__hidden this, unsigned __int16 *, struct ICLRDataTarget *, struct ICLRDataEnumMemoryRegions **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800f0f40`
- `0x1803feaa0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1803febf5`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1803fec22`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1803febf5`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1803fec22`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1803fead2`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1803fead2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1803febab`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1803febab`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1803feb4b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1803feb4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803feaee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803feb63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803feb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803febbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803febcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803feaee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803feb63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803feb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803febbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803febcc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1803feb31`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1803feb31`

## string_xrefs

- `0x1803feba1`: `CLRDataCreateInstance`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::GetClrEnum(
        Win32LiveSystemProvider *this,
        unsigned __int16 *a2,
        struct ICLRDataTarget *a3,
        struct ICLRDataEnumMemoryRegions **a4)
{
  HMODULE Library; // rax
  signed int v9; // eax
  unsigned int v10; // ebx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  CHAR MultiByteStr[368]; // [rsp+40h] [rbp-1A8h] BYREF

  Library = LoadLibraryExW(a2, 0, 0);
  *((_QWORD *)this + 92) = Library;
  if ( Library
    || GetLastError() == 120
    && WideCharToMultiByte(0, 0x400u, a2, -1, MultiByteStr, 360, 0, 0)
    && (Library = LoadLibraryExA(MultiByteStr, 0, 0), (*((_QWORD *)this + 92) = Library) != 0) )
  {
    ProcAddress = GetProcAddress(Library, "CLRDataCreateInstance");
    if ( ProcAddress )
    {
      v10 = ((__int64 (__fastcall *)(GUID *, struct ICLRDataTarget *, struct ICLRDataEnumMemoryRegions **))ProcAddress)(
              &GUID_471c35b4_7c2f_4ef0_a945_00f8c38056f1,
              a3,
              a4);
      if ( v10 )
      {
        FreeLibrary(*((HMODULE *)this + 92));
        *((_QWORD *)this + 92) = 0;
      }
    }
    else
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v10 = -2147467259;
      }
      FreeLibrary(*((HMODULE *)this + 92));
    }
  }
  else if ( GetLastError() )
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v10;
}

```

## disassembly

```asm
0x1803feaa0  push    rbx
0x1803feaa2  push    rbp
0x1803feaa3  push    rsi
0x1803feaa4  push    rdi
0x1803feaa5  sub     rsp, 1C8h
0x1803feaac  mov     rax, cs:__security_cookie
0x1803feab3  xor     rax, rsp
0x1803feab6  mov     [rsp+1E8h+var_38], rax
0x1803feabe  mov     rbx, rdx
0x1803feac1  mov     rsi, r8
0x1803feac4  mov     rdi, rcx
0x1803feac7  xor     r8d, r8d; dwFlags
0x1803feaca  mov     rcx, rbx; lpLibFileName
0x1803feacd  xor     edx, edx; hFile
0x1803feacf  mov     rbp, r9
0x1803fead2  call    cs:__imp_LoadLibraryExW
0x1803fead9  nop     dword ptr [rax+rax+00h]
0x1803feade  mov     [rdi+2E0h], rax
0x1803feae5  test    rax, rax
0x1803feae8  jnz     loc_1803FEBA1
0x1803feaee  call    cs:__imp_GetLastError
0x1803feaf5  nop     dword ptr [rax+rax+00h]
0x1803feafa  cmp     eax, 78h ; 'x'
0x1803feafd  jnz     short loc_1803FEB63
0x1803feaff  mov     [rsp+1E8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1803feb08  lea     rax, [rsp+1E8h+MultiByteStr]
0x1803feb0d  mov     [rsp+1E8h+lpDefaultChar], 0; lpDefaultChar
0x1803feb16  or      r9d, 0FFFFFFFFh; cchWideChar
0x1803feb1a  mov     [rsp+1E8h+cbMultiByte], 168h; cbMultiByte
0x1803feb22  mov     r8, rbx; lpWideCharStr
0x1803feb25  mov     edx, 400h; dwFlags
0x1803feb2a  mov     [rsp+1E8h+lpMultiByteStr], rax; lpMultiByteStr
0x1803feb2f  xor     ecx, ecx; CodePage
0x1803feb31  call    cs:__imp_WideCharToMultiByte
0x1803feb38  nop     dword ptr [rax+rax+00h]
0x1803feb3d  test    eax, eax
0x1803feb3f  jz      short loc_1803FEB63
0x1803feb41  xor     r8d, r8d; dwFlags
0x1803feb44  lea     rcx, [rsp+1E8h+MultiByteStr]; lpLibFileName
0x1803feb49  xor     edx, edx; hFile
0x1803feb4b  call    cs:__imp_LoadLibraryExA
0x1803feb52  nop     dword ptr [rax+rax+00h]
0x1803feb57  mov     [rdi+2E0h], rax
0x1803feb5e  test    rax, rax
0x1803feb61  jnz     short loc_1803FEBA1
0x1803feb63  call    cs:__imp_GetLastError
0x1803feb6a  nop     dword ptr [rax+rax+00h]
0x1803feb6f  test    eax, eax
0x1803feb71  jz      short loc_1803FEB97
0x1803feb73  call    cs:__imp_GetLastError
0x1803feb7a  nop     dword ptr [rax+rax+00h]
0x1803feb7f  mov     ebx, eax
0x1803feb81  test    eax, eax
0x1803feb83  jle     loc_1803FEC39
0x1803feb89  movzx   ebx, ax
0x1803feb8c  or      ebx, 80070000h
0x1803feb92  jmp     loc_1803FEC39
0x1803feb97  mov     ebx, 80004005h
0x1803feb9c  jmp     loc_1803FEC39
0x1803feba1  lea     rdx, aClrdatacreatei; "CLRDataCreateInstance"
0x1803feba8  mov     rcx, rax; hModule
0x1803febab  call    cs:__imp_GetProcAddress
0x1803febb2  nop     dword ptr [rax+rax+00h]
0x1803febb7  test    rax, rax
0x1803febba  jnz     short loc_1803FEC03
0x1803febbc  call    cs:__imp_GetLastError
0x1803febc3  nop     dword ptr [rax+rax+00h]
0x1803febc8  test    eax, eax
0x1803febca  jz      short loc_1803FEBE9
0x1803febcc  call    cs:__imp_GetLastError
0x1803febd3  nop     dword ptr [rax+rax+00h]
0x1803febd8  mov     ebx, eax
0x1803febda  test    eax, eax
0x1803febdc  jle     short loc_1803FEBEE
0x1803febde  movzx   ebx, ax
0x1803febe1  or      ebx, 80070000h
0x1803febe7  jmp     short loc_1803FEBEE
0x1803febe9  mov     ebx, 80004005h
0x1803febee  mov     rcx, [rdi+2E0h]; hLibModule
0x1803febf5  call    cs:__imp_FreeLibrary
0x1803febfc  nop     dword ptr [rax+rax+00h]
0x1803fec01  jmp     short loc_1803FEC39
0x1803fec03  mov     r8, rbp
0x1803fec06  lea     rcx, _GUID_471c35b4_7c2f_4ef0_a945_00f8c38056f1
0x1803fec0d  mov     rdx, rsi
0x1803fec10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803fec15  mov     ebx, eax
0x1803fec17  test    eax, eax
0x1803fec19  jz      short loc_1803FEC39
0x1803fec1b  mov     rcx, [rdi+2E0h]; hLibModule
0x1803fec22  call    cs:__imp_FreeLibrary
0x1803fec29  nop     dword ptr [rax+rax+00h]
0x1803fec2e  mov     qword ptr [rdi+2E0h], 0
0x1803fec39  mov     eax, ebx
0x1803fec3b  mov     rcx, [rsp+1E8h+var_38]
0x1803fec43  xor     rcx, rsp; StackCookie
0x1803fec46  call    __security_check_cookie
0x1803fec4b  add     rsp, 1C8h
0x1803fec52  pop     rdi
0x1803fec53  pop     rsi
0x1803fec54  pop     rbp
0x1803fec55  pop     rbx
0x1803fec56  retn
```
