# Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800f13d0`
- end: `0x1800f143d`
- name: `?GetIids@?$RuntimeClass@U?$InterfaceListHelper@UIXmlNamedNodeMap@Dom@Xml@Data@Windows@@U?$IIterable@PEAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PEAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f1450`
- `0x1800f1460`

## callees

- `0x1800f13d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f13f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f13f2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>::GetIids(
        Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_b3a69eb0_aab0_4b82_a6fa_b1453f7c021b;
  v5[1] = GUID_f1146ffc_8c92_56e8_93f1_711f86722633;
  v5[2] = GUID_139d959e_e7b5_5cb6_a596_4b544478da9b;
  *iidCount = 3;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x1800f13d0  mov     [rsp+arg_0], rbx
0x1800f13d5  push    rdi
0x1800f13d6  sub     rsp, 20h
0x1800f13da  mov     qword ptr [iids], 0
0x1800f13e1  mov     ecx, 30h ; '0'; cb
0x1800f13e6  mov     dword ptr [iidCount], 0
0x1800f13ec  mov     rbx, iids
0x1800f13ef  mov     rdi, iidCount
0x1800f13f2  call    cs:__imp_CoTaskMemAlloc
0x1800f13f8  test    rax, rax
0x1800f13fb  jnz     short loc_1800F1404
0x1800f13fd  mov     eax, 8007000Eh
0x1800f1402  jmp     short loc_1800F1432
0x1800f1404  movups  xmm0, xmmword ptr cs:_GUID_b3a69eb0_aab0_4b82_a6fa_b1453f7c021b.Data1
0x1800f140b  movdqu  xmmword ptr [rax], xmm0
0x1800f140f  movups  xmm1, xmmword ptr cs:_GUID_f1146ffc_8c92_56e8_93f1_711f86722633.Data1
0x1800f1416  movdqu  xmmword ptr [rax+10h], xmm1
0x1800f141b  movups  xmm0, xmmword ptr cs:_GUID_139d959e_e7b5_5cb6_a596_4b544478da9b.Data1
0x1800f1422  movdqu  xmmword ptr [rax+20h], xmm0
0x1800f1427  mov     dword ptr [rdi], 3
0x1800f142d  mov     [rbx], rax
0x1800f1430  xor     eax, eax
0x1800f1432  mov     rbx, [rsp+28h+arg_0]
0x1800f1437  add     rsp, 20h
0x1800f143b  pop     rdi
0x1800f143c  retn
```
