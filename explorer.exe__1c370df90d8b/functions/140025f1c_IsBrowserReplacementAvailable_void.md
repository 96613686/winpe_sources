# IsBrowserReplacementAvailable(void)

- ea: `0x140025f1c`
- end: `0x140026082`
- name: `?IsBrowserReplacementAvailable@@YA_NXZ`
- size: `358`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x14008964c`

## callees

- `0x140025f1c`
- `0x140026088`
- `0x1400a4a38`
- `0x1401040e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140025f81`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140025f81`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140025f6d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140025f6d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140026028`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140026028`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002603f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002603f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140025faf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140025faf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140025ffd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140025ffd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x140026017`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x140026017`

## string_xrefs

- `0x140025f5f`: `Software\Microsoft\EdgeUpdate\Clients\`

## pseudocode

```c
char __fastcall IsBrowserReplacementAvailable(__int64 a1, __int64 a2)
{
  char v2; // bl
  DWORD FileAttributesW; // eax
  char v4; // di
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF

  v2 = 1;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserReplacement>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_BrowserReplacement>::GetImpl'::`2'::impl,
    a2,
    0);
  _o_wcscpy_s(SubKey, 260, L"Software\\Microsoft\\EdgeUpdate\\Clients\\");
  _o_wcscat_s(SubKey, 260, L"{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}");
  hkey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20219u, &hkey)
    || ((pdwType = 0, pcbData = 520, RegGetValueW(hkey, 0, L"location", 2u, &pdwType, pszPath, &pcbData))
     || PathCchAppend(pszPath, 0x104u, L"msedge.exe")
     || (FileAttributesW = GetFileAttributesW(pszPath), FileAttributesW == -1)
     || (FileAttributesW & 0x10) != 0
      ? (v4 = 0)
      : (v4 = 1),
        RegCloseKey(hkey),
        !v4) )
  {
    if ( !IsPackagedBrowserReplacementFeaturePresent() )
      return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x140025f1c  mov     [rsp-8+arg_0], rbx
0x140025f21  mov     [rsp-8+arg_8], rdi
0x140025f26  push    rbp
0x140025f27  lea     rbp, [rsp-380h]
0x140025f2f  sub     rsp, 480h
0x140025f36  mov     rax, cs:__security_cookie
0x140025f3d  xor     rax, rsp
0x140025f40  mov     [rbp+380h+var_10], rax
0x140025f47  mov     bl, 1
0x140025f49  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BrowserReplacement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserReplacement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserReplacement> `wil::Feature<__WilFeatureTraits_Feature_BrowserReplacement>::GetImpl(void)'::`2'::impl
0x140025f50  mov     dl, bl
0x140025f52  xor     r8d, r8d
0x140025f55  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserReplacement@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserReplacement>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140025f5a  mov     edi, 104h
0x140025f5f  lea     r8, aSoftwareMicros_143; "Software\\Microsoft\\EdgeUpdate\\Client"...
0x140025f66  mov     edx, edi
0x140025f68  lea     rcx, [rsp+480h+SubKey]
0x140025f6d  call    cs:__imp__o_wcscpy_s
0x140025f73  lea     r8, a56eb18f8B0084c; "{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}"
0x140025f7a  mov     edx, edi
0x140025f7c  lea     rcx, [rsp+480h+SubKey]
0x140025f81  call    cs:__imp__o_wcscat_s
0x140025f87  lea     rax, [rsp+480h+hkey]
0x140025f8c  mov     [rsp+480h+hkey], 0
0x140025f95  mov     r9d, 20219h; samDesired
0x140025f9b  mov     [rsp+480h+phkResult], rax; phkResult
0x140025fa0  xor     r8d, r8d; ulOptions
0x140025fa3  lea     rdx, [rsp+480h+SubKey]; lpSubKey
0x140025fa8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140025faf  call    cs:__imp_RegOpenKeyExW
0x140025fb5  test    eax, eax
0x140025fb7  jnz     loc_140026075
0x140025fbd  mov     rcx, [rsp+480h+hkey]; hkey
0x140025fc2  lea     r8, aLocation; "location"
0x140025fc9  mov     [rsp+480h+pdwType], eax
0x140025fcd  mov     r9d, 2; dwFlags
0x140025fd3  lea     rax, [rsp+480h+var_440]
0x140025fd8  mov     [rsp+480h+var_440], 208h
0x140025fe0  mov     [rsp+480h+pcbData], rax; pcbData
0x140025fe5  xor     edx, edx; lpSubKey
0x140025fe7  lea     rax, [rbp+380h+pszPath]
0x140025fee  mov     [rsp+480h+pvData], rax; pvData
0x140025ff3  lea     rax, [rsp+480h+pdwType]
0x140025ff8  mov     [rsp+480h+phkResult], rax; pdwType
0x140025ffd  call    cs:__imp_RegGetValueW
0x140026003  test    eax, eax
0x140026005  jnz     short loc_140026070
0x140026007  lea     r8, pszMore; "msedge.exe"
0x14002600e  mov     edx, edi; cchPath
0x140026010  lea     rcx, [rbp+380h+pszPath]; pszPath
0x140026017  call    cs:__imp_PathCchAppend
0x14002601d  test    eax, eax
0x14002601f  jnz     short loc_140026070
0x140026021  lea     rcx, [rbp+380h+pszPath]; lpFileName
0x140026028  call    cs:__imp_GetFileAttributesW
0x14002602e  cmp     eax, 0FFFFFFFFh
0x140026031  jz      short loc_140026070
0x140026033  test    al, 10h
0x140026035  jnz     short loc_140026070
0x140026037  mov     dil, bl
0x14002603a  mov     rcx, [rsp+480h+hkey]; hKey
0x14002603f  call    cs:__imp_RegCloseKey
0x140026045  test    dil, dil
0x140026048  jz      short loc_140026075
0x14002604a  mov     al, bl
0x14002604c  mov     rcx, [rbp+380h+var_10]
0x140026053  xor     rcx, rsp; StackCookie
0x140026056  call    __security_check_cookie
0x14002605b  lea     r11, [rsp+480h+var_s0]
0x140026063  mov     rbx, [r11+10h]
0x140026067  mov     rdi, [r11+18h]
0x14002606b  mov     rsp, r11
0x14002606e  pop     rbp
0x14002606f  retn
0x140026070  xor     dil, dil
0x140026073  jmp     short loc_14002603A
0x140026075  call    ?IsPackagedBrowserReplacementFeaturePresent@@YA_NXZ; IsPackagedBrowserReplacementFeaturePresent(void)
0x14002607a  test    al, al
0x14002607c  jnz     short loc_14002604A
0x14002607e  xor     bl, bl
0x140026080  jmp     short loc_14002604A
```
