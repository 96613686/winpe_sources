# `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)

- ea: `0x140046dc8`
- end: `0x140046ecd`
- name: `??0FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140046b10`

## callees

- `0x140046dc8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140046dfa`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140046dfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::FTMEventDelegate(
        __int64 a1)
{
  __int64 *v2; // rsi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (__int64 *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v5 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  v6 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  *(_DWORD *)(a1 + 44) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
  *(_QWORD *)(a1 + 8) = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *(_QWORD *)(a1 + 8) = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  return a1;
}

```

## disassembly

```asm
0x140046dc8  push    rbx
0x140046dca  push    rbp
0x140046dcb  push    rsi
0x140046dcc  push    rdi
0x140046dcd  sub     rsp, 28h
0x140046dd1  mov     rdi, rcx
0x140046dd4  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x140046ddb  mov     [rcx+8], rax
0x140046ddf  lea     rsi, [rcx+20h]
0x140046de3  mov     qword ptr [rsi], 0
0x140046dea  mov     [rsp+48h+ppunkMarshal], 0
0x140046df3  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x140046df8  xor     ecx, ecx; punkOuter
0x140046dfa  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x140046e01  nop     dword ptr [rax+rax+00h]
0x140046e06  test    eax, eax
0x140046e08  js      short loc_140046E47
0x140046e0a  mov     rbx, [rsp+48h+ppunkMarshal]
0x140046e0f  mov     rax, [rbx]
0x140046e12  mov     rbp, [rax]
0x140046e15  mov     rcx, [rsi]
0x140046e18  test    rcx, rcx
0x140046e1b  jz      short loc_140046E31
0x140046e1d  mov     qword ptr [rsi], 0
0x140046e24  mov     rdx, [rcx]
0x140046e27  mov     rax, [rdx+10h]
0x140046e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046e30  nop
0x140046e31  mov     r8, rsi
0x140046e34  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140046e3b  mov     rcx, rbx
0x140046e3e  mov     rax, rbp
0x140046e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046e46  nop
0x140046e47  mov     rcx, [rsp+48h+ppunkMarshal]
0x140046e4c  test    rcx, rcx
0x140046e4f  jz      short loc_140046E67
0x140046e51  mov     [rsp+48h+ppunkMarshal], 0
0x140046e5a  mov     rax, [rcx]
0x140046e5d  mov     rax, [rax+10h]
0x140046e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046e66  nop
0x140046e67  mov     dword ptr [rdi+2Ch], 1
0x140046e6e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x140046e75  mov     [rdi], rax
0x140046e78  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140046e7f  mov     [rdi+8], rax
0x140046e83  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140046e8a  test    rcx, rcx
0x140046e8d  jz      short loc_140046E9C
0x140046e8f  mov     rax, [rcx]
0x140046e92  mov     rax, [rax+8]
0x140046e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046e9b  nop
0x140046e9c  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x140046ea3  mov     [rdi], rax
0x140046ea6  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140046ead  mov     [rdi+8], rax
0x140046eb1  mov     dword ptr [rdi+30h], 0
0x140046eb8  mov     qword ptr [rdi+38h], 0
0x140046ec0  mov     rax, rdi
0x140046ec3  add     rsp, 28h
0x140046ec7  pop     rdi
0x140046ec8  pop     rsi
0x140046ec9  pop     rbp
0x140046eca  pop     rbx
0x140046ecb  retn
```
