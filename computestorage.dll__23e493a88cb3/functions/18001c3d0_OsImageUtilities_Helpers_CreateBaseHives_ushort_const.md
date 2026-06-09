# OsImageUtilities::Helpers::CreateBaseHives(ushort const *)

- ea: `0x18001c3d0`
- end: `0x18001c5cd`
- name: `?CreateBaseHives@Helpers@OsImageUtilities@@YAXPEBG@Z`
- size: `509`
- prototype: `void __fastcall(PCWSTR pszPathIn, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ea88`

## callees

- `0x180002690`
- `0x180008fac`
- `0x18000a578`
- `0x18000a678`
- `0x180012818`
- `0x1800136f8`
- `0x18001c3d0`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18001c531`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18001c531`

## string_xrefs

- `0x18001c5a9`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001c5bb`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001c44b`: `Windows\System32\Config`
- `0x18001c4a4`: `SECURITY`
- `0x18001c4b0`: `SECURITY_BASE`

## pseudocode

```c
void __fastcall OsImageUtilities::Helpers::CreateBaseHives(PCWSTR pszPathIn, const unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // rdx
  const WCHAR *v4; // rcx
  unsigned int DirectoryW; // eax
  const WCHAR *v6; // rdx
  PCWSTR *v7; // rbx
  const WCHAR *v8; // rdx
  const WCHAR *v9; // rdx
  const WCHAR *v10; // rdx
  const WCHAR *v11; // rcx
  const char *v12; // r9
  _QWORD v13[10]; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpPathName[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v15; // [rsp+88h] [rbp-78h]
  LPCWSTR lpFileName[4]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpExistingFileName[4]; // [rsp+B0h] [rbp-50h] BYREF
  PCWSTR pszPathIna[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD Src[4]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  Vml::CombineFilePath(Src, pszPathIn, L"Files");
  Vml::CombineFilePath(lpPathName, pszPathIn, L"Hives");
  v4 = (const WCHAR *)lpPathName;
  if ( v15 > 7 )
    v4 = lpPathName[0];
  DirectoryW = Vml::CreateDirectoryW(v4, v3);
  if ( DirectoryW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)DirectoryW,
      v13[0]);
  v6 = (const WCHAR *)Src;
  if ( Src[3] > 7u )
    v6 = (const WCHAR *)Src[0];
  Vml::CombineFilePath(pszPathIna, v6, L"Windows\\System32\\Config");
  v13[0] = L"SYSTEM";
  v13[1] = L"SYSTEM_BASE";
  v13[2] = L"SOFTWARE";
  v13[3] = L"SOFTWARE_BASE";
  v13[4] = L"SAM";
  v13[5] = L"SAM_BASE";
  v13[6] = L"SECURITY";
  v13[7] = L"SECURITY_BASE";
  v13[8] = L"DEFAULT";
  v13[9] = L"DEFAULTUSER_BASE";
  v7 = (PCWSTR *)v13;
  do
  {
    v8 = (const WCHAR *)pszPathIna;
    if ( pszPathIna[3] > (PCWSTR)7 )
      v8 = pszPathIna[0];
    Vml::CombineFilePath(lpExistingFileName, v8, *v7);
    v9 = (const WCHAR *)lpPathName;
    if ( v15 > 7 )
      v9 = lpPathName[0];
    Vml::CombineFilePath(lpFileName, v9, v7[1]);
    v10 = (const WCHAR *)lpExistingFileName;
    if ( lpExistingFileName[3] > (LPCWSTR)7 )
      v10 = lpExistingFileName[0];
    v11 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v11 = lpFileName[0];
    if ( !CreateHardLinkW(v11, v10, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        v12);
    std::wstring::~wstring(lpFileName);
    std::wstring::~wstring(lpExistingFileName);
    v7 += 2;
  }
  while ( v7 != lpPathName );
  std::wstring::~wstring(pszPathIna);
  std::wstring::~wstring(lpPathName);
  std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x18001c3d0  mov     [rsp-8+arg_8], rbx
0x18001c3d5  push    rbp
0x18001c3d6  lea     rbp, [rsp-20h]
0x18001c3db  sub     rsp, 120h
0x18001c3e2  mov     rax, cs:__security_cookie
0x18001c3e9  xor     rax, rsp
0x18001c3ec  mov     [rbp+20h+var_10], rax
0x18001c3f0  mov     rbx, rcx
0x18001c3f3  lea     r8, aFiles; "Files"
0x18001c3fa  mov     rdx, rcx; pszPathIn
0x18001c3fd  lea     rcx, [rbp+20h+Src]; Src
0x18001c401  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001c406  nop
0x18001c407  lea     r8, aHives; "Hives"
0x18001c40e  mov     rdx, rbx; pszPathIn
0x18001c411  lea     rcx, [rsp+120h+lpPathName]; Src
0x18001c416  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001c41b  nop
0x18001c41c  lea     rcx, [rsp+120h+lpPathName]
0x18001c421  cmp     [rbp+20h+var_98], 7
0x18001c426  cmova   rcx, [rsp+120h+lpPathName]; lpPathName
0x18001c42c  call    ?CreateDirectoryW@Vml@@YAKPEBG@Z; Vml::CreateDirectoryW(ushort const *)
0x18001c431  mov     rcx, [rbp+28h]; this
0x18001c435  test    eax, eax
0x18001c437  jnz     loc_18001C5A6
0x18001c43d  lea     rdx, [rbp+20h+Src]
0x18001c441  cmp     [rbp+20h+var_18], 7
0x18001c446  cmova   rdx, [rbp+20h+Src]; pszPathIn
0x18001c44b  lea     r8, aWindowsSystem3_7; "Windows\\System32\\Config"
0x18001c452  lea     rcx, [rbp+20h+pszPathIn]; Src
0x18001c456  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001c45b  nop
0x18001c45c  lea     rax, aSystem; "SYSTEM"
0x18001c463  mov     [rsp+120h+var_100], rax
0x18001c468  lea     rax, aSystemBase; "SYSTEM_BASE"
0x18001c46f  mov     [rsp+120h+var_F8], rax
0x18001c474  lea     rax, aSoftware; "SOFTWARE"
0x18001c47b  mov     [rsp+120h+var_F0], rax
0x18001c480  lea     rax, aSoftwareBase; "SOFTWARE_BASE"
0x18001c487  mov     [rsp+120h+var_E8], rax
0x18001c48c  lea     rax, aSam; "SAM"
0x18001c493  mov     [rsp+120h+var_E0], rax
0x18001c498  lea     rax, aSamBase; "SAM_BASE"
0x18001c49f  mov     [rsp+120h+var_D8], rax
0x18001c4a4  lea     rax, aSecurity; "SECURITY"
0x18001c4ab  mov     [rsp+120h+var_D0], rax
0x18001c4b0  lea     rax, aSecurityBase; "SECURITY_BASE"
0x18001c4b7  mov     [rsp+120h+var_C8], rax
0x18001c4bc  lea     rax, aDefault; "DEFAULT"
0x18001c4c3  mov     [rsp+120h+var_C0], rax
0x18001c4c8  lea     rax, aDefaultuserBas; "DEFAULTUSER_BASE"
0x18001c4cf  mov     [rsp+120h+var_B8], rax
0x18001c4d4  lea     rbx, [rsp+120h+var_100]
0x18001c4d9  lea     rdx, [rbp+20h+pszPathIn]
0x18001c4dd  cmp     [rbp+20h+var_38], 7
0x18001c4e2  cmova   rdx, [rbp+20h+pszPathIn]; pszPathIn
0x18001c4e7  mov     r8, [rbx]; pszMore
0x18001c4ea  lea     rcx, [rbp+20h+lpExistingFileName]; Src
0x18001c4ee  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001c4f3  nop
0x18001c4f4  lea     rdx, [rsp+120h+lpPathName]
0x18001c4f9  cmp     [rbp+20h+var_98], 7
0x18001c4fe  cmova   rdx, [rsp+120h+lpPathName]; pszPathIn
0x18001c504  mov     r8, [rbx+8]; pszMore
0x18001c508  lea     rcx, [rbp+20h+lpFileName]; Src
0x18001c50c  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001c511  nop
0x18001c512  lea     rdx, [rbp+20h+lpExistingFileName]
0x18001c516  cmp     [rbp+20h+var_58], 7
0x18001c51b  cmova   rdx, [rbp+20h+lpExistingFileName]; lpExistingFileName
0x18001c520  lea     rcx, [rbp+20h+lpFileName]
0x18001c524  cmp     [rbp+20h+var_78], 7
0x18001c529  cmova   rcx, [rbp+20h+lpFileName]; lpFileName
0x18001c52e  xor     r8d, r8d; lpSecurityAttributes
0x18001c531  call    cs:__imp_CreateHardLinkW
0x18001c538  nop     dword ptr [rax+rax+00h]
0x18001c53d  mov     rcx, [rbp+28h]; this
0x18001c541  test    eax, eax
0x18001c543  jz      short loc_18001C5BB
0x18001c545  lea     rcx, [rbp+20h+lpFileName]
0x18001c549  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c54e  nop
0x18001c54f  lea     rcx, [rbp+20h+lpExistingFileName]
0x18001c553  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c558  add     rbx, 10h
0x18001c55c  lea     rax, [rsp+120h+lpPathName]
0x18001c561  cmp     rbx, rax
0x18001c564  jnz     loc_18001C4D9
0x18001c56a  lea     rcx, [rbp+20h+pszPathIn]
0x18001c56e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c573  nop
0x18001c574  lea     rcx, [rsp+120h+lpPathName]
0x18001c579  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c57e  nop
0x18001c57f  lea     rcx, [rbp+20h+Src]
0x18001c583  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c588  mov     rcx, [rbp+20h+var_10]
0x18001c58c  xor     rcx, rsp; StackCookie
0x18001c58f  call    __security_check_cookie
0x18001c594  mov     rbx, [rsp+120h+arg_8]
0x18001c59c  add     rsp, 120h
0x18001c5a3  pop     rbp
0x18001c5a4  retn
0x18001c5a6  mov     r9d, eax; char *
0x18001c5a9  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001c5b0  mov     edx, 0D7h; void *
0x18001c5b5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001c5bb  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001c5c2  mov     edx, 0EDh; void *
0x18001c5c7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
