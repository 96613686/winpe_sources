# Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults::ProvisionFromXmlDocumentResults(uchar,HSTRING__ *)

- ea: `0x1800613c8`
- end: `0x180061469`
- name: `??0ProvisionFromXmlDocumentResults@NetworkOperators@Networking@Windows@@QEAA@EPEAUHSTRING__@@@Z`
- size: `161`
- prototype: `void __fastcall(Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults *this, unsigned __int8 AllElementsProvisioned, HSTRING__ *ResultsXml)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060f64`

## callees

- `0x18005f3f8`
- `0x1800613c8`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006144c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006144c`

## pseudocode

```c
void __fastcall Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults::ProvisionFromXmlDocumentResults(
        Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults *this,
        unsigned __int8 AllElementsProvisioned,
        HSTRING__ *ResultsXml)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::NetworkOperators::IProvisionedProfile,IInspectable>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::NetworkOperators::IProvisionedProfile,IInspectable>(this);
  this->Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IWeakReferenceSource,IInspectable>::Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults::IInspectable::IUnknown::__vftable = (Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::`vftable';
  this->Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IWeakReferenceSource,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::`vftable'{for `IWeakReferenceSource'};
  this->Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IWeakReferenceSource,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    Microsoft::WRL::Details::ModuleBase::module_->IncrementObjectCount(Microsoft::WRL::Details::ModuleBase::module_);
  this->Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IWeakReferenceSource,IInspectable>::Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults::IInspectable::IUnknown::__vftable = (Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults_vtbl *)Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults::`vftable';
  this->Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IWeakReferenceSource,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable>_vtbl *)Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults::`vftable'{for `IWeakReferenceSource'};
  this->Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IWeakReferenceSource,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,IInspectable>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>_vtbl *)Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>'};
  this->m_allElementsProvisioned = AllElementsProvisioned;
  this->m_resultsXml._hstring = 0;
  WindowsDeleteString(0);
  this->m_resultsXml._hstring = ResultsXml;
}

```

## disassembly

```asm
0x1800613c8  mov     [rsp+arg_0], rbx
0x1800613cd  mov     [rsp+arg_8], rsi
0x1800613d2  push    rdi
0x1800613d3  sub     rsp, 20h
0x1800613d7  mov     rdi, ResultsXml
0x1800613da  mov     sil, AllElementsProvisioned
0x1800613dd  mov     rbx, this
0x1800613e0  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIProvisionedProfile@NetworkOperators@Networking@Windows@@UIInspectable@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::NetworkOperators::IProvisionedProfile,IInspectable>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::NetworkOperators::IProvisionedProfile,IInspectable>(void)
0x1800613e5  lea     this, ??_7?$RuntimeClass@UIProvisionFromXmlDocumentResults@NetworkOperators@Networking@Windows@@UIInspectable@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::`vftable'
0x1800613ec  mov     [rbx], this
0x1800613ef  lea     rax, ??_7?$RuntimeClass@UIProvisionFromXmlDocumentResults@NetworkOperators@Networking@Windows@@UIInspectable@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::`vftable'{for `IWeakReferenceSource'}
0x1800613f6  mov     [rbx+8], rax
0x1800613fa  lea     rax, ??_7?$RuntimeClass@UIProvisionFromXmlDocumentResults@NetworkOperators@Networking@Windows@@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Networking::NetworkOperators::IProvisionFromXmlDocumentResults,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>'}
0x180061401  mov     [rbx+10h], rax
0x180061405  mov     this, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18006140c  test    this, this
0x18006140f  jz      short loc_18006141E
0x180061411  mov     rax, [this]
0x180061414  mov     rax, [rax+8]
0x180061418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006141d  nop
0x18006141e  lea     rax, ??_7ProvisionFromXmlDocumentResults@NetworkOperators@Networking@Windows@@6B@; const Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults::`vftable'
0x180061425  mov     [rbx], rax
0x180061428  lea     rax, ??_7ProvisionFromXmlDocumentResults@NetworkOperators@Networking@Windows@@6BIWeakReferenceSource@@@; const Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults::`vftable'{for `IWeakReferenceSource'}
0x18006142f  mov     [rbx+8], rax
0x180061433  lea     rax, ??_7ProvisionFromXmlDocumentResults@NetworkOperators@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIInspectable@@@Details@WRL@Microsoft@@@; const Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentResults::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IInspectable>'}
0x18006143a  mov     [rbx+10h], rax
0x18006143e  mov     [rbx+28h], sil
0x180061442  mov     qword ptr [rbx+30h], 0
0x18006144a  xor     ecx, ecx; string
0x18006144c  call    cs:__imp_WindowsDeleteString
0x180061452  mov     [rbx+30h], rdi
0x180061456  mov     rax, rbx
0x180061459  mov     rbx, [rsp+28h+arg_0]
0x18006145e  mov     rsi, [rsp+28h+arg_8]
0x180061463  add     rsp, 20h
0x180061467  pop     rdi
0x180061468  retn
```
