# CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)

- ea: `0x180012ed4`
- end: `0x180016b82`
- name: `?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z`
- size: `15534`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *, _QWORD *, _QWORD *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, int, int, int, int)`
- caller_count: `8`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180016b88`
- `0x180018c6c`
- `0x180019560`
- `0x180019abc`
- `0x180019e58`
- `0x18001a25c`
- `0x18001aa50`
- `0x18001b094`

## callees

- `0x1800026b0`
- `0x1800034ac`
- `0x18000aa2c`
- `0x18000aab8`
- `0x18000ab84`
- `0x1800117c8`
- `0x180011d5c`
- `0x180012a58`
- `0x180012a70`
- `0x180012ed4`
- `0x18001ce54`
- `0x18001e79c`
- `0x180020010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800131e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800131ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800131e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800131ff`
- `OLEAUT32!__imp_SysAllocString` at `0x1800143ee`
- `OLEAUT32!__imp_SysAllocString` at `0x180014616`
- `OLEAUT32!__imp_SysAllocString` at `0x180014b74`
- `OLEAUT32!__imp_SysAllocString` at `0x1800143ee`
- `OLEAUT32!__imp_SysAllocString` at `0x180014616`
- `OLEAUT32!__imp_SysAllocString` at `0x180014b74`
- `OLEAUT32!__imp_VariantInit` at `0x180013fff`
- `OLEAUT32!__imp_VariantInit` at `0x180014017`
- `OLEAUT32!__imp_VariantInit` at `0x18001402c`
- `OLEAUT32!__imp_VariantInit` at `0x18001403f`
- `OLEAUT32!__imp_VariantInit` at `0x180013fff`
- `OLEAUT32!__imp_VariantInit` at `0x180014017`
- `OLEAUT32!__imp_VariantInit` at `0x18001402c`
- `OLEAUT32!__imp_VariantInit` at `0x18001403f`
- `OLEAUT32!__imp_VariantClear` at `0x1800140b9`
- `OLEAUT32!__imp_VariantClear` at `0x1800140c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800140cd`
- `OLEAUT32!__imp_VariantClear` at `0x1800140d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800143dc`
- `OLEAUT32!__imp_VariantClear` at `0x180014457`
- `OLEAUT32!__imp_VariantClear` at `0x180014604`
- `OLEAUT32!__imp_VariantClear` at `0x180014682`
- `OLEAUT32!__imp_VariantClear` at `0x180014bb9`
- `OLEAUT32!__imp_VariantClear` at `0x1800140b9`
- `OLEAUT32!__imp_VariantClear` at `0x1800140c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800140cd`
- `OLEAUT32!__imp_VariantClear` at `0x1800140d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800143dc`
- `OLEAUT32!__imp_VariantClear` at `0x180014457`
- `OLEAUT32!__imp_VariantClear` at `0x180014604`
- `OLEAUT32!__imp_VariantClear` at `0x180014682`
- `OLEAUT32!__imp_VariantClear` at `0x180014bb9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180013eec`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180014112`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180013eec`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180014112`

## string_xrefs

- `0x180013ea6`: `CreateTask`
- `0x180013ed7`: `22CoCreateTaskScheduler2`

## pseudocode

```c
__int64 __fastcall CreateTask(
        _QWORD *a1,
        __int64 *a2,
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
        int a13)
{
  unsigned int v16; // r14d
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // edi
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v23; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v25; // xmm8
  IRecordInfo *v26; // xmm9_8
  __int128 v27; // xmm6
  IRecordInfo *v28; // xmm7_8
  __int64 v29; // rbx
  __int64 (__fastcall *v30)(__int64, _QWORD *, __int64 **); // rdi
  _QWORD *v31; // rdx
  const struct std::nothrow_t *v32; // rdx
  __int64 v33; // rbx
  __int64 (__fastcall *v34)(__int64, _QWORD *, __int64 **); // rdi
  _QWORD *v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  __int64 v37; // rdi
  __int64 v38; // r12
  OLECHAR *v39; // rbx
  int v40; // ecx
  __int128 v41; // xmm6
  IRecordInfo *v42; // xmm7_8
  _QWORD *v43; // rdx
  const struct std::nothrow_t *v44; // rdx
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, _QWORD *, __int64 *); // r12
  _QWORD *v47; // rdx
  const struct std::nothrow_t *v48; // rdx
  __int64 v49; // r12
  OLECHAR *v50; // rdi
  int v51; // ecx
  __int64 (__fastcall *v52)(__int64, _QWORD *, VARIANTARG *, __int64 *); // rdi
  __int128 v53; // xmm6
  IRecordInfo *v54; // xmm7_8
  _QWORD *v55; // rdx
  const struct std::nothrow_t *v56; // rdx
  __int64 v57; // rbx
  __int64 *v58; // rbx
  __int64 (__fastcall *v59)(__int64 *); // rdi
  const struct std::nothrow_t *v60; // rdx
  __int64 *v61; // rdi
  __int64 v62; // r15
  OLECHAR *v63; // rbx
  __int64 *v64; // rdi
  __int64 v65; // rsi
  BSTR *v66; // rbx
  BSTR v67; // rax
  const struct std::nothrow_t *v68; // rdx
  __int64 *v69; // rbx
  __int64 v70; // rax
  __int64 (__fastcall *v71)(__int64 *); // rdi
  const struct std::nothrow_t *v72; // rdx
  __int64 (__fastcall *v73)(__int64 *); // rdi
  const struct std::nothrow_t *v74; // rdx
  __int64 v75; // rbx
  __int64 (__fastcall *v76)(__int64); // rdi
  const struct std::nothrow_t *v77; // rdx
  __int64 v78; // rbx
  __int64 (__fastcall *v79)(__int64); // rdi
  const struct std::nothrow_t *v80; // rdx
  __int64 v81; // rbx
  __int64 (__fastcall *v82)(__int64, __int64); // rdi
  _bstr_t *v83; // rax
  __int64 v84; // rdx
  const struct std::nothrow_t *v85; // rdx
  __int64 Data; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v87; // [rsp+40h] [rbp-C8h] BYREF
  __int64 *v88; // [rsp+48h] [rbp-C0h] BYREF
  __int64 *v89; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v90; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v91; // [rsp+60h] [rbp-A8h] BYREF
  __int64 *v92; // [rsp+68h] [rbp-A0h] BYREF
  __int64 *v93; // [rsp+70h] [rbp-98h] BYREF
  __int64 v94; // [rsp+78h] [rbp-90h] BYREF
  __int64 v95; // [rsp+80h] [rbp-88h] BYREF
  OLECHAR *psz; // [rsp+88h] [rbp-80h] BYREF
  OLECHAR *v97; // [rsp+90h] [rbp-78h]
  _WORD v98[8]; // [rsp+98h] [rbp-70h] BYREF
  OLECHAR *v99; // [rsp+A8h] [rbp-60h] BYREF
  OLECHAR *v100; // [rsp+B0h] [rbp-58h]
  _WORD v101[8]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v102[2]; // [rsp+C8h] [rbp-40h] BYREF
  _WORD v103[8]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v104[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v105; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG v106; // [rsp+100h] [rbp-8h] BYREF
  int v107; // [rsp+118h] [rbp+10h]
  VARIANTARG v108; // [rsp+120h] [rbp+18h] BYREF
  VARIANTARG v109; // [rsp+138h] [rbp+30h] BYREF
  VARIANTARG v110; // [rsp+158h] [rbp+50h] BYREF
  VARIANTARG pvarg; // [rsp+178h] [rbp+70h] BYREF
  __int128 v112; // [rsp+198h] [rbp+90h] BYREF
  IRecordInfo *v113; // [rsp+1A8h] [rbp+A0h]
  __int128 v114; // [rsp+1B8h] [rbp+B0h] BYREF
  IRecordInfo *v115; // [rsp+1C8h] [rbp+C0h]
  __int128 v116; // [rsp+1D8h] [rbp+D0h] BYREF
  IRecordInfo *v117; // [rsp+1E8h] [rbp+E0h]
  int v120; // [rsp+2F8h] [rbp+1F0h]

  v93 = 0;
  v89 = 0;
  v87 = 0;
  v92 = 0;
  v88 = 0;
  v90 = 0;
  v95 = 0;
  v94 = 0;
  v91 = 0;
  v99 = v101;
  v100 = v101;
  v101[0] = 0;
  v102[0] = v103;
  v102[1] = v103;
  v103[0] = 0;
  psz = v98;
  v97 = v98;
  v98[0] = 0;
  v16 = 0;
  if ( a13 != 1 )
  {
    LOBYTE(v16) = a10 != 1;
    ++v16;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v99,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FA;;;") )
  {
    if ( psz != v98 )
      operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
    if ( v102[0] != v103 )
      operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v99 != v101 )
      operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
LABEL_10:
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v87);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v89);
    ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v93);
    return 2147942414LL;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &psz,
                           L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;LS)(A;OICI;GA;;;") )
  {
    if ( psz != v98 )
      operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
    if ( v102[0] != v103 )
      operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v99 != v101 )
      operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_10;
  }
  v107 = 0;
  if ( a8 && (unsigned int)_o__wcsicmp(a8, L"S-1-5-18") )
  {
    v120 = 0;
    if ( (unsigned int)_o__wcsicmp(a8, L"S-1-5-32-545") )
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &v99,
                               a8) )
      {
        if ( psz != v98 )
          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
        if ( v102[0] != v103 )
          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v99 != v101 )
          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_10;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &v99,
                               L")") )
      {
        if ( psz != v98 )
          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
        if ( v102[0] != v103 )
          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v99 != v101 )
          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_10;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v102,
                               a8) )
      {
        if ( psz != v98 )
          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
        if ( v102[0] != v103 )
          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v99 != v101 )
          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_10;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v102,
                               L"\\EnterpriseMgmt") )
      {
        if ( psz != v98 )
          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
        if ( v102[0] != v103 )
          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v99 != v101 )
          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_10;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &psz,
                               a8) )
      {
        if ( psz != v98 )
          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
        if ( v102[0] != v103 )
          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v99 != v101 )
          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_10;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &psz,
                               L")") )
      {
        if ( psz != v98 )
          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
        if ( v102[0] != v103 )
          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v99 != v101 )
          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_10;
      }
    }
    else
    {
      v100 = v99;
      *v99 = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &v99,
                               L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)") )
      {
        if ( psz != v98 )
          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
        if ( v102[0] != v103 )
          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v99 != v101 )
          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
        if ( v91 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v94 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        if ( v95 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
        if ( v90 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
        if ( v88 )
          (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
        if ( v92 )
          (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
        goto LABEL_10;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v102,
                               L"\\Microsoft\\Windows\\EnterpriseMgmt") )
      {
        if ( psz != v98 )
          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
        if ( v102[0] != v103 )
          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v99 != v101 )
          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
        if ( v91 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v94 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        if ( v95 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
        if ( v90 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
        if ( v88 )
          (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
        if ( v92 )
          (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
        goto LABEL_10;
      }
      v107 = 1;
      v97 = psz;
      *psz = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &psz,
                               L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)") )
      {
        if ( psz != v98 )
          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
        if ( v102[0] != v103 )
          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v99 != v101 )
          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
        if ( v91 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v94 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        if ( v95 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
        if ( v90 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
        if ( v88 )
          (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
        if ( v92 )
          (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
        goto LABEL_10;
      }
    }
  }
  else
  {
    v100 = v99;
    *v99 = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v99,
                             L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)") )
    {
      if ( psz != v98 )
        operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
      if ( v102[0] != v103 )
        operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v99 != v101 )
        operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
      if ( v91 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      if ( v94 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      if ( v95 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
      if ( v90 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      if ( v88 )
        (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
      if ( v92 )
        (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
      goto LABEL_10;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v102,
                             L"\\Microsoft\\Windows\\EnterpriseMgmt") )
    {
      if ( psz != v98 )
        operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
      if ( v102[0] != v103 )
        operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v99 != v101 )
        operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
      if ( v91 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      if ( v94 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      if ( v95 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
      if ( v90 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      if ( v88 )
        (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
      if ( v92 )
        (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
      goto LABEL_10;
    }
    v120 = 1;
    v97 = psz;
    *psz = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &psz,
                             L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)") )
    {
      if ( psz != v98 )
        operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
      if ( v102[0] != v103 )
        operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v99 != v101 )
        operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
      if ( v91 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      if ( v94 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      if ( v95 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
      if ( v90 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      if ( v88 )
        (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
      if ( v92 )
        (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
      goto LABEL_10;
    }
  }
  LODWORD(Data) = CoCreateTaskScheduler(v19, v18, a1);
  v104[0] = "CreateTask";
  v104[1] = &Data;
  if ( (int)Data >= 0 )
  {
    v21 = *a1;
    v22 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*a1 + 80LL);
    VariantInit(&pvarg);
    v23 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v106);
    v25 = *(_OWORD *)&v106.vt;
    v26 = v106.pRecInfo;
    VariantInit(&v109);
    v27 = *(_OWORD *)&v109.vt;
    v28 = v109.pRecInfo;
    VariantInit(&v108);
    v112 = v23;
    v113 = pRecInfo;
    v114 = v25;
    v115 = v26;
    v116 = v27;
    v117 = v28;
    v110 = v108;
    LODWORD(Data) = v22(v21, &v110, &v116, &v114, &v112);
    VariantClear(&v108);
    VariantClear(&v109);
    VariantClear(&v106);
    VariantClear(&pvarg);
    if ( (int)Data >= 0 )
    {
      v29 = *a1;
      v30 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 **))(*(_QWORD *)*a1 + 56LL);
      v31 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v105, L"\\");
      if ( v31 )
        v31 = (_QWORD *)*v31;
      LODWORD(Data) = v30(v29, v31, &v93);
      _bstr_t::~_bstr_t((_bstr_t *)&v105, v32);
      v20 = Data;
      if ( (int)Data >= 0 )
      {
        *(_QWORD *)&v106.vt = "spRootFolder->GetFolder()";
        v106.llVal = (LONGLONG)&Data;
        v33 = (__int64)v93;
        v34 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 **))(*v93 + 72);
        v35 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v105, v102[0]);
        if ( v35 )
          v35 = (_QWORD *)*v35;
        LODWORD(Data) = v34(v33, v35, &v89);
        _bstr_t::~_bstr_t((_bstr_t *)&v105, v36);
        if ( (unsigned int)(Data + 2147024894) > 1 )
          goto LABEL_279;
        v37 = (__int64)v93;
        v38 = *v93;
        v39 = psz;
        v109.vt = 0;
        VariantClear(&v109);
        v109.vt = 8;
        v109.llVal = (LONGLONG)SysAllocString(v39);
        if ( !v109.llVal && v39 )
        {
          v109.vt = 10;
          v109.lVal = -2147024882;
          ATL::AtlThrowImpl(v40);
        }
        v41 = *(_OWORD *)&v109.vt;
        v42 = v109.pRecInfo;
        v43 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v105, v102[0]);
        if ( v43 )
          v43 = (_QWORD *)*v43;
        *(_OWORD *)&v110.vt = v41;
        v110.pRecInfo = v42;
        LODWORD(Data) = (*(__int64 (__fastcall **)(__int64, _QWORD *, VARIANTARG *, __int64 **))(v38 + 88))(
                          v37,
                          v43,
                          &v110,
                          &v89);
        _bstr_t::~_bstr_t((_bstr_t *)&v105, v44);
        VariantClear(&v109);
        v20 = Data;
        if ( (int)Data >= 0 )
        {
LABEL_279:
          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v106);
          if ( a5 )
          {
            *(_QWORD *)&v109.vt = "spEnterpriseMgmtFolder->GetFolder()";
            v109.llVal = (LONGLONG)&Data;
            v45 = (__int64)v89;
            v46 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*v89 + 72);
            v47 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v105, a5);
            if ( v47 )
              v47 = (_QWORD *)*v47;
            LODWORD(Data) = v46(v45, v47, a2);
            _bstr_t::~_bstr_t((_bstr_t *)&v105, v48);
            if ( (unsigned int)(Data + 2147024894) <= 1 )
            {
              v49 = (__int64)v89;
              v105 = *v89;
              v50 = psz;
              v108.vt = 0;
              VariantClear(&v108);
              v108.vt = 8;
              v108.llVal = (LONGLONG)SysAllocString(v50);
              if ( !v108.llVal && v50 )
              {
                v108.vt = 10;
                v108.lVal = -2147024882;
                ATL::AtlThrowImpl(v51);
              }
              v52 = *(__int64 (__fastcall **)(__int64, _QWORD *, VARIANTARG *, __int64 *))(v105 + 88);
              v53 = *(_OWORD *)&v108.vt;
              v54 = v108.pRecInfo;
              v55 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v106, a5);
              if ( v55 )
                v55 = (_QWORD *)*v55;
              *(_OWORD *)&v110.vt = v53;
              v110.pRecInfo = v54;
              LODWORD(Data) = v52(v49, v55, &v110, a2);
              _bstr_t::~_bstr_t((_bstr_t *)&v106, v56);
              VariantClear(&v108);
              v20 = Data;
              if ( (int)Data < 0 )
              {
                EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v109);
                EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                if ( psz != v98 )
                  operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                if ( v102[0] != v103 )
                  operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                if ( v99 != v101 )
                  operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                if ( v91 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                if ( v94 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                if ( v95 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                if ( v90 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                if ( v88 )
                  (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                if ( v92 )
                  (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                goto LABEL_920;
              }
            }
            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v109);
          }
          else
          {
            v57 = (__int64)v89;
            if ( (__int64 *)*a2 != v89 )
            {
              if ( v89 )
                (*(void (__fastcall **)(__int64 *))(*v89 + 8))(v89);
              if ( *a2 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)*a2 + 16LL))(*a2);
              *a2 = v57;
            }
          }
          v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(*(_QWORD *)*a1 + 72LL))(*a1, 0, a3);
          LODWORD(Data) = v20;
          if ( v20 >= 0 )
          {
            v20 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 56LL))(*a3, &v92);
            LODWORD(Data) = v20;
            if ( v20 >= 0 )
            {
              v58 = v92;
              v59 = *(__int64 (__fastcall **)(__int64 *))(*v92 + 80);
              _bstr_t::_bstr_t((_bstr_t *)&v106, L"Microsoft Corporation");
              LODWORD(Data) = v59(v58);
              _bstr_t::~_bstr_t((_bstr_t *)&v106, v60);
              v20 = Data;
              if ( (int)Data >= 0 )
              {
                v61 = v92;
                v62 = *v92;
                v63 = v99;
                v108.vt = 8;
                v108.llVal = (LONGLONG)SysAllocString(v99);
                if ( !v108.llVal && v63 )
                  _com_issue_error(-2147024882);
                v110 = v108;
                LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v62 + 176))(v61, &v110);
                VariantClear(&v108);
                v20 = Data;
                if ( (int)Data >= 0 )
                {
                  v20 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 120LL))(*a3, &v88);
                  LODWORD(Data) = v20;
                  if ( v20 >= 0 )
                  {
                    if ( v120 )
                    {
                      v64 = v88;
                      v65 = *v88;
                      v66 = (BSTR *)operator new(0x18u);
                      v66[1] = 0;
                      *((_DWORD *)v66 + 4) = 1;
                      v67 = _com_util::ConvertStringToBSTR("SYSTEM");
                      *v66 = v67;
                      if ( !v67 )
                        _com_issue_error(-2147024882);
                      *(_QWORD *)&v106.vt = v66;
                      LODWORD(Data) = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v65 + 128))(v64, v67);
                      _bstr_t::~_bstr_t((_bstr_t *)&v106, v68);
                      v20 = Data;
                      if ( (int)Data < 0 )
                      {
                        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                        if ( psz != v98 )
                          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                        if ( v102[0] != v103 )
                          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                        if ( v99 != v101 )
                          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                        if ( v91 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                        if ( v94 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                        if ( v95 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                        if ( v90 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                        if ( v88 )
                          (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                        if ( v92 )
                          (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                        goto LABEL_920;
                      }
                    }
                    else
                    {
                      v69 = v88;
                      v70 = *v88;
                      if ( v107 )
                      {
                        v71 = *(__int64 (__fastcall **)(__int64 *))(v70 + 128);
                        _bstr_t::_bstr_t((_bstr_t *)&v106, L"S-1-5-32-545");
                        LODWORD(Data) = v71(v69);
                        _bstr_t::~_bstr_t((_bstr_t *)&v106, v72);
                        v20 = Data;
                        if ( (int)Data < 0 )
                        {
                          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                          if ( psz != v98 )
                            operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v102[0] != v103 )
                            operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                          if ( v99 != v101 )
                            operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v91 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                          if ( v94 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                          if ( v95 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                          if ( v90 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                          if ( v88 )
                            (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                          if ( v92 )
                            (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                          goto LABEL_920;
                        }
                        v20 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v88 + 144))(v88, 1);
                        LODWORD(Data) = v20;
                        if ( v20 < 0 )
                        {
                          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                          if ( psz != v98 )
                            operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v102[0] != v103 )
                            operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                          if ( v99 != v101 )
                            operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v91 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                          if ( v94 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                          if ( v95 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                          if ( v90 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                          if ( v88 )
                            (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                          if ( v92 )
                            (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                          goto LABEL_920;
                        }
                      }
                      else
                      {
                        v73 = *(__int64 (__fastcall **)(__int64 *))(v70 + 96);
                        _bstr_t::_bstr_t((_bstr_t *)&v106, a8);
                        LODWORD(Data) = v73(v69);
                        _bstr_t::~_bstr_t((_bstr_t *)&v106, v74);
                        v20 = Data;
                        if ( (int)Data < 0 )
                        {
                          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                          if ( psz != v98 )
                            operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v102[0] != v103 )
                            operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                          if ( v99 != v101 )
                            operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v91 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                          if ( v94 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                          if ( v95 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                          if ( v90 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                          if ( v88 )
                            (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                          if ( v92 )
                            (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                          goto LABEL_920;
                        }
                        v20 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v88 + 112))(v88, 3);
                        LODWORD(Data) = v20;
                        if ( v20 < 0 )
                        {
                          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                          if ( psz != v98 )
                            operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v102[0] != v103 )
                            operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                          if ( v99 != v101 )
                            operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v91 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                          if ( v94 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                          if ( v95 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                          if ( v90 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                          if ( v88 )
                            (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                          if ( v92 )
                            (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                          goto LABEL_920;
                        }
                        v20 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v88 + 144))(v88, a9);
                        LODWORD(Data) = v20;
                        if ( v20 < 0 )
                        {
                          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                          if ( psz != v98 )
                            operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v102[0] != v103 )
                            operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                          if ( v99 != v101 )
                            operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v91 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                          if ( v94 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                          if ( v95 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                          if ( v90 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                          if ( v88 )
                            (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                          if ( v92 )
                            (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                          goto LABEL_920;
                        }
                      }
                    }
                    v20 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 88LL))(*a3, &v87);
                    LODWORD(Data) = v20;
                    if ( v20 >= 0 )
                    {
                      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 128LL))(v87, 0);
                      LODWORD(Data) = v20;
                      if ( v20 >= 0 )
                      {
                        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 144LL))(v87, 0);
                        LODWORD(Data) = v20;
                        if ( v20 >= 0 )
                        {
                          v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 112LL))(v87, v16);
                          LODWORD(Data) = v20;
                          if ( v20 >= 0 )
                          {
                            v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 352LL))(v87, 0);
                            LODWORD(Data) = v20;
                            if ( v20 >= 0 )
                            {
                              v75 = v87;
                              v76 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v87 + 224LL);
                              _bstr_t::_bstr_t((_bstr_t *)&v106, L"PT1H");
                              LODWORD(Data) = v76(v75);
                              _bstr_t::~_bstr_t((_bstr_t *)&v106, v77);
                              v20 = Data;
                              if ( (int)Data >= 0 )
                              {
                                v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v87)(
                                        v87,
                                        &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                                        a4);
                                LODWORD(Data) = v20;
                                if ( v20 >= 0 )
                                {
                                  v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 176LL))(
                                          *a4,
                                          (unsigned __int16)((a11 != 1) - 1));
                                  LODWORD(Data) = v20;
                                  if ( v20 >= 0 )
                                  {
                                    v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 208LL))(
                                            *a4,
                                            (unsigned __int16)((a12 != 1) - 1));
                                    LODWORD(Data) = v20;
                                    if ( v20 >= 0 )
                                    {
                                      v20 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 400LL))(
                                              *a4,
                                              0xFFFFFFFFLL);
                                      LODWORD(Data) = v20;
                                      if ( v20 >= 0 )
                                      {
                                        v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v87 + 312LL))(
                                                v87,
                                                &v90);
                                        LODWORD(Data) = v20;
                                        if ( v20 >= 0 )
                                        {
                                          v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v90 + 96LL))(
                                                  v90,
                                                  0);
                                          LODWORD(Data) = v20;
                                          if ( v20 >= 0 )
                                          {
                                            v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v90 + 64LL))(
                                                    v90,
                                                    0);
                                            LODWORD(Data) = v20;
                                            if ( v20 >= 0 )
                                            {
                                              v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v90 + 80LL))(
                                                      v90,
                                                      0);
                                              LODWORD(Data) = v20;
                                              if ( v20 >= 0 )
                                              {
                                                v20 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 136LL))(
                                                        *a3,
                                                        &v95);
                                                LODWORD(Data) = v20;
                                                if ( v20 >= 0 )
                                                {
                                                  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v95 + 96LL))(
                                                          v95,
                                                          0,
                                                          &v94);
                                                  LODWORD(Data) = v20;
                                                  if ( v20 >= 0 )
                                                  {
                                                    v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v94)(
                                                            v94,
                                                            &IID_IExecAction,
                                                            &v91);
                                                    LODWORD(Data) = v20;
                                                    if ( v20 >= 0 )
                                                    {
                                                      v78 = v91;
                                                      v79 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 88LL);
                                                      _bstr_t::_bstr_t((_bstr_t *)&v106, a6);
                                                      LODWORD(Data) = v79(v78);
                                                      _bstr_t::~_bstr_t((_bstr_t *)&v106, v80);
                                                      v20 = Data;
                                                      if ( (int)Data >= 0 )
                                                      {
                                                        v81 = v91;
                                                        v82 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v91 + 104LL);
                                                        v83 = _bstr_t::_bstr_t((_bstr_t *)&v106, a7);
                                                        if ( *(_QWORD *)v83 )
                                                          v84 = **(_QWORD **)v83;
                                                        else
                                                          v84 = 0;
                                                        v20 = v82(v81, v84);
                                                        _bstr_t::~_bstr_t((_bstr_t *)&v106, v85);
                                                        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                                        if ( psz != v98 )
                                                          operator delete(
                                                            psz,
                                                            (const struct std::nothrow_t *)&std::nothrow);
                                                        if ( v102[0] != v103 )
                                                          operator delete(
                                                            v102[0],
                                                            (const struct std::nothrow_t *)&std::nothrow);
                                                        if ( v99 != v101 )
                                                          operator delete(
                                                            v99,
                                                            (const struct std::nothrow_t *)&std::nothrow);
                                                        if ( v91 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                                        if ( v94 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                        if ( v95 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                        if ( v90 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                                        if ( v88 )
                                                          (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                                        if ( v92 )
                                                          (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                                      }
                                                      else
                                                      {
                                                        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                                        if ( psz != v98 )
                                                          operator delete(
                                                            psz,
                                                            (const struct std::nothrow_t *)&std::nothrow);
                                                        if ( v102[0] != v103 )
                                                          operator delete(
                                                            v102[0],
                                                            (const struct std::nothrow_t *)&std::nothrow);
                                                        if ( v99 != v101 )
                                                          operator delete(
                                                            v99,
                                                            (const struct std::nothrow_t *)&std::nothrow);
                                                        if ( v91 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                                        if ( v94 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                        if ( v95 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                        if ( v90 )
                                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                                        if ( v88 )
                                                          (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                                        if ( v92 )
                                                          (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                                      }
                                                    }
                                                    else
                                                    {
                                                      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                                      if ( psz != v98 )
                                                        operator delete(
                                                          psz,
                                                          (const struct std::nothrow_t *)&std::nothrow);
                                                      if ( v102[0] != v103 )
                                                        operator delete(
                                                          v102[0],
                                                          (const struct std::nothrow_t *)&std::nothrow);
                                                      if ( v99 != v101 )
                                                        operator delete(
                                                          v99,
                                                          (const struct std::nothrow_t *)&std::nothrow);
                                                      if ( v91 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                                      if ( v94 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                      if ( v95 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                      if ( v90 )
                                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                                      if ( v88 )
                                                        (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                                      if ( v92 )
                                                        (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                                    }
                                                  }
                                                  else
                                                  {
                                                    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                                    if ( psz != v98 )
                                                      operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                                    if ( v102[0] != v103 )
                                                      operator delete(
                                                        v102[0],
                                                        (const struct std::nothrow_t *)&std::nothrow);
                                                    if ( v99 != v101 )
                                                      operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                                    if ( v91 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                                    if ( v94 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                    if ( v95 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                    if ( v90 )
                                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                                    if ( v88 )
                                                      (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                                    if ( v92 )
                                                      (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                                  }
                                                }
                                                else
                                                {
                                                  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                                  if ( psz != v98 )
                                                    operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                                  if ( v102[0] != v103 )
                                                    operator delete(
                                                      v102[0],
                                                      (const struct std::nothrow_t *)&std::nothrow);
                                                  if ( v99 != v101 )
                                                    operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                                  if ( v91 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                                  if ( v94 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                  if ( v95 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                  if ( v90 )
                                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                                  if ( v88 )
                                                    (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                                  if ( v92 )
                                                    (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                                }
                                              }
                                              else
                                              {
                                                EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                                if ( psz != v98 )
                                                  operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                                if ( v102[0] != v103 )
                                                  operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                                                if ( v99 != v101 )
                                                  operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                                if ( v91 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                                if ( v94 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                                if ( v95 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                                if ( v90 )
                                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                                if ( v88 )
                                                  (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                                if ( v92 )
                                                  (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                              }
                                            }
                                            else
                                            {
                                              EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                              if ( psz != v98 )
                                                operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                              if ( v102[0] != v103 )
                                                operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                                              if ( v99 != v101 )
                                                operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                              if ( v91 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                              if ( v94 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                              if ( v95 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                              if ( v90 )
                                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                              if ( v88 )
                                                (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                              if ( v92 )
                                                (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                            }
                                          }
                                          else
                                          {
                                            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                            if ( psz != v98 )
                                              operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                            if ( v102[0] != v103 )
                                              operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                                            if ( v99 != v101 )
                                              operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                            if ( v91 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                            if ( v94 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                            if ( v95 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                            if ( v90 )
                                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                            if ( v88 )
                                              (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                            if ( v92 )
                                              (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                          }
                                        }
                                        else
                                        {
                                          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                          if ( psz != v98 )
                                            operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                          if ( v102[0] != v103 )
                                            operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                                          if ( v99 != v101 )
                                            operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                          if ( v91 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                          if ( v94 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                          if ( v95 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                          if ( v90 )
                                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                          if ( v88 )
                                            (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                          if ( v92 )
                                            (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                        }
                                      }
                                      else
                                      {
                                        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                        if ( psz != v98 )
                                          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                        if ( v102[0] != v103 )
                                          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                                        if ( v99 != v101 )
                                          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                        if ( v91 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                        if ( v94 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                        if ( v95 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                        if ( v90 )
                                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                        if ( v88 )
                                          (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                        if ( v92 )
                                          (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                      }
                                    }
                                    else
                                    {
                                      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                      if ( psz != v98 )
                                        operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                      if ( v102[0] != v103 )
                                        operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                                      if ( v99 != v101 )
                                        operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                      if ( v91 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                      if ( v94 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                      if ( v95 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                      if ( v90 )
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                      if ( v88 )
                                        (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                      if ( v92 )
                                        (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                    }
                                  }
                                  else
                                  {
                                    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                    if ( psz != v98 )
                                      operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                    if ( v102[0] != v103 )
                                      operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                                    if ( v99 != v101 )
                                      operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                    if ( v91 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                    if ( v94 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                    if ( v95 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                    if ( v90 )
                                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                    if ( v88 )
                                      (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                    if ( v92 )
                                      (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                  }
                                }
                                else
                                {
                                  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                  if ( psz != v98 )
                                    operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                  if ( v102[0] != v103 )
                                    operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                                  if ( v99 != v101 )
                                    operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                  if ( v91 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                  if ( v94 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                  if ( v95 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                  if ( v90 )
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                  if ( v88 )
                                    (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                  if ( v92 )
                                    (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                                }
                              }
                              else
                              {
                                EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                                if ( psz != v98 )
                                  operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                                if ( v102[0] != v103 )
                                  operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                                if ( v99 != v101 )
                                  operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                                if ( v91 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                                if ( v94 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                                if ( v95 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                                if ( v90 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                                if ( v88 )
                                  (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                                if ( v92 )
                                  (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                              }
                            }
                            else
                            {
                              EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                              if ( psz != v98 )
                                operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                              if ( v102[0] != v103 )
                                operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                              if ( v99 != v101 )
                                operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                              if ( v91 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                              if ( v94 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                              if ( v95 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                              if ( v90 )
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                              if ( v88 )
                                (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                              if ( v92 )
                                (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                            }
                          }
                          else
                          {
                            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                            if ( psz != v98 )
                              operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                            if ( v102[0] != v103 )
                              operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                            if ( v99 != v101 )
                              operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                            if ( v91 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                            if ( v94 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                            if ( v95 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                            if ( v90 )
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                            if ( v88 )
                              (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                            if ( v92 )
                              (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                          }
                        }
                        else
                        {
                          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                          if ( psz != v98 )
                            operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v102[0] != v103 )
                            operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                          if ( v99 != v101 )
                            operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                          if ( v91 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                          if ( v94 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                          if ( v95 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                          if ( v90 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                          if ( v88 )
                            (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                          if ( v92 )
                            (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                        }
                      }
                      else
                      {
                        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                        if ( psz != v98 )
                          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                        if ( v102[0] != v103 )
                          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                        if ( v99 != v101 )
                          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                        if ( v91 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                        if ( v94 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                        if ( v95 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                        if ( v90 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                        if ( v88 )
                          (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                        if ( v92 )
                          (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                      }
                    }
                    else
                    {
                      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                      if ( psz != v98 )
                        operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                      if ( v102[0] != v103 )
                        operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                      if ( v99 != v101 )
                        operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                      if ( v91 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                      if ( v94 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                      if ( v95 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                      if ( v90 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                      if ( v88 )
                        (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                      if ( v92 )
                        (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                    }
                    goto LABEL_920;
                  }
                  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                  if ( psz != v98 )
                    operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                  if ( v102[0] != v103 )
                    operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                  if ( v99 != v101 )
                    operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                  if ( v91 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                  if ( v94 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                  if ( v95 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                  if ( v90 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                  if ( v88 )
                    (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                  if ( v92 )
                    (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                }
                else
                {
                  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                  if ( psz != v98 )
                    operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                  if ( v102[0] != v103 )
                    operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                  if ( v99 != v101 )
                    operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                  if ( v91 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                  if ( v94 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                  if ( v95 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                  if ( v90 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                  if ( v88 )
                    (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                  if ( v92 )
                    (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
                }
              }
              else
              {
                EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
                if ( psz != v98 )
                  operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
                if ( v102[0] != v103 )
                  operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
                if ( v99 != v101 )
                  operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
                if ( v91 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                if ( v94 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                if ( v95 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
                if ( v90 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                if ( v88 )
                  (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
                if ( v92 )
                  (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
              }
            }
            else
            {
              EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
              if ( psz != v98 )
                operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
              if ( v102[0] != v103 )
                operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
              if ( v99 != v101 )
                operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
              if ( v91 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
              if ( v94 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
              if ( v95 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
              if ( v90 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
              if ( v88 )
                (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
              if ( v92 )
                (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
            }
          }
          else
          {
            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
            if ( psz != v98 )
              operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
            if ( v102[0] != v103 )
              operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
            if ( v99 != v101 )
              operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
            if ( v91 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
            if ( v94 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
            if ( v95 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
            if ( v90 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
            if ( v88 )
              (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
            if ( v92 )
              (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
          }
        }
        else
        {
          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v106);
          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
          if ( psz != v98 )
            operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
          if ( v102[0] != v103 )
            operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( v99 != v101 )
            operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
          if ( v91 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
          if ( v94 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
          if ( v95 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
          if ( v90 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
          if ( v88 )
            (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
          if ( v92 )
            (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
        }
      }
      else
      {
        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
        if ( psz != v98 )
          operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
        if ( v102[0] != v103 )
          operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v99 != v101 )
          operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
        if ( v91 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v94 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
        if ( v95 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
        if ( v90 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
        if ( v88 )
          (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
        if ( v92 )
          (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
      }
    }
    else
    {
      RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"23Connect", 4u, &Data, 4u);
      v20 = Data;
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
      if ( psz != v98 )
        operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
      if ( v102[0] != v103 )
        operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v99 != v101 )
        operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
      if ( v91 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      if ( v94 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
      if ( v95 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
      if ( v90 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      if ( v88 )
        (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
      if ( v92 )
        (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
    }
  }
  else
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"22CoCreateTaskScheduler2", 4u, &Data, 4u);
    v20 = Data;
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v104);
    if ( psz != v98 )
      operator delete(psz, (const struct std::nothrow_t *)&std::nothrow);
    if ( v102[0] != v103 )
      operator delete(v102[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v99 != v101 )
      operator delete(v99, (const struct std::nothrow_t *)&std::nothrow);
    if ( v91 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    if ( v95 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    if ( v90 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    if ( v88 )
      (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
    if ( v92 )
      (*(void (__fastcall **)(__int64 *))(*v92 + 16))(v92);
  }
LABEL_920:
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v87);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v89);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>((__int64 *)&v93);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180012ed4  mov     rax, rsp
0x180012ed7  mov     [rax+10h], rbx
0x180012edb  mov     [rax+20h], r9
0x180012edf  mov     [rax+8], rcx
0x180012ee3  push    rbp
0x180012ee4  push    rsi
0x180012ee5  push    rdi
0x180012ee6  push    r12
0x180012ee8  push    r13
0x180012eea  push    r14
0x180012eec  push    r15
0x180012eee  lea     rbp, [rax-188h]
0x180012ef5  sub     rsp, 250h
0x180012efc  movaps  xmmword ptr [rax-48h], xmm6
0x180012f00  movaps  xmmword ptr [rax-58h], xmm7
0x180012f04  movaps  xmmword ptr [rax-68h], xmm8
0x180012f09  movaps  xmmword ptr [rax-78h], xmm9
0x180012f0e  movaps  xmmword ptr [rax-88h], xmm10
0x180012f16  movaps  xmmword ptr [rax-98h], xmm11
0x180012f1e  mov     r13, r8
0x180012f21  mov     r15, rdx
0x180012f24  mov     r12, rcx
0x180012f27  xor     edi, edi
0x180012f29  mov     [rsp+280h+var_218], rdi
0x180012f2e  mov     [rsp+280h+var_238], rdi
0x180012f33  mov     [rsp+280h+var_248], rdi
0x180012f38  mov     [rsp+280h+var_220], rdi
0x180012f3d  mov     [rsp+280h+var_240], rdi
0x180012f42  mov     [rsp+280h+var_230], rdi
0x180012f47  mov     [rsp+280h+var_208], rdi
0x180012f4c  mov     [rsp+280h+var_210], rdi
0x180012f51  mov     [rsp+280h+var_228], rdi
0x180012f56  lea     rax, [rbp+180h+var_1D0]
0x180012f5a  mov     [rbp+180h+var_1E0], rax
0x180012f5e  lea     rax, [rbp+180h+var_1D0]
0x180012f62  mov     [rbp+180h+var_1D8], rax
0x180012f66  mov     [rbp+180h+var_1D0], di
0x180012f6a  lea     rax, [rbp+180h+var_1B0]
0x180012f6e  mov     [rbp+180h+var_1C0], rax
0x180012f72  lea     rax, [rbp+180h+var_1B0]
0x180012f76  mov     [rbp+180h+var_1B8], rax
0x180012f7a  mov     [rbp+180h+var_1B0], di
0x180012f7e  lea     rax, [rbp+180h+var_1F0]
0x180012f82  mov     [rbp+180h+psz], rax
0x180012f86  lea     rax, [rbp+180h+var_1F0]
0x180012f8a  mov     [rbp+180h+var_1F8], rax
0x180012f8e  mov     [rbp+180h+var_1F0], di
0x180012f92  lea     ebx, [rdi+1]
0x180012f95  mov     r14d, edi
0x180012f98  cmp     [rbp+180h+arg_60], ebx
0x180012f9e  jz      short loc_180012FAD
0x180012fa0  cmp     [rbp+180h+arg_48], ebx
0x180012fa6  setnz   r14b
0x180012faa  add     r14d, ebx
0x180012fad  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x180012fb4  lea     rcx, [rbp+180h+var_1E0]
0x180012fb8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180012fbd  test    al, al
0x180012fbf  jnz     loc_1800130BB
0x180012fc5  lea     rax, [rbp+180h+var_1F0]
0x180012fc9  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180012fd0  mov     rcx, [rbp+180h+psz]; void *
0x180012fd4  cmp     rcx, rax
0x180012fd7  jz      short loc_180012FE1
0x180012fd9  mov     rdx, rbx; struct std::nothrow_t *
0x180012fdc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012fe1  lea     rax, [rbp+180h+var_1B0]
0x180012fe5  mov     rcx, [rbp+180h+var_1C0]; void *
0x180012fe9  cmp     rcx, rax
0x180012fec  jz      short loc_180012FF6
0x180012fee  mov     rdx, rbx; struct std::nothrow_t *
0x180012ff1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012ff6  lea     rax, [rbp+180h+var_1D0]
0x180012ffa  mov     rcx, [rbp+180h+var_1E0]; void *
0x180012ffe  cmp     rcx, rax
0x180013001  jz      short loc_18001300B
0x180013003  mov     rdx, rbx; struct std::nothrow_t *
0x180013006  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001300b  mov     rcx, [rsp+280h+var_228]
0x180013010  test    rcx, rcx
0x180013013  jz      short loc_180013021
0x180013015  mov     rax, [rcx]
0x180013018  mov     rax, [rax+10h]
0x18001301c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013021  mov     rcx, [rsp+280h+var_210]
0x180013026  test    rcx, rcx
0x180013029  jz      short loc_180013037
0x18001302b  mov     rax, [rcx]
0x18001302e  mov     rax, [rax+10h]
0x180013032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013037  mov     rcx, [rsp+280h+var_208]
0x18001303c  test    rcx, rcx
0x18001303f  jz      short loc_18001304D
0x180013041  mov     rax, [rcx]
0x180013044  mov     rax, [rax+10h]
0x180013048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001304d  mov     rcx, [rsp+280h+var_230]
0x180013052  test    rcx, rcx
0x180013055  jz      short loc_180013063
0x180013057  mov     rax, [rcx]
0x18001305a  mov     rax, [rax+10h]
0x18001305e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013063  mov     rcx, [rsp+280h+var_240]
0x180013068  test    rcx, rcx
0x18001306b  jz      short loc_180013079
0x18001306d  mov     rax, [rcx]
0x180013070  mov     rax, [rax+10h]
0x180013074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013079  mov     rcx, [rsp+280h+var_220]
0x18001307e  test    rcx, rcx
0x180013081  jz      short loc_180013090
0x180013083  mov     rax, [rcx]
0x180013086  mov     rax, [rax+10h]
0x18001308a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001308f  nop
0x180013090  lea     rcx, [rsp+280h+var_248]
0x180013095  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001309a  nop
0x18001309b  lea     rcx, [rsp+280h+var_238]
0x1800130a0  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1800130a5  nop
0x1800130a6  lea     rcx, [rsp+280h+var_218]
0x1800130ab  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1800130b0  nop
0x1800130b1  mov     eax, 8007000Eh
0x1800130b6  jmp     loc_180016B07
0x1800130bb  lea     rdx, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x1800130c2  lea     rcx, [rbp+180h+psz]
0x1800130c6  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800130cb  test    al, al
0x1800130cd  jnz     loc_1800131C4
0x1800130d3  lea     rax, [rbp+180h+var_1F0]
0x1800130d7  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800130de  mov     rcx, [rbp+180h+psz]; void *
0x1800130e2  cmp     rcx, rax
0x1800130e5  jz      short loc_1800130EF
0x1800130e7  mov     rdx, rbx; struct std::nothrow_t *
0x1800130ea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800130ef  lea     rax, [rbp+180h+var_1B0]
0x1800130f3  mov     rcx, [rbp+180h+var_1C0]; void *
0x1800130f7  cmp     rcx, rax
0x1800130fa  jz      short loc_180013104
0x1800130fc  mov     rdx, rbx; struct std::nothrow_t *
0x1800130ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013104  lea     rax, [rbp+180h+var_1D0]
0x180013108  mov     rcx, [rbp+180h+var_1E0]; void *
0x18001310c  cmp     rcx, rax
0x18001310f  jz      short loc_180013119
0x180013111  mov     rdx, rbx; struct std::nothrow_t *
0x180013114  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013119  mov     rcx, [rsp+280h+var_228]
0x18001311e  test    rcx, rcx
0x180013121  jz      short loc_18001312F
0x180013123  mov     rax, [rcx]
0x180013126  mov     rax, [rax+10h]
0x18001312a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001312f  mov     rcx, [rsp+280h+var_210]
0x180013134  test    rcx, rcx
0x180013137  jz      short loc_180013145
0x180013139  mov     rax, [rcx]
0x18001313c  mov     rax, [rax+10h]
0x180013140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013145  mov     rcx, [rsp+280h+var_208]
0x18001314a  test    rcx, rcx
0x18001314d  jz      short loc_18001315B
0x18001314f  mov     rax, [rcx]
0x180013152  mov     rax, [rax+10h]
0x180013156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001315b  mov     rcx, [rsp+280h+var_230]
0x180013160  test    rcx, rcx
0x180013163  jz      short loc_180013171
0x180013165  mov     rax, [rcx]
0x180013168  mov     rax, [rax+10h]
0x18001316c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013171  mov     rcx, [rsp+280h+var_240]
0x180013176  test    rcx, rcx
0x180013179  jz      short loc_180013187
0x18001317b  mov     rax, [rcx]
0x18001317e  mov     rax, [rax+10h]
0x180013182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013187  mov     rcx, [rsp+280h+var_220]
0x18001318c  test    rcx, rcx
0x18001318f  jz      short loc_18001319E
0x180013191  mov     rax, [rcx]
0x180013194  mov     rax, [rax+10h]
0x180013198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001319d  nop
0x18001319e  lea     rcx, [rsp+280h+var_248]
0x1800131a3  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1800131a8  nop
0x1800131a9  lea     rcx, [rsp+280h+var_238]
0x1800131ae  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1800131b3  nop
0x1800131b4  lea     rcx, [rsp+280h+var_218]
0x1800131b9  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1800131be  nop
0x1800131bf  jmp     loc_1800130B1
0x1800131c4  mov     [rbp+180h+var_170], edi
0x1800131c7  mov     rsi, [rbp+180h+arg_38]
0x1800131ce  test    rsi, rsi
0x1800131d1  jz      loc_180013B67
0x1800131d7  lea     rdx, psz; "S-1-5-18"
0x1800131de  mov     rcx, rsi
0x1800131e1  call    cs:__imp__o__wcsicmp
0x1800131e7  test    eax, eax
0x1800131e9  jz      loc_180013B67
0x1800131ef  mov     [rbp+180h+arg_60], edi
0x1800131f5  lea     rdx, aS1532545; "S-1-5-32-545"
0x1800131fc  mov     rcx, rsi
0x1800131ff  call    cs:__imp__o__wcsicmp
0x180013205  test    eax, eax
0x180013207  jnz     loc_18001353D
0x18001320d  mov     rcx, [rbp+180h+var_1E0]
0x180013211  mov     [rbp+180h+var_1D8], rcx
0x180013215  mov     [rcx], di
0x180013218  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x18001321f  lea     rcx, [rbp+180h+var_1E0]
0x180013223  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180013228  test    al, al
0x18001322a  jnz     loc_180013321
0x180013230  lea     rax, [rbp+180h+var_1F0]
0x180013234  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001323b  mov     rcx, [rbp+180h+psz]; void *
0x18001323f  cmp     rcx, rax
0x180013242  jz      short loc_18001324C
0x180013244  mov     rdx, rbx; struct std::nothrow_t *
0x180013247  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001324c  lea     rax, [rbp+180h+var_1B0]
0x180013250  mov     rcx, [rbp+180h+var_1C0]; void *
0x180013254  cmp     rcx, rax
0x180013257  jz      short loc_180013261
0x180013259  mov     rdx, rbx; struct std::nothrow_t *
0x18001325c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013261  lea     rax, [rbp+180h+var_1D0]
0x180013265  mov     rcx, [rbp+180h+var_1E0]; void *
0x180013269  cmp     rcx, rax
0x18001326c  jz      short loc_180013276
0x18001326e  mov     rdx, rbx; struct std::nothrow_t *
0x180013271  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013276  mov     rcx, [rsp+280h+var_228]
0x18001327b  test    rcx, rcx
0x18001327e  jz      short loc_18001328C
0x180013280  mov     rax, [rcx]
0x180013283  mov     rax, [rax+10h]
0x180013287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001328c  mov     rcx, [rsp+280h+var_210]
0x180013291  test    rcx, rcx
0x180013294  jz      short loc_1800132A2
0x180013296  mov     rax, [rcx]
0x180013299  mov     rax, [rax+10h]
0x18001329d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132a2  mov     rcx, [rsp+280h+var_208]
0x1800132a7  test    rcx, rcx
0x1800132aa  jz      short loc_1800132B8
0x1800132ac  mov     rax, [rcx]
0x1800132af  mov     rax, [rax+10h]
0x1800132b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132b8  mov     rcx, [rsp+280h+var_230]
0x1800132bd  test    rcx, rcx
0x1800132c0  jz      short loc_1800132CE
0x1800132c2  mov     rax, [rcx]
0x1800132c5  mov     rax, [rax+10h]
0x1800132c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132ce  mov     rcx, [rsp+280h+var_240]
0x1800132d3  test    rcx, rcx
0x1800132d6  jz      short loc_1800132E4
0x1800132d8  mov     rax, [rcx]
0x1800132db  mov     rax, [rax+10h]
0x1800132df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132e4  mov     rcx, [rsp+280h+var_220]
0x1800132e9  test    rcx, rcx
0x1800132ec  jz      short loc_1800132FB
0x1800132ee  mov     rax, [rcx]
0x1800132f1  mov     rax, [rax+10h]
0x1800132f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132fa  nop
0x1800132fb  lea     rcx, [rsp+280h+var_248]
0x180013300  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180013305  nop
0x180013306  lea     rcx, [rsp+280h+var_238]
0x18001330b  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x180013310  nop
0x180013311  lea     rcx, [rsp+280h+var_218]
0x180013316  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x18001331b  nop
0x18001331c  jmp     loc_1800130B1
0x180013321  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180013328  lea     rcx, [rbp+180h+var_1C0]
0x18001332c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180013331  mov     rcx, [rbp+180h+psz]; void *
0x180013335  test    al, al
0x180013337  jnz     loc_18001342A
0x18001333d  lea     rax, [rbp+180h+var_1F0]
0x180013341  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180013348  cmp     rcx, rax
0x18001334b  jz      short loc_180013355
0x18001334d  mov     rdx, rbx; struct std::nothrow_t *
0x180013350  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013355  lea     rax, [rbp+180h+var_1B0]
0x180013359  mov     rcx, [rbp+180h+var_1C0]; void *
  ... truncated ...
```
