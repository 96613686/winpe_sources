# Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::~ConfigServiceTelemetryActivity(void)

- ea: `0x1800759c0`
- end: `0x180076202`
- name: `??1ConfigServiceTelemetryActivity@OfficeWebServiceApi@Mso@@UEAA@XZ`
- size: `2114`
- prototype: `void __fastcall(Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity *__hidden this)`
- caller_count: `7`
- callee_count: `38`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180076b70`
- `0x180076c38`
- `0x180077894`
- `0x1800782a4`
- `0x180078780`
- `0x180078b34`
- `0x1800794b0`

## callees

- `0x180004474`
- `0x18000adf0`
- `0x18000c5f8`
- `0x18000d534`
- `0x180010414`
- `0x180013f28`
- `0x18002cbe4`
- `0x180031484`
- `0x180034970`
- `0x18003e690`
- `0x180052b60`
- `0x180053970`
- `0x180061b8c`
- `0x180072728`
- `0x180073074`
- `0x1800730f0`
- `0x18007317c`
- `0x180073200`
- `0x180073288`
- `0x18007330c`
- `0x180073388`
- `0x180073414`
- `0x180074ccc`
- `0x180075048`
- `0x180075868`
- `0x1800759c0`
- `0x18007629c`
- `0x1800764dc`
- `0x180076dd8`
- `0x18007733c`
- `0x18007a424`
- `0x18007a5f0`
- `0x18007d08c`
- `0x1800b9534`
- `0x1800b9734`
- `0x1800b97c8`
- `0x1800fb7a8`
- `0x1800fb8b0`

## string_xrefs

- `0x180075b2a`: `IsConfigUrl`
- `0x180075b0d`: `ConfigURLOrToken`
- `0x180075be4`: `IsCacheDeferredEnabled`
- `0x1800760e2`: `CachedFileName`
- `0x180076158`: `CachedFileTelemetryUrl`
- `0x18007611d`: `CachedFileBaseHost`
- `0x180075dfa`: `ServiceStatusFlags`
- `0x180075ef0`: `ConfigEnvironment`
- `0x180075e3e`: `ServiceStatusFlagsTag`

## pseudocode

```c
void __fastcall Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::~ConfigServiceTelemetryActivity(
        Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity *this)
{
  _QWORD *v2; // r14
  Mso::OfficeWebServiceApi::FederationProviderConfiguration *v3; // rsi
  char *v4; // r15
  __int64 v5; // r13
  int v6; // r12d
  struct Mso::Telemetry::IDataFieldCollection *v7; // rax
  struct Mso::Telemetry::IDataFieldCollection *v8; // rbx
  __int64 v9; // rax
  struct Mso::Telemetry::IDataFieldCollection *v10; // rbx
  __int64 ChainedString; // rax
  struct Mso::Telemetry::IDataFieldCollection *v12; // rax
  struct Mso::Telemetry::IDataFieldCollection *v13; // rax
  __int64 v14; // r8
  struct Mso::Telemetry::IDataFieldCollection *v15; // rax
  struct Mso::Telemetry::IDataFieldCollection *v16; // rax
  struct Mso::Telemetry::IDataFieldCollection *v17; // rbx
  __int64 v18; // rax
  struct Mso::Telemetry::IDataFieldCollection *v19; // rax
  struct Mso::Telemetry::IDataFieldCollection *v20; // rax
  __int64 v21; // r8
  struct Mso::Telemetry::IDataFieldCollection *v22; // rax
  __int64 v23; // rax
  struct Mso::Telemetry::IDataFieldCollection *v24; // rax
  __int64 v25; // rax
  struct Mso::Telemetry::IDataFieldCollection *v26; // rax
  unsigned int v27; // eax
  int v28; // r9d
  struct Mso::Telemetry::IDataFieldCollection *v29; // rbx
  __int64 v30; // r8
  __int64 v31; // rax
  struct Mso::Telemetry::IDataFieldCollection *v32; // rbx
  __int64 v33; // r8
  __int64 v34; // rax
  struct Mso::Telemetry::IDataFieldCollection *v35; // rax
  struct Mso::Telemetry::IDataFieldCollection *v36; // rax
  struct Mso::Telemetry::IDataFieldCollection *v37; // rax
  struct Mso::Telemetry::IDataFieldCollection *v38; // rbx
  __int64 v39; // rax
  bool v40; // al
  struct Mso::Telemetry::IDataFieldCollection *v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rax
  struct Mso::Telemetry::IDataFieldCollection *v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rax
  struct Mso::Telemetry::IDataFieldCollection *v47; // rbx
  __int64 v48; // rax
  unsigned int v49; // eax
  int v50; // r9d
  __int64 v51; // rax
  __int64 v52; // rax
  struct Mso::Telemetry::IDataFieldCollection *v53; // rax
  struct Mso::Telemetry::IDataFieldCollection *v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rax
  struct Mso::Telemetry::IDataFieldCollection *v57; // rbx
  __int64 v58; // rax
  __int64 v59; // rax
  struct Mso::Telemetry::IDataFieldCollection *v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rax
  struct Mso::Telemetry::IDataFieldCollection *v63; // rax
  __int16 v64; // [rsp+39h] [rbp-CFh] BYREF
  _BYTE v65[16]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v66[2]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v67[2]; // [rsp+52h] [rbp-B6h] BYREF
  _BYTE v68[4]; // [rsp+54h] [rbp-B4h] BYREF
  const char *v69; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v70[8]; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v71; // [rsp+70h] [rbp-98h] BYREF
  __int128 v72; // [rsp+80h] [rbp-88h]
  char v73; // [rsp+90h] [rbp-78h]
  __int128 v74; // [rsp+98h] [rbp-70h] BYREF
  __int128 v75; // [rsp+A8h] [rbp-60h]
  char v76; // [rsp+B8h] [rbp-50h]
  __int128 v77; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v78; // [rsp+D0h] [rbp-38h]
  char v79; // [rsp+E0h] [rbp-28h]
  const char *v80; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v81[40]; // [rsp+F0h] [rbp-18h] BYREF
  _OWORD v82[2]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v83[32]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v84[8]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v85[424]; // [rsp+160h] [rbp+58h] BYREF

  *(_QWORD *)this = &Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::`vftable';
  v2 = (_QWORD *)((char *)this + 408);
  if ( *((_QWORD *)this + 51) )
  {
    std::chrono::steady_clock::now(&v80);
    v5 = (__int64)&v80[-*((_QWORD *)this + 8)] / 1000000;
    v6 = *((_DWORD *)this + 19);
    Mso::Telemetry::Activity::Activity(v65, *v2);
    v7 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v7, "Api", *((unsigned int *)this + 12), 4);
    v8 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    LODWORD(v80) = 0;
    WORD2(v80) = 0;
    TaggingUtilities::ConvertTagToStringInternal<char>(*((unsigned int *)this + 2), &v80);
    v9 = std::string::string(v81, &v80);
    Mso::Telemetry::IDataFieldCollection::Add<std::string>(v8, "Tag", v9);
    v10 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    v4 = (char *)this + 16;
    ChainedString = Mso::OfficeWebServiceApi::ChainedTags<8>::GetChainedString((char *)this + 16, v81);
    Mso::Telemetry::IDataFieldCollection::Add<std::string>(v10, "ChainedTags", ChainedString);
    v12 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v12, "ConfigURLOrToken", *((unsigned int *)this + 13), 4);
    v13 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    LOBYTE(v14) = *((_BYTE *)this + 56);
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v13, "IsConfigUrl", v14);
    v15 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v15, "Options", *((unsigned int *)this + 18), 4);
    v16 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v16, "StatusFlags", *((unsigned int *)this + 19), 4);
    v17 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    LODWORD(v80) = 0;
    WORD2(v80) = 0;
    TaggingUtilities::ConvertTagToStringInternal<char>(*((unsigned int *)this + 20), &v80);
    v18 = std::string::string(v81, &v80);
    Mso::Telemetry::IDataFieldCollection::Add<std::string>(v17, "StatusFlagsTag", v18);
    v19 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Telemetry::IDataFieldCollection::Add<__int64>(v19, "ElapsedInMs", v5);
    v20 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    LOBYTE(v21) = *((_BYTE *)this + 84);
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v20, "IsCacheDeferredEnabled", v21);
    v22 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Telemetry::IDataFieldCollection::Add<unsigned __int64>(v22, "RequestFlags", *((_QWORD *)this + 11), 4);
    v3 = (Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity *)((char *)this + 112);
    v23 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>((char *)this + 144, v83);
    v71 = 0;
    v72 = 0;
    v71 = *(_OWORD *)v23;
    v72 = *(_OWORD *)(v23 + 16);
    *(_QWORD *)(v23 + 24) = 7;
    *(_WORD *)v23 = 0;
    *(_QWORD *)(v23 + 16) = 0;
    v73 = 1;
    v80 = "TelemetryRegionCode";
    v24 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Authentication::FederationProvider::AddTelemetryRegionCodeTo(v24, &v80, &v71);
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(&v71);
    std::wstring::~wstring(v83);
    v25 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>((char *)this + 256, v81);
    v74 = 0;
    v75 = 0;
    v74 = *(_OWORD *)v25;
    v75 = *(_OWORD *)(v25 + 16);
    *(_WORD *)v25 = 0;
    *(_QWORD *)(v25 + 16) = 0;
    *(_QWORD *)(v25 + 24) = 7;
    v76 = 1;
    v80 = "OriginalTelemetryRegionCode";
    v26 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Authentication::FederationProvider::AddTelemetryRegionCodeTo(v26, &v80, &v74);
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(&v74);
    std::wstring::~wstring(v81);
    v80 = "FederationProviderCode";
    v27 = (unsigned int)Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Authentication::FederationProvider::AddConfigurationProviderCodeTo(
      v27,
      (unsigned int)&v80,
      (_DWORD)this + 112,
      v28);
    v29 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    LOBYTE(v30) = 1;
    v31 = OGuid::ToString(v81, (char *)this + 216, v30);
    Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(v29, "FederationTenantId", v31, 4);
    v32 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    LOBYTE(v33) = 1;
    v34 = OGuid::ToString(v81, (char *)this + 232, v33);
    Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(v32, "FederationProviderId", v34, 256);
    v35 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v35, "FederationSource", *((unsigned int *)this + 63));
    v36 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    v82[0] = *((_OWORD *)this + 6);
    Mso::Telemetry::IDataFieldCollection::Add<_GUID>(v36, "CorrelationId", v82);
    v37 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v37, "ServiceStatusFlags", *((unsigned int *)this + 74), 4);
    v38 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v65);
    LODWORD(v80) = 0;
    WORD2(v80) = 0;
    TaggingUtilities::ConvertTagToStringInternal<char>(*((unsigned int *)this + 75), &v80);
    v39 = std::string::string(v81, &v80);
    Mso::Telemetry::IDataFieldCollection::Add<std::string>(v38, "ServiceStatusFlagsTag", v39);
    LODWORD(v80) = 0;
    WORD2(v80) = 0;
    TaggingUtilities::ConvertTagToStringInternal<char>(*((unsigned int *)this + 2), &v80);
    Mso::Telemetry::CreateResult(v84, *((unsigned int *)this + 12), &v80, 0);
    Mso::Telemetry::Activity::SetResult(
      (Mso::Telemetry::Activity *)v65,
      v6 == 0,
      (const struct Office::System::Result *)v84);
    Office::System::Result::Fields::~Fields((Office::System::Result::Fields *)v85);
    Mso::TCntPtr<Mso::Async::ICancellationListener>::Clear(v2);
    if ( Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::s_configEnvChangeTelemetry < 0 )
      v40 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::s_configEnvChangeTelemetry);
    else
      v40 = Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::s_configEnvChangeTelemetry != 0;
    if ( v40 && !v6 )
    {
      Mso::OfficeWebServiceApi::ConfigurationEnvRecord::AddConfigurationEnvRecordIfUnique((Mso::OfficeWebServiceApi::ConfigurationEnvRecord *)v84);
      if ( v85[232] )
      {
        *(_QWORD *)&v82[0] = &off_1801AECC0;
        *((_QWORD *)&v82[0] + 1) = "ConfigEnvironment";
        v64 = 366;
        LOWORD(v80) = 2;
        BYTE2(v80) = 1;
        v66[1] = 0;
        v67[1] = 0;
        v68[1] = 0;
        Mso::Telemetry::EventFlags::EventFlags(
          (unsigned int)&v69,
          (unsigned int)v68,
          (unsigned int)v67,
          (unsigned int)v66,
          (__int64)&v80,
          (__int64)&v64);
        Mso::Telemetry::Activity::Activity(v70, v82, 0, &v69);
        v41 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
        v42 = std::optional<Mso::OfficeWebServiceApi::ConfigurationEnvRecord>::operator->(v84);
        v43 = std::wstring::wstring(v82, v42);
        Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(v41, "FederationTenantId", v43, 4);
        v44 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
        v45 = std::optional<Mso::OfficeWebServiceApi::ConfigurationEnvRecord>::operator->(v84);
        v46 = std::wstring::wstring(v82, v45 + 32);
        Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(v44, "FederationProviderId", v46, 256);
        v47 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
        v48 = std::optional<Mso::OfficeWebServiceApi::ConfigurationEnvRecord>::operator->(v84);
        Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v47, "IdP", *(unsigned int *)(v48 + 64), 4);
        LODWORD(v47) = std::optional<Mso::OfficeWebServiceApi::ConfigurationEnvRecord>::operator->(v84);
        v69 = "FederationProviderCode";
        v49 = (unsigned int)Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
        Mso::Authentication::FederationProvider::AddConfigurationProviderCodeTo(
          v49,
          (unsigned int)&v69,
          (_DWORD)v47 + 72,
          v50);
        v51 = std::optional<Mso::OfficeWebServiceApi::ConfigurationEnvRecord>::operator->(v84);
        v52 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v51 + 104, v82);
        v77 = 0;
        v78 = 0;
        v77 = *(_OWORD *)v52;
        v78 = *(_OWORD *)(v52 + 16);
        *(_WORD *)v52 = 0;
        *(_QWORD *)(v52 + 16) = 0;
        *(_QWORD *)(v52 + 24) = 7;
        v79 = 1;
        v69 = "TelemetryRegionCode";
        v53 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
        Mso::Authentication::FederationProvider::AddTelemetryRegionCodeTo(v53, &v69, &v77);
        std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(&v77);
        std::wstring::~wstring(v82);
        v54 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
        v55 = std::optional<Mso::OfficeWebServiceApi::ConfigurationEnvRecord>::operator->(v84);
        v56 = std::wstring::wstring(v81, v55 + 144);
        Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(v54, "CachedFileName", v56, 4);
        v57 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
        v58 = std::optional<Mso::OfficeWebServiceApi::ConfigurationEnvRecord>::operator->(v84);
        v59 = std::wstring::wstring(v81, v58 + 176);
        Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(v57, "CachedFileBaseHost", v59, 4);
        v60 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
        v61 = std::optional<Mso::OfficeWebServiceApi::ConfigurationEnvRecord>::operator->(v84);
        v62 = std::wstring::wstring(v81, v61 + 208);
        Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(v60, "CachedFileTelemetryUrl", v62, 4);
        v63 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v70);
        Mso::Telemetry::IDataFieldCollection::Add<__int64>(v63, "ElapsedInMs", v5);
        Mso::Telemetry::Activity::SetSuccess((Mso::Telemetry::Activity *)v70, v6 == 0);
        Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v70);
      }
      std::_Optional_destruct_base<Mso::OfficeWebServiceApi::ConfigurationEnvRecord,0>::~_Optional_destruct_base<Mso::OfficeWebServiceApi::ConfigurationEnvRecord,0>(v84);
    }
    Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v65);
  }
  else
  {
    v3 = (Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity *)((char *)this + 112);
    v4 = (char *)this + 16;
  }
  Mso::TCntPtr<Mso::Async::ICancellationListener>::Clear(v2);
  std::_Optional_destruct_base<Mso::OfficeWebServiceApi::ConfigCachedFileInfo,0>::~_Optional_destruct_base<Mso::OfficeWebServiceApi::ConfigCachedFileInfo,0>((char *)this + 304);
  Mso::OfficeWebServiceApi::FederationProviderConfiguration::~FederationProviderConfiguration(v3);
  std::vector<MsoReserveTag>::~vector<MsoReserveTag>(v4);
}

```

## disassembly

```asm
0x1800759c0  mov     rax, rsp
0x1800759c3  mov     [rax+10h], rbx
0x1800759c7  mov     [rax+18h], rsi
0x1800759cb  mov     [rax+20h], rdi
0x1800759cf  push    rbp
0x1800759d0  push    r12
0x1800759d2  push    r13
0x1800759d4  push    r14
0x1800759d6  push    r15
0x1800759d8  lea     rbp, [rax-238h]
0x1800759df  sub     rsp, 310h
0x1800759e6  mov     rax, cs:__security_cookie
0x1800759ed  xor     rax, rsp
0x1800759f0  mov     [rbp+230h+var_30], rax
0x1800759f7  mov     rdi, rcx
0x1800759fa  lea     rax, ??_7ConfigServiceTelemetryActivity@OfficeWebServiceApi@Mso@@6B@; const Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::`vftable'
0x180075a01  mov     [rcx], rax
0x180075a04  lea     r14, [rcx+198h]
0x180075a0b  xor     ebx, ebx
0x180075a0d  cmp     [r14], rbx
0x180075a10  jnz     short loc_180075A1F
0x180075a12  lea     rsi, [rcx+70h]
0x180075a16  lea     r15, [rcx+10h]
0x180075a1a  jmp     loc_1800761AE
0x180075a1f  lea     rcx, [rbp+230h+var_250]
0x180075a23  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180075a28  mov     rcx, [rbp+230h+var_250]
0x180075a2c  sub     rcx, [rdi+40h]
0x180075a30  mov     rax, 431BDE82D7B634DBh
0x180075a3a  imul    rcx
0x180075a3d  mov     r13, rdx
0x180075a40  sar     r13, 12h
0x180075a44  mov     rax, r13
0x180075a47  shr     rax, 3Fh
0x180075a4b  add     r13, rax
0x180075a4e  mov     r12d, [rdi+4Ch]
0x180075a52  test    r12d, r12d
0x180075a55  setz    [rsp+330h+var_300]
0x180075a5a  mov     rdx, [r14]
0x180075a5d  lea     rcx, [rsp+330h+var_2F8]
0x180075a62  call    ??0Activity@Telemetry@Mso@@IEAA@AEBUIDetachedActivity@12@W4ContentType@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::IDetachedActivity const &,Mso::Telemetry::ContentType)
0x180075a67  lea     rcx, [rsp+330h+var_2F8]; this
0x180075a6c  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075a71  mov     esi, 4
0x180075a76  mov     r9d, esi
0x180075a79  mov     r8d, [rdi+30h]
0x180075a7d  lea     rdx, aApi; "Api"
0x180075a84  mov     rcx, rax
0x180075a87  call    ??$Add@I@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDIW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<uint>(char const *,uint,Mso::Logging::DataClassifications)
0x180075a8c  lea     rcx, [rsp+330h+var_2F8]; this
0x180075a91  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075a96  mov     rbx, rax
0x180075a99  xor     eax, eax
0x180075a9b  mov     dword ptr [rbp+230h+var_250], eax
0x180075a9e  mov     word ptr [rbp+230h+var_250+4], ax
0x180075aa2  lea     rdx, [rbp+230h+var_250]
0x180075aa6  mov     ecx, [rdi+8]
0x180075aa9  call    ??$ConvertTagToStringInternal@D@TaggingUtilities@@YA_NIPEAD_K@Z; TaggingUtilities::ConvertTagToStringInternal<char>(uint,char *,unsigned __int64)
0x180075aae  lea     rdx, [rbp+230h+var_250]
0x180075ab2  lea     rcx, [rbp+230h+var_248]
0x180075ab6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180075abb  mov     r8, rax
0x180075abe  lea     rdx, aTag; "Tag"
0x180075ac5  mov     rcx, rbx
0x180075ac8  call    ??$Add@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<std::string>(char const *,std::string,Mso::Logging::DataClassifications)
0x180075acd  lea     rcx, [rsp+330h+var_2F8]; this
0x180075ad2  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075ad7  mov     rbx, rax
0x180075ada  lea     r15, [rdi+10h]
0x180075ade  lea     rdx, [rbp+230h+var_248]
0x180075ae2  mov     rcx, r15
0x180075ae5  call    ?GetChainedString@?$ChainedTags@$07@OfficeWebServiceApi@Mso@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Mso::OfficeWebServiceApi::ChainedTags<8>::GetChainedString(void)
0x180075aea  mov     r8, rax
0x180075aed  lea     rdx, aChainedtags; "ChainedTags"
0x180075af4  mov     rcx, rbx
0x180075af7  call    ??$Add@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<std::string>(char const *,std::string,Mso::Logging::DataClassifications)
0x180075afc  lea     rcx, [rsp+330h+var_2F8]; this
0x180075b01  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075b06  mov     r9d, esi
0x180075b09  mov     r8d, [rdi+34h]
0x180075b0d  lea     rdx, aConfigurlortok; "ConfigURLOrToken"
0x180075b14  mov     rcx, rax
0x180075b17  call    ??$Add@I@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDIW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<uint>(char const *,uint,Mso::Logging::DataClassifications)
0x180075b1c  lea     rcx, [rsp+330h+var_2F8]; this
0x180075b21  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075b26  mov     r8b, [rdi+38h]
0x180075b2a  lea     rdx, aIsconfigurl; "IsConfigUrl"
0x180075b31  mov     rcx, rax
0x180075b34  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x180075b39  lea     rcx, [rsp+330h+var_2F8]; this
0x180075b3e  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075b43  mov     r9d, esi
0x180075b46  mov     r8d, [rdi+48h]
0x180075b4a  lea     rdx, aOptions; "Options"
0x180075b51  mov     rcx, rax
0x180075b54  call    ??$Add@I@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDIW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<uint>(char const *,uint,Mso::Logging::DataClassifications)
0x180075b59  lea     rcx, [rsp+330h+var_2F8]; this
0x180075b5e  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075b63  mov     r9d, esi
0x180075b66  mov     r8d, [rdi+4Ch]
0x180075b6a  lea     rdx, aStatusflags; "StatusFlags"
0x180075b71  mov     rcx, rax
0x180075b74  call    ??$Add@I@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDIW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<uint>(char const *,uint,Mso::Logging::DataClassifications)
0x180075b79  lea     rcx, [rsp+330h+var_2F8]; this
0x180075b7e  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075b83  mov     rbx, rax
0x180075b86  xor     eax, eax
0x180075b88  mov     dword ptr [rbp+230h+var_250], eax
0x180075b8b  mov     word ptr [rbp+230h+var_250+4], ax
0x180075b8f  lea     rdx, [rbp+230h+var_250]
0x180075b93  mov     ecx, [rdi+50h]
0x180075b96  call    ??$ConvertTagToStringInternal@D@TaggingUtilities@@YA_NIPEAD_K@Z; TaggingUtilities::ConvertTagToStringInternal<char>(uint,char *,unsigned __int64)
0x180075b9b  lea     rdx, [rbp+230h+var_250]
0x180075b9f  lea     rcx, [rbp+230h+var_248]
0x180075ba3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180075ba8  mov     r8, rax
0x180075bab  lea     rdx, aStatusflagstag; "StatusFlagsTag"
0x180075bb2  mov     rcx, rbx
0x180075bb5  call    ??$Add@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<std::string>(char const *,std::string,Mso::Logging::DataClassifications)
0x180075bba  lea     rcx, [rsp+330h+var_2F8]; this
0x180075bbf  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075bc4  mov     r8, r13
0x180075bc7  lea     rdx, aElapsedinms; "ElapsedInMs"
0x180075bce  mov     rcx, rax
0x180075bd1  call    ??$Add@_J@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_JW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<__int64>(char const *,__int64,Mso::Logging::DataClassifications)
0x180075bd6  lea     rcx, [rsp+330h+var_2F8]; this
0x180075bdb  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075be0  mov     r8b, [rdi+54h]
0x180075be4  lea     rdx, aIscachedeferre; "IsCacheDeferredEnabled"
0x180075beb  mov     rcx, rax
0x180075bee  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x180075bf3  lea     rcx, [rsp+330h+var_2F8]; this
0x180075bf8  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075bfd  mov     r9d, esi
0x180075c00  mov     r8, [rdi+58h]
0x180075c04  lea     rdx, aRequestflags; "RequestFlags"
0x180075c0b  mov     rcx, rax
0x180075c0e  call    ??$Add@_K@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_KW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<unsigned __int64>(char const *,unsigned __int64,Mso::Logging::DataClassifications)
0x180075c13  lea     rsi, [rdi+70h]
0x180075c17  lea     rcx, [rsi+20h]
0x180075c1b  lea     rdx, [rbp+230h+var_200]
0x180075c1f  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEGBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x180075c24  xorps   xmm0, xmm0
0x180075c27  movups  [rsp+330h+var_2D0+8], xmm0
0x180075c2c  xorps   xmm1, xmm1
0x180075c2f  movdqu  xmmword ptr [rsp+330h+var_2C0+8], xmm1
0x180075c35  movups  xmm0, xmmword ptr [rax]
0x180075c38  movups  [rsp+330h+var_2D0+8], xmm0
0x180075c3d  movups  xmm1, xmmword ptr [rax+10h]
0x180075c41  movups  xmmword ptr [rsp+330h+var_2C0+8], xmm1
0x180075c46  mov     qword ptr [rax+18h], 7
0x180075c4e  xor     ebx, ebx
0x180075c50  mov     [rax], bx
0x180075c53  mov     [rax+10h], rbx
0x180075c57  mov     [rbp+230h+var_2A8], 1
0x180075c5b  lea     rax, aTelemetryregio; "TelemetryRegionCode"
0x180075c62  mov     [rbp+230h+var_250], rax
0x180075c66  lea     rcx, [rsp+330h+var_2F8]; this
0x180075c6b  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075c70  mov     rcx, rax
0x180075c73  lea     r8, [rsp+330h+var_2D0+8]
0x180075c78  lea     rdx, [rbp+230h+var_250]
0x180075c7c  call    ?AddTelemetryRegionCodeTo@FederationProvider@Authentication@Mso@@YAXAEAUIDataFieldCollection@Telemetry@3@AEBV?$StringLiteral@D@StringLiterals@3@AEBV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z; Mso::Authentication::FederationProvider::AddTelemetryRegionCodeTo(Mso::Telemetry::IDataFieldCollection &,Mso::StringLiterals::StringLiteral<char> const &,std::optional<std::wstring> const &)
0x180075c81  lea     rcx, [rsp+330h+var_2D0+8]
0x180075c86  call    ??1?$_Optional_destruct_base@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180075c8b  lea     rcx, [rbp+230h+var_200]; void *
0x180075c8f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180075c94  lea     rcx, [rdi+100h]
0x180075c9b  lea     rdx, [rbp+230h+var_248]
0x180075c9f  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEGBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x180075ca4  xorps   xmm0, xmm0
0x180075ca7  movups  [rbp+230h+var_2A0], xmm0
0x180075cab  xorps   xmm1, xmm1
0x180075cae  movdqu  [rbp+230h+var_290], xmm1
0x180075cb3  movups  xmm0, xmmword ptr [rax]
0x180075cb6  movups  [rbp+230h+var_2A0], xmm0
0x180075cba  movups  xmm1, xmmword ptr [rax+10h]
0x180075cbe  movups  [rbp+230h+var_290], xmm1
0x180075cc2  mov     [rax], bx
0x180075cc5  mov     [rax+10h], rbx
0x180075cc9  mov     qword ptr [rax+18h], 7
0x180075cd1  mov     [rbp+230h+var_280], 1
0x180075cd5  lea     rax, aOriginalteleme_0; "OriginalTelemetryRegionCode"
0x180075cdc  mov     [rbp+230h+var_250], rax
0x180075ce0  lea     rcx, [rsp+330h+var_2F8]; this
0x180075ce5  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075cea  mov     rcx, rax
0x180075ced  lea     r8, [rbp+230h+var_2A0]
0x180075cf1  lea     rdx, [rbp+230h+var_250]
0x180075cf5  call    ?AddTelemetryRegionCodeTo@FederationProvider@Authentication@Mso@@YAXAEAUIDataFieldCollection@Telemetry@3@AEBV?$StringLiteral@D@StringLiterals@3@AEBV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z; Mso::Authentication::FederationProvider::AddTelemetryRegionCodeTo(Mso::Telemetry::IDataFieldCollection &,Mso::StringLiterals::StringLiteral<char> const &,std::optional<std::wstring> const &)
0x180075cfa  lea     rcx, [rbp+230h+var_2A0]
0x180075cfe  call    ??1?$_Optional_destruct_base@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180075d03  lea     rcx, [rbp+230h+var_248]; void *
0x180075d07  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180075d0c  lea     rax, aFederationprov_0; "FederationProviderCode"
0x180075d13  mov     [rbp+230h+var_250], rax
0x180075d17  lea     rcx, [rsp+330h+var_2F8]; this
0x180075d1c  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075d21  mov     rcx, rax
0x180075d24  mov     r8, rsi
0x180075d27  lea     rdx, [rbp+230h+var_250]
0x180075d2b  call    ?AddConfigurationProviderCodeTo@FederationProvider@Authentication@Mso@@YAXAEAUIDataFieldCollection@Telemetry@3@AEBV?$StringLiteral@D@StringLiterals@3@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Authentication::FederationProvider::AddConfigurationProviderCodeTo(Mso::Telemetry::IDataFieldCollection &,Mso::StringLiterals::StringLiteral<char> const &,std::wstring const &)
0x180075d30  lea     rcx, [rsp+330h+var_2F8]; this
0x180075d35  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075d3a  mov     rbx, rax
0x180075d3d  lea     rdx, [rsi+68h]
0x180075d41  mov     r8b, 1
0x180075d44  lea     rcx, [rbp+230h+var_248]
0x180075d48  call    ?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; OGuid::ToString(_GUID const &,bool)
0x180075d4d  mov     r9d, 4
0x180075d53  mov     r8, rax
0x180075d56  lea     rdx, aFederationtena; "FederationTenantId"
0x180075d5d  mov     rcx, rbx
0x180075d60  call    ??$Add@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(char const *,std::wstring,Mso::Logging::DataClassifications)
0x180075d65  lea     rcx, [rsp+330h+var_2F8]; this
0x180075d6a  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075d6f  mov     rbx, rax
0x180075d72  lea     rdx, [rdi+0E8h]
0x180075d79  mov     r8b, 1
0x180075d7c  lea     rcx, [rbp+230h+var_248]
0x180075d80  call    ?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; OGuid::ToString(_GUID const &,bool)
0x180075d85  mov     r9d, 100h
0x180075d8b  mov     r8, rax
0x180075d8e  lea     rdx, aFederationprov_2; "FederationProviderId"
0x180075d95  mov     rcx, rbx
0x180075d98  call    ??$Add@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<std::wstring>(char const *,std::wstring,Mso::Logging::DataClassifications)
0x180075d9d  lea     rcx, [rsp+330h+var_2F8]; this
0x180075da2  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075da7  mov     r8d, [rdi+0FCh]
0x180075dae  lea     rdx, aFederationsour; "FederationSource"
0x180075db5  mov     rcx, rax
0x180075db8  call    ??$Add@H@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDHW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<int>(char const *,int,Mso::Logging::DataClassifications)
0x180075dbd  lea     rcx, [rsp+330h+var_2F8]; this
0x180075dc2  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075dc7  movups  xmm0, xmmword ptr [rdi+60h]
0x180075dcb  movdqu  [rbp+230h+var_220], xmm0
0x180075dd0  lea     r8, [rbp+230h+var_220]
0x180075dd4  lea     rdx, aCorrelationid; "CorrelationId"
0x180075ddb  mov     rcx, rax
0x180075dde  call    ??$Add@U_GUID@@@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDU_GUID@@W4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<_GUID>(char const *,_GUID,Mso::Logging::DataClassifications)
0x180075de3  lea     rcx, [rsp+330h+var_2F8]; this
0x180075de8  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075ded  mov     r9d, 4
0x180075df3  mov     r8d, [rdi+128h]
0x180075dfa  lea     rdx, aServicestatusf_0; "ServiceStatusFlags"
0x180075e01  mov     rcx, rax
0x180075e04  call    ??$Add@I@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDIW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<uint>(char const *,uint,Mso::Logging::DataClassifications)
0x180075e09  lea     rcx, [rsp+330h+var_2F8]; this
0x180075e0e  call    ?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180075e13  mov     rbx, rax
0x180075e16  xor     eax, eax
0x180075e18  mov     dword ptr [rbp+230h+var_250], eax
0x180075e1b  mov     word ptr [rbp+230h+var_250+4], ax
0x180075e1f  lea     rdx, [rbp+230h+var_250]
0x180075e23  mov     ecx, [rdi+12Ch]
0x180075e29  call    ??$ConvertTagToStringInternal@D@TaggingUtilities@@YA_NIPEAD_K@Z; TaggingUtilities::ConvertTagToStringInternal<char>(uint,char *,unsigned __int64)
0x180075e2e  lea     rdx, [rbp+230h+var_250]
0x180075e32  lea     rcx, [rbp+230h+var_248]
0x180075e36  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180075e3b  mov     r8, rax
0x180075e3e  lea     rdx, aServicestatusf; "ServiceStatusFlagsTag"
0x180075e45  mov     rcx, rbx
0x180075e48  call    ??$Add@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<std::string>(char const *,std::string,Mso::Logging::DataClassifications)
0x180075e4d  xor     eax, eax
0x180075e4f  mov     dword ptr [rbp+230h+var_250], eax
0x180075e52  mov     word ptr [rbp+230h+var_250+4], ax
0x180075e56  lea     rdx, [rbp+230h+var_250]
0x180075e5a  mov     ecx, [rdi+8]
0x180075e5d  call    ??$ConvertTagToStringInternal@D@TaggingUtilities@@YA_NIPEAD_K@Z; TaggingUtilities::ConvertTagToStringInternal<char>(uint,char *,unsigned __int64)
0x180075e62  xor     r9d, r9d
0x180075e65  lea     r8, [rbp+230h+var_250]
0x180075e69  mov     edx, [rdi+30h]
0x180075e6c  lea     rcx, [rbp+230h+var_1E0]
0x180075e70  call    ?CreateResult@Telemetry@Mso@@YA?AVResult@System@Office@@HPEBDI@Z; Mso::Telemetry::CreateResult(int,char const *,uint)
0x180075e75  lea     r8, [rbp+230h+var_1E0]; struct Office::System::Result *
0x180075e79  mov     dl, [rsp+330h+var_300]; bool
0x180075e7d  lea     rcx, [rsp+330h+var_2F8]; this
0x180075e82  call    ?SetResult@Activity@Telemetry@Mso@@QEAAX_NAEBVResult@System@Office@@@Z; Mso::Telemetry::Activity::SetResult(bool,Office::System::Result const &)
0x180075e87  lea     rcx, [rbp+230h+var_1D8]; this
0x180075e8b  call    ??1Fields@Result@System@Office@@QEAA@XZ; Office::System::Result::Fields::~Fields(void)
0x180075e90  mov     rcx, r14
0x180075e93  call    ?Clear@?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEAAXXZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::Clear(void)
0x180075e98  mov     al, cs:?s_configEnvChangeTelemetry@ConfigServiceTelemetryActivity@OfficeWebServiceApi@Mso@@0VFeatureGate@Optimized@AB@3@B; Mso::AB::Optimized::FeatureGate const Mso::OfficeWebServiceApi::ConfigServiceTelemetryActivity::s_configEnvChangeTelemetry
0x180075e9e  xor     ebx, ebx
0x180075ea0  test    al, al
0x180075ea2  js      short loc_180075EA9
0x180075ea4  setnz   al
0x180075ea7  jmp     short loc_180075EB5
0x180075ea9  lea     rcx, ?s_configEnvChangeTelemetry@ConfigServiceTelemetryActivity@OfficeWebServiceApi@Mso@@0VFeatureGate@Optimized@AB@3@B; this
0x180075eb0  call    ?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x180075eb5  test    al, al
0x180075eb7  jz      loc_1800761A4
0x180075ebd  test    r12d, r12d
0x180075ec0  jnz     loc_1800761A4
0x180075ec6  lea     r8, [rdi+130h]
0x180075ecd  mov     rdx, rsi
0x180075ed0  lea     rcx, [rbp+230h+var_1E0]; this
0x180075ed4  call    ?AddConfigurationEnvRecordIfUnique@ConfigurationEnvRecord@OfficeWebServiceApi@Mso@@SA?AV?$optional@VConfigurationEnvRecord@OfficeWebServiceApi@Mso@@@std@@AEBVFederationProviderConfiguration@23@AEBV?$optional@UConfigCachedFileInfo@OfficeWebServiceApi@Mso@@@5@@Z; Mso::OfficeWebServiceApi::ConfigurationEnvRecord::AddConfigurationEnvRecordIfUnique(Mso::OfficeWebServiceApi::FederationProviderConfiguration const &,std::optional<Mso::OfficeWebServiceApi::ConfigCachedFileInfo> const &)
0x180075ed9  cmp     [rbp+230h+var_F0], bl
0x180075edf  jz      loc_18007619B
  ... truncated ...
```
