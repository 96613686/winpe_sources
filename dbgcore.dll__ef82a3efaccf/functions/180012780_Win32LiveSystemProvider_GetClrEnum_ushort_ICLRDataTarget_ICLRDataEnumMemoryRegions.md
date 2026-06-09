# Win32LiveSystemProvider::GetClrEnum(ushort *,ICLRDataTarget *,ICLRDataEnumMemoryRegions * *)

- ea: `0x180012780`
- end: `0x1800128f2`
- name: `?GetClrEnum@Win32LiveSystemProvider@@UEAAJPEAGPEAUICLRDataTarget@@PEAPEAUICLRDataEnumMemoryRegions@@@Z`
- size: `370`
- prototype: `int(Win32LiveSystemProvider *__hidden this, unsigned __int16 *, struct ICLRDataTarget *, struct ICLRDataEnumMemoryRegions **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001710`
- `0x180012780`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800127b2`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800127b2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012864`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180012864`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180012819`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180012819`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001289c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800128c3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001289c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800128c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001282b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001286f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001282b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001286f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012879`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180012805`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180012805`

## string_xrefs

- `0x18001285a`: `CLRDataCreateInstance`

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
0x180012780  push    rbx
0x180012782  push    rbp
0x180012783  push    rsi
0x180012784  push    rdi
0x180012785  sub     rsp, 1C8h
0x18001278c  mov     rax, cs:__security_cookie
0x180012793  xor     rax, rsp
0x180012796  mov     [rsp+1E8h+var_38], rax
0x18001279e  mov     rbx, rdx
0x1800127a1  mov     rsi, r8
0x1800127a4  mov     rdi, rcx
0x1800127a7  xor     r8d, r8d; dwFlags
0x1800127aa  mov     rcx, rbx; lpLibFileName
0x1800127ad  xor     edx, edx; hFile
0x1800127af  mov     rbp, r9
0x1800127b2  call    cs:__imp_LoadLibraryExW
0x1800127b8  mov     [rdi+2E0h], rax
0x1800127bf  test    rax, rax
0x1800127c2  jnz     loc_18001285A
0x1800127c8  call    cs:__imp_GetLastError
0x1800127ce  cmp     eax, 78h ; 'x'
0x1800127d1  jnz     short loc_18001282B
0x1800127d3  mov     [rsp+1E8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800127dc  lea     rax, [rsp+1E8h+MultiByteStr]
0x1800127e1  mov     [rsp+1E8h+lpDefaultChar], 0; lpDefaultChar
0x1800127ea  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800127ee  mov     [rsp+1E8h+cbMultiByte], 168h; cbMultiByte
0x1800127f6  mov     r8, rbx; lpWideCharStr
0x1800127f9  mov     edx, 400h; dwFlags
0x1800127fe  mov     [rsp+1E8h+lpMultiByteStr], rax; lpMultiByteStr
0x180012803  xor     ecx, ecx; CodePage
0x180012805  call    cs:__imp_WideCharToMultiByte
0x18001280b  test    eax, eax
0x18001280d  jz      short loc_18001282B
0x18001280f  xor     r8d, r8d; dwFlags
0x180012812  lea     rcx, [rsp+1E8h+MultiByteStr]; lpLibFileName
0x180012817  xor     edx, edx; hFile
0x180012819  call    cs:__imp_LoadLibraryExA
0x18001281f  mov     [rdi+2E0h], rax
0x180012826  test    rax, rax
0x180012829  jnz     short loc_18001285A
0x18001282b  call    cs:__imp_GetLastError
0x180012831  test    eax, eax
0x180012833  jz      short loc_180012853
0x180012835  call    cs:__imp_GetLastError
0x18001283b  mov     ebx, eax
0x18001283d  test    eax, eax
0x18001283f  jle     loc_1800128D4
0x180012845  movzx   ebx, ax
0x180012848  or      ebx, 80070000h
0x18001284e  jmp     loc_1800128D4
0x180012853  mov     ebx, 80004005h
0x180012858  jmp     short loc_1800128D4
0x18001285a  lea     rdx, aClrdatacreatei; "CLRDataCreateInstance"
0x180012861  mov     rcx, rax; hModule
0x180012864  call    cs:__imp_GetProcAddress
0x18001286a  test    rax, rax
0x18001286d  jnz     short loc_1800128A4
0x18001286f  call    cs:__imp_GetLastError
0x180012875  test    eax, eax
0x180012877  jz      short loc_180012890
0x180012879  call    cs:__imp_GetLastError
0x18001287f  mov     ebx, eax
0x180012881  test    eax, eax
0x180012883  jle     short loc_180012895
0x180012885  movzx   ebx, ax
0x180012888  or      ebx, 80070000h
0x18001288e  jmp     short loc_180012895
0x180012890  mov     ebx, 80004005h
0x180012895  mov     rcx, [rdi+2E0h]; hLibModule
0x18001289c  call    cs:__imp_FreeLibrary
0x1800128a2  jmp     short loc_1800128D4
0x1800128a4  mov     r8, rbp
0x1800128a7  lea     rcx, _GUID_471c35b4_7c2f_4ef0_a945_00f8c38056f1
0x1800128ae  mov     rdx, rsi
0x1800128b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128b6  mov     ebx, eax
0x1800128b8  test    eax, eax
0x1800128ba  jz      short loc_1800128D4
0x1800128bc  mov     rcx, [rdi+2E0h]; hLibModule
0x1800128c3  call    cs:__imp_FreeLibrary
0x1800128c9  mov     qword ptr [rdi+2E0h], 0
0x1800128d4  mov     eax, ebx
0x1800128d6  mov     rcx, [rsp+1E8h+var_38]
0x1800128de  xor     rcx, rsp; StackCookie
0x1800128e1  call    __security_check_cookie
0x1800128e6  add     rsp, 1C8h
0x1800128ed  pop     rdi
0x1800128ee  pop     rsi
0x1800128ef  pop     rbp
0x1800128f0  pop     rbx
0x1800128f1  retn
```
