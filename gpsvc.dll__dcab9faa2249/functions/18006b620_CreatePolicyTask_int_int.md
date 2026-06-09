# CreatePolicyTask(int,int)

- ea: `0x18006b620`
- end: `0x18006d3bf`
- name: `?CreatePolicyTask@@YAJHH@Z`
- size: `7583`
- prototype: `__int64 __fastcall(unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012540`

## callees

- `0x180003770`
- `0x1800585e8`
- `0x18006b620`
- `0x18006d3c8`
- `0x18006d428`
- `0x18006d44c`
- `0x18006da24`
- `0x180075ec0`
- `0x1800762fc`
- `0x18007d320`
- `0x180089d8c`
- `0x1800b5b8c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18006c5c6`
- `api-ms-win-crt-private-l1-1-0!_o__gmtime64` at `0x18006c5c6`
- `api-ms-win-crt-private-l1-1-0!_o__tzset` at `0x18006c59e`
- `api-ms-win-crt-private-l1-1-0!_o__tzset` at `0x18006c59e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsftime` at `0x18006c5f9`
- `api-ms-win-crt-private-l1-1-0!_o_wcsftime` at `0x18006c5f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006b6ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006b6ee`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18006c5ab`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18006c5ab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b858`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b858`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bd72`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d251`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bd72`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d251`
- `OLEAUT32!__imp_VariantInit` at `0x18006b8d8`
- `OLEAUT32!__imp_VariantInit` at `0x18006b8ee`
- `OLEAUT32!__imp_VariantInit` at `0x18006b907`
- `OLEAUT32!__imp_VariantInit` at `0x18006b924`
- `OLEAUT32!__imp_VariantInit` at `0x18006cfc9`
- `OLEAUT32!__imp_VariantInit` at `0x18006d0ac`
- `OLEAUT32!__imp_VariantInit` at `0x18006b8d8`
- `OLEAUT32!__imp_VariantInit` at `0x18006b8ee`
- `OLEAUT32!__imp_VariantInit` at `0x18006b907`
- `OLEAUT32!__imp_VariantInit` at `0x18006b924`
- `OLEAUT32!__imp_VariantInit` at `0x18006cfc9`
- `OLEAUT32!__imp_VariantInit` at `0x18006d0ac`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18006c8c2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18006c9f9`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18006c8c2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18006c9f9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18006c960`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18006ca2b`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18006c960`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18006ca2b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18006baf2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18006baf2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18006bafd`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18006bafd`

## string_xrefs

- `0x18006cddd`: `gpupdate.exe`
- `0x18006b6ab`: `CreatePolicyTask called : bMachine = %d, nInterval = %d`
- `0x18006b6d1`: `CreatePolicyTask called : bMachine = %d, nInterval = %d`
- `0x18006b712`: `CreatePolicyTask failed to wait gpservice initialized event with error = %d.`
- `0x18006b73a`: `CreatePolicyTask failed to wait gpservice initialized event with error = %d.`
- `0x18006b7c3`: `CreatePolicyTask: Could not created formatted interval 0x%x`
- `0x18006b7eb`: `CreatePolicyTask: Could not created formatted interval 0x%x`
- `0x18006b880`: `CreatePolicyTask failed 0x%x`
- `0x18006b8b3`: `CreatePolicyTask failed 0x%x`
- `0x18006ba8e`: `CreatePolicyTask %s folder does not exist. Shall attempt to create the folder.`
- `0x18006bab7`: `CreatePolicyTask %s folder does not exist. Shall attempt to create the folder.`
- `0x18006bbc1`: `CreatePolicyTask failed to create %s folder:0x%x `
- `0x18006bbed`: `CreatePolicyTask failed to create %s folder:0x%x `
- `0x18006bc1e`: `CreatePolicyTask failed to get %s folder:0x%x `
- `0x18006bc4a`: `CreatePolicyTask failed to get %s folder:0x%x `
- `0x18006bc77`: `CreatePolicyTask failed to get %s folder:0x%x `
- `0x18006bca3`: `CreatePolicyTask failed to get %s folder:0x%x `
- `0x18006bcda`: ` /target:computer`
- `0x18006bd92`: `CreatePolicyTask - put_Author failed: 0x%x`
- `0x18006bdad`: `CreatePolicyTask - put_Author failed: 0x%x`
- `0x18006bdcb`: `CreatePolicyTask failed creating RegistrationInfo: 0x%x`
- `0x18006bdf0`: `CreatePolicyTask failed creating RegistrationInfo: 0x%x`
- `0x18006d2cb`: `CreatePolicyTask failed: 0x%x`
- `0x18006d2f0`: `CreatePolicyTask failed: 0x%x`
- `0x18006be6d`: `CreatePolicyTask get_Principal failed: 0x%x`
- `0x18006be93`: `CreatePolicyTask get_Principal failed: 0x%x`
- `0x18006bf01`: `CreatePolicyTask put_UserId failed: 0x%x`
- `0x18006bf1c`: `CreatePolicyTask put_UserId failed: 0x%x`
- `0x18006bf56`: `CreatePolicyTask put_RunLevel failed: 0x%x`
- `0x18006bf7b`: `CreatePolicyTask put_RunLevel failed: 0x%x`
- `0x18006bff8`: `CreatePolicyTask put_Hidden failed: 0x%x`
- `0x18006c01e`: `CreatePolicyTask put_Hidden failed: 0x%x`
- `0x18006c33c`: `CreatePolicyTask get_Settings failed: 0x%x`
- `0x18006c35a`: `CreatePolicyTask get_Settings failed: 0x%x`
- `0x18006c060`: `CreatePolicyTask put_StartWhenAvailable failed: 0x%x`
- `0x18006c086`: `CreatePolicyTask put_StartWhenAvailable failed: 0x%x`
- `0x18006c0c7`: `CreatePolicyTask put_DisallowStartIfOnBatteries failed: 0x%x`
- `0x18006c0ed`: `CreatePolicyTask put_DisallowStartIfOnBatteries failed: 0x%x`
- `0x18006c12e`: `CreatePolicyTask put_StopIfGoingOnBatteries failed: 0x%x`
- `0x18006c154`: `CreatePolicyTask put_StopIfGoingOnBatteries failed: 0x%x`
- `0x18006c195`: `CreatePolicyTask put_WakeToRun failed: 0x%x`
- `0x18006c1bb`: `CreatePolicyTask put_WakeToRun failed: 0x%x`
- `0x18006c22c`: `CreatePolicyTask put_ExecutionTimeLimit failed: 0x%x`
- `0x18006c24f`: `CreatePolicyTask put_ExecutionTimeLimit failed: 0x%x`
- `0x18006c293`: `CreatePolicyTask put_Priority failed: 0x%x`
- `0x18006c2c3`: `CreatePolicyTask put_Priority failed: 0x%x`
- `0x18006c303`: `CreatePolicyTask put_Compatibility failed: 0x%x`
- `0x18006c31e`: `CreatePolicyTask put_Compatibility failed: 0x%x`
- `0x18006c3c6`: `CreatePolicyTask get_IdleSettings failed: 0x%x`
- `0x18006c3eb`: `CreatePolicyTask get_IdleSettings failed: 0x%x`
- `0x18006c42e`: `CreatePolicyTask put_RestartOnIdle failed: 0x%x`
- `0x18006c453`: `CreatePolicyTask put_RestartOnIdle failed: 0x%x`
- `0x18006c55b`: `CreatePolicyTask TimeTrigger put_Id failed: 0x%x`
- `0x18006c58b`: `CreatePolicyTask TimeTrigger put_Id failed: 0x%x`
- `0x18006c661`: `CreatePolicyTask put_StartBoundary failed: 0x%x`
- `0x18006c687`: `CreatePolicyTask put_StartBoundary failed: 0x%x`
- `0x18006c712`: `CreatePolicyTask put_StopAtDurationEnd failed: 0x%x`
- `0x18006c72d`: `CreatePolicyTask put_StopAtDurationEnd failed: 0x%x`
- `0x18006c74b`: `CreatePolicyTask put_Interval failed: 0x%x`
- `0x18006c773`: `CreatePolicyTask put_Interval failed: 0x%x`
- `0x18006c7b4`: `CreatePolicyTask spTriggerCollection create time trigger failed: 0x%x`
- `0x18006c7dc`: `CreatePolicyTask spTriggerCollection create time trigger failed: 0x%x`
- `0x18006c8ed`: `CreatePolicyTask WNFTrigger: Failed to allocate memory`
- `0x18006c91a`: `CreatePolicyTask WNFTrigger: Failed to allocate memory`
- `0x18006c992`: `CreatePolicyTask WNFTrigger: Failed to SafeArrayPutElement with 0x%x`
- `0x18006c9b8`: `CreatePolicyTask WNFTrigger: Failed to SafeArrayPutElement with 0x%x`
- `0x18006ca5d`: `CreatePolicyTask WNFTrigger: Failed to SafeArrayPutElement with 0x%x`
- `0x18006ca80`: `CreatePolicyTask WNFTrigger: Failed to SafeArrayPutElement with 0x%x`
- `0x18006cb34`: `CreatePolicyTask put_StateName failed: 0x%x`
- `0x18006cb59`: `CreatePolicyTask put_StateName failed: 0x%x`
- `0x18006cb92`: `CreatePolicyTask WNFTrigger put_Enabled failed: 0x%x`
- `0x18006cbb5`: `CreatePolicyTask WNFTrigger put_Enabled failed: 0x%x`
- `0x18006cbd3`: `CreatePolicyTask WNF Trigger put_Id failed: 0x%x`
- `0x18006cbee`: `CreatePolicyTask WNF Trigger put_Id failed: 0x%x`
- `0x18006cc67`: `CreatePolicyTask spTriggerCollection create custom trigger failed: 0x%x`
- `0x18006cc8c`: `CreatePolicyTask spTriggerCollection create custom trigger failed: 0x%x`
- `0x18006ccbe`: `CreatePolicyTask get_Triggers failed: 0x%x`
- `0x18006cce3`: `CreatePolicyTask get_Triggers failed: 0x%x`
- `0x18006cea3`: `CreatePolicyTask put_Path failed: 0x%x`
- `0x18006cebe`: `CreatePolicyTask put_Path failed: 0x%x`
- `0x18006ce60`: `CreatePolicyTask put_Arguments failed: 0x%x`
- `0x18006ce85`: `CreatePolicyTask put_Arguments failed: 0x%x`
- `0x18006cef4`: `CreatePolicyTask spActionCollection create failed: 0x%x`
- `0x18006cf19`: `CreatePolicyTask spActionCollection create failed: 0x%x`
- `0x18006cf4c`: `CreatePolicyTask get_Actions failed: 0x%x`
- `0x18006cf71`: `CreatePolicyTask get_Actions failed: 0x%x`
- `0x18006d1b8`: `CreatePolicyTask RegisterTaskDefinition failed: 0x%x`
- `0x18006d1dd`: `CreatePolicyTask RegisterTaskDefinition failed: 0x%x`
- `0x18006d26e`: `CreatePolicyTask RegisterTaskDefinition Task already existed`
- `0x18006d293`: `CreatePolicyTask RegisterTaskDefinition Task already existed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreatePolicyTask(unsigned int a1, unsigned int a2)
{
  DWORD v4; // ebx
  __int64 v5; // rcx
  VARIANTARG *v6; // rax
  HRESULT v8; // edi
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v11; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v13; // xmm8
  IRecordInfo *v14; // xmm9_8
  __int128 v15; // xmm6
  IRecordInfo *v16; // xmm7_8
  LPVOID v17; // rbx
  __int64 (__fastcall *v18)(LPVOID, __int64, __int64 **); // rdi
  _bstr_t *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rbx
  __int64 (__fastcall *v22)(__int64 *, __int64, __int64 *); // rdi
  _bstr_t *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rdi
  __int64 v26; // r14
  OLECHAR ***v27; // rax
  OLECHAR *v28; // rbx
  UINT v29; // eax
  BSTR v30; // rax
  __int128 v31; // xmm6
  IRecordInfo *v32; // xmm7_8
  _bstr_t *v33; // rax
  __int64 v34; // rdx
  const wchar_t *v35; // rdx
  void (*v36)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v37; // rdx
  void (*v38)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v39; // rdx
  __int64 *v40; // rbx
  __int64 (__fastcall *v41)(__int64 *, __int64); // rdi
  _bstr_t *v42; // rax
  __int64 v43; // rdx
  void (*v44)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v45; // rdx
  __int64 v46; // rbx
  __int64 (__fastcall *v47)(__int64, __int64); // rdi
  _bstr_t *v48; // rax
  __int64 v49; // rdx
  int v50; // eax
  __int64 *v51; // rbx
  __int64 (__fastcall *v52)(__int64 *, __int64); // rdi
  _bstr_t *v53; // rax
  __int64 v54; // rdx
  int v55; // ebx
  void (*v56)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v57; // rdx
  const struct tm *v58; // rax
  __int64 v59; // rdx
  wchar_t *v60; // rcx
  __int64 *v61; // rbx
  __int64 (__fastcall *v62)(__int64 *, __int64); // rdi
  _bstr_t *v63; // rax
  __int64 v64; // rdx
  int v65; // eax
  __int64 v66; // rdx
  void (*v67)(unsigned int, const unsigned __int16 *, ...); // r9
  const wchar_t *v68; // rdx
  __int64 *v69; // rbx
  __int64 (__fastcall *v70)(__int64 *, __int64); // rdi
  _bstr_t *v71; // rax
  __int64 v72; // rdx
  SAFEARRAY *v73; // rbx
  __int64 v74; // rax
  void (*v75)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v76; // rdx
  SAFEARRAY *v77; // rbx
  __int64 v78; // rax
  void (*v79)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v80; // rdx
  void (*v81)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v82; // rdx
  __int64 *v83; // rbx
  __int64 (__fastcall *v84)(__int64 *, __int64); // rdi
  _bstr_t *v85; // rax
  __int64 v86; // rdx
  __int64 *v87; // rbx
  __int64 (__fastcall *v88)(__int64 *, __int64); // rdi
  _bstr_t *v89; // rax
  __int64 v90; // rdx
  __int64 v91; // rdx
  void (*v92)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v93; // rdx
  __int64 v94; // rbx
  __int64 (__fastcall *v95)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, VARIANTARG *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 **)); // r14
  _variant_t *v96; // rax
  __int128 v97; // xmm6
  IRecordInfo *v98; // xmm7_8
  __int128 v99; // xmm8
  IRecordInfo *v100; // xmm9_8
  _variant_t *v101; // rax
  __int128 v102; // xmm10
  IRecordInfo *v103; // xmm11_8
  __int64 v104; // rdi
  _bstr_t *v105; // rax
  __int64 v106; // rdx
  _variant_t *v107; // rax
  _bstr_t *v108; // rax
  __int64 *v109; // [rsp+58h] [rbp-B0h] BYREF
  __int64 rgIndices; // [rsp+60h] [rbp-A8h] BYREF
  SAFEARRAYBOUND v111; // [rsp+68h] [rbp-A0h] BYREF
  SAFEARRAYBOUND v112; // [rsp+70h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-90h] BYREF
  __int64 (__fastcall ***v114)(_QWORD, GUID *, __int64 **); // [rsp+80h] [rbp-88h] BYREF
  __int64 v115; // [rsp+88h] [rbp-80h] BYREF
  SAFEARRAY *v116; // [rsp+90h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp-70h] BYREF
  __int64 v118; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v119; // [rsp+A8h] [rbp-60h] BYREF
  __int64 *v120; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD *v121; // [rsp+B8h] [rbp-50h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v123; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v125; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v126; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v127; // [rsp+118h] [rbp+10h]
  __int128 v128; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v129; // [rsp+138h] [rbp+30h]
  VARIANTARG v130; // [rsp+148h] [rbp+40h] BYREF
  __int128 v131; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v132; // [rsp+178h] [rbp+70h]
  SAFEARRAY *v133; // [rsp+188h] [rbp+80h] BYREF
  __int64 v134; // [rsp+190h] [rbp+88h] BYREF
  VARIANTARG v135; // [rsp+198h] [rbp+90h] BYREF
  __time64_t Time; // [rsp+1B0h] [rbp+A8h] BYREF
  VARIANTARG v137; // [rsp+1B8h] [rbp+B0h] BYREF
  wchar_t Buffer[104]; // [rsp+1D8h] [rbp+D0h] BYREF

  ppv = 0;
  v118 = 0;
  v123 = 0;
  v120 = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CreatePolicyTask called : bMachine = %d, nInterval = %d", a1, a2);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CreatePolicyTask called : bMachine = %d, nInterval = %d", a1, a2);
    }
  }
  if ( g_hGPServiceInitialized )
  {
    v4 = WaitForSingleObject(g_hGPServiceInitialized, 0x3A98u);
    if ( v4 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CreatePolicyTask failed to wait gpservice initialized event with error = %d.", v4);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CreatePolicyTask failed to wait gpservice initialized event with error = %d.", v4);
        }
      }
      if ( (int)v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
LABEL_27:
      _bstr_t::_Free((_bstr_t *)&v120);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v123);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v118);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
      return v4;
    }
  }
  if ( a2 - 1 <= 0xAE5F )
  {
    v5 = 18;
    v6 = &v137;
    do
    {
      LOBYTE(v6->vt) = 0;
      v6 = (VARIANTARG *)((char *)v6 + 1);
      --v5;
    }
    while ( v5 );
    v4 = StringCchPrintfW(&v137.vt, 9u, L"PT%dM", a2);
    if ( (v4 & 0x80000000) != 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CreatePolicyTask: Could not created formatted interval 0x%x", v4);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CreatePolicyTask: Could not created formatted interval 0x%x", v4);
        }
      }
      goto LABEL_27;
    }
    _bstr_t::operator=(&v120, &v137);
    v8 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
    if ( v8 < 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CreatePolicyTask failed 0x%x", (unsigned int)v8);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CreatePolicyTask failed 0x%x", (unsigned int)v8);
        }
      }
      goto LABEL_432;
    }
    v9 = ppv;
    v10 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
    VariantInit(&pvarg);
    v11 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v130);
    v13 = *(_OWORD *)&v130.vt;
    v14 = v130.pRecInfo;
    VariantInit(&v135);
    v15 = *(_OWORD *)&v135.vt;
    v16 = v135.pRecInfo;
    VariantInit(&v137);
    v131 = v11;
    v132 = pRecInfo;
    v126 = v13;
    v127 = v14;
    v128 = v15;
    v129 = v16;
    v125 = v137;
    v8 = v10(v9, &v125, &v128, &v126, &v131);
    _variant_t::~_variant_t((_variant_t *)&v137);
    _variant_t::~_variant_t((_variant_t *)&v135);
    _variant_t::~_variant_t((_variant_t *)&v130);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( v8 < 0 )
      goto LABEL_432;
    v109 = 0;
    v17 = ppv;
    v18 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 **))(*(_QWORD *)ppv + 56LL);
    v19 = _bstr_t::_bstr_t((_bstr_t *)&v112, L"\\");
    if ( *(_QWORD *)v19 )
      v20 = **(_QWORD **)v19;
    else
      v20 = 0;
    v8 = v18(v17, v20, &v109);
    _bstr_t::_Free((_bstr_t *)&v112);
    if ( v8 >= 0 )
    {
      v21 = v109;
      v22 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v109 + 72);
      v23 = _bstr_t::_bstr_t((_bstr_t *)&rgsabound, L"Microsoft\\Windows\\GroupPolicy");
      if ( *(_QWORD *)v23 )
        v24 = **(_QWORD **)v23;
      else
        v24 = 0;
      v8 = v22(v21, v24, &v118);
      _bstr_t::_Free((_bstr_t *)&rgsabound);
      if ( v8 >= 0 )
        goto LABEL_78;
      if ( (unsigned int)(v8 + 2147024894) <= 1 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"CreatePolicyTask %s folder does not exist. Shall attempt to create the folder.",
              L"Microsoft\\Windows\\GroupPolicy");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"CreatePolicyTask %s folder does not exist. Shall attempt to create the folder.",
              L"Microsoft\\Windows\\GroupPolicy");
          }
        }
        v25 = v109;
        v26 = *v109;
        v27 = (OLECHAR ***)_bstr_t::_bstr_t((_bstr_t *)&v114, L"O:BAG:DAD:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)");
        if ( *v27 )
          v28 = **v27;
        else
          v28 = 0;
        v29 = SysStringByteLen(v28);
        v30 = SysAllocStringByteLen((LPCSTR)v28, v29);
        if ( !v30 )
          _com_issue_error(-2147024882);
        v137.vt = 8;
        v137.llVal = (LONGLONG)v30;
        v31 = *(_OWORD *)&v137.vt;
        v32 = v137.pRecInfo;
        v33 = _bstr_t::_bstr_t((_bstr_t *)&v121, L"Microsoft\\Windows\\GroupPolicy");
        if ( *(_QWORD *)v33 )
          v34 = **(_QWORD **)v33;
        else
          v34 = 0;
        *(_OWORD *)&v125.vt = v31;
        v125.pRecInfo = v32;
        v8 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *, __int64 *))(v26 + 88))(v25, v34, &v125, &v118);
        _bstr_t::_Free((_bstr_t *)&v121);
        _variant_t::~_variant_t((_variant_t *)&v137);
        _bstr_t::_Free((_bstr_t *)&v114);
        if ( v8 >= 0 || !*(_DWORD *)&g_dwDebugLevel )
        {
LABEL_78:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v109);
          if ( v8 >= 0 )
          {
            v134 = 0;
            v121 = 0;
            v115 = 0;
            v35 = L" /target:computer";
            if ( !a1 )
              v35 = L" /target:user";
            _bstr_t::operator=(&v121, v35);
            v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, 0, &v115);
            if ( v8 < 0 )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(2u, L"CreatePolicyTask failed: 0x%x", (unsigned int)v8);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(2u, L"CreatePolicyTask failed: 0x%x", (unsigned int)v8);
                }
              }
              goto LABEL_431;
            }
            v109 = 0;
            v8 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v115 + 56LL))(v115, &v109);
            if ( v8 < 0 )
            {
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_98;
              v36 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                v37 = L"CreatePolicyTask failed creating RegistrationInfo: 0x%x";
                goto LABEL_94;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                RedirectDebugMsg(2u, L"CreatePolicyTask failed creating RegistrationInfo: 0x%x", (unsigned int)v8);
            }
            else
            {
              bstrString = 0;
              v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)ppv + 104LL))(ppv, &bstrString);
              if ( v8 >= 0 )
              {
                v8 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(*v109 + 80))(v109, bstrString);
                SysFreeString(bstrString);
                goto LABEL_98;
              }
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v36 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v37 = L"CreatePolicyTask - put_Author failed: 0x%x";
LABEL_94:
                  v36(2u, v37, (unsigned int)v8);
                  goto LABEL_98;
                }
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(2u, L"CreatePolicyTask - put_Author failed: 0x%x", (unsigned int)v8);
              }
            }
LABEL_98:
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v109);
            if ( v8 < 0 )
              goto LABEL_431;
            v109 = 0;
            v8 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v115 + 120LL))(v115, &v109);
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v109 + 112))(v109, 5);
              if ( v8 >= 0 )
              {
                v40 = v109;
                v41 = *(__int64 (__fastcall **)(__int64 *, __int64))(*v109 + 96);
                v42 = _bstr_t::_bstr_t((_bstr_t *)&v112, L"S-1-5-20");
                if ( *(_QWORD *)v42 )
                  v43 = **(_QWORD **)v42;
                else
                  v43 = 0;
                v8 = v41(v40, v43);
                _bstr_t::_Free((_bstr_t *)&v112);
                if ( v8 >= 0 )
                {
                  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v109 + 144))(v109, 0);
                  if ( v8 < 0 && *(_DWORD *)&g_dwDebugLevel )
                  {
                    v38 = g_lpDebugMsg;
                    if ( g_lpDebugMsg )
                    {
                      v39 = L"CreatePolicyTask put_RunLevel failed: 0x%x";
                      goto LABEL_121;
                    }
                    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      RedirectDebugMsg(2u, L"CreatePolicyTask put_RunLevel failed: 0x%x", (unsigned int)v8);
                  }
                }
                else
                {
                  if ( !*(_DWORD *)&g_dwDebugLevel )
                    goto LABEL_125;
                  v38 = g_lpDebugMsg;
                  if ( g_lpDebugMsg )
                  {
                    v39 = L"CreatePolicyTask put_UserId failed: 0x%x";
                    goto LABEL_121;
                  }
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    RedirectDebugMsg(2u, L"CreatePolicyTask put_UserId failed: 0x%x", (unsigned int)v8);
                }
              }
              else
              {
                if ( !*(_DWORD *)&g_dwDebugLevel )
                  goto LABEL_125;
                v38 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v39 = L"CreatePolicyTask get_Principal failed: 0x%x";
LABEL_121:
                  v38(2u, v39, (unsigned int)v8);
                  goto LABEL_125;
                }
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(2u, L"CreatePolicyTask get_Principal failed: 0x%x", (unsigned int)v8);
              }
            }
LABEL_125:
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v109);
            if ( v8 < 0 )
              goto LABEL_431;
            rgIndices = 0;
            v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v115 + 88LL))(v115, &rgIndices);
            if ( v8 < 0 )
            {
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_193;
              v44 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                v45 = L"CreatePolicyTask get_Settings failed: 0x%x";
                goto LABEL_176;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                RedirectDebugMsg(2u, L"CreatePolicyTask get_Settings failed: 0x%x", (unsigned int)v8);
            }
            else
            {
              v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)rgIndices + 304LL))(rgIndices, 0);
              if ( v8 >= 0 )
              {
                v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)rgIndices + 176LL))(
                       rgIndices,
                       0xFFFFFFFFLL);
                if ( v8 >= 0 )
                {
                  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)rgIndices + 144LL))(rgIndices, 0);
                  if ( v8 >= 0 )
                  {
                    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)rgIndices + 128LL))(rgIndices, 0);
                    if ( v8 >= 0 )
                    {
                      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)rgIndices + 352LL))(rgIndices, 0);
                      if ( v8 >= 0 )
                      {
                        v46 = rgIndices;
                        v47 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)rgIndices + 224LL);
                        v48 = _bstr_t::_bstr_t((_bstr_t *)&v112, L"P3D");
                        if ( *(_QWORD *)v48 )
                          v49 = **(_QWORD **)v48;
                        else
                          v49 = 0;
                        v8 = v47(v46, v49);
                        _bstr_t::_Free((_bstr_t *)&v112);
                        if ( v8 >= 0 )
                        {
                          v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)rgIndices + 272LL))(
                                 rgIndices,
                                 6);
                          if ( v8 >= 0 )
                          {
                            v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)rgIndices + 288LL))(
                                   rgIndices,
                                   4);
                            if ( v8 < 0 && *(_DWORD *)&g_dwDebugLevel )
                            {
                              v44 = g_lpDebugMsg;
                              if ( g_lpDebugMsg )
                              {
                                v45 = L"CreatePolicyTask put_Compatibility failed: 0x%x";
                                goto LABEL_176;
                              }
                              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                                RedirectDebugMsg(
                                  2u,
                                  L"CreatePolicyTask put_Compatibility failed: 0x%x",
                                  (unsigned int)v8);
                            }
                          }
                          else if ( *(_DWORD *)&g_dwDebugLevel )
                          {
                            v44 = g_lpDebugMsg;
                            if ( g_lpDebugMsg )
                            {
                              v45 = L"CreatePolicyTask put_Priority failed: 0x%x";
                              goto LABEL_176;
                            }
                            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                              RedirectDebugMsg(2u, L"CreatePolicyTask put_Priority failed: 0x%x", (unsigned int)v8);
                          }
                        }
                        else if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          v44 = g_lpDebugMsg;
                          if ( g_lpDebugMsg )
                          {
                            v45 = L"CreatePolicyTask put_ExecutionTimeLimit failed: 0x%x";
                            goto LABEL_176;
                          }
                          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            RedirectDebugMsg(
                              2u,
                              L"CreatePolicyTask put_ExecutionTimeLimit failed: 0x%x",
                              (unsigned int)v8);
                        }
                      }
                      else if ( *(_DWORD *)&g_dwDebugLevel )
                      {
                        v44 = g_lpDebugMsg;
                        if ( g_lpDebugMsg )
                        {
                          v45 = L"CreatePolicyTask put_WakeToRun failed: 0x%x";
                          goto LABEL_176;
                        }
                        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          RedirectDebugMsg(2u, L"CreatePolicyTask put_WakeToRun failed: 0x%x", (unsigned int)v8);
                      }
                    }
                    else if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      v44 = g_lpDebugMsg;
                      if ( g_lpDebugMsg )
                      {
                        v45 = L"CreatePolicyTask put_StopIfGoingOnBatteries failed: 0x%x";
                        goto LABEL_176;
                      }
                      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        RedirectDebugMsg(
                          2u,
                          L"CreatePolicyTask put_StopIfGoingOnBatteries failed: 0x%x",
                          (unsigned int)v8);
                    }
                  }
                  else if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    v44 = g_lpDebugMsg;
                    if ( g_lpDebugMsg )
                    {
                      v45 = L"CreatePolicyTask put_DisallowStartIfOnBatteries failed: 0x%x";
                      goto LABEL_176;
                    }
                    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      RedirectDebugMsg(
                        2u,
                        L"CreatePolicyTask put_DisallowStartIfOnBatteries failed: 0x%x",
                        (unsigned int)v8);
                  }
                }
                else if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  v44 = g_lpDebugMsg;
                  if ( g_lpDebugMsg )
                  {
                    v45 = L"CreatePolicyTask put_StartWhenAvailable failed: 0x%x";
                    goto LABEL_176;
                  }
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    RedirectDebugMsg(2u, L"CreatePolicyTask put_StartWhenAvailable failed: 0x%x", (unsigned int)v8);
                }
              }
              else if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v44 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v45 = L"CreatePolicyTask put_Hidden failed: 0x%x";
LABEL_176:
                  v44(2u, v45, (unsigned int)v8);
                  goto LABEL_193;
                }
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(2u, L"CreatePolicyTask put_Hidden failed: 0x%x", (unsigned int)v8);
              }
            }
LABEL_193:
            v109 = 0;
            if ( v8 < 0
              || (v8 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)rgIndices + 312LL))(rgIndices, &v109),
                  v8 < 0) )
            {
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_210;
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"CreatePolicyTask get_IdleSettings failed: 0x%x", (unsigned int)v8);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"CreatePolicyTask get_IdleSettings failed: 0x%x", (unsigned int)v8);
              }
            }
            else
            {
              v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v109 + 96))(v109, 0);
            }
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v109 + 112))(v109, 0);
              if ( v8 < 0 )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(2u, L"CreatePolicyTask put_RestartOnIdle failed: 0x%x", (unsigned int)v8);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(2u, L"CreatePolicyTask put_RestartOnIdle failed: 0x%x", (unsigned int)v8);
                  }
                }
              }
            }
LABEL_210:
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v109);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&rgIndices);
            if ( v8 < 0 )
              goto LABEL_431;
            bstrString = 0;
            v114 = 0;
            v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v115 + 72LL))(v115, &bstrString);
            if ( v8 < 0 )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(2u, L"CreatePolicyTask get_Triggers failed: 0x%x", (unsigned int)v8);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(2u, L"CreatePolicyTask get_Triggers failed: 0x%x", (unsigned int)v8);
                }
              }
LABEL_350:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v114);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&bstrString);
              if ( v8 >= 0 )
              {
                v119 = 0;
                v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v115 + 136LL))(v115, &v119);
                if ( v8 < 0 )
                {
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(2u, L"CreatePolicyTask get_Actions failed: 0x%x", (unsigned int)v8);
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(2u, L"CreatePolicyTask get_Actions failed: 0x%x", (unsigned int)v8);
                    }
                  }
                  goto LABEL_393;
                }
                v114 = 0;
                v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v119 + 96LL))(v119, 0, &v114);
                if ( v8 < 0 )
                {
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(2u, L"CreatePolicyTask spActionCollection create failed: 0x%x", (unsigned int)v8);
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(2u, L"CreatePolicyTask spActionCollection create failed: 0x%x", (unsigned int)v8);
                    }
                  }
                  goto LABEL_386;
                }
                v109 = 0;
                v8 = (**v114)(v114, &IID_IExecAction, &v109);
                v83 = v109;
                if ( v109 )
                {
                  v84 = *(__int64 (__fastcall **)(__int64 *, __int64))(*v109 + 64);
                  v85 = _bstr_t::_bstr_t((_bstr_t *)&v116, L"Group Policy Background Processing");
                  if ( *(_QWORD *)v85 )
                    v86 = **(_QWORD **)v85;
                  else
                    v86 = 0;
                  v8 = v84(v83, v86);
                  _bstr_t::_Free((_bstr_t *)&v116);
                  if ( v8 < 0 )
                  {
                    if ( !*(_DWORD *)&g_dwDebugLevel )
                      goto LABEL_379;
                    v92 = g_lpDebugMsg;
                    if ( !g_lpDebugMsg )
                    {
                      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        RedirectDebugMsg(2u, L"CreatePolicyTask put_Path failed: 0x%x", (unsigned int)v8);
                      goto LABEL_379;
                    }
                    v93 = L"CreatePolicyTask put_Path failed: 0x%x";
                  }
                  else
                  {
                    v87 = v109;
                    v88 = *(__int64 (__fastcall **)(__int64 *, __int64))(*v109 + 88);
                    v89 = _bstr_t::_bstr_t((_bstr_t *)&v116, L"gpupdate.exe");
                    if ( *(_QWORD *)v89 )
                      v90 = **(_QWORD **)v89;
                    else
                      v90 = 0;
                    v8 = v88(v87, v90);
                    _bstr_t::_Free((_bstr_t *)&v116);
                    if ( v8 < 0 )
                      goto LABEL_379;
                    v91 = v121 ? *v121 : 0LL;
                    v8 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v109 + 104))(v109, v91);
                    if ( v8 >= 0 || !*(_DWORD *)&g_dwDebugLevel )
                      goto LABEL_379;
                    v92 = g_lpDebugMsg;
                    if ( !g_lpDebugMsg )
                    {
                      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        RedirectDebugMsg(2u, L"CreatePolicyTask put_Arguments failed: 0x%x", (unsigned int)v8);
                      goto LABEL_379;
                    }
                    v93 = L"CreatePolicyTask put_Arguments failed: 0x%x";
                  }
                  v92(2u, v93, (unsigned int)v8);
                }
LABEL_379:
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v109);
LABEL_386:
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v114);
LABEL_393:
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v119);
                if ( v8 >= 0 )
                {
                  v114 = 0;
                  v94 = v118;
                  v95 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, VARIANTARG *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 **)))(*(_QWORD *)v118 + 136LL);
                  v96 = _variant_t::_variant_t((_variant_t *)&v130, L"O:BAG:DAD:P(A;;GA;;;SY)");
                  if ( a1 )
                  {
                    v97 = *(_OWORD *)v96;
                    v98 = (IRecordInfo *)*((_QWORD *)v96 + 2);
                    VariantInit(&pvarg);
                    v99 = *(_OWORD *)&pvarg.vt;
                    v100 = pvarg.pRecInfo;
                    v101 = _variant_t::_variant_t((_variant_t *)&v131, L"S-1-5-20");
                    v102 = *(_OWORD *)v101;
                    v103 = (IRecordInfo *)*((_QWORD *)v101 + 2);
                    v104 = v115;
                    v105 = _bstr_t::_bstr_t((_bstr_t *)&v116, L"{3E0A038B-D834-4930-9981-E89C9BFF83AA}");
                    if ( *(_QWORD *)v105 )
                      v106 = **(_QWORD **)v105;
                    else
                      v106 = 0;
                  }
                  else
                  {
                    v97 = *(_OWORD *)v96;
                    v98 = (IRecordInfo *)*((_QWORD *)v96 + 2);
                    VariantInit(&pvarg);
                    v99 = *(_OWORD *)&pvarg.vt;
                    v100 = pvarg.pRecInfo;
                    v107 = _variant_t::_variant_t((_variant_t *)&v131, L"S-1-5-20");
                    v102 = *(_OWORD *)v107;
                    v103 = (IRecordInfo *)*((_QWORD *)v107 + 2);
                    v104 = v115;
                    v108 = _bstr_t::_bstr_t((_bstr_t *)&v116, L"{A7719E0F-10DB-4640-AD8C-490CC6AD5202}");
                    if ( *(_QWORD *)v108 )
                      v106 = **(_QWORD **)v108;
                    else
                      v106 = 0;
                  }
                  *(_OWORD *)&v125.vt = v97;
                  v125.pRecInfo = v98;
                  v128 = v99;
                  v129 = v100;
                  v126 = v102;
                  v127 = v103;
                  v8 = v95(v94, v106, v104, 6, &v126, &v128, 5, &v125, &v114);
                  _bstr_t::_Free((_bstr_t *)&v116);
                  _variant_t::~_variant_t((_variant_t *)&v131);
                  _variant_t::~_variant_t((_variant_t *)&pvarg);
                  _variant_t::~_variant_t((_variant_t *)&v130);
                  if ( v8 < 0 )
                  {
                    if ( v8 == -2147024713 )
                    {
                      if ( *(_DWORD *)&g_dwDebugLevel )
                      {
                        if ( g_lpDebugMsg )
                        {
                          g_lpDebugMsg(4u, L"CreatePolicyTask RegisterTaskDefinition Task already existed");
                        }
                        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        {
                          RedirectDebugMsg(4u, L"CreatePolicyTask RegisterTaskDefinition Task already existed");
                        }
                      }
                      v8 = 0;
                    }
                    else
                    {
                      bstrString = 0;
                      if ( *(_DWORD *)&g_dwDebugLevel )
                      {
                        if ( g_lpDebugMsg )
                        {
                          g_lpDebugMsg(2u, L"CreatePolicyTask RegisterTaskDefinition failed: 0x%x", (unsigned int)v8);
                        }
                        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        {
                          RedirectDebugMsg(
                            2u,
                            L"CreatePolicyTask RegisterTaskDefinition failed: 0x%x",
                            (unsigned int)v8);
                        }
                      }
                      if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v115 + 152LL))(v115, &bstrString) >= 0 )
                      {
                        if ( *(_DWORD *)&g_dwDebugLevel )
                        {
                          if ( g_lpDebugMsg )
                          {
                            g_lpDebugMsg(2u, bstrString);
                          }
                          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          {
                            RedirectDebugMsg(2u, bstrString);
                          }
                        }
                        SysFreeString(bstrString);
                      }
                    }
                  }
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v114);
                }
              }
LABEL_431:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v115);
              _bstr_t::_Free((_bstr_t *)&v121);
              _bstr_t::_Free((_bstr_t *)&v134);
              goto LABEL_432;
            }
            v50 = (*(__int64 (__fastcall **)(BSTR, __int64, _QWORD))(*(_QWORD *)bstrString + 80LL))(
                    bstrString,
                    1,
                    &v114);
            if ( v50 < 0 )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(
                    2u,
                    L"CreatePolicyTask spTriggerCollection create time trigger failed: 0x%x",
                    (unsigned int)v50);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(
                    2u,
                    L"CreatePolicyTask spTriggerCollection create time trigger failed: 0x%x",
                    (unsigned int)v50);
                }
              }
LABEL_264:
              v119 = 0;
              v8 = (*(__int64 (__fastcall **)(BSTR, __int64, __int64 *))(*(_QWORD *)bstrString + 80LL))(
                     bstrString,
                     12,
                     &v119);
              if ( v8 < 0 )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(
                      2u,
                      L"CreatePolicyTask spTriggerCollection create custom trigger failed: 0x%x",
                      (unsigned int)v8);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(
                      2u,
                      L"CreatePolicyTask spTriggerCollection create custom trigger failed: 0x%x",
                      (unsigned int)v8);
                  }
                }
                goto LABEL_343;
              }
              v109 = 0;
              v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v119)(
                     v119,
                     &IID_IWnfStateChangeTrigger,
                     &v109);
              v69 = v109;
              if ( v109 )
              {
                v70 = *(__int64 (__fastcall **)(__int64 *, __int64))(*v109 + 72);
                v71 = _bstr_t::_bstr_t((_bstr_t *)&v112, L"GP WNF Trigger");
                if ( *(_QWORD *)v71 )
                  v72 = **(_QWORD **)v71;
                else
                  v72 = 0;
                v8 = v70(v69, v72);
                _bstr_t::_Free((_bstr_t *)&v112);
                if ( v8 >= 0 )
                {
                  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v109 + 152))(v109, 0);
                  if ( v8 >= 0 )
                  {
                    rgsabound = (SAFEARRAYBOUND)8LL;
                    v73 = SafeArrayCreate(0x11u, 1u, &rgsabound);
                    v116 = v73;
                    if ( v73 )
                    {
                      Time = 0x418B0D3AA3BC0875LL;
                      LODWORD(rgIndices) = 0;
                      v74 = 0;
                      while ( (unsigned int)v74 < 8 )
                      {
                        v8 = SafeArrayPutElement(v73, (LONG *)&rgIndices, (char *)&Time + v74);
                        if ( v8 < 0 )
                        {
                          if ( !*(_DWORD *)&g_dwDebugLevel )
                            goto LABEL_316;
                          v75 = g_lpDebugMsg;
                          if ( g_lpDebugMsg )
                          {
                            v76 = L"CreatePolicyTask WNFTrigger: Failed to SafeArrayPutElement with 0x%x";
LABEL_312:
                            v75(2u, v76, (unsigned int)v8);
                            goto LABEL_316;
                          }
                          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                            RedirectDebugMsg(
                              2u,
                              L"CreatePolicyTask WNFTrigger: Failed to SafeArrayPutElement with 0x%x",
                              (unsigned int)v8);
                          goto LABEL_316;
                        }
                        v74 = (unsigned int)(rgIndices + 1);
                        LODWORD(rgIndices) = rgIndices + 1;
                      }
                      v8 = (*(__int64 (__fastcall **)(__int64 *, SAFEARRAY *))(*v109 + 184))(v109, v73);
                      if ( v8 < 0 )
                      {
                        if ( !*(_DWORD *)&g_dwDebugLevel )
                          goto LABEL_316;
                        v75 = g_lpDebugMsg;
                        if ( g_lpDebugMsg )
                        {
                          v76 = L"CreatePolicyTask put_StateName failed: 0x%x";
                          goto LABEL_312;
                        }
                        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                          RedirectDebugMsg(2u, L"CreatePolicyTask put_StateName failed: 0x%x", (unsigned int)v8);
                      }
                      else
                      {
                        v112 = (SAFEARRAYBOUND)1LL;
                        v77 = SafeArrayCreate(0x11u, 1u, &v112);
                        v133 = v77;
                        LOBYTE(v111.cElements) = 1;
                        LODWORD(rgIndices) = 0;
                        v78 = 0;
                        while ( !(_DWORD)v78 )
                        {
                          v8 = SafeArrayPutElement(v77, (LONG *)&rgIndices, (char *)&v111 + v78);
                          if ( v8 < 0 )
                          {
                            if ( !*(_DWORD *)&g_dwDebugLevel )
                              goto LABEL_308;
                            v79 = g_lpDebugMsg;
                            if ( g_lpDebugMsg )
                            {
                              v80 = L"CreatePolicyTask WNFTrigger: Failed to SafeArrayPutElement with 0x%x";
LABEL_304:
                              v79(2u, v80, (unsigned int)v8);
                              goto LABEL_308;
                            }
                            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                              RedirectDebugMsg(
                                2u,
                                L"CreatePolicyTask WNFTrigger: Failed to SafeArrayPutElement with 0x%x",
                                (unsigned int)v8);
                            goto LABEL_308;
                          }
                          v78 = (unsigned int)(rgIndices + 1);
                          LODWORD(rgIndices) = rgIndices + 1;
                        }
                        v8 = (*(__int64 (__fastcall **)(__int64 *, SAFEARRAY *))(*v109 + 200))(v109, v77);
                        if ( v8 < 0
                          || (v8 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v109 + 216))(v109, 28), v8 < 0) )
                        {
                          if ( *(_DWORD *)&g_dwDebugLevel )
                          {
                            v79 = g_lpDebugMsg;
                            if ( g_lpDebugMsg )
                            {
                              v80 = L"Cannot set WNF trigger data: %x";
                              goto LABEL_304;
                            }
                            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                              RedirectDebugMsg(2u, L"Cannot set WNF trigger data: %x", (unsigned int)v8);
                          }
                        }
LABEL_308:
                        XSafeArray::~XSafeArray((XSafeArray *)&v133);
                      }
                    }
                    else if ( *(_DWORD *)&g_dwDebugLevel )
                    {
                      if ( g_lpDebugMsg )
                      {
                        g_lpDebugMsg(2u, L"CreatePolicyTask WNFTrigger: Failed to allocate memory");
                      }
                      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      {
                        RedirectDebugMsg(2u, L"CreatePolicyTask WNFTrigger: Failed to allocate memory");
                      }
                    }
LABEL_316:
                    XSafeArray::~XSafeArray((XSafeArray *)&v116);
                    goto LABEL_336;
                  }
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    v81 = g_lpDebugMsg;
                    if ( !g_lpDebugMsg )
                    {
                      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                        RedirectDebugMsg(2u, L"CreatePolicyTask WNFTrigger put_Enabled failed: 0x%x", (unsigned int)v8);
                      goto LABEL_336;
                    }
                    v82 = L"CreatePolicyTask WNFTrigger put_Enabled failed: 0x%x";
                    goto LABEL_332;
                  }
LABEL_336:
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v109);
LABEL_343:
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v119);
                  goto LABEL_350;
                }
                if ( !*(_DWORD *)&g_dwDebugLevel )
                  goto LABEL_336;
                v81 = g_lpDebugMsg;
                if ( !g_lpDebugMsg )
                {
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    RedirectDebugMsg(2u, L"CreatePolicyTask WNF Trigger put_Id failed: 0x%x", (unsigned int)v8);
                  goto LABEL_336;
                }
                v82 = L"CreatePolicyTask WNF Trigger put_Id failed: 0x%x";
              }
              else
              {
                if ( !*(_DWORD *)&g_dwDebugLevel )
                  goto LABEL_336;
                v81 = g_lpDebugMsg;
                if ( !g_lpDebugMsg )
                {
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    RedirectDebugMsg(
                      2u,
                      L"QueryInterface call failed for IWNFStateChangeTrigger: 0x%x",
                      (unsigned int)v8);
                  goto LABEL_336;
                }
                v82 = L"QueryInterface call failed for IWNFStateChangeTrigger: 0x%x";
              }
LABEL_332:
              v81(2u, v82, (unsigned int)v8);
              goto LABEL_336;
            }
            v109 = 0;
            (**v114)(v114, &IID_ITimeTrigger, &v109);
            v51 = v109;
            if ( !v109 )
              goto LABEL_257;
            v52 = *(__int64 (__fastcall **)(__int64 *, __int64))(*v109 + 72);
            v53 = _bstr_t::_bstr_t((_bstr_t *)&v112, L"GP Periodic Timer Trigger");
            if ( *(_QWORD *)v53 )
              v54 = **(_QWORD **)v53;
            else
              v54 = 0;
            v55 = v52(v51, v54);
            _bstr_t::_Free((_bstr_t *)&v112);
            if ( v55 < 0 )
            {
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v56 = g_lpDebugMsg;
                if ( !g_lpDebugMsg )
                {
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    RedirectDebugMsg(2u, L"CreatePolicyTask TimeTrigger put_Id failed: 0x%x", (unsigned int)v55);
                  goto LABEL_257;
                }
                v57 = L"CreatePolicyTask TimeTrigger put_Id failed: 0x%x";
LABEL_221:
                v56(2u, v57, (unsigned int)v55);
              }
LABEL_257:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v109);
              goto LABEL_264;
            }
            Time = 0;
            _o__tzset();
            _time64(&Time);
            Time += (int)(60 * a2);
            v58 = (const struct tm *)_o__gmtime64(&Time);
            v59 = 200;
            v60 = Buffer;
            do
            {
              *(_BYTE *)v60 = 0;
              v60 = (wchar_t *)((char *)v60 + 1);
              --v59;
            }
            while ( v59 );
            wcsftime(Buffer, 0x64u, L"%Y-%m-%dT%H:%M:%SZ", v58);
            v61 = v109;
            v62 = *(__int64 (__fastcall **)(__int64 *, __int64))(*v109 + 120);
            v63 = _bstr_t::_bstr_t((_bstr_t *)&v112, Buffer);
            if ( *(_QWORD *)v63 )
              v64 = **(_QWORD **)v63;
            else
              v64 = 0;
            v55 = v62(v61, v64);
            _bstr_t::_Free((_bstr_t *)&v112);
            if ( v55 < 0 )
            {
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_257;
              v56 = g_lpDebugMsg;
              if ( !g_lpDebugMsg )
              {
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(2u, L"CreatePolicyTask put_StartBoundary failed: 0x%x", (unsigned int)v55);
                goto LABEL_257;
              }
              v57 = L"CreatePolicyTask put_StartBoundary failed: 0x%x";
              goto LABEL_221;
            }
            rgIndices = 0;
            v65 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v109 + 80))(v109, &rgIndices);
            if ( v65 < 0 )
            {
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_256;
              v67 = g_lpDebugMsg;
              if ( !g_lpDebugMsg )
              {
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(2u, L"CreatePolicyTask put_Interval failed: 0x%x", (unsigned int)v65);
                goto LABEL_256;
              }
              v68 = L"CreatePolicyTask put_Interval failed: 0x%x";
            }
            else
            {
              if ( v120 )
                v66 = *v120;
              else
                v66 = 0;
              v65 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)rgIndices + 64LL))(rgIndices, v66);
              if ( v65 >= 0 )
              {
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)rgIndices + 96LL))(rgIndices, 0);
LABEL_256:
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&rgIndices);
                goto LABEL_257;
              }
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_256;
              v67 = g_lpDebugMsg;
              if ( !g_lpDebugMsg )
              {
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(2u, L"CreatePolicyTask put_StopAtDurationEnd failed: 0x%x", (unsigned int)v65);
                goto LABEL_256;
              }
              v68 = L"CreatePolicyTask put_StopAtDurationEnd failed: 0x%x";
            }
            v67(2u, v68, (unsigned int)v65);
            goto LABEL_256;
          }
LABEL_432:
          _bstr_t::_Free((_bstr_t *)&v120);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v123);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v118);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
          return (unsigned int)v8;
        }
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            2u,
            L"CreatePolicyTask failed to create %s folder:0x%x ",
            L"Microsoft\\Windows\\GroupPolicy",
            (unsigned int)v8);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"CreatePolicyTask failed to create %s folder:0x%x ",
            L"Microsoft\\Windows\\GroupPolicy",
            (unsigned int)v8);
        }
      }
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_78;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(
          2u,
          L"CreatePolicyTask failed to get %s folder:0x%x ",
          L"Microsoft\\Windows\\GroupPolicy",
          (unsigned int)v8);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          2u,
          L"CreatePolicyTask failed to get %s folder:0x%x ",
          L"Microsoft\\Windows\\GroupPolicy",
          (unsigned int)v8);
      }
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CreatePolicyTask failed to get %s folder:0x%x ", L"\\", (unsigned int)v8);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CreatePolicyTask failed to get %s folder:0x%x ", L"\\", (unsigned int)v8);
      }
    }
    goto LABEL_78;
  }
  _bstr_t::_Free((_bstr_t *)&v120);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v123);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v118);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18006b620  mov     rax, rsp
0x18006b623  mov     [rax+18h], rbx
0x18006b627  push    rbp
0x18006b628  push    rsi
0x18006b629  push    rdi
0x18006b62a  push    r12
0x18006b62c  push    r13
0x18006b62e  push    r14
0x18006b630  push    r15
0x18006b632  lea     rbp, [rax-248h]
0x18006b639  sub     rsp, 310h
0x18006b640  movaps  xmmword ptr [rax-48h], xmm6
0x18006b644  movaps  xmmword ptr [rax-58h], xmm7
0x18006b648  movaps  xmmword ptr [rax-68h], xmm8
0x18006b64d  movaps  xmmword ptr [rax-78h], xmm9
0x18006b652  movaps  xmmword ptr [rax-88h], xmm10
0x18006b65a  movaps  xmmword ptr [rax-98h], xmm11
0x18006b662  mov     rax, cs:__security_cookie
0x18006b669  xor     rax, rsp
0x18006b66c  mov     [rbp+240h+var_A0], rax
0x18006b673  mov     r15d, edx
0x18006b676  mov     r12d, ecx
0x18006b679  xor     r13d, r13d
0x18006b67c  mov     [rbp+240h+var_2B0], r13
0x18006b680  mov     [rbp+240h+var_2A8], r13
0x18006b684  mov     [rbp+240h+var_280], r13
0x18006b688  mov     [rbp+240h+var_298], r13
0x18006b68c  lea     ecx, [r13+4]; unsigned int
0x18006b690  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006b697  jz      short loc_18006B6DD
0x18006b699  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006b6a0  test    rax, rax
0x18006b6a3  jz      short loc_18006B6B9
0x18006b6a5  mov     r9d, edx
0x18006b6a8  mov     r8d, r12d
0x18006b6ab  lea     rdx, aCreatepolicyta_3; "CreatePolicyTask called : bMachine = %d"...
0x18006b6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6b7  jmp     short loc_18006B6DD
0x18006b6b9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006b6c0  jz      short loc_18006B6DD
0x18006b6c2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006b6c9  jz      short loc_18006B6DD
0x18006b6cb  mov     r9d, r15d
0x18006b6ce  mov     r8d, r12d
0x18006b6d1  lea     rdx, aCreatepolicyta_3; "CreatePolicyTask called : bMachine = %d"...
0x18006b6d8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006b6dd  mov     rcx, cs:?g_hGPServiceInitialized@@3PEAXEA; hHandle
0x18006b6e4  test    rcx, rcx
0x18006b6e7  jz      short loc_18006B761
0x18006b6e9  mov     edx, 3A98h; dwMilliseconds
0x18006b6ee  call    cs:__imp_WaitForSingleObject
0x18006b6f4  mov     ebx, eax
0x18006b6f6  test    eax, eax
0x18006b6f8  jz      short loc_18006B761
0x18006b6fa  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006b701  jz      short loc_18006B74B
0x18006b703  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006b70a  test    rax, rax
0x18006b70d  jz      short loc_18006B725
0x18006b70f  mov     r8d, ebx
0x18006b712  lea     rdx, aCreatepolicyta_40; "CreatePolicyTask failed to wait gpservi"...
0x18006b719  mov     ecx, 2
0x18006b71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b723  jmp     short loc_18006B74B
0x18006b725  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006b72c  jz      short loc_18006B74B
0x18006b72e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006b735  jz      short loc_18006B74B
0x18006b737  mov     r8d, ebx
0x18006b73a  lea     rdx, aCreatepolicyta_40; "CreatePolicyTask failed to wait gpservi"...
0x18006b741  mov     ecx, 2; unsigned int
0x18006b746  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006b74b  test    ebx, ebx
0x18006b74d  jle     loc_18006B7FD
0x18006b753  movzx   ebx, bx
0x18006b756  or      ebx, 80070000h
0x18006b75c  jmp     loc_18006B7FD
0x18006b761  lea     eax, [r15-1]
0x18006b765  cmp     eax, 0AE5Fh
0x18006b76a  ja      loc_18006D34B
0x18006b770  mov     ecx, 12h
0x18006b775  lea     rax, [rbp+240h+var_190]
0x18006b77c  mov     [rax], r13b
0x18006b77f  inc     rax
0x18006b782  sub     rcx, 1
0x18006b786  jnz     short loc_18006B77C
0x18006b788  mov     r9d, r15d
0x18006b78b  lea     r8, aPtDm; "PT%dM"
0x18006b792  lea     edx, [rcx+9]; unsigned __int64
0x18006b795  lea     rcx, [rbp+240h+var_190]; unsigned __int16 *
0x18006b79c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006b7a1  mov     ebx, eax
0x18006b7a3  test    eax, eax
0x18006b7a5  jns     loc_18006B82B
0x18006b7ab  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006b7b2  jz      short loc_18006B7FD
0x18006b7b4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006b7bb  test    rax, rax
0x18006b7be  jz      short loc_18006B7D6
0x18006b7c0  mov     r8d, ebx
0x18006b7c3  lea     rdx, aCreatepolicyta_36; "CreatePolicyTask: Could not created for"...
0x18006b7ca  mov     ecx, 2
0x18006b7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7d4  jmp     short loc_18006B7FD
0x18006b7d6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006b7dd  jz      short loc_18006B7FD
0x18006b7df  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006b7e6  jz      short loc_18006B7FD
0x18006b7e8  mov     r8d, ebx
0x18006b7eb  lea     rdx, aCreatepolicyta_36; "CreatePolicyTask: Could not created for"...
0x18006b7f2  mov     ecx, 2; unsigned int
0x18006b7f7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006b7fc  nop
0x18006b7fd  lea     rcx, [rbp+240h+var_298]; this
0x18006b801  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006b806  nop
0x18006b807  lea     rcx, [rbp+240h+var_280]
0x18006b80b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006b810  nop
0x18006b811  lea     rcx, [rbp+240h+var_2A8]
0x18006b815  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006b81a  nop
0x18006b81b  lea     rcx, [rbp+240h+var_2B0]
0x18006b81f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006b824  mov     eax, ebx
0x18006b826  jmp     loc_18006D377
0x18006b82b  lea     rdx, [rbp+240h+var_190]
0x18006b832  lea     rcx, [rbp+240h+var_298]
0x18006b836  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18006b83b  lea     rax, [rbp+240h+var_2B0]
0x18006b83f  mov     [rsp+340h+ppv], rax; ppv
0x18006b844  lea     r9, IID_ITaskService; riid
0x18006b84b  xor     edx, edx; pUnkOuter
0x18006b84d  lea     r8d, [rdx+1]; dwClsContext
0x18006b851  lea     rcx, CLSID_TaskScheduler; rclsid
0x18006b858  call    cs:__imp_CoCreateInstance
0x18006b85e  mov     edi, eax
0x18006b860  test    eax, eax
0x18006b862  jns     short loc_18006B8C9
0x18006b864  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006b86b  jz      loc_18006D320
0x18006b871  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006b878  test    rax, rax
0x18006b87b  jz      short loc_18006B896
0x18006b87d  mov     r8d, edi
0x18006b880  lea     rdx, aCreatepolicyta_27; "CreatePolicyTask failed 0x%x"
0x18006b887  mov     ecx, 2
0x18006b88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b891  jmp     loc_18006D320
0x18006b896  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006b89d  jz      loc_18006D320
0x18006b8a3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006b8aa  jz      loc_18006D320
0x18006b8b0  mov     r8d, edi
0x18006b8b3  lea     rdx, aCreatepolicyta_27; "CreatePolicyTask failed 0x%x"
0x18006b8ba  mov     ecx, 2; unsigned int
0x18006b8bf  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006b8c4  jmp     loc_18006D320
0x18006b8c9  mov     rdi, [rbp+240h+var_2B0]
0x18006b8cd  mov     rax, [rdi]
0x18006b8d0  mov     rbx, [rax+50h]
0x18006b8d4  lea     rcx, [rbp+240h+pvarg]; pvarg
0x18006b8d8  call    cs:__imp_VariantInit
0x18006b8de  nop
0x18006b8df  movups  xmm10, xmmword ptr [rbp+240h+pvarg]
0x18006b8e4  movsd   xmm11, qword ptr [rbp+240h+pvarg+10h]
0x18006b8ea  lea     rcx, [rbp+240h+var_200]; pvarg
0x18006b8ee  call    cs:__imp_VariantInit
0x18006b8f4  nop
0x18006b8f5  movups  xmm8, xmmword ptr [rbp+240h+var_200]
0x18006b8fa  movsd   xmm9, qword ptr [rbp+240h+var_200+10h]
0x18006b900  lea     rcx, [rbp+240h+var_1B0]; pvarg
0x18006b907  call    cs:__imp_VariantInit
0x18006b90d  nop
0x18006b90e  movups  xmm6, xmmword ptr [rbp+240h+var_1B0]
0x18006b915  movsd   xmm7, qword ptr [rbp+240h+var_1B0+10h]
0x18006b91d  lea     rcx, [rbp+240h+var_190]; pvarg
0x18006b924  call    cs:__imp_VariantInit
0x18006b92a  nop
0x18006b92b  movups  xmm0, xmmword ptr [rbp+240h+var_190]
0x18006b932  movsd   xmm1, qword ptr [rbp+240h+var_190+10h]
0x18006b93a  movaps  [rbp+240h+var_1E0], xmm10
0x18006b93f  movsd   [rbp+240h+var_1D0], xmm11
0x18006b945  movaps  [rbp+240h+var_240], xmm8
0x18006b94a  movsd   [rbp+240h+var_230], xmm9
0x18006b950  movaps  [rbp+240h+var_220], xmm6
0x18006b954  movsd   [rbp+240h+var_210], xmm7
0x18006b959  movaps  [rbp+240h+var_260], xmm0
0x18006b95d  movsd   [rbp+240h+var_250], xmm1
0x18006b962  lea     rax, [rbp+240h+var_1E0]
0x18006b966  mov     [rsp+340h+ppv], rax
0x18006b96b  lea     r9, [rbp+240h+var_240]
0x18006b96f  lea     r8, [rbp+240h+var_220]
0x18006b973  lea     rdx, [rbp+240h+var_260]
0x18006b977  mov     rcx, rdi
0x18006b97a  mov     rax, rbx
0x18006b97d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b982  mov     edi, eax
0x18006b984  lea     rcx, [rbp+240h+var_190]; this
0x18006b98b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006b990  nop
0x18006b991  lea     rcx, [rbp+240h+var_1B0]; this
0x18006b998  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006b99d  nop
0x18006b99e  lea     rcx, [rbp+240h+var_200]; this
0x18006b9a2  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006b9a7  nop
0x18006b9a8  lea     rcx, [rbp+240h+pvarg]; this
0x18006b9ac  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006b9b1  test    edi, edi
0x18006b9b3  js      loc_18006D320
0x18006b9b9  mov     [rsp+340h+var_2F0], r13
0x18006b9be  mov     rbx, [rbp+240h+var_2B0]
0x18006b9c2  mov     rax, [rbx]
0x18006b9c5  mov     rdi, [rax+38h]
0x18006b9c9  lea     rdx, asc_1800C3A8C; "\\"
0x18006b9d0  lea     rcx, [rsp+340h+var_2D8]; this
0x18006b9d5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006b9da  nop
0x18006b9db  mov     rcx, [rax]
0x18006b9de  test    rcx, rcx
0x18006b9e1  jz      short loc_18006B9E8
0x18006b9e3  mov     rdx, [rcx]
0x18006b9e6  jmp     short loc_18006B9EB
0x18006b9e8  mov     rdx, r13
0x18006b9eb  lea     r8, [rsp+340h+var_2F0]
0x18006b9f0  mov     rcx, rbx
0x18006b9f3  mov     rax, rdi
0x18006b9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9fb  mov     edi, eax
0x18006b9fd  lea     rcx, [rsp+340h+var_2D8]; this
0x18006ba02  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006ba07  mov     esi, 2
0x18006ba0c  test    edi, edi
0x18006ba0e  js      loc_18006BC58
0x18006ba14  mov     rbx, [rsp+340h+var_2F0]
0x18006ba19  mov     rax, [rbx]
0x18006ba1c  mov     rdi, [rax+48h]
0x18006ba20  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\GroupPolicy"
0x18006ba27  lea     rcx, [rbp+240h+rgsabound]; this
0x18006ba2b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006ba30  nop
0x18006ba31  mov     rdx, [rax]
0x18006ba34  test    rdx, rdx
0x18006ba37  jz      short loc_18006BA3E
0x18006ba39  mov     rdx, [rdx]
0x18006ba3c  jmp     short loc_18006BA41
0x18006ba3e  mov     rdx, r13
0x18006ba41  lea     r8, [rbp+240h+var_2A8]
0x18006ba45  mov     rcx, rbx
0x18006ba48  mov     rax, rdi
0x18006ba4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba50  mov     edi, eax
0x18006ba52  lea     rcx, [rbp+240h+rgsabound]; this
0x18006ba56  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006ba5b  test    edi, edi
0x18006ba5d  jns     loc_18006BCB2
0x18006ba63  lea     eax, [rdi+7FF8FFFEh]
0x18006ba69  cmp     eax, 1
0x18006ba6c  ja      loc_18006BBFB
0x18006ba72  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006ba79  jz      short loc_18006BAC5
0x18006ba7b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006ba82  test    rax, rax
0x18006ba85  jz      short loc_18006BA9E
0x18006ba87  lea     r8, aMicrosoftWindo; "Microsoft\\Windows\\GroupPolicy"
0x18006ba8e  lea     rdx, aCreatepolicyta_22; "CreatePolicyTask %s folder does not exi"...
0x18006ba95  mov     ecx, esi
0x18006ba97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba9c  jmp     short loc_18006BAC5
0x18006ba9e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18006baa5  jz      short loc_18006BAC5
0x18006baa7  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006baae  jz      short loc_18006BAC5
0x18006bab0  lea     r8, aMicrosoftWindo; "Microsoft\\Windows\\GroupPolicy"
0x18006bab7  lea     rdx, aCreatepolicyta_22; "CreatePolicyTask %s folder does not exi"...
0x18006babe  mov     ecx, esi; unsigned int
0x18006bac0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006bac5  mov     rdi, [rsp+340h+var_2F0]
0x18006baca  mov     r14, [rdi]
0x18006bacd  lea     rdx, aOBagDadAOiciGa; "O:BAG:DAD:(A;OICI;GA;;;BA)(A;OICI;GA;;;"...
0x18006bad4  lea     rcx, [rsp+340h+var_2C8]; this
0x18006bad9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006bade  nop
0x18006badf  mov     rbx, [rax]
0x18006bae2  test    rbx, rbx
0x18006bae5  jz      short loc_18006BAEC
0x18006bae7  mov     rbx, [rbx]
0x18006baea  jmp     short loc_18006BAEF
0x18006baec  mov     rbx, r13
0x18006baef  mov     rcx, rbx; bstr
0x18006baf2  call    cs:__imp_SysStringByteLen
0x18006baf8  mov     edx, eax; len
0x18006bafa  mov     rcx, rbx; psz
0x18006bafd  call    cs:__imp_SysAllocStringByteLen
0x18006bb03  test    rax, rax
0x18006bb06  jnz     short loc_18006BB13
0x18006bb08  mov     ecx, 8007000Eh; int
0x18006bb0d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18006bb13  mov     ecx, 8
  ... truncated ...
```
