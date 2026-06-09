# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18017fc60`
- end: `0x18017fe02`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180180110`

## callees

- `0x18000dcd4`
- `0x180012b74`
- `0x18017b45c`
- `0x18017db84`
- `0x18017f1b8`
- `0x18017fc60`
- `0x1801801e0`
- `0x180180e18`
- `0x180182ac8`
- `0x180182af8`
- `0x180182b9c`
- `0x180182fa0`
- `0x1801830c4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18017fd45`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18017fd45`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18017fd74`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18017fd74`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rdx
  bool v5; // dl
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v11; // [rsp+40h] [rbp-10h]
  unsigned int v12; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v13; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v14; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SetAllConstantsForInputTypeToDefaultAsyncCasualityName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = a1;
    wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<HSTRING__ *> *>>(
                &v9,
                &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v13) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const SetAllConstantsForInputTypeToDefaultAsyncCasualityName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v14 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
        RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
        ppstm = 0;
        v11 = 0;
        if ( v14 && v13 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
          v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v11 >= 0 )
            v11 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v6, 0, 0, 1u);
        }
        else
        {
          v11 = -2147467262;
        }
        v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v13->lpVtbl[1].QueryInterface)(
               v13,
               pUnk,
               v12);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
               v7,
               v13,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>>(&ppstm);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x18017fc60  push    rbp
0x18017fc62  push    rbx
0x18017fc63  push    rdi
0x18017fc64  mov     rbp, rsp
0x18017fc67  sub     rsp, 50h
0x18017fc6b  mov     rbx, rcx
0x18017fc6e  xor     edi, edi
0x18017fc70  lea     edx, [rdi+1]
0x18017fc73  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetAllConstantsForInputTypeToDefaultAsyncCasualityName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SetAllConstantsForInputTypeToDefaultAsyncCasualityName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18017fc78  cmp     [rbx+88h], edi
0x18017fc7e  jle     loc_18017FDF8
0x18017fc84  mov     eax, edx
0x18017fc86  lock xadd [rbx+10h], eax
0x18017fc8b  inc     eax
0x18017fc8d  cmp     eax, edx
0x18017fc8f  jnz     loc_18017FDF8
0x18017fc95  mov     [rbp+var_20], rbx
0x18017fc99  lea     rcx, [rbp+var_20]
0x18017fc9d  call    ??1?$com_ptr_t@VAsyncHRESULTPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(void)
0x18017fca2  nop
0x18017fca3  mov     [rbp+pUnk], rdi
0x18017fca7  mov     rcx, rbx
0x18017fcaa  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertyValue@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18017fcaf  lea     rdx, [rbp+pUnk]
0x18017fcb3  lea     rcx, [rbp+var_20]
0x18017fcb7  call    ??$As@U?$IAsyncOperation@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<HSTRING__ *> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVector<HSTRING__ *> *>>>)
0x18017fcbc  test    eax, eax
0x18017fcbe  js      loc_18017FDDE
0x18017fcc4  mov     [rbp+arg_0], 0FFFFFFFEh
0x18017fccb  mov     ecx, [rbx+38h]
0x18017fcce  mov     eax, [rbp+arg_0]
0x18017fcd1  lock cmpxchg [rbp+arg_0], ecx
0x18017fcd6  mov     [rbp+arg_8], rdi
0x18017fcda  lea     rcx, [rbp+arg_8]
0x18017fcde  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017fce3  lea     rcx, [rbx+78h]
0x18017fce7  lea     r8, [rbp+arg_8]
0x18017fceb  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>>::CopyLocal(_GUID const &,void * *)
0x18017fcf0  test    eax, eax
0x18017fcf2  js      loc_18017FDD4
0x18017fcf8  mov     rcx, rbx
0x18017fcfb  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetAllConstantsForInputTypeToDefaultAsyncCasualityName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const SetAllConstantsForInputTypeToDefaultAsyncCasualityName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18017fd00  mov     [rbp+arg_10], rdi
0x18017fd04  lea     rcx, [rbp+arg_10]
0x18017fd08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017fd0d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18017fd11  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18017fd15  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18017fd1a  mov     [rbp+ppstm], rdi
0x18017fd1e  mov     [rbp+var_10], edi
0x18017fd21  cmp     [rbp+arg_10], rdi
0x18017fd25  jz      short loc_18017FD7F
0x18017fd27  cmp     [rbp+arg_8], rdi
0x18017fd2b  jz      short loc_18017FD7F
0x18017fd2d  mov     rdi, [rbp+pUnk]
0x18017fd31  lea     rcx, [rbp+ppstm]
0x18017fd35  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017fd3a  lea     r8, [rbp+ppstm]; ppstm
0x18017fd3e  mov     edx, 1; fDeleteOnRelease
0x18017fd43  xor     ecx, ecx; hGlobal
0x18017fd45  call    cs:__imp_CreateStreamOnHGlobal
0x18017fd4b  mov     [rbp+var_10], eax
0x18017fd4e  test    eax, eax
0x18017fd50  js      short loc_18017FD86
0x18017fd52  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18017fd5a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18017fd63  xor     r9d, r9d; dwDestContext
0x18017fd66  mov     r8, rdi; pUnk
0x18017fd69  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18017fd70  mov     rcx, [rbp+ppstm]; pStm
0x18017fd74  call    cs:__imp_CoMarshalInterface
0x18017fd7a  mov     [rbp+var_10], eax
0x18017fd7d  jmp     short loc_18017FD86
0x18017fd7f  mov     [rbp+var_10], 80004002h
0x18017fd86  mov     rcx, [rbp+arg_8]
0x18017fd8a  mov     rax, [rcx]
0x18017fd8d  mov     r8d, [rbp+arg_0]
0x18017fd91  mov     rdx, [rbp+pUnk]
0x18017fd95  mov     rax, [rax+18h]
0x18017fd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017fd9e  mov     r8, [rbx+80h]
0x18017fda5  mov     rdx, [rbp+arg_8]
0x18017fda9  mov     ecx, eax
0x18017fdab  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18017fdb0  mov     edi, eax
0x18017fdb2  mov     rcx, rbx
0x18017fdb5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18017fdba  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVector<HSTRING__ *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18017fdbf  nop
0x18017fdc0  lea     rcx, [rbp+ppstm]
0x18017fdc4  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAUIPropertyValue@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertyValue@Foundation@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::IPropertyValue *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::IPropertyValue *>>(void)
0x18017fdc9  nop
0x18017fdca  lea     rcx, [rbp+arg_10]
0x18017fdce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017fdd3  nop
0x18017fdd4  lea     rcx, [rbp+arg_8]
0x18017fdd8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017fddd  nop
0x18017fdde  lea     rcx, [rbp+pUnk]
0x18017fde2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017fde7  nop
0x18017fde8  mov     rax, [rbx]
0x18017fdeb  mov     rcx, rbx
0x18017fdee  mov     rax, [rax+10h]
0x18017fdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017fdf7  nop
0x18017fdf8  mov     eax, edi
0x18017fdfa  add     rsp, 50h
0x18017fdfe  pop     rdi
0x18017fdff  pop     rbx
0x18017fe00  pop     rbp
0x18017fe01  retn
```
