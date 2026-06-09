# InitializeRegTermsrvFpns

- ea: `0x18002f878`
- end: `0x18002f9d2`
- name: `InitializeRegTermsrvFpns`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800361ec`

## callees

- `0x18002f878`
- `0x18002fae0`
- `0x18002fb18`
- `0x18002fd88`
- `0x18002ff34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f902`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f919`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f930`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f947`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f95e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f975`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f98c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f9a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f9ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f902`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f919`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f930`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f947`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f95e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f975`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f98c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f9a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f9ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f8e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f8e6`

## string_xrefs

- `0x18002f8d6`: `tsappcmp.dll`
- `0x18002f8f8`: `TermsrvCreateRegEntry`
- `0x18002f908`: `TermsrvOpenRegEntry`
- `0x18002f94d`: `TermsrvDeleteValue`
- `0x18002f936`: `TermsrvDeleteKey`
- `0x18002f97b`: `TermsrvSetKeySecurity`
- `0x18002f992`: `TermsrvOpenUserClasses`

## pseudocode

```c
char __fastcall InitializeRegTermsrvFpns(__int64 a1, _DWORD *a2)
{
  int CompatFlags; // eax
  __int16 v6; // bx
  char v7; // di
  HMODULE Library; // rax
  HMODULE v9; // rbx

  if ( (unsigned int)IsTerminalServerCompatible() || !(unsigned int)IsRegTSAppCompatEnabled(a1) )
    return 0;
  CompatFlags = GetCompatFlags();
  v6 = CompatFlags;
  *a2 = CompatFlags;
  if ( (unsigned int)IsSystemLUID() )
  {
    if ( (v6 & 0x2008) == 0x2008 )
      goto LABEL_8;
    return 0;
  }
  if ( (v6 & 0x108) == 0x108 )
    return 0;
LABEL_8:
  v7 = 0;
  Library = LoadLibraryExW(L"tsappcmp.dll", 0, 0x800u);
  v9 = Library;
  if ( Library )
  {
    qword_1800B5D10 = (__int64)GetProcAddress(Library, "TermsrvCreateRegEntry");
    qword_1800B5D18 = (__int64)GetProcAddress(v9, "TermsrvOpenRegEntry");
    qword_1800B5D20 = (__int64)GetProcAddress(v9, "TermsrvSetValueKey");
    qword_1800B5D28 = (__int64)GetProcAddress(v9, "TermsrvDeleteKey");
    qword_1800B5D30 = (__int64)GetProcAddress(v9, "TermsrvDeleteValue");
    qword_1800B5D38 = (__int64)GetProcAddress(v9, "TermsrvRestoreKey");
    qword_1800B5D40 = (__int64)GetProcAddress(v9, "TermsrvSetKeySecurity");
    qword_1800B5D48 = (__int64)GetProcAddress(v9, "TermsrvOpenUserClasses");
    qword_1800B5D50 = (__int64)GetProcAddress(v9, "TermsrvGetPreSetValue");
    return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x18002f878  mov     [rsp+arg_0], rbx
0x18002f87d  push    rdi
0x18002f87e  sub     rsp, 20h
0x18002f882  mov     rdi, rdx
0x18002f885  mov     rbx, rcx
0x18002f888  call    IsTerminalServerCompatible
0x18002f88d  test    eax, eax
0x18002f88f  jz      short loc_18002F89E
0x18002f891  xor     al, al
0x18002f893  mov     rbx, [rsp+28h+arg_0]
0x18002f898  add     rsp, 20h
0x18002f89c  pop     rdi
0x18002f89d  retn
0x18002f89e  mov     rcx, rbx
0x18002f8a1  call    IsRegTSAppCompatEnabled
0x18002f8a6  test    eax, eax
0x18002f8a8  jz      short loc_18002F891
0x18002f8aa  call    GetCompatFlags
0x18002f8af  mov     ebx, eax
0x18002f8b1  mov     [rdi], eax
0x18002f8b3  call    IsSystemLUID
0x18002f8b8  test    eax, eax
0x18002f8ba  jz      short loc_18002F8C9
0x18002f8bc  mov     eax, 2008h
0x18002f8c1  and     ebx, eax
0x18002f8c3  cmp     ebx, eax
0x18002f8c5  jnz     short loc_18002F891
0x18002f8c7  jmp     short loc_18002F8D4
0x18002f8c9  mov     eax, 108h
0x18002f8ce  and     ebx, eax
0x18002f8d0  cmp     ebx, eax
0x18002f8d2  jz      short loc_18002F891
0x18002f8d4  xor     edx, edx; hFile
0x18002f8d6  lea     rcx, LibFileName; "tsappcmp.dll"
0x18002f8dd  mov     r8d, 800h; dwFlags
0x18002f8e3  xor     dil, dil
0x18002f8e6  call    cs:__imp_LoadLibraryExW
0x18002f8ec  mov     rbx, rax
0x18002f8ef  test    rax, rax
0x18002f8f2  jz      loc_18002F9CA
0x18002f8f8  lea     rdx, aTermsrvcreater_0; "TermsrvCreateRegEntry"
0x18002f8ff  mov     rcx, rax; hModule
0x18002f902  call    cs:__imp_GetProcAddress
0x18002f908  lea     rdx, aTermsrvopenreg_0; "TermsrvOpenRegEntry"
0x18002f90f  mov     rcx, rbx; hModule
0x18002f912  mov     cs:qword_1800B5D10, rax
0x18002f919  call    cs:__imp_GetProcAddress
0x18002f91f  lea     rdx, aTermsrvsetvalu_0; "TermsrvSetValueKey"
0x18002f926  mov     rcx, rbx; hModule
0x18002f929  mov     cs:qword_1800B5D18, rax
0x18002f930  call    cs:__imp_GetProcAddress
0x18002f936  lea     rdx, aTermsrvdeletek_0; "TermsrvDeleteKey"
0x18002f93d  mov     rcx, rbx; hModule
0x18002f940  mov     cs:qword_1800B5D20, rax
0x18002f947  call    cs:__imp_GetProcAddress
0x18002f94d  lea     rdx, aTermsrvdeletev_0; "TermsrvDeleteValue"
0x18002f954  mov     rcx, rbx; hModule
0x18002f957  mov     cs:qword_1800B5D28, rax
0x18002f95e  call    cs:__imp_GetProcAddress
0x18002f964  lea     rdx, aTermsrvrestore_0; "TermsrvRestoreKey"
0x18002f96b  mov     rcx, rbx; hModule
0x18002f96e  mov     cs:qword_1800B5D30, rax
0x18002f975  call    cs:__imp_GetProcAddress
0x18002f97b  lea     rdx, aTermsrvsetkeys_0; "TermsrvSetKeySecurity"
0x18002f982  mov     rcx, rbx; hModule
0x18002f985  mov     cs:qword_1800B5D38, rax
0x18002f98c  call    cs:__imp_GetProcAddress
0x18002f992  lea     rdx, aTermsrvopenuse_0; "TermsrvOpenUserClasses"
0x18002f999  mov     rcx, rbx; hModule
0x18002f99c  mov     cs:qword_1800B5D40, rax
0x18002f9a3  call    cs:__imp_GetProcAddress
0x18002f9a9  lea     rdx, aTermsrvgetpres_0; "TermsrvGetPreSetValue"
0x18002f9b0  mov     rcx, rbx; hModule
0x18002f9b3  mov     cs:qword_1800B5D48, rax
0x18002f9ba  call    cs:__imp_GetProcAddress
0x18002f9c0  mov     cs:qword_1800B5D50, rax
0x18002f9c7  mov     dil, 1
0x18002f9ca  mov     al, dil
0x18002f9cd  jmp     loc_18002F893
```
