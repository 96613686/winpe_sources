# Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800d3040`
- end: `0x1800d309f`
- name: `?GetIids@?$ActivationFactory@UIXmlDocumentStatics@Dom@Xml@Data@Windows@@VFtmBase@WRL@Microsoft@@VNil@Details@78@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `HRESULT __fastcall(Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d30b0`

## callees

- `0x1800d2fbc`
- `0x1800d3040`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d3062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d3062`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::GetIids(
        Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *v5; // rcx
  _GUID *v6; // r8
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v6 = (_GUID *)CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  index = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v5,
    &index,
    v6);
  *iidCount = 2;
  result = 0;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x1800d3040  mov     [rsp+arg_0], rbx
0x1800d3045  push    rdi
0x1800d3046  sub     rsp, 20h
0x1800d304a  mov     qword ptr [iids], 0
0x1800d3051  mov     ecx, 20h ; ' '; cb
0x1800d3056  mov     dword ptr [iidCount], 0
0x1800d305c  mov     rbx, iids
0x1800d305f  mov     rdi, iidCount
0x1800d3062  call    cs:__imp_CoTaskMemAlloc
0x1800d3068  mov     iids, rax; iids
0x1800d306b  test    rax, rax
0x1800d306e  jnz     short loc_1800D3077
0x1800d3070  mov     eax, 8007000Eh
0x1800d3075  jmp     short loc_1800D3094
0x1800d3077  lea     iidCount, [rsp+28h+index]; index
0x1800d307c  mov     [rsp+28h+index], 0
0x1800d3084  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@UIXmlDocumentStatics@Dom@Xml@Data@Windows@@VFtmBase@23@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x1800d3089  mov     dword ptr [rdi], 2
0x1800d308f  xor     eax, eax
0x1800d3091  mov     [rbx], iids
0x1800d3094  mov     rbx, [rsp+28h+arg_0]
0x1800d3099  add     rsp, 20h
0x1800d309d  pop     rdi
0x1800d309e  retn
```
