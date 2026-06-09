# RegistrationStoreData::PrivateHive::GetUserHivePath(void *,HSTRING__ *,HSTRING__ * *)

- ea: `0x18010f24c`
- end: `0x18010f5d8`
- name: `?GetUserHivePath@PrivateHive@RegistrationStoreData@@SAJPEAXPEAUHSTRING__@@PEAPEAU3@@Z`
- size: `908`
- prototype: `__int64 __fastcall(void *userToken, HSTRING packageId, HSTRING__ **pPrivateHivePath)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043198`
- `0x180059250`

## callees

- `0x1800417b0`
- `0x18005e3f0`
- `0x18005fca0`
- `0x180086714`
- `0x180087660`
- `0x18008db2c`
- `0x1800a6f50`
- `0x1800c4250`
- `0x1800d92b8`
- `0x1800f5294`
- `0x18010db34`
- `0x18010f24c`
- `0x1801999b0`
- `0x18019a654`
- `0x18019c220`
- `0x18019c59c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f4c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f4c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f528`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x18010f2e5`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x18010f2e5`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x18010f379`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x18010f379`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateRootFolderBase` at `0x18010f39a`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateRootFolderBase` at `0x18010f40c`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateRootFolderBase` at `0x18010f39a`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateRootFolderBase` at `0x18010f40c`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseState` at `0x18010f51d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseState` at `0x18010f51d`

## string_xrefs

- `0x18010f35c`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x18010f50e`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x18010f5a3`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x18010f34a`: `RegistrationStoreData::PrivateHive::GetUserHivePath`
- `0x18010f4f9`: `RegistrationStoreData::PrivateHive::GetUserHivePath`
- `0x18010f594`: `RegistrationStoreData::PrivateHive::GetUserHivePath`

## pseudocode

```c
__int64 __fastcall RegistrationStoreData::PrivateHive::GetUserHivePath(
        void *userToken,
        HSTRING packageId,
        HSTRING__ **pPrivateHivePath)
{
  unsigned __int64 v6; // r14
  const wchar_t *StringRawBuffer; // rax
  LONG v8; // eax
  HRESULT hstring_from_buffer_nothrow; // ebx
  __int64 v10; // rax
  __int64 v11; // rsi
  UINT32 StringLen; // eax
  UINT32 v13; // r15d
  wchar_t *v14; // rdi
  const wchar_t *v15; // r8
  HRESULT v16; // eax
  signed int v17; // eax
  const wchar_t *v18; // rax
  signed int LastError; // eax
  signed int v20; // eax
  int v21; // r8d
  unsigned int cchDest; // [rsp+28h] [rbp-B1h]
  unsigned int cchStateRoot; // [rsp+30h] [rbp-A9h] BYREF
  unsigned __int64 cchRemaining; // [rsp+38h] [rbp-A1h] BYREF
  wchar_t *pszEnd; // [rsp+40h] [rbp-99h] BYREF
  unsigned int cchPackageFamilyName; // [rsp+48h] [rbp-91h] BYREF
  wchar_t *pszPrivateHivePath; // [rsp+50h] [rbp-89h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (__cdecl*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer,wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t> > > stringBuffer; // [rsp+58h] [rbp-81h] BYREF
  wchar_t szPackageFamilyName[72]; // [rsp+60h] [rbp-79h] BYREF

  v6 = 0;
  if ( !IsPackageFullNameFromIdPresent()
    || !IsOpenStateExplicitPresent()
    || !IsOpenStateExplicitPresent()
    || !IsOpenStateExplicitPresent() )
  {
    hstring_from_buffer_nothrow = -2147023728;
    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      return (unsigned int)hstring_from_buffer_nothrow;
    v21 = 178;
LABEL_45:
    ComTraceMessageT<long>(
      "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
      "RegistrationStoreData::PrivateHive::GetUserHivePath",
      v21,
      ERRORS,
      L"hr:%!HRESULT!",
      hstring_from_buffer_nothrow);
    return (unsigned int)hstring_from_buffer_nothrow;
  }
  memset_0(szPackageFamilyName, 0, 0x82u);
  cchPackageFamilyName = 65;
  StringRawBuffer = WindowsGetStringRawBuffer(packageId, 0);
  v8 = PackageFamilyNameFromFullName(StringRawBuffer, &cchPackageFamilyName, szPackageFamilyName);
  hstring_from_buffer_nothrow = v8;
  if ( v8 > 0 )
    hstring_from_buffer_nothrow = (unsigned __int16)v8 | 0x80070000;
  if ( hstring_from_buffer_nothrow >= 0 )
  {
    if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
      goto LABEL_15;
  }
  else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
  {
    return (unsigned int)hstring_from_buffer_nothrow;
  }
  cchDest = hstring_from_buffer_nothrow;
  ComTraceHr(
    hstring_from_buffer_nothrow,
    "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
    "RegistrationStoreData::PrivateHive::GetUserHivePath",
    189,
    L"hr:%!HRESULT!");
  if ( hstring_from_buffer_nothrow < 0 )
    return (unsigned int)hstring_from_buffer_nothrow;
LABEL_15:
  v10 = OpenStateExplicit(userToken, szPackageFamilyName);
  v11 = v10;
  if ( v10 )
  {
    cchStateRoot = 0;
    if ( (unsigned int)GetStateRootFolderBase(v10, 0, &cchStateRoot) || GetLastError() != 122 )
    {
      LastError = GetLastError();
      hstring_from_buffer_nothrow = LastError;
      if ( LastError > 0 )
        hstring_from_buffer_nothrow = (unsigned __int16)LastError | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
          "RegistrationStoreData::PrivateHive::GetUserHivePath",
          245,
          ERRORS,
          L"hr:%!HRESULT!",
          hstring_from_buffer_nothrow);
    }
    else
    {
      StringLen = WindowsGetStringLen(packageId);
      pszPrivateHivePath = 0;
      v13 = StringLen + cchStateRoot + 38;
      stringBuffer.m_ptr = 0;
      hstring_from_buffer_nothrow = WindowsPreallocateStringBuffer(v13 - 1, &pszPrivateHivePath, &stringBuffer.m_ptr);
      if ( hstring_from_buffer_nothrow >= 0 )
      {
        pszEnd = 0;
        v14 = 0;
        cchRemaining = 0;
        if ( (unsigned int)GetStateRootFolderBase(v11, pszPrivateHivePath, &cchStateRoot) )
        {
          v16 = StringCchCatExW(pszPrivateHivePath, v13, v15, &pszEnd, &cchRemaining, cchDest);
          v14 = pszEnd;
          hstring_from_buffer_nothrow = v16;
          v6 = cchRemaining;
        }
        else
        {
          v17 = GetLastError();
          hstring_from_buffer_nothrow = v17;
          if ( v17 > 0 )
            hstring_from_buffer_nothrow = (unsigned __int16)v17 | 0x80070000;
        }
        if ( hstring_from_buffer_nothrow >= 0 )
        {
          v18 = WindowsGetStringRawBuffer(packageId, 0);
          hstring_from_buffer_nothrow = StringCchCopyExW(v14, v6, v18, &pszEnd, &cchRemaining, 0);
          if ( hstring_from_buffer_nothrow >= 0 )
          {
            hstring_from_buffer_nothrow = StringCchCopyW(
                                            pszEnd,
                                            cchRemaining,
                                            L"\\ActivationStore\\ActivationStore.dat");
            if ( hstring_from_buffer_nothrow >= 0 )
              hstring_from_buffer_nothrow = wil::make_hstring_from_buffer_nothrow(&stringBuffer, pPrivateHivePath);
          }
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&stringBuffer);
    }
    CloseState(v11);
    return (unsigned int)hstring_from_buffer_nothrow;
  }
  v20 = GetLastError();
  hstring_from_buffer_nothrow = v20;
  if ( v20 > 0 )
    hstring_from_buffer_nothrow = (unsigned __int16)v20 | 0x80070000;
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
  {
    v21 = 253;
    goto LABEL_45;
  }
  return (unsigned int)hstring_from_buffer_nothrow;
}

```

## disassembly

```asm
0x18010f24c  mov     [rsp-8+arg_18], rbx
0x18010f251  push    rbp
0x18010f252  push    rsi
0x18010f253  push    rdi
0x18010f254  push    r12
0x18010f256  push    r13
0x18010f258  push    r14
0x18010f25a  push    r15
0x18010f25c  lea     rbp, [rsp-27h]
0x18010f261  sub     rsp, 100h
0x18010f268  mov     rax, cs:__security_cookie
0x18010f26f  xor     rax, rsp
0x18010f272  mov     [rbp+57h+var_40], rax
0x18010f276  mov     r13, pPrivateHivePath
0x18010f279  mov     r12, packageId
0x18010f27c  mov     rsi, userToken
0x18010f27f  call    IsPackageFullNameFromIdPresent
0x18010f284  xor     r14d, r14d
0x18010f287  test    al, al
0x18010f289  jz      loc_18010F560
0x18010f28f  call    IsOpenStateExplicitPresent
0x18010f294  test    al, al
0x18010f296  jz      loc_18010F560
0x18010f29c  call    IsOpenStateExplicitPresent
0x18010f2a1  test    al, al
0x18010f2a3  jz      loc_18010F560
0x18010f2a9  call    IsOpenStateExplicitPresent
0x18010f2ae  test    al, al
0x18010f2b0  jz      loc_18010F560
0x18010f2b6  xor     edx, edx; Val
0x18010f2b8  lea     userToken, [rbp+57h+szPackageFamilyName]; void *
0x18010f2bc  mov     r8d, 82h; Size
0x18010f2c2  call    memset_0
0x18010f2c7  xor     edx, edx; length
0x18010f2c9  mov     [rsp+130h+cchPackageFamilyName], 41h ; 'A'
0x18010f2d1  mov     userToken, r12; string
0x18010f2d4  call    WindowsGetStringRawBuffer
0x18010f2d9  mov     userToken, rax; packageFullName
0x18010f2dc  lea     pPrivateHivePath, [rbp+57h+szPackageFamilyName]; packageFamilyName
0x18010f2e0  lea     packageId, [rsp+130h+cchPackageFamilyName]; packageFamilyNameLength
0x18010f2e5  call    cs:__imp_PackageFamilyNameFromFullName
0x18010f2eb  mov     ebx, eax
0x18010f2ed  mov     r15d, 80070000h
0x18010f2f3  test    eax, eax
0x18010f2f5  jle     short loc_18010F2FD
0x18010f2f7  movzx   ebx, ax
0x18010f2fa  or      ebx, r15d
0x18010f2fd  lea     rdi, aHrHresult; "hr:%!HRESULT!"
0x18010f304  test    ebx, ebx
0x18010f306  jns     short loc_18010F32F
0x18010f308  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18010f30e  test    eax, eax
0x18010f310  jnz     short loc_18010F346
0x18010f312  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18010f319  jz      loc_18010F5AF
0x18010f31f  xor     ecx, ecx; level
0x18010f321  call    IsWppLevelEnabled
0x18010f326  test    al, al
0x18010f328  jnz     short loc_18010F346
0x18010f32a  jmp     loc_18010F5AF
0x18010f32f  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18010f336  jz      short loc_18010F372
0x18010f338  mov     ecx, 3; level
0x18010f33d  call    IsWppLevelEnabled
0x18010f342  test    al, al
0x18010f344  jz      short loc_18010F372
0x18010f346  mov     [rsp+130h+cchDest], ebx; cchDest
0x18010f34a  lea     pPrivateHivePath, aRegistrationst_23; "RegistrationStoreData::PrivateHive::Get"...
0x18010f351  mov     r9d, 0BDh; line
0x18010f357  mov     [rsp+130h+format], rdi; format
0x18010f35c  lea     packageId, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x18010f363  mov     ecx, ebx; hr
0x18010f365  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x18010f36a  test    ebx, ebx
0x18010f36c  js      loc_18010F5AF
0x18010f372  lea     packageId, [rbp+57h+szPackageFamilyName]
0x18010f376  mov     userToken, rsi
0x18010f379  call    cs:__imp_OpenStateExplicit
0x18010f37f  mov     rsi, rax
0x18010f382  test    rax, rax
0x18010f385  jz      loc_18010F528
0x18010f38b  lea     pPrivateHivePath, [rsp+130h+cchStateRoot]
0x18010f390  mov     [rsp+130h+cchStateRoot], r14d
0x18010f395  xor     edx, edx
0x18010f397  mov     userToken, rax
0x18010f39a  call    cs:__imp_GetStateRootFolderBase
0x18010f3a0  test    eax, eax
0x18010f3a2  jnz     loc_18010F4C5
0x18010f3a8  call    cs:__imp_GetLastError
0x18010f3ae  cmp     eax, 7Ah ; 'z'
0x18010f3b1  jnz     loc_18010F4C5
0x18010f3b7  mov     userToken, r12; string
0x18010f3ba  call    WindowsGetStringLen
0x18010f3bf  mov     r15d, [rsp+130h+cchStateRoot]
0x18010f3c4  lea     pPrivateHivePath, [rsp+130h+stringBuffer]; bufferHandle
0x18010f3c9  add     r15d, 26h ; '&'
0x18010f3cd  mov     [rsp+130h+pszPrivateHivePath], r14
0x18010f3d2  add     r15d, eax
0x18010f3d5  mov     [rsp+130h+stringBuffer.m_ptr], r14
0x18010f3da  lea     packageId, [rsp+130h+pszPrivateHivePath]; charBuffer
0x18010f3df  lea     ecx, [r15-1]; length
0x18010f3e3  call    WindowsPreallocateStringBuffer
0x18010f3e8  mov     ebx, eax
0x18010f3ea  test    eax, eax
0x18010f3ec  js      loc_18010F4B9
0x18010f3f2  mov     packageId, [rsp+130h+pszPrivateHivePath]
0x18010f3f7  lea     pPrivateHivePath, [rsp+130h+cchStateRoot]
0x18010f3fc  mov     userToken, rsi
0x18010f3ff  mov     [rsp+130h+pszEnd], r14
0x18010f404  mov     rdi, r14
0x18010f407  mov     [rsp+130h+cchRemaining], r14
0x18010f40c  call    cs:__imp_GetStateRootFolderBase
0x18010f412  test    eax, eax
0x18010f414  jz      short loc_18010F440
0x18010f416  mov     userToken, [rsp+130h+pszPrivateHivePath]; pszDest
0x18010f41b  lea     rax, [rsp+130h+cchRemaining]
0x18010f420  mov     edx, r15d; cchDest
0x18010f423  lea     r9, [rsp+130h+pszEnd]; pcchRemaining
0x18010f428  mov     [rsp+130h+format], rax; pszDest
0x18010f42d  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18010f432  mov     rdi, [rsp+130h+pszEnd]
0x18010f437  mov     ebx, eax
0x18010f439  mov     r14, [rsp+130h+cchRemaining]
0x18010f43e  jmp     short loc_18010F455
0x18010f440  call    cs:__imp_GetLastError
0x18010f446  mov     ebx, eax
0x18010f448  test    eax, eax
0x18010f44a  jle     short loc_18010F455
0x18010f44c  movzx   ebx, ax
0x18010f44f  or      ebx, 80070000h
0x18010f455  test    ebx, ebx
0x18010f457  js      short loc_18010F4B9
0x18010f459  xor     edx, edx; length
0x18010f45b  mov     userToken, r12; string
0x18010f45e  call    WindowsGetStringRawBuffer
0x18010f463  lea     userToken, [rsp+130h+cchRemaining]
0x18010f468  mov     [rsp+130h+cchDest], 0; dwFlags
0x18010f470  mov     [rsp+130h+format], userToken; pcchRemaining
0x18010f475  lea     r9, [rsp+130h+pszEnd]; ppszDestEnd
0x18010f47a  mov     userToken, rdi; pszDest
0x18010f47d  mov     pPrivateHivePath, rax; pszSrc
0x18010f480  mov     packageId, r14; cchDest
0x18010f483  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18010f488  mov     ebx, eax
0x18010f48a  test    eax, eax
0x18010f48c  js      short loc_18010F4B9
0x18010f48e  mov     packageId, [rsp+130h+cchRemaining]; cchDest
0x18010f493  lea     pPrivateHivePath, aActivationstor_0; "\\ActivationStore\\ActivationStore.dat"
0x18010f49a  mov     userToken, [rsp+130h+pszEnd]; pszDest
0x18010f49f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18010f4a4  mov     ebx, eax
0x18010f4a6  test    eax, eax
0x18010f4a8  js      short loc_18010F4B9
0x18010f4aa  mov     packageId, r13; promoted
0x18010f4ad  lea     userToken, [rsp+130h+stringBuffer]; source
0x18010f4b2  call    ?make_hstring_from_buffer_nothrow@wil@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAPEAUHSTRING__@@@Z; wil::make_hstring_from_buffer_nothrow(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>> &&,HSTRING__ * *)
0x18010f4b7  mov     ebx, eax
0x18010f4b9  lea     userToken, [rsp+130h+stringBuffer]; this
0x18010f4be  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x18010f4c3  jmp     short loc_18010F51A
0x18010f4c5  call    cs:__imp_GetLastError
0x18010f4cb  mov     ebx, eax
0x18010f4cd  test    eax, eax
0x18010f4cf  jle     short loc_18010F4D7
0x18010f4d1  movzx   ebx, ax
0x18010f4d4  or      ebx, r15d
0x18010f4d7  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18010f4dd  test    eax, eax
0x18010f4df  jnz     short loc_18010F4F5
0x18010f4e1  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18010f4e8  jz      short loc_18010F51A
0x18010f4ea  xor     ecx, ecx; level
0x18010f4ec  call    IsWppLevelEnabled
0x18010f4f1  test    al, al
0x18010f4f3  jz      short loc_18010F51A
0x18010f4f5  mov     [rsp+130h+cchDest], ebx; <args_0>
0x18010f4f9  lea     packageId, aRegistrationst_23; "RegistrationStoreData::PrivateHive::Get"...
0x18010f500  xor     r9d, r9d; level
0x18010f503  mov     [rsp+130h+format], rdi; format
0x18010f508  mov     r8d, 0F5h; line
0x18010f50e  lea     userToken, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x18010f515  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18010f51a  mov     userToken, rsi
0x18010f51d  call    cs:__imp_CloseState
0x18010f523  jmp     loc_18010F5AF
0x18010f528  call    cs:__imp_GetLastError
0x18010f52e  mov     ebx, eax
0x18010f530  test    eax, eax
0x18010f532  jle     short loc_18010F53A
0x18010f534  movzx   ebx, ax
0x18010f537  or      ebx, r15d
0x18010f53a  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18010f540  test    eax, eax
0x18010f542  jnz     short loc_18010F558
0x18010f544  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18010f54b  jz      short loc_18010F5AF
0x18010f54d  xor     ecx, ecx; level
0x18010f54f  call    IsWppLevelEnabled
0x18010f554  test    al, al
0x18010f556  jz      short loc_18010F5AF
0x18010f558  mov     r8d, 0FDh
0x18010f55e  jmp     short loc_18010F590
0x18010f560  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18010f566  mov     ebx, 80070490h
0x18010f56b  test    eax, eax
0x18010f56d  jnz     short loc_18010F583
0x18010f56f  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18010f576  jz      short loc_18010F5AF
0x18010f578  xor     ecx, ecx; level
0x18010f57a  call    IsWppLevelEnabled
0x18010f57f  test    al, al
0x18010f581  jz      short loc_18010F5AF
0x18010f583  lea     rdi, aHrHresult; "hr:%!HRESULT!"
0x18010f58a  mov     r8d, 0B2h; line
0x18010f590  mov     [rsp+130h+cchDest], ebx; <args_0>
0x18010f594  lea     packageId, aRegistrationst_23; "RegistrationStoreData::PrivateHive::Get"...
0x18010f59b  xor     r9d, r9d; level
0x18010f59e  mov     [rsp+130h+format], rdi; format
0x18010f5a3  lea     userToken, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x18010f5aa  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18010f5af  mov     eax, ebx
0x18010f5b1  mov     userToken, [rbp+57h+var_40]
0x18010f5b5  xor     userToken, rsp; StackCookie
0x18010f5b8  call    __security_check_cookie
0x18010f5bd  mov     rbx, [rsp+130h+arg_18]
0x18010f5c5  add     rsp, 100h
0x18010f5cc  pop     r15
0x18010f5ce  pop     r14
0x18010f5d0  pop     r13
0x18010f5d2  pop     r12
0x18010f5d4  pop     rdi
0x18010f5d5  pop     rsi
0x18010f5d6  pop     rbp
0x18010f5d7  retn
```
