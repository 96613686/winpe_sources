# GetDeviceFamily(void)

- ea: `0x180027f1c`
- end: `0x180027fbb`
- name: `?GetDeviceFamily@@YAKXZ`
- size: `159`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180036768`
- `0x1800533a4`

## callees

- `0x180027f1c`
- `0x18003bc70`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027f93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027f93`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027f49`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027f49`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027f67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027f67`

## string_xrefs

- `0x180027f42`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 GetDeviceFamily(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v3; // edi
  int v5; // [rsp+20h] [rbp-18h] BYREF

  v5 = 3;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v1 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetDeviceFamilyInfoEnum");
    if ( ProcAddress )
      ((void (__fastcall *)(_QWORD, int *, _QWORD))ProcAddress)(0, &v5, 0);
  }
  v3 = v5;
  if ( v1 )
    FreeLibrary(v1);
  return v3;
}

```

## disassembly

```asm
0x180027f1c  mov     [rsp+arg_0], rbx
0x180027f21  push    rdi
0x180027f22  sub     rsp, 30h
0x180027f26  mov     rax, cs:__security_cookie
0x180027f2d  xor     rax, rsp
0x180027f30  mov     [rsp+38h+var_10], rax
0x180027f35  mov     [rsp+38h+var_18], 3
0x180027f3d  xor     r8d, r8d; dwFlags
0x180027f40  xor     edx, edx; hFile
0x180027f42  lea     rcx, LibFileName; "ntdll.dll"
0x180027f49  call    cs:__imp_LoadLibraryExW
0x180027f50  nop     dword ptr [rax+rax+00h]
0x180027f55  mov     rbx, rax
0x180027f58  test    rax, rax
0x180027f5b  jz      short loc_180027F87
0x180027f5d  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x180027f64  mov     rcx, rax; hModule
0x180027f67  call    cs:__imp_GetProcAddress
0x180027f6e  nop     dword ptr [rax+rax+00h]
0x180027f73  test    rax, rax
0x180027f76  jz      short loc_180027F87
0x180027f78  xor     r8d, r8d
0x180027f7b  lea     rdx, [rsp+38h+var_18]
0x180027f80  xor     ecx, ecx
0x180027f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f87  mov     edi, [rsp+38h+var_18]
0x180027f8b  test    rbx, rbx
0x180027f8e  jz      short loc_180027FA0
0x180027f90  mov     rcx, rbx; hLibModule
0x180027f93  call    cs:__imp_FreeLibrary
0x180027f9a  nop     dword ptr [rax+rax+00h]
0x180027f9f  nop
0x180027fa0  mov     eax, edi
0x180027fa2  mov     rcx, [rsp+38h+var_10]
0x180027fa7  xor     rcx, rsp; StackCookie
0x180027faa  call    __security_check_cookie
0x180027faf  mov     rbx, [rsp+38h+arg_0]
0x180027fb4  add     rsp, 30h
0x180027fb8  pop     rdi
0x180027fb9  retn
```
