# Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800d4c30`
- end: `0x1800d4c96`
- name: `?GetIids@?$ActivationFactory@UIXmlDocumentStatics@Dom@Xml@Data@Windows@@VFtmBase@WRL@Microsoft@@VNil@Details@78@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: `HRESULT __fastcall(Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d4ca0`

## callees

- `0x1800d4bac`
- `0x1800d4c30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d4c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d4c52`

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
0x1800d4c30  mov     [rsp+arg_0], rbx
0x1800d4c35  push    rdi
0x1800d4c36  sub     rsp, 20h
0x1800d4c3a  mov     qword ptr [iids], 0
0x1800d4c41  mov     ecx, 20h ; ' '; cb
0x1800d4c46  mov     dword ptr [iidCount], 0
0x1800d4c4c  mov     rbx, iids
0x1800d4c4f  mov     rdi, iidCount
0x1800d4c52  call    cs:__imp_CoTaskMemAlloc
0x1800d4c59  nop     dword ptr [rax+rax+00h]
0x1800d4c5e  mov     iids, rax; iids
0x1800d4c61  test    rax, rax
0x1800d4c64  jnz     short loc_1800D4C6D
0x1800d4c66  mov     eax, 8007000Eh
0x1800d4c6b  jmp     short loc_1800D4C8A
0x1800d4c6d  lea     iidCount, [rsp+28h+index]; index
0x1800d4c72  mov     [rsp+28h+index], 0
0x1800d4c7a  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@UIXmlDocumentStatics@Dom@Xml@Data@Windows@@VFtmBase@23@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Dom::IXmlDocumentStatics,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x1800d4c7f  mov     dword ptr [rdi], 2
0x1800d4c85  xor     eax, eax
0x1800d4c87  mov     [rbx], iids
0x1800d4c8a  mov     rbx, [rsp+28h+arg_0]
0x1800d4c8f  add     rsp, 20h
0x1800d4c93  pop     rdi
0x1800d4c94  retn
```
