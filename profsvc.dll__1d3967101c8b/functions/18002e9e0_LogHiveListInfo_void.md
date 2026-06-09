# LogHiveListInfo(void)

- ea: `0x18002e9e0`
- end: `0x18002eccb`
- name: `?LogHiveListInfo@@YAJXZ`
- size: `747`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cf64`

## callees

- `0x180007978`
- `0x18000fa10`
- `0x1800111a0`
- `0x180014fc4`
- `0x18001f060`
- `0x18002d2d8`
- `0x18002e9e0`
- `0x18002ecd4`
- `0x18003a730`
- `0x18004c958`
- `0x18004d8f8`
- `0x18004da0c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002ebab`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002ebdb`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002ebab`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002ebdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ea61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ea61`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002eabd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002eabd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ec4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ec93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ec4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ec93`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002eb78`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002eb78`

## string_xrefs

- `0x18002eaf4`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002ec1a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

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
  LPBYTE lpData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbMaxValueLen; // [rsp+74h] [rbp-8Ch] BYREF
  LPWSTR lpValueName; // [rsp+78h] [rbp-88h] BYREF
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
    goto LABEL_20;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
    goto LABEL_20;
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpValueName,
    v0,
    2LL * cbMaxValueNameLen);
  if ( !lpValueName )
  {
    v2 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x547,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)0x8007000ELL,
      phkResult);
LABEL_16:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpValueName);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_24;
  }
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
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpData);
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
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpData);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpValueName);
  v8 = (const unsigned __int16 *)v19[0];
  if ( !v19[0] || !*(_WORD *)v19[0] )
LABEL_20:
    v8 = L"Nothing is holding a reference to NTUSER.DAT";
  ProfileTelemetry::RecordHiveList::Stop((ProfileTelemetry::RecordHiveList *)v20, v8);
  if ( hKey )
    RegCloseKey(hKey);
  v2 = 0;
LABEL_24:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v19);
  ProfileTelemetry::RecordHiveList::~RecordHiveList((ProfileTelemetry::RecordHiveList *)v20);
  return v2;
}

```

## disassembly

```asm
0x18002e9e0  push    rbp
0x18002e9e2  push    rbx
0x18002e9e3  push    rsi
0x18002e9e4  push    rdi
0x18002e9e5  lea     rbp, [rsp-118h]
0x18002e9ed  sub     rsp, 218h
0x18002e9f4  mov     rax, cs:__security_cookie
0x18002e9fb  xor     rax, rsp
0x18002e9fe  mov     [rbp+130h+var_30], rax
0x18002ea05  xor     esi, esi
0x18002ea07  lea     rcx, [rbp+130h+var_180]; struct wil::details::IFailureCallback *
0x18002ea0b  call    ??0?$ActivityBase@VProfileLogging@@$00$0CAAAAAAAAAAA@$03$0IBAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,35184372088832,4,2164260864,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,35184372088832,4,2164260864,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002ea10  lea     rax, ??_7RecordHiveList@ProfileTelemetry@@6B@; const ProfileTelemetry::RecordHiveList::`vftable'
0x18002ea17  mov     [rbp+130h+var_180], rax
0x18002ea1b  lea     rcx, [rbp+130h+var_180]; this
0x18002ea1f  call    ?StartActivity@RecordHiveList@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::RecordHiveList::StartActivity(void)
0x18002ea24  nop
0x18002ea25  mov     [rbp+130h+var_1A0], rsi
0x18002ea29  mov     [rbp+130h+var_198], rsi
0x18002ea2d  mov     [rbp+130h+var_190], rsi
0x18002ea31  mov     [rsp+230h+hKey], rsi
0x18002ea36  xor     edx, edx
0x18002ea38  lea     rcx, [rsp+230h+hKey]
0x18002ea3d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002ea42  lea     rax, [rsp+230h+hKey]
0x18002ea47  mov     [rsp+230h+phkResult], rax; phkResult
0x18002ea4c  lea     r9d, [rsi+1]; samDesired
0x18002ea50  xor     r8d, r8d; ulOptions
0x18002ea53  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Hiv"...
0x18002ea5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ea61  call    cs:__imp_RegOpenKeyExW
0x18002ea67  test    eax, eax
0x18002ea69  jnz     loc_18002EC78
0x18002ea6f  mov     [rbp+130h+cValues], esi
0x18002ea72  mov     [rsp+230h+cbMaxValueNameLen], esi
0x18002ea76  mov     [rsp+230h+cbMaxValueLen], esi
0x18002ea7a  mov     [rsp+230h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18002ea7f  mov     [rsp+230h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18002ea84  lea     rax, [rsp+230h+cbMaxValueLen]
0x18002ea89  mov     [rsp+230h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18002ea8e  lea     rax, [rsp+230h+cbMaxValueNameLen]
0x18002ea93  mov     [rsp+230h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18002ea98  lea     rax, [rbp+130h+cValues]
0x18002ea9c  mov     [rsp+230h+lpcValues], rax; lpcValues
0x18002eaa1  mov     [rsp+230h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18002eaa6  mov     [rsp+230h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18002eaab  mov     [rsp+230h+phkResult], rsi; int
0x18002eab0  xor     r9d, r9d; lpReserved
0x18002eab3  xor     r8d, r8d; lpcchClass
0x18002eab6  xor     edx, edx; lpClass
0x18002eab8  mov     rcx, [rsp+230h+hKey]; hKey
0x18002eabd  call    cs:__imp_RegQueryInfoKeyW
0x18002eac3  test    eax, eax
0x18002eac5  jnz     loc_18002EC78
0x18002eacb  mov     r8d, [rsp+230h+cbMaxValueNameLen]
0x18002ead0  add     r8, r8
0x18002ead3  lea     rcx, [rsp+230h+lpValueName]
0x18002ead8  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002eadd  nop
0x18002eade  cmp     [rsp+230h+lpValueName], rsi
0x18002eae3  jnz     short loc_18002EB0A
0x18002eae5  mov     rcx, [rbp+138h]; this
0x18002eaec  mov     ebx, 8007000Eh
0x18002eaf1  mov     r9d, ebx; char *
0x18002eaf4  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002eafb  mov     edx, 547h; void *
0x18002eb00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eb05  jmp     loc_18002EC38
0x18002eb0a  mov     r8d, [rsp+230h+cbMaxValueLen]
0x18002eb0f  lea     rcx, [rsp+230h+lpData]
0x18002eb14  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002eb19  mov     rax, [rsp+230h+lpData]
0x18002eb1e  test    rax, rax
0x18002eb21  jnz     short loc_18002EB35
0x18002eb23  mov     ebx, 8007000Eh
0x18002eb28  mov     r9d, ebx
0x18002eb2b  mov     edx, 54Ah
0x18002eb30  jmp     loc_18002EC1A
0x18002eb35  mov     edi, esi
0x18002eb37  cmp     edi, [rbp+130h+cValues]
0x18002eb3a  jnb     loc_18002EC55
0x18002eb40  mov     ecx, [rsp+230h+cbMaxValueNameLen]
0x18002eb44  add     ecx, ecx
0x18002eb46  mov     [rbp+130h+cchValueName], ecx
0x18002eb49  mov     ecx, [rsp+230h+cbMaxValueLen]
0x18002eb4d  mov     [rbp+130h+cbData], ecx
0x18002eb50  lea     rcx, [rbp+130h+cbData]
0x18002eb54  mov     [rsp+230h+lpcValues], rcx; lpcbData
0x18002eb59  mov     [rsp+230h+lpcbMaxClassLen], rax; lpData
0x18002eb5e  mov     [rsp+230h+lpcbMaxSubKeyLen], rsi; lpType
0x18002eb63  mov     [rsp+230h+phkResult], rsi; lpReserved
0x18002eb68  lea     r9, [rbp+130h+cchValueName]; lpcchValueName
0x18002eb6c  mov     r8, [rsp+230h+lpValueName]; lpValueName
0x18002eb71  mov     edx, edi; dwIndex
0x18002eb73  mov     rcx, [rsp+230h+hKey]; hKey
0x18002eb78  call    cs:__imp_RegEnumValueW
0x18002eb7e  test    eax, eax
0x18002eb80  jnz     loc_18002EC06
0x18002eb86  mov     dword ptr [rsp+230h+lpcbMaxSubKeyLen], 1; bIgnoreCase
0x18002eb8e  mov     dword ptr [rsp+230h+phkResult], 0FFFFFFFFh; cchValue
0x18002eb96  lea     r9, StringValue; "\\Users\\"
0x18002eb9d  or      r8d, 0FFFFFFFFh; cchSource
0x18002eba1  mov     rdx, [rsp+230h+lpData]; lpStringSource
0x18002eba6  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x18002ebab  call    cs:__imp_FindStringOrdinal
0x18002ebb1  cmp     eax, 0FFFFFFFFh
0x18002ebb4  jz      short loc_18002EC06
0x18002ebb6  mov     dword ptr [rsp+230h+lpcbMaxSubKeyLen], 1; bIgnoreCase
0x18002ebbe  mov     dword ptr [rsp+230h+phkResult], 0FFFFFFFFh; int
0x18002ebc6  lea     r9, aNtuserDat_0; "\\NTUSER.DAT"
0x18002ebcd  or      r8d, 0FFFFFFFFh; cchSource
0x18002ebd1  mov     rdx, [rsp+230h+lpData]; lpStringSource
0x18002ebd6  mov     ecx, 200000h; dwFindStringOrdinalFlags
0x18002ebdb  call    cs:__imp_FindStringOrdinal
0x18002ebe1  cmp     eax, 0FFFFFFFFh
0x18002ebe4  jz      short loc_18002EC06
0x18002ebe6  mov     r9, [rsp+230h+lpData]
0x18002ebeb  mov     r8, [rsp+230h+lpValueName]
0x18002ebf0  lea     rdx, aSS_2; "%s\t\t%s\n"
0x18002ebf7  lea     rcx, [rbp+130h+var_1A0]
0x18002ebfb  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18002ec00  mov     ebx, eax
0x18002ec02  test    eax, eax
0x18002ec04  js      short loc_18002EC12
0x18002ec06  inc     edi
0x18002ec08  mov     rax, [rsp+230h+lpData]
0x18002ec0d  jmp     loc_18002EB37
0x18002ec12  mov     r9d, eax; char *
0x18002ec15  mov     edx, 557h; void *
0x18002ec1a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ec21  mov     rcx, [rbp+138h]; this
0x18002ec28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ec2d  lea     rcx, [rsp+230h+lpData]
0x18002ec32  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ec37  nop
0x18002ec38  lea     rcx, [rsp+230h+lpValueName]
0x18002ec3d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ec42  nop
0x18002ec43  mov     rcx, [rsp+230h+hKey]; hKey
0x18002ec48  test    rcx, rcx
0x18002ec4b  jz      short loc_18002EC9B
0x18002ec4d  call    cs:__imp_RegCloseKey
0x18002ec53  jmp     short loc_18002EC9B
0x18002ec55  lea     rcx, [rsp+230h+lpData]
0x18002ec5a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ec5f  nop
0x18002ec60  lea     rcx, [rsp+230h+lpValueName]
0x18002ec65  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ec6a  mov     rdx, [rbp+130h+var_1A0]
0x18002ec6e  test    rdx, rdx
0x18002ec71  jz      short loc_18002EC78
0x18002ec73  cmp     [rdx], si
0x18002ec76  jnz     short loc_18002EC7F
0x18002ec78  lea     rdx, aNothingIsHoldi; "Nothing is holding a reference to NTUSE"...
0x18002ec7f  lea     rcx, [rbp+130h+var_180]; this
0x18002ec83  call    ?Stop@RecordHiveList@ProfileTelemetry@@QEAAXPEBG@Z; ProfileTelemetry::RecordHiveList::Stop(ushort const *)
0x18002ec88  nop
0x18002ec89  mov     rcx, [rsp+230h+hKey]; hKey
0x18002ec8e  test    rcx, rcx
0x18002ec91  jz      short loc_18002EC99
0x18002ec93  call    cs:__imp_RegCloseKey
0x18002ec99  mov     ebx, esi
0x18002ec9b  lea     rcx, [rbp+130h+var_1A0]
0x18002ec9f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002eca4  nop
0x18002eca5  lea     rcx, [rbp+130h+var_180]; this
0x18002eca9  call    ??1RecordHiveList@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::RecordHiveList::~RecordHiveList(void)
0x18002ecae  mov     eax, ebx
0x18002ecb0  mov     rcx, [rbp+130h+var_30]
0x18002ecb7  xor     rcx, rsp; StackCookie
0x18002ecba  call    __security_check_cookie
0x18002ecbf  add     rsp, 218h
0x18002ecc6  pop     rdi
0x18002ecc7  pop     rsi
0x18002ecc8  pop     rbx
0x18002ecc9  pop     rbp
0x18002ecca  retn
```
