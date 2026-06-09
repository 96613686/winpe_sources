# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1800a218c`
- end: `0x1800a222d`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `161`
- prototype: `void __fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ac4e0`
- `0x1800d3a30`
- `0x1800d3d6c`
- `0x1800d3e74`
- `0x1800d3f7c`
- `0x1800d4050`
- `0x1800e3a64`
- `0x1800ed990`
- `0x1800ede04`
- `0x1800f8ed4`

## callees

- `0x1800719e4`
- `0x1800a218c`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a21c8`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a21c8`

## pseudocode

```c
void __fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  Microsoft::WRL::ComPtr<IMarshal> *p_marshaller; // r14
  IUnknown *ptr; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  IUnknown *v4; // rcx
  Microsoft::WRL::ComPtr<IUnknown> unknown; // [rsp+50h] [rbp+8h] BYREF

  p_marshaller = &this->marshaller_;
  unknown.ptr_ = 0;
  this->__vftable = (Microsoft::WRL::FtmBase_vtbl *)CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  this->marshaller_.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&unknown);
  if ( CoCreateFreeThreadedMarshaler(0, &unknown.ptr_) >= 0 )
  {
    ptr = unknown.ptr_;
    QueryInterface = unknown.ptr_->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)p_marshaller);
    QueryInterface(ptr, &GUID_00000003_0000_0000_c000_000000000046, (void **)&p_marshaller->ptr_);
  }
  v4 = unknown.ptr_;
  if ( unknown.ptr_ )
  {
    unknown.ptr_ = 0;
    v4->Release(v4);
  }
}

```

## disassembly

```asm
0x1800a218c  push    rbx
0x1800a218e  push    rsi
0x1800a218f  push    rdi
0x1800a2190  push    r14
0x1800a2192  sub     rsp, 28h
0x1800a2196  lea     r14, [this+18h]
0x1800a219a  mov     [rsp+48h+unknown.ptr_], 0
0x1800a21a3  lea     rax, ??_7?$CAsyncOperationBase@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@23@$0A@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800a21aa  mov     rsi, this
0x1800a21ad  mov     [this], rax
0x1800a21b0  lea     this, [rsp+48h+unknown]; this
0x1800a21b5  mov     qword ptr [r14], 0
0x1800a21bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a21c1  lea     rdx, [rsp+48h+unknown]; ppunkMarshal
0x1800a21c6  xor     ecx, ecx; punkOuter
0x1800a21c8  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800a21cf  nop     dword ptr [rax+rax+00h]
0x1800a21d4  test    eax, eax
0x1800a21d6  js      short loc_1800A2200
0x1800a21d8  mov     rbx, [rsp+48h+unknown.ptr_]
0x1800a21dd  mov     this, r14; this
0x1800a21e0  mov     rax, [rbx]
0x1800a21e3  mov     rdi, [rax]
0x1800a21e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a21eb  mov     r8, r14
0x1800a21ee  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800a21f5  mov     this, rbx
0x1800a21f8  mov     rax, rdi
0x1800a21fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2200  mov     this, [rsp+48h+unknown.ptr_]
0x1800a2205  test    this, this
0x1800a2208  jz      short loc_1800A221F
0x1800a220a  mov     [rsp+48h+unknown.ptr_], 0
0x1800a2213  mov     rax, [this]
0x1800a2216  mov     rax, [rax+10h]
0x1800a221a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a221f  mov     rax, rsi
0x1800a2222  add     rsp, 28h
0x1800a2226  pop     r14
0x1800a2228  pop     rdi
0x1800a2229  pop     rsi
0x1800a222a  pop     rbx
0x1800a222b  retn
```
