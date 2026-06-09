# ??$call@AEAV_lambda_84dad07838de48a565098aab66ca8ecd_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_84dad07838de48a565098aab66ca8ecd_@@@Z

- ea: `0x180016528`
- end: `0x180016638`
- name: `??$call@AEAV_lambda_84dad07838de48a565098aab66ca8ecd_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_84dad07838de48a565098aab66ca8ecd_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180019b6c`

## callees

- `0x180002471`
- `0x180003444`
- `0x180003580`
- `0x1800065f0`
- `0x180013a88`
- `0x180016528`
- `0x180017d14`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_84dad07838de48a565098aab66ca8ecd_ &>(
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
    _lambda_84dad07838de48a565098aab66ca8ecd_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
    _InterlockedDecrement64(&qword_180035928);
  }
  else
  {
    _lambda_84dad07838de48a565098aab66ca8ecd_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x180016528  mov     [rsp-18h+arg_8], rbx
0x18001652d  mov     [rsp-18h+arg_0], rcx
0x180016532  push    rbp
0x180016533  push    rsi
0x180016534  push    rdi
0x180016535  mov     rbp, rsp
0x180016538  sub     rsp, 60h
0x18001653c  mov     rsi, r8
0x18001653f  mov     rbx, rdx
0x180016542  lea     rax, aWindowsGraphic_6; "Windows.Graphics.Capture.Server.Captura"...
0x180016549  mov     [rbp+var_38], rax
0x18001654d  mov     [rbp+var_30], 2Eh ; '.'
0x180016555  lea     rdx, [rbp+var_38]
0x180016559  lea     rcx, [rbp+var_28]
0x18001655d  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x180016562  lea     rdx, [rbp+var_28]
0x180016566  lea     rcx, [rbp+arg_0]
0x18001656a  call    ??$get_activation_factory@UICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@winrt@@YA?AUICapturableItemStatics@Server@Capture@Graphics@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>(winrt::param::hstring const &)
0x18001656f  nop
0x180016570  mov     rdi, [rbp+arg_0]
0x180016574  test    rdi, rdi
0x180016577  jz      loc_18001660C
0x18001657d  mov     [rbp+arg_18], 0
0x180016585  mov     rax, [rdi]
0x180016588  lea     r8, [rbp+arg_18]
0x18001658c  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180016593  mov     rcx, rdi
0x180016596  mov     rax, [rax]
0x180016599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001659e  mov     rax, [rbp+arg_18]
0x1800165a2  mov     [rbp+arg_18], rax
0x1800165a6  test    rax, rax
0x1800165a9  jz      short loc_18001660C
0x1800165ab  lea     rcx, [rbp+arg_18]
0x1800165af  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x1800165b4  lea     rax, qword_180035928
0x1800165bb  mov     [rbp+arg_18], rax
0x1800165bf  lock inc cs:qword_180035928
0x1800165c7  xor     eax, eax
0x1800165c9  lock cmpxchg cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, rdi; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x1800165d2  jnz     short loc_1800165EF
0x1800165d4  mov     [rbp+arg_0], 0
0x1800165dc  lea     rdx, ListEntry; ListEntry
0x1800165e3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800165ea  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800165ef  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x1800165f6  mov     rdx, rbx
0x1800165f9  mov     rcx, rsi
0x1800165fc  call    ??R_lambda_84dad07838de48a565098aab66ca8ecd_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_84dad07838de48a565098aab66ca8ecd_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x180016601  nop
0x180016602  lock dec cs:qword_180035928
0x18001660a  jmp     short loc_18001661C
0x18001660c  lea     r8, [rbp+arg_0]
0x180016610  mov     rdx, rbx
0x180016613  mov     rcx, rsi
0x180016616  call    ??R_lambda_84dad07838de48a565098aab66ca8ecd_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_84dad07838de48a565098aab66ca8ecd_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x18001661b  nop
0x18001661c  lea     rcx, [rbp+arg_0]
0x180016620  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180016625  mov     rax, rbx
0x180016628  mov     rbx, [rsp+60h+arg_8]
0x180016630  add     rsp, 60h
0x180016634  pop     rdi
0x180016635  pop     rsi
0x180016636  pop     rbp
0x180016637  retn
```
