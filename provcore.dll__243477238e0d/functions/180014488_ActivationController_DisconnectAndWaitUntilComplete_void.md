# ActivationController::DisconnectAndWaitUntilComplete(void)

- ea: `0x180014488`
- end: `0x180014821`
- name: `?DisconnectAndWaitUntilComplete@ActivationController@@QEAAJXZ`
- size: `921`
- prototype: `HRESULT __fastcall(ActivationController *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014b98`

## callees

- `0x180002790`
- `0x180009090`
- `0x180009124`
- `0x18000b178`
- `0x18000fa6c`
- `0x180012748`
- `0x180012770`
- `0x180012bc8`
- `0x180012d70`
- `0x180013078`
- `0x180013458`
- `0x1800134c0`
- `0x180014488`
- `0x1800149bc`
- `0x180016dc0`
- `0x1800677d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800144b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800144b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001451a`
- `ext-ms-win-wwan-wwapi-l1-1-3!WwanDisconnect` at `0x180014683`
- `ext-ms-win-wwan-wwapi-l1-1-3!WwanDisconnect` at `0x180014683`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ActivationController::DisconnectAndWaitUntilComplete(ActivationController *this)
{
  WWAN_INTERFACE_OBJECT *EventW; // r14
  signed int LastError; // eax
  int v4; // ebx
  unsigned int v5; // r8d
  unsigned int v6; // r9d
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  int v9; // eax
  const _EVENT_DESCRIPTOR *v10; // rdx
  std::allocator<std::shared_ptr<Notification::Configuration::Node> > *v11; // r8
  WPP_PROJECT_CONTROL_BLOCK *v12; // rcx
  const _EVENT_DESCRIPTOR *v13; // rdx
  _MCGEN_TRACE_CONTEXT *v14; // rcx
  std::shared_ptr<void> result; // [rsp+30h] [rbp-49h] BYREF
  ActivationController::DisconnectAndWaitUntilComplete::__l2::<lambda_2> Code; // [rsp+40h] [rbp-39h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+50h] [rbp-29h] BYREF
  WwanMsmNotificationSubscriptions msmSubscriptions; // [rsp+68h] [rbp-11h] BYREF
  HRESULT hrDisconnect; // [rsp+88h] [rbp+Fh] BYREF

  EventW = (WWAN_INTERFACE_OBJECT *)CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    j.dismissed_ = 0;
    j.fun_ = (void (__fastcall *)(void *))CloseHandle;
    j.p1_ = EventW;
    memset(&msmSubscriptions, 0, sizeof(msmSubscriptions));
    std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&msmSubscriptions);
    msmSubscriptions.m_subscriber = &this->m_subscriber;
    Code.disconnectedEvent = EventW;
    result = 0;
    ___SubscribeToEvent_V_lambda_1___1__DisconnectAndWaitUntilComplete_ActivationController__QEAAJXZ__WwanNotificationSubscriber__QEAA_AV__shared_ptr_X_std__KK__QEAV_lambda_1___1__DisconnectAndWaitUntilComplete_ActivationController__QEAAJXZ__Z(
      &this->m_subscriber,
      (std::shared_ptr<WwanNotificationSubscriber::Unsubscriber> *)&result,
      v5,
      v6,
      (ActivationController::DisconnectAndWaitUntilComplete::__l2::<lambda_1> *)&Code);
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
    hrDisconnect = 0;
    Code.disconnectedEvent = EventW;
    Code.hrDisconnect = &hrDisconnect;
    result = 0;
    ___SubscribeToEvent_V_lambda_2___1__DisconnectAndWaitUntilComplete_ActivationController__QEAAJXZ__WwanNotificationSubscriber__QEAA_AV__shared_ptr_X_std__KK__QEAV_lambda_2___1__DisconnectAndWaitUntilComplete_ActivationController__QEAAJXZ__Z(
      msmSubscriptions.m_subscriber,
      (std::shared_ptr<WwanNotificationSubscriber::Unsubscriber> *)&result,
      v7,
      v8,
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
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x29u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids);
    }
    v9 = WwanDisconnect(this->m_wwan->m_handle, &this->m_interfaceGuid, 0, 0, 0, 0);
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x24u, WPP_785cd9ea59c9302df8b87f94fe851dfa_Traceguids, v4);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v4 == -1073479663 )
    {
      if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v12->ReserveSpace[28] & 0x10) != 0 )
        WPP_SF_(v12->Control.Logger, 0x2Au, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids);
      if ( msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<WcmCommon::Xml::Node>>>(
          (std::shared_ptr<Notification::Configuration::Node> *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst,
          (std::shared_ptr<Notification::Configuration::Node> *const)msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast,
          v11);
        std::_Deallocate<16>(
          msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst,
          ((char *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend
         - (char *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst)
        & 0xFFFFFFFFFFFFFFF0uLL);
        memset(&msmSubscriptions, 0, 24);
      }
      v4 = 0;
    }
    else
    {
      if ( v4 >= 0 )
      {
        if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v12->ReserveSpace[28] & 8) != 0 )
          WPP_SF_(v12->Control.Logger, 0x2Cu, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids);
        v4 = ActivationController::InternalWaitForEvent(this, EventW, 1);
        if ( v4 < 0 || (v4 = hrDisconnect, hrDisconnect < 0) )
        {
          if ( SLOBYTE(Microsoft_Windows_NetworkProvisioningEnableBits[0]) < 0 )
            McTemplateU0jd_EtwEventWriteTransfer(v14, v13, &this->m_interfaceGuid, v4);
        }
      }
      else
      {
        if ( SLOBYTE(Microsoft_Windows_NetworkProvisioningEnableBits[0]) < 0 )
        {
          McTemplateU0jd_EtwEventWriteTransfer((_MCGEN_TRACE_CONTEXT *)v12, v10, &this->m_interfaceGuid, v4);
          v12 = WPP_GLOBAL_Control;
        }
        if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v12->ReserveSpace[28] & 2) != 0 )
          WPP_SF_d(v12->Control.Logger, 0x2Bu, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v4);
      }
      if ( msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<WcmCommon::Xml::Node>>>(
          (std::shared_ptr<Notification::Configuration::Node> *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst,
          (std::shared_ptr<Notification::Configuration::Node> *const)msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast,
          v11);
        std::_Deallocate<16>(
          msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst,
          ((char *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend
         - (char *)msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst)
        & 0xFFFFFFFFFFFFFFF0uLL);
        memset(&msmSubscriptions, 0, 24);
      }
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
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x26u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014488  push    rbp
0x18001448a  push    rbx
0x18001448b  push    rdi
0x18001448c  push    r12
0x18001448e  push    r14
0x180014490  push    r15
0x180014492  lea     rbp, [rsp-2Fh]
0x180014497  sub     rsp, 0A8h
0x18001449e  mov     rax, cs:__security_cookie
0x1800144a5  xor     rax, rsp
0x1800144a8  mov     [rbp+57h+var_40], rax
0x1800144ac  mov     r12, this
0x1800144af  xor     r9d, r9d; lpName
0x1800144b2  xor     r8d, r8d; bInitialState
0x1800144b5  xor     edx, edx; bManualReset
0x1800144b7  xor     ecx, ecx; lpEventAttributes
0x1800144b9  call    cs:__imp_CreateEventW
0x1800144bf  mov     r14, rax
0x1800144c2  test    rax, rax
0x1800144c5  jnz     short loc_18001451A
0x1800144c7  call    cs:__imp_GetLastError
0x1800144cd  mov     ebx, eax
0x1800144cf  test    eax, eax
0x1800144d1  jle     short loc_1800144DC
0x1800144d3  movzx   ebx, ax
0x1800144d6  or      ebx, 80070000h
0x1800144dc  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800144e3  mov     this, cs:WPP_GLOBAL_Control
0x1800144ea  cmp     this, rdi
0x1800144ed  jz      loc_180014802
0x1800144f3  test    byte ptr [this+1Ch], 2
0x1800144f7  jz      loc_180014802
0x1800144fd  mov     edx, 26h ; '&'; id
0x180014502  mov     r9d, ebx; _a1
0x180014505  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x18001450c  mov     this, [this+10h]; Logger
0x180014510  call    WPP_SF_d
0x180014515  jmp     loc_180014802
0x18001451a  mov     rax, cs:__imp_CloseHandle
0x180014521  mov     [rbp+57h+j.dismissed_], 0
0x180014525  mov     [rbp+57h+j.fun_], rax
0x180014529  mov     [rbp+57h+j.p1_], r14
0x18001452d  xorps   xmm0, xmm0
0x180014530  movups  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst], xmm0
0x180014534  movups  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend], xmm0
0x180014538  lea     this, [rbp+57h+msmSubscriptions]; this
0x18001453c  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x180014541  lea     this, [r12+28h]; this
0x180014546  mov     [rbp+57h+msmSubscriptions.m_subscriber], this
0x18001454a  mov     [rbp+57h+var_90.disconnectedEvent], r14
0x18001454e  movups  xmmword ptr [rbp+57h+result._Ptr], xmm0
0x180014552  lea     rax, [rbp+57h+var_90]
0x180014556  mov     [rsp+0D0h+Code], rax; Code
0x18001455b  lea     rdx, [rbp+57h+result]; result
0x18001455f  call    ??$SubscribeToEvent@V_lambda_1_@?1??DisconnectAndWaitUntilComplete@ActivationController@@QEAAJXZ@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_1_@?1??DisconnectAndWaitUntilComplete@ActivationController@@QEAAJXZ@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::DisconnectAndWaitUntilComplete(void)'::`2'::_lambda_1_>(ulong,ulong,`ActivationController::DisconnectAndWaitUntilComplete(void)'::`2'::_lambda_1_ &&)
0x180014564  nop
0x180014565  mov     rbx, [rbp+57h+result._Ptr]
0x180014569  test    rbx, rbx
0x18001456c  jnz     short loc_180014578
0x18001456e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "subscription")
0x180014573  test    rbx, rbx
0x180014576  jz      short loc_1800145A3
0x180014578  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Obj
0x18001457c  cmp     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x180014580  jz      short loc_180014592
0x180014582  lea     rdx, [rbp+57h+result]; <_Args_0>
0x180014586  call    ??$_Construct_in_place@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18001458b  add     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], 10h
0x180014590  jmp     short loc_1800145A3
0x180014592  lea     r8, [rbp+57h+result]; <_Val_0>
0x180014596  mov     rdx, this; _Whereptr
0x180014599  lea     this, [rbp+57h+msmSubscriptions]; this
0x18001459d  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> * const,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x1800145a2  nop
0x1800145a3  mov     this, [rbp+57h+result._Rep]; this
0x1800145a7  test    this, this
0x1800145aa  jz      short loc_1800145B1
0x1800145ac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800145b1  mov     [rbp+57h+hrDisconnect], 0
0x1800145b8  mov     [rbp+57h+var_90.disconnectedEvent], r14
0x1800145bc  lea     rax, [rbp+57h+hrDisconnect]
0x1800145c0  mov     [rbp+57h+var_88], rax
0x1800145c4  xorps   xmm0, xmm0
0x1800145c7  movups  xmmword ptr [rbp+57h+result._Ptr], xmm0
0x1800145cb  lea     rax, [rbp+57h+var_90]
0x1800145cf  mov     [rsp+0D0h+Code], rax; Code
0x1800145d4  lea     rdx, [rbp+57h+result]; result
0x1800145d8  mov     this, [rbp+57h+msmSubscriptions.m_subscriber]; this
0x1800145dc  call    ??$SubscribeToEvent@V_lambda_2_@?1??DisconnectAndWaitUntilComplete@ActivationController@@QEAAJXZ@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_2_@?1??DisconnectAndWaitUntilComplete@ActivationController@@QEAAJXZ@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::DisconnectAndWaitUntilComplete(void)'::`2'::_lambda_2_>(ulong,ulong,`ActivationController::DisconnectAndWaitUntilComplete(void)'::`2'::_lambda_2_ &&)
0x1800145e1  nop
0x1800145e2  mov     rbx, [rbp+57h+result._Ptr]
0x1800145e6  test    rbx, rbx
0x1800145e9  jnz     short loc_1800145F5
0x1800145eb  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "subscription")
0x1800145f0  test    rbx, rbx
0x1800145f3  jz      short loc_180014620
0x1800145f5  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Obj
0x1800145f9  cmp     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x1800145fd  jz      short loc_18001460F
0x1800145ff  lea     rdx, [rbp+57h+result]; <_Args_0>
0x180014603  call    ??$_Construct_in_place@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180014608  add     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], 10h
0x18001460d  jmp     short loc_180014620
0x18001460f  lea     r8, [rbp+57h+result]; <_Val_0>
0x180014613  mov     rdx, this; _Whereptr
0x180014616  lea     this, [rbp+57h+msmSubscriptions]; this
0x18001461a  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> * const,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18001461f  nop
0x180014620  mov     this, [rbp+57h+result._Rep]; this
0x180014624  test    this, this
0x180014627  jz      short loc_18001462E
0x180014629  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001462e  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x180014635  mov     this, cs:WPP_GLOBAL_Control
0x18001463c  cmp     this, rdi
0x18001463f  jz      short loc_18001465C
0x180014641  test    byte ptr [this+1Ch], 8
0x180014645  jz      short loc_18001465C
0x180014647  mov     edx, 29h ; ')'; id
0x18001464c  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180014653  mov     this, [this+10h]; Logger
0x180014657  call    WPP_SF_
0x18001465c  lea     r15, [r12+8]
0x180014661  mov     this, [r12]
0x180014665  mov     [rsp+0D0h+var_A8], 0
0x18001466e  mov     [rsp+0D0h+Code], 0
0x180014677  xor     r9d, r9d
0x18001467a  xor     r8d, r8d
0x18001467d  mov     rdx, r15
0x180014680  mov     this, [this]
0x180014683  call    cs:__imp_WwanDisconnect
0x180014689  mov     ebx, eax
0x18001468b  test    eax, eax
0x18001468d  jle     short loc_180014698
0x18001468f  movzx   ebx, ax
0x180014692  or      ebx, 80070000h
0x180014698  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001469f  cmp     this, rdi
0x1800146a2  jz      short loc_1800146C9
0x1800146a4  test    byte ptr [this+1Ch], 10h
0x1800146a8  jz      short loc_1800146C9
0x1800146aa  mov     edx, 24h ; '$'; id
0x1800146af  mov     r9d, ebx; _a1
0x1800146b2  lea     r8, WPP_785cd9ea59c9302df8b87f94fe851dfa_Traceguids; TraceGuid
0x1800146b9  mov     this, [this+10h]; Logger
0x1800146bd  call    WPP_SF_d
0x1800146c2  mov     this, cs:WPP_GLOBAL_Control; _Arg0
0x1800146c9  cmp     ebx, 0C0040011h
0x1800146cf  jnz     short loc_18001472F
0x1800146d1  cmp     this, rdi; __annotation("TMF:",
0x1800146d4  jz      short loc_1800146F2
0x1800146d6  test    byte ptr [this+1Ch], 10h
0x1800146da  jz      short loc_1800146F2
0x1800146dc  mov     edx, 2Ah ; '*'; id
0x1800146e1  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x1800146e8  mov     this, [this+10h]; Logger
0x1800146ec  call    WPP_SF_
0x1800146f1  nop
0x1800146f2  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst]; _First
0x1800146f6  test    this, this
0x1800146f9  jz      short loc_180014728
0x1800146fb  mov     rdx, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Last
0x1800146ff  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<WcmCommon::Xml::Node>>>(std::shared_ptr<WcmCommon::Xml::Node> *,std::shared_ptr<WcmCommon::Xml::Node> * const,std::allocator<std::shared_ptr<WcmCommon::Xml::Node>> &)
0x180014704  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst]; _Ptr
0x180014708  mov     rdx, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x18001470c  sub     rdx, this
0x18001470f  and     rdx, 0FFFFFFFFFFFFFFF0h; _Bytes
0x180014713  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014718  mov     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst], 0
0x180014720  xorps   xmm0, xmm0
0x180014723  movdqu  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], xmm0
0x180014728  xor     ebx, ebx
0x18001472a  jmp     loc_1800147F9
0x18001472f  test    ebx, ebx
0x180014731  jns     short loc_180014773
0x180014733  cmp     byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 0
0x18001473a  jge     short loc_18001474E
0x18001473c  mov     r9d, ebx; Descriptor
0x18001473f  mov     r8, r15; Context
0x180014742  call    McTemplateU0jd_EtwEventWriteTransfer
0x180014747  mov     this, cs:WPP_GLOBAL_Control
0x18001474e  cmp     this, rdi; __annotation("TMF:",
0x180014751  jz      short loc_1800147C3
0x180014753  test    byte ptr [this+1Ch], 2
0x180014757  jz      short loc_1800147C3
0x180014759  mov     edx, 2Bh ; '+'; id
0x18001475e  mov     r9d, ebx; _a1
0x180014761  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180014768  mov     this, [this+10h]; Logger
0x18001476c  call    WPP_SF_d
0x180014771  jmp     short loc_1800147C3
0x180014773  cmp     this, rdi; __annotation("TMF:",
0x180014776  jz      short loc_180014793
0x180014778  test    byte ptr [this+1Ch], 8
0x18001477c  jz      short loc_180014793
0x18001477e  mov     edx, 2Ch ; ','; id
0x180014783  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x18001478a  mov     this, [this+10h]; Logger
0x18001478e  call    WPP_SF_
0x180014793  mov     r8b, 1; Cancellable
0x180014796  mov     rdx, r14; EventHandle
0x180014799  mov     this, r12; this
0x18001479c  call    ?InternalWaitForEvent@ActivationController@@AEAAJPEAX_N@Z; ActivationController::InternalWaitForEvent(void *,bool)
0x1800147a1  mov     ebx, eax
0x1800147a3  test    eax, eax
0x1800147a5  js      short loc_1800147AE
0x1800147a7  mov     ebx, [rbp+57h+hrDisconnect]
0x1800147aa  test    ebx, ebx
0x1800147ac  jns     short loc_1800147C3
0x1800147ae  cmp     byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 0
0x1800147b5  jge     short loc_1800147C3
0x1800147b7  mov     r9d, ebx; Descriptor
0x1800147ba  mov     r8, r15; Context
0x1800147bd  call    McTemplateU0jd_EtwEventWriteTransfer
0x1800147c2  nop
0x1800147c3  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst]; _First
0x1800147c7  test    this, this
0x1800147ca  jz      short loc_1800147F9
0x1800147cc  mov     rdx, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Last
0x1800147d0  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<WcmCommon::Xml::Node>>>(std::shared_ptr<WcmCommon::Xml::Node> *,std::shared_ptr<WcmCommon::Xml::Node> * const,std::allocator<std::shared_ptr<WcmCommon::Xml::Node>> &)
0x1800147d5  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst]; _Ptr
0x1800147d9  mov     rdx, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x1800147dd  sub     rdx, this
0x1800147e0  and     rdx, 0FFFFFFFFFFFFFFF0h; _Bytes
0x1800147e4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800147e9  xorps   xmm0, xmm0
0x1800147ec  movdqu  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], xmm0
0x1800147f1  mov     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst], 0
0x1800147f9  lea     this, [rbp+57h+j]; j
0x1800147fd  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180014802  mov     eax, ebx
0x180014804  mov     this, [rbp+57h+var_40]
0x180014808  xor     this, rsp; StackCookie
0x18001480b  call    __security_check_cookie
0x180014810  add     rsp, 0A8h
0x180014817  pop     r15
0x180014819  pop     r14
0x18001481b  pop     r12
0x18001481d  pop     rdi
0x18001481e  pop     rbx
0x18001481f  pop     rbp
0x180014820  retn
```
