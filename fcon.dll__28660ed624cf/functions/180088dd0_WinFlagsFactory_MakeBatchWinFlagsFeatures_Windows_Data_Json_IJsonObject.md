# WinFlagsFactory::MakeBatchWinFlagsFeatures(Windows::Data::Json::IJsonObject *)

- ea: `0x180088dd0`
- end: `0x180089a15`
- name: `?MakeBatchWinFlagsFeatures@WinFlagsFactory@@SA?AVBatchWinFlagsFeatures@@PEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `3141`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180088420`

## callees

- `0x180003220`
- `0x18000796c`
- `0x180010450`
- `0x1800107b0`
- `0x1800109ac`
- `0x1800442c0`
- `0x18005e248`
- `0x18005e2a0`
- `0x18005e758`
- `0x18005e7e0`
- `0x18005e84c`
- `0x18005e8b0`
- `0x180060ce4`
- `0x180060d08`
- `0x18008714c`
- `0x180087478`
- `0x180087520`
- `0x180087a60`
- `0x180087d58`
- `0x18008899c`
- `0x180088dd0`
- `0x180089d54`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088f86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008910e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800891e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008941b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800894b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008951a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800896c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800896d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800896eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008970e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008976a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180088f86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008910e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800891e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008941b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800894b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008951a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800896c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800896d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800896eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008970e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008976a`

## pseudocode

```c
// Hidden C++ exception states: #wind=46
HSTRING __fastcall WinFlagsFactory::MakeBatchWinFlagsFeatures(
        HSTRING a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, HSTRING *))
{
  int v4; // r14d
  __int64 (__fastcall **v5)(_QWORD, GUID *, HSTRING *); // rax
  int v6; // eax
  __int64 v7; // r12
  __int64 v8; // rcx
  __int64 (__fastcall *v9)(__int64, __int64 **); // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  __int64 v15; // rax
  int v16; // eax
  char v17; // cl
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v20; // rax
  unsigned int v21; // eax
  char v22; // cl
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rbx
  __int64 v25; // rax
  unsigned int v26; // eax
  char v27; // cl
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64 *); // rbx
  __int64 v30; // rax
  unsigned int v31; // eax
  char v32; // cl
  int i; // eax
  __int64 **v34; // rsi
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, HSTRING *); // rbx
  int v37; // eax
  __int64 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, _QWORD, __int64 *); // rbx
  __int64 v43; // rax
  unsigned int v44; // eax
  char v45; // cl
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, _QWORD, __int64 *); // rbx
  __int64 v48; // rax
  unsigned int v49; // eax
  char v50; // cl
  __int64 v51; // rdi
  __int64 (__fastcall *v52)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v53; // rax
  int v54; // eax
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, _QWORD, double *); // rbx
  __int64 v57; // rax
  unsigned int v58; // eax
  char v59; // cl
  __int64 v60; // rdx
  __int64 v61; // rcx
  int v62; // eax
  __int64 *v63; // rsi
  __int64 (__fastcall *v64)(__int64 *, _QWORD, HSTRING, __int64 *); // rdi
  HSTRING v65; // rbx
  __int64 v66; // rax
  int v67; // eax
  __int64 *v68; // rsi
  __int64 (__fastcall *v69)(__int64 *, _QWORD, HSTRING, __int64 *); // rdi
  HSTRING v70; // rbx
  __int64 v71; // rax
  int v72; // eax
  __int64 **v73; // rsi
  __int64 *v74; // rdi
  __int64 (__fastcall *v75)(__int64 *, HSTRING *); // rbx
  int v76; // eax
  __int64 *v77; // rcx
  __int64 v78; // rax
  int v79; // eax
  int v80; // eax
  __int64 v81; // rdi
  __int64 (__fastcall *v82)(__int64, HSTRING *); // rbx
  int v83; // eax
  int v84; // eax
  HSTRING v85; // rbx
  __int64 *v86; // rsi
  __int64 (__fastcall *v87)(__int64 *, _QWORD, HSTRING, __int64 *); // rdi
  __int64 v88; // rax
  int v89; // eax
  __int64 v90; // rax
  int v91; // eax
  __int64 v92; // rax
  char v93; // al
  int v95; // [rsp+28h] [rbp-E0h]
  __int64 v96; // [rsp+38h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v98; // [rsp+48h] [rbp-C0h]
  __int64 v99; // [rsp+50h] [rbp-B8h] BYREF
  HSTRING v100; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v101; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v102; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v103; // [rsp+70h] [rbp-98h] BYREF
  __int64 v104; // [rsp+78h] [rbp-90h] BYREF
  HSTRING v105; // [rsp+80h] [rbp-88h] BYREF
  __int64 v106; // [rsp+88h] [rbp-80h] BYREF
  HSTRING v107; // [rsp+90h] [rbp-78h] BYREF
  __int64 v108; // [rsp+98h] [rbp-70h] BYREF
  __int64 v109; // [rsp+A0h] [rbp-68h] BYREF
  int v110; // [rsp+A8h] [rbp-60h] BYREF
  HSTRING v111; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v112; // [rsp+B8h] [rbp-50h] BYREF
  HSTRING v113; // [rsp+C0h] [rbp-48h] BYREF
  __int64 *v114; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v115; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v116[2]; // [rsp+D8h] [rbp-30h] BYREF
  HSTRING v117; // [rsp+E8h] [rbp-20h] BYREF
  double v118; // [rsp+F0h] [rbp-18h] BYREF
  HSTRING v119; // [rsp+F8h] [rbp-10h] BYREF
  HSTRING v120; // [rsp+100h] [rbp-8h] BYREF
  int v121; // [rsp+108h] [rbp+0h]
  __int64 v122; // [rsp+110h] [rbp+8h] BYREF
  char v123[8]; // [rsp+118h] [rbp+10h] BYREF
  int v124; // [rsp+120h] [rbp+18h]
  char v125[8]; // [rsp+130h] [rbp+28h] BYREF
  int v126; // [rsp+138h] [rbp+30h]
  __int64 v127; // [rsp+148h] [rbp+40h] BYREF
  char v128; // [rsp+150h] [rbp+48h]
  __int64 v129; // [rsp+158h] [rbp+50h] BYREF
  int v130; // [rsp+160h] [rbp+58h]
  __int64 v131; // [rsp+168h] [rbp+60h]
  __int64 v132; // [rsp+170h] [rbp+68h]
  __int64 v133; // [rsp+178h] [rbp+70h] BYREF
  int v134; // [rsp+180h] [rbp+78h]
  __int64 v135; // [rsp+188h] [rbp+80h]
  char v136[8]; // [rsp+198h] [rbp+90h] BYREF
  int v137; // [rsp+1A0h] [rbp+98h]
  char v138[16]; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v139[272]; // [rsp+1B8h] [rbp+B0h] BYREF
  _BYTE v140[272]; // [rsp+2C8h] [rbp+1C0h] BYREF
  _BYTE v141[272]; // [rsp+3D8h] [rbp+2D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+550h] [rbp+448h]

  v113 = a1;
  v4 = 0;
  LODWORD(v98) = 0;
  std::set<WinFlagsFeature>::set<WinFlagsFeature>(v116);
  if ( a2 )
  {
    v5 = *a2;
    v117 = 0;
    v6 = (*v5)(a2, &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099, &v117);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
        (const char *)(unsigned int)v6,
        v95);
    v113 = v117;
    wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::begin(
      &v113,
      v125);
    v129 = 0;
    v130 = -1;
    v131 = 0;
    while ( v126 != -1 )
    {
      v7 = wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator*(v125);
      v114 = 0;
      v8 = *(_QWORD *)v7;
      v9 = *(__int64 (__fastcall **)(__int64, __int64 **))(**(_QWORD **)v7 + 56LL);
      v114 = 0;
      v10 = v9(v8, &v114);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8A,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
          (const char *)(unsigned int)v10,
          v95);
      v102 = 0;
      v11 = *v114;
      v102 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v11 + 96))(v114, &v102);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8C,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
          (const char *)(unsigned int)v12,
          v95);
      string = 0;
      v109 = 0;
      v13 = v102;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v102 + 64LL);
      v109 = 0;
      v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              v136,
              &WinFlagsFactory::c_winflagsHistoryJsonTag);
      v16 = v14(v13, *(_QWORD *)(v15 + 24), &v109);
      if ( (int)(v16 + 0x80000000) < 0 || (v17 = 1, v16 == -2089484279) )
        v17 = 0;
      if ( v17 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x92,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
          (const char *)(unsigned int)v16,
          v95);
      if ( v16 >= 0 )
      {
        v18 = v109;
        v19 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v109 + 80LL);
        WindowsDeleteString(string);
        string = 0;
        v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                v136,
                &WinFlagsFeature::c_winflagsVersionProp);
        v21 = v19(v18, *(_QWORD *)(v20 + 24), &string);
        if ( (int)(v21 + 0x80000000) < 0 || (v22 = 1, v21 == -2089484279) )
          v22 = 0;
        if ( v22 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x97,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
            (const char *)v21,
            v95);
      }
      v108 = 0;
      v23 = v102;
      v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v102 + 64LL);
      v108 = 0;
      v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v136, &WinFlagsFactory::c_winflagsDataJsonTag);
      v26 = v24(v23, *(_QWORD *)(v25 + 24), &v108);
      if ( (int)(v26 + 0x80000000) < 0 || (v27 = 1, v26 == -2089484279) )
        v27 = 0;
      if ( v27 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9D,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
          (const char *)v26,
          v95);
      if ( v26 != -2089484279 )
      {
        v112 = 0;
        v28 = v108;
        v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v108 + 72LL);
        v112 = 0;
        v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                v136,
                &WinFlagsFactory::c_winflagsItemsJsonTag);
        v31 = v29(v28, *(_QWORD *)(v30 + 24), &v112);
        if ( (int)(v31 + 0x80000000) < 0 || (v32 = 1, v31 == -2089484279) )
          v32 = 0;
        if ( v32 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA5,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
            (const char *)v31,
            v95);
        if ( v31 != -2089484279 )
        {
          wil::com_ptr_t<Windows::Data::Json::IJsonArray,wil::err_exception_policy>::query<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
            &v112,
            &v113);
          v100 = v113;
          v120 = v113;
          v121 = 0;
          v122 = 0;
          wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>,wil::err_exception_policy>::end(
            &v100,
            v136);
          for ( i = v121; i != v137; i = ++v121 )
          {
            v34 = (__int64 **)wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>,wil::err_exception_policy>::vector_iterator::operator*(&v120);
            v107 = 0;
            v35 = *(_QWORD *)v7;
            v36 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v7 + 48LL);
            WindowsDeleteString(0);
            v107 = 0;
            v37 = v36(v35, &v107);
            if ( v37 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xAE,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                (const char *)(unsigned int)v37,
                v95);
            v99 = 0;
            v38 = *v34;
            v39 = **v34;
            v99 = 0;
            v40 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v39 + 96))(v38, &v99);
            if ( v40 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xB1,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                (const char *)(unsigned int)v40,
                v95);
            v106 = 0;
            v41 = v99;
            v42 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v99 + 64LL);
            v106 = 0;
            v43 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &v133,
                    &WinFlagsFactory::c_winflagsJsonTag);
            v44 = v42(v41, *(_QWORD *)(v43 + 24), &v106);
            if ( (int)(v44 + 0x80000000) < 0 || (v45 = 1, v44 == -2089484279) )
              v45 = 0;
            if ( v45 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xB5,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                (const char *)v44,
                v95);
            if ( v44 == -2089484279 )
              goto LABEL_36;
            v115 = 0;
            v46 = v99;
            v47 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v99 + 88LL);
            v48 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &v133,
                    &WinFlagsFactory::c_winflagsFeatureIdJsonTag);
            v49 = v47(v46, *(_QWORD *)(v48 + 24), &v115);
            if ( (int)(v49 + 0x80000000) < 0 || (v50 = 1, v49 == -2089484279) )
              v50 = 0;
            if ( v50 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xBD,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                (const char *)v49,
                v95);
            if ( v49 == -2089484279 )
            {
LABEL_36:
              wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v106);
              wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v99);
              WindowsDeleteString(v107);
            }
            else
            {
              v111 = 0;
              v51 = v99;
              v52 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v99 + 80LL);
              WindowsDeleteString(0);
              v111 = 0;
              v53 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v133,
                      &WinFlagsFactory::c_winflagsFeatureFlagIdJsonTag);
              v54 = v52(v51, *(_QWORD *)(v53 + 24), &v111);
              if ( v54 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xC5,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                  (const char *)(unsigned int)v54,
                  v95);
              v118 = DOUBLE_N1_0;
              v55 = v99;
              v56 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)v99 + 88LL);
              v57 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v133,
                      &WinFlagsFactory::c_winflagsChangeTimeOverrideJsonTag);
              v58 = v56(v55, *(_QWORD *)(v57 + 24), &v118);
              if ( (int)(v58 + 0x80000000) < 0 || (v59 = 1, v58 == -2089484279) )
                v59 = 0;
              if ( v59 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xCA,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                  (const char *)v58,
                  v95);
              v101 = 0;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v101);
              v62 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(
                      v61,
                      v60,
                      &v101);
              if ( v62 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xD1,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                  (const char *)(unsigned int)v62,
                  v95);
              v132 = 0;
              v105 = 0;
              LOBYTE(v96) = 0;
              v63 = v101;
              v64 = *(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING, __int64 *))(*v101 + 80);
              v65 = v107;
              v66 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v133,
                      &WinFlagsFeature::c_winflagsPayloadKeyProp);
              v67 = v64(v63, *(_QWORD *)(v66 + 24), v65, &v96);
              if ( v67 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xD5,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                  (const char *)(unsigned int)v67,
                  v95);
              v68 = v101;
              v69 = *(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING, __int64 *))(*v101 + 80);
              v70 = v111;
              v71 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v133,
                      &WinFlagsFeature::c_winflagsFeatureFlagIdProp);
              v72 = v69(v68, *(_QWORD *)(v71 + 24), v70, &v96);
              if ( v72 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xD6,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                  (const char *)(unsigned int)v72,
                  v95);
              wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::query<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>(
                &v106,
                &v119);
              v100 = v119;
              wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::begin(
                &v100,
                v123);
              v133 = 0;
              v134 = -1;
              v135 = 0;
              while ( v124 != -1 )
              {
                v73 = (__int64 **)wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator*(v123);
                v100 = 0;
                v74 = *v73;
                v75 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(**v73 + 48);
                WindowsDeleteString(0);
                v100 = 0;
                v76 = v75(v74, &v100);
                if ( v76 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xDC,
                    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                    (const char *)(unsigned int)v76,
                    v95);
                v103 = 0;
                v77 = *v73;
                v78 = **v73;
                v103 = 0;
                v79 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v78 + 56))(v77, &v103);
                if ( v79 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xDF,
                    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                    (const char *)(unsigned int)v79,
                    v95);
                v110 = 0;
                v80 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v103 + 48LL))(v103, &v110);
                if ( v80 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xE2,
                    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                    (const char *)(unsigned int)v80,
                    v95);
                if ( v110 == 3 )
                {
                  v81 = v103;
                  v82 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v103 + 64LL);
                  WindowsDeleteString(v105);
                  v105 = 0;
                  v83 = v82(v81, &v105);
                  if ( v83 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0xE8,
                      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                      (const char *)(unsigned int)v83,
                      v95);
                  v84 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, __int64 *))(*v101 + 80))(
                          v101,
                          v100,
                          v105,
                          &v96);
                  if ( v84 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0xE9,
                      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                      (const char *)(unsigned int)v84,
                      v95);
                }
                wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v103);
                WindowsDeleteString(v100);
                wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator++(v123);
              }
              wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v133);
              wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v123);
              v85 = string;
              if ( string )
              {
                v86 = v101;
                v87 = *(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING, __int64 *))(*v101 + 80);
                v88 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &v133,
                        &WinFlagsFeature::c_winflagsVersionProp);
                v89 = v87(v86, *(_QWORD *)(v88 + 24), v85, &v96);
                if ( v89 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xEE,
                    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                    (const char *)(unsigned int)v89,
                    v95);
              }
              v104 = 0;
              v90 = *v101;
              v104 = 0;
              v91 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v90 + 72))(v101, &v104);
              if ( v91 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xF1,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                  (const char *)(unsigned int)v91,
                  v95);
              WinFlagsFeature::WinFlagsFeature((WinFlagsFeature *)v141);
              if ( v118 == 1.0 )
              {
                v92 = WinFlagsFeature::WinFlagsFeature((WinFlagsFeature *)v140);
                v4 |= 2u;
              }
              else
              {
                v92 = WinFlagsFeature::WinFlagsFeature((WinFlagsFeature *)v139);
                v4 |= 4u;
              }
              LODWORD(v98) = v4;
              std::_Tree<std::_Tset_traits<WinFlagsFeature,std::less<WinFlagsFeature>,std::allocator<WinFlagsFeature>,0>>::_Emplace<WinFlagsFeature const &>(
                v116,
                &v127,
                v92);
              if ( (v4 & 4) != 0 )
              {
                v4 &= ~4u;
                LODWORD(v98) = v4;
                WinFlagsFeature::~WinFlagsFeature((WinFlagsFeature *)v139);
              }
              if ( (v4 & 2) != 0 )
              {
                v4 &= ~2u;
                LODWORD(v98) = v4;
                WinFlagsFeature::~WinFlagsFeature((WinFlagsFeature *)v140);
              }
              if ( !v128 || (v93 = 0, v127 == v116[0]) )
                v93 = 1;
              if ( v93 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xF7,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\winflags\\winflagsfactory.cpp",
                  (const char *)0x8000FFFFLL,
                  v95);
              WinFlagsFeature::~WinFlagsFeature((WinFlagsFeature *)v141);
              wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v104);
              wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v119);
              WindowsDeleteString(v105);
              v105 = 0;
              WindowsDeleteString(0);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v101);
              WindowsDeleteString(v111);
              v111 = 0;
              wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v106);
              wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v99);
              WindowsDeleteString(v107);
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v138);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
          wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v113);
        }
        wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v112);
      }
      wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v108);
      wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v109);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v102);
      wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v114);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator++(v125);
    }
    wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v129);
    wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v125);
    std::_Tree<std::_Tset_traits<WinFlagsFeature,std::less<WinFlagsFeature>,std::allocator<WinFlagsFeature>,0>>::_Tree<std::_Tset_traits<WinFlagsFeature,std::less<WinFlagsFeature>,std::allocator<WinFlagsFeature>,0>>(
      a1,
      v116);
    wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v117);
  }
  else
  {
    BatchWinFlagsFeatures::BatchWinFlagsFeatures(a1, v116);
  }
  std::_Tree_val<std::_Tree_simple_types<WinFlagsFeature>>::_Erase_head<std::allocator<std::_Tree_node<WinFlagsFeature,void *>>>(
    v116,
    v116);
  return a1;
}

```

## disassembly

```asm
0x180088dd0  mov     rax, rsp
0x180088dd3  mov     [rax+18h], rbx
0x180088dd7  push    rbp
0x180088dd8  push    rsi
0x180088dd9  push    rdi
0x180088dda  push    r12
0x180088ddc  push    r13
0x180088dde  push    r14
0x180088de0  push    r15
0x180088de2  lea     rbp, [rax-448h]
0x180088de9  sub     rsp, 510h
0x180088df0  movaps  xmmword ptr [rax-48h], xmm6
0x180088df4  movaps  xmmword ptr [rax-58h], xmm7
0x180088df8  mov     rax, cs:__security_cookie
0x180088dff  xor     rax, rsp
0x180088e02  mov     [rbp+440h+var_60], rax
0x180088e09  mov     rbx, rdx
0x180088e0c  mov     r15, rcx
0x180088e0f  mov     [rbp+440h+var_488], rcx
0x180088e13  xor     r13d, r13d
0x180088e16  mov     r14d, r13d
0x180088e19  mov     dword ptr [rsp+540h+var_500], r13d
0x180088e1e  lea     rcx, [rbp+440h+var_470]
0x180088e22  call    ??0?$set@VWinFlagsFeature@@U?$less@VWinFlagsFeature@@@std@@V?$allocator@VWinFlagsFeature@@@3@@std@@QEAA@XZ; std::set<WinFlagsFeature>::set<WinFlagsFeature>(void)
0x180088e27  nop
0x180088e28  test    rbx, rbx
0x180088e2b  jnz     short loc_180088E3E
0x180088e2d  lea     rdx, [rbp+440h+var_470]
0x180088e31  mov     rcx, r15
0x180088e34  call    ??0BatchWinFlagsFeatures@@QEAA@AEBV?$set@VWinFlagsFeature@@U?$less@VWinFlagsFeature@@@std@@V?$allocator@VWinFlagsFeature@@@3@@std@@@Z; BatchWinFlagsFeatures::BatchWinFlagsFeatures(std::set<WinFlagsFeature> const &)
0x180088e39  jmp     loc_1800897C1
0x180088e3e  mov     rax, [rbx]
0x180088e41  mov     [rbp+440h+var_460], r13
0x180088e45  lea     r8, [rbp+440h+var_460]
0x180088e49  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x180088e50  mov     rcx, rbx
0x180088e53  mov     rax, [rax]
0x180088e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e5b  mov     rcx, [rbp+448h]; this
0x180088e62  test    eax, eax
0x180088e64  js      loc_18008981A
0x180088e6a  mov     rax, [rbp+440h+var_460]
0x180088e6e  mov     [rbp+440h+var_488], rax
0x180088e72  lea     rdx, [rbp+440h+var_418]
0x180088e76  lea     rcx, [rbp+440h+var_488]
0x180088e7a  call    ?begin@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AViterable_iterator@12@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::begin(void)
0x180088e7f  nop
0x180088e80  mov     [rbp+440h+var_3F0], r13
0x180088e84  mov     [rbp+440h+var_3E8], 0FFFFFFFFh
0x180088e8b  mov     [rbp+440h+var_3E0], r13
0x180088e8f  mov     esi, 83750009h
0x180088e94  xorps   xmm6, xmm6
0x180088e97  movsd   xmm7, cs:__real@bff0000000000000
0x180088e9f  cmp     [rbp+440h+var_410], 0FFFFFFFFh
0x180088ea3  jz      loc_180089797
0x180088ea9  lea     rcx, [rbp+440h+var_418]
0x180088ead  call    ??Diterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x180088eb2  mov     r12, rax
0x180088eb5  mov     [rbp+440h+var_480], r13
0x180088eb9  mov     rcx, [rax]
0x180088ebc  mov     rdx, [rcx]
0x180088ebf  mov     rax, [rdx+38h]
0x180088ec3  mov     [rbp+440h+var_480], r13
0x180088ec7  lea     rdx, [rbp+440h+var_480]
0x180088ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ed0  mov     rcx, [rbp+448h]; this
0x180088ed7  test    eax, eax
0x180088ed9  js      loc_180089805
0x180088edf  mov     [rsp+540h+var_4E0], r13
0x180088ee4  mov     rcx, [rbp+440h+var_480]
0x180088ee8  mov     rax, [rcx]
0x180088eeb  mov     [rsp+540h+var_4E0], r13
0x180088ef0  lea     rdx, [rsp+540h+var_4E0]
0x180088ef5  mov     rax, [rax+60h]
0x180088ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088efe  mov     rcx, [rbp+448h]; this
0x180088f05  test    eax, eax
0x180088f07  js      loc_180089A00
0x180088f0d  mov     [rsp+540h+string], r13
0x180088f12  mov     [rbp+440h+var_4A8], r13
0x180088f16  mov     rdi, [rsp+540h+var_4E0]
0x180088f1b  mov     rax, [rdi]
0x180088f1e  mov     rbx, [rax+40h]
0x180088f22  mov     [rbp+440h+var_4A8], r13
0x180088f26  lea     rdx, ?c_winflagsHistoryJsonTag@WinFlagsFactory@@0QEBGEB; ushort const * const WinFlagsFactory::c_winflagsHistoryJsonTag
0x180088f2d  lea     rcx, [rbp+440h+var_3B0]
0x180088f34  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180088f39  nop
0x180088f3a  lea     r8, [rbp+440h+var_4A8]
0x180088f3e  mov     rdx, [rax+18h]
0x180088f42  mov     rcx, rdi
0x180088f45  mov     rax, rbx
0x180088f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f4d  nop
0x180088f4e  mov     edx, 80000000h
0x180088f53  lea     ecx, [rax+rdx]
0x180088f56  test    edx, ecx
0x180088f58  jnz     short loc_180088F60
0x180088f5a  cmp     eax, esi
0x180088f5c  mov     cl, 1
0x180088f5e  jnz     short loc_180088F63
0x180088f60  mov     cl, r13b
0x180088f63  mov     r10, [rbp+448h]
0x180088f6a  test    cl, cl
0x180088f6c  jnz     loc_1800899E8
0x180088f72  test    eax, eax
0x180088f74  js      short loc_180088FDE
0x180088f76  mov     rdi, [rbp+440h+var_4A8]
0x180088f7a  mov     rax, [rdi]
0x180088f7d  mov     rbx, [rax+50h]
0x180088f81  mov     rcx, [rsp+540h+string]; string
0x180088f86  call    cs:__imp_WindowsDeleteString
0x180088f8c  mov     [rsp+540h+string], r13
0x180088f91  lea     rdx, ?c_winflagsVersionProp@WinFlagsFeature@@2QEBGEB; ushort const * const WinFlagsFeature::c_winflagsVersionProp
0x180088f98  lea     rcx, [rbp+440h+var_3B0]
0x180088f9f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180088fa4  nop
0x180088fa5  lea     r8, [rsp+540h+string]
0x180088faa  mov     rdx, [rax+18h]
0x180088fae  mov     rcx, rdi
0x180088fb1  mov     rax, rbx
0x180088fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088fb9  nop
0x180088fba  mov     edx, 80000000h
0x180088fbf  lea     ecx, [rax+rdx]
0x180088fc2  test    edx, ecx
0x180088fc4  jnz     short loc_180088FCC
0x180088fc6  cmp     eax, esi
0x180088fc8  mov     cl, 1
0x180088fca  jnz     short loc_180088FCF
0x180088fcc  mov     cl, r13b
0x180088fcf  mov     r10, [rbp+448h]
0x180088fd6  test    cl, cl
0x180088fd8  jnz     loc_18008982F
0x180088fde  mov     [rbp+440h+var_4B0], r13
0x180088fe2  mov     rdi, [rsp+540h+var_4E0]
0x180088fe7  mov     rax, [rdi]
0x180088fea  mov     rbx, [rax+40h]
0x180088fee  mov     [rbp+440h+var_4B0], r13
0x180088ff2  lea     rdx, ?c_winflagsDataJsonTag@WinFlagsFactory@@0QEBGEB; ushort const * const WinFlagsFactory::c_winflagsDataJsonTag
0x180088ff9  lea     rcx, [rbp+440h+var_3B0]
0x180089000  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180089005  nop
0x180089006  lea     r8, [rbp+440h+var_4B0]
0x18008900a  mov     rdx, [rax+18h]
0x18008900e  mov     rcx, rdi
0x180089011  mov     rax, rbx
0x180089014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089019  nop
0x18008901a  mov     ebx, 80000000h
0x18008901f  lea     ecx, [rax+rbx]
0x180089022  test    ebx, ecx
0x180089024  jnz     short loc_18008902C
0x180089026  cmp     eax, esi
0x180089028  mov     cl, 1
0x18008902a  jnz     short loc_18008902F
0x18008902c  mov     cl, r13b
0x18008902f  mov     r10, [rbp+448h]
0x180089036  test    cl, cl
0x180089038  jnz     loc_1800899D0
0x18008903e  cmp     eax, esi
0x180089040  jz      loc_180089751
0x180089046  mov     [rbp+440h+var_490], r13
0x18008904a  mov     rdi, [rbp+440h+var_4B0]
0x18008904e  mov     rax, [rdi]
0x180089051  mov     rbx, [rax+48h]
0x180089055  mov     [rbp+440h+var_490], r13
0x180089059  lea     rdx, ?c_winflagsItemsJsonTag@WinFlagsFactory@@0QEBGEB; ushort const * const WinFlagsFactory::c_winflagsItemsJsonTag
0x180089060  lea     rcx, [rbp+440h+var_3B0]
0x180089067  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008906c  nop
0x18008906d  lea     r8, [rbp+440h+var_490]
0x180089071  mov     rdx, [rax+18h]
0x180089075  mov     rcx, rdi
0x180089078  mov     rax, rbx
0x18008907b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089080  nop
0x180089081  mov     ebx, 80000000h
0x180089086  lea     ecx, [rax+rbx]
0x180089089  test    ebx, ecx
0x18008908b  jnz     short loc_180089093
0x18008908d  cmp     eax, esi
0x18008908f  mov     cl, 1
0x180089091  jnz     short loc_180089096
0x180089093  mov     cl, r13b
0x180089096  mov     r10, [rbp+448h]
0x18008909d  test    cl, cl
0x18008909f  jnz     loc_1800899B8
0x1800890a5  cmp     eax, esi
0x1800890a7  jz      loc_180089747
0x1800890ad  lea     rdx, [rbp+440h+var_488]
0x1800890b1  lea     rcx, [rbp+440h+var_490]
0x1800890b5  call    ??$query@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$com_ptr_t@UIJsonArray@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonArray,wil::err_exception_policy>::query<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(void)
0x1800890ba  nop
0x1800890bb  mov     rax, [rbp+440h+var_488]
0x1800890bf  mov     [rsp+540h+var_4F0], rax
0x1800890c4  mov     [rbp+440h+var_448], rax
0x1800890c8  mov     [rbp+440h+var_440], r13d
0x1800890cc  mov     [rbp+440h+var_438], r13
0x1800890d0  lea     rdx, [rbp+440h+var_3B0]
0x1800890d7  lea     rcx, [rsp+540h+var_4F0]
0x1800890dc  call    ?end@?$vector_range@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>,wil::err_exception_policy>::end(void)
0x1800890e1  nop
0x1800890e2  mov     eax, [rbp+440h+var_440]
0x1800890e5  cmp     eax, [rbp+440h+var_3A8]
0x1800890eb  jz      loc_180089726
0x1800890f1  lea     rcx, [rbp+440h+var_448]
0x1800890f5  call    ??Dvector_iterator@?$vector_range@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x1800890fa  mov     rsi, rax
0x1800890fd  mov     [rbp+440h+var_4B8], r13
0x180089101  mov     rdi, [r12]
0x180089105  mov     rdx, [rdi]
0x180089108  mov     rbx, [rdx+30h]
0x18008910c  xor     ecx, ecx; string
0x18008910e  call    cs:__imp_WindowsDeleteString
0x180089114  mov     [rbp+440h+var_4B8], r13
0x180089118  lea     rdx, [rbp+440h+var_4B8]
0x18008911c  mov     rcx, rdi
0x18008911f  mov     rax, rbx
0x180089122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089127  mov     rcx, [rbp+448h]; this
0x18008912e  test    eax, eax
0x180089130  js      loc_1800899A3
0x180089136  mov     [rsp+540h+var_4F8], r13
0x18008913b  mov     rcx, [rsi]
0x18008913e  mov     rax, [rcx]
0x180089141  mov     [rsp+540h+var_4F8], r13
0x180089146  lea     rdx, [rsp+540h+var_4F8]
0x18008914b  mov     rax, [rax+60h]
0x18008914f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089154  mov     rcx, [rbp+448h]; this
0x18008915b  test    eax, eax
0x18008915d  js      loc_18008998E
0x180089163  mov     [rbp+440h+var_4C0], r13
0x180089167  mov     rdi, [rsp+540h+var_4F8]
0x18008916c  mov     rax, [rdi]
0x18008916f  mov     rbx, [rax+40h]
0x180089173  mov     [rbp+440h+var_4C0], r13
0x180089177  lea     rdx, ?c_winflagsJsonTag@WinFlagsFactory@@0QEBGEB; ushort const * const WinFlagsFactory::c_winflagsJsonTag
0x18008917e  lea     rcx, [rbp+440h+var_3D0]
0x180089182  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180089187  nop
0x180089188  lea     r8, [rbp+440h+var_4C0]
0x18008918c  mov     rdx, [rax+18h]
0x180089190  mov     rcx, rdi
0x180089193  mov     rax, rbx
0x180089196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008919b  nop
0x18008919c  mov     ebx, 80000000h
0x1800891a1  lea     ecx, [rax+rbx]
0x1800891a4  mov     esi, 83750009h
0x1800891a9  test    ebx, ecx
0x1800891ab  jnz     short loc_1800891B3
0x1800891ad  cmp     eax, esi
0x1800891af  mov     cl, 1
0x1800891b1  jnz     short loc_1800891B6
0x1800891b3  mov     cl, r13b
0x1800891b6  mov     r10, [rbp+448h]
0x1800891bd  test    cl, cl
0x1800891bf  jnz     loc_180089976
0x1800891c5  cmp     eax, esi
0x1800891c7  jnz     short loc_1800891ED
0x1800891c9  lea     rcx, [rbp+440h+var_4C0]
0x1800891cd  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800891d2  nop
0x1800891d3  lea     rcx, [rsp+540h+var_4F8]
0x1800891d8  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800891dd  nop
0x1800891de  mov     rcx, [rbp+440h+var_4B8]; string
0x1800891e2  call    cs:__imp_WindowsDeleteString
0x1800891e8  jmp     loc_180089719
0x1800891ed  movsd   [rbp+440h+var_478], xmm6
0x1800891f2  mov     rdi, [rsp+540h+var_4F8]
0x1800891f7  mov     rax, [rdi]
0x1800891fa  mov     rbx, [rax+58h]
0x1800891fe  lea     rdx, ?c_winflagsFeatureIdJsonTag@WinFlagsFactory@@0QEBGEB; ushort const * const WinFlagsFactory::c_winflagsFeatureIdJsonTag
0x180089205  lea     rcx, [rbp+440h+var_3D0]
0x180089209  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008920e  nop
0x18008920f  lea     r8, [rbp+440h+var_478]
0x180089213  mov     rdx, [rax+18h]
0x180089217  mov     rcx, rdi
0x18008921a  mov     rax, rbx
0x18008921d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089222  nop
0x180089223  mov     edx, 80000000h
0x180089228  lea     ecx, [rax+rdx]
0x18008922b  test    edx, ecx
0x18008922d  jnz     short loc_180089235
0x18008922f  cmp     eax, esi
0x180089231  mov     cl, 1
0x180089233  jnz     short loc_180089238
0x180089235  mov     cl, r13b
0x180089238  mov     r10, [rbp+448h]
0x18008923f  test    cl, cl
0x180089241  jnz     loc_18008995E
0x180089247  cmp     eax, esi
0x180089249  jz      loc_1800891C9
0x18008924f  mov     [rbp+440h+var_498], r13
0x180089253  mov     rdi, [rsp+540h+var_4F8]
  ... truncated ...
```
