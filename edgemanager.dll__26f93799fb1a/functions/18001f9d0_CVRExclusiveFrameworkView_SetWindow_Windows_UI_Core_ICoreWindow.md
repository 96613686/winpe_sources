# CVRExclusiveFrameworkView::SetWindow(Windows::UI::Core::ICoreWindow *)

- ea: `0x18001f9d0`
- end: `0x18001fdd6`
- name: `?SetWindow@CVRExclusiveFrameworkView@@UEAAJPEAUICoreWindow@Core@UI@Windows@@@Z`
- size: `1030`
- prototype: `int(CVRExclusiveFrameworkView *__hidden this, struct Windows::UI::Core::ICoreWindow *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800069a0`
- `0x180007ee0`
- `0x18000b0ec`
- `0x1800127c0`
- `0x18001f9d0`
- `0x1800204b4`
- `0x1800204f0`
- `0x180026988`
- `0x18002b530`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18001fac5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18001fac5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001fb0c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001fb0c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001fb81`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001fb81`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001fbbf`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001fbbf`

## pseudocode

```c
__int64 __fastcall CVRExclusiveFrameworkView::SetWindow(LPSTREAM *this, struct Windows::UI::Core::ICoreWindow *a2)
{
  __int64 (__fastcall *v4)(struct Windows::UI::Core::ICoreWindow *, LPSTREAM *); // rdi
  int v5; // eax
  __int64 (__fastcall **v6)(struct Windows::UI::Core::ICoreWindow *, GUID *, __int64 *); // rax
  int v7; // eax
  int v8; // eax
  __int64 v9; // rbx
  int ActivationFactory; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, struct Windows::UI::Core::ICoreWindow *, __int64 *); // rbx
  int v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  LPSTREAM v16; // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  __int64 (__fastcall **v22)(struct Windows::UI::Core::ICoreWindow *, GUID *, __int64 *); // rax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  int pvDestContext; // [rsp+20h] [rbp-49h]
  int pvDestContexta; // [rsp+20h] [rbp-49h]
  __int64 v30; // [rsp+30h] [rbp-39h] BYREF
  __int64 v31; // [rsp+38h] [rbp-31h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-29h] BYREF
  __int64 v33; // [rsp+48h] [rbp-21h] BYREF
  __int64 v34; // [rsp+50h] [rbp-19h] BYREF
  LPSTREAM v35; // [rsp+58h] [rbp-11h] BYREF
  __int64 v36; // [rsp+60h] [rbp-9h] BYREF
  __int64 v37; // [rsp+68h] [rbp-1h] BYREF
  HWND hWnd; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v40; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v4 = *(__int64 (__fastcall **)(struct Windows::UI::Core::ICoreWindow *, LPSTREAM *))(*(_QWORD *)a2 + 72LL);
  Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreDispatcher>::InternalRelease(this + 10);
  v5 = v4(a2, this + 10);
  if ( v5 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v5,
      pvDestContext);
  CVRExclusiveFrameworkView::AddWindowEvents((CVRExclusiveFrameworkView *)this, a2);
  v6 = *(__int64 (__fastcall ***)(struct Windows::UI::Core::ICoreWindow *, GUID *, __int64 *))a2;
  v34 = 0;
  v7 = (*v6)(a2, &GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f, &v34);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v7,
      pvDestContext);
  hWnd = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v34 + 24LL))(v34, &hWnd);
  if ( v8 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v8,
      pvDestContext);
  SetPropW(hWnd, L"{E40C9088-C521-424B-AA4B-6520171CD690}", HANDLE_FLAG_INHERIT);
  v37 = 0;
  v33 = 0;
  v40 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Graphics.Holographic.HolographicSpace",
    0x2Eu,
    0x2Du);
  v9 = v40;
  Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(&v33);
  ActivationFactory = RoGetActivationFactory(v9, &GUID_364e6064_c8f2_3ba1_8391_66b8489e67fd, &v33);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)ActivationFactory,
      pvDestContext);
  v11 = v33;
  v12 = *(__int64 (__fastcall **)(__int64, struct Windows::UI::Core::ICoreWindow *, __int64 *))(*(_QWORD *)v33 + 48LL);
  Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(&v37);
  v13 = v12(v11, a2, &v37);
  if ( v13 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v13,
      pvDestContext);
  ppstm = 0;
  v14 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v14 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v14,
      pvDestContext);
  v15 = CoMarshalInterface(ppstm, &GUID_79b9d5f2_879e_4b89_b798_79e47598030c, (LPUNKNOWN)a2, 0, 0, 0);
  if ( v15 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v15,
      pvDestContexta);
  v16 = ppstm;
  if ( this[9] != ppstm )
  {
    v35 = ppstm;
    Microsoft::WRL::ComPtr<IVRExclusiveViewCallbacks>::InternalAddRef(&v35);
    v35 = this[9];
    this[9] = v16;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  }
  v36 = 0;
  v40 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.ViewManagement.ApplicationView",
    0x2Au,
    0x29u);
  v17 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::ViewManagement::IApplicationViewStatics2>>(
          v40,
          &v36);
  if ( v17 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v17,
      pvDestContexta);
  v18 = v36;
  v31 = 0;
  v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 48LL);
  Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(&v31);
  v20 = v19(v18, &v31);
  if ( v20 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v20,
      pvDestContexta);
  v21 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v31 + 120LL))(v31, (char *)this + 392);
  if ( v21 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v21,
      pvDestContexta);
  v22 = *(__int64 (__fastcall ***)(struct Windows::UI::Core::ICoreWindow *, GUID *, __int64 *))a2;
  v30 = 0;
  v23 = (*v22)(a2, &GUID_0576ab31_a310_4c40_ba31_fd37e0298dfa, &v30);
  if ( v23 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v23,
      pvDestContexta);
  v24 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v30 + 32LL))(v30, (char *)this + 396);
  if ( v24 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\inetcore\\lib\\edge\\webvr\\viewcore\\vrexclusiveframeworkview.cpp",
      (const char *)(unsigned int)v24,
      pvDestContexta);
  (*(void (__fastcall **)(struct Windows::UI::Core::ICoreWindow *))(*(_QWORD *)a2 + 144LL))(a2);
  v25 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
  Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(&v37);
  v26 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return 0;
}

```

## disassembly

```asm
0x18001f9d0  mov     [rsp-8+arg_10], rbx
0x18001f9d5  push    rbp
0x18001f9d6  push    rsi
0x18001f9d7  push    rdi
0x18001f9d8  push    r14
0x18001f9da  push    r15
0x18001f9dc  lea     rbp, [rsp-37h]
0x18001f9e1  sub     rsp, 0A0h
0x18001f9e8  mov     rax, cs:__security_cookie
0x18001f9ef  xor     rax, rsp
0x18001f9f2  mov     [rbp+57h+var_28], rax
0x18001f9f6  mov     rax, [rdx]
0x18001f9f9  mov     r14, rcx
0x18001f9fc  add     rcx, 50h ; 'P'
0x18001fa00  mov     rsi, rdx
0x18001fa03  mov     rdi, [rax+48h]
0x18001fa07  call    ?InternalRelease@?$ComPtr@UICoreDispatcher@Core@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreDispatcher>::InternalRelease(void)
0x18001fa0c  lea     rdx, [r14+50h]
0x18001fa10  mov     rcx, rsi
0x18001fa13  mov     rax, rdi
0x18001fa16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa1b  xor     r15d, r15d
0x18001fa1e  test    eax, eax
0x18001fa20  jns     short loc_18001FA3A
0x18001fa22  mov     rcx, [rbp+5Fh]; this
0x18001fa26  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fa2d  mov     r9d, eax; char *
0x18001fa30  lea     edx, [r15+49h]; void *
0x18001fa34  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fa3a  mov     rdx, rsi; struct Windows::UI::Core::ICoreWindow *
0x18001fa3d  mov     rcx, r14; this
0x18001fa40  call    ?AddWindowEvents@CVRExclusiveFrameworkView@@AEAAXPEAUICoreWindow@Core@UI@Windows@@@Z; CVRExclusiveFrameworkView::AddWindowEvents(Windows::UI::Core::ICoreWindow *)
0x18001fa45  mov     rax, [rsi]
0x18001fa48  lea     r8, [rbp+57h+var_70]
0x18001fa4c  lea     rdx, _GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f
0x18001fa53  mov     [rbp+57h+var_70], r15
0x18001fa57  mov     rcx, rsi
0x18001fa5a  mov     rax, [rax]
0x18001fa5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa62  test    eax, eax
0x18001fa64  jns     short loc_18001FA7F
0x18001fa66  mov     rcx, [rbp+5Fh]; this
0x18001fa6a  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fa71  mov     r9d, eax; char *
0x18001fa74  mov     edx, 4Dh ; 'M'; void *
0x18001fa79  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fa7f  mov     rcx, [rbp+57h+var_70]
0x18001fa83  lea     rdx, [rbp+57h+hWnd]
0x18001fa87  mov     [rbp+57h+hWnd], r15
0x18001fa8b  mov     rax, [rcx]
0x18001fa8e  mov     rax, [rax+18h]
0x18001fa92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa97  test    eax, eax
0x18001fa99  jns     short loc_18001FAB4
0x18001fa9b  mov     rcx, [rbp+5Fh]; this
0x18001fa9f  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001faa6  mov     r9d, eax; char *
0x18001faa9  mov     edx, 50h ; 'P'; void *
0x18001faae  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fab4  mov     rcx, [rbp+57h+hWnd]; hWnd
0x18001fab8  lea     rdx, aE40c9088C52142; "{E40C9088-C521-424B-AA4B-6520171CD690}"
0x18001fabf  mov     r8d, 1; hData
0x18001fac5  call    cs:__imp_SetPropW
0x18001facb  mov     r9d, 2Dh ; '-'; unsigned int
0x18001fad1  mov     [rbp+57h+var_58], r15
0x18001fad5  lea     rdx, ?RuntimeClass_Windows_Graphics_Holographic_HolographicSpace@@3QBGB; "Windows.Graphics.Holographic.Holographi"...
0x18001fadc  mov     [rbp+57h+var_78], r15
0x18001fae0  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001fae4  mov     [rbp+57h+var_30], r15
0x18001fae8  lea     r8d, [r9+1]; unsigned int
0x18001faec  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001faf1  mov     rbx, [rbp+57h+var_30]
0x18001faf5  lea     rcx, [rbp+57h+var_78]
0x18001faf9  call    ?InternalRelease@?$ComPtr@UIVRExclusiveViewState@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(void)
0x18001fafe  lea     r8, [rbp+57h+var_78]
0x18001fb02  mov     rcx, rbx
0x18001fb05  lea     rdx, _GUID_364e6064_c8f2_3ba1_8391_66b8489e67fd
0x18001fb0c  call    cs:__imp_RoGetActivationFactory
0x18001fb12  test    eax, eax
0x18001fb14  jns     short loc_18001FB2F
0x18001fb16  mov     rcx, [rbp+5Fh]; this
0x18001fb1a  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fb21  mov     r9d, eax; char *
0x18001fb24  mov     edx, 5Dh ; ']'; void *
0x18001fb29  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fb2f  mov     rdi, [rbp+57h+var_78]
0x18001fb33  lea     rcx, [rbp+57h+var_58]
0x18001fb37  mov     rax, [rdi]
0x18001fb3a  mov     rbx, [rax+30h]
0x18001fb3e  call    ?InternalRelease@?$ComPtr@UIVRExclusiveViewState@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(void)
0x18001fb43  lea     r8, [rbp+57h+var_58]
0x18001fb47  mov     rdx, rsi
0x18001fb4a  mov     rcx, rdi
0x18001fb4d  mov     rax, rbx
0x18001fb50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb55  test    eax, eax
0x18001fb57  jns     short loc_18001FB72
0x18001fb59  mov     rcx, [rbp+5Fh]; this
0x18001fb5d  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fb64  mov     r9d, eax; char *
0x18001fb67  mov     edx, 5Eh ; '^'; void *
0x18001fb6c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fb72  lea     r8, [rbp+57h+ppstm]; ppstm
0x18001fb76  mov     [rbp+57h+ppstm], r15
0x18001fb7a  mov     edx, 1; fDeleteOnRelease
0x18001fb7f  xor     ecx, ecx; hGlobal
0x18001fb81  call    cs:__imp_CreateStreamOnHGlobal
0x18001fb87  test    eax, eax
0x18001fb89  jns     short loc_18001FBA4
0x18001fb8b  mov     rcx, [rbp+5Fh]; this
0x18001fb8f  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fb96  mov     r9d, eax; char *
0x18001fb99  mov     edx, 61h ; 'a'; void *
0x18001fb9e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fba4  mov     rcx, [rbp+57h+ppstm]; pStm
0x18001fba8  lea     rdx, _GUID_79b9d5f2_879e_4b89_b798_79e47598030c; riid
0x18001fbaf  mov     [rsp+0C0h+mshlflags], r15d; mshlflags
0x18001fbb4  xor     r9d, r9d; dwDestContext
0x18001fbb7  mov     r8, rsi; pUnk
0x18001fbba  mov     [rsp+0C0h+pvDestContext], r15; int
0x18001fbbf  call    cs:__imp_CoMarshalInterface
0x18001fbc5  test    eax, eax
0x18001fbc7  jns     short loc_18001FBE2
0x18001fbc9  mov     rcx, [rbp+5Fh]; this
0x18001fbcd  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fbd4  mov     r9d, eax; char *
0x18001fbd7  mov     edx, 63h ; 'c'; void *
0x18001fbdc  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fbe2  mov     rbx, [rbp+57h+ppstm]
0x18001fbe6  cmp     [r14+48h], rbx
0x18001fbea  jz      short loc_18001FC0E
0x18001fbec  lea     rcx, [rbp+57h+var_68]
0x18001fbf0  mov     [rbp+57h+var_68], rbx
0x18001fbf4  call    ?InternalAddRef@?$ComPtr@UIVRExclusiveViewCallbacks@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IVRExclusiveViewCallbacks>::InternalAddRef(void)
0x18001fbf9  mov     rax, [r14+48h]
0x18001fbfd  lea     rcx, [rbp+57h+var_68]
0x18001fc01  mov     [rbp+57h+var_68], rax
0x18001fc05  mov     [r14+48h], rbx
0x18001fc09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001fc0e  mov     r9d, 29h ; ')'; unsigned int
0x18001fc14  mov     [rbp+57h+var_60], r15
0x18001fc18  lea     rdx, ?RuntimeClass_Windows_UI_ViewManagement_ApplicationView@@3QBGB; "Windows.UI.ViewManagement.ApplicationVi"...
0x18001fc1f  mov     [rbp+57h+var_30], r15
0x18001fc23  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001fc27  lea     r8d, [r9+1]; unsigned int
0x18001fc2b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001fc30  mov     rcx, [rbp+57h+var_30]
0x18001fc34  lea     rdx, [rbp+57h+var_60]
0x18001fc38  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationViewStatics2@ViewManagement@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationViewStatics2@ViewManagement@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::ViewManagement::IApplicationViewStatics2>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::ViewManagement::IApplicationViewStatics2>>)
0x18001fc3d  test    eax, eax
0x18001fc3f  jns     short loc_18001FC5A
0x18001fc41  mov     rcx, [rbp+5Fh]; this
0x18001fc45  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fc4c  mov     r9d, eax; char *
0x18001fc4f  mov     edx, 6Bh ; 'k'; void *
0x18001fc54  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fc5a  mov     rdi, [rbp+57h+var_60]
0x18001fc5e  lea     rcx, [rbp+57h+var_88]
0x18001fc62  mov     [rbp+57h+var_88], r15
0x18001fc66  mov     rax, [rdi]
0x18001fc69  mov     rbx, [rax+30h]
0x18001fc6d  call    ?InternalRelease@?$ComPtr@UIVRExclusiveViewState@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(void)
0x18001fc72  lea     rdx, [rbp+57h+var_88]
0x18001fc76  mov     rcx, rdi
0x18001fc79  mov     rax, rbx
0x18001fc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc81  test    eax, eax
0x18001fc83  jns     short loc_18001FC9E
0x18001fc85  mov     rcx, [rbp+5Fh]; this
0x18001fc89  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fc90  mov     r9d, eax; char *
0x18001fc93  mov     edx, 6Eh ; 'n'; void *
0x18001fc98  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fc9e  mov     rcx, [rbp+57h+var_88]
0x18001fca2  lea     rdx, [r14+188h]
0x18001fca9  mov     rax, [rcx]
0x18001fcac  mov     rax, [rax+78h]
0x18001fcb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcb5  test    eax, eax
0x18001fcb7  jns     short loc_18001FCD2
0x18001fcb9  mov     rcx, [rbp+5Fh]; this
0x18001fcbd  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fcc4  mov     r9d, eax; char *
0x18001fcc7  mov     edx, 70h ; 'p'; void *
0x18001fccc  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fcd2  mov     rax, [rsi]
0x18001fcd5  lea     r8, [rbp+57h+var_90]
0x18001fcd9  lea     rdx, _GUID_0576ab31_a310_4c40_ba31_fd37e0298dfa
0x18001fce0  mov     [rbp+57h+var_90], r15
0x18001fce4  mov     rcx, rsi
0x18001fce7  mov     rax, [rax]
0x18001fcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcef  test    eax, eax
0x18001fcf1  jns     short loc_18001FD0C
0x18001fcf3  mov     rcx, [rbp+5Fh]; this
0x18001fcf7  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fcfe  mov     r9d, eax; char *
0x18001fd01  mov     edx, 75h ; 'u'; void *
0x18001fd06  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fd0c  mov     rcx, [rbp+57h+var_90]
0x18001fd10  lea     rdx, [r14+18Ch]
0x18001fd17  mov     rax, [rcx]
0x18001fd1a  mov     rax, [rax+20h]
0x18001fd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd23  test    eax, eax
0x18001fd25  jns     short loc_18001FD40
0x18001fd27  mov     rcx, [rbp+5Fh]; this
0x18001fd2b  lea     r8, aOnecoreuapInet_40; "onecoreuap\\inetcore\\lib\\edge\\webvr"...
0x18001fd32  mov     r9d, eax; char *
0x18001fd35  mov     edx, 76h ; 'v'; void *
0x18001fd3a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001fd40  mov     rax, [rsi]
0x18001fd43  mov     rcx, rsi
0x18001fd46  mov     rax, [rax+90h]
0x18001fd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd52  mov     rcx, [rbp+57h+var_90]
0x18001fd56  test    rcx, rcx
0x18001fd59  jz      short loc_18001FD6B
0x18001fd5b  mov     [rbp+57h+var_90], r15
0x18001fd5f  mov     rax, [rcx]
0x18001fd62  mov     rax, [rax+10h]
0x18001fd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd6b  lea     rcx, [rbp+57h+var_88]
0x18001fd6f  call    ?InternalRelease@?$ComPtr@UIVRExclusiveViewState@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(void)
0x18001fd74  lea     rcx, [rbp+57h+var_60]
0x18001fd78  call    ?InternalRelease@?$ComPtr@UIVRExclusiveViewState@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(void)
0x18001fd7d  lea     rcx, [rbp+57h+ppstm]
0x18001fd81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001fd86  lea     rcx, [rbp+57h+var_78]
0x18001fd8a  call    ?InternalRelease@?$ComPtr@UIVRExclusiveViewState@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(void)
0x18001fd8f  lea     rcx, [rbp+57h+var_58]
0x18001fd93  call    ?InternalRelease@?$ComPtr@UIVRExclusiveViewState@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IVRExclusiveViewState>::InternalRelease(void)
0x18001fd98  mov     rcx, [rbp+57h+var_70]
0x18001fd9c  test    rcx, rcx
0x18001fd9f  jz      short loc_18001FDB1
0x18001fda1  mov     [rbp+57h+var_70], r15
0x18001fda5  mov     rax, [rcx]
0x18001fda8  mov     rax, [rax+10h]
0x18001fdac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdb1  xor     eax, eax
0x18001fdb3  mov     rcx, [rbp+57h+var_28]
0x18001fdb7  xor     rcx, rsp; StackCookie
0x18001fdba  call    __security_check_cookie
0x18001fdbf  mov     rbx, [rsp+0C0h+arg_10]
0x18001fdc7  add     rsp, 0A0h
0x18001fdce  pop     r15
0x18001fdd0  pop     r14
0x18001fdd2  pop     rdi
0x18001fdd3  pop     rsi
0x18001fdd4  pop     rbp
0x18001fdd5  retn
```
