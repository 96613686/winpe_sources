# TryCreatePdhErrorDetails

- ea: `0x18002c558`
- end: `0x18002c6c2`
- name: `TryCreatePdhErrorDetails`
- size: `362`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002b490`
- `0x18002bda0`

## callees

- `0x180006ef8`
- `0x180007920`
- `0x180007c80`
- `0x18002c558`
- `0x180042c5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c64a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c64a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c5ef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c5ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002c593`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002c593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c635`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002c6ac`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002c6ac`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002c62b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002c62b`

## string_xrefs

- `0x18002c588`: `mpunits.dll`
- `0x18002c5e6`: `pdh.dll`

## pseudocode

```c
HLOCAL __fastcall TryCreatePdhErrorDetails(DWORD a1)
{
  HMODULE ModuleHandleA; // rax
  HLOCAL result; // rax
  HMODULE Library; // rbx
  const int *v5; // rcx
  MI_Instance *v6; // rcx
  HLOCAL Buffer; // [rsp+68h] [rbp+18h] BYREF
  MI_Instance *extendedError; // [rsp+70h] [rbp+20h] BYREF

  Buffer = 0;
  extendedError = 0;
  if ( a1 == -1073738824 )
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_GetString_LoadString(ModuleHandleA, 2121);
    return (HLOCAL)MI_ReportErrorDetails_ForCustomError(-1073738824, (int)L"WIN32", 0, 0);
  }
  Library = LoadLibraryExW(L"pdh.dll", 0, 0);
  if ( Library )
  {
    if ( !FormatMessageW(0x900u, Library, a1, 0, (LPWSTR)&Buffer, 0, 0) && GetLastError() )
      Buffer = 0;
    FreeLibrary(Library);
    LODWORD(v5) = (_DWORD)Buffer;
    if ( Buffer )
      goto LABEL_10;
  }
  else
  {
    Buffer = 0;
  }
  v5 = &dword_18005C6C4;
LABEL_10:
  if ( (unsigned int)CreateOMIError_shared((int)v5, a1, (int)L"Win32", 0, (__int64)&OMI_Error_rtti, &extendedError) )
  {
    v6 = 0;
    extendedError = 0;
  }
  else
  {
    v6 = extendedError;
  }
  result = (HLOCAL)ReportErrorDetails(v6);
  extendedError = 0;
  if ( Buffer )
    return LocalFree(Buffer);
  return result;
}

```

## disassembly

```asm
0x18002c558  mov     [rsp-8+arg_0], rbx
0x18002c55d  mov     [rsp-8+arg_18], rdi
0x18002c562  push    rbp
0x18002c563  mov     rbp, rsp
0x18002c566  sub     rsp, 50h
0x18002c56a  mov     ebx, 0C0000BB8h
0x18002c56f  mov     [rbp+Buffer], 0
0x18002c577  mov     [rbp+extendedError], 0
0x18002c57f  mov     edi, ecx
0x18002c581  cmp     ecx, ebx
0x18002c583  jnz     short loc_18002C5E3
0x18002c585  xorps   xmm0, xmm0
0x18002c588  lea     rcx, ModuleName; "mpunits.dll"
0x18002c58f  movups  [rbp+var_10], xmm0
0x18002c593  call    cs:__imp_GetModuleHandleA
0x18002c599  mov     rcx, rax
0x18002c59c  mov     edx, 849h
0x18002c5a1  call    _Intlstr_GetString_LoadString
0x18002c5a6  mov     qword ptr [rbp+var_10], rax
0x18002c5aa  lea     r9, [rbp+var_10]
0x18002c5ae  mov     byte ptr [rbp+var_10+8], 0
0x18002c5b2  lea     rdx, aWin32; "WIN32"
0x18002c5b9  movaps  xmm0, [rbp+var_10]
0x18002c5bd  xor     r8d, r8d
0x18002c5c0  mov     qword ptr [rsp+50h+nSize], 0; __int64
0x18002c5c9  mov     ecx, ebx; int
0x18002c5cb  movdqa  [rbp+var_10], xmm0
0x18002c5d0  mov     [rsp+50h+lpBuffer], 0; __int64
0x18002c5d9  call    MI_ReportErrorDetails_ForCustomError
0x18002c5de  jmp     loc_18002C6B2
0x18002c5e3  xor     r8d, r8d; dwFlags
0x18002c5e6  lea     rcx, LibFileName; "pdh.dll"
0x18002c5ed  xor     edx, edx; hFile
0x18002c5ef  call    cs:__imp_LoadLibraryExW
0x18002c5f5  mov     rbx, rax
0x18002c5f8  test    rax, rax
0x18002c5fb  jnz     short loc_18002C603
0x18002c5fd  mov     [rbp+Buffer], rax
0x18002c601  jmp     short loc_18002C659
0x18002c603  mov     [rsp+50h+Arguments], 0; Arguments
0x18002c60c  lea     rax, [rbp+Buffer]
0x18002c610  mov     [rsp+50h+nSize], 0; nSize
0x18002c618  xor     r9d, r9d; dwLanguageId
0x18002c61b  mov     r8d, edi; dwMessageId
0x18002c61e  mov     [rsp+50h+lpBuffer], rax; lpBuffer
0x18002c623  mov     rdx, rbx; lpSource
0x18002c626  mov     ecx, 900h; dwFlags
0x18002c62b  call    cs:__imp_FormatMessageW
0x18002c631  test    eax, eax
0x18002c633  jnz     short loc_18002C647
0x18002c635  call    cs:__imp_GetLastError
0x18002c63b  test    eax, eax
0x18002c63d  jz      short loc_18002C647
0x18002c63f  mov     [rbp+Buffer], 0
0x18002c647  mov     rcx, rbx; hLibModule
0x18002c64a  call    cs:__imp_FreeLibrary
0x18002c650  mov     rcx, [rbp+Buffer]
0x18002c654  test    rcx, rcx
0x18002c657  jnz     short loc_18002C660
0x18002c659  lea     rcx, dword_18005C6C4; int
0x18002c660  lea     rax, [rbp+extendedError]
0x18002c664  xor     r9d, r9d; int
0x18002c667  mov     qword ptr [rsp+50h+nSize], rax; extendedError
0x18002c66c  lea     r8, aWin32_0; "Win32"
0x18002c673  lea     rax, OMI_Error_rtti
0x18002c67a  mov     edx, edi; int
0x18002c67c  mov     [rsp+50h+lpBuffer], rax; __int64
0x18002c681  call    CreateOMIError_shared
0x18002c686  test    eax, eax
0x18002c688  jz      short loc_18002C692
0x18002c68a  xor     ecx, ecx
0x18002c68c  mov     [rbp+extendedError], rcx
0x18002c690  jmp     short loc_18002C696
0x18002c692  mov     rcx, [rbp+extendedError]; lpTlsValue
0x18002c696  call    ReportErrorDetails
0x18002c69b  mov     rcx, [rbp+Buffer]; hMem
0x18002c69f  mov     [rbp+extendedError], 0
0x18002c6a7  test    rcx, rcx
0x18002c6aa  jz      short loc_18002C6B2
0x18002c6ac  call    cs:__imp_LocalFree
0x18002c6b2  mov     rbx, [rsp+50h+arg_0]
0x18002c6b7  mov     rdi, [rsp+50h+arg_18]
0x18002c6bc  add     rsp, 50h
0x18002c6c0  pop     rbp
0x18002c6c1  retn
```
