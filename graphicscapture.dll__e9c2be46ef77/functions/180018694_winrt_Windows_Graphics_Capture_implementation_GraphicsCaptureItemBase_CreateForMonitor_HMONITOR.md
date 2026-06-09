# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForMonitor(HMONITOR__ *)

- ea: `0x180018694`
- end: `0x18001878a`
- name: `?CreateForMonitor@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@SA?AUGraphicsCaptureItem@3456@PEAUHMONITOR__@@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018540`

## callees

- `0x180003580`
- `0x1800039fc`
- `0x180014458`
- `0x180016758`
- `0x180017e54`
- `0x180018340`
- `0x180018694`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void (__fastcall ***__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForMonitor(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2))(_QWORD, __int64 *, __int64 **)
{
  char v3; // al
  __int64 v5; // rbx
  unsigned int *v6; // rax
  _QWORD v7[2]; // [rsp+28h] [rbp-70h] BYREF
  const winrt::hresult_error *v8; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v9[24]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v11; // [rsp+78h] [rbp-20h] BYREF
  __int64 v12; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v13; // [rsp+B0h] [rbp+18h] BYREF
  _QWORD *v14; // [rsp+B8h] [rbp+20h] BYREF

  try
  {
    v13 = 0;
    v7[0] = a2;
    v14 = v7;
    v7[1] = &qword_180035928;
    _InterlockedIncrement64(&qword_180035928);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> )
    {
      _lambda_e676731b0f093ccf152ab099f4faa1ec_::operator()(
        &v14,
        &v12,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
      _InterlockedDecrement64(&qword_180035928);
    }
    else
    {
      _InterlockedDecrement64(&qword_180035928);
      winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_e676731b0f093ccf152ab099f4faa1ec_ &>(
        a1,
        (__int64)&v12,
        (__int64)&v14);
    }
    winrt::Windows::Foundation::IUnknown::operator=(&v13, &v12);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v12);
    v12 = 0;
    v3 = winrt::Windows::Foundation::operator==(&v13, &v12);
  }
  catch ( const winrt::hresult_error *v8 )
  {
    if ( *((_DWORD *)v8 + 3) == -2147024891 )
    {
      v5 = winrt::impl::slim_source_location::current(&v11);
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v10,
        L"You do not have permission to capture the given monitor.");
      v6 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v12, -2147024891);
      winrt::hresult_error::hresult_error(v9, *v6, v10, v5);
      throw (winrt::hresult_error *)v9;
    }
    throw;
  }
  if ( v3 )
    *a1 = 0;
  else
    winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem((__int64)a1, (__int64)&v13);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v13);
  return a1;
}

```

## disassembly

```asm
0x180018694  mov     r11, rsp
0x180018697  push    rbx
0x180018698  sub     rsp, 90h
0x18001869f  mov     rbx, rcx
0x1800186a2  mov     qword ptr [r11+18h], 0
0x1800186aa  mov     [r11-70h], rdx
0x1800186ae  lea     rax, [r11-70h]
0x1800186b2  mov     [r11+20h], rax
0x1800186b6  lea     rax, qword_180035928
0x1800186bd  mov     [r11-68h], rax
0x1800186c1  lock inc cs:qword_180035928
0x1800186c9  cmp     cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, 0; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x1800186d1  jz      short loc_1800186F2
0x1800186d3  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x1800186da  lea     rdx, [r11+10h]
0x1800186de  lea     rcx, [r11+20h]
0x1800186e2  call    ??R_lambda_e676731b0f093ccf152ab099f4faa1ec_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_e676731b0f093ccf152ab099f4faa1ec_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x1800186e7  nop
0x1800186e8  lock dec cs:qword_180035928
0x1800186f0  jmp     short loc_18001870F
0x1800186f2  lock dec cs:qword_180035928
0x1800186fa  lea     r8, [rsp+98h+arg_18]
0x180018702  lea     rdx, [rsp+98h+arg_8]
0x18001870a  call    ??$call@AEAV_lambda_e676731b0f093ccf152ab099f4faa1ec_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_e676731b0f093ccf152ab099f4faa1ec_@@@Z
0x18001870f  lea     rdx, [rsp+98h+arg_8]
0x180018717  lea     rcx, [rsp+98h+arg_10]
0x18001871f  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180018724  lea     rcx, [rsp+98h+arg_8]
0x18001872c  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180018731  nop
0x180018732  mov     [rsp+98h+arg_8], 0
0x18001873e  lea     rdx, [rsp+98h+arg_8]
0x180018746  lea     rcx, [rsp+98h+arg_10]
0x18001874e  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180018753  test    al, al
0x180018755  jz      short loc_180018777
0x180018757  mov     qword ptr [rbx], 0
0x18001875e  lea     rcx, [rsp+98h+arg_10]
0x180018766  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001876b  mov     rax, rbx
0x18001876e  add     rsp, 90h
0x180018775  pop     rbx
0x180018776  retn
0x180018777  lea     rdx, [rsp+98h+arg_10]
0x18001877f  mov     rcx, rbx
0x180018782  call    ?CreateApiItemFromServerItem@implementation@Capture@Graphics@Windows@winrt@@YA?AUGraphicsCaptureItem@2345@AEBUCapturableItem@Server@2345@@Z; winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem(winrt::Windows::Graphics::Capture::Server::CapturableItem const &)
0x180018787  jmp     short loc_18001875E
```
