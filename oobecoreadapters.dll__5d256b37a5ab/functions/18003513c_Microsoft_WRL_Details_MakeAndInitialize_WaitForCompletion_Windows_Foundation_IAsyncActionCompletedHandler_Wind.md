# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18003513c`
- end: `0x180035233`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035748`

## callees

- `0x180003ffc`
- `0x18000683c`
- `0x180009724`
- `0x18003513c`
- `0x180035f18`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800351c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800351c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800351d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  signed int v4; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v9 = v2;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(v2);
    *v3 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    v3[1] = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::`vftable';
    *((_DWORD *)v3 + 12) = 0;
    v3[7] = 0;
    v8 = v3;
    v9 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v3[7] = Event;
    if ( Event )
      goto LABEL_8;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_8:
      (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
      *a1 = v3;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<OobeSnapshotCapture,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<OobeSnapshotCapture,0>>(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003513c  mov     [rsp+arg_10], rbx
0x180035141  mov     [rsp+arg_18], rsi
0x180035146  push    rdi
0x180035147  sub     rsp, 20h
0x18003514b  mov     rsi, rcx
0x18003514e  mov     qword ptr [rcx], 0
0x180035155  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003515c  mov     ecx, 40h ; '@'; unsigned __int64
0x180035161  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035166  mov     rbx, rax
0x180035169  mov     [rsp+28h+arg_8], rax
0x18003516e  test    rax, rax
0x180035171  jnz     short loc_18003517D
0x180035173  mov     edi, 8007000Eh
0x180035178  jmp     loc_180035217
0x18003517d  mov     rcx, rbx
0x180035180  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(void)
0x180035185  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18003518c  mov     [rbx], rax
0x18003518f  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180035196  mov     [rbx+8], rax
0x18003519a  mov     dword ptr [rbx+30h], 0
0x1800351a1  mov     qword ptr [rbx+38h], 0
0x1800351a9  mov     [rsp+28h+arg_0], rbx
0x1800351ae  mov     [rsp+28h+arg_8], 0
0x1800351b7  mov     r9d, 1F0003h; dwDesiredAccess
0x1800351bd  xor     r8d, r8d; dwFlags
0x1800351c0  xor     edx, edx; lpName
0x1800351c2  xor     ecx, ecx; lpEventAttributes
0x1800351c4  call    cs:__imp_CreateEventExW
0x1800351ca  mov     [rbx+38h], rax
0x1800351ce  test    rax, rax
0x1800351d1  jnz     short loc_1800351F8
0x1800351d3  call    cs:__imp_GetLastError
0x1800351d9  mov     edi, eax
0x1800351db  test    eax, eax
0x1800351dd  jle     short loc_1800351E8
0x1800351df  movzx   edi, ax
0x1800351e2  or      edi, 80070000h
0x1800351e8  test    edi, edi
0x1800351ea  jns     short loc_1800351F8
0x1800351ec  lea     rcx, [rsp+28h+arg_0]
0x1800351f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800351f6  jmp     short loc_180035217
0x1800351f8  mov     rax, [rbx]
0x1800351fb  mov     rcx, rbx
0x1800351fe  mov     rax, [rax+8]
0x180035202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035207  nop
0x180035208  mov     [rsi], rbx
0x18003520b  lea     rcx, [rsp+28h+arg_0]
0x180035210  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035215  xor     edi, edi
0x180035217  lea     rcx, [rsp+28h+arg_8]
0x18003521c  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VOobeSnapshotCapture@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<OobeSnapshotCapture,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<OobeSnapshotCapture,0>>(void)
0x180035221  mov     eax, edi
0x180035223  mov     rbx, [rsp+28h+arg_10]
0x180035228  mov     rsi, [rsp+28h+arg_18]
0x18003522d  add     rsp, 20h
0x180035231  pop     rdi
0x180035232  retn
```
