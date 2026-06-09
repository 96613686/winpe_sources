# FindMediaServerByUDN(Windows::Internal::String const &,Windows::Media::Streaming::Internal::IMediaServer * *)

- ea: `0x180025860`
- end: `0x180025ac5`
- name: `?FindMediaServerByUDN@@YAJAEBVString@Internal@Windows@@PEAPEAUIMediaServer@2Streaming@Media@3@@Z`
- size: `613`
- prototype: `__int64 __fastcall(const struct Windows::Internal::String *, struct Windows::Media::Streaming::Internal::IMediaServer **)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001073c`
- `0x18001d4e0`
- `0x1800281a0`

## callees

- `0x180001710`
- `0x180005f60`
- `0x18000f1f4`
- `0x180011930`
- `0x180011954`
- `0x180012a4c`
- `0x180021e64`
- `0x1800250dc`
- `0x180025860`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002593f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002593f`
- `ext-ms-win-casting-device-l1-1-0!GetMediaServerFromUniqueDeviceNameAsync` at `0x1800258c3`
- `ext-ms-win-casting-device-l1-1-0!GetMediaServerFromUniqueDeviceNameAsync` at `0x1800258c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800258b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800258b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025926`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025960`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025960`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall FindMediaServerByUDN(HSTRING *a1, struct Windows::Media::Streaming::Internal::IMediaServer **a2)
{
  PCWSTR StringRawBuffer; // rax
  int MediaServerFromUniqueDeviceNameAsync; // eax
  signed int v6; // r14d
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, _QWORD); // rdi
  int v9; // ebx
  HSTRING v10; // rbx
  int ActivationFactory; // eax
  __int64 v12; // rdi
  void *v13; // rax
  int (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v15)(_QWORD, GUID *, _QWORD); // rsi
  __int64 (__fastcall ***v17)(_QWORD, GUID *, _QWORD); // [rsp+20h] [rbp-50h] BYREF
  signed int v18; // [rsp+28h] [rbp-48h] BYREF
  int (__fastcall ***v19)(_QWORD, GUID *, _QWORD); // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h] BYREF
  __int64 v21; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-20h] BYREF

  v21 = 0;
  v19 = 0;
  *a2 = 0;
  v17 = 0;
  if ( (unsigned __int8)IsGetMediaServerFromUniqueDeviceNameAsyncPresent() )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
    MediaServerFromUniqueDeviceNameAsync = GetMediaServerFromUniqueDeviceNameAsync(StringRawBuffer, &v17);
    v6 = MediaServerFromUniqueDeviceNameAsync;
    v18 = MediaServerFromUniqueDeviceNameAsync;
    if ( MediaServerFromUniqueDeviceNameAsync >= 0 )
    {
      v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
      v8 = **v17;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v19);
      MediaServerFromUniqueDeviceNameAsync = v8(v7, &GUID_b04dd9b4_c7ca_5371_9dbd_b2641ac851f2, &v19);
      v6 = MediaServerFromUniqueDeviceNameAsync;
      v18 = MediaServerFromUniqueDeviceNameAsync;
    }
    v9 = MediaServerFromUniqueDeviceNameAsync;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  }
  else
  {
    if ( WindowsCreateStringReference(L"Windows.Media.Streaming.Internal.MediaServer", 0x2Cu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v10 = string;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v17);
    ActivationFactory = RoGetActivationFactory(v10, &GUID_a023e9e9_dc21_445f_8799_4bd37b572d28, &v17);
    v6 = ActivationFactory;
    v18 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = (*v17)[6](v17, (GUID *)*a1, &v19);
      v6 = ActivationFactory;
      v18 = ActivationFactory;
    }
    v9 = ActivationFactory;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v17);
  }
  if ( v9 >= 0 )
  {
    v17 = 0;
    v12 = 0;
    v13 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v20 = (__int64)v13;
    if ( v13 )
    {
      v12 = CDelegateBase<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>::CDelegateBase<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>(
              (__int64)v13,
              &v18);
      v20 = 0;
      v6 = v18;
    }
    Microsoft::WRL::Details::MakeAllocator<CThumbnailRequest>::~MakeAllocator<CThumbnailRequest>(&v20);
    v20 = v12;
    if ( v6 >= 0 )
    {
      v6 = v12 == 0 ? 0x8007000E : 0;
      if ( v12 )
      {
        v6 = CallSync<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>(
               v19,
               v12);
        if ( v6 >= 0 )
          v6 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD), struct Windows::Media::Streaming::Internal::IMediaServer **))(*v19)[8])(
                 v19,
                 a2);
      }
    }
    v14 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
    v15 = **v19;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v17);
    if ( v15(v14, &GUID_00000036_0000_0000_c000_000000000046, &v17) >= 0 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v17)[10])(v17);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v17);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v21);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180025860  mov     [rsp-18h+arg_10], rbx
0x180025865  mov     [rsp-18h+arg_18], rsi
0x18002586a  push    rbp
0x18002586b  push    rdi
0x18002586c  push    r14
0x18002586e  mov     rbp, rsp
0x180025871  sub     rsp, 70h
0x180025875  mov     rax, cs:__security_cookie
0x18002587c  xor     rax, rsp
0x18002587f  mov     [rbp+var_8], rax
0x180025883  mov     rsi, rdx
0x180025886  mov     rdi, rcx
0x180025889  mov     [rbp+var_30], 0
0x180025891  mov     [rbp+var_40], 0
0x180025899  mov     qword ptr [rdx], 0
0x1800258a0  call    IsGetMediaServerFromUniqueDeviceNameAsyncPresent
0x1800258a5  mov     [rbp+var_50], 0
0x1800258ad  test    al, al
0x1800258af  jz      short loc_180025912
0x1800258b1  xor     edx, edx; length
0x1800258b3  mov     rcx, [rdi]; string
0x1800258b6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800258bc  lea     rdx, [rbp+var_50]
0x1800258c0  mov     rcx, rax
0x1800258c3  call    cs:__imp_GetMediaServerFromUniqueDeviceNameAsync
0x1800258c9  mov     r14d, eax
0x1800258cc  mov     [rbp+var_48], eax
0x1800258cf  test    eax, eax
0x1800258d1  js      short loc_180025902
0x1800258d3  mov     rbx, [rbp+var_50]
0x1800258d7  mov     rax, [rbx]
0x1800258da  mov     rdi, [rax]
0x1800258dd  lea     rcx, [rbp+var_40]
0x1800258e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800258e6  lea     r8, [rbp+var_40]
0x1800258ea  lea     rdx, _GUID_b04dd9b4_c7ca_5371_9dbd_b2641ac851f2
0x1800258f1  mov     rcx, rbx
0x1800258f4  mov     rax, rdi
0x1800258f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258fc  mov     r14d, eax
0x1800258ff  mov     [rbp+var_48], eax
0x180025902  mov     ebx, eax
0x180025904  lea     rcx, [rbp+var_50]
0x180025908  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002590d  jmp     loc_180025998
0x180025912  lea     r9, [rbp+string]; string
0x180025916  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002591a  mov     edx, 2Ch ; ','; length
0x18002591f  lea     rcx, ?RuntimeClass_Windows_Media_Streaming_Internal_MediaServer@@3QBGB; "Windows.Media.Streaming.Internal.MediaS"...
0x180025926  call    cs:__imp_WindowsCreateStringReference
0x18002592c  test    eax, eax
0x18002592e  jns     short loc_180025945
0x180025930  xor     r9d, r9d; lpArguments
0x180025933  xor     r8d, r8d; nNumberOfArguments
0x180025936  lea     edx, [r9+1]; dwExceptionFlags
0x18002593a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002593f  call    cs:__imp_RaiseException
0x180025945  mov     rbx, [rbp+string]
0x180025949  lea     rcx, [rbp+var_50]
0x18002594d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180025952  lea     r8, [rbp+var_50]
0x180025956  lea     rdx, _GUID_a023e9e9_dc21_445f_8799_4bd37b572d28
0x18002595d  mov     rcx, rbx
0x180025960  call    cs:__imp_RoGetActivationFactory
0x180025966  mov     r14d, eax
0x180025969  mov     [rbp+var_48], eax
0x18002596c  test    eax, eax
0x18002596e  js      short loc_18002598D
0x180025970  mov     rcx, [rbp+var_50]
0x180025974  mov     rax, [rcx]
0x180025977  lea     r8, [rbp+var_40]
0x18002597b  mov     rdx, [rdi]
0x18002597e  mov     rax, [rax+30h]
0x180025982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025987  mov     r14d, eax
0x18002598a  mov     [rbp+var_48], eax
0x18002598d  mov     ebx, eax
0x18002598f  lea     rcx, [rbp+var_50]
0x180025993  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180025998  test    ebx, ebx
0x18002599a  js      loc_180025A8E
0x1800259a0  mov     [rbp+var_50], 0
0x1800259a8  xor     edi, edi
0x1800259aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800259b1  lea     ecx, [rdi+38h]; unsigned __int64
0x1800259b4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800259b9  mov     [rbp+var_38], rax
0x1800259bd  test    rax, rax
0x1800259c0  jz      short loc_1800259DD
0x1800259c2  lea     rdx, [rbp+var_48]
0x1800259c6  mov     rcx, rax
0x1800259c9  call    ??0?$CDelegateBase@U?$IAsyncOperation@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@23@@@QEAA@PEAJ@Z; CDelegateBase<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>::CDelegateBase<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>(long *)
0x1800259ce  mov     rdi, rax
0x1800259d1  mov     [rbp+var_38], 0
0x1800259d9  mov     r14d, [rbp+var_48]
0x1800259dd  lea     rcx, [rbp+var_38]
0x1800259e1  call    ??1?$MakeAllocator@VCThumbnailRequest@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CThumbnailRequest>::~MakeAllocator<CThumbnailRequest>(void)
0x1800259e6  mov     [rbp+var_38], rdi
0x1800259ea  test    r14d, r14d
0x1800259ed  js      short loc_180025A30
0x1800259ef  mov     rax, rdi
0x1800259f2  neg     rax
0x1800259f5  sbb     r14d, r14d
0x1800259f8  not     r14d
0x1800259fb  and     r14d, 8007000Eh
0x180025a02  test    rdi, rdi
0x180025a05  jz      short loc_180025A30
0x180025a07  mov     rdx, rdi
0x180025a0a  mov     rcx, [rbp+var_40]
0x180025a0e  call    ??$CallSync@U?$IAsyncOperation@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@12@K@Z; CallSync<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>(Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *> *,ulong)
0x180025a13  mov     r14d, eax
0x180025a16  test    eax, eax
0x180025a18  js      short loc_180025A30
0x180025a1a  mov     rcx, [rbp+var_40]
0x180025a1e  mov     rax, [rcx]
0x180025a21  mov     rdx, rsi
0x180025a24  mov     rax, [rax+40h]
0x180025a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a2d  mov     r14d, eax
0x180025a30  mov     rbx, [rbp+var_40]
0x180025a34  mov     rax, [rbx]
0x180025a37  mov     rsi, [rax]
0x180025a3a  lea     rcx, [rbp+var_50]
0x180025a3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180025a43  lea     r8, [rbp+var_50]
0x180025a47  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180025a4e  mov     rcx, rbx
0x180025a51  mov     rax, rsi
0x180025a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a59  nop
0x180025a5a  test    eax, eax
0x180025a5c  js      short loc_180025A6F
0x180025a5e  mov     rcx, [rbp+var_50]
0x180025a62  mov     rax, [rcx]
0x180025a65  mov     rax, [rax+50h]
0x180025a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a6e  nop
0x180025a6f  test    rdi, rdi
0x180025a72  jz      short loc_180025A84
0x180025a74  mov     rax, [rdi]
0x180025a77  mov     rcx, rdi
0x180025a7a  mov     rax, [rax+10h]
0x180025a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a83  nop
0x180025a84  lea     rcx, [rbp+var_50]
0x180025a88  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180025a8d  nop
0x180025a8e  lea     rcx, [rbp+var_40]
0x180025a92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180025a97  nop
0x180025a98  lea     rcx, [rbp+var_30]
0x180025a9c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180025aa1  mov     eax, r14d
0x180025aa4  mov     rcx, [rbp+var_8]
0x180025aa8  xor     rcx, rsp; StackCookie
0x180025aab  call    __security_check_cookie
0x180025ab0  lea     r11, [rsp+70h+var_s0]
0x180025ab5  mov     rbx, [r11+30h]
0x180025ab9  mov     rsi, [r11+38h]
0x180025abd  mov     rsp, r11
0x180025ac0  pop     r14
0x180025ac2  pop     rdi
0x180025ac3  pop     rbp
0x180025ac4  retn
```
