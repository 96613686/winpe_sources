# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180059a64`
- end: `0x180059b90`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `300`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180059b98`

## callees

- `0x18001d3ec`
- `0x18002e5ac`
- `0x18003c968`
- `0x180043438`
- `0x180059a64`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180059b21`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180059b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059b30`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rbx
  signed int v4; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v9 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>(v2);
    v3[11] = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>'};
    *((_QWORD *)v3 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v3 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>'::`2'::FTMEventDelegate::`vftable';
    v3[12] = 0;
    *((_QWORD *)v3 + 7) = 0;
    v8 = v3;
    v9 = 0;
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
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
      *a1 = v3;
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v8);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v8);
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
0x180059a64  mov     [rsp+arg_10], rbx
0x180059a69  mov     [rsp+arg_18], rsi
0x180059a6e  push    rdi
0x180059a6f  sub     rsp, 20h
0x180059a73  mov     rsi, rcx
0x180059a76  mov     qword ptr [rcx], 0
0x180059a7d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180059a84  mov     ecx, 40h ; '@'; unsigned __int64
0x180059a89  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180059a8e  mov     rbx, rax
0x180059a91  mov     [rsp+28h+arg_8], rax
0x180059a96  test    rax, rax
0x180059a99  jnz     short loc_180059AA5
0x180059a9b  mov     edi, 8007000Eh
0x180059aa0  jmp     loc_180059B74
0x180059aa5  mov     rcx, rbx
0x180059aa8  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>(void)
0x180059aad  mov     dword ptr [rbx+2Ch], 1
0x180059ab4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>'}
0x180059abb  mov     [rbx], rax
0x180059abe  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180059ac5  mov     [rbx+8], rax
0x180059ac9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180059ad0  test    rcx, rcx
0x180059ad3  jz      short loc_180059AE2
0x180059ad5  mov     rax, [rcx]
0x180059ad8  mov     rax, [rax+8]
0x180059adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ae1  nop
0x180059ae2  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>'}
0x180059ae9  mov     [rbx], rax
0x180059aec  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180059af3  mov     [rbx+8], rax
0x180059af7  mov     dword ptr [rbx+30h], 0
0x180059afe  mov     qword ptr [rbx+38h], 0
0x180059b06  mov     [rsp+28h+arg_0], rbx
0x180059b0b  mov     [rsp+28h+arg_8], 0
0x180059b14  mov     r9d, 1F0003h; dwDesiredAccess
0x180059b1a  xor     r8d, r8d; dwFlags
0x180059b1d  xor     edx, edx; lpName
0x180059b1f  xor     ecx, ecx; lpEventAttributes
0x180059b21  call    cs:__imp_CreateEventExW
0x180059b27  mov     [rbx+38h], rax
0x180059b2b  test    rax, rax
0x180059b2e  jnz     short loc_180059B55
0x180059b30  call    cs:__imp_GetLastError
0x180059b36  mov     edi, eax
0x180059b38  test    eax, eax
0x180059b3a  jle     short loc_180059B45
0x180059b3c  movzx   edi, ax
0x180059b3f  or      edi, 80070000h
0x180059b45  test    edi, edi
0x180059b47  jns     short loc_180059B55
0x180059b49  lea     rcx, [rsp+28h+arg_0]
0x180059b4e  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180059b53  jmp     short loc_180059B74
0x180059b55  mov     rax, [rbx]
0x180059b58  mov     rcx, rbx
0x180059b5b  mov     rax, [rax+8]
0x180059b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b64  nop
0x180059b65  mov     [rsi], rbx
0x180059b68  lea     rcx, [rsp+28h+arg_0]
0x180059b6d  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180059b72  xor     edi, edi
0x180059b74  lea     rcx, [rsp+28h+arg_8]
0x180059b79  call    ??1?$MakeAllocator@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>(void)
0x180059b7e  mov     eax, edi
0x180059b80  mov     rbx, [rsp+28h+arg_10]
0x180059b85  mov     rsi, [rsp+28h+arg_18]
0x180059b8a  add     rsp, 20h
0x180059b8e  pop     rdi
0x180059b8f  retn
```
