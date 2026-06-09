# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::TryCreateFromWindowId(winrt::Windows::UI::WindowId)

- ea: `0x180019c8c`
- end: `0x180019d40`
- name: `?TryCreateFromWindowId@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@SA?AUGraphicsCaptureItem@3456@UWindowId@UI@56@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800056d8`

## callees

- `0x180003580`
- `0x180014458`
- `0x1800162f8`
- `0x180017bb0`
- `0x180018340`
- `0x180019c8c`

## pseudocode

```c
void (__fastcall ***__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::TryCreateFromWindowId(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2))(_QWORD, __int64 *, __int64 **)
{
  __int64 v4; // [rsp+48h] [rbp+18h] BYREF
  __int64 *v5; // [rsp+50h] [rbp+20h] BYREF
  __int64 v6; // [rsp+58h] [rbp+28h] BYREF

  v6 = a2;
  v5 = &v6;
  _InterlockedIncrement64(&qword_180035928);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> )
  {
    _lambda_2c8b1cfcca3196ebb6bd591c86b03c56_::operator()(
      &v5,
      &v4,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
    _InterlockedDecrement64(&qword_180035928);
  }
  else
  {
    _InterlockedDecrement64(&qword_180035928);
    winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_2c8b1cfcca3196ebb6bd591c86b03c56_ &>(
      a1,
      (__int64)&v4,
      (__int64)&v5);
  }
  v5 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v4, &v5) )
    *a1 = 0;
  else
    winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem((__int64)a1, (__int64)&v4);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v4);
  return a1;
}

```

## disassembly

```asm
0x180019c8c  mov     [rsp-8+arg_0], rbx
0x180019c91  push    rbp
0x180019c92  mov     rbp, rsp
0x180019c95  sub     rsp, 30h
0x180019c99  mov     rbx, rcx
0x180019c9c  mov     [rbp+arg_18], rdx
0x180019ca0  lea     rax, [rbp+arg_18]
0x180019ca4  mov     [rbp+arg_10], rax
0x180019ca8  lea     rax, qword_180035928
0x180019caf  mov     [rbp+var_8], rax
0x180019cb3  lock inc cs:qword_180035928
0x180019cbb  cmp     cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, 0; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x180019cc3  jz      short loc_180019CE4
0x180019cc5  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x180019ccc  lea     rdx, [rbp+arg_8]
0x180019cd0  lea     rcx, [rbp+arg_10]
0x180019cd4  call    ??R_lambda_2c8b1cfcca3196ebb6bd591c86b03c56_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_2c8b1cfcca3196ebb6bd591c86b03c56_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x180019cd9  nop
0x180019cda  lock dec cs:qword_180035928
0x180019ce2  jmp     short loc_180019CFA
0x180019ce4  lock dec cs:qword_180035928
0x180019cec  lea     r8, [rbp+arg_10]
0x180019cf0  lea     rdx, [rbp+arg_8]
0x180019cf4  call    ??$call@AEAV_lambda_2c8b1cfcca3196ebb6bd591c86b03c56_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_2c8b1cfcca3196ebb6bd591c86b03c56_@@@Z
0x180019cf9  nop
0x180019cfa  mov     [rbp+arg_10], 0
0x180019d02  lea     rdx, [rbp+arg_10]
0x180019d06  lea     rcx, [rbp+arg_8]
0x180019d0a  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180019d0f  test    al, al
0x180019d11  jz      short loc_180019D1C
0x180019d13  mov     qword ptr [rbx], 0
0x180019d1a  jmp     short loc_180019D29
0x180019d1c  lea     rdx, [rbp+arg_8]
0x180019d20  mov     rcx, rbx
0x180019d23  call    ?CreateApiItemFromServerItem@implementation@Capture@Graphics@Windows@winrt@@YA?AUGraphicsCaptureItem@2345@AEBUCapturableItem@Server@2345@@Z; winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem(winrt::Windows::Graphics::Capture::Server::CapturableItem const &)
0x180019d28  nop
0x180019d29  lea     rcx, [rbp+arg_8]
0x180019d2d  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180019d32  mov     rax, rbx
0x180019d35  mov     rbx, [rsp+30h+arg_0]
0x180019d3a  add     rsp, 30h
0x180019d3e  pop     rbp
0x180019d3f  retn
```
