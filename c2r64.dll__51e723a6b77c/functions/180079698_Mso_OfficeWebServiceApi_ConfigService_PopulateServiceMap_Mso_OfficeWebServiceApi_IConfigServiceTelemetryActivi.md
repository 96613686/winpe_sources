# Mso::OfficeWebServiceApi::ConfigService::PopulateServiceMap(Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity &,Mso::OfficeWebServiceApi::FederationProviderConfiguration const &)

- ea: `0x180079698`
- end: `0x18007a18e`
- name: `?PopulateServiceMap@ConfigService@OfficeWebServiceApi@Mso@@QEAA_NAEAVIConfigServiceTelemetryActivity@23@AEBVFederationProviderConfiguration@23@@Z`
- size: `2806`
- prototype: `bool(Mso::OfficeWebServiceApi::ConfigService *__hidden this, struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *, const struct Mso::OfficeWebServiceApi::FederationProviderConfiguration *)`
- caller_count: `1`
- callee_count: `55`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180077ed0`

## callees

- `0x180004474`
- `0x180008a5c`
- `0x18000adf0`
- `0x18000b6e0`
- `0x18000c2dc`
- `0x18000ffb0`
- `0x180012bf8`
- `0x18001afdc`
- `0x18001d190`
- `0x180034970`
- `0x18003e690`
- `0x18003ed20`
- `0x18003ed8c`
- `0x180052b30`
- `0x180052e28`
- `0x18005396c`
- `0x180053970`
- `0x180063814`
- `0x180072728`
- `0x180072b90`
- `0x1800730f0`
- `0x18007317c`
- `0x180073200`
- `0x180073288`
- `0x180073414`
- `0x180073490`
- `0x180074b80`
- `0x180074ccc`
- `0x180074db0`
- `0x180075048`
- `0x18007629c`
- `0x180076ee0`
- `0x180078224`
- `0x180078f24`
- `0x180079698`
- `0x18007a190`
- `0x18007a5f0`
- `0x18007a864`
- `0x18007c188`
- `0x18007e670`
- `0x18007fe18`
- `0x180080a04`
- `0x180092c74`
- `0x18009afa0`
- `0x18009aff4`
- `0x1800a01d0`
- `0x1800b9734`
- `0x1800b97c8`
- `0x1800c88f4`
- `0x180123e8c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180079f74`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180079f74`

## string_xrefs

- `0x180079a29`: `[ConfigService] Telemetry Region can't be obtained because of error.`
- `0x180079d84`: `ConfigPopulateServiceMap`
- `0x180079b97`: `[ConfigService] Win32 App running in WDAG | Apply UseCacheOnly Flag`
- `0x1800796e2`: `[ConfigService] Shutting Down | [PopulateServiceMap] Not attempted`
- `0x180079805`: `[ConfigService] Unable to get ONetUrl for default | [PopulateServiceMap] critical failure`
- `0x180079739`: `[ConfigService] Populate is cooling down from last failure | [PopulateServiceMap] Not attempted`
- `0x18007a0d3`: `[ConfigService] Configuration Syncronous Fetch Failed | [PopulateServiceMap] Failed`
- `0x18007a037`: `[ConfigService] Configuration Syncronous Fetch Succeed | [PopulateServiceMap] Succeed`
- `0x180079efe`: `CachedOnly`
- `0x180079ed2`: `ConfigServiceUrlParams`
- `0x180079f91`: `CachedFileDateTime`
- `0x180079f25`: `CachedFileStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Mso::OfficeWebServiceApi::ConfigService::PopulateServiceMap(
        Mso::OfficeWebServiceApi::ConfigService *this,
        struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *a2,
        const struct Mso::OfficeWebServiceApi::FederationProviderConfiguration *a3)
{
  int v5; // esi
  char v6; // r14
  __int64 v7; // rdx
  __int64 v8; // r8
  Mso::OfficeWebServiceApi *v9; // rcx
  __int64 DefaultConfiguration; // rbx
  int ServiceName; // eax
  char v12; // r13
  __int128 *p_Src; // rdx
  bool v14; // al
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  const struct Mso::OfficeWebServiceApi::FederationProviderConfiguration *v19; // r8
  __int64 v20; // rax
  const wchar_t *v21; // r8
  bool v22; // al
  __int64 v23; // rax
  __int64 v24; // rbx
  unsigned int v25; // eax
  __int64 v26; // rdx
  Mso::AppGuard *v27; // rcx
  __int64 v28; // r8
  struct _GUID *v29; // rdx
  char v30; // di
  struct _GUID *v31; // rdx
  bool v32; // al
  unsigned __int64 v33; // r12
  bool v34; // al
  int v35; // eax
  _QWORD *v36; // rax
  int v37; // eax
  int v38; // r9d
  bool v39; // al
  struct Mso::Telemetry::IDataFieldCollection *v40; // rsi
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  struct Mso::Telemetry::IDataFieldCollection *v45; // rsi
  __int64 v46; // rax
  struct Mso::Telemetry::IDataFieldCollection *v47; // rax
  __int64 v48; // r8
  struct Mso::Telemetry::IDataFieldCollection *v49; // rax
  struct Mso::Telemetry::IDataFieldCollection *v50; // rsi
  struct Mso::Telemetry::IDataFieldCollection *v51; // rax
  unsigned int v52; // r12d
  Mso::Logging *v53; // rcx
  Mso::Logging *v55; // rcx
  int Reserved; // [rsp+20h] [rbp-E0h]
  __int16 v57; // [rsp+30h] [rbp-D0h] BYREF
  const char *v58; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v59; // [rsp+40h] [rbp-C0h] BYREF
  const char *v60; // [rsp+48h] [rbp-B8h] BYREF
  char v61; // [rsp+50h] [rbp-B0h]
  _BYTE v62[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v63[2]; // [rsp+5Ah] [rbp-A6h] BYREF
  _BYTE v64[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  Mso::OfficeWebServiceApi::ConfigService *v65; // [rsp+60h] [rbp-A0h] BYREF
  Mso::OfficeWebServiceApi::Service *v66[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v67; // [rsp+78h] [rbp-88h]
  _QWORD v68[2]; // [rsp+80h] [rbp-80h] BYREF
  int v69; // [rsp+90h] [rbp-70h] BYREF
  __int16 v70; // [rsp+94h] [rbp-6Ch]
  struct _GUID v71; // [rsp+A0h] [rbp-60h] BYREF
  char v72; // [rsp+B0h] [rbp-50h]
  struct _GUID Buf1; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v74[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v75; // [rsp+E0h] [rbp-20h]
  __int16 v76; // [rsp+E4h] [rbp-1Ch]
  __int128 v77; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v78; // [rsp+F8h] [rbp-8h]
  __int64 v79; // [rsp+100h] [rbp+0h]
  __int128 Src; // [rsp+108h] [rbp+8h] BYREF
  __m128i si128; // [rsp+118h] [rbp+18h]
  _QWORD v82[5]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v83[192]; // [rsp+150h] [rbp+50h] BYREF
  wchar_t v84[256]; // [rsp+210h] [rbp+110h] BYREF

  v5 = (int)this;
  v65 = this;
  v6 = 0;
  if ( !*((_BYTE *)this + 568) )
  {
    if ( !Mso::OfficeWebServiceApi::ConfigService::PopulateTimeoutElapsed(this, a3) )
    {
      v58 = "[ConfigService] Populate is cooling down from last failure | [PopulateServiceMap] Not attempted";
      Mso::Diagnostics::SendDiagnosticTrace<>(509154186, 823, 50, 2, (__int64)&v58);
      v7 = 509363916;
      v8 = 0x100000;
      goto LABEL_3;
    }
    Src = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src) = 0;
    if ( Mso::OfficeWebServiceApi::IsCloudSwitcherEnabled(v9) )
    {
      Mso::OfficeWebServiceApi::CloudSwitcher::GetConfigServiceEndpoint(&v71);
      std::wstring::operator=(&Src);
      std::wstring::~wstring(&v71);
    }
    else
    {
      DefaultConfiguration = Mso::OfficeWebServiceApi::GetDefaultConfiguration(v83);
      ServiceName = Mso::OfficeWebServiceApi::ConfigService::GetServiceName(&v71, 0);
      Mso::OfficeWebServiceApi::ConfigService::FindServiceInMap(
        v5,
        (unsigned int)v66,
        (_DWORD)a2,
        ServiceName,
        DefaultConfiguration);
      std::wstring::~wstring(&v71);
      Mso::OfficeWebServiceApi::FederationProviderConfiguration::~FederationProviderConfiguration((Mso::OfficeWebServiceApi::FederationProviderConfiguration *)v83);
      if ( !v66[0] )
      {
        v58 = "[ConfigService] Unable to get ONetUrl for default | [PopulateServiceMap] critical failure";
        Mso::Diagnostics::SendDiagnosticTrace<>(509154185, 823, 10, 2, (__int64)&v58);
        (*(void (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *, __int64, __int64))(*(_QWORD *)a2 + 16LL))(
          a2,
          509154184,
          1);
        std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v66);
LABEL_90:
        std::wstring::~wstring(&Src);
        return 0;
      }
      Mso::OfficeWebServiceApi::Service::GetUrl(v66[0]);
      std::wstring::operator=(&Src);
      std::wstring::~wstring(&v71);
      std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v66);
    }
    v12 = 1;
    if ( dword_18021DC20 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 24LL) )
    {
      Init_thread_header(&dword_18021DC20);
      if ( dword_18021DC20 == -1 )
      {
        byte_18021DC24 = MsoDwRegGetDw((const struct _msoreg *)&vmsoridPhoneOnlyAuth) == 1;
        Init_thread_footer(&dword_18021DC20);
      }
    }
    if ( byte_18021DC24 )
      std::wstring::append(&Src, L"?flights=Client.PhoneAuthentication,Client.OneDriveSiteChange");
    p_Src = &Src;
    if ( si128.m128i_i64[1] > 7uLL )
      p_Src = (__int128 *)Src;
    Mso::OfficeWebServiceApi::CreateUrlBuilder(&v58, p_Src);
    if ( !v58 )
    {
      (*(void (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *, __int64, __int64))(*(_QWORD *)a2 + 16LL))(
        a2,
        509363915,
        1);
LABEL_89:
      Mso::TCntPtr<Mso::OfficeWebServiceApi::IAuthTicket>::Clear(&v58);
      goto LABEL_90;
    }
    if ( byte_180213128 < 0 )
      v14 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180213128);
    else
      v14 = byte_180213128 != 0;
    if ( v14 )
    {
      v15 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(&v58);
      v16 = 576;
    }
    else
    {
      v15 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(&v58);
      v16 = 71;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 24LL))(v15, v16);
    memset(v84, 0, sizeof(v84));
    if ( (unsigned int)MsoFRegReadWz((const struct _msoreg *)&vmsoridConfigServiceEnvironment, v84, 0x100u) )
    {
      v17 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(&v58);
      (*(void (__fastcall **)(__int64, const wchar_t *, wchar_t *))(*(_QWORD *)v17 + 48LL))(v17, L"cenv", v84);
    }
    if ( *((_QWORD *)a3 + 2) )
    {
      v18 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(&v58);
      v19 = a3;
      if ( *((_QWORD *)a3 + 3) > 7u )
        v19 = *(const struct Mso::OfficeWebServiceApi::FederationProviderConfiguration **)a3;
      (*(void (__fastcall **)(__int64, const wchar_t *, const struct Mso::OfficeWebServiceApi::FederationProviderConfiguration *))(*(_QWORD *)v18 + 48LL))(
        v18,
        L"fp",
        v19);
    }
    if ( !*((_BYTE *)a3 + 64) )
    {
      v59 = (__int64)"[ConfigService] Telemetry Region can't be obtained because of error.";
      Mso::Diagnostics::SendDiagnosticTrace<>(507887968, 823, 10, 2, (__int64)&v59);
    }
    std::optional<std::wstring>::value_or<wchar_t const (&)[1]>((char *)a3 + 32, v82);
    if ( v82[2] )
    {
      v20 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(&v58);
      v21 = (const wchar_t *)v82;
      if ( v82[3] > 7u )
        v21 = (const wchar_t *)v82[0];
    }
    else
    {
      if ( byte_180213138 < 0 )
        v22 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180213138);
      else
        v22 = byte_180213138 != 0;
      if ( !v22
        || Mso::OfficeWebServiceApi::CloudSwitcher::s_selectedCloud != 1
        && Mso::OfficeWebServiceApi::CloudSwitcher::s_selectedCloud != 100
        || *((_QWORD *)a3 + 2) )
      {
LABEL_47:
        v23 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(&v58);
        (*(void (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v23 + 40LL))(v23, L"crev", 3);
        Mso::Make<Mso::OfficeWebServiceApi::ConfigServiceCallback,Mso::OfficeWebServiceApi::ConfigServiceCallback,Mso::OfficeWebServiceApi::FederationProviderConfiguration const &>(
          &v59,
          a3);
        v24 = v59;
        if ( v59 )
        {
          *(_QWORD *)(v59 + 368) = "(";
          v25 = Mso::OfficeWebServiceApi::ConfigService::UseResponseOverrideIfPresent(v65, a3, v24);
          v28 = v25;
          if ( v25 == 0x400000 )
          {
            v59 = 12582912;
            if ( Mso::AppGuard::IsWin32AppRunningInWdag(v27) )
            {
              v59 = (__int64)"[ConfigService] Win32 App running in WDAG | Apply UseCacheOnly Flag";
              Mso::Diagnostics::SendDiagnosticTrace<>(512230345, 823, 50, 2, (__int64)&v59);
              v59 = 29360128;
            }
            Buf1 = *Mso::Logging::GetCurrentCorrelation((Mso::Logging *)&v71, v29);
            v30 = 0;
            LOBYTE(v57) = 0;
            if ( !memcmp(&Buf1, &GUID_NULL, 0x10u) )
            {
              Buf1 = *OGuid::Create((OGuid *)&v71, v31);
              Mso::Logging::CorrelationScope::SetCorrelation((Mso::Logging::CorrelationScope *)&v57, &Buf1);
              v30 = v57;
            }
            (*(void (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *, struct _GUID *))(*(_QWORD *)a2 + 48LL))(
              a2,
              &Buf1);
            if ( byte_180213148 < 0 )
              v32 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_180213148);
            else
              v32 = byte_180213148 != 0;
            v33 = v59 | (((unsigned __int64)v32 << 21) + 1);
            if ( byte_180213118 < 0 )
              v34 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180213118);
            else
              v34 = byte_180213118 != 0;
            if ( v34 )
              v33 |= 0x100u;
            if ( (*(unsigned int (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *))(*(_QWORD *)a2 + 8LL))(a2) )
              v35 = (*(__int64 (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *))(*(_QWORD *)a2 + 8LL))(a2);
            else
              v35 = 507581398;
            v67 = v35;
            v69 = v35;
            LODWORD(v65) = 4;
            v36 = (_QWORD *)std::make_shared<Mso::OfficeWebServiceApi::ServiceRequestTelemetryActivity,MsoReserveTag &,enum Mso::OfficeWebServiceApi::ServiceRequestTelemetryApi>(
                              &v71,
                              &v69,
                              &v65);
            v68[0] = *v36;
            v68[1] = v36[1];
            *v36 = 0;
            v36[1] = 0;
            std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(&v71);
            v71 = Buf1;
            v72 = 1;
            v37 = Mso::TCntPtr<Mso::Http::IRequest>::TCntPtr<Mso::Http::IRequest>(&v60, &v58);
            LODWORD(v65) = Mso::OfficeWebServiceApi::OfficeDotComFileRequestInternal(
                             (unsigned int)v68,
                             v37,
                             v24,
                             v33,
                             Reserved,
                             (__int64)&v71);
            (*(void (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *, unsigned __int64))(*(_QWORD *)a2 + 40LL))(
              a2,
              v33);
            LODWORD(v59) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v68[0] + 96LL))(v68[0]);
            if ( byte_180213108 < 0 )
              v39 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180213108);
            else
              v39 = byte_180213108 != 0;
            if ( v39 )
            {
              *(_QWORD *)&v71.Data1 = &off_1801AECC0;
              *(_QWORD *)v71.Data4 = "ConfigPopulateServiceMap";
              v57 = 366;
              LOWORD(v69) = 2;
              BYTE2(v69) = 1;
              v62[1] = 0;
              v63[1] = 0;
              v64[1] = 0;
              Mso::Telemetry::EventFlags::EventFlags(
                (unsigned int)&v60,
                (unsigned int)v64,
                (unsigned int)v63,
                (unsigned int)v62,
                (__int64)&v69,
                (__int64)&v57);
              Mso::Telemetry::Activity::Activity(v66, &v71, 0, &v60);
              v40 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v66);
              v69 = 0;
              v70 = 0;
              TaggingUtilities::ConvertTagToStringInternal<char>(v67, &v69);
              v41 = std::string::string(&v71, &v69);
              Mso::Telemetry::IDataFieldCollection::Add<std::string>(v40, "Tag", v41);
              v42 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(&v58);
              if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 160LL))(v42) )
              {
                v43 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(&v58);
                v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 160LL))(v43);
                std::wstring::wstring(&v71, v44);
                v60 = (const char *)std::wstring::find(&v71, L"?", 0);
                if ( v60 != (const char *)-1LL )
                {
                  v45 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v66);
                  v46 = std::wstring::substr(&v71, v74, v60 + 1, -1);
                  Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(v45, "ConfigServiceUrlParams", v46, 4);
                }
                std::wstring::~wstring(&v71);
              }
              v47 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v66);
              LOBYTE(v48) = BYTE3(v33) & 1;
              Mso::Telemetry::IDataFieldCollection::Add<bool>(v47, "CachedOnly", v48);
              v49 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v66);
              Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v49, "CachedFileStatus", (unsigned int)v59, 4);
              (*(void (__fastcall **)(_QWORD, const char **))(*(_QWORD *)v68[0] + 112LL))(v68[0], &v60);
              if ( v61 )
              {
                v50 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v66);
                if ( !v61 )
                  _invoke_watson(0, 0, 0, 0, 0);
                Mso::DateTime::FileTimeToISO8601(&v71, &v60);
                Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(v50, "CachedFileDateTime", &v71, 4);
              }
              v51 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v66);
              v71 = Buf1;
              Mso::Telemetry::IDataFieldCollection::Add<_GUID>(v51, "CorrelationId", &v71);
              v52 = (unsigned int)v65;
              Mso::Telemetry::Activity::SetSuccess((Mso::Telemetry::Activity *)v66, (_DWORD)v65 == 0);
              Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v66);
            }
            else
            {
              v52 = (unsigned int)v65;
            }
            v78 = 0;
            v79 = 7;
            v74[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
            v76 = 4;
            v77 = 0;
            LOWORD(v77) = 0;
            v74[1] = "RequestStatus";
            if ( v52 )
            {
              v75 = v52;
              v60 = "[ConfigService] Configuration Syncronous Fetch Failed | [PopulateServiceMap] Failed";
              Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
                509154178,
                823,
                15,
                v38,
                (__int64)&v60,
                (__int64)v74);
              std::wstring::~wstring(&v77);
              (*(void (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
                a2,
                509363912,
                v52);
              std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v68);
              if ( v30 )
                Mso::Logging::EndCurrentCorrelation(v55);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
              std::wstring::~wstring(v82);
              goto LABEL_89;
            }
            v75 = 0;
            v60 = "[ConfigService] Configuration Syncronous Fetch Succeed | [PopulateServiceMap] Succeed";
            Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
              509154180,
              823,
              50,
              v38,
              (__int64)&v60,
              (__int64)v74);
            std::wstring::~wstring(&v77);
            (*(void (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
              a2,
              509154179,
              0);
            std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v68);
            if ( v30 )
              Mso::Logging::EndCurrentCorrelation(v53);
          }
          else if ( v25 )
          {
            v12 = 0;
            (*(void (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
              a2,
              509363913,
              v25);
          }
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v24 + 8LL))(v24, v26, v28);
          v6 = v12;
        }
        else
        {
          (*(void (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *, __int64, __int64))(*(_QWORD *)a2 + 16LL))(
            a2,
            509363914,
            1);
        }
        std::wstring::~wstring(v82);
        Mso::TCntPtr<Mso::OfficeWebServiceApi::IAuthTicket>::Clear(&v58);
        std::wstring::~wstring(&Src);
        return v6;
      }
      v20 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(&v58);
      v21 = L"GLOBAL";
    }
    (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v20 + 48LL))(
      v20,
      L"telemetryRegion",
      v21);
    goto LABEL_47;
  }
  v58 = "[ConfigService] Shutting Down | [PopulateServiceMap] Not attempted";
  Mso::Diagnostics::SendDiagnosticTrace<>(509154187, 823, 50, 2, (__int64)&v58);
  v7 = 509363917;
  v8 = 1;
LABEL_3:
  (*(void (__fastcall **)(struct Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity *, __int64, __int64))(*(_QWORD *)a2 + 16LL))(
    a2,
    v7,
    v8);
  return 0;
}

```

## disassembly

```asm
0x180079698  mov     [rsp-8+arg_18], rbx
0x18007969d  push    rbp
0x18007969e  push    rsi
0x18007969f  push    rdi
0x1800796a0  push    r12
0x1800796a2  push    r13
0x1800796a4  push    r14
0x1800796a6  push    r15
0x1800796a8  lea     rbp, [rsp-320h]
0x1800796b0  sub     rsp, 420h
0x1800796b7  mov     rax, cs:__security_cookie
0x1800796be  xor     rax, rsp
0x1800796c1  mov     [rbp+350h+var_40], rax
0x1800796c8  mov     rdi, r8
0x1800796cb  mov     r15, rdx
0x1800796ce  mov     rsi, rcx
0x1800796d1  mov     [rsp+450h+var_3F0], rcx
0x1800796d6  xor     r14d, r14d
0x1800796d9  cmp     [rcx+238h], r14b
0x1800796e0  jz      short loc_18007972D
0x1800796e2  lea     rax, aConfigserviceS; "[ConfigService] Shutting Down | [Popula"...
0x1800796e9  mov     [rsp+450h+var_418], rax
0x1800796ee  lea     r9d, [r14+2]
0x1800796f2  lea     rax, [rsp+450h+var_418]
0x1800796f7  mov     [rsp+450h+Reserved], rax
0x1800796fc  mov     edx, 337h
0x180079701  mov     ecx, 1E59138Bh
0x180079706  lea     r8d, [r14+32h]
0x18007970a  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x18007970f  mov     edx, 1E5C46CDh
0x180079714  lea     r8d, [r14+1]
0x180079718  mov     rax, [r15]
0x18007971b  mov     rcx, r15
0x18007971e  mov     rax, [rax+10h]
0x180079722  call    cs:__guard_dispatch_icall_fptr
0x180079728  jmp     loc_18007A162
0x18007972d  mov     rdx, rdi; struct Mso::OfficeWebServiceApi::FederationProviderConfiguration *
0x180079730  call    ?PopulateTimeoutElapsed@ConfigService@OfficeWebServiceApi@Mso@@QEAA_NAEBVFederationProviderConfiguration@23@@Z; Mso::OfficeWebServiceApi::ConfigService::PopulateTimeoutElapsed(Mso::OfficeWebServiceApi::FederationProviderConfiguration const &)
0x180079735  test    al, al
0x180079737  jnz     short loc_180079775
0x180079739  lea     rax, aConfigserviceP; "[ConfigService] Populate is cooling dow"...
0x180079740  mov     [rsp+450h+var_418], rax
0x180079745  mov     r9d, 2
0x18007974b  lea     rax, [rsp+450h+var_418]
0x180079750  mov     [rsp+450h+Reserved], rax
0x180079755  mov     edx, 337h
0x18007975a  mov     ecx, 1E59138Ah
0x18007975f  lea     r8d, [r9+30h]
0x180079763  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x180079768  mov     edx, 1E5C46CCh
0x18007976d  mov     r8d, 100000h
0x180079773  jmp     short loc_180079718
0x180079775  xorps   xmm0, xmm0
0x180079778  movups  [rbp+350h+Src], xmm0
0x18007977c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180079784  movdqu  [rbp+350h+var_338], xmm1
0x180079789  mov     word ptr [rbp+350h+Src], r14w
0x18007978e  call    ?IsCloudSwitcherEnabled@OfficeWebServiceApi@Mso@@YA_NXZ; Mso::OfficeWebServiceApi::IsCloudSwitcherEnabled(void)
0x180079793  test    al, al
0x180079795  jz      short loc_1800797BA
0x180079797  lea     rcx, [rbp+350h+var_3B0]
0x18007979b  call    ?GetConfigServiceEndpoint@CloudSwitcher@OfficeWebServiceApi@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::OfficeWebServiceApi::CloudSwitcher::GetConfigServiceEndpoint(void)
0x1800797a0  mov     rdx, rax
0x1800797a3  lea     rcx, [rbp+350h+Src]
0x1800797a7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800797ac  lea     rcx, [rbp+350h+var_3B0]; void *
0x1800797b0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800797b5  jmp     loc_180079884
0x1800797ba  lea     rcx, [rbp+350h+var_300]
0x1800797be  call    ?GetDefaultConfiguration@OfficeWebServiceApi@Mso@@YA?AVFederationProviderConfiguration@12@XZ; Mso::OfficeWebServiceApi::GetDefaultConfiguration(void)
0x1800797c3  mov     rbx, rax
0x1800797c6  xor     edx, edx
0x1800797c8  lea     rcx, [rbp+350h+var_3B0]
0x1800797cc  call    ?GetServiceName@ConfigService@OfficeWebServiceApi@Mso@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4URL@ConfigURL@23@@Z; Mso::OfficeWebServiceApi::ConfigService::GetServiceName(Mso::OfficeWebServiceApi::ConfigURL::URL)
0x1800797d1  mov     [rsp+450h+Reserved], rbx
0x1800797d6  mov     r9, rax
0x1800797d9  mov     r8, r15
0x1800797dc  lea     rdx, [rsp+450h+var_3E8]
0x1800797e1  mov     rcx, rsi
0x1800797e4  call    ?FindServiceInMap@ConfigService@OfficeWebServiceApi@Mso@@QEAA?AV?$shared_ptr@VService@OfficeWebServiceApi@Mso@@@std@@AEAVIConfigServiceTelemetryActivity@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@AEBVFederationProviderConfiguration@23@@Z; Mso::OfficeWebServiceApi::ConfigService::FindServiceInMap(Mso::OfficeWebServiceApi::IConfigServiceTelemetryActivity &,std::wstring const &,Mso::OfficeWebServiceApi::FederationProviderConfiguration const &)
0x1800797e9  lea     rcx, [rbp+350h+var_3B0]; void *
0x1800797ed  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800797f2  lea     rcx, [rbp+350h+var_300]; this
0x1800797f6  call    ??1FederationProviderConfiguration@OfficeWebServiceApi@Mso@@QEAA@XZ; Mso::OfficeWebServiceApi::FederationProviderConfiguration::~FederationProviderConfiguration(void)
0x1800797fb  mov     rcx, [rsp+450h+var_3E8]; this
0x180079800  test    rcx, rcx
0x180079803  jnz     short loc_18007985C
0x180079805  lea     rax, aConfigserviceU; "[ConfigService] Unable to get ONetUrl f"...
0x18007980c  mov     [rsp+450h+var_418], rax
0x180079811  lea     r9d, [rcx+2]
0x180079815  lea     rax, [rsp+450h+var_418]
0x18007981a  mov     [rsp+450h+Reserved], rax
0x18007981f  mov     edx, 337h
0x180079824  mov     ecx, 1E591389h
0x180079829  lea     r8d, [r9+8]
0x18007982d  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x180079832  mov     rax, [r15]
0x180079835  mov     edx, 1E591388h
0x18007983a  mov     r8d, 1
0x180079840  mov     rcx, r15
0x180079843  mov     rax, [rax+10h]
0x180079847  call    cs:__guard_dispatch_icall_fptr
0x18007984d  lea     rcx, [rsp+450h+var_3E8]; void *
0x180079852  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x180079857  jmp     loc_18007A159
0x18007985c  lea     rdx, [rbp+350h+var_3B0]
0x180079860  call    ?GetUrl@Service@OfficeWebServiceApi@Mso@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::OfficeWebServiceApi::Service::GetUrl(void)
0x180079865  mov     rdx, rax
0x180079868  lea     rcx, [rbp+350h+Src]
0x18007986c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180079871  lea     rcx, [rbp+350h+var_3B0]; void *
0x180079875  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007987a  lea     rcx, [rsp+450h+var_3E8]; void *
0x18007987f  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x180079884  mov     ecx, cs:_tls_index
0x18007988a  mov     rax, gs:58h
0x180079893  mov     edx, 18h
0x180079898  mov     rax, [rax+rcx*8]
0x18007989c  mov     r13d, 1
0x1800798a2  mov     eax, [rdx+rax]
0x1800798a5  cmp     cs:dword_18021DC20, eax
0x1800798ab  jle     short loc_1800798E4
0x1800798ad  lea     rcx, dword_18021DC20
0x1800798b4  call    _Init_thread_header
0x1800798b9  cmp     cs:dword_18021DC20, 0FFFFFFFFh
0x1800798c0  jnz     short loc_1800798E4
0x1800798c2  lea     rcx, ?vmsoridPhoneOnlyAuth@@3U_msoreg@@B; struct _msoreg *
0x1800798c9  call    ?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1800798ce  cmp     eax, r13d
0x1800798d1  setz    cs:byte_18021DC24
0x1800798d8  lea     rcx, dword_18021DC20
0x1800798df  call    _Init_thread_footer
0x1800798e4  cmp     cs:byte_18021DC24, r14b
0x1800798eb  jz      short loc_1800798FD
0x1800798ed  lea     rdx, aFlightsClientP; "?flights=Client.PhoneAuthentication,Cli"...
0x1800798f4  lea     rcx, [rbp+350h+Src]; Src
0x1800798f8  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800798fd  lea     rdx, [rbp+350h+Src]
0x180079901  cmp     qword ptr [rbp+350h+var_338+8], 7
0x180079906  cmova   rdx, qword ptr [rbp+350h+Src]
0x18007990b  lea     rcx, [rsp+450h+var_418]
0x180079910  call    ?CreateUrlBuilder@OfficeWebServiceApi@Mso@@YA?AV?$TCntPtr@UIUrlBuilder@OfficeWebServiceApi@Mso@@@2@PEB_W@Z; Mso::OfficeWebServiceApi::CreateUrlBuilder(wchar_t const *)
0x180079915  cmp     [rsp+450h+var_418], r14
0x18007991a  jnz     short loc_180079939
0x18007991c  mov     rax, [r15]
0x18007991f  mov     r8d, r13d
0x180079922  mov     edx, 1E5C46CBh
0x180079927  mov     rcx, r15
0x18007992a  mov     rax, [rax+10h]
0x18007992e  call    cs:__guard_dispatch_icall_fptr
0x180079934  jmp     loc_18007A14F
0x180079939  mov     al, cs:byte_180213128
0x18007993f  test    al, al
0x180079941  js      short loc_180079948
0x180079943  setnz   al
0x180079946  jmp     short loc_180079954
0x180079948  lea     rcx, byte_180213128; this
0x18007994f  call    ?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x180079954  lea     rcx, [rsp+450h+var_418]
0x180079959  test    al, al
0x18007995b  jz      short loc_180079969
0x18007995d  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x180079962  mov     edx, 240h
0x180079967  jmp     short loc_180079973
0x180079969  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x18007996e  mov     edx, 47h ; 'G'
0x180079973  mov     rcx, rax
0x180079976  mov     rax, [rax]
0x180079979  mov     rax, [rax+18h]
0x18007997d  call    cs:__guard_dispatch_icall_fptr
0x180079983  mov     [rbp+350h+var_240], r14w
0x18007998b  xor     edx, edx; Val
0x18007998d  mov     r8d, 1FEh; Size
0x180079993  lea     rcx, [rbp+350h+var_23E]; void *
0x18007999a  call    memset
0x18007999f  mov     r8d, 100h; unsigned int
0x1800799a5  lea     rdx, [rbp+350h+var_240]; wchar_t *
0x1800799ac  lea     rcx, ?vmsoridConfigServiceEnvironment@@3U_msoreg@@B; struct _msoreg *
0x1800799b3  call    ?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z; MsoFRegReadWz(_msoreg const *,wchar_t *,ulong)
0x1800799b8  test    eax, eax
0x1800799ba  jz      short loc_1800799E4
0x1800799bc  lea     rcx, [rsp+450h+var_418]
0x1800799c1  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x1800799c6  mov     rcx, rax
0x1800799c9  mov     rax, [rax]
0x1800799cc  lea     r8, [rbp+350h+var_240]
0x1800799d3  lea     rdx, aCenv; "cenv"
0x1800799da  mov     rax, [rax+30h]
0x1800799de  call    cs:__guard_dispatch_icall_fptr
0x1800799e4  cmp     [rdi+10h], r14
0x1800799e8  jz      short loc_180079A18
0x1800799ea  lea     rcx, [rsp+450h+var_418]
0x1800799ef  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x1800799f4  mov     rcx, rax
0x1800799f7  mov     rax, [rax]
0x1800799fa  mov     r8, rdi
0x1800799fd  cmp     qword ptr [rdi+18h], 7
0x180079a02  jbe     short loc_180079A07
0x180079a04  mov     r8, [rdi]
0x180079a07  lea     rdx, aFp; "fp"
0x180079a0e  mov     rax, [rax+30h]
0x180079a12  call    cs:__guard_dispatch_icall_fptr
0x180079a18  mov     esi, 337h
0x180079a1d  mov     r12d, 2
0x180079a23  cmp     [rdi+40h], r14b
0x180079a27  jnz     short loc_180079A53
0x180079a29  lea     rax, aConfigserviceT; "[ConfigService] Telemetry Region can't "...
0x180079a30  mov     [rsp+450h+var_410], rax
0x180079a35  mov     r9d, r12d
0x180079a38  lea     rax, [rsp+450h+var_410]
0x180079a3d  mov     [rsp+450h+Reserved], rax
0x180079a42  lea     r8d, [r12+8]
0x180079a47  mov     edx, esi
0x180079a49  mov     ecx, 1E45C160h
0x180079a4e  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x180079a53  lea     rdx, [rbp+350h+var_328]
0x180079a57  lea     rcx, [rdi+20h]
0x180079a5b  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEGBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x180079a60  cmp     [rbp+350h+var_318], r14
0x180079a64  jz      short loc_180079A80
0x180079a66  lea     rcx, [rsp+450h+var_418]
0x180079a6b  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x180079a70  lea     r8, [rbp+350h+var_328]
0x180079a74  cmp     [rbp+350h+var_310], 7
0x180079a79  cmova   r8, [rbp+350h+var_328]
0x180079a7e  jmp     short loc_180079AC6
0x180079a80  mov     al, cs:byte_180213138
0x180079a86  test    al, al
0x180079a88  js      short loc_180079A8F
0x180079a8a  setnz   al
0x180079a8d  jmp     short loc_180079A9B
0x180079a8f  lea     rcx, byte_180213138; this
0x180079a96  call    ?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x180079a9b  test    al, al
0x180079a9d  jz      short loc_180079ADD
0x180079a9f  mov     eax, cs:?s_selectedCloud@CloudSwitcher@OfficeWebServiceApi@Mso@@3U?$atomic@I@std@@A; std::atomic<uint> Mso::OfficeWebServiceApi::CloudSwitcher::s_selectedCloud
0x180079aa5  cmp     eax, r13d
0x180079aa8  jz      short loc_180079AAF
0x180079aaa  cmp     eax, 64h ; 'd'
0x180079aad  jnz     short loc_180079ADD
0x180079aaf  cmp     [rdi+10h], r14
0x180079ab3  jnz     short loc_180079ADD
0x180079ab5  lea     rcx, [rsp+450h+var_418]
0x180079aba  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x180079abf  lea     r8, aGlobal; "GLOBAL"
0x180079ac6  mov     rcx, rax
0x180079ac9  mov     rax, [rax]
0x180079acc  lea     rdx, aTelemetryregio_0; "telemetryRegion"
0x180079ad3  mov     rax, [rax+30h]
0x180079ad7  call    cs:__guard_dispatch_icall_fptr
0x180079add  lea     rcx, [rsp+450h+var_418]
0x180079ae2  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x180079ae7  mov     rcx, rax
0x180079aea  mov     rax, [rax]
0x180079aed  mov     r8d, 3
0x180079af3  lea     rdx, aCrev; "crev"
0x180079afa  mov     rax, [rax+28h]
0x180079afe  call    cs:__guard_dispatch_icall_fptr
0x180079b04  mov     rdx, rdi
0x180079b07  lea     rcx, [rsp+450h+var_410]
0x180079b0c  call    ??$Make@VConfigServiceCallback@OfficeWebServiceApi@Mso@@V123@AEBVFederationProviderConfiguration@23@@Mso@@YA?AV?$TCntPtr@VConfigServiceCallback@OfficeWebServiceApi@Mso@@@0@AEBVFederationProviderConfiguration@OfficeWebServiceApi@0@@Z; Mso::Make<Mso::OfficeWebServiceApi::ConfigServiceCallback,Mso::OfficeWebServiceApi::ConfigServiceCallback,Mso::OfficeWebServiceApi::FederationProviderConfiguration const &>(Mso::OfficeWebServiceApi::FederationProviderConfiguration const &)
0x180079b11  mov     rbx, [rsp+450h+var_410]
0x180079b16  test    rbx, rbx
0x180079b19  jnz     short loc_180079B38
0x180079b1b  mov     rax, [r15]
0x180079b1e  mov     r8d, r13d
0x180079b21  mov     edx, 1E5C46CAh
0x180079b26  mov     rcx, r15
0x180079b29  mov     rax, [rax+10h]
0x180079b2d  call    cs:__guard_dispatch_icall_fptr
0x180079b33  jmp     loc_18007A0AB
0x180079b38  lea     rax, ?Config16_xsd@Config16Xsd@OfficeWebServiceApi@Mso@@3U_Config16_xsd@123@B; "("
0x180079b3f  mov     [rbx+170h], rax
0x180079b46  mov     r8, rbx
0x180079b49  mov     rdx, rdi
0x180079b4c  mov     rcx, [rsp+450h+var_3F0]
0x180079b51  call    ?UseResponseOverrideIfPresent@ConfigService@OfficeWebServiceApi@Mso@@AEAA?AW4Flags@Status@23@AEBVFederationProviderConfiguration@23@AEAVConfigServiceCallback@23@@Z; Mso::OfficeWebServiceApi::ConfigService::UseResponseOverrideIfPresent(Mso::OfficeWebServiceApi::FederationProviderConfiguration const &,Mso::OfficeWebServiceApi::ConfigServiceCallback &)
0x180079b56  mov     r8d, eax
0x180079b59  cmp     eax, 400000h
0x180079b5e  jz      short loc_180079B85
0x180079b60  test    eax, eax
0x180079b62  jz      loc_18007A098
0x180079b68  mov     r13b, r14b
0x180079b6b  mov     rax, [r15]
0x180079b6e  mov     edx, 1E5C46C9h
0x180079b73  mov     rcx, r15
0x180079b76  mov     rax, [rax+10h]
0x180079b7a  call    cs:__guard_dispatch_icall_fptr
0x180079b80  jmp     loc_18007A098
0x180079b85  mov     [rsp+450h+var_410], 0C00000h
0x180079b8e  call    ?IsWin32AppRunningInWdag@AppGuard@Mso@@YA_NXZ; Mso::AppGuard::IsWin32AppRunningInWdag(void)
0x180079b93  test    al, al
0x180079b95  jz      short loc_180079BCB
0x180079b97  lea     rax, aConfigserviceW; "[ConfigService] Win32 App running in WD"...
0x180079b9e  mov     [rsp+450h+var_410], rax
0x180079ba3  mov     r9d, r12d
0x180079ba6  lea     rax, [rsp+450h+var_410]
0x180079bab  mov     [rsp+450h+Reserved], rax
0x180079bb0  mov     r8d, 32h ; '2'
0x180079bb6  mov     edx, esi
  ... truncated ...
```
