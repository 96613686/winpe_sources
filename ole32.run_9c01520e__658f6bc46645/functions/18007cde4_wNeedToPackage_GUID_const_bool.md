# wNeedToPackage(_GUID const &,bool)

- ea: `0x18007cde4`
- end: `0x18007d0ec`
- name: `?wNeedToPackage@@YAHAEBU_GUID@@_N@Z`
- size: `776`
- prototype: `int __fastcall(const _GUID *rclsid, bool rclsid)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007c62c`

## callees

- `0x1800085a8`
- `0x18000f358`
- `0x18003a394`
- `0x180046460`
- `0x18007cde4`
- `0x18009a3a0`
- `0x1800cd6d0`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007cf4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007cfed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d052`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d08e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007cf4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007cfed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d052`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d08e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cf61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cfad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cfc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d001`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d064`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d0ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cf61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cfad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cfc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d001`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d064`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d0ac`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18007cef3`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18007cef3`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x18007ce3e`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x18007ce3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007cf1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007cf1f`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18007cedb`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18007d028`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18007cedb`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18007d028`

## pseudocode

```c
__int64 __fastcall wNeedToPackage(const _GUID *rclsid, bool a2, bool a3)
{
  unsigned int v3; // edi
  int v4; // r14d
  __int64 v6; // rax
  int v7; // ebx
  unsigned int v8; // r8d
  __int64 v9; // rax
  LSTATUS v10; // eax
  LSTATUS v11; // ebx
  bool isInsertable[8]; // [rsp+30h] [rbp-50h] BYREF
  HKEY__ *hkeyTmp; // [rsp+38h] [rbp-48h] BYREF
  HKEY__ *hkeyClsid; // [rsp+40h] [rbp-40h] BYREF
  Microsoft::WRL::ComPtr<IOleClassInfo> oleClassInfo; // [rsp+48h] [rbp-38h] BYREF
  wchar_t *lpszProgID; // [rsp+50h] [rbp-30h] BYREF
  HKEY__ *hKeyClsidOther; // [rsp+58h] [rbp-28h] BYREF
  HKEY__ *hkeyTmp2; // [rsp+60h] [rbp-20h] BYREF
  _GUID clsidNew; // [rsp+68h] [rbp-18h] BYREF

  v3 = 0;
  hkeyClsid = 0;
  hkeyTmp = 0;
  v4 = 0;
  hkeyTmp2 = 0;
  lpszProgID = 0;
  clsidNew = 0;
  if ( OleGetAutoConvertInternal(rclsid, &clsidNew, a3) && CoGetTreatAsClass(rclsid, &clsidNew) )
    clsidNew = *rclsid;
  oleClassInfo.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&oleClassInfo);
  if ( GetClassInfoWithInprocOrLocalServer(
         &clsidNew,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.ptr_) < 0 )
  {
    if ( (int)InternalRegOpenClassKey(&clsidNew, 131097, &hkeyClsid) < 0 )
    {
LABEL_10:
      v3 = 1;
      goto LABEL_31;
    }
    if ( ProgIDFromCLSID(&clsidNew, &lpszProgID)
      || (v7 = OpenClassesRootKeyExW(lpszProgID, 0x2000000u, &hkeyTmp), CoTaskMemFree(lpszProgID), v7) )
    {
LABEL_23:
      v10 = RegOpenKeyExW(hkeyClsid, Com::Catalog::Constants::Insertable, 0, 0x20019u, &hkeyTmp);
      if ( v10
        && (v10 != 2
         || (hKeyClsidOther = 0, (unsigned int)InternalRegOpenClassKey(&clsidNew, 131609, &hKeyClsidOther))
         || (v11 = RegOpenKeyExW(hKeyClsidOther, Com::Catalog::Constants::Insertable, 0, 0x20019u, &hkeyTmp),
             RegCloseKey(hKeyClsidOther),
             v11))
        && RegOpenKeyExW(hkeyClsid, L"Ole1Class", 0, 0x20019u, &hkeyTmp) )
      {
        v4 = 1;
      }
      else
      {
        RegCloseKey(hkeyTmp);
      }
      RegCloseKey(hkeyClsid);
      v3 = v4;
      goto LABEL_31;
    }
    if ( RegOpenKeyExW(hkeyTmp, L"PackageOnFileDrop", 0, 0x20019u, &hkeyTmp2) )
    {
      v9 = *(_QWORD *)&clsidNew.Data1 - *(_QWORD *)&CLSID_WordDocument.Data1;
      if ( *(_QWORD *)&clsidNew.Data1 == *(_QWORD *)&CLSID_WordDocument.Data1 )
        v9 = *(_QWORD *)clsidNew.Data4 - *(_QWORD *)CLSID_WordDocument.Data4;
      if ( v9 )
      {
LABEL_21:
        RegCloseKey(hkeyTmp);
        if ( v4 )
        {
          RegCloseKey(hkeyClsid);
          goto LABEL_10;
        }
        goto LABEL_23;
      }
      wRegSetValue(hkeyTmp, L"PackageOnFileDrop", v8, 0, 0);
    }
    else
    {
      RegCloseKey(hkeyTmp2);
    }
    v4 = 1;
    goto LABEL_21;
  }
  v6 = *(_QWORD *)&clsidNew.Data1 - *(_QWORD *)&CLSID_WordDocument.Data1;
  if ( *(_QWORD *)&clsidNew.Data1 == *(_QWORD *)&CLSID_WordDocument.Data1 )
    v6 = *(_QWORD *)clsidNew.Data4 - *(_QWORD *)CLSID_WordDocument.Data4;
  if ( !v6 )
    goto LABEL_10;
  isInsertable[0] = 0;
  if ( ((int (__fastcall *)(IOleClassInfo *, bool *))oleClassInfo.ptr_->lpVtbl[1].QueryInterface)(
         oleClassInfo.ptr_,
         isInsertable) < 0
    || !isInsertable[0] )
  {
    goto LABEL_10;
  }
LABEL_31:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&oleClassInfo);
  return v3;
}

```

## disassembly

```asm
0x18007cde4  mov     [rsp-18h+arg_8], rbx
0x18007cde9  mov     [rsp-18h+arg_10], rdi
0x18007cdee  push    rbp
0x18007cdef  push    r14
0x18007cdf1  push    r15
0x18007cdf3  mov     rbp, rsp
0x18007cdf6  sub     rsp, 80h
0x18007cdfd  mov     rax, cs:__security_cookie
0x18007ce04  xor     rax, rsp
0x18007ce07  mov     [rbp+var_8], rax
0x18007ce0b  xor     edi, edi
0x18007ce0d  lea     rdx, [rbp+clsidNew]; pClsidNew
0x18007ce11  xorps   xmm0, xmm0
0x18007ce14  mov     [rbp+hkeyClsid], rdi
0x18007ce18  mov     [rbp+hkeyTmp], rdi
0x18007ce1c  mov     r14d, edi
0x18007ce1f  mov     [rbp+hkeyTmp2], rdi
0x18007ce23  mov     rbx, rclsid
0x18007ce26  mov     [rbp+lpszProgID], rdi
0x18007ce2a  movups  xmmword ptr [rbp+clsidNew.Data1], xmm0
0x18007ce2e  call    ?OleGetAutoConvertInternal@@YAJAEBU_GUID@@PEAU1@_N@Z
0x18007ce33  test    eax, eax
0x18007ce35  jz      short loc_18007CE56
0x18007ce37  lea     rdx, [rbp+clsidNew]; pClsidNew
0x18007ce3b  mov     rclsid, rbx; clsidOld
0x18007ce3e  call    cs:__imp_CoGetTreatAsClass
0x18007ce45  nop     dword ptr [rax+rax+00h]
0x18007ce4a  test    eax, eax
0x18007ce4c  jz      short loc_18007CE56
0x18007ce4e  movups  xmm0, xmmword ptr [rbx]
0x18007ce51  movdqu  xmmword ptr [rbp+clsidNew.Data1], xmm0
0x18007ce56  lea     rclsid, [rbp+oleClassInfo]; this
0x18007ce5a  mov     [rbp+oleClassInfo.ptr_], rdi
0x18007ce5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x18007ce63  lea     r9, [rbp+oleClassInfo]; ppv
0x18007ce67  xor     edx, edx; pComCatalog
0x18007ce69  lea     r8, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18007ce70  lea     rclsid, [rbp+clsidNew]; clsid
0x18007ce74  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z
0x18007ce79  test    eax, eax
0x18007ce7b  js      short loc_18007CECA
0x18007ce7d  mov     rax, qword ptr [rbp+clsidNew.Data1]
0x18007ce81  sub     rax, qword ptr cs:CLSID_WordDocument.Data1
0x18007ce88  jnz     short loc_18007CE95
0x18007ce8a  mov     rax, qword ptr [rbp+clsidNew.Data4]
0x18007ce8e  sub     rax, qword ptr cs:CLSID_WordDocument.Data4
0x18007ce95  test    rax, rax
0x18007ce98  jz      short loc_18007CEC0
0x18007ce9a  mov     rclsid, [rbp+oleClassInfo.ptr_]
0x18007ce9e  lea     rdx, [rbp+isInsertable]
0x18007cea2  mov     [rbp+isInsertable], dil
0x18007cea6  mov     rax, [rclsid]
0x18007cea9  mov     rax, [rax+18h]
0x18007cead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ceb2  test    eax, eax
0x18007ceb4  js      short loc_18007CEC0
0x18007ceb6  cmp     [rbp+isInsertable], dil
0x18007ceba  jnz     loc_18007D0BB
0x18007cec0  mov     edi, 1
0x18007cec5  jmp     loc_18007D0BB
0x18007ceca  mov     r15d, 20019h
0x18007ced0  lea     r8, [rbp+hkeyClsid]
0x18007ced4  mov     edx, r15d
0x18007ced7  lea     rclsid, [rbp+clsidNew]
0x18007cedb  call    cs:__imp_InternalRegOpenClassKey
0x18007cee2  nop     dword ptr [rax+rax+00h]
0x18007cee7  test    eax, eax
0x18007cee9  js      short loc_18007CEC0
0x18007ceeb  lea     rdx, [rbp+lpszProgID]; lplpszProgID
0x18007ceef  lea     rclsid, [rbp+clsidNew]; clsid
0x18007cef3  call    cs:__imp_ProgIDFromCLSID
0x18007cefa  nop     dword ptr [rax+rax+00h]
0x18007ceff  test    eax, eax
0x18007cf01  jnz     loc_18007CFD3
0x18007cf07  mov     rclsid, [rbp+lpszProgID]; pszSubKey
0x18007cf0b  lea     r8, [rbp+hkeyTmp]; phkResult
0x18007cf0f  mov     edx, 2000000h; samDesired
0x18007cf14  call    OpenClassesRootKeyExW
0x18007cf19  mov     rclsid, [rbp+lpszProgID]; pv
0x18007cf1d  mov     ebx, eax
0x18007cf1f  call    cs:__imp_CoTaskMemFree
0x18007cf26  nop     dword ptr [rax+rax+00h]
0x18007cf2b  test    ebx, ebx
0x18007cf2d  jnz     loc_18007CFD3
0x18007cf33  mov     rclsid, [rbp+hkeyTmp]; hKey
0x18007cf37  lea     rax, [rbp+hkeyTmp2]
0x18007cf3b  mov     r9d, r15d; samDesired
0x18007cf3e  mov     [rsp+80h+phkResult], rax; phkResult
0x18007cf43  xor     r8d, r8d; ulOptions
0x18007cf46  lea     rdx, aPackageonfiled
0x18007cf4d  call    cs:__imp_RegOpenKeyExW
0x18007cf54  nop     dword ptr [rax+rax+00h]
0x18007cf59  test    eax, eax
0x18007cf5b  jnz     short loc_18007CF6F
0x18007cf5d  mov     rclsid, [rbp+hkeyTmp2]; hKey
0x18007cf61  call    cs:__imp_RegCloseKey
0x18007cf68  nop     dword ptr [rax+rax+00h]
0x18007cf6d  jmp     short loc_18007CFA3
0x18007cf6f  mov     rax, qword ptr [rbp+clsidNew.Data1]
0x18007cf73  sub     rax, qword ptr cs:CLSID_WordDocument.Data1
0x18007cf7a  jnz     short loc_18007CF87
0x18007cf7c  mov     rax, qword ptr [rbp+clsidNew.Data4]
0x18007cf80  sub     rax, qword ptr cs:CLSID_WordDocument.Data4
0x18007cf87  test    rax, rax
0x18007cf8a  jnz     short loc_18007CFA9
0x18007cf8c  mov     rclsid, [rbp+hkeyTmp]; hKey
0x18007cf90  lea     rdx, aPackageonfiled
0x18007cf97  xor     r9d, r9d; cchData
0x18007cf9a  mov     dword ptr [rsp+80h+phkResult], edi; hKey
0x18007cf9e  call    wRegSetValue
0x18007cfa3  mov     r14d, 1
0x18007cfa9  mov     rclsid, [rbp+hkeyTmp]; hKey
0x18007cfad  call    cs:__imp_RegCloseKey
0x18007cfb4  nop     dword ptr [rax+rax+00h]
0x18007cfb9  test    r14d, r14d
0x18007cfbc  jz      short loc_18007CFD3
0x18007cfbe  mov     rclsid, [rbp+hkeyClsid]; hKey
0x18007cfc2  call    cs:__imp_RegCloseKey
0x18007cfc9  nop     dword ptr [rax+rax+00h]
0x18007cfce  jmp     loc_18007CEC0
0x18007cfd3  mov     rclsid, [rbp+hkeyClsid]; hKey
0x18007cfd7  lea     rax, [rbp+hkeyTmp]
0x18007cfdb  mov     r9d, r15d; samDesired
0x18007cfde  mov     [rsp+80h+phkResult], rax; phkResult
0x18007cfe3  xor     r8d, r8d; ulOptions
0x18007cfe6  lea     rdx, ?Insertable@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18007cfed  call    cs:__imp_RegOpenKeyExW
0x18007cff4  nop     dword ptr [rax+rax+00h]
0x18007cff9  test    eax, eax
0x18007cffb  jnz     short loc_18007D012
0x18007cffd  mov     rclsid, [rbp+hkeyTmp]; hKey
0x18007d001  call    cs:__imp_RegCloseKey
0x18007d008  nop     dword ptr [rax+rax+00h]
0x18007d00d  jmp     $errRtn_77
0x18007d012  cmp     eax, 2
0x18007d015  jnz     short loc_18007D074
0x18007d017  lea     r8, [rbp+hKeyClsidOther]
0x18007d01b  mov     [rbp+hKeyClsidOther], rdi
0x18007d01f  mov     edx, 20219h
0x18007d024  lea     rclsid, [rbp+clsidNew]
0x18007d028  call    cs:__imp_InternalRegOpenClassKey
0x18007d02f  nop     dword ptr [rax+rax+00h]
0x18007d034  test    eax, eax
0x18007d036  jnz     short loc_18007D074
0x18007d038  mov     rclsid, [rbp+hKeyClsidOther]; hKey
0x18007d03c  lea     rax, [rbp+hkeyTmp]
0x18007d040  mov     r9d, r15d; samDesired
0x18007d043  mov     [rsp+80h+phkResult], rax; phkResult
0x18007d048  xor     r8d, r8d; ulOptions
0x18007d04b  lea     rdx, ?Insertable@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18007d052  call    cs:__imp_RegOpenKeyExW
0x18007d059  nop     dword ptr [rax+rax+00h]
0x18007d05e  mov     rclsid, [rbp+hKeyClsidOther]; hKey
0x18007d062  mov     ebx, eax
0x18007d064  call    cs:__imp_RegCloseKey
0x18007d06b  nop     dword ptr [rax+rax+00h]
0x18007d070  test    ebx, ebx
0x18007d072  jz      short loc_18007CFFD
0x18007d074  mov     rclsid, [rbp+hkeyClsid]; hKey
0x18007d078  lea     rax, [rbp+hkeyTmp]
0x18007d07c  mov     r9d, r15d; samDesired
0x18007d07f  mov     [rsp+80h+phkResult], rax; phkResult
0x18007d084  xor     r8d, r8d; ulOptions
0x18007d087  lea     rdx, aOle1class
0x18007d08e  call    cs:__imp_RegOpenKeyExW
0x18007d095  nop     dword ptr [rax+rax+00h]
0x18007d09a  test    eax, eax
0x18007d09c  jz      loc_18007CFFD
0x18007d0a2  mov     r14d, 1
0x18007d0a8  mov     rclsid, [rbp+hkeyClsid]; hKey
0x18007d0ac  call    cs:__imp_RegCloseKey
0x18007d0b3  nop     dword ptr [rax+rax+00h]
0x18007d0b8  mov     edi, r14d
0x18007d0bb  lea     rclsid, [rbp+oleClassInfo]; this
0x18007d0bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x18007d0c4  mov     eax, edi
0x18007d0c6  mov     rclsid, [rbp+var_8]
0x18007d0ca  xor     rclsid, rsp; StackCookie
0x18007d0cd  call    __security_check_cookie
0x18007d0d2  lea     r11, [rsp+80h+var_s0]
0x18007d0da  mov     rbx, [r11+28h]
0x18007d0de  mov     rdi, [r11+30h]
0x18007d0e2  mov     rsp, r11
0x18007d0e5  pop     r15
0x18007d0e7  pop     r14
0x18007d0e9  pop     rbp
0x18007d0ea  retn
```
