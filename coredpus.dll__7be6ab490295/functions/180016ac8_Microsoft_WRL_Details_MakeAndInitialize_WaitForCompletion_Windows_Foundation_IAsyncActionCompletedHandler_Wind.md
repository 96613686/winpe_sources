# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180016ac8`
- end: `0x180016c03`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800174b8`

## callees

- `0x180011d6c`
- `0x1800145f0`
- `0x180016ac8`
- `0x1800182a8`
- `0x180018600`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016b87`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b9c`

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
    *(_QWORD *)v3 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  Z::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate,Windows::Foundation::AJPEAUIAsyncAction,enum tagCOWAIT_FLAGS,void *>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate,Windows::Foundation::AJPEAUIAsyncAction,enum tagCOWAIT_FLAGS,void *>(&v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016ac8  mov     [rsp+arg_10], rbx
0x180016acd  mov     [rsp+arg_18], rsi
0x180016ad2  push    rdi
0x180016ad3  sub     rsp, 20h
0x180016ad7  mov     rsi, rcx
0x180016ada  mov     qword ptr [rcx], 0
0x180016ae1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016ae8  mov     ecx, 40h ; '@'; unsigned __int64
0x180016aed  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016af2  mov     rbx, rax
0x180016af5  mov     [rsp+28h+arg_8], rax
0x180016afa  test    rax, rax
0x180016afd  jnz     short loc_180016B09
0x180016aff  mov     edi, 8007000Eh
0x180016b04  jmp     loc_180016BE6
0x180016b09  lea     rdi, [rax+8]
0x180016b0d  mov     rcx, rdi; this
0x180016b10  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180016b15  mov     dword ptr [rbx+2Ch], 1
0x180016b1c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x180016b23  mov     [rbx], rax
0x180016b26  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180016b2d  mov     [rdi], rax
0x180016b30  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180016b37  test    rcx, rcx
0x180016b3a  jz      short loc_180016B49
0x180016b3c  mov     rax, [rcx]
0x180016b3f  mov     rax, [rax+8]
0x180016b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b48  nop
0x180016b49  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x180016b50  mov     [rbx], rax
0x180016b53  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180016b5a  mov     [rdi], rax
0x180016b5d  mov     dword ptr [rbx+30h], 0
0x180016b64  mov     qword ptr [rbx+38h], 0
0x180016b6c  mov     [rsp+28h+arg_0], rbx
0x180016b71  mov     [rsp+28h+arg_8], 0
0x180016b7a  mov     r9d, 1F0003h; dwDesiredAccess
0x180016b80  xor     r8d, r8d; dwFlags
0x180016b83  xor     edx, edx; lpName
0x180016b85  xor     ecx, ecx; lpEventAttributes
0x180016b87  call    cs:__imp_CreateEventExW
0x180016b8e  nop     dword ptr [rax+rax+00h]
0x180016b93  mov     [rbx+38h], rax
0x180016b97  test    rax, rax
0x180016b9a  jnz     short loc_180016BC7
0x180016b9c  call    cs:__imp_GetLastError
0x180016ba3  nop     dword ptr [rax+rax+00h]
0x180016ba8  mov     edi, eax
0x180016baa  test    eax, eax
0x180016bac  jle     short loc_180016BB7
0x180016bae  movzx   edi, ax
0x180016bb1  or      edi, 80070000h
0x180016bb7  test    edi, edi
0x180016bb9  jns     short loc_180016BC7
0x180016bbb  lea     rcx, [rsp+28h+arg_0]
0x180016bc0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016bc5  jmp     short loc_180016BE6
0x180016bc7  mov     rax, [rbx]
0x180016bca  mov     rcx, rbx
0x180016bcd  mov     rax, [rax+8]
0x180016bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bd6  nop
0x180016bd7  mov     [rsi], rbx
0x180016bda  lea     rcx, [rsp+28h+arg_0]
0x180016bdf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016be4  xor     edi, edi
0x180016be6  lea     rcx, [rsp+28h+arg_8]
0x180016beb  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x180016bf0  mov     eax, edi
0x180016bf2  mov     rbx, [rsp+28h+arg_10]
0x180016bf7  mov     rsi, [rsp+28h+arg_18]
0x180016bfc  add     rsp, 20h
0x180016c00  pop     rdi
0x180016c01  retn
```
