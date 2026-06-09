# RaiseInvalid16BitExeError

- ea: `0x180064df0`
- end: `0x180064f14`
- name: `RaiseInvalid16BitExeError`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800643a0`

## callees

- `0x180064df0`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x180064ec7`
- `ntdll!EtwEventWriteNoRegistration` at `0x180064ec7`
- `ntdll!RtlWow64LogMessageInEventLogger` at `0x180064e8d`
- `ntdll!RtlWow64LogMessageInEventLogger` at `0x180064e8d`
- `ntdll!RtlSetLastWin32Error` at `0x180064eef`
- `ntdll!RtlSetLastWin32Error` at `0x180064eef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064e41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064e41`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180064e5d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180064e5d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180064e23`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180064e23`

## string_xrefs

- `0x180064e0f`: `NtVdm64.Dll`

## pseudocode

```c
void __fastcall RaiseInvalid16BitExeError(unsigned __int16 *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  FARPROC ProcAddress; // rax
  ULONG v5; // ecx
  _QWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v7; // [rsp+30h] [rbp-28h] BYREF

  v7 = 0;
  Library = LoadLibraryExW(L"NtVdm64.Dll", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "NtVdm64RaiseInvalid16BitError");
    if ( ProcAddress )
      ((void (__fastcall *)(unsigned __int16 *))ProcAddress)(a1);
    FreeLibrary(v3);
  }
  v6[0] = *((_QWORD *)a1 + 1);
  v6[1] = 0;
  RtlWow64LogMessageInEventLogger(1, v6, 1073742933);
  *(_QWORD *)&v7 = *((_QWORD *)a1 + 1);
  *((_QWORD *)&v7 + 1) = *a1;
  EtwEventWriteNoRegistration(UserLoaderGuid, Launch16BitApp, 1, &v7);
  v5 = 193;
  if ( NtCurrentPeb()->ImageSubsystemMajorVersion > 3 )
    v5 = 216;
  RtlSetLastWin32Error(v5);
}

```

## disassembly

```asm
0x180064df0  mov     [rsp+arg_8], rbx
0x180064df5  push    rdi
0x180064df6  sub     rsp, 50h
0x180064dfa  mov     rax, cs:__security_cookie
0x180064e01  xor     rax, rsp
0x180064e04  mov     [rsp+58h+var_18], rax
0x180064e09  mov     rdi, rcx
0x180064e0c  xorps   xmm0, xmm0
0x180064e0f  lea     rcx, aNtvdm64Dll; "NtVdm64.Dll"
0x180064e16  xor     edx, edx; hFile
0x180064e18  mov     r8d, 800h; dwFlags
0x180064e1e  movups  [rsp+58h+var_28], xmm0
0x180064e23  call    cs:__imp_LoadLibraryExW
0x180064e2a  nop     dword ptr [rax+rax+00h]
0x180064e2f  mov     rbx, rax
0x180064e32  test    rax, rax
0x180064e35  jz      short loc_180064E69
0x180064e37  lea     rdx, aNtvdm64raisein; "NtVdm64RaiseInvalid16BitError"
0x180064e3e  mov     rcx, rax; hModule
0x180064e41  call    cs:__imp_GetProcAddress
0x180064e48  nop     dword ptr [rax+rax+00h]
0x180064e4d  test    rax, rax
0x180064e50  jz      short loc_180064E5A
0x180064e52  mov     rcx, rdi
0x180064e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e5a  mov     rcx, rbx; hLibModule
0x180064e5d  call    cs:__imp_FreeLibrary
0x180064e64  nop     dword ptr [rax+rax+00h]
0x180064e69  mov     rax, [rdi+8]
0x180064e6d  lea     rdx, [rsp+58h+var_38]
0x180064e72  mov     ebx, 1
0x180064e77  mov     [rsp+58h+var_38], rax
0x180064e7c  mov     ecx, ebx
0x180064e7e  mov     [rsp+58h+var_30], 0
0x180064e87  mov     r8d, 40000455h
0x180064e8d  call    cs:__imp_RtlWow64LogMessageInEventLogger
0x180064e94  nop     dword ptr [rax+rax+00h]
0x180064e99  mov     rax, [rdi+8]
0x180064e9d  lea     r9, [rsp+58h+var_28]
0x180064ea2  mov     qword ptr [rsp+58h+var_28], rax
0x180064ea7  lea     rdx, Launch16BitApp
0x180064eae  movzx   eax, word ptr [rdi]
0x180064eb1  lea     rcx, UserLoaderGuid
0x180064eb8  mov     r8d, ebx
0x180064ebb  mov     dword ptr [rsp+58h+var_28+8], eax
0x180064ebf  mov     dword ptr [rsp+58h+var_28+0Ch], 0
0x180064ec7  call    cs:__imp_EtwEventWriteNoRegistration
0x180064ece  nop     dword ptr [rax+rax+00h]
0x180064ed3  mov     rax, gs:60h
0x180064edc  mov     ecx, 0C1h
0x180064ee1  cmp     dword ptr [rax+12Ch], 3
0x180064ee8  jbe     short loc_180064EEF
0x180064eea  mov     ecx, 0D8h; LastError
0x180064eef  call    cs:__imp_RtlSetLastWin32Error
0x180064ef6  nop     dword ptr [rax+rax+00h]
0x180064efb  mov     rcx, [rsp+58h+var_18]
0x180064f00  xor     rcx, rsp; StackCookie
0x180064f03  call    __security_check_cookie
0x180064f08  mov     rbx, [rsp+58h+arg_8]
0x180064f0d  add     rsp, 50h
0x180064f11  pop     rdi
0x180064f12  retn
```
