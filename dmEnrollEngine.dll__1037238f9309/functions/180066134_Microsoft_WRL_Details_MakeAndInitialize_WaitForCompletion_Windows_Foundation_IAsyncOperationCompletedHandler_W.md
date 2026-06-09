# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180066134`
- end: `0x18006622a`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `246`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006632c`

## callees

- `0x18001d3ec`
- `0x18002e5ac`
- `0x180066134`
- `0x180066644`
- `0x180066d98`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800661bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800661bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>(v2);
    v3[12] = 0;
    *(_QWORD *)v3 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v3 + 7) = 0;
    *((_QWORD *)v3 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180066134  mov     [rsp+arg_10], rbx
0x180066139  mov     [rsp+arg_18], rsi
0x18006613e  push    rdi
0x18006613f  sub     rsp, 20h
0x180066143  mov     rsi, rcx
0x180066146  mov     qword ptr [rcx], 0
0x18006614d  mov     ecx, 40h ; '@'; unsigned __int64
0x180066152  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180066159  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006615e  mov     [rsp+28h+arg_8], rax
0x180066163  mov     rdi, rax
0x180066166  test    rax, rax
0x180066169  jnz     short loc_180066175
0x18006616b  mov     ebx, 8007000Eh
0x180066170  jmp     loc_18006620E
0x180066175  mov     rcx, rdi
0x180066178  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>(void)
0x18006617d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x180066184  mov     dword ptr [rdi+30h], 0
0x18006618b  mov     [rdi], rax
0x18006618e  mov     r9d, 1F0003h; dwDesiredAccess
0x180066194  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006619b  mov     qword ptr [rdi+38h], 0
0x1800661a3  xor     r8d, r8d; dwFlags
0x1800661a6  mov     [rdi+8], rax
0x1800661aa  xor     edx, edx; lpName
0x1800661ac  mov     [rsp+28h+arg_0], rdi
0x1800661b1  xor     ecx, ecx; lpEventAttributes
0x1800661b3  mov     [rsp+28h+arg_8], 0
0x1800661bc  call    cs:__imp_CreateEventExW
0x1800661c2  mov     [rdi+38h], rax
0x1800661c6  test    rax, rax
0x1800661c9  jnz     short loc_1800661F0
0x1800661cb  call    cs:__imp_GetLastError
0x1800661d1  mov     ebx, eax
0x1800661d3  test    eax, eax
0x1800661d5  jle     short loc_1800661E0
0x1800661d7  movzx   ebx, ax
0x1800661da  or      ebx, 80070000h
0x1800661e0  test    ebx, ebx
0x1800661e2  jns     short loc_1800661F0
0x1800661e4  lea     rcx, [rsp+28h+arg_0]
0x1800661e9  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x1800661ee  jmp     short loc_18006620E
0x1800661f0  mov     rax, [rdi]
0x1800661f3  mov     rcx, rdi
0x1800661f6  mov     rax, [rax+8]
0x1800661fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661ff  lea     rcx, [rsp+28h+arg_0]
0x180066204  mov     [rsi], rdi
0x180066207  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x18006620c  xor     ebx, ebx
0x18006620e  lea     rcx, [rsp+28h+arg_8]
0x180066213  call    ??1?$MakeAllocator@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>(void)
0x180066218  mov     rsi, [rsp+28h+arg_18]
0x18006621d  mov     eax, ebx
0x18006621f  mov     rbx, [rsp+28h+arg_10]
0x180066224  add     rsp, 20h
0x180066228  pop     rdi
0x180066229  retn
```
