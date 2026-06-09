# DuplicateEncryptionInfoFileExt

- ea: `0x18005ff70`
- end: `0x180060049`
- name: `DuplicateEncryptionInfoFileExt`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18005ff70`
- `0x180084010`

## import_xrefs

- `ntdll!LdrAddRefDll` at `0x180060007`
- `ntdll!LdrAddRefDll` at `0x180060007`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005ffd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005ffd0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005ffef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005ffef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005ffa8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005ffa8`

## string_xrefs

- `0x18005ff9b`: `advapi32.dll`

## pseudocode

```c
ULONG __fastcall DuplicateEncryptionInfoFileExt(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, __int64 a5)
{
  FARPROC ProcAddress; // rbx
  HMODULE Library; // rax
  HMODULE v11; // rdi
  ULONG LastErrorValue; // ebx

  ProcAddress = (FARPROC)pfnDuplicateEncryptionInfoFile;
  if ( !pfnDuplicateEncryptionInfoFile )
  {
    Library = LoadLibraryExW(L"advapi32.dll", 0, 0x800u);
    v11 = Library;
    if ( !Library )
      return NtCurrentTeb()->LastErrorValue;
    ProcAddress = GetProcAddress(Library, "DuplicateEncryptionInfoFile");
    if ( !ProcAddress )
    {
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
      FreeLibrary(v11);
      return LastErrorValue;
    }
    LdrAddRefDll(1u, v11);
    pfnDuplicateEncryptionInfoFile = (__int64)ProcAddress;
  }
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64))ProcAddress)(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18005ff70  push    rbx
0x18005ff72  push    rbp
0x18005ff73  push    rsi
0x18005ff74  push    rdi
0x18005ff75  push    r14
0x18005ff77  push    r15
0x18005ff79  sub     rsp, 38h
0x18005ff7d  mov     rbx, cs:pfnDuplicateEncryptionInfoFile
0x18005ff84  mov     esi, r9d
0x18005ff87  mov     ebp, r8d
0x18005ff8a  mov     r14, rdx
0x18005ff8d  mov     r15, rcx
0x18005ff90  test    rbx, rbx
0x18005ff93  jnz     loc_18006001A
0x18005ff99  xor     edx, edx; hFile
0x18005ff9b  lea     rcx, AdvapiDllString; "advapi32.dll"
0x18005ffa2  mov     r8d, 800h; dwFlags
0x18005ffa8  call    cs:__imp_LoadLibraryExW
0x18005ffaf  nop     dword ptr [rax+rax+00h]
0x18005ffb4  mov     rdi, rax
0x18005ffb7  test    rax, rax
0x18005ffba  jnz     short loc_18005FFC6
0x18005ffbc  mov     eax, gs:68h
0x18005ffc4  jmp     short loc_18006003B
0x18005ffc6  lea     rdx, aDuplicateencry_0; "DuplicateEncryptionInfoFile"
0x18005ffcd  mov     rcx, rdi; hModule
0x18005ffd0  call    cs:__imp_GetProcAddress
0x18005ffd7  nop     dword ptr [rax+rax+00h]
0x18005ffdc  mov     rbx, rax
0x18005ffdf  test    rax, rax
0x18005ffe2  jnz     short loc_18005FFFF
0x18005ffe4  mov     ebx, gs:68h
0x18005ffec  mov     rcx, rdi; hLibModule
0x18005ffef  call    cs:__imp_FreeLibrary
0x18005fff6  nop     dword ptr [rax+rax+00h]
0x18005fffb  mov     eax, ebx
0x18005fffd  jmp     short loc_18006003B
0x18005ffff  mov     rdx, rdi; BaseAddress
0x180060002  mov     ecx, 1; Flags
0x180060007  call    cs:__imp_LdrAddRefDll
0x18006000e  nop     dword ptr [rax+rax+00h]
0x180060013  mov     cs:pfnDuplicateEncryptionInfoFile, rbx
0x18006001a  mov     rax, [rsp+68h+arg_20]
0x180060022  mov     r9d, esi
0x180060025  mov     [rsp+68h+var_48], rax
0x18006002a  mov     r8d, ebp
0x18006002d  mov     rax, rbx
0x180060030  mov     rdx, r14
0x180060033  mov     rcx, r15
0x180060036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006003b  add     rsp, 38h
0x18006003f  pop     r15
0x180060041  pop     r14
0x180060043  pop     rdi
0x180060044  pop     rsi
0x180060045  pop     rbp
0x180060046  pop     rbx
0x180060047  retn
```
