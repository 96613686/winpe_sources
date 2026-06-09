# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180087da0`
- end: `0x180087fc7`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180087d70`

## callees

- `0x180004870`
- `0x180087da0`
- `0x180087fd0`
- `0x180088008`
- `0x180088074`
- `0x180088158`
- `0x1800881a0`
- `0x1800881f0`
- `0x1800ae3f0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180087fba`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180087fba`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180087f72`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180087f72`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180087f07`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180087f07`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180087fa5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180087fa5`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rcx
  int (__fastcall *v4)(__int64, GUID *, LPUNKNOWN *); // rbx
  LPUNKNOWN v5; // rcx
  signed __int32 v7; // ecx
  __int64 v8; // rdx
  bool v9; // dl
  struct IRpcOptions *v10; // rbx
  int v11; // eax
  struct IUnknown *v12; // rcx
  IUnknown *v13; // rsi
  LPSTREAM pStm; // [rsp+30h] [rbp-18h] BYREF
  HRESULT v15; // [rsp+38h] [rbp-10h]
  unsigned int v16; // [rsp+70h] [rbp+28h] BYREF
  struct IUnknown *v17; // [rsp+78h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+80h] [rbp+38h] BYREF
  struct IRpcOptions *v19; // [rsp+88h] [rbp+40h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted();
  if ( *(int *)(v3 + 136) > 0 && _InterlockedIncrement((volatile signed __int32 *)(v3 + 16)) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned int,unsigned int>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    v4 = **(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pUnk);
    if ( v4(a1, &GUID_d26b2819_897f_5c7d_84d6_56d796561431, &pUnk) >= 0 )
    {
      v7 = *(_DWORD *)(a1 + 56);
      v16 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v16, v7, -2);
      v17 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v17);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>>::CopyLocal(
                  a1 + 120,
                  v8,
                  &v17) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v19 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v19);
        RpcOptionsHelper::GetRpcOptions(v17, v9, &v19);
        v10 = v19;
        pStm = 0;
        v15 = 0;
        if ( v19 && v17 )
        {
          v13 = pUnk;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pStm);
          v15 = CreateStreamOnHGlobal(0, 1, &pStm);
          if ( v15 >= 0 )
            v15 = CoMarshalInterface(pStm, &GUID_00000000_0000_0000_c000_000000000046, v13, 0, 0, 1u);
        }
        else
        {
          v15 = -2147467262;
        }
        v11 = v17->__vftable[1].QueryInterface(v17, (const _GUID *)pUnk, (void **)v16);
        v2 = v11;
        if ( v11 < 0 )
        {
          RoTransformError((unsigned int)v11, 0, 0);
          v2 = 0;
        }
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        if ( v15 >= 0 )
        {
          ((void (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))pStm->Seek)(pStm, 0, 0, 0);
          CoReleaseMarshalData(pStm);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&pStm);
        if ( v10 )
          ((void (__fastcall *)(struct IRpcOptions *))v10->lpVtbl->Release)(v10);
      }
      v12 = v17;
      if ( v17 )
      {
        v17 = 0;
        v12->Release(v12);
      }
    }
    v5 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      v5->Release(v5);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180087da0  push    rbp
0x180087da2  push    rbx
0x180087da3  push    rsi
0x180087da4  push    rdi
0x180087da5  mov     rbp, rsp
0x180087da8  sub     rsp, 48h
0x180087dac  mov     rdi, rcx
0x180087daf  xor     esi, esi
0x180087db1  call    ?TryTransitionToCompleted@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NW4CancelTransitionPolicy@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted(Microsoft::WRL::CancelTransitionPolicy)
0x180087db6  cmp     [rcx+88h], esi
0x180087dbc  jle     short loc_180087E3A
0x180087dbe  lea     eax, [rsi+1]
0x180087dc1  lock xadd [rcx+10h], eax
0x180087dc6  inc     eax
0x180087dc8  cmp     eax, 1
0x180087dcb  jnz     short loc_180087E3A
0x180087dcd  mov     rax, [rcx]
0x180087dd0  mov     rax, [rax+8]
0x180087dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087dd9  mov     rcx, rdi
0x180087ddc  mov     [rbp+pUnk], rsi
0x180087de0  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x180087de5  mov     rax, [rdi]
0x180087de8  lea     rcx, [rbp+pUnk]
0x180087dec  mov     rbx, [rax]
0x180087def  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180087df4  lea     r8, [rbp+pUnk]
0x180087df8  mov     rcx, rdi
0x180087dfb  lea     rdx, _GUID_d26b2819_897f_5c7d_84d6_56d796561431
0x180087e02  mov     rax, rbx
0x180087e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e0a  test    eax, eax
0x180087e0c  jns     short loc_180087E45
0x180087e0e  mov     rcx, [rbp+pUnk]
0x180087e12  test    rcx, rcx
0x180087e15  jz      short loc_180087E2B
0x180087e17  mov     [rbp+pUnk], 0
0x180087e1f  mov     rax, [rcx]
0x180087e22  mov     rax, [rax+10h]
0x180087e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e2b  mov     rcx, [rdi]
0x180087e2e  mov     rax, [rcx+10h]
0x180087e32  mov     rcx, rdi
0x180087e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e3a  mov     eax, esi
0x180087e3c  add     rsp, 48h
0x180087e40  pop     rdi
0x180087e41  pop     rsi
0x180087e42  pop     rbx
0x180087e43  pop     rbp
0x180087e44  retn
0x180087e45  mov     ecx, [rdi+38h]
0x180087e48  mov     [rbp+arg_0], 0FFFFFFFEh
0x180087e4f  mov     eax, [rbp+arg_0]
0x180087e52  lock cmpxchg [rbp+arg_0], ecx
0x180087e57  lea     rcx, [rbp+arg_8]
0x180087e5b  mov     [rbp+arg_8], rsi
0x180087e5f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180087e64  lea     rcx, [rdi+78h]
0x180087e68  lea     r8, [rbp+arg_8]
0x180087e6c  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>>::CopyLocal(_GUID const &,void * *)
0x180087e71  test    eax, eax
0x180087e73  js      loc_180087F2A
0x180087e79  mov     rcx, rdi
0x180087e7c  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180087e81  lea     rcx, [rbp+arg_18]
0x180087e85  mov     [rbp+arg_18], rsi
0x180087e89  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180087e8e  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180087e92  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x180087e96  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180087e9b  mov     rbx, [rbp+arg_18]
0x180087e9f  mov     [rbp+pStm], rsi
0x180087ea3  mov     [rbp+var_10], esi
0x180087ea6  test    rbx, rbx
0x180087ea9  jnz     loc_180087F50
0x180087eaf  mov     [rbp+var_10], 80004002h
0x180087eb6  mov     rcx, [rbp+arg_8]
0x180087eba  mov     r8d, [rbp+arg_0]
0x180087ebe  mov     rdx, [rbp+pUnk]
0x180087ec2  mov     rax, [rcx]
0x180087ec5  mov     rax, [rax+18h]
0x180087ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ece  mov     esi, eax
0x180087ed0  test    eax, eax
0x180087ed2  js      loc_180087FB3
0x180087ed8  mov     rcx, rdi
0x180087edb  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x180087ee0  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x180087ee5  cmp     [rbp+var_10], 0
0x180087ee9  jl      short loc_180087F0D
0x180087eeb  mov     rcx, [rbp+pStm]
0x180087eef  xor     edx, edx
0x180087ef1  xor     r9d, r9d
0x180087ef4  xor     r8d, r8d
0x180087ef7  mov     rax, [rcx]
0x180087efa  mov     rax, [rax+28h]
0x180087efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087f03  mov     rcx, [rbp+pStm]; pStm
0x180087f07  call    cs:__imp_CoReleaseMarshalData
0x180087f0d  lea     rcx, [rbp+pStm]
0x180087f11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180087f16  test    rbx, rbx
0x180087f19  jz      short loc_180087F2A
0x180087f1b  mov     rax, [rbx]
0x180087f1e  mov     rcx, rbx
0x180087f21  mov     rax, [rax+10h]
0x180087f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087f2a  mov     rcx, [rbp+arg_8]
0x180087f2e  test    rcx, rcx
0x180087f31  jz      loc_180087E0E
0x180087f37  mov     [rbp+arg_8], 0
0x180087f3f  mov     rax, [rcx]
0x180087f42  mov     rax, [rax+10h]
0x180087f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087f4b  jmp     loc_180087E0E
0x180087f50  cmp     [rbp+arg_8], rsi
0x180087f54  jz      loc_180087EAF
0x180087f5a  mov     rsi, [rbp+pUnk]
0x180087f5e  lea     rcx, [rbp+pStm]
0x180087f62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180087f67  lea     r8, [rbp+pStm]; ppstm
0x180087f6b  mov     edx, 1; fDeleteOnRelease
0x180087f70  xor     ecx, ecx; hGlobal
0x180087f72  call    cs:__imp_CreateStreamOnHGlobal
0x180087f78  mov     [rbp+var_10], eax
0x180087f7b  test    eax, eax
0x180087f7d  js      loc_180087EB6
0x180087f83  mov     rcx, [rbp+pStm]; pStm
0x180087f87  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180087f8e  mov     [rsp+48h+mshlflags], 1; mshlflags
0x180087f96  xor     r9d, r9d; dwDestContext
0x180087f99  mov     r8, rsi; pUnk
0x180087f9c  mov     [rsp+48h+pvDestContext], 0; pvDestContext
0x180087fa5  call    cs:__imp_CoMarshalInterface
0x180087fab  mov     [rbp+var_10], eax
0x180087fae  jmp     loc_180087EB6
0x180087fb3  xor     r8d, r8d
0x180087fb6  xor     edx, edx
0x180087fb8  mov     ecx, eax
0x180087fba  call    cs:__imp_RoTransformError
0x180087fc0  xor     esi, esi
0x180087fc2  jmp     loc_180087ED8
```
