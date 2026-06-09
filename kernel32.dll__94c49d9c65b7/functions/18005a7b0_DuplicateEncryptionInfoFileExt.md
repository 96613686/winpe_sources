# DuplicateEncryptionInfoFileExt

- ea: `0x18005a7b0`
- end: `0x18005a86c`
- name: `DuplicateEncryptionInfoFileExt`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18005a7b0`
- `0x18007c010`

## import_xrefs

- `ntdll!LdrAddRefDll` at `0x18005a831`
- `ntdll!LdrAddRefDll` at `0x18005a831`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a806`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a806`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a81f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a81f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005a7e4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005a7e4`

## string_xrefs

- `0x18005a7d7`: `advapi32.dll`

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
0x18005a7b0  push    rbx
0x18005a7b2  push    rbp
0x18005a7b3  push    rsi
0x18005a7b4  push    rdi
0x18005a7b5  push    r14
0x18005a7b7  push    r15
0x18005a7b9  sub     rsp, 38h
0x18005a7bd  mov     rbx, cs:pfnDuplicateEncryptionInfoFile
0x18005a7c4  mov     esi, r9d
0x18005a7c7  mov     ebp, r8d
0x18005a7ca  mov     r14, rdx
0x18005a7cd  mov     r15, rcx
0x18005a7d0  test    rbx, rbx
0x18005a7d3  jnz     short loc_18005A83E
0x18005a7d5  xor     edx, edx; hFile
0x18005a7d7  lea     rcx, AdvapiDllString; "advapi32.dll"
0x18005a7de  mov     r8d, 800h; dwFlags
0x18005a7e4  call    cs:__imp_LoadLibraryExW
0x18005a7ea  mov     rdi, rax
0x18005a7ed  test    rax, rax
0x18005a7f0  jnz     short loc_18005A7FC
0x18005a7f2  mov     eax, gs:68h
0x18005a7fa  jmp     short loc_18005A85F
0x18005a7fc  lea     rdx, aDuplicateencry_0; "DuplicateEncryptionInfoFile"
0x18005a803  mov     rcx, rdi; hModule
0x18005a806  call    cs:__imp_GetProcAddress
0x18005a80c  mov     rbx, rax
0x18005a80f  test    rax, rax
0x18005a812  jnz     short loc_18005A829
0x18005a814  mov     ebx, gs:68h
0x18005a81c  mov     rcx, rdi; hLibModule
0x18005a81f  call    cs:__imp_FreeLibrary
0x18005a825  mov     eax, ebx
0x18005a827  jmp     short loc_18005A85F
0x18005a829  mov     rdx, rdi; BaseAddress
0x18005a82c  mov     ecx, 1; Flags
0x18005a831  call    cs:__imp_LdrAddRefDll
0x18005a837  mov     cs:pfnDuplicateEncryptionInfoFile, rbx
0x18005a83e  mov     rax, [rsp+68h+arg_20]
0x18005a846  mov     r9d, esi
0x18005a849  mov     [rsp+68h+var_48], rax
0x18005a84e  mov     r8d, ebp
0x18005a851  mov     rax, rbx
0x18005a854  mov     rdx, r14
0x18005a857  mov     rcx, r15
0x18005a85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a85f  add     rsp, 38h
0x18005a863  pop     r15
0x18005a865  pop     r14
0x18005a867  pop     rdi
0x18005a868  pop     rsi
0x18005a869  pop     rbp
0x18005a86a  pop     rbx
0x18005a86b  retn
```
