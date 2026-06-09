# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800d3220`
- end: `0x1800d328a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIXsltProcessor@Xsl@Xml@Data@Windows@@UIXsltProcessor2@5678@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `HRESULT __fastcall(XsltProcessorImpl *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d3290`

## callees

- `0x1800d2ef4`
- `0x1800d3220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d3242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d3242`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Data::Xml::Xsl::IXsltProcessor,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>::GetIids(
        XsltProcessorImpl *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase> *v6; // rcx
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  index = 1;
  *v5 = GUID_7b64703f_550c_48c6_a90f_93a5b964518f;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &index,
    v5);
  *iidCount = 3;
  result = 0;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x1800d3220  mov     [rsp+arg_0], rbx
0x1800d3225  push    rdi
0x1800d3226  sub     rsp, 20h
0x1800d322a  mov     qword ptr [iids], 0
0x1800d3231  mov     ecx, 30h ; '0'; cb
0x1800d3236  mov     dword ptr [iidCount], 0
0x1800d323c  mov     rbx, iids
0x1800d323f  mov     rdi, iidCount
0x1800d3242  call    cs:__imp_CoTaskMemAlloc
0x1800d3248  mov     iids, rax; iids
0x1800d324b  test    rax, rax
0x1800d324e  jnz     short loc_1800D3257
0x1800d3250  mov     eax, 8007000Eh
0x1800d3255  jmp     short loc_1800D327F
0x1800d3257  movups  xmm0, xmmword ptr cs:_GUID_7b64703f_550c_48c6_a90f_93a5b964518f.Data1
0x1800d325e  lea     iidCount, [rsp+28h+index]; index
0x1800d3263  mov     [rsp+28h+index], 1
0x1800d326b  movdqu  xmmword ptr [rax], xmm0
0x1800d326f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIXsltProcessor2@Xsl@Xml@Data@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Data::Xml::Xsl::IXsltProcessor2,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800d3274  mov     dword ptr [rdi], 3
0x1800d327a  xor     eax, eax
0x1800d327c  mov     [rbx], iids
0x1800d327f  mov     rbx, [rsp+28h+arg_0]
0x1800d3284  add     rsp, 20h
0x1800d3288  pop     rdi
0x1800d3289  retn
```
