# CreateTaskInFolder(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)

- ea: `0x1800d935c`
- end: `0x1800da47f`
- name: `?CreateTaskInFolder@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG4444W4_TASK_RUNLEVEL@@HHHH@Z`
- size: `4387`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800dc440`

## callees

- `0x1800091b0`
- `0x18001a4fc`
- `0x18001aa94`
- `0x18002ec0c`
- `0x180039900`
- `0x180039928`
- `0x180039950`
- `0x1800459a8`
- `0x1800637f4`
- `0x180063870`
- `0x1800639d0`
- `0x1800d7230`
- `0x1800d7300`
- `0x1800d7d5c`
- `0x1800d935c`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9446`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d946a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d9446`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d946a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d97d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d98a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d997a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9a63`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9b3f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9c6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9d9e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9f3e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800da001`
- `OLEAUT32!__imp_SysFreeString` at `0x1800da0a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800da2ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800da38b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d97d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d98a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d997a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9a63`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9b3f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9c6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9d9e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d9f3e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800da001`
- `OLEAUT32!__imp_SysFreeString` at `0x1800da0a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800da2ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800da38b`
- `OLEAUT32!__imp_VariantInit` at `0x1800d9670`
- `OLEAUT32!__imp_VariantInit` at `0x1800d968b`
- `OLEAUT32!__imp_VariantInit` at `0x1800d96a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800d96c0`
- `OLEAUT32!__imp_VariantInit` at `0x1800d9670`
- `OLEAUT32!__imp_VariantInit` at `0x1800d968b`
- `OLEAUT32!__imp_VariantInit` at `0x1800d96a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800d96c0`
- `OLEAUT32!__imp_VariantClear` at `0x1800d99b2`
- `OLEAUT32!__imp_VariantClear` at `0x1800d9b77`
- `OLEAUT32!__imp_VariantClear` at `0x1800d99b2`
- `OLEAUT32!__imp_VariantClear` at `0x1800d9b77`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800d9640`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800d9640`

## string_xrefs

- `0x1800d9614`: `22CoCreateTaskScheduler2`
- `0x1800da28e`: `%windir%\system32\deviceenroller.exe `
- `0x1800d95f8`: `CreateTaskInFolder`

## pseudocode

```c
__int64 CreateTaskInFolder(LPVOID *a1, struct IUnknown **a2, _QWORD *a3, _QWORD *a4, unsigned __int16 *a5, ...)
{
  _QWORD *v6; // r14
  char *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  const wchar_t *v12; // rdx
  const WCHAR *v13; // r8
  unsigned int v14; // ebx
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v17; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v19; // xmm8
  IRecordInfo *v20; // xmm9_8
  __int128 v21; // xmm6
  IRecordInfo *v22; // xmm7_8
  LPVOID v23; // rbx
  __int64 (__fastcall *v24)(LPVOID, __int64, VARIANTARG *); // rdi
  _bstr_t *v25; // rax
  __int64 v26; // rdx
  int v27; // eax
  BSTR *v28; // rbx
  int v29; // edi
  BSTR v30; // rcx
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, _QWORD *, struct IUnknown **); // rdi
  _QWORD *v33; // rdx
  int v34; // eax
  BSTR *v35; // rbx
  BSTR v36; // rcx
  __int64 v37; // rbx
  __int64 (__fastcall *v38)(__int64, _QWORD *, __int128 *, struct IUnknown **); // rdi
  __int128 v39; // xmm6
  __int64 v40; // xmm7_8
  _QWORD *v41; // rdx
  int v42; // eax
  BSTR *v43; // rbx
  BSTR v44; // rcx
  struct IUnknown *v45; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r14
  _QWORD *v47; // rdx
  int v48; // eax
  BSTR *v49; // rbx
  BSTR v50; // rcx
  struct IUnknown *v51; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // r14
  __int128 v53; // xmm6
  __int64 v54; // xmm7_8
  _bstr_t *v55; // rax
  __int64 v56; // rdx
  int v57; // eax
  BSTR *v58; // rbx
  BSTR v59; // rcx
  __int64 v60; // rbx
  __int64 (__fastcall *v61)(__int64, __int64); // rdi
  _bstr_t *v62; // rax
  __int64 v63; // rdx
  int v64; // eax
  BSTR *v65; // rbx
  BSTR v66; // rcx
  __int64 v67; // rdi
  __int64 (__fastcall *v68)(__int64, __int128 *); // rbx
  _variant_t *v69; // rax
  __int64 v70; // xmm1_8
  __int64 *v71; // rbx
  __int64 v72; // rax
  __int64 (__fastcall *v73)(__int64 *, __int64); // rdi
  _bstr_t *v74; // rax
  __int64 v75; // rdx
  int v76; // eax
  BSTR *v77; // rbx
  BSTR v78; // rcx
  __int64 v79; // rbx
  __int64 (__fastcall *v80)(__int64, __int64); // rdi
  _bstr_t *v81; // rax
  __int64 v82; // rdx
  __int64 (__fastcall *v83)(__int64 *, __int64); // rdi
  _bstr_t *v84; // rax
  __int64 v85; // rdx
  int v86; // eax
  BSTR *v87; // rbx
  BSTR v88; // rcx
  __int64 v89; // rdx
  __int64 (__fastcall *v90)(__int64 *, __int64); // rdi
  _bstr_t *v91; // rax
  __int64 v92; // rdx
  int v93; // eax
  BSTR *v94; // rbx
  BSTR v95; // rcx
  int v96; // eax
  BSTR *v97; // rbx
  BSTR v98; // rcx
  __int64 v99; // rbx
  __int64 (__fastcall *v100)(__int64, __int64); // rdi
  _bstr_t *v101; // rax
  __int64 v102; // rdx
  int v103; // eax
  BSTR *v104; // rbx
  BSTR v105; // rcx
  __int64 v106; // rbx
  __int64 (__fastcall *v107)(__int64, __int64); // rdi
  _bstr_t *v108; // rax
  __int64 v109; // rdx
  int v110; // eax
  BSTR *v111; // rbx
  BSTR v112; // rcx
  void *Block; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v115[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v116; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v117; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v118; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v119; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v120; // [rsp+80h] [rbp-88h]
  __int64 (__fastcall ***v121)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-80h] BYREF
  __int64 v122; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG v123; // [rsp+98h] [rbp-70h] BYREF
  __int128 v124; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v125; // [rsp+C8h] [rbp-40h]
  _WORD *v126; // [rsp+D8h] [rbp-30h] BYREF
  _WORD *v127; // [rsp+E0h] [rbp-28h]
  unsigned __int16 *v128; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int16 *v129; // [rsp+100h] [rbp-8h]
  unsigned __int16 *v130[4]; // [rsp+118h] [rbp+10h] BYREF
  __int128 v131; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v132; // [rsp+148h] [rbp+40h]
  VARIANTARG v133; // [rsp+158h] [rbp+50h] BYREF
  VARIANTARG pvarg; // [rsp+170h] [rbp+68h] BYREF
  __int128 v135; // [rsp+188h] [rbp+80h] BYREF
  IRecordInfo *v136; // [rsp+198h] [rbp+90h]
  __int128 v137; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v138; // [rsp+1B8h] [rbp+B0h]
  __int64 v140; // [rsp+280h] [rbp+178h] BYREF
  va_list va; // [rsp+280h] [rbp+178h]
  unsigned __int16 *v142; // [rsp+288h] [rbp+180h]
  __int64 *v143; // [rsp+290h] [rbp+188h] BYREF
  va_list va1; // [rsp+290h] [rbp+188h]
  struct IUnknown *v145; // [rsp+298h] [rbp+190h] BYREF
  va_list va2; // [rsp+298h] [rbp+190h]
  __int64 Data; // [rsp+2A0h] [rbp+198h] BYREF
  va_list Dataa; // [rsp+2A0h] [rbp+198h]
  __int64 v149; // [rsp+2A8h] [rbp+1A0h]
  __int64 v150; // [rsp+2B0h] [rbp+1A8h]
  va_list va4; // [rsp+2B8h] [rbp+1B0h] BYREF

  va_start(va4, a5);
  va_start(Dataa, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  va_arg(va1, _QWORD);
  v142 = va_arg(va1, unsigned __int16 *);
  va_copy(va2, va1);
  va_arg(va2, _QWORD);
  va_copy(Dataa, va2);
  va_arg(Dataa, _QWORD);
  va_copy(va4, Dataa);
  Data = va_arg(va4, _QWORD);
  v149 = va_arg(va4, _QWORD);
  v150 = va_arg(va4, _QWORD);
  v6 = a4;
  *(_QWORD *)&v119.vt = 0;
  v145 = 0;
  v140 = 0;
  v118 = 0;
  v143 = 0;
  v116 = 0;
  v122 = 0;
  v121 = 0;
  v117 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v128);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v130);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v126);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v128,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FA;;;",
                           50)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v126,
                           L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;LS)(A;OICI;GA;;;",
                           63) )
  {
    goto LABEL_208;
  }
  LODWORD(v150) = 0;
  if ( (unsigned int)_o__wcsicmp(L"S-1-5-18", L"S-1-5-18") )
  {
    LODWORD(v149) = 0;
    if ( !(unsigned int)_o__wcsicmp(L"S-1-5-18", L"S-1-5-32-545") )
    {
      v129 = v128;
      *v128 = 0;
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                              &v128,
                              L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                              41) )
      {
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v130,
                                L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical") )
        {
          v127 = v126;
          *v126 = 0;
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  &v126,
                                  L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
                                  34) )
          {
            LODWORD(v150) = 1;
            goto LABEL_19;
          }
        }
      }
LABEL_208:
      v14 = -2147024882;
      goto LABEL_209;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v128,
                             L"S-1-5-18")
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v128,
                             L")",
                             1)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v130,
                             L"S-1-5-18")
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v130,
                             L"\\EnterpriseMgmt",
                             15)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v126,
                             L"S-1-5-18") )
    {
      goto LABEL_208;
    }
    v11 = 1;
    v12 = L")";
  }
  else
  {
    v129 = v128;
    *v128 = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v128,
                             L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                             41)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v130,
                             L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical") )
    {
      goto LABEL_208;
    }
    v12 = L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)";
    v127 = v126;
    v11 = 34;
    LODWORD(v149) = 1;
    *v126 = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v126,
                           v12,
                           v11) )
    goto LABEL_208;
LABEL_19:
  LODWORD(Data) = CoCreateTaskScheduler(v10, v9, a1);
  v115[0] = "CreateTaskInFolder";
  va_copy((va_list)&v115[1], Dataa);
  if ( (int)Data >= 0 )
  {
    v15 = *a1;
    v16 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*a1 + 80LL);
    VariantInit(&pvarg);
    v17 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v133);
    v19 = *(_OWORD *)&v133.vt;
    v20 = v133.pRecInfo;
    VariantInit(&v123);
    v21 = *(_OWORD *)&v123.vt;
    v22 = v123.pRecInfo;
    VariantInit((VARIANTARG *)&v119.decVal.8);
    v124 = *(_OWORD *)&v119.decVal.Lo32;
    v135 = v17;
    v136 = pRecInfo;
    v137 = v19;
    v138 = v20;
    v131 = v21;
    v132 = v22;
    v125 = v120;
    LODWORD(Data) = v16(v15, &v124, &v131, &v137, &v135);
    _variant_t::~_variant_t((_variant_t *)&v119.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&v123);
    _variant_t::~_variant_t((_variant_t *)&v133);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( (int)Data < 0 )
    {
      v13 = L"23Connect";
      goto LABEL_21;
    }
    v23 = *a1;
    v24 = *(__int64 (__fastcall **)(LPVOID, __int64, VARIANTARG *))(*(_QWORD *)*a1 + 56LL);
    v25 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"\\");
    if ( *(_QWORD *)v25 )
      v26 = **(_QWORD **)v25;
    else
      v26 = 0;
    v27 = v24(v23, v26, &v119);
    v28 = (BSTR *)Block;
    v29 = v27;
    LODWORD(Data) = v27;
    if ( Block )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v28 )
      {
        if ( *v28 )
        {
          SysFreeString(*v28);
          *v28 = 0;
        }
        v30 = v28[1];
        if ( v30 )
        {
          operator delete(v30);
          v28[1] = 0;
        }
        operator delete(v28);
      }
      v29 = Data;
    }
    if ( v29 < 0 )
      goto LABEL_38;
    v31 = *(_QWORD *)&v119.vt;
    *(_QWORD *)&v123.vt = "spRootFolder->GetFolder()";
    va_copy(v123.pcVal, Dataa);
    v32 = *(__int64 (__fastcall **)(__int64, _QWORD *, struct IUnknown **))(**(_QWORD **)&v119.vt + 72LL);
    v33 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&Block, v130[0]);
    if ( v33 )
      v33 = (_QWORD *)*v33;
    v34 = v32(v31, v33, (struct IUnknown **)va2);
    v35 = (BSTR *)Block;
    LODWORD(Data) = v34;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v35 )
    {
      if ( *v35 )
      {
        SysFreeString(*v35);
        *v35 = 0;
      }
      v36 = v35[1];
      if ( v36 )
      {
        operator delete(v36);
        v35[1] = 0;
      }
      operator delete(v35);
    }
    if ( (unsigned int)(Data + 2147024894) <= 1 )
    {
      v37 = *(_QWORD *)&v119.vt;
      v38 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *, struct IUnknown **))(**(_QWORD **)&v119.vt + 88LL);
      v119.iVal = 0;
      ATL::CComVariant::operator=(&v119.decVal.Lo32, v126);
      v39 = *(_OWORD *)&v119.decVal.Lo32;
      v40 = v120;
      v41 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&Block, v130[0]);
      if ( v41 )
        v41 = (_QWORD *)*v41;
      v124 = v39;
      v125 = v40;
      v42 = v38(v37, v41, &v124, (struct IUnknown **)va2);
      v43 = (BSTR *)Block;
      LODWORD(Data) = v42;
      if ( Block )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v43 )
        {
          if ( *v43 )
          {
            SysFreeString(*v43);
            *v43 = 0;
          }
          v44 = v43[1];
          if ( v44 )
          {
            operator delete(v44);
            v43[1] = 0;
          }
          operator delete(v43);
        }
        Block = 0;
      }
      VariantClear((VARIANTARG *)&v119.decVal.8);
      v14 = Data;
      if ( (int)Data < 0 )
      {
LABEL_62:
        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v123);
        goto LABEL_22;
      }
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v123);
    if ( a5 )
    {
      v45 = v145;
      *(_QWORD *)&v123.vt = "spEnterpriseMgmtFolder->GetFolder()";
      va_copy(v123.pcVal, Dataa);
      QueryInterface = v145->lpVtbl[3].QueryInterface;
      v47 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&Block, a5);
      if ( v47 )
        v47 = (_QWORD *)*v47;
      v48 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *, struct IUnknown **))QueryInterface)(v45, v47, a2);
      v49 = (BSTR *)Block;
      LODWORD(Data) = v48;
      if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v49 )
      {
        if ( *v49 )
        {
          SysFreeString(*v49);
          *v49 = 0;
        }
        v50 = v49[1];
        if ( v50 )
        {
          operator delete(v50);
          v49[1] = 0;
        }
        operator delete(v49);
      }
      if ( (unsigned int)(Data + 2147024894) <= 1 )
      {
        v51 = v145;
        Release = v145->lpVtbl[3].Release;
        v119.iVal = 0;
        ATL::CComVariant::operator=(&v119.decVal.Lo32, v126);
        v53 = *(_OWORD *)&v119.decVal.Lo32;
        v54 = v120;
        v55 = _bstr_t::_bstr_t((_bstr_t *)&Block, a5);
        if ( *(_QWORD *)v55 )
          v56 = **(_QWORD **)v55;
        else
          v56 = 0;
        v124 = v53;
        v125 = v54;
        v57 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int128 *, struct IUnknown **))Release)(
                v51,
                v56,
                &v124,
                a2);
        v58 = (BSTR *)Block;
        LODWORD(Data) = v57;
        if ( Block )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v58 )
          {
            if ( *v58 )
            {
              SysFreeString(*v58);
              *v58 = 0;
            }
            v59 = v58[1];
            if ( v59 )
            {
              operator delete(v59);
              v58[1] = 0;
            }
            operator delete(v58);
          }
          Block = 0;
        }
        VariantClear((VARIANTARG *)&v119.decVal.8);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_62;
      }
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v123);
      v6 = a4;
    }
    else if ( *a2 != v145 )
    {
      ATL::AtlComPtrAssign(a2, v145);
    }
    LODWORD(Data) = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD *))(*(_QWORD *)*a1 + 72LL))(*a1, 0, a3);
    v14 = Data;
    if ( (int)Data < 0 )
      goto LABEL_22;
    LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 56LL))(*a3, &v118);
    v14 = Data;
    if ( (int)Data < 0 )
      goto LABEL_22;
    v60 = v118;
    v61 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v118 + 80LL);
    v62 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Microsoft Corporation");
    if ( *(_QWORD *)v62 )
      v63 = **(_QWORD **)v62;
    else
      v63 = 0;
    v64 = v61(v60, v63);
    v65 = (BSTR *)Block;
    LODWORD(Data) = v64;
    v29 = v64;
    if ( Block )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v65 )
      {
        if ( *v65 )
        {
          SysFreeString(*v65);
          *v65 = 0;
        }
        v66 = v65[1];
        if ( v66 )
        {
          operator delete(v66);
          v65[1] = 0;
        }
        operator delete(v65);
      }
      v29 = Data;
    }
    if ( v29 >= 0 )
    {
      v67 = v118;
      v68 = *(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v118 + 176LL);
      v69 = _variant_t::_variant_t((_variant_t *)&v131, v128);
      v70 = *((_QWORD *)v69 + 2);
      v124 = *(_OWORD *)v69;
      v125 = v70;
      LODWORD(Data) = v68(v67, &v124);
      _variant_t::~_variant_t((_variant_t *)&v131);
      v14 = Data;
      if ( (int)Data < 0 )
        goto LABEL_22;
      LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 120LL))(*a3, (__int64 **)va1);
      v14 = Data;
      if ( (int)Data < 0 )
        goto LABEL_22;
      v71 = v143;
      v72 = *v143;
      if ( (_DWORD)v149 )
      {
        v73 = *(__int64 (__fastcall **)(__int64 *, __int64))(v72 + 128);
        v74 = _bstr_t::_bstr_t((_bstr_t *)&Block, "SYSTEM");
        if ( *(_QWORD *)v74 )
          v75 = **(_QWORD **)v74;
        else
          v75 = 0;
        v76 = v73(v71, v75);
        v77 = (BSTR *)Block;
        v29 = v76;
        LODWORD(Data) = v76;
        if ( Block )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v77 )
          {
            if ( *v77 )
            {
              SysFreeString(*v77);
              *v77 = 0;
            }
            v78 = v77[1];
            if ( v78 )
            {
              operator delete(v78);
              v77[1] = 0;
            }
            operator delete(v77);
          }
          v29 = Data;
        }
        if ( v29 < 0 )
          goto LABEL_38;
      }
      else
      {
        if ( (_DWORD)v150 )
        {
          v83 = *(__int64 (__fastcall **)(__int64 *, __int64))(v72 + 128);
          v84 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"S-1-5-32-545");
          if ( *(_QWORD *)v84 )
            v85 = **(_QWORD **)v84;
          else
            v85 = 0;
          v86 = v83(v71, v85);
          v87 = (BSTR *)Block;
          v29 = v86;
          LODWORD(Data) = v86;
          if ( Block )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v87 )
            {
              if ( *v87 )
              {
                SysFreeString(*v87);
                *v87 = 0;
              }
              v88 = v87[1];
              if ( v88 )
              {
                operator delete(v88);
                v87[1] = 0;
              }
              operator delete(v87);
            }
            v29 = Data;
          }
          if ( v29 < 0 )
            goto LABEL_38;
          v89 = 1;
        }
        else
        {
          v90 = *(__int64 (__fastcall **)(__int64 *, __int64))(v72 + 96);
          v91 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"S-1-5-18");
          if ( *(_QWORD *)v91 )
            v92 = **(_QWORD **)v91;
          else
            v92 = 0;
          v93 = v90(v71, v92);
          v94 = (BSTR *)Block;
          v29 = v93;
          LODWORD(Data) = v93;
          if ( Block )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v94 )
            {
              if ( *v94 )
              {
                SysFreeString(*v94);
                *v94 = 0;
              }
              v95 = v94[1];
              if ( v95 )
              {
                operator delete(v95);
                v94[1] = 0;
              }
              operator delete(v94);
            }
            v29 = Data;
          }
          if ( v29 < 0 )
            goto LABEL_38;
          LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v143 + 112))(v143, 3);
          v14 = Data;
          if ( (int)Data < 0 )
            goto LABEL_22;
          v89 = 0;
        }
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v143 + 144))(v143, v89);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
      }
      LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 88LL))(*a3, (__int64 *)va);
      v14 = Data;
      if ( (int)Data < 0 )
        goto LABEL_22;
      LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v140 + 128LL))(v140, 0);
      v14 = Data;
      if ( (int)Data < 0 )
        goto LABEL_22;
      LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v140 + 144LL))(v140, 0);
      v14 = Data;
      if ( (int)Data < 0 )
        goto LABEL_22;
      LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v140 + 112LL))(v140, 1);
      v14 = Data;
      if ( (int)Data < 0 )
        goto LABEL_22;
      LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v140 + 352LL))(v140, 0);
      v14 = Data;
      if ( (int)Data < 0 )
        goto LABEL_22;
      v79 = v140;
      v80 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v140 + 224LL);
      v81 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"PT1H");
      if ( *(_QWORD *)v81 )
        v82 = **(_QWORD **)v81;
      else
        v82 = 0;
      v96 = v80(v79, v82);
      v97 = (BSTR *)Block;
      v29 = v96;
      LODWORD(Data) = v96;
      if ( Block )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v97 )
        {
          if ( *v97 )
          {
            SysFreeString(*v97);
            *v97 = 0;
          }
          v98 = v97[1];
          if ( v98 )
          {
            operator delete(v98);
            v97[1] = 0;
          }
          operator delete(v97);
        }
        v29 = Data;
      }
      if ( v29 >= 0 )
      {
        LODWORD(Data) = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v140)(
                          v140,
                          &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                          v6);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v6 + 176LL))(*v6, 0xFFFFFFFFLL);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v6 + 208LL))(*v6, 0xFFFFFFFFLL);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v6 + 400LL))(*v6, 0xFFFFFFFFLL);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v140 + 312LL))(v140, &v116);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v116 + 96LL))(v116, 0);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v116 + 64LL))(v116, 0);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v116 + 80LL))(v116, 0);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 136LL))(*a3, &v122);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v122 + 96LL))(v122, 0, &v121);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        LODWORD(Data) = (**v121)(v121, &IID_IExecAction, &v117);
        v14 = Data;
        if ( (int)Data < 0 )
          goto LABEL_22;
        v99 = v117;
        v100 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v117 + 88LL);
        v101 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"%windir%\\system32\\deviceenroller.exe ");
        if ( *(_QWORD *)v101 )
          v102 = **(_QWORD **)v101;
        else
          v102 = 0;
        v103 = v100(v99, v102);
        v104 = (BSTR *)Block;
        v29 = v103;
        LODWORD(Data) = v103;
        if ( Block )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v104 )
          {
            if ( *v104 )
            {
              SysFreeString(*v104);
              *v104 = 0;
            }
            v105 = v104[1];
            if ( v105 )
            {
              operator delete(v105);
              v104[1] = 0;
            }
            operator delete(v104);
          }
          v29 = Data;
        }
        if ( v29 >= 0 )
        {
          v106 = v117;
          v107 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v117 + 104LL);
          v108 = _bstr_t::_bstr_t((_bstr_t *)&Block, v142);
          v109 = *(_QWORD *)v108 ? **(_QWORD **)v108 : 0LL;
          v110 = v107(v106, v109);
          v111 = (BSTR *)Block;
          v29 = v110;
          if ( Block )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v111 )
            {
              if ( *v111 )
              {
                SysFreeString(*v111);
                *v111 = 0;
              }
              v112 = v111[1];
              if ( v112 )
              {
                operator delete(v112);
                v111[1] = 0;
              }
              operator delete(v111);
            }
            Block = 0;
          }
        }
      }
    }
LABEL_38:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v115);
    v14 = v29;
    goto LABEL_209;
  }
  v13 = L"22CoCreateTaskScheduler2";
LABEL_21:
  RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, v13, 4u, Dataa, 4u);
  v14 = Data;
LABEL_22:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v115);
LABEL_209:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v126);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v130);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v128);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v117);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v121);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v122);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v116);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>((__int64 **)va1);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v118);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>((__int64 *)va);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>((struct IUnknown **)va2);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v119);
  return v14;
}

```

## disassembly

```asm
0x1800d935c  mov     rax, rsp
0x1800d935f  mov     [rax+8], rbx
0x1800d9363  mov     [rax+10h], rdi
0x1800d9367  mov     [rax+20h], r9
0x1800d936b  push    rbp
0x1800d936c  push    r12
0x1800d936e  push    r13
0x1800d9370  push    r14
0x1800d9372  push    r15
0x1800d9374  lea     rbp, [rax-148h]
0x1800d937b  sub     rsp, 220h
0x1800d9382  xor     ebx, ebx
0x1800d9384  movaps  xmmword ptr [rax-38h], xmm6
0x1800d9388  movaps  xmmword ptr [rax-48h], xmm7
0x1800d938c  mov     r12, rcx
0x1800d938f  movaps  xmmword ptr [rax-58h], xmm8
0x1800d9394  lea     rcx, [rbp+140h+var_150]
0x1800d9398  movaps  xmmword ptr [rax-68h], xmm9
0x1800d939d  mov     r14, r9
0x1800d93a0  movaps  xmmword ptr [rax-78h], xmm10
0x1800d93a5  mov     r13, r8
0x1800d93a8  movaps  xmmword ptr [rax-88h], xmm11
0x1800d93b0  mov     r15, rdx
0x1800d93b3  mov     qword ptr [rsp+240h+var_1E0], rbx
0x1800d93b8  mov     [rbp+140h+arg_40], rbx
0x1800d93bf  mov     [rbp+140h+arg_28], rbx
0x1800d93c6  mov     [rsp+240h+var_1E8], rbx
0x1800d93cb  mov     [rbp+140h+arg_38], rbx
0x1800d93d2  mov     [rsp+240h+var_1F8], rbx
0x1800d93d7  mov     [rbp+140h+var_1B8], rbx
0x1800d93db  mov     [rbp+140h+var_1C0], rbx
0x1800d93df  mov     [rsp+240h+var_1F0], rbx
0x1800d93e4  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800d93e9  lea     rcx, [rbp+140h+var_130]
0x1800d93ed  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800d93f2  lea     rcx, [rbp+140h+var_170]
0x1800d93f6  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800d93fb  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x1800d9402  lea     r8d, [rbx+32h]
0x1800d9406  lea     rcx, [rbp+140h+var_150]
0x1800d940a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d940f  test    al, al
0x1800d9411  jz      loc_1800DA3C3
0x1800d9417  lea     r8d, [rbx+3Fh]
0x1800d941b  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x1800d9422  lea     rcx, [rbp+140h+var_170]
0x1800d9426  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d942b  test    al, al
0x1800d942d  jz      loc_1800DA3C3
0x1800d9433  lea     rdi, aS1518; "S-1-5-18"
0x1800d943a  mov     dword ptr [rbp+140h+arg_58], ebx
0x1800d9440  mov     rdx, rdi
0x1800d9443  mov     rcx, rdi
0x1800d9446  call    cs:__imp__o__wcsicmp
0x1800d944d  nop     dword ptr [rax+rax+00h]
0x1800d9452  test    eax, eax
0x1800d9454  jz      loc_1800D9576
0x1800d945a  lea     rdx, aS1532545; "S-1-5-32-545"
0x1800d9461  mov     dword ptr [rbp+140h+arg_50], ebx
0x1800d9467  mov     rcx, rdi
0x1800d946a  call    cs:__imp__o__wcsicmp
0x1800d9471  nop     dword ptr [rax+rax+00h]
0x1800d9476  test    eax, eax
0x1800d9478  jnz     short loc_1800D94EF
0x1800d947a  mov     rcx, [rbp+140h+var_150]
0x1800d947e  lea     r8d, [rbx+29h]
0x1800d9482  mov     [rbp+140h+var_148], rcx
0x1800d9486  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x1800d948d  mov     [rcx], bx
0x1800d9490  lea     rcx, [rbp+140h+var_150]
0x1800d9494  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d9499  test    al, al
0x1800d949b  jz      loc_1800DA3C3
0x1800d94a1  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x1800d94a8  lea     rcx, [rbp+140h+var_130]
0x1800d94ac  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800d94b1  test    al, al
0x1800d94b3  jz      loc_1800DA3C3
0x1800d94b9  mov     rcx, [rbp+140h+var_170]
0x1800d94bd  lea     r8d, [rbx+22h]
0x1800d94c1  mov     [rbp+140h+var_168], rcx
0x1800d94c5  lea     rdx, aDAOiciGaBaAOic_1; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x1800d94cc  mov     [rcx], bx
0x1800d94cf  lea     rcx, [rbp+140h+var_170]
0x1800d94d3  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d94d8  test    al, al
0x1800d94da  jz      loc_1800DA3C3
0x1800d94e0  mov     dword ptr [rbp+140h+arg_58], 1
0x1800d94ea  jmp     loc_1800D95EA
0x1800d94ef  mov     rdx, rdi
0x1800d94f2  lea     rcx, [rbp+140h+var_150]
0x1800d94f6  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800d94fb  test    al, al
0x1800d94fd  jz      loc_1800DA3C3
0x1800d9503  mov     r8d, 1
0x1800d9509  lea     rdx, asc_18012AA8C; ")"
0x1800d9510  lea     rcx, [rbp+140h+var_150]
0x1800d9514  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d9519  test    al, al
0x1800d951b  jz      loc_1800DA3C3
0x1800d9521  mov     rdx, rdi
0x1800d9524  lea     rcx, [rbp+140h+var_130]
0x1800d9528  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800d952d  test    al, al
0x1800d952f  jz      loc_1800DA3C3
0x1800d9535  mov     r8d, 0Fh
0x1800d953b  lea     rdx, aEnterprisemgmt_0; "\\EnterpriseMgmt"
0x1800d9542  lea     rcx, [rbp+140h+var_130]
0x1800d9546  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d954b  test    al, al
0x1800d954d  jz      loc_1800DA3C3
0x1800d9553  mov     rdx, rdi
0x1800d9556  lea     rcx, [rbp+140h+var_170]
0x1800d955a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800d955f  test    al, al
0x1800d9561  jz      loc_1800DA3C3
0x1800d9567  mov     r8d, 1
0x1800d956d  lea     rdx, asc_18012AA8C; ")"
0x1800d9574  jmp     short loc_1800D95D9
0x1800d9576  mov     rcx, [rbp+140h+var_150]
0x1800d957a  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x1800d9581  mov     [rbp+140h+var_148], rcx
0x1800d9585  mov     r8d, 29h ; ')'
0x1800d958b  mov     [rcx], bx
0x1800d958e  lea     rcx, [rbp+140h+var_150]
0x1800d9592  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d9597  test    al, al
0x1800d9599  jz      loc_1800DA3C3
0x1800d959f  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x1800d95a6  lea     rcx, [rbp+140h+var_130]
0x1800d95aa  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800d95af  test    al, al
0x1800d95b1  jz      loc_1800DA3C3
0x1800d95b7  mov     rcx, [rbp+140h+var_170]
0x1800d95bb  lea     rdx, aDAOiciGaBaAOic_1; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x1800d95c2  mov     [rbp+140h+var_168], rcx
0x1800d95c6  mov     r8d, 22h ; '"'
0x1800d95cc  mov     dword ptr [rbp+140h+arg_50], 1
0x1800d95d6  mov     [rcx], bx
0x1800d95d9  lea     rcx, [rbp+140h+var_170]
0x1800d95dd  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d95e2  test    al, al
0x1800d95e4  jz      loc_1800DA3C3
0x1800d95ea  mov     r8, r12
0x1800d95ed  call    CoCreateTaskScheduler
0x1800d95f2  mov     dword ptr [rbp+140h+Data], eax
0x1800d95f8  lea     rcx, aCreatetaskinfo; "CreateTaskInFolder"
0x1800d95ff  mov     [rsp+240h+var_208], rcx
0x1800d9604  lea     rcx, [rbp+140h+Data]
0x1800d960b  mov     [rsp+240h+var_200], rcx
0x1800d9610  test    eax, eax
0x1800d9612  jns     short loc_1800D9661
0x1800d9614  lea     r8, a22cocreatetask; "22CoCreateTaskScheduler2"
0x1800d961b  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800d9622  lea     rax, [rbp+140h+Data]
0x1800d9629  mov     r9d, 4; dwType
0x1800d962f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d9636  mov     [rsp+240h+cbData], r9d; cbData
0x1800d963b  mov     [rsp+240h+lpData], rax; lpData
0x1800d9640  call    cs:__imp_RegSetKeyValueW
0x1800d9647  nop     dword ptr [rax+rax+00h]
0x1800d964c  mov     ebx, dword ptr [rbp+140h+Data]
0x1800d9652  lea     rcx, [rsp+240h+var_208]; this
0x1800d9657  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800d965c  jmp     loc_1800DA3C8
0x1800d9661  mov     rdi, [r12]
0x1800d9665  lea     rcx, [rbp+140h+pvarg]; pvarg
0x1800d9669  mov     rax, [rdi]
0x1800d966c  mov     rbx, [rax+50h]
0x1800d9670  call    cs:__imp_VariantInit
0x1800d9677  nop     dword ptr [rax+rax+00h]
0x1800d967c  movups  xmm10, xmmword ptr [rbp+140h+pvarg]
0x1800d9681  lea     rcx, [rbp+140h+var_F0]; pvarg
0x1800d9685  movsd   xmm11, qword ptr [rbp+140h+pvarg+10h]
0x1800d968b  call    cs:__imp_VariantInit
0x1800d9692  nop     dword ptr [rax+rax+00h]
0x1800d9697  movups  xmm8, xmmword ptr [rbp+140h+var_F0]
0x1800d969c  lea     rcx, [rbp+140h+var_1B0]; pvarg
0x1800d96a0  movsd   xmm9, qword ptr [rbp+140h+var_F0+10h]
0x1800d96a6  call    cs:__imp_VariantInit
0x1800d96ad  nop     dword ptr [rax+rax+00h]
0x1800d96b2  movups  xmm6, xmmword ptr [rbp+140h+var_1B0]
0x1800d96b6  lea     rcx, [rsp+240h+var_1E0+8]; pvarg
0x1800d96bb  movsd   xmm7, qword ptr [rbp+140h+var_1B0+10h]
0x1800d96c0  call    cs:__imp_VariantInit
0x1800d96c7  nop     dword ptr [rax+rax+00h]
0x1800d96cc  movups  xmm0, xmmword ptr [rsp+240h+var_1E0+8]
0x1800d96d1  lea     rax, [rbp+140h+var_C0]
0x1800d96d8  mov     rcx, rdi
0x1800d96db  movsd   xmm1, [rsp+240h+var_1C8]
0x1800d96e1  lea     r9, [rbp+140h+var_A0]
0x1800d96e8  mov     [rsp+240h+lpData], rax
0x1800d96ed  lea     r8, [rbp+140h+var_110]
0x1800d96f1  mov     rax, rbx
0x1800d96f4  movaps  [rbp+140h+var_190], xmm0
0x1800d96f8  lea     rdx, [rbp+140h+var_190]
0x1800d96fc  movaps  [rbp+140h+var_C0], xmm10
0x1800d9704  movsd   [rbp+140h+var_B0], xmm11
0x1800d970d  movaps  [rbp+140h+var_A0], xmm8
0x1800d9715  movsd   [rbp+140h+var_90], xmm9
0x1800d971e  movaps  [rbp+140h+var_110], xmm6
0x1800d9722  movsd   [rbp+140h+var_100], xmm7
0x1800d9727  movsd   [rbp+140h+var_180], xmm1
0x1800d972c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9731  lea     rcx, [rsp+240h+var_1E0+8]; this
0x1800d9736  mov     dword ptr [rbp+140h+Data], eax
0x1800d973c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800d9741  lea     rcx, [rbp+140h+var_1B0]; this
0x1800d9745  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800d974a  lea     rcx, [rbp+140h+var_F0]; this
0x1800d974e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800d9753  lea     rcx, [rbp+140h+pvarg]; this
0x1800d9757  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800d975c  cmp     dword ptr [rbp+140h+Data], 0
0x1800d9763  jge     short loc_1800D9771
0x1800d9765  lea     r8, a23connect; "23Connect"
0x1800d976c  jmp     loc_1800D961B
0x1800d9771  mov     rbx, [r12]
0x1800d9775  lea     rdx, StringValue; "\\"
0x1800d977c  lea     rcx, [rsp+240h+Block]; this
0x1800d9781  mov     rax, [rbx]
0x1800d9784  mov     rdi, [rax+38h]
0x1800d9788  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800d978d  mov     rcx, [rax]
0x1800d9790  test    rcx, rcx
0x1800d9793  jz      short loc_1800D979A
0x1800d9795  mov     rdx, [rcx]
0x1800d9798  jmp     short loc_1800D979C
0x1800d979a  xor     edx, edx
0x1800d979c  lea     r8, [rsp+240h+var_1E0]
0x1800d97a1  mov     rcx, rbx
0x1800d97a4  mov     rax, rdi
0x1800d97a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d97ac  mov     rbx, [rsp+240h+Block]
0x1800d97b1  mov     edi, eax
0x1800d97b3  mov     dword ptr [rbp+140h+Data], eax
0x1800d97b9  test    rbx, rbx
0x1800d97bc  jz      short loc_1800D9814
0x1800d97be  or      eax, 0FFFFFFFFh
0x1800d97c1  lock xadd [rbx+10h], eax
0x1800d97c6  cmp     eax, 1
0x1800d97c9  jnz     short loc_1800D980E
0x1800d97cb  test    rbx, rbx
0x1800d97ce  jz      short loc_1800D980E
0x1800d97d0  mov     rcx, [rbx]; bstrString
0x1800d97d3  test    rcx, rcx
0x1800d97d6  jz      short loc_1800D97EB
0x1800d97d8  call    cs:__imp_SysFreeString
0x1800d97df  nop     dword ptr [rax+rax+00h]
0x1800d97e4  mov     qword ptr [rbx], 0
0x1800d97eb  mov     rcx, [rbx+8]; Block
0x1800d97ef  test    rcx, rcx
0x1800d97f2  jz      short loc_1800D9801
0x1800d97f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d97f9  mov     qword ptr [rbx+8], 0
0x1800d9801  mov     edx, 18h
0x1800d9806  mov     rcx, rbx; Block
0x1800d9809  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d980e  mov     edi, dword ptr [rbp+140h+Data]
0x1800d9814  test    edi, edi
0x1800d9816  jns     short loc_1800D9829
0x1800d9818  lea     rcx, [rsp+240h+var_208]; this
0x1800d981d  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800d9822  mov     ebx, edi
0x1800d9824  jmp     loc_1800DA3C8
0x1800d9829  mov     rbx, qword ptr [rsp+240h+var_1E0]
0x1800d982e  lea     rax, aSprootfolderGe; "spRootFolder->GetFolder()"
0x1800d9835  mov     rdx, [rbp+140h+var_130]; unsigned __int16 *
0x1800d9839  lea     rcx, [rsp+240h+Block]; this
0x1800d983e  mov     qword ptr [rbp+140h+var_1B0], rax
0x1800d9842  lea     rax, [rbp+140h+Data]
0x1800d9849  mov     qword ptr [rbp+140h+var_1B0+8], rax
0x1800d984d  mov     rax, [rbx]
0x1800d9850  mov     rdi, [rax+48h]
0x1800d9854  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800d9859  mov     rdx, [rax]
0x1800d985c  test    rdx, rdx
0x1800d985f  jz      short loc_1800D9864
0x1800d9861  mov     rdx, [rdx]
0x1800d9864  lea     r8, [rbp+140h+arg_40]
0x1800d986b  mov     rcx, rbx
0x1800d986e  mov     rax, rdi
0x1800d9871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9876  mov     rbx, [rsp+240h+Block]
0x1800d987b  mov     dword ptr [rbp+140h+Data], eax
0x1800d9881  test    rbx, rbx
0x1800d9884  jz      short loc_1800D98D6
0x1800d9886  or      eax, 0FFFFFFFFh
0x1800d9889  lock xadd [rbx+10h], eax
0x1800d988e  cmp     eax, 1
0x1800d9891  jnz     short loc_1800D98D6
0x1800d9893  test    rbx, rbx
0x1800d9896  jz      short loc_1800D98D6
0x1800d9898  mov     rcx, [rbx]; bstrString
0x1800d989b  test    rcx, rcx
0x1800d989e  jz      short loc_1800D98B3
0x1800d98a0  call    cs:__imp_SysFreeString
0x1800d98a7  nop     dword ptr [rax+rax+00h]
0x1800d98ac  mov     qword ptr [rbx], 0
0x1800d98b3  mov     rcx, [rbx+8]; Block
  ... truncated ...
```
