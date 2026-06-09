# XmlFilter::FInit(IStream *,IStream *,int,int)

- ea: `0x18006ce2c`
- end: `0x18006d029`
- name: `?FInit@XmlFilter@@QEAA_NPEAUIStream@@0HH@Z`
- size: `509`
- prototype: `bool(XmlFilter *__hidden this, struct IStream *, struct IStream *, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034c74`
- `0x180056138`

## callees

- `0x18004aa14`
- `0x18006ce2c`
- `0x18006da38`
- `0x180085010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18006ce7b`
- `XmlLite!CreateXmlReader` at `0x18006ce7b`
- `XmlLite!CreateXmlReaderInputWithEncodingCodePage` at `0x18006cedb`
- `XmlLite!CreateXmlReaderInputWithEncodingCodePage` at `0x18006cedb`
- `XmlLite!CreateXmlWriter` at `0x18006cf6f`
- `XmlLite!CreateXmlWriter` at `0x18006cf6f`
- `XmlLite!CreateXmlWriterOutputWithEncodingCodePage` at `0x18006cfbd`
- `XmlLite!CreateXmlWriterOutputWithEncodingCodePage` at `0x18006cfbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall XmlFilter::FInit(XmlFilter *this, IUnknown *a2, IUnknown *a3, UINT a4, UINT nEncodingCodePage)
{
  void *v10; // rdi
  _QWORD *v11; // rsi
  int v12; // eax
  _QWORD *v13; // rdi
  void *v14; // r14
  UINT v15; // r8d
  IXmlReaderInput *v16; // rdx
  void *ppvObject; // [rsp+30h] [rbp-18h] BYREF
  void *v18; // [rsp+38h] [rbp-10h] BYREF
  IXmlReaderInput *ppOutput; // [rsp+90h] [rbp+48h] BYREF

  if ( *(_OWORD *)this != 0 )
  {
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
  }
  ppvObject = 0;
  if ( CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0) )
    return 0;
  v10 = ppvObject;
  if ( ppvObject == *(void **)this )
  {
    v10 = *(void **)this;
  }
  else
  {
    std::unique_ptr<IXmlReader,ComDeleter>::_Delete(this);
    *(_QWORD *)this = v10;
  }
  if ( a4 == 65001 || !a4 )
  {
    v12 = (*(__int64 (__fastcall **)(void *, IUnknown *))(*(_QWORD *)v10 + 24LL))(v10, a2);
    v11 = (_QWORD *)((char *)this + 16);
  }
  else
  {
    ppOutput = 0;
    *((_DWORD *)this + 34) = a4;
    v11 = (_QWORD *)((char *)this + 16);
    if ( CreateXmlReaderInputWithEncodingCodePage(a2, 0, a4, 0, 0, &ppOutput) )
    {
      *(_QWORD *)this = 0;
      *((_QWORD *)this + 1) = 0;
LABEL_12:
      *v11 = 0;
      *((_QWORD *)this + 3) = 0;
      return 0;
    }
    std::unique_ptr<IUnknown,ComDeleter>::reset((char *)this + 16, ppOutput);
    v12 = (*(__int64 (__fastcall **)(_QWORD, IXmlReaderInput *))(**(_QWORD **)this + 24LL))(*(_QWORD *)this, ppOutput);
  }
  if ( !v12 )
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)this + 40LL))(*(_QWORD *)this, 4, 1);
  v13 = (_QWORD *)((char *)this + 8);
  if ( v12 || (v18 = 0, CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &v18, 0)) )
  {
    *(_QWORD *)this = 0;
    *v13 = 0;
    goto LABEL_12;
  }
  v14 = v18;
  if ( v18 != (void *)*v13 )
  {
    std::unique_ptr<IXmlReader,ComDeleter>::_Delete((char *)this + 8);
    *v13 = v14;
  }
  ((void (__fastcall *)(IUnknown *))a3->lpVtbl->AddRef)(a3);
  v15 = nEncodingCodePage;
  if ( nEncodingCodePage )
  {
    ppOutput = 0;
    *((_DWORD *)this + 35) = nEncodingCodePage;
    if ( CreateXmlWriterOutputWithEncodingCodePage(a3, 0, v15, &ppOutput) )
    {
LABEL_24:
      *(_QWORD *)this = 0;
      *v13 = 0;
      *v11 = 0;
      *((_QWORD *)this + 3) = 0;
      return 0;
    }
    std::unique_ptr<IUnknown,ComDeleter>::reset((char *)this + 24, ppOutput);
    v16 = ppOutput;
  }
  else
  {
    v16 = a3;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, IXmlReaderInput *))(*(_QWORD *)*v13 + 24LL))(*v13, v16) )
    goto LABEL_24;
  (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v13 + 40LL))(*v13, 1, 1);
  return 1;
}

```

## disassembly

```asm
0x18006ce2c  push    rbp
0x18006ce2e  push    rbx
0x18006ce2f  push    rsi
0x18006ce30  push    rdi
0x18006ce31  push    r12
0x18006ce33  push    r13
0x18006ce35  push    r14
0x18006ce37  push    r15
0x18006ce39  mov     rbp, rsp
0x18006ce3c  sub     rsp, 48h
0x18006ce40  mov     r14d, r9d
0x18006ce43  mov     r15, r8
0x18006ce46  mov     r12, rdx
0x18006ce49  mov     rbx, rcx
0x18006ce4c  xor     r13d, r13d
0x18006ce4f  cmp     [rcx], r13
0x18006ce52  jnz     short loc_18006CE5A
0x18006ce54  cmp     [rcx+8], r13
0x18006ce58  jz      short loc_18006CE69
0x18006ce5a  mov     [rcx], r13
0x18006ce5d  mov     [rcx+8], r13
0x18006ce61  mov     [rcx+10h], r13
0x18006ce65  mov     [rcx+18h], r13
0x18006ce69  mov     [rbp+ppvObject], r13
0x18006ce6d  xor     r8d, r8d; pMalloc
0x18006ce70  lea     rdx, [rbp+ppvObject]; ppvObject
0x18006ce74  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18006ce7b  call    cs:__imp_CreateXmlReader
0x18006ce81  test    eax, eax
0x18006ce83  jz      short loc_18006CE8C
0x18006ce85  xor     al, al
0x18006ce87  jmp     loc_18006D018
0x18006ce8c  mov     rdi, [rbp+ppvObject]
0x18006ce90  cmp     rdi, [rbx]
0x18006ce93  jz      short loc_18006CEA2
0x18006ce95  mov     rcx, rbx
0x18006ce98  call    ?_Delete@?$unique_ptr@UIXmlReader@@UComDeleter@@@std@@AEAAXXZ; std::unique_ptr<IXmlReader,ComDeleter>::_Delete(void)
0x18006ce9d  mov     [rbx], rdi
0x18006cea0  jmp     short loc_18006CEA5
0x18006cea2  mov     rdi, [rbx]
0x18006cea5  cmp     r14d, 0FDE9h
0x18006ceac  jz      short loc_18006CF16
0x18006ceae  test    r14d, r14d
0x18006ceb1  jz      short loc_18006CF16
0x18006ceb3  mov     [rbp+ppOutput], r13
0x18006ceb7  mov     [rbx+88h], r14d
0x18006cebe  lea     rsi, [rbx+10h]
0x18006cec2  lea     rax, [rbp+ppOutput]
0x18006cec6  mov     [rsp+48h+ppInput], rax; ppInput
0x18006cecb  mov     [rsp+48h+pwszBaseUri], r13; pwszBaseUri
0x18006ced0  xor     r9d, r9d; fEncodingHint
0x18006ced3  mov     r8d, r14d; nEncodingCodePage
0x18006ced6  xor     edx, edx; pMalloc
0x18006ced8  mov     rcx, r12; pInputStream
0x18006cedb  call    cs:__imp_CreateXmlReaderInputWithEncodingCodePage
0x18006cee1  test    eax, eax
0x18006cee3  jz      short loc_18006CEF5
0x18006cee5  mov     [rbx], r13
0x18006cee8  mov     [rbx+8], r13
0x18006ceec  mov     [rsi], r13
0x18006ceef  mov     [rbx+18h], r13
0x18006cef3  jmp     short loc_18006CE85
0x18006cef5  mov     rdx, [rbp+ppOutput]
0x18006cef9  mov     rcx, rsi
0x18006cefc  call    ?reset@?$unique_ptr@UIUnknown@@UComDeleter@@@std@@QEAAXPEAUIUnknown@@@Z; std::unique_ptr<IUnknown,ComDeleter>::reset(IUnknown *)
0x18006cf01  mov     rcx, [rbx]
0x18006cf04  mov     rax, [rcx]
0x18006cf07  mov     rdx, [rbp+ppOutput]
0x18006cf0b  mov     rax, [rax+18h]
0x18006cf0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf14  jmp     short loc_18006CF2C
0x18006cf16  mov     rax, [rdi]
0x18006cf19  mov     rdx, r12
0x18006cf1c  mov     rcx, rdi
0x18006cf1f  mov     rax, [rax+18h]
0x18006cf23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf28  lea     rsi, [rbx+10h]
0x18006cf2c  mov     r12d, 1
0x18006cf32  test    eax, eax
0x18006cf34  jnz     short loc_18006CF4D
0x18006cf36  mov     rcx, [rbx]
0x18006cf39  mov     rax, [rcx]
0x18006cf3c  mov     r8d, r12d
0x18006cf3f  lea     edx, [r12+3]
0x18006cf44  mov     rax, [rax+28h]
0x18006cf48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf4d  lea     rdi, [rbx+8]
0x18006cf51  test    eax, eax
0x18006cf53  jz      short loc_18006CF5D
0x18006cf55  mov     [rbx], r13
0x18006cf58  mov     [rdi], r13
0x18006cf5b  jmp     short loc_18006CEEC
0x18006cf5d  mov     [rbp+var_10], r13
0x18006cf61  xor     r8d, r8d; pMalloc
0x18006cf64  lea     rdx, [rbp+var_10]; ppvObject
0x18006cf68  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18006cf6f  call    cs:__imp_CreateXmlWriter
0x18006cf75  test    eax, eax
0x18006cf77  jnz     short loc_18006CF55
0x18006cf79  mov     r14, [rbp+var_10]
0x18006cf7d  cmp     r14, [rdi]
0x18006cf80  jz      short loc_18006CF8D
0x18006cf82  mov     rcx, rdi
0x18006cf85  call    ?_Delete@?$unique_ptr@UIXmlReader@@UComDeleter@@@std@@AEAAXXZ; std::unique_ptr<IXmlReader,ComDeleter>::_Delete(void)
0x18006cf8a  mov     [rdi], r14
0x18006cf8d  mov     rax, [r15]
0x18006cf90  mov     rcx, r15
0x18006cf93  mov     rax, [rax+8]
0x18006cf97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf9c  lea     r14, [rbx+18h]
0x18006cfa0  mov     r8d, [rbp+nEncodingCodePage]; nEncodingCodePage
0x18006cfa4  test    r8d, r8d
0x18006cfa7  jz      short loc_18006CFEA
0x18006cfa9  mov     [rbp+ppOutput], r13
0x18006cfad  mov     [rbx+8Ch], r8d
0x18006cfb4  lea     r9, [rbp+ppOutput]; ppOutput
0x18006cfb8  xor     edx, edx; pMalloc
0x18006cfba  mov     rcx, r15; pOutputStream
0x18006cfbd  call    cs:__imp_CreateXmlWriterOutputWithEncodingCodePage
0x18006cfc3  test    eax, eax
0x18006cfc5  jz      short loc_18006CFD8
0x18006cfc7  mov     [rbx], r13
0x18006cfca  mov     [rdi], r13
0x18006cfcd  mov     [rsi], r13
0x18006cfd0  mov     [r14], r13
0x18006cfd3  jmp     loc_18006CE85
0x18006cfd8  mov     rdx, [rbp+ppOutput]
0x18006cfdc  mov     rcx, r14
0x18006cfdf  call    ?reset@?$unique_ptr@UIUnknown@@UComDeleter@@@std@@QEAAXPEAUIUnknown@@@Z; std::unique_ptr<IUnknown,ComDeleter>::reset(IUnknown *)
0x18006cfe4  mov     rdx, [rbp+ppOutput]
0x18006cfe8  jmp     short loc_18006CFED
0x18006cfea  mov     rdx, r15
0x18006cfed  mov     rcx, [rdi]
0x18006cff0  mov     rax, [rcx]
0x18006cff3  mov     rax, [rax+18h]
0x18006cff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cffc  test    eax, eax
0x18006cffe  jnz     short loc_18006CFC7
0x18006d000  mov     rcx, [rdi]
0x18006d003  mov     rdx, [rcx]
0x18006d006  mov     rax, [rdx+28h]
0x18006d00a  mov     r8, r12
0x18006d00d  mov     edx, r12d
0x18006d010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d015  mov     al, r12b
0x18006d018  add     rsp, 48h
0x18006d01c  pop     r15
0x18006d01e  pop     r14
0x18006d020  pop     r13
0x18006d022  pop     r12
0x18006d024  pop     rdi
0x18006d025  pop     rsi
0x18006d026  pop     rbx
0x18006d027  pop     rbp
0x18006d028  retn
```
