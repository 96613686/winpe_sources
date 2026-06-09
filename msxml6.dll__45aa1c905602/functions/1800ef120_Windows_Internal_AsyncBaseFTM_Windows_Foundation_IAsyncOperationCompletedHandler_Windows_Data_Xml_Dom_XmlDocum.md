# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800ef120`
- end: `0x1800ef2c2`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `418`
- prototype: `HRESULT __fastcall(Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ef2d0`

## callees

- `0x1800719e4`
- `0x1800ed820`
- `0x1800ee120`
- `0x1800eeaa8`
- `0x1800ef120`
- `0x1800ef35c`
- `0x1800ef6d8`
- `0x1800efaec`
- `0x1800f09e8`
- `0x1800f0a1c`
- `0x1800f0ac0`
- `0x1800f0be4`
- `0x1800f0c50`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ef204`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ef204`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800ef239`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800ef239`

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
0x1800ef120  push    rbp
0x1800ef122  push    rbx
0x1800ef123  push    rdi
0x1800ef124  mov     rbp, rsp
0x1800ef127  sub     rsp, 50h
0x1800ef12b  xor     edi, edi
0x1800ef12d  mov     rbx, this
0x1800ef130  lea     edx, [rdi+1]; newState
0x1800ef133  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800ef138  cmp     [rbx+88h], edi
0x1800ef13e  jle     loc_1800EF2B7
0x1800ef144  mov     eax, edx
0x1800ef146  lock xadd [rbx+10h], eax
0x1800ef14b  inc     eax
0x1800ef14d  cmp     eax, edx
0x1800ef14f  jnz     loc_1800EF2B7
0x1800ef155  lea     this, [rbp+asyncInfo]; this
0x1800ef159  mov     [rbp+asyncInfo.ptr_], rbx
0x1800ef15d  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1800ef162  mov     this, rbx; this
0x1800ef165  mov     [rbp+operationInterface.ptr_], rdi
0x1800ef169  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800ef16e  lea     rdx, [rbp+operationInterface]; p
0x1800ef172  lea     this, [rbp+asyncInfo]; this
0x1800ef176  call    ??$As@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>>>)
0x1800ef17b  test    eax, eax
0x1800ef17d  js      loc_1800EF2A5
0x1800ef183  mov     ecx, [rbx+38h]
0x1800ef186  mov     [rbp+current], 0FFFFFFFEh
0x1800ef18d  mov     eax, [rbp+current]
0x1800ef190  lock cmpxchg [rbp+current], ecx
0x1800ef195  lea     this, [rbp+completedDelegateLocal]; this
0x1800ef199  mov     [rbp+completedDelegateLocal.ptr_], rdi
0x1800ef19d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ef1a2  lea     this, [rbx+78h]; this
0x1800ef1a6  lea     r8, [rbp+completedDelegateLocal]; riid
0x1800ef1aa  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>::CopyLocal(_GUID const &,void * *)
0x1800ef1af  test    eax, eax
0x1800ef1b1  js      loc_1800EF29C
0x1800ef1b7  mov     this, rbx; this
0x1800ef1ba  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x1800ef1bf  lea     this, [rbp+spRpcOptions]; this
0x1800ef1c3  mov     [rbp+spRpcOptions.ptr_], rdi
0x1800ef1c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ef1cc  mov     this, [rbp+completedDelegateLocal.ptr_]; pInterface
0x1800ef1d0  lea     r8, [rbp+spRpcOptions]; pInterface
0x1800ef1d4  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1800ef1d9  mov     [rbp+b1.spStream_.ptr_], rdi
0x1800ef1dd  mov     [rbp+b1.hr_], edi
0x1800ef1e0  cmp     [rbp+spRpcOptions.ptr_], rdi
0x1800ef1e4  jz      short loc_1800EF24A
0x1800ef1e6  cmp     [rbp+completedDelegateLocal.ptr_], rdi
0x1800ef1ea  jz      short loc_1800EF24A
0x1800ef1ec  mov     rdi, [rbp+operationInterface.ptr_]
0x1800ef1f0  lea     this, [rbp+b1]; this
0x1800ef1f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ef1f9  lea     r8, [rbp+b1]; ppstm
0x1800ef1fd  mov     edx, 1; fDeleteOnRelease
0x1800ef202  xor     ecx, ecx; hGlobal
0x1800ef204  call    cs:__imp_CreateStreamOnHGlobal
0x1800ef20b  nop     dword ptr [rax+rax+00h]
0x1800ef210  mov     [rbp+b1.hr_], eax
0x1800ef213  test    eax, eax
0x1800ef215  js      short loc_1800EF251
0x1800ef217  mov     this, [rbp+b1.spStream_.ptr_]; pStm
0x1800ef21b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800ef222  mov     [rsp+50h+mshlflags], 1; mshlflags
0x1800ef22a  xor     r9d, r9d; dwDestContext
0x1800ef22d  mov     r8, rdi; pUnk
0x1800ef230  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x1800ef239  call    cs:__imp_CoMarshalInterface
0x1800ef240  nop     dword ptr [rax+rax+00h]
0x1800ef245  mov     [rbp+b1.hr_], eax
0x1800ef248  jmp     short loc_1800EF251
0x1800ef24a  mov     [rbp+b1.hr_], 80004002h
0x1800ef251  mov     this, [rbp+completedDelegateLocal.ptr_]
0x1800ef255  mov     r8d, [rbp+current]
0x1800ef259  mov     rdx, [rbp+operationInterface.ptr_]
0x1800ef25d  mov     rax, [this]
0x1800ef260  mov     rax, [rax+18h]
0x1800ef264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef269  mov     r8, [rbx+80h]; pfnBucketAssist
0x1800ef270  mov     ecx, eax; hrIn
0x1800ef272  mov     rdx, [rbp+completedDelegateLocal.ptr_]; handler
0x1800ef276  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800ef27b  mov     this, rbx; this
0x1800ef27e  mov     edi, eax
0x1800ef280  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800ef285  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800ef28a  lea     this, [rbp+b1]; this
0x1800ef28e  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>(void)
0x1800ef293  lea     this, [rbp+spRpcOptions]; this
0x1800ef297  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ef29c  lea     this, [rbp+completedDelegateLocal]; this
0x1800ef2a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ef2a5  lea     this, [rbp+operationInterface]; this
0x1800ef2a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ef2ae  lea     this, [rbp+asyncInfo]; this
0x1800ef2b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ef2b7  mov     eax, edi
0x1800ef2b9  add     rsp, 50h
0x1800ef2bd  pop     rdi
0x1800ef2be  pop     rbx
0x1800ef2bf  pop     rbp
0x1800ef2c0  retn
```
