# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::TryCreateFromDisplayId(winrt::Windows::Graphics::DisplayId)

- ea: `0x180019b6c`
- end: `0x180019c20`
- name: `?TryCreateFromDisplayId@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@SA?AUGraphicsCaptureItem@3456@UDisplayId@456@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005640`

## callees

- `0x180003580`
- `0x180014458`
- `0x180016528`
- `0x180017d14`
- `0x180018340`
- `0x180019b6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void (__fastcall ***__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::TryCreateFromDisplayId(
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
    _lambda_84dad07838de48a565098aab66ca8ecd_::operator()(
      &v5,
      &v4,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
    _InterlockedDecrement64(&qword_180035928);
  }
  else
  {
    _InterlockedDecrement64(&qword_180035928);
    winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_84dad07838de48a565098aab66ca8ecd_ &>(
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
0x180019b6c  mov     [rsp-8+arg_0], rbx
0x180019b71  push    rbp
0x180019b72  mov     rbp, rsp
0x180019b75  sub     rsp, 30h
0x180019b79  mov     rbx, rcx
0x180019b7c  mov     [rbp+arg_18], rdx
0x180019b80  lea     rax, [rbp+arg_18]
0x180019b84  mov     [rbp+arg_10], rax
0x180019b88  lea     rax, qword_180035928
0x180019b8f  mov     [rbp+var_8], rax
0x180019b93  lock inc cs:qword_180035928
0x180019b9b  cmp     cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, 0; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x180019ba3  jz      short loc_180019BC4
0x180019ba5  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x180019bac  lea     rdx, [rbp+arg_8]
0x180019bb0  lea     rcx, [rbp+arg_10]
0x180019bb4  call    ??R_lambda_84dad07838de48a565098aab66ca8ecd_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_84dad07838de48a565098aab66ca8ecd_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x180019bb9  nop
0x180019bba  lock dec cs:qword_180035928
0x180019bc2  jmp     short loc_180019BDA
0x180019bc4  lock dec cs:qword_180035928
0x180019bcc  lea     r8, [rbp+arg_10]
0x180019bd0  lea     rdx, [rbp+arg_8]
0x180019bd4  call    ??$call@AEAV_lambda_84dad07838de48a565098aab66ca8ecd_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_84dad07838de48a565098aab66ca8ecd_@@@Z
0x180019bd9  nop
0x180019bda  mov     [rbp+arg_10], 0
0x180019be2  lea     rdx, [rbp+arg_10]
0x180019be6  lea     rcx, [rbp+arg_8]
0x180019bea  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180019bef  test    al, al
0x180019bf1  jz      short loc_180019BFC
0x180019bf3  mov     qword ptr [rbx], 0
0x180019bfa  jmp     short loc_180019C09
0x180019bfc  lea     rdx, [rbp+arg_8]
0x180019c00  mov     rcx, rbx
0x180019c03  call    ?CreateApiItemFromServerItem@implementation@Capture@Graphics@Windows@winrt@@YA?AUGraphicsCaptureItem@2345@AEBUCapturableItem@Server@2345@@Z; winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem(winrt::Windows::Graphics::Capture::Server::CapturableItem const &)
0x180019c08  nop
0x180019c09  lea     rcx, [rbp+arg_8]
0x180019c0d  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180019c12  mov     rax, rbx
0x180019c15  mov     rbx, [rsp+30h+arg_0]
0x180019c1a  add     rsp, 30h
0x180019c1e  pop     rbp
0x180019c1f  retn
```
