# ??$call@AEAV_lambda_cedeb74fb6dfb8bee9d71553667e8acc_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_cedeb74fb6dfb8bee9d71553667e8acc_@@@Z

- ea: `0x1800137e0`
- end: `0x1800138f0`
- name: `??$call@AEAV_lambda_cedeb74fb6dfb8bee9d71553667e8acc_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_cedeb74fb6dfb8bee9d71553667e8acc_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180014dd8`

## callees

- `0x180002471`
- `0x180003444`
- `0x180003580`
- `0x1800065f0`
- `0x1800137e0`
- `0x180013a88`
- `0x180014570`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_cedeb74fb6dfb8bee9d71553667e8acc_ &>(
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
    _lambda_280cd5b56449d64c91a1408b409a836e_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
    _InterlockedDecrement64(&qword_180035928);
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
0x1800137e0  mov     [rsp-18h+arg_8], rbx
0x1800137e5  mov     [rsp-18h+arg_0], rcx
0x1800137ea  push    rbp
0x1800137eb  push    rsi
0x1800137ec  push    rdi
0x1800137ed  mov     rbp, rsp
0x1800137f0  sub     rsp, 60h
0x1800137f4  mov     rsi, r8
0x1800137f7  mov     rbx, rdx
0x1800137fa  lea     rax, aWindowsGraphic_6; "Windows.Graphics.Capture.Server.Captura"...
0x180013801  mov     [rbp+var_38], rax
0x180013805  mov     [rbp+var_30], 2Eh ; '.'
0x18001380d  lea     rdx, [rbp+var_38]
0x180013811  lea     rcx, [rbp+var_28]
0x180013815  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001381a  lea     rdx, [rbp+var_28]
0x18001381e  lea     rcx, [rbp+arg_0]
0x180013822  call    ??$get_activation_factory@UICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@winrt@@YA?AUICapturableItemStatics@Server@Capture@Graphics@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>(winrt::param::hstring const &)
0x180013827  nop
0x180013828  mov     rdi, [rbp+arg_0]
0x18001382c  test    rdi, rdi
0x18001382f  jz      loc_1800138C4
0x180013835  mov     [rbp+arg_18], 0
0x18001383d  mov     rax, [rdi]
0x180013840  lea     r8, [rbp+arg_18]
0x180013844  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001384b  mov     rcx, rdi
0x18001384e  mov     rax, [rax]
0x180013851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013856  mov     rax, [rbp+arg_18]
0x18001385a  mov     [rbp+arg_18], rax
0x18001385e  test    rax, rax
0x180013861  jz      short loc_1800138C4
0x180013863  lea     rcx, [rbp+arg_18]
0x180013867  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001386c  lea     rax, qword_180035928
0x180013873  mov     [rbp+arg_18], rax
0x180013877  lock inc cs:qword_180035928
0x18001387f  xor     eax, eax
0x180013881  lock cmpxchg cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, rdi; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x18001388a  jnz     short loc_1800138A7
0x18001388c  mov     [rbp+arg_0], 0
0x180013894  lea     rdx, ListEntry; ListEntry
0x18001389b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800138a2  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800138a7  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x1800138ae  mov     rdx, rbx
0x1800138b1  mov     rcx, rsi
0x1800138b4  call    ??R_lambda_280cd5b56449d64c91a1408b409a836e_@@QEBA@AEBUICaptureServerAccessStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_280cd5b56449d64c91a1408b409a836e_::operator()(winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics const &)
0x1800138b9  nop
0x1800138ba  lock dec cs:qword_180035928
0x1800138c2  jmp     short loc_1800138D4
0x1800138c4  lea     r8, [rbp+arg_0]
0x1800138c8  mov     rdx, rbx
0x1800138cb  mov     rcx, rsi
0x1800138ce  call    ??R_lambda_280cd5b56449d64c91a1408b409a836e_@@QEBA@AEBUICaptureServerAccessStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_280cd5b56449d64c91a1408b409a836e_::operator()(winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics const &)
0x1800138d3  nop
0x1800138d4  lea     rcx, [rbp+arg_0]
0x1800138d8  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800138dd  mov     rax, rbx
0x1800138e0  mov     rbx, [rsp+60h+arg_8]
0x1800138e8  add     rsp, 60h
0x1800138ec  pop     rdi
0x1800138ed  pop     rsi
0x1800138ee  pop     rbp
0x1800138ef  retn
```
