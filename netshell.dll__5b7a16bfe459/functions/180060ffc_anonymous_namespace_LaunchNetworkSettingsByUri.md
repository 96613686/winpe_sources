# _anonymous_namespace_::LaunchNetworkSettingsByUri

- ea: `0x180060ffc`
- end: `0x18006128e`
- name: `_anonymous_namespace_::LaunchNetworkSettingsByUri`
- size: `658`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180046650`

## callees

- `0x18001e1e0`
- `0x18004ccc4`
- `0x180060e4c`
- `0x180060fb0`
- `0x180060ffc`
- `0x180061300`
- `0x180061368`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18006117e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18006117e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006118d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006118d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006122d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006122d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006105b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800610f6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006105b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800610f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006125f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006125f`
- `ole32!CoWaitForMultipleHandles` at `0x18006121c`
- `ole32!CoWaitForMultipleHandles` at `0x18006121c`

## string_xrefs

- `0x180061020`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 anonymous_namespace_::LaunchNetworkSettingsByUri()
{
  __int64 v0; // rbx
  int ActivationFactory; // esi
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, HSTRING, __int64 *); // rbx
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rdi
  int v9; // eax
  __int64 (__fastcall *v10)(__int64, __int64, __int64 *); // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  __int64 *v13; // rax
  __int64 v14; // rbx
  HANDLE pHandles; // [rsp+30h] [rbp-39h] BYREF
  DWORD dwindex[2]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v18; // [rsp+40h] [rbp-29h] BYREF
  __int64 v19; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-19h] BYREF
  __int64 v21; // [rsp+58h] [rbp-11h] BYREF
  HSTRING string; // [rsp+60h] [rbp-9h] BYREF
  __int64 v23; // [rsp+68h] [rbp-1h] BYREF
  HANDLE v24; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+90h] [rbp+27h]

  v23 = 0;
  v26 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v0 = v26;
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v23);
  string = 0;
  ActivationFactory = RoGetActivationFactory(v0, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v23);
  if ( ActivationFactory >= 0 )
    ActivationFactory = Microsoft::WRL::Wrappers::HString::Set(
                          (Microsoft::WRL::Wrappers::HString *)&string,
                          L"ms-availablenetworks:",
                          0x15u);
  v21 = 0;
  if ( ActivationFactory >= 0 )
  {
    v2 = v23;
    v3 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v23 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v21);
    ActivationFactory = v3(v2, string, &v21);
  }
  v4 = 0;
  v20 = 0;
  if ( ActivationFactory >= 0 )
  {
    v26 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Launcher",
      0x18u,
      0x17u);
    v5 = v26;
    Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v20);
    v6 = RoGetActivationFactory(v5, &GUID_00000035_0000_0000_c000_000000000046, &v20);
    v4 = v20;
    ActivationFactory = v6;
  }
  v19 = 0;
  v7 = 0;
  if ( ActivationFactory >= 0 )
  {
    v8 = **v4;
    Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v19);
    v9 = v8(v4, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v19);
    v7 = v19;
    ActivationFactory = v9;
  }
  v18 = 0;
  if ( ActivationFactory >= 0 )
  {
    v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v7 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v18);
    ActivationFactory = v10(v7, v21, &v18);
  }
  pHandles = 0;
  if ( ActivationFactory >= 0 )
  {
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    pHandles = Event;
    if ( !Event )
    {
      LastError = GetLastError();
      ActivationFactory = LastError;
      if ( LastError > 0 )
        ActivationFactory = (unsigned __int16)LastError | 0x80070000;
      if ( ActivationFactory < 0 )
        goto LABEL_23;
      Event = pHandles;
    }
    v24 = Event;
    v13 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_bool_unsigned_char___::___Windows::Foundation::IAsyncOperation_bool____enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_bool___lambda_e16d6350a3d9cf5b29d8f49fb2cc75b4___1_Windows::Foundation::IAsyncOperation_bool____enum_ABI::Windows::Foundation::AsyncStatus___lambda_e16d6350a3d9cf5b29d8f49fb2cc75b4___(
                       dwindex,
                       &v24);
    v14 = *v13;
    *v13 = 0;
    if ( *(_QWORD *)dwindex )
    {
      *(_QWORD *)dwindex = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::Release();
    }
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 48LL))(v18, v14);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( ActivationFactory >= 0 )
    {
      dwindex[0] = 0;
      ActivationFactory = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, dwindex);
    }
LABEL_23:
    if ( pHandles )
    {
      CloseHandle(pHandles);
      pHandles = 0;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v21);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v23);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180060ffc  push    rbp
0x180060ffe  push    rbx
0x180060fff  push    rsi
0x180061000  push    rdi
0x180061001  push    r14
0x180061003  lea     rbp, [rsp-37h]
0x180061008  sub     rsp, 0A0h
0x18006100f  mov     rax, cs:__security_cookie
0x180061016  xor     rax, rsp
0x180061019  mov     [rbp+57h+var_28], rax
0x18006101d  xor     r14d, r14d
0x180061020  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180061027  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18006102b  mov     [rbp+57h+var_58], r14
0x18006102f  mov     [rbp+57h+var_30], r14
0x180061033  lea     r9d, [r14+16h]; unsigned int
0x180061037  lea     r8d, [r14+17h]; unsigned int
0x18006103b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180061040  mov     rbx, [rbp+57h+var_30]
0x180061044  lea     rcx, [rbp+57h+var_58]
0x180061048  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x18006104d  lea     r8, [rbp+57h+var_58]
0x180061051  mov     rcx, rbx
0x180061054  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18006105b  call    cs:__imp_RoGetActivationFactory
0x180061061  mov     [rbp+57h+string], r14
0x180061065  mov     esi, eax
0x180061067  test    eax, eax
0x180061069  js      short loc_180061081
0x18006106b  lea     r8d, [r14+15h]; unsigned int
0x18006106f  lea     rdx, aMsAvailablenet; "ms-availablenetworks:"
0x180061076  lea     rcx, [rbp+57h+string]; this
0x18006107a  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18006107f  mov     esi, eax
0x180061081  mov     [rbp+57h+var_68], r14
0x180061085  test    esi, esi
0x180061087  js      short loc_1800610B2
0x180061089  mov     rdi, [rbp+57h+var_58]
0x18006108d  lea     rcx, [rbp+57h+var_68]
0x180061091  mov     rax, [rdi]
0x180061094  mov     rbx, [rax+30h]
0x180061098  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x18006109d  mov     rdx, [rbp+57h+string]
0x1800610a1  lea     r8, [rbp+57h+var_68]
0x1800610a5  mov     rcx, rdi
0x1800610a8  mov     rax, rbx
0x1800610ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800610b0  mov     esi, eax
0x1800610b2  mov     rbx, r14
0x1800610b5  mov     [rbp+57h+var_70], rbx
0x1800610b9  test    esi, esi
0x1800610bb  js      short loc_180061102
0x1800610bd  mov     r9d, 17h; unsigned int
0x1800610c3  mov     [rbp+57h+var_30], r14
0x1800610c7  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x1800610ce  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800610d2  lea     r8d, [r9+1]; unsigned int
0x1800610d6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800610db  mov     rbx, [rbp+57h+var_30]
0x1800610df  lea     rcx, [rbp+57h+var_70]
0x1800610e3  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x1800610e8  lea     r8, [rbp+57h+var_70]
0x1800610ec  mov     rcx, rbx
0x1800610ef  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x1800610f6  call    cs:__imp_RoGetActivationFactory
0x1800610fc  mov     rbx, [rbp+57h+var_70]
0x180061100  mov     esi, eax
0x180061102  mov     [rbp+57h+var_78], r14
0x180061106  mov     rdi, r14
0x180061109  test    esi, esi
0x18006110b  js      short loc_180061138
0x18006110d  mov     rax, [rbx]
0x180061110  lea     rcx, [rbp+57h+var_78]
0x180061114  mov     rdi, [rax]
0x180061117  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x18006111c  lea     r8, [rbp+57h+var_78]
0x180061120  mov     rcx, rbx
0x180061123  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x18006112a  mov     rax, rdi
0x18006112d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061132  mov     rdi, [rbp+57h+var_78]
0x180061136  mov     esi, eax
0x180061138  mov     [rbp+57h+var_80], r14
0x18006113c  test    esi, esi
0x18006113e  js      short loc_180061165
0x180061140  mov     rax, [rdi]
0x180061143  lea     rcx, [rbp+57h+var_80]
0x180061147  mov     rbx, [rax+40h]
0x18006114b  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180061150  mov     rdx, [rbp+57h+var_68]
0x180061154  lea     r8, [rbp+57h+var_80]
0x180061158  mov     rcx, rdi
0x18006115b  mov     rax, rbx
0x18006115e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061163  mov     esi, eax
0x180061165  mov     [rbp+57h+pHandles], r14
0x180061169  test    esi, esi
0x18006116b  js      loc_180061237
0x180061171  mov     r9d, 1F0003h; dwDesiredAccess
0x180061177  xor     r8d, r8d; dwFlags
0x18006117a  xor     edx, edx; lpName
0x18006117c  xor     ecx, ecx; lpEventAttributes
0x18006117e  call    cs:__imp_CreateEventExW
0x180061184  mov     [rbp+57h+pHandles], rax
0x180061188  test    rax, rax
0x18006118b  jnz     short loc_1800611AA
0x18006118d  call    cs:__imp_GetLastError
0x180061193  mov     esi, eax
0x180061195  test    eax, eax
0x180061197  jle     short loc_1800611A2
0x180061199  movzx   esi, ax
0x18006119c  or      esi, 80070000h
0x1800611a2  test    esi, esi
0x1800611a4  js      short loc_180061224
0x1800611a6  mov     rax, [rbp+57h+pHandles]
0x1800611aa  lea     rdx, [rbp+57h+var_50]
0x1800611ae  mov     [rbp+57h+var_50], rax
0x1800611b2  lea     rcx, [rbp+57h+dwindex]
0x1800611b6  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_Windows__Foundation__Internal__AggregateType_bool_unsigned_char________Windows__Foundation__IAsyncOperation_bool____enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Windows__Foundation__IAsyncOperationCompletedHandler_bool___lambda_e16d6350a3d9cf5b29d8f49fb2cc75b4___1_Windows__Foundation__IAsyncOperation_bool____enum_ABI__Windows__Foundation__AsyncStatus___lambda_e16d6350a3d9cf5b29d8f49fb2cc75b4___
0x1800611bb  mov     rbx, [rax]
0x1800611be  mov     [rax], r14
0x1800611c1  mov     rcx, qword ptr [rbp+57h+dwindex]
0x1800611c5  test    rcx, rcx
0x1800611c8  jz      short loc_1800611D3
0x1800611ca  mov     qword ptr [rbp+57h+dwindex], r14
0x1800611ce  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::Release(void)
0x1800611d3  mov     rcx, [rbp+57h+var_80]
0x1800611d7  mov     rdx, rbx
0x1800611da  mov     rax, [rcx]
0x1800611dd  mov     rax, [rax+30h]
0x1800611e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800611e6  mov     esi, eax
0x1800611e8  test    rbx, rbx
0x1800611eb  jz      short loc_1800611FC
0x1800611ed  mov     rax, [rbx]
0x1800611f0  mov     rcx, rbx
0x1800611f3  mov     rax, [rax+10h]
0x1800611f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800611fc  test    esi, esi
0x1800611fe  js      short loc_180061224
0x180061200  lea     rax, [rbp+57h+dwindex]
0x180061204  mov     [rbp+57h+dwindex], r14d
0x180061208  lea     r9, [rbp+57h+pHandles]; pHandles
0x18006120c  mov     [rsp+0C0h+lpdwindex], rax; lpdwindex
0x180061211  mov     r8d, 1; cHandles
0x180061217  or      edx, 0FFFFFFFFh; dwTimeout
0x18006121a  xor     ecx, ecx; dwFlags
0x18006121c  call    cs:__imp_CoWaitForMultipleHandles
0x180061222  mov     esi, eax
0x180061224  mov     rcx, [rbp+57h+pHandles]; hObject
0x180061228  test    rcx, rcx
0x18006122b  jz      short loc_180061237
0x18006122d  call    cs:__imp_CloseHandle
0x180061233  mov     [rbp+57h+pHandles], r14
0x180061237  lea     rcx, [rbp+57h+var_80]
0x18006123b  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180061240  lea     rcx, [rbp+57h+var_78]
0x180061244  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180061249  lea     rcx, [rbp+57h+var_70]
0x18006124d  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180061252  lea     rcx, [rbp+57h+var_68]
0x180061256  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x18006125b  mov     rcx, [rbp+57h+string]; string
0x18006125f  call    cs:__imp_WindowsDeleteString
0x180061265  lea     rcx, [rbp+57h+var_58]
0x180061269  mov     [rbp+57h+string], r14
0x18006126d  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180061272  mov     eax, esi
0x180061274  mov     rcx, [rbp+57h+var_28]
0x180061278  xor     rcx, rsp; StackCookie
0x18006127b  call    __security_check_cookie
0x180061280  add     rsp, 0A0h
0x180061287  pop     r14
0x180061289  pop     rdi
0x18006128a  pop     rsi
0x18006128b  pop     rbx
0x18006128c  pop     rbp
0x18006128d  retn
```
