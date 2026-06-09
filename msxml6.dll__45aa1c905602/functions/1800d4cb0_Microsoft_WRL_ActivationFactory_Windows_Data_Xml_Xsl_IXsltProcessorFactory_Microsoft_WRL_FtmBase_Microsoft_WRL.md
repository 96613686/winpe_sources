# Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800d4cb0`
- end: `0x1800d4d16`
- name: `?GetIids@?$ActivationFactory@UIXsltProcessorFactory@Xsl@Xml@Data@Windows@@VFtmBase@WRL@Microsoft@@VNil@Details@78@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: `HRESULT __fastcall(Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d4d20`

## callees

- `0x1800d4bd0`
- `0x1800d4cb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d4cd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d4cd2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::GetIids(
        Microsoft::WRL::ActivationFactory<Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0> *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *v5; // rcx
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x1800d4cb0  mov     [rsp+arg_0], rbx
0x1800d4cb5  push    rdi
0x1800d4cb6  sub     rsp, 20h
0x1800d4cba  mov     qword ptr [iids], 0
0x1800d4cc1  mov     ecx, 20h ; ' '; cb
0x1800d4cc6  mov     dword ptr [iidCount], 0
0x1800d4ccc  mov     rbx, iids
0x1800d4ccf  mov     rdi, iidCount
0x1800d4cd2  call    cs:__imp_CoTaskMemAlloc
0x1800d4cd9  nop     dword ptr [rax+rax+00h]
0x1800d4cde  mov     iids, rax; iids
0x1800d4ce1  test    rax, rax
0x1800d4ce4  jnz     short loc_1800D4CED
0x1800d4ce6  mov     eax, 8007000Eh
0x1800d4ceb  jmp     short loc_1800D4D0A
0x1800d4ced  lea     iidCount, [rsp+28h+index]; index
0x1800d4cf2  mov     [rsp+28h+index], 0
0x1800d4cfa  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@UIXsltProcessorFactory@Xsl@Xml@Data@Windows@@VFtmBase@23@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Windows::Data::Xml::Xsl::IXsltProcessorFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x1800d4cff  mov     dword ptr [rdi], 2
0x1800d4d05  xor     eax, eax
0x1800d4d07  mov     [rbx], iids
0x1800d4d0a  mov     rbx, [rsp+28h+arg_0]
0x1800d4d0f  add     rsp, 20h
0x1800d4d13  pop     rdi
0x1800d4d14  retn
```
