# ActivationTaskThread(IStream *)

- ea: `0x180017d2c`
- end: `0x180018281`
- name: `?ActivationTaskThread@@YAJPEAUIStream@@@Z`
- size: `1365`
- prototype: `HRESULT __fastcall(IStream *pStream)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017558`

## callees

- `0x180002790`
- `0x18000a42c`
- `0x18000af94`
- `0x18000b0a0`
- `0x18000b178`
- `0x18000b2f4`
- `0x180011844`
- `0x180011cfc`
- `0x180012400`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x180014b98`
- `0x18001532c`
- `0x180017d2c`
- `0x180018ca0`
- `0x180018efc`
- `0x1800191ac`
- `0x180019d04`
- `0x18001a0d4`
- `0x18001a700`
- `0x18001a80c`
- `0x1800677d8`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001807d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001807d`

## string_xrefs

- `0x180018182`: `ServiceActivation`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ActivationTaskThread(IStream *pStream)
{
  WPP_PROJECT_CONTROL_BLOCK *v2; // rcx
  int ActivationTaskParamsFromRegistry; // edi
  const wchar_t *v4; // rax
  __int64 v5; // r10
  const wchar_t *v6; // rax
  const wchar_t *v7; // r8
  unsigned __int64 v8; // r9
  unsigned int v9; // ebx
  const wchar_t *v10; // rax
  const _EVENT_DESCRIPTOR *v11; // rdx
  _MCGEN_TRACE_CONTEXT *v12; // rcx
  const wchar_t *Descriptor; // r8
  HRESULT v14; // eax
  const wchar_t *v15; // rax
  const _EVENT_DESCRIPTOR *v16; // rdx
  _MCGEN_TRACE_CONTEXT *v17; // rcx
  const wchar_t *v18; // r8
  WPP_PROJECT_CONTROL_BLOCK *v19; // r10
  ITaskHandlerStatus *p; // rbx
  const wchar_t *v22; // rax
  const wchar_t *v23; // r8
  unsigned __int64 v24; // r9
  const wchar_t *v25; // rax
  const _EVENT_DESCRIPTOR *v26; // rdx
  _MCGEN_TRACE_CONTEXT *v27; // rcx
  const wchar_t *v28; // r8
  const wchar_t *v29; // rax
  const _EVENT_DESCRIPTOR *v30; // rdx
  _MCGEN_TRACE_CONTEXT *v31; // rcx
  const wchar_t *v32; // r8
  const wchar_t *v33; // rax
  const wchar_t *v34; // r8
  unsigned __int64 v35; // r9
  const wchar_t *v36; // rax
  const _EVENT_DESCRIPTOR *v37; // rdx
  _MCGEN_TRACE_CONTEXT *v38; // rcx
  const wchar_t *v39; // r8
  const wchar_t *v40; // rax
  __int64 v41; // r10
  bool firstAttemptWasFailedReregistration; // [rsp+40h] [rbp-C0h] BYREF
  ATL::CComBSTR data; // [rsp+48h] [rbp-B8h] BYREF
  ATL::CComPtr<ITaskHandlerStatus> spTaskHandlerStatus; // [rsp+50h] [rbp-B0h] BYREF
  void *cancelEvent; // [rsp+58h] [rbp-A8h] BYREF
  std::wstring subscriberId; // [rsp+60h] [rbp-A0h] BYREF
  std::vector<unsigned char> payload; // [rsp+80h] [rbp-80h] BYREF
  std::wstring method; // [rsp+A0h] [rbp-60h] BYREF
  std::wstring carrierId; // [rsp+C0h] [rbp-40h] BYREF
  std::wstring taskParams; // [rsp+E0h] [rbp-20h] BYREF
  std::wstring deviceId; // [rsp+100h] [rbp+0h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x21u, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  cancelEvent = 0;
  if ( v2 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v2->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_(v2->Control.Logger, 0x22u, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
  spTaskHandlerStatus.p = 0;
  data.m_str = 0;
  ActivationTaskParamsFromRegistry = UnmarshalActivationTaskParametersFromStream(
                                       pStream,
                                       &cancelEvent,
                                       &data.m_str,
                                       &spTaskHandlerStatus.p);
  std::wstring::wstring(&taskParams);
  std::wstring::wstring(&carrierId);
  std::wstring::wstring(&subscriberId);
  std::wstring::wstring(&deviceId);
  if ( ActivationTaskParamsFromRegistry >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x23u, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
    }
    std::wstring::wstring((std::wstring *)&payload, data.m_str);
    ActivationTaskParamsFromRegistry = GetActivationTaskParamsFromRegistry(
                                         (const std::wstring *)&payload,
                                         &taskParams,
                                         &carrierId,
                                         &subscriberId,
                                         &deviceId);
    std::wstring::_Tidy_deallocate((std::wstring *)&payload);
  }
  std::wstring::wstring(&method);
  memset(&payload, 0, sizeof(payload));
  std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&payload);
  if ( ActivationTaskParamsFromRegistry < 0 )
    goto LABEL_25;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x24u, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
  }
  firstAttemptWasFailedReregistration = 0;
  ParseTaskData(&taskParams, &method, &payload, &firstAttemptWasFailedReregistration);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&method._Mypair._Myval2);
    WPP_SF_S(*(_QWORD *)(v5 + 16), 0x25u, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids, v4);
  }
  std::_WChar_traits<unsigned short>::length(L"ReconnectToNetwork");
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&method._Mypair._Myval2);
  if ( std::_Traits_equal<std::char_traits<unsigned short>>(v6, method._Mypair._Myval2._Mysize, v7, v8) )
  {
    v9 = 3;
    if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x20) != 0 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&taskParams._Mypair._Myval2);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&subscriberId._Mypair._Myval2);
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&carrierId._Mypair._Myval2);
      McTemplateU0qzzz_EtwEventWriteTransfer(v12, v11, 3u, v10, &v11->Id, Descriptor);
    }
    v14 = ActivationMethods::ReconnectToNetwork(
            &subscriberId,
            &deviceId,
            firstAttemptWasFailedReregistration,
            cancelEvent);
LABEL_23:
    ActivationTaskParamsFromRegistry = v14;
    if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x20) != 0 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&taskParams._Mypair._Myval2);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&subscriberId._Mypair._Myval2);
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&carrierId._Mypair._Myval2);
      McTemplateU0qzzzd_EtwEventWriteTransfer(v17, v16, v9, v15, &v16->Id, v18, ActivationTaskParamsFromRegistry);
    }
LABEL_25:
    v19 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  std::_WChar_traits<unsigned short>::length(L"ReregisterToNetwork");
  v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&method._Mypair._Myval2);
  if ( std::_Traits_equal<std::char_traits<unsigned short>>(v22, method._Mypair._Myval2._Mysize, v23, v24) )
  {
    if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x20) != 0 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&taskParams._Mypair._Myval2);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&subscriberId._Mypair._Myval2);
      v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&carrierId._Mypair._Myval2);
      McTemplateU0qzzz_EtwEventWriteTransfer(v27, v26, 2u, v25, &v26->Id, v28);
    }
    ActivationTaskParamsFromRegistry = PerformReregisterToNetwork(&carrierId, &subscriberId, &deviceId, cancelEvent);
    if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x20) != 0 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&taskParams._Mypair._Myval2);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&subscriberId._Mypair._Myval2);
      v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&carrierId._Mypair._Myval2);
      McTemplateU0qzzzd_EtwEventWriteTransfer(v31, v30, 2u, v29, &v30->Id, v32, ActivationTaskParamsFromRegistry);
    }
    goto LABEL_25;
  }
  std::_WChar_traits<unsigned short>::length(L"ServiceActivation");
  v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&method._Mypair._Myval2);
  if ( std::_Traits_equal<std::char_traits<unsigned short>>(v33, method._Mypair._Myval2._Mysize, v34, v35) )
  {
    v9 = 1;
    if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x20) != 0 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&taskParams._Mypair._Myval2);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&subscriberId._Mypair._Myval2);
      v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&carrierId._Mypair._Myval2);
      McTemplateU0qzzz_EtwEventWriteTransfer(v38, v37, 1u, v36, &v37->Id, v39);
    }
    if ( payload._Mypair._Myval2._Myfirst == payload._Mypair._Myval2._Mylast
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x20u, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
    }
    v14 = ActivationMethods::ServiceActivate(&subscriberId, &deviceId, &payload);
    goto LABEL_23;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
  {
    v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&method._Mypair._Myval2);
    WPP_SF_S(*(_QWORD *)(v41 + 16), 0x26u, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids, v40);
    v19 = WPP_GLOBAL_Control;
  }
  ActivationTaskParamsFromRegistry = -2147023266;
LABEL_26:
  p = spTaskHandlerStatus.p;
  if ( spTaskHandlerStatus.p )
  {
    if ( v19 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v19->ReserveSpace[28] & 0x10) != 0 )
      WPP_SF_d(
        v19->Control.Logger,
        0x27u,
        WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids,
        ActivationTaskParamsFromRegistry);
    p->TaskCompleted(p, ActivationTaskParamsFromRegistry);
    v19 = WPP_GLOBAL_Control;
  }
  if ( v19 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v19->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(
      v19->Control.Logger,
      0x28u,
      WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids,
      ActivationTaskParamsFromRegistry);
  std::vector<unsigned char>::_Tidy((std::vector<char> *)&payload);
  std::wstring::_Tidy_deallocate(&method);
  std::wstring::_Tidy_deallocate(&deviceId);
  std::wstring::_Tidy_deallocate(&subscriberId);
  std::wstring::_Tidy_deallocate(&carrierId);
  std::wstring::_Tidy_deallocate(&taskParams);
  SysFreeString(data.m_str);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spTaskHandlerStatus);
  return (unsigned int)ActivationTaskParamsFromRegistry;
}

```

## disassembly

```asm
0x180017d2c  mov     [rsp-8+arg_8], rbx
0x180017d31  mov     [rsp-8+arg_10], rsi
0x180017d36  push    rbp
0x180017d37  push    rdi
0x180017d38  push    r14
0x180017d3a  lea     rbp, [rsp-30h]
0x180017d3f  sub     rsp, 130h
0x180017d46  mov     rax, cs:__security_cookie
0x180017d4d  xor     rax, rsp
0x180017d50  mov     [rbp+40h+var_20], rax
0x180017d54  mov     rbx, pStream
0x180017d57  lea     rsi, WPP_GLOBAL_Control; __annotation("TMF:",
0x180017d5e  lea     r14, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids
0x180017d65  mov     pStream, cs:WPP_GLOBAL_Control
0x180017d6c  cmp     pStream, rsi
0x180017d6f  jz      short loc_180017D8F
0x180017d71  test    byte ptr [pStream+1Ch], 10h
0x180017d75  jz      short loc_180017D8F
0x180017d77  mov     edx, 21h ; '!'; id
0x180017d7c  mov     r8, r14; TraceGuid
0x180017d7f  mov     pStream, [pStream+10h]; Logger
0x180017d83  call    WPP_SF_
0x180017d88  mov     pStream, cs:WPP_GLOBAL_Control
0x180017d8f  mov     [rsp+140h+cancelEvent], 0
0x180017d98  cmp     pStream, rsi; __annotation("TMF:",
0x180017d9b  jz      short loc_180017DB4
0x180017d9d  test    byte ptr [pStream+1Ch], 10h
0x180017da1  jz      short loc_180017DB4
0x180017da3  mov     edx, 22h ; '"'; id
0x180017da8  mov     r8, r14; TraceGuid
0x180017dab  mov     pStream, [pStream+10h]; Logger
0x180017daf  call    WPP_SF_
0x180017db4  mov     [rsp+140h+spTaskHandlerStatus.p], 0
0x180017dbd  mov     [rsp+140h+data.m_str], 0
0x180017dc6  lea     r9, [rsp+140h+spTaskHandlerStatus]; ppTaskHandlerStatus
0x180017dcb  lea     r8, [rsp+140h+data]; Data
0x180017dd0  lea     rdx, [rsp+140h+cancelEvent]; CancelEvent
0x180017dd5  mov     pStream, rbx; pStream
0x180017dd8  call    ?UnmarshalActivationTaskParametersFromStream@@YAJPEAUIStream@@AEAPEAXPEAPEAGPEAPEAUITaskHandlerStatus@@@Z; UnmarshalActivationTaskParametersFromStream(IStream *,void * &,ushort * *,ITaskHandlerStatus * *)
0x180017ddd  mov     edi, eax
0x180017ddf  lea     pStream, [rbp+40h+taskParams]; this
0x180017de3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017de8  nop
0x180017de9  lea     pStream, [rbp+40h+carrierId]; this
0x180017ded  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017df2  nop
0x180017df3  lea     pStream, [rsp+140h+subscriberId]; this
0x180017df8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017dfd  nop
0x180017dfe  lea     pStream, [rbp+40h+deviceId]; this
0x180017e02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017e07  nop
0x180017e08  test    edi, edi
0x180017e0a  js      short loc_180017E68
0x180017e0c  mov     pStream, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180017e13  cmp     pStream, rsi
0x180017e16  jz      short loc_180017E2F
0x180017e18  test    byte ptr [pStream+1Ch], 10h
0x180017e1c  jz      short loc_180017E2F
0x180017e1e  mov     edx, 23h ; '#'; id
0x180017e23  mov     r8, r14; TraceGuid
0x180017e26  mov     pStream, [pStream+10h]; Logger
0x180017e2a  call    WPP_SF_
0x180017e2f  mov     rdx, [rsp+140h+data.m_str]; _Ptr
0x180017e34  lea     pStream, [rbp+40h+payload]; this
0x180017e38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180017e3d  nop
0x180017e3e  lea     rax, [rbp+40h+deviceId]
0x180017e42  mov     [rsp+140h+var_120], rax; deviceId
0x180017e47  lea     r9, [rsp+140h+subscriberId]; subscriberId
0x180017e4c  lea     r8, [rbp+40h+carrierId]; carrierId
0x180017e50  lea     rdx, [rbp+40h+taskParams]; taskParams
0x180017e54  lea     pStream, [rbp+40h+payload]; data
0x180017e58  call    ?GetActivationTaskParamsFromRegistry@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@111@Z; GetActivationTaskParamsFromRegistry(std::wstring const &,std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x180017e5d  mov     edi, eax
0x180017e5f  lea     pStream, [rbp+40h+payload]; this
0x180017e63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017e68  lea     pStream, [rbp+40h+method]; this
0x180017e6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017e71  nop
0x180017e72  xorps   xmm1, xmm1
0x180017e75  xor     eax, eax
0x180017e77  movups  xmmword ptr [rbp+40h+payload._Mypair._Myval2._Myfirst], xmm1
0x180017e7b  mov     [rbp+40h+payload._Mypair._Myval2._Myend], rax
0x180017e7f  lea     pStream, [rbp+40h+payload]; this
0x180017e83  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x180017e88  nop
0x180017e89  test    edi, edi
0x180017e8b  js      loc_180017FD1
0x180017e91  mov     pStream, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180017e98  cmp     pStream, rsi
0x180017e9b  jz      short loc_180017EB4
0x180017e9d  test    byte ptr [pStream+1Ch], 10h
0x180017ea1  jz      short loc_180017EB4
0x180017ea3  mov     edx, 24h ; '$'; id
0x180017ea8  mov     r8, r14; TraceGuid
0x180017eab  mov     pStream, [pStream+10h]; Logger
0x180017eaf  call    WPP_SF_
0x180017eb4  mov     [rsp+140h+firstAttemptWasFailedReregistration], 0
0x180017eb9  lea     r9, [rsp+140h+firstAttemptWasFailedReregistration]; FirstAttemptWasFailedReregistration
0x180017ebe  lea     r8, [rbp+40h+payload]; Payload
0x180017ec2  lea     rdx, [rbp+40h+method]; Method
0x180017ec6  lea     pStream, [rbp+40h+taskParams]; Data
0x180017eca  call    ?ParseTaskData@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@AEAV?$vector@EV?$allocator@E@std@@@2@AEA_N@Z; ParseTaskData(std::wstring const &,std::wstring &,std::vector<uchar> &,bool &)
0x180017ecf  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180017ed6  cmp     r10, rsi
0x180017ed9  jz      short loc_180017EFF
0x180017edb  test    byte ptr [r10+1Ch], 10h
0x180017ee0  jz      short loc_180017EFF
0x180017ee2  lea     pStream, [rbp+40h+method]; this
0x180017ee6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017eeb  mov     r9, rax; _a1
0x180017eee  mov     edx, 25h ; '%'; id
0x180017ef3  mov     r8, r14; TraceGuid
0x180017ef6  mov     pStream, [r10+10h]; Logger
0x180017efa  call    WPP_SF_S
0x180017eff  lea     r8, aReconnecttonet; "ReconnectToNetwork"
0x180017f06  mov     pStream, r8; _First
0x180017f09  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180017f0e  mov     r9, rax
0x180017f11  lea     pStream, [rbp+40h+method]; this
0x180017f15  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017f1a  mov     pStream, rax; _Left
0x180017f1d  mov     rdx, [rbp+40h+method._Mypair._Myval2._Mysize]; _Left_size
0x180017f21  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180017f26  test    al, al
0x180017f28  jz      loc_1800180B4
0x180017f2e  mov     ebx, 3
0x180017f33  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 20h
0x180017f3a  jz      short loc_180017F73
0x180017f3c  lea     pStream, [rbp+40h+taskParams]; this
0x180017f40  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017f45  mov     r8, rax
0x180017f48  lea     pStream, [rsp+140h+subscriberId]; this
0x180017f4d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017f52  mov     rdx, rax
0x180017f55  lea     pStream, [rbp+40h+carrierId]; this
0x180017f59  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017f5e  mov     r9, rax; _Arg3
0x180017f61  mov     [rsp+140h+Descriptor], r8; Descriptor
0x180017f66  mov     [rsp+140h+var_120], rdx; Context
0x180017f6b  mov     r8d, ebx; _Arg2
0x180017f6e  call    McTemplateU0qzzz_EtwEventWriteTransfer
0x180017f73  mov     r9, [rsp+140h+cancelEvent]; CancelEvent
0x180017f78  mov     r8b, [rsp+140h+firstAttemptWasFailedReregistration]; FirstAttemptWasFailedReregistration
0x180017f7d  lea     rdx, [rbp+40h+deviceId]; DeviceId
0x180017f81  lea     pStream, [rsp+140h+subscriberId]; SubscriberId
0x180017f86  call    ?ReconnectToNetwork@ActivationMethods@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_NPEAX@Z; ActivationMethods::ReconnectToNetwork(std::wstring const &,std::wstring const &,bool,void *)
0x180017f8b  mov     edi, eax
0x180017f8d  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 20h
0x180017f94  jz      short loc_180017FD1
0x180017f96  lea     pStream, [rbp+40h+taskParams]; this
0x180017f9a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017f9f  mov     r8, rax
0x180017fa2  lea     pStream, [rsp+140h+subscriberId]; this
0x180017fa7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017fac  mov     rdx, rax
0x180017faf  lea     pStream, [rbp+40h+carrierId]; this
0x180017fb3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017fb8  mov     [rsp+140h+var_110], edi; Descriptor
0x180017fbc  mov     [rsp+140h+Descriptor], r8; Context
0x180017fc1  mov     r8d, ebx; _Arg2
0x180017fc4  mov     [rsp+140h+var_120], rdx; _Arg4
0x180017fc9  mov     r9, rax; _Arg3
0x180017fcc  call    McTemplateU0qzzzd_EtwEventWriteTransfer
0x180017fd1  mov     r10, cs:WPP_GLOBAL_Control
0x180017fd8  mov     rbx, [rsp+140h+spTaskHandlerStatus.p]
0x180017fdd  test    rbx, rbx
0x180017fe0  jz      short loc_18001801A
0x180017fe2  cmp     r10, rsi; __annotation("TMF:",
0x180017fe5  jz      short loc_180018002
0x180017fe7  test    byte ptr [r10+1Ch], 10h
0x180017fec  jz      short loc_180018002
0x180017fee  mov     edx, 27h ; '''; id
0x180017ff3  mov     r9d, edi; _a1
0x180017ff6  mov     r8, r14; TraceGuid
0x180017ff9  mov     pStream, [r10+10h]; Logger
0x180017ffd  call    WPP_SF_d
0x180018002  mov     rax, [rbx]
0x180018005  mov     edx, edi
0x180018007  mov     pStream, rbx
0x18001800a  mov     rax, [rax+20h]
0x18001800e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018013  mov     r10, cs:WPP_GLOBAL_Control
0x18001801a  cmp     r10, rsi; __annotation("TMF:",
0x18001801d  jz      short loc_18001803B
0x18001801f  test    byte ptr [r10+1Ch], 10h
0x180018024  jz      short loc_18001803B
0x180018026  mov     edx, 28h ; '('; id
0x18001802b  mov     r9d, edi; _a1
0x18001802e  mov     r8, r14; TraceGuid
0x180018031  mov     pStream, [r10+10h]; Logger
0x180018035  call    WPP_SF_d
0x18001803a  nop
0x18001803b  lea     pStream, [rbp+40h+payload]; this
0x18001803f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180018044  nop
0x180018045  lea     pStream, [rbp+40h+method]; this
0x180018049  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001804e  nop
0x18001804f  lea     pStream, [rbp+40h+deviceId]; this
0x180018053  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018058  nop
0x180018059  lea     pStream, [rsp+140h+subscriberId]; this
0x18001805e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018063  nop
0x180018064  lea     pStream, [rbp+40h+carrierId]; this
0x180018068  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001806d  nop
0x18001806e  lea     pStream, [rbp+40h+taskParams]; this
0x180018072  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018077  nop
0x180018078  mov     pStream, [rsp+140h+data.m_str]; bstrString
0x18001807d  call    cs:__imp_SysFreeString
0x180018083  nop
0x180018084  lea     pStream, [rsp+140h+spTaskHandlerStatus]; this
0x180018089  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001808e  mov     eax, edi
0x180018090  mov     pStream, [rbp+40h+var_20]
0x180018094  xor     pStream, rsp; StackCookie
0x180018097  call    __security_check_cookie
0x18001809c  lea     r11, [rsp+140h+var_10]
0x1800180a4  mov     rbx, [r11+28h]
0x1800180a8  mov     rsi, [r11+30h]
0x1800180ac  mov     rsp, r11
0x1800180af  pop     r14
0x1800180b1  pop     rdi
0x1800180b2  pop     rbp
0x1800180b3  retn
0x1800180b4  lea     r8, aReregistertone; "ReregisterToNetwork"
0x1800180bb  mov     pStream, r8; _First
0x1800180be  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800180c3  mov     r9, rax
0x1800180c6  lea     pStream, [rbp+40h+method]; this
0x1800180ca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800180cf  mov     pStream, rax; _Left
0x1800180d2  mov     rdx, [rbp+40h+method._Mypair._Myval2._Mysize]; _Left_size
0x1800180d6  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800180db  test    al, al
0x1800180dd  jz      loc_180018182
0x1800180e3  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 20h
0x1800180ea  jz      short loc_180018126
0x1800180ec  lea     pStream, [rbp+40h+taskParams]; this
0x1800180f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800180f5  mov     r8, rax
0x1800180f8  lea     pStream, [rsp+140h+subscriberId]; this
0x1800180fd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018102  mov     rdx, rax
0x180018105  lea     pStream, [rbp+40h+carrierId]; this
0x180018109  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001810e  mov     r9, rax; _Arg3
0x180018111  mov     [rsp+140h+Descriptor], r8; Descriptor
0x180018116  mov     [rsp+140h+var_120], rdx; Context
0x18001811b  mov     r8d, 2; _Arg2
0x180018121  call    McTemplateU0qzzz_EtwEventWriteTransfer
0x180018126  mov     r9, [rsp+140h+cancelEvent]; CancelEvent
0x18001812b  lea     r8, [rbp+40h+deviceId]; DeviceId
0x18001812f  lea     rdx, [rsp+140h+subscriberId]; SubscriberId
0x180018134  lea     pStream, [rbp+40h+carrierId]; CarrierId
0x180018138  call    ?PerformReregisterToNetwork@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEAX@Z; PerformReregisterToNetwork(std::wstring const &,std::wstring const &,std::wstring const &,void *)
0x18001813d  mov     edi, eax
0x18001813f  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 20h
0x180018146  jz      loc_180017FD1
0x18001814c  lea     pStream, [rbp+40h+taskParams]; this
0x180018150  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018155  mov     r8, rax
0x180018158  lea     pStream, [rsp+140h+subscriberId]; this
0x18001815d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018162  mov     rdx, rax
0x180018165  lea     pStream, [rbp+40h+carrierId]; this
0x180018169  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001816e  mov     [rsp+140h+var_110], edi
0x180018172  mov     [rsp+140h+Descriptor], r8
0x180018177  mov     r8d, 2
0x18001817d  jmp     loc_180017FC4
0x180018182  lea     r8, aServiceactivat; "ServiceActivation"
0x180018189  mov     pStream, r8; _First
0x18001818c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180018191  mov     r9, rax
0x180018194  lea     pStream, [rbp+40h+method]; this
0x180018198  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001819d  mov     pStream, rax; _Left
0x1800181a0  mov     rdx, [rbp+40h+method._Mypair._Myval2._Mysize]; _Left_size
0x1800181a4  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800181a9  test    al, al
0x1800181ab  jz      loc_18001823A
0x1800181b1  mov     ebx, 1
0x1800181b6  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 20h
0x1800181bd  jz      short loc_1800181F6
0x1800181bf  lea     pStream, [rbp+40h+taskParams]; this
0x1800181c3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800181c8  mov     r8, rax
0x1800181cb  lea     pStream, [rsp+140h+subscriberId]; this
0x1800181d0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800181d5  mov     rdx, rax
0x1800181d8  lea     pStream, [rbp+40h+carrierId]; this
0x1800181dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800181e1  mov     r9, rax; _Arg3
0x1800181e4  mov     [rsp+140h+Descriptor], r8; Descriptor
0x1800181e9  mov     [rsp+140h+var_120], rdx; Context
  ... truncated ...
```
