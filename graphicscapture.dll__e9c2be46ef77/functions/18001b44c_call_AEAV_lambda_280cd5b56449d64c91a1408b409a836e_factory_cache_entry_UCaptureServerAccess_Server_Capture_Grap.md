# ??$call@AEAV_lambda_280cd5b56449d64c91a1408b409a836e_@@@?$factory_cache_entry@UCaptureServerAccess@Server@Capture@Graphics@Windows@winrt@@UICaptureServerAccessStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_280cd5b56449d64c91a1408b409a836e_@@@Z

- ea: `0x18001b44c`
- end: `0x18001b55c`
- name: `??$call@AEAV_lambda_280cd5b56449d64c91a1408b409a836e_@@@?$factory_cache_entry@UCaptureServerAccess@Server@Capture@Graphics@Windows@winrt@@UICaptureServerAccessStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_280cd5b56449d64c91a1408b409a836e_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001be68`

## callees

- `0x180002471`
- `0x180003444`
- `0x180003580`
- `0x1800065f0`
- `0x180014570`
- `0x18001b44c`
- `0x18001b5c0`
- `0x180028010`

## string_xrefs

- `0x18001b466`: `Windows.Graphics.Capture.Server.CaptureServerAccess`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CaptureServerAccess,winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics>::call<_lambda_280cd5b56449d64c91a1408b409a836e_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        __int64 a3)
{
  signed __int64 v5; // rdi
  _QWORD v7[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+80h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+98h] [rbp+38h] BYREF

  v9 = a1;
  v7[0] = L"Windows.Graphics.Capture.Server.CaptureServerAccess";
  v7[1] = 51;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v10);
    v10 = &qword_180035948;
    _InterlockedIncrement64(&qword_180035948);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CaptureServerAccess,winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180035950);
    }
    _lambda_280cd5b56449d64c91a1408b409a836e_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CaptureServerAccess,winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics>);
    _InterlockedDecrement64(&qword_180035948);
  }
  else
  {
    _lambda_280cd5b56449d64c91a1408b409a836e_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x18001b44c  mov     [rsp-18h+arg_8], rbx
0x18001b451  mov     [rsp-18h+arg_0], rcx
0x18001b456  push    rbp
0x18001b457  push    rsi
0x18001b458  push    rdi
0x18001b459  mov     rbp, rsp
0x18001b45c  sub     rsp, 60h
0x18001b460  mov     rsi, r8
0x18001b463  mov     rbx, rdx
0x18001b466  lea     rax, aWindowsGraphic_3; "Windows.Graphics.Capture.Server.Capture"...
0x18001b46d  mov     [rbp+var_38], rax
0x18001b471  mov     [rbp+var_30], 33h ; '3'
0x18001b479  lea     rdx, [rbp+var_38]
0x18001b47d  lea     rcx, [rbp+var_28]
0x18001b481  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001b486  lea     rdx, [rbp+var_28]
0x18001b48a  lea     rcx, [rbp+arg_0]
0x18001b48e  call    ??$get_activation_factory@UICaptureServerAccessStatics@Server@Capture@Graphics@Windows@winrt@@@winrt@@YA?AUICaptureServerAccessStatics@Server@Capture@Graphics@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics>(winrt::param::hstring const &)
0x18001b493  nop
0x18001b494  mov     rdi, [rbp+arg_0]
0x18001b498  test    rdi, rdi
0x18001b49b  jz      loc_18001B530
0x18001b4a1  mov     [rbp+arg_18], 0
0x18001b4a9  mov     rax, [rdi]
0x18001b4ac  lea     r8, [rbp+arg_18]
0x18001b4b0  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001b4b7  mov     rcx, rdi
0x18001b4ba  mov     rax, [rax]
0x18001b4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4c2  mov     rax, [rbp+arg_18]
0x18001b4c6  mov     [rbp+arg_18], rax
0x18001b4ca  test    rax, rax
0x18001b4cd  jz      short loc_18001B530
0x18001b4cf  lea     rcx, [rbp+arg_18]
0x18001b4d3  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001b4d8  lea     rax, qword_180035948
0x18001b4df  mov     [rbp+arg_18], rax
0x18001b4e3  lock inc cs:qword_180035948
0x18001b4eb  xor     eax, eax
0x18001b4ed  lock cmpxchg cs:??$factory_cache_entry_v@UCaptureServerAccess@Server@Capture@Graphics@Windows@winrt@@UICaptureServerAccessStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCaptureServerAccess@Server@Capture@Graphics@Windows@winrt@@UICaptureServerAccessStatics@23456@@12@A, rdi; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CaptureServerAccess,winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CaptureServerAccess,winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CaptureServerAccess,winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics>
0x18001b4f6  jnz     short loc_18001B513
0x18001b4f8  mov     [rbp+arg_0], 0
0x18001b500  lea     rdx, stru_180035950; ListEntry
0x18001b507  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001b50e  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001b513  lea     r8, ??$factory_cache_entry_v@UCaptureServerAccess@Server@Capture@Graphics@Windows@winrt@@UICaptureServerAccessStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCaptureServerAccess@Server@Capture@Graphics@Windows@winrt@@UICaptureServerAccessStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CaptureServerAccess,winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CaptureServerAccess,winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CaptureServerAccess,winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics>
0x18001b51a  mov     rdx, rbx
0x18001b51d  mov     rcx, rsi
0x18001b520  call    ??R_lambda_280cd5b56449d64c91a1408b409a836e_@@QEBA@AEBUICaptureServerAccessStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_280cd5b56449d64c91a1408b409a836e_::operator()(winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics const &)
0x18001b525  nop
0x18001b526  lock dec cs:qword_180035948
0x18001b52e  jmp     short loc_18001B540
0x18001b530  lea     r8, [rbp+arg_0]
0x18001b534  mov     rdx, rbx
0x18001b537  mov     rcx, rsi
0x18001b53a  call    ??R_lambda_280cd5b56449d64c91a1408b409a836e_@@QEBA@AEBUICaptureServerAccessStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_280cd5b56449d64c91a1408b409a836e_::operator()(winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics const &)
0x18001b53f  nop
0x18001b540  lea     rcx, [rbp+arg_0]
0x18001b544  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001b549  mov     rax, rbx
0x18001b54c  mov     rbx, [rsp+60h+arg_8]
0x18001b554  add     rsp, 60h
0x18001b558  pop     rdi
0x18001b559  pop     rsi
0x18001b55a  pop     rbp
0x18001b55b  retn
```
