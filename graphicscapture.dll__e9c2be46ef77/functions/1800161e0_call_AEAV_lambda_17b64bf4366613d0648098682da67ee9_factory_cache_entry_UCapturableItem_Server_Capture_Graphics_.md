# ??$call@AEAV_lambda_17b64bf4366613d0648098682da67ee9_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_17b64bf4366613d0648098682da67ee9_@@@Z

- ea: `0x1800161e0`
- end: `0x1800162f0`
- name: `??$call@AEAV_lambda_17b64bf4366613d0648098682da67ee9_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_17b64bf4366613d0648098682da67ee9_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001845c`

## callees

- `0x180002471`
- `0x180003444`
- `0x180003580`
- `0x1800065f0`
- `0x180013a88`
- `0x1800161e0`
- `0x180017b48`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_17b64bf4366613d0648098682da67ee9_ &>(
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
    _lambda_17b64bf4366613d0648098682da67ee9_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
    _InterlockedDecrement64(&qword_180035928);
  }
  else
  {
    _lambda_17b64bf4366613d0648098682da67ee9_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x1800161e0  mov     [rsp-18h+arg_8], rbx
0x1800161e5  mov     [rsp-18h+arg_0], rcx
0x1800161ea  push    rbp
0x1800161eb  push    rsi
0x1800161ec  push    rdi
0x1800161ed  mov     rbp, rsp
0x1800161f0  sub     rsp, 60h
0x1800161f4  mov     rsi, r8
0x1800161f7  mov     rbx, rdx
0x1800161fa  lea     rax, aWindowsGraphic_6; "Windows.Graphics.Capture.Server.Captura"...
0x180016201  mov     [rbp+var_38], rax
0x180016205  mov     [rbp+var_30], 2Eh ; '.'
0x18001620d  lea     rdx, [rbp+var_38]
0x180016211  lea     rcx, [rbp+var_28]
0x180016215  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001621a  lea     rdx, [rbp+var_28]
0x18001621e  lea     rcx, [rbp+arg_0]
0x180016222  call    ??$get_activation_factory@UICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@winrt@@YA?AUICapturableItemStatics@Server@Capture@Graphics@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>(winrt::param::hstring const &)
0x180016227  nop
0x180016228  mov     rdi, [rbp+arg_0]
0x18001622c  test    rdi, rdi
0x18001622f  jz      loc_1800162C4
0x180016235  mov     [rbp+arg_18], 0
0x18001623d  mov     rax, [rdi]
0x180016240  lea     r8, [rbp+arg_18]
0x180016244  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001624b  mov     rcx, rdi
0x18001624e  mov     rax, [rax]
0x180016251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016256  mov     rax, [rbp+arg_18]
0x18001625a  mov     [rbp+arg_18], rax
0x18001625e  test    rax, rax
0x180016261  jz      short loc_1800162C4
0x180016263  lea     rcx, [rbp+arg_18]
0x180016267  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001626c  lea     rax, qword_180035928
0x180016273  mov     [rbp+arg_18], rax
0x180016277  lock inc cs:qword_180035928
0x18001627f  xor     eax, eax
0x180016281  lock cmpxchg cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, rdi; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x18001628a  jnz     short loc_1800162A7
0x18001628c  mov     [rbp+arg_0], 0
0x180016294  lea     rdx, ListEntry; ListEntry
0x18001629b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800162a2  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800162a7  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x1800162ae  mov     rdx, rbx
0x1800162b1  mov     rcx, rsi
0x1800162b4  call    ??R_lambda_17b64bf4366613d0648098682da67ee9_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_17b64bf4366613d0648098682da67ee9_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x1800162b9  nop
0x1800162ba  lock dec cs:qword_180035928
0x1800162c2  jmp     short loc_1800162D4
0x1800162c4  lea     r8, [rbp+arg_0]
0x1800162c8  mov     rdx, rbx
0x1800162cb  mov     rcx, rsi
0x1800162ce  call    ??R_lambda_17b64bf4366613d0648098682da67ee9_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_17b64bf4366613d0648098682da67ee9_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x1800162d3  nop
0x1800162d4  lea     rcx, [rbp+arg_0]
0x1800162d8  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800162dd  mov     rax, rbx
0x1800162e0  mov     rbx, [rsp+60h+arg_8]
0x1800162e8  add     rsp, 60h
0x1800162ec  pop     rdi
0x1800162ed  pop     rsi
0x1800162ee  pop     rbp
0x1800162ef  retn
```
