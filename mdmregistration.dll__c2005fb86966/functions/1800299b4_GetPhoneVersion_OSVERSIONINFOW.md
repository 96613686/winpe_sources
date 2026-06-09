# GetPhoneVersion(_OSVERSIONINFOW *)

- ea: `0x1800299b4`
- end: `0x180029a3d`
- name: `?GetPhoneVersion@@YAHPEAU_OSVERSIONINFOW@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(LPOSVERSIONINFOW lpVersionInformation)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180022e74`

## callees

- `0x1800299b4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029a10`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029a10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800299ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800299ee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800299d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800299d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180029a21`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180029a21`

## string_xrefs

- `0x1800299c3`: `phoneinfo.dll`

## pseudocode

```c
__int64 __fastcall GetPhoneVersion(LPOSVERSIONINFOW lpVersionInformation)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v5; // ebx

  Library = LoadLibraryExW(L"phoneinfo.dll", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetPhoneVersion");
    if ( ProcAddress )
      v5 = ((__int64 (__fastcall *)(LPOSVERSIONINFOW))ProcAddress)(lpVersionInformation);
    else
      v5 = 0;
    FreeLibrary(v3);
  }
  else
  {
    return GetVersionExW(lpVersionInformation);
  }
  return v5;
}

```

## disassembly

```asm
0x1800299b4  mov     [rsp+arg_0], rbx
0x1800299b9  push    rdi
0x1800299ba  sub     rsp, 20h
0x1800299be  mov     rbx, rcx
0x1800299c1  xor     edx, edx; hFile
0x1800299c3  lea     rcx, LibFileName; "phoneinfo.dll"
0x1800299ca  mov     r8d, 800h; dwFlags
0x1800299d0  call    cs:__imp_LoadLibraryExW
0x1800299d7  nop     dword ptr [rax+rax+00h]
0x1800299dc  mov     rdi, rax
0x1800299df  test    rax, rax
0x1800299e2  jz      short loc_180029A1E
0x1800299e4  lea     rdx, aGetphoneversio; "GetPhoneVersion"
0x1800299eb  mov     rcx, rax; hModule
0x1800299ee  call    cs:__imp_GetProcAddress
0x1800299f5  nop     dword ptr [rax+rax+00h]
0x1800299fa  test    rax, rax
0x1800299fd  jz      short loc_180029A0B
0x1800299ff  mov     rcx, rbx
0x180029a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a07  mov     ebx, eax
0x180029a09  jmp     short loc_180029A0D
0x180029a0b  xor     ebx, ebx
0x180029a0d  mov     rcx, rdi; hLibModule
0x180029a10  call    cs:__imp_FreeLibrary
0x180029a17  nop     dword ptr [rax+rax+00h]
0x180029a1c  jmp     short loc_180029A2F
0x180029a1e  mov     rcx, rbx; lpVersionInformation
0x180029a21  call    cs:__imp_GetVersionExW
0x180029a28  nop     dword ptr [rax+rax+00h]
0x180029a2d  mov     ebx, eax
0x180029a2f  mov     eax, ebx
0x180029a31  mov     rbx, [rsp+28h+arg_0]
0x180029a36  add     rsp, 20h
0x180029a3a  pop     rdi
0x180029a3b  retn
```
