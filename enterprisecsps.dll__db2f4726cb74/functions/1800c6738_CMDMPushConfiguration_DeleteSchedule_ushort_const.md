# CMDMPushConfiguration::DeleteSchedule(ushort const *)

- ea: `0x1800c6738`
- end: `0x1800c6fab`
- name: `?DeleteSchedule@CMDMPushConfiguration@@AEAAJPEBG@Z`
- size: `2163`
- prototype: `int(CMDMPushConfiguration *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180026990`
- `0x1800c66b0`
- `0x1800c66f4`

## callees

- `0x180008de0`
- `0x1800091b0`
- `0x18000caf4`
- `0x18000d4d4`
- `0x18001a714`
- `0x180025c8c`
- `0x18002a280`
- `0x1800637f4`
- `0x1800639d0`
- `0x1800c1838`
- `0x1800c1d68`
- `0x1800c6738`
- `0x1800caad4`
- `0x1800cb1a8`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800c6ae8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6b86`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6c17`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6cbe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6dbb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6ae8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6b86`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6c17`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6cbe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6dbb`
- `OLEAUT32!__imp_VariantInit` at `0x1800c68ea`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6912`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6937`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6957`
- `OLEAUT32!__imp_VariantInit` at `0x1800c68ea`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6912`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6937`
- `OLEAUT32!__imp_VariantInit` at `0x1800c6957`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c68b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6a4b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6d3f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6e51`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6ec6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6f1f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6f46`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c68b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6a4b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6d3f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6e51`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6ec6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6f1f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c6f46`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c6801`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c6801`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c6876`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c6876`

## string_xrefs

- `0x1800c6785`: `DeleteScheduleActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CMDMPushConfiguration::DeleteSchedule(const unsigned __int16 **this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rbx
  HRESULT v8; // eax
  __int64 result; // rax
  HRESULT v10; // eax
  unsigned int v11; // ebx
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v14; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v16; // xmm8
  IRecordInfo *v17; // xmm9_8
  __int128 v18; // xmm6
  IRecordInfo *v19; // xmm7_8
  int v20; // ebx
  const char *v21; // r9
  LPVOID v22; // rbx
  __int64 v23; // rdi
  __int64 *v24; // rax
  __int64 v25; // rdx
  int v26; // r14d
  BSTR *v27; // rbx
  BSTR v28; // rcx
  _QWORD *v29; // rbx
  __int64 v30; // r14
  __int64 *v31; // rax
  __int64 v32; // rdx
  BSTR *v33; // rbx
  BSTR v34; // rcx
  _QWORD *v35; // rbx
  __int64 v36; // r14
  _QWORD *v37; // rax
  __int64 v38; // rdx
  BSTR *v39; // rbx
  BSTR v40; // rcx
  LPVOID v41; // rbx
  __int64 v42; // r14
  __int64 *v43; // rax
  __int64 v44; // rdx
  int v45; // r14d
  BSTR *v46; // rbx
  BSTR v47; // rcx
  _QWORD *v48; // rbx
  __int64 v49; // r14
  __int64 *v50; // rax
  __int64 v51; // rdx
  unsigned int v52; // r14d
  BSTR *v53; // rbx
  BSTR v54; // rcx
  int ppv; // [rsp+20h] [rbp-308h]
  int ppva; // [rsp+20h] [rbp-308h]
  char v57; // [rsp+31h] [rbp-2F7h]
  unsigned int v58; // [rsp+34h] [rbp-2F4h]
  LPVOID v59; // [rsp+38h] [rbp-2F0h] BYREF
  _QWORD *v60; // [rsp+40h] [rbp-2E8h] BYREF
  void *Block; // [rsp+48h] [rbp-2E0h] BYREF
  _QWORD *v62; // [rsp+50h] [rbp-2D8h] BYREF
  __int64 v63; // [rsp+58h] [rbp-2D0h] BYREF
  VARIANTARG v64; // [rsp+60h] [rbp-2C8h] BYREF
  VARIANTARG v65; // [rsp+78h] [rbp-2B0h] BYREF
  VARIANTARG v66; // [rsp+90h] [rbp-298h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-280h] BYREF
  int v68[4]; // [rsp+C0h] [rbp-268h] BYREF
  IRecordInfo *v69; // [rsp+D0h] [rbp-258h]
  __int128 v70; // [rsp+E0h] [rbp-248h] BYREF
  IRecordInfo *v71; // [rsp+F0h] [rbp-238h]
  __int128 v72; // [rsp+100h] [rbp-228h] BYREF
  IRecordInfo *v73; // [rsp+110h] [rbp-218h]
  VARIANTARG v74; // [rsp+120h] [rbp-208h] BYREF
  _QWORD v75[34]; // [rsp+140h] [rbp-1E8h] BYREF
  __int64 v76; // [rsp+250h] [rbp-D8h]
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v75);
  v75[0] = &MDMPushProvider::DeleteScheduleActivity::`vftable';
  MDMPushProvider::DeleteScheduleActivity::StartActivity((MDMPushProvider::DeleteScheduleActivity *)v75);
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 2147942487LL;
    v6 = 1553;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)v5,
      ppv);
    MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity((MDMPushProvider::DeleteScheduleActivity *)v75);
    return v4;
  }
  wil::ActivityBase<NodeCacheProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(v75, &v63);
  v7 = v76;
  wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)(v76 + 40));
  *(_QWORD *)(v7 + 56) = a2;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v63);
  v8 = CoInitializeEx(0, 0);
  v4 = v8;
  if ( v8 < 0 )
  {
    v5 = (unsigned int)v8;
    v6 = 1556;
    goto LABEL_5;
  }
  v57 = 1;
  v59 = 0;
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v59);
  v10 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v59);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)(unsigned int)v10,
      ppva);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v59);
    CoUninitialize();
    MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity((MDMPushProvider::DeleteScheduleActivity *)v75);
    return v11;
  }
  v12 = v59;
  v13 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v59 + 80LL);
  VariantInit(&pvarg);
  v14 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v66);
  v16 = *(_OWORD *)&v66.vt;
  v17 = v66.pRecInfo;
  VariantInit(&v65);
  v18 = *(_OWORD *)&v65.vt;
  v19 = v65.pRecInfo;
  VariantInit(&v64);
  try
  {
    *(_OWORD *)v68 = v14;
    v69 = pRecInfo;
    v70 = v16;
    v71 = v17;
    v72 = v18;
    v73 = v19;
    v74 = v64;
    v20 = v13(v12, &v74, &v72, &v70);
    _variant_t::~_variant_t((_variant_t *)&v64);
    _variant_t::~_variant_t((_variant_t *)&v65);
    _variant_t::~_variant_t((_variant_t *)&v66);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x620,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)v20,
        (int)v68);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v59);
      v57 = 0;
      CoUninitialize();
      MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity((MDMPushProvider::DeleteScheduleActivity *)v75);
      return (unsigned int)v20;
    }
    v62 = 0;
    v60 = 0;
    v63 = 0;
    v22 = v59;
    v23 = *(_QWORD *)v59;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
    v24 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&Block, L"\\Microsoft\\Windows\\EnterpriseMgmt");
    if ( v24 )
      v25 = *v24;
    else
      v25 = 0;
    v26 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v23 + 56))(v22, v25, &v62);
    v27 = (BSTR *)Block;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v27 )
    {
      if ( *v27 )
      {
        SysFreeString(*v27);
        *v27 = 0;
      }
      v28 = v27[1];
      if ( v28 )
      {
        operator delete(v28);
        v27[1] = 0;
      }
      operator delete(v27);
    }
    if ( v26 >= 0 )
    {
      v29 = v62;
      v30 = *v62;
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v60);
      v31 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&Block, this[1]);
      if ( v31 )
        v32 = *v31;
      else
        v32 = 0;
      v26 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD **))(v30 + 72))(v29, v32, &v60);
      v33 = (BSTR *)Block;
      if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v33 )
      {
        if ( *v33 )
        {
          SysFreeString(*v33);
          *v33 = 0;
        }
        v34 = v33[1];
        if ( v34 )
        {
          operator delete(v34);
          v33[1] = 0;
        }
        operator delete(v33);
      }
      if ( v26 >= 0 )
      {
        v35 = v60;
        v36 = *v60;
        v37 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&Block, a2);
        v38 = v37 ? *v37 : 0LL;
        v26 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD))(v36 + 120))(v35, v38, 0);
        v39 = (BSTR *)Block;
        if ( Block )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v39 )
          {
            if ( *v39 )
            {
              SysFreeString(*v39);
              *v39 = 0;
            }
            v40 = v39[1];
            if ( v40 )
            {
              operator delete(v40);
              v39[1] = 0;
            }
            operator delete(v39);
          }
        }
      }
    }
    if ( v26 == -2147024894 )
    {
      v41 = v59;
      v42 = *(_QWORD *)v59;
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v60);
      v43 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&Block, L"Microsoft\\Windows\\Dmclient");
      if ( v43 )
        v44 = *v43;
      else
        v44 = 0;
      v45 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD **))(v42 + 56))(v41, v44, &v60);
      v46 = (BSTR *)Block;
      if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v46 )
      {
        if ( *v46 )
        {
          SysFreeString(*v46);
          *v46 = 0;
        }
        v47 = v46[1];
        if ( v47 )
        {
          operator delete(v47);
          v46[1] = 0;
        }
        operator delete(v46);
      }
      if ( v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x635,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
          (const char *)(unsigned int)v45,
          (int)v68);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v63);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v60);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v59);
        v57 = 0;
        CoUninitialize();
        MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity((MDMPushProvider::DeleteScheduleActivity *)v75);
        return (unsigned int)v45;
      }
      v48 = v60;
      v49 = *v60;
      v50 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)&Block, a2);
      if ( v50 )
        v51 = *v50;
      else
        v51 = 0;
      v52 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD))(v49 + 120))(v48, v51, 0);
      v53 = (BSTR *)Block;
      if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v53 )
      {
        if ( *v53 )
        {
          SysFreeString(*v53);
          *v53 = 0;
        }
        v54 = v53[1];
        if ( v54 )
        {
          operator delete(v54);
          v53[1] = 0;
        }
        operator delete(v53);
      }
      if ( (int)(v52 + 0x80000000) >= 0 && v52 != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x63B,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
          (const char *)v52,
          (int)v68);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v63);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v60);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v59);
        v57 = 0;
        CoUninitialize();
        MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity((MDMPushProvider::DeleteScheduleActivity *)v75);
        return v52;
      }
    }
    else if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x643,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)v26,
        (int)v68);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v63);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v60);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v59);
      v57 = 0;
      CoUninitialize();
      MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity((MDMPushProvider::DeleteScheduleActivity *)v75);
      return (unsigned int)v26;
    }
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v59);
    wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v75);
    CoUninitialize();
    MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity((MDMPushProvider::DeleteScheduleActivity *)v75);
    result = 0;
  }
  catch ( ... )
  {
    v58 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x646,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
            v21);
    if ( v57 )
      CoUninitialize();
    MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity((MDMPushProvider::DeleteScheduleActivity *)v75);
    return v58;
  }
  return result;
}

```

## disassembly

```asm
0x1800c6738  mov     rax, rsp
0x1800c673b  mov     [rax+18h], rbx
0x1800c673f  push    rsi
0x1800c6740  push    rdi
0x1800c6741  push    r12
0x1800c6743  push    r13
0x1800c6745  push    r14
0x1800c6747  sub     rsp, 300h
0x1800c674e  movaps  xmmword ptr [rax-38h], xmm6
0x1800c6752  movaps  xmmword ptr [rax-48h], xmm7
0x1800c6756  movaps  xmmword ptr [rax-58h], xmm8
0x1800c675b  movaps  xmmword ptr [rax-68h], xmm9
0x1800c6760  movaps  xmmword ptr [rax-78h], xmm10
0x1800c6765  movaps  xmmword ptr [rax-88h], xmm11
0x1800c676d  mov     rax, cs:__security_cookie
0x1800c6774  xor     rax, rsp
0x1800c6777  mov     [rsp+328h+var_98], rax
0x1800c677f  mov     r12, rdx
0x1800c6782  mov     r13, rcx
0x1800c6785  lea     rdx, aDeleteschedule; "DeleteScheduleActivity"
0x1800c678c  lea     rcx, [rsp+328h+var_1E8]; struct wil::details::IFailureCallback *
0x1800c6794  call    ??0?$ActivityBase@VMDMPushProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c6799  lea     rax, ??_7DeleteScheduleActivity@MDMPushProvider@@6B@; const MDMPushProvider::DeleteScheduleActivity::`vftable'
0x1800c67a0  mov     [rsp+328h+var_1E8], rax
0x1800c67a8  lea     rcx, [rsp+328h+var_1E8]; this
0x1800c67b0  call    ?StartActivity@DeleteScheduleActivity@MDMPushProvider@@QEAAXXZ; MDMPushProvider::DeleteScheduleActivity::StartActivity(void)
0x1800c67b5  nop
0x1800c67b6  xor     esi, esi
0x1800c67b8  test    r12, r12
0x1800c67bb  jnz     short loc_1800C67CC
0x1800c67bd  mov     ebx, 80070057h
0x1800c67c2  mov     r9d, ebx
0x1800c67c5  mov     edx, 611h
0x1800c67ca  jmp     short loc_1800C681B
0x1800c67cc  lea     rdx, [rsp+328h+var_2D0]
0x1800c67d1  lea     rcx, [rsp+328h+var_1E8]
0x1800c67d9  call    ?LockExclusive@?$ActivityBase@VNodeCacheProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NodeCacheProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800c67de  mov     rbx, [rsp+328h+var_D8]
0x1800c67e6  lea     rcx, [rbx+28h]; this
0x1800c67ea  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x1800c67ef  mov     [rbx+38h], r12
0x1800c67f3  lea     rcx, [rsp+328h+var_2D0]
0x1800c67f8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800c67fd  xor     edx, edx; dwCoInit
0x1800c67ff  xor     ecx, ecx; pvReserved
0x1800c6801  call    cs:__imp_CoInitializeEx
0x1800c6808  nop     dword ptr [rax+rax+00h]
0x1800c680d  mov     ebx, eax
0x1800c680f  test    eax, eax
0x1800c6811  jns     short loc_1800C6844
0x1800c6813  mov     r9d, eax; char *
0x1800c6816  mov     edx, 614h; void *
0x1800c681b  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800c6822  mov     rcx, [rsp+328h]; this
0x1800c682a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c682f  nop
0x1800c6830  lea     rcx, [rsp+328h+var_1E8]; this
0x1800c6838  call    ??1DeleteScheduleActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity(void)
0x1800c683d  mov     eax, ebx
0x1800c683f  jmp     loc_1800C6F64
0x1800c6844  mov     [rsp+328h+var_2F7], 1
0x1800c6849  mov     [rsp+328h+var_2F0], rsi
0x1800c684e  lea     rcx, [rsp+328h+var_2F0]
0x1800c6853  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c6858  lea     rax, [rsp+328h+var_2F0]
0x1800c685d  mov     qword ptr [rsp+328h+ppv], rax; int
0x1800c6862  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800c6869  xor     edx, edx; pUnkOuter
0x1800c686b  lea     r8d, [rdx+1]; dwClsContext
0x1800c686f  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800c6876  call    cs:__imp_CoCreateInstance
0x1800c687d  nop     dword ptr [rax+rax+00h]
0x1800c6882  mov     ebx, eax
0x1800c6884  test    eax, eax
0x1800c6886  jns     short loc_1800C68D6
0x1800c6888  mov     rcx, [rsp+328h]; this
0x1800c6890  mov     r9d, eax; char *
0x1800c6893  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800c689a  mov     edx, 61Eh; void *
0x1800c689f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c68a4  nop
0x1800c68a5  lea     rcx, [rsp+328h+var_2F0]
0x1800c68aa  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c68af  nop
0x1800c68b0  mov     [rsp+328h+var_2F7], sil
0x1800c68b5  call    cs:__imp_CoUninitialize
0x1800c68bc  nop     dword ptr [rax+rax+00h]
0x1800c68c1  nop
0x1800c68c2  lea     rcx, [rsp+328h+var_1E8]; this
0x1800c68ca  call    ??1DeleteScheduleActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity(void)
0x1800c68cf  mov     eax, ebx
0x1800c68d1  jmp     loc_1800C6F64
0x1800c68d6  mov     rdi, [rsp+328h+var_2F0]
0x1800c68db  mov     rax, [rdi]
0x1800c68de  mov     rbx, [rax+50h]
0x1800c68e2  lea     rcx, [rsp+328h+pvarg]; pvarg
0x1800c68ea  call    cs:__imp_VariantInit
0x1800c68f1  nop     dword ptr [rax+rax+00h]
0x1800c68f6  nop
0x1800c68f7  movups  xmm10, xmmword ptr [rsp+328h+pvarg]
0x1800c6900  movsd   xmm11, qword ptr [rsp+328h+pvarg+10h]
0x1800c690a  lea     rcx, [rsp+328h+var_298]; pvarg
0x1800c6912  call    cs:__imp_VariantInit
0x1800c6919  nop     dword ptr [rax+rax+00h]
0x1800c691e  nop
0x1800c691f  movups  xmm8, xmmword ptr [rsp+328h+var_298]
0x1800c6928  movsd   xmm9, qword ptr [rsp+328h+var_298+10h]
0x1800c6932  lea     rcx, [rsp+328h+var_2B0]; pvarg
0x1800c6937  call    cs:__imp_VariantInit
0x1800c693e  nop     dword ptr [rax+rax+00h]
0x1800c6943  nop
0x1800c6944  movups  xmm6, xmmword ptr [rsp+328h+var_2B0]
0x1800c6949  movsd   xmm7, qword ptr [rsp+328h+var_2B0+10h]
0x1800c6952  lea     rcx, [rsp+328h+var_2C8]; pvarg
0x1800c6957  call    cs:__imp_VariantInit
0x1800c695e  nop     dword ptr [rax+rax+00h]
0x1800c6963  nop
0x1800c6964  movups  xmm0, xmmword ptr [rsp+328h+var_2C8]
0x1800c6969  movsd   xmm1, qword ptr [rsp+328h+var_2C8+10h]
0x1800c696f  movaps  xmmword ptr [rsp+328h+var_268], xmm10
0x1800c6978  movsd   [rsp+328h+var_258], xmm11
0x1800c6982  movaps  [rsp+328h+var_248], xmm8
0x1800c698b  movsd   [rsp+328h+var_238], xmm9
0x1800c6995  movaps  [rsp+328h+var_228], xmm6
0x1800c699d  movsd   [rsp+328h+var_218], xmm7
0x1800c69a6  movaps  [rsp+328h+var_208], xmm0
0x1800c69ae  movsd   [rsp+328h+var_1F8], xmm1
0x1800c69b7  lea     rax, [rsp+328h+var_268]
0x1800c69bf  mov     qword ptr [rsp+328h+ppv], rax; int
0x1800c69c4  lea     r9, [rsp+328h+var_248]
0x1800c69cc  lea     r8, [rsp+328h+var_228]
0x1800c69d4  lea     rdx, [rsp+328h+var_208]
0x1800c69dc  mov     rcx, rdi
0x1800c69df  mov     rax, rbx
0x1800c69e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c69e7  mov     ebx, eax
0x1800c69e9  lea     rcx, [rsp+328h+var_2C8]; this
0x1800c69ee  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800c69f3  nop
0x1800c69f4  lea     rcx, [rsp+328h+var_2B0]; this
0x1800c69f9  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800c69fe  nop
0x1800c69ff  lea     rcx, [rsp+328h+var_298]; this
0x1800c6a07  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800c6a0c  nop
0x1800c6a0d  lea     rcx, [rsp+328h+pvarg]; this
0x1800c6a15  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800c6a1a  test    ebx, ebx
0x1800c6a1c  jns     short loc_1800C6A6C
0x1800c6a1e  mov     rcx, [rsp+328h]; this
0x1800c6a26  mov     r9d, ebx; char *
0x1800c6a29  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800c6a30  mov     edx, 620h; void *
0x1800c6a35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6a3a  nop
0x1800c6a3b  lea     rcx, [rsp+328h+var_2F0]
0x1800c6a40  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c6a45  nop
0x1800c6a46  mov     [rsp+328h+var_2F7], sil
0x1800c6a4b  call    cs:__imp_CoUninitialize
0x1800c6a52  nop     dword ptr [rax+rax+00h]
0x1800c6a57  nop
0x1800c6a58  lea     rcx, [rsp+328h+var_1E8]; this
0x1800c6a60  call    ??1DeleteScheduleActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::DeleteScheduleActivity::~DeleteScheduleActivity(void)
0x1800c6a65  mov     eax, ebx
0x1800c6a67  jmp     loc_1800C6F64
0x1800c6a6c  mov     [rsp+328h+var_2D8], rsi
0x1800c6a71  mov     [rsp+328h+var_2E8], rsi
0x1800c6a76  mov     [rsp+328h+var_2D0], rsi
0x1800c6a7b  mov     rbx, [rsp+328h+var_2F0]
0x1800c6a80  mov     rdi, [rbx]
0x1800c6a83  lea     rcx, [rsp+328h+var_2D8]
0x1800c6a88  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c6a8d  lea     rdx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800c6a94  lea     rcx, [rsp+328h+Block]; this
0x1800c6a99  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800c6a9e  nop
0x1800c6a9f  mov     rax, [rax]
0x1800c6aa2  test    rax, rax
0x1800c6aa5  jz      short loc_1800C6AAC
0x1800c6aa7  mov     rdx, [rax]
0x1800c6aaa  jmp     short loc_1800C6AAF
0x1800c6aac  mov     rdx, rsi
0x1800c6aaf  lea     r8, [rsp+328h+var_2D8]
0x1800c6ab4  mov     rcx, rbx
0x1800c6ab7  mov     rax, [rdi+38h]
0x1800c6abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6ac0  mov     r14d, eax
0x1800c6ac3  mov     rbx, [rsp+328h+Block]
0x1800c6ac8  or      edi, 0FFFFFFFFh
0x1800c6acb  test    rbx, rbx
0x1800c6ace  jz      short loc_1800C6B16
0x1800c6ad0  mov     eax, edi
0x1800c6ad2  lock xadd [rbx+10h], eax
0x1800c6ad7  add     eax, edi
0x1800c6ad9  jnz     short loc_1800C6B16
0x1800c6adb  test    rbx, rbx
0x1800c6ade  jz      short loc_1800C6B16
0x1800c6ae0  cmp     [rbx], rsi
0x1800c6ae3  jz      short loc_1800C6AF7
0x1800c6ae5  mov     rcx, [rbx]; bstrString
0x1800c6ae8  call    cs:__imp_SysFreeString
0x1800c6aef  nop     dword ptr [rax+rax+00h]
0x1800c6af4  mov     [rbx], rsi
0x1800c6af7  mov     rcx, [rbx+8]; Block
0x1800c6afb  test    rcx, rcx
0x1800c6afe  jz      short loc_1800C6B09
0x1800c6b00  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c6b05  mov     [rbx+8], rsi
0x1800c6b09  mov     edx, 18h
0x1800c6b0e  mov     rcx, rbx; Block
0x1800c6b11  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c6b16  test    r14d, r14d
0x1800c6b19  js      loc_1800C6C45
0x1800c6b1f  mov     rbx, [rsp+328h+var_2D8]
0x1800c6b24  mov     r14, [rbx]
0x1800c6b27  lea     rcx, [rsp+328h+var_2E8]
0x1800c6b2c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c6b31  mov     rdx, [r13+8]; unsigned __int16 *
0x1800c6b35  lea     rcx, [rsp+328h+Block]; this
0x1800c6b3a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800c6b3f  nop
0x1800c6b40  mov     rax, [rax]
0x1800c6b43  test    rax, rax
0x1800c6b46  jz      short loc_1800C6B4D
0x1800c6b48  mov     rdx, [rax]
0x1800c6b4b  jmp     short loc_1800C6B50
0x1800c6b4d  mov     rdx, rsi
0x1800c6b50  lea     r8, [rsp+328h+var_2E8]
0x1800c6b55  mov     rcx, rbx
0x1800c6b58  mov     rax, [r14+48h]
0x1800c6b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6b61  mov     r14d, eax
0x1800c6b64  mov     rbx, [rsp+328h+Block]
0x1800c6b69  test    rbx, rbx
0x1800c6b6c  jz      short loc_1800C6BB4
0x1800c6b6e  mov     eax, edi
0x1800c6b70  lock xadd [rbx+10h], eax
0x1800c6b75  add     eax, edi
0x1800c6b77  jnz     short loc_1800C6BB4
0x1800c6b79  test    rbx, rbx
0x1800c6b7c  jz      short loc_1800C6BB4
0x1800c6b7e  cmp     [rbx], rsi
0x1800c6b81  jz      short loc_1800C6B95
0x1800c6b83  mov     rcx, [rbx]; bstrString
0x1800c6b86  call    cs:__imp_SysFreeString
0x1800c6b8d  nop     dword ptr [rax+rax+00h]
0x1800c6b92  mov     [rbx], rsi
0x1800c6b95  mov     rcx, [rbx+8]; Block
0x1800c6b99  test    rcx, rcx
0x1800c6b9c  jz      short loc_1800C6BA7
0x1800c6b9e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c6ba3  mov     [rbx+8], rsi
0x1800c6ba7  mov     edx, 18h
0x1800c6bac  mov     rcx, rbx; Block
0x1800c6baf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c6bb4  test    r14d, r14d
0x1800c6bb7  js      loc_1800C6C45
0x1800c6bbd  mov     rbx, [rsp+328h+var_2E8]
0x1800c6bc2  mov     r14, [rbx]
0x1800c6bc5  mov     rdx, r12; unsigned __int16 *
0x1800c6bc8  lea     rcx, [rsp+328h+Block]; this
0x1800c6bcd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800c6bd2  nop
0x1800c6bd3  mov     rax, [rax]
0x1800c6bd6  test    rax, rax
0x1800c6bd9  jz      short loc_1800C6BE0
0x1800c6bdb  mov     rdx, [rax]
0x1800c6bde  jmp     short loc_1800C6BE3
0x1800c6be0  mov     rdx, rsi
0x1800c6be3  xor     r8d, r8d
0x1800c6be6  mov     rcx, rbx
0x1800c6be9  mov     rax, [r14+78h]
0x1800c6bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6bf2  mov     r14d, eax
0x1800c6bf5  mov     rbx, [rsp+328h+Block]
0x1800c6bfa  test    rbx, rbx
0x1800c6bfd  jz      short loc_1800C6C45
0x1800c6bff  mov     eax, edi
0x1800c6c01  lock xadd [rbx+10h], eax
0x1800c6c06  add     eax, edi
0x1800c6c08  jnz     short loc_1800C6C45
0x1800c6c0a  test    rbx, rbx
0x1800c6c0d  jz      short loc_1800C6C45
0x1800c6c0f  cmp     [rbx], rsi
0x1800c6c12  jz      short loc_1800C6C26
0x1800c6c14  mov     rcx, [rbx]; bstrString
0x1800c6c17  call    cs:__imp_SysFreeString
0x1800c6c1e  nop     dword ptr [rax+rax+00h]
0x1800c6c23  mov     [rbx], rsi
0x1800c6c26  mov     rcx, [rbx+8]; Block
0x1800c6c2a  test    rcx, rcx
0x1800c6c2d  jz      short loc_1800C6C38
0x1800c6c2f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c6c34  mov     [rbx+8], rsi
0x1800c6c38  mov     edx, 18h
0x1800c6c3d  mov     rcx, rbx; Block
0x1800c6c40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c6c45  mov     r13d, 80070002h
0x1800c6c4b  cmp     r14d, r13d
  ... truncated ...
```
