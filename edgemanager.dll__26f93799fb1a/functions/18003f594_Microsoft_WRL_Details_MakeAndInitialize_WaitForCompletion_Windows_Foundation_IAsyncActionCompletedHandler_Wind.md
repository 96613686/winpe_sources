# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18003f594`
- end: `0x18003f6c2`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d194`

## callees

- `0x180002a90`
- `0x18000b0ec`
- `0x18000f5d4`
- `0x18002b5e4`
- `0x18003f594`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003f653`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003f653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f662`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        char **a1)
{
  char *v2; // rax
  char *v3; // rbx
  signed int v4; // edi
  _QWORD *v5; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  char *v9; // [rsp+30h] [rbp+8h] BYREF
  char *v10; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v10 = v2;
  if ( v2 )
  {
    v5 = v2 + 8;
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 8));
    *((_DWORD *)v3 + 11) = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
    *v5 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = &`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    *v5 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    *((_DWORD *)v3 + 12) = 0;
    *((_QWORD *)v3 + 7) = 0;
    v9 = v3;
    v10 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v3 + 7) = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
      *a1 = v3;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003f594  mov     [rsp+arg_10], rbx
0x18003f599  mov     [rsp+arg_18], rsi
0x18003f59e  push    rdi
0x18003f59f  sub     rsp, 20h
0x18003f5a3  mov     rsi, rcx
0x18003f5a6  mov     qword ptr [rcx], 0
0x18003f5ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003f5b4  mov     ecx, 40h ; '@'; unsigned __int64
0x18003f5b9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003f5be  mov     rbx, rax
0x18003f5c1  mov     [rsp+28h+arg_8], rax
0x18003f5c6  test    rax, rax
0x18003f5c9  jnz     short loc_18003F5D5
0x18003f5cb  mov     edi, 8007000Eh
0x18003f5d0  jmp     loc_18003F6A6
0x18003f5d5  lea     rdi, [rax+8]
0x18003f5d9  mov     rcx, rdi; this
0x18003f5dc  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18003f5e1  mov     dword ptr [rbx+2Ch], 1
0x18003f5e8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18003f5ef  mov     [rbx], rax
0x18003f5f2  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003f5f9  mov     [rdi], rax
0x18003f5fc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003f603  test    rcx, rcx
0x18003f606  jz      short loc_18003F615
0x18003f608  mov     rax, [rcx]
0x18003f60b  mov     rax, [rax+8]
0x18003f60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f614  nop
0x18003f615  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18003f61c  mov     [rbx], rax
0x18003f61f  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003f626  mov     [rdi], rax
0x18003f629  mov     dword ptr [rbx+30h], 0
0x18003f630  mov     qword ptr [rbx+38h], 0
0x18003f638  mov     [rsp+28h+arg_0], rbx
0x18003f63d  mov     [rsp+28h+arg_8], 0
0x18003f646  mov     r9d, 1F0003h; dwDesiredAccess
0x18003f64c  xor     r8d, r8d; dwFlags
0x18003f64f  xor     edx, edx; lpName
0x18003f651  xor     ecx, ecx; lpEventAttributes
0x18003f653  call    cs:__imp_CreateEventExW
0x18003f659  mov     [rbx+38h], rax
0x18003f65d  test    rax, rax
0x18003f660  jnz     short loc_18003F687
0x18003f662  call    cs:__imp_GetLastError
0x18003f668  mov     edi, eax
0x18003f66a  test    eax, eax
0x18003f66c  jle     short loc_18003F677
0x18003f66e  movzx   edi, ax
0x18003f671  or      edi, 80070000h
0x18003f677  test    edi, edi
0x18003f679  jns     short loc_18003F687
0x18003f67b  lea     rcx, [rsp+28h+arg_0]
0x18003f680  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f685  jmp     short loc_18003F6A6
0x18003f687  mov     rax, [rbx]
0x18003f68a  mov     rcx, rbx
0x18003f68d  mov     rax, [rax+8]
0x18003f691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f696  nop
0x18003f697  mov     [rsi], rbx
0x18003f69a  lea     rcx, [rsp+28h+arg_0]
0x18003f69f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f6a4  xor     edi, edi
0x18003f6a6  lea     rcx, [rsp+28h+arg_8]
0x18003f6ab  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18003f6b0  mov     eax, edi
0x18003f6b2  mov     rbx, [rsp+28h+arg_10]
0x18003f6b7  mov     rsi, [rsp+28h+arg_18]
0x18003f6bc  add     rsp, 20h
0x18003f6c0  pop     rdi
0x18003f6c1  retn
```
