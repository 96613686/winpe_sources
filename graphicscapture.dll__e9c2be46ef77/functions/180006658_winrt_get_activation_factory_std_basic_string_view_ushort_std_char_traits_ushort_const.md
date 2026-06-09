# winrt_get_activation_factory(std::basic_string_view<ushort,std::char_traits<ushort>> const &)

- ea: `0x180006658`
- end: `0x1800068ab`
- name: `?winrt_get_activation_factory@@YAPEAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180006964`

## callees

- `0x180001f78`
- `0x180002158`
- `0x180002cb4`
- `0x180002da8`
- `0x180003168`
- `0x1800031a0`
- `0x1800031c4`
- `0x18000320c`
- `0x180003580`
- `0x180003aac`
- `0x180005d28`
- `0x180006658`

## string_xrefs

- `0x1800066e6`: `Windows.Graphics.Capture.GraphicsCaptureAccess`

## pseudocode

```c
_QWORD *winrt_get_activation_factory()
{
  __int64 v0; // rcx
  __int64 v1; // r10
  _OWORD *v2; // rax
  _OWORD *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  void ***v7; // r9
  void **v8; // rcx
  __int64 v10; // rcx
  __int64 v11; // r10
  _OWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // r10
  _QWORD *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // r10
  _QWORD *v21; // rax
  __int64 v22; // r8
  _QWORD *v23; // r8
  __int64 v24; // rcx
  __int64 v25; // r10
  _OWORD *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  const unsigned __int16 *v30; // [rsp+20h] [rbp-10h] BYREF
  __int64 v31; // [rsp+28h] [rbp-8h]
  __int64 v32; // [rsp+48h] [rbp+18h] BYREF

  v30 = L"Windows.Graphics.Capture.Direct3D11CaptureFramePool";
  v31 = std::_WChar_traits<unsigned short>::length(L"Windows.Graphics.Capture.Direct3D11CaptureFramePool");
  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v0, v1, &v30) )
  {
    v2 = operator new(0x30u);
    *v2 = 0;
    v3 = v2 + 1;
    v2[1] = 0;
    v2[2] = 0;
    winrt::impl::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics2,winrt::Windows::Internal::Graphics::Capture::IDirect3D11CaptureFramePoolFactoryInternal>>::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics2,winrt::Windows::Internal::Graphics::Capture::IDirect3D11CaptureFramePoolFactoryInternal>>(
      v2 + 1,
      v4,
      v5,
      v2);
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v6 + 8);
    v8 = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::Direct3D11CaptureFramePool>::`vftable';
LABEL_3:
    *v7 = v8;
LABEL_4:
    v32 = 0;
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v32);
    return v3;
  }
  v30 = L"Windows.Graphics.Capture.GraphicsCaptureAccess";
  v31 = std::_WChar_traits<unsigned short>::length(L"Windows.Graphics.Capture.GraphicsCaptureAccess");
  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v10, v11, &v30) )
  {
    v12 = operator new(0x20u);
    v3 = v12 + 1;
    *v12 = 0;
    v12[1] = 0;
    winrt::impl::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>>::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>>(
      v12 + 1,
      v13,
      v14,
      v12);
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v15 + 8);
    v8 = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess>::`vftable';
    goto LABEL_3;
  }
  v30 = L"Windows.Graphics.Capture.GraphicsCaptureItem";
  v31 = std::_WChar_traits<unsigned short>::length(L"Windows.Graphics.Capture.GraphicsCaptureItem");
  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v16, v17, &v30) )
  {
    v18 = operator new(0x48u);
    memset_0(v18, 0, 0x48u);
    winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItemT<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,IGraphicsCaptureItemInterop,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInterop2,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInteropInternal,winrt::cloaked<winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemFactoryInternal>>::GraphicsCaptureItemT<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,IGraphicsCaptureItemInterop,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInterop2,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInteropInternal,winrt::cloaked<winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemFactoryInternal>>(v18);
    v32 = 0;
    v18[1] = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem>::`vftable'{for `winrt::impl::producer_convert<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInterop2,void>'};
    *v18 = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem>::`vftable'{for `winrt::impl::producer_convert<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem,IGraphicsCaptureItemInterop,void>'};
    v18[2] = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem>::`vftable'{for `winrt::impl::producer_convert<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInteropInternal,void>'};
    v18[7] = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem>::`vftable';
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v32);
    return v18 + 3;
  }
  else
  {
    v30 = L"Windows.Graphics.Capture.GraphicsCapturePicker";
    v31 = std::_WChar_traits<unsigned short>::length(L"Windows.Graphics.Capture.GraphicsCapturePicker");
    if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v19, v20, &v30) )
    {
      v21 = operator new(0x18u);
      *(_OWORD *)v21 = 0;
      v3 = v21 + 2;
      v21[2] = 0;
      winrt::impl::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCapturePicker,std::tuple<winrt::Windows::Foundation::IActivationFactory>>::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCapturePicker,std::tuple<winrt::Windows::Foundation::IActivationFactory>>(v21 + 2);
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      std::atomic<unsigned __int64>::atomic<unsigned __int64>(v22 + 8);
      *v23 = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCapturePicker>::`vftable';
      goto LABEL_4;
    }
    v30 = L"Windows.Graphics.Capture.GraphicsCaptureSession";
    v31 = std::_WChar_traits<unsigned short>::length(L"Windows.Graphics.Capture.GraphicsCaptureSession");
    if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v24, v25, &v30) )
    {
      v26 = operator new(0x20u);
      v3 = v26 + 1;
      *v26 = 0;
      v26[1] = 0;
      winrt::impl::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureSession,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureSessionStatics>>::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureSession,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureSessionStatics>>(
        v26 + 1,
        v27,
        v28,
        v26);
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      std::atomic<unsigned __int64>::atomic<unsigned __int64>(v29 + 8);
      v8 = &winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureSession>::`vftable';
      goto LABEL_3;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180006658  mov     [rsp-8+arg_0], rbx
0x18000665d  push    rbp
0x18000665e  mov     rbp, rsp
0x180006661  sub     rsp, 30h
0x180006665  mov     r10, rcx
0x180006668  lea     rcx, aWindowsGraphic_5; "Windows.Graphics.Capture.Direct3D11Capt"...
0x18000666f  mov     [rbp+var_10], rcx
0x180006673  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006678  lea     r8, [rbp+var_10]
0x18000667c  mov     [rbp+var_8], rax
0x180006680  mov     rdx, r10
0x180006683  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180006688  test    al, al
0x18000668a  jz      short loc_1800066E6
0x18000668c  mov     ecx, 30h ; '0'; Size
0x180006691  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006696  xorps   xmm0, xmm0
0x180006699  mov     r9, rax
0x18000669c  movups  xmmword ptr [rax], xmm0
0x18000669f  lea     rbx, [rax+10h]
0x1800066a3  movups  xmmword ptr [rax+10h], xmm0
0x1800066a7  mov     rcx, rbx
0x1800066aa  movups  xmmword ptr [rax+20h], xmm0
0x1800066ae  call    ??0?$producers_base@UDirect3D11CaptureFramePool@factory_implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@UIDirect3D11CaptureFramePoolStatics@Capture@Graphics@34@UIDirect3D11CaptureFramePoolStatics2@6734@UIDirect3D11CaptureFramePoolFactoryInternal@67Internal@34@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics2,winrt::Windows::Internal::Graphics::Capture::IDirect3D11CaptureFramePoolFactoryInternal>>::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::Direct3D11CaptureFramePool,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics2,winrt::Windows::Internal::Graphics::Capture::IDirect3D11CaptureFramePoolFactoryInternal>>(void)
0x1800066b3  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800066ba  lea     rcx, [r9+8]
0x1800066be  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x1800066c3  lea     rcx, ??_7?$heap_implements@UDirect3D11CaptureFramePool@factory_implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::Direct3D11CaptureFramePool>::`vftable'
0x1800066ca  mov     [r9], rcx
0x1800066cd  lea     rcx, [rbp+arg_8]
0x1800066d1  mov     [rbp+arg_8], 0
0x1800066d9  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800066de  mov     rax, rbx
0x1800066e1  jmp     loc_1800068A0
0x1800066e6  lea     rcx, aWindowsGraphic_1; "Windows.Graphics.Capture.GraphicsCaptur"...
0x1800066ed  mov     [rbp+var_10], rcx
0x1800066f1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800066f6  lea     r8, [rbp+var_10]
0x1800066fa  mov     [rbp+var_8], rax
0x1800066fe  mov     rdx, r10
0x180006701  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180006706  test    al, al
0x180006708  jz      short loc_180006746
0x18000670a  mov     ecx, 20h ; ' '; Size
0x18000670f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006714  xorps   xmm0, xmm0
0x180006717  mov     r9, rax
0x18000671a  lea     rbx, [rax+10h]
0x18000671e  movups  xmmword ptr [rax], xmm0
0x180006721  mov     rcx, rbx
0x180006724  movups  xmmword ptr [rax+10h], xmm0
0x180006728  call    ??0?$producers_base@UGraphicsCaptureAccess@factory_implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@UIGraphicsCaptureAccessStatics@Capture@Graphics@34@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>>::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>>(void)
0x18000672d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180006734  lea     rcx, [r9+8]
0x180006738  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18000673d  lea     rcx, ??_7?$heap_implements@UGraphicsCaptureAccess@factory_implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess>::`vftable'
0x180006744  jmp     short loc_1800066CA
0x180006746  lea     rcx, aWindowsGraphic_7; "Windows.Graphics.Capture.GraphicsCaptur"...
0x18000674d  mov     [rbp+var_10], rcx
0x180006751  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006756  lea     r8, [rbp+var_10]
0x18000675a  mov     [rbp+var_8], rax
0x18000675e  mov     rdx, r10
0x180006761  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180006766  test    al, al
0x180006768  jz      short loc_1800067D2
0x18000676a  mov     ecx, 48h ; 'H'; Size
0x18000676f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006774  xor     edx, edx; Val
0x180006776  mov     rcx, rax; void *
0x180006779  mov     rbx, rax
0x18000677c  lea     r8d, [rdx+48h]; Size
0x180006780  call    memset_0
0x180006785  mov     rcx, rbx
0x180006788  call    ??0?$GraphicsCaptureItemT@UGraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@UGraphicsCaptureItemBase@implementation@3456@UIGraphicsCaptureItemInterop@@UIGraphicsCaptureItemInterop2@34Internal@5ABI@@UIGraphicsCaptureItemInteropInternal@34Internal@5ABI@@U?$cloaked@UIGraphicsCaptureItemFactoryInternal@Capture@Graphics@Internal@Windows@winrt@@@6@@factory_implementation@Capture@Graphics@Windows@winrt@@QEAA@XZ; winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItemT<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,IGraphicsCaptureItemInterop,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInterop2,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInteropInternal,winrt::cloaked<winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemFactoryInternal>>::GraphicsCaptureItemT<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem,winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureItemBase,IGraphicsCaptureItemInterop,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInterop2,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInteropInternal,winrt::cloaked<winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemFactoryInternal>>(void)
0x18000678d  lea     rax, ??_7?$heap_implements@UGraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B?$producer_convert@UGraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@UIGraphicsCaptureItemInterop2@34Internal@5ABI@@X@12@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem>::`vftable'{for `winrt::impl::producer_convert<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInterop2,void>'}
0x180006794  mov     [rbp+arg_8], 0
0x18000679c  mov     [rbx+8], rax
0x1800067a0  lea     rcx, ??_7?$heap_implements@UGraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B?$producer_convert@UGraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@UIGraphicsCaptureItemInterop@@X@12@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem>::`vftable'{for `winrt::impl::producer_convert<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem,IGraphicsCaptureItemInterop,void>'}
0x1800067a7  lea     rax, ??_7?$heap_implements@UGraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B?$producer_convert@UGraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@UIGraphicsCaptureItemInteropInternal@34Internal@5ABI@@X@12@@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem>::`vftable'{for `winrt::impl::producer_convert<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem,ABI::Windows::Internal::Graphics::Capture::IGraphicsCaptureItemInteropInternal,void>'}
0x1800067ae  mov     [rbx], rcx
0x1800067b1  mov     [rbx+10h], rax
0x1800067b5  lea     rcx, [rbp+arg_8]
0x1800067b9  lea     rax, ??_7?$heap_implements@UGraphicsCaptureItem@factory_implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureItem>::`vftable'
0x1800067c0  mov     [rbx+38h], rax
0x1800067c4  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800067c9  lea     rax, [rbx+18h]
0x1800067cd  jmp     loc_1800068A0
0x1800067d2  lea     rcx, aWindowsGraphic_0; "Windows.Graphics.Capture.GraphicsCaptur"...
0x1800067d9  mov     [rbp+var_10], rcx
0x1800067dd  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800067e2  lea     r8, [rbp+var_10]
0x1800067e6  mov     [rbp+var_8], rax
0x1800067ea  mov     rdx, r10
0x1800067ed  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x1800067f2  test    al, al
0x1800067f4  jz      short loc_18000683B
0x1800067f6  mov     ecx, 18h; Size
0x1800067fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006800  mov     r8, rax
0x180006803  xorps   xmm0, xmm0
0x180006806  xor     eax, eax
0x180006808  movups  xmmword ptr [r8], xmm0
0x18000680c  lea     rbx, [r8+10h]
0x180006810  mov     [r8+10h], rax
0x180006814  mov     rcx, rbx
0x180006817  call    ??0?$producers_base@UGraphicsCapturePicker@factory_implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCapturePicker,std::tuple<winrt::Windows::Foundation::IActivationFactory>>::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCapturePicker,std::tuple<winrt::Windows::Foundation::IActivationFactory>>(void)
0x18000681c  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180006823  lea     rcx, [r8+8]
0x180006827  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18000682c  lea     rcx, ??_7?$heap_implements@UGraphicsCapturePicker@factory_implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCapturePicker>::`vftable'
0x180006833  mov     [r8], rcx
0x180006836  jmp     loc_1800066CD
0x18000683b  lea     rcx, aWindowsGraphic_2; "Windows.Graphics.Capture.GraphicsCaptur"...
0x180006842  mov     [rbp+var_10], rcx
0x180006846  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000684b  lea     r8, [rbp+var_10]
0x18000684f  mov     [rbp+var_8], rax
0x180006853  mov     rdx, r10
0x180006856  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x18000685b  test    al, al
0x18000685d  jz      short loc_18000689E
0x18000685f  mov     ecx, 20h ; ' '; Size
0x180006864  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006869  xorps   xmm0, xmm0
0x18000686c  mov     r9, rax
0x18000686f  lea     rbx, [rax+10h]
0x180006873  movups  xmmword ptr [rax], xmm0
0x180006876  mov     rcx, rbx
0x180006879  movups  xmmword ptr [rax+10h], xmm0
0x18000687d  call    ??0?$producers_base@UGraphicsCaptureSession@factory_implementation@Capture@Graphics@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@UIGraphicsCaptureSessionStatics@Capture@Graphics@34@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureSession,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureSessionStatics>>::producers_base<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureSession,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureSessionStatics>>(void)
0x180006882  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180006889  lea     rcx, [r9+8]
0x18000688d  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180006892  lea     rcx, ??_7?$heap_implements@UGraphicsCaptureSession@factory_implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureSession>::`vftable'
0x180006899  jmp     loc_1800066CA
0x18000689e  xor     eax, eax
0x1800068a0  mov     rbx, [rsp+30h+arg_0]
0x1800068a5  add     rsp, 30h
0x1800068a9  pop     rbp
0x1800068aa  retn
```
