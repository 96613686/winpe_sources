# MvSetCurrentUserProfileLanguages(ushort const *)

- ea: `0x18002edf0`
- end: `0x18002ef7e`
- name: `?MvSetCurrentUserProfileLanguages@@YAXPEBG@Z`
- size: `398`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002ef84`

## callees

- `0x180021cf4`
- `0x18002edf0`
- `0x18002f9bc`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ee3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ee3d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ef01`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ef01`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eede`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eede`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eef7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eef7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002eea1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002eea1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002ee17`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002ee17`
- `Bcp47Langs!ClearUserLocaleFromLanguageProfileOptOut` at `0x18002edfd`
- `Bcp47Langs!ClearUserLocaleFromLanguageProfileOptOut` at `0x18002edfd`

## string_xrefs

- `0x18002ee10`: `wpglobutil.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall MvSetCurrentUserProfileLanguages(const unsigned __int16 *a1)
{
  int v2; // eax
  HMODULE LibraryW; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rax
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  int dwOptions; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  HMODULE v15; // [rsp+78h] [rbp+20h]

  v2 = ClearUserLocaleFromLanguageProfileOptOut();
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)v2,
      dwOptions);
  LibraryW = LoadLibraryW(L"wpglobutil.dll");
  v4 = LibraryW;
  v15 = LibraryW;
  if ( !LibraryW )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)0x80070032LL,
      dwOptions);
  ProcAddress = GetProcAddress(LibraryW, "SetUserProfileLanguagesWP");
  v6 = ((__int64 (__fastcall *)(const unsigned __int16 *))ProcAddress)(a1);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)(unsigned int)v6,
      dwOptions);
  hKey = 0;
  v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegMultivariantStatus, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1B7,
      (int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)v7,
      dwOptionsa);
  Data = 1;
  v8 = RegSetValueExW(hKey, L"ChangedLanguageBeforeOOBE", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1BC,
      (int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\languageandregion.cpp",
      (const char *)v8,
      dwOptionsb);
  if ( hKey )
    RegCloseKey(hKey);
  FreeLibrary(v4);
}

```

## disassembly

```asm
0x18002edf0  mov     [rsp+arg_0], rbx
0x18002edf5  push    rdi
0x18002edf6  sub     rsp, 50h
0x18002edfa  mov     rdi, rcx
0x18002edfd  call    cs:__imp_ClearUserLocaleFromLanguageProfileOptOut
0x18002ee03  mov     rcx, [rsp+58h]; this
0x18002ee08  test    eax, eax
0x18002ee0a  js      loc_18002EF27
0x18002ee10  lea     rcx, LibFileName; "wpglobutil.dll"
0x18002ee17  call    cs:__imp_LoadLibraryW
0x18002ee1d  mov     rbx, rax
0x18002ee20  mov     [rsp+58h+arg_18], rax
0x18002ee25  mov     rcx, [rsp+58h]; this
0x18002ee2a  test    rax, rax
0x18002ee2d  jz      loc_18002EF3C
0x18002ee33  lea     rdx, aSetuserprofile; "SetUserProfileLanguagesWP"
0x18002ee3a  mov     rcx, rax; hModule
0x18002ee3d  call    cs:__imp_GetProcAddress
0x18002ee43  mov     rcx, rdi
0x18002ee46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee4b  mov     rcx, [rsp+58h]; this
0x18002ee50  test    eax, eax
0x18002ee52  js      loc_18002EF54
0x18002ee58  mov     [rsp+58h+hKey], 0
0x18002ee61  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18002ee6a  lea     rax, [rsp+58h+hKey]
0x18002ee6f  mov     [rsp+58h+phkResult], rax; phkResult
0x18002ee74  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002ee7d  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18002ee85  mov     [rsp+58h+dwOptions], 0; unsigned int
0x18002ee8d  xor     r9d, r9d; lpClass
0x18002ee90  xor     r8d, r8d; Reserved
0x18002ee93  mov     rdx, cs:?gc_wszRegMultivariantStatus@@3PEBGEB; lpSubKey
0x18002ee9a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002eea1  call    cs:__imp_RegCreateKeyExW
0x18002eea7  mov     rcx, [rsp+58h]; this
0x18002eeac  test    eax, eax
0x18002eeae  jnz     loc_18002EF69
0x18002eeb4  mov     [rsp+58h+Data], 1
0x18002eebc  lea     r9d, [rax+4]; dwType
0x18002eec0  mov     [rsp+58h+samDesired], r9d; cbData
0x18002eec5  lea     rax, [rsp+58h+Data]
0x18002eeca  mov     qword ptr [rsp+58h+dwOptions], rax; unsigned int
0x18002eecf  xor     r8d, r8d; Reserved
0x18002eed2  lea     rdx, ?gc_wszLanguageChanged@@3QBGB; "ChangedLanguageBeforeOOBE"
0x18002eed9  mov     rcx, [rsp+58h+hKey]; hKey
0x18002eede  call    cs:__imp_RegSetValueExW
0x18002eee4  mov     rcx, [rsp+58h]; this
0x18002eee9  test    eax, eax
0x18002eeeb  jnz     short loc_18002EF12
0x18002eeed  mov     rcx, [rsp+58h+hKey]; hKey
0x18002eef2  test    rcx, rcx
0x18002eef5  jz      short loc_18002EEFE
0x18002eef7  call    cs:__imp_RegCloseKey
0x18002eefd  nop
0x18002eefe  mov     rcx, rbx; hLibModule
0x18002ef01  call    cs:__imp_FreeLibrary
0x18002ef07  mov     rbx, [rsp+58h+arg_0]
0x18002ef0c  add     rsp, 50h
0x18002ef10  pop     rdi
0x18002ef11  retn
0x18002ef12  mov     r9d, eax; char *
0x18002ef15  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ef1c  mov     edx, 1BCh; void *
0x18002ef21  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002ef27  mov     r9d, eax; char *
0x18002ef2a  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ef31  mov     edx, 1A5h; void *
0x18002ef36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ef3c  mov     r9d, 80070032h; char *
0x18002ef42  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ef49  mov     edx, 1A9h; void *
0x18002ef4e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ef54  mov     r9d, eax; char *
0x18002ef57  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ef5e  mov     edx, 1ADh; void *
0x18002ef63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ef69  mov     r9d, eax; char *
0x18002ef6c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002ef73  mov     edx, 1B7h; void *
0x18002ef78  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
