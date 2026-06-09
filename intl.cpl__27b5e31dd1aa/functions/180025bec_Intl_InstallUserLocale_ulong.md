# Intl_InstallUserLocale(ulong)

- ea: `0x180025bec`
- end: `0x180025ca3`
- name: `?Intl_InstallUserLocale@@YAHK@Z`
- size: `183`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180014488`
- `0x18001e340`
- `0x18001e95c`
- `0x18001ee90`
- `0x18001f70c`
- `0x180020a9c`
- `0x1800245bc`
- `0x180025abc`

## callees

- `0x180023490`
- `0x180025bec`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025c6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025c6c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025c52`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025c52`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180025c19`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180025c19`
- `KERNEL32!NlsUpdateLocale` at `0x180025c39`
- `KERNEL32!NlsUpdateLocale` at `0x180025c39`

## string_xrefs

- `0x180025c4b`: `CoreGlobConfig.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Intl_InstallUserLocale(unsigned int a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  HMODULE Library; // rax
  void (*ProcAddress)(void); // rax
  HMODULE v6; // [rsp+38h] [rbp+10h] BYREF

  v1 = a1;
  if ( !g_localeInfo )
    return 0;
  v2 = *((_QWORD *)g_localeInfo + a1);
  if ( !v2
    || !IsValidLocaleName(*(LPCWSTR *)(v2 + 8))
    || (unsigned int)NlsUpdateLocale(*(_QWORD *)(*((_QWORD *)g_localeInfo + v1) + 8LL), 1) )
  {
    return 0;
  }
  Library = LoadLibraryExW(L"CoreGlobConfig.dll", 0, 0x800u);
  v6 = Library;
  if ( Library )
  {
    ProcAddress = (void (*)(void))GetProcAddress(Library, "SyncLanguageDataToCloud");
    if ( ProcAddress )
      ProcAddress();
  }
  RegUserLocaleIndex = v1;
  UserLocaleIndex = v1;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v6);
  return 1;
}

```

## disassembly

```asm
0x180025bec  mov     [rsp+arg_0], rbx
0x180025bf1  push    rdi
0x180025bf2  sub     rsp, 20h
0x180025bf6  mov     ebx, ecx
0x180025bf8  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180025bff  test    rax, rax
0x180025c02  jz      loc_180025C96
0x180025c08  mov     rcx, [rax+rbx*8]
0x180025c0c  test    rcx, rcx
0x180025c0f  jz      loc_180025C96
0x180025c15  mov     rcx, [rcx+8]; lpLocaleName
0x180025c19  call    cs:__imp_IsValidLocaleName
0x180025c1f  test    eax, eax
0x180025c21  jz      short loc_180025C96
0x180025c23  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180025c2a  mov     rcx, [rax+rbx*8]
0x180025c2e  mov     edi, 1
0x180025c33  mov     edx, edi
0x180025c35  mov     rcx, [rcx+8]
0x180025c39  call    cs:__imp_NlsUpdateLocale
0x180025c3f  test    eax, eax
0x180025c41  jnz     short loc_180025C96
0x180025c43  xor     edx, edx; hFile
0x180025c45  mov     r8d, 800h; dwFlags
0x180025c4b  lea     rcx, aCoreglobconfig; "CoreGlobConfig.dll"
0x180025c52  call    cs:__imp_LoadLibraryExW
0x180025c58  mov     [rsp+28h+arg_8], rax
0x180025c5d  test    rax, rax
0x180025c60  jz      short loc_180025C7C
0x180025c62  lea     rdx, aSynclanguageda; "SyncLanguageDataToCloud"
0x180025c69  mov     rcx, rax; hModule
0x180025c6c  call    cs:__imp_GetProcAddress
0x180025c72  test    rax, rax
0x180025c75  jz      short loc_180025C7C
0x180025c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c7c  mov     cs:?RegUserLocaleIndex@@3KA, ebx; ulong RegUserLocaleIndex
0x180025c82  mov     cs:?UserLocaleIndex@@3KA, ebx; ulong UserLocaleIndex
0x180025c88  lea     rcx, [rsp+28h+arg_8]
0x180025c8d  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180025c92  mov     eax, edi
0x180025c94  jmp     short loc_180025C98
0x180025c96  xor     eax, eax
0x180025c98  mov     rbx, [rsp+28h+arg_0]
0x180025c9d  add     rsp, 20h
0x180025ca1  pop     rdi
0x180025ca2  retn
```
