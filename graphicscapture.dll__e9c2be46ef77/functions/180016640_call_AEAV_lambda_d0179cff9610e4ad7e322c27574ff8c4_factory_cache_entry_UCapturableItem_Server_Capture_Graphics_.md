# ??$call@AEAV_lambda_d0179cff9610e4ad7e322c27574ff8c4_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_d0179cff9610e4ad7e322c27574ff8c4_@@@Z

- ea: `0x180016640`
- end: `0x180016750`
- name: `??$call@AEAV_lambda_d0179cff9610e4ad7e322c27574ff8c4_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_d0179cff9610e4ad7e322c27574ff8c4_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800188e4`

## callees

- `0x180002471`
- `0x180003444`
- `0x180003580`
- `0x1800065f0`
- `0x180013a88`
- `0x180016640`
- `0x180017e2c`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_d0179cff9610e4ad7e322c27574ff8c4_ &>(
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
  v7[0] = L"Windows.Graphics.Capture.Server.CapturableItem";
  v7[1] = 46;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref((__int64 *)&v10);
    v10 = &qword_180035928;
    _InterlockedIncrement64(&qword_180035928);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    _lambda_d0179cff9610e4ad7e322c27574ff8c4_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
    _InterlockedDecrement64(&qword_180035928);
  }
  else
  {
    _lambda_d0179cff9610e4ad7e322c27574ff8c4_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x180016640  mov     [rsp-18h+arg_8], rbx
0x180016645  mov     [rsp-18h+arg_0], rcx
0x18001664a  push    rbp
0x18001664b  push    rsi
0x18001664c  push    rdi
0x18001664d  mov     rbp, rsp
0x180016650  sub     rsp, 60h
0x180016654  mov     rsi, r8
0x180016657  mov     rbx, rdx
0x18001665a  lea     rax, aWindowsGraphic_6; "Windows.Graphics.Capture.Server.Captura"...
0x180016661  mov     [rbp+var_38], rax
0x180016665  mov     [rbp+var_30], 2Eh ; '.'
0x18001666d  lea     rdx, [rbp+var_38]
0x180016671  lea     rcx, [rbp+var_28]
0x180016675  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001667a  lea     rdx, [rbp+var_28]
0x18001667e  lea     rcx, [rbp+arg_0]
0x180016682  call    ??$get_activation_factory@UICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@winrt@@YA?AUICapturableItemStatics@Server@Capture@Graphics@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>(winrt::param::hstring const &)
0x180016687  nop
0x180016688  mov     rdi, [rbp+arg_0]
0x18001668c  test    rdi, rdi
0x18001668f  jz      loc_180016724
0x180016695  mov     [rbp+arg_18], 0
0x18001669d  mov     rax, [rdi]
0x1800166a0  lea     r8, [rbp+arg_18]
0x1800166a4  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800166ab  mov     rcx, rdi
0x1800166ae  mov     rax, [rax]
0x1800166b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166b6  mov     rax, [rbp+arg_18]
0x1800166ba  mov     [rbp+arg_18], rax
0x1800166be  test    rax, rax
0x1800166c1  jz      short loc_180016724
0x1800166c3  lea     rcx, [rbp+arg_18]
0x1800166c7  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x1800166cc  lea     rax, qword_180035928
0x1800166d3  mov     [rbp+arg_18], rax
0x1800166d7  lock inc cs:qword_180035928
0x1800166df  xor     eax, eax
0x1800166e1  lock cmpxchg cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, rdi; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x1800166ea  jnz     short loc_180016707
0x1800166ec  mov     [rbp+arg_0], 0
0x1800166f4  lea     rdx, ListEntry; ListEntry
0x1800166fb  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180016702  call    WINRT_IMPL_InterlockedPushEntrySList
0x180016707  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x18001670e  mov     rdx, rbx
0x180016711  mov     rcx, rsi
0x180016714  call    ??R_lambda_d0179cff9610e4ad7e322c27574ff8c4_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_d0179cff9610e4ad7e322c27574ff8c4_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x180016719  nop
0x18001671a  lock dec cs:qword_180035928
0x180016722  jmp     short loc_180016734
0x180016724  lea     r8, [rbp+arg_0]
0x180016728  mov     rdx, rbx
0x18001672b  mov     rcx, rsi
0x18001672e  call    ??R_lambda_d0179cff9610e4ad7e322c27574ff8c4_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_d0179cff9610e4ad7e322c27574ff8c4_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x180016733  nop
0x180016734  lea     rcx, [rbp+arg_0]
0x180016738  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001673d  mov     rax, rbx
0x180016740  mov     rbx, [rsp+60h+arg_8]
0x180016748  add     rsp, 60h
0x18001674c  pop     rdi
0x18001674d  pop     rsi
0x18001674e  pop     rbp
0x18001674f  retn
```
