# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800ece60`
- end: `0x1800ecff5`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `405`
- prototype: `HRESULT __fastcall(Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ed000`

## callees

- `0x1800730a4`
- `0x1800eb63c`
- `0x1800ebf00`
- `0x1800ec828`
- `0x1800ece60`
- `0x1800ed08c`
- `0x1800ed3b8`
- `0x1800ed7b8`
- `0x1800ee608`
- `0x1800ee638`
- `0x1800ee6dc`
- `0x1800ee800`
- `0x1800ee868`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ecf44`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ecf44`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800ecf73`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800ecf73`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)
{
  unsigned int v1; // edi
  unsigned int v3; // edx
  volatile Microsoft::WRL::Details::AsyncStatusInternal currentStatus; // ecx
  const _GUID *v5; // rdx
  bool v6; // dl
  Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *> *ptr; // rdi
  HRESULT v8; // eax
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *v9; // rcx
  Microsoft::WRL::ComPtr<IAsyncInfo> asyncInfo; // [rsp+30h] [rbp-20h] BYREF
  AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *> > b1; // [rsp+38h] [rbp-18h] BYREF
  Microsoft::WRL::Details::AsyncStatusInternal current; // [rsp+70h] [rbp+20h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *> > completedDelegateLocal; // [rsp+78h] [rbp+28h] BYREF
  Microsoft::WRL::ComPtr<IRpcOptions> spRpcOptions; // [rsp+80h] [rbp+30h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *> > operationInterface; // [rsp+88h] [rbp+38h] BYREF

  v1 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    (Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *)this,
    _Completed);
  if ( this->completedDelegateLockCount_ > 0 && _InterlockedExchangeAdd(&this->cCallbackMade_, v3) + 1 == v3 )
  {
    asyncInfo.ptr_ = this;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef((Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler> *)&asyncInfo);
    operationInterface.ptr_ = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete((Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *)this);
    if ( Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>>(
           &asyncInfo,
           (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *> > >)&operationInterface) >= 0 )
    {
      currentStatus = this->currentStatus_;
      current = _Undefined;
      _InterlockedCompareExchange((volatile signed __int32 *)&current, currentStatus, -2);
      completedDelegateLocal.ptr_ = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&completedDelegateLocal);
      if ( Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>::CopyLocal(
             &this->completedDelegate_,
             v5,
             (void **)&completedDelegateLocal.ptr_) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart((Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *)this);
        spRpcOptions.ptr_ = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spRpcOptions);
        RpcOptionsHelper::GetRpcOptions(completedDelegateLocal.ptr_, v6, &spRpcOptions.ptr_);
        b1.spStream_.ptr_ = 0;
        b1.hr_ = 0;
        if ( spRpcOptions.ptr_ && completedDelegateLocal.ptr_ )
        {
          ptr = operationInterface.ptr_;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&b1);
          b1.hr_ = CreateStreamOnHGlobal(0, 1, &b1.spStream_.ptr_);
          if ( b1.hr_ >= 0 )
            b1.hr_ = CoMarshalInterface(b1.spStream_.ptr_, &GUID_00000000_0000_0000_c000_000000000046, ptr, 0, 0, 1u);
        }
        else
        {
          b1.hr_ = -2147467262;
        }
        v8 = completedDelegateLocal.ptr_->Invoke(
               completedDelegateLocal.ptr_,
               operationInterface.ptr_,
               (ABI::Windows::Foundation::AsyncStatus)current);
        v1 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v8,
               completedDelegateLocal.ptr_,
               this->completedDelegateBucketAssist_);
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate((Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *)this);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(v9);
        AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>((AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler> *)&b1);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spRpcOptions);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&completedDelegateLocal);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&operationInterface);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&asyncInfo);
  }
  return v1;
}

```

## disassembly

```asm
0x1800ece60  push    rbp
0x1800ece62  push    rbx
0x1800ece63  push    rdi
0x1800ece64  mov     rbp, rsp
0x1800ece67  sub     rsp, 50h
0x1800ece6b  xor     edi, edi
0x1800ece6d  mov     rbx, this
0x1800ece70  lea     edx, [rdi+1]; newState
0x1800ece73  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800ece78  cmp     [rbx+88h], edi
0x1800ece7e  jle     loc_1800ECFEB
0x1800ece84  mov     eax, edx
0x1800ece86  lock xadd [rbx+10h], eax
0x1800ece8b  inc     eax
0x1800ece8d  cmp     eax, edx
0x1800ece8f  jnz     loc_1800ECFEB
0x1800ece95  lea     this, [rbp+asyncInfo]; this
0x1800ece99  mov     [rbp+asyncInfo.ptr_], rbx
0x1800ece9d  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1800ecea2  mov     this, rbx; this
0x1800ecea5  mov     [rbp+operationInterface.ptr_], rdi
0x1800ecea9  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800eceae  lea     rdx, [rbp+operationInterface]; p
0x1800eceb2  lea     this, [rbp+asyncInfo]; this
0x1800eceb6  call    ??$As@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>>>)
0x1800ecebb  test    eax, eax
0x1800ecebd  js      loc_1800ECFD9
0x1800ecec3  mov     ecx, [rbx+38h]
0x1800ecec6  mov     [rbp+current], 0FFFFFFFEh
0x1800ececd  mov     eax, [rbp+current]
0x1800eced0  lock cmpxchg [rbp+current], ecx
0x1800eced5  lea     this, [rbp+completedDelegateLocal]; this
0x1800eced9  mov     [rbp+completedDelegateLocal.ptr_], rdi
0x1800ecedd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ecee2  lea     this, [rbx+78h]; this
0x1800ecee6  lea     r8, [rbp+completedDelegateLocal]; riid
0x1800eceea  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>::CopyLocal(_GUID const &,void * *)
0x1800eceef  test    eax, eax
0x1800ecef1  js      loc_1800ECFD0
0x1800ecef7  mov     this, rbx; this
0x1800ecefa  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x1800eceff  lea     this, [rbp+spRpcOptions]; this
0x1800ecf03  mov     [rbp+spRpcOptions.ptr_], rdi
0x1800ecf07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ecf0c  mov     this, [rbp+completedDelegateLocal.ptr_]; pInterface
0x1800ecf10  lea     r8, [rbp+spRpcOptions]; pInterface
0x1800ecf14  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1800ecf19  mov     [rbp+b1.spStream_.ptr_], rdi
0x1800ecf1d  mov     [rbp+b1.hr_], edi
0x1800ecf20  cmp     [rbp+spRpcOptions.ptr_], rdi
0x1800ecf24  jz      short loc_1800ECF7E
0x1800ecf26  cmp     [rbp+completedDelegateLocal.ptr_], rdi
0x1800ecf2a  jz      short loc_1800ECF7E
0x1800ecf2c  mov     rdi, [rbp+operationInterface.ptr_]
0x1800ecf30  lea     this, [rbp+b1]; this
0x1800ecf34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ecf39  lea     r8, [rbp+b1]; ppstm
0x1800ecf3d  mov     edx, 1; fDeleteOnRelease
0x1800ecf42  xor     ecx, ecx; hGlobal
0x1800ecf44  call    cs:__imp_CreateStreamOnHGlobal
0x1800ecf4a  mov     [rbp+b1.hr_], eax
0x1800ecf4d  test    eax, eax
0x1800ecf4f  js      short loc_1800ECF85
0x1800ecf51  mov     this, [rbp+b1.spStream_.ptr_]; pStm
0x1800ecf55  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800ecf5c  mov     [rsp+50h+mshlflags], 1; mshlflags
0x1800ecf64  xor     r9d, r9d; dwDestContext
0x1800ecf67  mov     r8, rdi; pUnk
0x1800ecf6a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x1800ecf73  call    cs:__imp_CoMarshalInterface
0x1800ecf79  mov     [rbp+b1.hr_], eax
0x1800ecf7c  jmp     short loc_1800ECF85
0x1800ecf7e  mov     [rbp+b1.hr_], 80004002h
0x1800ecf85  mov     this, [rbp+completedDelegateLocal.ptr_]
0x1800ecf89  mov     r8d, [rbp+current]
0x1800ecf8d  mov     rdx, [rbp+operationInterface.ptr_]
0x1800ecf91  mov     rax, [this]
0x1800ecf94  mov     rax, [rax+18h]
0x1800ecf98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecf9d  mov     r8, [rbx+80h]; pfnBucketAssist
0x1800ecfa4  mov     ecx, eax; hrIn
0x1800ecfa6  mov     rdx, [rbp+completedDelegateLocal.ptr_]; handler
0x1800ecfaa  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800ecfaf  mov     this, rbx; this
0x1800ecfb2  mov     edi, eax
0x1800ecfb4  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800ecfb9  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800ecfbe  lea     this, [rbp+b1]; this
0x1800ecfc2  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>(void)
0x1800ecfc7  lea     this, [rbp+spRpcOptions]; this
0x1800ecfcb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ecfd0  lea     this, [rbp+completedDelegateLocal]; this
0x1800ecfd4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ecfd9  lea     this, [rbp+operationInterface]; this
0x1800ecfdd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ecfe2  lea     this, [rbp+asyncInfo]; this
0x1800ecfe6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ecfeb  mov     eax, edi
0x1800ecfed  add     rsp, 50h
0x1800ecff1  pop     rdi
0x1800ecff2  pop     rbx
0x1800ecff3  pop     rbp
0x1800ecff4  retn
```
