# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1800a18a0`
- end: `0x1800a193a`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `154`
- prototype: `void __fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ab010`
- `0x1800d1e68`
- `0x1800d21a0`
- `0x1800d22a8`
- `0x1800d23b0`
- `0x1800d2484`
- `0x1800e18c8`
- `0x1800eb7a0`
- `0x1800ebbf8`
- `0x1800f69a0`

## callees

- `0x1800730a4`
- `0x1800a18a0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a18dc`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a18dc`

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
0x1800a18a0  push    rbx
0x1800a18a2  push    rsi
0x1800a18a3  push    rdi
0x1800a18a4  push    r14
0x1800a18a6  sub     rsp, 28h
0x1800a18aa  lea     r14, [this+18h]
0x1800a18ae  mov     [rsp+48h+unknown.ptr_], 0
0x1800a18b7  lea     rax, ??_7?$CAsyncOperationBase@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@23@$0A@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800a18be  mov     rsi, this
0x1800a18c1  mov     [this], rax
0x1800a18c4  lea     this, [rsp+48h+unknown]; this
0x1800a18c9  mov     qword ptr [r14], 0
0x1800a18d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a18d5  lea     rdx, [rsp+48h+unknown]; ppunkMarshal
0x1800a18da  xor     ecx, ecx; punkOuter
0x1800a18dc  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800a18e2  test    eax, eax
0x1800a18e4  js      short loc_1800A190E
0x1800a18e6  mov     rbx, [rsp+48h+unknown.ptr_]
0x1800a18eb  mov     this, r14; this
0x1800a18ee  mov     rax, [rbx]
0x1800a18f1  mov     rdi, [rax]
0x1800a18f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a18f9  mov     r8, r14
0x1800a18fc  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800a1903  mov     this, rbx
0x1800a1906  mov     rax, rdi
0x1800a1909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a190e  mov     this, [rsp+48h+unknown.ptr_]
0x1800a1913  test    this, this
0x1800a1916  jz      short loc_1800A192D
0x1800a1918  mov     [rsp+48h+unknown.ptr_], 0
0x1800a1921  mov     rax, [this]
0x1800a1924  mov     rax, [rax+10h]
0x1800a1928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a192d  mov     rax, rsi
0x1800a1930  add     rsp, 28h
0x1800a1934  pop     r14
0x1800a1936  pop     rdi
0x1800a1937  pop     rsi
0x1800a1938  pop     rbx
0x1800a1939  retn
```
