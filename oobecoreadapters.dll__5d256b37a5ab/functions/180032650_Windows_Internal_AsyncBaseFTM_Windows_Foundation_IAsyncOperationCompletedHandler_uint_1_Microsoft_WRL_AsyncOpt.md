# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<uint>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180032650`
- end: `0x1800327eb`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180032800`

## callees

- `0x18000683c`
- `0x180023d18`
- `0x180027770`
- `0x180028c28`
- `0x180029224`
- `0x18002b7f4`
- `0x18002b824`
- `0x18002b8c8`
- `0x18002c064`
- `0x18002c188`
- `0x180030800`
- `0x180032368`
- `0x180032650`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180032764`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180032764`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180032735`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180032735`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::SetMachineFirstSignInSettingsAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::FirstLogonRestoreAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<unsigned int>>(&v9, &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v13) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::CancelUpdateAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v14 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
        RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
        ppstm = 0;
        v11 = 0;
        if ( v14 && v13 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
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
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::SetMachineFirstSignInSettingsAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(&ppstm);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  }
  return v2;
}

```

## disassembly

```asm
0x180032650  push    rbp
0x180032652  push    rbx
0x180032653  push    rdi
0x180032654  mov     rbp, rsp
0x180032657  sub     rsp, 50h
0x18003265b  mov     rbx, rcx
0x18003265e  xor     edi, edi
0x180032660  lea     edx, [rdi+1]
0x180032663  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetMachineFirstSignInSettingsAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::SetMachineFirstSignInSettingsAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180032668  cmp     [rbx+88h], edi
0x18003266e  jle     loc_1800327E1
0x180032674  mov     eax, edx
0x180032676  lock xadd [rbx+10h], eax
0x18003267b  inc     eax
0x18003267d  cmp     eax, edx
0x18003267f  jnz     loc_1800327E1
0x180032685  mov     [rbp+var_20], rbx
0x180032689  lea     rcx, [rbp+var_20]
0x18003268d  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180032692  nop
0x180032693  mov     [rbp+pUnk], rdi
0x180032697  mov     rcx, rbx
0x18003269a  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?FirstLogonRestoreAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::FirstLogonRestoreAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18003269f  lea     rdx, [rbp+pUnk]
0x1800326a3  lea     rcx, [rbp+var_20]
0x1800326a7  call    ??$As@U?$IAsyncOperation@I@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@I@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<uint>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<uint>>>)
0x1800326ac  test    eax, eax
0x1800326ae  js      loc_1800327CE
0x1800326b4  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800326bb  mov     ecx, [rbx+38h]
0x1800326be  mov     eax, [rbp+arg_0]
0x1800326c1  lock cmpxchg [rbp+arg_0], ecx
0x1800326c6  mov     [rbp+arg_8], rdi
0x1800326ca  lea     rcx, [rbp+arg_8]
0x1800326ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800326d3  lea     rcx, [rbx+78h]
0x1800326d7  lea     r8, [rbp+arg_8]
0x1800326db  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<uint>>::CopyLocal(_GUID const &,void * *)
0x1800326e0  test    eax, eax
0x1800326e2  js      loc_1800327C4
0x1800326e8  mov     rcx, rbx
0x1800326eb  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CancelUpdateAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::CancelUpdateAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x1800326f0  mov     [rbp+arg_10], rdi
0x1800326f4  lea     rcx, [rbp+arg_10]
0x1800326f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800326fd  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180032701  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180032705  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18003270a  mov     [rbp+ppstm], rdi
0x18003270e  mov     [rbp+var_10], edi
0x180032711  cmp     [rbp+arg_10], rdi
0x180032715  jz      short loc_18003276F
0x180032717  cmp     [rbp+arg_8], rdi
0x18003271b  jz      short loc_18003276F
0x18003271d  mov     rdi, [rbp+pUnk]
0x180032721  lea     rcx, [rbp+ppstm]
0x180032725  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003272a  lea     r8, [rbp+ppstm]; ppstm
0x18003272e  mov     edx, 1; fDeleteOnRelease
0x180032733  xor     ecx, ecx; hGlobal
0x180032735  call    cs:__imp_CreateStreamOnHGlobal
0x18003273b  mov     [rbp+var_10], eax
0x18003273e  test    eax, eax
0x180032740  js      short loc_180032776
0x180032742  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18003274a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180032753  xor     r9d, r9d; dwDestContext
0x180032756  mov     r8, rdi; pUnk
0x180032759  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180032760  mov     rcx, [rbp+ppstm]; pStm
0x180032764  call    cs:__imp_CoMarshalInterface
0x18003276a  mov     [rbp+var_10], eax
0x18003276d  jmp     short loc_180032776
0x18003276f  mov     [rbp+var_10], 80004002h
0x180032776  mov     rcx, [rbp+arg_8]
0x18003277a  mov     rax, [rcx]
0x18003277d  mov     r8d, [rbp+arg_0]
0x180032781  mov     rdx, [rbp+pUnk]
0x180032785  mov     rax, [rax+18h]
0x180032789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003278e  mov     r8, [rbx+80h]
0x180032795  mov     rdx, [rbp+arg_8]
0x180032799  mov     ecx, eax
0x18003279b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800327a0  mov     edi, eax
0x1800327a2  mov     rcx, rbx
0x1800327a5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800327aa  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetMachineFirstSignInSettingsAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::SetMachineFirstSignInSettingsAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800327af  nop
0x1800327b0  lea     rcx, [rbp+ppstm]
0x1800327b4  call    ??1?$AutoStubBias@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(void)
0x1800327b9  nop
0x1800327ba  lea     rcx, [rbp+arg_10]
0x1800327be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800327c3  nop
0x1800327c4  lea     rcx, [rbp+arg_8]
0x1800327c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800327cd  nop
0x1800327ce  lea     rcx, [rbp+pUnk]
0x1800327d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800327d7  nop
0x1800327d8  lea     rcx, [rbp+var_20]
0x1800327dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800327e1  mov     eax, edi
0x1800327e3  add     rsp, 50h
0x1800327e7  pop     rdi
0x1800327e8  pop     rbx
0x1800327e9  pop     rbp
0x1800327ea  retn
```
