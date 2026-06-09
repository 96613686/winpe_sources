# RefreshTaskThread(IStream *)

- ea: `0x180036d38`
- end: `0x18003710b`
- name: `?RefreshTaskThread@@YAJPEAUIStream@@@Z`
- size: `979`
- prototype: `HRESULT __fastcall(IStream *pStream)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180036524`

## callees

- `0x180002790`
- `0x18000af94`
- `0x18000b0a0`
- `0x18000b2f4`
- `0x18000b8fc`
- `0x18000b974`
- `0x18000d024`
- `0x18000fa6c`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x1800196d0`
- `0x18001c414`
- `0x18001c680`
- `0x1800270d8`
- `0x180027c8c`
- `0x180036558`
- `0x180036ba8`
- `0x180036d38`
- `0x1800372a4`
- `0x180037a14`
- `0x18003bda0`
- `0x18003c040`
- `0x18003cbd0`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800370d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800370d0`

## string_xrefs

- `0x180036fc9`: `TaskParams`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall RefreshTaskThread(IStream *pStream)
{
  WPP_PROJECT_CONTROL_BLOCK *v2; // rcx
  int TaskParamsFromRegistry; // edi
  int v4; // eax
  WPP_PROJECT_CONTROL_BLOCK *v5; // rcx
  RegistryStore<1> *v6; // rax
  Registry::REGISTRY_ACCESS_PERMISSIONS v7; // r8d
  ITaskHandlerStatus *p; // rbx
  ATL::CComBSTR data; // [rsp+20h] [rbp-E0h] BYREF
  ATL::CComPtr<ITaskHandlerStatus> spTaskHandlerStatus; // [rsp+28h] [rbp-D8h] BYREF
  std::shared_ptr<Registry::Key> storeKey; // [rsp+30h] [rbp-D0h] BYREF
  std::wstring ValueName; // [rsp+40h] [rbp-C0h] BYREF
  std::wstring newTaskParams; // [rsp+60h] [rbp-A0h] BYREF
  std::wstring subscriberId; // [rsp+80h] [rbp-80h] BYREF
  std::wstring carrierId; // [rsp+A0h] [rbp-60h] BYREF
  std::wstring taskParams; // [rsp+C0h] [rbp-40h] BYREF
  std::wstring dummyString; // [rsp+E0h] [rbp-20h] BYREF
  Handler::Parameters params; // [rsp+100h] [rbp+0h] BYREF
  EngineHandler engineHandler; // [rsp+160h] [rbp+60h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x14u, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v2->ReserveSpace[28] & 0x10) != 0 )
      WPP_SF_(v2->Control.Logger, 0x15u, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
  }
  spTaskHandlerStatus.p = 0;
  data.m_str = 0;
  TaskParamsFromRegistry = UnmarshalTaskParametersFromStream(pStream, &data.m_str, &spTaskHandlerStatus.p);
  std::wstring::wstring(&carrierId);
  std::wstring::wstring(&subscriberId);
  std::wstring::wstring(&dummyString);
  if ( TaskParamsFromRegistry >= 0 )
  {
    std::wstring::wstring(&newTaskParams, data.m_str);
    TaskParamsFromRegistry = anonymous_namespace_::RetreiveTaskParameters(
                               &newTaskParams,
                               &carrierId,
                               &subscriberId,
                               &dummyString);
    std::wstring::_Tidy_deallocate(&newTaskParams);
  }
  std::wstring::wstring(&taskParams);
  if ( TaskParamsFromRegistry < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
    {
      goto LABEL_32;
    }
    WPP_SF_d(
      WPP_GLOBAL_Control->Control.Logger,
      0x16u,
      WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids,
      TaskParamsFromRegistry);
LABEL_31:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_32;
  }
  TaskParamsFromRegistry = GetTaskParamsFromRegistry(&carrierId, &subscriberId, &taskParams);
  if ( TaskParamsFromRegistry < 0 )
    goto LABEL_31;
  storeKey._Ptr = (Registry::Key *)&taskParams;
  v4 = ExecuteAndConvertAnyException__RefreshTaskThread_::_16_::_lambda_1___((const RefreshTaskThread::__l16::<lambda_1> *)&storeKey);
  TaskParamsFromRegistry = v4;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x17u, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids, v4);
    v5 = WPP_GLOBAL_Control;
  }
  if ( TaskParamsFromRegistry >= 0 )
  {
    if ( GetTaskParamsFromRegistry(&carrierId, &subscriberId, &taskParams) >= 0 )
    {
      std::wstring::wstring(&newTaskParams);
      if ( ShouldTaskBeDeleted(&taskParams, &newTaskParams) )
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x18u, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
        }
        Handler::Parameters::Parameters(&params);
        std::wstring::operator=(&params.CarrierId, &carrierId);
        std::wstring::operator=(&params.SubscriberId, &subscriberId);
        EngineHandler::EngineHandler(&engineHandler);
        Handler::Parameters::operator=(&engineHandler.m_params, &params);
        EngineHandler::RemoveRefreshTrigger(&engineHandler);
        Signature::SignatureInfo::~SignatureInfo((Signature::SignatureInfo *)&engineHandler.m_params);
        Signature::SignatureInfo::~SignatureInfo((Signature::SignatureInfo *)&params);
      }
      else if ( newTaskParams._Mypair._Myval2._Mysize )
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
        }
        storeKey = 0;
        v6 = RegistryStore<1>::CreateCarrierSubscriberTasksStore((RegistryStore<1> *)&params, &carrierId, &subscriberId);
        Registry::CreateKeyRW(&storeKey, &v6->m_storePath, v7);
        Registry::Path::~Path((Registry::Path *)&params);
        std::wstring::wstring(&ValueName, L"TaskParams");
        Registry::Key::SetSzValue(storeKey._Ptr, &ValueName, &newTaskParams);
        std::wstring::_Tidy_deallocate(&ValueName);
        if ( storeKey._Rep )
          std::_Ref_count_base::_Decref(storeKey._Rep);
      }
      std::wstring::_Tidy_deallocate(&newTaskParams);
    }
    goto LABEL_31;
  }
LABEL_32:
  p = spTaskHandlerStatus.p;
  if ( spTaskHandlerStatus.p )
  {
    if ( v5 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v5->ReserveSpace[28] & 0x10) != 0 )
      WPP_SF_d(v5->Control.Logger, 0x1Au, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids, TaskParamsFromRegistry);
    p->TaskCompleted(p, TaskParamsFromRegistry);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v5->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v5->Control.Logger, 0x1Bu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids, TaskParamsFromRegistry);
  std::wstring::_Tidy_deallocate(&taskParams);
  std::wstring::_Tidy_deallocate(&dummyString);
  std::wstring::_Tidy_deallocate(&subscriberId);
  std::wstring::_Tidy_deallocate(&carrierId);
  SysFreeString(data.m_str);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spTaskHandlerStatus);
  return (unsigned int)TaskParamsFromRegistry;
}

```

## disassembly

```asm
0x180036d38  mov     [rsp-8+arg_8], rbx
0x180036d3d  mov     [rsp-8+arg_10], rdi
0x180036d42  push    rbp
0x180036d43  push    r12
0x180036d45  push    r14
0x180036d47  lea     rbp, [rsp-0E0h]
0x180036d4f  sub     rsp, 1E0h
0x180036d56  mov     rax, cs:__security_cookie
0x180036d5d  xor     rax, rsp
0x180036d60  mov     [rbp+0F0h+var_20], rax
0x180036d67  mov     rbx, pStream
0x180036d6a  lea     r14, WPP_GLOBAL_Control; __annotation("TMF:",
0x180036d71  lea     r12, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids
0x180036d78  mov     pStream, cs:WPP_GLOBAL_Control
0x180036d7f  cmp     pStream, r14
0x180036d82  jz      short loc_180036DBE
0x180036d84  test    byte ptr [pStream+1Ch], 10h
0x180036d88  jz      short loc_180036DA2
0x180036d8a  mov     edx, 14h; id
0x180036d8f  mov     r8, r12; TraceGuid
0x180036d92  mov     pStream, [pStream+10h]; Logger
0x180036d96  call    WPP_SF_
0x180036d9b  mov     pStream, cs:WPP_GLOBAL_Control
0x180036da2  cmp     pStream, r14; __annotation("TMF:",
0x180036da5  jz      short loc_180036DBE
0x180036da7  test    byte ptr [pStream+1Ch], 10h
0x180036dab  jz      short loc_180036DBE
0x180036dad  mov     edx, 15h; id
0x180036db2  mov     r8, r12; TraceGuid
0x180036db5  mov     pStream, [pStream+10h]; Logger
0x180036db9  call    WPP_SF_
0x180036dbe  mov     [rsp+1F0h+spTaskHandlerStatus.p], 0
0x180036dc7  mov     [rsp+1F0h+data.m_str], 0
0x180036dd0  lea     r8, [rsp+1F0h+spTaskHandlerStatus]; ppTaskHandlerStatus
0x180036dd5  lea     rdx, [rsp+1F0h+data]; Data
0x180036dda  mov     pStream, rbx; pStream
0x180036ddd  call    ?UnmarshalTaskParametersFromStream@@YAJPEAUIStream@@PEAPEAGPEAPEAUITaskHandlerStatus@@@Z; UnmarshalTaskParametersFromStream(IStream *,ushort * *,ITaskHandlerStatus * *)
0x180036de2  mov     edi, eax
0x180036de4  lea     pStream, [rbp+0F0h+carrierId]; this
0x180036de8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036ded  nop
0x180036dee  lea     pStream, [rbp+0F0h+subscriberId]; this
0x180036df2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036df7  nop
0x180036df8  lea     pStream, [rbp+0F0h+dummyString]; this
0x180036dfc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036e01  nop
0x180036e02  test    edi, edi
0x180036e04  js      short loc_180036E38
0x180036e06  mov     rdx, [rsp+1F0h+data.m_str]; _Ptr
0x180036e0b  lea     pStream, [rsp+1F0h+newTaskParams]; this
0x180036e10  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180036e15  nop
0x180036e16  lea     r9, [rbp+0F0h+dummyString]; Param3
0x180036e1a  lea     r8, [rbp+0F0h+subscriberId]; Param2
0x180036e1e  lea     rdx, [rbp+0F0h+carrierId]; Param1
0x180036e22  lea     pStream, [rsp+1F0h+newTaskParams]; TaskBlob
0x180036e27  call    _anonymous_namespace___RetreiveTaskParameters
0x180036e2c  mov     edi, eax
0x180036e2e  lea     pStream, [rsp+1F0h+newTaskParams]; this
0x180036e33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036e38  lea     pStream, [rbp+0F0h+taskParams]; this
0x180036e3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036e41  nop
0x180036e42  test    edi, edi
0x180036e44  js      loc_180037015
0x180036e4a  lea     r8, [rbp+0F0h+taskParams]; taskParams
0x180036e4e  lea     rdx, [rbp+0F0h+subscriberId]; subscriberId
0x180036e52  lea     pStream, [rbp+0F0h+carrierId]; carrierId
0x180036e56  call    ?GetTaskParamsFromRegistry@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV12@@Z; GetTaskParamsFromRegistry(std::wstring const &,std::wstring const &,std::wstring &)
0x180036e5b  mov     edi, eax
0x180036e5d  test    eax, eax
0x180036e5f  js      loc_18003703B
0x180036e65  lea     rax, [rbp+0F0h+taskParams]
0x180036e69  mov     [rsp+1F0h+storeKey._Ptr], rax
0x180036e6e  lea     pStream, [rsp+1F0h+storeKey]; f
0x180036e73  call    ExecuteAndConvertAnyException__RefreshTaskThread____16____lambda_1___
0x180036e78  mov     edi, eax
0x180036e7a  mov     pStream, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180036e81  cmp     pStream, r14
0x180036e84  jz      short loc_180036EA7
0x180036e86  test    byte ptr [pStream+1Ch], 10h
0x180036e8a  jz      short loc_180036EA7
0x180036e8c  mov     edx, 17h; id
0x180036e91  mov     r9d, eax; _a1
0x180036e94  mov     r8, r12; TraceGuid
0x180036e97  mov     pStream, [pStream+10h]; Logger
0x180036e9b  call    WPP_SF_d
0x180036ea0  mov     pStream, cs:WPP_GLOBAL_Control
0x180036ea7  test    edi, edi
0x180036ea9  js      loc_180037042
0x180036eaf  lea     r8, [rbp+0F0h+taskParams]; taskParams
0x180036eb3  lea     rdx, [rbp+0F0h+subscriberId]; subscriberId
0x180036eb7  lea     pStream, [rbp+0F0h+carrierId]; carrierId
0x180036ebb  call    ?GetTaskParamsFromRegistry@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV12@@Z; GetTaskParamsFromRegistry(std::wstring const &,std::wstring const &,std::wstring &)
0x180036ec0  test    eax, eax
0x180036ec2  js      loc_18003703B
0x180036ec8  lea     pStream, [rsp+1F0h+newTaskParams]; this
0x180036ecd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036ed2  nop
0x180036ed3  lea     rdx, [rsp+1F0h+newTaskParams]; newTaskParams
0x180036ed8  lea     pStream, [rbp+0F0h+taskParams]; taskParams
0x180036edc  call    ?ShouldTaskBeDeleted@@YA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ShouldTaskBeDeleted(std::wstring &,std::wstring &)
0x180036ee1  test    al, al
0x180036ee3  jz      loc_180036F69
0x180036ee9  mov     pStream, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180036ef0  cmp     pStream, r14
0x180036ef3  jz      short loc_180036F0C
0x180036ef5  test    byte ptr [pStream+1Ch], 10h
0x180036ef9  jz      short loc_180036F0C
0x180036efb  mov     edx, 18h; id
0x180036f00  mov     r8, r12; TraceGuid
0x180036f03  mov     pStream, [pStream+10h]; Logger
0x180036f07  call    WPP_SF_
0x180036f0c  lea     pStream, [rbp+0F0h+params]; this
0x180036f10  call    ??0Parameters@Handler@@QEAA@XZ; Handler::Parameters::Parameters(void)
0x180036f15  nop
0x180036f16  lea     rdx, [rbp+0F0h+carrierId]; _Right
0x180036f1a  lea     pStream, [rbp+0F0h+params]; this
0x180036f1e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180036f23  lea     rdx, [rbp+0F0h+subscriberId]; _Right
0x180036f27  lea     pStream, [rbp+0F0h+params.SubscriberId]; this
0x180036f2b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180036f30  lea     pStream, [rbp+0F0h+engineHandler]; this
0x180036f34  call    ??0EngineHandler@@QEAA@XZ; EngineHandler::EngineHandler(void)
0x180036f39  nop
0x180036f3a  lea     rdx, [rbp+0F0h+params]; __that
0x180036f3e  lea     pStream, [rbp+0F0h+engineHandler.m_params]; this
0x180036f42  call    ??4Parameters@Handler@@QEAAAEAU01@AEBU01@@Z; Handler::Parameters::operator=(Handler::Parameters const &)
0x180036f47  lea     pStream, [rbp+0F0h+engineHandler]; this
0x180036f4b  call    ?RemoveRefreshTrigger@EngineHandler@@QEAAXXZ; EngineHandler::RemoveRefreshTrigger(void)
0x180036f50  nop
0x180036f51  lea     pStream, [rbp+0F0h+engineHandler.m_params]; this
0x180036f55  call    ??1SignatureInfo@Signature@@QEAA@XZ; Signature::SignatureInfo::~SignatureInfo(void)
0x180036f5a  nop
0x180036f5b  lea     pStream, [rbp+0F0h+params]; this
0x180036f5f  call    ??1SignatureInfo@Signature@@QEAA@XZ; Signature::SignatureInfo::~SignatureInfo(void)
0x180036f64  jmp     loc_180037009
0x180036f69  cmp     [rsp+1F0h+newTaskParams._Mypair._Myval2._Mysize], 0
0x180036f6f  jz      loc_180037009
0x180036f75  mov     pStream, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180036f7c  cmp     pStream, r14
0x180036f7f  jz      short loc_180036F98
0x180036f81  test    byte ptr [pStream+1Ch], 10h
0x180036f85  jz      short loc_180036F98
0x180036f87  mov     edx, 19h; id
0x180036f8c  mov     r8, r12; TraceGuid
0x180036f8f  mov     pStream, [pStream+10h]; Logger
0x180036f93  call    WPP_SF_
0x180036f98  xorps   xmm0, xmm0
0x180036f9b  movups  xmmword ptr [rsp+1F0h+storeKey._Ptr], xmm0
0x180036fa0  lea     r8, [rbp+0F0h+subscriberId]; SubscriberId
0x180036fa4  lea     rdx, [rbp+0F0h+carrierId]; CarrierId
0x180036fa8  lea     pStream, [rbp+0F0h+params]; result
0x180036fac  call    ?CreateCarrierSubscriberTasksStore@?$RegistryStore@$00@@SA?AV1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; RegistryStore<1>::CreateCarrierSubscriberTasksStore(std::wstring const &,std::wstring const &)
0x180036fb1  nop
0x180036fb2  mov     rdx, rax; path
0x180036fb5  lea     pStream, [rsp+1F0h+storeKey]; result
0x180036fba  call    ?CreateKeyRW@Registry@@YA?AV?$shared_ptr@VKey@Registry@@@std@@AEBVPath@1@W4REGISTRY_ACCESS_PERMISSIONS@1@@Z; Registry::CreateKeyRW(Registry::Path const &,Registry::REGISTRY_ACCESS_PERMISSIONS)
0x180036fbf  nop
0x180036fc0  lea     pStream, [rbp+0F0h+params]; this
0x180036fc4  call    ??1Path@Registry@@QEAA@XZ; Registry::Path::~Path(void)
0x180036fc9  lea     rdx, aTaskparams; "TaskParams"
0x180036fd0  lea     pStream, [rsp+1F0h+ValueName]; this
0x180036fd5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180036fda  lea     r8, [rsp+1F0h+newTaskParams]; Data
0x180036fdf  lea     rdx, [rsp+1F0h+ValueName]; ValueName
0x180036fe4  mov     pStream, [rsp+1F0h+storeKey._Ptr]; this
0x180036fe9  call    ?SetSzValue@Key@Registry@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Registry::Key::SetSzValue(std::wstring const &,std::wstring const &)
0x180036fee  lea     pStream, [rsp+1F0h+ValueName]; this
0x180036ff3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036ff8  nop
0x180036ff9  mov     pStream, [rsp+1F0h+storeKey._Rep]; this
0x180036ffe  test    pStream, pStream
0x180037001  jz      short loc_180037009
0x180037003  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037008  nop
0x180037009  lea     pStream, [rsp+1F0h+newTaskParams]; this
0x18003700e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037013  jmp     short loc_18003703B
0x180037015  mov     pStream, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003701c  cmp     pStream, r14
0x18003701f  jz      short loc_180037042
0x180037021  test    byte ptr [pStream+1Ch], 2
0x180037025  jz      short loc_180037042
0x180037027  mov     edx, 16h; id
0x18003702c  mov     r9d, edi; _a1
0x18003702f  mov     r8, r12; TraceGuid
0x180037032  mov     pStream, [pStream+10h]; Logger
0x180037036  call    WPP_SF_d
0x18003703b  mov     pStream, cs:WPP_GLOBAL_Control
0x180037042  mov     rbx, [rsp+1F0h+spTaskHandlerStatus.p]
0x180037047  test    rbx, rbx
0x18003704a  jz      short loc_180037083
0x18003704c  cmp     pStream, r14; __annotation("TMF:",
0x18003704f  jz      short loc_18003706B
0x180037051  test    byte ptr [pStream+1Ch], 10h
0x180037055  jz      short loc_18003706B
0x180037057  mov     edx, 1Ah; id
0x18003705c  mov     r9d, edi; _a1
0x18003705f  mov     r8, r12; TraceGuid
0x180037062  mov     pStream, [pStream+10h]; Logger
0x180037066  call    WPP_SF_d
0x18003706b  mov     rax, [rbx]
0x18003706e  mov     edx, edi
0x180037070  mov     pStream, rbx
0x180037073  mov     rax, [rax+20h]
0x180037077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003707c  mov     pStream, cs:WPP_GLOBAL_Control
0x180037083  cmp     pStream, r14; __annotation("TMF:",
0x180037086  jz      short loc_1800370A3
0x180037088  test    byte ptr [pStream+1Ch], 10h
0x18003708c  jz      short loc_1800370A3
0x18003708e  mov     edx, 1Bh; id
0x180037093  mov     r9d, edi; _a1
0x180037096  mov     r8, r12; TraceGuid
0x180037099  mov     pStream, [pStream+10h]; Logger
0x18003709d  call    WPP_SF_d
0x1800370a2  nop
0x1800370a3  lea     pStream, [rbp+0F0h+taskParams]; this
0x1800370a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800370ac  nop
0x1800370ad  lea     pStream, [rbp+0F0h+dummyString]; this
0x1800370b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800370b6  nop
0x1800370b7  lea     pStream, [rbp+0F0h+subscriberId]; this
0x1800370bb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800370c0  nop
0x1800370c1  lea     pStream, [rbp+0F0h+carrierId]; this
0x1800370c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800370ca  nop
0x1800370cb  mov     pStream, [rsp+1F0h+data.m_str]; bstrString
0x1800370d0  call    cs:__imp_SysFreeString
0x1800370d6  nop
0x1800370d7  lea     pStream, [rsp+1F0h+spTaskHandlerStatus]; this
0x1800370dc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800370e1  mov     eax, edi
0x1800370e3  mov     pStream, [rbp+0F0h+var_20]
0x1800370ea  xor     pStream, rsp; StackCookie
0x1800370ed  call    __security_check_cookie
0x1800370f2  lea     r11, [rsp+1F0h+var_10]
0x1800370fa  mov     rbx, [r11+28h]
0x1800370fe  mov     rdi, [r11+30h]
0x180037102  mov     rsp, r11
0x180037105  pop     r14
0x180037107  pop     r12
0x180037109  pop     rbp
0x18003710a  retn
```
