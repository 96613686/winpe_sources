# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800e2a50`
- end: `0x1800e2aaf`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PEAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `HRESULT __fastcall(NodeIterator *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800e2600`
- `0x1800e2a50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e2a72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e2a72`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>::GetIids(
        NodeIterator *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,IWeakReferenceSource,Microsoft::WRL::FtmBase> *v5; // rcx
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x1800e2a50  mov     [rsp+arg_0], rbx
0x1800e2a55  push    rdi
0x1800e2a56  sub     rsp, 20h
0x1800e2a5a  mov     qword ptr [iids], 0
0x1800e2a61  mov     ecx, 20h ; ' '; cb
0x1800e2a66  mov     dword ptr [iidCount], 0
0x1800e2a6c  mov     rbx, iids
0x1800e2a6f  mov     rdi, iidCount
0x1800e2a72  call    cs:__imp_CoTaskMemAlloc
0x1800e2a78  mov     iids, rax; iids
0x1800e2a7b  test    rax, rax
0x1800e2a7e  jnz     short loc_1800E2A87
0x1800e2a80  mov     eax, 8007000Eh
0x1800e2a85  jmp     short loc_1800E2AA4
0x1800e2a87  lea     iidCount, [rsp+28h+index]; index
0x1800e2a8c  mov     [rsp+28h+index], 0
0x1800e2a94  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@PEAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Data::Xml::Dom::IXmlNode *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800e2a99  mov     dword ptr [rdi], 2
0x1800e2a9f  xor     eax, eax
0x1800e2aa1  mov     [rbx], iids
0x1800e2aa4  mov     rbx, [rsp+28h+arg_0]
0x1800e2aa9  add     rsp, 20h
0x1800e2aad  pop     rdi
0x1800e2aae  retn
```
