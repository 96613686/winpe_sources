# ??$call@AEAV_lambda_560578b1a229ceef15b3e7ac670cb16b_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_560578b1a229ceef15b3e7ac670cb16b_@@@Z

- ea: `0x180016410`
- end: `0x180016520`
- name: `??$call@AEAV_lambda_560578b1a229ceef15b3e7ac670cb16b_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_560578b1a229ceef15b3e7ac670cb16b_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180018b34`

## callees

- `0x180002471`
- `0x180003444`
- `0x180003580`
- `0x1800065f0`
- `0x180013a88`
- `0x180016410`
- `0x180017bdc`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_560578b1a229ceef15b3e7ac670cb16b_ &>(
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
    _lambda_560578b1a229ceef15b3e7ac670cb16b_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
    _InterlockedDecrement64(&qword_180035928);
  }
  else
  {
    _lambda_560578b1a229ceef15b3e7ac670cb16b_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x180016410  mov     [rsp-18h+arg_8], rbx
0x180016415  mov     [rsp-18h+arg_0], rcx
0x18001641a  push    rbp
0x18001641b  push    rsi
0x18001641c  push    rdi
0x18001641d  mov     rbp, rsp
0x180016420  sub     rsp, 60h
0x180016424  mov     rsi, r8
0x180016427  mov     rbx, rdx
0x18001642a  lea     rax, aWindowsGraphic_6; "Windows.Graphics.Capture.Server.Captura"...
0x180016431  mov     [rbp+var_38], rax
0x180016435  mov     [rbp+var_30], 2Eh ; '.'
0x18001643d  lea     rdx, [rbp+var_38]
0x180016441  lea     rcx, [rbp+var_28]
0x180016445  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001644a  lea     rdx, [rbp+var_28]
0x18001644e  lea     rcx, [rbp+arg_0]
0x180016452  call    ??$get_activation_factory@UICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@winrt@@YA?AUICapturableItemStatics@Server@Capture@Graphics@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>(winrt::param::hstring const &)
0x180016457  nop
0x180016458  mov     rdi, [rbp+arg_0]
0x18001645c  test    rdi, rdi
0x18001645f  jz      loc_1800164F4
0x180016465  mov     [rbp+arg_18], 0
0x18001646d  mov     rax, [rdi]
0x180016470  lea     r8, [rbp+arg_18]
0x180016474  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001647b  mov     rcx, rdi
0x18001647e  mov     rax, [rax]
0x180016481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016486  mov     rax, [rbp+arg_18]
0x18001648a  mov     [rbp+arg_18], rax
0x18001648e  test    rax, rax
0x180016491  jz      short loc_1800164F4
0x180016493  lea     rcx, [rbp+arg_18]
0x180016497  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001649c  lea     rax, qword_180035928
0x1800164a3  mov     [rbp+arg_18], rax
0x1800164a7  lock inc cs:qword_180035928
0x1800164af  xor     eax, eax
0x1800164b1  lock cmpxchg cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, rdi; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x1800164ba  jnz     short loc_1800164D7
0x1800164bc  mov     [rbp+arg_0], 0
0x1800164c4  lea     rdx, ListEntry; ListEntry
0x1800164cb  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800164d2  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800164d7  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x1800164de  mov     rdx, rbx
0x1800164e1  mov     rcx, rsi
0x1800164e4  call    ??R_lambda_560578b1a229ceef15b3e7ac670cb16b_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_560578b1a229ceef15b3e7ac670cb16b_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x1800164e9  nop
0x1800164ea  lock dec cs:qword_180035928
0x1800164f2  jmp     short loc_180016504
0x1800164f4  lea     r8, [rbp+arg_0]
0x1800164f8  mov     rdx, rbx
0x1800164fb  mov     rcx, rsi
0x1800164fe  call    ??R_lambda_560578b1a229ceef15b3e7ac670cb16b_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_560578b1a229ceef15b3e7ac670cb16b_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x180016503  nop
0x180016504  lea     rcx, [rbp+arg_0]
0x180016508  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001650d  mov     rax, rbx
0x180016510  mov     rbx, [rsp+60h+arg_8]
0x180016518  add     rsp, 60h
0x18001651c  pop     rdi
0x18001651d  pop     rsi
0x18001651e  pop     rbp
0x18001651f  retn
```
