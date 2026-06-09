# CAccountData::_ReadUserLocale(void)

- ea: `0x1800086cc`
- end: `0x1800087ef`
- name: `?_ReadUserLocale@CAccountData@@AEAAXXZ`
- size: `291`
- prototype: `void __fastcall(CAccountData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008184`

## callees

- `0x1800086cc`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x1800086f8`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x1800086f8`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000878e`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000878e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008730`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008730`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000876a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000876a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000877b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000877b`

## pseudocode

```c
void __fastcall CAccountData::_ReadUserLocale(CAccountData *this)
{
  bool v1; // zf
  BOOL v3; // edi
  HKEY v4; // rcx
  const WCHAR *v5; // rcx
  LCID v6; // eax
  int v7; // ecx
  __int64 i; // rdx
  _DWORD *v9; // r8
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v1 = *((_DWORD *)this + 150) == 0;
  *((_DWORD *)this + 151) = 0;
  if ( v1 )
  {
    v3 = GetUserDefaultLocaleName((LPWSTR)this + 215, 85) != 0;
  }
  else
  {
    v4 = (HKEY)*((_QWORD *)this + 77);
    v3 = 0;
    hKey = 0;
    if ( !RegOpenKeyExW(v4, L"Control Panel\\International", 0, 0x20019u, &hKey) )
    {
      cbData = 170;
      LOBYTE(v3) = RegQueryValueExW(hKey, L"LocaleName", 0, 0, (LPBYTE)this + 430, &cbData) == 0;
      RegCloseKey(hKey);
    }
  }
  v5 = (const WCHAR *)((char *)this + 430);
  if ( v3 )
  {
    v6 = LocaleNameToLCID(v5, 0);
    if ( v6 )
    {
      v7 = 0;
      if ( g_localeInfo && *(_QWORD *)g_localeInfo )
      {
        for ( i = 0; (unsigned int)i < g_dwLocaleCount; i = (unsigned int)(i + 1) )
        {
          v9 = (_DWORD *)*((_QWORD *)g_localeInfo + i);
          if ( v9[4] == v6 )
          {
            if ( v9[6] == 1 || v9[5] == 1 )
              v7 = 1;
            break;
          }
        }
      }
      *((_DWORD *)this + 151) = v7;
    }
  }
  else
  {
    *v5 = 0;
  }
}

```

## disassembly

```asm
0x1800086cc  mov     [rsp+arg_10], rbx
0x1800086d1  push    rdi
0x1800086d2  sub     rsp, 30h
0x1800086d6  cmp     dword ptr [rcx+258h], 0
0x1800086dd  mov     rbx, rcx
0x1800086e0  mov     dword ptr [rcx+25Ch], 0
0x1800086ea  jnz     short loc_180008708
0x1800086ec  add     rcx, 1AEh; lpLocaleName
0x1800086f3  mov     edx, 55h ; 'U'; cchLocaleName
0x1800086f8  call    cs:__imp_GetUserDefaultLocaleName
0x1800086fe  xor     edi, edi
0x180008700  test    eax, eax
0x180008702  setnz   dil
0x180008706  jmp     short loc_180008781
0x180008708  mov     rcx, [rcx+268h]; hKey
0x18000870f  lea     rax, [rsp+38h+hKey]
0x180008714  xor     edi, edi
0x180008716  mov     [rsp+38h+phkResult], rax; phkResult
0x18000871b  mov     r9d, 20019h; samDesired
0x180008721  mov     [rsp+38h+hKey], rdi
0x180008726  xor     r8d, r8d; ulOptions
0x180008729  lea     rdx, aControlPanelIn; "Control Panel\\International"
0x180008730  call    cs:__imp_RegOpenKeyExW
0x180008736  test    eax, eax
0x180008738  jnz     short loc_180008781
0x18000873a  lea     rcx, [rsp+38h+cbData]
0x18000873f  mov     [rsp+38h+cbData], 0AAh
0x180008747  mov     [rsp+38h+lpcbData], rcx; lpcbData
0x18000874c  lea     rax, [rbx+1AEh]
0x180008753  mov     rcx, [rsp+38h+hKey]; hKey
0x180008758  lea     rdx, aLocalename; "LocaleName"
0x18000875f  xor     r9d, r9d; lpType
0x180008762  mov     [rsp+38h+phkResult], rax; lpData
0x180008767  xor     r8d, r8d; lpReserved
0x18000876a  call    cs:__imp_RegQueryValueExW
0x180008770  mov     rcx, [rsp+38h+hKey]; hKey
0x180008775  test    eax, eax
0x180008777  setz    dil
0x18000877b  call    cs:__imp_RegCloseKey
0x180008781  lea     rcx, [rbx+1AEh]; lpName
0x180008788  test    edi, edi
0x18000878a  jz      short loc_1800087DF
0x18000878c  xor     edx, edx; dwFlags
0x18000878e  call    cs:__imp_LocaleNameToLCID
0x180008794  test    eax, eax
0x180008796  jz      short loc_1800087E4
0x180008798  mov     r9, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18000879f  xor     ecx, ecx
0x1800087a1  test    r9, r9
0x1800087a4  jz      short loc_1800087D7
0x1800087a6  cmp     [r9], rcx
0x1800087a9  jz      short loc_1800087D7
0x1800087ab  xor     edx, edx
0x1800087ad  lea     r11d, [rcx+1]
0x1800087b1  cmp     edx, cs:?g_dwLocaleCount@@3KA; ulong g_dwLocaleCount
0x1800087b7  jnb     short loc_1800087D7
0x1800087b9  mov     r8, [r9+rdx*8]
0x1800087bd  cmp     [r8+10h], eax
0x1800087c1  jz      short loc_1800087C8
0x1800087c3  add     edx, r11d
0x1800087c6  jmp     short loc_1800087B1
0x1800087c8  cmp     [r8+18h], r11d
0x1800087cc  jz      short loc_1800087D4
0x1800087ce  cmp     [r8+14h], r11d
0x1800087d2  jnz     short loc_1800087D7
0x1800087d4  mov     ecx, r11d
0x1800087d7  mov     [rbx+25Ch], ecx
0x1800087dd  jmp     short loc_1800087E4
0x1800087df  xor     eax, eax
0x1800087e1  mov     [rcx], ax
0x1800087e4  mov     rbx, [rsp+38h+arg_10]
0x1800087e9  add     rsp, 30h
0x1800087ed  pop     rdi
0x1800087ee  retn
```
