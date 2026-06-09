# ActivationHandler::CreateActivationTask(std::shared_ptr<WcmCommon::Xml::Node> const &)

- ea: `0x18000bfe0`
- end: `0x18000ce26`
- name: `?CreateActivationTask@ActivationHandler@@QEAAJAEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@Z`
- size: `3654`
- prototype: `HRESULT __fastcall(ActivationHandler *this, const std::shared_ptr<WcmCommon::Xml::Node> *ActivationNode)`
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d9d0`

## callees

- `0x180002790`
- `0x180008200`
- `0x180008234`
- `0x180008388`
- `0x18000af94`
- `0x18000b1e4`
- `0x18000b2f4`
- `0x18000bd94`
- `0x18000bdb4`
- `0x18000bfe0`
- `0x18000ce2c`
- `0x18000d024`
- `0x18000d060`
- `0x18000d3fc`
- `0x18000d708`
- `0x18000db7c`
- `0x18000fa6c`
- `0x180010c34`
- `0x180011844`
- `0x180011cfc`
- `0x180012618`
- `0x180012748`
- `0x180012770`
- `0x18001282c`
- `0x180020e70`
- `0x18002108c`
- `0x1800211e0`
- `0x18003bda0`
- `0x18003c040`
- `0x18003cbd0`
- `0x180048194`
- `0x180048558`
- `0x1800498dc`
- `0x180049d4c`
- `0x180049e4c`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000cb21`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cb21`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb52`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb52`
- `OLEAUT32!__imp_VariantInit` at `0x18000c18b`
- `OLEAUT32!__imp_VariantInit` at `0x18000ccca`
- `OLEAUT32!__imp_VariantInit` at `0x18000c18b`
- `OLEAUT32!__imp_VariantInit` at `0x18000ccca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c10f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c10f`

## string_xrefs

- `0x18000c31e`: `<?xml version="1.0" ?>\n<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">\n    <RegistrationInfo>\n        <Author>Microsoft</Author>\n        <Version>1.0.0</Version>\n    </RegistrationInfo>\n    <Triggers>\n    </Triggers>\n    <Settings>\n        <Enabled>true</Enabled>\n        <AllowStartOnDemand>true</AllowStartOnDemand>\n        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n        <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n       `
- `0x18000c353`: `http://schemas.microsoft.com/windows/2004/02/mit/task`
- `0x18000c5bf`: `http://schemas.microsoft.com/windows/2004/02/mit/task`
- `0x18000c7fe`: `http://schemas.microsoft.com/windows/2004/02/mit/task`
- `0x18000c3d3`: `//default:ComHandler/default:Data`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=83
__int64 __fastcall ActivationHandler::CreateActivationTask(
        ActivationHandler *this,
        const std::shared_ptr<WcmCommon::Xml::Node> *ActivationNode)
{
  __m128i si128; // xmm6
  HRESULT Instance; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v6; // rcx
  unsigned __int16 v7; // dx
  ITaskFolder *p; // rbx
  HRESULT (__fastcall *get_Name)(ITaskFolder *, wchar_t **); // rdi
  _QWORD **v10; // rax
  _QWORD *v11; // rdx
  WPP_PROJECT_CONTROL_BLOCK *v12; // rcx
  WcmCommon::Xml::Document *v13; // rbx
  WcmCommon::Xml::Document *v14; // rbx
  std::wstring *p_SubscriberId; // r14
  Handler::Parameters *p_m_params; // r15
  int TaskParameters; // eax
  WcmCommon::Xml::Document *v18; // rbx
  WPP_PROJECT_CONTROL_BLOCK *v19; // rcx
  __int64 v20; // rbx
  WcmCommon::Xml::Node *v21; // rbx
  const std::wstring *v22; // rax
  unsigned __int64 *v23; // rdx
  int v24; // r8d
  WcmCommon::Xml::Document *v25; // rbx
  std::wstring *v26; // rax
  std::wstring *v27; // rax
  __int64 v28; // rdi
  __int64 v29; // rsi
  const OLECHAR *v30; // rax
  OLECHAR *v31; // rbx
  BSTR v32; // rdx
  BSTR v33; // rax
  int v34; // edi
  WPP_PROJECT_CONTROL_BLOCK *v35; // r10
  const wchar_t *v36; // rax
  __int64 v37; // r10
  RegistryStore<1> *CarrierSubscriberTasksStore; // rax
  Registry::REGISTRY_ACCESS_PERMISSIONS v39; // r8d
  int v40; // eax
  _TASK_LOGON_TYPE ActivationData; // [rsp+28h] [rbp-E0h]
  AutoRevertImpersonate v43; // [rsp+38h] [rbp-D0h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> interval_8; // [rsp+48h] [rbp-C0h] OVERLAPPED BYREF
  wchar_t *v45; // [rsp+58h] [rbp-B0h]
  std::shared_ptr<Registry::Key> storeKey_8; // [rsp+68h] [rbp-A0h] OVERLAPPED BYREF
  wchar_t *Ptr; // [rsp+78h] [rbp-90h]
  std::wstring ValueName; // [rsp+88h] [rbp-80h] BYREF
  __m256i v49; // [rsp+A8h] [rbp-60h] OVERLAPPED BYREF
  std::shared_ptr<WcmCommon::Xml::Node> settings_8; // [rsp+D8h] [rbp-30h] OVERLAPPED BYREF
  std::wstring result; // [rsp+F8h] [rbp-10h] BYREF
  __m256i triggers_8; // [rsp+128h] [rbp+20h] OVERLAPPED BYREF
  wchar_t *v53; // [rsp+148h] [rbp+40h]
  std::wstring Name; // [rsp+158h] [rbp+50h] BYREF
  std::wstring Namespace; // [rsp+178h] [rbp+70h] BYREF
  std::wstring Path; // [rsp+198h] [rbp+90h] BYREF
  ATL::CComPtr<ITaskFolder> spRootFolder; // [rsp+1B8h] [rbp+B0h] BYREF
  tagVARIANT varEmpty; // [rsp+1C0h] [rbp+B8h] BYREF
  __m128i v59; // [rsp+1D8h] [rbp+D0h] OVERLAPPED
  _BYTE retryCount[216]; // [rsp+1E8h] [rbp+E0h] OVERLAPPED BYREF
  std::wstring taskPath; // [rsp+2C0h] [rbp+1B8h] BYREF

  settings_8._Ptr = 0;
  *(_OWORD *)&retryCount[8] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(__m128i *)&retryCount[24] = si128;
  *(_WORD *)&retryCount[8] = 0;
  *(_OWORD *)&retryCount[104] = 0;
  *(__m128i *)&retryCount[120] = si128;
  *(_WORD *)&retryCount[104] = 0;
  *(_OWORD *)&retryCount[72] = 0;
  *(__m128i *)&retryCount[88] = si128;
  *(_WORD *)&retryCount[72] = 0;
  *(_OWORD *)&retryCount[40] = 0;
  *(__m128i *)&retryCount[56] = si128;
  *(_WORD *)&retryCount[40] = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x19u, (const _GUID *)&Descriptor.MatchAnyKeyword);
  }
  ParseActivationParams(
    ActivationNode,
    (std::wstring *)&retryCount[8],
    (std::wstring *)&retryCount[72],
    (std::wstring *)&retryCount[104],
    (std::wstring *)&retryCount[40]);
  spRootFolder.p = 0;
  Instance = CoCreateInstance(
               &CLSID_TaskScheduler,
               0,
               0x17u,
               &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
               (LPVOID *)&spRootFolder.p);
  if ( Instance < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      v7 = 26;
LABEL_8:
      WPP_SF_d(v6->Control.Logger, v7, (const _GUID *)&Descriptor.MatchAnyKeyword, Instance);
      goto LABEL_118;
    }
    goto LABEL_118;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Bu, (const _GUID *)&Descriptor.MatchAnyKeyword);
  }
  *(_OWORD *)&retryCount[200] = 0;
  taskPath._Mypair._Myval2._Bx._Ptr = 0;
  VariantInit((VARIANTARG *)&retryCount[200]);
  *($098DB7A1025FD79723C31AABD315313E *)((char *)&varEmpty.0 + 8) = *($098DB7A1025FD79723C31AABD315313E *)&retryCount[200];
  v59.m128i_i64[0] = (__int64)taskPath._Mypair._Myval2._Bx._Ptr;
  storeKey_8 = *(std::shared_ptr<Registry::Key> *)&retryCount[200];
  Ptr = taskPath._Mypair._Myval2._Bx._Ptr;
  interval_8 = *(std::shared_ptr<WcmCommon::Xml::Node> *)&retryCount[200];
  v45 = taskPath._Mypair._Myval2._Bx._Ptr;
  *(_OWORD *)&triggers_8.m256i_u64[2] = *(_OWORD *)&retryCount[200];
  v53 = taskPath._Mypair._Myval2._Bx._Ptr;
  Instance = ((__int64 (__fastcall *)(ITaskFolder *, unsigned __int64 *, std::shared_ptr<WcmCommon::Xml::Node> *, std::shared_ptr<Registry::Key> *, __int16 *))spRootFolder.p->GetFolders)(
               spRootFolder.p,
               &triggers_8.m256i_u64[2],
               &interval_8,
               &storeKey_8,
               &varEmpty.boolVal);
  if ( Instance >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Du, (const _GUID *)&Descriptor.MatchAnyKeyword);
    }
    *(_QWORD *)&varEmpty.vt = 0;
    p = spRootFolder.p;
    get_Name = spRootFolder.p->get_Name;
    _bstr_t::_bstr_t((_bstr_t *)&v49.m256i_u64[2], L"\\");
    v11 = *v10;
    if ( *v10 )
      v11 = (_QWORD *)*v11;
    Instance = ((__int64 (__fastcall *)(ITaskFolder *, _QWORD *, tagVARIANT *))get_Name)(p, v11, &varEmpty);
    _bstr_t::_Free((_bstr_t *)&v49.m256i_u64[2]);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Eu, (const _GUID *)&Descriptor.MatchAnyKeyword, Instance);
      }
LABEL_117:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&varEmpty);
      goto LABEL_118;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Fu, (const _GUID *)&Descriptor.MatchAnyKeyword);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v12->ReserveSpace[28] & 0x10) != 0 )
        WPP_SF_(v12->Control.Logger, 0x20u, (const _GUID *)&Descriptor.MatchAnyKeyword);
    }
    *(_OWORD *)v49.m256i_i8 = 0;
    std::wstring::wstring(
      (std::wstring *)&retryCount[136],
      L"<?xml version=\"1.0\" ?>\n"
       "<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\">\n"
       "    <RegistrationInfo>\n"
       "        <Author>Microsoft</Author>\n"
       "        <Version>1.0.0</Version>\n"
       "    </RegistrationInfo>\n"
       "    <Triggers>\n"
       "    </Triggers>\n"
       "    <Settings>\n"
       "        <Enabled>true</Enabled>\n"
       "        <AllowStartOnDemand>true</AllowStartOnDemand>\n"
       "        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n"
       "        <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n"
       "        <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>\n"
       "    </Settings>\n"
       "    <Actions>\n"
       "        <ComHandler>\n"
       "            <ClassId>{217700E0-2004-11DF-ADB9-F4CE462D9137}</ClassId>\n"
       "            <Data></Data>\n"
       "        </ComHandler>\n"
       "    </Actions>\n"
       "</Task>\n");
    WcmCommon::Xml::Document::LoadFromString(
      (std::shared_ptr<WcmCommon::Xml::Document> *)&v49,
      (const std::wstring *)&retryCount[136]);
    std::wstring::_Tidy_deallocate((std::wstring *)&retryCount[136]);
    v13 = (WcmCommon::Xml::Document *)v49.m256i_i64[0];
    std::wstring::wstring((std::wstring *)&storeKey_8, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
    std::wstring::wstring((std::wstring *)&varEmpty.boolVal, L"default");
    WcmCommon::Xml::Document::AddSelectionNamespace(
      v13,
      (const std::wstring *)&varEmpty.boolVal,
      (const std::wstring *)&storeKey_8);
    std::wstring::_Tidy_deallocate((std::wstring *)&varEmpty.boolVal);
    std::wstring::_Tidy_deallocate((std::wstring *)&storeKey_8);
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x21u, (const _GUID *)&Descriptor.MatchAnyKeyword);
    }
    *(_OWORD *)&triggers_8.m256i_u64[2] = 0;
    v14 = (WcmCommon::Xml::Document *)v49.m256i_i64[0];
    std::wstring::wstring((std::wstring *)&varEmpty.boolVal, L"//default:ComHandler/default:Data");
    WcmCommon::Xml::Document::SelectSingle(
      v14,
      (std::shared_ptr<WcmCommon::Xml::Node> *)&triggers_8.m256i_u64[2],
      (const std::wstring *)&varEmpty.boolVal);
    std::wstring::_Tidy_deallocate((std::wstring *)&varEmpty.boolVal);
    *(_OWORD *)&retryCount[168] = 0;
    *(__m128i *)&retryCount[184] = si128;
    *(_WORD *)&retryCount[168] = 0;
    p_SubscriberId = &this->m_params.SubscriberId;
    p_m_params = &this->m_params;
    TaskParameters = anonymous_namespace_::CreateTaskParameters(
                       &this->m_params.CarrierId,
                       &this->m_params.SubscriberId,
                       &this->m_params.DeviceId,
                       (std::wstring *)&retryCount[168]);
    Instance = TaskParameters;
    if ( TaskParameters < 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x22u, (const _GUID *)&Descriptor.MatchAnyKeyword, TaskParameters);
      }
LABEL_113:
      std::wstring::_Tidy_deallocate((std::wstring *)&retryCount[168]);
      if ( triggers_8.m256i_i64[3] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)triggers_8.m256i_i64[3]);
      if ( v49.m256i_i64[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v49.m256i_i64[1]);
      goto LABEL_117;
    }
    WcmCommon::Xml::Node::SetText(
      (WcmCommon::Xml::Node *)triggers_8.m256i_i64[2],
      (const std::wstring *)&retryCount[168]);
    *(_OWORD *)triggers_8.m256i_i8 = 0;
    v18 = (WcmCommon::Xml::Document *)v49.m256i_i64[0];
    std::wstring::wstring(&Path, L"./default:Triggers");
    WcmCommon::Xml::Document::SelectSingle(v18, (std::shared_ptr<WcmCommon::Xml::Node> *)&triggers_8, &Path);
    std::wstring::_Tidy_deallocate(&Path);
    if ( !GetDelayInSeconds((const std::wstring *)&retryCount[104], (__int64 *)&settings_8) )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
      {
        goto LABEL_43;
      }
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x23u, (const _GUID *)&Descriptor.MatchAnyKeyword);
    }
    v19 = WPP_GLOBAL_Control;
LABEL_43:
    v20 = (__int64)settings_8._Ptr;
    if ( settings_8._Ptr )
    {
      *(_OWORD *)&retryCount[136] = 0;
      *(__m128i *)&retryCount[152] = si128;
      *(_WORD *)&retryCount[136] = 0;
      *($098DB7A1025FD79723C31AABD315313E *)((char *)&varEmpty.0 + 8) = 0;
      v59 = si128;
      varEmpty.iVal = 0;
      if ( v19 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v19->ReserveSpace[28] & 0x10) != 0 )
        WPP_SF_(v19->Control.Logger, 0x24u, (const _GUID *)&Descriptor.MatchAnyKeyword);
      CreateActivationTaskBoundaries(v20, (std::wstring *)&retryCount[136], (std::wstring *)&varEmpty.boolVal);
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x25u, (const _GUID *)&Descriptor.MatchAnyKeyword);
      }
      storeKey_8 = 0;
      interval_8 = 0;
      std::wstring::wstring((std::wstring *)&settings_8, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
      std::wstring::wstring((std::wstring *)&v49.m256i_u64[2], L"TimeTrigger");
      WcmCommon::Xml::Node::CreateChild(
        (WcmCommon::Xml::Node *)triggers_8.m256i_i64[0],
        (std::shared_ptr<WcmCommon::Xml::Node> *)&storeKey_8,
        (const std::wstring *)&v49.m256i_u64[2],
        (const std::wstring *)&settings_8,
        &interval_8);
      std::wstring::_Tidy_deallocate((std::wstring *)&v49.m256i_u64[2]);
      std::wstring::_Tidy_deallocate((std::wstring *)&settings_8);
      if ( interval_8._Rep )
        std::_Ref_count_base::_Decref(interval_8._Rep);
      settings_8 = 0;
      v21 = (WcmCommon::Xml::Node *)storeKey_8._Ptr;
      interval_8 = 0;
      std::wstring::wstring(&Namespace, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
      std::wstring::wstring(&Name, L"Enabled");
      WcmCommon::Xml::Node::CreateChild(v21, &settings_8, &Name, &Namespace, &interval_8);
      std::wstring::_Tidy_deallocate(&Name);
      std::wstring::_Tidy_deallocate(&Namespace);
      if ( interval_8._Rep )
        std::_Ref_count_base::_Decref(interval_8._Rep);
      std::wstring::wstring(&ValueName, L"true");
      WcmCommon::Xml::Node::SetText(settings_8._Ptr, v22);
      std::wstring::_Tidy_deallocate(&ValueName);
      *(_OWORD *)&v49.m256i_u64[2] = 0;
      std::wstring::wstring(&ValueName, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
      std::wstring::wstring(&result, L"EndBoundary");
      WcmCommon::Xml::Node::CreateChild(
        v21,
        (std::shared_ptr<WcmCommon::Xml::Node> *)&v49.m256i_u64[2],
        &result,
        &ValueName,
        &settings_8);
      std::wstring::_Tidy_deallocate(&result);
      std::wstring::_Tidy_deallocate(&ValueName);
      WcmCommon::Xml::Node::SetText((WcmCommon::Xml::Node *)v49.m256i_i64[2], (const std::wstring *)&varEmpty.boolVal);
      interval_8 = 0;
      std::wstring::wstring(&Name, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
      std::wstring::wstring(&Namespace, L"StartBoundary");
      WcmCommon::Xml::Node::CreateChild(
        v21,
        &interval_8,
        &Namespace,
        &Name,
        (const std::shared_ptr<WcmCommon::Xml::Node> *)&v49.m256i_u64[2]);
      std::wstring::_Tidy_deallocate(&Namespace);
      std::wstring::_Tidy_deallocate(&Name);
      WcmCommon::Xml::Node::SetText(interval_8._Ptr, (const std::wstring *)&retryCount[136]);
      if ( interval_8._Rep )
        std::_Ref_count_base::_Decref(interval_8._Rep);
      if ( v49.m256i_i64[3] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v49.m256i_i64[3]);
      if ( settings_8._Rep )
        std::_Ref_count_base::_Decref(settings_8._Rep);
      if ( storeKey_8._Rep )
        std::_Ref_count_base::_Decref(storeKey_8._Rep);
      std::wstring::_Tidy_deallocate((std::wstring *)&varEmpty.boolVal);
      std::wstring::_Tidy_deallocate((std::wstring *)&retryCount[136]);
    }
    else
    {
      interval_8 = 0;
      storeKey_8 = 0;
      std::wstring::wstring(&result, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
      std::wstring::wstring(&ValueName, L"RegistrationTrigger");
      WcmCommon::Xml::Node::CreateChild(
        (WcmCommon::Xml::Node *)triggers_8.m256i_i64[0],
        &interval_8,
        &ValueName,
        &result,
        (const std::shared_ptr<WcmCommon::Xml::Node> *)&storeKey_8);
      std::wstring::_Tidy_deallocate(&ValueName);
      std::wstring::_Tidy_deallocate(&result);
      if ( storeKey_8._Rep )
        std::_Ref_count_base::_Decref(storeKey_8._Rep);
      if ( interval_8._Rep )
        std::_Ref_count_base::_Decref(interval_8._Rep);
    }
    if ( std::stoul((const std::wstring *)&retryCount[8], v23, v24) )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x26u, (const _GUID *)&Descriptor.MatchAnyKeyword);
      }
      settings_8 = 0;
      v25 = (WcmCommon::Xml::Document *)v49.m256i_i64[0];
      std::wstring::wstring(&ValueName, L"./default:Settings");
      WcmCommon::Xml::Document::SelectSingle(v25, &settings_8, &ValueName);
      std::wstring::_Tidy_deallocate(&ValueName);
      *(_OWORD *)&v49.m256i_u64[2] = 0;
      storeKey_8 = 0;
      std::wstring::wstring(&result, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
      std::wstring::wstring(&ValueName, L"RestartOnFailure");
      WcmCommon::Xml::Node::CreateChild(
        settings_8._Ptr,
        (std::shared_ptr<WcmCommon::Xml::Node> *)&v49.m256i_u64[2],
        &ValueName,
        &result,
        (const std::shared_ptr<WcmCommon::Xml::Node> *)&storeKey_8);
      std::wstring::_Tidy_deallocate(&ValueName);
      std::wstring::_Tidy_deallocate(&result);
      if ( storeKey_8._Rep )
        std::_Ref_count_base::_Decref(storeKey_8._Rep);
      interval_8 = 0;
      storeKey_8 = 0;
      std::wstring::wstring(&result, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
      std::wstring::wstring(&ValueName, L"Interval");
      WcmCommon::Xml::Node::CreateChild(
        (WcmCommon::Xml::Node *)v49.m256i_i64[2],
        &interval_8,
        &ValueName,
        &result,
        (const std::shared_ptr<WcmCommon::Xml::Node> *)&storeKey_8);
      std::wstring::_Tidy_deallocate(&ValueName);
      std::wstring::_Tidy_deallocate(&result);
      if ( storeKey_8._Rep )
        std::_Ref_count_base::_Decref(storeKey_8._Rep);
      WcmCommon::Xml::Node::SetText(interval_8._Ptr, (const std::wstring *)&retryCount[72]);
      storeKey_8 = 0;
      *($098DB7A1025FD79723C31AABD315313E *)((char *)&varEmpty.0 + 8) = 0;
      std::wstring::wstring(&result, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
      std::wstring::wstring(&ValueName, L"Count");
      WcmCommon::Xml::Node::CreateChild(
        (WcmCommon::Xml::Node *)v49.m256i_i64[2],
        (std::shared_ptr<WcmCommon::Xml::Node> *)&storeKey_8,
        &ValueName,
        &result,
        (const std::shared_ptr<WcmCommon::Xml::Node> *)&varEmpty.boolVal);
      std::wstring::_Tidy_deallocate(&ValueName);
      std::wstring::_Tidy_deallocate(&result);
      if ( varEmpty.pRecInfo )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)varEmpty.pRecInfo);
      WcmCommon::Xml::Node::SetText((WcmCommon::Xml::Node *)storeKey_8._Ptr, (const std::wstring *)&retryCount[8]);
      if ( storeKey_8._Rep )
        std::_Ref_count_base::_Decref(storeKey_8._Rep);
      if ( interval_8._Rep )
        std::_Ref_count_base::_Decref(interval_8._Rep);
      if ( v49.m256i_i64[3] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v49.m256i_i64[3]);
      if ( settings_8._Rep )
        std::_Ref_count_base::_Decref(settings_8._Rep);
    }
    v26 = std::operator+<unsigned short>(&result, L"Microsoft\\Windows\\WCM\\Provisioning\\", &p_m_params->CarrierId);
    v27 = std::operator+<unsigned short>(&ValueName, v26, L"\\Activate");
    std::operator+<unsigned short>((std::wstring *)&taskPath._Mypair._Myval2._Bx._Alias[8], v27, p_SubscriberId);
    std::wstring::_Tidy_deallocate(&ValueName);
    std::wstring::_Tidy_deallocate(&result);
    *(_QWORD *)retryCount = 0;
    v28 = *(_QWORD *)&varEmpty.vt;
    v29 = **(_QWORD **)&varEmpty.vt;
    v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((std::_String_val<std::_Simple_types<unsigned short> > *)&taskPath._Mypair._Myval2._Bx._Alias[8]);
    if ( v30 )
    {
      v33 = SysAllocString(v30);
      v31 = v33;
      v49.m256i_i64[2] = (__int64)v33;
      if ( !v33 )
        ATL::AtlThrowImpl(-2147024882);
      v32 = v33;
    }
    else
    {
      v31 = 0;
      v49.m256i_i64[2] = 0;
      v32 = 0;
    }
    v34 = (*(__int64 (__fastcall **)(__int64, BSTR, _BYTE *))(v29 + 104))(v28, v32, retryCount);
    SysFreeString(v31);
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((std::_String_val<std::_Simple_types<unsigned short> > *)&taskPath._Mypair._Myval2._Bx._Alias[8]);
      WPP_SF_Sd(*(_QWORD *)(v37 + 16), 0x27u, (const _GUID *)&Descriptor.MatchAnyKeyword, v36, v34);
      v35 = WPP_GLOBAL_Control;
    }
    if ( v34 >= 0 )
    {
      CancelAnyRunningTaskInstances(*(IRegisteredTask **)retryCount);
      v35 = WPP_GLOBAL_Control;
    }
    if ( v35 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v35->ReserveSpace[28] & 0x10) != 0 )
      WPP_SF_(v35->Control.Logger, 0x28u, (const _GUID *)&Descriptor.MatchAnyKeyword);
    AutoRevertImpersonate::AutoRevertImpersonate(&v43);
    storeKey_8 = 0;
    CarrierSubscriberTasksStore = RegistryStore<1>::CreateCarrierSubscriberTasksStore(
                                    (RegistryStore<1> *)&result,
                                    &p_m_params->CarrierId,
                                    p_SubscriberId);
    Registry::CreateKeyRW(&storeKey_8, &CarrierSubscriberTasksStore->m_storePath, v39);
    Registry::Path::~Path((Registry::Path *)&result);
    std::wstring::wstring(&ValueName, L"ActivationParams");
    Instance = Registry::Key::SetSzValue(storeKey_8._Ptr, &ValueName, (const std::wstring *)&retryCount[40]);
    std::wstring::_Tidy_deallocate(&ValueName);
    if ( Instance < 0
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x29u, (const _GUID *)&Descriptor.MatchAnyKeyword, Instance);
    }
    if ( storeKey_8._Rep )
      std::_Ref_count_base::_Decref(storeKey_8._Rep);
    AutoRevertImpersonate::~AutoRevertImpersonate(&v43);
    VerifyUserIsImpersonating();
    if ( Instance >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x2Au, (const _GUID *)&Descriptor.MatchAnyKeyword);
      }
      *($098DB7A1025FD79723C31AABD315313E *)((char *)&varEmpty.0 + 8) = 0;
      v59.m128i_i64[0] = 0;
      VariantInit((VARIANTARG *)&varEmpty.boolVal);
      storeKey_8 = *(std::shared_ptr<Registry::Key> *)((char *)&varEmpty.0 + 8);
      Ptr = (wchar_t *)v59.m128i_i64[0];
      interval_8 = *(std::shared_ptr<WcmCommon::Xml::Node> *)((char *)&varEmpty.0 + 8);
      v45 = (wchar_t *)v59.m128i_i64[0];
      v40 = RegisterActivationTask(
              *(ITaskFolder **)&varEmpty.vt,
              (std::wstring *)&taskPath._Mypair._Myval2._Bx._Alias[8],
              (std::shared_ptr<WcmCommon::Xml::Document> *)&v49,
              (tagVARIANT *)&interval_8,
              ActivationData,
              (tagVARIANT *)&storeKey_8);
      Instance = v40;
      if ( v40 < 0
        && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x2Bu, (const _GUID *)&Descriptor.MatchAnyKeyword, v40);
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)retryCount);
    std::wstring::_Tidy_deallocate((std::wstring *)&taskPath._Mypair._Myval2._Bx._Alias[8]);
    if ( triggers_8.m256i_i64[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)triggers_8.m256i_i64[1]);
    goto LABEL_113;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
  {
    v7 = 28;
    goto LABEL_8;
  }
LABEL_118:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spRootFolder);
  std::wstring::_Tidy_deallocate((std::wstring *)&retryCount[40]);
  std::wstring::_Tidy_deallocate((std::wstring *)&retryCount[72]);
  std::wstring::_Tidy_deallocate((std::wstring *)&retryCount[104]);
  std::wstring::_Tidy_deallocate((std::wstring *)&retryCount[8]);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000bfe0  mov     rax, rsp
0x18000bfe3  mov     [rax+18h], rbx
0x18000bfe7  mov     [rax+20h], rsi
0x18000bfeb  push    rbp
0x18000bfec  push    rdi
0x18000bfed  push    r13
0x18000bfef  push    r14
0x18000bff1  push    r15
0x18000bff3  lea     rbp, [rax-228h]
0x18000bffa  sub     rsp, 300h
0x18000c001  movaps  xmmword ptr [rax-38h], xmm6
0x18000c005  mov     rax, cs:__security_cookie
0x18000c00c  xor     rax, rsp
0x18000c00f  mov     [rbp+220h+var_40], rax
0x18000c016  mov     rbx, ActivationNode
0x18000c019  mov     rsi, this
0x18000c01c  mov     [rbp+220h+settings._Rep], 0
0x18000c024  xorps   xmm0, xmm0
0x18000c027  movups  xmmword ptr [rbp+220h+retryCount._Mypair._Myval2._Bx+8], xmm0
0x18000c02e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000c036  movdqu  xmmword ptr [rbp+220h+retryCount._Mypair._Myval2._Myres], xmm6
0x18000c03e  xor     eax, eax
0x18000c040  mov     word ptr [rbp+220h+retryCount._Mypair._Myval2._Bx+8], ax
0x18000c047  movups  xmmword ptr [rbp+220h+delay._Mypair._Myval2._Bx+8], xmm0
0x18000c04e  movdqu  xmmword ptr [rbp+220h+delay._Mypair._Myval2._Myres], xmm6
0x18000c056  mov     word ptr [rbp+220h+delay._Mypair._Myval2._Bx+8], ax
0x18000c05d  movups  xmmword ptr [rbp+220h+retryInterval._Mypair._Myval2._Bx+8], xmm0
0x18000c064  movdqu  xmmword ptr [rbp+220h+retryInterval._Mypair._Myval2._Myres], xmm6
0x18000c06c  mov     word ptr [rbp+220h+retryInterval._Mypair._Myval2._Bx+8], ax
0x18000c073  movups  xmmword ptr [rbp+220h+activationData._Mypair._Myval2._Bx+8], xmm0
0x18000c07a  movdqu  xmmword ptr [rbp+220h+activationData._Mypair._Myval2._Myres], xmm6
0x18000c082  mov     word ptr [rbp+220h+activationData._Mypair._Myval2._Bx+8], ax
0x18000c089  lea     r14, WPP_GLOBAL_Control; __annotation("TMF:",
0x18000c090  mov     r15b, 10h
0x18000c093  lea     r13, Descriptor.MatchAnyKeyword
0x18000c09a  mov     this, cs:WPP_GLOBAL_Control
0x18000c0a1  cmp     this, r14
0x18000c0a4  jz      short loc_18000C0BB
0x18000c0a6  test    [this+1Ch], r15b
0x18000c0aa  jz      short loc_18000C0BB
0x18000c0ac  lea     edx, [rax+19h]; id
0x18000c0af  mov     r8, r13; TraceGuid
0x18000c0b2  mov     this, [this+10h]; Logger
0x18000c0b6  call    WPP_SF_
0x18000c0bb  lea     rax, [rbp+220h+activationData._Mypair._Myval2._Bx+8]
0x18000c0c2  mov     [rsp+320h+ActivationData], rax; ActivationData
0x18000c0c7  lea     r9, [rbp+220h+delay._Mypair._Myval2._Bx+8]; Delay
0x18000c0ce  lea     r8, [rbp+220h+retryInterval._Mypair._Myval2._Bx+8]; RetryInterval
0x18000c0d5  lea     ActivationNode, [rbp+220h+retryCount._Mypair._Myval2._Bx+8]; RetryCount
0x18000c0dc  mov     this, rbx; ActivationNode
0x18000c0df  call    ?ParseActivationParams@@YAXAEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@111@Z; ParseActivationParams(std::shared_ptr<WcmCommon::Xml::Node> const &,std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x18000c0e4  mov     [rbp+220h+spRootFolder.p], 0
0x18000c0ef  lea     rax, [rbp+220h+spRootFolder]
0x18000c0f6  mov     [rsp+320h+ActivationData], rax; ppv
0x18000c0fb  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18000c102  xor     edx, edx; pUnkOuter
0x18000c104  lea     r8d, [ActivationNode+17h]; dwClsContext
0x18000c108  lea     this, CLSID_TaskScheduler; rclsid
0x18000c10f  call    cs:__imp_CoCreateInstance
0x18000c115  mov     ebx, eax
0x18000c117  test    eax, eax
0x18000c119  jns     short loc_18000C14E
0x18000c11b  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000c122  cmp     this, r14
0x18000c125  jz      loc_18000CDA9
0x18000c12b  test    byte ptr [this+1Ch], 2
0x18000c12f  jz      loc_18000CDA9
0x18000c135  mov     edx, 1Ah; id
0x18000c13a  mov     r9d, ebx; _a1
0x18000c13d  mov     r8, r13; TraceGuid
0x18000c140  mov     this, [this+10h]; Logger
0x18000c144  call    WPP_SF_d
0x18000c149  jmp     loc_18000CDA9
0x18000c14e  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000c155  cmp     this, r14
0x18000c158  jz      short loc_18000C171
0x18000c15a  test    [this+1Ch], r15b
0x18000c15e  jz      short loc_18000C171
0x18000c160  mov     edx, 1Bh; id
0x18000c165  mov     r8, r13; TraceGuid
0x18000c168  mov     this, [this+10h]; Logger
0x18000c16c  call    WPP_SF_
0x18000c171  xorps   xmm0, xmm0
0x18000c174  xor     eax, eax
0x18000c176  movups  xmmword ptr [rbp+220h+vtEmpty.___u0+8], xmm0
0x18000c17d  mov     qword ptr [rbp+220h+taskPath._Mypair._Myval2._Bx], rax
0x18000c184  lea     this, [rbp+220h+vtEmpty.___u0+8]; pvarg
0x18000c18b  call    cs:__imp_VariantInit
0x18000c191  mov     this, [rbp+220h+spRootFolder.p]
0x18000c198  movups  xmm1, xmmword ptr [rbp+220h+vtEmpty.___u0+8]
0x18000c19f  movsd   xmm0, qword ptr [rbp+220h+taskPath._Mypair._Myval2._Bx]
0x18000c1a7  movaps  xmmword ptr [rbp+220h+varEmpty.___u0+8], xmm1
0x18000c1ae  movsd   [rbp+220h+var_150], xmm0
0x18000c1b6  movaps  xmmword ptr [rsp+320h+storeKey._Rep], xmm1
0x18000c1bb  movsd   [rsp+320h+var_2B0], xmm0
0x18000c1c1  movaps  xmmword ptr [rsp+320h+interval._Rep], xmm1
0x18000c1c6  movsd   [rsp+320h+var_2D0], xmm0
0x18000c1cc  movaps  xmmword ptr [rbp+220h+taskData._Rep], xmm1
0x18000c1d0  movsd   [rbp+220h+var_1E0], xmm0
0x18000c1d5  mov     rax, [this]
0x18000c1d8  lea     ActivationNode, [rbp+220h+varEmpty.___u0+8]
0x18000c1df  mov     [rsp+320h+ActivationData], ActivationNode
0x18000c1e4  lea     r9, [rsp+320h+storeKey._Rep]
0x18000c1e9  lea     r8, [rsp+320h+interval._Rep]
0x18000c1ee  lea     ActivationNode, [rbp+220h+taskData._Rep]
0x18000c1f2  mov     rax, [rax+50h]
0x18000c1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1fb  mov     ebx, eax
0x18000c1fd  test    eax, eax
0x18000c1ff  jns     short loc_18000C225
0x18000c201  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000c208  cmp     this, r14
0x18000c20b  jz      loc_18000CDA9
0x18000c211  test    byte ptr [this+1Ch], 2
0x18000c215  jz      loc_18000CDA9
0x18000c21b  mov     edx, 1Ch
0x18000c220  jmp     loc_18000C13A
0x18000c225  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000c22c  cmp     this, r14
0x18000c22f  jz      short loc_18000C248
0x18000c231  test    [this+1Ch], r15b
0x18000c235  jz      short loc_18000C248
0x18000c237  mov     edx, 1Dh; id
0x18000c23c  mov     r8, r13; TraceGuid
0x18000c23f  mov     this, [this+10h]; Logger
0x18000c243  call    WPP_SF_
0x18000c248  mov     qword ptr [rbp+220h+varEmpty.___u0], 0
0x18000c253  mov     rbx, [rbp+220h+spRootFolder.p]
0x18000c25a  mov     rax, [rbx]
0x18000c25d  mov     rdi, [rax+38h]
0x18000c261  lea     ActivationNode, s; "\\"
0x18000c268  lea     this, [rbp+220h+restart._Rep]; this
0x18000c26c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000c271  nop
0x18000c272  mov     ActivationNode, [rax]
0x18000c275  test    ActivationNode, ActivationNode
0x18000c278  jz      short loc_18000C27D
0x18000c27a  mov     ActivationNode, [ActivationNode]
0x18000c27d  lea     r8, [rbp+220h+varEmpty]
0x18000c284  mov     this, rbx
0x18000c287  mov     rax, rdi
0x18000c28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c28f  mov     ebx, eax
0x18000c291  lea     this, [rbp+220h+restart._Rep]; this
0x18000c295  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c29a  test    ebx, ebx
0x18000c29c  jns     short loc_18000C2D1
0x18000c29e  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000c2a5  cmp     this, r14
0x18000c2a8  jz      loc_18000CD9C
0x18000c2ae  test    byte ptr [this+1Ch], 2
0x18000c2b2  jz      loc_18000CD9C
0x18000c2b8  mov     edx, 1Eh; id
0x18000c2bd  mov     r9d, ebx; _a1
0x18000c2c0  mov     r8, r13; TraceGuid
0x18000c2c3  mov     this, [this+10h]; Logger
0x18000c2c7  call    WPP_SF_d
0x18000c2cc  jmp     loc_18000CD9C
0x18000c2d1  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000c2d8  cmp     this, r14
0x18000c2db  jz      short loc_18000C317
0x18000c2dd  test    [this+1Ch], r15b
0x18000c2e1  jz      short loc_18000C2FB
0x18000c2e3  mov     edx, 1Fh; id
0x18000c2e8  mov     r8, r13; TraceGuid
0x18000c2eb  mov     this, [this+10h]; Logger
0x18000c2ef  call    WPP_SF_
0x18000c2f4  mov     this, cs:WPP_GLOBAL_Control
0x18000c2fb  cmp     this, r14; __annotation("TMF:",
0x18000c2fe  jz      short loc_18000C317
0x18000c300  test    [this+1Ch], r15b
0x18000c304  jz      short loc_18000C317
0x18000c306  mov     edx, 20h ; ' '; id
0x18000c30b  mov     r8, r13; TraceGuid
0x18000c30e  mov     this, [this+10h]; Logger
0x18000c312  call    WPP_SF_
0x18000c317  xorps   xmm0, xmm0
0x18000c31a  movups  xmmword ptr [rbp-60h], xmm0
0x18000c31e  lea     ActivationNode, aXmlVersion10Ta_1; "<?xml version=\"1.0\" ?>\n<Task xmlns="...
0x18000c325  lea     this, [rbp+220h+startTime._Mypair._Myval2._Bx+8]; this
0x18000c32c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c331  nop
0x18000c332  lea     ActivationNode, [rbp+220h+startTime._Mypair._Myval2._Bx+8]; Xml
0x18000c339  lea     this, [rbp-60h]; result
0x18000c33d  call    ?LoadFromString@Document@Xml@WcmCommon@@SA?AV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::LoadFromString(std::wstring const &)
0x18000c342  nop
0x18000c343  lea     this, [rbp+220h+startTime._Mypair._Myval2._Bx+8]; this
0x18000c34a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c34f  mov     rbx, [rbp-60h]
0x18000c353  lea     ActivationNode, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18000c35a  lea     this, [rsp+320h+storeKey._Rep]; this
0x18000c35f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c364  nop
0x18000c365  lea     ActivationNode, aDefault; "default"
0x18000c36c  lea     this, [rbp+220h+varEmpty.___u0+8]; this
0x18000c373  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c378  nop
0x18000c379  lea     r8, [rsp+320h+storeKey._Rep]; ns
0x18000c37e  lea     ActivationNode, [rbp+220h+varEmpty.___u0+8]; key
0x18000c385  mov     this, rbx; this
0x18000c388  call    ?AddSelectionNamespace@Document@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WcmCommon::Xml::Document::AddSelectionNamespace(std::wstring const &,std::wstring const &)
0x18000c38d  nop
0x18000c38e  lea     this, [rbp+220h+varEmpty.___u0+8]; this
0x18000c395  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c39a  nop
0x18000c39b  lea     this, [rsp+320h+storeKey._Rep]; this
0x18000c3a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c3a5  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000c3ac  cmp     this, r14
0x18000c3af  jz      short loc_18000C3C8
0x18000c3b1  test    [this+1Ch], r15b
0x18000c3b5  jz      short loc_18000C3C8
0x18000c3b7  mov     edx, 21h ; '!'; id
0x18000c3bc  mov     r8, r13; TraceGuid
0x18000c3bf  mov     this, [this+10h]; Logger
0x18000c3c3  call    WPP_SF_
0x18000c3c8  xorps   xmm0, xmm0
0x18000c3cb  movups  xmmword ptr [rbp+220h+taskData._Rep], xmm0
0x18000c3cf  mov     rbx, [rbp-60h]
0x18000c3d3  lea     ActivationNode, aDefaultComhand; "//default:ComHandler/default:Data"
0x18000c3da  lea     this, [rbp+220h+varEmpty.___u0+8]; this
0x18000c3e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c3e6  nop
0x18000c3e7  lea     r8, [rbp+220h+varEmpty.___u0+8]; Path
0x18000c3ee  lea     ActivationNode, [rbp+220h+taskData._Rep]; result
0x18000c3f2  mov     this, rbx; this
0x18000c3f5  call    ?SelectSingle@Document@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::SelectSingle(std::wstring const &)
0x18000c3fa  nop
0x18000c3fb  lea     this, [rbp+220h+varEmpty.___u0+8]; this
0x18000c402  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c407  xorps   xmm0, xmm0
0x18000c40a  movups  xmmword ptr [rbp+220h+taskDataString._Mypair._Myval2._Bx+8], xmm0
0x18000c411  movdqu  xmmword ptr [rbp+220h+taskDataString._Mypair._Myval2._Myres], xmm6
0x18000c419  xor     eax, eax
0x18000c41b  mov     word ptr [rbp+220h+taskDataString._Mypair._Myval2._Bx+8], ax
0x18000c422  lea     r14, [rsi+28h]
0x18000c426  lea     r15, [rsi+8]
0x18000c42a  lea     r8, [rsi+48h]; Param3
0x18000c42e  lea     r9, [rbp+220h+taskDataString._Mypair._Myval2._Bx+8]; TaskBlob
0x18000c435  mov     ActivationNode, r14; Param2
0x18000c438  mov     this, r15; Param1
0x18000c43b  call    _anonymous_namespace___CreateTaskParameters
0x18000c440  mov     ebx, eax
0x18000c442  test    eax, eax
0x18000c444  jns     short loc_18000C480
0x18000c446  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000c44d  lea     rdi, WPP_GLOBAL_Control
0x18000c454  cmp     this, rdi
0x18000c457  jz      loc_18000CD71
0x18000c45d  test    byte ptr [this+1Ch], 2
0x18000c461  jz      loc_18000CD71
0x18000c467  mov     edx, 22h ; '"'; id
0x18000c46c  mov     r9d, eax; _a1
0x18000c46f  mov     r8, r13; TraceGuid
0x18000c472  mov     this, [this+10h]; Logger
0x18000c476  call    WPP_SF_d
0x18000c47b  jmp     loc_18000CD71
0x18000c480  lea     ActivationNode, [rbp+220h+taskDataString._Mypair._Myval2._Bx+8]; Text
0x18000c487  mov     this, [rbp+220h+taskData._Rep]; this
0x18000c48b  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x18000c490  xorps   xmm0, xmm0
0x18000c493  movups  xmmword ptr [rbp+220h+triggers._Rep], xmm0
0x18000c497  mov     rbx, [rbp-60h]
0x18000c49b  lea     ActivationNode, aDefaultTrigger; "./default:Triggers"
0x18000c4a2  lea     this, [rbp+220h+Path]; this
0x18000c4a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c4ae  nop
0x18000c4af  lea     r8, [rbp+220h+Path]; Path
0x18000c4b6  lea     ActivationNode, [rbp+220h+triggers._Rep]; result
0x18000c4ba  mov     this, rbx; this
0x18000c4bd  call    ?SelectSingle@Document@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::SelectSingle(std::wstring const &)
0x18000c4c2  nop
0x18000c4c3  lea     this, [rbp+220h+Path]; this
0x18000c4ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c4cf  lea     ActivationNode, [rbp+220h+settings._Rep]; delayInSeconds
0x18000c4d3  lea     this, [rbp+220h+delay._Mypair._Myval2._Bx+8]; delay
0x18000c4da  call    ?GetDelayInSeconds@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_J@Z; GetDelayInSeconds(std::wstring const &,__int64 &)
0x18000c4df  test    al, al
0x18000c4e1  jnz     short loc_18000C50F
0x18000c4e3  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000c4ea  lea     rdi, WPP_GLOBAL_Control
0x18000c4f1  cmp     this, rdi
0x18000c4f4  jz      short loc_18000C51D
0x18000c4f6  test    byte ptr [this+1Ch], 2
0x18000c4fa  jz      short loc_18000C51D
0x18000c4fc  mov     edx, 23h ; '#'; id
0x18000c501  mov     r8, r13; TraceGuid
0x18000c504  mov     this, [this+10h]; Logger
0x18000c508  call    WPP_SF_
0x18000c50d  jmp     short loc_18000C516
0x18000c50f  lea     rdi, WPP_GLOBAL_Control
0x18000c516  mov     this, cs:WPP_GLOBAL_Control
0x18000c51d  mov     rbx, [rbp+220h+settings._Rep]
0x18000c521  xorps   xmm0, xmm0
0x18000c524  test    rbx, rbx
0x18000c527  jz      loc_18000C7F0
0x18000c52d  movups  xmmword ptr [rbp+220h+startTime._Mypair._Myval2._Bx+8], xmm0
0x18000c534  movdqu  xmmword ptr [rbp+220h+startTime._Mypair._Myval2._Myres], xmm6
0x18000c53c  xor     eax, eax
0x18000c53e  mov     word ptr [rbp+220h+startTime._Mypair._Myval2._Bx+8], ax
  ... truncated ...
```
