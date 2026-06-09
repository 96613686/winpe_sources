# CPluginSite::IsFileExtensionActiveXControl(ushort *,ushort *,ulong)

- ea: `0x180e742c0`
- end: `0x180e74636`
- name: `?IsFileExtensionActiveXControl@CPluginSite@@IEAA_NPEAG0K@Z`
- size: `886`
- prototype: `bool __fastcall(CPluginSite *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180e75688`

## callees

- `0x18040ac58`
- `0x18042d198`
- `0x180745a1c`
- `0x18083bda8`
- `0x180e732ac`
- `0x180e741ec`
- `0x180e742c0`
- `0x1810f65c0`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180e7439f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180e7439f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e7435e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e74458`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e7448d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e7453c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e7435e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e74458`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e7448d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180e7453c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e745c0`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e745d6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e745ec`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e74602`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e745c0`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e745d6`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e745ec`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180e74602`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180e743fd`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180e744d7`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180e743fd`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180e744d7`

## string_xrefs

- `0x180e74486`: `CLSID`
- `0x180e74592`: `clsid:`
- `0x180e74501`: `CLSID\<0s>\Control`

## pseudocode

```c
bool __fastcall CPluginSite::IsFileExtensionActiveXControl(
        CPluginSite *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  CPluginSite *v5; // rcx
  unsigned int v6; // edx
  int ValueW; // ebx
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
            Format(0, SubKey, 260, L"CLSID\\<0s>\\Control", pvData);
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
0x180e742c0  mov     rax, rsp
0x180e742c3  mov     [rax+20h], r9d
0x180e742c7  mov     [rax+18h], r8
0x180e742cb  mov     [rax+10h], rdx
0x180e742cf  mov     [rax+8], rcx
0x180e742d3  push    rbp
0x180e742d4  push    rbx
0x180e742d5  push    rdi
0x180e742d6  push    r14
0x180e742d8  lea     rbp, [rax-5D8h]
0x180e742df  sub     rsp, 6B8h
0x180e742e6  mov     rax, cs:__security_cookie
0x180e742ed  xor     rax, rsp
0x180e742f0  mov     [rbp+5D0h+var_30], rax
0x180e742f7  mov     rdx, [rbp+5D0h+lpSubKey]; lpSubKey
0x180e742fe  mov     rdi, [rbp+5D0h+arg_10]
0x180e74305  mov     [rsp+6D0h+hKey], 0
0x180e7430e  mov     [rsp+6D0h+var_680], 0
0x180e74317  mov     [rsp+6D0h+hkey], 0
0x180e74320  mov     [rsp+6D0h+cbData], 0
0x180e74328  mov     [rsp+6D0h+var_670], 0
0x180e74331  test    rdx, rdx
0x180e74334  jnz     short loc_180E7433D
0x180e74336  xor     al, al
0x180e74338  jmp     loc_180E74613
0x180e7433d  xor     eax, eax
0x180e7433f  mov     r9d, 20019h; samDesired
0x180e74345  mov     [rsp+6D0h+Data], ax
0x180e7434a  xor     r8d, r8d; ulOptions
0x180e7434d  lea     rax, [rsp+6D0h+hKey]
0x180e74352  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180e74359  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180e7435e  call    cs:__imp_RegOpenKeyExW
0x180e74365  nop     dword ptr [rax+rax+00h]
0x180e7436a  mov     r14d, 104h
0x180e74370  test    eax, eax
0x180e74372  jnz     short loc_180E743CB
0x180e74374  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180e74379  lea     rax, [rsp+6D0h+cbData]
0x180e7437e  mov     [rsp+6D0h+lpcbData], rax; lpcbData
0x180e74383  lea     rdx, aContentType; "Content Type"
0x180e7438a  lea     rax, [rsp+6D0h+Data]
0x180e7438f  mov     [rsp+6D0h+cbData], r14d
0x180e74394  xor     r9d, r9d; lpType
0x180e74397  mov     [rsp+6D0h+phkResult], rax; lpData
0x180e7439c  xor     r8d, r8d; lpReserved
0x180e7439f  call    cs:__imp_RegQueryValueExW
0x180e743a6  nop     dword ptr [rax+rax+00h]
0x180e743ab  test    eax, eax
0x180e743ad  jnz     short loc_180E743CB
0x180e743af  mov     r9d, r14d; unsigned int
0x180e743b2  lea     r8, [rbp+5D0h+pvData]; unsigned __int16 *
0x180e743b9  lea     rdx, [rsp+6D0h+Data]; unsigned __int16 *
0x180e743be  call    ?ClsidStringFromMime@CPluginSite@@IEAAJPEBGPEAGK@Z; CPluginSite::ClsidStringFromMime(ushort const *,ushort *,ulong)
0x180e743c3  test    eax, eax
0x180e743c5  jz      loc_180E74576
0x180e743cb  mov     rcx, [rsp+6D0h+hKey]; hkey
0x180e743d0  lea     rax, [rsp+6D0h+cbData]
0x180e743d5  mov     [rsp+30h], rax; pcbData
0x180e743da  mov     r9d, 10000006h; dwFlags
0x180e743e0  lea     rax, [rsp+6D0h+Data]
0x180e743e5  mov     [rsp+6D0h+cbData], r14d
0x180e743ea  mov     [rsp+6D0h+lpcbData], rax; pvData
0x180e743ef  xor     r8d, r8d; lpValue
0x180e743f2  xor     edx, edx; lpSubKey
0x180e743f4  mov     [rsp+6D0h+phkResult], 0; pdwType
0x180e743fd  call    cs:__imp_RegGetValueW
0x180e74404  nop     dword ptr [rax+rax+00h]
0x180e74409  mov     ebx, eax
0x180e7440b  test    eax, eax
0x180e7440d  jnz     loc_180E745B6
0x180e74413  mov     eax, [rsp+6D0h+cbData]
0x180e74417  test    eax, eax
0x180e74419  jz      loc_180E745B6
0x180e7441f  lea     ecx, [rax-1]
0x180e74422  add     rcx, rcx
0x180e74425  cmp     rcx, 208h
0x180e7442c  jnb     loc_180E74630
0x180e74432  xor     eax, eax
0x180e74434  lea     rdx, [rsp+6D0h+Data]; lpSubKey
0x180e74439  mov     [rsp+rcx+6D0h+Data], ax
0x180e7443e  mov     r9d, 20019h; samDesired
0x180e74444  lea     rax, [rsp+6D0h+var_680]
0x180e74449  xor     r8d, r8d; ulOptions
0x180e7444c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180e74453  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180e74458  call    cs:__imp_RegOpenKeyExW
0x180e7445f  nop     dword ptr [rax+rax+00h]
0x180e74464  mov     ebx, eax
0x180e74466  test    eax, eax
0x180e74468  jnz     loc_180E745B6
0x180e7446e  mov     rcx, [rsp+6D0h+var_680]; hKey
0x180e74473  lea     rax, [rsp+6D0h+hkey]
0x180e74478  mov     r9d, 20019h; samDesired
0x180e7447e  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180e74483  xor     r8d, r8d; ulOptions
0x180e74486  lea     rdx, aClsid_1; "CLSID"
0x180e7448d  call    cs:__imp_RegOpenKeyExW
0x180e74494  nop     dword ptr [rax+rax+00h]
0x180e74499  mov     ebx, eax
0x180e7449b  test    eax, eax
0x180e7449d  jnz     loc_180E745B6
0x180e744a3  mov     rcx, [rsp+6D0h+hkey]; hkey
0x180e744a8  lea     rax, [rsp+6D0h+cbData]
0x180e744ad  mov     [rsp+30h], rax; pcbData
0x180e744b2  mov     r9d, 10000006h; dwFlags
0x180e744b8  lea     rax, [rbp+5D0h+pvData]
0x180e744bf  mov     [rsp+6D0h+cbData], r14d
0x180e744c4  mov     [rsp+6D0h+lpcbData], rax; pvData
0x180e744c9  xor     r8d, r8d; lpValue
0x180e744cc  xor     edx, edx; lpSubKey
0x180e744ce  mov     [rsp+6D0h+phkResult], 0; pdwType
0x180e744d7  call    cs:__imp_RegGetValueW
0x180e744de  nop     dword ptr [rax+rax+00h]
0x180e744e3  mov     ebx, eax
0x180e744e5  test    eax, eax
0x180e744e7  jnz     loc_180E745B6
0x180e744ed  cmp     [rsp+6D0h+cbData], eax
0x180e744f1  jz      loc_180E745B6
0x180e744f7  lea     rax, [rbp+5D0h+pvData]
0x180e744fe  mov     r8, r14; unsigned __int64
0x180e74501  lea     r9, aClsid0sControl; "CLSID\\<0s>\\Control"
0x180e74508  mov     [rsp+6D0h+phkResult], rax
0x180e7450d  lea     rdx, [rbp+5D0h+SubKey]; unsigned __int16 *
0x180e74514  xor     ecx, ecx; unsigned int
0x180e74516  call    ?Format@@YAJKPEAG_KPEBGZZ; Format(ulong,ushort *,unsigned __int64,ushort const *,...)
0x180e7451b  lea     rax, [rsp+6D0h+var_670]
0x180e74520  mov     r9d, 20019h; samDesired
0x180e74526  xor     r8d, r8d; ulOptions
0x180e74529  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180e7452e  lea     rdx, [rbp+5D0h+SubKey]; lpSubKey
0x180e74535  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180e7453c  call    cs:__imp_RegOpenKeyExW
0x180e74543  nop     dword ptr [rax+rax+00h]
0x180e74548  mov     ebx, eax
0x180e7454a  test    eax, eax
0x180e7454c  jnz     short loc_180E745B6
0x180e7454e  mov     eax, [rsp+6D0h+cbData]
0x180e74552  cmp     eax, 2
0x180e74555  jb      short loc_180E74576
0x180e74557  add     eax, 0FFFFFFFEh
0x180e7455a  mov     ecx, eax
0x180e7455c  add     rcx, rcx
0x180e7455f  cmp     rcx, 208h
0x180e74566  jnb     loc_180E74630
0x180e7456c  xor     eax, eax
0x180e7456e  mov     [rbp+rcx+5D0h+pvData], ax
0x180e74576  lea     rcx, [rbp+5D0h+pvData]; unsigned __int16 *
0x180e7457d  call    ?GetRawClsidString@@YAJPEAGK@Z; GetRawClsidString(ushort *,ulong)
0x180e74582  mov     ebx, eax
0x180e74584  test    eax, eax
0x180e74586  jnz     short loc_180E745B6
0x180e74588  lea     r11d, [rax+4Ch]
0x180e7458c  mov     rcx, rdi; unsigned __int16 *
0x180e7458f  mov     edx, r11d; unsigned __int64
0x180e74592  lea     r8, aClsid_0; "clsid:"
0x180e74599  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180e7459e  mov     ebx, eax
0x180e745a0  test    eax, eax
0x180e745a2  jnz     short loc_180E745B6
0x180e745a4  lea     r8, [rbp+5D0h+pvData]; unsigned __int16 *
0x180e745ab  mov     edx, r11d; unsigned __int64
0x180e745ae  mov     rcx, rdi; unsigned __int16 *
0x180e745b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180e745b6  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180e745bb  test    rcx, rcx
0x180e745be  jz      short loc_180E745CC
0x180e745c0  call    cs:__imp_RegCloseKey
0x180e745c7  nop     dword ptr [rax+rax+00h]
0x180e745cc  mov     rcx, [rsp+6D0h+var_680]; hKey
0x180e745d1  test    rcx, rcx
0x180e745d4  jz      short loc_180E745E2
0x180e745d6  call    cs:__imp_RegCloseKey
0x180e745dd  nop     dword ptr [rax+rax+00h]
0x180e745e2  mov     rcx, [rsp+6D0h+hkey]; hKey
0x180e745e7  test    rcx, rcx
0x180e745ea  jz      short loc_180E745F8
0x180e745ec  call    cs:__imp_RegCloseKey
0x180e745f3  nop     dword ptr [rax+rax+00h]
0x180e745f8  mov     rcx, [rsp+6D0h+var_670]; hKey
0x180e745fd  test    rcx, rcx
0x180e74600  jz      short loc_180E7460E
0x180e74602  call    cs:__imp_RegCloseKey
0x180e74609  nop     dword ptr [rax+rax+00h]
0x180e7460e  test    ebx, ebx
0x180e74610  setz    al
0x180e74613  mov     rcx, [rbp+5D0h+var_30]
0x180e7461a  xor     rcx, rsp; StackCookie
0x180e7461d  call    __security_check_cookie
0x180e74622  add     rsp, 6B8h
0x180e74629  pop     r14
0x180e7462b  pop     rdi
0x180e7462c  pop     rbx
0x180e7462d  pop     rbp
0x180e7462e  retn
0x180e74630  call    __report_rangecheckfailure
```
