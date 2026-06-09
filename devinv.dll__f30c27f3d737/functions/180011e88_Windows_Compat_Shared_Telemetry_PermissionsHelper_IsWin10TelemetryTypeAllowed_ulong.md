# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x180011e88`
- end: `0x180011fa0`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `280`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800042a0`
- `0x1800132ec`
- `0x18002db94`

## callees

- `0x180011e88`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011eb0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011efc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011eb0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180011efc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011f68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011f76`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011f84`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011f68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011f76`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011f84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011ec8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011f14`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011f3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011ec8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011f14`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011f3e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180011f26`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180011f26`

## pseudocode

```c
bool __fastcall Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(unsigned int a1)
{
  HMODULE v2; // rbx
  HMODULE Library; // rax
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rax
  int v6; // eax
  HMODULE v7; // rdi
  bool v8; // bp
  HMODULE v9; // rax
  FARPROC v10; // rax
  HMODULE LibraryW; // rax
  unsigned int v13; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings", 0, 0x800u);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TelIsTelemetryTypeAllowed");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1);
      if ( v6 >= 0 )
      {
        v7 = 0;
        v8 = v6 == 0;
LABEL_12:
        FreeLibrary(v4);
        goto LABEL_13;
      }
    }
  }
  v13 = 0;
  v8 = 0;
  v9 = LoadLibraryExW(L"Aepic", 0, 0x800u);
  v7 = v9;
  if ( v9 && (v10 = GetProcAddress(v9, "GetPrivacyLevel")) != 0
    || (LibraryW = LoadLibraryW(L"Devinv"), (v2 = LibraryW) != 0)
    && (v10 = GetProcAddress(LibraryW, "GetPrivacyLevel")) != 0 )
  {
    if ( ((int (__fastcall *)(unsigned int *))v10)(&v13) >= 0 )
      v8 = a1 <= v13;
  }
  if ( v4 )
    goto LABEL_12;
LABEL_13:
  if ( v7 )
    FreeLibrary(v7);
  if ( v2 )
    FreeLibrary(v2);
  return v8;
}

```

## disassembly

```asm
0x180011e88  mov     [rsp+arg_0], rbx
0x180011e8d  mov     [rsp+arg_10], rbp
0x180011e92  push    rsi
0x180011e93  push    rdi
0x180011e94  push    r14
0x180011e96  sub     rsp, 20h
0x180011e9a  mov     r14d, ecx
0x180011e9d  mov     edi, 800h
0x180011ea2  mov     r8d, edi; dwFlags
0x180011ea5  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings"
0x180011eac  xor     edx, edx; hFile
0x180011eae  xor     ebx, ebx
0x180011eb0  call    cs:__imp_LoadLibraryExW
0x180011eb6  mov     rsi, rax
0x180011eb9  test    rax, rax
0x180011ebc  jz      short loc_180011EE9
0x180011ebe  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180011ec5  mov     rcx, rax; hModule
0x180011ec8  call    cs:__imp_GetProcAddress
0x180011ece  test    rax, rax
0x180011ed1  jz      short loc_180011EE9
0x180011ed3  mov     ecx, r14d
0x180011ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011edb  test    eax, eax
0x180011edd  js      short loc_180011EE9
0x180011edf  xor     edi, edi
0x180011ee1  test    eax, eax
0x180011ee3  setz    bpl
0x180011ee7  jmp     short loc_180011F65
0x180011ee9  mov     r8d, edi; dwFlags
0x180011eec  mov     [rsp+38h+arg_8], ebx
0x180011ef0  xor     edx, edx; hFile
0x180011ef2  lea     rcx, aAepic; "Aepic"
0x180011ef9  xor     bpl, bpl
0x180011efc  call    cs:__imp_LoadLibraryExW
0x180011f02  mov     rdi, rax
0x180011f05  test    rax, rax
0x180011f08  jz      short loc_180011F1F
0x180011f0a  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x180011f11  mov     rcx, rax; hModule
0x180011f14  call    cs:__imp_GetProcAddress
0x180011f1a  test    rax, rax
0x180011f1d  jnz     short loc_180011F49
0x180011f1f  lea     rcx, aDevinv_0; "Devinv"
0x180011f26  call    cs:__imp_LoadLibraryW
0x180011f2c  mov     rbx, rax
0x180011f2f  test    rax, rax
0x180011f32  jz      short loc_180011F60
0x180011f34  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x180011f3b  mov     rcx, rax; hModule
0x180011f3e  call    cs:__imp_GetProcAddress
0x180011f44  test    rax, rax
0x180011f47  jz      short loc_180011F60
0x180011f49  lea     rcx, [rsp+38h+arg_8]
0x180011f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f53  test    eax, eax
0x180011f55  js      short loc_180011F60
0x180011f57  cmp     r14d, [rsp+38h+arg_8]
0x180011f5c  setbe   bpl
0x180011f60  test    rsi, rsi
0x180011f63  jz      short loc_180011F6E
0x180011f65  mov     rcx, rsi; hLibModule
0x180011f68  call    cs:__imp_FreeLibrary
0x180011f6e  test    rdi, rdi
0x180011f71  jz      short loc_180011F7C
0x180011f73  mov     rcx, rdi; hLibModule
0x180011f76  call    cs:__imp_FreeLibrary
0x180011f7c  test    rbx, rbx
0x180011f7f  jz      short loc_180011F8A
0x180011f81  mov     rcx, rbx; hLibModule
0x180011f84  call    cs:__imp_FreeLibrary
0x180011f8a  mov     rbx, [rsp+38h+arg_0]
0x180011f8f  mov     al, bpl
0x180011f92  mov     rbp, [rsp+38h+arg_10]
0x180011f97  add     rsp, 20h
0x180011f9b  pop     r14
0x180011f9d  pop     rdi
0x180011f9e  pop     rsi
0x180011f9f  retn
```
