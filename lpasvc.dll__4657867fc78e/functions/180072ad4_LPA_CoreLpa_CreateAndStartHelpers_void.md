# LPA::CoreLpa::CreateAndStartHelpers(void)

- ea: `0x180072ad4`
- end: `0x180072f7a`
- name: `?CreateAndStartHelpers@CoreLpa@LPA@@AEAAJXZ`
- size: `1190`
- prototype: `__int64 __fastcall(LPA::CoreLpa *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800732e4`

## callees

- `0x18000df90`
- `0x18000e46c`
- `0x1800636dc`
- `0x180065170`
- `0x18006ba8c`
- `0x1800709e4`
- `0x180071a34`
- `0x1800720a4`
- `0x180072110`
- `0x180072198`
- `0x1800721dc`
- `0x1800721e8`
- `0x1800722f0`
- `0x1800723e4`
- `0x1800724d0`
- `0x1800725e4`
- `0x1800726e0`
- `0x180072878`
- `0x180072ad4`
- `0x180072f80`
- `0x1800daa0c`
- `0x1800dacc0`
- `0x1800dad58`
- `0x1800eaf40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072b16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072def`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072e03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072e17`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072e2b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072e3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072b16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072def`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072e03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072e17`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072e2b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072e3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072f3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072f3f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180072dd3`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180072dd3`
- `ntdll!RtlQueryWnfStateData` at `0x180072d90`
- `ntdll!RtlQueryWnfStateData` at `0x180072d90`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180072f1a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180072f1a`
- `wwapi!WwanOpenHandle` at `0x180072b4a`
- `wwapi!WwanOpenHandle` at `0x180072b4a`
- `wwapi!WwanRegisterNotification` at `0x180072d56`
- `wwapi!WwanRegisterNotification` at `0x180072d56`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LPA::CoreLpa::CreateAndStartHelpers(LPA::CoreLpa *this)
{
  _QWORD *v2; // rbx
  HANDLE EventW; // rax
  CommonUtil *v4; // rcx
  __int64 result; // rax
  LPA::CoreLpa *v6; // rdi
  PVOID *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  std::_Ref_count_base *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r8
  CommonUtil *v17; // rcx
  __int64 v18; // r8
  int LastErrorToHResultAndForceFailure; // eax
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 i; // rbx
  HANDLE v30; // rcx
  int v31; // [rsp+40h] [rbp-59h] BYREF
  _DWORD *v32; // [rsp+48h] [rbp-51h] BYREF
  std::_Ref_count_base *v33; // [rsp+50h] [rbp-49h]
  LPA::CoreLpa *v34; // [rsp+58h] [rbp-41h] BYREF
  HANDLE Handles[3]; // [rsp+60h] [rbp-39h] BYREF
  HANDLE v36; // [rsp+78h] [rbp-21h]
  HANDLE v37; // [rsp+80h] [rbp-19h]

  v31 = 0;
  v2 = (_QWORD *)((char *)this + 192);
  EventW = CreateEventW(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v2,
    EventW);
  if ( *v2 )
  {
    LODWORD(v34) = 0;
    result = WwanOpenHandle(1, 0, &v34, (char *)this + 176);
    if ( (int)result > 0 )
      result = (unsigned __int16)result | 0x80070000;
  }
  else
  {
    result = CommonUtil::GetLastErrorToHResultAndForceFailure(v4);
  }
  v31 = result;
  if ( (int)result >= 0 )
  {
    v6 = (LPA::CoreLpa *)operator new(0xA8u);
    v34 = v6;
    *(_OWORD *)v6 = 0;
    *((_DWORD *)v6 + 2) = 1;
    *((_DWORD *)v6 + 3) = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj2<MessageDispatcher>::`vftable';
    std::_Construct_in_place<MessageDispatcher,>((char *)v6 + 16);
    v32 = (_DWORD *)((char *)v6 + 16);
    v33 = v6;
    v7 = (PVOID *)((char *)this + 24);
    std::shared_ptr<LPA::EnterpriseManager>::operator=((char *)this + 24, &v32);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    v8 = std::make_shared<LPA::ApduHelper,void * &,std::shared_ptr<MessageDispatcher> &>(
           &v32,
           (char *)this + 176,
           (char *)this + 24);
    std::shared_ptr<LPA::EnterpriseManager>::operator=((char *)this + 104, v8);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    v9 = std::make_shared<LPA::Lpd,std::shared_ptr<MessageDispatcher> &,std::shared_ptr<LPA::ApduHelper> &>(
           &v32,
           (char *)this + 24,
           (char *)this + 104);
    std::shared_ptr<LPA::EnterpriseManager>::operator=((char *)this + 40, v9);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    v10 = std::make_shared<LPA::EnterpriseManager,std::shared_ptr<MessageDispatcher> &>(&v32, (char *)this + 24);
    std::shared_ptr<LPA::EnterpriseManager>::operator=((char *)this + 88, v10);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    v11 = std::make_shared<LPA::EsimManager,void * &,std::shared_ptr<MessageDispatcher> &,std::shared_ptr<LPA::ApduHelper> &,std::shared_ptr<LPA::Lpd> &,std::shared_ptr<LPA::EnterpriseManager> &>(
            (unsigned int)&v32,
            (int)this + 176,
            (int)this + 24,
            (int)this + 104,
            (__int64)this + 40,
            (__int64)this + 88);
    std::shared_ptr<LPA::EnterpriseManager>::operator=((char *)this + 72, v11);
    v12 = 0;
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    v13 = std::make_shared<LPA::Lui,std::shared_ptr<MessageDispatcher> &,std::shared_ptr<LPA::EsimManager> &,std::shared_ptr<LPA::EnterpriseManager> &>(
            &v32,
            (char *)this + 24,
            (char *)this + 72,
            (char *)this + 88);
    std::shared_ptr<LPA::EnterpriseManager>::operator=((char *)this + 56, v13);
    v14 = v33;
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    result = (unsigned int)v31;
    if ( v31 >= 0 )
    {
      if ( !*((_BYTE *)this + 168) )
      {
        result = LuiApiServer::LuiApiServerInit(v14);
        v31 = result;
      }
      if ( (int)result >= 0 )
      {
        *((_BYTE *)this + 168) = 1;
        v34 = this;
        v15 = msl::safeint3::SafeInt<unsigned __int64,msl::safeint3::SafeIntInternal::SafeIntExceptionHandler<msl::safeint3::SafeIntException>>::SafeInt<unsigned __int64,msl::safeint3::SafeIntInternal::SafeIntExceptionHandler<msl::safeint3::SafeIntException>>(
                &v32,
                &v34,
                *v7);
        std::function_void___cdecl_void__::function_void___cdecl_void____LPA::CoreLpa::CreateAndStartHelpers_::_25_::_lambda_1__0_(
          Handles,
          v15);
        v31 = MessageDispatcher::SetExceptionLambda(v16, Handles);
        `pplx::details::_MakeTToUnitFunc<web::json::value>'::`2'::_lambda_1_::~_lambda_1_(Handles);
        result = (unsigned int)v31;
        if ( v31 >= 0 )
        {
          result = MessageDispatcher::Start(*v7);
          v31 = result;
          if ( (int)result >= 0 )
          {
            LODWORD(v34) = 0;
            result = WwanRegisterNotification(*((_QWORD *)this + 22), 6, LPA::CoreLpa::WwapiNotification, this, 0, &v34);
            if ( (int)result > 0 )
              result = (unsigned __int16)result | 0x80070000;
            v31 = result;
            if ( (int)result >= 0 )
            {
              LODWORD(v34) = 0;
              result = (unsigned int)RtlQueryWnfStateData(
                                       &v34,
                                       WNF_SEB_INTERNET_PRESENT,
                                       LPA::CoreLpa::WnfNotification,
                                       this,
                                       0)
                     | 0x10000000;
              v31 = result;
              if ( (int)result >= 0 )
              {
                result = (unsigned int)RtlSubscribeWnfStateChangeNotification(
                                         (char *)this + 184,
                                         WNF_SEB_INTERNET_PRESENT,
                                         (unsigned int)v34,
                                         LPA::CoreLpa::WnfNotification,
                                         this,
                                         0,
                                         0,
                                         0,
                                         v31)
                       | 0x10000000;
                v31 = result;
                if ( (int)result >= 0 )
                {
                  Handles[0] = CreateEventW(0, 0, 0, 0);
                  Handles[1] = CreateEventW(0, 0, 0, 0);
                  Handles[2] = CreateEventW(0, 0, 0, 0);
                  v36 = CreateEventW(0, 0, 0, 0);
                  v37 = CreateEventW(0, 0, 0, 0);
                  LastErrorToHResultAndForceFailure = v31;
                  do
                  {
                    if ( !Handles[v12] )
                    {
                      LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v17);
                      v31 = LastErrorToHResultAndForceFailure;
                    }
                    ++v12;
                  }
                  while ( v12 != 5 );
                  if ( LastErrorToHResultAndForceFailure >= 0 )
                  {
                    v20 = std::shared_ptr<LPA::EnterpriseManagerInterface>::shared_ptr<LPA::EnterpriseManagerInterface>(
                            &v32,
                            (char *)this + 104,
                            v18,
                            Handles[0]);
                    LPA::CoreLpa::EnqueueLpaHelperStart(this, v20, &v31);
                    v22 = std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(&v32, (char *)this + 40, v21);
                    LPA::CoreLpa::EnqueueLpaHelperStart(this, v22, &v31);
                    v24 = std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(&v32, (char *)this + 88, v23);
                    LPA::CoreLpa::EnqueueLpaHelperStart(this, v24, &v31);
                    v26 = std::shared_ptr<LPA::LpaHelper>::shared_ptr<LPA::LpaHelper>(&v32, (char *)this + 72, v25, v36);
                    LPA::CoreLpa::EnqueueLpaHelperStart(this, v26, &v31);
                    v28 = std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(&v32, (char *)this + 56, v27);
                    LPA::CoreLpa::EnqueueLpaHelperStart(this, v28, &v31);
                    if ( WaitForMultipleObjects(5u, Handles, 1, 0xEA60u) )
                    {
                      v31 = -2147467259;
                      MessageDispatcher::CancelAndWaitForQueueComplete(*v7);
                    }
                  }
                  for ( i = 0; i != 5; ++i )
                  {
                    v30 = Handles[i];
                    if ( v30 )
                    {
                      CloseHandle(v30);
                      Handles[i] = 0;
                    }
                  }
                  return (unsigned int)v31;
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180072ad4  push    rbp
0x180072ad6  push    rbx
0x180072ad7  push    rsi
0x180072ad8  push    rdi
0x180072ad9  push    r12
0x180072adb  push    r13
0x180072add  push    r14
0x180072adf  push    r15
0x180072ae1  lea     rbp, [rsp-1Fh]
0x180072ae6  sub     rsp, 0B8h
0x180072aed  mov     rax, cs:__security_cookie
0x180072af4  xor     rax, rsp
0x180072af7  mov     [rbp+57h+var_50], rax
0x180072afb  mov     rsi, rcx
0x180072afe  xor     r13d, r13d
0x180072b01  mov     [rbp+57h+var_B0], r13d
0x180072b05  lea     rbx, [rcx+0C0h]
0x180072b0c  xor     r9d, r9d; lpName
0x180072b0f  xor     r8d, r8d; bInitialState
0x180072b12  xor     edx, edx; bManualReset
0x180072b14  xor     ecx, ecx; lpEventAttributes
0x180072b16  call    cs:__imp_CreateEventW
0x180072b1c  mov     rdx, rax
0x180072b1f  mov     rcx, rbx
0x180072b22  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180072b27  lea     r14, [rsi+0B0h]
0x180072b2e  cmp     [rbx], r13
0x180072b31  jnz     short loc_180072B3A
0x180072b33  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x180072b38  jmp     short loc_180072B5C
0x180072b3a  mov     dword ptr [rbp+57h+var_98], r13d
0x180072b3e  mov     r9, r14
0x180072b41  lea     r8, [rbp+57h+var_98]
0x180072b45  xor     edx, edx
0x180072b47  lea     ecx, [rdx+1]
0x180072b4a  call    cs:__imp_WwanOpenHandle
0x180072b50  test    eax, eax
0x180072b52  jle     short loc_180072B5C
0x180072b54  movzx   eax, ax
0x180072b57  or      eax, 80070000h
0x180072b5c  mov     [rbp+57h+var_B0], eax
0x180072b5f  test    eax, eax
0x180072b61  js      loc_180072F5A
0x180072b67  mov     ecx, 0A8h; Size
0x180072b6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180072b71  mov     rdi, rax
0x180072b74  mov     [rbp+57h+var_98], rax
0x180072b78  xorps   xmm0, xmm0
0x180072b7b  movups  xmmword ptr [rax], xmm0
0x180072b7e  mov     dword ptr [rax+8], 1
0x180072b85  mov     dword ptr [rax+0Ch], 1
0x180072b8c  lea     rax, ??_7?$_Ref_count_obj2@VMessageDispatcher@@@std@@6B@; const std::_Ref_count_obj2<MessageDispatcher>::`vftable'
0x180072b93  mov     [rdi], rax
0x180072b96  lea     rbx, [rdi+10h]
0x180072b9a  mov     rcx, rbx
0x180072b9d  call    ??$_Construct_in_place@VMessageDispatcher@@$$V@std@@YAXAEAVMessageDispatcher@@@Z; std::_Construct_in_place<MessageDispatcher,>(MessageDispatcher &)
0x180072ba2  nop
0x180072ba3  mov     [rbp+57h+var_A8], rbx
0x180072ba7  mov     [rbp+57h+var_A0], rdi
0x180072bab  lea     rbx, [rsi+18h]
0x180072baf  lea     rdx, [rbp+57h+var_A8]
0x180072bb3  mov     rcx, rbx
0x180072bb6  call    ??4?$shared_ptr@VEnterpriseManager@LPA@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<LPA::EnterpriseManager>::operator=(std::shared_ptr<LPA::EnterpriseManager> &&)
0x180072bbb  mov     rcx, [rbp+57h+var_A0]; this
0x180072bbf  test    rcx, rcx
0x180072bc2  jz      short loc_180072BC9
0x180072bc4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072bc9  mov     r8, rbx
0x180072bcc  mov     rdx, r14
0x180072bcf  lea     rcx, [rbp+57h+var_A8]
0x180072bd3  call    ??$make_shared@VApduHelper@LPA@@AEAPEAXAEAV?$shared_ptr@VMessageDispatcher@@@std@@@std@@YA?AV?$shared_ptr@VApduHelper@LPA@@@0@AEAPEAXAEAV?$shared_ptr@VMessageDispatcher@@@0@@Z; std::make_shared<LPA::ApduHelper,void * &,std::shared_ptr<MessageDispatcher> &>(void * &,std::shared_ptr<MessageDispatcher> &)
0x180072bd8  lea     r12, [rsi+68h]
0x180072bdc  mov     rdx, rax
0x180072bdf  mov     rcx, r12
0x180072be2  call    ??4?$shared_ptr@VEnterpriseManager@LPA@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<LPA::EnterpriseManager>::operator=(std::shared_ptr<LPA::EnterpriseManager> &&)
0x180072be7  mov     rcx, [rbp+57h+var_A0]; this
0x180072beb  test    rcx, rcx
0x180072bee  jz      short loc_180072BF5
0x180072bf0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072bf5  mov     r8, r12
0x180072bf8  mov     rdx, rbx
0x180072bfb  lea     rcx, [rbp+57h+var_A8]
0x180072bff  call    ??$make_shared@VLpd@LPA@@AEAV?$shared_ptr@VMessageDispatcher@@@std@@AEAV?$shared_ptr@VApduHelper@LPA@@@4@@std@@YA?AV?$shared_ptr@VLpd@LPA@@@0@AEAV?$shared_ptr@VMessageDispatcher@@@0@AEAV?$shared_ptr@VApduHelper@LPA@@@0@@Z; std::make_shared<LPA::Lpd,std::shared_ptr<MessageDispatcher> &,std::shared_ptr<LPA::ApduHelper> &>(std::shared_ptr<MessageDispatcher> &,std::shared_ptr<LPA::ApduHelper> &)
0x180072c04  lea     rdi, [rsi+28h]
0x180072c08  mov     rdx, rax
0x180072c0b  mov     rcx, rdi
0x180072c0e  call    ??4?$shared_ptr@VEnterpriseManager@LPA@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<LPA::EnterpriseManager>::operator=(std::shared_ptr<LPA::EnterpriseManager> &&)
0x180072c13  mov     rcx, [rbp+57h+var_A0]; this
0x180072c17  test    rcx, rcx
0x180072c1a  jz      short loc_180072C21
0x180072c1c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072c21  mov     rdx, rbx
0x180072c24  lea     rcx, [rbp+57h+var_A8]
0x180072c28  call    ??$make_shared@VEnterpriseManager@LPA@@AEAV?$shared_ptr@VMessageDispatcher@@@std@@@std@@YA?AV?$shared_ptr@VEnterpriseManager@LPA@@@0@AEAV?$shared_ptr@VMessageDispatcher@@@0@@Z; std::make_shared<LPA::EnterpriseManager,std::shared_ptr<MessageDispatcher> &>(std::shared_ptr<MessageDispatcher> &)
0x180072c2d  lea     r15, [rsi+58h]
0x180072c31  mov     rdx, rax
0x180072c34  mov     rcx, r15
0x180072c37  call    ??4?$shared_ptr@VEnterpriseManager@LPA@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<LPA::EnterpriseManager>::operator=(std::shared_ptr<LPA::EnterpriseManager> &&)
0x180072c3c  mov     rcx, [rbp+57h+var_A0]; this
0x180072c40  test    rcx, rcx
0x180072c43  jz      short loc_180072C4A
0x180072c45  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072c4a  mov     [rsp+0F0h+var_C8], r15
0x180072c4f  mov     [rsp+0F0h+var_D0], rdi
0x180072c54  mov     r9, r12
0x180072c57  mov     r8, rbx
0x180072c5a  mov     rdx, r14
0x180072c5d  lea     rcx, [rbp+57h+var_A8]
0x180072c61  call    ??$make_shared@VEsimManager@LPA@@AEAPEAXAEAV?$shared_ptr@VMessageDispatcher@@@std@@AEAV?$shared_ptr@VApduHelper@LPA@@@4@AEAV?$shared_ptr@VLpd@LPA@@@4@AEAV?$shared_ptr@VEnterpriseManager@LPA@@@4@@std@@YA?AV?$shared_ptr@VEsimManager@LPA@@@0@AEAPEAXAEAV?$shared_ptr@VMessageDispatcher@@@0@AEAV?$shared_ptr@VApduHelper@LPA@@@0@AEAV?$shared_ptr@VLpd@LPA@@@0@AEAV?$shared_ptr@VEnterpriseManager@LPA@@@0@@Z; std::make_shared<LPA::EsimManager,void * &,std::shared_ptr<MessageDispatcher> &,std::shared_ptr<LPA::ApduHelper> &,std::shared_ptr<LPA::Lpd> &,std::shared_ptr<LPA::EnterpriseManager> &>(void * &,std::shared_ptr<MessageDispatcher> &,std::shared_ptr<LPA::ApduHelper> &,std::shared_ptr<LPA::Lpd> &,std::shared_ptr<LPA::EnterpriseManager> &)
0x180072c66  lea     r13, [rsi+48h]
0x180072c6a  mov     rdx, rax
0x180072c6d  mov     rcx, r13
0x180072c70  call    ??4?$shared_ptr@VEnterpriseManager@LPA@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<LPA::EnterpriseManager>::operator=(std::shared_ptr<LPA::EnterpriseManager> &&)
0x180072c75  mov     rcx, [rbp+57h+var_A0]; this
0x180072c79  xor     edi, edi
0x180072c7b  test    rcx, rcx
0x180072c7e  jz      short loc_180072C85
0x180072c80  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072c85  mov     r9, r15
0x180072c88  mov     r8, r13
0x180072c8b  mov     rdx, rbx
0x180072c8e  lea     rcx, [rbp+57h+var_A8]
0x180072c92  call    ??$make_shared@VLui@LPA@@AEAV?$shared_ptr@VMessageDispatcher@@@std@@AEAV?$shared_ptr@VEsimManager@LPA@@@4@AEAV?$shared_ptr@VEnterpriseManager@LPA@@@4@@std@@YA?AV?$shared_ptr@VLui@LPA@@@0@AEAV?$shared_ptr@VMessageDispatcher@@@0@AEAV?$shared_ptr@VEsimManager@LPA@@@0@AEAV?$shared_ptr@VEnterpriseManager@LPA@@@0@@Z; std::make_shared<LPA::Lui,std::shared_ptr<MessageDispatcher> &,std::shared_ptr<LPA::EsimManager> &,std::shared_ptr<LPA::EnterpriseManager> &>(std::shared_ptr<MessageDispatcher> &,std::shared_ptr<LPA::EsimManager> &,std::shared_ptr<LPA::EnterpriseManager> &)
0x180072c97  lea     rcx, [rsi+38h]
0x180072c9b  mov     rdx, rax
0x180072c9e  call    ??4?$shared_ptr@VEnterpriseManager@LPA@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<LPA::EnterpriseManager>::operator=(std::shared_ptr<LPA::EnterpriseManager> &&)
0x180072ca3  mov     rcx, [rbp+57h+var_A0]; this
0x180072ca7  test    rcx, rcx
0x180072caa  jz      short loc_180072CB1
0x180072cac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072cb1  mov     eax, [rbp+57h+var_B0]
0x180072cb4  test    eax, eax
0x180072cb6  js      loc_180072F5A
0x180072cbc  cmp     [rsi+0A8h], dil
0x180072cc3  jnz     short loc_180072CCD
0x180072cc5  call    ?LuiApiServerInit@LuiApiServer@@YAJXZ; LuiApiServer::LuiApiServerInit(void)
0x180072cca  mov     [rbp+57h+var_B0], eax
0x180072ccd  test    eax, eax
0x180072ccf  js      loc_180072F5A
0x180072cd5  mov     byte ptr [rsi+0A8h], 1
0x180072cdc  mov     [rbp+57h+var_98], rsi
0x180072ce0  mov     r8, [rbx]
0x180072ce3  lea     rdx, [rbp+57h+var_98]
0x180072ce7  lea     rcx, [rbp+57h+var_A8]
0x180072ceb  call    ??0?$SafeInt@_KV?$SafeIntExceptionHandler@VSafeIntException@safeint3@msl@@@SafeIntInternal@safeint3@msl@@@safeint3@msl@@QEAA@AEB_K@Z; msl::safeint3::SafeInt<unsigned __int64,msl::safeint3::SafeIntInternal::SafeIntExceptionHandler<msl::safeint3::SafeIntException>>::SafeInt<unsigned __int64,msl::safeint3::SafeIntInternal::SafeIntExceptionHandler<msl::safeint3::SafeIntException>>(unsigned __int64 const &)
0x180072cf0  mov     rdx, rax
0x180072cf3  lea     rcx, [rbp+57h+Handles]
0x180072cf7  call    std__function_void___cdecl_void____function_void___cdecl_void____LPA__CoreLpa__CreateAndStartHelpers____25____lambda_1__0_
0x180072cfc  nop
0x180072cfd  lea     rdx, [rbp+57h+Handles]
0x180072d01  mov     rcx, r8
0x180072d04  call    ?SetExceptionLambda@MessageDispatcher@@QEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; MessageDispatcher::SetExceptionLambda(std::function<void (void)> &&)
0x180072d09  mov     [rbp+57h+var_B0], eax
0x180072d0c  lea     rcx, [rbp+57h+Handles]
0x180072d10  call    ??1_lambda_1_@?1???$_MakeTToUnitFunc@Vvalue@json@web@@@details@pplx@@YA?AV?$function@$$A6AEVvalue@json@web@@@Z@std@@AEBV?$function@$$A6AXVvalue@json@web@@@Z@4@@Z@QEAA@XZ; `pplx::details::_MakeTToUnitFunc<web::json::value>(std::function<void (web::json::value)> const &)'::`2'::_lambda_1_::~_lambda_1_(void)
0x180072d15  mov     eax, [rbp+57h+var_B0]
0x180072d18  test    eax, eax
0x180072d1a  js      loc_180072F5A
0x180072d20  mov     rcx, [rbx]; pvCleanupContext
0x180072d23  call    ?Start@MessageDispatcher@@QEAAJXZ; MessageDispatcher::Start(void)
0x180072d28  mov     [rbp+57h+var_B0], eax
0x180072d2b  test    eax, eax
0x180072d2d  js      loc_180072F5A
0x180072d33  mov     dword ptr [rbp+57h+var_98], edi
0x180072d36  lea     rax, [rbp+57h+var_98]
0x180072d3a  mov     [rsp+0F0h+var_C8], rax
0x180072d3f  mov     [rsp+0F0h+var_D0], rdi
0x180072d44  mov     r9, rsi
0x180072d47  lea     r8, ?WwapiNotification@CoreLpa@LPA@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; LPA::CoreLpa::WwapiNotification(_L2_NOTIFICATION_DATA *,void *)
0x180072d4e  mov     edx, 6
0x180072d53  mov     rcx, [r14]
0x180072d56  call    cs:__imp_WwanRegisterNotification
0x180072d5c  test    eax, eax
0x180072d5e  jle     short loc_180072D68
0x180072d60  movzx   eax, ax
0x180072d63  or      eax, 80070000h
0x180072d68  mov     [rbp+57h+var_B0], eax
0x180072d6b  test    eax, eax
0x180072d6d  js      loc_180072F5A
0x180072d73  mov     dword ptr [rbp+57h+var_98], edi
0x180072d76  mov     [rsp+0F0h+var_D0], rdi
0x180072d7b  mov     r9, rsi
0x180072d7e  lea     r8, ?WnfNotification@CoreLpa@LPA@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; LPA::CoreLpa::WnfNotification(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180072d85  mov     rdx, cs:WNF_SEB_INTERNET_PRESENT
0x180072d8c  lea     rcx, [rbp+57h+var_98]
0x180072d90  call    cs:__imp_RtlQueryWnfStateData
0x180072d96  mov     r14d, 10000000h
0x180072d9c  or      eax, r14d
0x180072d9f  mov     [rbp+57h+var_B0], eax
0x180072da2  jl      loc_180072F5A
0x180072da8  lea     rcx, [rsi+0B8h]
0x180072daf  mov     [rsp+0F0h+var_B8], edi
0x180072db3  mov     [rsp+0F0h+var_C0], edi
0x180072db7  mov     [rsp+0F0h+var_C8], rdi
0x180072dbc  mov     [rsp+0F0h+var_D0], rsi
0x180072dc1  lea     r9, ?WnfNotification@CoreLpa@LPA@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; LPA::CoreLpa::WnfNotification(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180072dc8  mov     r8d, dword ptr [rbp+57h+var_98]
0x180072dcc  mov     rdx, cs:WNF_SEB_INTERNET_PRESENT
0x180072dd3  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180072dd9  or      eax, r14d
0x180072ddc  mov     [rbp+57h+var_B0], eax
0x180072ddf  jl      loc_180072F5A
0x180072de5  xor     r9d, r9d; lpName
0x180072de8  xor     r8d, r8d; bInitialState
0x180072deb  xor     edx, edx; bManualReset
0x180072ded  xor     ecx, ecx; lpEventAttributes
0x180072def  call    cs:__imp_CreateEventW
0x180072df5  mov     [rbp+57h+Handles], rax
0x180072df9  xor     r9d, r9d; lpName
0x180072dfc  xor     r8d, r8d; bInitialState
0x180072dff  xor     edx, edx; bManualReset
0x180072e01  xor     ecx, ecx; lpEventAttributes
0x180072e03  call    cs:__imp_CreateEventW
0x180072e09  mov     [rbp+57h+var_88], rax
0x180072e0d  xor     r9d, r9d; lpName
0x180072e10  xor     r8d, r8d; bInitialState
0x180072e13  xor     edx, edx; bManualReset
0x180072e15  xor     ecx, ecx; lpEventAttributes
0x180072e17  call    cs:__imp_CreateEventW
0x180072e1d  mov     [rbp+57h+var_80], rax
0x180072e21  xor     r9d, r9d; lpName
0x180072e24  xor     r8d, r8d; bInitialState
0x180072e27  xor     edx, edx; bManualReset
0x180072e29  xor     ecx, ecx; lpEventAttributes
0x180072e2b  call    cs:__imp_CreateEventW
0x180072e31  mov     [rbp+57h+var_78], rax
0x180072e35  xor     r9d, r9d; lpName
0x180072e38  xor     r8d, r8d; bInitialState
0x180072e3b  xor     edx, edx; bManualReset
0x180072e3d  xor     ecx, ecx; lpEventAttributes
0x180072e3f  call    cs:__imp_CreateEventW
0x180072e45  mov     [rbp+57h+var_70], rax
0x180072e49  mov     eax, [rbp+57h+var_B0]
0x180072e4c  cmp     [rbp+rdi*8+57h+Handles], 0
0x180072e52  jnz     short loc_180072E5C
0x180072e54  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x180072e59  mov     [rbp+57h+var_B0], eax
0x180072e5c  inc     rdi
0x180072e5f  cmp     rdi, 5
0x180072e63  jnz     short loc_180072E4C
0x180072e65  test    eax, eax
0x180072e67  js      loc_180072F33
0x180072e6d  mov     r9, [rbp+57h+Handles]
0x180072e71  mov     rdx, r12
0x180072e74  lea     rcx, [rbp+57h+var_A8]
0x180072e78  call    ??$?0VEnterpriseManager@LPA@@$0A@@?$shared_ptr@UEnterpriseManagerInterface@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEnterpriseManager@LPA@@@1@@Z; std::shared_ptr<LPA::EnterpriseManagerInterface>::shared_ptr<LPA::EnterpriseManagerInterface>(std::shared_ptr<LPA::EnterpriseManager> const &)
0x180072e7d  lea     r8, [rbp+57h+var_B0]
0x180072e81  mov     rdx, rax
0x180072e84  mov     rcx, rsi
0x180072e87  call    ?EnqueueLpaHelperStart@CoreLpa@LPA@@AEAAXV?$shared_ptr@ULpaHelper@LPA@@@std@@AEAJPEAX@Z; LPA::CoreLpa::EnqueueLpaHelperStart(std::shared_ptr<LPA::LpaHelper>,long &,void *)
0x180072e8c  mov     r9, [rbp+57h+var_88]
0x180072e90  lea     rdx, [rsi+28h]
0x180072e94  lea     rcx, [rbp+57h+var_A8]
0x180072e98  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x180072e9d  lea     r8, [rbp+57h+var_B0]
0x180072ea1  mov     rdx, rax
0x180072ea4  mov     rcx, rsi
0x180072ea7  call    ?EnqueueLpaHelperStart@CoreLpa@LPA@@AEAAXV?$shared_ptr@ULpaHelper@LPA@@@std@@AEAJPEAX@Z; LPA::CoreLpa::EnqueueLpaHelperStart(std::shared_ptr<LPA::LpaHelper>,long &,void *)
0x180072eac  mov     r9, [rbp+57h+var_80]
0x180072eb0  mov     rdx, r15
0x180072eb3  lea     rcx, [rbp+57h+var_A8]
0x180072eb7  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x180072ebc  lea     r8, [rbp+57h+var_B0]
0x180072ec0  mov     rdx, rax
0x180072ec3  mov     rcx, rsi
0x180072ec6  call    ?EnqueueLpaHelperStart@CoreLpa@LPA@@AEAAXV?$shared_ptr@ULpaHelper@LPA@@@std@@AEAJPEAX@Z; LPA::CoreLpa::EnqueueLpaHelperStart(std::shared_ptr<LPA::LpaHelper>,long &,void *)
0x180072ecb  mov     r9, [rbp+57h+var_78]
0x180072ecf  mov     rdx, r13
0x180072ed2  lea     rcx, [rbp+57h+var_A8]
0x180072ed6  call    ??$?0VEsimManager@LPA@@$0A@@?$shared_ptr@ULpaHelper@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::shared_ptr<LPA::LpaHelper>::shared_ptr<LPA::LpaHelper>(std::shared_ptr<LPA::EsimManager> const &)
0x180072edb  lea     r8, [rbp+57h+var_B0]
0x180072edf  mov     rdx, rax
0x180072ee2  mov     rcx, rsi
0x180072ee5  call    ?EnqueueLpaHelperStart@CoreLpa@LPA@@AEAAXV?$shared_ptr@ULpaHelper@LPA@@@std@@AEAJPEAX@Z; LPA::CoreLpa::EnqueueLpaHelperStart(std::shared_ptr<LPA::LpaHelper>,long &,void *)
0x180072eea  mov     r9, [rbp+57h+var_70]
0x180072eee  lea     rdx, [rsi+38h]
0x180072ef2  lea     rcx, [rbp+57h+var_A8]
0x180072ef6  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x180072efb  lea     r8, [rbp+57h+var_B0]
0x180072eff  mov     rdx, rax
0x180072f02  mov     rcx, rsi
0x180072f05  call    ?EnqueueLpaHelperStart@CoreLpa@LPA@@AEAAXV?$shared_ptr@ULpaHelper@LPA@@@std@@AEAJPEAX@Z; LPA::CoreLpa::EnqueueLpaHelperStart(std::shared_ptr<LPA::LpaHelper>,long &,void *)
0x180072f0a  mov     r9d, 0EA60h; dwMilliseconds
0x180072f10  lea     r8d, [rdi-4]; bWaitAll
0x180072f14  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180072f18  mov     ecx, edi; nCount
0x180072f1a  call    cs:__imp_WaitForMultipleObjects
0x180072f20  test    eax, eax
0x180072f22  jz      short loc_180072F33
0x180072f24  mov     [rbp+57h+var_B0], 80004005h
0x180072f2b  mov     rcx, [rbx]; pv
0x180072f2e  call    ?CancelAndWaitForQueueComplete@MessageDispatcher@@QEAAJXZ; MessageDispatcher::CancelAndWaitForQueueComplete(void)
0x180072f33  xor     ebx, ebx
0x180072f35  mov     rcx, [rbp+rbx*8+57h+Handles]; hObject
0x180072f3a  test    rcx, rcx
0x180072f3d  jz      short loc_180072F4E
0x180072f3f  call    cs:__imp_CloseHandle
0x180072f45  mov     [rbp+rbx*8+57h+Handles], 0
0x180072f4e  inc     rbx
0x180072f51  cmp     rbx, 5
  ... truncated ...
```
