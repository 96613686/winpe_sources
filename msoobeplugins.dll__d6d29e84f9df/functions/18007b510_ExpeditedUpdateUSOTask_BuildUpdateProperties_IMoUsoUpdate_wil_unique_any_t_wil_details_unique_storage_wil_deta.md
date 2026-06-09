# ExpeditedUpdateUSOTask::_BuildUpdateProperties(IMoUsoUpdate *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18007b510`
- end: `0x18007c409`
- name: `?_BuildUpdateProperties@ExpeditedUpdateUSOTask@@AEAAJPEAUIMoUsoUpdate@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `3833`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180079ce0`

## callees

- `0x180003470`
- `0x1800068f4`
- `0x180006bb8`
- `0x180008544`
- `0x18001ad08`
- `0x1800230b0`
- `0x18002f39c`
- `0x180040918`
- `0x1800418d8`
- `0x180042068`
- `0x180043c58`
- `0x180078004`
- `0x18007b510`
- `0x18007cc5c`
- `0x18007ce48`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007b796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007ba9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007bda6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007beef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007c0e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007c1f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007b796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007ba9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007bda6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007beef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007c0e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007c1f6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007b5cb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007b5cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c032`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c032`
- `OLEAUT32!__imp_SysStringLen` at `0x18007b786`
- `OLEAUT32!__imp_SysStringLen` at `0x18007ba8d`
- `OLEAUT32!__imp_SysStringLen` at `0x18007bd95`
- `OLEAUT32!__imp_SysStringLen` at `0x18007bedf`
- `OLEAUT32!__imp_SysStringLen` at `0x18007c0d4`
- `OLEAUT32!__imp_SysStringLen` at `0x18007c1e6`
- `OLEAUT32!__imp_SysStringLen` at `0x18007b786`
- `OLEAUT32!__imp_SysStringLen` at `0x18007ba8d`
- `OLEAUT32!__imp_SysStringLen` at `0x18007bd95`
- `OLEAUT32!__imp_SysStringLen` at `0x18007bedf`
- `OLEAUT32!__imp_SysStringLen` at `0x18007c0d4`
- `OLEAUT32!__imp_SysStringLen` at `0x18007c1e6`

## string_xrefs

- `0x18007b557`: `Windows.Data.Json.JsonObject`
- `0x18007b5ab`: `Windows.Data.Json.JsonValue`
- `0x18007bb45`: `UpdateTitle`
- `0x18007b583`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007b5de`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007b630`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007b689`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007b6b6`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
__int64 __fastcall ExpeditedUpdateUSOTask::_BuildUpdateProperties(
        __int64 a1,
        __int64 (__fastcall ***a2)(__int64, GUID *, __int64 **),
        __int64 a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int ActivationFactory; // eax
  __int64 (__fastcall **v8)(__int64, GUID *, __int64 **); // rax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, __int64, __int64); // rdi
  __int64 v15; // rbx
  int v16; // eax
  int v17; // eax
  BSTR *p_pbstr; // rcx
  UINT v19; // eax
  HRESULT v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, HSTRING, int *); // rdi
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, __int64, __int64); // rdi
  __int64 v28; // rbx
  int v29; // eax
  __int64 v30; // rbx
  __int64 (__fastcall *v31)(__int64, __int64, int *); // rdi
  __int64 v32; // rdx
  int v33; // eax
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, __int64, __int64); // rdi
  __int64 v36; // rbx
  int v37; // eax
  __int64 v38; // rbx
  __int64 (__fastcall *v39)(__int64, __int64, int *); // rdi
  __int64 v40; // rdx
  int v41; // eax
  __int64 v42; // rsi
  __int64 (__fastcall *v43)(__int64, __int64, __int64); // rdi
  __int64 v44; // rbx
  int v45; // eax
  int v46; // eax
  UINT v47; // eax
  HRESULT v48; // eax
  __int64 v49; // rdx
  __int64 v50; // rbx
  __int64 (__fastcall *v51)(__int64, HSTRING, int *); // rdi
  __int64 v52; // rdx
  int v53; // eax
  __int64 v54; // rsi
  __int64 (__fastcall *v55)(__int64, __int64, __int64); // rdi
  __int64 v56; // rbx
  int v57; // eax
  __int64 v58; // rbx
  __int64 (__fastcall *v59)(__int64, __int64, int *); // rdi
  __int64 v60; // rdx
  int v61; // eax
  __int64 v62; // rsi
  __int64 (__fastcall *v63)(__int64, __int64, __int64); // rdi
  __int64 v64; // rbx
  int v65; // eax
  __int64 v66; // rbx
  __int64 (__fastcall *v67)(__int64, __int64, int *); // rdi
  __int64 v68; // rdx
  int v69; // eax
  __int64 v70; // rsi
  __int64 (__fastcall *v71)(__int64, __int64, __int64); // rdi
  __int64 v72; // rbx
  int v73; // eax
  int v74; // eax
  UINT v75; // eax
  HRESULT v76; // eax
  __int64 v77; // rbx
  __int64 (__fastcall *v78)(__int64, HSTRING, int *); // rdi
  __int64 v79; // rcx
  int v80; // eax
  __int64 v81; // rsi
  __int64 (__fastcall *v82)(__int64, __int64, __int64); // rdi
  __int64 v83; // rbx
  int v84; // eax
  __int64 v85; // rax
  int v86; // eax
  UINT v87; // eax
  HRESULT v88; // eax
  __int64 v89; // rbx
  __int64 (__fastcall *v90)(__int64, HSTRING, int *); // rdi
  __int64 v91; // rcx
  int v92; // eax
  __int64 v93; // rsi
  __int64 (__fastcall *v94)(__int64, __int64, __int64); // rdi
  __int64 v95; // rbx
  int v96; // eax
  __int64 *v97; // rdi
  __int64 (__fastcall *v98)(__int64 *, BSTR *); // rsi
  OLECHAR *v99; // rbx
  int v100; // eax
  __int64 v101; // rbx
  __int64 (__fastcall *v102)(__int64, HSTRING, int *); // rdi
  __int64 v103; // rcx
  int v104; // eax
  UINT v105; // eax
  HRESULT v106; // eax
  BSTR *v107; // rcx
  __int64 v108; // rsi
  __int64 (__fastcall *v109)(__int64, __int64, __int64); // rdi
  __int64 v110; // rbx
  int v111; // eax
  BSTR *p_bstrString; // rcx
  __int64 v113; // rax
  int v114; // eax
  UINT v115; // eax
  HRESULT v116; // eax
  __int64 v117; // rbx
  __int64 (__fastcall *v118)(__int64, HSTRING, int *); // rdi
  __int64 v119; // rcx
  int v120; // eax
  __int64 v121; // rsi
  __int64 (__fastcall *v122)(__int64, __int64, __int64); // rdi
  __int64 v123; // rbx
  int v124; // eax
  int v125; // eax
  __int64 v126; // rdx
  __int64 v127; // rdi
  __int64 (__fastcall *v128)(__int64, __int64); // rbx
  int v130[2]; // [rsp+20h] [rbp-B9h] BYREF
  __int64 v131; // [rsp+28h] [rbp-B1h] BYREF
  __int64 *v132; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v133; // [rsp+38h] [rbp-A1h] BYREF
  BSTR v134; // [rsp+40h] [rbp-99h] BYREF
  HSTRING v135; // [rsp+48h] [rbp-91h] BYREF
  __int64 v136; // [rsp+50h] [rbp-89h] BYREF
  BSTR v137; // [rsp+58h] [rbp-81h] BYREF
  BSTR v138; // [rsp+60h] [rbp-79h] BYREF
  HSTRING v139; // [rsp+68h] [rbp-71h] BYREF
  HSTRING v140; // [rsp+70h] [rbp-69h] BYREF
  BSTR pbstr; // [rsp+78h] [rbp-61h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-59h] BYREF
  BSTR v143; // [rsp+88h] [rbp-51h] BYREF
  HSTRING v144; // [rsp+90h] [rbp-49h] BYREF
  HSTRING string; // [rsp+98h] [rbp-41h] BYREF
  int v146; // [rsp+A0h] [rbp-39h] BYREF
  int v147; // [rsp+A4h] [rbp-35h] BYREF
  HSTRING v148; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v149; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v150; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v151; // [rsp+C8h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v153; // [rsp+E8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v136 = 0;
  v153 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v5 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v153, &v136);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v131 = 0;
    v153 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = RoGetActivationFactory(v153, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v131);
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BD,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v130[0]);
LABEL_5:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v131);
      goto LABEL_132;
    }
    *(_QWORD *)v130 = 0;
    v8 = *a2;
    v132 = 0;
    v9 = (*v8)((__int64)a2, &GUID_094c3761_2220_471d_9830_3baa13cea544, &v132);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CD,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v9,
        v130[0]);
LABEL_8:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v132);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v130);
      goto LABEL_5;
    }
    v133 = 0;
    v10 = *v132;
    v133 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v10 + 328))(v132, &v133);
    v6 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D0,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v11,
        v130[0]);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v133);
      goto LABEL_8;
    }
    if ( (int)ExpeditedUpdateUSOTask::_ParseStringToJsonValue(v12, &v133, v130) >= 0 )
    {
      v13 = v136;
      v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
      v15 = *(_QWORD *)v130;
      v153 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ClientMetadata", 0xFu, 0xEu);
      v16 = v14(v13, v153, v15);
      if ( v16 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2D3,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v16,
          v130[0]);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::GetImpl'::`2'::impl) )
    {
      pbstr = 0;
      v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), BSTR *))(*a2)[20])(
              a2,
              &pbstr);
      v6 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D9,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v17,
          v130[0]);
LABEL_18:
        p_pbstr = &pbstr;
LABEL_19:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(p_pbstr);
        goto LABEL_11;
      }
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v19 = SysStringLen(pbstr);
      v20 = WindowsCreateString(pbstr, v19, &string);
      v6 = v20;
      if ( v20 < 0 )
      {
        v21 = 731;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v20,
          v130[0]);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        goto LABEL_18;
      }
      v22 = v131;
      v23 = *(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v131 + 80LL);
      v24 = *(_QWORD *)v130;
      *(_QWORD *)v130 = 0;
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v25 = v23(v22, string, v130);
      if ( v25 >= 0 )
      {
        v26 = v136;
        v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
        v28 = *(_QWORD *)v130;
        v153 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ProviderId", 0xBu, 0xAu);
        v29 = v27(v26, v153, v28);
        if ( v29 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2DE,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
            (const char *)(unsigned int)v29,
            v130[0]);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2DC,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v25,
          v130[0]);
      }
      v150 = 0;
      v151 = 0;
      v20 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), __int128 *))(*a2)[15])(
              a2,
              &v150);
      v6 = v20;
      if ( v20 < 0 )
      {
        v21 = 738;
        goto LABEL_22;
      }
      v30 = v131;
      v31 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v131 + 72LL);
      v32 = *(_QWORD *)v130;
      *(_QWORD *)v130 = 0;
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      v33 = v31(v30, v32, v130);
      if ( v33 >= 0 )
      {
        v34 = v136;
        v35 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
        v36 = *(_QWORD *)v130;
        v153 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ActionClass", 0xCu, 0xBu);
        v37 = v35(v34, v153, v36);
        if ( v37 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2E5,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
            (const char *)(unsigned int)v37,
            v130[0]);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E3,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v33,
          v130[0]);
      }
      v38 = v131;
      v39 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v131 + 64LL);
      v40 = *(_QWORD *)v130;
      *(_QWORD *)v130 = 0;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      LOBYTE(v40) = BYTE12(v150);
      v41 = v39(v38, v40, v130);
      if ( v41 >= 0 )
      {
        v42 = v136;
        v43 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
        v44 = *(_QWORD *)v130;
        v153 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"InProgress", 0xBu, 0xAu);
        v45 = v43(v42, v153, v44);
        if ( v45 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2EA,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
            (const char *)(unsigned int)v45,
            v130[0]);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E8,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v41,
          v130[0]);
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExpeditedUpdatePILess>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExpeditedUpdatePILess>::GetImpl'::`2'::impl) )
    {
LABEL_126:
      v149 = 0;
      v125 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v136)(
               v136,
               &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
               &v149);
      v6 = v125;
      if ( v125 >= 0 )
      {
        v127 = v149;
        v128 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v149 + 56LL);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          a3,
          0);
        v125 = v128(v127, a3);
        v6 = v125;
        if ( v125 >= 0 )
        {
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v149);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v133);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v132);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v130);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v131);
          v6 = 0;
          goto LABEL_132;
        }
        v126 = 825;
      }
      else
      {
        v126 = 824;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v126,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v125,
        v130[0]);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v149);
      goto LABEL_11;
    }
    v134 = 0;
    v46 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), BSTR *))(*a2)[3])(a2, &v134);
    v6 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F1,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v46,
        v130[0]);
LABEL_47:
      p_pbstr = &v134;
      goto LABEL_19;
    }
    v135 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v135,
      0);
    v47 = SysStringLen(v134);
    v48 = WindowsCreateString(v134, v47, &v135);
    v6 = v48;
    if ( v48 < 0 )
    {
      v49 = 755;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v49,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v48,
        v130[0]);
LABEL_51:
      Windows::Internal::String::~String((Windows::Internal::String *)&v135);
      goto LABEL_47;
    }
    v50 = v131;
    v51 = *(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v131 + 80LL);
    v52 = *(_QWORD *)v130;
    *(_QWORD *)v130 = 0;
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    v53 = v51(v50, v135, v130);
    if ( v53 >= 0 )
    {
      v54 = v136;
      v55 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
      v56 = *(_QWORD *)v130;
      v153 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UpdateTitle", 0xCu, 0xBu);
      v57 = v55(v54, v153, v56);
      if ( v57 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2F6,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v57,
          v130[0]);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2F4,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v53,
        v130[0]);
    }
    v146 = 0;
    v48 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), int *))(*a2)[19])(a2, &v146);
    v6 = v48;
    if ( v48 < 0 )
    {
      v49 = 762;
      goto LABEL_50;
    }
    v58 = v131;
    v59 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v131 + 64LL);
    v60 = *(_QWORD *)v130;
    *(_QWORD *)v130 = 0;
    if ( v60 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    LOBYTE(v60) = v146;
    v61 = v59(v58, v60, v130);
    if ( v61 >= 0 )
    {
      v62 = v136;
      v63 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
      v64 = *(_QWORD *)v130;
      v153 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsSeeker", 9u, 8u);
      v65 = v63(v62, v153, v64);
      if ( v65 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2FD,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v65,
          v130[0]);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2FB,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v61,
        v130[0]);
    }
    v147 = 0;
    v48 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), int *))(*a2)[24])(a2, &v147);
    v6 = v48;
    if ( v48 < 0 )
    {
      v49 = 769;
      goto LABEL_50;
    }
    v66 = v131;
    v67 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v131 + 64LL);
    v68 = *(_QWORD *)v130;
    *(_QWORD *)v130 = 0;
    if ( v68 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    LOBYTE(v68) = v147;
    v69 = v67(v66, v68, v130);
    if ( v69 >= 0 )
    {
      v70 = v136;
      v71 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
      v72 = *(_QWORD *)v130;
      v153 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsFeature", 0xAu, 9u);
      v73 = v71(v70, v153, v72);
      if ( v73 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x304,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v73,
          v130[0]);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x302,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v69,
        v130[0]);
    }
    v137 = 0;
    v74 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), BSTR *))(*a2)[31])(a2, &v137);
    v6 = v74;
    if ( v74 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x308,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v74,
        v130[0]);
LABEL_76:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v137);
      goto LABEL_51;
    }
    v139 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v139,
      0);
    v75 = SysStringLen(v137);
    v76 = WindowsCreateString(v137, v75, &v139);
    v6 = v76;
    if ( v76 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30A,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v76,
        v130[0]);
LABEL_79:
      Windows::Internal::String::~String((Windows::Internal::String *)&v139);
      goto LABEL_76;
    }
    v77 = v131;
    v78 = *(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v131 + 80LL);
    v79 = *(_QWORD *)v130;
    *(_QWORD *)v130 = 0;
    if ( v79 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    v80 = v78(v77, v139, v130);
    if ( v80 >= 0 )
    {
      v81 = v136;
      v82 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
      v83 = *(_QWORD *)v130;
      v153 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"FlightID", 9u, 8u);
      v84 = v82(v81, v153, v83);
      if ( v84 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x30D,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v84,
          v130[0]);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x30B,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v80,
        v130[0]);
    }
    v138 = 0;
    v85 = *v132;
    v138 = 0;
    v86 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v85 + 320))(v132, &v138);
    v6 = v86;
    if ( v86 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x311,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v86,
        v130[0]);
LABEL_88:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v138);
      goto LABEL_79;
    }
    v140 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v140,
      0);
    v87 = SysStringLen(v138);
    v88 = WindowsCreateString(v138, v87, &v140);
    v6 = v88;
    if ( v88 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x313,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v88,
        v130[0]);
LABEL_91:
      Windows::Internal::String::~String((Windows::Internal::String *)&v140);
      goto LABEL_88;
    }
    v89 = v131;
    v90 = *(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v131 + 80LL);
    v91 = *(_QWORD *)v130;
    *(_QWORD *)v130 = 0;
    if ( v91 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    v92 = v90(v89, v140, v130);
    if ( v92 >= 0 )
    {
      v93 = v136;
      v94 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
      v95 = *(_QWORD *)v130;
      v153 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ProductName", 0xCu, 0xBu);
      v96 = v94(v93, v153, v95);
      if ( v96 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x316,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v96,
          v130[0]);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x314,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v92,
        v130[0]);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::GetImpl'::`2'::impl) )
    {
      bstrString = 0;
      v153 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"0", 2u, 1u);
      v148 = (HSTRING)v153;
      v153 = 0;
      v97 = v132;
      v98 = *(__int64 (__fastcall **)(__int64 *, BSTR *))(*v132 + 312);
      v99 = bstrString;
      if ( bstrString )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v144);
        SysFreeString(v99);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v144);
      }
      bstrString = 0;
      v100 = v98(v97, &bstrString);
      if ( v100 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x31E,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v100,
          v130[0]);
LABEL_103:
        v101 = v131;
        v102 = *(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v131 + 80LL);
        v103 = *(_QWORD *)v130;
        *(_QWORD *)v130 = 0;
        if ( v103 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
        v104 = v102(v101, v148, v130);
        if ( v104 >= 0 )
        {
          v108 = v136;
          v109 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
          v110 = *(_QWORD *)v130;
          v153 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ProductVersion", 0xFu, 0xEu);
          v111 = v109(v108, v153, v110);
          if ( v111 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x325,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
              (const char *)(unsigned int)v111,
              v130[0]);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x323,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
            (const char *)(unsigned int)v104,
            v130[0]);
        }
        Windows::Internal::String::~String((Windows::Internal::String *)&v148);
        p_bstrString = &bstrString;
LABEL_125:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(p_bstrString);
        Windows::Internal::String::~String((Windows::Internal::String *)&v140);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v138);
        Windows::Internal::String::~String((Windows::Internal::String *)&v139);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v137);
        Windows::Internal::String::~String((Windows::Internal::String *)&v135);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v134);
        goto LABEL_126;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v148,
        0);
      v105 = SysStringLen(bstrString);
      v106 = WindowsCreateString(bstrString, v105, &v148);
      v6 = v106;
      if ( v106 >= 0 )
        goto LABEL_103;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x320,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v106,
        v130[0]);
      Windows::Internal::String::~String((Windows::Internal::String *)&v148);
      v107 = &bstrString;
    }
    else
    {
      v143 = 0;
      v113 = *v132;
      v143 = 0;
      v114 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v113 + 312))(v132, &v143);
      v6 = v114;
      if ( v114 >= 0 )
      {
        v144 = 0;
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          &v144,
          0);
        v115 = SysStringLen(v143);
        v116 = WindowsCreateString(v143, v115, &v144);
        v6 = v116;
        if ( v116 >= 0 )
        {
          v117 = v131;
          v118 = *(__int64 (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v131 + 80LL);
          v119 = *(_QWORD *)v130;
          *(_QWORD *)v130 = 0;
          if ( v119 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
          v120 = v118(v117, v144, v130);
          if ( v120 >= 0 )
          {
            v121 = v136;
            v122 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v136 + 56LL);
            v123 = *(_QWORD *)v130;
            v153 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ProductVersion", 0xFu, 0xEu);
            v124 = v122(v121, v153, v123);
            if ( v124 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x332,
                (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
                (const char *)(unsigned int)v124,
                v130[0]);
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x330,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
              (const char *)(unsigned int)v120,
              v130[0]);
          }
          Windows::Internal::String::~String((Windows::Internal::String *)&v144);
          p_bstrString = &v143;
          goto LABEL_125;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32F,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v116,
          v130[0]);
        Windows::Internal::String::~String((Windows::Internal::String *)&v144);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32D,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v114,
          v130[0]);
      }
      v107 = &v143;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v107);
    goto LABEL_91;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2BB,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
    (const char *)(unsigned int)v5,
    v130[0]);
LABEL_132:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v136);
  return v6;
}

```

## disassembly

```asm
0x18007b510  mov     [rsp-8+arg_0], rbx
0x18007b515  push    rbp
0x18007b516  push    rsi
0x18007b517  push    rdi
0x18007b518  push    r12
0x18007b51a  push    r13
0x18007b51c  push    r14
0x18007b51e  push    r15
0x18007b520  lea     rbp, [rsp-27h]
0x18007b525  sub     rsp, 100h
0x18007b52c  mov     rax, cs:__security_cookie
0x18007b533  xor     rax, rsp
0x18007b536  mov     [rbp+57h+var_40], rax
0x18007b53a  mov     r12, r8
0x18007b53d  mov     r15, rdx
0x18007b540  xor     r13d, r13d
0x18007b543  mov     [rsp+130h+var_E0], r13
0x18007b548  mov     [rbp+57h+var_48], r13
0x18007b54c  lea     edi, [r13+1Ch]
0x18007b550  mov     r9d, edi; unsigned int
0x18007b553  lea     r8d, [r13+1Dh]; unsigned int
0x18007b557  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18007b55e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007b562  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007b567  nop
0x18007b568  lea     rdx, [rsp+130h+var_E0]
0x18007b56d  mov     rcx, [rbp+57h+var_48]
0x18007b571  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18007b576  mov     ebx, eax
0x18007b578  test    eax, eax
0x18007b57a  jns     short loc_18007B599
0x18007b57c  mov     rcx, [rbp+5Fh]; this
0x18007b580  mov     r9d, eax; char *
0x18007b583  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007b58a  mov     edx, 2BBh; void *
0x18007b58f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b594  jmp     loc_18007C3D6
0x18007b599  mov     [rsp+130h+var_108], r13
0x18007b59e  mov     [rbp+57h+var_48], r13
0x18007b5a2  mov     r9d, 1Bh; unsigned int
0x18007b5a8  mov     r8d, edi; unsigned int
0x18007b5ab  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18007b5b2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007b5b6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007b5bb  lea     r8, [rsp+130h+var_108]
0x18007b5c0  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18007b5c7  mov     rcx, [rbp+57h+var_48]
0x18007b5cb  call    cs:__imp_RoGetActivationFactory
0x18007b5d1  mov     ebx, eax
0x18007b5d3  test    eax, eax
0x18007b5d5  jns     short loc_18007B5FF
0x18007b5d7  mov     rcx, [rbp+5Fh]; this
0x18007b5db  mov     r9d, eax; char *
0x18007b5de  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007b5e5  mov     edx, 2BDh; void *
0x18007b5ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b5ef  nop
0x18007b5f0  lea     rcx, [rsp+130h+var_108]
0x18007b5f5  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007b5fa  jmp     loc_18007C3D6
0x18007b5ff  mov     qword ptr [rsp+130h+var_110], r13; int
0x18007b604  mov     rax, [r15]
0x18007b607  mov     [rsp+130h+var_100], r13
0x18007b60c  lea     r8, [rsp+130h+var_100]
0x18007b611  lea     rdx, _GUID_094c3761_2220_471d_9830_3baa13cea544
0x18007b618  mov     rcx, r15
0x18007b61b  mov     rax, [rax]
0x18007b61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b623  mov     ebx, eax
0x18007b625  test    eax, eax
0x18007b627  jns     short loc_18007B659
0x18007b629  mov     rcx, [rbp+5Fh]; this
0x18007b62d  mov     r9d, eax; char *
0x18007b630  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007b637  mov     edx, 2CDh; void *
0x18007b63c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b641  nop
0x18007b642  lea     rcx, [rsp+130h+var_100]
0x18007b647  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007b64c  nop
0x18007b64d  lea     rcx, [rsp+130h+var_110]
0x18007b652  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007b657  jmp     short loc_18007B5F0
0x18007b659  mov     [rsp+130h+var_F8], r13
0x18007b65e  mov     rcx, [rsp+130h+var_100]
0x18007b663  mov     rax, [rcx]
0x18007b666  mov     [rsp+130h+var_F8], r13
0x18007b66b  lea     rdx, [rsp+130h+var_F8]
0x18007b670  mov     rax, [rax+148h]
0x18007b677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b67c  mov     ebx, eax
0x18007b67e  test    eax, eax
0x18007b680  jns     short loc_18007B6A7
0x18007b682  mov     rcx, [rbp+5Fh]; this
0x18007b686  mov     r9d, eax; char *
0x18007b689  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007b690  mov     edx, 2D0h; void *
0x18007b695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b69a  nop
0x18007b69b  lea     rcx, [rsp+130h+var_F8]
0x18007b6a0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007b6a5  jmp     short loc_18007B642
0x18007b6a7  lea     r8, [rsp+130h+var_110]
0x18007b6ac  lea     rdx, [rsp+130h+var_F8]
0x18007b6b1  call    ?_ParseStringToJsonValue@ExpeditedUpdateUSOTask@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$com_ptr_t@UIJsonValue@Json@Data@Windows@@Uerr_returncode_policy@wil@@@3@@Z; ExpeditedUpdateUSOTask::_ParseStringToJsonValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::com_ptr_t<Windows::Data::Json::IJsonValue,wil::err_returncode_policy> &)
0x18007b6b6  lea     r14, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007b6bd  test    eax, eax
0x18007b6bf  js      short loc_18007B71C
0x18007b6c1  mov     rsi, [rsp+130h+var_E0]
0x18007b6c6  mov     rax, [rsi]
0x18007b6c9  mov     rdi, [rax+38h]
0x18007b6cd  mov     rbx, qword ptr [rsp+130h+var_110]
0x18007b6d2  mov     [rbp+57h+var_48], r13
0x18007b6d6  mov     r9d, 0Eh; unsigned int
0x18007b6dc  lea     r8d, [r9+1]; unsigned int
0x18007b6e0  lea     rdx, aClientmetadata; "ClientMetadata"
0x18007b6e7  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007b6eb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007b6f0  nop
0x18007b6f1  mov     r8, rbx
0x18007b6f4  mov     rdx, [rbp+57h+var_48]
0x18007b6f8  mov     rcx, rsi
0x18007b6fb  mov     rax, rdi
0x18007b6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b703  mov     rcx, [rbp+5Fh]; this
0x18007b707  test    eax, eax
0x18007b709  jns     short loc_18007B71C
0x18007b70b  mov     r9d, eax; char *
0x18007b70e  mov     r8, r14; unsigned int
0x18007b711  mov     edx, 2D3h; void *
0x18007b716  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007b71b  nop
0x18007b71c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus> `wil::Feature<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::GetImpl(void)'::`2'::impl
0x18007b723  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::__private_IsEnabled(void)
0x18007b728  test    al, al
0x18007b72a  jz      loc_18007BA25
0x18007b730  mov     [rbp+57h+pbstr], r13
0x18007b734  mov     rax, [r15]
0x18007b737  lea     rdx, [rbp+57h+pbstr]
0x18007b73b  mov     rcx, r15
0x18007b73e  mov     rax, [rax+0A0h]
0x18007b745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b74a  mov     ebx, eax
0x18007b74c  test    eax, eax
0x18007b74e  jns     short loc_18007B773
0x18007b750  mov     rcx, [rbp+5Fh]; this
0x18007b754  mov     r9d, eax; char *
0x18007b757  mov     r8, r14; unsigned int
0x18007b75a  mov     edx, 2D9h; void *
0x18007b75f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b764  nop
0x18007b765  lea     rcx, [rbp+57h+pbstr]
0x18007b769  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007b76e  jmp     loc_18007B69B
0x18007b773  mov     [rbp+57h+string], r13
0x18007b777  xor     edx, edx
0x18007b779  lea     rcx, [rbp+57h+string]
0x18007b77d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18007b782  mov     rcx, [rbp+57h+pbstr]; pbstr
0x18007b786  call    cs:__imp_SysStringLen
0x18007b78c  lea     r8, [rbp+57h+string]; string
0x18007b790  mov     edx, eax; length
0x18007b792  mov     rcx, [rbp+57h+pbstr]; sourceString
0x18007b796  call    cs:__imp_WindowsCreateString
0x18007b79c  mov     ebx, eax
0x18007b79e  test    eax, eax
0x18007b7a0  jns     short loc_18007B7C2
0x18007b7a2  mov     edx, 2DBh; void *
0x18007b7a7  mov     r8, r14; unsigned int
0x18007b7aa  mov     r9d, eax; char *
0x18007b7ad  mov     rcx, [rbp+5Fh]; this
0x18007b7b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b7b6  nop
0x18007b7b7  lea     rcx, [rbp+57h+string]; this
0x18007b7bb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007b7c0  jmp     short loc_18007B765
0x18007b7c2  mov     rbx, [rsp+130h+var_108]
0x18007b7c7  mov     rax, [rbx]
0x18007b7ca  mov     rdi, [rax+50h]
0x18007b7ce  mov     rdx, qword ptr [rsp+130h+var_110]
0x18007b7d3  mov     qword ptr [rsp+130h+var_110], r13; int
0x18007b7d8  test    rdx, rdx
0x18007b7db  jz      short loc_18007B7ED
0x18007b7dd  mov     rcx, [rdx]
0x18007b7e0  mov     rax, [rcx+10h]
0x18007b7e4  mov     rcx, rdx
0x18007b7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b7ec  nop
0x18007b7ed  lea     r8, [rsp+130h+var_110]
0x18007b7f2  mov     rdx, [rbp+57h+string]
0x18007b7f6  mov     rcx, rbx
0x18007b7f9  mov     rax, rdi
0x18007b7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b801  mov     rcx, [rbp+5Fh]; this
0x18007b805  test    eax, eax
0x18007b807  jns     short loc_18007B81B
0x18007b809  mov     r9d, eax; char *
0x18007b80c  mov     r8, r14; unsigned int
0x18007b80f  mov     edx, 2DCh; void *
0x18007b814  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007b819  jmp     short loc_18007B876
0x18007b81b  mov     rsi, [rsp+130h+var_E0]
0x18007b820  mov     rax, [rsi]
0x18007b823  mov     rdi, [rax+38h]
0x18007b827  mov     rbx, qword ptr [rsp+130h+var_110]
0x18007b82c  mov     [rbp+57h+var_48], r13
0x18007b830  mov     r9d, 0Ah; unsigned int
0x18007b836  lea     r8d, [r9+1]; unsigned int
0x18007b83a  lea     rdx, aProviderid; "ProviderId"
0x18007b841  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007b845  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007b84a  nop
0x18007b84b  mov     r8, rbx
0x18007b84e  mov     rdx, [rbp+57h+var_48]
0x18007b852  mov     rcx, rsi
0x18007b855  mov     rax, rdi
0x18007b858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b85d  mov     rcx, [rbp+5Fh]; this
0x18007b861  test    eax, eax
0x18007b863  jns     short loc_18007B876
0x18007b865  mov     r9d, eax; char *
0x18007b868  mov     r8, r14; unsigned int
0x18007b86b  mov     edx, 2DEh; void *
0x18007b870  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007b875  nop
0x18007b876  xorps   xmm0, xmm0
0x18007b879  xor     eax, eax
0x18007b87b  movups  [rbp+57h+var_78], xmm0
0x18007b87f  mov     [rbp+57h+var_68], rax
0x18007b883  mov     rax, [r15]
0x18007b886  lea     rdx, [rbp+57h+var_78]
0x18007b88a  mov     rcx, r15
0x18007b88d  mov     rax, [rax+78h]
0x18007b891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b896  mov     ebx, eax
0x18007b898  test    eax, eax
0x18007b89a  jns     short loc_18007B8A6
0x18007b89c  mov     edx, 2E2h
0x18007b8a1  jmp     loc_18007B7A7
0x18007b8a6  mov     rbx, [rsp+130h+var_108]
0x18007b8ab  mov     rax, [rbx]
0x18007b8ae  mov     rdi, [rax+48h]
0x18007b8b2  mov     rdx, qword ptr [rsp+130h+var_110]
0x18007b8b7  mov     qword ptr [rsp+130h+var_110], r13; int
0x18007b8bc  test    rdx, rdx
0x18007b8bf  jz      short loc_18007B8D1
0x18007b8c1  mov     rcx, [rdx]
0x18007b8c4  mov     rax, [rcx+10h]
0x18007b8c8  mov     rcx, rdx
0x18007b8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b8d0  nop
0x18007b8d1  movd    xmm1, dword ptr [rbp+57h+var_78+8]
0x18007b8d6  cvtdq2pd xmm1, xmm1
0x18007b8da  lea     r8, [rsp+130h+var_110]
0x18007b8df  mov     rcx, rbx
0x18007b8e2  mov     rax, rdi
0x18007b8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b8ea  mov     rcx, [rbp+5Fh]; this
0x18007b8ee  test    eax, eax
0x18007b8f0  jns     short loc_18007B904
0x18007b8f2  mov     r9d, eax; char *
0x18007b8f5  mov     r8, r14; unsigned int
0x18007b8f8  mov     edx, 2E3h; void *
0x18007b8fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007b902  jmp     short loc_18007B95F
0x18007b904  mov     rsi, [rsp+130h+var_E0]
0x18007b909  mov     rax, [rsi]
0x18007b90c  mov     rdi, [rax+38h]
0x18007b910  mov     rbx, qword ptr [rsp+130h+var_110]
0x18007b915  mov     [rbp+57h+var_48], r13
0x18007b919  mov     r9d, 0Bh; unsigned int
0x18007b91f  lea     r8d, [r9+1]; unsigned int
0x18007b923  lea     rdx, aActionclass; "ActionClass"
0x18007b92a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18007b92e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007b933  nop
0x18007b934  mov     r8, rbx
0x18007b937  mov     rdx, [rbp+57h+var_48]
0x18007b93b  mov     rcx, rsi
0x18007b93e  mov     rax, rdi
0x18007b941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b946  mov     rcx, [rbp+5Fh]; this
0x18007b94a  test    eax, eax
0x18007b94c  jns     short loc_18007B95F
0x18007b94e  mov     r9d, eax; char *
0x18007b951  mov     r8, r14; unsigned int
0x18007b954  mov     edx, 2E5h; void *
0x18007b959  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007b95e  nop
0x18007b95f  mov     rbx, [rsp+130h+var_108]
0x18007b964  mov     rax, [rbx]
0x18007b967  mov     rdi, [rax+40h]
0x18007b96b  mov     rdx, qword ptr [rsp+130h+var_110]
0x18007b970  mov     qword ptr [rsp+130h+var_110], r13; int
0x18007b975  test    rdx, rdx
0x18007b978  jz      short loc_18007B98A
0x18007b97a  mov     rcx, [rdx]
0x18007b97d  mov     rax, [rcx+10h]
0x18007b981  mov     rcx, rdx
0x18007b984  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
