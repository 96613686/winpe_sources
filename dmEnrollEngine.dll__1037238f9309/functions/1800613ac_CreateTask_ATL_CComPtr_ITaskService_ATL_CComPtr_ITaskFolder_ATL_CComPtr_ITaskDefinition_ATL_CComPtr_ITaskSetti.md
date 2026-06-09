# CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)

- ea: `0x1800613ac`
- end: `0x180062576`
- name: `?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z`
- size: `4554`
- prototype: `__int64(_QWORD *, struct IUnknown **, _QWORD *, _QWORD *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, int, int, int, ...)`
- caller_count: `9`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18006257c`
- `0x180062ee0`
- `0x1800635d4`
- `0x180063b68`
- `0x1800640a4`
- `0x180064578`
- `0x180064938`
- `0x180064d98`
- `0x1800653dc`

## callees

- `0x18000dec0`
- `0x18000efc4`
- `0x1800140d0`
- `0x180016508`
- `0x18001788c`
- `0x18002e570`
- `0x180035f10`
- `0x1800434d0`
- `0x180043544`
- `0x18004c594`
- `0x180057e28`
- `0x180057e50`
- `0x1800608f8`
- `0x180060974`
- `0x1800613ac`
- `0x18007b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800614bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800614d7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800614bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800614d7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800616a5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800616a5`
- `OLEAUT32!__imp_SysAllocString` at `0x18006194e`
- `OLEAUT32!__imp_SysAllocString` at `0x180061b41`
- `OLEAUT32!__imp_SysAllocString` at `0x18006194e`
- `OLEAUT32!__imp_SysAllocString` at `0x180061b41`
- `OLEAUT32!__imp_SysFreeString` at `0x18006182c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800618e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800619f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180061ad2`
- `OLEAUT32!__imp_SysFreeString` at `0x180061beb`
- `OLEAUT32!__imp_SysFreeString` at `0x180061d0e`
- `OLEAUT32!__imp_SysFreeString` at `0x180061e31`
- `OLEAUT32!__imp_SysFreeString` at `0x180061ed0`
- `OLEAUT32!__imp_SysFreeString` at `0x180061f89`
- `OLEAUT32!__imp_SysFreeString` at `0x180062135`
- `OLEAUT32!__imp_SysFreeString` at `0x18006238a`
- `OLEAUT32!__imp_SysFreeString` at `0x18006241d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006182c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800618e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800619f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180061ad2`
- `OLEAUT32!__imp_SysFreeString` at `0x180061beb`
- `OLEAUT32!__imp_SysFreeString` at `0x180061d0e`
- `OLEAUT32!__imp_SysFreeString` at `0x180061e31`
- `OLEAUT32!__imp_SysFreeString` at `0x180061ed0`
- `OLEAUT32!__imp_SysFreeString` at `0x180061f89`
- `OLEAUT32!__imp_SysFreeString` at `0x180062135`
- `OLEAUT32!__imp_SysFreeString` at `0x18006238a`
- `OLEAUT32!__imp_SysFreeString` at `0x18006241d`
- `OLEAUT32!__imp_VariantInit` at `0x1800616d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800616ec`
- `OLEAUT32!__imp_VariantInit` at `0x180061704`
- `OLEAUT32!__imp_VariantInit` at `0x180061718`
- `OLEAUT32!__imp_VariantInit` at `0x1800616d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800616ec`
- `OLEAUT32!__imp_VariantInit` at `0x180061704`
- `OLEAUT32!__imp_VariantInit` at `0x180061718`
- `OLEAUT32!__imp_VariantClear` at `0x18006193b`
- `OLEAUT32!__imp_VariantClear` at `0x180061a29`
- `OLEAUT32!__imp_VariantClear` at `0x180061b2e`
- `OLEAUT32!__imp_VariantClear` at `0x180061c1d`
- `OLEAUT32!__imp_VariantClear` at `0x18006193b`
- `OLEAUT32!__imp_VariantClear` at `0x180061a29`
- `OLEAUT32!__imp_VariantClear` at `0x180061b2e`
- `OLEAUT32!__imp_VariantClear` at `0x180061c1d`

## string_xrefs

- `0x18006165d`: `CreateTask`
- `0x180061679`: `22CoCreateTaskScheduler2`

## pseudocode

```c
__int64 CreateTask(
        _QWORD *a1,
        struct IUnknown **a2,
        _QWORD *a3,
        _QWORD *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned int a9,
        int a10,
        int a11,
        int a12,
        ...)
{
  _QWORD *v12; // r15
  unsigned int v14; // r13d
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  const WCHAR *v19; // r8
  unsigned int v20; // ebx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int128 *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v23; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v25; // xmm8
  IRecordInfo *v26; // xmm9_8
  __int128 v27; // xmm6
  IRecordInfo *v28; // xmm7_8
  __int64 v29; // rbx
  __int64 (__fastcall *v30)(__int64, __int64, __int64 **); // rdi
  _bstr_t *v31; // rax
  __int64 v32; // rdx
  int v33; // eax
  BSTR *v34; // rbx
  int v35; // edi
  BSTR v36; // rcx
  __int64 *v37; // rbx
  __int64 (__fastcall *v38)(__int64 *, __int64, VARIANTARG *); // rdi
  _bstr_t *v39; // rax
  __int64 v40; // rdx
  int v41; // eax
  BSTR *v42; // rbx
  BSTR v43; // rcx
  __int64 *v44; // rdi
  OLECHAR *v45; // rbx
  __int64 v46; // r14
  __int128 v47; // xmm6
  __int64 v48; // xmm7_8
  _QWORD *v49; // rdx
  __int64 (__fastcall *v50)(__int64 *, _QWORD *, __int128 *, VARIANTARG *); // rax
  int v51; // eax
  BSTR *v52; // rbx
  BSTR v53; // rcx
  __int64 v54; // rbx
  __int64 (__fastcall *v55)(__int64, _QWORD *, struct IUnknown **); // r14
  _QWORD *v56; // rdx
  int v57; // eax
  BSTR *v58; // rbx
  BSTR v59; // rcx
  __int64 v60; // r14
  OLECHAR *v61; // rbx
  __int64 v62; // r15
  __int128 v63; // xmm6
  __int64 v64; // xmm7_8
  _bstr_t *v65; // rax
  __int64 v66; // rdx
  __int64 (__fastcall *v67)(__int64, __int64, __int128 *, struct IUnknown **); // rax
  int v68; // eax
  BSTR *v69; // rbx
  BSTR v70; // rcx
  __int64 v71; // rbx
  __int64 (__fastcall *v72)(__int64, __int64); // rdi
  _bstr_t *v73; // rax
  __int64 v74; // rdx
  int v75; // eax
  BSTR *v76; // rbx
  BSTR v77; // rcx
  __int64 v78; // rdi
  __int64 (__fastcall *v79)(__int64, __int128 *); // rbx
  _variant_t *v80; // rax
  __int64 v81; // xmm1_8
  __int64 *v82; // rbx
  __int64 v83; // rax
  __int64 (__fastcall *v84)(__int64 *, __int64); // rdi
  _bstr_t *v85; // rax
  __int64 v86; // rdx
  int v87; // eax
  BSTR *v88; // rbx
  BSTR v89; // rcx
  __int64 (__fastcall *v90)(__int64 *, __int64); // rdi
  _bstr_t *v91; // rax
  __int64 v92; // rdx
  int v93; // eax
  BSTR *v94; // rbx
  BSTR v95; // rcx
  __int64 (__fastcall *v96)(__int64 *, __int64); // rdi
  _bstr_t *v97; // rax
  __int64 v98; // rdx
  int v99; // eax
  BSTR *v100; // rbx
  BSTR v101; // rcx
  __int64 v102; // rbx
  __int64 (__fastcall *v103)(__int64, __int64); // rdi
  _bstr_t *v104; // rax
  __int64 v105; // rdx
  int v106; // eax
  BSTR *v107; // rbx
  BSTR v108; // rcx
  __int64 v109; // rbx
  __int64 (__fastcall *v110)(__int64, __int64); // rdi
  _bstr_t *v111; // rax
  __int64 v112; // rdx
  int v113; // eax
  BSTR *v114; // rbx
  BSTR v115; // rcx
  __int64 v116; // rbx
  __int64 (__fastcall *v117)(__int64, __int64); // rdi
  _bstr_t *v118; // rax
  __int64 v119; // rdx
  unsigned int v120; // eax
  BSTR *v121; // rbx
  unsigned int v122; // edi
  BSTR v123; // rcx
  void *Block[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v126[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v127; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v128; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v129; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v130; // [rsp+80h] [rbp-88h]
  __int64 v131; // [rsp+88h] [rbp-80h] BYREF
  int v132; // [rsp+90h] [rbp-78h]
  int v133; // [rsp+94h] [rbp-74h]
  __int64 v134; // [rsp+98h] [rbp-70h] BYREF
  __int64 v135; // [rsp+A0h] [rbp-68h] BYREF
  __int64 *v136; // [rsp+A8h] [rbp-60h] BYREF
  __int64 (__fastcall ***v137)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-58h] BYREF
  __int64 v138; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v139; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v140; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v141; // [rsp+E8h] [rbp-20h]
  OLECHAR *psz; // [rsp+F8h] [rbp-10h] BYREF
  OLECHAR *v143; // [rsp+100h] [rbp-8h]
  unsigned __int16 *v144; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 *v145; // [rsp+120h] [rbp+18h]
  unsigned __int16 *v146[4]; // [rsp+138h] [rbp+30h] BYREF
  __int128 v147; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v148; // [rsp+168h] [rbp+60h]
  VARIANTARG v149; // [rsp+178h] [rbp+70h] BYREF
  VARIANTARG pvarg; // [rsp+190h] [rbp+88h] BYREF
  __int128 v151; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v152; // [rsp+1B8h] [rbp+B0h]
  __int128 v153; // [rsp+1C8h] [rbp+C0h] BYREF
  IRecordInfo *v154; // [rsp+1D8h] [rbp+D0h]
  __int64 Data; // [rsp+2E8h] [rbp+1E0h] BYREF
  va_list Dataa; // [rsp+2E8h] [rbp+1E0h]
  va_list va1; // [rsp+2F0h] [rbp+1E8h] BYREF

  va_start(va1, a12);
  va_start(Dataa, a12);
  Data = va_arg(va1, _QWORD);
  v12 = a1;
  v136 = 0;
  *(_QWORD *)&v129.vt = 0;
  v127 = 0;
  v135 = 0;
  v128 = 0;
  v131 = 0;
  v138 = 0;
  v137 = 0;
  v134 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v144);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v146);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&psz);
  v14 = 0;
  if ( (_DWORD)Data != 1 )
  {
    LOBYTE(v14) = a10 != 1;
    ++v14;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v144,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FA;;;",
                           50)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;LS)(A;OICI;GA;;;",
                           63) )
  {
    goto LABEL_220;
  }
  v133 = 0;
  if ( a8 && (unsigned int)_o__wcsicmp(a8, L"S-1-5-18") )
  {
    v132 = 0;
    if ( !(unsigned int)_o__wcsicmp(a8, L"S-1-5-32-545") )
    {
      v145 = v144;
      *v144 = 0;
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                              &v144,
                              L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                              41) )
      {
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v146,
                                L"\\Microsoft\\Windows\\EnterpriseMgmt",
                                33) )
        {
          v143 = psz;
          *psz = 0;
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  &psz,
                                  L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
                                  34) )
          {
            v133 = 1;
            goto LABEL_22;
          }
        }
      }
LABEL_220:
      v20 = -2147024882;
      goto LABEL_221;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v144,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v144,
                             L")",
                             1)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v146,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v146,
                             L"\\EnterpriseMgmt",
                             15)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &psz,
                             a8) )
    {
      goto LABEL_220;
    }
    v17 = 1;
    v18 = L")";
  }
  else
  {
    v145 = v144;
    *v144 = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v144,
                             L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                             41)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v146,
                             L"\\Microsoft\\Windows\\EnterpriseMgmt",
                             33) )
    {
      goto LABEL_220;
    }
    v18 = L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)";
    v143 = psz;
    v17 = 34;
    v132 = 1;
    *psz = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           v18,
                           v17) )
    goto LABEL_220;
LABEL_22:
  LODWORD(Data) = CoCreateTaskScheduler(v16, v15, v12);
  v126[0] = "CreateTask";
  va_copy((va_list)&v126[1], Dataa);
  if ( (int)Data < 0 )
  {
    v19 = L"22CoCreateTaskScheduler2";
LABEL_24:
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, v19, 4u, Dataa, 4u);
    v20 = Data;
LABEL_25:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v126);
LABEL_221:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&psz);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v146);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v144);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v134);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v137);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v138);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v131);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v128);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v135);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v127);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v129);
    ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v136);
    return v20;
  }
  v21 = *v12;
  v22 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*v12 + 80LL);
  VariantInit(&pvarg);
  v23 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v149);
  v25 = *(_OWORD *)&v149.vt;
  v26 = v149.pRecInfo;
  VariantInit(&v139);
  v27 = *(_OWORD *)&v139.vt;
  v28 = v139.pRecInfo;
  VariantInit((VARIANTARG *)&v129.decVal.8);
  v140 = *(_OWORD *)&v129.decVal.Lo32;
  v151 = v23;
  v152 = pRecInfo;
  v153 = v25;
  v154 = v26;
  v147 = v27;
  v148 = v28;
  v141 = v130;
  LODWORD(Data) = v22(v21, &v140, &v147, &v153, &v151);
  _variant_t::~_variant_t((_variant_t *)&v129.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v139);
  _variant_t::~_variant_t((_variant_t *)&v149);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( (int)Data < 0 )
  {
    v19 = L"23Connect";
    goto LABEL_24;
  }
  v29 = *v12;
  v30 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)*v12 + 56LL);
  v31 = _bstr_t::_bstr_t((_bstr_t *)Block, L"\\");
  if ( *(_QWORD *)v31 )
    v32 = **(_QWORD **)v31;
  else
    v32 = 0;
  v33 = v30(v29, v32, &v136);
  v34 = (BSTR *)Block[0];
  v35 = v33;
  LODWORD(Data) = v33;
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v34 )
    {
      if ( *v34 )
      {
        SysFreeString(*v34);
        *v34 = 0;
      }
      v36 = v34[1];
      if ( v36 )
      {
        operator delete(v36);
        v34[1] = 0;
      }
      operator delete(v34);
    }
    v35 = Data;
  }
  if ( v35 < 0 )
    goto LABEL_41;
  v37 = v136;
  *(_QWORD *)&v139.vt = "spRootFolder->GetFolder()";
  va_copy(v139.pcVal, Dataa);
  v38 = *(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(*v136 + 72);
  v39 = _bstr_t::_bstr_t((_bstr_t *)Block, v146[0]);
  if ( *(_QWORD *)v39 )
    v40 = **(_QWORD **)v39;
  else
    v40 = 0;
  v41 = v38(v37, v40, &v129);
  v42 = (BSTR *)Block[0];
  LODWORD(Data) = v41;
  if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v42 )
  {
    if ( *v42 )
    {
      SysFreeString(*v42);
      *v42 = 0;
    }
    v43 = v42[1];
    if ( v43 )
    {
      operator delete(v43);
      v42[1] = 0;
    }
    operator delete(v42);
  }
  if ( (unsigned int)(Data + 2147024894) <= 1 )
  {
    v44 = v136;
    v45 = psz;
    v46 = *v136;
    v129.iVal = 0;
    VariantClear((VARIANTARG *)&v129.decVal.8);
    v129.iVal = 8;
    v129.pRecInfo = (IRecordInfo *)SysAllocString(v45);
    if ( !v129.pRecInfo && v45 )
    {
      v129.iVal = 10;
      *((_DWORD *)&v129.decVal + 4) = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v47 = *(_OWORD *)&v129.decVal.Lo32;
    v48 = v130;
    v49 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)Block, v146[0]);
    if ( v49 )
      v49 = (_QWORD *)*v49;
    v50 = *(__int64 (__fastcall **)(__int64 *, _QWORD *, __int128 *, VARIANTARG *))(v46 + 88);
    v140 = v47;
    v141 = v48;
    v51 = v50(v44, v49, &v140, &v129);
    v52 = (BSTR *)Block[0];
    LODWORD(Data) = v51;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v52 )
      {
        if ( *v52 )
        {
          SysFreeString(*v52);
          *v52 = 0;
        }
        v53 = v52[1];
        if ( v53 )
        {
          operator delete(v53);
          v52[1] = 0;
        }
        operator delete(v52);
      }
      Block[0] = 0;
    }
    VariantClear((VARIANTARG *)&v129.decVal.8);
    v20 = Data;
    if ( (int)Data < 0 )
    {
LABEL_69:
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v139);
      goto LABEL_25;
    }
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v139);
  if ( a5 )
  {
    v54 = *(_QWORD *)&v129.vt;
    *(_QWORD *)&v139.vt = "spEnterpriseMgmtFolder->GetFolder()";
    va_copy(v139.pcVal, Dataa);
    v55 = *(__int64 (__fastcall **)(__int64, _QWORD *, struct IUnknown **))(**(_QWORD **)&v129.vt + 72LL);
    v56 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)Block, a5);
    if ( v56 )
      v56 = (_QWORD *)*v56;
    v57 = v55(v54, v56, a2);
    v58 = (BSTR *)Block[0];
    LODWORD(Data) = v57;
    if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v58 )
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
    if ( (unsigned int)(Data + 2147024894) <= 1 )
    {
      v60 = *(_QWORD *)&v129.vt;
      v61 = psz;
      v62 = **(_QWORD **)&v129.vt;
      v129.iVal = 0;
      VariantClear((VARIANTARG *)&v129.decVal.8);
      v129.iVal = 8;
      v129.pRecInfo = (IRecordInfo *)SysAllocString(v61);
      if ( !v129.pRecInfo && v61 )
      {
        v129.iVal = 10;
        *((_DWORD *)&v129.decVal + 4) = -2147024882;
        ATL::AtlThrowImpl(-2147024882);
      }
      v63 = *(_OWORD *)&v129.decVal.Lo32;
      v64 = v130;
      v65 = _bstr_t::_bstr_t((_bstr_t *)Block, a5);
      if ( *(_QWORD *)v65 )
        v66 = **(_QWORD **)v65;
      else
        v66 = 0;
      v67 = *(__int64 (__fastcall **)(__int64, __int64, __int128 *, struct IUnknown **))(v62 + 88);
      v140 = v63;
      v141 = v64;
      v68 = v67(v60, v66, &v140, a2);
      v69 = (BSTR *)Block[0];
      LODWORD(Data) = v68;
      if ( Block[0] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v69 )
        {
          if ( *v69 )
          {
            SysFreeString(*v69);
            *v69 = 0;
          }
          v70 = v69[1];
          if ( v70 )
          {
            operator delete(v70);
            v69[1] = 0;
          }
          operator delete(v69);
        }
        Block[0] = 0;
      }
      VariantClear((VARIANTARG *)&v129.decVal.8);
      v20 = Data;
      if ( (int)Data < 0 )
        goto LABEL_69;
      v12 = a1;
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v139);
  }
  else if ( *a2 != *(struct IUnknown **)&v129.vt )
  {
    ATL::AtlComPtrAssign(a2, *(struct IUnknown **)&v129.vt);
  }
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(*(_QWORD *)*v12 + 72LL))(*v12, 0, a3);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 56LL))(*a3, &v135);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v71 = v135;
  v72 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v135 + 80LL);
  v73 = _bstr_t::_bstr_t((_bstr_t *)Block, L"Microsoft Corporation");
  if ( *(_QWORD *)v73 )
    v74 = **(_QWORD **)v73;
  else
    v74 = 0;
  v75 = v72(v71, v74);
  v76 = (BSTR *)Block[0];
  LODWORD(Data) = v75;
  v35 = v75;
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v76 )
    {
      if ( *v76 )
      {
        SysFreeString(*v76);
        *v76 = 0;
      }
      v77 = v76[1];
      if ( v77 )
      {
        operator delete(v77);
        v76[1] = 0;
      }
      operator delete(v76);
    }
    v35 = Data;
  }
  if ( v35 < 0 )
    goto LABEL_41;
  v78 = v135;
  v79 = *(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v135 + 176LL);
  v80 = _variant_t::_variant_t((_variant_t *)&v147, v144);
  v81 = *((_QWORD *)v80 + 2);
  v140 = *(_OWORD *)v80;
  v141 = v81;
  LODWORD(Data) = v79(v78, &v140);
  _variant_t::~_variant_t((_variant_t *)&v147);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 120LL))(*a3, &v128);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v82 = v128;
  v83 = *v128;
  if ( v132 )
  {
    v84 = *(__int64 (__fastcall **)(__int64 *, __int64))(v83 + 128);
    v85 = _bstr_t::_bstr_t((_bstr_t *)Block, "SYSTEM");
    if ( *(_QWORD *)v85 )
      v86 = **(_QWORD **)v85;
    else
      v86 = 0;
    v87 = v84(v82, v86);
    v88 = (BSTR *)Block[0];
    v35 = v87;
    LODWORD(Data) = v87;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v88 )
      {
        if ( *v88 )
        {
          SysFreeString(*v88);
          *v88 = 0;
        }
        v89 = v88[1];
        if ( v89 )
        {
          operator delete(v89);
          v88[1] = 0;
        }
        operator delete(v88);
      }
      v35 = Data;
    }
    if ( v35 < 0 )
      goto LABEL_41;
  }
  else if ( v133 )
  {
    v90 = *(__int64 (__fastcall **)(__int64 *, __int64))(v83 + 128);
    v91 = _bstr_t::_bstr_t((_bstr_t *)Block, L"S-1-5-32-545");
    if ( *(_QWORD *)v91 )
      v92 = **(_QWORD **)v91;
    else
      v92 = 0;
    v93 = v90(v82, v92);
    v94 = (BSTR *)Block[0];
    v35 = v93;
    LODWORD(Data) = v93;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v94 )
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
      v35 = Data;
    }
    if ( v35 < 0 )
      goto LABEL_41;
    LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v128 + 144))(v128, 1);
    v20 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
  }
  else
  {
    v96 = *(__int64 (__fastcall **)(__int64 *, __int64))(v83 + 96);
    v97 = _bstr_t::_bstr_t((_bstr_t *)Block, a8);
    if ( *(_QWORD *)v97 )
      v98 = **(_QWORD **)v97;
    else
      v98 = 0;
    v99 = v96(v82, v98);
    v100 = (BSTR *)Block[0];
    v35 = v99;
    LODWORD(Data) = v99;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v100 )
      {
        if ( *v100 )
        {
          SysFreeString(*v100);
          *v100 = 0;
        }
        v101 = v100[1];
        if ( v101 )
        {
          operator delete(v101);
          v100[1] = 0;
        }
        operator delete(v100);
      }
      v35 = Data;
    }
    if ( v35 < 0 )
      goto LABEL_41;
    LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v128 + 112))(v128, 3);
    v20 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
    LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v128 + 144))(v128, a9);
    v20 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
  }
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 88LL))(*a3, &v127);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v127 + 128LL))(v127, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v127 + 144LL))(v127, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v127 + 112LL))(v127, v14);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v127 + 352LL))(v127, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v102 = v127;
  v103 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v127 + 224LL);
  v104 = _bstr_t::_bstr_t((_bstr_t *)Block, L"PT1H");
  if ( *(_QWORD *)v104 )
    v105 = **(_QWORD **)v104;
  else
    v105 = 0;
  v106 = v103(v102, v105);
  v107 = (BSTR *)Block[0];
  v35 = v106;
  LODWORD(Data) = v106;
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v107 )
    {
      if ( *v107 )
      {
        SysFreeString(*v107);
        *v107 = 0;
      }
      v108 = v107[1];
      if ( v108 )
      {
        operator delete(v108);
        v107[1] = 0;
      }
      operator delete(v107);
    }
    v35 = Data;
  }
  if ( v35 < 0 )
    goto LABEL_41;
  LODWORD(Data) = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v127)(
                    v127,
                    &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                    a4);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 176LL))(
                    *a4,
                    (unsigned __int16)((a11 != 1) - 1));
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 208LL))(
                    *a4,
                    (unsigned __int16)((a12 != 1) - 1));
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 400LL))(*a4, 0xFFFFFFFFLL);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v127 + 312LL))(v127, &v131);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v131 + 96LL))(v131, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v131 + 64LL))(v131, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v131 + 80LL))(v131, 0);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 136LL))(*a3, &v138);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v138 + 96LL))(v138, 0, &v137);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  LODWORD(Data) = (**v137)(v137, &IID_IExecAction, &v134);
  v20 = Data;
  if ( (int)Data < 0 )
    goto LABEL_25;
  v109 = v134;
  v110 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v134 + 88LL);
  v111 = _bstr_t::_bstr_t((_bstr_t *)Block, a6);
  if ( *(_QWORD *)v111 )
    v112 = **(_QWORD **)v111;
  else
    v112 = 0;
  v113 = v110(v109, v112);
  v114 = (BSTR *)Block[0];
  v35 = v113;
  LODWORD(Data) = v113;
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v114 )
    {
      if ( *v114 )
      {
        SysFreeString(*v114);
        *v114 = 0;
      }
      v115 = v114[1];
      if ( v115 )
      {
        operator delete(v115);
        v114[1] = 0;
      }
      operator delete(v114);
    }
    v35 = Data;
  }
  if ( v35 < 0 )
  {
LABEL_41:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v126);
    v20 = v35;
    goto LABEL_221;
  }
  v116 = v134;
  v117 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v134 + 104LL);
  v118 = _bstr_t::_bstr_t((_bstr_t *)Block, a7);
  if ( *(_QWORD *)v118 )
    v119 = **(_QWORD **)v118;
  else
    v119 = 0;
  v120 = v117(v116, v119);
  v121 = (BSTR *)Block[0];
  v122 = v120;
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v121 )
    {
      if ( *v121 )
      {
        SysFreeString(*v121);
        *v121 = 0;
      }
      v123 = v121[1];
      if ( v123 )
      {
        operator delete(v123);
        v121[1] = 0;
      }
      operator delete(v121);
    }
    Block[0] = 0;
  }
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v126);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&psz);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v146);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v144);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v134);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v137);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v138);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v131);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v128);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v135);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v127);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v129);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v136);
  return v122;
}

```

## disassembly

```asm
0x1800613ac  mov     rax, rsp
0x1800613af  mov     [rax+10h], rbx
0x1800613b3  mov     [rax+20h], r9
0x1800613b7  mov     [rax+18h], r8
0x1800613bb  mov     [rax+8], rcx
0x1800613bf  push    rbp
0x1800613c0  push    rsi
0x1800613c1  push    rdi
0x1800613c2  push    r12
0x1800613c4  push    r13
0x1800613c6  push    r14
0x1800613c8  push    r15
0x1800613ca  lea     rbp, [rax-178h]
0x1800613d1  sub     rsp, 240h
0x1800613d8  xor     r14d, r14d
0x1800613db  movaps  xmmword ptr [rax-48h], xmm6
0x1800613df  movaps  xmmword ptr [rax-58h], xmm7
0x1800613e3  mov     r15, rcx
0x1800613e6  movaps  xmmword ptr [rax-68h], xmm8
0x1800613eb  lea     rcx, [rbp+170h+var_160]
0x1800613ef  movaps  xmmword ptr [rax-78h], xmm9
0x1800613f4  mov     r12, rdx
0x1800613f7  movaps  xmmword ptr [rax-88h], xmm10
0x1800613ff  movaps  xmmword ptr [rax-98h], xmm11
0x180061407  mov     [rbp+170h+var_1D0], r14
0x18006140b  mov     qword ptr [rsp+270h+var_210], r14
0x180061410  mov     [rsp+270h+var_220], r14
0x180061415  mov     [rbp+170h+var_1D8], r14
0x180061419  mov     [rsp+270h+var_218], r14
0x18006141e  mov     [rbp+170h+var_1F0], r14
0x180061422  mov     [rbp+170h+var_1C0], r14
0x180061426  mov     [rbp+170h+var_1C8], r14
0x18006142a  mov     [rbp+170h+var_1E0], r14
0x18006142e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180061433  lea     rcx, [rbp+170h+var_140]
0x180061437  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18006143c  lea     rcx, [rbp+170h+psz]
0x180061440  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180061445  lea     ebx, [r14+1]
0x180061449  mov     r13d, r14d
0x18006144c  cmp     dword ptr [rbp+170h+Data], ebx
0x180061452  jz      short loc_180061461
0x180061454  cmp     [rbp+170h+arg_48], ebx
0x18006145a  setnz   r13b
0x18006145e  add     r13d, ebx
0x180061461  mov     r8d, 32h ; '2'
0x180061467  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x18006146e  lea     rcx, [rbp+170h+var_160]
0x180061472  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180061477  test    al, al
0x180061479  jz      loc_1800624C7
0x18006147f  mov     r8d, 3Fh ; '?'
0x180061485  lea     rdx, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x18006148c  lea     rcx, [rbp+170h+psz]
0x180061490  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180061495  test    al, al
0x180061497  jz      loc_1800624C7
0x18006149d  mov     rsi, [rbp+170h+arg_38]
0x1800614a4  mov     [rbp+170h+var_1E4], r14d
0x1800614a8  test    rsi, rsi
0x1800614ab  jz      loc_1800615DA
0x1800614b1  lea     rdx, aS1518; "S-1-5-18"
0x1800614b8  mov     rcx, rsi
0x1800614bb  call    cs:__imp__o__wcsicmp
0x1800614c1  test    eax, eax
0x1800614c3  jz      loc_1800615DA
0x1800614c9  lea     rdx, aS1532545; "S-1-5-32-545"
0x1800614d0  mov     [rbp+170h+var_1E8], r14d
0x1800614d4  mov     rcx, rsi
0x1800614d7  call    cs:__imp__o__wcsicmp
0x1800614dd  test    eax, eax
0x1800614df  jnz     short loc_180061559
0x1800614e1  mov     rcx, [rbp+170h+var_160]
0x1800614e5  lea     r8d, [rax+29h]
0x1800614e9  mov     [rbp+170h+var_158], rcx
0x1800614ed  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x1800614f4  mov     [rcx], r14w
0x1800614f8  lea     rcx, [rbp+170h+var_160]
0x1800614fc  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180061501  test    al, al
0x180061503  jz      loc_1800624C7
0x180061509  mov     r8d, 21h ; '!'
0x18006150f  lea     rdx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180061516  lea     rcx, [rbp+170h+var_140]
0x18006151a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18006151f  test    al, al
0x180061521  jz      loc_1800624C7
0x180061527  mov     rcx, [rbp+170h+psz]
0x18006152b  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x180061532  mov     [rbp+170h+var_178], rcx
0x180061536  mov     r8d, 22h ; '"'
0x18006153c  mov     [rcx], r14w
0x180061540  lea     rcx, [rbp+170h+psz]
0x180061544  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180061549  test    al, al
0x18006154b  jz      loc_1800624C7
0x180061551  mov     [rbp+170h+var_1E4], ebx
0x180061554  jmp     loc_18006164F
0x180061559  mov     rdx, rsi
0x18006155c  lea     rcx, [rbp+170h+var_160]
0x180061560  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180061565  test    al, al
0x180061567  jz      loc_1800624C7
0x18006156d  mov     r8, rbx
0x180061570  lea     rdx, asc_18009A8D4; ")"
0x180061577  lea     rcx, [rbp+170h+var_160]
0x18006157b  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180061580  test    al, al
0x180061582  jz      loc_1800624C7
0x180061588  mov     rdx, rsi
0x18006158b  lea     rcx, [rbp+170h+var_140]
0x18006158f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180061594  test    al, al
0x180061596  jz      loc_1800624C7
0x18006159c  mov     r8d, 0Fh
0x1800615a2  lea     rdx, aEnterprisemgmt_0; "\\EnterpriseMgmt"
0x1800615a9  lea     rcx, [rbp+170h+var_140]
0x1800615ad  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800615b2  test    al, al
0x1800615b4  jz      loc_1800624C7
0x1800615ba  mov     rdx, rsi
0x1800615bd  lea     rcx, [rbp+170h+psz]
0x1800615c1  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800615c6  test    al, al
0x1800615c8  jz      loc_1800624C7
0x1800615ce  mov     r8, rbx
0x1800615d1  lea     rdx, asc_18009A8D4; ")"
0x1800615d8  jmp     short loc_18006163E
0x1800615da  mov     rcx, [rbp+170h+var_160]
0x1800615de  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x1800615e5  mov     [rbp+170h+var_158], rcx
0x1800615e9  mov     r8d, 29h ; ')'
0x1800615ef  mov     [rcx], r14w
0x1800615f3  lea     rcx, [rbp+170h+var_160]
0x1800615f7  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800615fc  test    al, al
0x1800615fe  jz      loc_1800624C7
0x180061604  mov     r8d, 21h ; '!'
0x18006160a  lea     rdx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180061611  lea     rcx, [rbp+170h+var_140]
0x180061615  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18006161a  test    al, al
0x18006161c  jz      loc_1800624C7
0x180061622  mov     rcx, [rbp+170h+psz]
0x180061626  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x18006162d  mov     [rbp+170h+var_178], rcx
0x180061631  mov     r8d, 22h ; '"'
0x180061637  mov     [rbp+170h+var_1E8], ebx
0x18006163a  mov     [rcx], r14w
0x18006163e  lea     rcx, [rbp+170h+psz]
0x180061642  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180061647  test    al, al
0x180061649  jz      loc_1800624C7
0x18006164f  mov     r8, r15
0x180061652  call    CoCreateTaskScheduler
0x180061657  mov     dword ptr [rbp+170h+Data], eax
0x18006165d  lea     rcx, aCreatetask; "CreateTask"
0x180061664  mov     [rsp+270h+var_230], rcx
0x180061669  lea     rcx, [rbp+170h+Data]
0x180061670  mov     [rsp+270h+var_228], rcx
0x180061675  test    eax, eax
0x180061677  jns     short loc_1800616C0
0x180061679  lea     r8, a22cocreatetask; "22CoCreateTaskScheduler2"
0x180061680  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180061687  lea     rax, [rbp+170h+Data]
0x18006168e  mov     r9d, 4; dwType
0x180061694  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006169b  mov     [rsp+270h+cbData], r9d; cbData
0x1800616a0  mov     [rsp+270h+lpData], rax; lpData
0x1800616a5  call    cs:__imp_RegSetKeyValueW
0x1800616ab  mov     ebx, dword ptr [rbp+170h+Data]
0x1800616b1  lea     rcx, [rsp+270h+var_230]; this
0x1800616b6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800616bb  jmp     loc_1800624CC
0x1800616c0  mov     rdi, [r15]
0x1800616c3  lea     rcx, [rbp+170h+pvarg]; pvarg
0x1800616ca  mov     rax, [rdi]
0x1800616cd  mov     rbx, [rax+50h]
0x1800616d1  call    cs:__imp_VariantInit
0x1800616d7  movups  xmm10, xmmword ptr [rbp+170h+pvarg]
0x1800616df  lea     rcx, [rbp+170h+var_100]; pvarg
0x1800616e3  movsd   xmm11, qword ptr [rbp+170h+pvarg+10h]
0x1800616ec  call    cs:__imp_VariantInit
0x1800616f2  movups  xmm8, xmmword ptr [rbp+170h+var_100]
0x1800616f7  lea     rcx, [rbp+170h+var_1B8]; pvarg
0x1800616fb  movsd   xmm9, qword ptr [rbp+170h+var_100+10h]
0x180061704  call    cs:__imp_VariantInit
0x18006170a  movups  xmm6, xmmword ptr [rbp+170h+var_1B8]
0x18006170e  lea     rcx, [rsp+270h+var_210+8]; pvarg
0x180061713  movsd   xmm7, qword ptr [rbp+170h+var_1B8+10h]
0x180061718  call    cs:__imp_VariantInit
0x18006171e  movups  xmm0, xmmword ptr [rsp+270h+var_210+8]
0x180061723  lea     rax, [rbp+170h+var_D0]
0x18006172a  mov     rcx, rdi
0x18006172d  movsd   xmm1, [rsp+270h+var_1F8]
0x180061733  lea     r9, [rbp+170h+var_B0]
0x18006173a  mov     [rsp+270h+lpData], rax
0x18006173f  lea     r8, [rbp+170h+var_120]
0x180061743  mov     rax, rbx
0x180061746  movaps  [rbp+170h+var_1A0], xmm0
0x18006174a  lea     rdx, [rbp+170h+var_1A0]
0x18006174e  movaps  [rbp+170h+var_D0], xmm10
0x180061756  movsd   [rbp+170h+var_C0], xmm11
0x18006175f  movaps  [rbp+170h+var_B0], xmm8
0x180061767  movsd   [rbp+170h+var_A0], xmm9
0x180061770  movaps  [rbp+170h+var_120], xmm6
0x180061774  movsd   [rbp+170h+var_110], xmm7
0x180061779  movsd   [rbp+170h+var_190], xmm1
0x18006177e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061783  lea     rcx, [rsp+270h+var_210+8]; this
0x180061788  mov     dword ptr [rbp+170h+Data], eax
0x18006178e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180061793  lea     rcx, [rbp+170h+var_1B8]; this
0x180061797  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006179c  lea     rcx, [rbp+170h+var_100]; this
0x1800617a0  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800617a5  lea     rcx, [rbp+170h+pvarg]; this
0x1800617ac  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800617b1  cmp     dword ptr [rbp+170h+Data], r14d
0x1800617b8  jge     short loc_1800617C6
0x1800617ba  lea     r8, a23connect; "23Connect"
0x1800617c1  jmp     loc_180061680
0x1800617c6  mov     rbx, [r15]
0x1800617c9  lea     rdx, asc_18007FF94; "\\"
0x1800617d0  lea     rcx, [rsp+270h+Block]; this
0x1800617d5  mov     rax, [rbx]
0x1800617d8  mov     rdi, [rax+38h]
0x1800617dc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800617e1  mov     rcx, [rax]
0x1800617e4  test    rcx, rcx
0x1800617e7  jz      short loc_1800617EE
0x1800617e9  mov     rdx, [rcx]
0x1800617ec  jmp     short loc_1800617F1
0x1800617ee  mov     rdx, r14
0x1800617f1  lea     r8, [rbp+170h+var_1D0]
0x1800617f5  mov     rcx, rbx
0x1800617f8  mov     rax, rdi
0x1800617fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061800  mov     rbx, [rsp+270h+Block]
0x180061805  mov     edi, eax
0x180061807  mov     dword ptr [rbp+170h+Data], eax
0x18006180d  test    rbx, rbx
0x180061810  jz      short loc_18006185A
0x180061812  or      eax, 0FFFFFFFFh
0x180061815  lock xadd [rbx+10h], eax
0x18006181a  cmp     eax, 1
0x18006181d  jnz     short loc_180061854
0x18006181f  test    rbx, rbx
0x180061822  jz      short loc_180061854
0x180061824  mov     rcx, [rbx]; bstrString
0x180061827  test    rcx, rcx
0x18006182a  jz      short loc_180061835
0x18006182c  call    cs:__imp_SysFreeString
0x180061832  mov     [rbx], r14
0x180061835  mov     rcx, [rbx+8]; Block
0x180061839  test    rcx, rcx
0x18006183c  jz      short loc_180061847
0x18006183e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061843  mov     [rbx+8], r14
0x180061847  mov     edx, 18h
0x18006184c  mov     rcx, rbx; Block
0x18006184f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061854  mov     edi, dword ptr [rbp+170h+Data]
0x18006185a  test    edi, edi
0x18006185c  jns     short loc_18006186F
0x18006185e  lea     rcx, [rsp+270h+var_230]; this
0x180061863  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180061868  mov     ebx, edi
0x18006186a  jmp     loc_1800624CC
0x18006186f  mov     rbx, [rbp+170h+var_1D0]
0x180061873  lea     rax, aSprootfolderGe; "spRootFolder->GetFolder()"
0x18006187a  mov     rdx, [rbp+170h+var_140]; unsigned __int16 *
0x18006187e  lea     rcx, [rsp+270h+Block]; this
0x180061883  mov     qword ptr [rbp+170h+var_1B8], rax
0x180061887  lea     rax, [rbp+170h+Data]
0x18006188e  mov     qword ptr [rbp+170h+var_1B8+8], rax
0x180061892  mov     rax, [rbx]
0x180061895  mov     rdi, [rax+48h]
0x180061899  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006189e  mov     rdx, [rax]
0x1800618a1  test    rdx, rdx
0x1800618a4  jz      short loc_1800618AB
0x1800618a6  mov     rdx, [rdx]
0x1800618a9  jmp     short loc_1800618AE
0x1800618ab  mov     rdx, r14
0x1800618ae  lea     r8, [rsp+270h+var_210]
0x1800618b3  mov     rcx, rbx
0x1800618b6  mov     rax, rdi
0x1800618b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800618be  mov     rbx, [rsp+270h+Block]
0x1800618c3  mov     dword ptr [rbp+170h+Data], eax
0x1800618c9  test    rbx, rbx
0x1800618cc  jz      short loc_180061910
0x1800618ce  or      eax, 0FFFFFFFFh
0x1800618d1  lock xadd [rbx+10h], eax
0x1800618d6  cmp     eax, 1
0x1800618d9  jnz     short loc_180061910
0x1800618db  test    rbx, rbx
0x1800618de  jz      short loc_180061910
0x1800618e0  mov     rcx, [rbx]; bstrString
  ... truncated ...
```
