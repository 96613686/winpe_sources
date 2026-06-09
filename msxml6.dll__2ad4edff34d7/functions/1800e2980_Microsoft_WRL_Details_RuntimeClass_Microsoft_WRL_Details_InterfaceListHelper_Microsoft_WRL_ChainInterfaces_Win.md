# Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800e2980`
- end: `0x1800e2a11`
- name: `?GetIids@?$RuntimeClass@U?$InterfaceListHelper@U?$ChainInterfaces@UIXmlDocument@Dom@Xml@Data@Windows@@UIXmlNode@2345@UIXmlNodeSelector@2345@VNil@Details@WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@@WRL@Microsoft@@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@UIXmlDocumentIO@5678@UIXmlDocumentIO2@5678@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `145`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e2a20`
- `0x1800e2a30`
- `0x1800e2a40`

## callees

- `0x1800e2980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e29a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e29a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>::GetIids(
        Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x60u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494;
  v5[1] = GUID_1c741d59_2122_47d5_a856_83f3d4214875;
  v5[2] = GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b;
  v5[3] = GUID_5cc5b382_e6dd_4991_abef_06d8d2e7bd0c;
  v5[4] = GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637;
  v5[5] = GUID_5d034661_7bd8_4ad5_9ebf_81e6347263b1;
  *iidCount = 6;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x1800e2980  mov     [rsp+arg_0], rbx
0x1800e2985  push    rdi
0x1800e2986  sub     rsp, 20h
0x1800e298a  mov     qword ptr [iids], 0
0x1800e2991  mov     ecx, 60h ; '`'; cb
0x1800e2996  mov     dword ptr [iidCount], 0
0x1800e299c  mov     rbx, iids
0x1800e299f  mov     rdi, iidCount
0x1800e29a2  call    cs:__imp_CoTaskMemAlloc
0x1800e29a8  test    rax, rax
0x1800e29ab  jnz     short loc_1800E29B4
0x1800e29ad  mov     eax, 8007000Eh
0x1800e29b2  jmp     short loc_1800E2A06
0x1800e29b4  movups  xmm0, xmmword ptr cs:_GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494.Data1
0x1800e29bb  movdqu  xmmword ptr [rax], xmm0
0x1800e29bf  movups  xmm1, xmmword ptr cs:_GUID_1c741d59_2122_47d5_a856_83f3d4214875.Data1
0x1800e29c6  movdqu  xmmword ptr [rax+10h], xmm1
0x1800e29cb  movups  xmm0, xmmword ptr cs:_GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b.Data1
0x1800e29d2  movdqu  xmmword ptr [rax+20h], xmm0
0x1800e29d7  movups  xmm1, xmmword ptr cs:_GUID_5cc5b382_e6dd_4991_abef_06d8d2e7bd0c.Data1
0x1800e29de  movdqu  xmmword ptr [rax+30h], xmm1
0x1800e29e3  movups  xmm0, xmmword ptr cs:_GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637.Data1
0x1800e29ea  movdqu  xmmword ptr [rax+40h], xmm0
0x1800e29ef  movups  xmm1, xmmword ptr cs:_GUID_5d034661_7bd8_4ad5_9ebf_81e6347263b1.Data1
0x1800e29f6  movdqu  xmmword ptr [rax+50h], xmm1
0x1800e29fb  mov     dword ptr [rdi], 6
0x1800e2a01  mov     [rbx], rax
0x1800e2a04  xor     eax, eax
0x1800e2a06  mov     rbx, [rsp+28h+arg_0]
0x1800e2a0b  add     rsp, 20h
0x1800e2a0f  pop     rdi
0x1800e2a10  retn
```
