# CreateReaderOnStream

- ea: `0x180032dc8`
- end: `0x180032f13`
- name: `CreateReaderOnStream`
- size: `331`
- prototype: `__int64 __fastcall(void **ppvObject, IUnknown *pInputStream)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032f1c`

## callees

- `0x18001b388`
- `0x180032dc8`
- `0x180037010`

## import_xrefs

- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x180032e61`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x180032e61`
- `XmlLite!CreateXmlReader` at `0x180032e00`
- `XmlLite!CreateXmlReader` at `0x180032e00`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void **__fastcall CreateReaderOnStream(void **ppvObject, IUnknown *pInputStream)
{
  HRESULT XmlReader; // eax
  int v5; // eax
  HRESULT v6; // eax
  int v7; // eax
  IXmlReaderInput *v8; // rcx
  int pwszBaseUri; // [rsp+20h] [rbp-28h]
  int pwszBaseUria; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  IXmlReaderInput *ppInput; // [rsp+60h] [rbp+18h] BYREF

  *ppvObject = 0;
  XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
  if ( XmlReader < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)(unsigned int)XmlReader,
      pwszBaseUri);
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*ppvObject + 40LL))(*ppvObject, 4);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)(unsigned int)v5,
      pwszBaseUri);
  ppInput = 0;
  v6 = CreateXmlReaderInputWithEncodingName(pInputStream, 0, L"UTF-16", 0, 0, &ppInput);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)(unsigned int)v6,
      pwszBaseUria);
  v7 = (*(__int64 (__fastcall **)(_QWORD, IXmlReaderInput *))(*(_QWORD *)*ppvObject + 24LL))(*ppvObject, ppInput);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)(unsigned int)v7,
      pwszBaseUria);
  v8 = ppInput;
  if ( ppInput )
  {
    ppInput = 0;
    ((void (__fastcall *)(IXmlReaderInput *))v8->lpVtbl->Release)(v8);
  }
  return ppvObject;
}

```

## disassembly

```asm
0x180032dc8  mov     rax, rsp
0x180032dcb  mov     [rax+10h], rbx
0x180032dcf  mov     [rax+8], rcx
0x180032dd3  push    rdi
0x180032dd4  sub     rsp, 40h
0x180032dd8  mov     rdi, rdx
0x180032ddb  mov     rbx, rcx
0x180032dde  mov     dword ptr [rax-18h], 0
0x180032de5  mov     qword ptr [rcx], 0
0x180032dec  mov     dword ptr [rax-18h], 1
0x180032df3  xor     r8d, r8d; pMalloc
0x180032df6  mov     rdx, rcx; ppvObject
0x180032df9  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180032e00  call    cs:__imp_CreateXmlReader
0x180032e06  mov     rcx, [rsp+48h]; this
0x180032e0b  test    eax, eax
0x180032e0d  js      loc_180032ED4
0x180032e13  mov     rcx, [rbx]
0x180032e16  mov     rax, [rcx]
0x180032e19  xor     r8d, r8d
0x180032e1c  lea     edx, [r8+4]
0x180032e20  mov     rax, [rax+28h]
0x180032e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e29  mov     rcx, [rsp+48h]; this
0x180032e2e  test    eax, eax
0x180032e30  js      loc_180032EE9
0x180032e36  mov     [rsp+48h+arg_10], 0
0x180032e3f  lea     rax, [rsp+48h+arg_10]
0x180032e44  mov     [rsp+48h+ppInput], rax; ppInput
0x180032e49  mov     [rsp+48h+pwszBaseUri], 0; int
0x180032e52  xor     r9d, r9d; fEncodingHint
0x180032e55  lea     r8, pwszEncodingName; "UTF-16"
0x180032e5c  xor     edx, edx; pMalloc
0x180032e5e  mov     rcx, rdi; pInputStream
0x180032e61  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x180032e67  mov     rcx, [rsp+48h]; this
0x180032e6c  test    eax, eax
0x180032e6e  js      loc_180032EFE
0x180032e74  mov     rcx, [rbx]
0x180032e77  mov     rax, [rcx]
0x180032e7a  mov     rdx, [rsp+48h+arg_10]
0x180032e7f  mov     rax, [rax+18h]
0x180032e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e88  mov     rcx, [rsp+48h]; this
0x180032e8d  test    eax, eax
0x180032e8f  js      short loc_180032EBF
0x180032e91  mov     rcx, [rsp+48h+arg_10]
0x180032e96  test    rcx, rcx
0x180032e99  jz      short loc_180032EB1
0x180032e9b  mov     [rsp+48h+arg_10], 0
0x180032ea4  mov     rax, [rcx]
0x180032ea7  mov     rax, [rax+10h]
0x180032eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032eb0  nop
0x180032eb1  mov     rax, rbx
0x180032eb4  mov     rbx, [rsp+48h+arg_8]
0x180032eb9  add     rsp, 40h
0x180032ebd  pop     rdi
0x180032ebe  retn
0x180032ebf  mov     r9d, eax; char *
0x180032ec2  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x180032ec9  mov     edx, 19h; void *
0x180032ece  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032ed4  mov     r9d, eax; char *
0x180032ed7  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x180032ede  mov     edx, 14h; void *
0x180032ee3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032ee9  mov     r9d, eax; char *
0x180032eec  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x180032ef3  mov     edx, 15h; void *
0x180032ef8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032efe  mov     r9d, eax; char *
0x180032f01  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x180032f08  mov     edx, 18h; void *
0x180032f0d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
