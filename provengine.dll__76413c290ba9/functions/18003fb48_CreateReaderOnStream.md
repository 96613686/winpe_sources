# CreateReaderOnStream

- ea: `0x18003fb48`
- end: `0x18003fc93`
- name: `CreateReaderOnStream`
- size: `331`
- prototype: `__int64 __fastcall(void **ppvObject, IUnknown *pInputStream)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003fdc8`

## callees

- `0x180021cf4`
- `0x18003fb48`
- `0x180047010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18003fb80`
- `XmlLite!CreateXmlReader` at `0x18003fb80`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18003fbe1`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18003fbe1`

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
0x18003fb48  mov     rax, rsp
0x18003fb4b  mov     [rax+10h], rbx
0x18003fb4f  mov     [rax+8], rcx
0x18003fb53  push    rdi
0x18003fb54  sub     rsp, 40h
0x18003fb58  mov     rdi, rdx
0x18003fb5b  mov     rbx, rcx
0x18003fb5e  mov     dword ptr [rax-18h], 0
0x18003fb65  mov     qword ptr [rcx], 0
0x18003fb6c  mov     dword ptr [rax-18h], 1
0x18003fb73  xor     r8d, r8d; pMalloc
0x18003fb76  mov     rdx, rcx; ppvObject
0x18003fb79  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18003fb80  call    cs:__imp_CreateXmlReader
0x18003fb86  mov     rcx, [rsp+48h]; this
0x18003fb8b  test    eax, eax
0x18003fb8d  js      loc_18003FC54
0x18003fb93  mov     rcx, [rbx]
0x18003fb96  mov     rax, [rcx]
0x18003fb99  xor     r8d, r8d
0x18003fb9c  lea     edx, [r8+4]
0x18003fba0  mov     rax, [rax+28h]
0x18003fba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fba9  mov     rcx, [rsp+48h]; this
0x18003fbae  test    eax, eax
0x18003fbb0  js      loc_18003FC69
0x18003fbb6  mov     [rsp+48h+arg_10], 0
0x18003fbbf  lea     rax, [rsp+48h+arg_10]
0x18003fbc4  mov     [rsp+48h+ppInput], rax; ppInput
0x18003fbc9  mov     [rsp+48h+pwszBaseUri], 0; int
0x18003fbd2  xor     r9d, r9d; fEncodingHint
0x18003fbd5  lea     r8, pwszEncodingName; "UTF-16"
0x18003fbdc  xor     edx, edx; pMalloc
0x18003fbde  mov     rcx, rdi; pInputStream
0x18003fbe1  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x18003fbe7  mov     rcx, [rsp+48h]; this
0x18003fbec  test    eax, eax
0x18003fbee  js      loc_18003FC7E
0x18003fbf4  mov     rcx, [rbx]
0x18003fbf7  mov     rax, [rcx]
0x18003fbfa  mov     rdx, [rsp+48h+arg_10]
0x18003fbff  mov     rax, [rax+18h]
0x18003fc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc08  mov     rcx, [rsp+48h]; this
0x18003fc0d  test    eax, eax
0x18003fc0f  js      short loc_18003FC3F
0x18003fc11  mov     rcx, [rsp+48h+arg_10]
0x18003fc16  test    rcx, rcx
0x18003fc19  jz      short loc_18003FC31
0x18003fc1b  mov     [rsp+48h+arg_10], 0
0x18003fc24  mov     rax, [rcx]
0x18003fc27  mov     rax, [rax+10h]
0x18003fc2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc30  nop
0x18003fc31  mov     rax, rbx
0x18003fc34  mov     rbx, [rsp+48h+arg_8]
0x18003fc39  add     rsp, 40h
0x18003fc3d  pop     rdi
0x18003fc3e  retn
0x18003fc3f  mov     r9d, eax; char *
0x18003fc42  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18003fc49  mov     edx, 19h; void *
0x18003fc4e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fc54  mov     r9d, eax; char *
0x18003fc57  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18003fc5e  mov     edx, 14h; void *
0x18003fc63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fc69  mov     r9d, eax; char *
0x18003fc6c  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18003fc73  mov     edx, 15h; void *
0x18003fc78  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fc7e  mov     r9d, eax; char *
0x18003fc81  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18003fc88  mov     edx, 18h; void *
0x18003fc8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
