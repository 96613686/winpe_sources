# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800f9700`
- end: `0x1800f98a2`
- name: `?FireCompletion@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `418`
- prototype: `HRESULT __fastcall(Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f98b0`

## callees

- `0x1800719e4`
- `0x1800ee120`
- `0x1800ef35c`
- `0x1800ef6d8`
- `0x1800efaec`
- `0x1800f09e8`
- `0x1800f0a1c`
- `0x1800f0ac0`
- `0x1800f0be4`
- `0x1800f0c50`
- `0x1800f8da8`
- `0x1800f9370`
- `0x1800f9700`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f97e4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f97e4`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800f9819`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800f9819`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)
{
  unsigned int v1; // edi
  unsigned int v3; // edx
  volatile Microsoft::WRL::Details::AsyncStatusInternal currentStatus; // ecx
  const _GUID *v5; // rdx
  bool v6; // dl
  Windows::Foundation::IAsyncAction *ptr; // rdi
  HRESULT v8; // eax
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *v9; // rcx
  Microsoft::WRL::ComPtr<IAsyncInfo> asyncInfo; // [rsp+30h] [rbp-20h] BYREF
  AutoStubBias<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler> b1; // [rsp+38h] [rbp-18h] BYREF
  Microsoft::WRL::Details::AsyncStatusInternal current; // [rsp+70h] [rbp+20h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler> completedDelegateLocal; // [rsp+78h] [rbp+28h] BYREF
  Microsoft::WRL::ComPtr<IRpcOptions> spRpcOptions; // [rsp+80h] [rbp+30h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction> operationInterface; // [rsp+88h] [rbp+38h] BYREF

  v1 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    this,
    _Completed);
  if ( this->completedDelegateLockCount_ > 0 && _InterlockedExchangeAdd(&this->cCallbackMade_, v3) + 1 == v3 )
  {
    asyncInfo.ptr_ = this;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef((Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler> *)&asyncInfo);
    operationInterface.ptr_ = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(this);
    if ( Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncAction>(
           &asyncInfo,
           (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction> >)&operationInterface) >= 0 )
    {
      currentStatus = this->currentStatus_;
      current = _Undefined;
      _InterlockedCompareExchange((volatile signed __int32 *)&current, currentStatus, -2);
      completedDelegateLocal.ptr_ = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&completedDelegateLocal);
      if ( Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncActionCompletedHandler>::CopyLocal(
             &this->completedDelegate_,
             v5,
             (void **)&completedDelegateLocal.ptr_) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(this);
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
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(this);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(v9);
        AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>(&b1);
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
0x1800f9700  push    rbp
0x1800f9702  push    rbx
0x1800f9703  push    rdi
0x1800f9704  mov     rbp, rsp
0x1800f9707  sub     rsp, 50h
0x1800f970b  xor     edi, edi
0x1800f970d  mov     rbx, this
0x1800f9710  lea     edx, [rdi+1]; newState
0x1800f9713  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800f9718  cmp     [rbx+88h], edi
0x1800f971e  jle     loc_1800F9897
0x1800f9724  mov     eax, edx
0x1800f9726  lock xadd [rbx+10h], eax
0x1800f972b  inc     eax
0x1800f972d  cmp     eax, edx
0x1800f972f  jnz     loc_1800F9897
0x1800f9735  lea     this, [rbp+asyncInfo]; this
0x1800f9739  mov     [rbp+asyncInfo.ptr_], rbx
0x1800f973d  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1800f9742  mov     this, rbx; this
0x1800f9745  mov     [rbp+operationInterface.ptr_], rdi
0x1800f9749  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800f974e  lea     rdx, [rbp+operationInterface]; p
0x1800f9752  lea     this, [rbp+asyncInfo]; this
0x1800f9756  call    ??$As@UIAsyncAction@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncAction>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>)
0x1800f975b  test    eax, eax
0x1800f975d  js      loc_1800F9885
0x1800f9763  mov     ecx, [rbx+38h]
0x1800f9766  mov     [rbp+current], 0FFFFFFFEh
0x1800f976d  mov     eax, [rbp+current]
0x1800f9770  lock cmpxchg [rbp+current], ecx
0x1800f9775  lea     this, [rbp+completedDelegateLocal]; this
0x1800f9779  mov     [rbp+completedDelegateLocal.ptr_], rdi
0x1800f977d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f9782  lea     this, [rbx+78h]; this
0x1800f9786  lea     r8, [rbp+completedDelegateLocal]; riid
0x1800f978a  call    ?CopyLocal@?$GitPtrSupportsAgile@UIAsyncActionCompletedHandler@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncActionCompletedHandler>::CopyLocal(_GUID const &,void * *)
0x1800f978f  test    eax, eax
0x1800f9791  js      loc_1800F987C
0x1800f9797  mov     this, rbx; this
0x1800f979a  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SaveToFileAsyncOperationName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SaveToFileAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x1800f979f  lea     this, [rbp+spRpcOptions]; this
0x1800f97a3  mov     [rbp+spRpcOptions.ptr_], rdi
0x1800f97a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f97ac  mov     this, [rbp+completedDelegateLocal.ptr_]; pInterface
0x1800f97b0  lea     r8, [rbp+spRpcOptions]; pInterface
0x1800f97b4  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1800f97b9  mov     [rbp+b1.spStream_.ptr_], rdi
0x1800f97bd  mov     [rbp+b1.hr_], edi
0x1800f97c0  cmp     [rbp+spRpcOptions.ptr_], rdi
0x1800f97c4  jz      short loc_1800F982A
0x1800f97c6  cmp     [rbp+completedDelegateLocal.ptr_], rdi
0x1800f97ca  jz      short loc_1800F982A
0x1800f97cc  mov     rdi, [rbp+operationInterface.ptr_]
0x1800f97d0  lea     this, [rbp+b1]; this
0x1800f97d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f97d9  lea     r8, [rbp+b1]; ppstm
0x1800f97dd  mov     edx, 1; fDeleteOnRelease
0x1800f97e2  xor     ecx, ecx; hGlobal
0x1800f97e4  call    cs:__imp_CreateStreamOnHGlobal
0x1800f97eb  nop     dword ptr [rax+rax+00h]
0x1800f97f0  mov     [rbp+b1.hr_], eax
0x1800f97f3  test    eax, eax
0x1800f97f5  js      short loc_1800F9831
0x1800f97f7  mov     this, [rbp+b1.spStream_.ptr_]; pStm
0x1800f97fb  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800f9802  mov     [rsp+50h+mshlflags], 1; mshlflags
0x1800f980a  xor     r9d, r9d; dwDestContext
0x1800f980d  mov     r8, rdi; pUnk
0x1800f9810  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x1800f9819  call    cs:__imp_CoMarshalInterface
0x1800f9820  nop     dword ptr [rax+rax+00h]
0x1800f9825  mov     [rbp+b1.hr_], eax
0x1800f9828  jmp     short loc_1800F9831
0x1800f982a  mov     [rbp+b1.hr_], 80004002h
0x1800f9831  mov     this, [rbp+completedDelegateLocal.ptr_]
0x1800f9835  mov     r8d, [rbp+current]
0x1800f9839  mov     rdx, [rbp+operationInterface.ptr_]
0x1800f983d  mov     rax, [this]
0x1800f9840  mov     rax, [rax+18h]
0x1800f9844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9849  mov     r8, [rbx+80h]; pfnBucketAssist
0x1800f9850  mov     ecx, eax; hrIn
0x1800f9852  mov     rdx, [rbp+completedDelegateLocal.ptr_]; handler
0x1800f9856  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800f985b  mov     this, rbx; this
0x1800f985e  mov     edi, eax
0x1800f9860  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800f9865  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800f986a  lea     this, [rbp+b1]; this
0x1800f986e  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>>(void)
0x1800f9873  lea     this, [rbp+spRpcOptions]; this
0x1800f9877  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f987c  lea     this, [rbp+completedDelegateLocal]; this
0x1800f9880  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f9885  lea     this, [rbp+operationInterface]; this
0x1800f9889  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f988e  lea     this, [rbp+asyncInfo]; this
0x1800f9892  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f9897  mov     eax, edi
0x1800f9899  add     rsp, 50h
0x1800f989d  pop     rdi
0x1800f989e  pop     rbx
0x1800f989f  pop     rbp
0x1800f98a0  retn
```
