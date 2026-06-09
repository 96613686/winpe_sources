# ActivationController::ActivationController(Wwan &,_GUID,void *)

- ea: `0x180013aa0`
- end: `0x180013b98`
- name: `??0ActivationController@@QEAA@AEAVWwan@@U_GUID@@PEAX@Z`
- size: `248`
- prototype: `void __fastcall(ActivationController *this, Wwan *wwan, _GUID InterfaceGuid, void *CancelEvent)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014b98`
- `0x180014f9c`

## callees

- `0x180002b9c`
- `0x18000fa6c`
- `0x180012bf0`
- `0x180013478`
- `0x180013aa0`
- `0x180013fe4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013ada`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013ada`

## pseudocode

```c
void __fastcall ActivationController::ActivationController(
        ActivationController *this,
        Wwan *wwan,
        _GUID *InterfaceGuid,
        void *CancelEvent)
{
  char *v7; // rdi
  unsigned int v8; // r8d
  unsigned int v9; // r9d
  std::shared_ptr<Notification::Configuration::Node> *v10; // rax
  ActivationController::{ctor}::__l2::<lambda_1> Code; // [rsp+30h] [rbp-48h] BYREF
  _GUID v12; // [rsp+40h] [rbp-38h] BYREF
  ActivationController *v13; // [rsp+50h] [rbp-28h]

  v13 = this;
  this->m_wwan = wwan;
  this->m_interfaceGuid = *InterfaceGuid;
  this->m_cancelEvent = CancelEvent;
  this->m_interfaceRemovedEvent = CreateEventW(0, 0, 0, 0);
  v12 = *InterfaceGuid;
  v7 = (char *)operator new(0x40u);
  *(_OWORD *)v7 = 0;
  *((_DWORD *)v7 + 2) = 1;
  *((_DWORD *)v7 + 3) = 1;
  *(_QWORD *)v7 = std::_Ref_count_obj2<WwanNotificationListener>::`vftable';
  std::_Construct_in_place<WwanNotificationListener,Wwan &,_GUID &>((WwanNotificationListener *)(v7 + 16), wwan, &v12);
  this->m_subscriber.m_listener._Ptr = (WwanNotificationListener *)(v7 + 16);
  this->m_subscriber.m_listener._Rep = (std::_Ref_count_base *)v7;
  this->m_interfaceRemovalSubscription._Ptr = 0;
  this->m_interfaceRemovalSubscription._Rep = 0;
  Code.__this = this;
  v10 = (std::shared_ptr<Notification::Configuration::Node> *)Z::SubscribeToEvent<`ActivationController::ActivationController'::`2'::_lambda_1_,AEAVWwan::A * const,_GUID,void *>(
                                                                &this->m_subscriber,
                                                                (std::shared_ptr<void> *)&v12,
                                                                v8,
                                                                v9,
                                                                &Code);
  std::shared_ptr<WcmCommon::Xml::Node>::operator=(
    (std::shared_ptr<Notification::Configuration::Node> *)&this->m_interfaceRemovalSubscription,
    v10);
  if ( *(_QWORD *)v12.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v12.Data4);
}

```

## disassembly

```asm
0x180013aa0  mov     [rsp+arg_8], rbx
0x180013aa5  mov     [rsp+arg_10], rbp
0x180013aaa  push    rsi
0x180013aab  push    rdi
0x180013aac  push    r14
0x180013aae  sub     rsp, 60h
0x180013ab2  mov     rbx, InterfaceGuid
0x180013ab5  mov     rbp, wwan
0x180013ab8  mov     r14, this
0x180013abb  mov     [rsp+78h+var_28], this
0x180013ac0  mov     [this], wwan
0x180013ac3  movaps  xmm0, xmmword ptr [InterfaceGuid]
0x180013ac7  movdqu  xmmword ptr [this+8], xmm0
0x180013acc  mov     [this+18h], CancelEvent
0x180013ad0  xor     r9d, r9d; lpName
0x180013ad3  xor     r8d, r8d; bInitialState
0x180013ad6  xor     edx, edx; bManualReset
0x180013ad8  xor     ecx, ecx; lpEventAttributes
0x180013ada  call    cs:__imp_CreateEventW
0x180013ae0  mov     [r14+20h], rax
0x180013ae4  movaps  xmm0, xmmword ptr [rbx]
0x180013ae7  movdqa  xmmword ptr [rsp+78h+var_38.Data1], xmm0
0x180013aed  mov     ecx, 40h ; '@'; size
0x180013af2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013af7  mov     rdi, rax
0x180013afa  mov     [rsp+78h+var_48.__this], rax
0x180013aff  xorps   xmm0, xmm0
0x180013b02  movups  xmmword ptr [rax], xmm0
0x180013b05  mov     eax, 1
0x180013b0a  mov     [rdi+8], eax
0x180013b0d  mov     [rdi+0Ch], eax
0x180013b10  lea     rax, ??_7?$_Ref_count_obj2@VWwanNotificationListener@@@std@@6B@; const std::_Ref_count_obj2<WwanNotificationListener>::`vftable'
0x180013b17  mov     [rdi], rax
0x180013b1a  lea     rbx, [rdi+10h]
0x180013b1e  lea     InterfaceGuid, [rsp+78h+var_38]; <_Args_1>
0x180013b23  mov     wwan, rbp; <_Args_0>
0x180013b26  mov     this, rbx; _Obj
0x180013b29  call    ??$_Construct_in_place@VWwanNotificationListener@@AEAVWwan@@AEAU_GUID@@@std@@YAXAEAVWwanNotificationListener@@AEAVWwan@@AEAU_GUID@@@Z; std::_Construct_in_place<WwanNotificationListener,Wwan &,_GUID &>(WwanNotificationListener &,Wwan &,_GUID &)
0x180013b2e  nop
0x180013b2f  mov     [r14+28h], rbx
0x180013b33  mov     [r14+30h], rdi
0x180013b37  mov     qword ptr [r14+38h], 0
0x180013b3f  mov     qword ptr [r14+40h], 0
0x180013b47  mov     [rsp+78h+var_48.__this], r14
0x180013b4c  lea     rax, [rsp+78h+var_48]
0x180013b51  mov     [rsp+78h+Code], rax; Code
0x180013b56  lea     wwan, [rsp+78h+var_38]; result
0x180013b5b  lea     this, [r14+28h]; this
0x180013b5f  call    ??$SubscribeToEvent@V_lambda_1_@?1???0ActivationController@@QEAA@AEAVWwan@@U_GUID@@PEAX@Z@@WwanNotificationSubscriber@@QEAA?AV?$shared_ptr@X@std@@KK$$QEAV_lambda_1_@?1???0ActivationController@@QEAA@AEAVWwan@@U_GUID@@PEAX@Z@@Z; WwanNotificationSubscriber::SubscribeToEvent<`ActivationController::ActivationController(Wwan &,_GUID,void *)'::`2'::_lambda_1_>(ulong,ulong,`ActivationController::ActivationController(Wwan &,_GUID,void *)'::`2'::_lambda_1_ &&)
0x180013b64  mov     wwan, rax; _Right
0x180013b67  lea     this, [r14+38h]; this
0x180013b6b  call    ??4?$shared_ptr@VNode@Xml@WcmCommon@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WcmCommon::Xml::Node>::operator=(std::shared_ptr<WcmCommon::Xml::Node> &&)
0x180013b70  mov     this, qword ptr [rsp+78h+var_38.Data4]; this
0x180013b75  test    this, this
0x180013b78  jz      short loc_180013B80
0x180013b7a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180013b7f  nop
0x180013b80  mov     rax, r14
0x180013b83  lea     r11, [rsp+78h+var_18]
0x180013b88  mov     rbx, [r11+28h]
0x180013b8c  mov     rbp, [r11+30h]
0x180013b90  mov     rsp, r11
0x180013b93  pop     r14
0x180013b95  pop     rdi
0x180013b96  pop     rsi
0x180013b97  retn
```
