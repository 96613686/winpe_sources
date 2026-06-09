# ComDeviceInfoFromCDPDeviceInfo

- ea: `0x1801b5fe8`
- end: `0x1801b6e04`
- name: `ComDeviceInfoFromCDPDeviceInfo`
- size: `3612`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1802c3a38`

## callees

- `0x180013da0`
- `0x1800ce6b8`
- `0x1800f6590`
- `0x1800fd420`
- `0x18018ddd8`
- `0x1801b5fe8`
- `0x1801b7c0c`
- `0x1801fc5e8`
- `0x1802c36e4`
- `0x1802c3750`
- `0x1802c37fc`
- `0x1802c38bc`
- `0x1802c3b98`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b628a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b6423`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b645d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b65a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b6635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b676e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b679a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b67b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b6b0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b628a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b6423`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b645d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b65a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b6635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b676e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b679a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b67b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b6b0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b621a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b63b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b65c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b621a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b63b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b65c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall ComDeviceInfoFromCDPDeviceInfo(__int64 a1, __int64 a2)
{
  __int64 v4; // r13
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  int v9; // r9d
  unsigned __int16 v10; // ax
  __int64 unique; // rax
  const struct std::nothrow_t *v12; // rdx
  void *v13; // rcx
  int v14; // eax
  int v15; // edx
  int v16; // ecx
  int v17; // r9d
  const struct std::nothrow_t *v18; // rdx
  void *v19; // rcx
  char *v20; // rdi
  int i; // esi
  int v22; // eax
  int v23; // edx
  int v24; // ecx
  int v25; // r9d
  int v26; // eax
  int v27; // edx
  int v28; // ecx
  int v29; // r9d
  const struct std::nothrow_t *v30; // rdx
  void *v31; // rcx
  unsigned __int16 v32; // ax
  __int64 v33; // rax
  const struct std::nothrow_t *v34; // rdx
  void *v35; // rcx
  char *v36; // rsi
  unsigned __int16 j; // r15
  int v38; // eax
  int v39; // edx
  int v40; // ecx
  int v41; // r9d
  const struct std::nothrow_t *v42; // rdx
  void *v43; // rcx
  bool v44; // zf
  unsigned __int16 v45; // ax
  __int64 v46; // rax
  const struct std::nothrow_t *v47; // rdx
  void *v48; // rcx
  int v49; // eax
  int v50; // edx
  int v51; // ecx
  int v52; // r9d
  const struct std::nothrow_t *v53; // rdx
  void *v54; // rcx
  const struct std::nothrow_t *v55; // rdx
  void *v56; // rcx
  char *v57; // r15
  unsigned __int16 k; // r12
  int v59; // eax
  int v60; // edx
  int v61; // ecx
  int v62; // r9d
  __int64 v63; // r12
  char *v64; // rax
  int v65; // eax
  int v66; // edx
  int v67; // ecx
  int v68; // r9d
  const struct std::nothrow_t *v69; // rdx
  void *v70; // rcx
  const struct std::nothrow_t *v71; // rdx
  void *v72; // rcx
  char *v73; // rax
  char *v74; // rax
  char *v75; // rax
  char *v76; // rax
  char *v77; // rax
  char *v78; // rax
  char *v79; // rax
  char *v80; // rax
  char *v81; // rax
  char *v82; // rax
  int v83; // eax
  int v84; // edx
  int v85; // ecx
  int v86; // r9d
  char *v87; // rax
  char *v88; // rax
  char *v89; // rax
  __int64 v90; // rcx
  __int64 v91; // rdx
  void *v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  const struct std::nothrow_t *v102; // rdx
  void *v103; // rcx
  const struct std::nothrow_t *v104; // rdx
  void *v105; // rcx
  const struct std::nothrow_t *v106; // rdx
  void *v107; // rcx
  const struct std::nothrow_t *v108; // rdx
  void *v109; // rcx
  unsigned int v110; // [rsp+30h] [rbp-D0h] BYREF
  void *v111; // [rsp+38h] [rbp-C8h] BYREF
  void *v112; // [rsp+40h] [rbp-C0h] BYREF
  int v113; // [rsp+48h] [rbp-B8h] BYREF
  void *v114; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v115; // [rsp+58h] [rbp-A8h] BYREF
  void *v116; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v117; // [rsp+68h] [rbp-98h] BYREF
  void *v118; // [rsp+70h] [rbp-90h] BYREF
  __int64 v119; // [rsp+78h] [rbp-88h] BYREF
  __int64 v120; // [rsp+80h] [rbp-80h] BYREF
  __int64 v121; // [rsp+88h] [rbp-78h] BYREF
  __int64 v122; // [rsp+90h] [rbp-70h] BYREF
  __int64 v123; // [rsp+98h] [rbp-68h] BYREF
  __int64 v124; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v125; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v126; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v127; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v128; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v129; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v130; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v131; // [rsp+D8h] [rbp-28h] BYREF
  std::_Ref_count_base *v132[2]; // [rsp+E0h] [rbp-20h] BYREF
  char *v133; // [rsp+F0h] [rbp-10h]
  char *v134; // [rsp+F8h] [rbp-8h]
  _QWORD v135[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v136[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v137[10]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v138; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v139; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v140; // [rsp+198h] [rbp+98h] BYREF

  v4 = 0;
  if ( !a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147500035LL;
  *(_DWORD *)(a2 + 28) = (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
  *(_DWORD *)(a2 + 32) = (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
  *(_DWORD *)(a2 + 36) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 64LL))(a1);
  *(_WORD *)(a2 + 24) = 0;
  *(_DWORD *)(a2 + 48) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 80LL))(a1);
  *(_DWORD *)(a2 + 56) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
  *(_WORD *)(a2 + 96) = 0;
  *(_DWORD *)(a2 + 100) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
  *(_DWORD *)(a2 + 52) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 200LL))(a1);
  *(_DWORD *)(a2 + 184) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 216LL))(a1);
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 40LL))(a1, 0, 0, &v140);
  if ( v6 < 0 )
  {
    v110 = v6;
    v113 = 535;
    Log<long &,char const (&)[64],int>(v8, v7, (unsigned int)&v110, v9, (__int64)&v113);
    return v110;
  }
  v111 = 0;
  v135[0] = &v111;
  v135[1] = &v140;
  v115 = v135;
  v10 = v140;
  if ( v140 )
  {
    unique = wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(&v116, v140);
    wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(
      &v111,
      unique);
    v13 = v116;
    v116 = 0;
    if ( v13 )
      operator delete(v13, v12);
    if ( !v111 )
      goto LABEL_116;
    v14 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 40LL))(
            a1,
            v111,
            v140,
            &v140);
    if ( v14 < 0 )
    {
      v110 = v14;
      v113 = 556;
      Log<long &,char const (&)[64],int>(v16, v15, (unsigned int)&v110, v17, (__int64)&v113);
LABEL_14:
      ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v115);
      v19 = v111;
      v111 = 0;
      goto LABEL_15;
    }
    v10 = v140;
  }
  v20 = (char *)CoTaskMemAlloc(40LL * v10);
  v137[2] = v20;
  if ( !v20 )
  {
LABEL_116:
    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v115);
    v109 = v111;
    v44 = v111 == 0;
    v111 = 0;
    if ( !v44 )
      operator delete(v109, v108);
    return 2147942414LL;
  }
  for ( i = 0; i < v140; ++i )
  {
    v22 = ComEndpointFromCDPEndpoint(*((_QWORD *)v111 + i), &v20[40 * i]);
    if ( v22 < 0 )
    {
      v110 = v22;
      v113 = 573;
      Log<long &,char const (&)[64],int>(v24, v23, (unsigned int)&v110, v25, (__int64)&v113);
LABEL_24:
      CoTaskMemFree(v20);
      goto LABEL_14;
    }
  }
  v112 = 0;
  v138 = 0;
  v133 = 0;
  v136[0] = &v112;
  v136[1] = &v138;
  v117 = v136;
  v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 136LL))(
          a1,
          0,
          0,
          &v138);
  if ( v26 < 0 )
  {
    v113 = 592;
    goto LABEL_27;
  }
  v32 = v138;
  if ( v138 )
  {
    v33 = wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(&v116, v138);
    wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(&v112, v33);
    v35 = v116;
    v116 = 0;
    if ( v35 )
      operator delete(v35, v34);
    if ( !v112 )
      goto LABEL_42;
    v26 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 136LL))(
            a1,
            v112,
            v138,
            &v138);
    if ( v26 < 0 )
    {
      v113 = 598;
LABEL_27:
      v110 = v26;
      Log<long &,char const (&)[64],int>(v28, v27, (unsigned int)&v110, v29, (__int64)&v113);
      ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v117);
LABEL_28:
      v31 = v112;
      v112 = 0;
      if ( v31 )
        operator delete(v31, v30);
      goto LABEL_24;
    }
    v32 = v138;
  }
  v36 = (char *)CoTaskMemAlloc(40LL * v32);
  v133 = v36;
  if ( !v36 )
  {
LABEL_42:
    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v117);
LABEL_43:
    v43 = v112;
    v44 = v112 == 0;
    v112 = 0;
    if ( !v44 )
      operator delete(v43, v42);
    CoTaskMemFree(v20);
    goto LABEL_116;
  }
  for ( j = 0; j < v138; ++j )
  {
    v38 = ComResourceFromCDPResource(*((_QWORD *)v112 + j), &v36[40 * j]);
    if ( v38 < 0 )
    {
      v110 = v38;
      v113 = 614;
      Log<long &,char const (&)[64],int>(v40, v39, (unsigned int)&v110, v41, (__int64)&v113);
LABEL_47:
      ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v117);
      CoTaskMemFree(v36);
      goto LABEL_28;
    }
  }
  v114 = 0;
  v139 = 0;
  v134 = 0;
  v137[0] = &v114;
  v137[1] = &v139;
  v116 = v137;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(
         a1,
         0,
         0,
         &v139) == -2147221235 )
  {
    v45 = v139;
    if ( !v139 )
      goto LABEL_61;
    v46 = wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(&v118, v139);
    wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(&v114, v46);
    v48 = v118;
    v118 = 0;
    if ( v48 )
      operator delete(v48, v47);
    if ( !v114 )
      goto LABEL_57;
    v49 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(
            a1,
            v114,
            v139,
            &v139);
    if ( v49 < 0 )
    {
      v110 = v49;
      v113 = 640;
      Log<long &,char const (&)[64],int>(v51, v50, (unsigned int)&v110, v52, (__int64)&v113);
      ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v116);
LABEL_55:
      v54 = v114;
      v114 = 0;
      if ( v54 )
        operator delete(v54, v53);
      goto LABEL_47;
    }
  }
  v45 = v139;
LABEL_61:
  v57 = (char *)CoTaskMemAlloc(24LL * v45);
  v134 = v57;
  if ( !v57 )
  {
LABEL_57:
    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v116);
    v56 = v114;
    v44 = v114 == 0;
    v114 = 0;
    if ( !v44 )
      operator delete(v56, v55);
    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v117);
    CoTaskMemFree(v36);
    goto LABEL_43;
  }
  for ( k = 0; k < v139; ++k )
  {
    v59 = ComApplicationFromCDPApplication(*((_QWORD *)v114 + k), &v57[24 * k]);
    if ( v59 < 0 )
    {
      v110 = v59;
      v113 = 657;
      Log<long &,char const (&)[64],int>(v61, v60, (unsigned int)&v110, v62, (__int64)&v113);
      ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v116);
      CoTaskMemFree(v57);
      goto LABEL_55;
    }
  }
  v118 = 0;
  v131 = 0;
  v130 = 0;
  v129 = 0;
  v128 = 0;
  v127 = 0;
  v126 = 0;
  v125 = 0;
  v124 = 0;
  v123 = 0;
  v63 = 0;
  v122 = 0;
  v121 = 0;
  v120 = 0;
  v119 = 0;
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v118,
    0);
  v64 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v65 = CopyString(v64);
  if ( v65 < 0 )
  {
    v113 = 675;
LABEL_69:
    v110 = v65;
    Log<long &,char const (&)[64],int>(v67, v66, (unsigned int)&v110, v68, (__int64)&v113);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v119);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v120);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v121);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v122);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v123);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v124);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v125);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v126);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v127);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v128);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v129);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v130);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v131);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v118);
    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v116);
    CoTaskMemFree(v57);
LABEL_70:
    v70 = v114;
    v114 = 0;
    if ( v70 )
      operator delete(v70, v69);
    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v117);
    CoTaskMemFree(v36);
    v72 = v112;
    v44 = v112 == 0;
    v112 = 0;
    if ( !v44 )
      operator delete(v72, v71);
    CoTaskMemFree(v20);
    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v115);
    v19 = v111;
    v111 = 0;
LABEL_15:
    if ( v19 )
      operator delete(v19, v18);
    return v110;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v131,
    0);
  v73 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  v65 = CopyString(v73);
  if ( v65 < 0 )
  {
    v113 = 676;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v130,
    0);
  v74 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 72LL))(a1);
  v65 = CopyString(v74);
  if ( v65 < 0 )
  {
    v113 = 677;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v129,
    0);
  v75 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1);
  v65 = CopyString(v75);
  if ( v65 < 0 )
  {
    v113 = 678;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v128,
    0);
  v76 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 104LL))(a1);
  v65 = CopyString(v76);
  if ( v65 < 0 )
  {
    v113 = 679;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v127,
    0);
  v77 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 112LL))(a1);
  v65 = CopyString(v77);
  if ( v65 < 0 )
  {
    v113 = 680;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v126,
    0);
  v78 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 176LL))(a1);
  v65 = CopyString(v78);
  if ( v65 < 0 )
  {
    v113 = 681;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v125,
    0);
  v79 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 120LL))(a1);
  v65 = CopyString(v79);
  if ( v65 < 0 )
  {
    v113 = 682;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v124,
    0);
  v80 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 168LL))(a1);
  v65 = CopyString(v80);
  if ( v65 < 0 )
  {
    v113 = 683;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v123,
    0);
  v81 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 192LL))(a1);
  v65 = CopyString(v81);
  if ( v65 < 0 )
  {
    v113 = 684;
    goto LABEL_69;
  }
  *(_OWORD *)v132 = 0;
  if ( (*(int (__fastcall **)(__int64, std::_Ref_count_base **))(*(_QWORD *)a1 + 208LL))(a1, v132) < 0 )
  {
    v90 = 0;
    v91 = 0;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v122,
      0);
    v82 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v132[0] + 24LL))(v132[0]);
    v83 = CopyString(v82);
    if ( v83 < 0 )
    {
      v113 = 689;
LABEL_96:
      v110 = v83;
      Log<long &,char const (&)[64],int>(v85, v84, (unsigned int)&v110, v86, (__int64)&v113);
      if ( v132[1] )
        std::_Ref_count_base::_Decref(v132[1]);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v119);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v120);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v121);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v122);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v123);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v124);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v125);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v126);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v127);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v128);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v129);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v130);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v131);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v118);
      ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v116);
      CoTaskMemFree(v57);
      goto LABEL_70;
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v121,
      0);
    v87 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v132[0] + 32LL))(v132[0]);
    v83 = CopyString(v87);
    if ( v83 < 0 )
    {
      v113 = 690;
      goto LABEL_96;
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v120,
      0);
    v88 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v132[0] + 40LL))(v132[0]);
    v83 = CopyString(v88);
    if ( v83 < 0 )
    {
      v113 = 691;
      goto LABEL_96;
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v119,
      0);
    v89 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v132[0] + 48LL))(v132[0]);
    v83 = CopyString(v89);
    if ( v83 < 0 )
    {
      v113 = 692;
      goto LABEL_96;
    }
    v63 = v122;
    v4 = v121;
    v90 = v120;
    v91 = v119;
  }
  v92 = v118;
  v118 = 0;
  *(_QWORD *)a2 = v92;
  v93 = v131;
  v131 = 0;
  *(_QWORD *)(a2 + 8) = v93;
  v94 = v130;
  v130 = 0;
  *(_QWORD *)(a2 + 40) = v94;
  v95 = v129;
  v129 = 0;
  *(_QWORD *)(a2 + 64) = v95;
  v96 = v128;
  v128 = 0;
  *(_QWORD *)(a2 + 72) = v96;
  v97 = v127;
  v127 = 0;
  *(_QWORD *)(a2 + 104) = v97;
  v98 = v126;
  v126 = 0;
  *(_QWORD *)(a2 + 120) = v98;
  v99 = v125;
  v125 = 0;
  *(_QWORD *)(a2 + 80) = v99;
  v100 = v124;
  v124 = 0;
  *(_QWORD *)(a2 + 112) = v100;
  v122 = 0;
  *(_QWORD *)(a2 + 160) = v63;
  v121 = 0;
  *(_QWORD *)(a2 + 168) = v4;
  v120 = 0;
  *(_QWORD *)(a2 + 152) = v90;
  v119 = 0;
  *(_QWORD *)(a2 + 176) = v91;
  *(_QWORD *)(a2 + 16) = v20;
  *(_WORD *)(a2 + 24) = v140;
  *(_QWORD *)(a2 + 88) = v36;
  *(_WORD *)(a2 + 96) = v138;
  *(_QWORD *)(a2 + 128) = v57;
  *(_WORD *)(a2 + 136) = v139;
  v101 = v123;
  v123 = 0;
  *(_QWORD *)(a2 + 144) = v101;
  if ( v132[1] )
    std::_Ref_count_base::_Decref(v132[1]);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v119);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v120);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v121);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v122);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v123);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v124);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v125);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v126);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v127);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v128);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v129);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v130);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v131);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v118);
  ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v116);
  v103 = v114;
  v114 = 0;
  if ( v103 )
    operator delete(v103, v102);
  ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v117);
  v105 = v112;
  v112 = 0;
  if ( v105 )
    operator delete(v105, v104);
  ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___::_ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___(&v115);
  v107 = v111;
  v111 = 0;
  if ( v107 )
    operator delete(v107, v106);
  return 0;
}

```

## disassembly

```asm
0x1801b5fe8  mov     [rsp-8+arg_8], rbx
0x1801b5fed  push    rbp
0x1801b5fee  push    rsi
0x1801b5fef  push    rdi
0x1801b5ff0  push    r12
0x1801b5ff2  push    r13
0x1801b5ff4  push    r14
0x1801b5ff6  push    r15
0x1801b5ff8  lea     rbp, [rsp-40h]
0x1801b5ffd  sub     rsp, 140h
0x1801b6004  mov     r14, rdx
0x1801b6007  mov     rbx, rcx
0x1801b600a  xor     r13d, r13d
0x1801b600d  test    rcx, rcx
0x1801b6010  jnz     short loc_1801B601C
0x1801b6012  mov     eax, 80070057h
0x1801b6017  jmp     loc_1801B6DE9
0x1801b601c  test    r14, r14
0x1801b601f  jnz     short loc_1801B602B
0x1801b6021  mov     eax, 80004003h
0x1801b6026  jmp     loc_1801B6DE9
0x1801b602b  mov     rax, [rcx]
0x1801b602e  mov     rax, [rax+30h]
0x1801b6032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6037  movzx   eax, ax
0x1801b603a  mov     [r14+1Ch], eax
0x1801b603e  mov     rax, [rbx]
0x1801b6041  mov     rcx, rbx
0x1801b6044  mov     rax, [rax+38h]
0x1801b6048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b604d  movzx   eax, ax
0x1801b6050  mov     [r14+20h], eax
0x1801b6054  mov     rax, [rbx]
0x1801b6057  mov     rcx, rbx
0x1801b605a  mov     rax, [rax+40h]
0x1801b605e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6063  mov     [r14+24h], eax
0x1801b6067  mov     [r14+18h], r13w
0x1801b606c  mov     rax, [rbx]
0x1801b606f  mov     rcx, rbx
0x1801b6072  mov     rax, [rax+50h]
0x1801b6076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b607b  movzx   eax, al
0x1801b607e  mov     [r14+30h], eax
0x1801b6082  mov     rax, [rbx]
0x1801b6085  mov     rcx, rbx
0x1801b6088  mov     rax, [rax+58h]
0x1801b608c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6091  movzx   eax, al
0x1801b6094  mov     [r14+38h], eax
0x1801b6098  mov     [r14+60h], r13w
0x1801b609d  mov     rax, [rbx]
0x1801b60a0  mov     rcx, rbx
0x1801b60a3  mov     rax, [rax+0A0h]
0x1801b60aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b60af  movzx   eax, al
0x1801b60b2  mov     [r14+64h], eax
0x1801b60b6  mov     rax, [rbx]
0x1801b60b9  mov     rcx, rbx
0x1801b60bc  mov     rax, [rax+0C8h]
0x1801b60c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b60c8  movzx   eax, al
0x1801b60cb  mov     [r14+34h], eax
0x1801b60cf  mov     rax, [rbx]
0x1801b60d2  mov     rcx, rbx
0x1801b60d5  mov     rax, [rax+0D8h]
0x1801b60dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b60e1  mov     [r14+0B8h], eax
0x1801b60e8  mov     rax, [rbx]
0x1801b60eb  xor     r8d, r8d
0x1801b60ee  lea     r9, [rbp+70h+arg_18]
0x1801b60f5  xor     edx, edx
0x1801b60f7  mov     rcx, rbx
0x1801b60fa  mov     rax, [rax+28h]
0x1801b60fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6103  test    eax, eax
0x1801b6105  jns     short loc_1801B6130
0x1801b6107  mov     [rsp+170h+var_140], eax
0x1801b610b  mov     [rsp+170h+var_128], 217h
0x1801b6113  lea     rax, [rsp+170h+var_128]
0x1801b6118  mov     [rsp+170h+var_150], rax
0x1801b611d  lea     r8, [rsp+170h+var_140]
0x1801b6122  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x1801b6127  mov     eax, [rsp+170h+var_140]
0x1801b612b  jmp     loc_1801B6DE9
0x1801b6130  mov     [rsp+170h+var_138], r13
0x1801b6135  lea     rax, [rsp+170h+var_138]
0x1801b613a  mov     [rbp+70h+var_70], rax
0x1801b613e  lea     rax, [rbp+70h+arg_18]
0x1801b6145  mov     [rbp+70h+var_68], rax
0x1801b6149  lea     rax, [rbp+70h+var_70]
0x1801b614d  mov     [rsp+170h+var_118], rax
0x1801b6152  movzx   eax, [rbp+70h+arg_18]
0x1801b6159  test    ax, ax
0x1801b615c  jz      loc_1801B620F
0x1801b6162  mov     edx, eax
0x1801b6164  lea     rcx, [rsp+170h+var_110]
0x1801b6169  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x1801b616e  mov     rdx, rax
0x1801b6171  lea     rcx, [rsp+170h+var_138]
0x1801b6176  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x1801b617b  mov     rcx, [rsp+170h+var_110]; void *
0x1801b6180  mov     [rsp+170h+var_110], r13
0x1801b6185  test    rcx, rcx
0x1801b6188  jz      short loc_1801B618F
0x1801b618a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b618f  mov     rdx, [rsp+170h+var_138]
0x1801b6194  test    rdx, rdx
0x1801b6197  jz      loc_1801B6DC5
0x1801b619d  mov     rax, [rbx]
0x1801b61a0  lea     r9, [rbp+70h+arg_18]
0x1801b61a7  movzx   r8d, [rbp+70h+arg_18]
0x1801b61af  mov     rcx, rbx
0x1801b61b2  mov     rax, [rax+28h]
0x1801b61b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b61bb  test    eax, eax
0x1801b61bd  jns     short loc_1801B6208
0x1801b61bf  mov     [rsp+170h+var_140], eax
0x1801b61c3  mov     [rsp+170h+var_128], 22Ch
0x1801b61cb  lea     rax, [rsp+170h+var_128]
0x1801b61d0  mov     [rsp+170h+var_150], rax
0x1801b61d5  lea     r8, [rsp+170h+var_140]
0x1801b61da  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x1801b61df  nop
0x1801b61e0  lea     rcx, [rsp+170h+var_118]
0x1801b61e5  call    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb______ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___
0x1801b61ea  nop
0x1801b61eb  mov     rcx, [rsp+170h+var_138]; void *
0x1801b61f0  mov     [rsp+170h+var_138], r13
0x1801b61f5  test    rcx, rcx
0x1801b61f8  jz      loc_1801B6127
0x1801b61fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b6203  jmp     loc_1801B6127
0x1801b6208  movzx   eax, [rbp+70h+arg_18]
0x1801b620f  movzx   eax, ax
0x1801b6212  lea     rcx, [rax+rax*4]
0x1801b6216  shl     rcx, 3; cb
0x1801b621a  call    cs:__imp_CoTaskMemAlloc
0x1801b6220  mov     rdi, rax
0x1801b6223  mov     [rbp+70h+var_40], rax
0x1801b6227  test    rax, rax
0x1801b622a  jz      loc_1801B6DC5
0x1801b6230  mov     esi, r13d
0x1801b6233  mov     r12d, 1
0x1801b6239  movzx   ecx, [rbp+70h+arg_18]
0x1801b6240  cmp     esi, ecx
0x1801b6242  jge     short loc_1801B6295
0x1801b6244  movsxd  r8, esi
0x1801b6247  lea     rax, [r8+r8*4]
0x1801b624b  lea     rdx, [rdi+rax*8]
0x1801b624f  mov     rcx, [rsp+170h+var_138]
0x1801b6254  mov     rcx, [rcx+r8*8]
0x1801b6258  call    ComEndpointFromCDPEndpoint
0x1801b625d  test    eax, eax
0x1801b625f  js      short loc_1801B6266
0x1801b6261  add     esi, r12d
0x1801b6264  jmp     short loc_1801B6239
0x1801b6266  mov     [rsp+170h+var_140], eax
0x1801b626a  mov     [rsp+170h+var_128], 23Dh
0x1801b6272  lea     rax, [rsp+170h+var_128]
0x1801b6277  mov     [rsp+170h+var_150], rax
0x1801b627c  lea     r8, [rsp+170h+var_140]
0x1801b6281  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x1801b6286  nop
0x1801b6287  mov     rcx, rdi; pv
0x1801b628a  call    cs:__imp_CoTaskMemFree
0x1801b6290  jmp     loc_1801B61E0
0x1801b6295  mov     [rsp+170h+var_130], r13
0x1801b629a  mov     [rbp+70h+arg_0], r13w
0x1801b62a2  mov     [rbp+70h+var_80], r13
0x1801b62a6  lea     rax, [rsp+170h+var_130]
0x1801b62ab  mov     [rbp+70h+var_60], rax
0x1801b62af  lea     rax, [rbp+70h+arg_0]
0x1801b62b6  mov     [rbp+70h+var_58], rax
0x1801b62ba  lea     rax, [rbp+70h+var_60]
0x1801b62be  mov     [rsp+170h+var_108], rax
0x1801b62c3  mov     rax, [rbx]
0x1801b62c6  xor     r8d, r8d
0x1801b62c9  lea     r9, [rbp+70h+arg_0]
0x1801b62d0  xor     edx, edx
0x1801b62d2  mov     rcx, rbx
0x1801b62d5  mov     rax, [rax+88h]
0x1801b62dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b62e1  test    eax, eax
0x1801b62e3  jns     short loc_1801B632E
0x1801b62e5  mov     [rsp+170h+var_128], 250h
0x1801b62ed  mov     [rsp+170h+var_140], eax
0x1801b62f1  lea     rax, [rsp+170h+var_128]
0x1801b62f6  mov     [rsp+170h+var_150], rax
0x1801b62fb  lea     r8, [rsp+170h+var_140]
0x1801b6300  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x1801b6305  nop
0x1801b6306  lea     rcx, [rsp+170h+var_108]
0x1801b630b  call    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb______ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___
0x1801b6310  nop
0x1801b6311  mov     rcx, [rsp+170h+var_130]; void *
0x1801b6316  mov     [rsp+170h+var_130], r13
0x1801b631b  test    rcx, rcx
0x1801b631e  jz      loc_1801B6287
0x1801b6324  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b6329  jmp     loc_1801B6287
0x1801b632e  movzx   eax, [rbp+70h+arg_0]
0x1801b6335  test    ax, ax
0x1801b6338  jz      short loc_1801B63AE
0x1801b633a  mov     edx, eax
0x1801b633c  lea     rcx, [rsp+170h+var_110]
0x1801b6341  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x1801b6346  mov     rdx, rax
0x1801b6349  lea     rcx, [rsp+170h+var_130]
0x1801b634e  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x1801b6353  mov     rcx, [rsp+170h+var_110]; void *
0x1801b6358  mov     [rsp+170h+var_110], r13
0x1801b635d  test    rcx, rcx
0x1801b6360  jz      short loc_1801B6367
0x1801b6362  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b6367  mov     rdx, [rsp+170h+var_130]
0x1801b636c  test    rdx, rdx
0x1801b636f  jz      loc_1801B6400
0x1801b6375  mov     rax, [rbx]
0x1801b6378  lea     r9, [rbp+70h+arg_0]
0x1801b637f  movzx   r8d, [rbp+70h+arg_0]
0x1801b6387  mov     rcx, rbx
0x1801b638a  mov     rax, [rax+88h]
0x1801b6391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6396  test    eax, eax
0x1801b6398  jns     short loc_1801B63A7
0x1801b639a  mov     [rsp+170h+var_128], 256h
0x1801b63a2  jmp     loc_1801B62ED
0x1801b63a7  movzx   eax, [rbp+70h+arg_0]
0x1801b63ae  movzx   eax, ax
0x1801b63b1  lea     rcx, [rax+rax*4]
0x1801b63b5  shl     rcx, 3; cb
0x1801b63b9  call    cs:__imp_CoTaskMemAlloc
0x1801b63bf  mov     rsi, rax
0x1801b63c2  mov     [rbp+70h+var_80], rax
0x1801b63c6  test    rax, rax
0x1801b63c9  jz      short loc_1801B6400
0x1801b63cb  mov     r15d, r13d
0x1801b63ce  cmp     r15w, [rbp+70h+arg_0]
0x1801b63d6  jnb     loc_1801B6468
0x1801b63dc  movzx   r8d, r15w
0x1801b63e0  lea     rdx, [r8+r8*4]
0x1801b63e4  lea     rdx, [rsi+rdx*8]
0x1801b63e8  mov     rcx, [rsp+170h+var_130]
0x1801b63ed  mov     rcx, [rcx+r8*8]
0x1801b63f1  call    ComResourceFromCDPResource
0x1801b63f6  test    eax, eax
0x1801b63f8  js      short loc_1801B642E
0x1801b63fa  add     r15w, r12w
0x1801b63fe  jmp     short loc_1801B63CE
0x1801b6400  lea     rcx, [rsp+170h+var_108]
0x1801b6405  call    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb______ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___
0x1801b640a  nop
0x1801b640b  mov     rcx, [rsp+170h+var_130]; void *
0x1801b6410  test    rcx, rcx
0x1801b6413  mov     [rsp+170h+var_130], r13
0x1801b6418  jz      short loc_1801B6420
0x1801b641a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b641f  nop
0x1801b6420  mov     rcx, rdi; pv
0x1801b6423  call    cs:__imp_CoTaskMemFree
0x1801b6429  jmp     loc_1801B6DC5
0x1801b642e  mov     [rsp+170h+var_140], eax
0x1801b6432  mov     [rsp+170h+var_128], 266h
0x1801b643a  lea     rax, [rsp+170h+var_128]
0x1801b643f  mov     [rsp+170h+var_150], rax
0x1801b6444  lea     r8, [rsp+170h+var_140]
0x1801b6449  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x1801b644e  nop
0x1801b644f  lea     rcx, [rsp+170h+var_108]
0x1801b6454  call    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb______ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___
0x1801b6459  nop
0x1801b645a  mov     rcx, rsi; pv
0x1801b645d  call    cs:__imp_CoTaskMemFree
0x1801b6463  jmp     loc_1801B6311
0x1801b6468  mov     [rsp+170h+var_120], r13
0x1801b646d  mov     [rbp+70h+arg_10], r13w
0x1801b6475  mov     [rbp+70h+var_78], r13
0x1801b6479  lea     rax, [rsp+170h+var_120]
0x1801b647e  mov     [rbp+70h+var_50], rax
0x1801b6482  lea     rax, [rbp+70h+arg_10]
0x1801b6489  mov     [rbp+70h+var_48], rax
0x1801b648d  lea     rax, [rbp+70h+var_50]
0x1801b6491  mov     [rsp+170h+var_110], rax
0x1801b6496  mov     rax, [rbx]
0x1801b6499  xor     r8d, r8d
0x1801b649c  lea     r9, [rbp+70h+arg_10]
0x1801b64a3  xor     edx, edx
0x1801b64a5  mov     rcx, rbx
0x1801b64a8  mov     rax, [rax+0B8h]
0x1801b64af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b64b4  cmp     eax, 8004010Dh
0x1801b64b9  jnz     loc_1801B65B1
0x1801b64bf  movzx   eax, [rbp+70h+arg_10]
0x1801b64c6  test    ax, ax
0x1801b64c9  jz      loc_1801B65B8
0x1801b64cf  mov     edx, eax
0x1801b64d1  lea     rcx, [rsp+170h+var_100]
0x1801b64d6  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x1801b64db  mov     rdx, rax
  ... truncated ...
```
