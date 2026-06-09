# Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800f38e0`
- end: `0x1800f3954`
- name: `?GetIids@?$RuntimeClass@U?$InterfaceListHelper@UIXmlNodeList@Dom@Xml@Data@Windows@@U?$IIterable@PEAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PEAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `116`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f3960`
- `0x1800f3970`

## callees

- `0x1800f38e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3902`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3902`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>::GetIids(
        Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNodeList,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_8c60ad77_83a4_4ec1_9c54_7ba429e13da6;
  v5[1] = GUID_f1146ffc_8c92_56e8_93f1_711f86722633;
  v5[2] = GUID_139d959e_e7b5_5cb6_a596_4b544478da9b;
  *iidCount = 3;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x1800f38e0  mov     [rsp+arg_0], rbx
0x1800f38e5  push    rdi
0x1800f38e6  sub     rsp, 20h
0x1800f38ea  mov     qword ptr [iids], 0
0x1800f38f1  mov     ecx, 30h ; '0'; cb
0x1800f38f6  mov     dword ptr [iidCount], 0
0x1800f38fc  mov     rbx, iids
0x1800f38ff  mov     rdi, iidCount
0x1800f3902  call    cs:__imp_CoTaskMemAlloc
0x1800f3909  nop     dword ptr [rax+rax+00h]
0x1800f390e  test    rax, rax
0x1800f3911  jnz     short loc_1800F391A
0x1800f3913  mov     eax, 8007000Eh
0x1800f3918  jmp     short loc_1800F3948
0x1800f391a  movups  xmm0, xmmword ptr cs:_GUID_8c60ad77_83a4_4ec1_9c54_7ba429e13da6.Data1
0x1800f3921  movdqu  xmmword ptr [rax], xmm0
0x1800f3925  movups  xmm1, xmmword ptr cs:_GUID_f1146ffc_8c92_56e8_93f1_711f86722633.Data1
0x1800f392c  movdqu  xmmword ptr [rax+10h], xmm1
0x1800f3931  movups  xmm0, xmmword ptr cs:_GUID_139d959e_e7b5_5cb6_a596_4b544478da9b.Data1
0x1800f3938  movdqu  xmmword ptr [rax+20h], xmm0
0x1800f393d  mov     dword ptr [rdi], 3
0x1800f3943  mov     [rbx], rax
0x1800f3946  xor     eax, eax
0x1800f3948  mov     rbx, [rsp+28h+arg_0]
0x1800f394d  add     rsp, 20h
0x1800f3951  pop     rdi
0x1800f3952  retn
```
