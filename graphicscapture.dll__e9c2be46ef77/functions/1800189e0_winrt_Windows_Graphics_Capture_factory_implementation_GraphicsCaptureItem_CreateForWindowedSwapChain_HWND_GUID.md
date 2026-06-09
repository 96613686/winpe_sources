# winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem::CreateForWindowedSwapChain(HWND__ *,_GUID const &,void * *)

- ea: `0x1800189e0`
- end: `0x180018b2b`
- name: `?CreateForWindowedSwapChain@GraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800022f2`
- `0x180003330`
- `0x180003384`
- `0x180003580`
- `0x1800058c4`
- `0x180006610`
- `0x18000eafc`
- `0x1800125ec`
- `0x180014458`
- `0x1800189e0`
- `0x180018b34`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem::CreateForWindowedSwapChain(
        winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem *this,
        HWND a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall ***v6)(_QWORD, const struct _GUID *, void **); // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  __int64 v10; // rbx
  unsigned int *v11; // rax
  int v12; // [rsp+20h] [rbp-78h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, const struct _GUID *, void **); // [rsp+28h] [rbp-70h] BYREF
  __int64 (__fastcall ***v14)(_QWORD, const struct _GUID *, void **); // [rsp+30h] [rbp-68h] BYREF
  int v15; // [rsp+38h] [rbp-60h] BYREF
  __int128 v16; // [rsp+40h] [rbp-58h]
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v18[48]; // [rsp+68h] [rbp-30h] BYREF

  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindowedSwapChain(&v14, a2);
  v13 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v14, &v13) )
  {
    v10 = winrt::impl::slim_source_location::current(&v15);
    winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"Could not capture the given window.");
    v11 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v12, -2147024809);
    winrt::hresult_error::hresult_error(pExceptionObject, *v11, v18, v10);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  v6 = v14;
  v13 = 0;
  if ( v14 )
  {
    v15 = 0;
    v16 = 0;
    v7 = (**v14)(v14, (const struct _GUID *)&winrt::impl::guid_v<IUnknown>, (void **)&v13);
    winrt::check_hresult(&v12, v7, &v15);
    v6 = v13;
  }
  v15 = 0;
  v16 = 0;
  v8 = (**v6)(v6, a3, a4);
  winrt::check_hresult(&v12, v8, &v15);
  winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref((__int64 *)&v13);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v14);
  return 0;
}

```

## disassembly

```asm
0x1800189e0  mov     [rsp+arg_0], rbx
0x1800189e5  push    rdi
0x1800189e6  sub     rsp, 90h
0x1800189ed  mov     rbx, r9
0x1800189f0  mov     rdi, r8
0x1800189f3  lea     rcx, [rsp+98h+var_68]
0x1800189f8  call    ?CreateForWindowedSwapChain@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@SA?AUGraphicsCaptureItem@3456@PEAUHWND__@@@Z; winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindowedSwapChain(HWND__ *)
0x1800189fd  nop
0x1800189fe  mov     [rsp+98h+var_70], 0
0x180018a07  lea     rdx, [rsp+98h+var_70]
0x180018a0c  lea     rcx, [rsp+98h+var_68]
0x180018a11  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180018a16  test    al, al
0x180018a18  jnz     loc_180018AD7
0x180018a1e  mov     rcx, [rsp+98h+var_68]
0x180018a23  mov     [rsp+98h+var_70], 0
0x180018a2c  test    rcx, rcx
0x180018a2f  jz      short loc_180018A74
0x180018a31  mov     [rsp+98h+var_60], 0
0x180018a39  xorps   xmm0, xmm0
0x180018a3c  movdqu  [rsp+98h+var_58], xmm0
0x180018a42  mov     rax, [rcx]
0x180018a45  lea     r8, [rsp+98h+var_70]
0x180018a4a  lea     rdx, ??$guid_v@UIUnknown@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IUnknown>
0x180018a51  mov     rax, [rax]
0x180018a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a59  lea     r8, [rsp+98h+var_60]
0x180018a5e  mov     edx, eax
0x180018a60  lea     rcx, [rsp+98h+var_78]
0x180018a65  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018a6a  mov     rcx, [rsp+98h+var_70]
0x180018a6f  mov     [rsp+98h+var_70], rcx
0x180018a74  mov     [rsp+98h+var_60], 0
0x180018a7c  xorps   xmm0, xmm0
0x180018a7f  movdqu  [rsp+98h+var_58], xmm0
0x180018a85  mov     rax, [rcx]
0x180018a88  mov     r8, rbx
0x180018a8b  mov     rdx, rdi
0x180018a8e  mov     rax, [rax]
0x180018a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a96  lea     r8, [rsp+98h+var_60]
0x180018a9b  mov     edx, eax
0x180018a9d  lea     rcx, [rsp+98h+var_78]
0x180018aa2  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018aa7  nop
0x180018aa8  lea     rcx, [rsp+98h+var_70]
0x180018aad  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180018ab2  nop
0x180018ab3  lea     rcx, [rsp+98h+var_68]
0x180018ab8  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180018abd  nop
0x180018abe  xor     eax, eax
0x180018ac0  jmp     short loc_180018AC6
0x180018ac2  mov     eax, [rsp+98h+var_78]
0x180018ac6  mov     rbx, [rsp+98h+arg_0]
0x180018ace  add     rsp, 90h
0x180018ad5  pop     rdi
0x180018ad6  retn
0x180018ad7  lea     rcx, [rsp+98h+var_60]
0x180018adc  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180018ae1  mov     rbx, rax
0x180018ae4  lea     rdx, aCouldNotCaptur_0; "Could not capture the given window."
0x180018aeb  lea     rcx, [rsp+98h+var_30]; this
0x180018af0  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180018af5  mov     edx, 80070057h; int
0x180018afa  lea     rcx, [rsp+98h+var_78]; this
0x180018aff  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180018b04  mov     r9, rbx
0x180018b07  lea     r8, [rsp+98h+var_30]
0x180018b0c  mov     edx, [rax]
0x180018b0e  lea     rcx, [rsp+98h+pExceptionObject]
0x180018b13  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180018b18  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180018b1f  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180018b24  call    _CxxThrowException_0
```
