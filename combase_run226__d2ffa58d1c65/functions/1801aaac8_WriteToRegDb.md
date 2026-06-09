# WriteToRegDb

- ea: `0x1801aaac8`
- end: `0x1801aae18`
- name: `WriteToRegDb`
- size: `848`
- prototype: `__int64 __fastcall(const wchar_t *szOle1, const BYTE *szClsid, int fPerUser)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004d180`
- `0x1801aaa1c`

## callees

- `0x18003d5d4`
- `0x180040078`
- `0x18004d348`
- `0x180179024`
- `0x18018e9ec`
- `0x1801999b0`
- `0x1801aaac8`
- `0x1802135ad`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801aabbc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801aad25`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801aabbc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801aad25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aabda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aac95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aada0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aadaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aadc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aadd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aade3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aabda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aac95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aada0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aadaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aadc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aadd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801aade3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801aab78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801aab78`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801aad57`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801aad57`

## string_xrefs

- `0x1801aac35`: `onecore\com\combase\classregcommon\ole1guid.cxx`
- `0x1801aace5`: `onecore\com\combase\classregcommon\ole1guid.cxx`
- `0x1801aacab`: `CLSID\%s`

## pseudocode

```c
__int64 __fastcall WriteToRegDb(const wchar_t *szOle1, const BYTE *szClsid, int fPerUser)
{
  int v6; // eax
  HKEY__ *v7; // rcx
  LSTATUS v8; // eax
  unsigned int v9; // r8d
  int v10; // eax
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rax
  unsigned int v13; // r8d
  int v14; // edi
  unsigned int v15; // r8d
  unsigned int v16; // ebx
  unsigned int v17; // r8d
  HKEY__ *hkeyWrite; // [rsp+50h] [rbp-B0h] BYREF
  HKEY__ *hkeyRead; // [rsp+58h] [rbp-A8h] BYREF
  HKEY__ *hkeyWriteRoot; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  unsigned int cbUserName; // [rsp+6Ch] [rbp-94h] BYREF
  wchar_t szKey[256]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t szUserName[256]; // [rsp+270h] [rbp+170h] BYREF
  void *retaddr; // [rsp+4A8h] [rbp+3A8h]

  cbUserName = 512;
  hkeyRead = 0;
  hkeyWriteRoot = 0;
  hkeyWrite = 0;
  v6 = OpenClassesRootKeyExW(szOle1, 0x2000000u, &hkeyRead);
  v7 = hkeyRead;
  if ( v6 )
    goto LABEL_30;
  if ( wRegQueryValue(hkeyRead, 0, szUserName, &cbUserName) )
    goto LABEL_29;
  if ( fPerUser )
  {
    if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Classes", 0, 0x2000000u, &hkeyWriteRoot) )
      goto LABEL_29;
    dwDisposition = 0;
    v8 = RegCreateKeyExW(hkeyWriteRoot, szOle1, 0, 0, 0, 0x2000000u, 0, &hkeyWrite, &dwDisposition);
    v7 = hkeyRead;
    if ( v8 || dwDisposition == 1 )
      goto LABEL_30;
    if ( RegCloseKey(hkeyRead) )
      goto LABEL_29;
    v7 = hkeyWrite;
  }
  else
  {
    v10 = OpenClassesRootKeyExW(0, 0x2000000u, &hkeyWriteRoot);
    v7 = hkeyRead;
    if ( v10 )
    {
LABEL_30:
      if ( v7 )
        RegCloseKey(v7);
      if ( hkeyWriteRoot )
        RegCloseKey(hkeyWriteRoot);
      if ( hkeyWrite )
        RegCloseKey(hkeyWrite);
      return 2147746129LL;
    }
    hkeyWrite = hkeyRead;
  }
  v11 = -1;
  hkeyRead = 0;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)&szClsid[2 * v12] );
  if ( v12 > 0x7FFFFFFF )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0xA1u, "onecore\\com\\combase\\classregcommon\\ole1guid.cxx");
  if ( wRegSetValue(v7, Com::Catalog::Constants::CLSID, v9, szClsid, v12 + 1) )
    goto LABEL_29;
  if ( !wcscmp_0((const wchar_t *)szClsid, L"{00030003-0000-0000-C000-000000000046}") )
    wRegSetValue(hkeyWrite, L"PackageOnFileDrop", v13, 0, 0);
  if ( RegCloseKey(hkeyWrite) )
    goto LABEL_29;
  hkeyWrite = 0;
  v14 = StringCchPrintfW(szKey, 0x100u, L"CLSID\\%s", szClsid);
  if ( v14 < 0 )
    return 2147746129LL;
  do
    ++v11;
  while ( szOle1[v11] );
  if ( v11 > 0x7FFFFFFF )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0xB8u, "onecore\\com\\combase\\classregcommon\\ole1guid.cxx");
  if ( RegCreateKeyExW(hkeyWriteRoot, szKey, 0, 0, 0, 0x2000000u, 0, &hkeyWrite, 0)
    || RegSetValueExW(hkeyWrite, 0, 0, 1u, (const BYTE *)szUserName, cbUserName)
    || (v16 = v11 + 1, wRegSetValue(hkeyWrite, L"Ole1Class", v15, (const BYTE *)szOle1, v16))
    || wRegSetValue(hkeyWrite, Com::Catalog::Constants::ProgID, v17, (const BYTE *)szOle1, v16)
    || RegCloseKey(hkeyWrite)
    || RegCloseKey(hkeyWriteRoot) )
  {
LABEL_29:
    v7 = hkeyRead;
    goto LABEL_30;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1801aaac8  mov     [rsp-8+arg_10], rbx
0x1801aaacd  push    rbp
0x1801aaace  push    rsi
0x1801aaacf  push    rdi
0x1801aaad0  push    r12
0x1801aaad2  push    r14
0x1801aaad4  lea     rbp, [rsp-380h]
0x1801aaadc  sub     rsp, 480h
0x1801aaae3  mov     rax, cs:__security_cookie
0x1801aaaea  xor     rax, rsp
0x1801aaaed  mov     [rbp+3A0h+var_30], rax
0x1801aaaf4  xor     r14d, r14d
0x1801aaaf7  mov     [rsp+4A0h+cbUserName], 200h
0x1801aaaff  mov     ebx, fPerUser
0x1801aab02  mov     [rsp+4A0h+hkeyRead], r14
0x1801aab07  mov     rdi, szClsid
0x1801aab0a  mov     [rsp+4A0h+hkeyWriteRoot], r14
0x1801aab0f  mov     r12d, 2000000h
0x1801aab15  mov     [rsp+4A0h+hkeyWrite], r14
0x1801aab1a  mov     edx, r12d; samDesired
0x1801aab1d  lea     r8, [rsp+4A0h+hkeyRead]; phkResult
0x1801aab22  mov     rsi, szOle1
0x1801aab25  call    OpenClassesRootKeyExW
0x1801aab2a  mov     szOle1, [rsp+4A0h+hkeyRead]; hKey
0x1801aab2f  test    eax, eax
0x1801aab31  jnz     loc_1801AADBE
0x1801aab37  lea     r9, [rsp+4A0h+cbUserName]; lpdwSize
0x1801aab3c  xor     edx, edx; lpSubKey
0x1801aab3e  lea     r8, [rbp+3A0h+szUserName]; lpValue
0x1801aab45  call    wRegQueryValue
0x1801aab4a  test    eax, eax
0x1801aab4c  jnz     loc_1801AADB9
0x1801aab52  test    ebx, ebx
0x1801aab54  jz      loc_1801AABEF
0x1801aab5a  lea     rax, [rsp+4A0h+hkeyWriteRoot]
0x1801aab5f  mov     r9d, r12d; samDesired
0x1801aab62  xor     fPerUser, fPerUser; ulOptions
0x1801aab65  mov     [rsp+4A0h+phkResult], rax; phkResult
0x1801aab6a  lea     szClsid, aSoftwareClasse_1; "Software\\Classes"
0x1801aab71  mov     szOle1, 0FFFFFFFF80000001h; hKey
0x1801aab78  call    cs:__imp_RegOpenKeyExW
0x1801aab7e  test    eax, eax
0x1801aab80  jnz     loc_1801AADB9
0x1801aab86  mov     szOle1, [rsp+4A0h+hkeyWriteRoot]; hKey
0x1801aab8b  lea     rax, [rsp+4A0h+dwDisposition]
0x1801aab90  mov     [rsp+4A0h+lpdwDisposition], rax; lpdwDisposition
0x1801aab95  xor     r9d, r9d; lpClass
0x1801aab98  lea     rax, [rsp+4A0h+hkeyWrite]
0x1801aab9d  mov     [rsp+4A0h+dwDisposition], r14d
0x1801aaba2  mov     [rsp+4A0h+var_468], rax; phkResult
0x1801aaba7  xor     fPerUser, fPerUser; Reserved
0x1801aabaa  mov     [rsp+4A0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1801aabaf  mov     szClsid, rsi; lpSubKey
0x1801aabb2  mov     [rsp+4A0h+samDesired], r12d; samDesired
0x1801aabb7  mov     dword ptr [rsp+4A0h+phkResult], r14d; dwOptions
0x1801aabbc  call    cs:__imp_RegCreateKeyExW
0x1801aabc2  mov     szOle1, [rsp+4A0h+hkeyRead]; hKey
0x1801aabc7  test    eax, eax
0x1801aabc9  jnz     loc_1801AADBE
0x1801aabcf  cmp     [rsp+4A0h+dwDisposition], 1
0x1801aabd4  jz      loc_1801AADBE
0x1801aabda  call    cs:__imp_RegCloseKey
0x1801aabe0  test    eax, eax
0x1801aabe2  jnz     loc_1801AADB9
0x1801aabe8  mov     szOle1, [rsp+4A0h+hkeyWrite]
0x1801aabed  jmp     short loc_1801AAC10
0x1801aabef  lea     r8, [rsp+4A0h+hkeyWriteRoot]; phkResult
0x1801aabf4  mov     edx, r12d; samDesired
0x1801aabf7  xor     ecx, ecx; pszSubKey
0x1801aabf9  call    OpenClassesRootKeyExW
0x1801aabfe  mov     szOle1, [rsp+4A0h+hkeyRead]; hKey
0x1801aac03  test    eax, eax
0x1801aac05  jnz     loc_1801AADBE
0x1801aac0b  mov     [rsp+4A0h+hkeyWrite], szOle1
0x1801aac10  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801aac14  mov     [rsp+4A0h+hkeyRead], r14
0x1801aac19  mov     rax, rbx
0x1801aac1c  inc     rax
0x1801aac1f  cmp     [rdi+rax*2], r14w
0x1801aac24  jnz     short loc_1801AAC1C
0x1801aac26  cmp     rax, 7FFFFFFFh
0x1801aac2c  jbe     short loc_1801AAC47
0x1801aac2e  mov     szOle1, [rbp+3A8h]; callerReturnAddress
0x1801aac35  lea     r8, aOnecoreComComb_165; "onecore\\com\\combase\\classregcommon\\"...
0x1801aac3c  mov     edx, 0A1h; lineNumber
0x1801aac41  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1801aac47  inc     eax
0x1801aac49  lea     szClsid, ?CLSID@Constants@Catalog@Com@@3QBGB; lpSubKey
0x1801aac50  mov     r9, rdi; cchData
0x1801aac53  mov     dword ptr [rsp+4A0h+phkResult], eax; hKey
0x1801aac57  call    wRegSetValue
0x1801aac5c  test    eax, eax
0x1801aac5e  jnz     loc_1801AADB9
0x1801aac64  lea     szClsid, a00030003000000; "{00030003-0000-0000-C000-000000000046}"
0x1801aac6b  mov     szOle1, rdi; String1
0x1801aac6e  call    wcscmp_0
0x1801aac73  test    eax, eax
0x1801aac75  jnz     short loc_1801AAC90
0x1801aac77  mov     szOle1, [rsp+4A0h+hkeyWrite]; hKey
0x1801aac7c  lea     szClsid, aPackageonfiled; "PackageOnFileDrop"
0x1801aac83  xor     r9d, r9d; cchData
0x1801aac86  mov     dword ptr [rsp+4A0h+phkResult], r14d; hKey
0x1801aac8b  call    wRegSetValue
0x1801aac90  mov     szOle1, [rsp+4A0h+hkeyWrite]; hKey
0x1801aac95  call    cs:__imp_RegCloseKey
0x1801aac9b  test    eax, eax
0x1801aac9d  jnz     loc_1801AADB9
0x1801aaca3  mov     r9, rdi
0x1801aaca6  mov     [rsp+4A0h+hkeyWrite], r14
0x1801aacab  lea     r8, aClsidS; "CLSID\\%s"
0x1801aacb2  mov     edx, 100h; cchDest
0x1801aacb7  lea     szOle1, [rsp+4A0h+szKey]; pszDest
0x1801aacbc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801aacc1  mov     edi, eax
0x1801aacc3  test    eax, eax
0x1801aacc5  js      loc_1801AADE9
0x1801aaccb  inc     rbx
0x1801aacce  cmp     [rsi+rbx*2], r14w
0x1801aacd3  jnz     short loc_1801AACCB
0x1801aacd5  cmp     rbx, 7FFFFFFFh
0x1801aacdc  jbe     short loc_1801AACF7
0x1801aacde  mov     szOle1, [rbp+3A8h]; callerReturnAddress
0x1801aace5  lea     r8, aOnecoreComComb_165; "onecore\\com\\combase\\classregcommon\\"...
0x1801aacec  mov     edx, 0B8h; lineNumber
0x1801aacf1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1801aacf7  mov     szOle1, [rsp+4A0h+hkeyWriteRoot]; hKey
0x1801aacfc  lea     rax, [rsp+4A0h+hkeyWrite]
0x1801aad01  mov     [rsp+4A0h+lpdwDisposition], r14; lpdwDisposition
0x1801aad06  lea     szClsid, [rsp+4A0h+szKey]; lpSubKey
0x1801aad0b  mov     [rsp+4A0h+var_468], rax; phkResult
0x1801aad10  xor     r9d, r9d; lpClass
0x1801aad13  mov     [rsp+4A0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1801aad18  xor     fPerUser, fPerUser; Reserved
0x1801aad1b  mov     [rsp+4A0h+samDesired], r12d; samDesired
0x1801aad20  mov     dword ptr [rsp+4A0h+phkResult], r14d; dwOptions
0x1801aad25  call    cs:__imp_RegCreateKeyExW
0x1801aad2b  test    eax, eax
0x1801aad2d  jnz     loc_1801AADB9
0x1801aad33  mov     eax, [rsp+4A0h+cbUserName]
0x1801aad37  mov     r9d, 1; dwType
0x1801aad3d  mov     szOle1, [rsp+4A0h+hkeyWrite]; hKey
0x1801aad42  xor     fPerUser, fPerUser; Reserved
0x1801aad45  mov     [rsp+4A0h+samDesired], eax; cbData
0x1801aad49  xor     edx, edx; lpValueName
0x1801aad4b  lea     rax, [rbp+3A0h+szUserName]
0x1801aad52  mov     [rsp+4A0h+phkResult], rax; lpData
0x1801aad57  call    cs:__imp_RegSetValueExW
0x1801aad5d  test    eax, eax
0x1801aad5f  jnz     short loc_1801AADB9
0x1801aad61  mov     szOle1, [rsp+4A0h+hkeyWrite]; hKey
0x1801aad66  lea     szClsid, aOle1class; "Ole1Class"
0x1801aad6d  inc     ebx
0x1801aad6f  mov     r9, rsi; cchData
0x1801aad72  mov     dword ptr [rsp+4A0h+phkResult], ebx; hKey
0x1801aad76  call    wRegSetValue
0x1801aad7b  test    eax, eax
0x1801aad7d  jnz     short loc_1801AADB9
0x1801aad7f  mov     szOle1, [rsp+4A0h+hkeyWrite]; hKey
0x1801aad84  lea     szClsid, ?ProgID@Constants@Catalog@Com@@3QBGB; lpSubKey
0x1801aad8b  mov     r9, rsi; cchData
0x1801aad8e  mov     dword ptr [rsp+4A0h+phkResult], ebx; hKey
0x1801aad92  call    wRegSetValue
0x1801aad97  test    eax, eax
0x1801aad99  jnz     short loc_1801AADB9
0x1801aad9b  mov     szOle1, [rsp+4A0h+hkeyWrite]; hKey
0x1801aada0  call    cs:__imp_RegCloseKey
0x1801aada6  test    eax, eax
0x1801aada8  jnz     short loc_1801AADB9
0x1801aadaa  mov     szOle1, [rsp+4A0h+hkeyWriteRoot]; hKey
0x1801aadaf  call    cs:__imp_RegCloseKey
0x1801aadb5  test    eax, eax
0x1801aadb7  jz      short loc_1801AAE14
0x1801aadb9  mov     szOle1, [rsp+4A0h+hkeyRead]; hKey
0x1801aadbe  test    szOle1, szOle1
0x1801aadc1  jz      short loc_1801AADC9
0x1801aadc3  call    cs:__imp_RegCloseKey
0x1801aadc9  mov     szOle1, [rsp+4A0h+hkeyWriteRoot]; hKey
0x1801aadce  test    szOle1, szOle1
0x1801aadd1  jz      short loc_1801AADD9
0x1801aadd3  call    cs:__imp_RegCloseKey
0x1801aadd9  mov     szOle1, [rsp+4A0h+hkeyWrite]; hKey
0x1801aadde  test    szOle1, szOle1
0x1801aade1  jz      short loc_1801AADE9
0x1801aade3  call    cs:__imp_RegCloseKey
0x1801aade9  mov     eax, 80040151h
0x1801aadee  mov     szOle1, [rbp+3A0h+var_30]
0x1801aadf5  xor     szOle1, rsp; StackCookie
0x1801aadf8  call    __security_check_cookie
0x1801aadfd  mov     rbx, [rsp+4A0h+arg_10]
0x1801aae05  add     rsp, 480h
0x1801aae0c  pop     r14
0x1801aae0e  pop     r12
0x1801aae10  pop     rdi
0x1801aae11  pop     rsi
0x1801aae12  pop     rbp
0x1801aae13  retn
0x1801aae14  mov     eax, edi
0x1801aae16  jmp     short loc_1801AADEE
```
