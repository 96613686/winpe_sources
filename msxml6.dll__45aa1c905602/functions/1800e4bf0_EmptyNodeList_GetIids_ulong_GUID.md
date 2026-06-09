# EmptyNodeList::GetIids(ulong *,_GUID * *)

- ea: `0x1800e4bf0`
- end: `0x1800e4c6d`
- name: `?GetIids@EmptyNodeList@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `125`
- prototype: `HRESULT __fastcall(EmptyNodeList *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e4c80`
- `0x1800e4c90`

## callees

- `0x1800e4780`
- `0x1800e4bf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e4c12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e4c12`

## pseudocode

```c
__int64 __fastcall EmptyNodeList::GetIids(EmptyNodeList *this, unsigned int *iidCount, _GUID **iids)
{
  _GUID *v5; // rax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase> *v6; // rcx
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  index = 2;
  *v5 = GUID_8c60ad77_83a4_4ec1_9c54_7ba429e13da6;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &index,
    v5);
  *iidCount = 4;
  result = 0;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x1800e4bf0  mov     [rsp+arg_0], rbx
0x1800e4bf5  push    rdi
0x1800e4bf6  sub     rsp, 20h
0x1800e4bfa  mov     qword ptr [iids], 0
0x1800e4c01  mov     ecx, 40h ; '@'; cb
0x1800e4c06  mov     dword ptr [iidCount], 0
0x1800e4c0c  mov     rbx, iids
0x1800e4c0f  mov     rdi, iidCount
0x1800e4c12  call    cs:__imp_CoTaskMemAlloc
0x1800e4c19  nop     dword ptr [rax+rax+00h]
0x1800e4c1e  mov     iids, rax; iids
0x1800e4c21  test    rax, rax
0x1800e4c24  jnz     short loc_1800E4C2D
0x1800e4c26  mov     eax, 8007000Eh
0x1800e4c2b  jmp     short loc_1800E4C61
0x1800e4c2d  movups  xmm0, xmmword ptr cs:_GUID_8c60ad77_83a4_4ec1_9c54_7ba429e13da6.Data1
0x1800e4c34  lea     iidCount, [rsp+28h+index]; index
0x1800e4c39  mov     [rsp+28h+index], 2
0x1800e4c41  movdqu  xmmword ptr [rax], xmm0
0x1800e4c45  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800e4c4c  movdqu  xmmword ptr [rax+10h], xmm1
0x1800e4c51  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IIterable@PEAUIXmlNode@Dom@Xml@Data@Windows@@@Collections@Foundation@Windows@@U?$IVectorView@PEAUIXmlNode@Dom@Xml@Data@Windows@@@567@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Data::Xml::Dom::IXmlNode *>,Windows::Foundation::Collections::IVectorView<Windows::Data::Xml::Dom::IXmlNode *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800e4c56  mov     dword ptr [rdi], 4
0x1800e4c5c  xor     eax, eax
0x1800e4c5e  mov     [rbx], iids
0x1800e4c61  mov     rbx, [rsp+28h+arg_0]
0x1800e4c66  add     rsp, 20h
0x1800e4c6a  pop     rdi
0x1800e4c6b  retn
```
