# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindow(HWND__ *)

- ea: `0x1800188e4`
- end: `0x1800189d7`
- name: `?CreateForWindow@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@SA?AUGraphicsCaptureItem@3456@PEAUHWND__@@@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018790`

## callees

- `0x180003580`
- `0x1800039fc`
- `0x180014458`
- `0x180016640`
- `0x180017e2c`
- `0x180018340`
- `0x1800188e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void (__fastcall ***__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindow(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        int a2))(_QWORD, __int64 *, __int64 **)
{
  char v3; // al
  __int64 v5; // rbx
  unsigned int *v6; // rax
  _QWORD v7[3]; // [rsp+20h] [rbp-78h] BYREF
  const winrt::hresult_error *v8; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v9[24]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v11; // [rsp+78h] [rbp-20h] BYREF
  int v12; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v13; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v14; // [rsp+B8h] [rbp+20h] BYREF

  try
  {
    v12 = a2;
    v14 = 0;
    v7[0] = &v12;
    v7[2] = &qword_180035928;
    _InterlockedIncrement64(&qword_180035928);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> )
    {
      _lambda_d0179cff9610e4ad7e322c27574ff8c4_::operator()(
        v7,
        &v13,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
      _InterlockedDecrement64(&qword_180035928);
    }
    else
    {
      _InterlockedDecrement64(&qword_180035928);
      winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_d0179cff9610e4ad7e322c27574ff8c4_ &>(
        a1,
        (__int64)&v13,
        (__int64)v7);
    }
    winrt::Windows::Foundation::IUnknown::operator=(&v14, &v13);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v13);
    v13 = 0;
    v3 = winrt::Windows::Foundation::operator==(&v14, &v13);
  }
  catch ( const winrt::hresult_error *v8 )
  {
    if ( *((_DWORD *)v8 + 3) == -2147024891 )
    {
      v5 = winrt::impl::slim_source_location::current(&v11);
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v10,
        L"You do not have permission to capture the given window.");
      v6 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v13, -2147024891);
      winrt::hresult_error::hresult_error(v9, *v6, v10, v5);
      throw (winrt::hresult_error *)v9;
    }
    throw;
  }
  if ( v3 )
    *a1 = 0;
  else
    winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem((__int64)a1, (__int64)&v14);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v14);
  return a1;
}

```

## disassembly

```asm
0x1800188e4  mov     r11, rsp
0x1800188e7  push    rbx
0x1800188e8  sub     rsp, 90h
0x1800188ef  mov     rbx, rcx
0x1800188f2  mov     [r11+10h], edx
0x1800188f6  mov     qword ptr [r11+20h], 0
0x1800188fe  lea     rax, [r11+10h]
0x180018902  mov     [r11-78h], rax
0x180018906  lea     rax, qword_180035928
0x18001890d  mov     [r11-68h], rax
0x180018911  lock inc cs:qword_180035928
0x180018919  cmp     cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, 0; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x180018921  jz      short loc_180018942
0x180018923  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x18001892a  lea     rdx, [r11+18h]
0x18001892e  lea     rcx, [r11-78h]
0x180018932  call    ??R_lambda_d0179cff9610e4ad7e322c27574ff8c4_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_d0179cff9610e4ad7e322c27574ff8c4_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x180018937  nop
0x180018938  lock dec cs:qword_180035928
0x180018940  jmp     short loc_18001895C
0x180018942  lock dec cs:qword_180035928
0x18001894a  lea     r8, [rsp+98h+var_78]
0x18001894f  lea     rdx, [rsp+98h+arg_10]
0x180018957  call    ??$call@AEAV_lambda_d0179cff9610e4ad7e322c27574ff8c4_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_d0179cff9610e4ad7e322c27574ff8c4_@@@Z
0x18001895c  lea     rdx, [rsp+98h+arg_10]
0x180018964  lea     rcx, [rsp+98h+arg_18]
0x18001896c  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180018971  lea     rcx, [rsp+98h+arg_10]
0x180018979  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001897e  nop
0x18001897f  mov     [rsp+98h+arg_10], 0
0x18001898b  lea     rdx, [rsp+98h+arg_10]
0x180018993  lea     rcx, [rsp+98h+arg_18]
0x18001899b  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800189a0  test    al, al
0x1800189a2  jz      short loc_1800189C4
0x1800189a4  mov     qword ptr [rbx], 0
0x1800189ab  lea     rcx, [rsp+98h+arg_18]
0x1800189b3  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800189b8  mov     rax, rbx
0x1800189bb  add     rsp, 90h
0x1800189c2  pop     rbx
0x1800189c3  retn
0x1800189c4  lea     rdx, [rsp+98h+arg_18]
0x1800189cc  mov     rcx, rbx
0x1800189cf  call    ?CreateApiItemFromServerItem@implementation@Capture@Graphics@Windows@winrt@@YA?AUGraphicsCaptureItem@2345@AEBUCapturableItem@Server@2345@@Z; winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem(winrt::Windows::Graphics::Capture::Server::CapturableItem const &)
0x1800189d4  jmp     short loc_1800189AB
```
