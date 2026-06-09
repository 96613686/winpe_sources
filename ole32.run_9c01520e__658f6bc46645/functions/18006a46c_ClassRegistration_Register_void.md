# ClassRegistration::Register(void)

- ea: `0x18006a46c`
- end: `0x18006aa30`
- name: `?Register@ClassRegistration@@QEAAJXZ`
- size: `1476`
- prototype: `HRESULT __fastcall(ClassRegistration *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005e0f0`

## callees

- `0x180046460`
- `0x180069fb8`
- `0x18006a270`
- `0x18006a28c`
- `0x18006a46c`
- `0x18006aa38`
- `0x18006ab9c`
- `0x1800ce94f`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006a985`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d7419`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006a985`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d7419`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a8c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a8c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006a524`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006a524`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006a975`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006a9c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006a975`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006a9c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a93f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a93f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a993`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006a5c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006a5c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a7c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a81a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a887`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a9e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a9f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7486`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d749c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d74b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a7c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a81a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a887`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a9e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a9f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7486`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d749c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d74b2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18006a89f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18006a89f`

## pseudocode

```c
__int64 __fastcall ClassRegistration::Register(ClassRegistration *this)
{
  HKEY__ *v2; // rsi
  HINSTANCE__ *hModule; // rcx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  HKEY__ *v8; // rbx
  HRESULT v9; // eax
  unsigned int serverType; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  const wchar_t *v13; // rdx
  HKEY__ *v14; // rbx
  HINSTANCE__ *LibraryA; // rax
  HMODULE v16; // rbx
  FARPROC ProcAddress; // rax
  int v18; // eax
  signed int LastError; // eax
  signed int v20; // eax
  _BYTE v21[32]; // [rsp+0h] [rbp-3B8h] BYREF
  signed int v22; // [rsp+30h] [rbp-388h]
  HKEY__ *hkProgID; // [rsp+38h] [rbp-380h] BYREF
  _BYTE *v24; // [rsp+40h] [rbp-378h]
  HKEY__ *hkGuid; // [rsp+48h] [rbp-370h] BYREF
  HKEY__ *hkCLSID; // [rsp+50h] [rbp-368h] BYREF
  unsigned int v27; // [rsp+58h] [rbp-360h]
  HRESULT hr; // [rsp+5Ch] [rbp-35Ch]
  ITypeLib *pITypeLib; // [rsp+60h] [rbp-358h] BYREF
  HKEY__ *hkInproc; // [rsp+68h] [rbp-350h] BYREF
  _EXCEPTION_POINTERS *e; // [rsp+70h] [rbp-348h]
  int v32; // [rsp+78h] [rbp-340h]
  int v34; // [rsp+80h] [rbp-338h]
  int v35; // [rsp+84h] [rbp-334h]
  HRESULT v36; // [rsp+88h] [rbp-330h]
  int v37; // [rsp+8Ch] [rbp-32Ch]
  int v38; // [rsp+90h] [rbp-328h]
  ULONG_PTR Arguments; // [rsp+98h] [rbp-320h] BYREF
  HINSTANCE__ *hOleAut; // [rsp+A0h] [rbp-318h]
  ULONG_PTR v41[2]; // [rsp+A8h] [rbp-310h] BYREF
  AppRegistration a; // [rsp+B8h] [rbp-300h] BYREF
  wchar_t szClsid[40]; // [rsp+E0h] [rbp-2D8h] BYREF
  wchar_t szAppId[40]; // [rsp+130h] [rbp-288h] BYREF
  wchar_t szModuleName[264]; // [rsp+180h] [rbp-238h] BYREF

  v24 = v21;
  hkCLSID = 0;
  hkGuid = 0;
  hkProgID = 0;
  v2 = 0;
  hkInproc = 0;
  e = 0;
  hModule = this->hModule;
  if ( !hModule )
  {
    v32 = -2147024809;
    local_unwind_0(v21, &_LN46_0);
    return 2147942487LL;
  }
  if ( !GetModuleFileNameW(hModule, szModuleName, 0x104u) )
  {
    v34 = -2147418113;
    local_unwind_0(v24, &_LN47);
    return 2147549183LL;
  }
  v5 = *(_QWORD *)&this->clsid.Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&this->clsid.Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v5 = *(_QWORD *)this->clsid.Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( !v5 )
  {
    v35 = -2147024809;
    local_unwind_0(v24, &_LN48);
    return 2147942487LL;
  }
  v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, Com::Catalog::Constants::CLSID, 0, 0xF003Fu, &hkCLSID);
  if ( v6 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v27 = v6;
    local_unwind_0(v24, &_LN49);
    return v27;
  }
  else
  {
    GetGuidString(&this->clsid, szClsid);
    SetKeyAndValue(hkCLSID, szClsid, this->className, &hkGuid, 1);
    v7 = *(_QWORD *)&this->appid.Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v7 )
      v7 = *(_QWORD *)this->appid.Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v7 )
    {
      GetGuidString(&this->appid, szAppId);
      v8 = hkGuid;
      SetValue(hkGuid, Com::Catalog::Constants::AppID, szAppId);
      memset(&a, 0, sizeof(a));
      a.appid = this->appid;
      v9 = AppRegistration::Register(&a);
      hr = v9;
      if ( v9 )
      {
        v36 = v9;
        local_unwind_0(v24, &_LN50);
        return (unsigned int)hr;
      }
    }
    else
    {
      v8 = hkGuid;
    }
    serverType = this->serverType;
    if ( serverType )
    {
      v11 = serverType - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          if ( v12 != 2 )
          {
            v37 = -2147024809;
            local_unwind_0(v24, &_LN51_0);
            return 2147942487LL;
          }
          v13 = Com::Catalog::Constants::LocalServer32;
        }
        else
        {
          v13 = Com::Catalog::Constants::InprocHandler32;
        }
        SetKeyAndValue(v8, v13, szModuleName, 0, 0);
      }
      else
      {
        SetKeyAndValue(v8, Com::Catalog::Constants::InprocServer32, szModuleName, &hkInproc, 0);
        v2 = hkInproc;
        SetValue(hkInproc, Com::Catalog::Constants::ThreadingModel, this->threadingModel);
      }
    }
    SetKeyAndValue(v8, Com::Catalog::Constants::ProgID, this->progID, 0, 0);
    SetKeyAndValue(v8, Com::Catalog::Constants::VersionIndependentProgID, this->versionIndependentProgID, 0, 0);
    RegCloseKey(v8);
    hkGuid = 0;
    SetKeyAndValue((HKEY__ *)0xFFFFFFFF80000000LL, this->progID, this->className, &hkProgID, 0);
    SetKeyAndValue(hkProgID, Com::Catalog::Constants::CLSID, szClsid, 0, 0);
    RegCloseKey(hkProgID);
    hkProgID = 0;
    SetKeyAndValue((HKEY__ *)0xFFFFFFFF80000000LL, this->versionIndependentProgID, this->className, &hkProgID, 0);
    v14 = hkProgID;
    SetKeyAndValue(hkProgID, Com::Catalog::Constants::CLSID, szClsid, 0, 0);
    SetKeyAndValue(v14, Com::Catalog::Constants::CurVer, this->progID, 0, 0);
    RegCloseKey(v14);
    hkProgID = 0;
    LibraryA = LoadLibraryA("OLEAUT32");
    v16 = LibraryA;
    hOleAut = LibraryA;
    if ( LibraryA )
    {
      ProcAddress = GetProcAddress(LibraryA, "LoadTypeLibEx");
      if ( ProcAddress )
      {
        pITypeLib = 0;
        v18 = ((__int64 (__fastcall *)(wchar_t *, __int64, ITypeLib **))ProcAddress)(szModuleName, 1, &pITypeLib);
        if ( v18 < 0 )
        {
          if ( v18 != -2147312566 )
          {
            v38 = -2147220992;
            local_unwind_0(v24, &_LN56);
            return 2147746304LL;
          }
        }
        else
        {
          ((void (__fastcall *)(ITypeLib *))pITypeLib->lpVtbl->Release)(pITypeLib);
          pITypeLib = 0;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v22 = LastError;
        Arguments = LastError;
        RaiseException(0, 1u, 1u, &Arguments);
      }
      FreeLibrary(v16);
    }
    else
    {
      v20 = GetLastError();
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      v22 = v20;
      v41[0] = v20;
      RaiseException(0, 1u, 1u, v41);
    }
    if ( hkCLSID )
      RegCloseKey(hkCLSID);
    if ( v2 )
      RegCloseKey(v2);
    return 0;
  }
}

```

## disassembly

```asm
0x18006a46c  mov     [rsp+arg_8], rbx
0x18006a471  mov     [rsp+arg_10], rsi
0x18006a476  mov     [rsp+arg_18], rdi
0x18006a47b  push    r12
0x18006a47d  push    r14
0x18006a47f  push    r15
0x18006a481  sub     rsp, 3A0h
0x18006a488  mov     rax, cs:__security_cookie
0x18006a48f  xor     rax, rsp
0x18006a492  mov     [rsp+3B8h+var_28], rax
0x18006a49a  mov     [rsp+3B8h+var_378], rsp
0x18006a49f  mov     rdi, this
0x18006a4a2  xor     r15d, r15d
0x18006a4a5  mov     [rsp+3B8h+hkCLSID], r15
0x18006a4aa  mov     [rsp+3B8h+hkGuid], r15
0x18006a4af  mov     [rsp+3B8h+hkProgID], r15
0x18006a4b4  mov     esi, r15d
0x18006a4b7  mov     [rsp+3B8h+hkInproc], r15
0x18006a4bc  mov     [rsp+3B8h+e], r15
0x18006a4c1  mov     this, [this+18h]; hModule
0x18006a4c5  test    this, this
0x18006a4c8  jnz     short loc_18006A516
0x18006a4ca  mov     [rsp+3B8h+var_340], 80070057h
0x18006a4d2  lea     rdx, $LN46_0
0x18006a4d9  mov     this, rsp
0x18006a4dc  call    _local_unwind_0
0x18006a4e1  nop
0x18006a4e2  mov     eax, 80070057h
0x18006a4e7  mov     this, [rsp+3B8h+var_28]
0x18006a4ef  xor     this, rsp; StackCookie
0x18006a4f2  call    __security_check_cookie
0x18006a4f7  lea     r11, [rsp+3B8h+var_18]
0x18006a4ff  mov     rbx, [r11+28h]
0x18006a503  mov     rsi, [r11+30h]
0x18006a507  mov     rdi, [r11+38h]
0x18006a50b  mov     rsp, r11
0x18006a50e  pop     r15
0x18006a510  pop     r14
0x18006a512  pop     r12
0x18006a514  retn
0x18006a516  mov     r8d, 104h; nSize
0x18006a51c  lea     rdx, [rsp+3B8h+szModuleName]; lpFilename
0x18006a524  call    cs:__imp_GetModuleFileNameW
0x18006a52b  nop     dword ptr [rax+rax+00h]
0x18006a530  mov     [rsp+3B8h+dwLenFileName], eax
0x18006a534  test    eax, eax
0x18006a536  jnz     short loc_18006A55C
0x18006a538  mov     [rsp+3B8h+var_338], 8000FFFFh
0x18006a543  lea     rdx, $LN47
0x18006a54a  mov     this, [rsp+3B8h+var_378]
0x18006a54f  call    _local_unwind_0
0x18006a554  nop
0x18006a555  mov     eax, 8000FFFFh
0x18006a55a  jmp     short $LN37
0x18006a55c  mov     rax, [rdi]
0x18006a55f  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18006a566  jnz     short loc_18006A573
0x18006a568  mov     rax, [rdi+8]
0x18006a56c  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18006a573  test    rax, rax
0x18006a576  jnz     short loc_18006A59F
0x18006a578  mov     [rsp+3B8h+var_334], 80070057h
0x18006a583  lea     rdx, $LN48
0x18006a58a  mov     this, [rsp+3B8h+var_378]
0x18006a58f  call    _local_unwind_0
0x18006a594  nop
0x18006a595  mov     eax, 80070057h
0x18006a59a  jmp     $LN37
0x18006a59f  lea     rax, [rsp+3B8h+hkCLSID]
0x18006a5a4  mov     [rsp+3B8h+phkResult], rax; phkResult
0x18006a5a9  mov     r9d, 0F003Fh; samDesired
0x18006a5af  xor     r8d, r8d; ulOptions
0x18006a5b2  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18006a5b9  mov     this, 0FFFFFFFF80000000h; hKey
0x18006a5c0  call    cs:__imp_RegOpenKeyExW
0x18006a5c7  nop     dword ptr [rax+rax+00h]
0x18006a5cc  test    eax, eax
0x18006a5ce  jz      short loc_18006A5F9
0x18006a5d0  jle     short loc_18006A5DA
0x18006a5d2  movzx   eax, ax
0x18006a5d5  or      eax, 80070000h
0x18006a5da  mov     [rsp+3B8h+var_360], eax
0x18006a5de  lea     rdx, $LN49
0x18006a5e5  mov     this, [rsp+3B8h+var_378]
0x18006a5ea  call    _local_unwind_0
0x18006a5ef  nop
0x18006a5f0  mov     eax, [rsp+3B8h+var_360]
0x18006a5f4  jmp     $LN37
0x18006a5f9  lea     rdx, [rsp+3B8h+szClsid]; pstrGuid
0x18006a601  mov     this, rdi; rGuid
0x18006a604  call    GetGuidString
0x18006a609  mov     r12d, 1
0x18006a60f  mov     dword ptr [rsp+3B8h+phkResult], r12d; fForceKeyCreation
0x18006a614  lea     r9, [rsp+3B8h+hkGuid]; o_phkOut
0x18006a619  mov     r8, [rdi+20h]; i_szVal
0x18006a61d  lea     rdx, [rsp+3B8h+szClsid]; i_szKey
0x18006a625  mov     this, [rsp+3B8h+hkCLSID]; i_hKey
0x18006a62a  call    SetKeyAndValue
0x18006a62f  lea     r14, [rdi+40h]
0x18006a633  mov     rax, [r14]
0x18006a636  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18006a63d  jnz     short loc_18006A64A
0x18006a63f  mov     rax, [r14+8]
0x18006a643  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18006a64a  test    rax, rax
0x18006a64d  jz      loc_18006A6E0
0x18006a653  lea     rdx, [rsp+3B8h+szAppId]; pstrGuid
0x18006a65b  mov     this, r14; rGuid
0x18006a65e  call    GetGuidString
0x18006a663  lea     r8, [rsp+3B8h+szAppId]; i_szVal
0x18006a66b  lea     rdx, ?AppID@Constants@Catalog@Com@@3QBGB; i_szName
0x18006a672  mov     rbx, [rsp+3B8h+hkGuid]
0x18006a677  mov     this, rbx; i_hKey
0x18006a67a  call    SetValue
0x18006a67f  xorps   xmm0, xmm0
0x18006a682  xor     eax, eax
0x18006a684  movups  xmmword ptr [rsp+3B8h+a.appid.Data1], xmm0
0x18006a68c  movups  xmmword ptr [rsp+3B8h+a.appName], xmm0
0x18006a694  mov     [rsp+3B8h+a.hModuleSurrogate], rax
0x18006a69c  movups  xmm0, xmmword ptr [r14]
0x18006a6a0  movdqu  xmmword ptr [rsp+3B8h+a.appid.Data1], xmm0
0x18006a6a9  lea     this, [rsp+3B8h+a]; this
0x18006a6b1  call    ?Register@AppRegistration@@QEAAJXZ; AppRegistration::Register(void)
0x18006a6b6  mov     [rsp+3B8h+hr], eax
0x18006a6ba  test    eax, eax
0x18006a6bc  jz      short loc_18006A6E5
0x18006a6be  mov     [rsp+3B8h+var_330], eax
0x18006a6c5  lea     rdx, $LN50
0x18006a6cc  mov     this, [rsp+3B8h+var_378]
0x18006a6d1  call    _local_unwind_0
0x18006a6d6  nop
0x18006a6d7  mov     eax, [rsp+3B8h+hr]
0x18006a6db  jmp     $LN37
0x18006a6e0  mov     rbx, [rsp+3B8h+hkGuid]
0x18006a6e5  mov     ecx, [rdi+10h]
0x18006a6e8  test    ecx, ecx
0x18006a6ea  jz      loc_18006A789
0x18006a6f0  sub     ecx, r12d
0x18006a6f3  jz      short loc_18006A750
0x18006a6f5  sub     ecx, r12d
0x18006a6f8  jz      short loc_18006A747
0x18006a6fa  cmp     ecx, 2
0x18006a6fd  jz      short loc_18006A726
0x18006a6ff  mov     [rsp+3B8h+var_32C], 80070057h
0x18006a70a  lea     rdx, $LN51_0
0x18006a711  mov     this, [rsp+3B8h+var_378]
0x18006a716  call    _local_unwind_0
0x18006a71b  nop
0x18006a71c  mov     eax, 80070057h
0x18006a721  jmp     $LN37
0x18006a726  lea     rdx, ?LocalServer32@Constants@Catalog@Com@@3QBGB; i_szKey
0x18006a72d  lea     r8, [rsp+3B8h+szModuleName]; i_szVal
0x18006a735  xor     r9d, r9d; o_phkOut
0x18006a738  mov     dword ptr [rsp+3B8h+phkResult], r15d; fForceKeyCreation
0x18006a73d  mov     this, rbx; i_hKey
0x18006a740  call    SetKeyAndValue
0x18006a745  jmp     short loc_18006A789
0x18006a747  lea     rdx, ?InprocHandler32@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::InprocHandler32
0x18006a74e  jmp     short loc_18006A72D
0x18006a750  mov     dword ptr [rsp+3B8h+phkResult], r15d; fForceKeyCreation
0x18006a755  lea     r9, [rsp+3B8h+hkInproc]; o_phkOut
0x18006a75a  lea     r8, [rsp+3B8h+szModuleName]; i_szVal
0x18006a762  lea     rdx, ?InprocServer32@Constants@Catalog@Com@@3QBGB; i_szKey
0x18006a769  mov     this, rbx; i_hKey
0x18006a76c  call    SetKeyAndValue
0x18006a771  mov     r8, [rdi+38h]; i_szVal
0x18006a775  lea     rdx, ?ThreadingModel@Constants@Catalog@Com@@3QBGB; i_szName
0x18006a77c  mov     rsi, [rsp+3B8h+hkInproc]
0x18006a781  mov     this, rsi; i_hKey
0x18006a784  call    SetValue
0x18006a789  mov     dword ptr [rsp+3B8h+phkResult], r15d; fForceKeyCreation
0x18006a78e  xor     r9d, r9d; o_phkOut
0x18006a791  mov     r8, [rdi+28h]; i_szVal
0x18006a795  lea     rdx, ?ProgID@Constants@Catalog@Com@@3QBGB; i_szKey
0x18006a79c  mov     this, rbx; i_hKey
0x18006a79f  call    SetKeyAndValue
0x18006a7a4  mov     dword ptr [rsp+3B8h+phkResult], r15d; fForceKeyCreation
0x18006a7a9  xor     r9d, r9d; o_phkOut
0x18006a7ac  mov     r8, [rdi+30h]; i_szVal
0x18006a7b0  lea     rdx, ?VersionIndependentProgID@Constants@Catalog@Com@@3QBGB; i_szKey
0x18006a7b7  mov     this, rbx; i_hKey
0x18006a7ba  call    SetKeyAndValue
0x18006a7bf  mov     this, rbx; hKey
0x18006a7c2  call    cs:__imp_RegCloseKey
0x18006a7c9  nop     dword ptr [rax+rax+00h]
0x18006a7ce  mov     [rsp+3B8h+hkGuid], r15
0x18006a7d3  mov     dword ptr [rsp+3B8h+phkResult], r15d; fForceKeyCreation
0x18006a7d8  lea     r9, [rsp+3B8h+hkProgID]; o_phkOut
0x18006a7dd  mov     r8, [rdi+20h]; i_szVal
0x18006a7e1  mov     rdx, [rdi+28h]; i_szKey
0x18006a7e5  mov     rbx, 0FFFFFFFF80000000h
0x18006a7ec  mov     this, rbx; i_hKey
0x18006a7ef  call    SetKeyAndValue
0x18006a7f4  mov     dword ptr [rsp+3B8h+phkResult], r15d; fForceKeyCreation
0x18006a7f9  xor     r9d, r9d; o_phkOut
0x18006a7fc  lea     r8, [rsp+3B8h+szClsid]; i_szVal
0x18006a804  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; i_szKey
0x18006a80b  mov     this, [rsp+3B8h+hkProgID]; i_hKey
0x18006a810  call    SetKeyAndValue
0x18006a815  mov     this, [rsp+3B8h+hkProgID]; hKey
0x18006a81a  call    cs:__imp_RegCloseKey
0x18006a821  nop     dword ptr [rax+rax+00h]
0x18006a826  mov     [rsp+3B8h+hkProgID], r15
0x18006a82b  mov     dword ptr [rsp+3B8h+phkResult], r15d; fForceKeyCreation
0x18006a830  lea     r9, [rsp+3B8h+hkProgID]; o_phkOut
0x18006a835  mov     r8, [rdi+20h]; i_szVal
0x18006a839  mov     rdx, [rdi+30h]; i_szKey
0x18006a83d  mov     this, rbx; i_hKey
0x18006a840  call    SetKeyAndValue
0x18006a845  mov     dword ptr [rsp+3B8h+phkResult], r15d; fForceKeyCreation
0x18006a84a  xor     r9d, r9d; o_phkOut
0x18006a84d  lea     r8, [rsp+3B8h+szClsid]; i_szVal
0x18006a855  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; i_szKey
0x18006a85c  mov     rbx, [rsp+3B8h+hkProgID]
0x18006a861  mov     this, rbx; i_hKey
0x18006a864  call    SetKeyAndValue
0x18006a869  mov     dword ptr [rsp+3B8h+phkResult], r15d; fForceKeyCreation
0x18006a86e  xor     r9d, r9d; o_phkOut
0x18006a871  mov     r8, [rdi+28h]; i_szVal
0x18006a875  lea     rdx, ?CurVer@Constants@Catalog@Com@@3QBGB; i_szKey
0x18006a87c  mov     this, rbx; i_hKey
0x18006a87f  call    SetKeyAndValue
0x18006a884  mov     this, rbx; hKey
0x18006a887  call    cs:__imp_RegCloseKey
0x18006a88e  nop     dword ptr [rax+rax+00h]
0x18006a893  mov     [rsp+3B8h+hkProgID], r15
0x18006a898  lea     this, aOleaut32; "OLEAUT32"
0x18006a89f  call    cs:__imp_LoadLibraryA
0x18006a8a6  nop     dword ptr [rax+rax+00h]
0x18006a8ab  mov     rbx, rax
0x18006a8ae  mov     [rsp+3B8h+hOleAut], rax
0x18006a8b6  test    rax, rax
0x18006a8b9  jz      loc_18006A993
0x18006a8bf  lea     rdx, aLoadtypelibex; "LoadTypeLibEx"
0x18006a8c6  mov     this, rax; hModule
0x18006a8c9  call    cs:__imp_GetProcAddress
0x18006a8d0  nop     dword ptr [rax+rax+00h]
0x18006a8d5  test    rax, rax
0x18006a8d8  jz      short loc_18006A93F
0x18006a8da  mov     [rsp+3B8h+pITypeLib], r15
0x18006a8df  lea     r8, [rsp+3B8h+pITypeLib]
0x18006a8e4  mov     edx, r12d
0x18006a8e7  lea     this, [rsp+3B8h+szModuleName]
0x18006a8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8f4  test    eax, eax
0x18006a8f6  js      short loc_18006A910
0x18006a8f8  mov     this, [rsp+3B8h+pITypeLib]
0x18006a8fd  mov     rax, [this]
0x18006a900  mov     rax, [rax+10h]
0x18006a904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a909  mov     [rsp+3B8h+pITypeLib], r15
0x18006a90e  jmp     short $LN55
0x18006a910  cmp     eax, 80029C4Ah
0x18006a915  jz      short $LN55
0x18006a917  mov     [rsp+3B8h+var_328], 80040200h
0x18006a922  lea     rdx, $LN56
0x18006a929  mov     this, [rsp+3B8h+var_378]
0x18006a92e  call    _local_unwind_0
0x18006a933  nop
0x18006a934  nop
0x18006a935  mov     eax, 80040200h
0x18006a93a  jmp     $LN37
0x18006a93f  call    cs:__imp_GetLastError
0x18006a946  nop     dword ptr [rax+rax+00h]
0x18006a94b  test    eax, eax
0x18006a94d  jle     short loc_18006A957
0x18006a94f  movzx   eax, ax
0x18006a952  or      eax, 80070000h
0x18006a957  mov     [rsp+3B8h+var_388], eax
0x18006a95b  cdqe
0x18006a95d  mov     [rsp+3B8h+Arguments], rax
0x18006a965  lea     r9, [rsp+3B8h+Arguments]; lpArguments
0x18006a96d  mov     r8d, r12d; nNumberOfArguments
0x18006a970  mov     edx, r12d; dwExceptionFlags
0x18006a973  xor     ecx, ecx; dwExceptionCode
0x18006a975  call    cs:__imp_RaiseException
0x18006a97c  nop     dword ptr [rax+rax+00h]
0x18006a981  nop
0x18006a982  mov     this, rbx; hLibModule
0x18006a985  call    cs:__imp_FreeLibrary
0x18006a98c  nop     dword ptr [rax+rax+00h]
0x18006a991  jmp     short $LN41
0x18006a993  call    cs:__imp_GetLastError
0x18006a99a  nop     dword ptr [rax+rax+00h]
0x18006a99f  test    eax, eax
0x18006a9a1  jle     short loc_18006A9AB
0x18006a9a3  movzx   eax, ax
0x18006a9a6  or      eax, 80070000h
0x18006a9ab  mov     [rsp+3B8h+var_388], eax
0x18006a9af  cdqe
0x18006a9b1  mov     [rsp+3B8h+var_310], rax
0x18006a9b9  lea     r9, [rsp+3B8h+var_310]; lpArguments
0x18006a9c1  mov     r8d, r12d; nNumberOfArguments
0x18006a9c4  mov     edx, r12d; dwExceptionFlags
0x18006a9c7  xor     ecx, ecx; dwExceptionCode
0x18006a9c9  call    cs:__imp_RaiseException
0x18006a9d0  nop     dword ptr [rax+rax+00h]
0x18006a9d5  nop
0x18006a9d6  mov     this, [rsp+3B8h+hkCLSID]; hKey
0x18006a9db  test    this, this
  ... truncated ...
```
