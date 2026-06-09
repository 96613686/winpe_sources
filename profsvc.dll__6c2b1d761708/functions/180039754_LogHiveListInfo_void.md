# LogHiveListInfo(void)

- ea: `0x180039754`
- end: `0x180039a47`
- name: `?LogHiveListInfo@@YAJXZ`
- size: `755`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800393f8`

## callees

- `0x180005330`
- `0x18000dc10`
- `0x18000e1a0`
- `0x1800103d4`
- `0x1800130d0`
- `0x180013770`
- `0x180030ad0`
- `0x180039754`
- `0x180039a50`
- `0x180039cb4`
- `0x18003bc70`
- `0x18004f97c`
- `0x180050c1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180039931`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180039967`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180039931`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180039967`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800397d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800397d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180039837`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180039837`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800398f8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800398f8`

## string_xrefs

- `0x180039874`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800399ac`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 LogHiveListInfo(void)
{
  __int64 v0; // rdx
  __int64 v1; // rdx
  unsigned int v2; // ebx
  BYTE *v3; // rax
  __int64 v4; // r9
  __int64 v5; // rdx
  DWORD i; // edi
  int v7; // eax
  const unsigned __int16 *v8; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-9Ch] BYREF
  LPBYTE lpData; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR lpValueName; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cValues; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchValueName; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cbData; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v19[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v20[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  wil::ActivityBase<ProfileLogging,1,35184372088832,4,2164260864,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,35184372088832,4,2164260864,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v20);
  v20[0] = &ProfileTelemetry::RecordHiveList::`vftable';
  ProfileTelemetry::RecordHiveList::StartActivity((ProfileTelemetry::RecordHiveList *)v20);
  memset(v19, 0, 24);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\HiveList", 0, 1u, &hKey) )
    goto LABEL_19;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
    goto LABEL_19;
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpValueName,
    v0,
    2LL * cbMaxValueNameLen);
  if ( lpValueName )
  {
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpData,
      v1,
      cbMaxValueLen);
    v3 = lpData;
    if ( !lpData )
    {
      v2 = -2147024882;
      v4 = 2147942414LL;
      v5 = 1354;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)v4,
        phkResult);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
      goto LABEL_16;
    }
    for ( i = 0; i < cValues; ++i )
    {
      cchValueName = 2 * cbMaxValueNameLen;
      cbData = cbMaxValueLen;
      if ( !RegEnumValueW(hKey, i, lpValueName, &cchValueName, 0, 0, v3, &cbData)
        && FindStringOrdinal(0x400000u, (LPCWSTR)lpData, -1, L"\\Users\\", -1, 1) != -1
        && FindStringOrdinal(0x200000u, (LPCWSTR)lpData, -1, L"\\NTUSER.DAT", -1, 1) != -1 )
      {
        v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
               v19,
               L"%s\t\t%s\n",
               lpValueName,
               lpData);
        v2 = v7;
        if ( v7 < 0 )
        {
          v4 = (unsigned int)v7;
          v5 = 1367;
          goto LABEL_15;
        }
      }
      v3 = lpData;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
    v8 = (const unsigned __int16 *)v19[0];
    if ( v19[0] && *(_WORD *)v19[0] )
    {
LABEL_20:
      ProfileTelemetry::RecordHiveList::Stop((ProfileTelemetry::RecordHiveList *)v20, v8);
      v2 = 0;
      goto LABEL_21;
    }
LABEL_19:
    v8 = L"Nothing is holding a reference to NTUSER.DAT";
    goto LABEL_20;
  }
  v2 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x547,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)0x8007000ELL,
    phkResult);
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v19);
  ProfileTelemetry::RecordHiveList::~RecordHiveList((ProfileTelemetry::RecordHiveList *)v20);
  return v2;
}

```

## disassembly

```asm
0x180039754  push    rbp
0x180039756  push    rbx
0x180039757  push    rsi
0x180039758  push    rdi
0x180039759  lea     rbp, [rsp-118h]
0x180039761  sub     rsp, 218h
0x180039768  mov     rax, cs:__security_cookie
0x18003976f  xor     rax, rsp
0x180039772  mov     [rbp+130h+var_30], rax
0x180039779  xor     esi, esi
0x18003977b  lea     rcx, [rbp+130h+var_180]; struct wil::details::IFailureCallback *
0x18003977f  call    ??0?$ActivityBase@VProfileLogging@@$00$0CAAAAAAAAAAA@$03$0IBAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,35184372088832,4,2164260864,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,35184372088832,4,2164260864,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180039784  lea     rax, ??_7RecordHiveList@ProfileTelemetry@@6B@; const ProfileTelemetry::RecordHiveList::`vftable'
0x18003978b  mov     [rbp+130h+var_180], rax
0x18003978f  lea     rcx, [rbp+130h+var_180]; this
0x180039793  call    ?StartActivity@RecordHiveList@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::RecordHiveList::StartActivity(void)
0x180039798  nop
0x180039799  mov     [rbp+130h+var_1A0], rsi
0x18003979d  mov     [rbp+130h+var_198], rsi
0x1800397a1  mov     [rbp+130h+var_190], rsi
0x1800397a5  mov     [rsp+230h+hKey], rsi
0x1800397aa  xor     edx, edx
0x1800397ac  lea     rcx, [rsp+230h+hKey]
0x1800397b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800397b6  lea     rax, [rsp+230h+hKey]
0x1800397bb  mov     [rsp+230h+phkResult], rax; phkResult
0x1800397c0  lea     r9d, [rsi+1]; samDesired
0x1800397c4  xor     r8d, r8d; ulOptions
0x1800397c7  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Hiv"...
0x1800397ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800397d5  call    cs:__imp_RegOpenKeyExW
0x1800397dc  nop     dword ptr [rax+rax+00h]
0x1800397e1  test    eax, eax
0x1800397e3  jnz     loc_1800399F9
0x1800397e9  mov     [rbp+130h+cValues], esi
0x1800397ec  mov     [rsp+230h+cbMaxValueNameLen], esi
0x1800397f0  mov     [rsp+230h+cbMaxValueLen], esi
0x1800397f4  mov     [rsp+230h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800397f9  mov     [rsp+230h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800397fe  lea     rax, [rsp+230h+cbMaxValueLen]
0x180039803  mov     [rsp+230h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180039808  lea     rax, [rsp+230h+cbMaxValueNameLen]
0x18003980d  mov     [rsp+230h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180039812  lea     rax, [rbp+130h+cValues]
0x180039816  mov     [rsp+230h+lpcValues], rax; lpcValues
0x18003981b  mov     [rsp+230h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180039820  mov     [rsp+230h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180039825  mov     [rsp+230h+phkResult], rsi; int
0x18003982a  xor     r9d, r9d; lpReserved
0x18003982d  xor     r8d, r8d; lpcchClass
0x180039830  xor     edx, edx; lpClass
0x180039832  mov     rcx, [rsp+230h+hKey]; hKey
0x180039837  call    cs:__imp_RegQueryInfoKeyW
0x18003983e  nop     dword ptr [rax+rax+00h]
0x180039843  test    eax, eax
0x180039845  jnz     loc_1800399F9
0x18003984b  mov     r8d, [rsp+230h+cbMaxValueNameLen]
0x180039850  add     r8, r8
0x180039853  lea     rcx, [rsp+230h+lpValueName]
0x180039858  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003985d  nop
0x18003985e  cmp     [rsp+230h+lpValueName], rsi
0x180039863  jnz     short loc_18003988A
0x180039865  mov     rcx, [rbp+138h]; this
0x18003986c  mov     ebx, 8007000Eh
0x180039871  mov     r9d, ebx; char *
0x180039874  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003987b  mov     edx, 547h; void *
0x180039880  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039885  jmp     loc_1800399CA
0x18003988a  mov     r8d, [rsp+230h+cbMaxValueLen]
0x18003988f  lea     rcx, [rsp+230h+lpData]
0x180039894  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180039899  mov     rax, [rsp+230h+lpData]
0x18003989e  test    rax, rax
0x1800398a1  jnz     short loc_1800398B5
0x1800398a3  mov     ebx, 8007000Eh
0x1800398a8  mov     r9d, ebx
0x1800398ab  mov     edx, 54Ah
0x1800398b0  jmp     loc_1800399AC
0x1800398b5  mov     edi, esi
0x1800398b7  cmp     edi, [rbp+130h+cValues]
0x1800398ba  jnb     loc_1800399D6
0x1800398c0  mov     ecx, [rsp+230h+cbMaxValueNameLen]
0x1800398c4  add     ecx, ecx
0x1800398c6  mov     [rbp+130h+cchValueName], ecx
0x1800398c9  mov     ecx, [rsp+230h+cbMaxValueLen]
0x1800398cd  mov     [rbp+130h+cbData], ecx
0x1800398d0  lea     rcx, [rbp+130h+cbData]
0x1800398d4  mov     [rsp+230h+lpcValues], rcx; lpcbData
0x1800398d9  mov     [rsp+230h+lpcbMaxClassLen], rax; lpData
0x1800398de  mov     [rsp+230h+lpcbMaxSubKeyLen], rsi; lpType
0x1800398e3  mov     [rsp+230h+phkResult], rsi; lpReserved
0x1800398e8  lea     r9, [rbp+130h+cchValueName]; lpcchValueName
0x1800398ec  mov     r8, [rsp+230h+lpValueName]; lpValueName
0x1800398f1  mov     edx, edi; dwIndex
0x1800398f3  mov     rcx, [rsp+230h+hKey]; hKey
0x1800398f8  call    cs:__imp_RegEnumValueW
0x1800398ff  nop     dword ptr [rax+rax+00h]
0x180039904  test    eax, eax
0x180039906  jnz     loc_180039998
0x18003990c  mov     dword ptr [rsp+230h+lpcbMaxSubKeyLen], 1; bIgnoreCase
0x180039914  mov     dword ptr [rsp+230h+phkResult], 0FFFFFFFFh; cchValue
0x18003991c  lea     r9, StringValue; "\\Users\\"
0x180039923  or      r8d, 0FFFFFFFFh; cchSource
0x180039927  mov     rdx, [rsp+230h+lpData]; lpStringSource
0x18003992c  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x180039931  call    cs:__imp_FindStringOrdinal
0x180039938  nop     dword ptr [rax+rax+00h]
0x18003993d  cmp     eax, 0FFFFFFFFh
0x180039940  jz      short loc_180039998
0x180039942  mov     dword ptr [rsp+230h+lpcbMaxSubKeyLen], 1; bIgnoreCase
0x18003994a  mov     dword ptr [rsp+230h+phkResult], 0FFFFFFFFh; int
0x180039952  lea     r9, aNtuserDat_0; "\\NTUSER.DAT"
0x180039959  or      r8d, 0FFFFFFFFh; cchSource
0x18003995d  mov     rdx, [rsp+230h+lpData]; lpStringSource
0x180039962  mov     ecx, 200000h; dwFindStringOrdinalFlags
0x180039967  call    cs:__imp_FindStringOrdinal
0x18003996e  nop     dword ptr [rax+rax+00h]
0x180039973  cmp     eax, 0FFFFFFFFh
0x180039976  jz      short loc_180039998
0x180039978  mov     r9, [rsp+230h+lpData]
0x18003997d  mov     r8, [rsp+230h+lpValueName]
0x180039982  lea     rdx, aSS_2; "%s\t\t%s\n"
0x180039989  lea     rcx, [rbp+130h+var_1A0]
0x18003998d  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180039992  mov     ebx, eax
0x180039994  test    eax, eax
0x180039996  js      short loc_1800399A4
0x180039998  inc     edi
0x18003999a  mov     rax, [rsp+230h+lpData]
0x18003999f  jmp     loc_1800398B7
0x1800399a4  mov     r9d, eax; char *
0x1800399a7  mov     edx, 557h; void *
0x1800399ac  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800399b3  mov     rcx, [rbp+138h]; this
0x1800399ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800399bf  lea     rcx, [rsp+230h+lpData]
0x1800399c4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800399c9  nop
0x1800399ca  lea     rcx, [rsp+230h+lpValueName]
0x1800399cf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800399d4  jmp     short loc_180039A0B
0x1800399d6  lea     rcx, [rsp+230h+lpData]
0x1800399db  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800399e0  nop
0x1800399e1  lea     rcx, [rsp+230h+lpValueName]
0x1800399e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800399eb  mov     rdx, [rbp+130h+var_1A0]
0x1800399ef  test    rdx, rdx
0x1800399f2  jz      short loc_1800399F9
0x1800399f4  cmp     [rdx], si
0x1800399f7  jnz     short loc_180039A00
0x1800399f9  lea     rdx, aNothingIsHoldi; "Nothing is holding a reference to NTUSE"...
0x180039a00  lea     rcx, [rbp+130h+var_180]; this
0x180039a04  call    ?Stop@RecordHiveList@ProfileTelemetry@@QEAAXPEBG@Z; ProfileTelemetry::RecordHiveList::Stop(ushort const *)
0x180039a09  mov     ebx, esi
0x180039a0b  lea     rcx, [rsp+230h+hKey]
0x180039a10  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180039a15  nop
0x180039a16  lea     rcx, [rbp+130h+var_1A0]
0x180039a1a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180039a1f  nop
0x180039a20  lea     rcx, [rbp+130h+var_180]; this
0x180039a24  call    ??1RecordHiveList@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::RecordHiveList::~RecordHiveList(void)
0x180039a29  mov     eax, ebx
0x180039a2b  mov     rcx, [rbp+130h+var_30]
0x180039a32  xor     rcx, rsp; StackCookie
0x180039a35  call    __security_check_cookie
0x180039a3a  add     rsp, 218h
0x180039a41  pop     rdi
0x180039a42  pop     rsi
0x180039a43  pop     rbx
0x180039a44  pop     rbp
0x180039a45  retn
```
