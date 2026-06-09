# winrt::Windows::Graphics::Capture::implementation::VisualCaptureSessionCore::VisualCaptureSessionCore(winrt::Windows::UI::Composition::Visual,void *)

- ea: `0x180024298`
- end: `0x180024539`
- name: `??0VisualCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@QEAA@UVisual@Composition@UI@45@PEAX@Z`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001c5c8`

## callees

- `0x180003580`
- `0x1800039fc`
- `0x180006610`
- `0x1800125ec`
- `0x180024298`
- `0x1800245ac`
- `0x18002467c`
- `0x180024738`
- `0x180024874`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall winrt::Windows::Graphics::Capture::implementation::VisualCaptureSessionCore::VisualCaptureSessionCore(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  _QWORD *v6; // rdi
  void (__fastcall ****v7)(_QWORD, __int64 *, __int64 *); // r15
  __int64 v8; // r14
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  __int64 (__fastcall ***v12)(_QWORD, __int64 *, __int64 *); // rcx
  unsigned int v13; // eax
  void (__fastcall ***v14)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v15; // rdx
  __int64 (__fastcall ***v16)(_QWORD, __int64 *, __int64 *); // rcx
  unsigned int v17; // eax
  __int64 (__fastcall ***v18)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  __int64 v23; // [rsp+20h] [rbp-30h] BYREF
  __int64 v24; // [rsp+28h] [rbp-28h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, __int64 *, __int64 *); // [rsp+30h] [rbp-20h] BYREF
  int v26; // [rsp+38h] [rbp-18h] BYREF
  __int128 v27; // [rsp+40h] [rbp-10h]
  __int64 v28; // [rsp+A8h] [rbp+58h] BYREF

  *a1 = &winrt::Windows::Graphics::Capture::implementation::VisualCaptureSessionCore::`vftable';
  v6 = a1 + 1;
  a1[1] = 0;
  v7 = (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 2);
  a1[2] = 0;
  winrt::impl::consume_Windows_UI_Composition_ICompositionObject<winrt::Windows::UI::Composition::Visual>::Compositor(
    a2,
    &v25);
  if ( v25 )
  {
    v23 = 0;
    v26 = 0;
    v27 = 0;
    v9 = (**v25)(v25, winrt::impl::guid_v<winrt::Windows::UI::Composition::Internal::ICompositorInternal>, &v23);
    winrt::check_hresult(&v28, v9, &v26);
    v8 = v23;
    v24 = v23;
  }
  else
  {
    v24 = 0;
    v8 = 0;
  }
  v23 = 0;
  v26 = 0;
  v27 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 56LL))(v8, &v23);
  winrt::check_hresult(&v28, v10, &v26);
  v28 = v23;
  winrt::Windows::Foundation::IUnknown::operator=(v6, &v28);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v28);
  v23 = 0;
  v26 = 0;
  v27 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 48LL))(v8, &v23);
  winrt::check_hresult(&v28, v11, &v26);
  v28 = v23;
  winrt::Windows::Foundation::IUnknown::operator=(v7, &v28);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v28);
  v12 = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *))*v6;
  v26 = 0;
  v27 = 0;
  v13 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD))(*v12)[9])(v12, 0);
  winrt::check_hresult(&v28, v13, &v26);
  winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::IsCapturing(
    v7,
    0);
  winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::IsConstrainedBySize(v7);
  winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::Root(
    v7,
    a2);
  v14 = *v7;
  if ( *v7 )
  {
    v28 = 0;
    (**v14)(v14, winrt::impl::guid_v<winrt::Windows::UI::Composition::Internal::ICaptureControllerBase>, &v28);
    v15 = v28;
  }
  else
  {
    v15 = 0;
  }
  v23 = v15;
  v16 = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *))*v6;
  v26 = 0;
  v27 = 0;
  v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *)))(*v16)[7])(v16);
  winrt::check_hresult(&v28, v17, &v26);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v23);
  v18 = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *))*v6;
  v23 = 0;
  if ( v18 )
  {
    v26 = 0;
    v27 = 0;
    v20 = (**v18)(v18, winrt::impl::guid_v<Windows::UI::Composition::Internal::ICaptureRenderTargetInterop>, &v23);
    winrt::check_hresult(&v28, v20, &v26);
    v19 = v23;
  }
  else
  {
    v19 = 0;
  }
  v26 = 0;
  v27 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 24LL))(v19, a3);
  winrt::check_hresult(&v28, v21, &v26);
  winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(&v23);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v24);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v25);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(a2);
  return a1;
}

```

## disassembly

```asm
0x180024298  mov     [rsp-38h+arg_10], rbx
0x18002429d  mov     [rsp-38h+arg_8], rdx
0x1800242a2  mov     [rsp-38h+arg_0], rcx
0x1800242a7  push    rbp
0x1800242a8  push    rsi
0x1800242a9  push    rdi
0x1800242aa  push    r12
0x1800242ac  push    r13
0x1800242ae  push    r14
0x1800242b0  push    r15
0x1800242b2  mov     rbp, rsp
0x1800242b5  sub     rsp, 50h
0x1800242b9  mov     r12, r8
0x1800242bc  mov     rsi, rdx
0x1800242bf  mov     rbx, rcx
0x1800242c2  xor     r13d, r13d
0x1800242c5  lea     rax, ??_7VisualCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@6B@; const winrt::Windows::Graphics::Capture::implementation::VisualCaptureSessionCore::`vftable'
0x1800242cc  mov     [rcx], rax
0x1800242cf  lea     rdi, [rcx+8]
0x1800242d3  mov     [rdi], r13
0x1800242d6  lea     r15, [rcx+10h]
0x1800242da  mov     [r15], r13
0x1800242dd  lea     rdx, [rbp+var_20]
0x1800242e1  mov     rcx, rsi
0x1800242e4  call    ?Compositor@?$consume_Windows_UI_Composition_ICompositionObject@UVisual@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Composition_ICompositionObject<winrt::Windows::UI::Composition::Visual>::Compositor(void)
0x1800242e9  nop
0x1800242ea  mov     rcx, [rbp+var_20]
0x1800242ee  test    rcx, rcx
0x1800242f1  jnz     short loc_1800242FC
0x1800242f3  mov     [rbp+var_28], r13
0x1800242f7  mov     r14d, r13d
0x1800242fa  jmp     short loc_180024339
0x1800242fc  mov     [rbp+var_30], r13
0x180024300  mov     [rbp+var_18], r13d
0x180024304  xorps   xmm0, xmm0
0x180024307  movdqu  [rbp+var_10], xmm0
0x18002430c  mov     rax, [rcx]
0x18002430f  lea     r8, [rbp+var_30]
0x180024313  lea     rdx, ??$guid_v@UICompositorInternal@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::Internal::ICompositorInternal>
0x18002431a  mov     rax, [rax]
0x18002431d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024322  lea     r8, [rbp+var_18]
0x180024326  mov     edx, eax
0x180024328  lea     rcx, [rbp+arg_18]
0x18002432c  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024331  mov     r14, [rbp+var_30]
0x180024335  mov     [rbp+var_28], r14
0x180024339  mov     [rbp+var_30], r13
0x18002433d  mov     [rbp+var_18], r13d
0x180024341  xorps   xmm0, xmm0
0x180024344  movdqu  [rbp+var_10], xmm0
0x180024349  mov     rax, [r14]
0x18002434c  lea     rdx, [rbp+var_30]
0x180024350  mov     rcx, r14
0x180024353  mov     rax, [rax+38h]
0x180024357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002435c  lea     r8, [rbp+var_18]
0x180024360  mov     edx, eax
0x180024362  lea     rcx, [rbp+arg_18]
0x180024366  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002436b  mov     rax, [rbp+var_30]
0x18002436f  mov     [rbp+arg_18], rax
0x180024373  lea     rdx, [rbp+arg_18]
0x180024377  mov     rcx, rdi
0x18002437a  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18002437f  lea     rcx, [rbp+arg_18]
0x180024383  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180024388  mov     [rbp+var_30], r13
0x18002438c  mov     [rbp+var_18], r13d
0x180024390  xorps   xmm0, xmm0
0x180024393  movdqu  [rbp+var_10], xmm0
0x180024398  mov     rax, [r14]
0x18002439b  lea     rdx, [rbp+var_30]
0x18002439f  mov     rcx, r14
0x1800243a2  mov     rax, [rax+30h]
0x1800243a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243ab  lea     r8, [rbp+var_18]
0x1800243af  mov     edx, eax
0x1800243b1  lea     rcx, [rbp+arg_18]
0x1800243b5  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800243ba  mov     rax, [rbp+var_30]
0x1800243be  mov     [rbp+arg_18], rax
0x1800243c2  lea     rdx, [rbp+arg_18]
0x1800243c6  mov     rcx, r15
0x1800243c9  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800243ce  lea     rcx, [rbp+arg_18]
0x1800243d2  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800243d7  mov     rcx, [rdi]
0x1800243da  mov     [rbp+var_18], r13d
0x1800243de  xorps   xmm0, xmm0
0x1800243e1  movdqu  [rbp+var_10], xmm0
0x1800243e6  mov     rax, [rcx]
0x1800243e9  xor     edx, edx
0x1800243eb  mov     rax, [rax+48h]
0x1800243ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243f4  lea     r8, [rbp+var_18]
0x1800243f8  mov     edx, eax
0x1800243fa  lea     rcx, [rbp+arg_18]
0x1800243fe  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024403  xor     edx, edx
0x180024405  mov     rcx, r15
0x180024408  call    ?IsCapturing@?$consume_Windows_UI_Composition_Internal_IWriteCaptureController@UCaptureController@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::IsCapturing(bool)
0x18002440d  mov     rcx, r15
0x180024410  call    ?IsConstrainedBySize@?$consume_Windows_UI_Composition_Internal_IWriteCaptureController@UCaptureController@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::IsConstrainedBySize(bool)
0x180024415  mov     rdx, rsi
0x180024418  mov     rcx, r15
0x18002441b  call    ?Root@?$consume_Windows_UI_Composition_Internal_IWriteCaptureController@UCaptureController@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUVisual@Composition@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::Root(winrt::Windows::UI::Composition::Visual const &)
0x180024420  mov     rcx, [r15]
0x180024423  test    rcx, rcx
0x180024426  jnz     short loc_18002442D
0x180024428  mov     rdx, r13
0x18002442b  jmp     short loc_18002444B
0x18002442d  mov     [rbp+arg_18], r13
0x180024431  mov     rax, [rcx]
0x180024434  lea     r8, [rbp+arg_18]
0x180024438  lea     rdx, ??$guid_v@UICaptureControllerBase@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::Internal::ICaptureControllerBase>
0x18002443f  mov     rax, [rax]
0x180024442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024447  mov     rdx, [rbp+arg_18]
0x18002444b  mov     [rbp+var_30], rdx
0x18002444f  mov     rcx, [rdi]
0x180024452  mov     [rbp+var_18], r13d
0x180024456  xorps   xmm0, xmm0
0x180024459  movdqu  [rbp+var_10], xmm0
0x18002445e  mov     rax, [rcx]
0x180024461  mov     rax, [rax+38h]
0x180024465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002446a  lea     r8, [rbp+var_18]
0x18002446e  mov     edx, eax
0x180024470  lea     rcx, [rbp+arg_18]
0x180024474  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024479  nop
0x18002447a  lea     rcx, [rbp+var_30]
0x18002447e  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180024483  mov     rcx, [rdi]
0x180024486  mov     [rbp+var_30], r13
0x18002448a  test    rcx, rcx
0x18002448d  jnz     short loc_180024494
0x18002448f  mov     rcx, r13
0x180024492  jmp     short loc_1800244CD
0x180024494  mov     [rbp+var_18], r13d
0x180024498  xorps   xmm0, xmm0
0x18002449b  movdqu  [rbp+var_10], xmm0
0x1800244a0  mov     rax, [rcx]
0x1800244a3  lea     r8, [rbp+var_30]
0x1800244a7  lea     rdx, ??$guid_v@UICaptureRenderTargetInterop@Internal@Composition@UI@Windows@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<Windows::UI::Composition::Internal::ICaptureRenderTargetInterop>
0x1800244ae  mov     rax, [rax]
0x1800244b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244b6  lea     r8, [rbp+var_18]
0x1800244ba  mov     edx, eax
0x1800244bc  lea     rcx, [rbp+arg_18]
0x1800244c0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800244c5  mov     rcx, [rbp+var_30]
0x1800244c9  mov     [rbp+var_30], rcx
0x1800244cd  mov     [rbp+var_18], r13d
0x1800244d1  xorps   xmm0, xmm0
0x1800244d4  movdqu  [rbp+var_10], xmm0
0x1800244d9  mov     rax, [rcx]
0x1800244dc  mov     rdx, r12
0x1800244df  mov     rax, [rax+18h]
0x1800244e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244e8  lea     r8, [rbp+var_18]
0x1800244ec  mov     edx, eax
0x1800244ee  lea     rcx, [rbp+arg_18]
0x1800244f2  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800244f7  nop
0x1800244f8  lea     rcx, [rbp+var_30]
0x1800244fc  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x180024501  nop
0x180024502  lea     rcx, [rbp+var_28]
0x180024506  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18002450b  nop
0x18002450c  lea     rcx, [rbp+var_20]
0x180024510  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180024515  nop
0x180024516  mov     rcx, rsi
0x180024519  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18002451e  mov     rax, rbx
0x180024521  mov     rbx, [rsp+50h+arg_10]
0x180024529  add     rsp, 50h
0x18002452d  pop     r15
0x18002452f  pop     r14
0x180024531  pop     r13
0x180024533  pop     r12
0x180024535  pop     rdi
0x180024536  pop     rsi
0x180024537  pop     rbp
0x180024538  retn
```
