# ComDeviceInfoFromCDPDeviceInfo_0

- ea: `0x1801b6e0c`
- end: `0x1801b7c04`
- name: `ComDeviceInfoFromCDPDeviceInfo_0`
- size: `3576`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1801a9eb0`

## callees

- `0x180013da0`
- `0x1800f6590`
- `0x1800fd420`
- `0x18018ddd8`
- `0x1801b6e0c`
- `0x1801b7c0c`
- `0x1801fc5e8`
- `0x1802c36e4`
- `0x1802c3750`
- `0x1802c37fc`
- `0x1802cf71c`
- `0x1802cffec`
- `0x1802d0160`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b70ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b73ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b75bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b75db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7917`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b70ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b73ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b75bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b75db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7917`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b703e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b71dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b73e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b703e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b71dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b73e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall ComDeviceInfoFromCDPDeviceInfo_0(__int64 a1, __int64 a2)
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
    v38 = ComResourceFromCDPResource_0(*((_QWORD *)v112 + j), &v36[40 * j]);
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
    v59 = ComApplicationFromCDPApplication_0(*((_QWORD *)v114 + k), &v57[24 * k]);
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
  v65 = CopyString_0(v64);
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
  v65 = CopyString_0(v73);
  if ( v65 < 0 )
  {
    v113 = 676;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v130,
    0);
  v74 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 72LL))(a1);
  v65 = CopyString_0(v74);
  if ( v65 < 0 )
  {
    v113 = 677;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v129,
    0);
  v75 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1);
  v65 = CopyString_0(v75);
  if ( v65 < 0 )
  {
    v113 = 678;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v128,
    0);
  v76 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 104LL))(a1);
  v65 = CopyString_0(v76);
  if ( v65 < 0 )
  {
    v113 = 679;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v127,
    0);
  v77 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 112LL))(a1);
  v65 = CopyString_0(v77);
  if ( v65 < 0 )
  {
    v113 = 680;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v126,
    0);
  v78 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 176LL))(a1);
  v65 = CopyString_0(v78);
  if ( v65 < 0 )
  {
    v113 = 681;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v125,
    0);
  v79 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 120LL))(a1);
  v65 = CopyString_0(v79);
  if ( v65 < 0 )
  {
    v113 = 682;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v124,
    0);
  v80 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 168LL))(a1);
  v65 = CopyString_0(v80);
  if ( v65 < 0 )
  {
    v113 = 683;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v123,
    0);
  v81 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 192LL))(a1);
  v65 = CopyString_0(v81);
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
    v83 = CopyString_0(v82);
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
    v83 = CopyString_0(v87);
    if ( v83 < 0 )
    {
      v113 = 690;
      goto LABEL_96;
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v120,
      0);
    v88 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v132[0] + 40LL))(v132[0]);
    v83 = CopyString_0(v88);
    if ( v83 < 0 )
    {
      v113 = 691;
      goto LABEL_96;
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v119,
      0);
    v89 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v132[0] + 48LL))(v132[0]);
    v83 = CopyString_0(v89);
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
0x1801b6e0c  mov     [rsp-8+arg_8], rbx
0x1801b6e11  push    rbp
0x1801b6e12  push    rsi
0x1801b6e13  push    rdi
0x1801b6e14  push    r12
0x1801b6e16  push    r13
0x1801b6e18  push    r14
0x1801b6e1a  push    r15
0x1801b6e1c  lea     rbp, [rsp-40h]
0x1801b6e21  sub     rsp, 140h
0x1801b6e28  mov     r14, rdx
0x1801b6e2b  mov     rbx, rcx
0x1801b6e2e  xor     r13d, r13d
0x1801b6e31  test    rcx, rcx
0x1801b6e34  jnz     short loc_1801B6E40
0x1801b6e36  mov     eax, 80070057h
0x1801b6e3b  jmp     loc_1801B7BE9
0x1801b6e40  test    r14, r14
0x1801b6e43  jnz     short loc_1801B6E4F
0x1801b6e45  mov     eax, 80004003h
0x1801b6e4a  jmp     loc_1801B7BE9
0x1801b6e4f  mov     rax, [rcx]
0x1801b6e52  mov     rax, [rax+30h]
0x1801b6e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6e5b  movzx   eax, ax
0x1801b6e5e  mov     [r14+1Ch], eax
0x1801b6e62  mov     rax, [rbx]
0x1801b6e65  mov     rcx, rbx
0x1801b6e68  mov     rax, [rax+38h]
0x1801b6e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6e71  movzx   eax, ax
0x1801b6e74  mov     [r14+20h], eax
0x1801b6e78  mov     rax, [rbx]
0x1801b6e7b  mov     rcx, rbx
0x1801b6e7e  mov     rax, [rax+40h]
0x1801b6e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6e87  mov     [r14+24h], eax
0x1801b6e8b  mov     [r14+18h], r13w
0x1801b6e90  mov     rax, [rbx]
0x1801b6e93  mov     rcx, rbx
0x1801b6e96  mov     rax, [rax+50h]
0x1801b6e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6e9f  movzx   eax, al
0x1801b6ea2  mov     [r14+30h], eax
0x1801b6ea6  mov     rax, [rbx]
0x1801b6ea9  mov     rcx, rbx
0x1801b6eac  mov     rax, [rax+58h]
0x1801b6eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6eb5  movzx   eax, al
0x1801b6eb8  mov     [r14+38h], eax
0x1801b6ebc  mov     [r14+60h], r13w
0x1801b6ec1  mov     rax, [rbx]
0x1801b6ec4  mov     rcx, rbx
0x1801b6ec7  mov     rax, [rax+0A0h]
0x1801b6ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6ed3  movzx   eax, al
0x1801b6ed6  mov     [r14+64h], eax
0x1801b6eda  mov     rax, [rbx]
0x1801b6edd  mov     rcx, rbx
0x1801b6ee0  mov     rax, [rax+0C8h]
0x1801b6ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6eec  movzx   eax, al
0x1801b6eef  mov     [r14+34h], eax
0x1801b6ef3  mov     rax, [rbx]
0x1801b6ef6  mov     rcx, rbx
0x1801b6ef9  mov     rax, [rax+0D8h]
0x1801b6f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6f05  mov     [r14+0B8h], eax
0x1801b6f0c  mov     rax, [rbx]
0x1801b6f0f  xor     r8d, r8d
0x1801b6f12  lea     r9, [rbp+70h+arg_18]
0x1801b6f19  xor     edx, edx
0x1801b6f1b  mov     rcx, rbx
0x1801b6f1e  mov     rax, [rax+28h]
0x1801b6f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6f27  test    eax, eax
0x1801b6f29  jns     short loc_1801B6F54
0x1801b6f2b  mov     [rsp+170h+var_140], eax
0x1801b6f2f  mov     [rsp+170h+var_128], 217h
0x1801b6f37  lea     rax, [rsp+170h+var_128]
0x1801b6f3c  mov     [rsp+170h+var_150], rax
0x1801b6f41  lea     r8, [rsp+170h+var_140]
0x1801b6f46  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x1801b6f4b  mov     eax, [rsp+170h+var_140]
0x1801b6f4f  jmp     loc_1801B7BE9
0x1801b6f54  mov     [rsp+170h+var_138], r13
0x1801b6f59  lea     rax, [rsp+170h+var_138]
0x1801b6f5e  mov     [rbp+70h+var_70], rax
0x1801b6f62  lea     rax, [rbp+70h+arg_18]
0x1801b6f69  mov     [rbp+70h+var_68], rax
0x1801b6f6d  lea     rax, [rbp+70h+var_70]
0x1801b6f71  mov     [rsp+170h+var_118], rax
0x1801b6f76  movzx   eax, [rbp+70h+arg_18]
0x1801b6f7d  test    ax, ax
0x1801b6f80  jz      loc_1801B7033
0x1801b6f86  mov     edx, eax
0x1801b6f88  lea     rcx, [rsp+170h+var_110]
0x1801b6f8d  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x1801b6f92  mov     rdx, rax
0x1801b6f95  lea     rcx, [rsp+170h+var_138]
0x1801b6f9a  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x1801b6f9f  mov     rcx, [rsp+170h+var_110]; void *
0x1801b6fa4  mov     [rsp+170h+var_110], r13
0x1801b6fa9  test    rcx, rcx
0x1801b6fac  jz      short loc_1801B6FB3
0x1801b6fae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b6fb3  mov     rdx, [rsp+170h+var_138]
0x1801b6fb8  test    rdx, rdx
0x1801b6fbb  jz      loc_1801B7BC5
0x1801b6fc1  mov     rax, [rbx]
0x1801b6fc4  lea     r9, [rbp+70h+arg_18]
0x1801b6fcb  movzx   r8d, [rbp+70h+arg_18]
0x1801b6fd3  mov     rcx, rbx
0x1801b6fd6  mov     rax, [rax+28h]
0x1801b6fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b6fdf  test    eax, eax
0x1801b6fe1  jns     short loc_1801B702C
0x1801b6fe3  mov     [rsp+170h+var_140], eax
0x1801b6fe7  mov     [rsp+170h+var_128], 22Ch
0x1801b6fef  lea     rax, [rsp+170h+var_128]
0x1801b6ff4  mov     [rsp+170h+var_150], rax
0x1801b6ff9  lea     r8, [rsp+170h+var_140]
0x1801b6ffe  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x1801b7003  nop
0x1801b7004  lea     rcx, [rsp+170h+var_118]
0x1801b7009  call    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb______ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___
0x1801b700e  nop
0x1801b700f  mov     rcx, [rsp+170h+var_138]; void *
0x1801b7014  mov     [rsp+170h+var_138], r13
0x1801b7019  test    rcx, rcx
0x1801b701c  jz      loc_1801B6F4B
0x1801b7022  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b7027  jmp     loc_1801B6F4B
0x1801b702c  movzx   eax, [rbp+70h+arg_18]
0x1801b7033  movzx   eax, ax
0x1801b7036  lea     rcx, [rax+rax*4]
0x1801b703a  shl     rcx, 3; cb
0x1801b703e  call    cs:__imp_CoTaskMemAlloc
0x1801b7044  mov     rdi, rax
0x1801b7047  mov     [rbp+70h+var_40], rax
0x1801b704b  test    rax, rax
0x1801b704e  jz      loc_1801B7BC5
0x1801b7054  mov     esi, r13d
0x1801b7057  mov     r12d, 1
0x1801b705d  movzx   ecx, [rbp+70h+arg_18]
0x1801b7064  cmp     esi, ecx
0x1801b7066  jge     short loc_1801B70B9
0x1801b7068  movsxd  r8, esi
0x1801b706b  lea     rax, [r8+r8*4]
0x1801b706f  lea     rdx, [rdi+rax*8]
0x1801b7073  mov     rcx, [rsp+170h+var_138]
0x1801b7078  mov     rcx, [rcx+r8*8]
0x1801b707c  call    ComEndpointFromCDPEndpoint
0x1801b7081  test    eax, eax
0x1801b7083  js      short loc_1801B708A
0x1801b7085  add     esi, r12d
0x1801b7088  jmp     short loc_1801B705D
0x1801b708a  mov     [rsp+170h+var_140], eax
0x1801b708e  mov     [rsp+170h+var_128], 23Dh
0x1801b7096  lea     rax, [rsp+170h+var_128]
0x1801b709b  mov     [rsp+170h+var_150], rax
0x1801b70a0  lea     r8, [rsp+170h+var_140]
0x1801b70a5  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x1801b70aa  nop
0x1801b70ab  mov     rcx, rdi; pv
0x1801b70ae  call    cs:__imp_CoTaskMemFree
0x1801b70b4  jmp     loc_1801B7004
0x1801b70b9  mov     [rsp+170h+var_130], r13
0x1801b70be  mov     [rbp+70h+arg_0], r13w
0x1801b70c6  mov     [rbp+70h+var_80], r13
0x1801b70ca  lea     rax, [rsp+170h+var_130]
0x1801b70cf  mov     [rbp+70h+var_60], rax
0x1801b70d3  lea     rax, [rbp+70h+arg_0]
0x1801b70da  mov     [rbp+70h+var_58], rax
0x1801b70de  lea     rax, [rbp+70h+var_60]
0x1801b70e2  mov     [rsp+170h+var_108], rax
0x1801b70e7  mov     rax, [rbx]
0x1801b70ea  xor     r8d, r8d
0x1801b70ed  lea     r9, [rbp+70h+arg_0]
0x1801b70f4  xor     edx, edx
0x1801b70f6  mov     rcx, rbx
0x1801b70f9  mov     rax, [rax+88h]
0x1801b7100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b7105  test    eax, eax
0x1801b7107  jns     short loc_1801B7152
0x1801b7109  mov     [rsp+170h+var_128], 250h
0x1801b7111  mov     [rsp+170h+var_140], eax
0x1801b7115  lea     rax, [rsp+170h+var_128]
0x1801b711a  mov     [rsp+170h+var_150], rax
0x1801b711f  lea     r8, [rsp+170h+var_140]
0x1801b7124  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x1801b7129  nop
0x1801b712a  lea     rcx, [rsp+170h+var_108]
0x1801b712f  call    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb______ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___
0x1801b7134  nop
0x1801b7135  mov     rcx, [rsp+170h+var_130]; void *
0x1801b713a  mov     [rsp+170h+var_130], r13
0x1801b713f  test    rcx, rcx
0x1801b7142  jz      loc_1801B70AB
0x1801b7148  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b714d  jmp     loc_1801B70AB
0x1801b7152  movzx   eax, [rbp+70h+arg_0]
0x1801b7159  test    ax, ax
0x1801b715c  jz      short loc_1801B71D2
0x1801b715e  mov     edx, eax
0x1801b7160  lea     rcx, [rsp+170h+var_110]
0x1801b7165  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x1801b716a  mov     rdx, rax
0x1801b716d  lea     rcx, [rsp+170h+var_130]
0x1801b7172  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x1801b7177  mov     rcx, [rsp+170h+var_110]; void *
0x1801b717c  mov     [rsp+170h+var_110], r13
0x1801b7181  test    rcx, rcx
0x1801b7184  jz      short loc_1801B718B
0x1801b7186  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b718b  mov     rdx, [rsp+170h+var_130]
0x1801b7190  test    rdx, rdx
0x1801b7193  jz      loc_1801B7224
0x1801b7199  mov     rax, [rbx]
0x1801b719c  lea     r9, [rbp+70h+arg_0]
0x1801b71a3  movzx   r8d, [rbp+70h+arg_0]
0x1801b71ab  mov     rcx, rbx
0x1801b71ae  mov     rax, [rax+88h]
0x1801b71b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b71ba  test    eax, eax
0x1801b71bc  jns     short loc_1801B71CB
0x1801b71be  mov     [rsp+170h+var_128], 256h
0x1801b71c6  jmp     loc_1801B7111
0x1801b71cb  movzx   eax, [rbp+70h+arg_0]
0x1801b71d2  movzx   eax, ax
0x1801b71d5  lea     rcx, [rax+rax*4]
0x1801b71d9  shl     rcx, 3; cb
0x1801b71dd  call    cs:__imp_CoTaskMemAlloc
0x1801b71e3  mov     rsi, rax
0x1801b71e6  mov     [rbp+70h+var_80], rax
0x1801b71ea  test    rax, rax
0x1801b71ed  jz      short loc_1801B7224
0x1801b71ef  mov     r15d, r13d
0x1801b71f2  cmp     r15w, [rbp+70h+arg_0]
0x1801b71fa  jnb     loc_1801B728C
0x1801b7200  movzx   r8d, r15w
0x1801b7204  lea     rdx, [r8+r8*4]
0x1801b7208  lea     rdx, [rsi+rdx*8]
0x1801b720c  mov     rcx, [rsp+170h+var_130]
0x1801b7211  mov     rcx, [rcx+r8*8]
0x1801b7215  call    ComResourceFromCDPResource_0
0x1801b721a  test    eax, eax
0x1801b721c  js      short loc_1801B7252
0x1801b721e  add     r15w, r12w
0x1801b7222  jmp     short loc_1801B71F2
0x1801b7224  lea     rcx, [rsp+170h+var_108]
0x1801b7229  call    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb______ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___
0x1801b722e  nop
0x1801b722f  mov     rcx, [rsp+170h+var_130]; void *
0x1801b7234  test    rcx, rcx
0x1801b7237  mov     [rsp+170h+var_130], r13
0x1801b723c  jz      short loc_1801B7244
0x1801b723e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b7243  nop
0x1801b7244  mov     rcx, rdi; pv
0x1801b7247  call    cs:__imp_CoTaskMemFree
0x1801b724d  jmp     loc_1801B7BC5
0x1801b7252  mov     [rsp+170h+var_140], eax
0x1801b7256  mov     [rsp+170h+var_128], 266h
0x1801b725e  lea     rax, [rsp+170h+var_128]
0x1801b7263  mov     [rsp+170h+var_150], rax
0x1801b7268  lea     r8, [rsp+170h+var_140]
0x1801b726d  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x1801b7272  nop
0x1801b7273  lea     rcx, [rsp+170h+var_108]
0x1801b7278  call    ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb______ScopeWarden__lambda_7a5e9bdd535b5df68b5bbadc1e623fcb___
0x1801b727d  nop
0x1801b727e  mov     rcx, rsi; pv
0x1801b7281  call    cs:__imp_CoTaskMemFree
0x1801b7287  jmp     loc_1801B7135
0x1801b728c  mov     [rsp+170h+var_120], r13
0x1801b7291  mov     [rbp+70h+arg_10], r13w
0x1801b7299  mov     [rbp+70h+var_78], r13
0x1801b729d  lea     rax, [rsp+170h+var_120]
0x1801b72a2  mov     [rbp+70h+var_50], rax
0x1801b72a6  lea     rax, [rbp+70h+arg_10]
0x1801b72ad  mov     [rbp+70h+var_48], rax
0x1801b72b1  lea     rax, [rbp+70h+var_50]
0x1801b72b5  mov     [rsp+170h+var_110], rax
0x1801b72ba  mov     rax, [rbx]
0x1801b72bd  xor     r8d, r8d
0x1801b72c0  lea     r9, [rbp+70h+arg_10]
0x1801b72c7  xor     edx, edx
0x1801b72c9  mov     rcx, rbx
0x1801b72cc  mov     rax, [rax+0B8h]
0x1801b72d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b72d8  cmp     eax, 8004010Dh
0x1801b72dd  jnz     loc_1801B73D5
0x1801b72e3  movzx   eax, [rbp+70h+arg_10]
0x1801b72ea  test    ax, ax
0x1801b72ed  jz      loc_1801B73DC
0x1801b72f3  mov     edx, eax
0x1801b72f5  lea     rcx, [rsp+170h+var_100]
0x1801b72fa  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x1801b72ff  mov     rdx, rax
  ... truncated ...
```
