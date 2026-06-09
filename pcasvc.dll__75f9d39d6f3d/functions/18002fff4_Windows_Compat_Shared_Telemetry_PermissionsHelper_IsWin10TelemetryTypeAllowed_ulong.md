# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x18002fff4`
- end: `0x180030120`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `300`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002fecc`
- `0x1800b3d38`

## callees

- `0x18002fff4`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003001c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003009e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003001c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003009e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030056`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030107`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030115`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030056`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030107`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030115`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030034`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800300b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800300e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030034`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800300b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800300e0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800300c8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800300c8`

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
  HMODULE v10; // rax
  FARPROC v11; // rax
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
LABEL_5:
        FreeLibrary(v4);
        goto LABEL_6;
      }
    }
  }
  v13 = 0;
  v8 = 0;
  v10 = LoadLibraryExW(L"Aepic", 0, 0x800u);
  v7 = v10;
  if ( v10 && (v11 = GetProcAddress(v10, "GetPrivacyLevel")) != 0
    || (LibraryW = LoadLibraryW(L"Devinv"), (v2 = LibraryW) != 0)
    && (v11 = GetProcAddress(LibraryW, "GetPrivacyLevel")) != 0 )
  {
    if ( ((int (__fastcall *)(unsigned int *))v11)(&v13) >= 0 )
      v8 = a1 <= v13;
  }
  if ( v4 )
    goto LABEL_5;
LABEL_6:
  if ( v7 )
    FreeLibrary(v7);
  if ( v2 )
    FreeLibrary(v2);
  return v8;
}

```

## disassembly

```asm
0x18002fff4  mov     [rsp+arg_0], rbx
0x18002fff9  mov     [rsp+arg_10], rbp
0x18002fffe  push    rsi
0x18002ffff  push    rdi
0x180030000  push    r14
0x180030002  sub     rsp, 20h
0x180030006  mov     r14d, ecx
0x180030009  mov     edi, 800h
0x18003000e  mov     r8d, edi; dwFlags
0x180030011  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings"
0x180030018  xor     edx, edx; hFile
0x18003001a  xor     ebx, ebx
0x18003001c  call    cs:__imp_LoadLibraryExW
0x180030022  mov     rsi, rax
0x180030025  test    rax, rax
0x180030028  jz      short loc_18003008B
0x18003002a  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180030031  mov     rcx, rax; hModule
0x180030034  call    cs:__imp_GetProcAddress
0x18003003a  test    rax, rax
0x18003003d  jz      short loc_18003008B
0x18003003f  mov     ecx, r14d
0x180030042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030047  test    eax, eax
0x180030049  js      short loc_18003008B
0x18003004b  xor     edi, edi
0x18003004d  test    eax, eax
0x18003004f  setz    bpl
0x180030053  mov     rcx, rsi; hLibModule
0x180030056  call    cs:__imp_FreeLibrary
0x18003005c  test    rdi, rdi
0x18003005f  jnz     loc_180030104
0x180030065  test    rbx, rbx
0x180030068  jnz     loc_180030112
0x18003006e  mov     rbx, [rsp+38h+arg_0]
0x180030073  mov     al, bpl
0x180030076  mov     rbp, [rsp+38h+arg_10]
0x18003007b  add     rsp, 20h
0x18003007f  pop     r14
0x180030081  pop     rdi
0x180030082  pop     rsi
0x180030083  retn
0x180030084  test    rsi, rsi
0x180030087  jz      short loc_18003005C
0x180030089  jmp     short loc_180030053
0x18003008b  mov     r8d, edi; dwFlags
0x18003008e  mov     [rsp+38h+arg_8], ebx
0x180030092  xor     edx, edx; hFile
0x180030094  lea     rcx, aAepic; "Aepic"
0x18003009b  xor     bpl, bpl
0x18003009e  call    cs:__imp_LoadLibraryExW
0x1800300a4  mov     rdi, rax
0x1800300a7  test    rax, rax
0x1800300aa  jz      short loc_1800300C1
0x1800300ac  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x1800300b3  mov     rcx, rax; hModule
0x1800300b6  call    cs:__imp_GetProcAddress
0x1800300bc  test    rax, rax
0x1800300bf  jnz     short loc_1800300EB
0x1800300c1  lea     rcx, aDevinv; "Devinv"
0x1800300c8  call    cs:__imp_LoadLibraryW
0x1800300ce  mov     rbx, rax
0x1800300d1  test    rax, rax
0x1800300d4  jz      short loc_180030084
0x1800300d6  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x1800300dd  mov     rcx, rax; hModule
0x1800300e0  call    cs:__imp_GetProcAddress
0x1800300e6  test    rax, rax
0x1800300e9  jz      short loc_180030084
0x1800300eb  lea     rcx, [rsp+38h+arg_8]
0x1800300f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300f5  test    eax, eax
0x1800300f7  js      short loc_180030084
0x1800300f9  cmp     r14d, [rsp+38h+arg_8]
0x1800300fe  setbe   bpl
0x180030102  jmp     short loc_180030084
0x180030104  mov     rcx, rdi; hLibModule
0x180030107  call    cs:__imp_FreeLibrary
0x18003010d  jmp     loc_180030065
0x180030112  mov     rcx, rbx; hLibModule
0x180030115  call    cs:__imp_FreeLibrary
0x18003011b  jmp     loc_18003006E
```
