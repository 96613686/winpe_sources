# winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem::CreateForWindow(HWND__ *,_GUID const &,void * *)

- ea: `0x180018790`
- end: `0x1800188db`
- name: `?CreateForWindow@GraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
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
- `0x180018790`
- `0x1800188e4`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem::CreateForWindow(
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

  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindow(&v14, a2);
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
0x180018790  mov     [rsp+arg_0], rbx
0x180018795  push    rdi
0x180018796  sub     rsp, 90h
0x18001879d  mov     rbx, r9
0x1800187a0  mov     rdi, r8
0x1800187a3  lea     rcx, [rsp+98h+var_68]
0x1800187a8  call    ?CreateForWindow@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@SA?AUGraphicsCaptureItem@3456@PEAUHWND__@@@Z; winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForWindow(HWND__ *)
0x1800187ad  nop
0x1800187ae  mov     [rsp+98h+var_70], 0
0x1800187b7  lea     rdx, [rsp+98h+var_70]
0x1800187bc  lea     rcx, [rsp+98h+var_68]
0x1800187c1  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800187c6  test    al, al
0x1800187c8  jnz     loc_180018887
0x1800187ce  mov     rcx, [rsp+98h+var_68]
0x1800187d3  mov     [rsp+98h+var_70], 0
0x1800187dc  test    rcx, rcx
0x1800187df  jz      short loc_180018824
0x1800187e1  mov     [rsp+98h+var_60], 0
0x1800187e9  xorps   xmm0, xmm0
0x1800187ec  movdqu  [rsp+98h+var_58], xmm0
0x1800187f2  mov     rax, [rcx]
0x1800187f5  lea     r8, [rsp+98h+var_70]
0x1800187fa  lea     rdx, ??$guid_v@UIUnknown@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IUnknown>
0x180018801  mov     rax, [rax]
0x180018804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018809  lea     r8, [rsp+98h+var_60]
0x18001880e  mov     edx, eax
0x180018810  lea     rcx, [rsp+98h+var_78]
0x180018815  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001881a  mov     rcx, [rsp+98h+var_70]
0x18001881f  mov     [rsp+98h+var_70], rcx
0x180018824  mov     [rsp+98h+var_60], 0
0x18001882c  xorps   xmm0, xmm0
0x18001882f  movdqu  [rsp+98h+var_58], xmm0
0x180018835  mov     rax, [rcx]
0x180018838  mov     r8, rbx
0x18001883b  mov     rdx, rdi
0x18001883e  mov     rax, [rax]
0x180018841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018846  lea     r8, [rsp+98h+var_60]
0x18001884b  mov     edx, eax
0x18001884d  lea     rcx, [rsp+98h+var_78]
0x180018852  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018857  nop
0x180018858  lea     rcx, [rsp+98h+var_70]
0x18001885d  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180018862  nop
0x180018863  lea     rcx, [rsp+98h+var_68]
0x180018868  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001886d  nop
0x18001886e  xor     eax, eax
0x180018870  jmp     short loc_180018876
0x180018872  mov     eax, [rsp+98h+var_78]
0x180018876  mov     rbx, [rsp+98h+arg_0]
0x18001887e  add     rsp, 90h
0x180018885  pop     rdi
0x180018886  retn
0x180018887  lea     rcx, [rsp+98h+var_60]
0x18001888c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180018891  mov     rbx, rax
0x180018894  lea     rdx, aCouldNotCaptur_0; "Could not capture the given window."
0x18001889b  lea     rcx, [rsp+98h+var_30]; this
0x1800188a0  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800188a5  mov     edx, 80070057h; int
0x1800188aa  lea     rcx, [rsp+98h+var_78]; this
0x1800188af  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1800188b4  mov     r9, rbx
0x1800188b7  lea     r8, [rsp+98h+var_30]
0x1800188bc  mov     edx, [rax]
0x1800188be  lea     rcx, [rsp+98h+pExceptionObject]
0x1800188c3  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800188c8  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x1800188cf  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800188d4  call    _CxxThrowException_0
```
