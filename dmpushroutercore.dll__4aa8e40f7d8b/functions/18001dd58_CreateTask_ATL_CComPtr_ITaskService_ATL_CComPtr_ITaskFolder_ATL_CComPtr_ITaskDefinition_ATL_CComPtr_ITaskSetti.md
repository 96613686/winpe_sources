# CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)

- ea: `0x18001dd58`
- end: `0x18001ef07`
- name: `?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z`
- size: `4527`
- prototype: `__int64 __fastcall(LPVOID *, BSTR ***, _QWORD *, _QWORD *, OLECHAR *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, int, int, int, int Data)`
- caller_count: `9`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180020418`
- `0x180020b70`
- `0x1800211c0`
- `0x180021748`
- `0x180021d40`
- `0x180022164`
- `0x1800225f8`
- `0x180022e88`
- `0x1800384c0`

## callees

- `0x180003a14`
- `0x18000604c`
- `0x180013d4c`
- `0x18001cc8c`
- `0x18001ccfc`
- `0x18001cdb8`
- `0x18001ce6c`
- `0x18001d8f4`
- `0x18001dd58`
- `0x180023bc0`
- `0x18003593c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001de80`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001de9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001de80`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001de9b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e159`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e159`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e3d1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e45d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e4e1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e525`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e5f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e66e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e6ae`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e8e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e937`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e3d1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e45d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e4e1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e525`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e5f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e66e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e6ae`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e8e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e937`
- `OLEAUT32!__imp_VariantInit` at `0x18001e291`
- `OLEAUT32!__imp_VariantInit` at `0x18001e2a6`
- `OLEAUT32!__imp_VariantInit` at `0x18001e2bb`
- `OLEAUT32!__imp_VariantInit` at `0x18001e2ce`
- `OLEAUT32!__imp_VariantInit` at `0x18001e291`
- `OLEAUT32!__imp_VariantInit` at `0x18001e2a6`
- `OLEAUT32!__imp_VariantInit` at `0x18001e2bb`
- `OLEAUT32!__imp_VariantInit` at `0x18001e2ce`
- `OLEAUT32!__imp_VariantClear` at `0x18001e34a`
- `OLEAUT32!__imp_VariantClear` at `0x18001e35c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e36e`
- `OLEAUT32!__imp_VariantClear` at `0x18001e380`
- `OLEAUT32!__imp_VariantClear` at `0x18001e4d4`
- `OLEAUT32!__imp_VariantClear` at `0x18001e578`
- `OLEAUT32!__imp_VariantClear` at `0x18001e65c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e6fa`
- `OLEAUT32!__imp_VariantClear` at `0x18001e987`
- `OLEAUT32!__imp_VariantClear` at `0x18001e34a`
- `OLEAUT32!__imp_VariantClear` at `0x18001e35c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e36e`
- `OLEAUT32!__imp_VariantClear` at `0x18001e380`
- `OLEAUT32!__imp_VariantClear` at `0x18001e4d4`
- `OLEAUT32!__imp_VariantClear` at `0x18001e578`
- `OLEAUT32!__imp_VariantClear` at `0x18001e65c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e6fa`
- `OLEAUT32!__imp_VariantClear` at `0x18001e987`

## string_xrefs

- `0x18001e10f`: `CreateTask`
- `0x18001e12d`: `22CoCreateTaskScheduler2`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CreateTask(
        LPVOID *a1,
        BSTR ***a2,
        _QWORD *a3,
        _QWORD *a4,
        OLECHAR *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned int a9,
        int a10,
        int a11,
        int a12,
        int Data)
{
  unsigned int v16; // r14d
  char v17; // al
  OLECHAR *v18; // rcx
  const wchar_t *v19; // rdx
  char v20; // al
  __int64 v21; // rdx
  __int64 v22; // rcx
  const WCHAR *v24; // r8
  unsigned int v25; // edi
  void (*v26)(void); // rax
  LPVOID v27; // rdi
  __int64 (__fastcall *v28)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v29; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v31; // xmm8
  IRecordInfo *v32; // xmm9_8
  __int128 v33; // xmm6
  IRecordInfo *v34; // xmm7_8
  HRESULT v35; // eax
  HRESULT v36; // eax
  HRESULT v37; // eax
  HRESULT v38; // eax
  LPVOID v39; // rdi
  __int64 (__fastcall *v40)(LPVOID, BSTR, BSTR ***); // r12
  BSTR *v41; // rbx
  BSTR v42; // rax
  BSTR **v43; // r12
  const OLECHAR *v44; // rdi
  BSTR *v45; // rbx
  BSTR v46; // rax
  BSTR **v47; // r12
  OLECHAR *v48; // rbx
  __int128 v49; // xmm6
  const OLECHAR *v50; // rdi
  IRecordInfo *v51; // xmm7_8
  BSTR *v52; // rbx
  BSTR v53; // rax
  BSTR **v54; // r12
  BSTR *v55; // rbx
  BSTR v56; // rax
  BSTR **v57; // r12
  OLECHAR *v58; // rbx
  __int128 v59; // xmm6
  IRecordInfo *v60; // xmm7_8
  BSTR *v61; // rbx
  BSTR v62; // rax
  BSTR **v63; // rbx
  __int64 *v64; // rdi
  __int64 v65; // r15
  BSTR *v66; // rbx
  BSTR v67; // rax
  __int64 *v68; // rdi
  OLECHAR *v69; // rbx
  __int64 v70; // r15
  BSTR v71; // rax
  __int64 (__fastcall *v72)(__int64 *, VARIANTARG *); // rax
  HRESULT v73; // eax
  __int64 *v74; // rbx
  __int64 v75; // rax
  __int64 (__fastcall *v76)(__int64 *); // rdi
  __int64 v77; // rbx
  __int64 (__fastcall *v78)(__int64); // rdi
  __int64 v79; // rbx
  __int64 (__fastcall *v80)(__int64); // rdi
  __int64 v81; // rbx
  __int64 (__fastcall *v82)(__int64, __int64); // rdi
  _bstr_t *v83; // rax
  __int64 v84; // rdx
  __int64 (__fastcall *v85)(__int64 *); // rdi
  __int64 v86; // rdx
  __int64 (__fastcall *v87)(__int64 *); // rdi
  __int64 v88; // [rsp+38h] [rbp-D0h] BYREF
  __int64 *v89; // [rsp+40h] [rbp-C8h] BYREF
  BSTR **v90; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v91; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v92; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v93; // [rsp+60h] [rbp-A8h] BYREF
  BSTR **v94; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v95; // [rsp+70h] [rbp-98h] BYREF
  __int64 v96; // [rsp+78h] [rbp-90h] BYREF
  OLECHAR *v97; // [rsp+80h] [rbp-88h] BYREF
  OLECHAR *v98; // [rsp+88h] [rbp-80h]
  _WORD v99[8]; // [rsp+90h] [rbp-78h] BYREF
  OLECHAR *v100; // [rsp+A0h] [rbp-68h] BYREF
  OLECHAR *v101; // [rsp+A8h] [rbp-60h]
  _WORD v102[8]; // [rsp+B0h] [rbp-58h] BYREF
  OLECHAR *psz[2]; // [rsp+C0h] [rbp-48h] BYREF
  _WORD v104[8]; // [rsp+D0h] [rbp-38h] BYREF
  BSTR *v105; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v106[2]; // [rsp+E8h] [rbp-20h] BYREF
  BSTR *v107; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG v108; // [rsp+100h] [rbp-8h] BYREF
  int v109; // [rsp+118h] [rbp+10h]
  int v110; // [rsp+11Ch] [rbp+14h]
  VARIANTARG v111; // [rsp+120h] [rbp+18h] BYREF
  VARIANTARG v112; // [rsp+138h] [rbp+30h] BYREF
  VARIANTARG v113; // [rsp+158h] [rbp+50h] BYREF
  VARIANTARG pvarg; // [rsp+170h] [rbp+68h] BYREF
  __int128 v115; // [rsp+188h] [rbp+80h] BYREF
  IRecordInfo *v116; // [rsp+198h] [rbp+90h]
  __int128 v117; // [rsp+1A8h] [rbp+A0h] BYREF
  IRecordInfo *v118; // [rsp+1B8h] [rbp+B0h]
  __int128 v119; // [rsp+1C8h] [rbp+C0h] BYREF
  IRecordInfo *v120; // [rsp+1D8h] [rbp+D0h]

  v16 = 0;
  v94 = 0;
  v100 = v102;
  v101 = v102;
  psz[0] = v104;
  psz[1] = v104;
  v97 = v99;
  v98 = v99;
  v90 = 0;
  v88 = 0;
  v93 = 0;
  v89 = 0;
  v91 = 0;
  v96 = 0;
  v95 = 0;
  v92 = 0;
  v102[0] = 0;
  v104[0] = 0;
  v99[0] = 0;
  if ( Data != 1 )
  {
    LOBYTE(v16) = a10 != 1;
    ++v16;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v100,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FA;;;")
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v97,
                           L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;LS)(A;OICI;GA;;;") )
  {
    goto LABEL_22;
  }
  v110 = 0;
  if ( a8 && (unsigned int)_o__wcsicmp(a8, L"S-1-5-18") )
  {
    v109 = 0;
    if ( (unsigned int)_o__wcsicmp(a8, L"S-1-5-32-545") )
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &v100,
                               a8)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &v100,
                               L")")
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               psz,
                               a8)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               psz,
                               L"\\EnterpriseMgmt")
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &v97,
                               a8) )
      {
        goto LABEL_22;
      }
      v19 = L")";
LABEL_21:
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               &v97,
                               v19) )
        goto LABEL_22;
      Data = CoCreateTaskScheduler(v22, v21, a1);
      v106[0] = "CreateTask";
      v106[1] = &Data;
      if ( Data < 0 )
      {
        v24 = L"22CoCreateTaskScheduler2";
LABEL_50:
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, v24, 4u, &Data, 4u);
        v25 = Data;
LABEL_51:
        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v106);
        if ( v97 != v99 )
          operator delete(v97, (const struct std::nothrow_t *)&std::nothrow);
        if ( psz[0] != v104 )
          operator delete(psz[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v100 != v102 )
          operator delete(v100, (const struct std::nothrow_t *)&std::nothrow);
        if ( v92 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        if ( v95 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
        if ( v96 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
        if ( v91 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v89 )
          (*(void (__fastcall **)(__int64 *))(*v89 + 16))(v89);
        if ( v93 )
          (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
        if ( v88 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
        if ( v90 )
          ((void (__fastcall *)(BSTR **))(*v90)[2])(v90);
        if ( !v94 )
          return v25;
        v26 = (void (*)(void))(*v94)[2];
LABEL_75:
        v26();
        return v25;
      }
      v27 = *a1;
      v28 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*a1 + 80LL);
      VariantInit(&pvarg);
      v29 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v113);
      v31 = *(_OWORD *)&v113.vt;
      v32 = v113.pRecInfo;
      VariantInit(&v111);
      v33 = *(_OWORD *)&v111.vt;
      v34 = v111.pRecInfo;
      VariantInit(&v108);
      v112 = v108;
      v115 = v29;
      v116 = pRecInfo;
      v117 = v31;
      v118 = v32;
      v119 = v33;
      v120 = v34;
      Data = v28(v27, &v112, &v119, &v117, &v115);
      v35 = VariantClear(&v108);
      if ( v35 < 0 )
        _com_issue_error(v35);
      v36 = VariantClear(&v111);
      if ( v36 < 0 )
        _com_issue_error(v36);
      v37 = VariantClear(&v113);
      if ( v37 < 0 )
        _com_issue_error(v37);
      v38 = VariantClear(&pvarg);
      if ( v38 < 0 )
        _com_issue_error(v38);
      if ( Data < 0 )
      {
        v24 = L"23Connect";
        goto LABEL_50;
      }
      v39 = *a1;
      v40 = *(__int64 (__fastcall **)(LPVOID, BSTR, BSTR ***))(*(_QWORD *)*a1 + 56LL);
      v41 = (BSTR *)operator new(0x18u);
      v41[1] = 0;
      *((_DWORD *)v41 + 4) = 1;
      v42 = SysAllocString(L"\\");
      *v41 = v42;
      if ( v42 )
      {
        v107 = v41;
        Data = v40(v39, v42, &v94);
        _bstr_t::~_bstr_t((_bstr_t *)&v107);
        v25 = Data;
        if ( Data < 0 )
          goto LABEL_51;
        v43 = v94;
        v44 = psz[0];
        *(_QWORD *)&v111.vt = "spRootFolder->GetFolder()";
        v111.llVal = (LONGLONG)&Data;
        v107 = *v94;
        v45 = (BSTR *)operator new(0x18u);
        v45[1] = 0;
        *((_DWORD *)v45 + 4) = 1;
        v46 = SysAllocString(v44);
        *v45 = v46;
        if ( v46 || !v44 )
        {
          v105 = v45;
          Data = ((__int64 (__fastcall *)(BSTR **, BSTR, BSTR ***))v107[9])(v43, v46, &v90);
          _bstr_t::~_bstr_t((_bstr_t *)&v105);
          if ( (unsigned int)(Data + 2147024894) <= 1 )
          {
            v47 = v94;
            v48 = v97;
            v105 = *v94;
            v108.vt = 0;
            VariantClear(&v108);
            v108.vt = 8;
            v108.llVal = (LONGLONG)SysAllocString(v48);
            if ( !v108.llVal && v48 )
            {
              v108.lVal = -2147024882;
              v108.vt = 10;
              ATL::AtlThrowImpl(-2147024882);
            }
            v49 = *(_OWORD *)&v108.vt;
            v50 = psz[0];
            v51 = v108.pRecInfo;
            v52 = (BSTR *)operator new(0x18u);
            v52[1] = 0;
            *((_DWORD *)v52 + 4) = 1;
            v53 = SysAllocString(v50);
            *v52 = v53;
            if ( !v53 && v50 )
              _com_issue_error(-2147024882);
            v107 = v52;
            *(_OWORD *)&v112.vt = v49;
            v112.pRecInfo = v51;
            Data = ((__int64 (__fastcall *)(BSTR **, BSTR, VARIANTARG *, BSTR ***))v105[11])(v47, v53, &v112, &v90);
            _bstr_t::~_bstr_t((_bstr_t *)&v107);
            VariantClear(&v108);
            v25 = Data;
            if ( Data < 0 )
              goto LABEL_93;
          }
          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v111);
          if ( a5 )
          {
            v54 = v90;
            *(_QWORD *)&v111.vt = "spEnterpriseMgmtFolder->GetFolder()";
            v111.llVal = (LONGLONG)&Data;
            v105 = (BSTR *)(*v90)[9];
            v55 = (BSTR *)operator new(0x18u);
            v55[1] = 0;
            *((_DWORD *)v55 + 4) = 1;
            v56 = SysAllocString(a5);
            *v55 = v56;
            if ( !v56 )
              goto LABEL_174;
            v107 = v55;
            Data = ((__int64 (__fastcall *)(BSTR **, BSTR, BSTR ***))v105)(v54, v56, a2);
            _bstr_t::~_bstr_t((_bstr_t *)&v107);
            if ( (unsigned int)(Data + 2147024894) <= 1 )
            {
              v57 = v90;
              v58 = v97;
              v105 = *v90;
              v108.vt = 0;
              VariantClear(&v108);
              v108.vt = 8;
              v108.llVal = (LONGLONG)SysAllocString(v58);
              if ( !v108.llVal && v58 )
              {
                v108.lVal = -2147024882;
                v108.vt = 10;
                ATL::AtlThrowImpl(-2147024882);
              }
              v59 = *(_OWORD *)&v108.vt;
              v60 = v108.pRecInfo;
              v61 = (BSTR *)operator new(0x18u);
              v61[1] = 0;
              *((_DWORD *)v61 + 4) = 1;
              v62 = SysAllocString(a5);
              *v61 = v62;
              if ( !v62 )
                _com_issue_error(-2147024882);
              v107 = v61;
              *(_OWORD *)&v112.vt = v59;
              v112.pRecInfo = v60;
              Data = ((__int64 (__fastcall *)(BSTR **, BSTR, VARIANTARG *, BSTR ***))v105[11])(v57, v62, &v112, a2);
              _bstr_t::~_bstr_t((_bstr_t *)&v107);
              VariantClear(&v108);
              v25 = Data;
              if ( Data < 0 )
              {
LABEL_93:
                EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v111);
                goto LABEL_51;
              }
            }
            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)&v111);
          }
          else
          {
            v63 = v90;
            if ( *a2 != v90 )
            {
              if ( v90 )
                ((void (__fastcall *)(BSTR **))(*v90)[1])(v90);
              if ( *a2 )
                ((void (__fastcall *)(BSTR **))(**a2)[2])(*a2);
              *a2 = v63;
            }
          }
          Data = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD *))(*(_QWORD *)*a1 + 72LL))(*a1, 0, a3);
          v25 = Data;
          if ( Data < 0 )
            goto LABEL_109;
          Data = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 56LL))(*a3, &v93);
          v25 = Data;
          if ( Data < 0 )
            goto LABEL_109;
          v64 = v93;
          v65 = *v93;
          v66 = (BSTR *)operator new(0x18u);
          v66[1] = 0;
          *((_DWORD *)v66 + 4) = 1;
          v67 = SysAllocString(L"Microsoft Corporation");
          *v66 = v67;
          if ( v67 )
          {
            v105 = v66;
            Data = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v65 + 80))(v64, v67);
            _bstr_t::~_bstr_t((_bstr_t *)&v105);
            v25 = Data;
            if ( Data < 0 )
              goto LABEL_51;
            v68 = v93;
            v69 = v100;
            v70 = *v93;
            v71 = SysAllocString(v100);
            if ( !v71 && v69 )
              _com_issue_error(-2147024882);
            v108.llVal = (LONGLONG)v71;
            v72 = *(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v70 + 176);
            v108.vt = 8;
            v112 = v108;
            Data = v72(v68, &v112);
            v73 = VariantClear(&v108);
            if ( v73 < 0 )
              _com_issue_error(v73);
            v25 = Data;
            if ( Data < 0 )
              goto LABEL_51;
            Data = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 120LL))(*a3, &v89);
            v25 = Data;
            if ( Data < 0 )
              goto LABEL_109;
            v74 = v89;
            v75 = *v89;
            if ( v109 )
            {
              v76 = *(__int64 (__fastcall **)(__int64 *))(v75 + 128);
              _bstr_t::_bstr_t((_bstr_t *)&v105, "SYSTEM");
              Data = v76(v74);
              _bstr_t::~_bstr_t((_bstr_t *)&v105);
              v25 = Data;
              if ( Data < 0 )
                goto LABEL_51;
            }
            else
            {
              if ( v110 )
              {
                v85 = *(__int64 (__fastcall **)(__int64 *))(v75 + 128);
                _bstr_t::_bstr_t((_bstr_t *)&v105, L"S-1-5-32-545");
                Data = v85(v74);
                _bstr_t::~_bstr_t((_bstr_t *)&v105);
                v25 = Data;
                if ( Data < 0 )
                  goto LABEL_51;
                v86 = 1;
              }
              else
              {
                v87 = *(__int64 (__fastcall **)(__int64 *))(v75 + 96);
                _bstr_t::_bstr_t((_bstr_t *)&v105, a8);
                Data = v87(v74);
                _bstr_t::~_bstr_t((_bstr_t *)&v105);
                v25 = Data;
                if ( Data < 0 )
                  goto LABEL_51;
                Data = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v89 + 112))(v89, 3);
                v25 = Data;
                if ( Data < 0 )
                  goto LABEL_109;
                v86 = a9;
              }
              Data = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v89 + 144))(v89, v86);
              v25 = Data;
              if ( Data < 0 )
                goto LABEL_109;
            }
            Data = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 88LL))(*a3, &v88);
            v25 = Data;
            if ( Data >= 0 )
            {
              Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v88 + 128LL))(v88, 0);
              v25 = Data;
              if ( Data >= 0 )
              {
                Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v88 + 144LL))(v88, 0);
                v25 = Data;
                if ( Data >= 0 )
                {
                  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v88 + 112LL))(v88, v16);
                  v25 = Data;
                  if ( Data >= 0 )
                  {
                    Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v88 + 352LL))(v88, 0);
                    v25 = Data;
                    if ( Data >= 0 )
                    {
                      v77 = v88;
                      v78 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v88 + 224LL);
                      _bstr_t::_bstr_t((_bstr_t *)&v105, L"PT1H");
                      Data = v78(v77);
                      _bstr_t::~_bstr_t((_bstr_t *)&v105);
                      v25 = Data;
                      if ( Data < 0 )
                        goto LABEL_51;
                      Data = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v88)(
                               v88,
                               &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
                               a4);
                      v25 = Data;
                      if ( Data >= 0 )
                      {
                        Data = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 176LL))(
                                 *a4,
                                 (unsigned __int16)((a11 != 1) - 1));
                        v25 = Data;
                        if ( Data >= 0 )
                        {
                          Data = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 208LL))(
                                   *a4,
                                   (unsigned __int16)((a12 != 1) - 1));
                          v25 = Data;
                          if ( Data >= 0 )
                          {
                            Data = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a4 + 400LL))(
                                     *a4,
                                     0xFFFFFFFFLL);
                            v25 = Data;
                            if ( Data >= 0 )
                            {
                              Data = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v88 + 312LL))(v88, &v91);
                              v25 = Data;
                              if ( Data >= 0 )
                              {
                                Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 96LL))(v91, 0);
                                v25 = Data;
                                if ( Data >= 0 )
                                {
                                  Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 64LL))(v91, 0);
                                  v25 = Data;
                                  if ( Data >= 0 )
                                  {
                                    Data = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 80LL))(v91, 0);
                                    v25 = Data;
                                    if ( Data >= 0 )
                                    {
                                      Data = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 136LL))(
                                               *a3,
                                               &v96);
                                      v25 = Data;
                                      if ( Data >= 0 )
                                      {
                                        Data = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v96 + 96LL))(
                                                 v96,
                                                 0,
                                                 &v95);
                                        v25 = Data;
                                        if ( Data >= 0 )
                                        {
                                          Data = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v95)(
                                                   v95,
                                                   &IID_IExecAction,
                                                   &v92);
                                          v25 = Data;
                                          if ( Data >= 0 )
                                          {
                                            v79 = v92;
                                            v80 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v92 + 88LL);
                                            _bstr_t::_bstr_t((_bstr_t *)&v105, a6);
                                            Data = v80(v79);
                                            _bstr_t::~_bstr_t((_bstr_t *)&v105);
                                            v25 = Data;
                                            if ( Data < 0 )
                                              goto LABEL_51;
                                            v81 = v92;
                                            v82 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 104LL);
                                            v83 = _bstr_t::_bstr_t((_bstr_t *)&v105, a7);
                                            if ( *(_QWORD *)v83 )
                                              v84 = **(_QWORD **)v83;
                                            else
                                              v84 = 0;
                                            v25 = v82(v81, v84);
                                            _bstr_t::~_bstr_t((_bstr_t *)&v105);
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
LABEL_109:
            EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v106);
            if ( v97 != v99 )
              operator delete(v97, (const struct std::nothrow_t *)&std::nothrow);
            if ( psz[0] != v104 )
              operator delete(psz[0], (const struct std::nothrow_t *)&std::nothrow);
            if ( v100 != v102 )
              operator delete(v100, (const struct std::nothrow_t *)&std::nothrow);
            if ( v92 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
            if ( v95 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
            if ( v96 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
            if ( v91 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
            if ( v89 )
              (*(void (__fastcall **)(__int64 *))(*v89 + 16))(v89);
            if ( v93 )
              (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
            if ( v88 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
            if ( v90 )
              ((void (__fastcall *)(BSTR **))(*v90)[2])(v90);
            if ( !v94 )
              return v25;
            v26 = (void (*)(void))(*v94)[2];
            goto LABEL_75;
          }
        }
      }
LABEL_174:
      _com_issue_error(-2147024882);
    }
    v101 = v100;
    *v100 = 0;
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            &v100,
                            L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)") )
    {
      v17 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
              psz,
              L"\\Microsoft\\Windows\\EnterpriseMgmt");
      v18 = v97;
      if ( v17 )
      {
        v110 = 1;
LABEL_20:
        v98 = v18;
        v19 = L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)";
        *v18 = 0;
        goto LABEL_21;
      }
      goto LABEL_23;
    }
LABEL_22:
    v18 = v97;
    goto LABEL_23;
  }
  v101 = v100;
  *v100 = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v100,
                           L"D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;LS)") )
    goto LABEL_22;
  v20 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          psz,
          L"\\Microsoft\\Windows\\EnterpriseMgmt");
  v18 = v97;
  if ( v20 )
  {
    v109 = 1;
    goto LABEL_20;
  }
LABEL_23:
  if ( v18 != v99 )
    operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
  if ( psz[0] != v104 )
    operator delete(psz[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v100 != v102 )
    operator delete(v100, (const struct std::nothrow_t *)&std::nothrow);
  if ( v92 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
  if ( v95 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
  if ( v96 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  if ( v91 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
  if ( v89 )
    (*(void (__fastcall **)(__int64 *))(*v89 + 16))(v89);
  if ( v93 )
    (*(void (__fastcall **)(__int64 *))(*v93 + 16))(v93);
  if ( v88 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
  if ( v90 )
    ((void (__fastcall *)(BSTR **))(*v90)[2])(v90);
  if ( v94 )
    ((void (__fastcall *)(BSTR **))(*v94)[2])(v94);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001dd58  mov     rax, rsp
0x18001dd5b  mov     [rax+10h], rbx
0x18001dd5f  mov     [rax+20h], r9
0x18001dd63  mov     [rax+8], rcx
0x18001dd67  push    rbp
0x18001dd68  push    rsi
0x18001dd69  push    rdi
0x18001dd6a  push    r12
0x18001dd6c  push    r13
0x18001dd6e  push    r14
0x18001dd70  push    r15
0x18001dd72  lea     rbp, [rax-178h]
0x18001dd79  sub     rsp, 240h
0x18001dd80  xor     edi, edi
0x18001dd82  movaps  xmmword ptr [rax-48h], xmm6
0x18001dd86  movaps  xmmword ptr [rax-58h], xmm7
0x18001dd8a  mov     r13, r8
0x18001dd8d  movaps  xmmword ptr [rax-68h], xmm8
0x18001dd92  mov     r15, rdx
0x18001dd95  movaps  xmmword ptr [rax-78h], xmm9
0x18001dd9a  mov     r12, rcx
0x18001dd9d  movaps  xmmword ptr [rax-88h], xmm10
0x18001dda5  lea     ebx, [rdi+1]
0x18001dda8  mov     r14d, edi
0x18001ddab  movaps  xmmword ptr [rax-98h], xmm11
0x18001ddb3  lea     rax, [rbp+170h+var_1C8]
0x18001ddb7  mov     [rsp+270h+var_210], rdi
0x18001ddbc  mov     [rbp+170h+var_1D8], rax
0x18001ddc0  lea     rax, [rbp+170h+var_1C8]
0x18001ddc4  mov     [rbp+170h+var_1D0], rax
0x18001ddc8  lea     rax, [rbp+170h+var_1A8]
0x18001ddcc  mov     [rbp+170h+psz], rax
0x18001ddd0  lea     rax, [rbp+170h+var_1A8]
0x18001ddd4  mov     [rbp+170h+var_1B0], rax
0x18001ddd8  lea     rax, [rbp+170h+var_1E8]
0x18001dddc  mov     [rsp+270h+var_1F8], rax
0x18001dde1  lea     rax, [rbp+170h+var_1E8]
0x18001dde5  mov     [rbp+170h+var_1F0], rax
0x18001dde9  mov     [rsp+270h+var_230], rdi
0x18001ddee  mov     [rsp+270h+var_240], rdi
0x18001ddf3  mov     [rsp+270h+var_218], rdi
0x18001ddf8  mov     [rsp+270h+var_238], rdi
0x18001ddfd  mov     [rsp+270h+var_228], rdi
0x18001de02  mov     [rsp+270h+var_200], rdi
0x18001de07  mov     [rsp+270h+var_208], rdi
0x18001de0c  mov     [rsp+270h+var_220], rdi
0x18001de11  mov     [rbp+170h+var_1C8], di
0x18001de15  mov     [rbp+170h+var_1A8], di
0x18001de19  mov     [rbp+170h+var_1E8], di
0x18001de1d  cmp     [rbp+170h+Data], ebx
0x18001de23  jz      short loc_18001DE32
0x18001de25  cmp     [rbp+170h+arg_48], ebx
0x18001de2b  setnz   r14b
0x18001de2f  add     r14d, ebx
0x18001de32  lea     rdx, aDPAFaBaAFaSyAF_0; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x18001de39  lea     rcx, [rbp+170h+var_1D8]
0x18001de3d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001de42  test    al, al
0x18001de44  jz      loc_18001DFB6
0x18001de4a  lea     rdx, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x18001de51  lea     rcx, [rsp+270h+var_1F8]
0x18001de56  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001de5b  test    al, al
0x18001de5d  jz      loc_18001DFB6
0x18001de63  mov     rsi, [rbp+170h+arg_38]
0x18001de6a  mov     [rbp+170h+var_15C], edi
0x18001de6d  test    rsi, rsi
0x18001de70  jz      loc_18001DF5B
0x18001de76  lea     rdx, aS1518; "S-1-5-18"
0x18001de7d  mov     rcx, rsi
0x18001de80  call    cs:__imp__o__wcsicmp
0x18001de86  test    eax, eax
0x18001de88  jz      loc_18001DF5B
0x18001de8e  lea     rdx, aS1532545; "S-1-5-32-545"
0x18001de95  mov     [rbp+170h+var_160], edi
0x18001de98  mov     rcx, rsi
0x18001de9b  call    cs:__imp__o__wcsicmp
0x18001dea1  test    eax, eax
0x18001dea3  jnz     short loc_18001DEED
0x18001dea5  mov     rcx, [rbp+170h+var_1D8]
0x18001dea9  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x18001deb0  mov     [rbp+170h+var_1D0], rcx
0x18001deb4  mov     [rcx], di
0x18001deb7  lea     rcx, [rbp+170h+var_1D8]
0x18001debb  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001dec0  test    al, al
0x18001dec2  jz      loc_18001DFB6
0x18001dec8  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x18001decf  lea     rcx, [rbp+170h+psz]
0x18001ded3  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001ded8  mov     rcx, [rsp+270h+var_1F8]
0x18001dedd  test    al, al
0x18001dedf  jz      loc_18001DFBB
0x18001dee5  mov     [rbp+170h+var_15C], ebx
0x18001dee8  jmp     loc_18001DF96
0x18001deed  mov     rdx, rsi
0x18001def0  lea     rcx, [rbp+170h+var_1D8]
0x18001def4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001def9  test    al, al
0x18001defb  jz      loc_18001DFB6
0x18001df01  lea     rdx, asc_180041EB8; ")"
0x18001df08  lea     rcx, [rbp+170h+var_1D8]
0x18001df0c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001df11  test    al, al
0x18001df13  jz      loc_18001DFB6
0x18001df19  mov     rdx, rsi
0x18001df1c  lea     rcx, [rbp+170h+psz]
0x18001df20  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001df25  test    al, al
0x18001df27  jz      loc_18001DFB6
0x18001df2d  lea     rdx, aEnterprisemgmt_0; "\\EnterpriseMgmt"
0x18001df34  lea     rcx, [rbp+170h+psz]
0x18001df38  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001df3d  test    al, al
0x18001df3f  jz      short loc_18001DFB6
0x18001df41  mov     rdx, rsi
0x18001df44  lea     rcx, [rsp+270h+var_1F8]
0x18001df49  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001df4e  test    al, al
0x18001df50  jz      short loc_18001DFB6
0x18001df52  lea     rdx, asc_180041EB8; ")"
0x18001df59  jmp     short loc_18001DFA4
0x18001df5b  mov     rcx, [rbp+170h+var_1D8]
0x18001df5f  lea     rdx, aDPAFaBaAFaSyAF; "D:P(A;;FA;;;BA)(A;;FA;;;SY)(A;;FRFX;;;L"...
0x18001df66  mov     [rbp+170h+var_1D0], rcx
0x18001df6a  mov     [rcx], di
0x18001df6d  lea     rcx, [rbp+170h+var_1D8]
0x18001df71  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001df76  test    al, al
0x18001df78  jz      short loc_18001DFB6
0x18001df7a  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x18001df81  lea     rcx, [rbp+170h+psz]
0x18001df85  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001df8a  mov     rcx, [rsp+270h+var_1F8]
0x18001df8f  test    al, al
0x18001df91  jz      short loc_18001DFBB
0x18001df93  mov     [rbp+170h+var_160], ebx
0x18001df96  mov     [rbp+170h+var_1F0], rcx
0x18001df9a  lea     rdx, aDAOiciGaBaAOic_0; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x18001dfa1  mov     [rcx], di
0x18001dfa4  lea     rcx, [rsp+270h+var_1F8]
0x18001dfa9  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18001dfae  test    al, al
0x18001dfb0  jnz     loc_18001E101
0x18001dfb6  mov     rcx, [rsp+270h+var_1F8]; void *
0x18001dfbb  lea     rax, [rbp+170h+var_1E8]
0x18001dfbf  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001dfc6  cmp     rcx, rax
0x18001dfc9  jz      short loc_18001DFD3
0x18001dfcb  mov     rdx, rbx; struct std::nothrow_t *
0x18001dfce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001dfd3  mov     rcx, [rbp+170h+psz]; void *
0x18001dfd7  lea     rax, [rbp+170h+var_1A8]
0x18001dfdb  cmp     rcx, rax
0x18001dfde  jz      short loc_18001DFE8
0x18001dfe0  mov     rdx, rbx; struct std::nothrow_t *
0x18001dfe3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001dfe8  mov     rcx, [rbp+170h+var_1D8]; void *
0x18001dfec  lea     rax, [rbp+170h+var_1C8]
0x18001dff0  cmp     rcx, rax
0x18001dff3  jz      short loc_18001DFFD
0x18001dff5  mov     rdx, rbx; struct std::nothrow_t *
0x18001dff8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001dffd  mov     rcx, [rsp+270h+var_220]
0x18001e002  test    rcx, rcx
0x18001e005  jz      short loc_18001E013
0x18001e007  mov     rax, [rcx]
0x18001e00a  mov     rax, [rax+10h]
0x18001e00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e013  mov     rcx, [rsp+270h+var_208]
0x18001e018  test    rcx, rcx
0x18001e01b  jz      short loc_18001E029
0x18001e01d  mov     rax, [rcx]
0x18001e020  mov     rax, [rax+10h]
0x18001e024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e029  mov     rcx, [rsp+270h+var_200]
0x18001e02e  test    rcx, rcx
0x18001e031  jz      short loc_18001E03F
0x18001e033  mov     rax, [rcx]
0x18001e036  mov     rax, [rax+10h]
0x18001e03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e03f  mov     rcx, [rsp+270h+var_228]
0x18001e044  test    rcx, rcx
0x18001e047  jz      short loc_18001E055
0x18001e049  mov     rax, [rcx]
0x18001e04c  mov     rax, [rax+10h]
0x18001e050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e055  mov     rcx, [rsp+270h+var_238]
0x18001e05a  test    rcx, rcx
0x18001e05d  jz      short loc_18001E06B
0x18001e05f  mov     rax, [rcx]
0x18001e062  mov     rax, [rax+10h]
0x18001e066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e06b  mov     rcx, [rsp+270h+var_218]
0x18001e070  test    rcx, rcx
0x18001e073  jz      short loc_18001E081
0x18001e075  mov     rax, [rcx]
0x18001e078  mov     rax, [rax+10h]
0x18001e07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e081  mov     rcx, [rsp+270h+var_240]
0x18001e086  test    rcx, rcx
0x18001e089  jz      short loc_18001E097
0x18001e08b  mov     rax, [rcx]
0x18001e08e  mov     rax, [rax+10h]
0x18001e092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e097  mov     rcx, [rsp+270h+var_230]
0x18001e09c  test    rcx, rcx
0x18001e09f  jz      short loc_18001E0AD
0x18001e0a1  mov     rax, [rcx]
0x18001e0a4  mov     rax, [rax+10h]
0x18001e0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0ad  mov     rcx, [rsp+270h+var_210]
0x18001e0b2  test    rcx, rcx
0x18001e0b5  jz      short loc_18001E0C3
0x18001e0b7  mov     rax, [rcx]
0x18001e0ba  mov     rax, [rax+10h]
0x18001e0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0c3  mov     eax, 8007000Eh
0x18001e0c8  lea     r11, [rsp+270h+var_30]
0x18001e0d0  mov     rbx, [r11+48h]
0x18001e0d4  movaps  xmm6, xmmword ptr [r11-10h]
0x18001e0d9  movaps  xmm7, xmmword ptr [r11-20h]
0x18001e0de  movaps  xmm8, xmmword ptr [r11-30h]
0x18001e0e3  movaps  xmm9, xmmword ptr [r11-40h]
0x18001e0e8  movaps  xmm10, xmmword ptr [r11-50h]
0x18001e0ed  movaps  xmm11, xmmword ptr [r11-60h]
0x18001e0f2  mov     rsp, r11
0x18001e0f5  pop     r15
0x18001e0f7  pop     r14
0x18001e0f9  pop     r13
0x18001e0fb  pop     r12
0x18001e0fd  pop     rdi
0x18001e0fe  pop     rsi
0x18001e0ff  pop     rbp
0x18001e100  retn
0x18001e101  mov     r8, r12
0x18001e104  call    CoCreateTaskScheduler
0x18001e109  mov     [rbp+170h+Data], eax
0x18001e10f  lea     rcx, aCreatetask; "CreateTask"
0x18001e116  mov     [rbp+170h+var_190], rcx
0x18001e11a  lea     rcx, [rbp+170h+Data]
0x18001e121  mov     [rbp+170h+var_188], rcx
0x18001e125  test    eax, eax
0x18001e127  jns     loc_18001E282
0x18001e12d  lea     r8, ValueName; "22CoCreateTaskScheduler2"
0x18001e134  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18001e13b  lea     rax, [rbp+170h+Data]
0x18001e142  mov     r9d, 4; dwType
0x18001e148  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e14f  mov     [rsp+270h+cbData], r9d; cbData
0x18001e154  mov     [rsp+270h+lpData], rax; lpData
0x18001e159  call    cs:__imp_RegSetKeyValueW
0x18001e15f  mov     edi, [rbp+170h+Data]
0x18001e165  lea     rcx, [rbp+170h+var_190]; this
0x18001e169  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001e16e  mov     rcx, [rsp+270h+var_1F8]; void *
0x18001e173  lea     rax, [rbp+170h+var_1E8]
0x18001e177  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001e17e  cmp     rcx, rax
0x18001e181  jz      short loc_18001E18B
0x18001e183  mov     rdx, rbx; struct std::nothrow_t *
0x18001e186  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001e18b  mov     rcx, [rbp+170h+psz]; void *
0x18001e18f  lea     rax, [rbp+170h+var_1A8]
0x18001e193  cmp     rcx, rax
0x18001e196  jz      short loc_18001E1A0
0x18001e198  mov     rdx, rbx; struct std::nothrow_t *
0x18001e19b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001e1a0  mov     rcx, [rbp+170h+var_1D8]; void *
0x18001e1a4  lea     rax, [rbp+170h+var_1C8]
0x18001e1a8  cmp     rcx, rax
0x18001e1ab  jz      short loc_18001E1B5
0x18001e1ad  mov     rdx, rbx; struct std::nothrow_t *
0x18001e1b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001e1b5  mov     rcx, [rsp+270h+var_220]
0x18001e1ba  test    rcx, rcx
0x18001e1bd  jz      short loc_18001E1CB
0x18001e1bf  mov     rax, [rcx]
0x18001e1c2  mov     rax, [rax+10h]
0x18001e1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1cb  mov     rcx, [rsp+270h+var_208]
0x18001e1d0  test    rcx, rcx
0x18001e1d3  jz      short loc_18001E1E1
0x18001e1d5  mov     rax, [rcx]
0x18001e1d8  mov     rax, [rax+10h]
0x18001e1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1e1  mov     rcx, [rsp+270h+var_200]
0x18001e1e6  test    rcx, rcx
0x18001e1e9  jz      short loc_18001E1F7
0x18001e1eb  mov     rax, [rcx]
0x18001e1ee  mov     rax, [rax+10h]
0x18001e1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1f7  mov     rcx, [rsp+270h+var_228]
0x18001e1fc  test    rcx, rcx
0x18001e1ff  jz      short loc_18001E20D
0x18001e201  mov     rax, [rcx]
0x18001e204  mov     rax, [rax+10h]
0x18001e208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e20d  mov     rcx, [rsp+270h+var_238]
0x18001e212  test    rcx, rcx
  ... truncated ...
```
