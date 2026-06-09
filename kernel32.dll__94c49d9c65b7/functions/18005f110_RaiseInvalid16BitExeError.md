# RaiseInvalid16BitExeError

- ea: `0x18005f110`
- end: `0x18005f20f`
- name: `RaiseInvalid16BitExeError`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18005e780`

## callees

- `0x18005f110`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x18005f1cf`
- `ntdll!EtwEventWriteNoRegistration` at `0x18005f1cf`
- `ntdll!RtlWow64LogMessageInEventLogger` at `0x18005f19b`
- `ntdll!RtlWow64LogMessageInEventLogger` at `0x18005f19b`
- `ntdll!RtlSetLastWin32Error` at `0x18005f1f1`
- `ntdll!RtlSetLastWin32Error` at `0x18005f1f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f15b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005f15b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005f171`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005f171`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f143`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005f143`

## string_xrefs

- `0x18005f12f`: `NtVdm64.Dll`

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
0x18005f110  mov     [rsp+arg_8], rbx
0x18005f115  push    rdi
0x18005f116  sub     rsp, 50h
0x18005f11a  mov     rax, cs:__security_cookie
0x18005f121  xor     rax, rsp
0x18005f124  mov     [rsp+58h+var_18], rax
0x18005f129  mov     rdi, rcx
0x18005f12c  xorps   xmm0, xmm0
0x18005f12f  lea     rcx, aNtvdm64Dll; "NtVdm64.Dll"
0x18005f136  xor     edx, edx; hFile
0x18005f138  mov     r8d, 800h; dwFlags
0x18005f13e  movups  [rsp+58h+var_28], xmm0
0x18005f143  call    cs:__imp_LoadLibraryExW
0x18005f149  mov     rbx, rax
0x18005f14c  test    rax, rax
0x18005f14f  jz      short loc_18005F177
0x18005f151  lea     rdx, aNtvdm64raisein; "NtVdm64RaiseInvalid16BitError"
0x18005f158  mov     rcx, rax; hModule
0x18005f15b  call    cs:__imp_GetProcAddress
0x18005f161  test    rax, rax
0x18005f164  jz      short loc_18005F16E
0x18005f166  mov     rcx, rdi
0x18005f169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f16e  mov     rcx, rbx; hLibModule
0x18005f171  call    cs:__imp_FreeLibrary
0x18005f177  mov     rax, [rdi+8]
0x18005f17b  lea     rdx, [rsp+58h+var_38]
0x18005f180  mov     ebx, 1
0x18005f185  mov     [rsp+58h+var_38], rax
0x18005f18a  mov     ecx, ebx
0x18005f18c  mov     [rsp+58h+var_30], 0
0x18005f195  mov     r8d, 40000455h
0x18005f19b  call    cs:__imp_RtlWow64LogMessageInEventLogger
0x18005f1a1  mov     rax, [rdi+8]
0x18005f1a5  lea     r9, [rsp+58h+var_28]
0x18005f1aa  mov     qword ptr [rsp+58h+var_28], rax
0x18005f1af  lea     rdx, Launch16BitApp
0x18005f1b6  movzx   eax, word ptr [rdi]
0x18005f1b9  lea     rcx, UserLoaderGuid
0x18005f1c0  mov     r8d, ebx
0x18005f1c3  mov     dword ptr [rsp+58h+var_28+8], eax
0x18005f1c7  mov     dword ptr [rsp+58h+var_28+0Ch], 0
0x18005f1cf  call    cs:__imp_EtwEventWriteNoRegistration
0x18005f1d5  mov     rax, gs:60h
0x18005f1de  mov     ecx, 0C1h
0x18005f1e3  cmp     dword ptr [rax+12Ch], 3
0x18005f1ea  jbe     short loc_18005F1F1
0x18005f1ec  mov     ecx, 0D8h; LastError
0x18005f1f1  call    cs:__imp_RtlSetLastWin32Error
0x18005f1f7  mov     rcx, [rsp+58h+var_18]
0x18005f1fc  xor     rcx, rsp; StackCookie
0x18005f1ff  call    __security_check_cookie
0x18005f204  mov     rbx, [rsp+58h+arg_8]
0x18005f209  add     rsp, 50h
0x18005f20d  pop     rdi
0x18005f20e  retn
```
