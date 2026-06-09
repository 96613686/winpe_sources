# GetPhoneVersion(_OSVERSIONINFOW *)

- ea: `0x18005bb30`
- end: `0x18005bba0`
- name: `?GetPhoneVersion@@YAHPEAU_OSVERSIONINFOW@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(LPOSVERSIONINFOW lpVersionInformation)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800141d0`

## callees

- `0x18005bb30`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005bb80`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005bb80`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005bb4c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005bb4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005bb64`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005bb64`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18005bb8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18005bb8b`

## string_xrefs

- `0x18005bb3f`: `phoneinfo.dll`

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
0x18005bb30  mov     [rsp+arg_0], rbx
0x18005bb35  push    rdi
0x18005bb36  sub     rsp, 20h
0x18005bb3a  mov     rbx, rcx
0x18005bb3d  xor     edx, edx; hFile
0x18005bb3f  lea     rcx, aPhoneinfoDll; "phoneinfo.dll"
0x18005bb46  mov     r8d, 800h; dwFlags
0x18005bb4c  call    cs:__imp_LoadLibraryExW
0x18005bb52  mov     rdi, rax
0x18005bb55  test    rax, rax
0x18005bb58  jz      short loc_18005BB88
0x18005bb5a  lea     rdx, aGetphoneversio; "GetPhoneVersion"
0x18005bb61  mov     rcx, rax; hModule
0x18005bb64  call    cs:__imp_GetProcAddress
0x18005bb6a  test    rax, rax
0x18005bb6d  jz      short loc_18005BB7B
0x18005bb6f  mov     rcx, rbx
0x18005bb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb77  mov     ebx, eax
0x18005bb79  jmp     short loc_18005BB7D
0x18005bb7b  xor     ebx, ebx
0x18005bb7d  mov     rcx, rdi; hLibModule
0x18005bb80  call    cs:__imp_FreeLibrary
0x18005bb86  jmp     short loc_18005BB93
0x18005bb88  mov     rcx, rbx; lpVersionInformation
0x18005bb8b  call    cs:__imp_GetVersionExW
0x18005bb91  mov     ebx, eax
0x18005bb93  mov     eax, ebx
0x18005bb95  mov     rbx, [rsp+28h+arg_0]
0x18005bb9a  add     rsp, 20h
0x18005bb9e  pop     rdi
0x18005bb9f  retn
```
