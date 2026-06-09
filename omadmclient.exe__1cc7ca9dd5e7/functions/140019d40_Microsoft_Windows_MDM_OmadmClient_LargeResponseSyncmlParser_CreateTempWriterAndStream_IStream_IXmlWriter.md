# Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateTempWriterAndStream(IStream * *,IXmlWriter * *)

- ea: `0x140019d40`
- end: `0x140019f71`
- name: `?CreateTempWriterAndStream@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@KAJPEAPEAUIStream@@PEAPEAUIXmlWriter@@@Z`
- size: `561`
- prototype: `static int(struct IStream **, struct IXmlWriter **)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001adb8`
- `0x14001b308`
- `0x14001be2c`
- `0x14001ccf8`

## callees

- `0x14000b0f4`
- `0x140019d40`
- `0x140069010`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x140019e1a`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x140019e1a`
- `XmlLite!CreateXmlWriter` at `0x140019d97`
- `XmlLite!CreateXmlWriter` at `0x140019d97`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x140019d76`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x140019d76`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateTempWriterAndStream(
        struct IStream **a1,
        struct IXmlWriter **a2)
{
  IStream *v4; // rbx
  HRESULT v5; // eax
  unsigned int v6; // edi
  HRESULT v8; // eax
  int v9; // eax
  struct IXmlWriter *v10; // rax
  void *v11; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  void *ppvObject; // [rsp+50h] [rbp+30h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+58h] [rbp+38h] BYREF
  IStream *v16; // [rsp+60h] [rbp+40h]

  *a1 = 0;
  *a2 = 0;
  ppvObject = 0;
  ppOutput = 0;
  v4 = SHCreateMemStream(0, 0);
  v16 = v4;
  v5 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v5,
      savedregs);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    if ( v4 )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v4 + 16LL))(v4);
    return v6;
  }
  v8 = CreateXmlWriterOutputWithEncodingName((IUnknown *)v4, 0, L"UTF-8", &ppOutput);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v8,
      savedregs);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    if ( v4 )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v4 + 16LL))(v4);
    return v6;
  }
  v9 = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppOutput);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v9,
      savedregs);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    if ( v4 )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v4 + 16LL))(v4);
    return v6;
  }
  (*(void (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4, 1);
  v16 = 0;
  *a1 = v4;
  v10 = (struct IXmlWriter *)ppvObject;
  v11 = 0;
  ppvObject = 0;
  *a2 = v10;
  if ( ppOutput )
  {
    ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    v11 = ppvObject;
  }
  if ( v11 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  return 0;
}

```

## disassembly

```asm
0x140019d40  push    rbp
0x140019d42  push    rbx
0x140019d43  push    rsi
0x140019d44  push    rdi
0x140019d45  push    r14; int
0x140019d47  mov     rbp, rsp
0x140019d4a  sub     rsp, 20h
0x140019d4e  mov     rsi, rdx
0x140019d51  mov     r14, rcx
0x140019d54  mov     qword ptr [rcx], 0
0x140019d5b  mov     qword ptr [rdx], 0
0x140019d62  mov     [rbp+ppvObject], 0
0x140019d6a  mov     [rbp+ppOutput], 0
0x140019d72  xor     edx, edx; cbInit
0x140019d74  xor     ecx, ecx; pInit
0x140019d76  call    cs:__imp_SHCreateMemStream
0x140019d7d  nop     dword ptr [rax+rax+00h]
0x140019d82  mov     rbx, rax
0x140019d85  mov     [rbp+arg_10], rax
0x140019d89  xor     r8d, r8d; pMalloc
0x140019d8c  lea     rdx, [rbp+ppvObject]; ppvObject
0x140019d90  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x140019d97  call    cs:__imp_CreateXmlWriter
0x140019d9e  nop     dword ptr [rax+rax+00h]
0x140019da3  mov     edi, eax
0x140019da5  test    eax, eax
0x140019da7  jns     short loc_140019E0A
0x140019da9  mov     rcx, [rbp+28h]; this
0x140019dad  mov     r9d, eax; char *
0x140019db0  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140019db7  mov     edx, 1D5h; void *
0x140019dbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019dc1  nop
0x140019dc2  mov     rcx, [rbp+ppOutput]
0x140019dc6  test    rcx, rcx
0x140019dc9  jz      short loc_140019DD8
0x140019dcb  mov     rax, [rcx]
0x140019dce  mov     rax, [rax+10h]
0x140019dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019dd7  nop
0x140019dd8  mov     rcx, [rbp+ppvObject]
0x140019ddc  test    rcx, rcx
0x140019ddf  jz      short loc_140019DEE
0x140019de1  mov     rax, [rcx]
0x140019de4  mov     rax, [rax+10h]
0x140019de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019ded  nop
0x140019dee  test    rbx, rbx
0x140019df1  jz      short loc_140019E03
0x140019df3  mov     rax, [rbx]
0x140019df6  mov     rcx, rbx
0x140019df9  mov     rax, [rax+10h]
0x140019dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019e02  nop
0x140019e03  mov     eax, edi
0x140019e05  jmp     loc_140019F65
0x140019e0a  lea     r9, [rbp+ppOutput]; ppOutput
0x140019e0e  lea     r8, aUtf8_0; "UTF-8"
0x140019e15  xor     edx, edx; pMalloc
0x140019e17  mov     rcx, rbx; pOutputStream
0x140019e1a  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x140019e21  nop     dword ptr [rax+rax+00h]
0x140019e26  mov     edi, eax
0x140019e28  test    eax, eax
0x140019e2a  jns     short loc_140019E8B
0x140019e2c  mov     rcx, [rbp+28h]; this
0x140019e30  mov     r9d, eax; char *
0x140019e33  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140019e3a  mov     edx, 1DCh; void *
0x140019e3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019e44  nop
0x140019e45  mov     rcx, [rbp+ppOutput]
0x140019e49  test    rcx, rcx
0x140019e4c  jz      short loc_140019E5B
0x140019e4e  mov     rax, [rcx]
0x140019e51  mov     rax, [rax+10h]
0x140019e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019e5a  nop
0x140019e5b  mov     rcx, [rbp+ppvObject]
0x140019e5f  test    rcx, rcx
0x140019e62  jz      short loc_140019E71
0x140019e64  mov     rax, [rcx]
0x140019e67  mov     rax, [rax+10h]
0x140019e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019e70  nop
0x140019e71  test    rbx, rbx
0x140019e74  jz      short loc_140019E86
0x140019e76  mov     rax, [rbx]
0x140019e79  mov     rcx, rbx
0x140019e7c  mov     rax, [rax+10h]
0x140019e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019e85  nop
0x140019e86  jmp     loc_140019E03
0x140019e8b  mov     rcx, [rbp+ppvObject]
0x140019e8f  mov     rax, [rcx]
0x140019e92  mov     rdx, [rbp+ppOutput]
0x140019e96  mov     rax, [rax+18h]
0x140019e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019e9f  mov     edi, eax
0x140019ea1  test    eax, eax
0x140019ea3  jns     short loc_140019F04
0x140019ea5  mov     rcx, [rbp+28h]; this
0x140019ea9  mov     r9d, eax; char *
0x140019eac  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140019eb3  mov     edx, 1DFh; void *
0x140019eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019ebd  nop
0x140019ebe  mov     rcx, [rbp+ppOutput]
0x140019ec2  test    rcx, rcx
0x140019ec5  jz      short loc_140019ED4
0x140019ec7  mov     rax, [rcx]
0x140019eca  mov     rax, [rax+10h]
0x140019ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019ed3  nop
0x140019ed4  mov     rcx, [rbp+ppvObject]
0x140019ed8  test    rcx, rcx
0x140019edb  jz      short loc_140019EEA
0x140019edd  mov     rax, [rcx]
0x140019ee0  mov     rax, [rax+10h]
0x140019ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019ee9  nop
0x140019eea  test    rbx, rbx
0x140019eed  jz      short loc_140019EFF
0x140019eef  mov     rax, [rbx]
0x140019ef2  mov     rcx, rbx
0x140019ef5  mov     rax, [rax+10h]
0x140019ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019efe  nop
0x140019eff  jmp     loc_140019E03
0x140019f04  mov     rcx, [rbp+ppvObject]
0x140019f08  mov     rax, [rcx]
0x140019f0b  mov     edx, 4
0x140019f10  lea     r8d, [rdx-3]
0x140019f14  mov     rax, [rax+28h]
0x140019f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019f1d  mov     [rbp+arg_10], 0
0x140019f25  mov     [r14], rbx
0x140019f28  mov     rax, [rbp+ppvObject]
0x140019f2c  xor     ecx, ecx
0x140019f2e  mov     [rbp+ppvObject], rcx
0x140019f32  mov     [rsi], rax
0x140019f35  mov     rdx, [rbp+ppOutput]
0x140019f39  test    rdx, rdx
0x140019f3c  jz      short loc_140019F51
0x140019f3e  mov     rax, [rdx]
0x140019f41  mov     rcx, rdx
0x140019f44  mov     rax, [rax+10h]
0x140019f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019f4d  mov     rcx, [rbp+ppvObject]
0x140019f51  test    rcx, rcx
0x140019f54  jz      short loc_140019F63
0x140019f56  mov     rax, [rcx]
0x140019f59  mov     rax, [rax+10h]
0x140019f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019f62  nop
0x140019f63  xor     eax, eax
0x140019f65  add     rsp, 20h
0x140019f69  pop     r14
0x140019f6b  pop     rdi
0x140019f6c  pop     rsi
0x140019f6d  pop     rbx
0x140019f6e  pop     rbp
0x140019f6f  retn
```
