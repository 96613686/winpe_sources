# CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)

- ea: `0x1800d820c`
- end: `0x1800d9355`
- name: `?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z`
- size: `4425`
- prototype: ``
- caller_count: `8`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800dadec`
- `0x1800db400`
- `0x1800db804`
- `0x1800dc068`
- `0x1800dc828`
- `0x1800dd018`
- `0x1800dd734`
- `0x1800e03f0`

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
- `0x1800d820c`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d831a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d833c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d831a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d833c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d86b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8775`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8848`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d892e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8a04`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8b2b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8c55`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8cfb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8dba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8f6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d91cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d926b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d86b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8775`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8848`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d892e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8a04`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8b2b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8c55`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8cfb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8dba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d8f6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d91cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d926b`
- `OLEAUT32!__imp_VariantInit` at `0x1800d8541`
- `OLEAUT32!__imp_VariantInit` at `0x1800d8562`
- `OLEAUT32!__imp_VariantInit` at `0x1800d8580`
- `OLEAUT32!__imp_VariantInit` at `0x1800d8599`
- `OLEAUT32!__imp_VariantInit` at `0x1800d8541`
- `OLEAUT32!__imp_VariantInit` at `0x1800d8562`
- `OLEAUT32!__imp_VariantInit` at `0x1800d8580`
- `OLEAUT32!__imp_VariantInit` at `0x1800d8599`
- `OLEAUT32!__imp_VariantClear` at `0x1800d887f`
- `OLEAUT32!__imp_VariantClear` at `0x1800d8a3b`
- `OLEAUT32!__imp_VariantClear` at `0x1800d887f`
- `OLEAUT32!__imp_VariantClear` at `0x1800d8a3b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800d850e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800d850e`

## string_xrefs

- `0x1800d84c6`: `CreateTask`
- `0x1800d84e2`: `22CoCreateTaskScheduler2`

## pseudocode

```c
__int64 CreateTask(
        LPVOID *a1,
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
  _QWORD *v13; // r14
  unsigned int v15; // r12d
  char *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  const wchar_t *v19; // rdx
  const WCHAR *v20; // r8
  unsigned int v21; // ebx
  LPVOID v22; // rdi
  __int64 (__fastcall *v23)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v24; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v26; // xmm8
  IRecordInfo *v27; // xmm9_8
  __int128 v28; // xmm6
  IRecordInfo *v29; // xmm7_8
  LPVOID v30; // rbx
  __int64 (__fastcall *v31)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v32; // rax
  __int64 v33; // rdx
  int v34; // eax
  BSTR *v35; // rbx
  int v36; // edi
  BSTR v37; // rcx
  __int64 v38; // rbx
  __int64 (__fastcall *v39)(__int64, _QWORD *, struct IUnknown **); // rdi
  _QWORD *v40; // rdx
  int v41; // eax
  BSTR *v42; // rbx
  BSTR v43; // rcx
  __int64 v44; // rbx
  __int64 (__fastcall *v45)(__int64, _QWORD *, VARIANTARG *, struct IUnknown **); // rdi
  __int128 v46; // xmm6
  IRecordInfo *v47; // xmm7_8
  _QWORD *v48; // rdx
  int v49; // eax
  BSTR *v50; // rbx
  BSTR v51; // rcx
  struct IUnknown *v52; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r14
  _QWORD *v54; // rdx
  int v55; // eax
  BSTR *v56; // rbx
  BSTR v57; // rcx
  struct IUnknown *v58; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // r14
  __int128 v60; // xmm6
  IRecordInfo *v61; // xmm7_8
  _bstr_t *v62; // rax
  __int64 v63; // rdx
  int v64; // eax
  BSTR *v65; // rbx
  BSTR v66; // rcx
  __int64 v67; // rbx
  __int64 (__fastcall *v68)(__int64, __int64); // rdi
  _bstr_t *v69; // rax
  __int64 v70; // rdx
  int v71; // eax
  BSTR *v72; // rbx
  BSTR v73; // rcx
  __int64 v74; // rdi
  __int64 (__fastcall *v75)(__int64, VARIANTARG *); // rbx
  _variant_t *v76; // rax
  IRecordInfo *v77; // xmm1_8
  __int64 *v78; // rbx
  __int64 v79; // rax
  __int64 (__fastcall *v80)(__int64 *, __int64); // rdi
  _bstr_t *v81; // rax
  __int64 v82; // rdx
  int v83; // eax
  BSTR *v84; // rbx
  BSTR v85; // rcx
  __int64 (__fastcall *v86)(__int64 *, __int64); // rdi
  _bstr_t *v87; // rax
  __int64 v88; // rdx
  int v89; // eax
  BSTR *v90; // rbx
  BSTR v91; // rcx
  __int64 (__fastcall *v92)(__int64 *, __int64); // rdi
  _bstr_t *v93; // rax
  __int64 v94; // rdx
  int v95; // eax
  BSTR *v96; // rbx
  BSTR v97; // rcx
  __int64 v98; // rbx
  __int64 (__fastcall *v99)(__int64, __int64); // rdi
  _bstr_t *v100; // rax
  __int64 v101; // rdx
  int v102; // eax
  BSTR *v103; // rbx
  BSTR v104; // rcx
  __int64 v105; // rbx
  __int64 (__fastcall *v106)(__int64, __int64); // rdi
  _bstr_t *v107; // rax
  __int64 v108; // rdx
  int v109; // eax
  BSTR *v110; // rbx
  BSTR v111; // rcx
  __int64 v112; // rbx
  __int64 (__fastcall *v113)(__int64, __int64); // rdi
  _bstr_t *v114; // rax
  __int64 v115; // rdx
  int v116; // eax
  BSTR *v117; // rbx
  BSTR v118; // rcx
  void *Block[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v121[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v122; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v123; // [rsp+60h] [rbp-A8h] BYREF
  struct IUnknown *v124; // [rsp+68h] [rbp-A0h] BYREF
  int v125; // [rsp+70h] [rbp-98h]
  int v126; // [rsp+74h] [rbp-94h]
  __int64 v127; // [rsp+78h] [rbp-90h] BYREF
  __int64 v128; // [rsp+80h] [rbp-88h] BYREF
  __int64 v129; // [rsp+88h] [rbp-80h] BYREF
  __int64 v130; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG v131; // [rsp+98h] [rbp-70h] BYREF
  __int64 (__fastcall ***v132)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-58h] BYREF
  __int64 v133; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v134; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v135; // [rsp+D8h] [rbp-30h] BYREF
  _WORD *v136; // [rsp+F8h] [rbp-10h] BYREF
  _WORD *v137; // [rsp+100h] [rbp-8h]
  unsigned __int16 *v138; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 *v139; // [rsp+120h] [rbp+18h]
  unsigned __int16 *v140[4]; // [rsp+138h] [rbp+30h] BYREF
  __int128 v141; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v142; // [rsp+168h] [rbp+60h]
  VARIANTARG v143; // [rsp+178h] [rbp+70h] BYREF
  VARIANTARG pvarg; // [rsp+190h] [rbp+88h] BYREF
  __int128 v145; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v146; // [rsp+1B8h] [rbp+B0h]
  __int128 v147; // [rsp+1C8h] [rbp+C0h] BYREF
  IRecordInfo *v148; // [rsp+1D8h] [rbp+D0h]
  __int64 Data; // [rsp+2E8h] [rbp+1E0h] BYREF
  va_list Dataa; // [rsp+2E8h] [rbp+1E0h]
  va_list va1; // [rsp+2F0h] [rbp+1E8h] BYREF

  va_start(va1, a12);
  va_start(Dataa, a12);
  Data = va_arg(va1, _QWORD);
  v13 = a3;
  v130 = 0;
  v124 = 0;
  v122 = 0;
  v129 = 0;
  v123 = 0;
  v127 = 0;
  v133 = 0;
  v132 = 0;
  v128 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v138);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v140);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v136);
  v15 = 0;
  if ( (_DWORD)Data != 1 )
  {
    LOBYTE(v15) = a10 != 1;
    ++v15;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v138,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FA;;;",
                           50)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v136,
                           L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;LS)(A;OICI;GA;;;",
                           63) )
  {
    goto LABEL_211;
  }
  v126 = 0;
  if ( a8 && (unsigned int)_o__wcsicmp(a8, L"S-1-5-18") )
  {
    v125 = 0;
    if ( !(unsigned int)_o__wcsicmp(a8, L"S-1-5-32-545") )
    {
      v139 = v138;
      *v138 = 0;
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                              &v138,
                              L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                              41) )
      {
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                v140,
                                L"\\Microsoft\\Windows\\EnterpriseMgmt",
                                33) )
        {
          v137 = v136;
          *v136 = 0;
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                  &v136,
                                  L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
                                  34) )
          {
            v126 = 1;
            goto LABEL_22;
          }
        }
      }
LABEL_211:
      v21 = -2147024882;
      goto LABEL_212;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v138,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v138,
                             L")",
                             1)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v140,
                             a8)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v140,
                             L"\\EnterpriseMgmt",
                             15)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v136,
                             a8) )
    {
      goto LABEL_211;
    }
    v18 = 1;
    v19 = L")";
  }
  else
  {
    v139 = v138;
    *v138 = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v138,
                             L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)",
                             41)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v140,
                             L"\\Microsoft\\Windows\\EnterpriseMgmt",
                             33) )
    {
      goto LABEL_211;
    }
    v19 = L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)";
    v137 = v136;
    v18 = 34;
    v125 = 1;
    *v136 = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v136,
                           v19,
                           v18) )
    goto LABEL_211;
LABEL_22:
  LODWORD(Data) = CoCreateTaskScheduler(v17, v16, a1);
  v121[0] = "CreateTask";
  va_copy((va_list)&v121[1], Dataa);
  if ( (int)Data >= 0 )
  {
    v22 = *a1;
    v23 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*a1 + 80LL);
    VariantInit(&pvarg);
    v24 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v143);
    v26 = *(_OWORD *)&v143.vt;
    v27 = v143.pRecInfo;
    VariantInit(&v134);
    v28 = *(_OWORD *)&v134.vt;
    v29 = v134.pRecInfo;
    VariantInit(&v131);
    v135 = v131;
    v145 = v24;
    v146 = pRecInfo;
    v147 = v26;
    v148 = v27;
    v141 = v28;
    v142 = v29;
    LODWORD(Data) = v23(v22, &v135, &v141, &v147, &v145);
    _variant_t::~_variant_t((_variant_t *)&v131);
    _variant_t::~_variant_t((_variant_t *)&v134);
    _variant_t::~_variant_t((_variant_t *)&v143);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( (int)Data < 0 )
    {
      v20 = L"23Connect";
      goto LABEL_24;
    }
    v30 = *a1;
    v31 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)*a1 + 56LL);
    v32 = _bstr_t::_bstr_t((_bstr_t *)Block, L"\\");
    if ( *(_QWORD *)v32 )
      v33 = **(_QWORD **)v32;
    else
      v33 = 0;
    v34 = v31(v30, v33, &v130);
    v35 = (BSTR *)Block[0];
    v36 = v34;
    LODWORD(Data) = v34;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v35 )
      {
        if ( *v35 )
        {
          SysFreeString(*v35);
          *v35 = 0;
        }
        v37 = v35[1];
        if ( v37 )
        {
          operator delete(v37);
          v35[1] = 0;
        }
        operator delete(v35);
      }
      v36 = Data;
    }
    if ( v36 < 0 )
      goto LABEL_41;
    v38 = v130;
    *(_QWORD *)&v134.vt = "spRootFolder->GetFolder()";
    va_copy(v134.pcVal, Dataa);
    v39 = *(__int64 (__fastcall **)(__int64, _QWORD *, struct IUnknown **))(*(_QWORD *)v130 + 72LL);
    v40 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)Block, v140[0]);
    if ( v40 )
      v40 = (_QWORD *)*v40;
    v41 = v39(v38, v40, &v124);
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
      v44 = v130;
      v45 = *(__int64 (__fastcall **)(__int64, _QWORD *, VARIANTARG *, struct IUnknown **))(*(_QWORD *)v130 + 88LL);
      v131.vt = 0;
      ATL::CComVariant::operator=(&v131, v136);
      v46 = *(_OWORD *)&v131.vt;
      v47 = v131.pRecInfo;
      v48 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)Block, v140[0]);
      if ( v48 )
        v48 = (_QWORD *)*v48;
      *(_OWORD *)&v135.vt = v46;
      v135.pRecInfo = v47;
      v49 = v45(v44, v48, &v135, &v124);
      v50 = (BSTR *)Block[0];
      LODWORD(Data) = v49;
      if ( Block[0] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v50 )
        {
          if ( *v50 )
          {
            SysFreeString(*v50);
            *v50 = 0;
          }
          v51 = v50[1];
          if ( v51 )
          {
            operator delete(v51);
            v50[1] = 0;
          }
          operator delete(v50);
        }
        Block[0] = 0;
      }
      VariantClear(&v131);
      v21 = Data;
      if ( (int)Data < 0 )
      {
LABEL_65:
        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v134);
        goto LABEL_25;
      }
    }
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v134);
    if ( a5 )
    {
      v52 = v124;
      *(_QWORD *)&v134.vt = "spEnterpriseMgmtFolder->GetFolder()";
      va_copy(v134.pcVal, Dataa);
      QueryInterface = v124->lpVtbl[3].QueryInterface;
      v54 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)Block, a5);
      if ( v54 )
        v54 = (_QWORD *)*v54;
      v55 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *, struct IUnknown **))QueryInterface)(v52, v54, a2);
      v56 = (BSTR *)Block[0];
      LODWORD(Data) = v55;
      if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v56 )
      {
        if ( *v56 )
        {
          SysFreeString(*v56);
          *v56 = 0;
        }
        v57 = v56[1];
        if ( v57 )
        {
          operator delete(v57);
          v56[1] = 0;
        }
        operator delete(v56);
      }
      if ( (unsigned int)(Data + 2147024894) <= 1 )
      {
        v58 = v124;
        Release = v124->lpVtbl[3].Release;
        v131.vt = 0;
        ATL::CComVariant::operator=(&v131, v136);
        v60 = *(_OWORD *)&v131.vt;
        v61 = v131.pRecInfo;
        v62 = _bstr_t::_bstr_t((_bstr_t *)Block, a5);
        if ( *(_QWORD *)v62 )
          v63 = **(_QWORD **)v62;
        else
          v63 = 0;
        *(_OWORD *)&v135.vt = v60;
        v135.pRecInfo = v61;
        v64 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, VARIANTARG *, struct IUnknown **))Release)(
                v58,
                v63,
                &v135,
                a2);
        v65 = (BSTR *)Block[0];
        LODWORD(Data) = v64;
        if ( Block[0] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v65 )
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
          Block[0] = 0;
        }
        VariantClear(&v131);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_65;
      }
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v134);
      v13 = a3;
    }
    else if ( *a2 != v124 )
    {
      ATL::AtlComPtrAssign(a2, v124);
    }
    LODWORD(Data) = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD *))(*(_QWORD *)*a1 + 72LL))(*a1, 0, v13);
    v21 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
    LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v13 + 56LL))(*v13, &v129);
    v21 = Data;
    if ( (int)Data < 0 )
      goto LABEL_25;
    v67 = v129;
    v68 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v129 + 80LL);
    v69 = _bstr_t::_bstr_t((_bstr_t *)Block, L"Microsoft Corporation");
    if ( *(_QWORD *)v69 )
      v70 = **(_QWORD **)v69;
    else
      v70 = 0;
    v71 = v68(v67, v70);
    v72 = (BSTR *)Block[0];
    LODWORD(Data) = v71;
    v36 = v71;
    if ( Block[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v72 )
      {
        if ( *v72 )
        {
          SysFreeString(*v72);
          *v72 = 0;
        }
        v73 = v72[1];
        if ( v73 )
        {
          operator delete(v73);
          v72[1] = 0;
        }
        operator delete(v72);
      }
      v36 = Data;
    }
    if ( v36 >= 0 )
    {
      v74 = v129;
      v75 = *(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v129 + 176LL);
      v76 = _variant_t::_variant_t((_variant_t *)&v141, v138);
      v77 = (IRecordInfo *)*((_QWORD *)v76 + 2);
      *(_OWORD *)&v135.vt = *(_OWORD *)v76;
      v135.pRecInfo = v77;
      LODWORD(Data) = v75(v74, &v135);
      _variant_t::~_variant_t((_variant_t *)&v141);
      v21 = Data;
      if ( (int)Data < 0 )
        goto LABEL_25;
      LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*v13 + 120LL))(*v13, &v123);
      v21 = Data;
      if ( (int)Data < 0 )
        goto LABEL_25;
      v78 = v123;
      v79 = *v123;
      if ( v125 )
      {
        v80 = *(__int64 (__fastcall **)(__int64 *, __int64))(v79 + 128);
        v81 = _bstr_t::_bstr_t((_bstr_t *)Block, "SYSTEM");
        if ( *(_QWORD *)v81 )
          v82 = **(_QWORD **)v81;
        else
          v82 = 0;
        v83 = v80(v78, v82);
        v84 = (BSTR *)Block[0];
        v36 = v83;
        LODWORD(Data) = v83;
        if ( Block[0] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v84 )
          {
            if ( *v84 )
            {
              SysFreeString(*v84);
              *v84 = 0;
            }
            v85 = v84[1];
            if ( v85 )
            {
              operator delete(v85);
              v84[1] = 0;
            }
            operator delete(v84);
          }
          v36 = Data;
        }
        if ( v36 < 0 )
          goto LABEL_41;
      }
      else if ( v126 )
      {
        v86 = *(__int64 (__fastcall **)(__int64 *, __int64))(v79 + 128);
        v87 = _bstr_t::_bstr_t((_bstr_t *)Block, L"S-1-5-32-545");
        if ( *(_QWORD *)v87 )
          v88 = **(_QWORD **)v87;
        else
          v88 = 0;
        v89 = v86(v78, v88);
        v90 = (BSTR *)Block[0];
        v36 = v89;
        LODWORD(Data) = v89;
        if ( Block[0] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v90 )
          {
            if ( *v90 )
            {
              SysFreeString(*v90);
              *v90 = 0;
            }
            v91 = v90[1];
            if ( v91 )
            {
              operator delete(v91);
              v90[1] = 0;
            }
            operator delete(v90);
          }
          v36 = Data;
        }
        if ( v36 < 0 )
          goto LABEL_41;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v123 + 144))(v123, 1);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
      }
      else
      {
        v92 = *(__int64 (__fastcall **)(__int64 *, __int64))(v79 + 96);
        v93 = _bstr_t::_bstr_t((_bstr_t *)Block, a8);
        if ( *(_QWORD *)v93 )
          v94 = **(_QWORD **)v93;
        else
          v94 = 0;
        v95 = v92(v78, v94);
        v96 = (BSTR *)Block[0];
        v36 = v95;
        LODWORD(Data) = v95;
        if ( Block[0] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v96 )
          {
            if ( *v96 )
            {
              SysFreeString(*v96);
              *v96 = 0;
            }
            v97 = v96[1];
            if ( v97 )
            {
              operator delete(v97);
              v96[1] = 0;
            }
            operator delete(v96);
          }
          v36 = Data;
        }
        if ( v36 < 0 )
          goto LABEL_41;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v123 + 112))(v123, 3);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v123 + 144))(v123, a9);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
      }
      LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v13 + 88LL))(*v13, &v122);
      v21 = Data;
      if ( (int)Data < 0 )
        goto LABEL_25;
      LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v122 + 128LL))(v122, 0);
      v21 = Data;
      if ( (int)Data < 0 )
        goto LABEL_25;
      LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v122 + 144LL))(v122, 0);
      v21 = Data;
      if ( (int)Data < 0 )
        goto LABEL_25;
      LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v122 + 112LL))(v122, v15);
      v21 = Data;
      if ( (int)Data < 0 )
        goto LABEL_25;
      LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v122 + 352LL))(v122, 0);
      v21 = Data;
      if ( (int)Data < 0 )
        goto LABEL_25;
      v98 = v122;
      v99 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v122 + 224LL);
      v100 = _bstr_t::_bstr_t((_bstr_t *)Block, L"PT1H");
      if ( *(_QWORD *)v100 )
        v101 = **(_QWORD **)v100;
      else
        v101 = 0;
      v102 = v99(v98, v101);
      v103 = (BSTR *)Block[0];
      v36 = v102;
      LODWORD(Data) = v102;
      if ( Block[0] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v103 )
        {
          if ( *v103 )
          {
            SysFreeString(*v103);
            *v103 = 0;
          }
          v104 = v103[1];
          if ( v104 )
          {
            operator delete(v104);
            v103[1] = 0;
          }
          operator delete(v103);
        }
        v36 = Data;
      }
      if ( v36 >= 0 )
      {
        LODWORD(Data) = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v122)(
                          v122,
                          &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                          a4);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 176LL))(
                          *a4,
                          (unsigned __int16)((a11 != 1) - 1));
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 208LL))(
                          *a4,
                          (unsigned __int16)((a12 != 1) - 1));
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 400LL))(*a4, 0xFFFFFFFFLL);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v122 + 312LL))(v122, &v127);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v127 + 96LL))(v127, 0);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v127 + 64LL))(v127, 0);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v127 + 80LL))(v127, 0);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v13 + 136LL))(*v13, &v133);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v133 + 96LL))(v133, 0, &v132);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        LODWORD(Data) = (**v132)(v132, &IID_IExecAction, &v128);
        v21 = Data;
        if ( (int)Data < 0 )
          goto LABEL_25;
        v105 = v128;
        v106 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v128 + 88LL);
        v107 = _bstr_t::_bstr_t((_bstr_t *)Block, a6);
        if ( *(_QWORD *)v107 )
          v108 = **(_QWORD **)v107;
        else
          v108 = 0;
        v109 = v106(v105, v108);
        v110 = (BSTR *)Block[0];
        v36 = v109;
        LODWORD(Data) = v109;
        if ( Block[0] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v110 )
          {
            if ( *v110 )
            {
              SysFreeString(*v110);
              *v110 = 0;
            }
            v111 = v110[1];
            if ( v111 )
            {
              operator delete(v111);
              v110[1] = 0;
            }
            operator delete(v110);
          }
          v36 = Data;
        }
        if ( v36 >= 0 )
        {
          v112 = v128;
          v113 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v128 + 104LL);
          v114 = _bstr_t::_bstr_t((_bstr_t *)Block, a7);
          v115 = *(_QWORD *)v114 ? **(_QWORD **)v114 : 0LL;
          v116 = v113(v112, v115);
          v117 = (BSTR *)Block[0];
          v36 = v116;
          if ( Block[0] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v117 )
            {
              if ( *v117 )
              {
                SysFreeString(*v117);
                *v117 = 0;
              }
              v118 = v117[1];
              if ( v118 )
              {
                operator delete(v118);
                v117[1] = 0;
              }
              operator delete(v117);
            }
            Block[0] = 0;
          }
        }
      }
    }
LABEL_41:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v121);
    v21 = v36;
    goto LABEL_212;
  }
  v20 = L"22CoCreateTaskScheduler2";
LABEL_24:
  RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, v20, 4u, Dataa, 4u);
  v21 = Data;
LABEL_25:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v121);
LABEL_212:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v136);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v140);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v138);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v128);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v132);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v133);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v127);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v123);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v129);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v122);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v124);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v130);
  return v21;
}

```

## disassembly

```asm
0x1800d820c  mov     rax, rsp
0x1800d820f  mov     [rax+8], rbx
0x1800d8213  mov     [rax+20h], r9
0x1800d8217  mov     [rax+18h], r8
0x1800d821b  push    rbp
0x1800d821c  push    rsi
0x1800d821d  push    rdi
0x1800d821e  push    r12
0x1800d8220  push    r13
0x1800d8222  push    r14
0x1800d8224  push    r15
0x1800d8226  lea     rbp, [rax-178h]
0x1800d822d  sub     rsp, 240h
0x1800d8234  xor     ebx, ebx
0x1800d8236  movaps  xmmword ptr [rax-48h], xmm6
0x1800d823a  movaps  xmmword ptr [rax-58h], xmm7
0x1800d823e  mov     r13, rcx
0x1800d8241  movaps  xmmword ptr [rax-68h], xmm8
0x1800d8246  lea     rcx, [rbp+170h+var_160]
0x1800d824a  movaps  xmmword ptr [rax-78h], xmm9
0x1800d824f  mov     r14, r8
0x1800d8252  movaps  xmmword ptr [rax-88h], xmm10
0x1800d825a  mov     r15, rdx
0x1800d825d  movaps  xmmword ptr [rax-98h], xmm11
0x1800d8265  mov     [rbp+170h+var_1E8], rbx
0x1800d8269  mov     [rsp+270h+var_210], rbx
0x1800d826e  mov     [rsp+270h+var_220], rbx
0x1800d8273  mov     [rbp+170h+var_1F0], rbx
0x1800d8277  mov     [rsp+270h+var_218], rbx
0x1800d827c  mov     [rsp+270h+var_200], rbx
0x1800d8281  mov     [rbp+170h+var_1C0], rbx
0x1800d8285  mov     [rbp+170h+var_1C8], rbx
0x1800d8289  mov     [rsp+270h+var_1F8], rbx
0x1800d828e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800d8293  lea     rcx, [rbp+170h+var_140]
0x1800d8297  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800d829c  lea     rcx, [rbp+170h+var_180]
0x1800d82a0  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800d82a5  lea     edi, [rbx+1]
0x1800d82a8  mov     r12d, ebx
0x1800d82ab  cmp     dword ptr [rbp+170h+Data], edi
0x1800d82b1  jz      short loc_1800D82C0
0x1800d82b3  cmp     [rbp+170h+arg_48], edi
0x1800d82b9  setnz   r12b
0x1800d82bd  add     r12d, edi
0x1800d82c0  mov     r8d, 32h ; '2'
0x1800d82c6  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x1800d82cd  lea     rcx, [rbp+170h+var_160]
0x1800d82d1  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d82d6  test    al, al
0x1800d82d8  jz      loc_1800D92A3
0x1800d82de  mov     r8d, 3Fh ; '?'
0x1800d82e4  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x1800d82eb  lea     rcx, [rbp+170h+var_180]
0x1800d82ef  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d82f4  test    al, al
0x1800d82f6  jz      loc_1800D92A3
0x1800d82fc  mov     rsi, [rbp+170h+arg_38]
0x1800d8303  mov     dword ptr [rsp+270h+var_208+4], ebx
0x1800d8307  test    rsi, rsi
0x1800d830a  jz      loc_1800D8444
0x1800d8310  lea     rdx, aS1518; "S-1-5-18"
0x1800d8317  mov     rcx, rsi
0x1800d831a  call    cs:__imp__o__wcsicmp
0x1800d8321  nop     dword ptr [rax+rax+00h]
0x1800d8326  test    eax, eax
0x1800d8328  jz      loc_1800D8444
0x1800d832e  lea     rdx, aS1532545; "S-1-5-32-545"
0x1800d8335  mov     dword ptr [rsp+270h+var_208], ebx
0x1800d8339  mov     rcx, rsi
0x1800d833c  call    cs:__imp__o__wcsicmp
0x1800d8343  nop     dword ptr [rax+rax+00h]
0x1800d8348  test    eax, eax
0x1800d834a  jnz     short loc_1800D83C3
0x1800d834c  mov     rcx, [rbp+170h+var_160]
0x1800d8350  lea     r8d, [rax+29h]
0x1800d8354  mov     [rbp+170h+var_158], rcx
0x1800d8358  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x1800d835f  mov     [rcx], bx
0x1800d8362  lea     rcx, [rbp+170h+var_160]
0x1800d8366  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d836b  test    al, al
0x1800d836d  jz      loc_1800D92A3
0x1800d8373  mov     r8d, 21h ; '!'
0x1800d8379  lea     rdx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800d8380  lea     rcx, [rbp+170h+var_140]
0x1800d8384  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d8389  test    al, al
0x1800d838b  jz      loc_1800D92A3
0x1800d8391  mov     rcx, [rbp+170h+var_180]
0x1800d8395  lea     rdx, aDAOiciGaBaAOic_1; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x1800d839c  mov     [rbp+170h+var_178], rcx
0x1800d83a0  mov     r8d, 22h ; '"'
0x1800d83a6  mov     [rcx], bx
0x1800d83a9  lea     rcx, [rbp+170h+var_180]
0x1800d83ad  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d83b2  test    al, al
0x1800d83b4  jz      loc_1800D92A3
0x1800d83ba  mov     dword ptr [rsp+270h+var_208+4], edi
0x1800d83be  jmp     loc_1800D84B8
0x1800d83c3  mov     rdx, rsi
0x1800d83c6  lea     rcx, [rbp+170h+var_160]
0x1800d83ca  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800d83cf  test    al, al
0x1800d83d1  jz      loc_1800D92A3
0x1800d83d7  mov     r8, rdi
0x1800d83da  lea     rdx, asc_18012AA8C; ")"
0x1800d83e1  lea     rcx, [rbp+170h+var_160]
0x1800d83e5  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d83ea  test    al, al
0x1800d83ec  jz      loc_1800D92A3
0x1800d83f2  mov     rdx, rsi
0x1800d83f5  lea     rcx, [rbp+170h+var_140]
0x1800d83f9  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800d83fe  test    al, al
0x1800d8400  jz      loc_1800D92A3
0x1800d8406  mov     r8d, 0Fh
0x1800d840c  lea     rdx, aEnterprisemgmt_0; "\\EnterpriseMgmt"
0x1800d8413  lea     rcx, [rbp+170h+var_140]
0x1800d8417  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d841c  test    al, al
0x1800d841e  jz      loc_1800D92A3
0x1800d8424  mov     rdx, rsi
0x1800d8427  lea     rcx, [rbp+170h+var_180]
0x1800d842b  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800d8430  test    al, al
0x1800d8432  jz      loc_1800D92A3
0x1800d8438  mov     r8, rdi
0x1800d843b  lea     rdx, asc_18012AA8C; ")"
0x1800d8442  jmp     short loc_1800D84A7
0x1800d8444  mov     rcx, [rbp+170h+var_160]
0x1800d8448  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x1800d844f  mov     [rbp+170h+var_158], rcx
0x1800d8453  mov     r8d, 29h ; ')'
0x1800d8459  mov     [rcx], bx
0x1800d845c  lea     rcx, [rbp+170h+var_160]
0x1800d8460  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d8465  test    al, al
0x1800d8467  jz      loc_1800D92A3
0x1800d846d  mov     r8d, 21h ; '!'
0x1800d8473  lea     rdx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800d847a  lea     rcx, [rbp+170h+var_140]
0x1800d847e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d8483  test    al, al
0x1800d8485  jz      loc_1800D92A3
0x1800d848b  mov     rcx, [rbp+170h+var_180]
0x1800d848f  lea     rdx, aDAOiciGaBaAOic_1; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x1800d8496  mov     [rbp+170h+var_178], rcx
0x1800d849a  mov     r8d, 22h ; '"'
0x1800d84a0  mov     dword ptr [rsp+270h+var_208], edi
0x1800d84a4  mov     [rcx], bx
0x1800d84a7  lea     rcx, [rbp+170h+var_180]
0x1800d84ab  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800d84b0  test    al, al
0x1800d84b2  jz      loc_1800D92A3
0x1800d84b8  mov     r8, r13
0x1800d84bb  call    CoCreateTaskScheduler
0x1800d84c0  mov     dword ptr [rbp+170h+Data], eax
0x1800d84c6  lea     rcx, aCreatetask; "CreateTask"
0x1800d84cd  mov     [rsp+270h+var_230], rcx
0x1800d84d2  lea     rcx, [rbp+170h+Data]
0x1800d84d9  mov     [rsp+270h+var_228], rcx
0x1800d84de  test    eax, eax
0x1800d84e0  jns     short loc_1800D852F
0x1800d84e2  lea     r8, a22cocreatetask; "22CoCreateTaskScheduler2"
0x1800d84e9  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x1800d84f0  lea     rax, [rbp+170h+Data]
0x1800d84f7  mov     r9d, 4; dwType
0x1800d84fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d8504  mov     [rsp+270h+cbData], r9d; cbData
0x1800d8509  mov     [rsp+270h+lpData], rax; lpData
0x1800d850e  call    cs:__imp_RegSetKeyValueW
0x1800d8515  nop     dword ptr [rax+rax+00h]
0x1800d851a  mov     ebx, dword ptr [rbp+170h+Data]
0x1800d8520  lea     rcx, [rsp+270h+var_230]; this
0x1800d8525  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800d852a  jmp     loc_1800D92A8
0x1800d852f  mov     rdi, [r13+0]
0x1800d8533  lea     rcx, [rbp+170h+pvarg]; pvarg
0x1800d853a  mov     rax, [rdi]
0x1800d853d  mov     rbx, [rax+50h]
0x1800d8541  call    cs:__imp_VariantInit
0x1800d8548  nop     dword ptr [rax+rax+00h]
0x1800d854d  movups  xmm10, xmmword ptr [rbp+170h+pvarg]
0x1800d8555  lea     rcx, [rbp+170h+var_100]; pvarg
0x1800d8559  movsd   xmm11, qword ptr [rbp+170h+pvarg+10h]
0x1800d8562  call    cs:__imp_VariantInit
0x1800d8569  nop     dword ptr [rax+rax+00h]
0x1800d856e  movups  xmm8, xmmword ptr [rbp+170h+var_100]
0x1800d8573  lea     rcx, [rbp+170h+var_1B8]; pvarg
0x1800d8577  movsd   xmm9, qword ptr [rbp+170h+var_100+10h]
0x1800d8580  call    cs:__imp_VariantInit
0x1800d8587  nop     dword ptr [rax+rax+00h]
0x1800d858c  movups  xmm6, xmmword ptr [rbp+170h+var_1B8]
0x1800d8590  lea     rcx, [rbp+170h+var_1E0]; pvarg
0x1800d8594  movsd   xmm7, qword ptr [rbp+170h+var_1B8+10h]
0x1800d8599  call    cs:__imp_VariantInit
0x1800d85a0  nop     dword ptr [rax+rax+00h]
0x1800d85a5  movups  xmm0, xmmword ptr [rbp+170h+var_1E0]
0x1800d85a9  lea     rax, [rbp+170h+var_D0]
0x1800d85b0  mov     rcx, rdi
0x1800d85b3  movsd   xmm1, qword ptr [rbp+170h+var_1E0+10h]
0x1800d85b8  lea     r9, [rbp+170h+var_B0]
0x1800d85bf  mov     [rsp+270h+lpData], rax
0x1800d85c4  lea     r8, [rbp+170h+var_120]
0x1800d85c8  mov     rax, rbx
0x1800d85cb  movaps  [rbp+170h+var_1A0], xmm0
0x1800d85cf  lea     rdx, [rbp+170h+var_1A0]
0x1800d85d3  movaps  [rbp+170h+var_D0], xmm10
0x1800d85db  movsd   [rbp+170h+var_C0], xmm11
0x1800d85e4  movaps  [rbp+170h+var_B0], xmm8
0x1800d85ec  movsd   [rbp+170h+var_A0], xmm9
0x1800d85f5  movaps  [rbp+170h+var_120], xmm6
0x1800d85f9  movsd   [rbp+170h+var_110], xmm7
0x1800d85fe  movsd   [rbp+170h+var_190], xmm1
0x1800d8603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8608  lea     rcx, [rbp+170h+var_1E0]; this
0x1800d860c  mov     dword ptr [rbp+170h+Data], eax
0x1800d8612  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800d8617  lea     rcx, [rbp+170h+var_1B8]; this
0x1800d861b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800d8620  lea     rcx, [rbp+170h+var_100]; this
0x1800d8624  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800d8629  lea     rcx, [rbp+170h+pvarg]; this
0x1800d8630  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800d8635  cmp     dword ptr [rbp+170h+Data], 0
0x1800d863c  jge     short loc_1800D864A
0x1800d863e  lea     r8, a23connect; "23Connect"
0x1800d8645  jmp     loc_1800D84E9
0x1800d864a  mov     rbx, [r13+0]
0x1800d864e  lea     rdx, StringValue; "\\"
0x1800d8655  lea     rcx, [rsp+270h+Block]; this
0x1800d865a  mov     rax, [rbx]
0x1800d865d  mov     rdi, [rax+38h]
0x1800d8661  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800d8666  mov     rcx, [rax]
0x1800d8669  test    rcx, rcx
0x1800d866c  jz      short loc_1800D8673
0x1800d866e  mov     rdx, [rcx]
0x1800d8671  jmp     short loc_1800D8675
0x1800d8673  xor     edx, edx
0x1800d8675  lea     r8, [rbp+170h+var_1E8]
0x1800d8679  mov     rcx, rbx
0x1800d867c  mov     rax, rdi
0x1800d867f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8684  mov     rbx, [rsp+270h+Block]
0x1800d8689  mov     edi, eax
0x1800d868b  mov     dword ptr [rbp+170h+Data], eax
0x1800d8691  test    rbx, rbx
0x1800d8694  jz      short loc_1800D86EC
0x1800d8696  or      eax, 0FFFFFFFFh
0x1800d8699  lock xadd [rbx+10h], eax
0x1800d869e  cmp     eax, 1
0x1800d86a1  jnz     short loc_1800D86E6
0x1800d86a3  test    rbx, rbx
0x1800d86a6  jz      short loc_1800D86E6
0x1800d86a8  mov     rcx, [rbx]; bstrString
0x1800d86ab  test    rcx, rcx
0x1800d86ae  jz      short loc_1800D86C3
0x1800d86b0  call    cs:__imp_SysFreeString
0x1800d86b7  nop     dword ptr [rax+rax+00h]
0x1800d86bc  mov     qword ptr [rbx], 0
0x1800d86c3  mov     rcx, [rbx+8]; Block
0x1800d86c7  test    rcx, rcx
0x1800d86ca  jz      short loc_1800D86D9
0x1800d86cc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d86d1  mov     qword ptr [rbx+8], 0
0x1800d86d9  mov     edx, 18h
0x1800d86de  mov     rcx, rbx; Block
0x1800d86e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d86e6  mov     edi, dword ptr [rbp+170h+Data]
0x1800d86ec  test    edi, edi
0x1800d86ee  jns     short loc_1800D8701
0x1800d86f0  lea     rcx, [rsp+270h+var_230]; this
0x1800d86f5  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800d86fa  mov     ebx, edi
0x1800d86fc  jmp     loc_1800D92A8
0x1800d8701  mov     rbx, [rbp+170h+var_1E8]
0x1800d8705  lea     rax, aSprootfolderGe; "spRootFolder->GetFolder()"
0x1800d870c  mov     rdx, [rbp+170h+var_140]; unsigned __int16 *
0x1800d8710  lea     rcx, [rsp+270h+Block]; this
0x1800d8715  mov     qword ptr [rbp+170h+var_1B8], rax
0x1800d8719  lea     rax, [rbp+170h+Data]
0x1800d8720  mov     qword ptr [rbp+170h+var_1B8+8], rax
0x1800d8724  mov     rax, [rbx]
0x1800d8727  mov     rdi, [rax+48h]
0x1800d872b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800d8730  mov     rdx, [rax]
0x1800d8733  test    rdx, rdx
0x1800d8736  jz      short loc_1800D873B
0x1800d8738  mov     rdx, [rdx]
0x1800d873b  lea     r8, [rsp+270h+var_210]
0x1800d8740  mov     rcx, rbx
0x1800d8743  mov     rax, rdi
0x1800d8746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d874b  mov     rbx, [rsp+270h+Block]
0x1800d8750  mov     dword ptr [rbp+170h+Data], eax
0x1800d8756  test    rbx, rbx
0x1800d8759  jz      short loc_1800D87AB
0x1800d875b  or      eax, 0FFFFFFFFh
  ... truncated ...
```
