# ActivationController::TurnRadioOnAndWaitForHomeRegistration(void)

- ea: `0x180015aa4`
- end: `0x180015ebd`
- name: `?TurnRadioOnAndWaitForHomeRegistration@ActivationController@@QEAAJXZ`
- size: `1049`
- prototype: `HRESULT __fastcall(ActivationController *this)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014b98`
- `0x180014f9c`

## callees

- `0x180002790`
- `0x180009090`
- `0x180009124`
- `0x18000b178`
- `0x18000fa6c`
- `0x180012748`
- `0x180012770`
- `0x180012bc8`
- `0x180012ef0`
- `0x1800131fc`
- `0x180013384`
- `0x180013458`
- `0x1800134c0`
- `0x1800149bc`
- `0x180015aa4`
- `0x180016014`
- `0x180016e28`
- `0x180016e90`
- `0x180046780`
- `0x1800677d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015ad5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015b36`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ActivationController::TurnRadioOnAndWaitForHomeRegistration(ActivationController *this)
{
  WWAN_INTERFACE_OBJECT *EventW; // r15
  signed int LastError; // eax
  int v4; // ebx
  unsigned int v5; // r8d
  unsigned int v6; // r9d
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  int v11; // eax
  _MCGEN_TRACE_CONTEXT *v12; // rcx
  std::allocator<std::shared_ptr<Notification::Configuration::Node> > *v13; // r8
  _MCGEN_TRACE_CONTEXT *v14; // rcx
  WPP_PROJECT_CONTROL_BLOCK *v15; // rcx
  _RegisterState v16; // eax
  const _EVENT_DESCRIPTOR *v17; // rdx
  _MCGEN_TRACE_CONTEXT *v18; // rcx
  std::shared_ptr<void> result; // [rsp+30h] [rbp-49h] BYREF
  ActivationController::TurnRadioOnAndWaitForHomeRegistration::__l2::<lambda_1> Code; // [rsp+40h] [rbp-39h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+50h] [rbp-29h] BYREF
  _WWAN_REGISTER_STATE registerState; // [rsp+68h] [rbp-11h] BYREF
  WwanMsmNotificationSubscriptions msmSubscriptions; // [rsp+70h] [rbp-9h] BYREF
  HRESULT hrRegistration; // [rsp+90h] [rbp+17h] BYREF

  EventW = (WWAN_INTERFACE_OBJECT *)CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    j.dismissed_ = 0;
    j.fun_ = (void (__fastcall *)(void *))CloseHandle;
    j.p1_ = EventW;
    memset(&msmSubscriptions, 0, sizeof(msmSubscriptions));
    std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&msmSubscriptions);
    msmSubscriptions.m_subscriber = &this->m_subscriber;
    registerState = WwanRegisterStateUnknown;
    Code.registrationEvent = EventW;
    Code.registerState = &registerState;
    result = 0;
    ___SubscribeToEvent_V_lambda_1___1__TurnRadioOnAndWaitForHomeRegistration_ActivationController__QEAAJXZ__WwanNotificationSubscriber__QEAA_AV__shared_ptr_X_std__KK__QEAV_lambda_1___1__TurnRadioOnAndWaitForHomeRegistration_ActivationController__QEAAJXZ__Z(
      &this->m_subscriber,
      &result,
      v5,
      v6,
      &Code);
    if ( result._Ptr )
    {
      if ( msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast == msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend )
        std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(
          (std::vector<std::shared_ptr<WcmCommon::Xml::Node>> *)&msmSubscriptions,
          (std::shared_ptr<WcmCommon::Xml::Node> *const)msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast,
          (const std::shared_ptr<Notification::Configuration::Node> *)&result);
      else
        std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(
          (std::shared_ptr<Notification::Configuration::Node> *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast++,
          (const std::shared_ptr<Notification::Configuration::Node> *)&result);
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( result._Rep )
      std::_Ref_count_base::_Decref(result._Rep);
    Code.registrationEvent = EventW;
    Code.registerState = &registerState;
    result = 0;
    ___SubscribeToEvent_V_lambda_2___1__TurnRadioOnAndWaitForHomeRegistration_ActivationController__QEAAJXZ__WwanNotificationSubscriber__QEAA_AV__shared_ptr_X_std__KK__QEAV_lambda_2___1__TurnRadioOnAndWaitForHomeRegistration_ActivationController__QEAAJXZ__Z(
      msmSubscriptions.m_subscriber,
      &result,
      v7,
      v8,
      (ActivationController::TurnRadioOnAndWaitForHomeRegistration::__l2::<lambda_2> *)&Code);
    if ( result._Ptr )
    {
      if ( msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast == msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend )
        std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(
          (std::vector<std::shared_ptr<WcmCommon::Xml::Node>> *)&msmSubscriptions,
          (std::shared_ptr<WcmCommon::Xml::Node> *const)msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast,
          (const std::shared_ptr<Notification::Configuration::Node> *)&result);
      else
        std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(
          (std::shared_ptr<Notification::Configuration::Node> *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast++,
          (const std::shared_ptr<Notification::Configuration::Node> *)&result);
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( result._Rep )
      std::_Ref_count_base::_Decref(result._Rep);
    hrRegistration = 0;
    Code.registrationEvent = EventW;
    Code.registerState = (_WWAN_REGISTER_STATE *)&hrRegistration;
    result = 0;
    ___SubscribeToEvent_V_lambda_3___1__TurnRadioOnAndWaitForHomeRegistration_ActivationController__QEAAJXZ__WwanNotificationSubscriber__QEAA_AV__shared_ptr_X_std__KK__QEAV_lambda_3___1__TurnRadioOnAndWaitForHomeRegistration_ActivationController__QEAAJXZ__Z(
      msmSubscriptions.m_subscriber,
      &result,
      v9,
      v10,
      (ActivationController::TurnRadioOnAndWaitForHomeRegistration::__l2::<lambda_3> *)&Code);
    if ( result._Ptr )
    {
      if ( msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast == msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend )
        std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(
          (std::vector<std::shared_ptr<WcmCommon::Xml::Node>> *)&msmSubscriptions,
          (std::shared_ptr<WcmCommon::Xml::Node> *const)msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast,
          (const std::shared_ptr<Notification::Configuration::Node> *)&result);
      else
        std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(
          (std::shared_ptr<Notification::Configuration::Node> *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast++,
          (const std::shared_ptr<Notification::Configuration::Node> *)&result);
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( result._Rep )
      std::_Ref_count_base::_Decref(result._Rep);
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x21u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids);
    }
    v11 = Wwan::SetRadioState(this->m_wwan, &this->m_interfaceGuid, 1);
    v4 = v11;
    if ( v11 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x23u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids);
      }
      v4 = ActivationController::InternalWaitForEvent(this, EventW, 1);
      if ( v4 < 0 || (v4 = hrRegistration, hrRegistration < 0) )
      {
        if ( SLOBYTE(Microsoft_Windows_NetworkProvisioningEnableBits[0]) < 0 )
          McTemplateU0jqd_EtwEventWriteTransfer(v14, &UnableToSetRadioState, &this->m_interfaceGuid, 1u, v4);
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->Control.Logger,
            0x24u,
            WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids,
            registerState);
          v15 = WPP_GLOBAL_Control;
        }
        if ( registerState != WwanRegisterStateHome )
        {
          if ( SLOBYTE(Microsoft_Windows_NetworkProvisioningEnableBits[0]) < 0 )
          {
            v16 = anonymous_namespace_::WwanToEventRegisterState(registerState);
            McTemplateU0jq_EtwEventWriteTransfer(v18, v17, &this->m_interfaceGuid, v16);
            v15 = WPP_GLOBAL_Control;
          }
          if ( v15 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v15->ReserveSpace[28] & 4) != 0 )
            WPP_SF_(v15->Control.Logger, 0x25u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids);
          v4 = -2147019873;
        }
      }
    }
    else
    {
      if ( SLOBYTE(Microsoft_Windows_NetworkProvisioningEnableBits[0]) < 0 )
        McTemplateU0jqd_EtwEventWriteTransfer(v12, &UnableToSetRadioState, &this->m_interfaceGuid, 1u, v11);
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x22u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v4);
      }
    }
    if ( msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst )
    {
      std::_Destroy_range<std::allocator<std::shared_ptr<WcmCommon::Xml::Node>>>(
        (std::shared_ptr<Notification::Configuration::Node> *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst,
        (std::shared_ptr<Notification::Configuration::Node> *const)msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast,
        v13);
      std::_Deallocate<16>(
        msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst,
        ((char *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend
       - (char *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst)
      & 0xFFFFFFFFFFFFFFF0uLL);
      memset(&msmSubscriptions, 0, 24);
    }
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Du, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015aa4  push    rbp
0x180015aa6  push    rbx
0x180015aa7  push    rdi
0x180015aa8  push    r12
0x180015aaa  push    r14
0x180015aac  push    r15
0x180015aae  lea     rbp, [rsp-2Fh]
0x180015ab3  sub     rsp, 0A8h
0x180015aba  mov     rax, cs:__security_cookie
0x180015ac1  xor     rax, rsp
0x180015ac4  mov     [rbp+57h+var_38], rax
0x180015ac8  mov     r12, this
0x180015acb  xor     r9d, r9d; lpName
0x180015ace  xor     r8d, r8d; bInitialState
0x180015ad1  xor     edx, edx; bManualReset
0x180015ad3  xor     ecx, ecx; lpEventAttributes
0x180015ad5  call    cs:__imp_CreateEventW
0x180015adb  mov     r15, rax
0x180015ade  test    rax, rax
0x180015ae1  jnz     short loc_180015B36
0x180015ae3  call    cs:__imp_GetLastError
0x180015ae9  mov     ebx, eax
0x180015aeb  test    eax, eax
0x180015aed  jle     short loc_180015AF8
0x180015aef  movzx   ebx, ax
0x180015af2  or      ebx, 80070000h
0x180015af8  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x180015aff  mov     this, cs:WPP_GLOBAL_Control
0x180015b06  cmp     this, rdi
0x180015b09  jz      loc_180015E9E
0x180015b0f  test    byte ptr [this+1Ch], 2
0x180015b13  jz      loc_180015E9E
0x180015b19  mov     edx, 1Dh; id
0x180015b1e  mov     r9d, ebx; _a1
0x180015b21  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180015b28  mov     this, [this+10h]; Logger
0x180015b2c  call    WPP_SF_d
0x180015b31  jmp     loc_180015E9E
0x180015b36  mov     rax, cs:__imp_CloseHandle
0x180015b3d  mov     [rbp+57h+j.dismissed_], 0
0x180015b41  mov     [rbp+57h+j.fun_], rax
0x180015b45  mov     [rbp+57h+j.p1_], r15
0x180015b49  xorps   xmm0, xmm0
0x180015b4c  movups  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst], xmm0
0x180015b50  movups  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend], xmm0
0x180015b54  lea     this, [rbp+57h+msmSubscriptions]; this
0x180015b58  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x180015b5d  lea     this, [r12+28h]; this
0x180015b62  mov     [rbp+57h+msmSubscriptions.m_subscriber], this
0x180015b66  mov     [rbp+57h+registerState], 0
0x180015b6d  mov     [rbp+57h+var_90.registrationEvent], r15
0x180015b71  lea     rax, [rbp+57h+registerState]
0x180015b75  mov     [rbp+57h+var_90.registerState], rax
0x180015b79  movups  xmmword ptr [rbp+57h+result._Ptr], xmm0
0x180015b7d  lea     rax, [rbp+57h+var_90]
0x180015b81  mov     [rsp+0D0h+Code], rax; Code
0x180015b86  lea     rdx, [rbp+57h+result]; result
0x180015b8a  call    ??$SubscribeToEvent@V_lambda_1_@?1??TurnRadioOnAndWaitForHomeRegistration@ActivationController@@QEAAJXZ@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_1_@?1??TurnRadioOnAndWaitForHomeRegistration@ActivationController@@QEAAJXZ@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::TurnRadioOnAndWaitForHomeRegistration(void)'::`2'::_lambda_1_>(ulong,ulong,`ActivationController::TurnRadioOnAndWaitForHomeRegistration(void)'::`2'::_lambda_1_ &&)
0x180015b8f  nop
0x180015b90  mov     rbx, [rbp+57h+result._Ptr]
0x180015b94  test    rbx, rbx
0x180015b97  jnz     short loc_180015BA3
0x180015b99  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "subscription")
0x180015b9e  test    rbx, rbx
0x180015ba1  jz      short loc_180015BCE
0x180015ba3  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Obj
0x180015ba7  cmp     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x180015bab  jz      short loc_180015BBD
0x180015bad  lea     rdx, [rbp+57h+result]; <_Args_0>
0x180015bb1  call    ??$_Construct_in_place@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180015bb6  add     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], 10h
0x180015bbb  jmp     short loc_180015BCE
0x180015bbd  lea     r8, [rbp+57h+result]; <_Val_0>
0x180015bc1  mov     rdx, this; _Whereptr
0x180015bc4  lea     this, [rbp+57h+msmSubscriptions]; this
0x180015bc8  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> * const,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180015bcd  nop
0x180015bce  mov     this, [rbp+57h+result._Rep]; this
0x180015bd2  test    this, this
0x180015bd5  jz      short loc_180015BDC
0x180015bd7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015bdc  mov     [rbp+57h+var_90.registrationEvent], r15
0x180015be0  lea     rax, [rbp+57h+registerState]
0x180015be4  mov     [rbp+57h+var_90.registerState], rax
0x180015be8  xorps   xmm0, xmm0
0x180015beb  movups  xmmword ptr [rbp+57h+result._Ptr], xmm0
0x180015bef  lea     rax, [rbp+57h+var_90]
0x180015bf3  mov     [rsp+0D0h+Code], rax; Code
0x180015bf8  lea     rdx, [rbp+57h+result]; result
0x180015bfc  mov     this, [rbp+57h+msmSubscriptions.m_subscriber]; this
0x180015c00  call    ??$SubscribeToEvent@V_lambda_2_@?1??TurnRadioOnAndWaitForHomeRegistration@ActivationController@@QEAAJXZ@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_2_@?1??TurnRadioOnAndWaitForHomeRegistration@ActivationController@@QEAAJXZ@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::TurnRadioOnAndWaitForHomeRegistration(void)'::`2'::_lambda_2_>(ulong,ulong,`ActivationController::TurnRadioOnAndWaitForHomeRegistration(void)'::`2'::_lambda_2_ &&)
0x180015c05  nop
0x180015c06  mov     rbx, [rbp+57h+result._Ptr]
0x180015c0a  test    rbx, rbx
0x180015c0d  jnz     short loc_180015C19
0x180015c0f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "subscription")
0x180015c14  test    rbx, rbx
0x180015c17  jz      short loc_180015C44
0x180015c19  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Obj
0x180015c1d  cmp     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x180015c21  jz      short loc_180015C33
0x180015c23  lea     rdx, [rbp+57h+result]; <_Args_0>
0x180015c27  call    ??$_Construct_in_place@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180015c2c  add     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], 10h
0x180015c31  jmp     short loc_180015C44
0x180015c33  lea     r8, [rbp+57h+result]; <_Val_0>
0x180015c37  mov     rdx, this; _Whereptr
0x180015c3a  lea     this, [rbp+57h+msmSubscriptions]; this
0x180015c3e  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> * const,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180015c43  nop
0x180015c44  mov     this, [rbp+57h+result._Rep]; this
0x180015c48  test    this, this
0x180015c4b  jz      short loc_180015C52
0x180015c4d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015c52  mov     [rbp+57h+hrRegistration], 0
0x180015c59  mov     [rbp+57h+var_90.registrationEvent], r15
0x180015c5d  lea     rax, [rbp+57h+hrRegistration]
0x180015c61  mov     [rbp+57h+var_90.registerState], rax
0x180015c65  xorps   xmm0, xmm0
0x180015c68  movups  xmmword ptr [rbp+57h+result._Ptr], xmm0
0x180015c6c  lea     rax, [rbp+57h+var_90]
0x180015c70  mov     [rsp+0D0h+Code], rax; Code
0x180015c75  lea     rdx, [rbp+57h+result]; result
0x180015c79  mov     this, [rbp+57h+msmSubscriptions.m_subscriber]; this
0x180015c7d  call    ??$SubscribeToEvent@V_lambda_3_@?1??TurnRadioOnAndWaitForHomeRegistration@ActivationController@@QEAAJXZ@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_3_@?1??TurnRadioOnAndWaitForHomeRegistration@ActivationController@@QEAAJXZ@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::TurnRadioOnAndWaitForHomeRegistration(void)'::`2'::_lambda_3_>(ulong,ulong,`ActivationController::TurnRadioOnAndWaitForHomeRegistration(void)'::`2'::_lambda_3_ &&)
0x180015c82  nop
0x180015c83  mov     rbx, [rbp+57h+result._Ptr]
0x180015c87  test    rbx, rbx
0x180015c8a  jnz     short loc_180015C96
0x180015c8c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "subscription")
0x180015c91  test    rbx, rbx
0x180015c94  jz      short loc_180015CC1
0x180015c96  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Obj
0x180015c9a  cmp     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x180015c9e  jz      short loc_180015CB0
0x180015ca0  lea     rdx, [rbp+57h+result]; <_Args_0>
0x180015ca4  call    ??$_Construct_in_place@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180015ca9  add     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], 10h
0x180015cae  jmp     short loc_180015CC1
0x180015cb0  lea     r8, [rbp+57h+result]; <_Val_0>
0x180015cb4  mov     rdx, this; _Whereptr
0x180015cb7  lea     this, [rbp+57h+msmSubscriptions]; this
0x180015cbb  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> * const,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180015cc0  nop
0x180015cc1  mov     this, [rbp+57h+result._Rep]; this
0x180015cc5  test    this, this
0x180015cc8  jz      short loc_180015CCF
0x180015cca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015ccf  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x180015cd6  mov     this, cs:WPP_GLOBAL_Control
0x180015cdd  cmp     this, rdi
0x180015ce0  jz      short loc_180015CFD
0x180015ce2  test    byte ptr [this+1Ch], 8
0x180015ce6  jz      short loc_180015CFD
0x180015ce8  mov     edx, 21h ; '!'; id
0x180015ced  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180015cf4  mov     this, [this+10h]; Logger
0x180015cf8  call    WPP_SF_
0x180015cfd  lea     r14, [r12+8]
0x180015d02  mov     r8b, 1; TurnRadioOn
0x180015d05  mov     rdx, r14; InterfaceGuid
0x180015d08  mov     this, [r12]; this
0x180015d0c  call    ?SetRadioState@Wwan@@QEBAJAEBU_GUID@@_N@Z; Wwan::SetRadioState(_GUID const &,bool)
0x180015d11  mov     ebx, eax
0x180015d13  test    eax, eax
0x180015d15  jns     short loc_180015D70
0x180015d17  cmp     byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 0
0x180015d1e  jge     short loc_180015D39
0x180015d20  mov     dword ptr [rsp+0D0h+Code], eax; Context
0x180015d24  mov     r9d, 1; _Arg2
0x180015d2a  mov     r8, r14; _Arg1
0x180015d2d  lea     rdx, UnableToSetRadioState; _Arg0
0x180015d34  call    McTemplateU0jqd_EtwEventWriteTransfer
0x180015d39  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180015d40  cmp     this, rdi
0x180015d43  jz      loc_180015E5F
0x180015d49  test    byte ptr [this+1Ch], 2
0x180015d4d  jz      loc_180015E5F
0x180015d53  mov     edx, 22h ; '"'; id
0x180015d58  mov     r9d, ebx; _a1
0x180015d5b  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180015d62  mov     this, [this+10h]; Logger
0x180015d66  call    WPP_SF_d
0x180015d6b  jmp     loc_180015E5F
0x180015d70  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180015d77  cmp     this, rdi
0x180015d7a  jz      short loc_180015D97
0x180015d7c  test    byte ptr [this+1Ch], 8
0x180015d80  jz      short loc_180015D97
0x180015d82  mov     edx, 23h ; '#'; id
0x180015d87  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180015d8e  mov     this, [this+10h]; Logger
0x180015d92  call    WPP_SF_
0x180015d97  mov     r8b, 1; Cancellable
0x180015d9a  mov     rdx, r15; EventHandle
0x180015d9d  mov     this, r12; this
0x180015da0  call    ?InternalWaitForEvent@ActivationController@@AEAAJPEAX_N@Z; ActivationController::InternalWaitForEvent(void *,bool)
0x180015da5  mov     ebx, eax
0x180015da7  test    eax, eax
0x180015da9  js      loc_180015E3C
0x180015daf  mov     ebx, [rbp+57h+hrRegistration]
0x180015db2  test    ebx, ebx
0x180015db4  js      loc_180015E3C
0x180015dba  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180015dc1  cmp     this, rdi
0x180015dc4  jz      short loc_180015DEC
0x180015dc6  test    byte ptr [this+1Ch], 8
0x180015dca  jz      short loc_180015DEC
0x180015dcc  mov     edx, 24h ; '$'; id
0x180015dd1  mov     r9d, [rbp+57h+registerState]; _a1
0x180015dd5  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180015ddc  mov     this, [this+10h]; Logger
0x180015de0  call    WPP_SF_d
0x180015de5  mov     this, cs:WPP_GLOBAL_Control
0x180015dec  cmp     [rbp+57h+registerState], 3
0x180015df0  jz      short loc_180015E5F
0x180015df2  cmp     byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 0
0x180015df9  jge     short loc_180015E15
0x180015dfb  mov     ecx, [rbp+57h+registerState]; State
0x180015dfe  call    _anonymous_namespace___WwanToEventRegisterState
0x180015e03  mov     r9d, eax; Descriptor
0x180015e06  mov     r8, r14; Context
0x180015e09  call    McTemplateU0jq_EtwEventWriteTransfer
0x180015e0e  mov     this, cs:WPP_GLOBAL_Control
0x180015e15  cmp     this, rdi; __annotation("TMF:",
0x180015e18  jz      short loc_180015E35
0x180015e1a  test    byte ptr [this+1Ch], 4
0x180015e1e  jz      short loc_180015E35
0x180015e20  mov     edx, 25h ; '%'; id
0x180015e25  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180015e2c  mov     this, [this+10h]; Logger
0x180015e30  call    WPP_SF_
0x180015e35  mov     ebx, 8007139Fh
0x180015e3a  jmp     short loc_180015E5F
0x180015e3c  cmp     byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 0
0x180015e43  jge     short loc_180015E5F
0x180015e45  mov     dword ptr [rsp+0D0h+Code], ebx; Context
0x180015e49  mov     r9d, 1; _Arg2
0x180015e4f  mov     r8, r14; _Arg1
0x180015e52  lea     rdx, UnableToSetRadioState; _Arg0
0x180015e59  call    McTemplateU0jqd_EtwEventWriteTransfer
0x180015e5e  nop
0x180015e5f  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst]; _First
0x180015e63  test    this, this
0x180015e66  jz      short loc_180015E95
0x180015e68  mov     rdx, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Last
0x180015e6c  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<WcmCommon::Xml::Node>>>(std::shared_ptr<WcmCommon::Xml::Node> *,std::shared_ptr<WcmCommon::Xml::Node> * const,std::allocator<std::shared_ptr<WcmCommon::Xml::Node>> &)
0x180015e71  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst]; _Ptr
0x180015e75  mov     rdx, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x180015e79  sub     rdx, this
0x180015e7c  and     rdx, 0FFFFFFFFFFFFFFF0h; _Bytes
0x180015e80  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015e85  xorps   xmm0, xmm0
0x180015e88  mov     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst], 0
0x180015e90  movdqu  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], xmm0
0x180015e95  lea     this, [rbp+57h+j]; j
0x180015e99  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180015e9e  mov     eax, ebx
0x180015ea0  mov     this, [rbp+57h+var_38]
0x180015ea4  xor     this, rsp; StackCookie
0x180015ea7  call    __security_check_cookie
0x180015eac  add     rsp, 0A8h
0x180015eb3  pop     r15
0x180015eb5  pop     r14
0x180015eb7  pop     r12
0x180015eb9  pop     rdi
0x180015eba  pop     rbx
0x180015ebb  pop     rbp
0x180015ebc  retn
```
