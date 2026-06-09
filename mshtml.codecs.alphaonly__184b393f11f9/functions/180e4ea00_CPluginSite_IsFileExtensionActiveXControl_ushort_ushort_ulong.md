# CPluginSite::IsFileExtensionActiveXControl(ushort *,ushort *,ulong)

- ea: `0x180e4ea00`
- end: `0x180e4ed33`
- name: `?IsFileExtensionActiveXControl@CPluginSite@@IEAA_NPEAG0K@Z`
- size: `819`
- prototype: `bool __fastcall(CPluginSite *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180e4fad8`

## callees

- `0x1801100c4`
- `0x1802e5024`
- `0x18073d694`
- `0x180839298`
- `0x180e4dc48`
- `0x180e4e934`
- `0x180e4ea00`
- `0x1810c2d60`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180e4ead9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180e4ead9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e4ea9e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e4eb86`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e4ebb5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e4ec58`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e4ea9e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e4eb86`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e4ebb5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e4ec58`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e4ecd6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e4ece6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e4ecf6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e4ed06`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e4ecd6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e4ece6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e4ecf6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e4ed06`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180e4eb31`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180e4ebf9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180e4eb31`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180e4ebf9`

## string_xrefs

- `0x180e4ebae`: `CLSID`
- `0x180e4eca8`: `clsid:`
- `0x180e4ec1d`: `CLSID\<0s>\Control`

## pseudocode

```c
bool __fastcall CPluginSite::IsFileExtensionActiveXControl(
        CPluginSite *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  CPluginSite *v5; // rcx
  unsigned int v6; // edx
  LSTATUS ValueW; // ebx
  unsigned int v8; // r11d
  DWORD cbData[2]; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+60h] [rbp-A8h] BYREF
  HKEY v13; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR Data[264]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 pvData[264]; // [rsp+288h] [rbp+180h] BYREF
  WCHAR SubKey[264]; // [rsp+498h] [rbp+390h] BYREF

  hKey = 0;
  phkResult = 0;
  hkey = 0;
  cbData[0] = 0;
  v13 = 0;
  if ( !a2 )
    return 0;
  Data[0] = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, a2, 0, 0x20019u, &hKey) )
  {
    cbData[0] = 260;
    if ( !RegQueryValueExW(hKey, L"Content Type", 0, 0, (LPBYTE)Data, cbData)
      && !(unsigned int)CPluginSite::ClsidStringFromMime(v5, Data, pvData, 0x104u) )
    {
      goto LABEL_17;
    }
  }
  cbData[0] = 260;
  ValueW = RegGetValueW(hKey, 0, 0, 0x10000006u, 0, Data, cbData);
  if ( !ValueW && cbData[0] )
  {
    if ( 2 * (unsigned __int64)(cbData[0] - 1) >= 0x208 )
      goto LABEL_29;
    Data[cbData[0] - 1] = 0;
    ValueW = RegOpenKeyExW(HKEY_CLASSES_ROOT, Data, 0, 0x20019u, &phkResult);
    if ( !ValueW )
    {
      ValueW = RegOpenKeyExW(phkResult, L"CLSID", 0, 0x20019u, &hkey);
      if ( !ValueW )
      {
        cbData[0] = 260;
        ValueW = RegGetValueW(hkey, 0, 0, 0x10000006u, 0, pvData, cbData);
        if ( !ValueW )
        {
          if ( cbData[0] )
          {
            Format(0, SubKey, 0x104u, L"CLSID\\<0s>\\Control", pvData);
            ValueW = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &v13);
            if ( !ValueW )
            {
              if ( cbData[0] < 2 )
              {
LABEL_17:
                ValueW = GetRawClsidString(pvData, v6);
                if ( !ValueW )
                {
                  ValueW = StringCchCopyW(a3, 0x4Cu, L"clsid:");
                  if ( !ValueW )
                    StringCchCatW(a3, v8, pvData);
                }
                goto LABEL_20;
              }
              if ( 2 * (unsigned __int64)(cbData[0] - 2) < 0x208 )
              {
                pvData[cbData[0] - 2] = 0;
                goto LABEL_17;
              }
LABEL_29:
              _report_rangecheckfailure();
            }
          }
        }
      }
    }
  }
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hkey )
    RegCloseKey(hkey);
  if ( v13 )
    RegCloseKey(v13);
  return ValueW == 0;
}

```

## disassembly

```asm
0x180e4ea00  mov     rax, rsp
0x180e4ea03  mov     [rax+20h], r9d
0x180e4ea07  mov     [rax+18h], r8
0x180e4ea0b  mov     [rax+10h], rdx
0x180e4ea0f  mov     [rax+8], rcx
0x180e4ea13  push    rbp
0x180e4ea14  push    rbx
0x180e4ea15  push    rdi
0x180e4ea16  push    r14
0x180e4ea18  lea     rbp, [rax-5D8h]
0x180e4ea1f  sub     rsp, 6B8h
0x180e4ea26  mov     rax, cs:__security_cookie
0x180e4ea2d  xor     rax, rsp
0x180e4ea30  mov     [rbp+5D0h+var_30], rax
0x180e4ea37  mov     rdx, [rbp+5D0h+lpSubKey]; lpSubKey
0x180e4ea3e  mov     rdi, [rbp+5D0h+arg_10]
0x180e4ea45  mov     [rsp+6D0h+hKey], 0
0x180e4ea4e  mov     [rsp+6D0h+var_680], 0
0x180e4ea57  mov     [rsp+6D0h+hkey], 0
0x180e4ea60  mov     [rsp+6D0h+cbData], 0
0x180e4ea68  mov     [rsp+6D0h+var_670], 0
0x180e4ea71  test    rdx, rdx
0x180e4ea74  jnz     short loc_180E4EA7D
0x180e4ea76  xor     al, al
0x180e4ea78  jmp     loc_180E4ED11
0x180e4ea7d  xor     eax, eax
0x180e4ea7f  mov     r9d, 20019h; samDesired
0x180e4ea85  mov     [rsp+6D0h+Data], ax
0x180e4ea8a  xor     r8d, r8d; ulOptions
0x180e4ea8d  lea     rax, [rsp+6D0h+hKey]
0x180e4ea92  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180e4ea99  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180e4ea9e  call    cs:__imp_RegOpenKeyExW
0x180e4eaa4  mov     r14d, 104h
0x180e4eaaa  test    eax, eax
0x180e4eaac  jnz     short loc_180E4EAFF
0x180e4eaae  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180e4eab3  lea     rax, [rsp+6D0h+cbData]
0x180e4eab8  mov     [rsp+6D0h+lpcbData], rax; lpcbData
0x180e4eabd  lea     rdx, aContentType; "Content Type"
0x180e4eac4  lea     rax, [rsp+6D0h+Data]
0x180e4eac9  mov     [rsp+6D0h+cbData], r14d
0x180e4eace  xor     r9d, r9d; lpType
0x180e4ead1  mov     [rsp+6D0h+phkResult], rax; lpData
0x180e4ead6  xor     r8d, r8d; lpReserved
0x180e4ead9  call    cs:__imp_RegQueryValueExW
0x180e4eadf  test    eax, eax
0x180e4eae1  jnz     short loc_180E4EAFF
0x180e4eae3  mov     r9d, r14d; unsigned int
0x180e4eae6  lea     r8, [rbp+5D0h+pvData]; unsigned __int16 *
0x180e4eaed  lea     rdx, [rsp+6D0h+Data]; unsigned __int16 *
0x180e4eaf2  call    ?ClsidStringFromMime@CPluginSite@@IEAAJPEBGPEAGK@Z; CPluginSite::ClsidStringFromMime(ushort const *,ushort *,ulong)
0x180e4eaf7  test    eax, eax
0x180e4eaf9  jz      loc_180E4EC8C
0x180e4eaff  mov     rcx, [rsp+6D0h+hKey]; hkey
0x180e4eb04  lea     rax, [rsp+6D0h+cbData]
0x180e4eb09  mov     [rsp+30h], rax; pcbData
0x180e4eb0e  mov     r9d, 10000006h; dwFlags
0x180e4eb14  lea     rax, [rsp+6D0h+Data]
0x180e4eb19  mov     [rsp+6D0h+cbData], r14d
0x180e4eb1e  mov     [rsp+6D0h+lpcbData], rax; pvData
0x180e4eb23  xor     r8d, r8d; lpValue
0x180e4eb26  xor     edx, edx; lpSubKey
0x180e4eb28  mov     [rsp+6D0h+phkResult], 0; pdwType
0x180e4eb31  call    cs:__imp_RegGetValueW
0x180e4eb37  mov     ebx, eax
0x180e4eb39  test    eax, eax
0x180e4eb3b  jnz     loc_180E4ECCC
0x180e4eb41  mov     eax, [rsp+6D0h+cbData]
0x180e4eb45  test    eax, eax
0x180e4eb47  jz      loc_180E4ECCC
0x180e4eb4d  lea     ecx, [rax-1]
0x180e4eb50  add     rcx, rcx
0x180e4eb53  cmp     rcx, 208h
0x180e4eb5a  jnb     loc_180E4ED2D
0x180e4eb60  xor     eax, eax
0x180e4eb62  lea     rdx, [rsp+6D0h+Data]; lpSubKey
0x180e4eb67  mov     [rsp+rcx+6D0h+Data], ax
0x180e4eb6c  mov     r9d, 20019h; samDesired
0x180e4eb72  lea     rax, [rsp+6D0h+var_680]
0x180e4eb77  xor     r8d, r8d; ulOptions
0x180e4eb7a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180e4eb81  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180e4eb86  call    cs:__imp_RegOpenKeyExW
0x180e4eb8c  mov     ebx, eax
0x180e4eb8e  test    eax, eax
0x180e4eb90  jnz     loc_180E4ECCC
0x180e4eb96  mov     rcx, [rsp+6D0h+var_680]; hKey
0x180e4eb9b  lea     rax, [rsp+6D0h+hkey]
0x180e4eba0  mov     r9d, 20019h; samDesired
0x180e4eba6  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180e4ebab  xor     r8d, r8d; ulOptions
0x180e4ebae  lea     rdx, aClsid_1; "CLSID"
0x180e4ebb5  call    cs:__imp_RegOpenKeyExW
0x180e4ebbb  mov     ebx, eax
0x180e4ebbd  test    eax, eax
0x180e4ebbf  jnz     loc_180E4ECCC
0x180e4ebc5  mov     rcx, [rsp+6D0h+hkey]; hkey
0x180e4ebca  lea     rax, [rsp+6D0h+cbData]
0x180e4ebcf  mov     [rsp+30h], rax; pcbData
0x180e4ebd4  mov     r9d, 10000006h; dwFlags
0x180e4ebda  lea     rax, [rbp+5D0h+pvData]
0x180e4ebe1  mov     [rsp+6D0h+cbData], r14d
0x180e4ebe6  mov     [rsp+6D0h+lpcbData], rax; pvData
0x180e4ebeb  xor     r8d, r8d; lpValue
0x180e4ebee  xor     edx, edx; lpSubKey
0x180e4ebf0  mov     [rsp+6D0h+phkResult], 0; pdwType
0x180e4ebf9  call    cs:__imp_RegGetValueW
0x180e4ebff  mov     ebx, eax
0x180e4ec01  test    eax, eax
0x180e4ec03  jnz     loc_180E4ECCC
0x180e4ec09  cmp     [rsp+6D0h+cbData], eax
0x180e4ec0d  jz      loc_180E4ECCC
0x180e4ec13  lea     rax, [rbp+5D0h+pvData]
0x180e4ec1a  mov     r8, r14; unsigned __int64
0x180e4ec1d  lea     r9, aClsid0sControl; "CLSID\\<0s>\\Control"
0x180e4ec24  mov     [rsp+6D0h+phkResult], rax
0x180e4ec29  lea     rdx, [rbp+5D0h+SubKey]; unsigned __int16 *
0x180e4ec30  xor     ecx, ecx; unsigned int
0x180e4ec32  call    ?Format@@YAJKPEAG_KPEBGZZ; Format(ulong,ushort *,unsigned __int64,ushort const *,...)
0x180e4ec37  lea     rax, [rsp+6D0h+var_670]
0x180e4ec3c  mov     r9d, 20019h; samDesired
0x180e4ec42  xor     r8d, r8d; ulOptions
0x180e4ec45  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180e4ec4a  lea     rdx, [rbp+5D0h+SubKey]; lpSubKey
0x180e4ec51  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180e4ec58  call    cs:__imp_RegOpenKeyExW
0x180e4ec5e  mov     ebx, eax
0x180e4ec60  test    eax, eax
0x180e4ec62  jnz     short loc_180E4ECCC
0x180e4ec64  mov     eax, [rsp+6D0h+cbData]
0x180e4ec68  cmp     eax, 2
0x180e4ec6b  jb      short loc_180E4EC8C
0x180e4ec6d  add     eax, 0FFFFFFFEh
0x180e4ec70  mov     ecx, eax
0x180e4ec72  add     rcx, rcx
0x180e4ec75  cmp     rcx, 208h
0x180e4ec7c  jnb     loc_180E4ED2D
0x180e4ec82  xor     eax, eax
0x180e4ec84  mov     [rbp+rcx+5D0h+pvData], ax
0x180e4ec8c  lea     rcx, [rbp+5D0h+pvData]; unsigned __int16 *
0x180e4ec93  call    ?GetRawClsidString@@YAJPEAGK@Z; GetRawClsidString(ushort *,ulong)
0x180e4ec98  mov     ebx, eax
0x180e4ec9a  test    eax, eax
0x180e4ec9c  jnz     short loc_180E4ECCC
0x180e4ec9e  lea     r11d, [rax+4Ch]
0x180e4eca2  mov     rcx, rdi; unsigned __int16 *
0x180e4eca5  mov     edx, r11d; unsigned __int64
0x180e4eca8  lea     r8, aClsid_0; "clsid:"
0x180e4ecaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180e4ecb4  mov     ebx, eax
0x180e4ecb6  test    eax, eax
0x180e4ecb8  jnz     short loc_180E4ECCC
0x180e4ecba  lea     r8, [rbp+5D0h+pvData]; unsigned __int16 *
0x180e4ecc1  mov     edx, r11d; unsigned __int64
0x180e4ecc4  mov     rcx, rdi; unsigned __int16 *
0x180e4ecc7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180e4eccc  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180e4ecd1  test    rcx, rcx
0x180e4ecd4  jz      short loc_180E4ECDC
0x180e4ecd6  call    cs:__imp_RegCloseKey
0x180e4ecdc  mov     rcx, [rsp+6D0h+var_680]; hKey
0x180e4ece1  test    rcx, rcx
0x180e4ece4  jz      short loc_180E4ECEC
0x180e4ece6  call    cs:__imp_RegCloseKey
0x180e4ecec  mov     rcx, [rsp+6D0h+hkey]; hKey
0x180e4ecf1  test    rcx, rcx
0x180e4ecf4  jz      short loc_180E4ECFC
0x180e4ecf6  call    cs:__imp_RegCloseKey
0x180e4ecfc  mov     rcx, [rsp+6D0h+var_670]; hKey
0x180e4ed01  test    rcx, rcx
0x180e4ed04  jz      short loc_180E4ED0C
0x180e4ed06  call    cs:__imp_RegCloseKey
0x180e4ed0c  test    ebx, ebx
0x180e4ed0e  setz    al
0x180e4ed11  mov     rcx, [rbp+5D0h+var_30]
0x180e4ed18  xor     rcx, rsp; StackCookie
0x180e4ed1b  call    __security_check_cookie
0x180e4ed20  add     rsp, 6B8h
0x180e4ed27  pop     r14
0x180e4ed29  pop     rdi
0x180e4ed2a  pop     rbx
0x180e4ed2b  pop     rbp
0x180e4ed2c  retn
0x180e4ed2d  call    __report_rangecheckfailure
```
