# RetryScheduler::AddTask(void)

- ea: `0x140010384`
- end: `0x140010da1`
- name: `?AddTask@RetryScheduler@@QEAAXXZ`
- size: `2589`
- prototype: `void __fastcall(RetryScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d2a4`

## callees

- `0x1400034f8`
- `0x14000b470`
- `0x14000b8f4`
- `0x140010098`
- `0x140010300`
- `0x140010384`
- `0x140012ebc`
- `0x140014010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x140010a87`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x140010a87`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x140010a7c`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x140010a7c`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1400103e8`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140010a97`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1400103e8`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140010a97`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x1400103d2`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x140010a3e`
- `msvcp_win!?setbase@std@@YA?AU?$_Smanip@H@1@H@Z` at `0x140010a57`
- `msvcp_win!?setbase@std@@YA?AU?$_Smanip@H@1@H@Z` at `0x140010a57`
- `OLEAUT32!__imp_SysAllocString` at `0x14001048a`
- `OLEAUT32!__imp_SysAllocString` at `0x14001048a`
- `OLEAUT32!__imp_VariantInit` at `0x14001093f`
- `OLEAUT32!__imp_VariantInit` at `0x140010953`
- `OLEAUT32!__imp_VariantInit` at `0x140010969`
- `OLEAUT32!__imp_VariantInit` at `0x14001093f`
- `OLEAUT32!__imp_VariantInit` at `0x140010953`
- `OLEAUT32!__imp_VariantInit` at `0x140010969`
- `OLEAUT32!__imp_VariantClear` at `0x1400104d9`
- `OLEAUT32!__imp_VariantClear` at `0x140010a1b`
- `OLEAUT32!__imp_VariantClear` at `0x140010a26`
- `OLEAUT32!__imp_VariantClear` at `0x140010a31`
- `OLEAUT32!__imp_VariantClear` at `0x1400104d9`
- `OLEAUT32!__imp_VariantClear` at `0x140010a1b`
- `OLEAUT32!__imp_VariantClear` at `0x140010a26`
- `OLEAUT32!__imp_VariantClear` at `0x140010a31`

## string_xrefs

- `0x14001088b`: `%WINDIR%\SYSTEM32\EduPrintProv.exe`
- `0x1400103cb`: `Retry task already exists, enabling it.`
- `0x140010a37`: `Tried to register Retry task, hr = `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall RetryScheduler::AddTask(RetryScheduler *this)
{
  __int64 v2; // rax
  int v3; // eax
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  __int64 *v9; // rbx
  __int64 v10; // rsi
  int v11; // ecx
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, __int64); // r14
  const unsigned __int16 *v17; // rbx
  const unsigned __int16 *v18; // rdx
  _bstr_t *v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, __int64); // r14
  _bstr_t *v29; // rax
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  __int64 (__fastcall *v34)(__int64, __int64, _QWORD); // r14
  int v35; // eax
  __int64 (__fastcall *v36)(_QWORD, GUID *, __int64 *); // r14
  int v37; // eax
  __int64 v38; // rsi
  __int64 (__fastcall *v39)(__int64, __int64); // r14
  _bstr_t *v40; // rax
  __int64 v41; // rdx
  int v42; // eax
  __int64 v43; // rax
  int v44; // eax
  __int64 v45; // rbx
  __int64 (__fastcall *v46)(__int64, _QWORD, _QWORD); // rsi
  __int64 (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rcx
  int v48; // eax
  __int64 (__fastcall ***v49)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v50)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // rbx
  __int64 (__fastcall *v54)(__int64, __int64); // rsi
  _bstr_t *v55; // rax
  __int64 v56; // rdx
  int v57; // eax
  __int64 v58; // rbx
  __int64 (__fastcall *v59)(__int64, __int64); // rsi
  _bstr_t *v60; // rax
  __int64 v61; // rdx
  int v62; // eax
  __int64 v63; // rbx
  __int64 (__fastcall *v64)(__int64, __int64, __int64 *, __int64); // r14
  __int128 v65; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v67; // xmm8
  IRecordInfo *v68; // xmm9_8
  __int128 v69; // xmm10
  IRecordInfo *v70; // xmm11_8
  __int64 *v71; // rsi
  const unsigned __int16 *v72; // rdx
  _bstr_t *v73; // rax
  __int64 v74; // rdx
  int v75; // edi
  __int64 v76; // rbx
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  int v80; // [rsp+28h] [rbp-E0h]
  __int64 v81; // [rsp+58h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v82)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-A0h] BYREF
  IRecordInfo *v84; // [rsp+80h] [rbp-88h]
  __int64 v85; // [rsp+88h] [rbp-80h] BYREF
  __int64 v86; // [rsp+90h] [rbp-78h] BYREF
  __int64 *v87; // [rsp+98h] [rbp-70h] BYREF
  __int64 v88; // [rsp+A0h] [rbp-68h]
  VARIANTARG v89; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v90; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v91; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v92; // [rsp+F8h] [rbp-10h]
  IRecordInfo *v93; // [rsp+108h] [rbp+0h]
  __int128 v94; // [rsp+118h] [rbp+10h]
  IRecordInfo *v95; // [rsp+128h] [rbp+20h]
  int v96[4]; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v97; // [rsp+148h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]
  __int64 *v99; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v100; // [rsp+200h] [rbp+F8h] BYREF
  __int64 v101; // [rsp+208h] [rbp+100h] BYREF
  __int64 (__fastcall ***v102)(_QWORD, GUID *, __int64 *); // [rsp+210h] [rbp+108h] BYREF

  if ( *((_QWORD *)this + 11) )
  {
    v2 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
           std::wcout,
           L"Retry task already exists, enabling it.");
    std::basic_ostream<unsigned short>::operator<<(v2, std::endl<unsigned short,std::char_traits<unsigned short>>);
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 11) + 88LL))(
           *((_QWORD *)this + 11),
           0xFFFFFFFFLL);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v3,
        v80);
  }
  else
  {
    v99 = 0;
    v4 = (__int64 *)*((_QWORD *)this + 9);
    v5 = *v4;
    v99 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v5 + 72))(v4, 0, &v99);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v6,
        v80);
    v87 = 0;
    v7 = *v99;
    v87 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v7 + 56))(v99, &v87);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v8,
        v80);
    v9 = v87;
    v10 = *v87;
    pvarg.iVal = 8;
    pvarg.pRecInfo = (IRecordInfo *)SysAllocString(L"D:(A;;FA;;;WD)");
    if ( !pvarg.pRecInfo )
      _com_issue_error(v11);
    *(_OWORD *)&v89.vt = *(_OWORD *)&pvarg.decVal.Lo32;
    v89.pRecInfo = v84;
    v12 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v10 + 176))(v9, &v89);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v12,
        v80);
    VariantClear((VARIANTARG *)&pvarg.decVal.8);
    *(_QWORD *)&pvarg.vt = 0;
    v13 = *v99;
    *(_QWORD *)&pvarg.vt = 0;
    v14 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v13 + 120))(v99, &pvarg);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v14,
        v80);
    v15 = *(_QWORD *)&pvarg.vt;
    v16 = *(__int64 (__fastcall **)(__int64, __int64))(**(_QWORD **)&pvarg.vt + 96LL);
    v17 = (const unsigned __int16 *)((char *)this + 8);
    if ( *((_QWORD *)this + 4) <= 7u )
      v18 = (const unsigned __int16 *)((char *)this + 8);
    else
      v18 = *(const unsigned __int16 **)v17;
    v19 = _bstr_t::_bstr_t((_bstr_t *)&pvarg.decVal.8, v18);
    if ( *(_QWORD *)v19 )
      v20 = **(_QWORD **)v19;
    else
      v20 = 0;
    v21 = v16(v15, v20);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v21,
        v80);
    _bstr_t::~_bstr_t((_bstr_t *)&pvarg.decVal.8);
    v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&pvarg.vt + 112LL))(*(_QWORD *)&pvarg.vt, 3);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v22,
        v80);
    v101 = 0;
    v23 = *v99;
    v101 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v23 + 88))(v99, &v101);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v24,
        v80);
    v25 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v101 + 176LL))(v101, 0xFFFFFFFFLL);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v25,
        v80);
    v26 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v101 + 112LL))(v101, 2);
    if ( v26 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v26,
        v80);
    v27 = v101;
    v28 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v101 + 224LL);
    v29 = _bstr_t::_bstr_t((_bstr_t *)&pvarg.decVal.8, L"PT5M");
    if ( *(_QWORD *)v29 )
      v30 = **(_QWORD **)v29;
    else
      v30 = 0;
    v31 = v28(v27, v30);
    if ( v31 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v31,
        v80);
    _bstr_t::~_bstr_t((_bstr_t *)&pvarg.decVal.8);
    v86 = 0;
    v82 = 0;
    v81 = 0;
    v32 = *v99;
    v86 = 0;
    v33 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v32 + 72))(v99, &v86);
    if ( v33 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v33,
        v80);
    v34 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v86 + 80LL);
    v82 = 0;
    v35 = v34(v86, 9, &v82);
    if ( v35 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v35,
        v80);
    v36 = **v82;
    v81 = 0;
    v37 = v36(v82, &IID_ILogonTrigger, &v81);
    if ( v37 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v37,
        v80);
    v38 = v81;
    v39 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 184LL);
    if ( *((_QWORD *)this + 4) > 7u )
      v17 = *(const unsigned __int16 **)v17;
    v40 = _bstr_t::_bstr_t((_bstr_t *)&pvarg.decVal.8, v17);
    if ( *(_QWORD *)v40 )
      v41 = **(_QWORD **)v40;
    else
      v41 = 0;
    v42 = v39(v38, v41);
    if ( v42 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v42,
        v80);
    _bstr_t::~_bstr_t((_bstr_t *)&pvarg.decVal.8);
    v85 = 0;
    v102 = 0;
    v100 = 0;
    v43 = *v99;
    v85 = 0;
    v44 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v43 + 136))(v99, &v85);
    if ( v44 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v44,
        v80);
    v45 = v85;
    v46 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v85 + 96LL);
    v47 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v102;
    v102 = 0;
    if ( v47 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v47)[2])(v47);
    v48 = v46(v45, 0, &v102);
    if ( v48 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v48,
        v80);
    v49 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v102;
    v50 = **v102;
    v51 = v100;
    v100 = 0;
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v52 = v50(v49, &IID_IExecAction, &v100);
    if ( v52 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v52,
        v80);
    v53 = v100;
    v54 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v100 + 88LL);
    v55 = _bstr_t::_bstr_t((_bstr_t *)&pvarg.decVal.8, L"%WINDIR%\\SYSTEM32\\EduPrintProv.exe");
    if ( *(_QWORD *)v55 )
      v56 = **(_QWORD **)v55;
    else
      v56 = 0;
    v57 = v54(v53, v56);
    if ( v57 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v57,
        v80);
    _bstr_t::~_bstr_t((_bstr_t *)&pvarg.decVal.8);
    v58 = v100;
    v59 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v100 + 104LL);
    v60 = _bstr_t::_bstr_t((_bstr_t *)&pvarg.decVal.8, L"-r");
    if ( *(_QWORD *)v60 )
      v61 = **(_QWORD **)v60;
    else
      v61 = 0;
    v62 = v59(v58, v61);
    if ( v62 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v62,
        v80);
    _bstr_t::~_bstr_t((_bstr_t *)&pvarg.decVal.8);
    v88 = 0;
    v63 = *((_QWORD *)this + 10);
    v64 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64))(*(_QWORD *)v63 + 136LL);
    v88 = 0;
    VariantInit(&v89);
    v65 = *(_OWORD *)&v89.vt;
    pRecInfo = v89.pRecInfo;
    VariantInit(&v91);
    v67 = *(_OWORD *)&v91.vt;
    v68 = v91.pRecInfo;
    VariantInit(&v90);
    v69 = *(_OWORD *)&v90.vt;
    v70 = v90.pRecInfo;
    v71 = v99;
    v72 = (const unsigned __int16 *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v72 = *(const unsigned __int16 **)v72;
    v73 = _bstr_t::_bstr_t((_bstr_t *)&pvarg.decVal.8, v72);
    if ( *(_QWORD *)v73 )
      v74 = **(_QWORD **)v73;
    else
      v74 = 0;
    v92 = v65;
    v93 = pRecInfo;
    v94 = v67;
    v95 = v68;
    *(_OWORD *)v96 = v69;
    v97 = v70;
    v75 = v64(v63, v74, v71, 6);
    _bstr_t::~_bstr_t((_bstr_t *)&pvarg.decVal.8);
    VariantClear(&v90);
    VariantClear(&v91);
    VariantClear(&v89);
    v76 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            std::wcout,
            L"Tried to register Retry task, hr = ");
    v77 = std::setbase(&pvarg.decVal.Lo32, 16);
    (*(void (__fastcall **)(__int64, _QWORD))v77)(v76 + *(int *)(*(_QWORD *)v76 + 4LL), *(unsigned int *)(v77 + 8));
    v78 = std::basic_ostream<unsigned short>::operator<<(v76, std::showbase);
    v79 = std::basic_ostream<unsigned short>::operator<<(v78, (unsigned int)v75);
    std::basic_ostream<unsigned short>::operator<<(v79, std::endl<unsigned short,std::char_traits<unsigned short>>);
    if ( v75 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\retryscheduler.cpp",
        (const char *)(unsigned int)v75,
        (int)v96);
    if ( v88 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    if ( v100 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
    if ( v102 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v102)[2])(v102);
    if ( v85 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    if ( v81 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    if ( v82 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v82)[2])(v82);
    if ( v86 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    if ( v101 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
    if ( *(_QWORD *)&pvarg.vt )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pvarg.vt + 16LL))(*(_QWORD *)&pvarg.vt);
    if ( v87 )
      (*(void (__fastcall **)(__int64 *))(*v87 + 16))(v87);
    if ( v99 )
      (*(void (__fastcall **)(__int64 *))(*v99 + 16))(v99);
  }
}

```

## disassembly

```asm
0x140010384  mov     rax, rsp
0x140010387  push    rbp
0x140010388  push    rbx
0x140010389  push    rsi
0x14001038a  push    rdi
0x14001038b  push    r14
0x14001038d  push    r15
0x14001038f  lea     rbp, [rax-0E8h]
0x140010396  sub     rsp, 1B8h
0x14001039d  movaps  xmmword ptr [rax-48h], xmm6
0x1400103a1  movaps  xmmword ptr [rax-58h], xmm7
0x1400103a5  movaps  xmmword ptr [rax-68h], xmm8
0x1400103aa  movaps  xmmword ptr [rax-78h], xmm9
0x1400103af  movaps  xmmword ptr [rax-88h], xmm10
0x1400103b7  movaps  xmmword ptr [rax-98h], xmm11
0x1400103bf  mov     rdi, rcx
0x1400103c2  xor     r15d, r15d
0x1400103c5  cmp     [rcx+58h], r15
0x1400103c9  jz      short loc_14001040E
0x1400103cb  lea     rdx, aRetryTaskAlrea; "Retry task already exists, enabling it."
0x1400103d2  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x1400103d9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400103de  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x1400103e5  mov     rcx, rax
0x1400103e8  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x1400103ee  mov     rcx, [rdi+58h]
0x1400103f2  mov     rax, [rcx]
0x1400103f5  or      edx, 0FFFFFFFFh
0x1400103f8  mov     rax, [rax+58h]
0x1400103fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010401  test    eax, eax
0x140010403  js      loc_140010C05
0x140010409  jmp     loc_140010BBE
0x14001040e  mov     [rbp+0E0h+arg_0], r15
0x140010415  mov     rcx, [rcx+48h]
0x140010419  mov     rax, [rcx]
0x14001041c  mov     [rbp+0E0h+arg_0], r15
0x140010423  lea     r8, [rbp+0E0h+arg_0]
0x14001042a  xor     edx, edx
0x14001042c  mov     rax, [rax+48h]
0x140010430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010435  mov     rcx, [rbp+0E8h]; this
0x14001043c  test    eax, eax
0x14001043e  js      loc_140010C21
0x140010444  mov     [rbp+0E0h+var_150], r15
0x140010448  mov     rcx, [rbp+0E0h+arg_0]
0x14001044f  mov     rax, [rcx]
0x140010452  mov     [rbp+0E0h+var_150], r15
0x140010456  lea     rdx, [rbp+0E0h+var_150]
0x14001045a  mov     rax, [rax+38h]
0x14001045e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010463  mov     rcx, [rbp+0E8h]; this
0x14001046a  test    eax, eax
0x14001046c  js      loc_140010C36
0x140010472  mov     rbx, [rbp+0E0h+var_150]
0x140010476  mov     rsi, [rbx]
0x140010479  mov     eax, 8
0x14001047e  mov     word ptr [rsp+1E0h+pvarg+8], ax
0x140010483  lea     rcx, psz; "D:(A;;FA;;;WD)"
0x14001048a  call    cs:__imp_SysAllocString
0x140010490  mov     qword ptr [rsp+1E0h+pvarg+10h], rax
0x140010495  test    rax, rax
0x140010498  jz      loc_140010C4B
0x14001049e  movups  xmm0, xmmword ptr [rsp+1E0h+pvarg+8]
0x1400104a3  movaps  xmmword ptr [rbp+0E0h+var_140], xmm0
0x1400104a7  movsd   xmm1, [rsp+1E0h+var_168]
0x1400104ad  movsd   qword ptr [rbp+0E0h+var_140+10h], xmm1
0x1400104b2  lea     rdx, [rbp+0E0h+var_140]
0x1400104b6  mov     rcx, rbx
0x1400104b9  mov     rax, [rsi+0B0h]
0x1400104c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104c5  mov     rcx, [rbp+0E8h]; this
0x1400104cc  test    eax, eax
0x1400104ce  js      loc_140010C51
0x1400104d4  lea     rcx, [rsp+1E0h+pvarg+8]; pvarg
0x1400104d9  call    cs:__imp_VariantClear
0x1400104df  mov     qword ptr [rsp+1E0h+pvarg], r15
0x1400104e4  mov     rcx, [rbp+0E0h+arg_0]
0x1400104eb  mov     rax, [rcx]
0x1400104ee  mov     qword ptr [rsp+1E0h+pvarg], r15
0x1400104f3  lea     rdx, [rsp+1E0h+pvarg]
0x1400104f8  mov     rax, [rax+78h]
0x1400104fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010501  mov     rcx, [rbp+0E8h]; this
0x140010508  test    eax, eax
0x14001050a  js      loc_140010C66
0x140010510  mov     rsi, qword ptr [rsp+1E0h+pvarg]
0x140010515  mov     rax, [rsi]
0x140010518  mov     r14, [rax+60h]
0x14001051c  lea     rbx, [rdi+8]
0x140010520  cmp     qword ptr [rbx+18h], 7
0x140010525  jbe     short loc_14001052C
0x140010527  mov     rdx, [rbx]
0x14001052a  jmp     short loc_14001052F
0x14001052c  mov     rdx, rbx; unsigned __int16 *
0x14001052f  lea     rcx, [rsp+1E0h+pvarg+8]; this
0x140010534  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140010539  nop
0x14001053a  mov     rdx, [rax]
0x14001053d  test    rdx, rdx
0x140010540  jz      short loc_140010547
0x140010542  mov     rdx, [rdx]
0x140010545  jmp     short loc_14001054A
0x140010547  mov     rdx, r15
0x14001054a  mov     rcx, rsi
0x14001054d  mov     rax, r14
0x140010550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010555  mov     rcx, [rbp+0E8h]; this
0x14001055c  test    eax, eax
0x14001055e  js      loc_140010C7B
0x140010564  lea     rcx, [rsp+1E0h+pvarg+8]; this
0x140010569  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001056e  mov     rcx, qword ptr [rsp+1E0h+pvarg]
0x140010573  mov     rax, [rcx]
0x140010576  mov     edx, 3
0x14001057b  mov     rax, [rax+70h]
0x14001057f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010584  mov     rcx, [rbp+0E8h]; this
0x14001058b  test    eax, eax
0x14001058d  js      loc_140010C90
0x140010593  mov     [rbp+0E0h+arg_10], r15
0x14001059a  mov     rcx, [rbp+0E0h+arg_0]
0x1400105a1  mov     rax, [rcx]
0x1400105a4  mov     [rbp+0E0h+arg_10], r15
0x1400105ab  lea     rdx, [rbp+0E0h+arg_10]
0x1400105b2  mov     rax, [rax+58h]
0x1400105b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400105bb  mov     rcx, [rbp+0E8h]; this
0x1400105c2  test    eax, eax
0x1400105c4  js      loc_140010CA5
0x1400105ca  mov     rcx, [rbp+0E0h+arg_10]
0x1400105d1  mov     rax, [rcx]
0x1400105d4  or      edx, 0FFFFFFFFh
0x1400105d7  mov     rax, [rax+0B0h]
0x1400105de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400105e3  mov     rcx, [rbp+0E8h]; this
0x1400105ea  test    eax, eax
0x1400105ec  js      loc_140010CBA
0x1400105f2  mov     rcx, [rbp+0E0h+arg_10]
0x1400105f9  mov     rax, [rcx]
0x1400105fc  mov     edx, 2
0x140010601  mov     rax, [rax+70h]
0x140010605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001060a  mov     rcx, [rbp+0E8h]; this
0x140010611  test    eax, eax
0x140010613  js      loc_140010CCF
0x140010619  mov     rsi, [rbp+0E0h+arg_10]
0x140010620  mov     rax, [rsi]
0x140010623  mov     r14, [rax+0E0h]
0x14001062a  lea     rdx, aPt5m; "PT5M"
0x140010631  lea     rcx, [rsp+1E0h+pvarg+8]; this
0x140010636  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001063b  nop
0x14001063c  mov     rdx, [rax]
0x14001063f  test    rdx, rdx
0x140010642  jz      short loc_140010649
0x140010644  mov     rdx, [rdx]
0x140010647  jmp     short loc_14001064C
0x140010649  mov     rdx, r15
0x14001064c  mov     rcx, rsi
0x14001064f  mov     rax, r14
0x140010652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010657  mov     rcx, [rbp+0E8h]; this
0x14001065e  test    eax, eax
0x140010660  js      loc_140010CE4
0x140010666  lea     rcx, [rsp+1E0h+pvarg+8]; this
0x14001066b  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x140010670  mov     [rbp+0E0h+var_158], r15
0x140010674  mov     [rsp+1E0h+var_188], r15
0x140010679  mov     [rsp+1E0h+var_190], r15
0x14001067e  mov     rcx, [rbp+0E0h+arg_0]
0x140010685  mov     rax, [rcx]
0x140010688  mov     [rbp+0E0h+var_158], r15
0x14001068c  lea     rdx, [rbp+0E0h+var_158]
0x140010690  mov     rax, [rax+48h]
0x140010694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010699  mov     rcx, [rbp+0E8h]; this
0x1400106a0  test    eax, eax
0x1400106a2  js      loc_140010CF9
0x1400106a8  mov     rsi, [rbp+0E0h+var_158]
0x1400106ac  mov     rax, [rsi]
0x1400106af  mov     r14, [rax+50h]
0x1400106b3  mov     rcx, [rsp+1E0h+var_188]
0x1400106b8  mov     [rsp+1E0h+var_188], r15
0x1400106bd  test    rcx, rcx
0x1400106c0  jz      short loc_1400106CF
0x1400106c2  mov     rdx, [rcx]
0x1400106c5  mov     rax, [rdx+10h]
0x1400106c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106ce  nop
0x1400106cf  lea     r8, [rsp+1E0h+var_188]
0x1400106d4  mov     edx, 9
0x1400106d9  mov     rcx, rsi
0x1400106dc  mov     rax, r14
0x1400106df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106e4  mov     rcx, [rbp+0E8h]; this
0x1400106eb  test    eax, eax
0x1400106ed  js      loc_140010D0E
0x1400106f3  mov     rsi, [rsp+1E0h+var_188]
0x1400106f8  mov     rax, [rsi]
0x1400106fb  mov     r14, [rax]
0x1400106fe  mov     rcx, [rsp+1E0h+var_190]
0x140010703  mov     [rsp+1E0h+var_190], r15
0x140010708  test    rcx, rcx
0x14001070b  jz      short loc_14001071A
0x14001070d  mov     rdx, [rcx]
0x140010710  mov     rax, [rdx+10h]
0x140010714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010719  nop
0x14001071a  lea     r8, [rsp+1E0h+var_190]
0x14001071f  lea     rdx, IID_ILogonTrigger
0x140010726  mov     rcx, rsi
0x140010729  mov     rax, r14
0x14001072c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010731  mov     rcx, [rbp+0E8h]; this
0x140010738  test    eax, eax
0x14001073a  js      loc_140010D23
0x140010740  mov     rsi, [rsp+1E0h+var_190]
0x140010745  mov     rax, [rsi]
0x140010748  mov     r14, [rax+0B8h]
0x14001074f  cmp     qword ptr [rbx+18h], 7
0x140010754  jbe     short loc_140010759
0x140010756  mov     rbx, [rbx]
0x140010759  mov     rdx, rbx; unsigned __int16 *
0x14001075c  lea     rcx, [rsp+1E0h+pvarg+8]; this
0x140010761  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140010766  nop
0x140010767  mov     rdx, [rax]
0x14001076a  test    rdx, rdx
0x14001076d  jz      short loc_140010774
0x14001076f  mov     rdx, [rdx]
0x140010772  jmp     short loc_140010777
0x140010774  mov     rdx, r15
0x140010777  mov     rcx, rsi
0x14001077a  mov     rax, r14
0x14001077d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010782  mov     rcx, [rbp+0E8h]; this
0x140010789  test    eax, eax
0x14001078b  js      loc_140010D38
0x140010791  lea     rcx, [rsp+1E0h+pvarg+8]; this
0x140010796  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001079b  mov     [rbp+0E0h+var_160], r15
0x14001079f  mov     [rbp+0E0h+arg_18], r15
0x1400107a6  mov     [rbp+0E0h+arg_8], r15
0x1400107ad  mov     rcx, [rbp+0E0h+arg_0]
0x1400107b4  mov     rax, [rcx]
0x1400107b7  mov     [rbp+0E0h+var_160], r15
0x1400107bb  lea     rdx, [rbp+0E0h+var_160]
0x1400107bf  mov     rax, [rax+88h]
0x1400107c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400107cb  mov     rcx, [rbp+0E8h]; this
0x1400107d2  test    eax, eax
0x1400107d4  js      loc_140010D4D
0x1400107da  mov     rbx, [rbp+0E0h+var_160]
0x1400107de  mov     rax, [rbx]
0x1400107e1  mov     rsi, [rax+60h]
0x1400107e5  mov     rcx, [rbp+0E0h+arg_18]
0x1400107ec  mov     [rbp+0E0h+arg_18], r15
0x1400107f3  test    rcx, rcx
0x1400107f6  jz      short loc_140010805
0x1400107f8  mov     rdx, [rcx]
0x1400107fb  mov     rax, [rdx+10h]
0x1400107ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010804  nop
0x140010805  lea     r8, [rbp+0E0h+arg_18]
0x14001080c  xor     edx, edx
0x14001080e  mov     rcx, rbx
0x140010811  mov     rax, rsi
0x140010814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010819  mov     rcx, [rbp+0E8h]; this
0x140010820  test    eax, eax
0x140010822  js      loc_140010D62
0x140010828  mov     rbx, [rbp+0E0h+arg_18]
0x14001082f  mov     rax, [rbx]
0x140010832  mov     rsi, [rax]
0x140010835  mov     rcx, [rbp+0E0h+arg_8]
0x14001083c  mov     [rbp+0E0h+arg_8], r15
0x140010843  test    rcx, rcx
0x140010846  jz      short loc_140010855
0x140010848  mov     rdx, [rcx]
0x14001084b  mov     rax, [rdx+10h]
0x14001084f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010854  nop
0x140010855  lea     r8, [rbp+0E0h+arg_8]
0x14001085c  lea     rdx, IID_IExecAction
0x140010863  mov     rcx, rbx
0x140010866  mov     rax, rsi
0x140010869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001086e  mov     rcx, [rbp+0E8h]; this
0x140010875  test    eax, eax
0x140010877  js      loc_140010D77
0x14001087d  mov     rbx, [rbp+0E0h+arg_8]
0x140010884  mov     rax, [rbx]
0x140010887  mov     rsi, [rax+58h]
0x14001088b  lea     rdx, aWindirSystem32; "%WINDIR%\\SYSTEM32\\EduPrintProv.exe"
0x140010892  lea     rcx, [rsp+1E0h+pvarg+8]; this
0x140010897  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001089c  nop
0x14001089d  mov     rdx, [rax]
0x1400108a0  test    rdx, rdx
  ... truncated ...
```
