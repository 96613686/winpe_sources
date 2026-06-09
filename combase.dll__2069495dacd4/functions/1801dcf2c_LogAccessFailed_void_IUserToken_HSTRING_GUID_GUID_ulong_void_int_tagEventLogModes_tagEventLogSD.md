# LogAccessFailed(void *,IUserToken *,HSTRING__ *,_GUID *,_GUID *,ulong,void *,int,tagEventLogModes,tagEventLogSD)

- ea: `0x1801dcf2c`
- end: `0x1801dd7c7`
- name: `?LogAccessFailed@@YAXPEAXPEAUIUserToken@@PEAUHSTRING__@@PEAU_GUID@@3K0HW4tagEventLogModes@@W4tagEventLogSD@@@Z`
- size: `2203`
- prototype: `void __fastcall(void *hRpc, IUserToken *pAppId, HSTRING__ *pIID, _GUID *dwID, _GUID *hToken, unsigned int fRemote, void *enumSD, int hRpc, tagEventLogModes __formal, tagEventLogSD hsClassIdentifier)`
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028958`
- `0x180165ef0`

## callees

- `0x180020e14`
- `0x1800472a0`
- `0x180051420`
- `0x180051b34`
- `0x180059160`
- `0x18005cde8`
- `0x18005ce60`
- `0x1800865f4`
- `0x18008db2c`
- `0x1800a4730`
- `0x1800a6f50`
- `0x1800c4250`
- `0x180140fa0`
- `0x180152f44`
- `0x18015b904`
- `0x18018c89c`
- `0x18018d504`
- `0x18018f58c`
- `0x180190f68`
- `0x180193170`
- `0x180194274`
- `0x1801947d8`
- `0x1801999b0`
- `0x18019a654`
- `0x1801dc6d4`
- `0x1801dcddc`
- `0x1801dcf2c`
- `0x180209a68`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1801dd76b`
- `RPCRT4!RpcStringFreeW` at `0x1801dd76b`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x1801dd070`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x1801dd070`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1801dd6da`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1801dd6da`
- `ntdll!EtwEventRegister` at `0x1801dd690`
- `ntdll!EtwEventRegister` at `0x1801dd690`
- `ntdll!EtwEventUnregister` at `0x1801dd6e6`
- `ntdll!EtwEventUnregister` at `0x1801dd6e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dd70d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dd70d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801dd759`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801dd784`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801dd759`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801dd784`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801dd1bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801dd2cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801dd394`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801dd1bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801dd2cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801dd394`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801dd5c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801dd5c9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1801dd0fa`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1801dd0fa`

## string_xrefs

- `0x1801dd652`: `onecore\com\combase\catalog\services.cxx`
- `0x1801dd72a`: `onecore\com\combase\catalog\services.cxx`
- `0x1801dd65e`: `ClassIdentifier:%ws IID:%ws Type:%d Remote:%!bool! SID:%ws Domain:%ws User:%ws %!HRESULT!`
- `0x1801dd61d`: `LogAccessFailed`
- `0x1801dd71e`: `LogAccessFailed`

## pseudocode

```c
void __fastcall LogAccessFailed(
        void *hRpc,
        IUserToken *pAppId,
        HSTRING__ *pIID,
        _GUID *dwID,
        _GUID *hToken,
        unsigned int fRemote,
        void *enumSD,
        int hRpc_0,
        tagEventLogModes __formal,
        tagEventLogSD hsClassIdentifier)
{
  const wchar_t *v12; // rax
  int v13; // r10d
  const wchar_t *v14; // rax
  const wchar_t *v15; // rax
  const wchar_t *v16; // rax
  const wchar_t *v17; // rax
  const wchar_t *v18; // rax
  wchar_t *Myval2; // rdi
  void *UserSid; // rax
  void *v21; // r15
  const wchar_t *v22; // rax
  wchar_t *m_ptr; // rsi
  unsigned int v24; // ebx
  const wchar_t *v25; // rax
  int v26; // eax
  const wchar_t *v27; // rax
  const wchar_t *v28; // rax
  const wchar_t *v29; // rax
  const wchar_t *StringRawBuffer; // rax
  const wchar_t *v31; // rax
  const wchar_t *v32; // rax
  const wchar_t *v33; // rax
  const wchar_t *v34; // rax
  const wchar_t *v35; // r12
  _GUID *v36; // rsi
  LPWSTR v37; // r13
  __int64 v38; // rax
  PCWSTR v39; // rax
  int v40; // ebx
  DWORD LastError; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&PrivMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > applicationDisplayName; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *NetworkAddress; // [rsp+78h] [rbp-88h] BYREF
  void *pApplicationSid; // [rsp+80h] [rbp-80h] BYREF
  unsigned int type; // [rsp+88h] [rbp-78h] BYREF
  int v46; // [rsp+8Ch] [rbp-74h]
  unsigned __int64 LogHandle; // [rsp+90h] [rbp-70h] BYREF
  _SID_NAME_USE sidNameUse; // [rsp+98h] [rbp-68h] BYREF
  unsigned int dnamelen; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int unamelen; // [rsp+A0h] [rbp-60h] BYREF
  LPWSTR StringSid; // [rsp+A8h] [rbp-58h] BYREF
  _GUID *pGuid; // [rsp+B0h] [rbp-50h]
  void *hImp; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-40h]
  CGuidStr v55; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *Strings[11]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t wszAppID[40]; // [rsp+180h] [rbp+80h] BYREF
  wchar_t username[256]; // [rsp+1D0h] [rbp+D0h] BYREF
  wchar_t domainname[256]; // [rsp+3D0h] [rbp+2D0h] BYREF
  wchar_t sidAsText[256]; // [rsp+5D0h] [rbp+4D0h] BYREF
  wchar_t applicationSidAsText[256]; // [rsp+7D0h] [rbp+6D0h] BYREF
  wchar_t Module[264]; // [rsp+9D0h] [rbp+8D0h] BYREF

  pGuid = hToken;
  v46 = 2;
  v12 = ResourceStrings::Unavailable();
  StringCchCopyW(wszAppID, 0x27u, v12);
  if ( dwID
    && (*(_QWORD *)&dwID->Data1 != *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
     || *(_QWORD *)dwID->Data4 != *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4) )
  {
    wStringFromGUID2(dwID, wszAppID, v13);
  }
  sidNameUse = 0;
  unamelen = 256;
  dnamelen = 256;
  v14 = ResourceStrings::Unavailable();
  StringCchCopyW(username, 0x100u, v14);
  v15 = ResourceStrings::Unavailable();
  StringCchCopyW(domainname, 0x100u, v15);
  LODWORD(pApplicationSid) = 256;
  v16 = ResourceStrings::Unavailable();
  StringCchCopyW(sidAsText, 0x100u, v16);
  LODWORD(applicationDisplayName.m_ptr) = 256;
  v17 = ResourceStrings::Unavailable();
  StringCchCopyW(applicationSidAsText, 0x100u, v17);
  v18 = ResourceStrings::Unavailable();
  StringCchCopyW(Module, 0x104u, v18);
  NetworkAddress = 0;
  Myval2 = (wchar_t *)ResourceStrings::Unavailable();
  type = 4;
  if ( !I_RpcBindingInqTransportType(hRpc, &type) )
  {
    if ( type == 4 )
    {
      ResourceStrings::LoadResourceStrings();
      if ( !ResourceStrings::s_spResourceStrings._Mypair._Myval2
        || (Myval2 = ResourceStrings::s_spResourceStrings._Mypair._Myval2->_spRCLRPCAddress._Mypair._Myval2) == 0 )
      {
        Myval2 = (wchar_t *)ResourceStrings::s_defaultRCLRPCAddress;
      }
    }
    else
    {
      NetworkAddress = GetClientNetworkAddress(hRpc);
    }
  }
  UserSid = GetUserSid(enumSD);
  v21 = UserSid;
  if ( UserSid )
  {
    GetTextualSid(UserSid, sidAsText, (unsigned int *)&pApplicationSid);
    LookupAccountSidLocalW(v21, username, &unamelen, domainname, &dnamelen, &sidNameUse);
  }
  v22 = ResourceStrings::Unavailable();
  pApplicationSid = 0;
  m_ptr = (wchar_t *)v22;
  if ( (int)GetPackageSidFromToken(enumSD, &pApplicationSid) >= 0 )
    GetTextualSid(pApplicationSid, applicationSidAsText, (unsigned int *)&applicationDisplayName);
  applicationDisplayName.m_ptr = 0;
  TryGetPackageFullNameFromToken(enumSD, &applicationDisplayName);
  LogHandle = 0;
  memset_0(Strings, 0, sizeof(Strings));
  v24 = fRemote;
  if ( fRemote == 10036 )
  {
    LOWORD(v46) = 1;
    Strings[0] = domainname;
    Strings[1] = username;
    Strings[2] = sidAsText;
    if ( NetworkAddress )
      Myval2 = NetworkAddress;
    Strings[3] = Myval2;
    goto LABEL_89;
  }
  if ( fRemote == 18207 )
  {
    if ( g_bInSCM )
      v24 = 10015;
    if ( hRpc_0 )
      v34 = ResourceStrings::Remote();
    else
      v34 = ResourceStrings::Local();
    Strings[0] = v34;
    Strings[1] = ResourceStrings::Launch();
    if ( WindowsIsStringEmpty(0) )
      StringRawBuffer = ResourceStrings::Unavailable();
    else
      StringRawBuffer = WindowsGetStringRawBuffer(0, 0);
    goto LABEL_81;
  }
  if ( fRemote == 18208 )
  {
    if ( g_bInSCM )
      v24 = 10016;
    if ( hsClassIdentifier == EventLog_DEFAULTLAUNCHPERMISSIONS )
      v31 = ResourceStrings::MachineDefault();
    else
      v31 = ResourceStrings::ApplicationSpecific();
    Strings[0] = v31;
    if ( hRpc_0 )
      v32 = ResourceStrings::Remote();
    else
      v32 = ResourceStrings::Local();
    Strings[1] = v32;
    Strings[2] = ResourceStrings::Launch();
    if ( WindowsIsStringEmpty(0) )
      v33 = ResourceStrings::Unavailable();
    else
      v33 = WindowsGetStringRawBuffer(0, 0);
    Strings[3] = v33;
    Strings[4] = wszAppID;
    Strings[5] = domainname;
    Strings[6] = username;
    Strings[7] = sidAsText;
    if ( NetworkAddress )
      Myval2 = NetworkAddress;
    Strings[8] = Myval2;
    if ( applicationDisplayName.m_ptr )
      m_ptr = applicationDisplayName.m_ptr;
    Strings[10] = applicationSidAsText;
    Strings[9] = m_ptr;
    goto LABEL_89;
  }
  if ( fRemote == 18209 )
  {
    if ( g_bInSCM )
      v24 = 10017;
    if ( hsClassIdentifier == EventLog_DEFAULTACCESSPERMISSIONS )
      v28 = ResourceStrings::MachineDefault();
    else
      v28 = ResourceStrings::ApplicationSpecific();
    Strings[0] = v28;
    if ( hRpc_0 )
      v29 = ResourceStrings::Remote();
    else
      v29 = ResourceStrings::Local();
    Strings[1] = v29;
    GetModuleFileNameW(0, Module, 0x104u);
    StringRawBuffer = Module;
LABEL_81:
    Strings[2] = StringRawBuffer;
    Strings[3] = wszAppID;
    Strings[4] = domainname;
    Strings[5] = username;
    Strings[6] = sidAsText;
    if ( NetworkAddress )
      Myval2 = NetworkAddress;
    Strings[7] = Myval2;
    if ( applicationDisplayName.m_ptr )
      m_ptr = applicationDisplayName.m_ptr;
    Strings[9] = applicationSidAsText;
    Strings[8] = m_ptr;
    goto LABEL_89;
  }
  if ( fRemote == 18210 )
  {
    v26 = 10018;
  }
  else
  {
    if ( fRemote != 18211 )
    {
      if ( fRemote == 18219 )
      {
        if ( g_bInSCM )
          v24 = 10027;
        if ( hRpc_0 )
          v25 = ResourceStrings::Remote();
        else
          v25 = ResourceStrings::Local();
        Strings[0] = v25;
        Strings[1] = ResourceStrings::Access();
        Strings[3] = username;
        Strings[2] = domainname;
        Strings[4] = sidAsText;
        if ( NetworkAddress )
          Myval2 = NetworkAddress;
        Strings[5] = Myval2;
        if ( applicationDisplayName.m_ptr )
          m_ptr = applicationDisplayName.m_ptr;
        Strings[7] = applicationSidAsText;
        Strings[6] = m_ptr;
      }
      else if ( fRemote == 18221 )
      {
        GetModuleFileNameW(0, Module, 0x104u);
        Strings[0] = Module;
        Strings[1] = domainname;
        Strings[2] = username;
        Strings[3] = sidAsText;
        if ( applicationDisplayName.m_ptr )
          m_ptr = applicationDisplayName.m_ptr;
        Strings[5] = applicationSidAsText;
        Strings[4] = m_ptr;
      }
      goto LABEL_89;
    }
    v26 = 10019;
  }
  if ( g_bInSCM )
    v24 = v26;
  if ( hRpc_0 )
    v27 = ResourceStrings::Remote();
  else
    v27 = ResourceStrings::Local();
  Strings[0] = v27;
  GetModuleFileNameW(0, Module, 0x104u);
  Strings[1] = Module;
  Strings[2] = wszAppID;
  Strings[3] = domainname;
  Strings[4] = username;
  Strings[5] = sidAsText;
  if ( NetworkAddress )
    Myval2 = NetworkAddress;
  Strings[6] = Myval2;
  if ( applicationDisplayName.m_ptr )
    m_ptr = applicationDisplayName.m_ptr;
  Strings[8] = applicationSidAsText;
  Strings[7] = m_ptr;
LABEL_89:
  hImp = 0;
  if ( SuspendImpersonate(&hImp) >= 0 )
  {
    if ( g_bInSCM )
    {
      v35 = L"DCOM";
      v36 = &S_olemsg_DCOM;
    }
    else
    {
      v35 = L"COM";
      v36 = &S_olemsg_COM;
    }
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      StringSid = 0;
      ConvertSidToStringSidW(v21, &StringSid);
      v37 = (LPWSTR)&pszValueToSet;
      if ( StringSid )
        v37 = StringSid;
      CGuidStr::CGuidStr(&v55, pGuid);
      v54 = v38;
      if ( WindowsIsStringEmpty(0) )
        v39 = ResourceStrings::Unavailable();
      else
        v39 = WindowsGetStringRawBuffer(0, 0);
      ComTraceMessage(
        -2147024891,
        "onecore\\com\\combase\\catalog\\services.cxx",
        "LogAccessFailed",
        1069,
        ERRORS,
        L"ClassIdentifier:%ws IID:%ws Type:%d Remote:%!bool! SID:%ws Domain:%ws User:%ws %!HRESULT!",
        v39,
        v54,
        v24,
        hRpc_0,
        v37,
        domainname,
        username,
        -2147024891);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<void *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > *)&StringSid);
    }
    EtwEventRegister(v36, 0, 0, &LogHandle);
    if ( !LogHandle
      || (v40 = EvtIntReportEventAndSourceAsync(LogHandle, v35, (unsigned __int16)v46),
          EtwEventUnregister(LogHandle),
          !v40) )
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      {
        LastError = GetLastError();
        ComTraceMessageT<unsigned __int64,unsigned long>(
          "onecore\\com\\combase\\catalog\\services.cxx",
          "LogAccessFailed",
          1093,
          ERRORS,
          L"Either log registration or event reporting failed, log handle:0X%I64X, error: 0X%X",
          (const wchar_t *)LogHandle,
          LastError);
      }
    }
    if ( v21 )
      HeapFree(g_hHeap, 0, v21);
    if ( NetworkAddress )
      RpcStringFreeW(&NetworkAddress);
    if ( pApplicationSid )
      HeapFree(g_hHeap, 0, pApplicationSid);
    ResumeImpersonate(hImp);
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>((std::unique_ptr<wchar_t const * [0]> *)&applicationDisplayName);
}

```

## disassembly

```asm
0x1801dcf2c  mov     [rsp-8+arg_8], rbx
0x1801dcf31  push    rbp
0x1801dcf32  push    rsi
0x1801dcf33  push    rdi
0x1801dcf34  push    r12
0x1801dcf36  push    r13
0x1801dcf38  push    r14
0x1801dcf3a  push    r15
0x1801dcf3c  lea     rbp, [rsp-0AF0h]
0x1801dcf44  sub     rsp, 0BF0h
0x1801dcf4b  mov     rax, cs:__security_cookie
0x1801dcf52  xor     rax, rsp
0x1801dcf55  mov     [rbp+0B20h+var_40], rax
0x1801dcf5c  mov     r13, [rbp+0B20h+arg_20]
0x1801dcf63  mov     r12d, 2
0x1801dcf69  mov     r14, [rbp+0B20h+hUserToken]
0x1801dcf70  mov     rbx, pAppId
0x1801dcf73  mov     [rbp+0B20h+pGuid], r13
0x1801dcf77  mov     rsi, hRpc
0x1801dcf7a  mov     [rbp+0B20h+var_B94], r12d
0x1801dcf7e  call    ?Unavailable@ResourceStrings@@SAPEBGXZ; ResourceStrings::Unavailable(void)
0x1801dcf83  lea     r10d, [r12+25h]
0x1801dcf88  mov     r8, rax; pszSrc
0x1801dcf8b  mov     edx, r10d; cchDest
0x1801dcf8e  lea     hRpc, [rbp+0B20h+wszAppID]; pszDest
0x1801dcf95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801dcf9a  test    rbx, rbx
0x1801dcf9d  jz      short loc_1801DCFCA
0x1801dcf9f  mov     rax, [rbx]
0x1801dcfa2  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1801dcfa9  jnz     short loc_1801DCFB8
0x1801dcfab  mov     rax, [rbx+8]
0x1801dcfaf  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1801dcfb6  jz      short loc_1801DCFCA
0x1801dcfb8  mov     r8d, r10d; cchMax
0x1801dcfbb  lea     rdx, [rbp+0B20h+wszAppID]; lpsz
0x1801dcfc2  mov     hRpc, rbx; rguid
0x1801dcfc5  call    ?wStringFromGUID2@@YAHAEBU_GUID@@PEAGH@Z; wStringFromGUID2(_GUID const &,ushort *,int)
0x1801dcfca  mov     ebx, 100h
0x1801dcfcf  mov     [rbp+0B20h+sidNameUse], 0
0x1801dcfd6  mov     [rbp+0B20h+unamelen], ebx
0x1801dcfd9  mov     [rbp+0B20h+dnamelen], ebx
0x1801dcfdc  call    ?Unavailable@ResourceStrings@@SAPEBGXZ; ResourceStrings::Unavailable(void)
0x1801dcfe1  mov     r8, rax; pszSrc
0x1801dcfe4  lea     hRpc, [rbp+0B20h+username]; pszDest
0x1801dcfeb  mov     edx, ebx; cchDest
0x1801dcfed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801dcff2  call    ?Unavailable@ResourceStrings@@SAPEBGXZ; ResourceStrings::Unavailable(void)
0x1801dcff7  mov     r8, rax; pszSrc
0x1801dcffa  lea     hRpc, [rbp+0B20h+domainname]; pszDest
0x1801dd001  mov     edx, ebx; cchDest
0x1801dd003  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801dd008  mov     dword ptr [rbp+0B20h+pApplicationSid], ebx
0x1801dd00b  call    ?Unavailable@ResourceStrings@@SAPEBGXZ; ResourceStrings::Unavailable(void)
0x1801dd010  mov     r8, rax; pszSrc
0x1801dd013  lea     hRpc, [rbp+0B20h+sidAsText]; pszDest
0x1801dd01a  mov     edx, ebx; cchDest
0x1801dd01c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801dd021  mov     dword ptr [rsp+0C20h+applicationDisplayName.m_ptr], ebx
0x1801dd025  call    ?Unavailable@ResourceStrings@@SAPEBGXZ; ResourceStrings::Unavailable(void)
0x1801dd02a  mov     r8, rax; pszSrc
0x1801dd02d  lea     hRpc, [rbp+0B20h+applicationSidAsText]; pszDest
0x1801dd034  mov     edx, ebx; cchDest
0x1801dd036  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801dd03b  call    ?Unavailable@ResourceStrings@@SAPEBGXZ; ResourceStrings::Unavailable(void)
0x1801dd040  mov     r8, rax; pszSrc
0x1801dd043  lea     edx, [rbx+4]; cchDest
0x1801dd046  lea     hRpc, [rbp+0B20h+Module]; pszDest
0x1801dd04d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801dd052  call    ?Unavailable@ResourceStrings@@SAPEBGXZ; ResourceStrings::Unavailable(void)
0x1801dd057  xor     ebx, ebx
0x1801dd059  lea     rdx, [rbp+0B20h+type]; Type
0x1801dd05d  mov     hRpc, rsi; Binding
0x1801dd060  mov     [rsp+0C20h+NetworkAddress], rbx
0x1801dd065  mov     rdi, rax
0x1801dd068  lea     r15d, [rbx+4]
0x1801dd06c  mov     [rbp+0B20h+type], r15d
0x1801dd070  call    cs:__imp_I_RpcBindingInqTransportType
0x1801dd076  test    eax, eax
0x1801dd078  jnz     short loc_1801DD0B0
0x1801dd07a  cmp     [rbp+0B20h+type], r15d
0x1801dd07e  jnz     short loc_1801DD0A3
0x1801dd080  call    ?LoadResourceStrings@ResourceStrings@@CAXXZ; ResourceStrings::LoadResourceStrings(void)
0x1801dd085  mov     rax, cs:?s_spResourceStrings@ResourceStrings@@0V?$unique_ptr@UResourceStringStorage@ResourceStrings@@U?$default_delete@UResourceStringStorage@ResourceStrings@@@std@@@std@@A._Mypair._Myval2; std::unique_ptr<ResourceStrings::ResourceStringStorage> ResourceStrings::s_spResourceStrings ...
0x1801dd08c  test    rax, rax
0x1801dd08f  jz      short loc_1801DD09A
0x1801dd091  mov     rdi, [rax+20h]
0x1801dd095  test    rdi, rdi
0x1801dd098  jnz     short loc_1801DD0B0
0x1801dd09a  lea     rdi, ?s_defaultRCLRPCAddress@ResourceStrings@@0QBGB; ushort const near * const ResourceStrings::s_defaultRCLRPCAddress
0x1801dd0a1  jmp     short loc_1801DD0B0
0x1801dd0a3  mov     hRpc, rsi; hRpc
0x1801dd0a6  call    ?GetClientNetworkAddress@@YAPEAGPEAX@Z; GetClientNetworkAddress(void *)
0x1801dd0ab  mov     [rsp+0C20h+NetworkAddress], rax
0x1801dd0b0  mov     hRpc, r14; hUserToken
0x1801dd0b3  call    ?GetUserSid@@YAPEAXPEAX@Z; GetUserSid(void *)
0x1801dd0b8  mov     r15, rax
0x1801dd0bb  test    rax, rax
0x1801dd0be  jz      short loc_1801DD100
0x1801dd0c0  lea     r8, [rbp+0B20h+pApplicationSid]; cchSidSize
0x1801dd0c4  mov     hRpc, rax; pSid
0x1801dd0c7  lea     rdx, [rbp+0B20h+sidAsText]; TextualSid
0x1801dd0ce  call    ?GetTextualSid@@YAHPEAXPEAGPEAK@Z; GetTextualSid(void *,ushort *,ulong *)
0x1801dd0d3  lea     rax, [rbp+0B20h+sidNameUse]
0x1801dd0d7  mov     hRpc, r15; Sid
0x1801dd0da  mov     [rsp+0C20h+peUse], rax; peUse
0x1801dd0df  lea     pAppId, [rbp+0B20h+domainname]; ReferencedDomainName
0x1801dd0e6  lea     rax, [rbp+0B20h+dnamelen]
0x1801dd0ea  lea     r8, [rbp+0B20h+unamelen]; cchName
0x1801dd0ee  mov     [rsp+0C20h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1801dd0f3  lea     rdx, [rbp+0B20h+username]; Name
0x1801dd0fa  call    cs:__imp_LookupAccountSidLocalW
0x1801dd100  call    ?Unavailable@ResourceStrings@@SAPEBGXZ; ResourceStrings::Unavailable(void)
0x1801dd105  lea     rdx, [rbp+0B20h+pApplicationSid]; ppPackageSid
0x1801dd109  mov     [rbp+0B20h+pApplicationSid], rbx
0x1801dd10d  mov     hRpc, r14; hToken
0x1801dd110  mov     rsi, rax
0x1801dd113  call    ?GetPackageSidFromToken@@YAJPEAXPEAPEAX@Z; GetPackageSidFromToken(void *,void * *)
0x1801dd118  test    eax, eax
0x1801dd11a  js      short loc_1801DD131
0x1801dd11c  mov     hRpc, [rbp+0B20h+pApplicationSid]; pSid
0x1801dd120  lea     r8, [rsp+0C20h+applicationDisplayName]; cchSidSize
0x1801dd125  lea     rdx, [rbp+0B20h+applicationSidAsText]; TextualSid
0x1801dd12c  call    ?GetTextualSid@@YAHPEAXPEAGPEAK@Z; GetTextualSid(void *,ushort *,ulong *)
0x1801dd131  lea     rdx, [rsp+0C20h+applicationDisplayName]; packageFullName
0x1801dd136  mov     [rsp+0C20h+applicationDisplayName.m_ptr], rbx
0x1801dd13b  mov     hRpc, r14; hToken
0x1801dd13e  call    ?TryGetPackageFullNameFromToken@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?PrivMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; TryGetPackageFullNameFromToken(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801dd143  xor     edx, edx; Val
0x1801dd145  mov     [rbp+0B20h+LogHandle], rbx
0x1801dd149  lea     hRpc, [rbp+0B20h+Strings]; void *
0x1801dd14d  lea     r8d, [rdx+58h]; Size
0x1801dd151  call    memset_0
0x1801dd156  mov     ebx, [rbp+0B20h+arg_28]
0x1801dd15c  mov     eax, ebx
0x1801dd15e  mov     r14d, [rbp+0B20h+hRpc_0]
0x1801dd165  sub     eax, 2734h
0x1801dd16a  jz      loc_1801DD516
0x1801dd170  sub     eax, 1FEBh
0x1801dd175  jz      loc_1801DD46C
0x1801dd17b  sub     eax, 1
0x1801dd17e  jz      loc_1801DD3A6
0x1801dd184  sub     eax, 1
0x1801dd187  jz      loc_1801DD348
0x1801dd18d  sub     eax, 1
0x1801dd190  jz      loc_1801DD33E
0x1801dd196  sub     eax, 1
0x1801dd199  jz      loc_1801DD299
0x1801dd19f  sub     eax, 8
0x1801dd1a2  jz      short loc_1801DD216
0x1801dd1a4  cmp     eax, r12d
0x1801dd1a7  jz      short loc_1801DD1B0
0x1801dd1a9  xor     edi, edi
0x1801dd1ab  jmp     loc_1801DD555
0x1801dd1b0  mov     r8d, 104h; nSize
0x1801dd1b6  lea     rdx, [rbp+0B20h+Module]; lpFilename
0x1801dd1bd  xor     ecx, ecx; hModule
0x1801dd1bf  call    cs:__imp_GetModuleFileNameW
0x1801dd1c5  lea     rax, [rbp+0B20h+Module]
0x1801dd1cc  mov     edi, 6
0x1801dd1d1  mov     [rbp+0B20h+Strings], rax
0x1801dd1d5  lea     rax, [rbp+0B20h+domainname]
0x1801dd1dc  mov     [rbp+0B20h+Strings+8], rax
0x1801dd1e0  lea     rax, [rbp+0B20h+username]
0x1801dd1e7  mov     [rbp+0B20h+Strings+10h], rax
0x1801dd1eb  lea     rax, [rbp+0B20h+sidAsText]
0x1801dd1f2  mov     [rbp+0B20h+Strings+18h], rax
0x1801dd1f6  mov     rax, [rsp+0C20h+applicationDisplayName.m_ptr]
0x1801dd1fb  test    rax, rax
0x1801dd1fe  cmovnz  rsi, rax
0x1801dd202  lea     rax, [rbp+0B20h+applicationSidAsText]
0x1801dd209  mov     [rbp+0B20h+Strings+28h], rax
0x1801dd20d  mov     [rbp+0B20h+Strings+20h], rsi
0x1801dd211  jmp     loc_1801DD555
0x1801dd216  cmp     cs:?g_bInSCM@@3JA, 0; long g_bInSCM
0x1801dd21d  mov     eax, 272Bh
0x1801dd222  cmovnz  ebx, eax
0x1801dd225  test    r14d, r14d
0x1801dd228  jz      short loc_1801DD231
0x1801dd22a  call    ?Remote@ResourceStrings@@SAPEBGXZ; ResourceStrings::Remote(void)
0x1801dd22f  jmp     short loc_1801DD236
0x1801dd231  call    ?Local@ResourceStrings@@SAPEBGXZ; ResourceStrings::Local(void)
0x1801dd236  mov     [rbp+0B20h+Strings], rax
0x1801dd23a  call    ?Access@ResourceStrings@@SAPEBGXZ; ResourceStrings::Access(void)
0x1801dd23f  mov     [rbp+0B20h+Strings+8], rax
0x1801dd243  lea     rax, [rbp+0B20h+username]
0x1801dd24a  mov     [rbp+0B20h+Strings+18h], rax
0x1801dd24e  lea     rax, [rbp+0B20h+domainname]
0x1801dd255  mov     [rbp+0B20h+Strings+10h], rax
0x1801dd259  lea     rax, [rbp+0B20h+sidAsText]
0x1801dd260  mov     [rbp+0B20h+Strings+20h], rax
0x1801dd264  mov     rax, [rsp+0C20h+NetworkAddress]
0x1801dd269  test    rax, rax
0x1801dd26c  cmovnz  rdi, rax
0x1801dd270  mov     rax, [rsp+0C20h+applicationDisplayName.m_ptr]
0x1801dd275  test    rax, rax
0x1801dd278  mov     [rbp+0B20h+Strings+28h], rdi
0x1801dd27c  mov     edi, 8
0x1801dd281  cmovnz  rsi, rax
0x1801dd285  lea     rax, [rbp+0B20h+applicationSidAsText]
0x1801dd28c  mov     [rbp+0B20h+Strings+38h], rax
0x1801dd290  mov     [rbp+0B20h+Strings+30h], rsi
0x1801dd294  jmp     loc_1801DD555
0x1801dd299  mov     eax, 2723h
0x1801dd29e  cmp     cs:?g_bInSCM@@3JA, 0; long g_bInSCM
0x1801dd2a5  cmovnz  ebx, eax
0x1801dd2a8  test    r14d, r14d
0x1801dd2ab  jz      short loc_1801DD2B4
0x1801dd2ad  call    ?Remote@ResourceStrings@@SAPEBGXZ; ResourceStrings::Remote(void)
0x1801dd2b2  jmp     short loc_1801DD2B9
0x1801dd2b4  call    ?Local@ResourceStrings@@SAPEBGXZ; ResourceStrings::Local(void)
0x1801dd2b9  mov     r8d, 104h; nSize
0x1801dd2bf  mov     [rbp+0B20h+Strings], rax
0x1801dd2c3  lea     rdx, [rbp+0B20h+Module]; lpFilename
0x1801dd2ca  xor     ecx, ecx; hModule
0x1801dd2cc  call    cs:__imp_GetModuleFileNameW
0x1801dd2d2  lea     rax, [rbp+0B20h+Module]
0x1801dd2d9  mov     [rbp+0B20h+Strings+8], rax
0x1801dd2dd  lea     rax, [rbp+0B20h+wszAppID]
0x1801dd2e4  mov     [rbp+0B20h+Strings+10h], rax
0x1801dd2e8  lea     rax, [rbp+0B20h+domainname]
0x1801dd2ef  mov     [rbp+0B20h+Strings+18h], rax
0x1801dd2f3  lea     rax, [rbp+0B20h+username]
0x1801dd2fa  mov     [rbp+0B20h+Strings+20h], rax
0x1801dd2fe  lea     rax, [rbp+0B20h+sidAsText]
0x1801dd305  mov     [rbp+0B20h+Strings+28h], rax
0x1801dd309  mov     rax, [rsp+0C20h+NetworkAddress]
0x1801dd30e  test    rax, rax
0x1801dd311  cmovnz  rdi, rax
0x1801dd315  mov     rax, [rsp+0C20h+applicationDisplayName.m_ptr]
0x1801dd31a  test    rax, rax
0x1801dd31d  mov     [rbp+0B20h+Strings+30h], rdi
0x1801dd321  mov     edi, 9
0x1801dd326  cmovnz  rsi, rax
0x1801dd32a  lea     rax, [rbp+0B20h+applicationSidAsText]
0x1801dd331  mov     [rbp+0B20h+Strings+40h], rax
0x1801dd335  mov     [rbp+0B20h+Strings+38h], rsi
0x1801dd339  jmp     loc_1801DD555
0x1801dd33e  mov     eax, 2722h
0x1801dd343  jmp     loc_1801DD29E
0x1801dd348  cmp     cs:?g_bInSCM@@3JA, 0; long g_bInSCM
0x1801dd34f  mov     eax, 2721h
0x1801dd354  cmovnz  ebx, eax
0x1801dd357  cmp     [rbp+0B20h+hsClassIdentifier], 3
0x1801dd35e  jnz     short loc_1801DD367
0x1801dd360  call    ?MachineDefault@ResourceStrings@@SAPEBGXZ; ResourceStrings::MachineDefault(void)
0x1801dd365  jmp     short loc_1801DD36C
0x1801dd367  call    ?ApplicationSpecific@ResourceStrings@@SAPEBGXZ; ResourceStrings::ApplicationSpecific(void)
0x1801dd36c  mov     [rbp+0B20h+Strings], rax
0x1801dd370  test    r14d, r14d
0x1801dd373  jz      short loc_1801DD37C
0x1801dd375  call    ?Remote@ResourceStrings@@SAPEBGXZ; ResourceStrings::Remote(void)
0x1801dd37a  jmp     short loc_1801DD381
0x1801dd37c  call    ?Local@ResourceStrings@@SAPEBGXZ; ResourceStrings::Local(void)
0x1801dd381  mov     r8d, 104h; nSize
0x1801dd387  mov     [rbp+0B20h+Strings+8], rax
0x1801dd38b  lea     rdx, [rbp+0B20h+Module]; lpFilename
0x1801dd392  xor     ecx, ecx; hModule
0x1801dd394  call    cs:__imp_GetModuleFileNameW
0x1801dd39a  lea     rax, [rbp+0B20h+Module]
0x1801dd3a1  jmp     loc_1801DD4B4
0x1801dd3a6  cmp     cs:?g_bInSCM@@3JA, 0; long g_bInSCM
0x1801dd3ad  mov     eax, 2720h
0x1801dd3b2  cmovnz  ebx, eax
0x1801dd3b5  cmp     [rbp+0B20h+hsClassIdentifier], r12d
0x1801dd3bc  jnz     short loc_1801DD3C5
0x1801dd3be  call    ?MachineDefault@ResourceStrings@@SAPEBGXZ; ResourceStrings::MachineDefault(void)
0x1801dd3c3  jmp     short loc_1801DD3CA
0x1801dd3c5  call    ?ApplicationSpecific@ResourceStrings@@SAPEBGXZ; ResourceStrings::ApplicationSpecific(void)
0x1801dd3ca  mov     [rbp+0B20h+Strings], rax
0x1801dd3ce  test    r14d, r14d
0x1801dd3d1  jz      short loc_1801DD3DA
0x1801dd3d3  call    ?Remote@ResourceStrings@@SAPEBGXZ; ResourceStrings::Remote(void)
0x1801dd3d8  jmp     short loc_1801DD3DF
0x1801dd3da  call    ?Local@ResourceStrings@@SAPEBGXZ; ResourceStrings::Local(void)
0x1801dd3df  mov     [rbp+0B20h+Strings+8], rax
0x1801dd3e3  call    ?Launch@ResourceStrings@@SAPEBGXZ; ResourceStrings::Launch(void)
0x1801dd3e8  xor     ecx, ecx; string
0x1801dd3ea  mov     [rbp+0B20h+Strings+10h], rax
0x1801dd3ee  call    WindowsIsStringEmpty
0x1801dd3f3  test    eax, eax
0x1801dd3f5  jnz     short loc_1801DD402
0x1801dd3f7  xor     edx, edx; length
0x1801dd3f9  xor     ecx, ecx; string
0x1801dd3fb  call    WindowsGetStringRawBuffer
0x1801dd400  jmp     short loc_1801DD407
0x1801dd402  call    ?Unavailable@ResourceStrings@@SAPEBGXZ; ResourceStrings::Unavailable(void)
0x1801dd407  mov     [rbp+0B20h+Strings+18h], rax
0x1801dd40b  lea     rax, [rbp+0B20h+wszAppID]
0x1801dd412  mov     [rbp+0B20h+Strings+20h], rax
0x1801dd416  lea     rax, [rbp+0B20h+domainname]
0x1801dd41d  mov     [rbp+0B20h+Strings+28h], rax
0x1801dd421  lea     rax, [rbp+0B20h+username]
0x1801dd428  mov     [rbp+0B20h+Strings+30h], rax
0x1801dd42c  lea     rax, [rbp+0B20h+sidAsText]
0x1801dd433  mov     [rbp+0B20h+Strings+38h], rax
0x1801dd437  mov     rax, [rsp+0C20h+NetworkAddress]
0x1801dd43c  test    rax, rax
0x1801dd43f  cmovnz  rdi, rax
0x1801dd443  mov     rax, [rsp+0C20h+applicationDisplayName.m_ptr]
  ... truncated ...
```
