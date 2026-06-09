# ActivationController::ConnectAndWaitUntilComplete(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180014148`
- end: `0x180014482`
- name: `?ConnectAndWaitUntilComplete@ActivationController@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `826`
- prototype: `HRESULT __fastcall(ActivationController *this, const std::wstring *ProfileName)`
- caller_count: `2`
- callee_count: `18`
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
- `0x180011844`
- `0x180012770`
- `0x1800127cc`
- `0x180012bc8`
- `0x180012cb0`
- `0x180012fb4`
- `0x180013458`
- `0x1800134c0`
- `0x180014148`
- `0x1800149bc`
- `0x180016f04`
- `0x1800453cc`
- `0x1800677d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014184`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014192`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800141e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ActivationController::ConnectAndWaitUntilComplete(
        ActivationController *this,
        const std::wstring *ProfileName)
{
  WWAN_INTERFACE_OBJECT *EventW; // r15
  signed int LastError; // eax
  int v6; // ebx
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  const wchar_t *v11; // rax
  __int64 v12; // r10
  std::allocator<std::shared_ptr<Notification::Configuration::Node> > *v13; // r8
  const wchar_t *v14; // rax
  const _EVENT_DESCRIPTOR *v15; // rdx
  _MCGEN_TRACE_CONTEXT *v16; // rcx
  const wchar_t *v17; // rax
  __int64 v18; // r10
  const wchar_t *v19; // rax
  __int64 v20; // r10
  const wchar_t *v21; // rax
  const _EVENT_DESCRIPTOR *v22; // rdx
  _MCGEN_TRACE_CONTEXT *v23; // rcx
  std::shared_ptr<void> result; // [rsp+30h] [rbp-39h] BYREF
  ActivationController::ConnectAndWaitUntilComplete::__l2::<lambda_2> Code; // [rsp+40h] [rbp-29h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+50h] [rbp-19h] BYREF
  WwanMsmNotificationSubscriptions msmSubscriptions; // [rsp+68h] [rbp-1h] BYREF
  HRESULT hrConnect; // [rsp+88h] [rbp+1Fh] BYREF

  EventW = (WWAN_INTERFACE_OBJECT *)CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    j.dismissed_ = 0;
    j.fun_ = (void (__fastcall *)(void *))CloseHandle;
    j.p1_ = EventW;
    memset(&msmSubscriptions, 0, sizeof(msmSubscriptions));
    std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&msmSubscriptions);
    msmSubscriptions.m_subscriber = &this->m_subscriber;
    Code.connectedEvent = EventW;
    result = 0;
    ___SubscribeToEvent_V_lambda_1___1__ConnectAndWaitUntilComplete_ActivationController__QEAAJAEBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___Z__WwanNotificationSubscriber__QEAA_AV__shared_ptr_X_std__KK__QEAV_lambda_1___1__ConnectAndWaitUntilComplete_ActivationController__QEAAJAEBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__2__Z__Z(
      &this->m_subscriber,
      (std::shared_ptr<WwanNotificationSubscriber::Unsubscriber> *)&result,
      v7,
      v8,
      (ActivationController::ConnectAndWaitUntilComplete::__l2::<lambda_1> *)&Code);
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
    hrConnect = 0;
    Code.connectedEvent = EventW;
    Code.hrConnect = &hrConnect;
    result = 0;
    ___SubscribeToEvent_V_lambda_2___1__ConnectAndWaitUntilComplete_ActivationController__QEAAJAEBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___Z__WwanNotificationSubscriber__QEAA_AV__shared_ptr_X_std__KK__QEAV_lambda_2___1__ConnectAndWaitUntilComplete_ActivationController__QEAAJAEBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__2__Z__Z(
      msmSubscriptions.m_subscriber,
      (std::shared_ptr<WwanNotificationSubscriber::Unsubscriber> *)&result,
      v9,
      v10,
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
      v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&ProfileName->_Mypair._Myval2);
      WPP_SF_S(*(_QWORD *)(v12 + 16), 0x30u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v11);
    }
    v6 = Wwan::Connect(this->m_wwan, &this->m_interfaceGuid, ProfileName);
    if ( v6 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
      {
        v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&ProfileName->_Mypair._Myval2);
        WPP_SF_S(*(_QWORD *)(v20 + 16), 0x32u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v19);
      }
      v6 = ActivationController::InternalWaitForEvent(this, EventW, 1);
      if ( v6 < 0 || (v6 = hrConnect, hrConnect < 0) )
      {
        if ( SLOBYTE(Microsoft_Windows_NetworkProvisioningEnableBits[0]) < 0 )
        {
          v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&ProfileName->_Mypair._Myval2);
          McTemplateU0jzd_EtwEventWriteTransfer(v23, v22, &this->m_interfaceGuid, v21, v6);
        }
      }
    }
    else
    {
      if ( SLOBYTE(Microsoft_Windows_NetworkProvisioningEnableBits[0]) < 0 )
      {
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&ProfileName->_Mypair._Myval2);
        McTemplateU0jzd_EtwEventWriteTransfer(v16, v15, &this->m_interfaceGuid, v14, v6);
      }
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&ProfileName->_Mypair._Myval2);
        WPP_SF_S(*(_QWORD *)(v18 + 16), 0x31u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v17);
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
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x2Du, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v6);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180014148  mov     [rsp-8+arg_10], rbx
0x18001414d  mov     [rsp-8+arg_18], rsi
0x180014152  push    rbp
0x180014153  push    rdi
0x180014154  push    r12
0x180014156  push    r14
0x180014158  push    r15
0x18001415a  lea     rbp, [rsp-37h]
0x18001415f  sub     rsp, 0A0h
0x180014166  mov     rax, cs:__security_cookie
0x18001416d  xor     rax, rsp
0x180014170  mov     [rbp+57h+var_30], rax
0x180014174  mov     r14, ProfileName
0x180014177  mov     r12, this
0x18001417a  xor     r9d, r9d; lpName
0x18001417d  xor     r8d, r8d; bInitialState
0x180014180  xor     edx, edx; bManualReset
0x180014182  xor     ecx, ecx; lpEventAttributes
0x180014184  call    cs:__imp_CreateEventW
0x18001418a  mov     r15, rax
0x18001418d  test    rax, rax
0x180014190  jnz     short loc_1800141E5
0x180014192  call    cs:__imp_GetLastError
0x180014198  mov     ebx, eax
0x18001419a  test    eax, eax
0x18001419c  jle     short loc_1800141A7
0x18001419e  movzx   ebx, ax
0x1800141a1  or      ebx, 80070000h
0x1800141a7  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800141ae  mov     this, cs:WPP_GLOBAL_Control
0x1800141b5  cmp     this, rdi
0x1800141b8  jz      loc_180014458
0x1800141be  test    byte ptr [this+1Ch], 2
0x1800141c2  jz      loc_180014458
0x1800141c8  mov     edx, 2Dh ; '-'; id
0x1800141cd  mov     r9d, ebx; _a1
0x1800141d0  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x1800141d7  mov     this, [this+10h]; Logger
0x1800141db  call    WPP_SF_d
0x1800141e0  jmp     loc_180014458
0x1800141e5  mov     rax, cs:__imp_CloseHandle
0x1800141ec  mov     [rbp+57h+j.dismissed_], 0
0x1800141f0  mov     [rbp+57h+j.fun_], rax
0x1800141f4  mov     [rbp+57h+j.p1_], r15
0x1800141f8  xorps   xmm0, xmm0
0x1800141fb  movups  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst], xmm0
0x1800141ff  movups  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend], xmm0
0x180014203  lea     this, [rbp+57h+msmSubscriptions]; this
0x180014207  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18001420c  lea     this, [r12+28h]; this
0x180014211  mov     [rbp+57h+msmSubscriptions.m_subscriber], this
0x180014215  mov     [rbp+57h+var_80.connectedEvent], r15
0x180014219  movups  xmmword ptr [rbp+57h+result._Ptr], xmm0
0x18001421d  lea     rax, [rbp+57h+var_80]
0x180014221  mov     [rsp+0C0h+Code], rax; Code
0x180014226  lea     ProfileName, [rbp+57h+result]; result
0x18001422a  call    ??$SubscribeToEvent@V_lambda_1_@?1??ConnectAndWaitUntilComplete@ActivationController@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_1_@?1??ConnectAndWaitUntilComplete@ActivationController@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::ConnectAndWaitUntilComplete(std::wstring const &)'::`2'::_lambda_1_>(ulong,ulong,`ActivationController::ConnectAndWaitUntilComplete(std::wstring const &)'::`2'::_lambda_1_ &&)
0x18001422f  nop
0x180014230  mov     rbx, [rbp+57h+result._Ptr]
0x180014234  test    rbx, rbx
0x180014237  jnz     short loc_180014243
0x180014239  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "subscription")
0x18001423e  test    rbx, rbx
0x180014241  jz      short loc_18001426E
0x180014243  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Obj
0x180014247  cmp     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x18001424b  jz      short loc_18001425D
0x18001424d  lea     ProfileName, [rbp+57h+result]; <_Args_0>
0x180014251  call    ??$_Construct_in_place@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180014256  add     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], 10h
0x18001425b  jmp     short loc_18001426E
0x18001425d  lea     r8, [rbp+57h+result]; <_Val_0>
0x180014261  mov     ProfileName, this; _Whereptr
0x180014264  lea     this, [rbp+57h+msmSubscriptions]; this
0x180014268  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> * const,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18001426d  nop
0x18001426e  mov     this, [rbp+57h+result._Rep]; this
0x180014272  test    this, this
0x180014275  jz      short loc_18001427C
0x180014277  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001427c  mov     [rbp+57h+hrConnect], 0
0x180014283  mov     [rbp+57h+var_80.connectedEvent], r15
0x180014287  lea     rax, [rbp+57h+hrConnect]
0x18001428b  mov     [rbp+57h+var_78], rax
0x18001428f  xorps   xmm0, xmm0
0x180014292  movups  xmmword ptr [rbp+57h+result._Ptr], xmm0
0x180014296  lea     rax, [rbp+57h+var_80]
0x18001429a  mov     [rsp+0C0h+Code], rax; Code
0x18001429f  lea     ProfileName, [rbp+57h+result]; result
0x1800142a3  mov     this, [rbp+57h+msmSubscriptions.m_subscriber]; this
0x1800142a7  call    ??$SubscribeToEvent@V_lambda_2_@?1??ConnectAndWaitUntilComplete@ActivationController@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_2_@?1??ConnectAndWaitUntilComplete@ActivationController@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::ConnectAndWaitUntilComplete(std::wstring const &)'::`2'::_lambda_2_>(ulong,ulong,`ActivationController::ConnectAndWaitUntilComplete(std::wstring const &)'::`2'::_lambda_2_ &&)
0x1800142ac  nop
0x1800142ad  mov     rbx, [rbp+57h+result._Ptr]
0x1800142b1  test    rbx, rbx
0x1800142b4  jnz     short loc_1800142C0
0x1800142b6  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "subscription")
0x1800142bb  test    rbx, rbx
0x1800142be  jz      short loc_1800142EB
0x1800142c0  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Obj
0x1800142c4  cmp     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x1800142c8  jz      short loc_1800142DA
0x1800142ca  lea     ProfileName, [rbp+57h+result]; <_Args_0>
0x1800142ce  call    ??$_Construct_in_place@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x1800142d3  add     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], 10h
0x1800142d8  jmp     short loc_1800142EB
0x1800142da  lea     r8, [rbp+57h+result]; <_Val_0>
0x1800142de  mov     ProfileName, this; _Whereptr
0x1800142e1  lea     this, [rbp+57h+msmSubscriptions]; this
0x1800142e5  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> * const,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x1800142ea  nop
0x1800142eb  mov     this, [rbp+57h+result._Rep]; this
0x1800142ef  test    this, this
0x1800142f2  jz      short loc_1800142F9
0x1800142f4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800142f9  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x180014300  mov     r10, cs:WPP_GLOBAL_Control
0x180014307  cmp     r10, rdi
0x18001430a  jz      short loc_180014333
0x18001430c  test    byte ptr [r10+1Ch], 8
0x180014311  jz      short loc_180014333
0x180014313  mov     this, r14; this
0x180014316  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001431b  mov     edx, 30h ; '0'; id
0x180014320  mov     r9, rax; _a1
0x180014323  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x18001432a  mov     this, [r10+10h]; Logger
0x18001432e  call    WPP_SF_S
0x180014333  lea     rsi, [r12+8]
0x180014338  mov     r8, r14; ProfileName
0x18001433b  mov     ProfileName, rsi; InterfaceGuid
0x18001433e  mov     this, [r12]; this
0x180014342  call    ?Connect@Wwan@@QEAAJAEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Wwan::Connect(_GUID const &,std::wstring const &)
0x180014347  mov     ebx, eax
0x180014349  test    eax, eax
0x18001434b  jns     short loc_1800143AA
0x18001434d  cmp     byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 0
0x180014354  jge     short loc_18001436D
0x180014356  mov     this, r14; this
0x180014359  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001435e  mov     dword ptr [rsp+0C0h+Code], ebx; Descriptor
0x180014362  mov     r9, rax; Context
0x180014365  mov     r8, rsi; _Arg2
0x180014368  call    McTemplateU0jzd_EtwEventWriteTransfer
0x18001436d  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180014374  cmp     r10, rdi
0x180014377  jz      loc_180014419
0x18001437d  test    byte ptr [r10+1Ch], 2
0x180014382  jz      loc_180014419
0x180014388  mov     this, r14; this
0x18001438b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014390  mov     edx, 31h ; '1'; id
0x180014395  mov     r9, rax; _a1
0x180014398  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x18001439f  mov     this, [r10+10h]; Logger
0x1800143a3  call    WPP_SF_S
0x1800143a8  jmp     short loc_180014419
0x1800143aa  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800143b1  cmp     r10, rdi
0x1800143b4  jz      short loc_1800143DD
0x1800143b6  test    byte ptr [r10+1Ch], 8
0x1800143bb  jz      short loc_1800143DD
0x1800143bd  mov     this, r14; this
0x1800143c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800143c5  mov     edx, 32h ; '2'; id
0x1800143ca  mov     r9, rax; _a1
0x1800143cd  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x1800143d4  mov     this, [r10+10h]; Logger
0x1800143d8  call    WPP_SF_S
0x1800143dd  mov     r8b, 1; Cancellable
0x1800143e0  mov     ProfileName, r15; EventHandle
0x1800143e3  mov     this, r12; this
0x1800143e6  call    ?InternalWaitForEvent@ActivationController@@AEAAJPEAX_N@Z; ActivationController::InternalWaitForEvent(void *,bool)
0x1800143eb  mov     ebx, eax
0x1800143ed  test    eax, eax
0x1800143ef  js      short loc_1800143F8
0x1800143f1  mov     ebx, [rbp+57h+hrConnect]
0x1800143f4  test    ebx, ebx
0x1800143f6  jns     short loc_180014419
0x1800143f8  cmp     byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 0
0x1800143ff  jge     short loc_180014419
0x180014401  mov     this, r14; this
0x180014404  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014409  mov     dword ptr [rsp+0C0h+Code], ebx; Descriptor
0x18001440d  mov     r9, rax; Context
0x180014410  mov     r8, rsi; _Arg2
0x180014413  call    McTemplateU0jzd_EtwEventWriteTransfer
0x180014418  nop
0x180014419  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst]; _First
0x18001441d  test    this, this
0x180014420  jz      short loc_18001444F
0x180014422  mov     ProfileName, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Last
0x180014426  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<WcmCommon::Xml::Node>>>(std::shared_ptr<WcmCommon::Xml::Node> *,std::shared_ptr<WcmCommon::Xml::Node> * const,std::allocator<std::shared_ptr<WcmCommon::Xml::Node>> &)
0x18001442b  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst]; _Ptr
0x18001442f  mov     ProfileName, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x180014433  sub     ProfileName, this
0x180014436  and     ProfileName, 0FFFFFFFFFFFFFFF0h; _Bytes
0x18001443a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001443f  xorps   xmm0, xmm0
0x180014442  mov     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst], 0
0x18001444a  movdqu  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], xmm0
0x18001444f  lea     this, [rbp+57h+j]; j
0x180014453  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180014458  mov     eax, ebx
0x18001445a  mov     this, [rbp+57h+var_30]
0x18001445e  xor     this, rsp; StackCookie
0x180014461  call    __security_check_cookie
0x180014466  lea     r11, [rsp+0C0h+var_20]
0x18001446e  mov     rbx, [r11+40h]
0x180014472  mov     rsi, [r11+48h]
0x180014476  mov     rsp, r11
0x180014479  pop     r15
0x18001447b  pop     r14
0x18001447d  pop     r12
0x18001447f  pop     rdi
0x180014480  pop     rbp
0x180014481  retn
```
