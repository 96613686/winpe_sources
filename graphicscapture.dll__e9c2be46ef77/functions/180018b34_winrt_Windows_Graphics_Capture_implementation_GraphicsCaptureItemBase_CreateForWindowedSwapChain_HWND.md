# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindowedSwapChain(HWND__ *)

- ea: `0x180018b34`
- end: `0x180018c27`
- name: `?CreateForWindowedSwapChain@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@SA?AUGraphicsCaptureItem@3456@PEAUHWND__@@@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800189e0`

## callees

- `0x180003580`
- `0x1800039fc`
- `0x180014458`
- `0x180016410`
- `0x180017bdc`
- `0x180018340`
- `0x180018b34`

## pseudocode

```c
void (__fastcall ***__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindowedSwapChain(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        int a2))(_QWORD, __int64 *, __int64 **)
{
  _QWORD v4[15]; // [rsp+20h] [rbp-78h] BYREF
  int v5; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v6; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v7; // [rsp+B8h] [rbp+20h] BYREF

  v5 = a2;
  v7 = 0;
  v4[0] = &v5;
  v4[2] = &qword_180035928;
  _InterlockedIncrement64(&qword_180035928);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> )
  {
    _lambda_560578b1a229ceef15b3e7ac670cb16b_::operator()(
      v4,
      &v6,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
    _InterlockedDecrement64(&qword_180035928);
  }
  else
  {
    _InterlockedDecrement64(&qword_180035928);
    winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_560578b1a229ceef15b3e7ac670cb16b_ &>(
      a1,
      (__int64)&v6,
      (__int64)v4);
  }
  winrt::Windows::Foundation::IUnknown::operator=(&v7, &v6);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v6);
  v6 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v7, &v6) )
    *a1 = 0;
  else
    winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem((__int64)a1, (__int64)&v7);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v7);
  return a1;
}

```

## disassembly

```asm
0x180018b34  mov     r11, rsp
0x180018b37  push    rbx
0x180018b38  sub     rsp, 90h
0x180018b3f  mov     rbx, rcx
0x180018b42  mov     [r11+10h], edx
0x180018b46  mov     qword ptr [r11+20h], 0
0x180018b4e  lea     rax, [r11+10h]
0x180018b52  mov     [r11-78h], rax
0x180018b56  lea     rax, qword_180035928
0x180018b5d  mov     [r11-68h], rax
0x180018b61  lock inc cs:qword_180035928
0x180018b69  cmp     cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, 0; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x180018b71  jz      short loc_180018B92
0x180018b73  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x180018b7a  lea     rdx, [r11+18h]
0x180018b7e  lea     rcx, [r11-78h]
0x180018b82  call    ??R_lambda_560578b1a229ceef15b3e7ac670cb16b_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_560578b1a229ceef15b3e7ac670cb16b_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x180018b87  nop
0x180018b88  lock dec cs:qword_180035928
0x180018b90  jmp     short loc_180018BAC
0x180018b92  lock dec cs:qword_180035928
0x180018b9a  lea     r8, [rsp+98h+var_78]
0x180018b9f  lea     rdx, [rsp+98h+arg_10]
0x180018ba7  call    ??$call@AEAV_lambda_560578b1a229ceef15b3e7ac670cb16b_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_560578b1a229ceef15b3e7ac670cb16b_@@@Z
0x180018bac  lea     rdx, [rsp+98h+arg_10]
0x180018bb4  lea     rcx, [rsp+98h+arg_18]
0x180018bbc  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180018bc1  lea     rcx, [rsp+98h+arg_10]
0x180018bc9  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180018bce  nop
0x180018bcf  mov     [rsp+98h+arg_10], 0
0x180018bdb  lea     rdx, [rsp+98h+arg_10]
0x180018be3  lea     rcx, [rsp+98h+arg_18]
0x180018beb  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180018bf0  test    al, al
0x180018bf2  jz      short loc_180018C14
0x180018bf4  mov     qword ptr [rbx], 0
0x180018bfb  lea     rcx, [rsp+98h+arg_18]
0x180018c03  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180018c08  mov     rax, rbx
0x180018c0b  add     rsp, 90h
0x180018c12  pop     rbx
0x180018c13  retn
0x180018c14  lea     rdx, [rsp+98h+arg_18]
0x180018c1c  mov     rcx, rbx
0x180018c1f  call    ?CreateApiItemFromServerItem@implementation@Capture@Graphics@Windows@winrt@@YA?AUGraphicsCaptureItem@2345@AEBUCapturableItem@Server@2345@@Z; winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem(winrt::Windows::Graphics::Capture::Server::CapturableItem const &)
0x180018c24  jmp     short loc_180018BFB
```
