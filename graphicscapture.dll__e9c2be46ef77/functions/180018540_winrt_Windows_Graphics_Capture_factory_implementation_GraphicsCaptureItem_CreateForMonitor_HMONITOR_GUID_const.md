# winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem::CreateForMonitor(HMONITOR__ *,_GUID const &,void * *)

- ea: `0x180018540`
- end: `0x18001868b`
- name: `?CreateForMonitor@GraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@UEAAJPEAUHMONITOR__@@AEBU_GUID@@PEAPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem *__hidden this, HMONITOR, const struct _GUID *, void **)`
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
- `0x180018540`
- `0x180018694`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem::CreateForMonitor(
        winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem *this,
        HMONITOR a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall ***v6)(_QWORD, const struct _GUID *, void **); // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  __int64 result; // rax
  __int64 v10; // rbx
  unsigned int *v11; // rax
  int v12; // [rsp+20h] [rbp-78h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, const struct _GUID *, void **); // [rsp+28h] [rbp-70h] BYREF
  __int64 (__fastcall ***v14)(_QWORD, const struct _GUID *, void **); // [rsp+30h] [rbp-68h] BYREF
  int v15; // [rsp+38h] [rbp-60h] BYREF
  __int128 v16; // [rsp+40h] [rbp-58h]
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v18[48]; // [rsp+68h] [rbp-30h] BYREF

  try
  {
    winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForMonitor();
    v13 = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v14, &v13) )
    {
      v10 = winrt::impl::slim_source_location::current(&v15);
      winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"Could not capture the given monitor.");
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
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v12);
  }
  return result;
}

```

## disassembly

```asm
0x180018540  mov     [rsp+arg_0], rbx
0x180018545  push    rdi
0x180018546  sub     rsp, 90h
0x18001854d  mov     rbx, r9
0x180018550  mov     rdi, r8
0x180018553  lea     rcx, [rsp+98h+var_68]
0x180018558  call    ?CreateForMonitor@GraphicsCaptureItemBase@implementation@Capture@Graphics@Windows@winrt@@SA?AUGraphicsCaptureItem@3456@PEAUHMONITOR__@@@Z; winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase::CreateForMonitor(HMONITOR__ *)
0x18001855d  nop
0x18001855e  mov     [rsp+98h+var_70], 0
0x180018567  lea     rdx, [rsp+98h+var_70]
0x18001856c  lea     rcx, [rsp+98h+var_68]
0x180018571  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180018576  test    al, al
0x180018578  jnz     loc_180018637
0x18001857e  mov     rcx, [rsp+98h+var_68]
0x180018583  mov     [rsp+98h+var_70], 0
0x18001858c  test    rcx, rcx
0x18001858f  jz      short loc_1800185D4
0x180018591  mov     [rsp+98h+var_60], 0
0x180018599  xorps   xmm0, xmm0
0x18001859c  movdqu  [rsp+98h+var_58], xmm0
0x1800185a2  mov     rax, [rcx]
0x1800185a5  lea     r8, [rsp+98h+var_70]
0x1800185aa  lea     rdx, ??$guid_v@UIUnknown@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IUnknown>
0x1800185b1  mov     rax, [rax]
0x1800185b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185b9  lea     r8, [rsp+98h+var_60]
0x1800185be  mov     edx, eax
0x1800185c0  lea     rcx, [rsp+98h+var_78]
0x1800185c5  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800185ca  mov     rcx, [rsp+98h+var_70]
0x1800185cf  mov     [rsp+98h+var_70], rcx
0x1800185d4  mov     [rsp+98h+var_60], 0
0x1800185dc  xorps   xmm0, xmm0
0x1800185df  movdqu  [rsp+98h+var_58], xmm0
0x1800185e5  mov     rax, [rcx]
0x1800185e8  mov     r8, rbx
0x1800185eb  mov     rdx, rdi
0x1800185ee  mov     rax, [rax]
0x1800185f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185f6  lea     r8, [rsp+98h+var_60]
0x1800185fb  mov     edx, eax
0x1800185fd  lea     rcx, [rsp+98h+var_78]
0x180018602  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180018607  nop
0x180018608  lea     rcx, [rsp+98h+var_70]
0x18001860d  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180018612  nop
0x180018613  lea     rcx, [rsp+98h+var_68]
0x180018618  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001861d  nop
0x18001861e  xor     eax, eax
0x180018620  jmp     short loc_180018626
0x180018622  mov     eax, [rsp+98h+var_78]
0x180018626  mov     rbx, [rsp+98h+arg_0]
0x18001862e  add     rsp, 90h
0x180018635  pop     rdi
0x180018636  retn
0x180018637  lea     rcx, [rsp+98h+var_60]
0x18001863c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180018641  mov     rbx, rax
0x180018644  lea     rdx, aCouldNotCaptur; "Could not capture the given monitor."
0x18001864b  lea     rcx, [rsp+98h+var_30]; this
0x180018650  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180018655  mov     edx, 80070057h; int
0x18001865a  lea     rcx, [rsp+98h+var_78]; this
0x18001865f  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180018664  mov     r9, rbx
0x180018667  lea     r8, [rsp+98h+var_30]
0x18001866c  mov     edx, [rax]
0x18001866e  lea     rcx, [rsp+98h+pExceptionObject]
0x180018673  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180018678  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18001867f  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180018684  call    _CxxThrowException_0
```
