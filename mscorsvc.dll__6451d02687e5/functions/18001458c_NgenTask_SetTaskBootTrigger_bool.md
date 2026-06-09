# NgenTask::SetTaskBootTrigger(bool)

- ea: `0x18001458c`
- end: `0x180015207`
- name: `?SetTaskBootTrigger@NgenTask@@YAJ_N@Z`
- size: `3195`
- prototype: `__int64 __fastcall(NgenTask *__hidden this, bool)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180016fd4`
- `0x1800171a8`
- `0x1800283d0`
- `0x1800288e0`

## callees

- `0x180013f04`
- `0x180013f88`
- `0x18001406c`
- `0x18001458c`
- `0x180030568`
- `0x180030d84`
- `0x180032654`
- `0x1800366a8`
- `0x18003dc30`
- `0x18003e8f0`
- `0x18003f280`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180014697`
- `ole32!CoCreateInstance` at `0x180014697`
- `OLEAUT32!__imp_SysAllocString` at `0x180014e16`
- `OLEAUT32!__imp_SysAllocString` at `0x180014e5a`
- `OLEAUT32!__imp_SysAllocString` at `0x180014e16`
- `OLEAUT32!__imp_SysAllocString` at `0x180014e5a`
- `OLEAUT32!__imp_VariantInit` at `0x1800146c6`
- `OLEAUT32!__imp_VariantInit` at `0x1800146ed`
- `OLEAUT32!__imp_VariantInit` at `0x180014716`
- `OLEAUT32!__imp_VariantInit` at `0x18001473d`
- `OLEAUT32!__imp_VariantInit` at `0x1800146c6`
- `OLEAUT32!__imp_VariantInit` at `0x1800146ed`
- `OLEAUT32!__imp_VariantInit` at `0x180014716`
- `OLEAUT32!__imp_VariantInit` at `0x18001473d`
- `OLEAUT32!__imp_VariantClear` at `0x1800147d2`
- `OLEAUT32!__imp_VariantClear` at `0x1800147e0`
- `OLEAUT32!__imp_VariantClear` at `0x1800147ee`
- `OLEAUT32!__imp_VariantClear` at `0x1800147fc`
- `OLEAUT32!__imp_VariantClear` at `0x180014b51`
- `OLEAUT32!__imp_VariantClear` at `0x180014da2`
- `OLEAUT32!__imp_VariantClear` at `0x18001506d`
- `OLEAUT32!__imp_VariantClear` at `0x18001507b`
- `OLEAUT32!__imp_VariantClear` at `0x1800147d2`
- `OLEAUT32!__imp_VariantClear` at `0x1800147e0`
- `OLEAUT32!__imp_VariantClear` at `0x1800147ee`
- `OLEAUT32!__imp_VariantClear` at `0x1800147fc`
- `OLEAUT32!__imp_VariantClear` at `0x180014b51`
- `OLEAUT32!__imp_VariantClear` at `0x180014da2`
- `OLEAUT32!__imp_VariantClear` at `0x18001506d`
- `OLEAUT32!__imp_VariantClear` at `0x18001507b`

## pseudocode

```c
// Hidden C++ exception states: #wind=117
__int64 __fastcall NgenTask::SetTaskBootTrigger(NgenTask *this, __int64 a2, bool a3)
{
  __int16 v3; // r15
  HRESULT v4; // eax
  int v5; // edi
  int v6; // ecx
  LPVOID v7; // rdi
  _bstr_t *v8; // rax
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rsi
  unsigned __int16 *v12; // r14
  _bstr_t *v13; // rax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rsi
  int v17; // eax
  __int64 v18; // rsi
  int v19; // eax
  __int64 v20; // rdi
  int v21; // ebx
  int v22; // eax
  __int64 v23; // rdx
  LONG v24; // esi
  int v25; // eax
  __int64 v26; // rdi
  int v27; // eax
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // rsi
  bool v29; // dl
  int v30; // eax
  unsigned int ConfigValue; // eax
  __int64 v32; // rdi
  _bstr_t *v33; // rax
  __int64 v34; // rdx
  __int128 v35; // xmm2
  IRecordInfo *v36; // xmm3_8
  __int64 v37; // rdi
  _bstr_t *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rdi
  _bstr_t *v41; // rax
  __int64 v42; // rdx
  int v43; // eax
  IRecordInfo *p_ppv; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v46; // [rsp+68h] [rbp-A0h] BYREF
  IRecordInfo *v47; // [rsp+78h] [rbp-90h]
  __int64 v48; // [rsp+88h] [rbp-80h] BYREF
  int v49; // [rsp+90h] [rbp-78h]
  bool v50; // [rsp+98h] [rbp-70h] BYREF
  int v51; // [rsp+9Ch] [rbp-6Ch] BYREF
  __int64 v52; // [rsp+A0h] [rbp-68h] BYREF
  int v53; // [rsp+A8h] [rbp-60h]
  __int64 v54; // [rsp+B0h] [rbp-58h] BYREF
  int v55; // [rsp+B8h] [rbp-50h]
  LPVOID ppv; // [rsp+C0h] [rbp-48h] BYREF
  int v57; // [rsp+C8h] [rbp-40h]
  __int64 v58; // [rsp+D0h] [rbp-38h] BYREF
  int v59; // [rsp+D8h] [rbp-30h]
  __int64 v60; // [rsp+E0h] [rbp-28h] BYREF
  int v61; // [rsp+E8h] [rbp-20h]
  __int64 v62; // [rsp+F0h] [rbp-18h] BYREF
  int v63; // [rsp+F8h] [rbp-10h]
  __int64 (__fastcall ***v64)(_QWORD, GUID *, _QWORD *); // [rsp+100h] [rbp-8h] BYREF
  int v65; // [rsp+108h] [rbp+0h]
  __int64 v66; // [rsp+110h] [rbp+8h] BYREF
  int v67; // [rsp+118h] [rbp+10h]
  IRecordInfo *pRecInfo; // [rsp+120h] [rbp+18h] BYREF
  IRecordInfo *v69; // [rsp+128h] [rbp+20h]
  VARIANTARG v70; // [rsp+138h] [rbp+30h] BYREF
  VARIANTARG v71; // [rsp+158h] [rbp+50h] BYREF
  _DWORD v72[2]; // [rsp+178h] [rbp+70h] BYREF
  int v73; // [rsp+180h] [rbp+78h]
  unsigned __int16 *v74; // [rsp+188h] [rbp+80h]
  VARIANTARG pvarg; // [rsp+198h] [rbp+90h] BYREF
  VARIANTARG v76; // [rsp+1B8h] [rbp+B0h] BYREF
  VARIANTARG v77; // [rsp+1D0h] [rbp+C8h] BYREF
  __int128 v78; // [rsp+1E8h] [rbp+E0h] BYREF
  IRecordInfo *v79; // [rsp+1F8h] [rbp+F0h]
  VARIANTARG v80; // [rsp+208h] [rbp+100h] BYREF
  int v81; // [rsp+228h] [rbp+120h] BYREF
  __int64 v82; // [rsp+22Ch] [rbp+124h]
  void *lpMem; // [rsp+238h] [rbp+130h]
  __int16 v84; // [rsp+240h] [rbp+138h] BYREF

  v3 = (unsigned __int8)this;
  ppv = 0;
  v57 = 0;
  v60 = 0;
  v61 = 0;
  v66 = 0;
  v67 = 0;
  v54 = 0;
  v55 = 0;
  v58 = 0;
  v59 = 0;
  v48 = 0;
  v49 = 0;
  v64 = 0;
  v65 = 0;
  v52 = 0;
  v53 = 0;
  v62 = 0;
  v63 = 0;
  v72[0] = 2;
  v72[1] = 2;
  v73 = 16;
  v74 = (unsigned __int16 *)&SString::s_EmptyBuffer;
  NgenTask::GetTaskName((NgenTask *)v72, 0, a3);
  p_ppv = (IRecordInfo *)&ppv;
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  v5 = v4;
  v6 = v57;
  if ( ppv )
    v6 = 1;
  v57 = v6;
  if ( v4 < 0 )
    goto LABEL_112;
  VariantInit(&pvarg);
  v46 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v80);
  v78 = *(_OWORD *)&v80.vt;
  v69 = v80.pRecInfo;
  VariantInit(&v76);
  *(_OWORD *)&v70.vt = *(_OWORD *)&v76.vt;
  p_ppv = v76.pRecInfo;
  VariantInit(&v77);
  v47 = pRecInfo;
  v79 = v69;
  v70.pRecInfo = p_ppv;
  v71 = v77;
  v5 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL))(
         ppv,
         &v71,
         &v70,
         &v78,
         &v46);
  VariantClear(&v77);
  VariantClear(&v76);
  VariantClear(&v80);
  VariantClear(&pvarg);
  if ( v5 < 0 )
    goto LABEL_112;
  v7 = ppv;
  v69 = (IRecordInfo *)&v60;
  if ( v61 )
  {
    if ( v60 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    v61 = 0;
  }
  v60 = 0;
  v8 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, L"\\Microsoft\\Windows\\.NET Framework");
  if ( *(_QWORD *)v8 )
    v9 = **(_QWORD **)v8;
  else
    v9 = 0;
  v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v7 + 56LL))(v7, v9, &v60);
  _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
  v10 = v61;
  v11 = v60;
  if ( v60 )
    v10 = 1;
  v61 = v10;
  if ( v5 < 0 )
  {
LABEL_112:
    v12 = v74;
    goto LABEL_113;
  }
  v69 = (IRecordInfo *)&v66;
  if ( v67 )
  {
    if ( v66 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    v67 = 0;
  }
  v66 = 0;
  SString::ConvertToUnicode((SString *)v72);
  v12 = v74;
  v13 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, v74);
  if ( *(_QWORD *)v13 )
    v14 = **(_QWORD **)v13;
  else
    v14 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v11 + 104LL))(v11, v14, &v66);
  _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
  v15 = v67;
  v16 = v66;
  if ( v66 )
    v15 = 1;
  v67 = v15;
  if ( v5 >= 0 )
  {
    p_ppv = (IRecordInfo *)&v54;
    if ( v55 )
    {
      if ( v54 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v55 = 0;
    }
    v54 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 152LL))(v16, &v54);
    v17 = v55;
    v18 = v54;
    if ( v54 )
      v17 = 1;
    v55 = v17;
    if ( v5 >= 0 )
    {
      p_ppv = (IRecordInfo *)&v58;
      if ( v59 )
      {
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        v59 = 0;
      }
      v58 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 88LL))(v18, &v58);
      v19 = v59;
      if ( v58 )
        v19 = 1;
      v59 = v19;
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v58 + 144LL))(v58, (unsigned __int16)(v3 - 1));
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v58 + 128LL))(v58, (unsigned __int16)(v3 - 1));
          if ( v5 >= 0 )
          {
            v20 = v54;
            p_ppv = (IRecordInfo *)&v48;
            if ( v49 )
            {
              if ( v48 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
              v49 = 0;
            }
            v48 = 0;
            v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 72LL))(v20, &v48);
            v21 = 0;
            v22 = v49;
            if ( v48 )
              v22 = 1;
            v49 = v22;
            if ( v5 >= 0 )
            {
              v51 = 0;
              v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 56LL))(v48, &v51);
              if ( v5 >= 0 )
              {
                v24 = 1;
                if ( v51 < 1 )
                {
LABEL_60:
                  if ( (_BYTE)v3 )
                  {
                    v26 = v48;
                    p_ppv = (IRecordInfo *)&v64;
                    if ( v65 )
                    {
                      if ( v64 )
                        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64))(*v64)[2])(
                          v64,
                          v23);
                      v65 = 0;
                    }
                    v64 = 0;
                    v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v26 + 80LL))(v26, 8, &v64);
                    v27 = v65;
                    v28 = v64;
                    if ( v64 )
                      v27 = 1;
                    v65 = v27;
                    if ( v5 < 0 )
                      goto LABEL_113;
                    p_ppv = (IRecordInfo *)&v52;
                    if ( v53 )
                    {
                      if ( v52 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                      v53 = 0;
                    }
                    v52 = 0;
                    v5 = (**v28)(v28, &IID_IBootTrigger, &v52);
                    v30 = v53;
                    if ( v52 )
                      v30 = 1;
                    v53 = v30;
                    if ( v5 < 0 )
                      goto LABEL_113;
                    v82 = 512;
                    lpMem = &v84;
                    v81 = 2;
                    v84 = 0;
                    ConfigValue = CLRConfig::GetConfigValue(
                                    (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::INTERNAL_NGenTaskDelayStartAmount,
                                    v29,
                                    &v50);
                    SString::Printf((SString *)&v81, L"PT%uS", ConfigValue);
                    v32 = v52;
                    SString::ConvertToUnicode((SString *)&v81);
                    v33 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, (const unsigned __int16 *)lpMem);
                    if ( *(_QWORD *)v33 )
                      v34 = **(_QWORD **)v33;
                    else
                      v34 = 0;
                    v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 168LL))(v32, v34);
                    _bstr_t::~_bstr_t((_bstr_t *)&p_ppv);
                    if ( v5 < 0
                      || ((v40 = v52, v41 = _bstr_t::_bstr_t((_bstr_t *)&p_ppv, L"BootTrigger1"), !*(_QWORD *)v41)
                        ? (v42 = 0)
                        : (v42 = **(_QWORD **)v41),
                          v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 72LL))(v40, v42),
                          _bstr_t::~_bstr_t((_bstr_t *)&p_ppv),
                          v5 < 0) )
                    {
                      if ( (v82 & 0x800000000LL) != 0 )
                        operator delete(lpMem);
                      goto LABEL_113;
                    }
                    if ( (v82 & 0x800000000LL) != 0 )
                      operator delete(lpMem);
                  }
                }
                else
                {
                  while ( 1 )
                  {
                    DWORD2(v46) = 0;
                    p_ppv = (IRecordInfo *)&v46;
                    *(_QWORD *)&v46 = 0;
                    pvarg.vt = 3;
                    pvarg.lVal = v24;
                    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v48 + 64LL))(
                           v48,
                           (unsigned int)v24,
                           &v46);
                    VariantClear(&pvarg);
                    v21 &= ~0x40u;
                    v25 = DWORD2(v46);
                    if ( (_QWORD)v46 )
                      v25 = 1;
                    DWORD2(v46) = v25;
                    if ( v5 < 0 )
                      goto LABEL_79;
                    v5 = (*(__int64 (__fastcall **)(_QWORD, IRecordInfo **))(*(_QWORD *)v46 + 56LL))(v46, &pRecInfo);
                    if ( v5 < 0 )
                      goto LABEL_79;
                    if ( (_DWORD)pRecInfo == 8 )
                      break;
                    if ( DWORD2(v46) )
                    {
                      if ( (_QWORD)v46 )
                        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v46 + 16LL))(v46);
                      DWORD2(v46) = 0;
                    }
                    ++v24;
                    v23 = 3;
                    if ( v24 > v51 )
                      goto LABEL_60;
                  }
                  if ( (_BYTE)v3
                    || (v70.vt = 3,
                        v70.lVal = v24,
                        v71 = v70,
                        v5 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v48 + 88LL))(v48, &v71),
                        VariantClear(&v70),
                        v5 < 0) )
                  {
LABEL_79:
                    if ( DWORD2(v46) )
                    {
                      if ( (_QWORD)v46 )
                        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v46 + 16LL))(v46);
                      DWORD2(v46) = 0;
                    }
                    goto LABEL_113;
                  }
                  if ( DWORD2(v46) )
                  {
                    if ( (_QWORD)v46 )
                      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v46 + 16LL))(v46);
                    DWORD2(v46) = 0;
                  }
                }
                v71.vt = 0;
                v77.vt = 8;
                v77.llVal = (LONGLONG)SysAllocString(&psz);
                if ( v77.llVal )
                {
                  v78 = *(_OWORD *)&v77.vt;
                  v69 = v77.pRecInfo;
                  v76.vt = 8;
                  v76.llVal = (LONGLONG)SysAllocString(L"SYSTEM");
                  if ( v76.llVal )
                  {
                    v35 = *(_OWORD *)&v76.vt;
                    *(_OWORD *)&v70.vt = *(_OWORD *)&v76.vt;
                    v36 = v76.pRecInfo;
                    p_ppv = v76.pRecInfo;
                    v37 = v60;
                    *(_QWORD *)&v46 = &v62;
                    if ( v63 )
                    {
                      if ( v62 )
                      {
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
                        v35 = *(_OWORD *)&v70.vt;
                        v36 = p_ppv;
                      }
                      v63 = 0;
                    }
                    v62 = 0;
                    *(_OWORD *)&pvarg.vt = v78;
                    pvarg.pRecInfo = v69;
                    v80 = v71;
                    *(_OWORD *)&v71.vt = v35;
                    v71.pRecInfo = v36;
                    SString::ConvertToUnicode((SString *)v72);
                    v12 = v74;
                    v38 = _bstr_t::_bstr_t((_bstr_t *)&pRecInfo, v74);
                    if ( *(_QWORD *)v38 )
                      v39 = **(_QWORD **)v38;
                    else
                      v39 = 0;
                    v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, VARIANTARG *, VARIANTARG *, int, VARIANTARG *, __int64 *))(*(_QWORD *)v37 + 136LL))(
                           v37,
                           v39,
                           v54,
                           6,
                           &v71,
                           &v80,
                           5,
                           &pvarg,
                           &v62);
                    _bstr_t::~_bstr_t((_bstr_t *)&pRecInfo);
                    v43 = v63;
                    if ( v62 )
                      v43 = 1;
                    v63 = v43;
                    VariantClear(&v76);
                    VariantClear(&v77);
                    goto LABEL_113;
                  }
                  _com_issue_error(2147942414LL);
                }
                _com_issue_error(2147942414LL);
                JUMPOUT(0x180015206LL);
              }
            }
          }
        }
      }
    }
  }
LABEL_113:
  if ( (v73 & 8) != 0 )
    operator delete(v12);
  if ( v63 )
  {
    if ( v62 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    v63 = 0;
  }
  if ( v53 )
  {
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    v53 = 0;
  }
  if ( v65 )
  {
    if ( v64 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v64)[2])(v64);
    v65 = 0;
  }
  if ( v49 )
  {
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    v49 = 0;
  }
  if ( v59 )
  {
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v59 = 0;
  }
  if ( v55 )
  {
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v55 = 0;
  }
  if ( v67 )
  {
    if ( v66 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    v67 = 0;
  }
  if ( v61 )
  {
    if ( v60 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    v61 = 0;
  }
  if ( v57 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v57 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001458c  mov     rax, rsp
0x18001458f  mov     [rax+10h], rbx
0x180014593  mov     [rax+18h], rsi
0x180014597  mov     [rax+20h], rdi
0x18001459b  push    rbp
0x18001459c  push    r12
0x18001459e  push    r13
0x1800145a0  push    r14
0x1800145a2  push    r15
0x1800145a4  lea     rbp, [rax-378h]
0x1800145ab  sub     rsp, 450h
0x1800145b2  mov     rax, cs:__security_cookie
0x1800145b9  xor     rax, rsp
0x1800145bc  mov     [rbp+370h+var_30], rax
0x1800145c3  movzx   r15d, cl
0x1800145c7  xor     r12d, r12d
0x1800145ca  mov     dword ptr [rsp+470h+var_420], r12d
0x1800145cf  mov     [rbp+370h+var_3B8], r12
0x1800145d3  mov     [rbp+370h+var_3B0], r12d
0x1800145d7  mov     [rbp+370h+var_398], r12
0x1800145db  mov     [rbp+370h+var_390], r12d
0x1800145df  mov     [rbp+370h+var_368], r12
0x1800145e3  mov     [rbp+370h+var_360], r12d
0x1800145e7  mov     [rbp+370h+var_3C8], r12
0x1800145eb  mov     [rbp+370h+var_3C0], r12d
0x1800145ef  mov     [rbp+370h+var_3A8], r12
0x1800145f3  mov     [rbp+370h+var_3A0], r12d
0x1800145f7  mov     [rbp+370h+var_3F0], r12
0x1800145fb  mov     [rbp+370h+var_3E8], r12d
0x1800145ff  mov     [rbp+370h+var_378], r12
0x180014603  mov     [rbp+370h+var_370], r12d
0x180014607  mov     [rbp+370h+var_3D8], r12
0x18001460b  mov     [rbp+370h+var_3D0], r12d
0x18001460f  mov     [rbp+370h+var_388], r12
0x180014613  mov     [rbp+370h+var_380], r12d
0x180014617  lea     esi, [r12+2]
0x18001461c  mov     [rbp+370h+var_300], esi
0x18001461f  mov     [rbp+370h+var_2FC], esi
0x180014622  mov     [rbp+370h+var_2F8], 10h
0x180014629  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180014630  mov     [rbp+370h+var_2F0], rax
0x180014637  xor     edx, edx; struct SString *
0x180014639  lea     rcx, [rbp+370h+var_300]; this
0x18001463d  call    ?GetTaskName@NgenTask@@YAXAEAVSString@@_N@Z; NgenTask::GetTaskName(SString &,bool)
0x180014642  nop
0x180014643  lea     rax, [rbp+370h+var_3B8]
0x180014647  mov     qword ptr [rsp+470h+var_418], rax
0x18001464c  cmp     [rbp+370h+var_3B0], r12d
0x180014650  jz      short loc_18001466C
0x180014652  mov     rcx, [rbp+370h+var_3B8]
0x180014656  test    rcx, rcx
0x180014659  jz      short loc_180014668
0x18001465b  mov     rax, [rcx]
0x18001465e  mov     rax, [rax+10h]
0x180014662  call    cs:__guard_dispatch_icall_fptr
0x180014668  mov     [rbp+370h+var_3B0], r12d
0x18001466c  mov     [rbp+370h+var_3B8], r12
0x180014670  mov     r13d, 1
0x180014676  mov     dword ptr [rsp+470h+var_420], r13d
0x18001467b  lea     rax, [rbp+370h+var_3B8]
0x18001467f  mov     [rsp+470h+ppv], rax; ppv
0x180014684  lea     r9, IID_ITaskService; riid
0x18001468b  mov     r8d, r13d; dwClsContext
0x18001468e  xor     edx, edx; pUnkOuter
0x180014690  lea     rcx, CLSID_TaskScheduler; rclsid
0x180014697  call    cs:__imp_CoCreateInstance
0x18001469d  mov     edi, eax
0x18001469f  mov     ebx, r13d
0x1800146a2  and     ebx, 0FFFFFFFEh
0x1800146a5  mov     dword ptr [rsp+470h+var_420], ebx
0x1800146a9  mov     ecx, [rbp+370h+var_3B0]
0x1800146ac  cmp     [rbp+370h+var_3B8], r12
0x1800146b0  cmovnz  ecx, r13d
0x1800146b4  mov     [rbp+370h+var_3B0], ecx
0x1800146b7  test    eax, eax
0x1800146b9  js      loc_180015083
0x1800146bf  lea     rcx, [rbp+370h+pvarg]; pvarg
0x1800146c6  call    cs:__imp_VariantInit
0x1800146cc  nop
0x1800146cd  movups  xmm0, xmmword ptr [rbp+370h+pvarg]
0x1800146d4  movups  [rsp+470h+var_418+8], xmm0
0x1800146d9  movsd   xmm0, qword ptr [rbp+370h+pvarg+10h]
0x1800146e1  movsd   [rbp+370h+var_358], xmm0
0x1800146e6  lea     rcx, [rbp+370h+var_270]; pvarg
0x1800146ed  call    cs:__imp_VariantInit
0x1800146f3  nop
0x1800146f4  movups  xmm0, xmmword ptr [rbp+370h+var_270]
0x1800146fb  movups  [rbp+370h+var_290], xmm0
0x180014702  movsd   xmm0, qword ptr [rbp+370h+var_270+10h]
0x18001470a  movsd   [rbp+370h+var_350], xmm0
0x18001470f  lea     rcx, [rbp+370h+var_2C0]; pvarg
0x180014716  call    cs:__imp_VariantInit
0x18001471c  nop
0x18001471d  movups  xmm0, xmmword ptr [rbp+370h+var_2C0]
0x180014724  movups  xmmword ptr [rbp+370h+var_340], xmm0
0x180014728  movsd   xmm0, qword ptr [rbp+370h+var_2C0+10h]
0x180014730  movsd   qword ptr [rsp+470h+var_418], xmm0
0x180014736  lea     rcx, [rbp+370h+var_2A8]; pvarg
0x18001473d  call    cs:__imp_VariantInit
0x180014743  nop
0x180014744  movups  xmm0, [rsp+470h+var_418+8]
0x180014749  movaps  [rsp+470h+var_418+8], xmm0
0x18001474e  movsd   xmm0, [rbp+370h+var_358]
0x180014753  movsd   [rsp+470h+var_400], xmm0
0x180014759  movups  xmm0, [rbp+370h+var_290]
0x180014760  movaps  [rbp+370h+var_290], xmm0
0x180014767  movsd   xmm0, [rbp+370h+var_350]
0x18001476c  movsd   [rbp+370h+var_280], xmm0
0x180014774  movups  xmm0, xmmword ptr [rbp+370h+var_340]
0x180014778  movaps  xmmword ptr [rbp+370h+var_340], xmm0
0x18001477c  movsd   xmm0, qword ptr [rsp+470h+var_418]
0x180014782  movsd   qword ptr [rbp+370h+var_340+10h], xmm0
0x180014787  movups  xmm0, xmmword ptr [rbp+370h+var_2A8]
0x18001478e  movaps  [rbp+370h+var_320], xmm0
0x180014792  movsd   xmm1, qword ptr [rbp+370h+var_2A8+10h]
0x18001479a  movsd   [rbp+370h+var_310], xmm1
0x18001479f  mov     rcx, [rbp+370h+var_3B8]
0x1800147a3  mov     rax, [rcx]
0x1800147a6  lea     rdx, [rsp+470h+var_418+8]
0x1800147ab  mov     [rsp+470h+ppv], rdx
0x1800147b0  lea     r9, [rbp+370h+var_290]
0x1800147b7  lea     r8, [rbp+370h+var_340]
0x1800147bb  lea     rdx, [rbp+370h+var_320]
0x1800147bf  mov     rax, [rax+50h]
0x1800147c3  call    cs:__guard_dispatch_icall_fptr
0x1800147c9  mov     edi, eax
0x1800147cb  lea     rcx, [rbp+370h+var_2A8]; pvarg
0x1800147d2  call    cs:__imp_VariantClear
0x1800147d8  nop
0x1800147d9  lea     rcx, [rbp+370h+var_2C0]; pvarg
0x1800147e0  call    cs:__imp_VariantClear
0x1800147e6  nop
0x1800147e7  lea     rcx, [rbp+370h+var_270]; pvarg
0x1800147ee  call    cs:__imp_VariantClear
0x1800147f4  nop
0x1800147f5  lea     rcx, [rbp+370h+pvarg]; pvarg
0x1800147fc  call    cs:__imp_VariantClear
0x180014802  test    edi, edi
0x180014804  js      loc_180015083
0x18001480a  mov     rdi, [rbp+370h+var_3B8]
0x18001480e  lea     rax, [rbp+370h+var_398]
0x180014812  mov     [rbp+370h+var_350], rax
0x180014816  cmp     [rbp+370h+var_390], r12d
0x18001481a  jz      short loc_180014836
0x18001481c  mov     rcx, [rbp+370h+var_398]
0x180014820  test    rcx, rcx
0x180014823  jz      short loc_180014832
0x180014825  mov     rax, [rcx]
0x180014828  mov     rax, [rax+10h]
0x18001482c  call    cs:__guard_dispatch_icall_fptr
0x180014832  mov     [rbp+370h+var_390], r12d
0x180014836  mov     [rbp+370h+var_398], r12
0x18001483a  or      ebx, esi
0x18001483c  mov     dword ptr [rsp+470h+var_420], ebx
0x180014840  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\.NET Framework"
0x180014847  lea     rcx, [rsp+470h+var_418]; this
0x18001484c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180014851  nop
0x180014852  mov     rcx, [rax]
0x180014855  test    rcx, rcx
0x180014858  jz      short loc_18001485F
0x18001485a  mov     rdx, [rcx]
0x18001485d  jmp     short loc_180014862
0x18001485f  mov     rdx, r12
0x180014862  mov     rax, [rdi]
0x180014865  lea     r8, [rbp+370h+var_398]
0x180014869  mov     rcx, rdi
0x18001486c  mov     rax, [rax+38h]
0x180014870  call    cs:__guard_dispatch_icall_fptr
0x180014876  mov     edi, eax
0x180014878  lea     rcx, [rsp+470h+var_418]; this
0x18001487d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180014882  and     ebx, 0FFFFFFFDh
0x180014885  mov     dword ptr [rsp+470h+var_420], ebx
0x180014889  mov     eax, [rbp+370h+var_390]
0x18001488c  mov     rsi, [rbp+370h+var_398]
0x180014890  test    rsi, rsi
0x180014893  cmovnz  eax, r13d
0x180014897  mov     [rbp+370h+var_390], eax
0x18001489a  test    edi, edi
0x18001489c  js      loc_180015083
0x1800148a2  lea     rax, [rbp+370h+var_368]
0x1800148a6  mov     [rbp+370h+var_350], rax
0x1800148aa  cmp     [rbp+370h+var_360], r12d
0x1800148ae  jz      short loc_1800148CA
0x1800148b0  mov     rcx, [rbp+370h+var_368]
0x1800148b4  test    rcx, rcx
0x1800148b7  jz      short loc_1800148C6
0x1800148b9  mov     rax, [rcx]
0x1800148bc  mov     rax, [rax+10h]
0x1800148c0  call    cs:__guard_dispatch_icall_fptr
0x1800148c6  mov     [rbp+370h+var_360], r12d
0x1800148ca  mov     [rbp+370h+var_368], r12
0x1800148ce  or      ebx, 4
0x1800148d1  mov     dword ptr [rsp+470h+var_420], ebx
0x1800148d5  lea     rcx, [rbp+370h+var_300]; this
0x1800148d9  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800148de  mov     r14, [rbp+370h+var_2F0]
0x1800148e5  mov     rdx, r14; unsigned __int16 *
0x1800148e8  lea     rcx, [rsp+470h+var_418]; this
0x1800148ed  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800148f2  nop
0x1800148f3  mov     rcx, [rax]
0x1800148f6  test    rcx, rcx
0x1800148f9  jz      short loc_180014900
0x1800148fb  mov     rdx, [rcx]
0x1800148fe  jmp     short loc_180014903
0x180014900  mov     rdx, r12
0x180014903  mov     rax, [rsi]
0x180014906  lea     r8, [rbp+370h+var_368]
0x18001490a  mov     rcx, rsi
0x18001490d  mov     rax, [rax+68h]
0x180014911  call    cs:__guard_dispatch_icall_fptr
0x180014917  mov     edi, eax
0x180014919  lea     rcx, [rsp+470h+var_418]; this
0x18001491e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180014923  and     ebx, 0FFFFFFFBh
0x180014926  mov     dword ptr [rsp+470h+var_420], ebx
0x18001492a  mov     eax, [rbp+370h+var_360]
0x18001492d  mov     rsi, [rbp+370h+var_368]
0x180014931  test    rsi, rsi
0x180014934  cmovnz  eax, r13d
0x180014938  mov     [rbp+370h+var_360], eax
0x18001493b  test    edi, edi
0x18001493d  js      loc_18001508A
0x180014943  lea     rax, [rbp+370h+var_3C8]
0x180014947  mov     qword ptr [rsp+470h+var_418], rax
0x18001494c  cmp     [rbp+370h+var_3C0], r12d
0x180014950  jz      short loc_18001496C
0x180014952  mov     rcx, [rbp+370h+var_3C8]
0x180014956  test    rcx, rcx
0x180014959  jz      short loc_180014968
0x18001495b  mov     rax, [rcx]
0x18001495e  mov     rax, [rax+10h]
0x180014962  call    cs:__guard_dispatch_icall_fptr
0x180014968  mov     [rbp+370h+var_3C0], r12d
0x18001496c  mov     [rbp+370h+var_3C8], r12
0x180014970  or      ebx, 8
0x180014973  mov     dword ptr [rsp+470h+var_420], ebx
0x180014977  mov     rax, [rsi]
0x18001497a  lea     rdx, [rbp+370h+var_3C8]
0x18001497e  mov     rcx, rsi
0x180014981  mov     rax, [rax+98h]
0x180014988  call    cs:__guard_dispatch_icall_fptr
0x18001498e  mov     edi, eax
0x180014990  and     ebx, 0FFFFFFF7h
0x180014993  mov     dword ptr [rsp+470h+var_420], ebx
0x180014997  mov     eax, [rbp+370h+var_3C0]
0x18001499a  mov     rsi, [rbp+370h+var_3C8]
0x18001499e  test    rsi, rsi
0x1800149a1  cmovnz  eax, r13d
0x1800149a5  mov     [rbp+370h+var_3C0], eax
0x1800149a8  test    edi, edi
0x1800149aa  js      loc_18001508A
0x1800149b0  lea     rax, [rbp+370h+var_3A8]
0x1800149b4  mov     qword ptr [rsp+470h+var_418], rax
0x1800149b9  cmp     [rbp+370h+var_3A0], r12d
0x1800149bd  jz      short loc_1800149D9
0x1800149bf  mov     rcx, [rbp+370h+var_3A8]
0x1800149c3  test    rcx, rcx
0x1800149c6  jz      short loc_1800149D5
0x1800149c8  mov     rax, [rcx]
0x1800149cb  mov     rax, [rax+10h]
0x1800149cf  call    cs:__guard_dispatch_icall_fptr
0x1800149d5  mov     [rbp+370h+var_3A0], r12d
0x1800149d9  mov     [rbp+370h+var_3A8], r12
0x1800149dd  or      ebx, 10h
0x1800149e0  mov     dword ptr [rsp+470h+var_420], ebx
0x1800149e4  mov     rax, [rsi]
0x1800149e7  lea     rdx, [rbp+370h+var_3A8]
0x1800149eb  mov     rcx, rsi
0x1800149ee  mov     rax, [rax+58h]
0x1800149f2  call    cs:__guard_dispatch_icall_fptr
0x1800149f8  mov     edi, eax
0x1800149fa  and     ebx, 0FFFFFFEFh
0x1800149fd  mov     dword ptr [rsp+470h+var_420], ebx
0x180014a01  mov     eax, [rbp+370h+var_3A0]
0x180014a04  mov     rcx, [rbp+370h+var_3A8]
0x180014a08  test    rcx, rcx
0x180014a0b  cmovnz  eax, r13d
0x180014a0f  mov     [rbp+370h+var_3A0], eax
0x180014a12  test    edi, edi
0x180014a14  js      loc_18001508A
0x180014a1a  movzx   esi, r15w
0x180014a1e  sub     si, r13w
0x180014a22  mov     rax, [rcx]
0x180014a25  movzx   edx, si
0x180014a28  mov     rax, [rax+90h]
0x180014a2f  call    cs:__guard_dispatch_icall_fptr
0x180014a35  mov     edi, eax
0x180014a37  test    eax, eax
0x180014a39  js      loc_18001508A
0x180014a3f  mov     rcx, [rbp+370h+var_3A8]
0x180014a43  mov     rax, [rcx]
0x180014a46  movzx   edx, si
0x180014a49  mov     rax, [rax+80h]
0x180014a50  call    cs:__guard_dispatch_icall_fptr
0x180014a56  mov     edi, eax
0x180014a58  test    eax, eax
0x180014a5a  js      loc_18001508A
  ... truncated ...
```
