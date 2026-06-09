# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateFilteredItemForDisplay(unsigned __int64)

- ea: `0x18001845c`
- end: `0x18001852b`
- name: `?CreateFilteredItemForDisplay@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@SA?AUGraphicsCaptureItem@3456@_K@Z`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800041c0`

## callees

- `0x1800022f2`
- `0x180003330`
- `0x1800033c0`
- `0x180003580`
- `0x1800058c4`
- `0x1800161e0`
- `0x180017b48`
- `0x180018340`
- `0x18001845c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void (__fastcall ***__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateFilteredItemForDisplay(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2))(_QWORD, __int64 *, __int64 **)
{
  unsigned int *v4; // rax
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v6[24]; // [rsp+48h] [rbp-18h] BYREF
  __int64 *v7; // [rsp+78h] [rbp+18h] BYREF
  __int64 v8; // [rsp+80h] [rbp+20h] BYREF
  __int64 v9; // [rsp+88h] [rbp+28h] BYREF

  v9 = a2;
  v7 = &v9;
  _InterlockedIncrement64(&qword_180035928);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> )
  {
    _lambda_17b64bf4366613d0648098682da67ee9_::operator()(
      &v7,
      &v8,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>);
    _InterlockedDecrement64(&qword_180035928);
  }
  else
  {
    _InterlockedDecrement64(&qword_180035928);
    winrt::impl::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::call<_lambda_17b64bf4366613d0648098682da67ee9_ &>(
      a1,
      (__int64)&v8,
      (__int64)&v7);
  }
  if ( !v8 )
  {
    winrt::impl::slim_source_location::current(v6);
    v4 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v7, -2147024809);
    winrt::hresult_error::hresult_error(pExceptionObject, *v4);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem((__int64)a1, (__int64)&v8);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v8);
  return a1;
}

```

## disassembly

```asm
0x18001845c  mov     [rsp-8+arg_0], rbx
0x180018461  push    rbp
0x180018462  mov     rbp, rsp
0x180018465  sub     rsp, 60h
0x180018469  mov     rbx, rcx
0x18001846c  mov     [rbp+arg_18], rdx
0x180018470  lea     rax, [rbp+arg_18]
0x180018474  mov     [rbp+arg_8], rax
0x180018478  lea     rax, qword_180035928
0x18001847f  mov     [rbp+var_38], rax
0x180018483  lock inc cs:qword_180035928
0x18001848b  cmp     cs:??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A, 0; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x180018493  jz      short loc_1800184B4
0x180018495  lea     r8, ??$factory_cache_entry_v@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::winrt::factory_cache_entry<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Graphics::Capture::Server::CapturableItem,winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>
0x18001849c  lea     rdx, [rbp+arg_10]
0x1800184a0  lea     rcx, [rbp+arg_8]
0x1800184a4  call    ??R_lambda_17b64bf4366613d0648098682da67ee9_@@QEBA@AEBUICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@Z; _lambda_17b64bf4366613d0648098682da67ee9_::operator()(winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics const &)
0x1800184a9  nop
0x1800184aa  lock dec cs:qword_180035928
0x1800184b2  jmp     short loc_1800184CA
0x1800184b4  lock dec cs:qword_180035928
0x1800184bc  lea     r8, [rbp+arg_8]
0x1800184c0  lea     rdx, [rbp+arg_10]
0x1800184c4  call    ??$call@AEAV_lambda_17b64bf4366613d0648098682da67ee9_@@@?$factory_cache_entry@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@UICapturableItemStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_17b64bf4366613d0648098682da67ee9_@@@Z
0x1800184c9  nop
0x1800184ca  cmp     [rbp+arg_10], 0
0x1800184cf  jz      short loc_1800184F5
0x1800184d1  lea     rdx, [rbp+arg_10]
0x1800184d5  mov     rcx, rbx
0x1800184d8  call    ?CreateApiItemFromServerItem@implementation@Capture@Graphics@Windows@winrt@@YA?AUGraphicsCaptureItem@2345@AEBUCapturableItem@Server@2345@@Z; winrt::Windows::Graphics::Capture::implementation::CreateApiItemFromServerItem(winrt::Windows::Graphics::Capture::Server::CapturableItem const &)
0x1800184dd  nop
0x1800184de  lea     rcx, [rbp+arg_10]
0x1800184e2  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800184e7  mov     rax, rbx
0x1800184ea  mov     rbx, [rsp+60h+arg_0]
0x1800184ef  add     rsp, 60h
0x1800184f3  pop     rbp
0x1800184f4  retn
0x1800184f5  lea     rcx, [rbp+var_18]
0x1800184f9  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800184fe  mov     r8, rax
0x180018501  mov     edx, 80070057h; int
0x180018506  lea     rcx, [rbp+arg_8]; this
0x18001850a  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18001850f  mov     edx, [rax]
0x180018511  lea     rcx, [rbp+pExceptionObject]
0x180018515  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001851a  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180018521  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018525  call    _CxxThrowException_0
```
