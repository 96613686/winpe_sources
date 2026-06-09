# shared::WNSNotificationProvider::RegisterForNotificationsSynchronousWithLockHeld(bool)

- ea: `0x180057d44`
- end: `0x180059642`
- name: `?RegisterForNotificationsSynchronousWithLockHeld@WNSNotificationProvider@shared@@AEAAX_N@Z`
- size: `6398`
- prototype: `void __fastcall(shared::WNSNotificationProvider *__hidden this, bool)`
- caller_count: `3`
- callee_count: `43`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004df28`
- `0x180101a70`
- `0x1802d3b90`

## callees

- `0x18000b154`
- `0x18000b724`
- `0x18000f350`
- `0x180010ee0`
- `0x180010fb4`
- `0x180011058`
- `0x1800113bc`
- `0x1800113ec`
- `0x1800117f8`
- `0x180013da0`
- `0x180022dc0`
- `0x180030190`
- `0x18004e170`
- `0x1800578bc`
- `0x180057d44`
- `0x180059648`
- `0x180059714`
- `0x18005a07c`
- `0x18005a14c`
- `0x18005a1fc`
- `0x18005a380`
- `0x18005a4f4`
- `0x18005a56c`
- `0x18005ba50`
- `0x1800624cc`
- `0x1800a11bc`
- `0x1800aa850`
- `0x180104234`
- `0x180114c58`
- `0x18011d9a4`
- `0x18011db1c`
- `0x18012d5cc`
- `0x180133350`
- `0x1801333f0`
- `0x180199618`
- `0x1801f6fb0`
- `0x1801fc5e8`
- `0x1801fcb4e`
- `0x1802d364c`
- `0x1802d378c`
- `0x1802d38e4`
- `0x1802d397c`
- `0x180354010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005912a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005946d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005950a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005955f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800595d8`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005912a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005946d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005950a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005955f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800595d8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18005884b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18005884b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800580d4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800580d4`

## string_xrefs

- `0x180058290`: `{"text":"Notification Channel URI from WPN: %s for StableUserId %s"}`
- `0x18005862b`: `Expected notificationUri`
- `0x18005906d`: `{"text":"Trying to revoke current channelURI %s, with channelID '%s'"}`
- `0x180059192`: `Failed to create WPN endpoint.`
- `0x180059319`: `{"text":"Existing cached channelID is empty. Cannot successully close existing channelURI('%s')."}`
- `0x18005924d`: `ChannelRevocation attempted (ServiceStartup scenario: %s; HRESULT = 0x%08X); ChannelDetails for revocation: ChannelURI (%s), ChannelID (%s)`
- `0x18005936b`: `Failed to call CreateChannelRequest.`
- `0x1800591e4`: `{"text":"Successfully revoked channelURI %s, with channelID '%s'"}`
- `0x180059112`: `{"hr":"0x%08x","file":"%s","line":%d,"text":"Failed to call CloseChannel in WNSNotificationProvider::StartAsync(). Continuing with the CreateChannel workflow."}`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
void __fastcall shared::WNSNotificationProvider::RegisterForNotificationsSynchronousWithLockHeld(
        shared::WNSNotificationProvider *this,
        char a2)
{
  char v2; // r12
  __int64 v4; // r9
  __int64 v5; // rax
  const char *v6; // r8
  std::_Ref_count_base *v7; // r13
  void **v8; // r15
  size_t v9; // rsi
  const struct std::nothrow_t *v10; // rdx
  void *v11; // rcx
  unsigned __int64 v12; // r14
  void *v13; // r12
  const struct std::nothrow_t *v14; // rdx
  void *v15; // rcx
  int v16; // eax
  _QWORD *v17; // r8
  const char *v18; // r14
  int v19; // eax
  _QWORD *v20; // rdx
  FILETIME *v21; // r14
  unsigned __int64 v22; // rdx
  const struct std::nothrow_t *v23; // rdx
  void *v24; // rcx
  unsigned __int64 v25; // rdx
  const struct std::nothrow_t *v26; // rdx
  void *v27; // rcx
  const char *v28; // r9
  const char *v29; // r8
  void **v30; // r13
  size_t v31; // r14
  const struct std::nothrow_t *v32; // rdx
  void *v33; // rcx
  _QWORD *v34; // rdx
  char *v35; // r14
  unsigned __int64 v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  char *v38; // rcx
  unsigned __int64 v39; // rdx
  const struct std::nothrow_t *v40; // rdx
  void *v41; // rcx
  char *v42; // r15
  const char *v43; // r9
  unsigned __int64 v44; // r15
  void *v45; // r12
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rdx
  void **v51; // r13
  size_t v52; // r14
  const struct std::nothrow_t *v53; // rdx
  void *v54; // rcx
  int wMonth; // r9d
  int wDay; // r10d
  int wYear; // r11d
  int wHour; // r8d
  int wMinute; // edx
  int wSecond; // ecx
  int wMilliseconds; // eax
  void **v62; // r8
  std::_Ref_count_base *v63; // r13
  void **v64; // r15
  size_t v65; // rsi
  const struct std::nothrow_t *v66; // rdx
  void *v67; // rcx
  const struct std::nothrow_t *v68; // rdx
  void *v69; // rcx
  std::_Ref_count_base *v70; // r15
  __int64 v71; // r13
  void **v72; // rsi
  size_t v73; // r14
  __int64 v74; // r12
  const struct std::nothrow_t *v75; // rdx
  void *v76; // rcx
  IUnknown *v77; // rcx
  struct IWpnPlatform *v78; // rcx
  int v79; // esi
  unsigned __int64 v80; // r15
  void *v81; // r12
  __int64 v82; // rdx
  unsigned __int64 v83; // r14
  void *v84; // r12
  void *v85; // r14
  const struct std::nothrow_t *v86; // rdx
  void *v87; // rcx
  const struct std::nothrow_t *v88; // rdx
  void *v89; // rcx
  const struct std::nothrow_t *v90; // rdx
  void *v91; // rcx
  const struct std::nothrow_t *v92; // rdx
  void *v93; // rcx
  __int64 ChannelIdAndChannelURIFromSettingsWithLockHeld; // rsi
  IUnknown *v95; // r14
  struct IUnknownVtbl *lpVtbl; // rsi
  _QWORD *v97; // rax
  _QWORD *v98; // r8
  signed int v99; // r15d
  int v100; // ecx
  __int64 v101; // rdx
  const char *v102; // rax
  const char *v103; // rdx
  const char *v104; // r8
  __int64 v105; // r12
  void (__fastcall *v106)(__int64, void **, FILETIME *, _QWORD, int, void **, const char *, _QWORD, _QWORD); // r13
  void **v107; // r14
  __int64 v108; // rdx
  __int64 v109; // rdx
  __int64 v110; // rdx
  const char *v111; // rax
  int dwImpLevel; // [rsp+28h] [rbp-210h]
  RPC_AUTH_IDENTITY_HANDLE pAuthInfo; // [rsp+30h] [rbp-208h]
  FILETIME FileTime; // [rsp+50h] [rbp-1E8h] BYREF
  bool v115; // [rsp+58h] [rbp-1E0h]
  char v116; // [rsp+59h] [rbp-1DFh]
  int v117; // [rsp+5Ch] [rbp-1DCh] BYREF
  IUnknown *pProxy; // [rsp+60h] [rbp-1D8h] BYREF
  const char *v119; // [rsp+68h] [rbp-1D0h] BYREF
  int v120; // [rsp+70h] [rbp-1C8h]
  struct IWpnPlatform *v121[2]; // [rsp+78h] [rbp-1C0h] BYREF
  __int64 v122; // [rsp+88h] [rbp-1B0h] BYREF
  std::_Ref_count_base *v123; // [rsp+90h] [rbp-1A8h]
  __int64 v124; // [rsp+98h] [rbp-1A0h] BYREF
  std::_Ref_count_base *v125; // [rsp+A0h] [rbp-198h]
  struct _SYSTEMTIME SystemTime; // [rsp+A8h] [rbp-190h] BYREF
  void *v127[2]; // [rsp+B8h] [rbp-180h] BYREF
  __int128 v128; // [rsp+C8h] [rbp-170h]
  std::_Ref_count_base *v129[2]; // [rsp+D8h] [rbp-160h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-150h]
  void *Src[3]; // [rsp+F8h] [rbp-140h] BYREF
  unsigned __int64 v132; // [rsp+110h] [rbp-128h]
  void *v133[3]; // [rsp+120h] [rbp-118h] BYREF
  unsigned __int64 v134; // [rsp+138h] [rbp-100h]
  void *v135[2]; // [rsp+160h] [rbp-D8h] BYREF
  __int128 v136; // [rsp+170h] [rbp-C8h]
  void *v137[2]; // [rsp+180h] [rbp-B8h] BYREF
  __int128 v138; // [rsp+190h] [rbp-A8h]
  int v139; // [rsp+1A0h] [rbp-98h] BYREF
  _QWORD v140[4]; // [rsp+1A8h] [rbp-90h] BYREF
  _QWORD v141[4]; // [rsp+1C8h] [rbp-70h] BYREF
  int v142; // [rsp+1E8h] [rbp-50h]
  FILETIME v143; // [rsp+1ECh] [rbp-4Ch]
  int v144; // [rsp+1F4h] [rbp-44h]

  v2 = a2;
  v116 = a2;
  v121[1] = this;
  if ( !*((_BYTE *)this + 291) )
  {
    v117 = 0;
    v115 = 0;
    shared::SharedInstanceManager::GetInstanceThrowIfNull<shared::ISharedSettingsManager>(&v124);
    LOBYTE(v4) = 1;
    (*(void (__fastcall **)(__int64, __int64 *, char *, __int64))(*(_QWORD *)v124 + 24LL))(
      v124,
      &v122,
      (char *)this + 160,
      v4);
    try
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 16) + 40LL))(*((_QWORD *)this + 16), 2);
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 16) + 40LL))(*((_QWORD *)this + 16), 3);
      if ( !*((_QWORD *)this + 22) )
      {
        v119 = ".\\wnsnotificationprovider.cpp";
        v120 = 567;
        v5 = cdp::MakeException<cdp::HResultException<-2147221245>,>(
               v133,
               &v119,
               "StableUserId should be set before registering for notifications");
        cdp::CdpThrow<cdp::HResultException<-2147221245>>(&v119, v5);
      }
      if ( *((_QWORD *)this + 23) <= 0xFu )
        v6 = (char *)this + 160;
      else
        v6 = (const char *)*((_QWORD *)this + 20);
      cdp::detail::StringFormat(Src, "{\"text\":\"Registering with WPN for StableUserId %s\"}", v6);
      shared::TraceLogInstance::Get(v129);
      if ( v129[0]
        && (*(unsigned __int8 (__fastcall **)(std::_Ref_count_base *, __int64, __int64))(*(_QWORD *)v129[0] + 176LL))(
             v129[0],
             4,
             2) )
      {
        v7 = v129[0];
        v119 = *(const char **)v129[0];
        v8 = Src;
        if ( v132 > 0xF )
          v8 = (void **)Src[0];
        *(_OWORD *)v127 = 0;
        v128 = 0;
        v9 = -1;
        do
          ++v9;
        while ( *((_BYTE *)v8 + v9) );
        if ( v9 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Xlength_error("string too long");
        if ( v9 > 0xF )
        {
          v12 = v9 | 0xF;
          if ( (v9 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
          {
            v12 = 0x7FFFFFFFFFFFFFFFLL;
          }
          else if ( v12 < 0x16 )
          {
            v12 = 22;
          }
          v13 = (void *)std::allocator<char>::allocate(v127, v12 + 1);
          v127[0] = v13;
          *(_QWORD *)&v128 = v9;
          *((_QWORD *)&v128 + 1) = v12;
          memcpy_0(v13, v8, v9);
          *((_BYTE *)v13 + v9) = 0;
          v2 = v116;
        }
        else
        {
          *(_QWORD *)&v128 = v9;
          *((_QWORD *)&v128 + 1) = 15;
          memcpy_0(v127, v8, v9);
          *((_BYTE *)v127 + v9) = 0;
        }
        (*((void (__fastcall **)(std::_Ref_count_base *, __int64, __int64, void **))v119 + 8))(v7, 4, 2, v127);
        if ( *((_QWORD *)&v128 + 1) > 0xFu )
        {
          v10 = (const struct std::nothrow_t *)(*((_QWORD *)&v128 + 1) + 1LL);
          FileTime = (FILETIME)(*((_QWORD *)&v128 + 1) + 1LL);
          v11 = v127[0];
          *(void **)&SystemTime.wYear = v127[0];
          if ( (unsigned __int64)(*((_QWORD *)&v128 + 1) + 1LL) >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
            v10 = (const struct std::nothrow_t *)FileTime;
            v11 = *(void **)&SystemTime.wYear;
          }
          operator delete(v11, v10);
        }
      }
      if ( v129[1] )
        std::_Ref_count_base::_Decref(v129[1]);
      if ( v132 > 0xF )
      {
        v14 = (const struct std::nothrow_t *)(v132 + 1);
        FileTime = (FILETIME)(v132 + 1);
        v15 = Src[0];
        *(void **)&SystemTime.wYear = Src[0];
        if ( v132 + 1 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
          v14 = (const struct std::nothrow_t *)FileTime;
          v15 = *(void **)&SystemTime.wYear;
        }
        operator delete(v15, v14);
      }
      shared::WNSNotificationProvider::SubscribeForWpnNotifications(this);
      shared::WNSNotificationProvider::CreateWpnPlatform((LPVOID *)v121);
      if ( !v121[0] )
      {
        v129[0] = (std::_Ref_count_base *)".\\wnsnotificationprovider.cpp";
        LODWORD(v129[1]) = 574;
        v46 = cdp::MakeException<cdp::HResultException<-2147418113>,>(v133, v129, "Expected WPN Platform.");
        cdp::CdpThrow<cdp::HResultException<-2147418113>>(v129, v46);
      }
      shared::WNSNotificationProvider::RegisterWithSystemLocked(this, v121[0]);
      pProxy = 0;
      v16 = (*(__int64 (__fastcall **)(struct IWpnPlatform *, IUnknown **))(*(_QWORD *)v121[0] + 24LL))(
              v121[0],
              &pProxy);
      if ( v16 < 0 )
      {
        v129[0] = (std::_Ref_count_base *)".\\wnsnotificationprovider.cpp";
        LODWORD(v129[1]) = 579;
        v101 = cdp::MakeException<cdp::hresult_exception,>(
                 v133,
                 v129,
                 (unsigned int)v16,
                 "Failed to create WPN endpoint.");
        cdp::CdpThrow<cdp::hresult_exception>(v129, v101);
      }
      if ( !pProxy )
      {
        v129[0] = (std::_Ref_count_base *)".\\wnsnotificationprovider.cpp";
        LODWORD(v129[1]) = 580;
        v47 = cdp::MakeException<cdp::HResultException<-2147418113>,>(v133, v129, "Expected AppEndpoint.");
        cdp::CdpThrow<cdp::HResultException<-2147418113>>(v129, v47);
      }
      CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v122 + 216LL))(v122) && !*((_BYTE *)this + 290) || v2 )
      {
        *(_OWORD *)v127 = 0;
        *(_QWORD *)&v128 = 0;
        *((_QWORD *)&v128 + 1) = 15;
        LOBYTE(v127[0]) = 0;
        *(_OWORD *)v129 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(v129[0]) = 0;
        ChannelIdAndChannelURIFromSettingsWithLockHeld = shared::WNSNotificationProvider::GetChannelIdAndChannelURIFromSettingsWithLockHeld(
                                                           this,
                                                           v133);
        std::string::operator=(v127, ChannelIdAndChannelURIFromSettingsWithLockHeld);
        std::string::operator=(v129, ChannelIdAndChannelURIFromSettingsWithLockHeld + 32);
        cdp::AfsETagInfo::~AfsETagInfo((cdp::AfsETagInfo *)v133);
        if ( (_QWORD)v128 )
        {
          Log<std::string &,std::string &>(
            2,
            "{\"text\":\"Trying to revoke current channelURI %s, with channelID '%s'\"}",
            (const char *)v129,
            (const char *)v127);
          v95 = pProxy;
          lpVtbl = pProxy->lpVtbl;
          v97 = (_QWORD *)cdp::ToWstring(v133, v127);
          if ( v97[3] > 7u )
            v97 = (_QWORD *)*v97;
          v98 = (_QWORD *)((char *)this + 256);
          if ( *((_QWORD *)this + 35) > 7u )
            v98 = (_QWORD *)*v98;
          v99 = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, _QWORD *, _QWORD *))lpVtbl[1].AddRef)(
                  v95,
                  L"Microsoft.Windows.ConnectedDevicesPlatform_cw5n1h2txyewy",
                  v98,
                  v97);
          std::wstring::_Tidy_deallocate(v133);
          FileTime.dwLowDateTime = v99;
          if ( v99 >= 0 )
          {
            Log<std::string &,std::string &>(
              2,
              "{\"text\":\"Successfully revoked channelURI %s, with channelID '%s'\"}",
              (const char *)v129,
              (const char *)v127);
            shared::WNSNotificationProvider::ClearChannelStateInSettingsWithLockHeld(this);
            shared::WNSNotificationProvider::SetNeedsToRevokeChannelSetting(this, 0);
          }
          else
          {
            *(_DWORD *)&SystemTime.wYear = 608;
            Log<long &,char const (&)[36],int>(
              v100,
              (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Failed to call CloseChannel in WNS"
                            "NotificationProvider::StartAsync(). Continuing with the CreateChannel workflow.\"}",
              (unsigned int)&FileTime,
              (unsigned int)".\\wnsnotificationprovider.cpp",
              (__int64)&SystemTime);
          }
          cdp::detail::BasicStringToCString<std::string const &>(v127);
          v102 = (const char *)cdp::detail::BasicStringToCString<std::string const &>(v129);
          v104 = "false";
          if ( !v2 )
            v104 = "true";
          cdp::detail::StringFormat(
            Src,
            "ChannelRevocation attempted (ServiceStartup scenario: %s; HRESULT = 0x%08X); ChannelDetails for revocation: "
            "ChannelURI (%s), ChannelID (%s)",
            v104,
            v99,
            v102,
            v103);
          Log<std::string const &>(2, "{\"text\":\"%s\"}", (const char *)Src);
          v105 = *((_QWORD *)this + 48);
          v106 = *(void (__fastcall **)(__int64, void **, FILETIME *, _QWORD, int, void **, const char *, _QWORD, _QWORD))(*(_QWORD *)v105 + 64LL);
          v107 = Src;
          if ( v132 > 0xF )
            v107 = (void **)Src[0];
          FileTime.dwLowDateTime = 0;
          std::string::string(v133, "WnsNotificationProvider.ChannelRevoke");
          v106(v105, v133, &FileTime, (unsigned int)v99, 1, v107, qword_1803986E0, 0, 0);
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v133);
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(Src);
        }
        else
        {
          Log<std::string const &>(
            3,
            "{\"text\":\"Existing cached channelID is empty. Cannot successully close existing channelURI('%s').\"}",
            (const char *)v129);
        }
        *((_BYTE *)this + 290) = 1;
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v129);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v127);
      }
      Microsoft::WRL::Details::Make<shared::WpnChannelRequestCallbackHandler,>(&v119);
      v17 = (_QWORD *)((char *)this + 256);
      if ( *((_QWORD *)this + 35) > 7u )
        v17 = (_QWORD *)*v17;
      v18 = v119;
      v19 = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, _QWORD *, const char *))pProxy->lpVtbl[1].QueryInterface)(
              pProxy,
              L"Microsoft.Windows.ConnectedDevicesPlatform_cw5n1h2txyewy",
              v17,
              v119);
      if ( v19 < 0 )
      {
        v129[0] = (std::_Ref_count_base *)".\\wnsnotificationprovider.cpp";
        LODWORD(v129[1]) = 637;
        v108 = cdp::MakeException<cdp::hresult_exception,>(
                 v133,
                 v129,
                 (unsigned int)v19,
                 "Failed to call CreateChannelRequest.");
        cdp::CdpThrow<cdp::hresult_exception>(v129, v108);
      }
      shared::WpnChannelRequestCallbackHandler::WaitForResult(v18, &v139);
      if ( v144 < 0 )
      {
        v129[0] = (std::_Ref_count_base *)".\\wnsnotificationprovider.cpp";
        LODWORD(v129[1]) = 641;
        v109 = cdp::MakeException<cdp::hresult_exception,>(
                 v133,
                 v129,
                 (unsigned int)v144,
                 "Failed in processing callback from WPN.");
        cdp::CdpThrow<cdp::hresult_exception>(v129, v109);
      }
      if ( v139 < 0 )
      {
        v129[0] = (std::_Ref_count_base *)".\\wnsnotificationprovider.cpp";
        LODWORD(v129[1]) = 642;
        v110 = cdp::MakeException<cdp::hresult_exception,>(
                 v133,
                 v129,
                 (unsigned int)v139,
                 "Failure getting WPN channel.");
        cdp::CdpThrow<cdp::hresult_exception>(v129, v110);
      }
      if ( !v140[2] )
      {
        v129[0] = (std::_Ref_count_base *)".\\wnsnotificationprovider.cpp";
        LODWORD(v129[1]) = 643;
        v48 = cdp::MakeException<cdp::HResultException<-2147221246>,>(v133, v129, "Expected channelId");
        cdp::CdpThrow<cdp::HResultException<-2147221246>>(v129, v48);
      }
      if ( !v141[2] )
      {
        v129[0] = (std::_Ref_count_base *)".\\wnsnotificationprovider.cpp";
        LODWORD(v129[1]) = 644;
        v49 = cdp::MakeException<cdp::HResultException<-2147221246>,>(v133, v129, "Expected notificationUri");
        cdp::CdpThrow<cdp::HResultException<-2147221246>>(v129, v49);
      }
      if ( v142 != 1 )
      {
        v129[0] = (std::_Ref_count_base *)".\\wnsnotificationprovider.cpp";
        LODWORD(v129[1]) = 645;
        v50 = cdp::MakeException<cdp::HResultException<-2147221246>,>(
                v133,
                v129,
                "Expected channel expiration time to be valid.");
        cdp::CdpThrow<cdp::HResultException<-2147221246>>(v129, v50);
      }
      v20 = v141;
      if ( v141[3] > 7u )
        v20 = (_QWORD *)v141[0];
      cdp::Wstring<2>::ToUtf8(v135, v20);
      v21 = (FILETIME *)((char *)this + 192);
      if ( (void **)((char *)this + 192) == v135 )
      {
        v25 = *((_QWORD *)&v136 + 1);
      }
      else
      {
        v22 = *((_QWORD *)this + 27);
        if ( v22 > 0xF )
        {
          v23 = (const struct std::nothrow_t *)(v22 + 1);
          *(_QWORD *)&SystemTime.wYear = v23;
          v24 = (void *)*v21;
          FileTime = *v21;
          if ( (unsigned __int64)v23 >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned((void **)&FileTime, (unsigned __int64 *)&SystemTime.wYear);
            v24 = (void *)FileTime;
            v23 = *(const struct std::nothrow_t **)&SystemTime.wYear;
          }
          operator delete(v24, v23);
        }
        *(_OWORD *)&v21->dwLowDateTime = *(_OWORD *)v135;
        *((_OWORD *)this + 13) = v136;
        v25 = 15;
        LOBYTE(v135[0]) = 0;
      }
      if ( v25 > 0xF )
      {
        v26 = (const struct std::nothrow_t *)(v25 + 1);
        FileTime = (FILETIME)v26;
        v27 = v135[0];
        *(void **)&SystemTime.wYear = v135[0];
        if ( (unsigned __int64)v26 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
          v26 = (const struct std::nothrow_t *)FileTime;
          v27 = *(void **)&SystemTime.wYear;
        }
        operator delete(v27, v26);
      }
      v28 = (char *)this + 160;
      v29 = (char *)this + 192;
      if ( *((_QWORD *)this + 23) > 0xFu )
        v28 = *(const char **)v28;
      if ( *((_QWORD *)this + 27) > 0xFu )
        v29 = *(const char **)v29;
      cdp::detail::StringFormat(
        Src,
        "{\"text\":\"Notification Channel URI from WPN: %s for StableUserId %s\"}",
        v29,
        v28);
      shared::TraceLogInstance::Get(v129);
      if ( v129[0]
        && (*(unsigned __int8 (__fastcall **)(std::_Ref_count_base *, __int64, __int64))(*(_QWORD *)v129[0] + 176LL))(
             v129[0],
             3,
             2) )
      {
        FileTime = (FILETIME)v129[0];
        *(_QWORD *)&SystemTime.wYear = *(_QWORD *)v129[0];
        v30 = Src;
        if ( v132 > 0xF )
          v30 = (void **)Src[0];
        *(_OWORD *)v127 = 0;
        v128 = 0;
        v31 = -1;
        do
          ++v31;
        while ( *((_BYTE *)v30 + v31) );
        if ( v31 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Xlength_error("string too long");
        if ( v31 > 0xF )
        {
          v44 = v31 | 0xF;
          if ( (v31 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
          {
            v44 = 0x7FFFFFFFFFFFFFFFLL;
          }
          else if ( v44 < 0x16 )
          {
            v44 = 22;
          }
          v45 = (void *)std::allocator<char>::allocate(v127, v44 + 1);
          v127[0] = v45;
          *(_QWORD *)&v128 = v31;
          *((_QWORD *)&v128 + 1) = v44;
          memcpy_0(v45, v30, v31);
          *((_BYTE *)v45 + v31) = 0;
        }
        else
        {
          *(_QWORD *)&v128 = v31;
          *((_QWORD *)&v128 + 1) = 15;
          memcpy_0(v127, v30, v31);
          *((_BYTE *)v127 + v31) = 0;
        }
        (*(void (__fastcall **)(FILETIME, __int64, __int64, void **))(*(_QWORD *)&SystemTime.wYear + 64LL))(
          FileTime,
          3,
          2,
          v127);
        if ( *((_QWORD *)&v128 + 1) > 0xFu )
        {
          v86 = (const struct std::nothrow_t *)(*((_QWORD *)&v128 + 1) + 1LL);
          FileTime = (FILETIME)(*((_QWORD *)&v128 + 1) + 1LL);
          v87 = v127[0];
          *(void **)&SystemTime.wYear = v127[0];
          if ( (unsigned __int64)(*((_QWORD *)&v128 + 1) + 1LL) >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
            v86 = (const struct std::nothrow_t *)FileTime;
            v87 = *(void **)&SystemTime.wYear;
          }
          operator delete(v87, v86);
        }
      }
      if ( v129[1] )
        std::_Ref_count_base::_Decref(v129[1]);
      if ( v132 > 0xF )
      {
        v32 = (const struct std::nothrow_t *)(v132 + 1);
        FileTime = (FILETIME)(v132 + 1);
        v33 = Src[0];
        *(void **)&SystemTime.wYear = Src[0];
        if ( v132 + 1 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
          v32 = (const struct std::nothrow_t *)FileTime;
          v33 = *(void **)&SystemTime.wYear;
        }
        operator delete(v33, v32);
      }
      v34 = v140;
      if ( v140[3] > 7u )
        v34 = (_QWORD *)v140[0];
      cdp::Wstring<2>::ToUtf8(v137, v34);
      v35 = (char *)this + 224;
      if ( (void **)((char *)this + 224) == v137 )
      {
        v39 = *((_QWORD *)&v138 + 1);
      }
      else
      {
        v36 = *((_QWORD *)this + 31);
        if ( v36 > 0xF )
        {
          v37 = (const struct std::nothrow_t *)(v36 + 1);
          FileTime = (FILETIME)v37;
          v38 = *(char **)v35;
          *(_QWORD *)&SystemTime.wYear = *(_QWORD *)v35;
          if ( (unsigned __int64)v37 >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
            v37 = (const struct std::nothrow_t *)FileTime;
            v38 = *(char **)&SystemTime.wYear;
          }
          operator delete(v38, v37);
        }
        *(_OWORD *)v35 = *(_OWORD *)v137;
        *((_OWORD *)this + 15) = v138;
        v39 = 15;
        LOBYTE(v137[0]) = 0;
      }
      if ( v39 > 0xF )
      {
        v40 = (const struct std::nothrow_t *)(v39 + 1);
        FileTime = (FILETIME)v40;
        v41 = v137[0];
        *(void **)&SystemTime.wYear = v137[0];
        if ( (unsigned __int64)v40 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
          v40 = (const struct std::nothrow_t *)FileTime;
          v41 = *(void **)&SystemTime.wYear;
        }
        operator delete(v41, v40);
      }
      v42 = (char *)this + 160;
      if ( *((_QWORD *)this + 23) > 0xFu )
        v43 = *(const char **)v42;
      else
        v43 = (char *)this + 160;
      if ( *((_QWORD *)this + 31) > 0xFu )
        v35 = *(char **)v35;
      cdp::detail::StringFormat(
        Src,
        "{\"text\":\"Notification Channel ID from WPN: %s for StableUserId %s\"}",
        v35,
        v43);
      shared::TraceLogInstance::Get(v129);
      if ( v129[0]
        && (*(unsigned __int8 (__fastcall **)(std::_Ref_count_base *, __int64, __int64))(*(_QWORD *)v129[0] + 176LL))(
             v129[0],
             3,
             2) )
      {
        FileTime = (FILETIME)v129[0];
        *(_QWORD *)&SystemTime.wYear = *(_QWORD *)v129[0];
        v51 = Src;
        if ( v132 > 0xF )
          v51 = (void **)Src[0];
        *(_OWORD *)v127 = 0;
        v128 = 0;
        v52 = -1;
        do
          ++v52;
        while ( *((_BYTE *)v51 + v52) );
        if ( v52 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Xlength_error("string too long");
        if ( v52 > 0xF )
        {
          v80 = v52 | 0xF;
          if ( (v52 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
          {
            v80 = 0x7FFFFFFFFFFFFFFFLL;
          }
          else if ( v80 < 0x16 )
          {
            v80 = 22;
          }
          v81 = (void *)std::allocator<char>::allocate(v127, v80 + 1);
          v127[0] = v81;
          *(_QWORD *)&v128 = v52;
          *((_QWORD *)&v128 + 1) = v80;
          memcpy_0(v81, v51, v52);
          *((_BYTE *)v81 + v52) = 0;
          v42 = (char *)this + 160;
        }
        else
        {
          *(_QWORD *)&v128 = v52;
          *((_QWORD *)&v128 + 1) = 15;
          memcpy_0(v127, v51, v52);
          *((_BYTE *)v127 + v52) = 0;
        }
        (*(void (__fastcall **)(FILETIME, __int64, __int64, void **))(*(_QWORD *)&SystemTime.wYear + 64LL))(
          FileTime,
          3,
          2,
          v127);
        if ( *((_QWORD *)&v128 + 1) > 0xFu )
        {
          v88 = (const struct std::nothrow_t *)(*((_QWORD *)&v128 + 1) + 1LL);
          FileTime = (FILETIME)(*((_QWORD *)&v128 + 1) + 1LL);
          v89 = v127[0];
          *(void **)&SystemTime.wYear = v127[0];
          if ( (unsigned __int64)(*((_QWORD *)&v128 + 1) + 1LL) >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
            v88 = (const struct std::nothrow_t *)FileTime;
            v89 = *(void **)&SystemTime.wYear;
          }
          operator delete(v89, v88);
        }
      }
      if ( v129[1] )
        std::_Ref_count_base::_Decref(v129[1]);
      if ( v132 > 0xF )
      {
        v53 = (const struct std::nothrow_t *)(v132 + 1);
        FileTime = (FILETIME)(v132 + 1);
        v54 = Src[0];
        *(void **)&SystemTime.wYear = Src[0];
        if ( v132 + 1 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
          v53 = (const struct std::nothrow_t *)FileTime;
          v54 = *(void **)&SystemTime.wYear;
        }
        operator delete(v54, v53);
      }
      FileTime = v143;
      SystemTime = 0;
      if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
      {
        v129[0] = (std::_Ref_count_base *)".\\wnsnotificationprovider.cpp";
        LODWORD(v129[1]) = 163;
        v82 = cdp::MakeException<cdp::HResultException<-2147418113>,>(v133, v129, "Unable to convert to UTC");
        cdp::CdpThrow<cdp::HResultException<-2147418113>>(v129, v82);
      }
      wMonth = SystemTime.wMonth;
      wDay = SystemTime.wDay;
      wYear = SystemTime.wYear;
      wHour = SystemTime.wHour;
      wMinute = SystemTime.wMinute;
      wSecond = SystemTime.wSecond;
      wMilliseconds = SystemTime.wMilliseconds;
      *((_DWORD *)this + 73) = SystemTime.wMonth;
      *((_DWORD *)this + 74) = wDay;
      *((_DWORD *)this + 75) = wYear;
      *((_DWORD *)this + 76) = wHour;
      *((_DWORD *)this + 77) = wMinute;
      *((_DWORD *)this + 78) = wSecond;
      *((_DWORD *)this + 79) = wMilliseconds;
      *((_BYTE *)this + 320) = 1;
      cdp::detail::StringFormat(
        v133,
        "%04u-%02u-%02uT%02u:%02u:%02u.%03uZ",
        wYear,
        wMonth,
        wDay,
        wHour,
        wMinute,
        wSecond,
        wMilliseconds);
      if ( *((_QWORD *)v42 + 3) > 0xFu )
        v42 = *(char **)v42;
      v62 = v133;
      if ( v134 > 0xF )
        v62 = (void **)v133[0];
      cdp::detail::StringFormat(
        Src,
        "{\"text\":\"Notification Channel Expiration from WPN: %s for StableUserId %s\"}",
        (const char *)v62,
        v42);
      shared::TraceLogInstance::Get(v129);
      if ( v129[0]
        && (*(unsigned __int8 (__fastcall **)(std::_Ref_count_base *, __int64, __int64))(*(_QWORD *)v129[0] + 176LL))(
             v129[0],
             3,
             2) )
      {
        v63 = v129[0];
        FileTime = *(FILETIME *)v129[0];
        v64 = Src;
        if ( v132 > 0xF )
          v64 = (void **)Src[0];
        *(_OWORD *)v127 = 0;
        v128 = 0;
        v65 = -1;
        do
          ++v65;
        while ( *((_BYTE *)v64 + v65) );
        if ( v65 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Xlength_error("string too long");
        if ( v65 > 0xF )
        {
          v83 = v65 | 0xF;
          if ( (v65 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
          {
            v83 = 0x7FFFFFFFFFFFFFFFLL;
          }
          else if ( v83 < 0x16 )
          {
            v83 = 22;
          }
          v84 = (void *)std::allocator<char>::allocate(v127, v83 + 1);
          v127[0] = v84;
          *(_QWORD *)&v128 = v65;
          *((_QWORD *)&v128 + 1) = v83;
          memcpy_0(v84, v64, v65);
          *((_BYTE *)v84 + v65) = 0;
        }
        else
        {
          *(_QWORD *)&v128 = v65;
          *((_QWORD *)&v128 + 1) = 15;
          memcpy_0(v127, v64, v65);
          *((_BYTE *)v127 + v65) = 0;
        }
        (*(void (__fastcall **)(std::_Ref_count_base *, __int64, __int64, void **))(*(_QWORD *)&FileTime + 64LL))(
          v63,
          3,
          2,
          v127);
        if ( *((_QWORD *)&v128 + 1) > 0xFu )
        {
          v90 = (const struct std::nothrow_t *)(*((_QWORD *)&v128 + 1) + 1LL);
          FileTime = (FILETIME)(*((_QWORD *)&v128 + 1) + 1LL);
          v91 = v127[0];
          *(void **)&SystemTime.wYear = v127[0];
          if ( (unsigned __int64)(*((_QWORD *)&v128 + 1) + 1LL) >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
            v90 = (const struct std::nothrow_t *)FileTime;
            v91 = *(void **)&SystemTime.wYear;
          }
          operator delete(v91, v90);
        }
      }
      if ( v129[1] )
        std::_Ref_count_base::_Decref(v129[1]);
      if ( v132 > 0xF )
      {
        v66 = (const struct std::nothrow_t *)(v132 + 1);
        FileTime = (FILETIME)(v132 + 1);
        v67 = Src[0];
        *(void **)&SystemTime.wYear = Src[0];
        if ( v132 + 1 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
          v66 = (const struct std::nothrow_t *)FileTime;
          v67 = *(void **)&SystemTime.wYear;
        }
        operator delete(v67, v66);
      }
      if ( v134 > 0xF )
      {
        v68 = (const struct std::nothrow_t *)(v134 + 1);
        FileTime = (FILETIME)(v134 + 1);
        v69 = v133[0];
        *(void **)&SystemTime.wYear = v133[0];
        if ( v134 + 1 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
          v68 = (const struct std::nothrow_t *)FileTime;
          v69 = *(void **)&SystemTime.wYear;
        }
        operator delete(v69, v68);
      }
      v115 = shared::WNSNotificationProvider::SyncWithSettings(this);
      *((_DWORD *)this + 38) = 0;
      cdp::detail::StringFormat(
        v133,
        "{\"text\":\"WNSNotificationProvider successfully registered for notifications\"}");
      shared::TraceLogInstance::Get(v129);
      if ( v129[0]
        && (*(unsigned __int8 (__fastcall **)(std::_Ref_count_base *, __int64, __int64))(*(_QWORD *)v129[0] + 176LL))(
             v129[0],
             3,
             2) )
      {
        v70 = v129[0];
        v71 = *(_QWORD *)v129[0];
        v72 = v133;
        if ( v134 > 0xF )
          v72 = (void **)v133[0];
        *(_OWORD *)v127 = 0;
        v128 = 0;
        v73 = -1;
        do
          FileTime = (FILETIME)++v73;
        while ( *((_BYTE *)v72 + v73) );
        v74 = 0x7FFFFFFFFFFFFFFFLL;
        if ( v73 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Xlength_error("string too long");
        if ( v73 > 0xF )
        {
          if ( (v73 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
          {
            v74 = v73 | 0xF;
            if ( (v73 | 0xF) < 0x16 )
              v74 = 22;
          }
          v85 = (void *)std::allocator<char>::allocate(v127, v74 + 1);
          v127[0] = v85;
          *(FILETIME *)&v128 = FileTime;
          *((_QWORD *)&v128 + 1) = v74;
          memcpy_0(v85, v72, *(_QWORD *)&FileTime);
          *((_BYTE *)v85 + *(_QWORD *)&FileTime) = 0;
        }
        else
        {
          *(_QWORD *)&v128 = v73;
          *((_QWORD *)&v128 + 1) = 15;
          memcpy_0(v127, v72, v73);
          *((_BYTE *)v127 + v73) = 0;
        }
        (*(void (__fastcall **)(std::_Ref_count_base *, __int64, __int64, void **))(v71 + 64))(v70, 3, 2, v127);
        if ( *((_QWORD *)&v128 + 1) > 0xFu )
        {
          v92 = (const struct std::nothrow_t *)(*((_QWORD *)&v128 + 1) + 1LL);
          FileTime = (FILETIME)(*((_QWORD *)&v128 + 1) + 1LL);
          v93 = v127[0];
          *(void **)&SystemTime.wYear = v127[0];
          if ( (unsigned __int64)(*((_QWORD *)&v128 + 1) + 1LL) >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
            v92 = (const struct std::nothrow_t *)FileTime;
            v93 = *(void **)&SystemTime.wYear;
          }
          operator delete(v93, v92);
        }
      }
      if ( v129[1] )
        std::_Ref_count_base::_Decref(v129[1]);
      if ( v134 > 0xF )
      {
        v75 = (const struct std::nothrow_t *)(v134 + 1);
        FileTime = (FILETIME)(v134 + 1);
        v76 = v133[0];
        *(void **)&SystemTime.wYear = v133[0];
        if ( v134 + 1 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&SystemTime, (unsigned __int64 *)&FileTime);
          v75 = (const struct std::nothrow_t *)FileTime;
          v76 = *(void **)&SystemTime.wYear;
        }
        operator delete(v76, v75);
      }
      std::wstring::_Tidy_deallocate(v141);
      std::wstring::_Tidy_deallocate(v140);
      if ( v119 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v119 + 16LL))(v119);
      v77 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v77->lpVtbl->Release)(v77);
      }
      v78 = v121[0];
      if ( v121[0] )
      {
        v121[0] = 0;
        (*(void (__fastcall **)(struct IWpnPlatform *))(*(_QWORD *)v78 + 16LL))(v78);
      }
      v79 = v117;
    }
    catch ( ... )
    {
      LODWORD(v111) = GetCurrentThreadId();
      v119 = v111;
      FileTime.dwLowDateTime = 661;
      cdp::CatchAllToHR<char const (&)[21],int,unsigned __int64>(
        &v117,
        "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"WNSNotifi"
        "cationProvider failed to register for notifications\"}",
        (unsigned int)".\\wnsnotificationprovider.cpp",
        (const char *)&FileTime,
        (const char *)&v119,
        dwImpLevel,
        (size_t)pAuthInfo);
    }
    if ( *((_BYTE *)this + 288) )
    {
      shared::WNSNotificationProvider::StartBlockedChannelWorkaroundTimerLocked(this);
      *((_BYTE *)this + 288) = 0;
    }
    shared::WNSNotificationProvider::RaiseInitializationCompletedCallback(this);
    if ( v79 >= 0 && v115 )
      shared::WNSNotificationProvider::NotificationUriChanged(this);
    if ( v123 )
      std::_Ref_count_base::_Decref(v123);
    if ( v125 )
      std::_Ref_count_base::_Decref(v125);
  }
}

```

## disassembly

```asm
0x180057d44  mov     [rsp+arg_8], rbx
0x180057d49  mov     [rsp+arg_10], rsi
0x180057d4e  push    rdi
0x180057d4f  push    r12
0x180057d51  push    r13
0x180057d53  push    r14
0x180057d55  push    r15
0x180057d57  sub     rsp, 210h
0x180057d5e  mov     rax, cs:__security_cookie
0x180057d65  xor     rax, rsp
0x180057d68  mov     [rsp+238h+var_38], rax
0x180057d70  mov     r12b, dl
0x180057d73  mov     [rsp+238h+var_1DF], dl
0x180057d77  mov     rdi, rcx
0x180057d7a  mov     [rsp+238h+var_1B8], rcx
0x180057d82  xor     ebx, ebx
0x180057d84  cmp     [rcx+123h], bl
0x180057d8a  jnz     loc_180058F51
0x180057d90  mov     [rsp+238h+var_1DC], ebx
0x180057d94  mov     [rsp+238h+var_1E0], bl
0x180057d98  lea     rcx, [rsp+238h+var_1A0]
0x180057da0  call    ??$GetInstanceThrowIfNull@VISharedSettingsManager@shared@@@SharedInstanceManager@shared@@SA?AV?$shared_ptr@VISharedSettingsManager@shared@@@std@@H@Z; shared::SharedInstanceManager::GetInstanceThrowIfNull<shared::ISharedSettingsManager>(int)
0x180057da5  nop
0x180057da6  mov     rcx, [rsp+238h+var_1A0]
0x180057dae  lea     rsi, [rdi+0A0h]
0x180057db5  mov     rax, [rcx]
0x180057db8  mov     r9b, 1
0x180057dbb  mov     r8, rsi
0x180057dbe  lea     rdx, [rsp+238h+var_1B0]
0x180057dc6  mov     rax, [rax+18h]
0x180057dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057dcf  nop
0x180057dd0  mov     rcx, [rdi+80h]
0x180057dd7  mov     rax, [rcx]
0x180057dda  lea     edx, [rbx+2]
0x180057ddd  mov     rax, [rax+28h]
0x180057de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057de6  mov     rcx, [rdi+80h]
0x180057ded  mov     rax, [rcx]
0x180057df0  lea     edx, [rbx+3]
0x180057df3  mov     rax, [rax+28h]
0x180057df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057dfc  cmp     [rdi+0B0h], rbx
0x180057e03  jnz     short loc_180057E41
0x180057e05  lea     rsi, aWnsnotificatio_0; ".\\wnsnotificationprovider.cpp"
0x180057e0c  mov     [rsp+238h+var_1D0], rsi
0x180057e11  mov     [rsp+238h+var_1C8], 237h
0x180057e19  lea     r8, aStableuseridSh; "StableUserId should be set before regis"...
0x180057e20  lea     rdx, [rsp+238h+var_1D0]
0x180057e25  lea     rcx, [rsp+238h+var_118]
0x180057e2d  call    ??$MakeException@V?$HResultException@$0?HPPLPOPN@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPLPOPN@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147221245>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180057e32  nop
0x180057e33  mov     rdx, rax
0x180057e36  lea     rcx, [rsp+238h+var_1D0]
0x180057e3b  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPN@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPN@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221245>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221245> &&)
0x180057e41  cmp     qword ptr [rsi+18h], 0Fh
0x180057e46  jbe     loc_18005853F
0x180057e4c  mov     r8, [rsi]
0x180057e4f  lea     rdx, aTextRegisterin_2; "{\"text\":\"Registering with WPN for St"...
0x180057e56  lea     rcx, [rsp+238h+Src]
0x180057e5e  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180057e63  nop
0x180057e64  lea     rcx, [rsp+238h+var_160]
0x180057e6c  call    ?Get@TraceLogInstance@shared@@SA?AV?$shared_ptr@VITraceLog@shared@@@std@@XZ; shared::TraceLogInstance::Get(void)
0x180057e71  nop
0x180057e72  mov     rcx, [rsp+238h+var_160]
0x180057e7a  test    rcx, rcx
0x180057e7d  jz      loc_180058009
0x180057e83  mov     rax, [rcx]
0x180057e86  mov     edx, 4
0x180057e8b  lea     r8d, [rdx-2]
0x180057e8f  mov     rax, [rax+0B0h]
0x180057e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e9b  test    al, al
0x180057e9d  jz      loc_180058009
0x180057ea3  mov     r13, [rsp+238h+var_160]
0x180057eab  mov     rax, [r13+0]
0x180057eaf  mov     [rsp+238h+var_1D0], rax
0x180057eb4  lea     r15, [rsp+238h+Src]
0x180057ebc  cmp     [rsp+238h+var_128], 0Fh
0x180057ec5  cmova   r15, [rsp+238h+Src]
0x180057ece  xorps   xmm0, xmm0
0x180057ed1  movups  xmmword ptr [rsp+238h+var_180], xmm0
0x180057ed9  xorps   xmm1, xmm1
0x180057edc  movdqu  [rsp+238h+var_170], xmm1
0x180057ee5  or      r14, 0FFFFFFFFFFFFFFFFh
0x180057ee9  mov     rsi, r14
0x180057eec  inc     rsi
0x180057eef  cmp     [r15+rsi], bl
0x180057ef3  jnz     short loc_180057EEC
0x180057ef5  mov     rax, 7FFFFFFFFFFFFFFFh
0x180057eff  cmp     rsi, rax
0x180057f02  ja      loc_180059123
0x180057f08  cmp     rsi, 0Fh
0x180057f0c  ja      loc_180057FA1
0x180057f12  mov     qword ptr [rsp+238h+var_170], rsi
0x180057f1a  mov     qword ptr [rsp+238h+var_170+8], 0Fh
0x180057f26  mov     r8, rsi; Size
0x180057f29  mov     rdx, r15; Src
0x180057f2c  lea     rcx, [rsp+238h+var_180]; void *
0x180057f34  call    memcpy_0
0x180057f39  mov     byte ptr [rsp+rsi+238h+var_180], bl
0x180057f40  lea     r9, [rsp+238h+var_180]
0x180057f48  mov     edx, 4
0x180057f4d  lea     r8d, [rdx-2]
0x180057f51  mov     rcx, r13
0x180057f54  mov     rax, [rsp+238h+var_1D0]
0x180057f59  mov     rax, [rax+40h]
0x180057f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f62  nop
0x180057f63  mov     rdx, qword ptr [rsp+238h+var_170+8]
0x180057f6b  cmp     rdx, 0Fh
0x180057f6f  jbe     loc_18005800D
0x180057f75  inc     rdx; struct std::nothrow_t *
0x180057f78  mov     qword ptr [rsp+238h+FileTime.dwLowDateTime], rdx
0x180057f7d  mov     rcx, [rsp+238h+var_180]; void *
0x180057f85  mov     qword ptr [rsp+238h+SystemTime.wYear], rcx
0x180057f8d  cmp     rdx, 1000h
0x180057f94  jnb     loc_180059130
0x180057f9a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057f9f  jmp     short loc_18005800D
0x180057fa1  mov     r14, rsi
0x180057fa4  or      r14, 0Fh
0x180057fa8  cmp     r14, rax
0x180057fab  ja      loc_180058F8E
0x180057fb1  mov     eax, 16h
0x180057fb6  cmp     r14, rax
0x180057fb9  cmovb   r14, rax
0x180057fbd  lea     rdx, [r14+1]
0x180057fc1  lea     rcx, [rsp+238h+var_180]
0x180057fc9  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x180057fce  mov     r12, rax
0x180057fd1  mov     [rsp+238h+var_180], rax
0x180057fd9  mov     qword ptr [rsp+238h+var_170], rsi
0x180057fe1  mov     qword ptr [rsp+238h+var_170+8], r14
0x180057fe9  mov     r8, rsi; Size
0x180057fec  mov     rdx, r15; Src
0x180057fef  mov     rcx, rax; void *
0x180057ff2  call    memcpy_0
0x180057ff7  mov     [r12+rsi], bl
0x180057ffb  mov     r12b, [rsp+238h+var_1DF]
0x180058000  or      r14, 0FFFFFFFFFFFFFFFFh
0x180058004  jmp     loc_180057F40
0x180058009  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005800d  mov     rcx, [rsp+238h+var_160+8]; this
0x180058015  test    rcx, rcx
0x180058018  jz      short loc_180058020
0x18005801a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005801f  nop
0x180058020  mov     rdx, [rsp+238h+var_128]
0x180058028  cmp     rdx, 0Fh
0x18005802c  jbe     short loc_180058058
0x18005802e  inc     rdx; struct std::nothrow_t *
0x180058031  mov     qword ptr [rsp+238h+FileTime.dwLowDateTime], rdx
0x180058036  mov     rcx, [rsp+238h+Src]; void *
0x18005803e  mov     qword ptr [rsp+238h+SystemTime.wYear], rcx
0x180058046  cmp     rdx, 1000h
0x18005804d  jnb     loc_180059154
0x180058053  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180058058  mov     rcx, rdi; this
0x18005805b  call    ?SubscribeForWpnNotifications@WNSNotificationProvider@shared@@AEAAXXZ; shared::WNSNotificationProvider::SubscribeForWpnNotifications(void)
0x180058060  lea     rcx, [rsp+238h+var_1C0]; ppv
0x180058065  call    ?CreateWpnPlatform@WNSNotificationProvider@shared@@SA?AV?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@XZ; shared::WNSNotificationProvider::CreateWpnPlatform(void)
0x18005806a  nop
0x18005806b  mov     rdx, [rsp+238h+var_1C0]; struct IWpnPlatform *
0x180058070  test    rdx, rdx
0x180058073  jz      loc_180058547
0x180058079  mov     rcx, rdi; this
0x18005807c  call    ?RegisterWithSystemLocked@WNSNotificationProvider@shared@@AEBAXPEAUIWpnPlatform@@@Z; shared::WNSNotificationProvider::RegisterWithSystemLocked(IWpnPlatform *)
0x180058081  mov     [rsp+238h+pProxy], rbx
0x180058086  mov     rcx, [rsp+238h+var_1C0]
0x18005808b  mov     rax, [rcx]
0x18005808e  lea     rdx, [rsp+238h+pProxy]
0x180058093  mov     rax, [rax+18h]
0x180058097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005809c  test    eax, eax
0x18005809e  js      loc_180059178
0x1800580a4  mov     rcx, [rsp+238h+pProxy]; pProxy
0x1800580a9  test    rcx, rcx
0x1800580ac  jz      loc_18005858F
0x1800580b2  mov     [rsp+238h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1800580ba  mov     [rsp+238h+pAuthInfo], rbx; pAuthInfo
0x1800580bf  mov     [rsp+238h+dwImpLevel], 3; dwImpLevel
0x1800580c7  mov     [rsp+238h+dwAuthnLevel], ebx; dwAuthnLevel
0x1800580cb  mov     r9, r14; pServerPrincName
0x1800580ce  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800580d1  mov     r8d, edx; dwAuthzSvc
0x1800580d4  call    cs:__imp_CoSetProxyBlanket
0x1800580da  mov     rcx, [rsp+238h+var_1B0]
0x1800580e2  mov     rax, [rcx]
0x1800580e5  mov     rax, [rax+0D8h]
0x1800580ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580f1  test    al, al
0x1800580f3  jnz     loc_1800591C3
0x1800580f9  test    r12b, r12b
0x1800580fc  jnz     loc_180058FC8
0x180058102  lea     rsi, aWnsnotificatio_0; ".\\wnsnotificationprovider.cpp"
0x180058109  lea     rcx, [rsp+238h+var_1D0]
0x18005810e  call    ??$Make@VWpnChannelRequestCallbackHandler@shared@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWpnChannelRequestCallbackHandler@shared@@@12@XZ; Microsoft::WRL::Details::Make<shared::WpnChannelRequestCallbackHandler,>(void)
0x180058113  nop
0x180058114  mov     rcx, [rsp+238h+pProxy]
0x180058119  mov     rax, [rcx]
0x18005811c  lea     r8, [rdi+100h]
0x180058123  cmp     qword ptr [r8+18h], 7
0x180058128  jbe     short loc_18005812D
0x18005812a  mov     r8, [r8]
0x18005812d  mov     r14, [rsp+238h+var_1D0]
0x180058132  mov     r9, r14
0x180058135  lea     rdx, aMicrosoftWindo_0; "Microsoft.Windows.ConnectedDevicesPlatf"...
0x18005813c  mov     rax, [rax+18h]
0x180058140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058145  test    eax, eax
0x180058147  js      loc_180059358
0x18005814d  lea     rdx, [rsp+238h+var_98]
0x180058155  mov     rcx, r14
0x180058158  call    ?WaitForResult@WpnChannelRequestCallbackHandler@shared@@QEAA?AUResult@12@XZ; shared::WpnChannelRequestCallbackHandler::WaitForResult(void)
0x18005815d  nop
0x18005815e  mov     r8d, [rsp+238h+var_44]
0x180058166  test    r8d, r8d
0x180058169  js      loc_18005939C
0x18005816f  mov     r8d, [rsp+238h+var_98]
0x180058177  test    r8d, r8d
0x18005817a  js      loc_1800593DD
0x180058180  cmp     [rsp+238h+var_80], rbx
0x180058188  jz      loc_1800585D7
0x18005818e  cmp     [rsp+238h+var_60], rbx
0x180058196  jz      loc_180058618
0x18005819c  cmp     [rsp+238h+var_50], 1
0x1800581a4  jnz     loc_180058659
0x1800581aa  lea     rdx, [rsp+238h+var_70]
0x1800581b2  cmp     [rsp+238h+var_58], 7
0x1800581bb  cmova   rdx, [rsp+238h+var_70]
0x1800581c4  lea     rcx, [rsp+238h+var_D8]
0x1800581cc  call    ?ToUtf8@?$Wstring@$01@cdp@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; cdp::Wstring<2>::ToUtf8(ushort const *)
0x1800581d1  lea     r14, [rdi+0C0h]
0x1800581d8  lea     rax, [rsp+238h+var_D8]
0x1800581e0  mov     r12d, 0Fh
0x1800581e6  cmp     r14, rax
0x1800581e9  jz      loc_180058FAE
0x1800581ef  mov     rdx, [r14+18h]
0x1800581f3  cmp     rdx, r12
0x1800581f6  jbe     short loc_18005821D
0x1800581f8  inc     rdx; struct std::nothrow_t *
0x1800581fb  mov     qword ptr [rsp+238h+SystemTime.wYear], rdx
0x180058203  mov     rcx, [r14]; void *
0x180058206  mov     qword ptr [rsp+238h+FileTime.dwLowDateTime], rcx
0x18005820b  cmp     rdx, 1000h
0x180058212  jnb     loc_18005941E
0x180058218  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005821d  movups  xmm0, xmmword ptr [rsp+238h+var_D8]
0x180058225  movups  xmmword ptr [r14], xmm0
0x180058229  movups  xmm1, [rsp+238h+var_C8]
0x180058231  movups  xmmword ptr [r14+10h], xmm1
0x180058236  mov     rdx, r12
0x180058239  mov     byte ptr [rsp+238h+var_D8], bl
0x180058240  cmp     rdx, r12
0x180058243  jbe     short loc_18005826F
0x180058245  inc     rdx; struct std::nothrow_t *
0x180058248  mov     qword ptr [rsp+238h+FileTime.dwLowDateTime], rdx
0x18005824d  mov     rcx, [rsp+238h+var_D8]; void *
0x180058255  mov     qword ptr [rsp+238h+SystemTime.wYear], rcx
0x18005825d  cmp     rdx, 1000h
0x180058264  jnb     loc_180059442
0x18005826a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005826f  lea     r9, [rdi+0A0h]
0x180058276  lea     r8, [rdi+0C0h]
0x18005827d  cmp     [r9+18h], r12
0x180058281  jbe     short loc_180058286
0x180058283  mov     r9, [r9]
0x180058286  cmp     [r8+18h], r12
0x18005828a  ja      loc_180058E44
0x180058290  lea     rdx, aTextNotificati; "{\"text\":\"Notification Channel URI fr"...
0x180058297  lea     rcx, [rsp+238h+Src]
0x18005829f  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x1800582a4  nop
0x1800582a5  lea     rcx, [rsp+238h+var_160]
0x1800582ad  call    ?Get@TraceLogInstance@shared@@SA?AV?$shared_ptr@VITraceLog@shared@@@std@@XZ; shared::TraceLogInstance::Get(void)
0x1800582b2  nop
0x1800582b3  mov     rcx, [rsp+238h+var_160]
0x1800582bb  test    rcx, rcx
0x1800582be  jz      loc_1800583B9
0x1800582c4  mov     rax, [rcx]
0x1800582c7  mov     edx, 3
0x1800582cc  lea     r8d, [rdx-1]
0x1800582d0  mov     rax, [rax+0B0h]
0x1800582d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582dc  test    al, al
0x1800582de  jz      loc_1800583B9
0x1800582e4  mov     rax, [rsp+238h+var_160]
0x1800582ec  mov     qword ptr [rsp+238h+FileTime.dwLowDateTime], rax
0x1800582f1  mov     rax, [rax]
0x1800582f4  mov     qword ptr [rsp+238h+SystemTime.wYear], rax
0x1800582fc  lea     r13, [rsp+238h+Src]
0x180058304  cmp     [rsp+238h+var_128], r12
0x18005830c  cmova   r13, [rsp+238h+Src]
0x180058315  xorps   xmm0, xmm0
0x180058318  movups  xmmword ptr [rsp+238h+var_180], xmm0
0x180058320  xorps   xmm1, xmm1
0x180058323  movdqu  [rsp+238h+var_170], xmm1
0x18005832c  or      r14, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
