# _lambda_d8c50c42e0be286d672e824af5d026fe_::operator()(void)

- ea: `0x180063f50`
- end: `0x18006498a`
- name: `??R_lambda_d8c50c42e0be286d672e824af5d026fe_@@QEBA@XZ`
- size: `2618`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180066018`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x180040898`
- `0x180040918`
- `0x180042068`
- `0x180043c58`
- `0x180063f50`
- `0x180070d98`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180063ffa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180064635`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180063ffa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180064635`

## string_xrefs

- `0x180063f89`: `Windows.Data.Json.JsonObject`
- `0x180064616`: `Windows.Data.Json.JsonObject`
- `0x180063fdb`: `Windows.Data.Json.JsonValue`
- `0x180063fb4`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdatecallbackshelper.h`
- `0x18006400d`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdatecallbackshelper.h`
- `0x18006405f`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdatecallbackshelper.h`
- `0x18006464d`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdatecallbackshelper.h`
- `0x1800648ed`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdatecallbackshelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall _lambda_d8c50c42e0be286d672e824af5d026fe_::operator()(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int ActivationFactory; // eax
  __int64 v5; // rax
  int v6; // eax
  char v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, PVOID, __int64); // rdi
  __int64 v11; // rbx
  HSTRING_HEADER *v12; // rax
  __int64 *v13; // rbx
  __int64 (__fastcall *v14)(__int64 *, _QWORD, __int64 *); // rdi
  __int64 v15; // rcx
  char v16; // r8
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, PVOID, __int64); // rdi
  __int64 v19; // rbx
  HSTRING_HEADER *v20; // rax
  __int64 *v21; // rbx
  __int64 (__fastcall *v22)(__int64 *, _QWORD, __int64 *); // rdi
  __int64 v23; // rcx
  char v24; // r8
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, PVOID, __int64); // rdi
  __int64 v27; // rbx
  HSTRING_HEADER *v28; // rax
  __int64 *v29; // rbx
  __int64 (__fastcall *v30)(__int64 *, _QWORD, __int64 *); // rdi
  __int64 v31; // rcx
  char v32; // r8
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, PVOID, __int64); // rdi
  __int64 v35; // rbx
  HSTRING_HEADER *v36; // rax
  __int64 v37; // rdx
  __int64 *v38; // rbx
  __int64 (__fastcall *v39)(__int64 *, __int64, __int64 *); // rdi
  __int64 v40; // rcx
  __int64 *v41; // rax
  char v42; // r8
  __int64 v43; // rsi
  __int64 (__fastcall *v44)(__int64, PVOID, __int64); // rdi
  __int64 v45; // rbx
  HSTRING_HEADER *v46; // rax
  __int64 v47; // rdx
  __int64 *v48; // rbx
  __int64 (__fastcall *v49)(__int64 *, __int64, __int64 *); // rdi
  __int64 v50; // rcx
  __int64 *v51; // rax
  char v52; // r8
  __int64 v53; // rsi
  __int64 (__fastcall *v54)(__int64, PVOID, __int64); // rdi
  __int64 v55; // rbx
  HSTRING_HEADER *v56; // rax
  __int64 v57; // rdx
  __int64 *v58; // rbx
  __int64 (__fastcall *v59)(__int64 *, __int64, __int64 *); // rdi
  __int64 v60; // rcx
  __int64 *v61; // rax
  char v62; // r8
  __int64 v63; // rsi
  __int64 (__fastcall *v64)(__int64, PVOID, __int64); // rdi
  __int64 v65; // rbx
  HSTRING_HEADER *v66; // rax
  __int64 v67; // rdx
  __int64 *v68; // rbx
  __int64 (__fastcall *v69)(__int64 *, __int64, __int64 *); // rdi
  __int64 v70; // rcx
  __int64 *v71; // rax
  char v72; // r8
  __int64 v73; // rsi
  __int64 (__fastcall *v74)(__int64, PVOID, __int64); // rdi
  __int64 v75; // rbx
  HSTRING_HEADER *v76; // rax
  __int64 v77; // rdx
  char v78; // r8
  __int64 *v79; // rbx
  __int64 (__fastcall *v80)(__int64 *, PVOID, __int64 *); // rdi
  __int64 v81; // rcx
  HSTRING_HEADER *v82; // rax
  char v83; // r8
  __int64 v84; // rsi
  __int64 (__fastcall *v85)(__int64, PVOID, __int64); // rdi
  __int64 v86; // rbx
  HSTRING_HEADER *v87; // rax
  int v88; // eax
  char v89; // r8
  __int64 v90; // rdx
  __int64 v91; // r9
  __int64 v92; // rbx
  __int64 (__fastcall *v93)(__int64, PVOID, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), char *); // rdi
  __int64 (__fastcall ***v94)(_QWORD, GUID *, _QWORD *); // rcx
  HSTRING_HEADER *v95; // rax
  __int64 (__fastcall ***v96)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v97; // rcx
  char v98; // r8
  __int64 v99; // rsi
  __int64 (__fastcall *v100)(__int64, PVOID, __int64); // rdi
  __int64 v101; // rbx
  HSTRING_HEADER *v102; // rax
  __int64 *v103; // rbx
  __int64 (__fastcall *v104)(__int64 *, __int64, __int64 *); // rdi
  __int64 v105; // rcx
  __int64 v106; // rsi
  __int64 (__fastcall *v107)(__int64, __int64, __int64); // rdi
  __int64 v108; // rbx
  __int64 *v109; // rbx
  __int64 (__fastcall *v110)(__int64 *, __int64, __int64 *); // rdi
  __int64 v111; // rcx
  __int64 v112; // rsi
  __int64 (__fastcall *v113)(__int64, __int64, __int64); // rdi
  __int64 v114; // rbx
  int v115; // eax
  __int64 v116; // rdx
  __int64 v117; // rsi
  __int64 (__fastcall *v118)(__int64, __int64); // rdi
  __int64 v119; // rbx
  int v121; // [rsp+20h] [rbp-49h]
  __int64 v122; // [rsp+30h] [rbp-39h] BYREF
  __int64 *v123; // [rsp+38h] [rbp-31h] BYREF
  char v124[8]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v125; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v126)(_QWORD, GUID *, _QWORD *); // [rsp+50h] [rbp-19h] BYREF
  __int64 v127; // [rsp+58h] [rbp-11h] BYREF
  __int64 v128; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  __int64 v130; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v125 = 0;
  v130 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v2 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v130, &v125);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v123 = 0;
    v130 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = RoGetActivationFactory(v130, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v123);
    v3 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdatecallbackshelper.h",
        (const char *)(unsigned int)ActivationFactory,
        v121);
LABEL_5:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v123);
      goto LABEL_106;
    }
    v122 = 0;
    v5 = *v123;
    v122 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v5 + 72))(v123, *(_QWORD *)a1, &v122);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 62;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdatecallbackshelper.h",
        (const char *)(unsigned int)v6,
        v121);
LABEL_9:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v122);
      goto LABEL_5;
    }
    v9 = v125;
    v10 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v125 + 56LL);
    v11 = v122;
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&ExpeditedUpdateStatusTypeName,
            v7);
    v6 = v10(v9, v12[1].Reserved.Reserved1, v11);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 63;
      goto LABEL_8;
    }
    v13 = v123;
    v14 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v123 + 72);
    v15 = v122;
    v122 = 0;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v6 = v14(v13, *(_QWORD *)(a1 + 8), &v122);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 66;
      goto LABEL_8;
    }
    v17 = v125;
    v18 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v125 + 56LL);
    v19 = v122;
    v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&DownloadInstallProgressTypeName,
            v16);
    v6 = v18(v17, v20[1].Reserved.Reserved1, v19);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 67;
      goto LABEL_8;
    }
    v21 = v123;
    v22 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v123 + 72);
    v23 = v122;
    v122 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v6 = v22(v21, *(_QWORD *)(a1 + 16), &v122);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 70;
      goto LABEL_8;
    }
    v25 = v125;
    v26 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v125 + 56LL);
    v27 = v122;
    v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&StatusCodeTypeName,
            v24);
    v6 = v26(v25, v28[1].Reserved.Reserved1, v27);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 71;
      goto LABEL_8;
    }
    v29 = v123;
    v30 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v123 + 72);
    v31 = v122;
    v122 = 0;
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v6 = v30(v29, *(_QWORD *)(a1 + 24), &v122);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 74;
      goto LABEL_8;
    }
    v33 = v125;
    v34 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v125 + 56LL);
    v35 = v122;
    v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&DownloadSubPhaseTypeName,
            v32);
    v6 = v34(v33, v36[1].Reserved.Reserved1, v35);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 75;
      goto LABEL_8;
    }
    v38 = v123;
    v39 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v123 + 72);
    v40 = v122;
    v122 = 0;
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v41 = *(__int64 **)(a1 + 32);
    if ( *v41 < 0 )
      v37 = *v41 & 1 | ((unsigned __int64)*v41 >> 1);
    v6 = v39(v38, v37, &v122);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 78;
      goto LABEL_8;
    }
    v43 = v125;
    v44 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v125 + 56LL);
    v45 = v122;
    v46 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&TotalBytesDownloadedTypeName,
            v42);
    v6 = v44(v43, v46[1].Reserved.Reserved1, v45);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 79;
      goto LABEL_8;
    }
    v48 = v123;
    v49 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v123 + 72);
    v50 = v122;
    v122 = 0;
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v51 = *(__int64 **)(a1 + 40);
    if ( *v51 < 0 )
      v47 = *v51 & 1 | ((unsigned __int64)*v51 >> 1);
    v6 = v49(v48, v47, &v122);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 82;
      goto LABEL_8;
    }
    v53 = v125;
    v54 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v125 + 56LL);
    v55 = v122;
    v56 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&TotalBytesToDownloadTypeName,
            v52);
    v6 = v54(v53, v56[1].Reserved.Reserved1, v55);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 83;
      goto LABEL_8;
    }
    v58 = v123;
    v59 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v123 + 72);
    v60 = v122;
    v122 = 0;
    if ( v60 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    v61 = *(__int64 **)(a1 + 48);
    if ( *v61 < 0 )
      v57 = *v61 & 1 | ((unsigned __int64)*v61 >> 1);
    v6 = v59(v58, v57, &v122);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 86;
      goto LABEL_8;
    }
    v63 = v125;
    v64 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v125 + 56LL);
    v65 = v122;
    v66 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&CurrentUpdateBytesDownloadedTypeName,
            v62);
    v6 = v64(v63, v66[1].Reserved.Reserved1, v65);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 87;
      goto LABEL_8;
    }
    v68 = v123;
    v69 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v123 + 72);
    v70 = v122;
    v122 = 0;
    if ( v70 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    v71 = *(__int64 **)(a1 + 56);
    if ( *v71 < 0 )
      v67 = *v71 & 1 | ((unsigned __int64)*v71 >> 1);
    v6 = v69(v68, v67, &v122);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 90;
      goto LABEL_8;
    }
    v73 = v125;
    v74 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v125 + 56LL);
    v75 = v122;
    v76 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&CurrentUpdateBytesToDownloadTypeName,
            v72);
    v6 = v74(v73, v76[1].Reserved.Reserved1, v75);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = 91;
      goto LABEL_8;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupUsoTask>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobeNdupUsoTask>::GetImpl'::`2'::impl) )
    {
      if ( **(_QWORD **)(a1 + 64) )
      {
        v79 = v123;
        v80 = *(__int64 (__fastcall **)(__int64 *, PVOID, __int64 *))(*v123 + 80);
        v81 = v122;
        v122 = 0;
        if ( v81 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
        v82 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                *(const WCHAR ***)(a1 + 64),
                v78);
        v6 = v80(v79, v82[1].Reserved.Reserved1, &v122);
        v3 = v6;
        if ( v6 < 0 )
        {
          v8 = 98;
          goto LABEL_8;
        }
        v84 = v125;
        v85 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v125 + 56LL);
        v86 = v122;
        v87 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)&UpdateIdTypeName,
                v83);
        v6 = v85(v84, v87[1].Reserved.Reserved1, v86);
        v3 = v6;
        if ( v6 < 0 )
        {
          v8 = 99;
          goto LABEL_8;
        }
      }
      if ( **(_QWORD **)(a1 + 72) )
      {
        v126 = 0;
        v127 = 0;
        v130 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonObject",
          0x1Du,
          0x1Cu);
        v88 = RoGetActivationFactory(v130, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v127);
        v3 = v88;
        if ( v88 < 0 )
        {
          v90 = 106;
LABEL_73:
          v91 = (unsigned int)v88;
LABEL_74:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v90,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdatecallbackshelper.h",
            (const char *)v91,
            v121);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v127);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v126);
          goto LABEL_9;
        }
        v124[0] = 0;
        v92 = v127;
        v93 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), char *))(*(_QWORD *)v127 + 56LL);
        v94 = v126;
        v126 = 0;
        if ( v94 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v94)[2])(v94);
        v95 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                *(const WCHAR ***)(a1 + 72),
                v89);
        v88 = v93(v92, v95[1].Reserved.Reserved1, &v126, v124);
        v3 = v88;
        if ( v88 < 0 )
        {
          v90 = 108;
          goto LABEL_73;
        }
        if ( !v124[0] )
        {
          v3 = -2147024809;
          v91 = 2147942487LL;
          v90 = 118;
          goto LABEL_74;
        }
        v96 = v126;
        v97 = v122;
        v122 = 0;
        if ( v97 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
        v88 = (**v96)(v96, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v122);
        v3 = v88;
        if ( v88 < 0 )
        {
          v90 = 111;
          goto LABEL_73;
        }
        v99 = v125;
        v100 = *(__int64 (__fastcall **)(__int64, PVOID, __int64))(*(_QWORD *)v125 + 56LL);
        v101 = v122;
        v102 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                 &hstringHeader,
                 (const WCHAR **)&UpdateStatusMapTypeName,
                 v98);
        v88 = v100(v99, v102[1].Reserved.Reserved1, v101);
        v3 = v88;
        if ( v88 < 0 )
        {
          v90 = 114;
          goto LABEL_73;
        }
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v127);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v126);
      }
      v103 = v123;
      v104 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v123 + 72);
      v105 = v122;
      v122 = 0;
      if ( v105 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
      v6 = v104(v103, v77, &v122);
      v3 = v6;
      if ( v6 < 0 )
      {
        v8 = 123;
        goto LABEL_8;
      }
      v106 = v125;
      v107 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v125 + 56LL);
      v108 = v122;
      v130 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"version", 8u, 7u);
      v6 = v107(v106, v130, v108);
      v3 = v6;
      if ( v6 < 0 )
      {
        v8 = 124;
        goto LABEL_8;
      }
    }
    else
    {
      v109 = v123;
      v110 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v123 + 72);
      v111 = v122;
      v122 = 0;
      if ( v111 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
      v6 = v110(v109, v77, &v122);
      v3 = v6;
      if ( v6 < 0 )
      {
        v8 = 129;
        goto LABEL_8;
      }
      v112 = v125;
      v113 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v125 + 56LL);
      v114 = v122;
      v130 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"version", 8u, 7u);
      v6 = v113(v112, v130, v114);
      v3 = v6;
      if ( v6 < 0 )
      {
        v8 = 130;
        goto LABEL_8;
      }
    }
    v128 = 0;
    v115 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v125)(
             v125,
             &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
             &v128);
    v3 = v115;
    if ( v115 >= 0 )
    {
      v117 = v128;
      v118 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v128 + 56LL);
      v119 = *(_QWORD *)(a1 + 80);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        v119,
        0);
      v115 = v118(v117, v119);
      v3 = v115;
      if ( v115 >= 0 )
      {
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v128);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v122);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v123);
        v3 = 0;
        goto LABEL_106;
      }
      v116 = 136;
    }
    else
    {
      v116 = 135;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v116,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdatecallbackshelper.h",
      (const char *)(unsigned int)v115,
      v121);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v128);
    goto LABEL_9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x38,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdatecallbackshelper.h",
    (const char *)(unsigned int)v2,
    v121);
LABEL_106:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v125);
  return v3;
}

```

## disassembly

```asm
0x180063f50  push    rbp
0x180063f52  push    rbx
0x180063f53  push    rsi
0x180063f54  push    rdi
0x180063f55  push    r14
0x180063f57  push    r15
0x180063f59  lea     rbp, [rsp-2Fh]
0x180063f5e  sub     rsp, 98h
0x180063f65  mov     rax, cs:__security_cookie
0x180063f6c  xor     rax, rsp
0x180063f6f  mov     [rbp+57h+var_38], rax
0x180063f73  mov     r14, rcx
0x180063f76  xor     r15d, r15d
0x180063f79  mov     [rbp+57h+var_78], r15
0x180063f7d  mov     [rbp+57h+var_40], r15
0x180063f81  lea     r9d, [r15+1Ch]; unsigned int
0x180063f85  lea     r8d, [r15+1Dh]; unsigned int
0x180063f89  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180063f90  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180063f94  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180063f99  nop
0x180063f9a  lea     rdx, [rbp+57h+var_78]
0x180063f9e  mov     rcx, [rbp+57h+var_40]
0x180063fa2  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180063fa7  mov     ebx, eax
0x180063fa9  test    eax, eax
0x180063fab  jns     short loc_180063FC9
0x180063fad  mov     rcx, [rbp+5Fh]; this
0x180063fb1  mov     r9d, eax; char *
0x180063fb4  lea     r8, aShellOobeMachi_5; "shell\\oobe\\machine\\plugins\\adapters"...
0x180063fbb  lea     edx, [r15+38h]; void *
0x180063fbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063fc4  jmp     loc_180064963
0x180063fc9  mov     [rbp+57h+var_88], r15
0x180063fcd  mov     [rbp+57h+var_40], r15
0x180063fd1  mov     r9d, 1Bh; unsigned int
0x180063fd7  lea     r8d, [r9+1]; unsigned int
0x180063fdb  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180063fe2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180063fe6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180063feb  lea     r8, [rbp+57h+var_88]
0x180063fef  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180063ff6  mov     rcx, [rbp+57h+var_40]
0x180063ffa  call    cs:__imp_RoGetActivationFactory
0x180064000  mov     ebx, eax
0x180064002  test    eax, eax
0x180064004  jns     short loc_18006402D
0x180064006  mov     rcx, [rbp+5Fh]; this
0x18006400a  mov     r9d, eax; char *
0x18006400d  lea     r8, aShellOobeMachi_5; "shell\\oobe\\machine\\plugins\\adapters"...
0x180064014  mov     edx, 3Ah ; ':'; void *
0x180064019  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006401e  nop
0x18006401f  lea     rcx, [rbp+57h+var_88]
0x180064023  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180064028  jmp     loc_180064963
0x18006402d  mov     [rbp+57h+var_90], r15
0x180064031  mov     rcx, [rbp+57h+var_88]
0x180064035  mov     rax, [rcx]
0x180064038  mov     [rbp+57h+var_90], r15
0x18006403c  mov     rdx, [r14]
0x18006403f  movd    xmm1, dword ptr [rdx]
0x180064043  cvtdq2pd xmm1, xmm1
0x180064047  lea     r8, [rbp+57h+var_90]
0x18006404b  mov     rax, [rax+48h]
0x18006404f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064054  mov     ebx, eax
0x180064056  test    eax, eax
0x180064058  jns     short loc_18006407E
0x18006405a  mov     edx, 3Eh ; '>'; void *
0x18006405f  lea     r8, aShellOobeMachi_5; "shell\\oobe\\machine\\plugins\\adapters"...
0x180064066  mov     r9d, eax; char *
0x180064069  mov     rcx, [rbp+5Fh]; this
0x18006406d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064072  nop
0x180064073  lea     rcx, [rbp+57h+var_90]
0x180064077  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006407c  jmp     short loc_18006401F
0x18006407e  mov     rsi, [rbp+57h+var_78]
0x180064082  mov     rax, [rsi]
0x180064085  mov     rdi, [rax+38h]
0x180064089  mov     rbx, [rbp+57h+var_90]
0x18006408d  lea     rdx, ?ExpeditedUpdateStatusTypeName@@3QEBGEB; ushort const * const ExpeditedUpdateStatusTypeName
0x180064094  lea     rcx, [rbp+57h+hstringHeader]
0x180064098  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18006409d  nop
0x18006409e  mov     r8, rbx
0x1800640a1  mov     rdx, [rax+18h]
0x1800640a5  mov     rcx, rsi
0x1800640a8  mov     rax, rdi
0x1800640ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800640b0  mov     ebx, eax
0x1800640b2  test    eax, eax
0x1800640b4  jns     short loc_1800640BD
0x1800640b6  mov     edx, 3Fh ; '?'
0x1800640bb  jmp     short loc_18006405F
0x1800640bd  mov     rbx, [rbp+57h+var_88]
0x1800640c1  mov     rax, [rbx]
0x1800640c4  mov     rdi, [rax+48h]
0x1800640c8  mov     rcx, [rbp+57h+var_90]
0x1800640cc  mov     [rbp+57h+var_90], r15
0x1800640d0  test    rcx, rcx
0x1800640d3  jz      short loc_1800640E2
0x1800640d5  mov     rax, [rcx]
0x1800640d8  mov     rax, [rax+10h]
0x1800640dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800640e1  nop
0x1800640e2  mov     rdx, [r14+8]
0x1800640e6  mov     r8d, [rdx]
0x1800640e9  xorps   xmm1, xmm1
0x1800640ec  cvtsi2sd xmm1, r8
0x1800640f1  lea     r8, [rbp+57h+var_90]
0x1800640f5  mov     rcx, rbx
0x1800640f8  mov     rax, rdi
0x1800640fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064100  mov     ebx, eax
0x180064102  test    eax, eax
0x180064104  jns     short loc_180064110
0x180064106  mov     edx, 42h ; 'B'
0x18006410b  jmp     loc_18006405F
0x180064110  mov     rsi, [rbp+57h+var_78]
0x180064114  mov     rax, [rsi]
0x180064117  mov     rdi, [rax+38h]
0x18006411b  mov     rbx, [rbp+57h+var_90]
0x18006411f  lea     rdx, ?DownloadInstallProgressTypeName@@3QEBGEB; ushort const * const DownloadInstallProgressTypeName
0x180064126  lea     rcx, [rbp+57h+hstringHeader]
0x18006412a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18006412f  nop
0x180064130  mov     r8, rbx
0x180064133  mov     rdx, [rax+18h]
0x180064137  mov     rcx, rsi
0x18006413a  mov     rax, rdi
0x18006413d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064142  mov     ebx, eax
0x180064144  test    eax, eax
0x180064146  jns     short loc_180064152
0x180064148  mov     edx, 43h ; 'C'
0x18006414d  jmp     loc_18006405F
0x180064152  mov     rbx, [rbp+57h+var_88]
0x180064156  mov     rax, [rbx]
0x180064159  mov     rdi, [rax+48h]
0x18006415d  mov     rcx, [rbp+57h+var_90]
0x180064161  mov     [rbp+57h+var_90], r15
0x180064165  test    rcx, rcx
0x180064168  jz      short loc_180064177
0x18006416a  mov     rdx, [rcx]
0x18006416d  mov     rax, [rdx+10h]
0x180064171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064176  nop
0x180064177  mov     rdx, [r14+10h]
0x18006417b  movd    xmm1, dword ptr [rdx]
0x18006417f  cvtdq2pd xmm1, xmm1
0x180064183  lea     r8, [rbp+57h+var_90]
0x180064187  mov     rcx, rbx
0x18006418a  mov     rax, rdi
0x18006418d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064192  mov     ebx, eax
0x180064194  test    eax, eax
0x180064196  jns     short loc_1800641A2
0x180064198  mov     edx, 46h ; 'F'
0x18006419d  jmp     loc_18006405F
0x1800641a2  mov     rsi, [rbp+57h+var_78]
0x1800641a6  mov     rax, [rsi]
0x1800641a9  mov     rdi, [rax+38h]
0x1800641ad  mov     rbx, [rbp+57h+var_90]
0x1800641b1  lea     rdx, ?StatusCodeTypeName@@3QEBGEB; ushort const * const StatusCodeTypeName
0x1800641b8  lea     rcx, [rbp+57h+hstringHeader]
0x1800641bc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800641c1  nop
0x1800641c2  mov     r8, rbx
0x1800641c5  mov     rdx, [rax+18h]
0x1800641c9  mov     rcx, rsi
0x1800641cc  mov     rax, rdi
0x1800641cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641d4  mov     ebx, eax
0x1800641d6  test    eax, eax
0x1800641d8  jns     short loc_1800641E4
0x1800641da  mov     edx, 47h ; 'G'
0x1800641df  jmp     loc_18006405F
0x1800641e4  mov     rbx, [rbp+57h+var_88]
0x1800641e8  mov     rax, [rbx]
0x1800641eb  mov     rdi, [rax+48h]
0x1800641ef  mov     rcx, [rbp+57h+var_90]
0x1800641f3  mov     [rbp+57h+var_90], r15
0x1800641f7  test    rcx, rcx
0x1800641fa  jz      short loc_180064209
0x1800641fc  mov     rdx, [rcx]
0x1800641ff  mov     rax, [rdx+10h]
0x180064203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064208  nop
0x180064209  mov     rdx, [r14+18h]
0x18006420d  movd    xmm1, dword ptr [rdx]
0x180064211  cvtdq2pd xmm1, xmm1
0x180064215  lea     r8, [rbp+57h+var_90]
0x180064219  mov     rcx, rbx
0x18006421c  mov     rax, rdi
0x18006421f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064224  mov     ebx, eax
0x180064226  test    eax, eax
0x180064228  jns     short loc_180064234
0x18006422a  mov     edx, 4Ah ; 'J'
0x18006422f  jmp     loc_18006405F
0x180064234  mov     rsi, [rbp+57h+var_78]
0x180064238  mov     rax, [rsi]
0x18006423b  mov     rdi, [rax+38h]
0x18006423f  mov     rbx, [rbp+57h+var_90]
0x180064243  lea     rdx, ?DownloadSubPhaseTypeName@@3QEBGEB; ushort const * const DownloadSubPhaseTypeName
0x18006424a  lea     rcx, [rbp+57h+hstringHeader]
0x18006424e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180064253  nop
0x180064254  mov     r8, rbx
0x180064257  mov     rdx, [rax+18h]
0x18006425b  mov     rcx, rsi
0x18006425e  mov     rax, rdi
0x180064261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064266  mov     ebx, eax
0x180064268  test    eax, eax
0x18006426a  jns     short loc_180064276
0x18006426c  mov     edx, 4Bh ; 'K'
0x180064271  jmp     loc_18006405F
0x180064276  mov     rbx, [rbp+57h+var_88]
0x18006427a  mov     rax, [rbx]
0x18006427d  mov     rdi, [rax+48h]
0x180064281  mov     rcx, [rbp+57h+var_90]
0x180064285  mov     [rbp+57h+var_90], r15
0x180064289  test    rcx, rcx
0x18006428c  jz      short loc_18006429B
0x18006428e  mov     rax, [rcx]
0x180064291  mov     rax, [rax+10h]
0x180064295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006429a  nop
0x18006429b  mov     rax, [r14+20h]
0x18006429f  mov     rcx, [rax]
0x1800642a2  xorps   xmm1, xmm1
0x1800642a5  test    rcx, rcx
0x1800642a8  js      short loc_1800642B1
0x1800642aa  cvtsi2sd xmm1, rcx
0x1800642af  jmp     short loc_1800642C6
0x1800642b1  mov     rdx, rcx
0x1800642b4  shr     rdx, 1
0x1800642b7  and     ecx, 1
0x1800642ba  or      rdx, rcx
0x1800642bd  cvtsi2sd xmm1, rdx
0x1800642c2  addsd   xmm1, xmm1
0x1800642c6  lea     r8, [rbp+57h+var_90]
0x1800642ca  mov     rcx, rbx
0x1800642cd  mov     rax, rdi
0x1800642d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642d5  mov     ebx, eax
0x1800642d7  test    eax, eax
0x1800642d9  jns     short loc_1800642E5
0x1800642db  mov     edx, 4Eh ; 'N'
0x1800642e0  jmp     loc_18006405F
0x1800642e5  mov     rsi, [rbp+57h+var_78]
0x1800642e9  mov     rax, [rsi]
0x1800642ec  mov     rdi, [rax+38h]
0x1800642f0  mov     rbx, [rbp+57h+var_90]
0x1800642f4  lea     rdx, ?TotalBytesDownloadedTypeName@@3QEBGEB; ushort const * const TotalBytesDownloadedTypeName
0x1800642fb  lea     rcx, [rbp+57h+hstringHeader]
0x1800642ff  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180064304  nop
0x180064305  mov     r8, rbx
0x180064308  mov     rdx, [rax+18h]
0x18006430c  mov     rcx, rsi
0x18006430f  mov     rax, rdi
0x180064312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064317  mov     ebx, eax
0x180064319  test    eax, eax
0x18006431b  jns     short loc_180064327
0x18006431d  mov     edx, 4Fh ; 'O'
0x180064322  jmp     loc_18006405F
0x180064327  mov     rbx, [rbp+57h+var_88]
0x18006432b  mov     rax, [rbx]
0x18006432e  mov     rdi, [rax+48h]
0x180064332  mov     rcx, [rbp+57h+var_90]
0x180064336  mov     [rbp+57h+var_90], r15
0x18006433a  test    rcx, rcx
0x18006433d  jz      short loc_18006434C
0x18006433f  mov     rax, [rcx]
0x180064342  mov     rax, [rax+10h]
0x180064346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006434b  nop
0x18006434c  mov     rax, [r14+28h]
0x180064350  mov     rcx, [rax]
0x180064353  xorps   xmm1, xmm1
0x180064356  test    rcx, rcx
0x180064359  js      short loc_180064362
0x18006435b  cvtsi2sd xmm1, rcx
0x180064360  jmp     short loc_180064377
0x180064362  mov     rdx, rcx
0x180064365  shr     rdx, 1
0x180064368  and     ecx, 1
0x18006436b  or      rdx, rcx
0x18006436e  cvtsi2sd xmm1, rdx
0x180064373  addsd   xmm1, xmm1
0x180064377  lea     r8, [rbp+57h+var_90]
0x18006437b  mov     rcx, rbx
0x18006437e  mov     rax, rdi
0x180064381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064386  mov     ebx, eax
  ... truncated ...
```
