# CAppRegistryHive::Init(bool)

- ea: `0x1800a0548`
- end: `0x1800a08a9`
- name: `?Init@CAppRegistryHive@@SAJ_N@Z`
- size: `865`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18007d520`

## callees

- `0x1800095a0`
- `0x18009b290`
- `0x18009b538`
- `0x1800a0548`
- `0x1800a0ad4`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800a6ae4`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0792`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0664`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a07a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0664`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a07a5`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyA` at `0x1800a0629`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyA` at `0x1800a0629`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800a06a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800a0800`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800a06a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800a0800`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a065c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a0723`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a079d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a065c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a0723`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a079d`

## string_xrefs

- `0x1800a05e5`: `CAppRegistryHive::Init`
- `0x1800a06db`: `CAppRegistryHive::Init`
- `0x1800a0702`: `CAppRegistryHive::Init`
- `0x1800a076f`: `CAppRegistryHive::Init`
- `0x1800a084e`: `CAppRegistryHive::Init`
- `0x1800a05d9`: `Hive file path: %s, exists? %u`
- `0x1800a06c6`: `Failed to open subkey %s under root in apphive`
- `0x1800a075a`: `Falling back to NetworkService/HKLM path: %s`
- `0x1800a0835`: `SUCCEEDED(hr) || (hr == HRESULT_FROM_WIN32(ERROR_WRITE_PROTECT))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAppRegistryHive::Init(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  int StatePath; // eax
  int v5; // ebx
  const char *v6; // rcx
  bool v7; // al
  const char *v8; // rcx
  const CHAR *v9; // rcx
  LSTATUS v10; // eax
  HKEY v11; // rsi
  DWORD LastError; // ebx
  LSTATUS Key; // eax
  struct CPersistenceLocation *v14; // rax
  HKEY v15; // r14
  DWORD v16; // ebx
  struct CPersistenceLocation *v17; // rax
  const CHAR *v18; // rbx
  struct CPersistenceLocation *v19; // rax
  LSTATUS v20; // eax
  const char *v21; // r9
  __int64 result; // rax
  HKEY phkResult; // [rsp+50h] [rbp-38h] BYREF
  LPCSTR lpFile[2]; // [rsp+58h] [rbp-30h] BYREF
  __m128i si128; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_OWORD *)lpFile = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(lpFile[0]) = 0;
  StatePath = CPersistenceLocation::GetStatePath("dosvcState.dat", (char **)lpFile, a3, a4);
  try
  {
    v5 = StatePath;
    if ( StatePath < 0 )
      goto LABEL_22;
    v6 = (const char *)lpFile;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v6 = lpFile[0];
    v7 = CPath::Exists(v6);
    v8 = (const char *)lpFile;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v8 = lpFile[0];
    LogMessage(4u, "CAppRegistryHive::Init", 0x1Au, "Hive file path: %s, exists? %u", v8, v7);
    CAppRegistryHive::_EnsureHivePermissions((char *)lpFile);
    phkResult = 0;
    v9 = (const CHAR *)lpFile;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v9 = lpFile[0];
    v10 = RegLoadAppKeyA(v9, &phkResult, 0x2001Fu, 0, 0);
    v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      v5 = v10;
    if ( v5 < 0 )
    {
      LogResult(2u, "CAppRegistryHive::Init", 0x33u, v5, "Failed to load private hive");
    }
    else
    {
      v11 = CAppRegistryHive::_shDOSubKey;
      if ( CAppRegistryHive::_shDOSubKey )
      {
        LastError = GetLastError();
        RegCloseKey(v11);
        SetLastError(LastError);
      }
      CAppRegistryHive::_shDOSubKey = 0;
      Key = RegCreateKeyExA(phkResult, "DeliveryOptimization", 0, 0, 0, 0x2001Fu, 0, &CAppRegistryHive::_shDOSubKey, 0);
      v5 = (unsigned __int16)Key | 0x80070000;
      if ( Key <= 0 )
        v5 = Key;
      if ( v5 < 0 )
        LogResult(
          2u,
          "CAppRegistryHive::Init",
          0x2Eu,
          v5,
          "Failed to open subkey %s under root in apphive",
          "DeliveryOptimization");
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v5 < 0 )
    {
LABEL_22:
      if ( v5 != -2147024877 )
      {
        v14 = CPersistenceLocation::Instance();
        if ( *((_QWORD *)v14 + 3) > 0xFu )
          v14 = *(struct CPersistenceLocation **)v14;
        LogResult(
          3u,
          "CAppRegistryHive::Init",
          0x3Au,
          v5,
          "Falling back to NetworkService/HKLM path: %s",
          (const char *)v14);
        CAppRegistryHive::_fUsingPrivateHive = 0;
        v15 = CAppRegistryHive::_shDOSubKey;
        if ( CAppRegistryHive::_shDOSubKey )
        {
          v16 = GetLastError();
          RegCloseKey(v15);
          SetLastError(v16);
        }
        CAppRegistryHive::_shDOSubKey = 0;
        v17 = CPersistenceLocation::Instance();
        v18 = (const CHAR *)v17;
        if ( *((_QWORD *)v17 + 3) > 0xFu )
          v18 = *(const CHAR **)v17;
        v19 = CPersistenceLocation::Instance();
        v20 = RegCreateKeyExA(
                (HKEY)(-(__int64)(*((_BYTE *)v19 + 160) != 0) - 2147483645),
                v18,
                0,
                0,
                0,
                0x2001Fu,
                0,
                &CAppRegistryHive::_shDOSubKey,
                0);
        v5 = (unsigned __int16)v20 | 0x80070000;
        if ( v20 <= 0 )
          v5 = v20;
        if ( v5 < 0 && v5 != -2147024877 )
        {
          LogMessage(
            2u,
            "CAppRegistryHive::Init",
            0x40u,
            "TelemetryAssert (%s): %s (0x%x, 0x%x)",
            "SUCCEEDED(hr) || (hr == HRESULT_FROM_WIN32(ERROR_WRITE_PROTECT))",
            "Apphive fallback failed",
            v5,
            0);
          DOTelemetryAssertTriggered(v5, 0);
        }
      }
    }
    std::string::~string(lpFile);
    result = (unsigned int)v5;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x45,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\AppRegistryHive.cpp",
                           v21);
  }
  return result;
}

```

## disassembly

```asm
0x1800a0548  mov     r11, rsp
0x1800a054b  mov     [r11+8], rbx
0x1800a054f  mov     [r11+10h], rsi
0x1800a0553  mov     [r11+18h], r12
0x1800a0557  push    r14
0x1800a0559  sub     rsp, 80h
0x1800a0560  mov     rax, cs:__security_cookie
0x1800a0567  xor     rax, rsp
0x1800a056a  mov     [rsp+88h+var_10], rax
0x1800a056f  xorps   xmm0, xmm0
0x1800a0572  movups  xmmword ptr [rsp+88h+lpFile], xmm0
0x1800a0577  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800a057f  movdqu  [rsp+88h+var_20], xmm1
0x1800a0585  xor     r12d, r12d
0x1800a0588  mov     [r11-30h], r12b
0x1800a058c  lea     rdx, [r11-30h]
0x1800a0590  lea     rcx, aDosvcstateDat; "dosvcState.dat"
0x1800a0597  call    ?GetStatePath@CPersistenceLocation@@SAJPEBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CPersistenceLocation::GetStatePath(char const *,std::string &)
0x1800a059c  mov     ebx, eax
0x1800a059e  test    eax, eax
0x1800a05a0  js      loc_1800A0733
0x1800a05a6  lea     rcx, [rsp+88h+lpFile]
0x1800a05ab  cmp     qword ptr [rsp+88h+var_20+8], 0Fh
0x1800a05b1  cmova   rcx, [rsp+88h+lpFile]; char *
0x1800a05b7  call    ?Exists@CPath@@SA_NPEBD@Z; CPath::Exists(char const *)
0x1800a05bc  lea     rcx, [rsp+88h+lpFile]
0x1800a05c1  cmp     qword ptr [rsp+88h+var_20+8], 0Fh
0x1800a05c7  cmova   rcx, [rsp+88h+lpFile]
0x1800a05cd  movzx   eax, al
0x1800a05d0  mov     [rsp+88h+samDesired], eax
0x1800a05d4  mov     qword ptr [rsp+88h+Reserved], rcx
0x1800a05d9  lea     r9, aHiveFilePathSE; "Hive file path: %s, exists? %u"
0x1800a05e0  lea     r8d, [r12+1Ah]; unsigned int
0x1800a05e5  lea     rdx, aCappregistryhi; "CAppRegistryHive::Init"
0x1800a05ec  lea     ecx, [r12+4]; unsigned __int8
0x1800a05f1  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800a05f6  lea     rcx, [rsp+88h+lpFile]; char *
0x1800a05fb  call    ?_EnsureHivePermissions@CAppRegistryHive@@CAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CAppRegistryHive::_EnsureHivePermissions(std::string const &)
0x1800a0600  mov     [rsp+88h+phkResult], r12
0x1800a0605  lea     rcx, [rsp+88h+lpFile]
0x1800a060a  cmp     qword ptr [rsp+88h+var_20+8], 0Fh
0x1800a0610  cmova   rcx, [rsp+88h+lpFile]; lpFile
0x1800a0616  mov     [rsp+88h+Reserved], r12d; Reserved
0x1800a061b  xor     r9d, r9d; dwOptions
0x1800a061e  mov     r8d, 2001Fh; samDesired
0x1800a0624  lea     rdx, [rsp+88h+phkResult]; phkResult
0x1800a0629  call    cs:__imp_RegLoadAppKeyA
0x1800a062f  movzx   ebx, ax
0x1800a0632  or      ebx, 80070000h
0x1800a0638  test    eax, eax
0x1800a063a  cmovle  ebx, eax
0x1800a063d  test    ebx, ebx
0x1800a063f  js      loc_1800A06ED
0x1800a0645  mov     rsi, cs:?_shDOSubKey@CAppRegistryHive@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CAppRegistryHive::_shDOSubKey
0x1800a064c  test    rsi, rsi
0x1800a064f  jz      short loc_1800A066A
0x1800a0651  call    cs:__imp_GetLastError
0x1800a0657  mov     ebx, eax
0x1800a0659  mov     rcx, rsi; hKey
0x1800a065c  call    cs:__imp_RegCloseKey
0x1800a0662  mov     ecx, ebx; dwErrCode
0x1800a0664  call    cs:__imp_SetLastError
0x1800a066a  mov     cs:?_shDOSubKey@CAppRegistryHive@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, r12; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CAppRegistryHive::_shDOSubKey
0x1800a0671  mov     [rsp+88h+lpdwDisposition], r12; lpdwDisposition
0x1800a0676  lea     rsi, ?_shDOSubKey@CAppRegistryHive@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CAppRegistryHive::_shDOSubKey
0x1800a067d  mov     [rsp+88h+var_50], rsi; phkResult
0x1800a0682  mov     [rsp+88h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800a0687  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x1800a068f  mov     [rsp+88h+Reserved], r12d; dwOptions
0x1800a0694  xor     r9d, r9d; lpClass
0x1800a0697  xor     r8d, r8d; Reserved
0x1800a069a  lea     r14, SubKey; "DeliveryOptimization"
0x1800a06a1  mov     rdx, r14; lpSubKey
0x1800a06a4  mov     rcx, [rsp+88h+phkResult]; hKey
0x1800a06a9  call    cs:__imp_RegCreateKeyExA
0x1800a06af  movzx   ebx, ax
0x1800a06b2  or      ebx, 80070000h
0x1800a06b8  test    eax, eax
0x1800a06ba  cmovle  ebx, eax
0x1800a06bd  test    ebx, ebx
0x1800a06bf  jns     short loc_1800A0719
0x1800a06c1  mov     qword ptr [rsp+88h+samDesired], r14
0x1800a06c6  lea     rax, aFailedToOpenSu; "Failed to open subkey %s under root in "...
0x1800a06cd  mov     qword ptr [rsp+88h+Reserved], rax; char *
0x1800a06d2  mov     r9d, ebx; int
0x1800a06d5  mov     r8d, 2Eh ; '.'; unsigned int
0x1800a06db  lea     rdx, aCappregistryhi; "CAppRegistryHive::Init"
0x1800a06e2  lea     ecx, [r8-2Ch]; unsigned __int8
0x1800a06e6  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800a06eb  jmp     short loc_1800A0719
0x1800a06ed  lea     rax, aFailedToLoadPr; "Failed to load private hive"
0x1800a06f4  mov     qword ptr [rsp+88h+Reserved], rax; char *
0x1800a06f9  mov     r9d, ebx; int
0x1800a06fc  mov     r8d, 33h ; '3'; unsigned int
0x1800a0702  lea     rdx, aCappregistryhi; "CAppRegistryHive::Init"
0x1800a0709  lea     ecx, [r8-31h]; unsigned __int8
0x1800a070d  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800a0712  lea     rsi, ?_shDOSubKey@CAppRegistryHive@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CAppRegistryHive::_shDOSubKey
0x1800a0719  mov     rcx, [rsp+88h+phkResult]; hKey
0x1800a071e  test    rcx, rcx
0x1800a0721  jz      short loc_1800A0729
0x1800a0723  call    cs:__imp_RegCloseKey
0x1800a0729  test    ebx, ebx
0x1800a072b  jns     loc_1800A0868
0x1800a0731  jmp     short loc_1800A073A
0x1800a0733  lea     rsi, ?_shDOSubKey@CAppRegistryHive@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CAppRegistryHive::_shDOSubKey
0x1800a073a  cmp     ebx, 80070013h
0x1800a0740  jz      loc_1800A0868
0x1800a0746  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800a074b  cmp     qword ptr [rax+18h], 0Fh
0x1800a0750  jbe     short loc_1800A0755
0x1800a0752  mov     rax, [rax]
0x1800a0755  mov     qword ptr [rsp+88h+samDesired], rax
0x1800a075a  lea     rax, aFallingBackToN; "Falling back to NetworkService/HKLM pat"...
0x1800a0761  mov     qword ptr [rsp+88h+Reserved], rax; char *
0x1800a0766  mov     r9d, ebx; int
0x1800a0769  mov     r8d, 3Ah ; ':'; unsigned int
0x1800a076f  lea     rdx, aCappregistryhi; "CAppRegistryHive::Init"
0x1800a0776  lea     ecx, [r8-37h]; unsigned __int8
0x1800a077a  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800a077f  mov     cs:?_fUsingPrivateHive@CAppRegistryHive@@0_NA, r12b; bool CAppRegistryHive::_fUsingPrivateHive
0x1800a0786  mov     r14, cs:?_shDOSubKey@CAppRegistryHive@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CAppRegistryHive::_shDOSubKey
0x1800a078d  test    r14, r14
0x1800a0790  jz      short loc_1800A07AB
0x1800a0792  call    cs:__imp_GetLastError
0x1800a0798  mov     ebx, eax
0x1800a079a  mov     rcx, r14; hKey
0x1800a079d  call    cs:__imp_RegCloseKey
0x1800a07a3  mov     ecx, ebx; dwErrCode
0x1800a07a5  call    cs:__imp_SetLastError
0x1800a07ab  mov     cs:?_shDOSubKey@CAppRegistryHive@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, r12; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CAppRegistryHive::_shDOSubKey
0x1800a07b2  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800a07b7  mov     rbx, rax
0x1800a07ba  cmp     qword ptr [rax+18h], 0Fh
0x1800a07bf  jbe     short loc_1800A07C4
0x1800a07c1  mov     rbx, [rax]
0x1800a07c4  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800a07c9  mov     al, [rax+0A0h]
0x1800a07cf  neg     al
0x1800a07d1  sbb     rcx, rcx
0x1800a07d4  add     rcx, 0FFFFFFFF80000003h; hKey
0x1800a07db  mov     [rsp+88h+lpdwDisposition], r12; lpdwDisposition
0x1800a07e0  mov     [rsp+88h+var_50], rsi; phkResult
0x1800a07e5  mov     [rsp+88h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800a07ea  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x1800a07f2  mov     [rsp+88h+Reserved], r12d; dwOptions
0x1800a07f7  xor     r9d, r9d; lpClass
0x1800a07fa  xor     r8d, r8d; Reserved
0x1800a07fd  mov     rdx, rbx; lpSubKey
0x1800a0800  call    cs:__imp_RegCreateKeyExA
0x1800a0806  movzx   ebx, ax
0x1800a0809  or      ebx, 80070000h
0x1800a080f  test    eax, eax
0x1800a0811  cmovle  ebx, eax
0x1800a0814  test    ebx, ebx
0x1800a0816  jns     short loc_1800A0868
0x1800a0818  cmp     ebx, 80070013h
0x1800a081e  jz      short loc_1800A0868
0x1800a0820  mov     [rsp+88h+var_50], r12
0x1800a0825  mov     dword ptr [rsp+88h+lpSecurityAttributes], ebx
0x1800a0829  lea     rax, aApphiveFallbac; "Apphive fallback failed"
0x1800a0830  mov     qword ptr [rsp+88h+samDesired], rax
0x1800a0835  lea     rax, aSucceededHrHrH; "SUCCEEDED(hr) || (hr == HRESULT_FROM_WI"...
0x1800a083c  mov     qword ptr [rsp+88h+Reserved], rax
0x1800a0841  lea     r9, aTelemetryasser_0; "TelemetryAssert (%s): %s (0x%x, 0x%x)"
0x1800a0848  mov     r8d, 40h ; '@'; unsigned int
0x1800a084e  lea     rdx, aCappregistryhi; "CAppRegistryHive::Init"
0x1800a0855  lea     ecx, [r8-3Eh]; unsigned __int8
0x1800a0859  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800a085e  xor     edx, edx; unsigned int
0x1800a0860  mov     ecx, ebx; unsigned int
0x1800a0862  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x1800a0867  nop
0x1800a0868  lea     rcx, [rsp+88h+lpFile]; void *
0x1800a086d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800a0872  mov     eax, ebx
0x1800a0874  jmp     short loc_1800A0881
0x1800a0876  mov     eax, dword ptr [rsp+88h+phkResult]
0x1800a087a  jmp     short loc_1800A0881
0x1800a087c  mov     eax, 8007000Eh
0x1800a0881  mov     rcx, [rsp+88h+var_10]
0x1800a0886  xor     rcx, rsp; StackCookie
0x1800a0889  call    __security_check_cookie
0x1800a088e  lea     r11, [rsp+88h+var_8]
0x1800a0896  mov     rbx, [r11+10h]
0x1800a089a  mov     rsi, [r11+18h]
0x1800a089e  mov     r12, [r11+20h]
0x1800a08a2  mov     rsp, r11
0x1800a08a5  pop     r14
0x1800a08a7  retn
```
