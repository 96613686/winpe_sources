# Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>>,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800f3840`
- end: `0x1800f38b4`
- name: `?GetIids@?$RuntimeClass@U?$InterfaceListHelper@UIXmlNamedNodeMap@Dom@Xml@Data@Windows@@U?$IIterable@PEAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@5@U?$IVectorView@PEAUIXmlNode@Dom@Xml@Data@Windows@@@785@@Details@WRL@Microsoft@@U?$RuntimeClassFlags@$0BAAH@@34@$0A@$00$0A@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `116`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::RuntimeClass<Microsoft::WRL::Details::InterfaceListHelper<Windows::Data::Xml::Dom::IXmlNamedNodeMap,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *> >,Microsoft::WRL::RuntimeClassFlags<4103>,0,1,0> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f38c0`
- `0x1800f38d0`

## callees

- `0x1800f3840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3862`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f3862`

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
0x1800f3840  mov     [rsp+arg_0], rbx
0x1800f3845  push    rdi
0x1800f3846  sub     rsp, 20h
0x1800f384a  mov     qword ptr [iids], 0
0x1800f3851  mov     ecx, 30h ; '0'; cb
0x1800f3856  mov     dword ptr [iidCount], 0
0x1800f385c  mov     rbx, iids
0x1800f385f  mov     rdi, iidCount
0x1800f3862  call    cs:__imp_CoTaskMemAlloc
0x1800f3869  nop     dword ptr [rax+rax+00h]
0x1800f386e  test    rax, rax
0x1800f3871  jnz     short loc_1800F387A
0x1800f3873  mov     eax, 8007000Eh
0x1800f3878  jmp     short loc_1800F38A8
0x1800f387a  movups  xmm0, xmmword ptr cs:_GUID_b3a69eb0_aab0_4b82_a6fa_b1453f7c021b.Data1
0x1800f3881  movdqu  xmmword ptr [rax], xmm0
0x1800f3885  movups  xmm1, xmmword ptr cs:_GUID_f1146ffc_8c92_56e8_93f1_711f86722633.Data1
0x1800f388c  movdqu  xmmword ptr [rax+10h], xmm1
0x1800f3891  movups  xmm0, xmmword ptr cs:_GUID_139d959e_e7b5_5cb6_a596_4b544478da9b.Data1
0x1800f3898  movdqu  xmmword ptr [rax+20h], xmm0
0x1800f389d  mov     dword ptr [rdi], 3
0x1800f38a3  mov     [rbx], rax
0x1800f38a6  xor     eax, eax
0x1800f38a8  mov     rbx, [rsp+28h+arg_0]
0x1800f38ad  add     rsp, 20h
0x1800f38b1  pop     rdi
0x1800f38b2  retn
```
