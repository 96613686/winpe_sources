# Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *,ulong *,_GUID * *)

- ea: `0x1800e35ec`
- end: `0x1800e3684`
- name: `??$GetImplementedIIDS@V?$RuntimeClass@U?$InterfaceListHelper@U?$ChainInterfaces@UIXmlDocument@Dom@Xml@Data@Windows@@UIXmlNode@2345@UIXmlNodeSelector@2345@VNil@Details@WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@@WRL@Microsoft@@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@UIXmlDocumentIO@5678@UIXmlDocumentIO2@5678@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$06@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClass@U?$InterfaceListHelper@U?$ChainInterfaces@UIXmlDocument@Dom@Xml@Data@Windows@@UIXmlNode@2345@UIXmlNodeSelector@2345@VNil@Details@WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@V89WRL@Microsoft@@@WRL@Microsoft@@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@UIXmlDocumentIO@5678@UIXmlDocumentIO2@5678@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@123@PEAKPEAPEAU_GUID@@@Z`
- size: `152`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount, unsigned int *iids, _GUID **implements)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e4b40`

## callees

- `0x1800e35ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e360e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e360e`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<7>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>>(
        Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Microsoft::WRL::ChainInterfaces<Windows::Data::Xml::Dom::IXmlDocument,Windows::Data::Xml::Dom::IXmlNode,Windows::Data::Xml::Dom::IXmlNodeSelector,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Windows::Data::Xml::Dom::IXmlNodeSerializer,Windows::Data::Xml::Dom::IXmlDocumentIO,Windows::Data::Xml::Dom::IXmlDocumentIO2>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *iidCount,
        unsigned int *iids,
        _GUID **implements)
{
  _GUID *v5; // rax

  *implements = 0;
  *iids = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x60u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494;
  v5[1] = GUID_1c741d59_2122_47d5_a856_83f3d4214875;
  v5[2] = GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b;
  v5[3] = GUID_5cc5b382_e6dd_4991_abef_06d8d2e7bd0c;
  v5[4] = GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637;
  v5[5] = GUID_5d034661_7bd8_4ad5_9ebf_81e6347263b1;
  *iids = 6;
  *implements = v5;
  return 0;
}

```

## disassembly

```asm
0x1800e35ec  mov     [rsp+arg_0], rbx
0x1800e35f1  push    rdi
0x1800e35f2  sub     rsp, 20h
0x1800e35f6  mov     qword ptr [iids], 0
0x1800e35fd  mov     ecx, 60h ; '`'; cb
0x1800e3602  mov     dword ptr [iidCount], 0
0x1800e3608  mov     rbx, iids
0x1800e360b  mov     rdi, iidCount
0x1800e360e  call    cs:__imp_CoTaskMemAlloc
0x1800e3615  nop     dword ptr [rax+rax+00h]
0x1800e361a  test    rax, rax
0x1800e361d  jnz     short loc_1800E3626
0x1800e361f  mov     eax, 8007000Eh
0x1800e3624  jmp     short loc_1800E3678
0x1800e3626  movups  xmm0, xmmword ptr cs:_GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494.Data1
0x1800e362d  movdqu  xmmword ptr [rax], xmm0
0x1800e3631  movups  xmm1, xmmword ptr cs:_GUID_1c741d59_2122_47d5_a856_83f3d4214875.Data1
0x1800e3638  movdqu  xmmword ptr [rax+10h], xmm1
0x1800e363d  movups  xmm0, xmmword ptr cs:_GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b.Data1
0x1800e3644  movdqu  xmmword ptr [rax+20h], xmm0
0x1800e3649  movups  xmm1, xmmword ptr cs:_GUID_5cc5b382_e6dd_4991_abef_06d8d2e7bd0c.Data1
0x1800e3650  movdqu  xmmword ptr [rax+30h], xmm1
0x1800e3655  movups  xmm0, xmmword ptr cs:_GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637.Data1
0x1800e365c  movdqu  xmmword ptr [rax+40h], xmm0
0x1800e3661  movups  xmm1, xmmword ptr cs:_GUID_5d034661_7bd8_4ad5_9ebf_81e6347263b1.Data1
0x1800e3668  movdqu  xmmword ptr [rax+50h], xmm1
0x1800e366d  mov     dword ptr [rdi], 6
0x1800e3673  mov     [rbx], rax
0x1800e3676  xor     eax, eax
0x1800e3678  mov     rbx, [rsp+28h+arg_0]
0x1800e367d  add     rsp, 20h
0x1800e3681  pop     rdi
0x1800e3682  retn
```
