# CLazyModule::DCompositionInfo::UpdateComposition(CDXGISwapChain const *,HWND__ *,IUnknown *)

- ea: `0x180091254`
- end: `0x180091883`
- name: `?UpdateComposition@DCompositionInfo@CLazyModule@@QEAAJPEBVCDXGISwapChain@@PEAUHWND__@@PEAUIUnknown@@@Z`
- size: `1583`
- prototype: `__int64 __fastcall(CLazyModule::DCompositionInfo *__hidden this, const struct CDXGISwapChain *, HWND, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180069a4c`

## callees

- `0x180067d2c`
- `0x18006a460`
- `0x180075fa0`
- `0x1800888dc`
- `0x18008b044`
- `0x18008b10c`
- `0x18008bcf8`
- `0x18008fd90`
- `0x180090904`
- `0x180091254`
- `0x180091a1c`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800912d5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800912d5`

## string_xrefs

- `0x1800912b6`: `Windows.UI.Composition.Core.CompositorController`
- `0x18009132b`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x18009137e`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x1800913d4`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x18009142d`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x180091471`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x1800914d3`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x18009151a`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x180091599`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x180091628`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x180091678`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x1800916d9`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x180091773`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x1800917bc`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x18009181f`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CLazyModule::DCompositionInfo::UpdateComposition(
        CLazyModule::DCompositionInfo *this,
        const struct CDXGISwapChain *a2,
        HWND a3,
        struct IUnknown *a4)
{
  const struct CDXGISwapChain *v6; // rsi
  _QWORD *v8; // r15
  int ActivationFactory; // eax
  int v10; // ebx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, _QWORD *); // rdi
  int v18; // eax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v20; // eax
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rdi
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64, _QWORD *); // rbx
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, char *); // rbx
  char *v29; // r12
  int v30; // eax
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v32)(_QWORD, GUID *, char *); // rbx
  int v33; // eax
  __int64 v34; // rbx
  __int64 (__fastcall *v35)(__int64, _QWORD, char *); // rsi
  _QWORD *v36; // rax
  __int64 (__fastcall ***v37)(_QWORD, GUID *, char *); // rdi
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v39)(_QWORD, GUID *, __int64 *); // rbx
  _QWORD *v40; // rsi
  int v41; // eax
  __int64 (__fastcall *v42)(_QWORD, GUID *, __int64 *); // rbx
  int v43; // eax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, HWND, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, char *)); // rbx
  int v46; // eax
  __int64 (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v48)(_QWORD, GUID *, char *); // rdi
  int v49; // eax
  __int64 (__fastcall ***v50)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v51)(_QWORD, _QWORD); // rbx
  char *v52; // r12
  int v53; // eax
  __int64 (__fastcall ***v54)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v55)(_QWORD, GUID *, struct Windows::UI::Composition::IVisual **); // rbx
  int v56; // eax
  int v57; // eax
  __int64 v58; // rdx
  __int64 v60; // rdx
  int v61; // [rsp+20h] [rbp-69h]
  __int64 v62; // [rsp+30h] [rbp-59h] BYREF
  struct Windows::UI::Composition::IVisual *v63; // [rsp+38h] [rbp-51h] BYREF
  __int64 v64; // [rsp+40h] [rbp-49h] BYREF
  __int64 (__fastcall ***v65)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-41h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, GUID *, char *); // [rsp+50h] [rbp-39h] BYREF
  __int64 (__fastcall ***v67)(_QWORD, GUID *, _QWORD *); // [rsp+58h] [rbp-31h] BYREF
  __int64 v68; // [rsp+60h] [rbp-29h] BYREF
  const struct CDXGISwapChain *v69; // [rsp+68h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-19h] BYREF
  __int64 v71; // [rsp+88h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v6 = a2;
  v69 = a2;
  v8 = (_QWORD *)((char *)this + 40);
  if ( *((_QWORD *)this + 5) )
    goto LABEL_51;
  v65 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v65);
  v71 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.Composition.Core.CompositorController",
    0x31u,
    0x30u);
  ActivationFactory = RoGetActivationFactory(v71, &GUID_00000035_0000_0000_c000_000000000046, &v65);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v11 = (unsigned int)ActivationFactory;
    v12 = 3994;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)v11,
      v61);
    goto LABEL_48;
  }
  if ( !a4 )
  {
    v67 = 0;
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v65;
    v14 = (*v65)[6];
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v67);
    v15 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v14)(v13, &v67);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFA3,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
        (const char *)(unsigned int)v15,
        v61);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v67);
LABEL_48:
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v65);
      return (unsigned int)v10;
    }
    v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v67;
    v17 = **v67;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v8);
    v18 = v17(v16, &GUID_2d75f35a_70a7_4395_ba2d_cef0b18399f9, v8);
    if ( v18 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xFA4,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
        (const char *)(unsigned int)v18,
        v61);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v67);
    goto LABEL_18;
  }
  v64 = 0;
  QueryInterface = a4->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v64);
  v20 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
          a4,
          &GUID_79b9d5f2_879e_4b89_b798_79e47598030c,
          &v64);
  v10 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFAC,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)(unsigned int)v20,
      v61);
LABEL_12:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v64);
    goto LABEL_48;
  }
  v68 = 0;
  v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v65;
  v22 = **v65;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v68);
  v23 = v22(v21, &GUID_1ae27891_516c_4b9e_8018_b5f8d846685e, &v68);
  if ( v23 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xFAF,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)(unsigned int)v23,
      v61);
  v24 = v68;
  v25 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v68 + 48LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v8);
  v26 = v25(v24, v64, v8);
  v10 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB2,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)(unsigned int)v26,
      v61);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v68);
    goto LABEL_12;
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v64);
LABEL_18:
  v27 = *v8;
  v28 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)*v8 + 48LL);
  v29 = (char *)this + 48;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 48);
  v30 = v28(v27, (char *)this + 48);
  if ( v30 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xFB5,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)(unsigned int)v30,
      v61);
  v31 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))v29;
  v32 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))v29;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 56);
  v33 = v32(v31, &GUID_25297d5c_3ad4_4c9c_b5cf_e36a38512330, (char *)this + 56);
  if ( v33 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xFB7,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)(unsigned int)v33,
      v61);
  v34 = *v8;
  v35 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)*v8 + 72LL);
  v36 = (_QWORD *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::UI::Composition::Core::CompositorController___Windows::UI::Composition::Core::ICompositorController____IInspectable___::___Windows::UI::Composition::Core::ICompositorController___IInspectable____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::UI::Composition::Core::CompositorController___IInspectable____Microsoft::WRL::FtmBase___lambda_2fb88d9e1efb7a932300a94effb7b3bb_____1_Windows::UI::Composition::Core::ICompositorController___IInspectable_____lambda_2fb88d9e1efb7a932300a94effb7b3bb____(&v62);
  v37 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v36;
  v66 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v36;
  *v36 = 0;
  if ( v62 )
  {
    v62 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::FtmBase>>::Release();
  }
  v10 = v35(v34, v37, (char *)this + 64);
  if ( v37 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, char *)))(*v37)[2])(v37);
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v12 = 4034;
    goto LABEL_28;
  }
  v38 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v29;
  if ( a3 )
  {
    v62 = 0;
    v42 = **v38;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v62);
    v43 = v42(v38, &GUID_29e691fa_4567_4dca_b319_d0f207eb6807, &v62);
    if ( v43 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xFD3,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
        (const char *)(unsigned int)v43,
        v61);
    v66 = 0;
    v44 = v62;
    v45 = *(__int64 (__fastcall **)(__int64, HWND, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, char *)))(*(_QWORD *)v62 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v66);
    v46 = v45(v44, a3, 0, &v66);
    v10 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFD9,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
        (const char *)(unsigned int)v46,
        v61);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v66);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v62);
      goto LABEL_48;
    }
    v40 = (_QWORD *)((char *)this + 72);
    v47 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
    v48 = **v66;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 72);
    v49 = v48(v47, &GUID_a1bea8ba_d726_4663_8129_6b5e7927ffa6, (char *)this + 72);
    if ( v49 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xFDB,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
        (const char *)(unsigned int)v49,
        v61);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v62);
  }
  else
  {
    v39 = (*v38)[25];
    v40 = (_QWORD *)((char *)this + 72);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 72);
    v41 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), char *))v39)(
            v38,
            (char *)this + 72);
    v10 = v41;
    if ( v41 < 0 )
    {
      v11 = (unsigned int)v41;
      v12 = 4045;
      goto LABEL_28;
    }
  }
  v50 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))v29;
  v51 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v29 + 72LL);
  v52 = (char *)this + 80;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 80);
  v53 = v51(v50, (char *)this + 80);
  v10 = v53;
  if ( v53 < 0 )
  {
    v11 = (unsigned int)v53;
    v12 = 4064;
    goto LABEL_28;
  }
  v63 = 0;
  v54 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))v52;
  v55 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, struct Windows::UI::Composition::IVisual **))v52;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v63);
  v56 = v55(v54, &GUID_117e202d_a859_4c89_873b_c2aa566788e3, &v63);
  if ( v56 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xFE3,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)(unsigned int)v56,
      v61);
  v57 = (*(__int64 (__fastcall **)(_QWORD, struct Windows::UI::Composition::IVisual *))(*(_QWORD *)*v40 + 56LL))(
          *v40,
          v63);
  v10 = v57;
  if ( v57 < 0 )
  {
    v58 = 4068;
LABEL_47:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v58,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)(unsigned int)v57,
      v61);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v63);
    goto LABEL_48;
  }
  v57 = CLazyModule::DCompositionInfo::ConfigureRelativeSize(v63);
  v10 = v57;
  if ( v57 < 0 )
  {
    v58 = 4070;
    goto LABEL_47;
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v65);
  v6 = v69;
LABEL_51:
  v10 = CLazyModule::DCompositionInfo::EnsureSprite(this, *((_DWORD *)v6 + 82) == 5);
  if ( v10 < 0 )
  {
    v60 = 4075;
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v60,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)(unsigned int)v10,
      v61);
    return (unsigned int)v10;
  }
  v10 = CLazyModule::DCompositionInfo::SetSwapChain(this, v6);
  if ( v10 < 0 )
  {
    v60 = 4077;
    goto LABEL_53;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 56LL))(*v8);
  if ( v10 < 0 )
  {
    v60 = 4081;
    goto LABEL_53;
  }
  return 0;
}

```

## disassembly

```asm
0x180091254  push    rbp
0x180091256  push    rbx
0x180091257  push    rsi
0x180091258  push    rdi
0x180091259  push    r12
0x18009125b  push    r13
0x18009125d  push    r14
0x18009125f  push    r15
0x180091261  lea     rbp, [rsp-1Fh]
0x180091266  sub     rsp, 0A8h
0x18009126d  mov     rax, cs:__security_cookie
0x180091274  xor     rax, rsp
0x180091277  mov     [rbp+57h+var_50], rax
0x18009127b  mov     rdi, r9
0x18009127e  mov     r13, r8
0x180091281  mov     rsi, rdx
0x180091284  mov     [rbp+57h+var_78], rdx
0x180091288  mov     r14, rcx
0x18009128b  lea     r15, [rcx+28h]
0x18009128f  xor     r12d, r12d
0x180091292  cmp     [r15], r12
0x180091295  jnz     loc_1800917FB
0x18009129b  mov     [rbp+57h+var_98], r12
0x18009129f  lea     rcx, [rbp+57h+var_98]
0x1800912a3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800912a8  mov     [rbp+57h+var_58], r12
0x1800912ac  lea     r9d, [r12+30h]; unsigned int
0x1800912b1  lea     r8d, [r12+31h]; unsigned int
0x1800912b6  lea     rdx, ?RuntimeClass_Windows_UI_Composition_Core_CompositorController@@3QBGB; "Windows.UI.Composition.Core.CompositorC"...
0x1800912bd  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800912c1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800912c6  lea     r8, [rbp+57h+var_98]
0x1800912ca  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x1800912d1  mov     rcx, [rbp+57h+var_58]
0x1800912d5  call    cs:__imp_RoGetActivationFactory
0x1800912db  mov     ebx, eax
0x1800912dd  test    eax, eax
0x1800912df  jns     short loc_1800912EE
0x1800912e1  mov     r9d, eax
0x1800912e4  mov     edx, 0F9Ah
0x1800912e9  jmp     loc_180091599
0x1800912ee  test    rdi, rdi
0x1800912f1  jnz     loc_18009139E
0x1800912f7  mov     [rbp+57h+var_88], r12
0x1800912fb  mov     rdi, [rbp+57h+var_98]
0x1800912ff  mov     rax, [rdi]
0x180091302  mov     rbx, [rax+30h]
0x180091306  lea     rcx, [rbp+57h+var_88]
0x18009130a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009130f  lea     rdx, [rbp+57h+var_88]
0x180091313  mov     rcx, rdi
0x180091316  mov     rax, rbx
0x180091319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009131e  mov     ebx, eax
0x180091320  test    eax, eax
0x180091322  jns     short loc_18009134B
0x180091324  mov     rcx, [rbp+5Fh]; this
0x180091328  mov     r9d, eax; char *
0x18009132b  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x180091332  mov     edx, 0FA3h; void *
0x180091337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009133c  nop
0x18009133d  lea     rcx, [rbp+57h+var_88]
0x180091341  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180091346  jmp     loc_1800917D7
0x18009134b  mov     rbx, [rbp+57h+var_88]
0x18009134f  mov     rax, [rbx]
0x180091352  mov     rdi, [rax]
0x180091355  mov     rcx, r15
0x180091358  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009135d  mov     r8, r15
0x180091360  lea     rdx, _GUID_2d75f35a_70a7_4395_ba2d_cef0b18399f9
0x180091367  mov     rcx, rbx
0x18009136a  mov     rax, rdi
0x18009136d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091372  nop
0x180091373  mov     rcx, [rbp+5Fh]; this
0x180091377  test    eax, eax
0x180091379  jns     short loc_180091390
0x18009137b  mov     r9d, eax; char *
0x18009137e  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x180091385  mov     edx, 0FA4h; void *
0x18009138a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180091390  lea     rcx, [rbp+57h+var_88]
0x180091394  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180091399  jmp     loc_1800914A4
0x18009139e  mov     [rbp+57h+var_A0], r12
0x1800913a2  mov     rax, [rdi]
0x1800913a5  mov     rbx, [rax]
0x1800913a8  lea     rcx, [rbp+57h+var_A0]
0x1800913ac  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800913b1  lea     r8, [rbp+57h+var_A0]
0x1800913b5  lea     rdx, _GUID_79b9d5f2_879e_4b89_b798_79e47598030c
0x1800913bc  mov     rcx, rdi
0x1800913bf  mov     rax, rbx
0x1800913c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800913c7  mov     ebx, eax
0x1800913c9  test    eax, eax
0x1800913cb  jns     short loc_1800913F4
0x1800913cd  mov     rcx, [rbp+5Fh]; this
0x1800913d1  mov     r9d, eax; char *
0x1800913d4  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x1800913db  mov     edx, 0FACh; void *
0x1800913e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800913e5  nop
0x1800913e6  lea     rcx, [rbp+57h+var_A0]
0x1800913ea  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800913ef  jmp     loc_1800917D7
0x1800913f4  mov     [rbp+57h+var_80], r12
0x1800913f8  mov     rbx, [rbp+57h+var_98]
0x1800913fc  mov     rax, [rbx]
0x1800913ff  mov     rdi, [rax]
0x180091402  lea     rcx, [rbp+57h+var_80]
0x180091406  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009140b  lea     r8, [rbp+57h+var_80]
0x18009140f  lea     rdx, _GUID_1ae27891_516c_4b9e_8018_b5f8d846685e
0x180091416  mov     rcx, rbx
0x180091419  mov     rax, rdi
0x18009141c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091421  nop
0x180091422  mov     rcx, [rbp+5Fh]; this
0x180091426  test    eax, eax
0x180091428  jns     short loc_18009143F
0x18009142a  mov     r9d, eax; char *
0x18009142d  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x180091434  mov     edx, 0FAFh; void *
0x180091439  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18009143f  mov     rdi, [rbp+57h+var_80]
0x180091443  mov     rax, [rdi]
0x180091446  mov     rbx, [rax+30h]
0x18009144a  mov     rcx, r15
0x18009144d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180091452  mov     r8, r15
0x180091455  mov     rdx, [rbp+57h+var_A0]
0x180091459  mov     rcx, rdi
0x18009145c  mov     rax, rbx
0x18009145f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091464  mov     ebx, eax
0x180091466  test    eax, eax
0x180091468  jns     short loc_180091491
0x18009146a  mov     rcx, [rbp+5Fh]; this
0x18009146e  mov     r9d, eax; char *
0x180091471  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x180091478  mov     edx, 0FB2h; void *
0x18009147d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091482  nop
0x180091483  lea     rcx, [rbp+57h+var_80]
0x180091487  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009148c  jmp     loc_1800913E6
0x180091491  lea     rcx, [rbp+57h+var_80]
0x180091495  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009149a  nop
0x18009149b  lea     rcx, [rbp+57h+var_A0]
0x18009149f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800914a4  mov     rdi, [r15]
0x1800914a7  mov     rax, [rdi]
0x1800914aa  mov     rbx, [rax+30h]
0x1800914ae  lea     r12, [r14+30h]
0x1800914b2  mov     rcx, r12
0x1800914b5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800914ba  mov     rdx, r12
0x1800914bd  mov     rcx, rdi
0x1800914c0  mov     rax, rbx
0x1800914c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800914c8  mov     rcx, [rbp+5Fh]; this
0x1800914cc  test    eax, eax
0x1800914ce  jns     short loc_1800914E5
0x1800914d0  mov     r9d, eax; char *
0x1800914d3  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x1800914da  mov     edx, 0FB5h; void *
0x1800914df  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800914e5  mov     rdi, [r12]
0x1800914e9  mov     rax, [rdi]
0x1800914ec  mov     rbx, [rax]
0x1800914ef  lea     rcx, [r14+38h]
0x1800914f3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800914f8  lea     r8, [r14+38h]
0x1800914fc  lea     rdx, _GUID_25297d5c_3ad4_4c9c_b5cf_e36a38512330
0x180091503  mov     rcx, rdi
0x180091506  mov     rax, rbx
0x180091509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009150e  nop
0x18009150f  mov     rcx, [rbp+5Fh]; this
0x180091513  test    eax, eax
0x180091515  jns     short loc_18009152C
0x180091517  mov     r9d, eax; char *
0x18009151a  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x180091521  mov     edx, 0FB7h; void *
0x180091526  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18009152c  mov     rbx, [r15]
0x18009152f  mov     rax, [rbx]
0x180091532  mov     rsi, [rax+48h]
0x180091536  lea     rcx, [rbp+57h+var_B0]
0x18009153a  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__UI__Composition__Core__CompositorController___Windows__UI__Composition__Core__ICompositorController____IInspectable________Windows__UI__Composition__Core__ICompositorController___IInspectable______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__ITypedEventHandler_Windows__UI__Composition__Core__CompositorController___IInspectable____Microsoft__WRL__FtmBase___lambda_2fb88d9e1efb7a932300a94effb7b3bb_____1_Windows__UI__Composition__Core__ICompositorController___IInspectable_____lambda_2fb88d9e1efb7a932300a94effb7b3bb____
0x18009153f  mov     rdi, [rax]
0x180091542  mov     [rbp+57h+var_90], rdi
0x180091546  mov     qword ptr [rax], 0
0x18009154d  mov     rcx, [rbp+57h+var_B0]
0x180091551  test    rcx, rcx
0x180091554  jz      short loc_180091564
0x180091556  mov     [rbp+57h+var_B0], 0
0x18009155e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVCompositorController@Core@Composition@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::FtmBase>>::Release(void)
0x180091563  nop
0x180091564  lea     r8, [r14+40h]
0x180091568  mov     rdx, rdi
0x18009156b  mov     rcx, rbx
0x18009156e  mov     rax, rsi
0x180091571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091576  mov     ebx, eax
0x180091578  test    rdi, rdi
0x18009157b  jz      short loc_18009158D
0x18009157d  mov     rcx, [rdi]
0x180091580  mov     rax, [rcx+10h]
0x180091584  mov     rcx, rdi
0x180091587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009158c  nop
0x18009158d  test    ebx, ebx
0x18009158f  jns     short loc_1800915AE
0x180091591  mov     r9d, ebx; char *
0x180091594  mov     edx, 0FC2h; void *
0x180091599  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x1800915a0  mov     rcx, [rbp+5Fh]; this
0x1800915a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800915a9  jmp     loc_1800917D7
0x1800915ae  mov     rdi, [r12]
0x1800915b2  test    r13, r13
0x1800915b5  jnz     short loc_1800915EF
0x1800915b7  mov     rax, [rdi]
0x1800915ba  mov     rbx, [rax+0C8h]
0x1800915c1  lea     rsi, [r14+48h]
0x1800915c5  mov     rcx, rsi
0x1800915c8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800915cd  mov     rdx, rsi
0x1800915d0  mov     rcx, rdi
0x1800915d3  mov     rax, rbx
0x1800915d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800915db  mov     ebx, eax
0x1800915dd  test    eax, eax
0x1800915df  jns     loc_1800916FE
0x1800915e5  mov     r9d, eax
0x1800915e8  mov     edx, 0FCDh
0x1800915ed  jmp     short loc_180091599
0x1800915ef  mov     [rbp+57h+var_B0], 0
0x1800915f7  mov     rax, [rdi]
0x1800915fa  mov     rbx, [rax]
0x1800915fd  lea     rcx, [rbp+57h+var_B0]
0x180091601  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180091606  lea     r8, [rbp+57h+var_B0]
0x18009160a  lea     rdx, _GUID_29e691fa_4567_4dca_b319_d0f207eb6807
0x180091611  mov     rcx, rdi
0x180091614  mov     rax, rbx
0x180091617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009161c  nop
0x18009161d  mov     rcx, [rbp+5Fh]; this
0x180091621  test    eax, eax
0x180091623  jns     short loc_18009163A
0x180091625  mov     r9d, eax; char *
0x180091628  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x18009162f  mov     edx, 0FD3h; void *
0x180091634  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18009163a  mov     [rbp+57h+var_90], 0
0x180091642  mov     rdi, [rbp+57h+var_B0]
0x180091646  mov     rax, [rdi]
0x180091649  mov     rbx, [rax+18h]
0x18009164d  lea     rcx, [rbp+57h+var_90]
0x180091651  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180091656  lea     r9, [rbp+57h+var_90]
0x18009165a  xor     r8d, r8d
0x18009165d  mov     rdx, r13
0x180091660  mov     rcx, rdi
0x180091663  mov     rax, rbx
0x180091666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009166b  mov     ebx, eax
0x18009166d  test    eax, eax
0x18009166f  jns     short loc_1800916A2
0x180091671  mov     rcx, [rbp+5Fh]; this
0x180091675  mov     r9d, eax; char *
0x180091678  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x18009167f  mov     edx, 0FD9h; void *
0x180091684  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091689  nop
0x18009168a  lea     rcx, [rbp+57h+var_90]
0x18009168e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180091693  nop
0x180091694  lea     rcx, [rbp+57h+var_B0]
0x180091698  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009169d  jmp     loc_1800917D7
0x1800916a2  lea     rsi, [r14+48h]
0x1800916a6  mov     rbx, [rbp+57h+var_90]
0x1800916aa  mov     rax, [rbx]
0x1800916ad  mov     rdi, [rax]
0x1800916b0  mov     rcx, rsi
0x1800916b3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800916b8  mov     r8, rsi
0x1800916bb  lea     rdx, _GUID_a1bea8ba_d726_4663_8129_6b5e7927ffa6
0x1800916c2  mov     rcx, rbx
0x1800916c5  mov     rax, rdi
0x1800916c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800916cd  nop
0x1800916ce  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
