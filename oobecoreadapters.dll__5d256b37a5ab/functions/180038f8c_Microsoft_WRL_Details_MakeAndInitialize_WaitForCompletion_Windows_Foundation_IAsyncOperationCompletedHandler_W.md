# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180038f8c`
- end: `0x1800390c4`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800394f8`

## callees

- `0x180003ffc`
- `0x18000683c`
- `0x180009724`
- `0x18000d2ec`
- `0x180038f8c`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180039055`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180039055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039064`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIBuffer_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIBuffer_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIBuffer_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v7; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v8; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>'::`2'::FTMEventDelegate::`vftable';
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v7 = v2;
    v8 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v2 + 7) = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
      *a1 = v2;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<OobeSnapshotCapture,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<OobeSnapshotCapture,0>>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180038f8c  mov     [rsp+arg_10], rbx
0x180038f91  mov     [rsp+arg_18], rsi
0x180038f96  push    rdi
0x180038f97  sub     rsp, 20h
0x180038f9b  mov     rsi, rcx
0x180038f9e  mov     qword ptr [rcx], 0
0x180038fa5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180038fac  mov     ecx, 40h ; '@'; unsigned __int64
0x180038fb1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180038fb6  mov     rbx, rax
0x180038fb9  mov     [rsp+28h+arg_8], rax
0x180038fbe  test    rax, rax
0x180038fc1  jnz     short loc_180038FCD
0x180038fc3  mov     edi, 8007000Eh
0x180038fc8  jmp     loc_1800390A8
0x180038fcd  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVSignInResult@Internal@System@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>::`vftable'
0x180038fd4  mov     [rbx], rax
0x180038fd7  lea     rdi, [rbx+8]
0x180038fdb  mov     rcx, rdi; this
0x180038fde  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180038fe3  mov     dword ptr [rbx+2Ch], 1
0x180038fea  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>'}
0x180038ff1  mov     [rbx], rax
0x180038ff4  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180038ffb  mov     [rdi], rax
0x180038ffe  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180039005  test    rcx, rcx
0x180039008  jz      short loc_180039017
0x18003900a  mov     rax, [rcx]
0x18003900d  mov     rax, [rax+8]
0x180039011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039016  nop
0x180039017  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>'}
0x18003901e  mov     [rbx], rax
0x180039021  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180039028  mov     [rdi], rax
0x18003902b  mov     dword ptr [rbx+30h], 0
0x180039032  mov     qword ptr [rbx+38h], 0
0x18003903a  mov     [rsp+28h+arg_0], rbx
0x18003903f  mov     [rsp+28h+arg_8], 0
0x180039048  mov     r9d, 1F0003h; dwDesiredAccess
0x18003904e  xor     r8d, r8d; dwFlags
0x180039051  xor     edx, edx; lpName
0x180039053  xor     ecx, ecx; lpEventAttributes
0x180039055  call    cs:__imp_CreateEventExW
0x18003905b  mov     [rbx+38h], rax
0x18003905f  test    rax, rax
0x180039062  jnz     short loc_180039089
0x180039064  call    cs:__imp_GetLastError
0x18003906a  mov     edi, eax
0x18003906c  test    eax, eax
0x18003906e  jle     short loc_180039079
0x180039070  movzx   edi, ax
0x180039073  or      edi, 80070000h
0x180039079  test    edi, edi
0x18003907b  jns     short loc_180039089
0x18003907d  lea     rcx, [rsp+28h+arg_0]
0x180039082  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039087  jmp     short loc_1800390A8
0x180039089  mov     rax, [rbx]
0x18003908c  mov     rcx, rbx
0x18003908f  mov     rax, [rax+8]
0x180039093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039098  nop
0x180039099  mov     [rsi], rbx
0x18003909c  lea     rcx, [rsp+28h+arg_0]
0x1800390a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800390a6  xor     edi, edi
0x1800390a8  lea     rcx, [rsp+28h+arg_8]
0x1800390ad  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VOobeSnapshotCapture@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<OobeSnapshotCapture,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<OobeSnapshotCapture,0>>(void)
0x1800390b2  mov     eax, edi
0x1800390b4  mov     rbx, [rsp+28h+arg_10]
0x1800390b9  mov     rsi, [rsp+28h+arg_18]
0x1800390be  add     rsp, 20h
0x1800390c2  pop     rdi
0x1800390c3  retn
```
