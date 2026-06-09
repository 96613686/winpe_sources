# Microsoft::Diagnostics::SettingsDownloader::GetQueryParametersFallback(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18029c1fc`
- end: `0x18029cacc`
- name: `?GetQueryParametersFallback@SettingsDownloader@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z`
- size: `2256`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180158bf8`

## callees

- `0x18001b374`
- `0x1800202a4`
- `0x180020a4c`
- `0x180027c28`
- `0x180027e50`
- `0x18002967c`
- `0x18002ac10`
- `0x18002cb04`
- `0x18002df00`
- `0x18008a4ec`
- `0x18009c8c0`
- `0x1800d6818`
- `0x1800e9a00`
- `0x180105618`
- `0x1801288a0`
- `0x180129fe0`
- `0x180139ec8`
- `0x18013cca4`
- `0x180142448`
- `0x1801abcac`
- `0x1801af6a0`
- `0x1801b7bd0`
- `0x1801dd8c8`
- `0x18020aac0`
- `0x180247df4`
- `0x18029c1fc`
- `0x18029cce0`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029c630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029c630`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18029c626`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18029c676`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18029c626`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18029c676`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18029c4d6`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18029c4d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029c724`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029c91c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029c724`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029c91c`

## string_xrefs

- `0x18029c931`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x18029c9b6`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::SettingsDownloader::GetQueryParametersFallback(__int64 a1, _OWORD *a2)
{
  void *v4; // r8
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  Microsoft::Diagnostics::LifetimeManager *v8; // rcx
  Microsoft::Diagnostics::TelemetryAssert *TelemetryAssert; // rax
  void *v10; // rax
  void *v11; // r8
  void *v12; // rax
  void *v13; // r8
  void *v14; // rax
  void *v15; // r8
  WCHAR *v16; // r8
  void *v17; // r8
  HRESULT v18; // ebx
  __int64 v19; // rax
  void *v20; // rax
  __int64 v21; // rax
  void *v22; // rax
  void *v23; // rax
  void *v24; // rax
  HRESULT Instance; // eax
  __int64 v26; // rax
  int v27; // eax
  wil::details::in1diag3 *v28; // rcx
  __int64 v29; // rdx
  void *v30; // rax
  int ppv; // [rsp+20h] [rbp-138h]
  ULONG pcchLanguagesBuffer; // [rsp+30h] [rbp-128h] BYREF
  ULONG pulNumLanguages; // [rsp+34h] [rbp-124h] BYREF
  int v35; // [rsp+38h] [rbp-120h]
  __int128 v36; // [rsp+40h] [rbp-118h] BYREF
  LPVOID v37[2]; // [rsp+50h] [rbp-108h] BYREF
  LPVOID v38; // [rsp+60h] [rbp-F8h] BYREF
  int v39; // [rsp+68h] [rbp-F0h] BYREF
  _OWORD *v40; // [rsp+70h] [rbp-E8h]
  __int64 v41; // [rsp+80h] [rbp-D8h]
  PZZWSTR pwszLanguagesBuffer[2]; // [rsp+88h] [rbp-D0h] BYREF
  __int64 v43; // [rsp+98h] [rbp-C0h]
  unsigned __int64 v44; // [rsp+A0h] [rbp-B8h]
  __int128 v45; // [rsp+A8h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+B8h] [rbp-A0h]
  _QWORD v47[2]; // [rsp+C8h] [rbp-90h] BYREF
  _QWORD v48[4]; // [rsp+F8h] [rbp-60h] BYREF
  __m128i Src[2]; // [rsp+118h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v41 = a1;
  v40 = a2;
  v35 = 0;
  Src[0] = 0;
  Src[1] = _mm_load_si128((const __m128i *)&_xmm);
  Src[0].m128i_i16[0] = 0;
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)v47);
  *(_OWORD *)v37 = *a2;
  Microsoft::Diagnostics::WideStringStream::AppendString(v47);
  Microsoft::Diagnostics::Utils::Os::GetCallingModuleVersion(v48);
  Microsoft::Diagnostics::WideStringStream::operator<<(v47);
  *(_OWORD *)v37 = *(_OWORD *)std::wstring::operator std::wstring_view(v48, &v36);
  Microsoft::Diagnostics::WideStringStream::AppendString(v4);
  LOWORD(pcchLanguagesBuffer) = 0;
  Microsoft::Diagnostics::Utils::General::GetDeviceId(pwszLanguagesBuffer, &pcchLanguagesBuffer);
  if ( !(_BYTE)pcchLanguagesBuffer )
  {
    if ( (unsigned int)dword_1804543B0 > 2 )
    {
      v37[0] = "GetQueryParametersFallback";
      *(_QWORD *)&v36 = "deviceIdType";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)&word_1803ED3A6,
        v6,
        v7,
        (__int64)&v36,
        (__int64)v37);
    }
    if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
    {
      TelemetryAssert = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v8);
      Microsoft::Diagnostics::TelemetryAssert::Assert(TelemetryAssert);
    }
  }
  if ( (int)Microsoft::Diagnostics::Utils::String::UtcUrlEscape(pwszLanguagesBuffer) >= 0 )
  {
    v10 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v47);
    Microsoft::Diagnostics::WideStringStream::operator<<(v10);
    *(_OWORD *)v37 = *(_OWORD *)std::wstring::operator std::wstring_view(pwszLanguagesBuffer, &v36);
    Microsoft::Diagnostics::WideStringStream::AppendString(v11);
  }
  pulNumLanguages = 0;
  *(_OWORD *)v37 = *(_OWORD *)&off_180385810;
  v36 = *(_OWORD *)&off_180385800;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, &v36, v37, &pulNumLanguages) >= 0 )
  {
    v12 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v47);
    Microsoft::Diagnostics::WideStringStream::operator<<(v12);
  }
  v45 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v45) = 0;
  if ( (int)Microsoft::Diagnostics::Utils::Os::GetDeviceClass(&v45) >= 0
    && (int)Microsoft::Diagnostics::Utils::String::UtcUrlEscape(&v45) >= 0 )
  {
    Microsoft::Diagnostics::WideStringStream::operator<<(v47);
    *(_OWORD *)v37 = *(_OWORD *)std::wstring::operator std::wstring_view(&v45, &v36);
    Microsoft::Diagnostics::WideStringStream::AppendString(v13);
  }
  pcchLanguagesBuffer = 0;
  if ( (int)Microsoft::Diagnostics::Utils::Os::GetCorrectedEditionId(&pcchLanguagesBuffer) >= 0 )
  {
    v14 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v47);
    Microsoft::Diagnostics::WideStringStream::operator<<(v14);
  }
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
    Microsoft::Diagnostics::WideStringStream::operator<<(v47);
  std::wstring::operator=(Src, v47);
  std::wstring::_Tidy_deallocate(&v45);
  std::wstring::_Tidy_deallocate(pwszLanguagesBuffer);
  std::wstring::_Tidy_deallocate(v48);
  std::wstring::_Tidy_deallocate(v47);
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)v47);
  v45 = 0;
  si128.m128i_i64[0] = 0;
  si128.m128i_i64[1] = 7;
  LOWORD(v45) = 0;
  Microsoft::Diagnostics::Utils::Os::GetBuildString(&v45);
  if ( si128.m128i_i64[0] && (int)Microsoft::Diagnostics::Utils::String::UtcUrlEscape(&v45) >= 0 )
  {
    Microsoft::Diagnostics::WideStringStream::operator<<(v47);
    v36 = *(_OWORD *)std::wstring::operator std::wstring_view(&v45, v48);
    Microsoft::Diagnostics::WideStringStream::AppendString(v15);
  }
  *(_OWORD *)pwszLanguagesBuffer = 0;
  v43 = 0;
  v44 = 7;
  LOWORD(pwszLanguagesBuffer[0]) = 0;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) || GetLastError() == 122 )
  {
    std::wstring::resize(pwszLanguagesBuffer, pcchLanguagesBuffer);
    v16 = (WCHAR *)pwszLanguagesBuffer;
    if ( v44 > 7 )
      v16 = pwszLanguagesBuffer[0];
    if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, v16, &pcchLanguagesBuffer) )
    {
      std::wstring::resize(pwszLanguagesBuffer, v43);
      if ( v43 )
      {
        if ( (int)Microsoft::Diagnostics::Utils::String::UtcUrlEscape(pwszLanguagesBuffer) >= 0 )
        {
          Microsoft::Diagnostics::WideStringStream::operator<<(v47);
          v36 = *(_OWORD *)std::wstring::operator std::wstring_view(pwszLanguagesBuffer, v48);
          Microsoft::Diagnostics::WideStringStream::AppendString(v17);
        }
      }
    }
  }
  std::wstring::_Tidy_deallocate(pwszLanguagesBuffer);
  v38 = 0;
  v18 = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &v38);
  v35 = v18;
  if ( v18 >= 0 )
  {
    *(_QWORD *)&v36 = 0;
    v35 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)v38 + 48LL))(v38, &v36);
    if ( v35 >= 0 )
    {
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(v36 + 2 * v19) );
      if ( v19 )
      {
        v20 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v47);
        Microsoft::Diagnostics::WideStringStream::operator<<(v20);
      }
      else
      {
        v35 = -2147024664;
      }
    }
    v48[0] = 0;
    v35 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)v38 + 80LL))(v38, v48);
    if ( v35 >= 0 )
    {
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(v48[0] + 2 * v21) );
      if ( v21 )
      {
        v22 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v47);
        Microsoft::Diagnostics::WideStringStream::operator<<(v22);
      }
      else
      {
        v35 = -2147024664;
      }
    }
    pulNumLanguages = 0;
    v39 = 4;
    v35 = (*(__int64 (__fastcall **)(LPVOID, ULONG *, int *))(*(_QWORD *)v38 + 96LL))(v38, &pulNumLanguages, &v39);
    if ( v35 >= 0 && pulNumLanguages )
    {
      v23 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v47);
      Microsoft::Diagnostics::WideStringStream::operator<<(v23);
    }
    LOWORD(pcchLanguagesBuffer) = 0;
    v18 = (*(__int64 (__fastcall **)(LPVOID, ULONG *))(*(_QWORD *)v38 + 112LL))(v38, &pcchLanguagesBuffer);
    v35 = v18;
    if ( v18 >= 0 )
    {
      v24 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v47);
      Microsoft::Diagnostics::WideStringStream::operator<<(v24);
    }
    __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(v48);
    __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&v36);
  }
  if ( Microsoft::Diagnostics::Utils::Os::IsMsftInternalMachine() )
    Microsoft::Diagnostics::WideStringStream::operator<<(v47);
  v37[0] = 0;
  Instance = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, v37);
  if ( Instance >= 0 )
  {
    *(_QWORD *)&v36 = 0;
    v26 = *(_QWORD *)v37[0];
    *(_QWORD *)&v36 = 0;
    v27 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(v26 + 32))(v37[0], &v36);
    v28 = retaddr;
    if ( v27 >= 0 )
    {
      v48[0] = 0;
      pulNumLanguages = 0;
      v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, ULONG *))(*(_QWORD *)v36 + 32LL))(v36, v48, &pulNumLanguages);
      v28 = retaddr;
      if ( v27 >= 0 )
      {
        if ( v48[0] && pulNumLanguages )
        {
          v30 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v47);
          Microsoft::Diagnostics::WideStringStream::operator<<(v30);
        }
        goto LABEL_59;
      }
      v29 = 481;
    }
    else
    {
      v29 = 474;
    }
    wil::details::in1diag3::_Log_Hr(
      v28,
      (void *)v29,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
      (const char *)(unsigned int)v27,
      ppv);
LABEL_59:
    wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v36);
    goto LABEL_60;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1D4,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_60:
  std::wstring::_Append<wchar_t>(Src);
  wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(v37);
  wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v38);
  std::wstring::_Tidy_deallocate(&v45);
  std::wstring::_Tidy_deallocate(v47);
  std::wstring::operator=(a1, Src);
  std::wstring::_Tidy_deallocate(Src);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18029c1fc  mov     r11, rsp
0x18029c1ff  mov     [r11+18h], rbx
0x18029c203  push    rsi
0x18029c204  push    rdi
0x18029c205  push    r14
0x18029c207  sub     rsp, 140h
0x18029c20e  mov     rax, cs:__security_cookie
0x18029c215  xor     rax, rsp
0x18029c218  mov     [rsp+158h+var_20], rax
0x18029c220  mov     rbx, rdx
0x18029c223  mov     rsi, rcx
0x18029c226  mov     [rsp+158h+var_D8], rcx
0x18029c22e  mov     [rsp+158h+var_E8], rdx
0x18029c233  xor     r14d, r14d
0x18029c236  mov     [rsp+158h+var_120], r14d
0x18029c23b  xorps   xmm0, xmm0
0x18029c23e  movups  xmmword ptr [r11-40h], xmm0
0x18029c243  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18029c24b  movdqu  xmmword ptr [r11-30h], xmm1
0x18029c251  mov     [r11-40h], r14w
0x18029c256  lea     rcx, [r11-90h]; this
0x18029c25d  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x18029c262  nop
0x18029c263  movups  xmm0, xmmword ptr [rbx]
0x18029c266  movdqu  xmmword ptr [rsp+158h+var_108], xmm0
0x18029c26c  lea     rdx, [rsp+158h+var_108]
0x18029c271  lea     rcx, [rsp+158h+var_90]; Src
0x18029c279  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18029c27e  lea     rcx, [rsp+158h+var_60]
0x18029c286  call    ?GetCallingModuleVersion@Os@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::Os::GetCallingModuleVersion(void)
0x18029c28b  nop
0x18029c28c  lea     rdx, aAppver_1; "&appVer="
0x18029c293  lea     rcx, [rsp+158h+var_90]; Src
0x18029c29b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c2a0  mov     r8, rax
0x18029c2a3  lea     rdx, [rsp+158h+var_118]
0x18029c2a8  lea     rcx, [rsp+158h+var_60]
0x18029c2b0  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029c2b5  movups  xmm0, xmmword ptr [rax]
0x18029c2b8  movdqu  xmmword ptr [rsp+158h+var_108], xmm0
0x18029c2be  lea     rdx, [rsp+158h+var_108]
0x18029c2c3  mov     rcx, r8; Src
0x18029c2c6  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18029c2cb  mov     word ptr [rsp+158h+pcchLanguagesBuffer], r14w
0x18029c2d1  lea     rdx, [rsp+158h+pcchLanguagesBuffer]
0x18029c2d6  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x18029c2de  call    ?GetDeviceId@General@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU?$optional@VDeviceIdType@EnumDetails@Utils@Diagnostics@Microsoft@@@better_enums@@@Z; Microsoft::Diagnostics::Utils::General::GetDeviceId(better_enums::optional<Microsoft::Diagnostics::Utils::EnumDetails::DeviceIdType> &)
0x18029c2e3  nop
0x18029c2e4  cmp     byte ptr [rsp+158h+pcchLanguagesBuffer], r14b
0x18029c2e9  jnz     short loc_18029C34B
0x18029c2eb  mov     eax, cs:dword_1804543B0
0x18029c2f1  cmp     eax, 2
0x18029c2f4  jbe     short loc_18029C32E
0x18029c2f6  lea     rax, aGetqueryparame; "GetQueryParametersFallback"
0x18029c2fd  mov     [rsp+158h+var_108], rax
0x18029c302  lea     rax, aDeviceidtype; "deviceIdType"
0x18029c309  mov     qword ptr [rsp+158h+var_118], rax
0x18029c30e  lea     rax, [rsp+158h+var_108]
0x18029c313  mov     [rsp+158h+var_130], rax
0x18029c318  lea     rax, [rsp+158h+var_118]
0x18029c31d  mov     [rsp+158h+ppv], rax
0x18029c322  lea     rdx, word_1803ED3A6
0x18029c329  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18029c32e  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18029c335  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x18029c33a  test    al, al
0x18029c33c  jz      short loc_18029C34B
0x18029c33e  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x18029c343  mov     rcx, rax; this
0x18029c346  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x18029c34b  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x18029c353  call    ?UtcUrlEscape@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::UtcUrlEscape(std::wstring &)
0x18029c358  test    eax, eax
0x18029c35a  js      short loc_18029C3BF
0x18029c35c  lea     rdx, aDeviceid; "&deviceId="
0x18029c363  lea     rcx, [rsp+158h+var_90]; Src
0x18029c36b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c370  cmp     byte ptr [rsp+158h+pcchLanguagesBuffer+1], 1
0x18029c375  setz    cl
0x18029c378  lea     r8, aS_7; "s:"
0x18029c37f  lea     rdx, asc_180395A48; "x:"
0x18029c386  test    cl, cl
0x18029c388  cmovz   rdx, r8
0x18029c38c  mov     rcx, rax; Src
0x18029c38f  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c394  mov     r8, rax
0x18029c397  lea     rdx, [rsp+158h+var_118]
0x18029c39c  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x18029c3a4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029c3a9  movups  xmm0, xmmword ptr [rax]
0x18029c3ac  movdqu  xmmword ptr [rsp+158h+var_108], xmm0
0x18029c3b2  lea     rdx, [rsp+158h+var_108]
0x18029c3b7  mov     rcx, r8; Src
0x18029c3ba  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18029c3bf  mov     [rsp+158h+pulNumLanguages], r14d
0x18029c3c4  movups  xmm0, xmmword ptr cs:off_180385810; "RacSampleNumber"
0x18029c3cb  movdqu  xmmword ptr [rsp+158h+var_108], xmm0
0x18029c3d1  movups  xmm1, xmmword ptr cs:off_180385800; "SOFTWARE\\Microsoft\\Reliability Analys"...
0x18029c3d8  movdqu  [rsp+158h+var_118], xmm1
0x18029c3de  lea     r9, [rsp+158h+pulNumLanguages]
0x18029c3e3  lea     r8, [rsp+158h+var_108]
0x18029c3e8  lea     rdx, [rsp+158h+var_118]
0x18029c3ed  mov     rcx, 0FFFFFFFF80000002h
0x18029c3f4  call    ?GetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAK@Z; Microsoft::Diagnostics::Utils::Registry::GetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong &)
0x18029c3f9  test    eax, eax
0x18029c3fb  js      short loc_18029C41D
0x18029c3fd  lea     rdx, aSampleid; "&sampleId="
0x18029c404  lea     rcx, [rsp+158h+var_90]; Src
0x18029c40c  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c411  mov     edx, [rsp+158h+pulNumLanguages]
0x18029c415  mov     rcx, rax; Src
0x18029c418  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18029c41d  xorps   xmm0, xmm0
0x18029c420  movups  [rsp+158h+var_B0], xmm0
0x18029c428  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18029c430  movdqu  [rsp+158h+var_A0], xmm1
0x18029c439  mov     word ptr [rsp+158h+var_B0], r14w
0x18029c442  lea     rcx, [rsp+158h+var_B0]
0x18029c44a  call    ?GetDeviceClass@Os@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::Os::GetDeviceClass(std::wstring &)
0x18029c44f  test    eax, eax
0x18029c451  js      short loc_18029C4A3
0x18029c453  lea     rcx, [rsp+158h+var_B0]
0x18029c45b  call    ?UtcUrlEscape@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::UtcUrlEscape(std::wstring &)
0x18029c460  test    eax, eax
0x18029c462  js      short loc_18029C4A3
0x18029c464  lea     rdx, aDeviceclass_0; "&deviceClass="
0x18029c46b  lea     rcx, [rsp+158h+var_90]; Src
0x18029c473  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c478  mov     r8, rax
0x18029c47b  lea     rdx, [rsp+158h+var_118]
0x18029c480  lea     rcx, [rsp+158h+var_B0]
0x18029c488  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029c48d  movups  xmm0, xmmword ptr [rax]
0x18029c490  movdqu  xmmword ptr [rsp+158h+var_108], xmm0
0x18029c496  lea     rdx, [rsp+158h+var_108]
0x18029c49b  mov     rcx, r8; Src
0x18029c49e  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18029c4a3  mov     [rsp+158h+pcchLanguagesBuffer], r14d
0x18029c4a8  lea     rcx, [rsp+158h+pcchLanguagesBuffer]; unsigned int *
0x18029c4ad  call    ?GetCorrectedEditionId@Os@Utils@Diagnostics@Microsoft@@SAJAEAK@Z; Microsoft::Diagnostics::Utils::Os::GetCorrectedEditionId(ulong &)
0x18029c4b2  test    eax, eax
0x18029c4b4  js      short loc_18029C4D6
0x18029c4b6  lea     rdx, aSku; "&sku="
0x18029c4bd  lea     rcx, [rsp+158h+var_90]; Src
0x18029c4c5  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c4ca  mov     edx, [rsp+158h+pcchLanguagesBuffer]
0x18029c4ce  mov     rcx, rax; Src
0x18029c4d1  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18029c4d6  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18029c4dc  test    eax, eax
0x18029c4de  jz      short loc_18029C4F4
0x18029c4e0  lea     rdx, aIscontainer1; "&isContainer=1"
0x18029c4e7  lea     rcx, [rsp+158h+var_90]; Src
0x18029c4ef  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c4f4  lea     rdx, [rsp+158h+var_90]
0x18029c4fc  lea     rcx, [rsp+158h+Src]
0x18029c504  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18029c509  nop
0x18029c50a  lea     rcx, [rsp+158h+var_B0]
0x18029c512  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029c517  nop
0x18029c518  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x18029c520  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029c525  nop
0x18029c526  lea     rcx, [rsp+158h+var_60]
0x18029c52e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029c533  nop
0x18029c534  lea     rcx, [rsp+158h+var_90]
0x18029c53c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029c541  lea     rcx, [rsp+158h+var_90]; this
0x18029c549  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x18029c54e  nop
0x18029c54f  xorps   xmm0, xmm0
0x18029c552  movups  [rsp+158h+var_B0], xmm0
0x18029c55a  mov     qword ptr [rsp+158h+var_A0], r14
0x18029c562  mov     qword ptr [rsp+158h+var_A0+8], 7
0x18029c56e  mov     word ptr [rsp+158h+var_B0], r14w
0x18029c577  lea     rcx, [rsp+158h+var_B0]
0x18029c57f  call    ?GetBuildString@Os@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::Os::GetBuildString(std::wstring &)
0x18029c584  cmp     qword ptr [rsp+158h+var_A0], r14
0x18029c58c  jz      short loc_18029C5E1
0x18029c58e  lea     rcx, [rsp+158h+var_B0]
0x18029c596  call    ?UtcUrlEscape@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::UtcUrlEscape(std::wstring &)
0x18029c59b  test    eax, eax
0x18029c59d  js      short loc_18029C5E1
0x18029c59f  lea     rdx, aOsver; "&osVer="
0x18029c5a6  lea     rcx, [rsp+158h+var_90]; Src
0x18029c5ae  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c5b3  mov     r8, rax
0x18029c5b6  lea     rdx, [rsp+158h+var_60]
0x18029c5be  lea     rcx, [rsp+158h+var_B0]
0x18029c5c6  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029c5cb  movups  xmm0, xmmword ptr [rax]
0x18029c5ce  movdqu  [rsp+158h+var_118], xmm0
0x18029c5d4  lea     rdx, [rsp+158h+var_118]
0x18029c5d9  mov     rcx, r8; Src
0x18029c5dc  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18029c5e1  xorps   xmm0, xmm0
0x18029c5e4  movups  xmmword ptr [rsp+158h+pwszLanguagesBuffer], xmm0
0x18029c5ec  mov     [rsp+158h+var_C0], r14
0x18029c5f4  mov     [rsp+158h+var_B8], 7
0x18029c600  mov     word ptr [rsp+158h+pwszLanguagesBuffer], r14w
0x18029c609  mov     [rsp+158h+pulNumLanguages], r14d
0x18029c60e  mov     [rsp+158h+pcchLanguagesBuffer], r14d
0x18029c613  lea     r9, [rsp+158h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18029c618  xor     r8d, r8d; pwszLanguagesBuffer
0x18029c61b  lea     rdx, [rsp+158h+pulNumLanguages]; pulNumLanguages
0x18029c620  lea     ebx, [r8+8]
0x18029c624  mov     ecx, ebx; dwFlags
0x18029c626  call    cs:__imp_GetSystemPreferredUILanguages
0x18029c62c  test    eax, eax
0x18029c62e  jnz     short loc_18029C63F
0x18029c630  call    cs:__imp_GetLastError
0x18029c636  cmp     eax, 7Ah ; 'z'
0x18029c639  jnz     loc_18029C6F3
0x18029c63f  mov     edx, [rsp+158h+pcchLanguagesBuffer]
0x18029c643  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x18029c64b  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18029c650  lea     r8, [rsp+158h+pwszLanguagesBuffer]
0x18029c658  cmp     [rsp+158h+var_B8], 7
0x18029c661  cmova   r8, [rsp+158h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x18029c66a  lea     r9, [rsp+158h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18029c66f  lea     rdx, [rsp+158h+pulNumLanguages]; pulNumLanguages
0x18029c674  mov     ecx, ebx; dwFlags
0x18029c676  call    cs:__imp_GetSystemPreferredUILanguages
0x18029c67c  test    eax, eax
0x18029c67e  jz      short loc_18029C6F3
0x18029c680  mov     rdx, [rsp+158h+var_C0]
0x18029c688  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x18029c690  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18029c695  cmp     [rsp+158h+var_C0], r14
0x18029c69d  jz      short loc_18029C6F3
0x18029c69f  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x18029c6a7  call    ?UtcUrlEscape@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::UtcUrlEscape(std::wstring &)
0x18029c6ac  test    eax, eax
0x18029c6ae  js      short loc_18029C6F3
0x18029c6b0  lea     rdx, aLocale; "&locale="
0x18029c6b7  lea     rcx, [rsp+158h+var_90]; Src
0x18029c6bf  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c6c4  mov     r8, rax
0x18029c6c7  lea     rdx, [rsp+158h+var_60]
0x18029c6cf  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x18029c6d7  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029c6dc  movups  xmm0, xmmword ptr [rax]
0x18029c6df  movdqu  [rsp+158h+var_118], xmm0
0x18029c6e5  lea     rdx, [rsp+158h+var_118]
0x18029c6ea  mov     rcx, r8; Src
0x18029c6ed  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18029c6f2  nop
0x18029c6f3  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x18029c6fb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18029c700  nop
0x18029c701  mov     [rsp+158h+var_F8], r14
0x18029c706  lea     rax, [rsp+158h+var_F8]
0x18029c70b  mov     [rsp+158h+ppv], rax; ppv
0x18029c710  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x18029c717  xor     edx, edx; pUnkOuter
0x18029c719  lea     r8d, [rdx+1]; dwClsContext
0x18029c71d  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x18029c724  call    cs:__imp_CoCreateInstance
0x18029c72a  mov     ebx, eax
0x18029c72c  mov     [rsp+158h+var_120], eax
0x18029c730  test    eax, eax
0x18029c732  js      loc_18029C8DB
0x18029c738  mov     qword ptr [rsp+158h+var_118], r14
0x18029c73d  mov     rcx, [rsp+158h+var_F8]
0x18029c742  mov     rax, [rcx]
0x18029c745  lea     rdx, [rsp+158h+var_118]
0x18029c74a  mov     rax, [rax+30h]
0x18029c74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029c753  mov     [rsp+158h+var_120], eax
0x18029c757  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18029c75b  test    eax, eax
0x18029c75d  js      short loc_18029C7A1
0x18029c75f  mov     rcx, qword ptr [rsp+158h+var_118]
0x18029c764  mov     rax, rdi
0x18029c767  inc     rax
0x18029c76a  cmp     [rcx+rax*2], r14w
0x18029c76f  jnz     short loc_18029C767
0x18029c771  test    rax, rax
0x18029c774  jz      short loc_18029C799
0x18029c776  lea     rdx, aRing_0; "&ring="
0x18029c77d  lea     rcx, [rsp+158h+var_90]; Src
0x18029c785  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c78a  mov     rdx, qword ptr [rsp+158h+var_118]
0x18029c78f  mov     rcx, rax; Src
0x18029c792  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18029c797  jmp     short loc_18029C7A1
0x18029c799  mov     [rsp+158h+var_120], 800700E8h
0x18029c7a1  mov     [rsp+158h+var_60], r14
0x18029c7a9  mov     rcx, [rsp+158h+var_F8]
0x18029c7ae  mov     rax, [rcx]
0x18029c7b1  lea     rdx, [rsp+158h+var_60]
0x18029c7b9  mov     rax, [rax+50h]
0x18029c7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029c7c2  mov     [rsp+158h+var_120], eax
0x18029c7c6  test    eax, eax
0x18029c7c8  js      short loc_18029C812
0x18029c7ca  mov     rcx, [rsp+158h+var_60]
0x18029c7d2  mov     rax, rdi
  ... truncated ...
```
