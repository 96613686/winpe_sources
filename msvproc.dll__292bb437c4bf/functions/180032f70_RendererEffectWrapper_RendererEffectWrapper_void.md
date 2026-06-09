# RendererEffectWrapper::~RendererEffectWrapper(void)

- ea: `0x180032f70`
- end: `0x180033015`
- name: `??1RendererEffectWrapper@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(RendererEffectWrapper *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800292f0`
- `0x1800b3660`

## callees

- `0x18000a09c`
- `0x18001a13c`
- `0x18001ba10`
- `0x1800b32b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032fa5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032fa5`

## pseudocode

```c
void __fastcall RendererEffectWrapper::~RendererEffectWrapper(RendererEffectWrapper *this)
{
  *(_QWORD *)this = &RendererEffectWrapper::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource>>'};
  *((_QWORD *)this + 5) = &RendererEffectWrapper::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource>>'};
  RendererEffectWrapper::Clear(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 728));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 200);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 192);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 184);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 176);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 168);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 160);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 152);
  MFD3D::CMFDXGIDeviceManagerHandle::~CMFDXGIDeviceManagerHandle((RendererEffectWrapper *)((char *)this + 112));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180032f70  push    rbx
0x180032f72  sub     rsp, 20h
0x180032f76  lea     rax, ??_7RendererEffectWrapper@@6B@; const RendererEffectWrapper::`vftable'
0x180032f7d  mov     rbx, rcx
0x180032f80  mov     [rcx], rax
0x180032f83  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource>>'}
0x180032f8a  mov     [rcx+8], rax
0x180032f8e  lea     rax, ??_7RendererEffectWrapper@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@@234@@Details@WRL@Microsoft@@@; const RendererEffectWrapper::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource>>'}
0x180032f95  mov     [rcx+28h], rax
0x180032f99  call    ?Clear@RendererEffectWrapper@@QEAAXXZ; RendererEffectWrapper::Clear(void)
0x180032f9e  lea     rcx, [rbx+2D8h]; lpCriticalSection
0x180032fa5  call    cs:__imp_DeleteCriticalSection
0x180032fab  lea     rcx, [rbx+0C8h]
0x180032fb2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032fb7  lea     rcx, [rbx+0C0h]
0x180032fbe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032fc3  lea     rcx, [rbx+0B8h]
0x180032fca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032fcf  lea     rcx, [rbx+0B0h]
0x180032fd6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032fdb  lea     rcx, [rbx+0A8h]
0x180032fe2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032fe7  lea     rcx, [rbx+0A0h]
0x180032fee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032ff3  lea     rcx, [rbx+98h]
0x180032ffa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032fff  lea     rcx, [rbx+70h]; this
0x180033003  call    ??1CMFDXGIDeviceManagerHandle@MFD3D@@QEAA@XZ; MFD3D::CMFDXGIDeviceManagerHandle::~CMFDXGIDeviceManagerHandle(void)
0x180033008  mov     rcx, rbx
0x18003300b  add     rsp, 20h
0x18003300f  pop     rbx
0x180033010  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase>(void)
```
