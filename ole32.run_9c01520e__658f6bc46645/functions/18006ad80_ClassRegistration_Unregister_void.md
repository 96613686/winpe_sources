# ClassRegistration::Unregister(void)

- ea: `0x18006ad80`
- end: `0x18006b25c`
- name: `?Unregister@ClassRegistration@@QEAAJXZ`
- size: `1244`
- prototype: `HRESULT __fastcall(ClassRegistration *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005e0f0`

## callees

- `0x180046460`
- `0x180047484`
- `0x180069f20`
- `0x180069fb8`
- `0x18006a0b8`
- `0x18006a168`
- `0x18006a270`
- `0x18006ac30`
- `0x18006ad80`
- `0x1800ce94f`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006ae37`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006ae37`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006aff4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006b012`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006b030`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006b04e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006b06c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006aff4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006b012`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006b030`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006b04e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006b06c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ae78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006aead`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b129`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b190`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ae78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006aead`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b129`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006b190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b0d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b0f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b153`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b1cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b1f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b20a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b220`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d752e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7544`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d755a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b0d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b0f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b153`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b1cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b1f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b20a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006b220`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d752e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7544`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d755a`

## pseudocode

```c
__int64 __fastcall ClassRegistration::Unregister(ClassRegistration *this)
{
  HINSTANCE__ *hModule; // rcx
  const wchar_t *v4; // r8
  const wchar_t *progID; // rdx
  const wchar_t *versionIndependentProgID; // rdx
  _BYTE v7[32]; // [rsp+0h] [rbp-4F8h] BYREF
  HKEY__ *hKeyGuid; // [rsp+30h] [rbp-4C8h] BYREF
  int lRetVal; // [rsp+38h] [rbp-4C0h]
  HKEY__ *hKeyProgID; // [rsp+40h] [rbp-4B8h] BYREF
  HKEY__ *hKeyCLSID; // [rsp+48h] [rbp-4B0h] BYREF
  _EXCEPTION_POINTERS *e; // [rsp+50h] [rbp-4A8h]
  int v13; // [rsp+58h] [rbp-4A0h]
  _BYTE *v14; // [rsp+60h] [rbp-498h]
  wchar_t szClsid[40]; // [rsp+70h] [rbp-488h] BYREF
  wchar_t szProgID[264]; // [rsp+C0h] [rbp-438h] BYREF
  wchar_t szModuleName[264]; // [rsp+2D0h] [rbp-228h] BYREF

  v14 = v7;
  hKeyCLSID = 0;
  hKeyGuid = 0;
  hKeyProgID = 0;
  e = 0;
  memset_0(szProgID, 0, 0x208u);
  GetGuidString(&this->clsid, szClsid);
  hModule = this->hModule;
  if ( hModule )
  {
    if ( GetModuleFileNameW(hModule, szModuleName, 0x104u) )
      UnRegisterTypeLib(szModuleName);
    lRetVal = RegOpenKeyExW(HKEY_CLASSES_ROOT, Com::Catalog::Constants::CLSID, 0, 0xF003Fu, &hKeyCLSID);
    if ( !lRetVal )
    {
      lRetVal = RegOpenKeyExW(hKeyCLSID, szClsid, 0, 0xF003Fu, &hKeyGuid);
      if ( !lRetVal )
      {
        if ( !this->progID )
          this->progID = GetSubkeyValue(hKeyGuid, Com::Catalog::Constants::ProgID, v4, szProgID);
        if ( !this->versionIndependentProgID )
          this->versionIndependentProgID = GetSubkeyValue(
                                             hKeyGuid,
                                             Com::Catalog::Constants::VersionIndependentProgID,
                                             v4,
                                             szProgID);
        DeleteValue(hKeyGuid, 0, Com::Catalog::Constants::AppID);
        DeleteValue(hKeyGuid, Com::Catalog::Constants::InprocServer32, Com::Catalog::Constants::ThreadingModel);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::InprocServer32);
        GuardedDeleteKey(hKeyGuid, L"LocalServer");
        GuardedDeleteKey(hKeyGuid, L"InprocHandler");
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::LocalServer32);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::InprocHandler32);
        GuardedDeleteKey(hKeyGuid, L"Control");
        GuardedDeleteKey(hKeyGuid, L"Programmable");
        GuardedDeleteKey(hKeyGuid, L"DocObject");
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::Insertable);
        GuardedDeleteKey(hKeyGuid, L"Printable");
        RegDeleteKeyExW(hKeyGuid, Com::Catalog::Constants::MiscStatus, 0, 0);
        RegDeleteKeyExW(hKeyGuid, Com::Catalog::Constants::Verb, 0, 0);
        RegDeleteKeyExW(hKeyGuid, Com::Catalog::Constants::AuxUserType, 0, 0);
        RegDeleteKeyExW(hKeyGuid, Com::Catalog::Constants::Conversion, 0, 0);
        RegDeleteKeyExW(hKeyGuid, Com::Catalog::Constants::DataFormats, 0, 0);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::ToolBoxBitmap32);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::DefaultIcon);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::Version);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::ProgID);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::VersionIndependentProgID);
        RegCloseKey(hKeyGuid);
        hKeyGuid = 0;
      }
      GuardedDeleteKey(hKeyCLSID, szClsid);
      RegCloseKey(hKeyCLSID);
      hKeyCLSID = 0;
    }
    progID = this->progID;
    if ( progID )
    {
      lRetVal = RegOpenKeyExW(HKEY_CLASSES_ROOT, progID, 0, 0xF003Fu, &hKeyProgID);
      if ( !lRetVal )
      {
        GuardedDeleteKey(hKeyProgID, Com::Catalog::Constants::CLSID);
        RegCloseKey(hKeyProgID);
        hKeyProgID = 0;
        GuardedDeleteKey((HKEY__ *)0xFFFFFFFF80000000LL, this->progID);
      }
    }
    versionIndependentProgID = this->versionIndependentProgID;
    if ( versionIndependentProgID )
    {
      lRetVal = RegOpenKeyExW(HKEY_CLASSES_ROOT, versionIndependentProgID, 0, 0xF003Fu, &hKeyProgID);
      if ( !lRetVal )
      {
        GuardedDeleteKey(hKeyProgID, Com::Catalog::Constants::CLSID);
        GuardedDeleteKey(hKeyProgID, Com::Catalog::Constants::CurVer);
        RegCloseKey(hKeyProgID);
        hKeyProgID = 0;
        GuardedDeleteKey((HKEY__ *)0xFFFFFFFF80000000LL, this->versionIndependentProgID);
      }
    }
    if ( hKeyCLSID )
      RegCloseKey(hKeyCLSID);
    if ( hKeyGuid )
      RegCloseKey(hKeyGuid);
    if ( hKeyProgID )
      RegCloseKey(hKeyProgID);
    return 0;
  }
  else
  {
    v13 = -2147024809;
    local_unwind_0(v7, &_LN32_0);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18006ad80  mov     [rsp+arg_8], rbx
0x18006ad85  push    rsi
0x18006ad86  sub     rsp, 4F0h
0x18006ad8d  mov     rax, cs:__security_cookie
0x18006ad94  xor     rax, rsp
0x18006ad97  mov     [rsp+4F8h+var_18], rax
0x18006ad9f  mov     [rsp+4F8h+var_498], rsp
0x18006ada4  mov     rbx, this
0x18006ada7  and     [rsp+4F8h+hKeyCLSID], 0
0x18006adad  and     [rsp+4F8h+hKeyGuid], 0
0x18006adb3  and     [rsp+4F8h+hKeyProgID], 0
0x18006adb9  and     [rsp+4F8h+e], 0
0x18006adbf  xor     edx, edx; Val
0x18006adc1  mov     r8d, 208h; Size
0x18006adc7  lea     this, [rsp+4F8h+szProgID]; void *
0x18006adcf  call    memset_0
0x18006add4  lea     rdx, [rsp+4F8h+szClsid]; pstrGuid
0x18006add9  mov     this, rbx; rGuid
0x18006addc  call    GetGuidString
0x18006ade1  mov     this, [rbx+18h]; hModule
0x18006ade5  test    this, this
0x18006ade8  jnz     short loc_18006AE29
0x18006adea  mov     [rsp+4F8h+var_4A0], 80070057h
0x18006adf2  lea     rdx, $LN32_0
0x18006adf9  mov     this, rsp
0x18006adfc  call    _local_unwind_0
0x18006ae01  nop
0x18006ae02  mov     eax, 80070057h
0x18006ae07  mov     this, [rsp+4F8h+var_18]
0x18006ae0f  xor     this, rsp; StackCookie
0x18006ae12  call    __security_check_cookie
0x18006ae17  mov     rbx, [rsp+4F8h+arg_8]
0x18006ae1f  add     rsp, 4F0h
0x18006ae26  pop     rsi
0x18006ae27  retn
0x18006ae29  mov     r8d, 104h; nSize
0x18006ae2f  lea     rdx, [rsp+4F8h+szModuleName]; lpFilename
0x18006ae37  call    cs:__imp_GetModuleFileNameW
0x18006ae3e  nop     dword ptr [rax+rax+00h]
0x18006ae43  test    eax, eax
0x18006ae45  jz      short loc_18006AE54
0x18006ae47  lea     this, [rsp+4F8h+szModuleName]; szModuleName
0x18006ae4f  call    UnRegisterTypeLib
0x18006ae54  lea     rax, [rsp+4F8h+hKeyCLSID]
0x18006ae59  mov     [rsp+4F8h+phkResult], rax; phkResult
0x18006ae5e  mov     r9d, 0F003Fh; samDesired
0x18006ae64  xor     r8d, r8d; ulOptions
0x18006ae67  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18006ae6e  mov     rsi, 0FFFFFFFF80000000h
0x18006ae75  mov     this, rsi; hKey
0x18006ae78  call    cs:__imp_RegOpenKeyExW
0x18006ae7f  nop     dword ptr [rax+rax+00h]
0x18006ae84  mov     [rsp+4F8h+lRetVal], eax
0x18006ae88  test    eax, eax
0x18006ae8a  jnz     loc_18006B10A
0x18006ae90  lea     rax, [rsp+4F8h+hKeyGuid]
0x18006ae95  mov     [rsp+4F8h+phkResult], rax; phkResult
0x18006ae9a  mov     r9d, 0F003Fh; samDesired
0x18006aea0  xor     r8d, r8d; ulOptions
0x18006aea3  lea     rdx, [rsp+4F8h+szClsid]; lpSubKey
0x18006aea8  mov     this, [rsp+4F8h+hKeyCLSID]; hKey
0x18006aead  call    cs:__imp_RegOpenKeyExW
0x18006aeb4  nop     dword ptr [rax+rax+00h]
0x18006aeb9  mov     [rsp+4F8h+lRetVal], eax
0x18006aebd  test    eax, eax
0x18006aebf  jnz     loc_18006B0E4
0x18006aec5  cmp     qword ptr [rbx+28h], 0
0x18006aeca  jnz     short loc_18006AEE9
0x18006aecc  lea     r9, [rsp+4F8h+szProgID]; hkey
0x18006aed4  lea     rdx, ?ProgID@Constants@Catalog@Com@@3QBGB; szSubKeyName
0x18006aedb  mov     this, [rsp+4F8h+hKeyGuid]; hkey
0x18006aee0  call    GetSubkeyValue
0x18006aee5  mov     [rbx+28h], rax
0x18006aee9  cmp     qword ptr [rbx+30h], 0
0x18006aeee  jnz     short loc_18006AF0D
0x18006aef0  lea     r9, [rsp+4F8h+szProgID]; hkey
0x18006aef8  lea     rdx, ?VersionIndependentProgID@Constants@Catalog@Com@@3QBGB; szSubKeyName
0x18006aeff  mov     this, [rsp+4F8h+hKeyGuid]; hkey
0x18006af04  call    GetSubkeyValue
0x18006af09  mov     [rbx+30h], rax
0x18006af0d  lea     r8, ?AppID@Constants@Catalog@Com@@3QBGB; szValue
0x18006af14  xor     edx, edx; szSubkey
0x18006af16  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006af1b  call    DeleteValue
0x18006af20  lea     r8, ?ThreadingModel@Constants@Catalog@Com@@3QBGB; szValue
0x18006af27  lea     rdx, ?InprocServer32@Constants@Catalog@Com@@3QBGB; szSubkey
0x18006af2e  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006af33  call    DeleteValue
0x18006af38  lea     rdx, ?InprocServer32@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006af3f  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006af44  call    GuardedDeleteKey
0x18006af49  lea     rdx, aLocalserver; "LocalServer"
0x18006af50  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006af55  call    GuardedDeleteKey
0x18006af5a  lea     rdx, aInprochandler; "InprocHandler"
0x18006af61  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006af66  call    GuardedDeleteKey
0x18006af6b  lea     rdx, ?LocalServer32@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006af72  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006af77  call    GuardedDeleteKey
0x18006af7c  lea     rdx, ?InprocHandler32@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006af83  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006af88  call    GuardedDeleteKey
0x18006af8d  lea     rdx, aControl; "Control"
0x18006af94  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006af99  call    GuardedDeleteKey
0x18006af9e  lea     rdx, aProgrammable; "Programmable"
0x18006afa5  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006afaa  call    GuardedDeleteKey
0x18006afaf  lea     rdx, aDocobject; "DocObject"
0x18006afb6  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006afbb  call    GuardedDeleteKey
0x18006afc0  lea     rdx, ?Insertable@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006afc7  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006afcc  call    GuardedDeleteKey
0x18006afd1  lea     rdx, aPrintable; "Printable"
0x18006afd8  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006afdd  call    GuardedDeleteKey
0x18006afe2  xor     r9d, r9d; Reserved
0x18006afe5  xor     r8d, r8d; samDesired
0x18006afe8  lea     rdx, ?MiscStatus@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18006afef  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006aff4  call    cs:__imp_RegDeleteKeyExW
0x18006affb  nop     dword ptr [rax+rax+00h]
0x18006b000  xor     r9d, r9d; Reserved
0x18006b003  xor     r8d, r8d; samDesired
0x18006b006  lea     rdx, ?Verb@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18006b00d  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b012  call    cs:__imp_RegDeleteKeyExW
0x18006b019  nop     dword ptr [rax+rax+00h]
0x18006b01e  xor     r9d, r9d; Reserved
0x18006b021  xor     r8d, r8d; samDesired
0x18006b024  lea     rdx, ?AuxUserType@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18006b02b  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b030  call    cs:__imp_RegDeleteKeyExW
0x18006b037  nop     dword ptr [rax+rax+00h]
0x18006b03c  xor     r9d, r9d; Reserved
0x18006b03f  xor     r8d, r8d; samDesired
0x18006b042  lea     rdx, ?Conversion@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18006b049  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b04e  call    cs:__imp_RegDeleteKeyExW
0x18006b055  nop     dword ptr [rax+rax+00h]
0x18006b05a  xor     r9d, r9d; Reserved
0x18006b05d  xor     r8d, r8d; samDesired
0x18006b060  lea     rdx, ?DataFormats@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18006b067  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b06c  call    cs:__imp_RegDeleteKeyExW
0x18006b073  nop     dword ptr [rax+rax+00h]
0x18006b078  lea     rdx, ?ToolBoxBitmap32@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006b07f  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b084  call    GuardedDeleteKey
0x18006b089  lea     rdx, ?DefaultIcon@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006b090  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b095  call    GuardedDeleteKey
0x18006b09a  lea     rdx, ?Version@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006b0a1  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b0a6  call    GuardedDeleteKey
0x18006b0ab  lea     rdx, ?ProgID@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006b0b2  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b0b7  call    GuardedDeleteKey
0x18006b0bc  lea     rdx, ?VersionIndependentProgID@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006b0c3  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b0c8  call    GuardedDeleteKey
0x18006b0cd  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b0d2  call    cs:__imp_RegCloseKey
0x18006b0d9  nop     dword ptr [rax+rax+00h]
0x18006b0de  and     [rsp+4F8h+hKeyGuid], 0
0x18006b0e4  lea     rdx, [rsp+4F8h+szClsid]; szSubKey
0x18006b0e9  mov     this, [rsp+4F8h+hKeyCLSID]; hKey
0x18006b0ee  call    GuardedDeleteKey
0x18006b0f3  mov     this, [rsp+4F8h+hKeyCLSID]; hKey
0x18006b0f8  call    cs:__imp_RegCloseKey
0x18006b0ff  nop     dword ptr [rax+rax+00h]
0x18006b104  and     [rsp+4F8h+hKeyCLSID], 0
0x18006b10a  mov     rdx, [rbx+28h]; lpSubKey
0x18006b10e  test    rdx, rdx
0x18006b111  jz      short loc_18006B171
0x18006b113  lea     rax, [rsp+4F8h+hKeyProgID]
0x18006b118  mov     [rsp+4F8h+phkResult], rax; phkResult
0x18006b11d  mov     r9d, 0F003Fh; samDesired
0x18006b123  xor     r8d, r8d; ulOptions
0x18006b126  mov     this, rsi; hKey
0x18006b129  call    cs:__imp_RegOpenKeyExW
0x18006b130  nop     dword ptr [rax+rax+00h]
0x18006b135  mov     [rsp+4F8h+lRetVal], eax
0x18006b139  test    eax, eax
0x18006b13b  jnz     short loc_18006B171
0x18006b13d  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006b144  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x18006b149  call    GuardedDeleteKey
0x18006b14e  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x18006b153  call    cs:__imp_RegCloseKey
0x18006b15a  nop     dword ptr [rax+rax+00h]
0x18006b15f  and     [rsp+4F8h+hKeyProgID], 0
0x18006b165  mov     rdx, [rbx+28h]; szSubKey
0x18006b169  mov     this, rsi; hKey
0x18006b16c  call    GuardedDeleteKey
0x18006b171  mov     rdx, [rbx+30h]; lpSubKey
0x18006b175  test    rdx, rdx
0x18006b178  jz      short $LN27_2
0x18006b17a  lea     rax, [rsp+4F8h+hKeyProgID]
0x18006b17f  mov     [rsp+4F8h+phkResult], rax; phkResult
0x18006b184  mov     r9d, 0F003Fh; samDesired
0x18006b18a  xor     r8d, r8d; ulOptions
0x18006b18d  mov     this, rsi; hKey
0x18006b190  call    cs:__imp_RegOpenKeyExW
0x18006b197  nop     dword ptr [rax+rax+00h]
0x18006b19c  mov     [rsp+4F8h+lRetVal], eax
0x18006b1a0  test    eax, eax
0x18006b1a2  jnz     short $LN27_2
0x18006b1a4  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006b1ab  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x18006b1b0  call    GuardedDeleteKey
0x18006b1b5  lea     rdx, ?CurVer@Constants@Catalog@Com@@3QBGB; szSubKey
0x18006b1bc  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x18006b1c1  call    GuardedDeleteKey
0x18006b1c6  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x18006b1cb  call    cs:__imp_RegCloseKey
0x18006b1d2  nop     dword ptr [rax+rax+00h]
0x18006b1d7  and     [rsp+4F8h+hKeyProgID], 0
0x18006b1dd  mov     rdx, [rbx+30h]; szSubKey
0x18006b1e1  mov     this, rsi; hKey
0x18006b1e4  call    GuardedDeleteKey
0x18006b1e9  nop
0x18006b1ea  mov     this, [rsp+4F8h+hKeyCLSID]; hKey
0x18006b1ef  test    this, this
0x18006b1f2  jz      short loc_18006B200
0x18006b1f4  call    cs:__imp_RegCloseKey
0x18006b1fb  nop     dword ptr [rax+rax+00h]
0x18006b200  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x18006b205  test    this, this
0x18006b208  jz      short loc_18006B216
0x18006b20a  call    cs:__imp_RegCloseKey
0x18006b211  nop     dword ptr [rax+rax+00h]
0x18006b216  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x18006b21b  test    this, this
0x18006b21e  jz      short loc_18006B22C
0x18006b220  call    cs:__imp_RegCloseKey
0x18006b227  nop     dword ptr [rax+rax+00h]
0x18006b22c  xor     eax, eax
0x18006b22e  jmp     $LN23_1
0x18006b233  mov     this, [rsp+4F8h+e]; e
0x18006b238  call    HRESULTFrom
0x18006b23d  mov     [rsp+4F8h+lRetVal], eax
0x18006b241  lea     rdx, $LN33
0x18006b248  mov     this, [rsp+4F8h+var_498]
0x18006b24d  call    _local_unwind_0
0x18006b252  nop
0x18006b253  mov     eax, [rsp+4F8h+lRetVal]
0x18006b257  jmp     $LN23_1
0x1800d74f1  push    rbp
0x1800d74f3  sub     rsp, 30h
0x1800d74f7  mov     rbp, rdx
0x1800d74fa  mov     [rbp+68h], rcx
0x1800d74fe  mov     rax, [rcx]
0x1800d7501  mov     edx, [rax]
0x1800d7503  mov     [rbp+5Ch], edx
0x1800d7506  test    edx, edx
0x1800d7508  jnz     short loc_1800D7513
0x1800d750a  mov     [rbp+50h], rcx
0x1800d750e  lea     eax, [rdx+1]
0x1800d7511  jmp     short loc_1800D7515
0x1800d7513  xor     eax, eax
0x1800d7515  add     rsp, 30h
0x1800d7519  pop     rbp
0x1800d751a  retn
0x1800d751c  push    rbp
0x1800d751e  sub     rsp, 30h
0x1800d7522  mov     rbp, rdx
0x1800d7525  mov     rcx, [rbp+48h]; hKey
0x1800d7529  test    rcx, rcx
0x1800d752c  jz      short loc_1800D753B
0x1800d752e  call    cs:__imp_RegCloseKey
0x1800d7535  nop     dword ptr [rax+rax+00h]
0x1800d753a  nop
0x1800d753b  mov     rcx, [rbp+30h]; hKey
0x1800d753f  test    rcx, rcx
0x1800d7542  jz      short loc_1800D7551
0x1800d7544  call    cs:__imp_RegCloseKey
0x1800d754b  nop     dword ptr [rax+rax+00h]
0x1800d7550  nop
0x1800d7551  mov     rcx, [rbp+40h]; hKey
0x1800d7555  test    rcx, rcx
0x1800d7558  jz      short loc_1800D7567
0x1800d755a  call    cs:__imp_RegCloseKey
0x1800d7561  nop     dword ptr [rax+rax+00h]
0x1800d7566  nop
0x1800d7567  add     rsp, 30h
0x1800d756b  pop     rbp
0x1800d756c  retn
```
