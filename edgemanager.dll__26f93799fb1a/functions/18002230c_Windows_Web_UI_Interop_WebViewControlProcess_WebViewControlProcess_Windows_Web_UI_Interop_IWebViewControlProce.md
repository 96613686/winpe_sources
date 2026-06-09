# Windows::Web::UI::Interop::WebViewControlProcess::WebViewControlProcess(Windows::Web::UI::Interop::IWebViewControlProcessOptions *,Windows::Web::UI::Interop::WebViewControlProcessFactory *)

- ea: `0x18002230c`
- end: `0x1800224ac`
- name: `??0WebViewControlProcess@Interop@UI@Web@Windows@@QEAA@PEAUIWebViewControlProcessOptions@1234@PEAVWebViewControlProcessFactory@1234@@Z`
- size: `416`
- prototype: `__int64 __fastcall(Windows::Web::UI::Interop::WebViewControlProcess *__hidden this, struct Windows::Web::UI::Interop::IWebViewControlProcessOptions *, struct Windows::Web::UI::Interop::WebViewControlProcessFactory *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004f558`

## callees

- `0x18000b0ec`
- `0x18002230c`
- `0x1800224b4`
- `0x18002ebb0`
- `0x180035b88`
- `0x1800508fc`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180022397`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800223a1`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180022397`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800223a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002244f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002244f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
RTL_SRWLOCK *__fastcall Windows::Web::UI::Interop::WebViewControlProcess::WebViewControlProcess(
        RTL_SRWLOCK *this,
        __int64 (__fastcall ***a2)(struct Windows::Web::UI::Interop::IWebViewControlProcessOptions *, GUID *, __int64 *),
        struct Windows::Web::UI::Interop::WebViewControlProcessFactory *a3)
{
  __int64 (__fastcall *v6)(struct Windows::Web::UI::Interop::IWebViewControlProcessOptions *, GUID *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  void (__fastcall *v9)(__int64, RTL_SRWLOCK *); // rbx
  __int64 v10; // rcx
  int v11; // eax
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Web::UI::Interop::IWebViewControlProcess,IWebViewControlProcessInternal>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Web::UI::Interop::IWebViewControlProcess,IWebViewControlProcessInternal>();
  this->Ptr = &Microsoft::WRL::RuntimeClass<Windows::Web::UI::Interop::IWebViewControlProcess,IWebViewControlProcessInternal>::`vftable';
  this[1].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Web::UI::Interop::IWebViewControlProcess,IWebViewControlProcessInternal>::`vftable'{for `IWeakReferenceSource'};
  this[2].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Web::UI::Interop::IWebViewControlProcess,IWebViewControlProcessInternal>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWebViewControlProcessInternal>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  this->Ptr = &Windows::Web::UI::Interop::WebViewControlProcess::`vftable';
  this[1].Ptr = &Windows::Web::UI::Interop::WebViewControlProcess::`vftable'{for `IWeakReferenceSource'};
  this[2].Ptr = &Windows::Web::UI::Interop::WebViewControlProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWebViewControlProcessInternal>'};
  this[6].Ptr = 0;
  InitializeSRWLock(this + 7);
  InitializeSRWLock(this + 8);
  this[10].Ptr = 0;
  this[11].Ptr = 0;
  this[12].Ptr = 0;
  this[13].Ptr = a3;
  if ( a3 )
    Microsoft::WRL::ActivationFactory<Windows::Web::UI::Interop::IWebViewControlProcessFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(a3);
  LODWORD(this[14].Ptr) = -1;
  v15 = 0;
  v6 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  v7 = v6(
         (struct Windows::Web::UI::Interop::IWebViewControlProcessOptions *)a2,
         &GUID_aab732b8_c158_4dba_b361_86d010c148a9,
         &v15);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocess.cpp",
      (const char *)(unsigned int)v7,
      v13);
  v8 = v15;
  v9 = *(void (__fastcall **)(__int64, RTL_SRWLOCK *))(*(_QWORD *)v15 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&this[11]);
  v9(v8, this + 11);
  LODWORD(this[5].Ptr) = GetCurrentThreadId();
  LOBYTE(this[9].Ptr) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&this[12]);
  v11 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Web::UI::Interop::WebViewControl,Windows::Foundation::Collections::Internal::Vector<Windows::Web::UI::Interop::WebViewControl *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Web::UI::Interop::WebViewControl *>>>(
          v10,
          &this[12]);
  if ( v11 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocess.cpp",
      (const char *)(unsigned int)v11,
      v13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  return this;
}

```

## disassembly

```asm
0x18002230c  mov     [rsp+arg_10], rbx
0x180022311  mov     [rsp+arg_18], rsi
0x180022316  mov     [rsp+arg_0], rcx
0x18002231b  push    rdi
0x18002231c  push    r14
0x18002231e  push    r15; int
0x180022320  sub     rsp, 20h
0x180022324  mov     rbx, r8
0x180022327  mov     rdi, rdx
0x18002232a  mov     rsi, rcx
0x18002232d  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIWebViewControlProcess@Interop@UI@Web@Windows@@UIWebViewControlProcessInternal@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Web::UI::Interop::IWebViewControlProcess,IWebViewControlProcessInternal>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Web::UI::Interop::IWebViewControlProcess,IWebViewControlProcessInternal>(void)
0x180022332  lea     r10, ??_7?$RuntimeClass@UIWebViewControlProcess@Interop@UI@Web@Windows@@UIWebViewControlProcessInternal@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::Web::UI::Interop::IWebViewControlProcess,IWebViewControlProcessInternal>::`vftable'
0x180022339  mov     [rsi], r10
0x18002233c  lea     rax, ??_7?$RuntimeClass@UIWebViewControlProcess@Interop@UI@Web@Windows@@UIWebViewControlProcessInternal@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::Web::UI::Interop::IWebViewControlProcess,IWebViewControlProcessInternal>::`vftable'{for `IWeakReferenceSource'}
0x180022343  mov     [rsi+8], rax
0x180022347  lea     rax, ??_7?$RuntimeClass@UIWebViewControlProcess@Interop@UI@Web@Windows@@UIWebViewControlProcessInternal@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWebViewControlProcessInternal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Web::UI::Interop::IWebViewControlProcess,IWebViewControlProcessInternal>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWebViewControlProcessInternal>'}
0x18002234e  mov     [rsi+10h], rax
0x180022352  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180022359  test    rcx, rcx
0x18002235c  jz      short loc_18002236B
0x18002235e  mov     rax, [rcx]
0x180022361  mov     rax, [rax+8]
0x180022365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002236a  nop
0x18002236b  lea     rax, ??_7WebViewControlProcess@Interop@UI@Web@Windows@@6B@; const Windows::Web::UI::Interop::WebViewControlProcess::`vftable'
0x180022372  mov     [rsi], rax
0x180022375  lea     rax, ??_7WebViewControlProcess@Interop@UI@Web@Windows@@6BIWeakReferenceSource@@@; const Windows::Web::UI::Interop::WebViewControlProcess::`vftable'{for `IWeakReferenceSource'}
0x18002237c  mov     [rsi+8], rax
0x180022380  lea     rax, ??_7WebViewControlProcess@Interop@UI@Web@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWebViewControlProcessInternal@@@Details@WRL@Microsoft@@@; const Windows::Web::UI::Interop::WebViewControlProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWebViewControlProcessInternal>'}
0x180022387  mov     [rsi+10h], rax
0x18002238b  mov     qword ptr [rsi+30h], 0
0x180022393  lea     rcx, [rsi+38h]; SRWLock
0x180022397  call    cs:__imp_InitializeSRWLock
0x18002239d  lea     rcx, [rsi+40h]; SRWLock
0x1800223a1  call    cs:__imp_InitializeSRWLock
0x1800223a7  nop
0x1800223a8  mov     qword ptr [rsi+50h], 0
0x1800223b0  lea     r14, [rsi+58h]
0x1800223b4  mov     qword ptr [r14], 0
0x1800223bb  lea     r15, [rsi+60h]
0x1800223bf  mov     qword ptr [r15], 0
0x1800223c6  mov     [rsi+68h], rbx
0x1800223ca  test    rbx, rbx
0x1800223cd  jz      short loc_1800223D8
0x1800223cf  mov     rcx, rbx
0x1800223d2  call    ?AddRef@?$ActivationFactory@UIWebViewControlProcessFactory@Interop@UI@Web@Windows@@VNil@Details@WRL@Microsoft@@V6789@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Windows::Web::UI::Interop::IWebViewControlProcessFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)
0x1800223d7  nop
0x1800223d8  mov     dword ptr [rsi+70h], 0FFFFFFFFh
0x1800223df  mov     [rsp+38h+arg_8], 0
0x1800223e8  mov     rax, [rdi]
0x1800223eb  mov     rbx, [rax]
0x1800223ee  lea     rcx, [rsp+38h+arg_8]
0x1800223f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800223f8  lea     r8, [rsp+38h+arg_8]
0x1800223fd  lea     rdx, _GUID_aab732b8_c158_4dba_b361_86d010c148a9
0x180022404  mov     rcx, rdi
0x180022407  mov     rax, rbx
0x18002240a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002240f  mov     rcx, [rsp+38h]; this
0x180022414  test    eax, eax
0x180022416  jns     short loc_18002242D
0x180022418  mov     r9d, eax; char *
0x18002241b  lea     r8, aOnecoreuapInet_28; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180022422  mov     edx, 22h ; '"'; void *
0x180022427  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18002242d  mov     rdi, [rsp+38h+arg_8]
0x180022432  mov     rax, [rdi]
0x180022435  mov     rbx, [rax+50h]
0x180022439  mov     rcx, r14
0x18002243c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022441  mov     rdx, r14
0x180022444  mov     rcx, rdi
0x180022447  mov     rax, rbx
0x18002244a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002244f  call    cs:__imp_GetCurrentThreadId
0x180022455  mov     [rsi+28h], eax
0x180022458  mov     byte ptr [rsi+48h], 0
0x18002245c  mov     rcx, r15
0x18002245f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022464  mov     rdx, r15
0x180022467  call    ??$CreateExternalObjectVector@VWebViewControl@Interop@UI@Web@Windows@@V?$Vector@PEAVWebViewControl@Interop@UI@Web@Windows@@U?$DefaultEqualityPredicate@PEAVWebViewControl@Interop@UI@Web@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVWebViewControl@Interop@UI@Web@Windows@@@7895@U?$DefaultVectorOptions@PEAVWebViewControl@Interop@UI@Web@Windows@@@7895@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVWebViewControl@Interop@UI@Web@Windows@@U?$DefaultEqualityPredicate@PEAVWebViewControl@Interop@UI@Web@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVWebViewControl@Interop@UI@Web@Windows@@@7895@U?$DefaultVectorOptions@PEAVWebViewControl@Interop@UI@Web@Windows@@@7895@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Web::UI::Interop::WebViewControl,Windows::Foundation::Collections::Internal::Vector<Windows::Web::UI::Interop::WebViewControl *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Web::UI::Interop::WebViewControl *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Web::UI::Interop::WebViewControl *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Web::UI::Interop::WebViewControl *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Web::UI::Interop::WebViewControl *>> * *)
0x18002246c  mov     rcx, [rsp+38h]; this
0x180022471  test    eax, eax
0x180022473  jns     short loc_18002248A
0x180022475  mov     r9d, eax; char *
0x180022478  lea     r8, aOnecoreuapInet_28; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18002247f  mov     edx, 27h ; '''; void *
0x180022484  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18002248a  lea     rcx, [rsp+38h+arg_8]
0x18002248f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022494  nop
0x180022495  mov     rax, rsi
0x180022498  mov     rbx, [rsp+38h+arg_10]
0x18002249d  mov     rsi, [rsp+38h+arg_18]
0x1800224a2  add     rsp, 20h
0x1800224a6  pop     r15
0x1800224a8  pop     r14
0x1800224aa  pop     rdi
0x1800224ab  retn
```
