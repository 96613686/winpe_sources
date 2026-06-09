# IsBrowserReplacementAvailable(void)

- ea: `0x140013604`
- end: `0x140013795`
- name: `?IsBrowserReplacementAvailable@@YA_NXZ`
- size: `401`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400123b0`

## callees

- `0x140013604`
- `0x14001379c`
- `0x1400aab1c`
- `0x14010e160`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001366f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001366f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140013655`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140013655`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001372e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001372e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400136a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400136a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001374b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001374b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400136f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400136f7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x140013717`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x140013717`

## string_xrefs

- `0x140013647`: `Software\Microsoft\EdgeUpdate\Clients\`

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
0x140013604  mov     [rsp-8+arg_0], rbx
0x140013609  mov     [rsp-8+arg_8], rdi
0x14001360e  push    rbp
0x14001360f  lea     rbp, [rsp-380h]
0x140013617  sub     rsp, 480h
0x14001361e  mov     rax, cs:__security_cookie
0x140013625  xor     rax, rsp
0x140013628  mov     [rbp+380h+var_10], rax
0x14001362f  mov     bl, 1
0x140013631  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BrowserReplacement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserReplacement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserReplacement> `wil::Feature<__WilFeatureTraits_Feature_BrowserReplacement>::GetImpl(void)'::`2'::impl
0x140013638  mov     dl, bl
0x14001363a  xor     r8d, r8d
0x14001363d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserReplacement@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserReplacement>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140013642  mov     edi, 104h
0x140013647  lea     r8, aSoftwareMicros_144; "Software\\Microsoft\\EdgeUpdate\\Client"...
0x14001364e  mov     edx, edi
0x140013650  lea     rcx, [rsp+480h+SubKey]
0x140013655  call    cs:__imp__o_wcscpy_s
0x14001365c  nop     dword ptr [rax+rax+00h]
0x140013661  lea     r8, a56eb18f8B0084c; "{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}"
0x140013668  mov     edx, edi
0x14001366a  lea     rcx, [rsp+480h+SubKey]
0x14001366f  call    cs:__imp__o_wcscat_s
0x140013676  nop     dword ptr [rax+rax+00h]
0x14001367b  lea     rax, [rsp+480h+hkey]
0x140013680  mov     [rsp+480h+hkey], 0
0x140013689  mov     r9d, 20219h; samDesired
0x14001368f  mov     [rsp+480h+phkResult], rax; phkResult
0x140013694  xor     r8d, r8d; ulOptions
0x140013697  lea     rdx, [rsp+480h+SubKey]; lpSubKey
0x14001369c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400136a3  call    cs:__imp_RegOpenKeyExW
0x1400136aa  nop     dword ptr [rax+rax+00h]
0x1400136af  test    eax, eax
0x1400136b1  jnz     loc_140013788
0x1400136b7  mov     rcx, [rsp+480h+hkey]; hkey
0x1400136bc  lea     r8, aLocation; "location"
0x1400136c3  mov     [rsp+480h+pdwType], eax
0x1400136c7  mov     r9d, 2; dwFlags
0x1400136cd  lea     rax, [rsp+480h+var_440]
0x1400136d2  mov     [rsp+480h+var_440], 208h
0x1400136da  mov     [rsp+480h+pcbData], rax; pcbData
0x1400136df  xor     edx, edx; lpSubKey
0x1400136e1  lea     rax, [rbp+380h+pszPath]
0x1400136e8  mov     [rsp+480h+pvData], rax; pvData
0x1400136ed  lea     rax, [rsp+480h+pdwType]
0x1400136f2  mov     [rsp+480h+phkResult], rax; pdwType
0x1400136f7  call    cs:__imp_RegGetValueW
0x1400136fe  nop     dword ptr [rax+rax+00h]
0x140013703  test    eax, eax
0x140013705  jnz     short loc_140013783
0x140013707  lea     r8, pszMore; "msedge.exe"
0x14001370e  mov     edx, edi; cchPath
0x140013710  lea     rcx, [rbp+380h+pszPath]; pszPath
0x140013717  call    cs:__imp_PathCchAppend
0x14001371e  nop     dword ptr [rax+rax+00h]
0x140013723  test    eax, eax
0x140013725  jnz     short loc_140013783
0x140013727  lea     rcx, [rbp+380h+pszPath]; lpFileName
0x14001372e  call    cs:__imp_GetFileAttributesW
0x140013735  nop     dword ptr [rax+rax+00h]
0x14001373a  cmp     eax, 0FFFFFFFFh
0x14001373d  jz      short loc_140013783
0x14001373f  test    al, 10h
0x140013741  jnz     short loc_140013783
0x140013743  mov     dil, bl
0x140013746  mov     rcx, [rsp+480h+hkey]; hKey
0x14001374b  call    cs:__imp_RegCloseKey
0x140013752  nop     dword ptr [rax+rax+00h]
0x140013757  test    dil, dil
0x14001375a  jz      short loc_140013788
0x14001375c  mov     al, bl
0x14001375e  mov     rcx, [rbp+380h+var_10]
0x140013765  xor     rcx, rsp; StackCookie
0x140013768  call    __security_check_cookie
0x14001376d  lea     r11, [rsp+480h+var_s0]
0x140013775  mov     rbx, [r11+10h]
0x140013779  mov     rdi, [r11+18h]
0x14001377d  mov     rsp, r11
0x140013780  pop     rbp
0x140013781  retn
0x140013783  xor     dil, dil
0x140013786  jmp     short loc_140013746
0x140013788  call    ?IsPackagedBrowserReplacementFeaturePresent@@YA_NXZ; IsPackagedBrowserReplacementFeaturePresent(void)
0x14001378d  test    al, al
0x14001378f  jnz     short loc_14001375C
0x140013791  xor     bl, bl
0x140013793  jmp     short loc_14001375C
```
