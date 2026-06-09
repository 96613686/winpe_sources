# wNeedToPackage(_GUID const &,bool)

- ea: `0x18004d258`
- end: `0x18004d507`
- name: `?wNeedToPackage@@YAHAEBU_GUID@@_N@Z`
- size: `687`
- prototype: `int __fastcall(const _GUID *rclsid, bool rclsid)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180082a58`

## callees

- `0x18000a0e8`
- `0x18001a3c8`
- `0x180036488`
- `0x1800481d8`
- `0x18004d258`
- `0x180052390`
- `0x180098c00`
- `0x1800c4645`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d3c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d446`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d4d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d3c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d446`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d4d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d3b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d438`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d48c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d4bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d3b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d438`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d48c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d4bc`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18004d367`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18004d367`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x18004d2bc`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x18004d2bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d390`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d390`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18004d353`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18004d468`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18004d353`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18004d468`

## pseudocode

```c
__int64 __fastcall wNeedToPackage(const _GUID *rclsid, bool a2, bool a3)
{
  unsigned int v4; // edi
  int v5; // esi
  int v6; // ebx
  unsigned int v7; // r8d
  LSTATUS v8; // eax
  LSTATUS v9; // ebx
  bool isInsertable[8]; // [rsp+30h] [rbp-50h] BYREF
  HKEY__ *hkeyTmp; // [rsp+38h] [rbp-48h] BYREF
  HKEY__ *hkeyClsid; // [rsp+40h] [rbp-40h] BYREF
  Microsoft::WRL::ComPtr<IOleClassInfo> oleClassInfo; // [rsp+48h] [rbp-38h] BYREF
  wchar_t *lpszProgID; // [rsp+50h] [rbp-30h] BYREF
  HKEY__ *hKeyClsidOther; // [rsp+58h] [rbp-28h] BYREF
  HKEY__ *hkeyTmp2; // [rsp+60h] [rbp-20h] BYREF
  _GUID clsidNew; // [rsp+68h] [rbp-18h] BYREF

  hkeyClsid = 0;
  hkeyTmp = 0;
  clsidNew = 0;
  hkeyTmp2 = 0;
  lpszProgID = 0;
  if ( OleGetAutoConvertInternal(rclsid, &clsidNew, a3) && CoGetTreatAsClass(rclsid, &clsidNew) )
    clsidNew = *rclsid;
  oleClassInfo.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&oleClassInfo);
  if ( GetClassInfoWithInprocOrLocalServer(
         &clsidNew,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.ptr_) >= 0 )
  {
    if ( memcmp_0(&clsidNew, &CLSID_WordDocument, 0x10u) )
    {
      isInsertable[0] = 0;
      if ( ((int (__fastcall *)(IOleClassInfo *, bool *))oleClassInfo.ptr_->lpVtbl[1].QueryInterface)(
             oleClassInfo.ptr_,
             isInsertable) >= 0
        && isInsertable[0] )
      {
        v4 = 0;
        goto LABEL_28;
      }
    }
LABEL_9:
    v4 = 1;
    goto LABEL_28;
  }
  if ( (int)InternalRegOpenClassKey(&clsidNew, 131097, &hkeyClsid) < 0 )
    goto LABEL_9;
  v5 = 0;
  v4 = 1;
  if ( !ProgIDFromCLSID(&clsidNew, &lpszProgID) )
  {
    v6 = OpenClassesRootKeyExW(lpszProgID, 0x2000000u, &hkeyTmp);
    CoTaskMemFree(lpszProgID);
    if ( !v6 )
    {
      if ( RegOpenKeyExW(hkeyTmp, L"PackageOnFileDrop", 0, 0x20019u, &hkeyTmp2) )
      {
        if ( memcmp_0(&clsidNew, &CLSID_WordDocument, 0x10u) )
          goto LABEL_18;
        wRegSetValue(hkeyTmp, L"PackageOnFileDrop", v7, 0, 0);
      }
      else
      {
        RegCloseKey(hkeyTmp2);
      }
      v5 = 1;
LABEL_18:
      RegCloseKey(hkeyTmp);
      if ( v5 )
      {
        RegCloseKey(hkeyClsid);
        goto LABEL_28;
      }
    }
  }
  v8 = RegOpenKeyExW(hkeyClsid, Com::Catalog::Constants::Insertable, 0, 0x20019u, &hkeyTmp);
  if ( v8
    && (v8 != 2
     || (hKeyClsidOther = 0, (unsigned int)InternalRegOpenClassKey(&clsidNew, 131609, &hKeyClsidOther))
     || (v9 = RegOpenKeyExW(hKeyClsidOther, Com::Catalog::Constants::Insertable, 0, 0x20019u, &hkeyTmp),
         RegCloseKey(hKeyClsidOther),
         v9))
    && RegOpenKeyExW(hkeyClsid, L"Ole1Class", 0, 0x20019u, &hkeyTmp) )
  {
    v5 = 1;
  }
  else
  {
    RegCloseKey(hkeyTmp);
  }
  RegCloseKey(hkeyClsid);
  v4 = v5;
LABEL_28:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&oleClassInfo);
  return v4;
}

```

## disassembly

```asm
0x18004d258  mov     [rsp-18h+arg_8], rbx
0x18004d25d  mov     [rsp-18h+arg_10], rsi
0x18004d262  push    rbp
0x18004d263  push    rdi
0x18004d264  push    r15
0x18004d266  mov     rbp, rsp
0x18004d269  sub     rsp, 80h
0x18004d270  mov     rax, cs:__security_cookie
0x18004d277  xor     rax, rsp
0x18004d27a  mov     [rbp+var_8], rax
0x18004d27e  xorps   xmm0, xmm0
0x18004d281  mov     [rbp+hkeyClsid], 0
0x18004d289  lea     rdx, [rbp+clsidNew]; pClsidNew
0x18004d28d  mov     [rbp+hkeyTmp], 0
0x18004d295  movups  xmmword ptr [rbp+clsidNew.Data1], xmm0
0x18004d299  mov     rbx, rclsid
0x18004d29c  mov     [rbp+hkeyTmp2], 0
0x18004d2a4  mov     [rbp+lpszProgID], 0
0x18004d2ac  call    ?OleGetAutoConvertInternal@@YAJAEBU_GUID@@PEAU1@_N@Z; OleGetAutoConvertInternal(_GUID const &,_GUID *,bool)
0x18004d2b1  test    eax, eax
0x18004d2b3  jz      short loc_18004D2CE
0x18004d2b5  lea     rdx, [rbp+clsidNew]; pClsidNew
0x18004d2b9  mov     rclsid, rbx; clsidOld
0x18004d2bc  call    cs:__imp_CoGetTreatAsClass
0x18004d2c2  test    eax, eax
0x18004d2c4  jz      short loc_18004D2CE
0x18004d2c6  movups  xmm0, xmmword ptr [rbx]
0x18004d2c9  movdqu  xmmword ptr [rbp+clsidNew.Data1], xmm0
0x18004d2ce  lea     rclsid, [rbp+oleClassInfo]; this
0x18004d2d2  mov     [rbp+oleClassInfo.ptr_], 0
0x18004d2da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d2df  lea     r9, [rbp+oleClassInfo]; ppv
0x18004d2e3  xor     edx, edx; pComCatalog
0x18004d2e5  lea     r8, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18004d2ec  lea     rclsid, [rbp+clsidNew]; clsid
0x18004d2f0  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18004d2f5  lea     rclsid, [rbp+clsidNew]; Buf1
0x18004d2f9  test    eax, eax
0x18004d2fb  js      short loc_18004D346
0x18004d2fd  mov     r8d, 10h; Size
0x18004d303  lea     rdx, CLSID_WordDocument; Buf2
0x18004d30a  call    memcmp_0
0x18004d30f  test    eax, eax
0x18004d311  jz      short loc_18004D33C
0x18004d313  mov     rclsid, [rbp+oleClassInfo.ptr_]
0x18004d317  lea     rdx, [rbp+isInsertable]
0x18004d31b  mov     [rbp+isInsertable], 0
0x18004d31f  mov     rax, [rclsid]
0x18004d322  mov     rax, [rax+18h]
0x18004d326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d32b  test    eax, eax
0x18004d32d  js      short loc_18004D33C
0x18004d32f  cmp     [rbp+isInsertable], 0
0x18004d333  jz      short loc_18004D33C
0x18004d335  xor     edi, edi
0x18004d337  jmp     loc_18004D4D8
0x18004d33c  mov     edi, 1
0x18004d341  jmp     loc_18004D4D8
0x18004d346  mov     r15d, 20019h
0x18004d34c  lea     r8, [rbp+hkeyClsid]
0x18004d350  mov     edx, r15d
0x18004d353  call    cs:__imp_InternalRegOpenClassKey
0x18004d359  test    eax, eax
0x18004d35b  js      short loc_18004D33C
0x18004d35d  lea     rdx, [rbp+lpszProgID]; lplpszProgID
0x18004d361  xor     esi, esi
0x18004d363  lea     rclsid, [rbp+clsidNew]; clsid
0x18004d367  call    cs:__imp_ProgIDFromCLSID
0x18004d36d  lea     edi, [rsi+1]
0x18004d370  test    eax, eax
0x18004d372  jnz     loc_18004D41E
0x18004d378  mov     rclsid, [rbp+lpszProgID]; pszSubKey
0x18004d37c  lea     r8, [rbp+hkeyTmp]; phkResult
0x18004d380  mov     edx, 2000000h; samDesired
0x18004d385  call    OpenClassesRootKeyExW
0x18004d38a  mov     rclsid, [rbp+lpszProgID]; pv
0x18004d38e  mov     ebx, eax
0x18004d390  call    cs:__imp_CoTaskMemFree
0x18004d396  test    ebx, ebx
0x18004d398  jnz     loc_18004D41E
0x18004d39e  mov     rclsid, [rbp+hkeyTmp]; hKey
0x18004d3a2  lea     rax, [rbp+hkeyTmp2]
0x18004d3a6  mov     r9d, r15d; samDesired
0x18004d3a9  mov     [rsp+80h+phkResult], rax; phkResult
0x18004d3ae  xor     r8d, r8d; ulOptions
0x18004d3b1  lea     rdx, aPackageonfiled; "PackageOnFileDrop"
0x18004d3b8  call    cs:__imp_RegOpenKeyExW
0x18004d3be  test    eax, eax
0x18004d3c0  jnz     short loc_18004D3CE
0x18004d3c2  mov     rclsid, [rbp+hkeyTmp2]; hKey
0x18004d3c6  call    cs:__imp_RegCloseKey
0x18004d3cc  jmp     short loc_18004D3FF
0x18004d3ce  mov     r8d, 10h; Size
0x18004d3d4  lea     rdx, CLSID_WordDocument; Buf2
0x18004d3db  lea     rclsid, [rbp+clsidNew]; Buf1
0x18004d3df  call    memcmp_0
0x18004d3e4  test    eax, eax
0x18004d3e6  jnz     short loc_18004D401
0x18004d3e8  mov     rclsid, [rbp+hkeyTmp]; hKey
0x18004d3ec  lea     rdx, aPackageonfiled; "PackageOnFileDrop"
0x18004d3f3  xor     r9d, r9d; cchData
0x18004d3f6  mov     dword ptr [rsp+80h+phkResult], esi; hKey
0x18004d3fa  call    wRegSetValue
0x18004d3ff  mov     esi, edi
0x18004d401  mov     rclsid, [rbp+hkeyTmp]; hKey
0x18004d405  call    cs:__imp_RegCloseKey
0x18004d40b  test    esi, esi
0x18004d40d  jz      short loc_18004D41E
0x18004d40f  mov     rclsid, [rbp+hkeyClsid]; hKey
0x18004d413  call    cs:__imp_RegCloseKey
0x18004d419  jmp     loc_18004D4D8
0x18004d41e  mov     rclsid, [rbp+hkeyClsid]; hKey
0x18004d422  lea     rax, [rbp+hkeyTmp]
0x18004d426  mov     r9d, r15d; samDesired
0x18004d429  mov     [rsp+80h+phkResult], rax; phkResult
0x18004d42e  xor     r8d, r8d; ulOptions
0x18004d431  lea     rdx, ?Insertable@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18004d438  call    cs:__imp_RegOpenKeyExW
0x18004d43e  test    eax, eax
0x18004d440  jnz     short loc_18004D44E
0x18004d442  mov     rclsid, [rbp+hkeyTmp]; hKey
0x18004d446  call    cs:__imp_RegCloseKey
0x18004d44c  jmp     short $errRtn_68
0x18004d44e  cmp     eax, 2
0x18004d451  jnz     short loc_18004D4A2
0x18004d453  lea     r8, [rbp+hKeyClsidOther]
0x18004d457  mov     [rbp+hKeyClsidOther], 0
0x18004d45f  mov     edx, 20219h
0x18004d464  lea     rclsid, [rbp+clsidNew]
0x18004d468  call    cs:__imp_InternalRegOpenClassKey
0x18004d46e  test    eax, eax
0x18004d470  jnz     short loc_18004D4A2
0x18004d472  mov     rclsid, [rbp+hKeyClsidOther]; hKey
0x18004d476  lea     rax, [rbp+hkeyTmp]
0x18004d47a  mov     r9d, r15d; samDesired
0x18004d47d  mov     [rsp+80h+phkResult], rax; phkResult
0x18004d482  xor     r8d, r8d; ulOptions
0x18004d485  lea     rdx, ?Insertable@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18004d48c  call    cs:__imp_RegOpenKeyExW
0x18004d492  mov     rclsid, [rbp+hKeyClsidOther]; hKey
0x18004d496  mov     ebx, eax
0x18004d498  call    cs:__imp_RegCloseKey
0x18004d49e  test    ebx, ebx
0x18004d4a0  jz      short loc_18004D442
0x18004d4a2  mov     rclsid, [rbp+hkeyClsid]; hKey
0x18004d4a6  lea     rax, [rbp+hkeyTmp]
0x18004d4aa  mov     r9d, r15d; samDesired
0x18004d4ad  mov     [rsp+80h+phkResult], rax; phkResult
0x18004d4b2  xor     r8d, r8d; ulOptions
0x18004d4b5  lea     rdx, aOle1class; "Ole1Class"
0x18004d4bc  call    cs:__imp_RegOpenKeyExW
0x18004d4c2  test    eax, eax
0x18004d4c4  jz      loc_18004D442
0x18004d4ca  mov     esi, edi
0x18004d4cc  mov     rclsid, [rbp+hkeyClsid]; hKey
0x18004d4d0  call    cs:__imp_RegCloseKey
0x18004d4d6  mov     edi, esi
0x18004d4d8  lea     rclsid, [rbp+oleClassInfo]; this
0x18004d4dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d4e1  mov     eax, edi
0x18004d4e3  mov     rclsid, [rbp+var_8]
0x18004d4e7  xor     rclsid, rsp; StackCookie
0x18004d4ea  call    __security_check_cookie
0x18004d4ef  lea     r11, [rsp+80h+var_s0]
0x18004d4f7  mov     rbx, [r11+28h]
0x18004d4fb  mov     rsi, [r11+30h]
0x18004d4ff  mov     rsp, r11
0x18004d502  pop     r15
0x18004d504  pop     rdi
0x18004d505  pop     rbp
0x18004d506  retn
```
