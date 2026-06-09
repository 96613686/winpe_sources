# EnrollForOneAIK(ushort const *)

- ea: `0x1800126e4`
- end: `0x180012ebc`
- name: `?EnrollForOneAIK@@YAJPEBG@Z`
- size: `2008`
- prototype: `__int64 __fastcall(OLECHAR *)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012438`

## callees

- `0x1800012cc`
- `0x18000247c`
- `0x180002e70`
- `0x180006330`
- `0x180006e9c`
- `0x180008ab0`
- `0x18000cc34`
- `0x18000ec2c`
- `0x18000feb8`
- `0x18000ff40`
- `0x1800101b0`
- `0x1800101fc`
- `0x1800108f8`
- `0x1800114ac`
- `0x1800114f8`
- `0x180011814`
- `0x180012274`
- `0x1800126e4`
- `0x1800150a0`
- `0x180016b24`
- `0x180022010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012740`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001276c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012cb0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012740`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001276c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012cb0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012927`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012927`
- `OLEAUT32!__imp_SysAllocString` at `0x18001298d`
- `OLEAUT32!__imp_SysAllocString` at `0x180012a84`
- `OLEAUT32!__imp_SysAllocString` at `0x18001298d`
- `OLEAUT32!__imp_SysAllocString` at `0x180012a84`
- `OLEAUT32!__imp_SysFreeString` at `0x1800129cd`
- `OLEAUT32!__imp_SysFreeString` at `0x180012a44`
- `OLEAUT32!__imp_SysFreeString` at `0x180012ac4`
- `OLEAUT32!__imp_SysFreeString` at `0x180012ace`
- `OLEAUT32!__imp_SysFreeString` at `0x180012b43`
- `OLEAUT32!__imp_SysFreeString` at `0x180012b4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180012bc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180012bce`
- `OLEAUT32!__imp_SysFreeString` at `0x180012d8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180012d99`
- `OLEAUT32!__imp_SysFreeString` at `0x180012dda`
- `OLEAUT32!__imp_SysFreeString` at `0x180012de4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800129cd`
- `OLEAUT32!__imp_SysFreeString` at `0x180012a44`
- `OLEAUT32!__imp_SysFreeString` at `0x180012ac4`
- `OLEAUT32!__imp_SysFreeString` at `0x180012ace`
- `OLEAUT32!__imp_SysFreeString` at `0x180012b43`
- `OLEAUT32!__imp_SysFreeString` at `0x180012b4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180012bc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180012bce`
- `OLEAUT32!__imp_SysFreeString` at `0x180012d8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180012d99`
- `OLEAUT32!__imp_SysFreeString` at `0x180012dda`
- `OLEAUT32!__imp_SysFreeString` at `0x180012de4`

## string_xrefs

- `0x18001293d`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800129b9`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180012a2f`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180012ab0`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180012b2e`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180012baf`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180012d7a`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180012e5b`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnrollForOneAIK(OLECHAR *a1)
{
  bool IsZero; // al
  GUID *v2; // r9
  int v3; // eax
  unsigned int v4; // ebx
  HRESULT Instance; // eax
  unsigned __int16 *v6; // rax
  OLECHAR *v7; // rbx
  int v8; // edi
  int v9; // eax
  unsigned __int16 *v10; // rax
  OLECHAR *v11; // rdi
  int v12; // eax
  int v13; // esi
  int v14; // eax
  bool v15; // al
  GUID *v16; // r9
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  bool v21; // [rsp+30h] [rbp-D0h] BYREF
  char v22; // [rsp+31h] [rbp-CFh] BYREF
  bool v23; // [rsp+32h] [rbp-CEh] BYREF
  char v24; // [rsp+33h] [rbp-CDh] BYREF
  _DWORD v25[3]; // [rsp+34h] [rbp-CCh] BYREF
  OLECHAR *psz; // [rsp+40h] [rbp-C0h] BYREF
  int v27[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct EnrollAIKResult *v28; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[24]; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  BSTR v31; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v32[3]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v33[9]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v34[80]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v35[5]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v36; // [rsp+180h] [rbp+80h]
  __int128 v37; // [rsp+190h] [rbp+90h]
  __int128 v38; // [rsp+1A0h] [rbp+A0h]
  __int128 v39; // [rsp+1B0h] [rbp+B0h]
  __int64 v40; // [rsp+1C0h] [rbp+C0h]
  int v41; // [rsp+1D0h] [rbp+D0h] BYREF
  char v42; // [rsp+1D4h] [rbp+D4h]
  _BYTE v43[16]; // [rsp+1D8h] [rbp+D8h] BYREF
  GUID v44; // [rsp+1E8h] [rbp+E8h] BYREF
  int v45; // [rsp+1F8h] [rbp+F8h] BYREF
  char v46; // [rsp+1FCh] [rbp+FCh]
  GUID ActivityId; // [rsp+200h] [rbp+100h] BYREF
  GUID v48; // [rsp+210h] [rbp+110h] BYREF
  _OWORD v49[2]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  psz = a1;
  v25[0] = 0;
  v45 = 0;
  v46 = 0;
  if ( (unsigned int)dword_180031038 <= 5 )
  {
    ActivityId = 0;
  }
  else
  {
    EventActivityIdControl(3u, &ActivityId);
    v48 = ActivityId;
    EventActivityIdControl(4u, &v48);
    v46 = 1;
  }
  v45 = 1;
  if ( (unsigned int)dword_180031038 > 5 )
  {
    v27[0] = v25[0];
    if ( !v46 || (IsZero = _tlgGuidIsZero(&v48), v2 = &v48, IsZero) )
      LODWORD(v2) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180031038,
      (unsigned int)byte_180029A19,
      (unsigned int)&ActivityId,
      (_DWORD)v2,
      (__int64)v27);
  }
  v32[0] = &v45;
  v32[1] = v25;
  wil::ScopeExitIgnore__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___(v29, v32);
  v41 = 0;
  v42 = 0;
  v21 = 1;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  memset_0(v35, 0, 0x98u);
  DWORD2(v36) = 3;
  memset(v49, 0, sizeof(v49));
  *(_QWORD *)v27 = v49;
  v32[0] = v27;
  lambda_480c9a5b356a727f9f61f1d4648b00a2_::operator()(v32);
  v28 = 0;
  v33[0] = v25;
  v33[1] = &v21;
  v33[2] = &v22;
  v33[3] = &v23;
  v33[4] = &v24;
  v33[5] = &psz;
  v33[6] = v35;
  v33[7] = v49;
  v33[8] = &v28;
  wil::ScopeExitIgnore__lambda_c7b5acbfa5fe69ccd764c511e264b77e___(v34, v33);
  v3 = ShouldEnrollAikCert(psz, &v21);
  v4 = v3;
  v25[0] = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50B,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)v3,
      ppv);
    wil::details::ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e___::operator()(v34);
    _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v41);
    wil::details::ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___::operator()(v29);
    goto LABEL_44;
  }
  if ( !v21 )
  {
    v25[0] = 0;
    wil::details::ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e___::operator()(v34);
    _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v41);
    wil::details::ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___::operator()(v29);
    goto LABEL_41;
  }
  *(_QWORD *)&v25[1] = 0;
  Instance = CoCreateInstance(
               &GUID_884e200c_217d_11da_b2a4_000e7bbb2b09,
               0,
               1u,
               &GUID_728ab30c_217d_11da_b2a4_000e7bbb2b09,
               (LPVOID *)&v25[1]);
  v4 = Instance;
  if ( Instance >= 0 )
  {
    bstrString = 0;
    v6 = SysAllocString(L"Microsoft Platform Crypto Provider");
    ATL::CComBSTR::Attach((ATL::CComBSTR *)&bstrString, v6);
    v7 = bstrString;
    if ( !bstrString )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51B,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)0x8007000ELL,
        ppva);
      SysFreeString(0);
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v25[1]);
      wil::details::ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e___::operator()(v34);
      _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v41);
      wil::details::ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___::operator()(v29);
LABEL_15:
      v4 = v8;
      goto LABEL_44;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(**(_QWORD **)&v25[1] + 208LL))(*(_QWORD *)&v25[1], bstrString);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51E,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v9,
        ppva);
      SysFreeString(v7);
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v25[1]);
      wil::details::ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e___::operator()(v34);
      _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v41);
      wil::details::ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___::operator()(v29);
      goto LABEL_15;
    }
    v31 = 0;
    v10 = SysAllocString(psz);
    ATL::CComBSTR::Attach((ATL::CComBSTR *)&v31, v10);
    v11 = v31;
    if ( !v31 )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x523,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)0x8007000ELL,
        ppva);
      SysFreeString(0);
      SysFreeString(v7);
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v25[1]);
      wil::details::ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e___::operator()(v34);
      _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v41);
      wil::details::ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___::operator()(v29);
      goto LABEL_15;
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(**(_QWORD **)&v25[1] + 128LL))(*(_QWORD *)&v25[1], v31);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x526,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v12,
        ppva);
      SysFreeString(v11);
      SysFreeString(v7);
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v25[1]);
      wil::details::ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e___::operator()(v34);
      _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v41);
      wil::details::ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___::operator()(v29);
LABEL_22:
      v4 = v13;
      goto LABEL_44;
    }
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v25[1] + 424LL))(*(_QWORD *)&v25[1], 0xFFFFFFFFLL);
    v13 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x529,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v14,
        ppva);
      SysFreeString(v11);
      SysFreeString(v7);
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v25[1]);
      wil::details::ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e___::operator()(v34);
      _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v41);
      wil::details::ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___::operator()(v29);
      goto LABEL_22;
    }
    _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v41);
    if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
    {
      if ( !v42 || (v15 = _tlgGuidIsZero(&v44), v16 = &v44, v15) )
        v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180031038,
        &byte_1800296E7,
        v43,
        v16);
    }
    v22 = 1;
    v25[0] = EnrollAIKWrapper(*(struct IX509PrivateKey2 **)&v25[1], psz, (const struct _RETRYINFO *)v49, &v23, &v28);
    if ( v42 )
      EventActivityIdControl(4u, &v44);
    v41 = 2;
    if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180031038,
        byte_1800299F1,
        v43,
        0);
    if ( v28 )
    {
      v35[0] = *(_OWORD *)v28;
      v35[1] = *((_OWORD *)v28 + 1);
      v35[2] = *((_OWORD *)v28 + 2);
      v35[3] = *((_OWORD *)v28 + 3);
      v35[4] = *((_OWORD *)v28 + 4);
      v36 = *((_OWORD *)v28 + 5);
      v37 = *((_OWORD *)v28 + 6);
      v38 = *((_OWORD *)v28 + 7);
      v39 = *((_OWORD *)v28 + 8);
      v40 = *((_QWORD *)v28 + 18);
    }
    v13 = v25[0];
    if ( v25[0] < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x542,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)v25[0],
        ppvb);
      SysFreeString(v11);
      SysFreeString(v7);
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v25[1]);
      wil::details::ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e___::operator()(v34);
      _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v41);
      wil::details::ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___::operator()(v29);
      goto LABEL_22;
    }
    v24 = 1;
    SysFreeString(v11);
    SysFreeString(v7);
    ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v25[1]);
    wil::details::ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e___::operator()(v34);
    _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v41);
    wil::details::ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___::operator()(v29);
LABEL_41:
    _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v45);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x516,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
    (const char *)(unsigned int)Instance,
    ppva);
  ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v25[1]);
  wil::details::ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e___::operator()(v34);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v41);
  wil::details::ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___::operator()(v29);
LABEL_44:
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v45);
  return v4;
}

```

## disassembly

```asm
0x1800126e4  push    rbp
0x1800126e6  push    rbx
0x1800126e7  push    rsi
0x1800126e8  push    rdi
0x1800126e9  push    r14
0x1800126eb  push    r15
0x1800126ed  lea     rbp, [rsp-158h]
0x1800126f5  sub     rsp, 258h
0x1800126fc  mov     rax, cs:__security_cookie
0x180012703  xor     rax, rsp
0x180012706  mov     [rbp+180h+var_40], rax
0x18001270d  mov     [rsp+280h+psz], rcx
0x180012712  xor     r14d, r14d
0x180012715  mov     dword ptr [rsp+280h+var_24C], r14d
0x18001271a  mov     [rbp+180h+var_88], r14d
0x180012721  mov     [rbp+180h+var_84], r14b
0x180012728  mov     eax, cs:dword_180031038
0x18001272e  lea     ebx, [r14+3]
0x180012732  cmp     eax, 5
0x180012735  jbe     short loc_18001277B
0x180012737  lea     rdx, [rbp+180h+ActivityId]; ActivityId
0x18001273e  mov     ecx, ebx; ControlCode
0x180012740  call    cs:__imp_EventActivityIdControl
0x180012746  mov     rax, qword ptr [rbp+180h+ActivityId.Data1]
0x18001274d  mov     qword ptr [rbp+180h+var_70.Data1], rax
0x180012754  mov     rax, qword ptr [rbp+180h+ActivityId.Data4]
0x18001275b  mov     qword ptr [rbp+180h+var_70.Data4], rax
0x180012762  lea     rdx, [rbp+180h+var_70]; ActivityId
0x180012769  lea     ecx, [rbx+1]; ControlCode
0x18001276c  call    cs:__imp_EventActivityIdControl
0x180012772  mov     [rbp+180h+var_84], 1
0x180012779  jmp     short loc_180012785
0x18001277b  xorps   xmm0, xmm0
0x18001277e  movups  xmmword ptr [rbp+180h+ActivityId.Data1], xmm0
0x180012785  mov     [rbp+180h+var_88], 1
0x18001278f  mov     eax, cs:dword_180031038
0x180012795  lea     r15, dword_180031038
0x18001279c  cmp     eax, 5
0x18001279f  jbe     short loc_1800127EC
0x1800127a1  mov     eax, dword ptr [rsp+280h+var_24C]
0x1800127a5  mov     [rsp+280h+var_238], eax
0x1800127a9  cmp     [rbp+180h+var_84], r14b
0x1800127b0  jz      short loc_1800127C9
0x1800127b2  lea     rcx, [rbp+180h+var_70]; struct _GUID *
0x1800127b9  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800127be  test    al, al
0x1800127c0  lea     r9, [rbp+180h+var_70]
0x1800127c7  jz      short loc_1800127CC
0x1800127c9  mov     r9, r14
0x1800127cc  lea     rax, [rsp+280h+var_238]
0x1800127d1  mov     qword ptr [rsp+280h+ppv], rax; int
0x1800127d6  lea     r8, [rbp+180h+ActivityId]
0x1800127dd  lea     rdx, byte_180029A19
0x1800127e4  mov     rcx, r15
0x1800127e7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800127ec  lea     rax, [rbp+180h+var_88]
0x1800127f3  mov     [rbp+180h+var_200], rax
0x1800127f7  lea     rax, [rsp+280h+var_24C]
0x1800127fc  mov     [rbp+180h+var_1F8], rax
0x180012800  lea     rdx, [rbp+180h+var_200]
0x180012804  lea     rcx, [rsp+280h+var_228]
0x180012809  call    wil__ScopeExitIgnore__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b___
0x18001280e  nop
0x18001280f  mov     [rbp+180h+var_B0], r14d
0x180012816  mov     [rbp+180h+var_AC], r14b
0x18001281d  mov     [rsp+280h+var_250], 1
0x180012822  mov     [rsp+280h+var_24F], r14b
0x180012827  mov     [rsp+280h+var_24E], r14b
0x18001282c  mov     [rsp+280h+var_24D], r14b
0x180012831  xor     edx, edx; Val
0x180012833  mov     r8d, 98h; Size
0x180012839  lea     rcx, [rbp+180h+var_150]; void *
0x18001283d  call    memset_0
0x180012842  mov     [rbp+180h+var_F8], ebx
0x180012848  xorps   xmm0, xmm0
0x18001284b  movups  [rbp+180h+var_60], xmm0
0x180012852  movups  [rbp+180h+var_50], xmm0
0x180012859  lea     rax, [rbp+180h+var_60]
0x180012860  mov     qword ptr [rsp+280h+var_238], rax
0x180012865  lea     rax, [rsp+280h+var_238]
0x18001286a  mov     [rbp+180h+var_200], rax
0x18001286e  lea     rcx, [rbp+180h+var_200]
0x180012872  call    _lambda_480c9a5b356a727f9f61f1d4648b00a2___operator__
0x180012877  mov     [rsp+280h+var_230], r14
0x18001287c  lea     rax, [rsp+280h+var_24C]
0x180012881  mov     [rbp+180h+var_1E8], rax
0x180012885  lea     rax, [rsp+280h+var_250]
0x18001288a  mov     [rbp+180h+var_1E0], rax
0x18001288e  lea     rax, [rsp+280h+var_24F]
0x180012893  mov     [rbp+180h+var_1D8], rax
0x180012897  lea     rax, [rsp+280h+var_24E]
0x18001289c  mov     [rbp+180h+var_1D0], rax
0x1800128a0  lea     rax, [rsp+280h+var_24D]
0x1800128a5  mov     [rbp+180h+var_1C8], rax
0x1800128a9  lea     rax, [rsp+280h+psz]
0x1800128ae  mov     [rbp+180h+var_1C0], rax
0x1800128b2  lea     rax, [rbp+180h+var_150]
0x1800128b6  mov     [rbp+180h+var_1B8], rax
0x1800128ba  lea     rax, [rbp+180h+var_60]
0x1800128c1  mov     [rbp+180h+var_1B0], rax
0x1800128c5  lea     rax, [rsp+280h+var_230]
0x1800128ca  mov     [rbp+180h+var_1A8], rax
0x1800128ce  lea     rdx, [rbp+180h+var_1E8]
0x1800128d2  lea     rcx, [rbp+180h+var_1A0]
0x1800128d6  call    wil__ScopeExitIgnore__lambda_c7b5acbfa5fe69ccd764c511e264b77e___
0x1800128db  nop
0x1800128dc  lea     rdx, [rsp+280h+var_250]; bool *
0x1800128e1  mov     rcx, [rsp+280h+psz]; unsigned __int16 *
0x1800128e6  call    ?ShouldEnrollAikCert@@YAJPEBGPEA_N@Z; ShouldEnrollAikCert(ushort const *,bool *)
0x1800128eb  mov     ebx, eax
0x1800128ed  mov     dword ptr [rsp+280h+var_24C], eax
0x1800128f1  test    eax, eax
0x1800128f3  js      loc_180012E51
0x1800128f9  cmp     [rsp+280h+var_250], r14b
0x1800128fe  jz      loc_180012E28
0x180012904  mov     qword ptr [rsp+280h+var_24C+4], r14
0x180012909  lea     rax, [rsp+280h+var_24C+4]
0x18001290e  mov     qword ptr [rsp+280h+ppv], rax; int
0x180012913  lea     r9, _GUID_728ab30c_217d_11da_b2a4_000e7bbb2b09; riid
0x18001291a  xor     edx, edx; pUnkOuter
0x18001291c  lea     r8d, [rdx+1]; dwClsContext
0x180012920  lea     rcx, _GUID_884e200c_217d_11da_b2a4_000e7bbb2b09; rclsid
0x180012927  call    cs:__imp_CoCreateInstance
0x18001292d  mov     ebx, eax
0x18001292f  test    eax, eax
0x180012931  jns     short loc_180012981
0x180012933  mov     rcx, [rbp+188h]; this
0x18001293a  mov     r9d, eax; char *
0x18001293d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180012944  mov     edx, 516h; void *
0x180012949  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001294e  nop
0x18001294f  lea     rcx, [rsp+280h+var_24C+4]
0x180012954  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180012959  nop
0x18001295a  lea     rcx, [rbp+180h+var_1A0]
0x18001295e  call    wil__details__ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e_____operator__
0x180012963  nop
0x180012964  lea     rcx, [rbp+180h+var_B0]
0x18001296b  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180012970  nop
0x180012971  lea     rcx, [rsp+280h+var_228]
0x180012976  call    wil__details__ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b_____operator__
0x18001297b  nop
0x18001297c  jmp     loc_180012E8F
0x180012981  mov     [rsp+280h+bstrString], r14
0x180012986  lea     rcx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001298d  call    cs:__imp_SysAllocString
0x180012993  mov     rdx, rax; unsigned __int16 *
0x180012996  lea     rcx, [rsp+280h+bstrString]; this
0x18001299b  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x1800129a0  mov     rbx, [rsp+280h+bstrString]
0x1800129a5  test    rbx, rbx
0x1800129a8  jnz     short loc_180012A08
0x1800129aa  mov     rcx, [rbp+188h]; this
0x1800129b1  mov     edi, 8007000Eh
0x1800129b6  mov     r9d, edi; char *
0x1800129b9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800129c0  mov     edx, 51Bh; void *
0x1800129c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129ca  nop
0x1800129cb  xor     ecx, ecx; bstrString
0x1800129cd  call    cs:__imp_SysFreeString
0x1800129d3  nop
0x1800129d4  lea     rcx, [rsp+280h+var_24C+4]
0x1800129d9  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800129de  nop
0x1800129df  lea     rcx, [rbp+180h+var_1A0]
0x1800129e3  call    wil__details__ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e_____operator__
0x1800129e8  nop
0x1800129e9  lea     rcx, [rbp+180h+var_B0]
0x1800129f0  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x1800129f5  nop
0x1800129f6  lea     rcx, [rsp+280h+var_228]
0x1800129fb  call    wil__details__ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b_____operator__
0x180012a00  nop
0x180012a01  mov     ebx, edi
0x180012a03  jmp     loc_180012E8F
0x180012a08  mov     rcx, qword ptr [rsp+280h+var_24C+4]
0x180012a0d  mov     rax, [rcx]
0x180012a10  mov     rdx, rbx
0x180012a13  mov     rax, [rax+0D0h]
0x180012a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a1f  mov     edi, eax
0x180012a21  test    eax, eax
0x180012a23  jns     short loc_180012A7A
0x180012a25  mov     rcx, [rbp+188h]; this
0x180012a2c  mov     r9d, eax; char *
0x180012a2f  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180012a36  mov     edx, 51Eh; void *
0x180012a3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a40  nop
0x180012a41  mov     rcx, rbx; bstrString
0x180012a44  call    cs:__imp_SysFreeString
0x180012a4a  nop
0x180012a4b  lea     rcx, [rsp+280h+var_24C+4]
0x180012a50  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180012a55  nop
0x180012a56  lea     rcx, [rbp+180h+var_1A0]
0x180012a5a  call    wil__details__ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e_____operator__
0x180012a5f  nop
0x180012a60  lea     rcx, [rbp+180h+var_B0]
0x180012a67  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180012a6c  nop
0x180012a6d  lea     rcx, [rsp+280h+var_228]
0x180012a72  call    wil__details__ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b_____operator__
0x180012a77  nop
0x180012a78  jmp     short loc_180012A01
0x180012a7a  mov     [rsp+280h+var_208], r14
0x180012a7f  mov     rcx, [rsp+280h+psz]; psz
0x180012a84  call    cs:__imp_SysAllocString
0x180012a8a  mov     rdx, rax; unsigned __int16 *
0x180012a8d  lea     rcx, [rsp+280h+var_208]; this
0x180012a92  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180012a97  mov     rdi, [rsp+280h+var_208]
0x180012a9c  test    rdi, rdi
0x180012a9f  jnz     short loc_180012B07
0x180012aa1  mov     rcx, [rbp+188h]; this
0x180012aa8  mov     edi, 8007000Eh
0x180012aad  mov     r9d, edi; char *
0x180012ab0  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180012ab7  mov     edx, 523h; void *
0x180012abc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ac1  nop
0x180012ac2  xor     ecx, ecx; bstrString
0x180012ac4  call    cs:__imp_SysFreeString
0x180012aca  nop
0x180012acb  mov     rcx, rbx; bstrString
0x180012ace  call    cs:__imp_SysFreeString
0x180012ad4  nop
0x180012ad5  lea     rcx, [rsp+280h+var_24C+4]
0x180012ada  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180012adf  nop
0x180012ae0  lea     rcx, [rbp+180h+var_1A0]
0x180012ae4  call    wil__details__ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e_____operator__
0x180012ae9  nop
0x180012aea  lea     rcx, [rbp+180h+var_B0]
0x180012af1  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180012af6  nop
0x180012af7  lea     rcx, [rsp+280h+var_228]
0x180012afc  call    wil__details__ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b_____operator__
0x180012b01  nop
0x180012b02  jmp     loc_180012A01
0x180012b07  mov     rcx, qword ptr [rsp+280h+var_24C+4]
0x180012b0c  mov     rax, [rcx]
0x180012b0f  mov     rdx, rdi
0x180012b12  mov     rax, [rax+80h]
0x180012b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b1e  mov     esi, eax
0x180012b20  test    eax, eax
0x180012b22  jns     short loc_180012B88
0x180012b24  mov     rcx, [rbp+188h]; this
0x180012b2b  mov     r9d, eax; char *
0x180012b2e  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180012b35  mov     edx, 526h; void *
0x180012b3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b3f  nop
0x180012b40  mov     rcx, rdi; bstrString
0x180012b43  call    cs:__imp_SysFreeString
0x180012b49  nop
0x180012b4a  mov     rcx, rbx; bstrString
0x180012b4d  call    cs:__imp_SysFreeString
0x180012b53  nop
0x180012b54  lea     rcx, [rsp+280h+var_24C+4]
0x180012b59  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180012b5e  nop
0x180012b5f  lea     rcx, [rbp+180h+var_1A0]
0x180012b63  call    wil__details__ScopeExitFnGuard__lambda_c7b5acbfa5fe69ccd764c511e264b77e_____operator__
0x180012b68  nop
0x180012b69  lea     rcx, [rbp+180h+var_B0]
0x180012b70  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180012b75  nop
0x180012b76  lea     rcx, [rsp+280h+var_228]
0x180012b7b  call    wil__details__ScopeExitFnGuard__lambda_ed9959dbdd82f8c99a1d8e08c030ea7b_____operator__
0x180012b80  nop
0x180012b81  mov     ebx, esi
0x180012b83  jmp     loc_180012E8F
0x180012b88  mov     rcx, qword ptr [rsp+280h+var_24C+4]
0x180012b8d  mov     rax, [rcx]
0x180012b90  or      edx, 0FFFFFFFFh
0x180012b93  mov     rax, [rax+1A8h]
0x180012b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b9f  mov     esi, eax
0x180012ba1  test    eax, eax
0x180012ba3  jns     short loc_180012C07
0x180012ba5  mov     rcx, [rbp+188h]; this
0x180012bac  mov     r9d, eax; char *
0x180012baf  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180012bb6  mov     edx, 529h; void *
0x180012bbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012bc0  nop
0x180012bc1  mov     rcx, rdi; bstrString
0x180012bc4  call    cs:__imp_SysFreeString
0x180012bca  nop
0x180012bcb  mov     rcx, rbx; bstrString
0x180012bce  call    cs:__imp_SysFreeString
0x180012bd4  nop
0x180012bd5  lea     rcx, [rsp+280h+var_24C+4]
0x180012bda  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180012bdf  nop
  ... truncated ...
```
