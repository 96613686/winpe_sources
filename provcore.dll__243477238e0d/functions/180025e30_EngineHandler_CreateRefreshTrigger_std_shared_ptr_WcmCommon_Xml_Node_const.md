# EngineHandler::CreateRefreshTrigger(std::shared_ptr<WcmCommon::Xml::Node> const &)

- ea: `0x180025e30`
- end: `0x18002680b`
- name: `?CreateRefreshTrigger@EngineHandler@@AEAAJAEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@Z`
- size: `2523`
- prototype: `HRESULT __fastcall(EngineHandler *this, const std::shared_ptr<WcmCommon::Xml::Node> *RefreshParams)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180026c70`

## callees

- `0x180002790`
- `0x180008200`
- `0x180008234`
- `0x1800082fc`
- `0x180008388`
- `0x18000af94`
- `0x18000b1e4`
- `0x18000b2f4`
- `0x18000d024`
- `0x18000d060`
- `0x18000db7c`
- `0x18000fa6c`
- `0x180010c34`
- `0x180011844`
- `0x180011cfc`
- `0x180011fdc`
- `0x180012618`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x180020e70`
- `0x18002108c`
- `0x1800211e0`
- `0x180025c9c`
- `0x180025e30`
- `0x180026868`
- `0x180026a48`
- `0x18003bda0`
- `0x18003c040`
- `0x18003c704`
- `0x18003cbd0`
- `0x180048194`
- `0x180048558`
- `0x1800498dc`
- `0x180049d4c`
- `0x180049e4c`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180025fb4`
- `OLEAUT32!__imp_VariantInit` at `0x18002652a`
- `OLEAUT32!__imp_VariantInit` at `0x180025fb4`
- `OLEAUT32!__imp_VariantInit` at `0x18002652a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025f38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025f38`

## string_xrefs

- `0x18002615d`: `http://schemas.microsoft.com/windows/2004/02/mit/task`
- `0x180026312`: `http://schemas.microsoft.com/windows/2004/02/mit/task`
- `0x180026387`: `http://schemas.microsoft.com/windows/2004/02/mit/task`
- `0x1800261d3`: `//default:ComHandler/default:Data`
- `0x18002612f`: `<?xml version="1.0" ?>\n<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">\n    <RegistrationInfo>\n        <Author>Microsoft</Author>\n        <Version>1.0.0</Version>\n    </RegistrationInfo>\n    <Triggers>\n    </Triggers>\n    <Settings>\n        <Enabled>true</Enabled>\n        <AllowStartOnDemand>true</AllowStartOnDemand>\n        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n        <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n       `
- `0x18002663a`: `TaskParams`
- `0x1800266df`: `TaskParams`

## pseudocode

```c
// Hidden C++ exception states: #wind=50
__int64 __fastcall EngineHandler::CreateRefreshTrigger(
        EngineHandler *this,
        const std::shared_ptr<WcmCommon::Xml::Node> *RefreshParams)
{
  unsigned __int64 *v4; // rdx
  int v5; // r8d
  unsigned int v6; // edi
  HRESULT Instance; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v8; // rcx
  unsigned __int16 v9; // dx
  ITaskService *p; // rbx
  HRESULT (__fastcall *GetFolder)(ITaskService *, wchar_t *, ITaskFolder **); // rsi
  wchar_t **v12; // rax
  wchar_t *v13; // rdx
  WPP_PROJECT_CONTROL_BLOCK *v14; // rcx
  WcmCommon::Xml::Document *Ptr; // rbx
  WcmCommon::Xml::Document *v16; // rbx
  std::wstring *p_SubscriberId; // rsi
  Handler::Parameters *p_m_params; // r14
  WcmCommon::Xml::Document *v19; // rbx
  std::wstring *v20; // rax
  std::wstring *v21; // rbx
  std::wstring *v22; // rax
  std::wstring *v23; // rax
  std::_String_constructor_concat_tag v24; // dl
  std::wstring *v25; // rax
  std::wstring *v26; // rax
  int v27; // eax
  RegistryStore<1> *CarrierSubscriberTasksStore; // rax
  Registry::REGISTRY_ACCESS_PERMISSIONS v29; // r8d
  int SzValue; // ebx
  unsigned __int16 v31; // dx
  const wchar_t *v32; // rax
  __int64 v33; // r10
  const std::wstring *v34; // rax
  std::wstring *ppv; // [rsp+20h] [rbp-E0h]
  AutoRevertImpersonate revertImpersonate; // [rsp+30h] [rbp-D0h] BYREF
  std::shared_ptr<Registry::Key> storeKey; // [rsp+40h] [rbp-C0h] BYREF
  IRecordInfo *v39; // [rsp+50h] [rbp-B0h]
  std::shared_ptr<WcmCommon::Xml::Document> xmlDoc; // [rsp+60h] [rbp-A0h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> taskData; // [rsp+70h] [rbp-90h] BYREF
  std::shared_ptr<WcmCommon::Xml::Node> maintenanceSettings; // [rsp+80h] [rbp-80h] BYREF
  IRecordInfo *pRecInfo; // [rsp+90h] [rbp-70h]
  std::wstring Namespace; // [rsp+A0h] [rbp-60h] BYREF
  std::wstring result; // [rsp+C0h] [rbp-40h] BYREF
  std::wstring v46; // [rsp+E0h] [rbp-20h] BYREF
  std::wstring v47; // [rsp+100h] [rbp+0h] BYREF
  ATL::CComPtr<ITaskService> spTaskService; // [rsp+120h] [rbp+20h] BYREF
  std::wstring oldRefreshPayload; // [rsp+130h] [rbp+30h] BYREF
  ATL::CComPtr<ITaskFolder> spRootFolder; // [rsp+150h] [rbp+50h] BYREF
  std::wstring taskDeletionFlag; // [rsp+160h] [rbp+60h] BYREF
  std::wstring delayInDaysStr; // [rsp+180h] [rbp+80h] BYREF
  std::wstring refreshPayload; // [rsp+1A0h] [rbp+A0h] BYREF
  std::wstring delayInDaysStrComplete; // [rsp+1C0h] [rbp+C0h] BYREF
  std::wstring taskDataString; // [rsp+1F0h] [rbp+F0h] BYREF
  tagVARIANT vtEmpty; // [rsp+210h] [rbp+110h] BYREF
  tagVARIANT varEmpty; // [rsp+228h] [rbp+128h] BYREF
  std::wstring path; // [rsp+240h] [rbp+140h] BYREF

  memset(&delayInDaysStr, 0, 24);
  delayInDaysStr._Mypair._Myval2._Myres = 7;
  delayInDaysStr._Mypair._Myval2._Bx._Buf[0] = 0;
  refreshPayload._Mypair._Myval2._Bx = 0;
  *(__m128i *)&refreshPayload._Mypair._Myval2._Mysize = _mm_load_si128((const __m128i *)&_xmm);
  refreshPayload._Mypair._Myval2._Bx._Buf[0] = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xCu, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
  }
  ParseRefreshParams(RefreshParams, &delayInDaysStr, &refreshPayload);
  if ( delayInDaysStr._Mypair._Myval2._Mysize )
    v6 = std::stoul(&delayInDaysStr, v4, v5);
  else
    v6 = 0;
  spTaskService.p = 0;
  Instance = CoCreateInstance(
               &CLSID_TaskScheduler,
               0,
               0x17u,
               &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
               (LPVOID *)&spTaskService.p);
  if ( Instance >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xEu, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
    }
    memset(&vtEmpty, 0, sizeof(vtEmpty));
    VariantInit(&vtEmpty);
    oldRefreshPayload._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)vtEmpty.0;
    oldRefreshPayload._Mypair._Myval2._Mysize = (unsigned __int64)vtEmpty.pRecInfo;
    taskDeletionFlag._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)vtEmpty.0;
    taskDeletionFlag._Mypair._Myval2._Mysize = (unsigned __int64)vtEmpty.pRecInfo;
    maintenanceSettings = (std::shared_ptr<WcmCommon::Xml::Node>)vtEmpty.0;
    pRecInfo = vtEmpty.pRecInfo;
    storeKey = (std::shared_ptr<Registry::Key>)vtEmpty.0;
    v39 = vtEmpty.pRecInfo;
    ppv = &oldRefreshPayload;
    Instance = ((__int64 (__fastcall *)(ITaskService *, std::shared_ptr<Registry::Key> *, std::shared_ptr<WcmCommon::Xml::Node> *, std::wstring *))spTaskService.p->Connect)(
                 spTaskService.p,
                 &storeKey,
                 &maintenanceSettings,
                 &taskDeletionFlag);
    if ( Instance >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x10u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
      }
      spRootFolder.p = 0;
      p = spTaskService.p;
      GetFolder = spTaskService.p->GetFolder;
      _bstr_t::_bstr_t((_bstr_t *)&taskData, L"\\");
      v13 = *v12;
      if ( *v12 )
        v13 = *(wchar_t **)v13;
      Instance = GetFolder(p, v13, &spRootFolder.p);
      _bstr_t::_Free((_bstr_t *)&taskData);
      if ( Instance >= 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x12u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
            v14 = WPP_GLOBAL_Control;
          }
          if ( v14 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v14->ReserveSpace[28] & 0x10) != 0 )
            WPP_SF_(v14->Control.Logger, 0x13u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
        }
        xmlDoc = 0;
        std::wstring::wstring(
          &oldRefreshPayload,
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
           "        <RestartOnFailure>\n"
           "            <Interval>P1DT9H36M</Interval>\n"
           "            <Count>10</Count>\n"
           "        </RestartOnFailure>\n"
           "    </Settings>\n"
           "    <Actions>\n"
           "        <ComHandler>\n"
           "            <ClassId>{217700E0-2003-11DF-ADB9-F4CE462D9137}</ClassId>\n"
           "            <Data></Data>\n"
           "        </ComHandler>\n"
           "    </Actions>\n"
           "</Task>\n");
        WcmCommon::Xml::Document::LoadFromString(&xmlDoc, &oldRefreshPayload);
        std::wstring::_Tidy_deallocate(&oldRefreshPayload);
        Ptr = xmlDoc._Ptr;
        std::wstring::wstring(
          (std::wstring *)&maintenanceSettings,
          L"http://schemas.microsoft.com/windows/2004/02/mit/task");
        std::wstring::wstring(&taskDeletionFlag, L"default");
        WcmCommon::Xml::Document::AddSelectionNamespace(
          Ptr,
          &taskDeletionFlag,
          (const std::wstring *)&maintenanceSettings);
        std::wstring::_Tidy_deallocate(&taskDeletionFlag);
        std::wstring::_Tidy_deallocate((std::wstring *)&maintenanceSettings);
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x14u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
        }
        taskData = 0;
        v16 = xmlDoc._Ptr;
        std::wstring::wstring(&taskDeletionFlag, L"//default:ComHandler/default:Data");
        WcmCommon::Xml::Document::SelectSingle(v16, &taskData, &taskDeletionFlag);
        std::wstring::_Tidy_deallocate(&taskDeletionFlag);
        taskDataString._Mypair._Myval2._Bx = 0;
        *(__m128i *)&taskDataString._Mypair._Myval2._Mysize = _mm_load_si128((const __m128i *)&_xmm);
        taskDataString._Mypair._Myval2._Bx._Buf[0] = 0;
        oldRefreshPayload._Mypair._Myval2._Bx = 0;
        *(_OWORD *)&oldRefreshPayload._Mypair._Myval2._Mysize = *(_OWORD *)&taskDataString._Mypair._Myval2._Mysize;
        oldRefreshPayload._Mypair._Myval2._Bx._Buf[0] = 0;
        p_SubscriberId = &this->m_params.SubscriberId;
        p_m_params = &this->m_params;
        Instance = anonymous_namespace_::CreateTaskParameters(
                     &p_m_params->CarrierId,
                     p_SubscriberId,
                     &oldRefreshPayload,
                     &taskDataString);
        std::wstring::_Tidy_deallocate(&oldRefreshPayload);
        if ( Instance >= 0 )
        {
          WcmCommon::Xml::Node::SetText(taskData._Ptr, &taskDataString);
          if ( v6 )
          {
            if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x16u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
            }
            taskDeletionFlag._Mypair._Myval2._Bx = 0;
            v19 = xmlDoc._Ptr;
            std::wstring::wstring(&oldRefreshPayload, L"./default:Settings");
            WcmCommon::Xml::Document::SelectSingle(
              v19,
              (std::shared_ptr<WcmCommon::Xml::Node> *)&taskDeletionFlag,
              &oldRefreshPayload);
            std::wstring::_Tidy_deallocate(&oldRefreshPayload);
            maintenanceSettings = 0;
            storeKey = 0;
            std::wstring::wstring(&Namespace, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
            std::wstring::wstring(&oldRefreshPayload, L"MaintenanceSettings");
            WcmCommon::Xml::Node::CreateChild(
              (WcmCommon::Xml::Node *)taskDeletionFlag._Mypair._Myval2._Bx._Ptr,
              &maintenanceSettings,
              &oldRefreshPayload,
              &Namespace,
              (const std::shared_ptr<WcmCommon::Xml::Node> *)&storeKey);
            std::wstring::_Tidy_deallocate(&oldRefreshPayload);
            std::wstring::_Tidy_deallocate(&Namespace);
            if ( storeKey._Rep )
              std::_Ref_count_base::_Decref(storeKey._Rep);
            storeKey = 0;
            oldRefreshPayload._Mypair._Myval2._Bx = 0;
            std::wstring::wstring(&v47, L"http://schemas.microsoft.com/windows/2004/02/mit/task");
            std::wstring::wstring(&Namespace, L"Period");
            WcmCommon::Xml::Node::CreateChild(
              maintenanceSettings._Ptr,
              (std::shared_ptr<WcmCommon::Xml::Node> *)&storeKey,
              &Namespace,
              &v47,
              (const std::shared_ptr<WcmCommon::Xml::Node> *)&oldRefreshPayload);
            std::wstring::_Tidy_deallocate(&Namespace);
            std::wstring::_Tidy_deallocate(&v47);
            if ( *(_QWORD *)&oldRefreshPayload._Mypair._Myval2._Bx._Alias[8] )
              std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&oldRefreshPayload._Mypair._Myval2._Bx._Alias[8]);
            std::wstring::wstring(&v46, L"D");
            v21 = v20;
            std::wstring::wstring(&result, L"P");
            v23 = std::operator+<unsigned short>(&oldRefreshPayload, v22, &delayInDaysStr);
            std::wstring::wstring(&delayInDaysStrComplete, v24, v23, v21);
            std::wstring::_Tidy_deallocate(&oldRefreshPayload);
            std::wstring::_Tidy_deallocate(&result);
            std::wstring::_Tidy_deallocate(&v46);
            WcmCommon::Xml::Node::SetText((WcmCommon::Xml::Node *)storeKey._Ptr, &delayInDaysStrComplete);
            std::wstring::_Tidy_deallocate(&delayInDaysStrComplete);
            if ( storeKey._Rep )
              std::_Ref_count_base::_Decref(storeKey._Rep);
            if ( maintenanceSettings._Rep )
              std::_Ref_count_base::_Decref(maintenanceSettings._Rep);
            if ( *(_QWORD *)&taskDeletionFlag._Mypair._Myval2._Bx._Alias[8] )
              std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&taskDeletionFlag._Mypair._Myval2._Bx._Alias[8]);
          }
          v25 = std::operator+<unsigned short>(
                  &result,
                  L"Microsoft\\Windows\\WCM\\Provisioning\\",
                  &p_m_params->CarrierId);
          v26 = std::operator+<unsigned short>(&v46, v25, L"\\");
          std::operator+<unsigned short>(&path, v26, p_SubscriberId);
          std::wstring::_Tidy_deallocate(&v46);
          std::wstring::_Tidy_deallocate(&result);
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x17u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
          }
          memset(&varEmpty, 0, sizeof(varEmpty));
          VariantInit(&varEmpty);
          oldRefreshPayload._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)varEmpty.0;
          oldRefreshPayload._Mypair._Myval2._Mysize = (unsigned __int64)varEmpty.pRecInfo;
          taskDeletionFlag._Mypair._Myval2._Bx = (std::_String_val<std::_Simple_types<unsigned short> >::_Bxty)varEmpty.0;
          taskDeletionFlag._Mypair._Myval2._Mysize = (unsigned __int64)varEmpty.pRecInfo;
          v27 = RegisterActivationTask(
                  spRootFolder.p,
                  &path,
                  &xmlDoc,
                  (tagVARIANT *)&taskDeletionFlag,
                  (_TASK_LOGON_TYPE)ppv,
                  (tagVARIANT *)&oldRefreshPayload);
          Instance = v27;
          if ( v27 >= 0 )
          {
            if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids);
            }
            AutoRevertImpersonate::AutoRevertImpersonate(&revertImpersonate);
            storeKey = 0;
            CarrierSubscriberTasksStore = RegistryStore<1>::CreateCarrierSubscriberTasksStore(
                                            (RegistryStore<1> *)&delayInDaysStrComplete,
                                            &p_m_params->CarrierId,
                                            p_SubscriberId);
            Registry::CreateKeyRW(&storeKey, &CarrierSubscriberTasksStore->m_storePath, v29);
            Registry::Path::~Path((Registry::Path *)&delayInDaysStrComplete);
            std::wstring::wstring(&taskDeletionFlag, L"1");
            oldRefreshPayload._Mypair._Myval2._Bx = 0;
            *(__m128i *)&oldRefreshPayload._Mypair._Myval2._Mysize = _mm_load_si128((const __m128i *)&_xmm);
            oldRefreshPayload._Mypair._Myval2._Bx._Buf[0] = 0;
            std::wstring::wstring(&delayInDaysStrComplete, L"TaskParams");
            SzValue = Registry::Key::GetSzValue(storeKey._Ptr, &delayInDaysStrComplete, &oldRefreshPayload);
            std::wstring::_Tidy_deallocate(&delayInDaysStrComplete);
            if ( SzValue >= 0 )
            {
              GetTaskDeletionFlag(&oldRefreshPayload, &taskDeletionFlag);
              if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
              {
                v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&taskDeletionFlag._Mypair._Myval2);
                WPP_SF_S(*(_QWORD *)(v33 + 16), 0x1Au, WPP_1aa1d128b86532d91064602d584084ba_Traceguids, v32);
              }
            }
            v34 = std::operator+<unsigned short>(&delayInDaysStrComplete, v31, &taskDeletionFlag);
            std::wstring::append(&refreshPayload, v34);
            std::wstring::_Tidy_deallocate(&delayInDaysStrComplete);
            std::wstring::wstring(&delayInDaysStrComplete, L"TaskParams");
            Instance = Registry::Key::SetSzValue(storeKey._Ptr, &delayInDaysStrComplete, &refreshPayload);
            std::wstring::_Tidy_deallocate(&delayInDaysStrComplete);
            if ( Instance < 0
              && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->Control.Logger,
                0x1Bu,
                WPP_1aa1d128b86532d91064602d584084ba_Traceguids,
                Instance);
            }
            std::wstring::_Tidy_deallocate(&oldRefreshPayload);
            std::wstring::_Tidy_deallocate(&taskDeletionFlag);
            if ( storeKey._Rep )
              std::_Ref_count_base::_Decref(storeKey._Rep);
            AutoRevertImpersonate::~AutoRevertImpersonate(&revertImpersonate);
            VerifyUserIsImpersonating();
          }
          else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                 && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x18u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids, v27);
          }
          std::wstring::_Tidy_deallocate(&path);
        }
        else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
               && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x15u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids, Instance);
        }
        std::wstring::_Tidy_deallocate(&taskDataString);
        if ( taskData._Rep )
          std::_Ref_count_base::_Decref(taskData._Rep);
        if ( xmlDoc._Rep )
          std::_Ref_count_base::_Decref(xmlDoc._Rep);
      }
      else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
             && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x11u, WPP_1aa1d128b86532d91064602d584084ba_Traceguids, Instance);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spRootFolder);
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        v9 = 15;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      v9 = 13;
LABEL_11:
      WPP_SF_d(v8->Control.Logger, v9, WPP_1aa1d128b86532d91064602d584084ba_Traceguids, Instance);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spTaskService);
  std::wstring::_Tidy_deallocate(&refreshPayload);
  std::wstring::_Tidy_deallocate(&delayInDaysStr);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180025e30  mov     [rsp-8+arg_10], rbx
0x180025e35  mov     [rsp-8+arg_18], rsi
0x180025e3a  push    rbp
0x180025e3b  push    rdi
0x180025e3c  push    r12
0x180025e3e  push    r13
0x180025e40  push    r14
0x180025e42  lea     rbp, [rsp-170h]
0x180025e4a  sub     rsp, 270h
0x180025e51  mov     rax, cs:__security_cookie
0x180025e58  xor     rax, rsp
0x180025e5b  mov     [rbp+190h+var_30], rax
0x180025e62  mov     rbx, RefreshParams
0x180025e65  mov     r14, this
0x180025e68  xorps   xmm0, xmm0
0x180025e6b  movups  xmmword ptr [rbp+190h+delayInDaysStr._Mypair._Myval2._Bx], xmm0
0x180025e72  mov     [rbp+190h+delayInDaysStr._Mypair._Myval2._Mysize], 0
0x180025e7d  mov     [rbp+190h+delayInDaysStr._Mypair._Myval2._Myres], 7
0x180025e88  xor     eax, eax
0x180025e8a  mov     word ptr [rbp+190h+delayInDaysStr._Mypair._Myval2._Bx], ax
0x180025e91  movups  xmmword ptr [rbp+190h+refreshPayload._Mypair._Myval2._Bx], xmm0
0x180025e98  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180025ea0  movdqu  xmmword ptr [rbp+190h+refreshPayload._Mypair._Myval2._Mysize], xmm1
0x180025ea8  mov     word ptr [rbp+190h+refreshPayload._Mypair._Myval2._Bx], ax
0x180025eaf  lea     r13, WPP_GLOBAL_Control; __annotation("TMF:",
0x180025eb6  lea     esi, [rax+10h]
0x180025eb9  lea     r12, WPP_1aa1d128b86532d91064602d584084ba_Traceguids
0x180025ec0  mov     this, cs:WPP_GLOBAL_Control
0x180025ec7  cmp     this, r13
0x180025eca  jz      short loc_180025EE1
0x180025ecc  test    [this+1Ch], sil
0x180025ed0  jz      short loc_180025EE1
0x180025ed2  lea     edx, [rax+0Ch]; id
0x180025ed5  mov     r8, r12; TraceGuid
0x180025ed8  mov     this, [this+10h]; Logger
0x180025edc  call    WPP_SF_
0x180025ee1  lea     r8, [rbp+190h+refreshPayload]; RefreshPayload
0x180025ee8  lea     RefreshParams, [rbp+190h+delayInDaysStr]; DelayInDays
0x180025eef  mov     this, rbx; RefreshParams
0x180025ef2  call    ?ParseRefreshParams@@YAXAEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@1@Z; ParseRefreshParams(std::shared_ptr<WcmCommon::Xml::Node> const &,std::wstring &,std::wstring &)
0x180025ef7  cmp     [rbp+190h+delayInDaysStr._Mypair._Myval2._Mysize], 0
0x180025eff  jnz     short loc_180025F05
0x180025f01  xor     edi, edi
0x180025f03  jmp     short loc_180025F13
0x180025f05  lea     this, [rbp+190h+delayInDaysStr]; _Str
0x180025f0c  call    ?stoul@std@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoul(std::wstring const &,unsigned __int64 *,int)
0x180025f11  mov     edi, eax
0x180025f13  mov     [rbp+190h+spTaskService.p], 0
0x180025f1b  lea     rax, [rbp+190h+spTaskService]
0x180025f1f  mov     [rsp+290h+ppv], rax; ppv
0x180025f24  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180025f2b  xor     edx, edx; pUnkOuter
0x180025f2d  lea     r8d, [RefreshParams+17h]; dwClsContext
0x180025f31  lea     this, CLSID_TaskScheduler; rclsid
0x180025f38  call    cs:__imp_CoCreateInstance
0x180025f3e  mov     ebx, eax
0x180025f40  test    eax, eax
0x180025f42  jns     short loc_180025F77
0x180025f44  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180025f4b  cmp     this, r13
0x180025f4e  jz      loc_1800267BB
0x180025f54  test    byte ptr [this+1Ch], 2
0x180025f58  jz      loc_1800267BB
0x180025f5e  mov     edx, 0Dh; id
0x180025f63  mov     r9d, ebx; _a1
0x180025f66  mov     r8, r12; TraceGuid
0x180025f69  mov     this, [this+10h]; Logger
0x180025f6d  call    WPP_SF_d
0x180025f72  jmp     loc_1800267BB
0x180025f77  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180025f7e  cmp     this, r13
0x180025f81  jz      short loc_180025F9A
0x180025f83  test    [this+1Ch], sil
0x180025f87  jz      short loc_180025F9A
0x180025f89  mov     edx, 0Eh; id
0x180025f8e  mov     r8, r12; TraceGuid
0x180025f91  mov     this, [this+10h]; Logger
0x180025f95  call    WPP_SF_
0x180025f9a  xorps   xmm0, xmm0
0x180025f9d  xor     eax, eax
0x180025f9f  movups  xmmword ptr [rbp+190h+vtEmpty.___u0], xmm0
0x180025fa6  mov     [rbp+190h+vtEmpty.pRecInfo], rax
0x180025fad  lea     this, [rbp+190h+vtEmpty]; pvarg
0x180025fb4  call    cs:__imp_VariantInit
0x180025fba  mov     this, [rbp+190h+spTaskService.p]
0x180025fbe  movups  xmm1, xmmword ptr [rbp+190h+vtEmpty.___u0]
0x180025fc5  movsd   xmm0, [rbp+190h+vtEmpty.pRecInfo]
0x180025fcd  movaps  xmmword ptr [rbp+190h+oldRefreshPayload._Mypair._Myval2._Bx], xmm1
0x180025fd1  movsd   [rbp+190h+oldRefreshPayload._Mypair._Myval2._Mysize], xmm0
0x180025fd6  movaps  xmmword ptr [rbp+190h+taskDeletionFlag._Mypair._Myval2._Bx], xmm1
0x180025fda  movsd   [rbp+190h+taskDeletionFlag._Mypair._Myval2._Mysize], xmm0
0x180025fdf  movaps  xmmword ptr [rbp+190h+maintenanceSettings._Ptr], xmm1
0x180025fe3  movsd   [rbp+190h+var_200], xmm0
0x180025fe8  movaps  xmmword ptr [rsp+290h+storeKey._Ptr], xmm1
0x180025fed  movsd   [rsp+290h+var_240], xmm0
0x180025ff3  mov     rax, [this]
0x180025ff6  lea     RefreshParams, [rbp+190h+oldRefreshPayload]
0x180025ffa  mov     [rsp+290h+ppv], RefreshParams
0x180025fff  lea     r9, [rbp+190h+taskDeletionFlag]
0x180026003  lea     r8, [rbp+190h+maintenanceSettings]
0x180026007  lea     RefreshParams, [rsp+290h+storeKey]
0x18002600c  mov     rax, [rax+50h]
0x180026010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026015  mov     ebx, eax
0x180026017  test    eax, eax
0x180026019  jns     short loc_18002603F
0x18002601b  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026022  cmp     this, r13
0x180026025  jz      loc_1800267BB
0x18002602b  test    byte ptr [this+1Ch], 2
0x18002602f  jz      loc_1800267BB
0x180026035  mov     edx, 0Fh
0x18002603a  jmp     loc_180025F63
0x18002603f  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026046  cmp     this, r13
0x180026049  jz      short loc_18002605F
0x18002604b  test    [this+1Ch], sil
0x18002604f  jz      short loc_18002605F
0x180026051  mov     edx, esi; id
0x180026053  mov     r8, r12; TraceGuid
0x180026056  mov     this, [this+10h]; Logger
0x18002605a  call    WPP_SF_
0x18002605f  mov     [rbp+190h+spRootFolder.p], 0
0x180026067  mov     rbx, [rbp+190h+spTaskService.p]
0x18002606b  mov     rax, [rbx]
0x18002606e  mov     rsi, [rax+38h]
0x180026072  lea     RefreshParams, s; "\\"
0x180026079  lea     this, [rsp+290h+taskData]; this
0x18002607e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180026083  nop
0x180026084  mov     RefreshParams, [rax]
0x180026087  test    RefreshParams, RefreshParams
0x18002608a  jz      short loc_18002608F
0x18002608c  mov     RefreshParams, [RefreshParams]
0x18002608f  lea     r8, [rbp+190h+spRootFolder]
0x180026093  mov     this, rbx
0x180026096  mov     rax, rsi
0x180026099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002609e  mov     ebx, eax
0x1800260a0  lea     this, [rsp+290h+taskData]; this
0x1800260a5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800260aa  test    ebx, ebx
0x1800260ac  jns     short loc_1800260E1
0x1800260ae  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800260b5  cmp     this, r13
0x1800260b8  jz      loc_1800267B1
0x1800260be  test    byte ptr [this+1Ch], 2
0x1800260c2  jz      loc_1800267B1
0x1800260c8  mov     edx, 11h; id
0x1800260cd  mov     r9d, ebx; _a1
0x1800260d0  mov     r8, r12; TraceGuid
0x1800260d3  mov     this, [this+10h]; Logger
0x1800260d7  call    WPP_SF_d
0x1800260dc  jmp     loc_1800267B1
0x1800260e1  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800260e8  cmp     this, r13
0x1800260eb  jz      short loc_180026127
0x1800260ed  test    byte ptr [this+1Ch], 10h
0x1800260f1  jz      short loc_18002610B
0x1800260f3  mov     edx, 12h; id
0x1800260f8  mov     r8, r12; TraceGuid
0x1800260fb  mov     this, [this+10h]; Logger
0x1800260ff  call    WPP_SF_
0x180026104  mov     this, cs:WPP_GLOBAL_Control
0x18002610b  cmp     this, r13; __annotation("TMF:",
0x18002610e  jz      short loc_180026127
0x180026110  test    byte ptr [this+1Ch], 10h
0x180026114  jz      short loc_180026127
0x180026116  mov     edx, 13h; id
0x18002611b  mov     r8, r12; TraceGuid
0x18002611e  mov     this, [this+10h]; Logger
0x180026122  call    WPP_SF_
0x180026127  xorps   xmm0, xmm0
0x18002612a  movups  xmmword ptr [rsp+290h+xmlDoc._Ptr], xmm0
0x18002612f  lea     RefreshParams, aXmlVersion10Ta; "<?xml version=\"1.0\" ?>\n<Task xmlns="...
0x180026136  lea     this, [rbp+190h+oldRefreshPayload]; this
0x18002613a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002613f  nop
0x180026140  lea     RefreshParams, [rbp+190h+oldRefreshPayload]; Xml
0x180026144  lea     this, [rsp+290h+xmlDoc]; result
0x180026149  call    ?LoadFromString@Document@Xml@WcmCommon@@SA?AV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::LoadFromString(std::wstring const &)
0x18002614e  nop
0x18002614f  lea     this, [rbp+190h+oldRefreshPayload]; this
0x180026153  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026158  mov     rbx, [rsp+290h+xmlDoc._Ptr]
0x18002615d  lea     RefreshParams, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180026164  lea     this, [rbp+190h+maintenanceSettings]; this
0x180026168  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002616d  nop
0x18002616e  lea     RefreshParams, aDefault; "default"
0x180026175  lea     this, [rbp+190h+taskDeletionFlag]; this
0x180026179  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002617e  nop
0x18002617f  lea     r8, [rbp+190h+maintenanceSettings]; ns
0x180026183  lea     RefreshParams, [rbp+190h+taskDeletionFlag]; key
0x180026187  mov     this, rbx; this
0x18002618a  call    ?AddSelectionNamespace@Document@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WcmCommon::Xml::Document::AddSelectionNamespace(std::wstring const &,std::wstring const &)
0x18002618f  nop
0x180026190  lea     this, [rbp+190h+taskDeletionFlag]; this
0x180026194  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026199  nop
0x18002619a  lea     this, [rbp+190h+maintenanceSettings]; this
0x18002619e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800261a3  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800261aa  cmp     this, r13
0x1800261ad  jz      short loc_1800261C6
0x1800261af  test    byte ptr [this+1Ch], 10h
0x1800261b3  jz      short loc_1800261C6
0x1800261b5  mov     edx, 14h; id
0x1800261ba  mov     r8, r12; TraceGuid
0x1800261bd  mov     this, [this+10h]; Logger
0x1800261c1  call    WPP_SF_
0x1800261c6  xorps   xmm0, xmm0
0x1800261c9  movups  xmmword ptr [rsp+290h+taskData._Ptr], xmm0
0x1800261ce  mov     rbx, [rsp+290h+xmlDoc._Ptr]
0x1800261d3  lea     RefreshParams, aDefaultComhand; "//default:ComHandler/default:Data"
0x1800261da  lea     this, [rbp+190h+taskDeletionFlag]; this
0x1800261de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800261e3  nop
0x1800261e4  lea     r8, [rbp+190h+taskDeletionFlag]; Path
0x1800261e8  lea     RefreshParams, [rsp+290h+taskData]; result
0x1800261ed  mov     this, rbx; this
0x1800261f0  call    ?SelectSingle@Document@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::SelectSingle(std::wstring const &)
0x1800261f5  nop
0x1800261f6  lea     this, [rbp+190h+taskDeletionFlag]; this
0x1800261fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800261ff  xorps   xmm0, xmm0
0x180026202  movups  xmmword ptr [rbp+190h+taskDataString._Mypair._Myval2._Bx], xmm0
0x180026209  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180026211  movdqu  xmmword ptr [rbp+190h+taskDataString._Mypair._Myval2._Mysize], xmm1
0x180026219  xor     eax, eax
0x18002621b  mov     word ptr [rbp+190h+taskDataString._Mypair._Myval2._Bx], ax
0x180026222  movups  xmmword ptr [rbp+190h+oldRefreshPayload._Mypair._Myval2._Bx], xmm0
0x180026226  movdqu  xmmword ptr [rbp+190h+oldRefreshPayload._Mypair._Myval2._Mysize], xmm1
0x18002622b  mov     word ptr [rbp+190h+oldRefreshPayload._Mypair._Myval2._Bx], ax
0x18002622f  lea     rsi, [r14+28h]
0x180026233  add     r14, 8
0x180026237  lea     r9, [rbp+190h+taskDataString]; TaskBlob
0x18002623e  lea     r8, [rbp+190h+oldRefreshPayload]; Param3
0x180026242  mov     RefreshParams, rsi; Param2
0x180026245  mov     this, r14; Param1
0x180026248  call    _anonymous_namespace___CreateTaskParameters
0x18002624d  mov     ebx, eax
0x18002624f  lea     this, [rbp+190h+oldRefreshPayload]; this
0x180026253  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026258  test    ebx, ebx
0x18002625a  jns     short loc_18002628F
0x18002625c  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026263  cmp     this, r13
0x180026266  jz      loc_180026784
0x18002626c  test    byte ptr [this+1Ch], 2
0x180026270  jz      loc_180026784
0x180026276  mov     edx, 15h; id
0x18002627b  mov     r9d, ebx; _a1
0x18002627e  mov     r8, r12; TraceGuid
0x180026281  mov     this, [this+10h]; Logger
0x180026285  call    WPP_SF_d
0x18002628a  jmp     loc_180026784
0x18002628f  lea     RefreshParams, [rbp+190h+taskDataString]; Text
0x180026296  mov     this, [rsp+290h+taskData._Ptr]; this
0x18002629b  call    ?SetText@Node@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Xml::Node::SetText(std::wstring const &)
0x1800262a0  test    edi, edi
0x1800262a2  jz      loc_18002649F
0x1800262a8  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800262af  cmp     this, r13
0x1800262b2  jz      short loc_1800262CB
0x1800262b4  test    byte ptr [this+1Ch], 10h
0x1800262b8  jz      short loc_1800262CB
0x1800262ba  mov     edx, 16h; id
0x1800262bf  mov     r8, r12; TraceGuid
0x1800262c2  mov     this, [this+10h]; Logger
0x1800262c6  call    WPP_SF_
0x1800262cb  xorps   xmm0, xmm0
0x1800262ce  movups  xmmword ptr [rbp+190h+taskDeletionFlag._Mypair._Myval2._Bx], xmm0
0x1800262d2  mov     rbx, [rsp+290h+xmlDoc._Ptr]
0x1800262d7  lea     RefreshParams, aDefaultSetting; "./default:Settings"
0x1800262de  lea     this, [rbp+190h+oldRefreshPayload]; this
0x1800262e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800262e7  nop
0x1800262e8  lea     r8, [rbp+190h+oldRefreshPayload]; Path
0x1800262ec  lea     RefreshParams, [rbp+190h+taskDeletionFlag]; result
0x1800262f0  mov     this, rbx; this
0x1800262f3  call    ?SelectSingle@Document@Xml@WcmCommon@@QEAA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Document::SelectSingle(std::wstring const &)
0x1800262f8  nop
0x1800262f9  lea     this, [rbp+190h+oldRefreshPayload]; this
0x1800262fd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026302  xorps   xmm0, xmm0
0x180026305  movups  xmmword ptr [rbp+190h+maintenanceSettings._Ptr], xmm0
0x180026309  xorps   xmm1, xmm1
0x18002630c  movdqu  xmmword ptr [rsp+290h+storeKey._Ptr], xmm1
0x180026312  lea     RefreshParams, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180026319  lea     this, [rbp+190h+Namespace]; this
0x18002631d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180026322  nop
0x180026323  lea     RefreshParams, aMaintenanceset; "MaintenanceSettings"
0x18002632a  lea     this, [rbp+190h+oldRefreshPayload]; this
0x18002632e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180026333  nop
0x180026334  lea     rax, [rsp+290h+storeKey]
0x180026339  mov     [rsp+290h+ppv], rax; insertBefore
  ... truncated ...
```
