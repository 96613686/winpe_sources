# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180027250`
- end: `0x1800273eb`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800276a0`

## callees

- `0x18000683c`
- `0x18001e9e8`
- `0x180023d18`
- `0x180026918`
- `0x180027250`
- `0x180027770`
- `0x180028c28`
- `0x180029224`
- `0x18002b7f4`
- `0x18002b824`
- `0x18002b8c8`
- `0x18002c064`
- `0x18002c188`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180027364`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180027364`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180027335`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180027335`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<HSTRING__ *>>(&v9, &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::CopyLocal(
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
0x180027250  push    rbp
0x180027252  push    rbx
0x180027253  push    rdi
0x180027254  mov     rbp, rsp
0x180027257  sub     rsp, 50h
0x18002725b  mov     rbx, rcx
0x18002725e  xor     edi, edi
0x180027260  lea     edx, [rdi+1]
0x180027263  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetMachineFirstSignInSettingsAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::SetMachineFirstSignInSettingsAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180027268  cmp     [rbx+88h], edi
0x18002726e  jle     loc_1800273E1
0x180027274  mov     eax, edx
0x180027276  lock xadd [rbx+10h], eax
0x18002727b  inc     eax
0x18002727d  cmp     eax, edx
0x18002727f  jnz     loc_1800273E1
0x180027285  mov     [rbp+var_20], rbx
0x180027289  lea     rcx, [rbp+var_20]
0x18002728d  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180027292  nop
0x180027293  mov     [rbp+pUnk], rdi
0x180027297  mov     rcx, rbx
0x18002729a  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?FirstLogonRestoreAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::FirstLogonRestoreAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18002729f  lea     rdx, [rbp+pUnk]
0x1800272a3  lea     rcx, [rbp+var_20]
0x1800272a7  call    ??$As@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>>)
0x1800272ac  test    eax, eax
0x1800272ae  js      loc_1800273CE
0x1800272b4  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800272bb  mov     ecx, [rbx+38h]
0x1800272be  mov     eax, [rbp+arg_0]
0x1800272c1  lock cmpxchg [rbp+arg_0], ecx
0x1800272c6  mov     [rbp+arg_8], rdi
0x1800272ca  lea     rcx, [rbp+arg_8]
0x1800272ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800272d3  lea     rcx, [rbx+78h]
0x1800272d7  lea     r8, [rbp+arg_8]
0x1800272db  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::CopyLocal(_GUID const &,void * *)
0x1800272e0  test    eax, eax
0x1800272e2  js      loc_1800273C4
0x1800272e8  mov     rcx, rbx
0x1800272eb  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CancelUpdateAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::CancelUpdateAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x1800272f0  mov     [rbp+arg_10], rdi
0x1800272f4  lea     rcx, [rbp+arg_10]
0x1800272f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800272fd  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180027301  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180027305  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002730a  mov     [rbp+ppstm], rdi
0x18002730e  mov     [rbp+var_10], edi
0x180027311  cmp     [rbp+arg_10], rdi
0x180027315  jz      short loc_18002736F
0x180027317  cmp     [rbp+arg_8], rdi
0x18002731b  jz      short loc_18002736F
0x18002731d  mov     rdi, [rbp+pUnk]
0x180027321  lea     rcx, [rbp+ppstm]
0x180027325  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002732a  lea     r8, [rbp+ppstm]; ppstm
0x18002732e  mov     edx, 1; fDeleteOnRelease
0x180027333  xor     ecx, ecx; hGlobal
0x180027335  call    cs:__imp_CreateStreamOnHGlobal
0x18002733b  mov     [rbp+var_10], eax
0x18002733e  test    eax, eax
0x180027340  js      short loc_180027376
0x180027342  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18002734a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180027353  xor     r9d, r9d; dwDestContext
0x180027356  mov     r8, rdi; pUnk
0x180027359  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180027360  mov     rcx, [rbp+ppstm]; pStm
0x180027364  call    cs:__imp_CoMarshalInterface
0x18002736a  mov     [rbp+var_10], eax
0x18002736d  jmp     short loc_180027376
0x18002736f  mov     [rbp+var_10], 80004002h
0x180027376  mov     rcx, [rbp+arg_8]
0x18002737a  mov     rax, [rcx]
0x18002737d  mov     r8d, [rbp+arg_0]
0x180027381  mov     rdx, [rbp+pUnk]
0x180027385  mov     rax, [rax+18h]
0x180027389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002738e  mov     r8, [rbx+80h]
0x180027395  mov     rdx, [rbp+arg_8]
0x180027399  mov     ecx, eax
0x18002739b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800273a0  mov     edi, eax
0x1800273a2  mov     rcx, rbx
0x1800273a5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800273aa  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetMachineFirstSignInSettingsAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::SetMachineFirstSignInSettingsAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800273af  nop
0x1800273b0  lea     rcx, [rbp+ppstm]
0x1800273b4  call    ??1?$AutoStubBias@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(void)
0x1800273b9  nop
0x1800273ba  lea     rcx, [rbp+arg_10]
0x1800273be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800273c3  nop
0x1800273c4  lea     rcx, [rbp+arg_8]
0x1800273c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800273cd  nop
0x1800273ce  lea     rcx, [rbp+pUnk]
0x1800273d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800273d7  nop
0x1800273d8  lea     rcx, [rbp+var_20]
0x1800273dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800273e1  mov     eax, edi
0x1800273e3  add     rsp, 50h
0x1800273e7  pop     rdi
0x1800273e8  pop     rbx
0x1800273e9  pop     rbp
0x1800273ea  retn
```
