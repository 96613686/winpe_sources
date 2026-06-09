# ApiSetQueryApiSetPresence

- ea: `0x180032420`
- end: `0x1800324b8`
- name: `ApiSetQueryApiSetPresence`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003af4`
- `0x180003c64`

## callees

- `0x1800152d0`
- `0x180032420`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032487`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032487`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180032447`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180032447`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800324a0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800324a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032455`

## string_xrefs

- `0x18003243a`: `ntdll.dll`
- `0x18003245b`: `LoadLibraryExW failed [%d]`

## pseudocode

```c
__int64 __fastcall ApiSetQueryApiSetPresence(__int64 a1, _BYTE *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rbx
  DWORD LastError; // eax
  FARPROC ProcAddress; // rax

  *a2 = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "ApiSetQueryApiSetPresence");
    if ( ProcAddress )
      ((void (__fastcall *)(__int64, _BYTE *))ProcAddress)(a1, a2);
    FreeLibrary(v5);
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "ApiSetQueryApiSetPresence", 603, "LoadLibraryExW failed [%d]", LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x180032420  mov     [rsp+arg_0], rbx
0x180032425  mov     [rsp+arg_8], rsi
0x18003242a  push    rdi
0x18003242b  sub     rsp, 30h
0x18003242f  mov     rdi, rdx
0x180032432  mov     byte ptr [rdx], 0
0x180032435  mov     rsi, rcx
0x180032438  xor     edx, edx; hFile
0x18003243a  lea     rcx, LibFileName; "ntdll.dll"
0x180032441  mov     r8d, 800h; dwFlags
0x180032447  call    cs:__imp_LoadLibraryExW
0x18003244d  mov     rbx, rax
0x180032450  test    rax, rax
0x180032453  jnz     short loc_18003247D
0x180032455  call    cs:__imp_GetLastError
0x18003245b  lea     r9, aLoadlibraryexw_1; "LoadLibraryExW failed [%d]"
0x180032462  mov     r8d, 25Bh
0x180032468  lea     rdx, aApisetqueryapi; "ApiSetQueryApiSetPresence"
0x18003246f  mov     [rsp+38h+var_18], eax
0x180032473  lea     ecx, [rbx+1]
0x180032476  call    AslLogCallPrintf
0x18003247b  jmp     short loc_1800324A6
0x18003247d  lea     rdx, aApisetqueryapi; "ApiSetQueryApiSetPresence"
0x180032484  mov     rcx, rbx; hModule
0x180032487  call    cs:__imp_GetProcAddress
0x18003248d  test    rax, rax
0x180032490  jz      short loc_18003249D
0x180032492  mov     rdx, rdi
0x180032495  mov     rcx, rsi
0x180032498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003249d  mov     rcx, rbx; hLibModule
0x1800324a0  call    cs:__imp_FreeLibrary
0x1800324a6  mov     rbx, [rsp+38h+arg_0]
0x1800324ab  xor     eax, eax
0x1800324ad  mov     rsi, [rsp+38h+arg_8]
0x1800324b2  add     rsp, 30h
0x1800324b6  pop     rdi
0x1800324b7  retn
```
