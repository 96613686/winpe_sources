# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180066230`
- end: `0x180066326`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `246`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800664b8`

## callees

- `0x18001d3ec`
- `0x18002e5ac`
- `0x180066230`
- `0x1800666f4`
- `0x180066d98`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800662b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800662b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800662c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800662c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  _DWORD *v3; // rdi
  signed int v4; // ebx
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v2;
  v3 = v2;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(v2);
    v3[12] = 0;
    *(_QWORD *)v3 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v3 + 7) = 0;
    *((_QWORD *)v3 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    v8 = v3;
    v9 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v3 + 7) = Event;
    if ( Event )
      goto LABEL_8;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_8:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
      *a1 = v3;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v8);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v8);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  __1__MakeAllocator_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Details_WRL_Microsoft__QEAA_XZ(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180066230  mov     [rsp+arg_10], rbx
0x180066235  mov     [rsp+arg_18], rsi
0x18006623a  push    rdi
0x18006623b  sub     rsp, 20h
0x18006623f  mov     rsi, rcx
0x180066242  mov     qword ptr [rcx], 0
0x180066249  mov     ecx, 40h ; '@'; unsigned __int64
0x18006624e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180066255  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006625a  mov     [rsp+28h+arg_8], rax
0x18006625f  mov     rdi, rax
0x180066262  test    rax, rax
0x180066265  jnz     short loc_180066271
0x180066267  mov     ebx, 8007000Eh
0x18006626c  jmp     loc_18006630A
0x180066271  mov     rcx, rdi
0x180066274  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(void)
0x180066279  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x180066280  mov     dword ptr [rdi+30h], 0
0x180066287  mov     [rdi], rax
0x18006628a  mov     r9d, 1F0003h; dwDesiredAccess
0x180066290  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180066297  mov     qword ptr [rdi+38h], 0
0x18006629f  xor     r8d, r8d; dwFlags
0x1800662a2  mov     [rdi+8], rax
0x1800662a6  xor     edx, edx; lpName
0x1800662a8  mov     [rsp+28h+arg_0], rdi
0x1800662ad  xor     ecx, ecx; lpEventAttributes
0x1800662af  mov     [rsp+28h+arg_8], 0
0x1800662b8  call    cs:__imp_CreateEventExW
0x1800662be  mov     [rdi+38h], rax
0x1800662c2  test    rax, rax
0x1800662c5  jnz     short loc_1800662EC
0x1800662c7  call    cs:__imp_GetLastError
0x1800662cd  mov     ebx, eax
0x1800662cf  test    eax, eax
0x1800662d1  jle     short loc_1800662DC
0x1800662d3  movzx   ebx, ax
0x1800662d6  or      ebx, 80070000h
0x1800662dc  test    ebx, ebx
0x1800662de  jns     short loc_1800662EC
0x1800662e0  lea     rcx, [rsp+28h+arg_0]
0x1800662e5  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x1800662ea  jmp     short loc_18006630A
0x1800662ec  mov     rax, [rdi]
0x1800662ef  mov     rcx, rdi
0x1800662f2  mov     rax, [rax+8]
0x1800662f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662fb  lea     rcx, [rsp+28h+arg_0]
0x180066300  mov     [rsi], rdi
0x180066303  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066308  xor     ebx, ebx
0x18006630a  lea     rcx, [rsp+28h+arg_8]
0x18006630f  call    ??1?$MakeAllocator@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>(void)
0x180066314  mov     rsi, [rsp+28h+arg_18]
0x180066319  mov     eax, ebx
0x18006631b  mov     rbx, [rsp+28h+arg_10]
0x180066320  add     rsp, 20h
0x180066324  pop     rdi
0x180066325  retn
```
