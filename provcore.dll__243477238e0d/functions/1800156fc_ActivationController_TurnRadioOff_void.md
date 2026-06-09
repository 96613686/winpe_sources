# ActivationController::TurnRadioOff(void)

- ea: `0x1800156fc`
- end: `0x180015a9e`
- name: `?TurnRadioOff@ActivationController@@QEAAJXZ`
- size: `930`
- prototype: `HRESULT __fastcall(ActivationController *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

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
- `0x180012e30`
- `0x18001313c`
- `0x1800132c0`
- `0x180013458`
- `0x1800134c0`
- `0x1800149bc`
- `0x1800156fc`
- `0x180016e90`
- `0x180046780`
- `0x1800677d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001572d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001572d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001573b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001573b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001578e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ActivationController::TurnRadioOff(ActivationController *this)
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
  std::shared_ptr<void> result; // [rsp+30h] [rbp-49h] BYREF
  ActivationController::TurnRadioOff::__l2::<lambda_3> Code; // [rsp+40h] [rbp-39h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+50h] [rbp-29h] BYREF
  WwanMsmNotificationSubscriptions msmSubscriptions; // [rsp+68h] [rbp-11h] BYREF
  HRESULT hrRadioOff; // [rsp+88h] [rbp+Fh] BYREF

  EventW = (WWAN_INTERFACE_OBJECT *)CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    j.dismissed_ = 0;
    j.fun_ = (void (__fastcall *)(void *))CloseHandle;
    j.p1_ = EventW;
    memset(&msmSubscriptions, 0, sizeof(msmSubscriptions));
    std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&msmSubscriptions);
    msmSubscriptions.m_subscriber = &this->m_subscriber;
    Code.radioOffEvent = EventW;
    result = 0;
    ___SubscribeToEvent_V_lambda_1___1__TurnRadioOff_ActivationController__QEAAJXZ__WwanNotificationSubscriber__QEAA_AV__shared_ptr_X_std__KK__QEAV_lambda_1___1__TurnRadioOff_ActivationController__QEAAJXZ__Z(
      &this->m_subscriber,
      &result,
      v5,
      v6,
      (ActivationController::TurnRadioOff::__l2::<lambda_1> *)&Code);
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
    Code.radioOffEvent = EventW;
    result = 0;
    ___SubscribeToEvent_V_lambda_2___1__TurnRadioOff_ActivationController__QEAAJXZ__WwanNotificationSubscriber__QEAA_AV__shared_ptr_X_std__KK__QEAV_lambda_2___1__TurnRadioOff_ActivationController__QEAAJXZ__Z(
      msmSubscriptions.m_subscriber,
      &result,
      v7,
      v8,
      (ActivationController::TurnRadioOff::__l2::<lambda_2> *)&Code);
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
    hrRadioOff = 0;
    Code.radioOffEvent = EventW;
    Code.hrRadioOff = &hrRadioOff;
    result = 0;
    ___SubscribeToEvent_V_lambda_3___1__TurnRadioOff_ActivationController__QEAAJXZ__WwanNotificationSubscriber__QEAA_AV__shared_ptr_X_std__KK__QEAV_lambda_3___1__TurnRadioOff_ActivationController__QEAAJXZ__Z(
      msmSubscriptions.m_subscriber,
      &result,
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
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids);
    }
    v11 = Wwan::SetRadioState(this->m_wwan, &this->m_interfaceGuid, 0);
    v4 = v11;
    if ( v11 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Bu, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids);
      }
      v4 = ActivationController::InternalWaitForEvent(this, EventW, 0);
      if ( v4 < 0 || (v4 = hrRadioOff, hrRadioOff < 0) )
      {
        v14 = (_MCGEN_TRACE_CONTEXT *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Cu, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v4);
        }
        if ( SLOBYTE(Microsoft_Windows_NetworkProvisioningEnableBits[0]) < 0 )
          McTemplateU0jqd_EtwEventWriteTransfer(v14, &UnableToSetRadioState, &this->m_interfaceGuid, 2u, v4);
      }
    }
    else
    {
      if ( SLOBYTE(Microsoft_Windows_NetworkProvisioningEnableBits[0]) < 0 )
        McTemplateU0jqd_EtwEventWriteTransfer(v12, &UnableToSetRadioState, &this->m_interfaceGuid, 2u, v11);
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Au, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v4);
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
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x15u, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids, v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800156fc  push    rbp
0x1800156fe  push    rbx
0x1800156ff  push    rdi
0x180015700  push    r12
0x180015702  push    r14
0x180015704  push    r15
0x180015706  lea     rbp, [rsp-2Fh]
0x18001570b  sub     rsp, 0A8h
0x180015712  mov     rax, cs:__security_cookie
0x180015719  xor     rax, rsp
0x18001571c  mov     [rbp+57h+var_40], rax
0x180015720  mov     r12, this
0x180015723  xor     r9d, r9d; lpName
0x180015726  xor     r8d, r8d; bInitialState
0x180015729  xor     edx, edx; bManualReset
0x18001572b  xor     ecx, ecx; lpEventAttributes
0x18001572d  call    cs:__imp_CreateEventW
0x180015733  mov     r15, rax
0x180015736  test    rax, rax
0x180015739  jnz     short loc_18001578E
0x18001573b  call    cs:__imp_GetLastError
0x180015741  mov     ebx, eax
0x180015743  test    eax, eax
0x180015745  jle     short loc_180015750
0x180015747  movzx   ebx, ax
0x18001574a  or      ebx, 80070000h
0x180015750  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x180015757  mov     this, cs:WPP_GLOBAL_Control
0x18001575e  cmp     this, rdi
0x180015761  jz      loc_180015A7F
0x180015767  test    byte ptr [this+1Ch], 2
0x18001576b  jz      loc_180015A7F
0x180015771  mov     edx, 15h; id
0x180015776  mov     r9d, ebx; _a1
0x180015779  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180015780  mov     this, [this+10h]; Logger
0x180015784  call    WPP_SF_d
0x180015789  jmp     loc_180015A7F
0x18001578e  mov     rax, cs:__imp_CloseHandle
0x180015795  mov     [rbp+57h+j.dismissed_], 0
0x180015799  mov     [rbp+57h+j.fun_], rax
0x18001579d  mov     [rbp+57h+j.p1_], r15
0x1800157a1  xorps   xmm0, xmm0
0x1800157a4  movups  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst], xmm0
0x1800157a8  movups  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend], xmm0
0x1800157ac  lea     this, [rbp+57h+msmSubscriptions]; this
0x1800157b0  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x1800157b5  lea     this, [r12+28h]; this
0x1800157ba  mov     [rbp+57h+msmSubscriptions.m_subscriber], this
0x1800157be  mov     [rbp+57h+var_90.radioOffEvent], r15
0x1800157c2  movups  xmmword ptr [rbp+57h+result._Ptr], xmm0
0x1800157c6  lea     rax, [rbp+57h+var_90]
0x1800157ca  mov     [rsp+0D0h+Code], rax; Code
0x1800157cf  lea     rdx, [rbp+57h+result]; result
0x1800157d3  call    ??$SubscribeToEvent@V_lambda_1_@?1??TurnRadioOff@ActivationController@@QEAAJXZ@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_1_@?1??TurnRadioOff@ActivationController@@QEAAJXZ@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::TurnRadioOff(void)'::`2'::_lambda_1_>(ulong,ulong,`ActivationController::TurnRadioOff(void)'::`2'::_lambda_1_ &&)
0x1800157d8  nop
0x1800157d9  mov     rbx, [rbp+57h+result._Ptr]
0x1800157dd  test    rbx, rbx
0x1800157e0  jnz     short loc_1800157EC
0x1800157e2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "subscription")
0x1800157e7  test    rbx, rbx
0x1800157ea  jz      short loc_180015817
0x1800157ec  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Obj
0x1800157f0  cmp     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x1800157f4  jz      short loc_180015806
0x1800157f6  lea     rdx, [rbp+57h+result]; <_Args_0>
0x1800157fa  call    ??$_Construct_in_place@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x1800157ff  add     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], 10h
0x180015804  jmp     short loc_180015817
0x180015806  lea     r8, [rbp+57h+result]; <_Val_0>
0x18001580a  mov     rdx, this; _Whereptr
0x18001580d  lea     this, [rbp+57h+msmSubscriptions]; this
0x180015811  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> * const,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180015816  nop
0x180015817  mov     this, [rbp+57h+result._Rep]; this
0x18001581b  test    this, this
0x18001581e  jz      short loc_180015825
0x180015820  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015825  mov     [rbp+57h+var_90.radioOffEvent], r15
0x180015829  xorps   xmm0, xmm0
0x18001582c  movups  xmmword ptr [rbp+57h+result._Ptr], xmm0
0x180015830  lea     rax, [rbp+57h+var_90]
0x180015834  mov     [rsp+0D0h+Code], rax; Code
0x180015839  lea     rdx, [rbp+57h+result]; result
0x18001583d  mov     this, [rbp+57h+msmSubscriptions.m_subscriber]; this
0x180015841  call    ??$SubscribeToEvent@V_lambda_2_@?1??TurnRadioOff@ActivationController@@QEAAJXZ@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_2_@?1??TurnRadioOff@ActivationController@@QEAAJXZ@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::TurnRadioOff(void)'::`2'::_lambda_2_>(ulong,ulong,`ActivationController::TurnRadioOff(void)'::`2'::_lambda_2_ &&)
0x180015846  nop
0x180015847  mov     rbx, [rbp+57h+result._Ptr]
0x18001584b  test    rbx, rbx
0x18001584e  jnz     short loc_18001585A
0x180015850  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "subscription")
0x180015855  test    rbx, rbx
0x180015858  jz      short loc_180015885
0x18001585a  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Obj
0x18001585e  cmp     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x180015862  jz      short loc_180015874
0x180015864  lea     rdx, [rbp+57h+result]; <_Args_0>
0x180015868  call    ??$_Construct_in_place@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x18001586d  add     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], 10h
0x180015872  jmp     short loc_180015885
0x180015874  lea     r8, [rbp+57h+result]; <_Val_0>
0x180015878  mov     rdx, this; _Whereptr
0x18001587b  lea     this, [rbp+57h+msmSubscriptions]; this
0x18001587f  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> * const,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180015884  nop
0x180015885  mov     this, [rbp+57h+result._Rep]; this
0x180015889  test    this, this
0x18001588c  jz      short loc_180015893
0x18001588e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015893  mov     [rbp+57h+hrRadioOff], 0
0x18001589a  mov     [rbp+57h+var_90.radioOffEvent], r15
0x18001589e  lea     rax, [rbp+57h+hrRadioOff]
0x1800158a2  mov     [rbp+57h+var_88], rax
0x1800158a6  xorps   xmm0, xmm0
0x1800158a9  movups  xmmword ptr [rbp+57h+result._Ptr], xmm0
0x1800158ad  lea     rax, [rbp+57h+var_90]
0x1800158b1  mov     [rsp+0D0h+Code], rax; Code
0x1800158b6  lea     rdx, [rbp+57h+result]; result
0x1800158ba  mov     this, [rbp+57h+msmSubscriptions.m_subscriber]; this
0x1800158be  call    ??$SubscribeToEvent@V_lambda_3_@?1??TurnRadioOff@ActivationController@@QEAAJXZ@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_3_@?1??TurnRadioOff@ActivationController@@QEAAJXZ@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::TurnRadioOff(void)'::`2'::_lambda_3_>(ulong,ulong,`ActivationController::TurnRadioOff(void)'::`2'::_lambda_3_ &&)
0x1800158c3  nop
0x1800158c4  mov     rbx, [rbp+57h+result._Ptr]
0x1800158c8  test    rbx, rbx
0x1800158cb  jnz     short loc_1800158D7
0x1800158cd  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "subscription")
0x1800158d2  test    rbx, rbx
0x1800158d5  jz      short loc_180015902
0x1800158d7  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Obj
0x1800158db  cmp     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x1800158df  jz      short loc_1800158F1
0x1800158e1  lea     rdx, [rbp+57h+result]; <_Args_0>
0x1800158e5  call    ??$_Construct_in_place@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<WcmCommon::Xml::Node>,std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> &,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x1800158ea  add     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], 10h
0x1800158ef  jmp     short loc_180015902
0x1800158f1  lea     r8, [rbp+57h+result]; <_Val_0>
0x1800158f5  mov     rdx, this; _Whereptr
0x1800158f8  lea     this, [rbp+57h+msmSubscriptions]; this
0x1800158fc  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<WcmCommon::Xml::Node>>::_Emplace_reallocate<std::shared_ptr<WcmCommon::Xml::Node> const &>(std::shared_ptr<WcmCommon::Xml::Node> * const,std::shared_ptr<WcmCommon::Xml::Node> const &)
0x180015901  nop
0x180015902  mov     this, [rbp+57h+result._Rep]; this
0x180015906  test    this, this
0x180015909  jz      short loc_180015910
0x18001590b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015910  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x180015917  mov     this, cs:WPP_GLOBAL_Control
0x18001591e  cmp     this, rdi
0x180015921  jz      short loc_18001593E
0x180015923  test    byte ptr [this+1Ch], 8
0x180015927  jz      short loc_18001593E
0x180015929  mov     edx, 19h; id
0x18001592e  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180015935  mov     this, [this+10h]; Logger
0x180015939  call    WPP_SF_
0x18001593e  lea     r14, [r12+8]
0x180015943  xor     r8d, r8d; TurnRadioOn
0x180015946  mov     rdx, r14; InterfaceGuid
0x180015949  mov     this, [r12]; this
0x18001594d  call    ?SetRadioState@Wwan@@QEBAJAEBU_GUID@@_N@Z; Wwan::SetRadioState(_GUID const &,bool)
0x180015952  mov     ebx, eax
0x180015954  test    eax, eax
0x180015956  jns     short loc_1800159B1
0x180015958  cmp     byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 0
0x18001595f  jge     short loc_18001597A
0x180015961  mov     dword ptr [rsp+0D0h+Code], eax; Context
0x180015965  mov     r9d, 2; _Arg2
0x18001596b  mov     r8, r14; _Arg1
0x18001596e  lea     rdx, UnableToSetRadioState; _Arg0
0x180015975  call    McTemplateU0jqd_EtwEventWriteTransfer
0x18001597a  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180015981  cmp     this, rdi
0x180015984  jz      loc_180015A40
0x18001598a  test    byte ptr [this+1Ch], 2
0x18001598e  jz      loc_180015A40
0x180015994  mov     edx, 1Ah; id
0x180015999  mov     r9d, ebx; _a1
0x18001599c  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x1800159a3  mov     this, [this+10h]; Logger
0x1800159a7  call    WPP_SF_d
0x1800159ac  jmp     loc_180015A40
0x1800159b1  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800159b8  cmp     this, rdi
0x1800159bb  jz      short loc_1800159D8
0x1800159bd  test    byte ptr [this+1Ch], 8
0x1800159c1  jz      short loc_1800159D8
0x1800159c3  mov     edx, 1Bh; id
0x1800159c8  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x1800159cf  mov     this, [this+10h]; Logger
0x1800159d3  call    WPP_SF_
0x1800159d8  xor     r8d, r8d; Cancellable
0x1800159db  mov     rdx, r15; EventHandle
0x1800159de  mov     this, r12; this
0x1800159e1  call    ?InternalWaitForEvent@ActivationController@@AEAAJPEAX_N@Z; ActivationController::InternalWaitForEvent(void *,bool)
0x1800159e6  mov     ebx, eax
0x1800159e8  test    eax, eax
0x1800159ea  js      short loc_1800159F3
0x1800159ec  mov     ebx, [rbp+57h+hrRadioOff]
0x1800159ef  test    ebx, ebx
0x1800159f1  jns     short loc_180015A40
0x1800159f3  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800159fa  cmp     this, rdi
0x1800159fd  jz      short loc_180015A1D
0x1800159ff  test    byte ptr [this+1Ch], 2
0x180015a03  jz      short loc_180015A1D
0x180015a05  mov     edx, 1Ch; id
0x180015a0a  mov     r9d, ebx; _a1
0x180015a0d  lea     r8, WPP_9fa83f2fdf5c31ca74c96452841c9779_Traceguids; TraceGuid
0x180015a14  mov     this, [this+10h]; Logger
0x180015a18  call    WPP_SF_d
0x180015a1d  cmp     byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits, 0
0x180015a24  jge     short loc_180015A40
0x180015a26  mov     dword ptr [rsp+0D0h+Code], ebx; Context
0x180015a2a  mov     r9d, 2; _Arg2
0x180015a30  mov     r8, r14; _Arg1
0x180015a33  lea     rdx, UnableToSetRadioState; _Arg0
0x180015a3a  call    McTemplateU0jqd_EtwEventWriteTransfer
0x180015a3f  nop
0x180015a40  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst]; _First
0x180015a44  test    this, this
0x180015a47  jz      short loc_180015A76
0x180015a49  mov     rdx, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast]; _Last
0x180015a4d  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VNode@Xml@WcmCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<WcmCommon::Xml::Node>>>(std::shared_ptr<WcmCommon::Xml::Node> *,std::shared_ptr<WcmCommon::Xml::Node> * const,std::allocator<std::shared_ptr<WcmCommon::Xml::Node>> &)
0x180015a52  mov     this, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst]; _Ptr
0x180015a56  mov     rdx, [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myend]
0x180015a5a  sub     rdx, this
0x180015a5d  and     rdx, 0FFFFFFFFFFFFFFF0h; _Bytes
0x180015a61  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015a66  xorps   xmm0, xmm0
0x180015a69  mov     [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Myfirst], 0
0x180015a71  movdqu  xmmword ptr [rbp+57h+msmSubscriptions.m_subscriptions._Mypair._Myval2._Mylast], xmm0
0x180015a76  lea     this, [rbp+57h+j]; j
0x180015a7a  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180015a7f  mov     eax, ebx
0x180015a81  mov     this, [rbp+57h+var_40]
0x180015a85  xor     this, rsp; StackCookie
0x180015a88  call    __security_check_cookie
0x180015a8d  add     rsp, 0A8h
0x180015a94  pop     r15
0x180015a96  pop     r14
0x180015a98  pop     r12
0x180015a9a  pop     rdi
0x180015a9b  pop     rbx
0x180015a9c  pop     rbp
0x180015a9d  retn
```
