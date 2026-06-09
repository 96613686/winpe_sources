# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x180048230`
- end: `0x180048348`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `280`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004bb3c`
- `0x1800a23c0`
- `0x1800a29c4`
- `0x1800a44fc`
- `0x1800c45d0`

## callees

- `0x180048230`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180048258`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800482a4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180048258`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800482a4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180048310`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004831e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004832c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180048310`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004831e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004832c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048270`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800482bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800482e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048270`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800482bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800482e6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800482ce`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800482ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180048230  mov     [rsp+arg_0], rbx
0x180048235  mov     [rsp+arg_10], rbp
0x18004823a  push    rsi
0x18004823b  push    rdi
0x18004823c  push    r14
0x18004823e  sub     rsp, 20h
0x180048242  mov     r14d, ecx
0x180048245  mov     edi, 800h
0x18004824a  mov     r8d, edi; dwFlags
0x18004824d  lea     rcx, aDiagnosticdata_0; "DiagnosticDataSettings"
0x180048254  xor     edx, edx; hFile
0x180048256  xor     ebx, ebx
0x180048258  call    cs:__imp_LoadLibraryExW
0x18004825e  mov     rsi, rax
0x180048261  test    rax, rax
0x180048264  jz      short loc_180048291
0x180048266  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x18004826d  mov     rcx, rax; hModule
0x180048270  call    cs:__imp_GetProcAddress
0x180048276  test    rax, rax
0x180048279  jz      short loc_180048291
0x18004827b  mov     ecx, r14d
0x18004827e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048283  test    eax, eax
0x180048285  js      short loc_180048291
0x180048287  xor     edi, edi
0x180048289  test    eax, eax
0x18004828b  setz    bpl
0x18004828f  jmp     short loc_18004830D
0x180048291  mov     r8d, edi; dwFlags
0x180048294  mov     [rsp+38h+arg_8], ebx
0x180048298  xor     edx, edx; hFile
0x18004829a  lea     rcx, aAepic; "Aepic"
0x1800482a1  xor     bpl, bpl
0x1800482a4  call    cs:__imp_LoadLibraryExW
0x1800482aa  mov     rdi, rax
0x1800482ad  test    rax, rax
0x1800482b0  jz      short loc_1800482C7
0x1800482b2  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x1800482b9  mov     rcx, rax; hModule
0x1800482bc  call    cs:__imp_GetProcAddress
0x1800482c2  test    rax, rax
0x1800482c5  jnz     short loc_1800482F1
0x1800482c7  lea     rcx, aDevinv; "Devinv"
0x1800482ce  call    cs:__imp_LoadLibraryW
0x1800482d4  mov     rbx, rax
0x1800482d7  test    rax, rax
0x1800482da  jz      short loc_180048308
0x1800482dc  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x1800482e3  mov     rcx, rax; hModule
0x1800482e6  call    cs:__imp_GetProcAddress
0x1800482ec  test    rax, rax
0x1800482ef  jz      short loc_180048308
0x1800482f1  lea     rcx, [rsp+38h+arg_8]
0x1800482f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482fb  test    eax, eax
0x1800482fd  js      short loc_180048308
0x1800482ff  cmp     r14d, [rsp+38h+arg_8]
0x180048304  setbe   bpl
0x180048308  test    rsi, rsi
0x18004830b  jz      short loc_180048316
0x18004830d  mov     rcx, rsi; hLibModule
0x180048310  call    cs:__imp_FreeLibrary
0x180048316  test    rdi, rdi
0x180048319  jz      short loc_180048324
0x18004831b  mov     rcx, rdi; hLibModule
0x18004831e  call    cs:__imp_FreeLibrary
0x180048324  test    rbx, rbx
0x180048327  jz      short loc_180048332
0x180048329  mov     rcx, rbx; hLibModule
0x18004832c  call    cs:__imp_FreeLibrary
0x180048332  mov     rbx, [rsp+38h+arg_0]
0x180048337  mov     al, bpl
0x18004833a  mov     rbp, [rsp+38h+arg_10]
0x18004833f  add     rsp, 20h
0x180048343  pop     r14
0x180048345  pop     rdi
0x180048346  pop     rsi
0x180048347  retn
```
