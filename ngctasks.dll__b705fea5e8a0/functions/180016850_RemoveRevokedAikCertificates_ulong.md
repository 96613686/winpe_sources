# RemoveRevokedAikCertificates(ulong *)

- ea: `0x180016850`
- end: `0x180016b1c`
- name: `?RemoveRevokedAikCertificates@@YAJPEAK@Z`
- size: `716`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014c24`

## callees

- `0x180008c74`
- `0x18000cc34`
- `0x18000ebc0`
- `0x18000ef9c`
- `0x18000ff9c`
- `0x180010310`
- `0x180014bcc`
- `0x180016708`
- `0x180016850`
- `0x18001c9ac`
- `0x18001cd5c`
- `0x18001d954`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800169d9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800169d9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800169a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800169a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800168d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800168d6`
- `ncrypt!NCryptSetProperty` at `0x180016a2c`
- `ncrypt!NCryptSetProperty` at `0x180016a2c`

## string_xrefs

- `0x18001688f`: `onecore\ds\security\ngc\ngctask\dll\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall RemoveRevokedAikCertificates(unsigned int *a1)
{
  const unsigned __int16 *v2; // rdx
  NgcUtils *v3; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  LSTATUS v5; // eax
  unsigned int *v6; // r9
  signed int v7; // ebx
  int RegistrySubKeys; // eax
  const char *v9; // r9
  DWORD v10; // edi
  WCHAR *v11; // r8
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  unsigned __int64 *v14; // r8
  int v15; // eax
  wil::details::in1diag3 *v16; // rcx
  __int64 v17; // rdx
  int phkResult; // [rsp+20h] [rbp-40h]
  int phkResulta; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR lpName; // [rsp+48h] [rbp-18h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD cchName; // [rsp+90h] [rbp+30h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+98h] [rbp+38h] BYREF

  *a1 = 0;
  lpSubKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v3,
                                        v2,
                                        L"PregenKeys\\RevokedAIK",
                                        (unsigned __int16 *)lpSubKey);
  if ( NgcStateSeparatedRegistryLocation < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC5,
      (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0xF003Fu, &hKey);
  v7 = v5;
  if ( v5 > 0 )
    v7 = (unsigned __int16)v5 | 0x80070000;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
      (const char *)(unsigned int)v7,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_29;
  }
  cchName = 0;
  LODWORD(hObject) = 0;
  RegistrySubKeys = NgcUtils::QueryRegistrySubKeys((NgcUtils *)hKey, (HKEY)&cchName, (unsigned int *)&hObject, v6);
  v7 = RegistrySubKeys;
  if ( RegistrySubKeys < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
      (const char *)(unsigned int)RegistrySubKeys,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_29;
  }
  if ( !cchName )
    goto LABEL_28;
  v10 = hObject + 1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpName,
    0,
    (unsigned int)(hObject + 1),
    v9);
  v11 = lpName;
  if ( !lpName )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
      (const char *)0x8007000ELL,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_29;
  }
  while ( 1 )
  {
    cchName = v10;
    v12 = RegEnumKeyExW(hKey, 0, v11, &cchName, 0, 0, 0, 0);
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v7 == -2147024637 )
      break;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF7,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
        (const char *)(unsigned int)v7,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpName);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_29;
    }
    v13 = RegDeleteKeyExW(hKey, lpName, 0, 0);
    v7 = v13;
    if ( v13 > 0 )
      v7 = (unsigned __int16)v13 | 0x80070000;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFD,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
        (const char *)(unsigned int)v7,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpName);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_29;
    }
    hObject = 0;
    v15 = NgcUtils::OpenAikNCryptHandle((NgcUtils *)lpName, (unsigned __int16 *)&hObject, v14);
    v16 = retaddr;
    if ( v15 < 0 )
    {
      v17 = 261;
LABEL_22:
      wil::details::in1diag3::_Log_Hr(
        v16,
        (void *)v17,
        (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\utilities.cpp",
        (const char *)(unsigned int)v15);
      goto LABEL_24;
    }
    v15 = NCryptSetProperty(hObject, L"SmartCardKeyCertificate", 0, 0, 0);
    v16 = retaddr;
    if ( v15 < 0 )
    {
      v17 = 272;
      goto LABEL_22;
    }
    ++*a1;
LABEL_24:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    v11 = lpName;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpName);
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  v7 = 0;
LABEL_29:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)lpSubKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180016850  mov     [rsp-28h+arg_10], rbx
0x180016855  push    rbp
0x180016856  push    rsi
0x180016857  push    rdi
0x180016858  push    r14
0x18001685a  push    r15
0x18001685c  mov     rbp, rsp
0x18001685f  sub     rsp, 60h
0x180016863  mov     rsi, rcx
0x180016866  xor     r14d, r14d
0x180016869  mov     [rcx], r14d
0x18001686c  mov     [rbp+lpSubKey], r14
0x180016870  xor     edx, edx
0x180016872  lea     rcx, [rbp+lpSubKey]
0x180016876  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001687b  lea     r9, [rbp+lpSubKey]; unsigned __int16 *
0x18001687f  lea     r8, aPregenkeysRevo; "PregenKeys\\RevokedAIK"
0x180016886  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001688b  mov     rcx, [rbp+28h]; this
0x18001688f  lea     r15, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016896  test    eax, eax
0x180016898  jns     short loc_1800168AA
0x18001689a  mov     r9d, eax; char *
0x18001689d  mov     r8, r15; unsigned int
0x1800168a0  mov     edx, 0C5h; void *
0x1800168a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800168aa  mov     [rbp+hKey], r14
0x1800168ae  xor     edx, edx
0x1800168b0  lea     rcx, [rbp+hKey]
0x1800168b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800168b9  lea     rax, [rbp+hKey]
0x1800168bd  mov     [rsp+60h+phkResult], rax; int
0x1800168c2  mov     r9d, 0F003Fh; samDesired
0x1800168c8  xor     r8d, r8d; ulOptions
0x1800168cb  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800168cf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800168d6  call    cs:__imp_RegOpenKeyExW
0x1800168dc  mov     ebx, eax
0x1800168de  test    eax, eax
0x1800168e0  jle     short loc_1800168EB
0x1800168e2  movzx   ebx, ax
0x1800168e5  or      ebx, 80070000h
0x1800168eb  test    ebx, ebx
0x1800168ed  jns     short loc_180016913
0x1800168ef  mov     rcx, [rbp+28h]; this
0x1800168f3  mov     r9d, ebx; char *
0x1800168f6  mov     r8, r15; unsigned int
0x1800168f9  mov     edx, 0CEh; void *
0x1800168fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016903  nop
0x180016904  lea     rcx, [rbp+hKey]
0x180016908  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001690d  nop
0x18001690e  jmp     loc_180016ACD
0x180016913  mov     [rbp+cchName], r14d
0x180016917  mov     dword ptr [rbp+hObject], r14d
0x18001691b  lea     r8, [rbp+hObject]; unsigned int *
0x18001691f  lea     rdx, [rbp+cchName]; HKEY
0x180016923  mov     rcx, [rbp+hKey]; this
0x180016927  call    ?QueryRegistrySubKeys@NgcUtils@@YAJPEAUHKEY__@@PEAK1@Z; NgcUtils::QueryRegistrySubKeys(HKEY__ *,ulong *,ulong *)
0x18001692c  mov     ebx, eax
0x18001692e  test    eax, eax
0x180016930  jns     short loc_180016956
0x180016932  mov     rcx, [rbp+28h]; this
0x180016936  mov     r9d, eax; char *
0x180016939  mov     r8, r15; unsigned int
0x18001693c  mov     edx, 0D6h; void *
0x180016941  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016946  nop
0x180016947  lea     rcx, [rbp+hKey]
0x18001694b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016950  nop
0x180016951  jmp     loc_180016ACD
0x180016956  cmp     [rbp+cchName], r14d
0x18001695a  jbe     loc_180016AC0
0x180016960  mov     edi, dword ptr [rbp+hObject]
0x180016963  inc     edi
0x180016965  mov     r8d, edi
0x180016968  xor     edx, edx
0x18001696a  lea     rcx, [rbp+lpName]
0x18001696e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180016973  nop
0x180016974  mov     r8, [rbp+lpName]; lpName
0x180016978  test    r8, r8
0x18001697b  jz      loc_180016AEC
0x180016981  mov     [rbp+cchName], edi
0x180016984  mov     [rsp+60h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180016989  mov     [rsp+60h+lpcchClass], r14; lpcchClass
0x18001698e  mov     [rsp+60h+lpClass], r14; lpClass
0x180016993  mov     [rsp+60h+phkResult], r14; int
0x180016998  lea     r9, [rbp+cchName]; lpcchName
0x18001699c  xor     edx, edx; dwIndex
0x18001699e  mov     rcx, [rbp+hKey]; hKey
0x1800169a2  call    cs:__imp_RegEnumKeyExW
0x1800169a8  mov     ebx, eax
0x1800169aa  test    eax, eax
0x1800169ac  jle     short loc_1800169B7
0x1800169ae  movzx   ebx, ax
0x1800169b1  or      ebx, 80070000h
0x1800169b7  cmp     ebx, 80070103h
0x1800169bd  jz      loc_180016AB6
0x1800169c3  test    ebx, ebx
0x1800169c5  js      loc_180016A8B
0x1800169cb  xor     r9d, r9d; Reserved
0x1800169ce  xor     r8d, r8d; samDesired
0x1800169d1  mov     rdx, [rbp+lpName]; lpSubKey
0x1800169d5  mov     rcx, [rbp+hKey]; hKey
0x1800169d9  call    cs:__imp_RegDeleteKeyExW
0x1800169df  mov     ebx, eax
0x1800169e1  test    eax, eax
0x1800169e3  jle     short loc_1800169EE
0x1800169e5  movzx   ebx, ax
0x1800169e8  or      ebx, 80070000h
0x1800169ee  test    ebx, ebx
0x1800169f0  js      short loc_180016A60
0x1800169f2  mov     [rbp+hObject], r14
0x1800169f6  mov     [rbp+hObject], r14
0x1800169fa  lea     rdx, [rbp+hObject]; unsigned __int16 *
0x1800169fe  mov     rcx, [rbp+lpName]; this
0x180016a02  call    ?OpenAikNCryptHandle@NgcUtils@@YAJPEBGPEA_K@Z; NgcUtils::OpenAikNCryptHandle(ushort const *,unsigned __int64 *)
0x180016a07  mov     rcx, [rbp+28h]
0x180016a0b  test    eax, eax
0x180016a0d  jns     short loc_180016A16
0x180016a0f  mov     edx, 105h
0x180016a14  jmp     short loc_180016A3F
0x180016a16  mov     dword ptr [rsp+60h+phkResult], r14d; int
0x180016a1b  xor     r9d, r9d; cbInput
0x180016a1e  xor     r8d, r8d; pbInput
0x180016a21  lea     rdx, pszProperty; "SmartCardKeyCertificate"
0x180016a28  mov     rcx, [rbp+hObject]; hObject
0x180016a2c  call    cs:__imp_NCryptSetProperty
0x180016a32  mov     rcx, [rbp+28h]; this
0x180016a36  test    eax, eax
0x180016a38  jns     short loc_180016A4C
0x180016a3a  mov     edx, 110h; void *
0x180016a3f  mov     r8, r15; unsigned int
0x180016a42  mov     r9d, eax; char *
0x180016a45  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016a4a  jmp     short loc_180016A4E
0x180016a4c  inc     dword ptr [rsi]
0x180016a4e  lea     rcx, [rbp+hObject]
0x180016a52  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016a57  mov     r8, [rbp+lpName]
0x180016a5b  jmp     loc_180016981
0x180016a60  mov     rcx, [rbp+28h]; this
0x180016a64  mov     r9d, ebx; char *
0x180016a67  mov     r8, r15; unsigned int
0x180016a6a  mov     edx, 0FDh; void *
0x180016a6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a74  nop
0x180016a75  lea     rcx, [rbp+lpName]
0x180016a79  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016a7e  nop
0x180016a7f  lea     rcx, [rbp+hKey]
0x180016a83  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016a88  nop
0x180016a89  jmp     short loc_180016ACD
0x180016a8b  mov     rcx, [rbp+28h]; this
0x180016a8f  mov     r9d, ebx; char *
0x180016a92  mov     r8, r15; unsigned int
0x180016a95  mov     edx, 0F7h; void *
0x180016a9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a9f  nop
0x180016aa0  lea     rcx, [rbp+lpName]
0x180016aa4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016aa9  nop
0x180016aaa  lea     rcx, [rbp+hKey]
0x180016aae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016ab3  nop
0x180016ab4  jmp     short loc_180016ACD
0x180016ab6  lea     rcx, [rbp+lpName]
0x180016aba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016abf  nop
0x180016ac0  lea     rcx, [rbp+hKey]
0x180016ac4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016ac9  nop
0x180016aca  mov     ebx, r14d
0x180016acd  lea     rcx, [rbp+lpSubKey]
0x180016ad1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016ad6  mov     eax, ebx
0x180016ad8  mov     rbx, [rsp+60h+arg_10]
0x180016ae0  add     rsp, 60h
0x180016ae4  pop     r15
0x180016ae6  pop     r14
0x180016ae8  pop     rdi
0x180016ae9  pop     rsi
0x180016aea  pop     rbp
0x180016aeb  retn
0x180016aec  mov     rcx, [rbp+28h]; this
0x180016af0  mov     ebx, 8007000Eh
0x180016af5  mov     r9d, ebx; char *
0x180016af8  mov     r8, r15; unsigned int
0x180016afb  mov     edx, 0E2h; void *
0x180016b00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b05  nop
0x180016b06  lea     rcx, [rbp+lpName]
0x180016b0a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016b0f  nop
0x180016b10  lea     rcx, [rbp+hKey]
0x180016b14  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016b19  nop
0x180016b1a  jmp     short loc_180016ACD
```
