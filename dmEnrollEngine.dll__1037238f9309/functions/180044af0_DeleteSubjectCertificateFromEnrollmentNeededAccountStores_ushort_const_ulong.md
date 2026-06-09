# DeleteSubjectCertificateFromEnrollmentNeededAccountStores(ushort const *,ulong)

- ea: `0x180044af0`
- end: `0x180044b72`
- name: `?DeleteSubjectCertificateFromEnrollmentNeededAccountStores@@YAJPEBGK@Z`
- size: `130`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180044958`
- `0x18004eb6c`

## callees

- `0x180044af0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044b58`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044b58`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044b0c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044b0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044b24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b40`

## string_xrefs

- `0x180044aff`: `SecRuntime.dll`
- `0x180044b1a`: `DeleteSubjectCertificateFromEnrollmentNeededAccountStores`

## pseudocode

```c
__int64 __fastcall DeleteSubjectCertificateFromEnrollmentNeededAccountStores(const unsigned __int16 *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v5; // ebx
  signed int LastError; // eax

  Library = LoadLibraryExW(L"SecRuntime.dll", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DeleteSubjectCertificateFromEnrollmentNeededAccountStores");
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(const unsigned __int16 *, __int64))ProcAddress)(a1, 1);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    FreeLibrary(v3);
  }
  else
  {
    return (unsigned int)-2147467263;
  }
  return v5;
}

```

## disassembly

```asm
0x180044af0  mov     [rsp+arg_0], rbx
0x180044af5  push    rdi
0x180044af6  sub     rsp, 20h
0x180044afa  mov     rbx, rcx
0x180044afd  xor     edx, edx; hFile
0x180044aff  lea     rcx, LibFileName; "SecRuntime.dll"
0x180044b06  mov     r8d, 800h; dwFlags
0x180044b0c  call    cs:__imp_LoadLibraryExW
0x180044b12  mov     rdi, rax
0x180044b15  test    rax, rax
0x180044b18  jz      short loc_180044B60
0x180044b1a  lea     rdx, aDeletesubjectc; "DeleteSubjectCertificateFromEnrollmentN"...
0x180044b21  mov     rcx, rax; hModule
0x180044b24  call    cs:__imp_GetProcAddress
0x180044b2a  test    rax, rax
0x180044b2d  jz      short loc_180044B40
0x180044b2f  mov     edx, 1
0x180044b34  mov     rcx, rbx
0x180044b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b3c  mov     ebx, eax
0x180044b3e  jmp     short loc_180044B55
0x180044b40  call    cs:__imp_GetLastError
0x180044b46  mov     ebx, eax
0x180044b48  test    eax, eax
0x180044b4a  jle     short loc_180044B55
0x180044b4c  movzx   ebx, ax
0x180044b4f  or      ebx, 80070000h
0x180044b55  mov     rcx, rdi; hLibModule
0x180044b58  call    cs:__imp_FreeLibrary
0x180044b5e  jmp     short loc_180044B65
0x180044b60  mov     ebx, 80004001h
0x180044b65  mov     eax, ebx
0x180044b67  mov     rbx, [rsp+28h+arg_0]
0x180044b6c  add     rsp, 20h
0x180044b70  pop     rdi
0x180044b71  retn
```
