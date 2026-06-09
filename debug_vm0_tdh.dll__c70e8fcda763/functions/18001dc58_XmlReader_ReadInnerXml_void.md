# XmlReader::ReadInnerXml(void)

- ea: `0x18001dc58`
- end: `0x18001df5b`
- name: `?ReadInnerXml@XmlReader@@QEAA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ`
- size: `771`
- prototype: `__int64 __fastcall(XmlReader *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001d810`

## callees

- `0x1800159ac`
- `0x18001cbd4`
- `0x18001dc58`
- `0x18001ee78`
- `0x180021490`
- `0x18002fab0`
- `0x1800310b4`
- `0x18003a638`
- `0x18003c93c`
- `0x18004c010`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingCodePage` at `0x18001dca6`
- `XmlLite!CreateXmlWriterOutputWithEncodingCodePage` at `0x18001dca6`
- `XmlLite!CreateXmlWriter` at `0x18001dcdc`
- `XmlLite!CreateXmlWriter` at `0x18001dcdc`

## string_xrefs

- `0x18001dcaf`: `CreateXmlWriterOutputWithEncodingCodePage`
- `0x18001dce5`: `CreateXmlWriterLite`
- `0x18001dd74`: `SetProperty(OmitXmlDeclaration)`
- `0x18001de3d`: `WriteNode`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct IUnknownVtbl **__fastcall XmlReader::ReadInnerXml(IUnknown *this, struct IUnknownVtbl **a2)
{
  IUnknown *v4; // r15
  HRESULT v5; // eax
  IXmlWriterOutput *v6; // rdi
  HRESULT v7; // eax
  __int64 v8; // rbx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  IUnknown *v13; // rbx
  struct IUnknownVtbl *lpVtbl; // rax
  unsigned __int64 v15; // r14
  enum XmlNodeType v16; // eax
  bool v17; // di
  int v18; // eax
  int v19; // eax
  int v20; // eax
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // rdi
  struct IUnknownVtbl *v23; // rdx
  struct IUnknownVtbl *v24; // r15
  unsigned __int64 v25; // rcx
  struct IUnknownVtbl *v26; // rax
  size_t v27; // rdi
  IXmlWriterOutput *v29; // [rsp+30h] [rbp-10h] BYREF
  enum XmlNodeType v30; // [rsp+80h] [rbp+40h] BYREF
  __int64 v31; // [rsp+88h] [rbp+48h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+90h] [rbp+50h] BYREF
  void *ppvObject; // [rsp+98h] [rbp+58h] BYREF

  v4 = this + 6;
  if ( !this[6].lpVtbl )
  {
    v31 = 0;
    ppOutput = 0;
    v5 = CreateXmlWriterOutputWithEncodingCodePage(this + 1, 0, 0x4B0u, &ppOutput);
    XmlReader::ThrowIfFailed((XmlReader *)this, "CreateXmlWriterOutputWithEncodingCodePage", v5);
    v6 = ppOutput;
    v29 = ppOutput;
    ppvObject = 0;
    v7 = CreateXmlWriter(&GUID_862494c6_1310_4aad_b3cd_2dbeebf670d3, &ppvObject, 0);
    XmlReader::ThrowIfFailed((XmlReader *)this, "CreateXmlWriterLite", v7);
    std::unique_ptr<IXmlWriterLite,XmlReader::ReleaseDelete>::reset(&v31, ppvObject);
    v8 = v31;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 40LL))(v31, 2);
    XmlReader::ThrowIfFailed((XmlReader *)this, "SetProperty(ByteOrderMark)", v9);
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, 4, 1);
    XmlReader::ThrowIfFailed((XmlReader *)this, "SetProperty(ConformanceLevel)", v10);
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, 3, 1);
    XmlReader::ThrowIfFailed((XmlReader *)this, "SetProperty(OmitXmlDeclaration)", v11);
    v12 = (*(__int64 (__fastcall **)(__int64, IXmlWriterOutput *))(*(_QWORD *)v8 + 24LL))(v8, v6);
    XmlReader::ThrowIfFailed((XmlReader *)this, "SetOutput(AppendStream)", v12);
    v31 = 0;
    std::unique_ptr<IXmlWriterLite,XmlReader::ReleaseDelete>::reset(v4, v8);
    std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v31);
    std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v29);
  }
  v13 = this + 2;
  lpVtbl = this[2].lpVtbl;
  if ( lpVtbl != this[3].lpVtbl )
    this[3].lpVtbl = lpVtbl;
  v30 = XmlNodeType_None;
  v15 = 0;
  if ( XmlReader::FirstChild((XmlReader *)this, &v30) )
  {
    v16 = v30;
    while ( 1 )
    {
      while ( 1 )
      {
        v17 = v16 == XmlNodeType_Whitespace;
        if ( v15 || v16 != XmlNodeType_Whitespace )
          break;
        XmlReader::Read((XmlReader *)this, &v30);
LABEL_14:
        v16 = v30;
        if ( v30 == XmlNodeType_EndElement )
          goto LABEL_15;
      }
      v18 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, struct IUnknownVtbl *, _QWORD))v4->lpVtbl->QueryInterface
             + 20))(
              v4->lpVtbl,
              this->lpVtbl,
              0);
      XmlReader::ThrowIfFailed((XmlReader *)this, "WriteNode", v18);
      LODWORD(v31) = 0;
      v19 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, __int64 *))this->lpVtbl->QueryInterface + 7))(
              this->lpVtbl,
              &v31);
      XmlReader::ThrowIfFailed((XmlReader *)this, "GetNodeType", v19);
      v16 = (int)v31;
      v30 = (int)v31;
      if ( !v17 || (_DWORD)v31 == 15 )
      {
        v20 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *))v4->lpVtbl->QueryInterface + 30))(v4->lpVtbl);
        XmlReader::ThrowIfFailed((XmlReader *)this, "Flush", v20);
        if ( !v17 )
          v15 = (char *)this[3].lpVtbl - (char *)v13->lpVtbl;
        goto LABEL_14;
      }
    }
  }
LABEL_15:
  v21 = v15 >> 1;
  v22 = 2 * v21;
  v23 = v13->lpVtbl;
  v24 = this[3].lpVtbl;
  v25 = (char *)v24 - (char *)this[2].lpVtbl;
  if ( 2 * v21 < v25 )
  {
    v26 = (struct IUnknownVtbl *)((char *)v23 + v22);
LABEL_21:
    this[3].lpVtbl = v26;
    goto LABEL_22;
  }
  if ( 2 * v21 > v25 )
  {
    if ( v22 <= (char *)this[4].lpVtbl - (char *)v23 )
    {
      v27 = v22 - v25;
      memset_0(this[3].lpVtbl, 0, v27);
      v26 = (struct IUnknownVtbl *)((char *)v24 + v27);
      goto LABEL_21;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&this[2], 2 * v21);
  }
LABEL_22:
  std::vector<unsigned char>::insert<unsigned char const *,0>(
    (_DWORD)this + 16,
    (unsigned int)&v31,
    this[3].lpVtbl,
    (unsigned int)&pszFormat,
    (__int64)&word_18005775E);
  *a2 = v13->lpVtbl;
  a2[1] = (struct IUnknownVtbl *)v21;
  return a2;
}

```

## disassembly

```asm
0x18001dc58  push    rbp
0x18001dc5a  push    rbx
0x18001dc5b  push    rsi
0x18001dc5c  push    rdi
0x18001dc5d  push    r12
0x18001dc5f  push    r14
0x18001dc61  push    r15
0x18001dc63  mov     rbp, rsp
0x18001dc66  sub     rsp, 40h
0x18001dc6a  mov     r12, rdx
0x18001dc6d  mov     rsi, rcx
0x18001dc70  lea     r15, [rcx+30h]
0x18001dc74  cmp     qword ptr [r15], 0
0x18001dc78  jnz     loc_18001DDCE
0x18001dc7e  mov     [rbp+var_10], 0
0x18001dc86  mov     [rbp+arg_8], 0
0x18001dc8e  mov     [rbp+ppOutput], 0
0x18001dc96  add     rcx, 8; pOutputStream
0x18001dc9a  lea     r9, [rbp+ppOutput]; ppOutput
0x18001dc9e  xor     edx, edx; pMalloc
0x18001dca0  mov     r8d, 4B0h; nEncodingCodePage
0x18001dca6  call    cs:__imp_CreateXmlWriterOutputWithEncodingCodePage
0x18001dcac  mov     r8d, eax; int
0x18001dcaf  lea     rdx, aCreatexmlwrite_1; "CreateXmlWriterOutputWithEncodingCodePa"...
0x18001dcb6  mov     rcx, rsi; this
0x18001dcb9  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x18001dcbe  mov     rdi, [rbp+ppOutput]
0x18001dcc2  mov     [rbp+var_10], rdi
0x18001dcc6  mov     [rbp+ppvObject], 0
0x18001dcce  xor     r8d, r8d; pMalloc
0x18001dcd1  lea     rdx, [rbp+ppvObject]; ppvObject
0x18001dcd5  lea     rcx, _GUID_862494c6_1310_4aad_b3cd_2dbeebf670d3; riid
0x18001dcdc  call    cs:__imp_CreateXmlWriter
0x18001dce2  mov     r8d, eax; int
0x18001dce5  lea     rdx, aCreatexmlwrite_2; "CreateXmlWriterLite"
0x18001dcec  mov     rcx, rsi; this
0x18001dcef  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x18001dcf4  mov     rdx, [rbp+ppvObject]
0x18001dcf8  lea     rcx, [rbp+arg_8]
0x18001dcfc  call    ?reset@?$unique_ptr@UIXmlWriterLite@@UReleaseDelete@XmlReader@@@std@@QEAAXPEAUIXmlWriterLite@@@Z; std::unique_ptr<IXmlWriterLite,XmlReader::ReleaseDelete>::reset(IXmlWriterLite *)
0x18001dd01  mov     rbx, [rbp+arg_8]
0x18001dd05  mov     rax, [rbx]
0x18001dd08  xor     r8d, r8d
0x18001dd0b  lea     edx, [r8+2]
0x18001dd0f  mov     rcx, rbx
0x18001dd12  mov     rax, [rax+28h]
0x18001dd16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd1b  mov     r8d, eax; int
0x18001dd1e  lea     rdx, aSetpropertyByt; "SetProperty(ByteOrderMark)"
0x18001dd25  mov     rcx, rsi; this
0x18001dd28  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x18001dd2d  mov     rax, [rbx]
0x18001dd30  mov     r14d, 1
0x18001dd36  mov     r8d, r14d
0x18001dd39  lea     edx, [r14+3]
0x18001dd3d  mov     rcx, rbx
0x18001dd40  mov     rax, [rax+28h]
0x18001dd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd49  mov     r8d, eax; int
0x18001dd4c  lea     rdx, aSetpropertyCon; "SetProperty(ConformanceLevel)"
0x18001dd53  mov     rcx, rsi; this
0x18001dd56  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x18001dd5b  mov     rax, [rbx]
0x18001dd5e  mov     r8d, r14d
0x18001dd61  lea     edx, [r14+2]
0x18001dd65  mov     rcx, rbx
0x18001dd68  mov     rax, [rax+28h]
0x18001dd6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd71  mov     r8d, eax; int
0x18001dd74  lea     rdx, aSetpropertyOmi; "SetProperty(OmitXmlDeclaration)"
0x18001dd7b  mov     rcx, rsi; this
0x18001dd7e  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x18001dd83  mov     rax, [rbx]
0x18001dd86  mov     rdx, rdi
0x18001dd89  mov     rcx, rbx
0x18001dd8c  mov     rax, [rax+18h]
0x18001dd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd95  mov     r8d, eax; int
0x18001dd98  lea     rdx, aSetoutputAppen; "SetOutput(AppendStream)"
0x18001dd9f  mov     rcx, rsi; this
0x18001dda2  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x18001dda7  mov     [rbp+arg_8], 0
0x18001ddaf  mov     rdx, rbx
0x18001ddb2  mov     rcx, r15
0x18001ddb5  call    ?reset@?$unique_ptr@UIXmlWriterLite@@UReleaseDelete@XmlReader@@@std@@QEAAXPEAUIXmlWriterLite@@@Z; std::unique_ptr<IXmlWriterLite,XmlReader::ReleaseDelete>::reset(IXmlWriterLite *)
0x18001ddba  nop
0x18001ddbb  lea     rcx, [rbp+arg_8]
0x18001ddbf  call    ??1?$unique_ptr@UIUnknown@@UReleaseDelete@XmlReader@@@std@@QEAA@XZ; std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(void)
0x18001ddc4  nop
0x18001ddc5  lea     rcx, [rbp+var_10]
0x18001ddc9  call    ??1?$unique_ptr@UIUnknown@@UReleaseDelete@XmlReader@@@std@@QEAA@XZ; std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(void)
0x18001ddce  lea     rbx, [rsi+10h]
0x18001ddd2  mov     rax, [rbx]
0x18001ddd5  cmp     rax, [rbx+8]
0x18001ddd9  jz      short loc_18001DDDF
0x18001dddb  mov     [rbx+8], rax
0x18001dddf  mov     [rbp+arg_0], 0
0x18001dde6  xor     r14d, r14d
0x18001dde9  lea     rdx, [rbp+arg_0]; enum XmlNodeType *
0x18001dded  mov     rcx, rsi; this
0x18001ddf0  call    ?FirstChild@XmlReader@@QEAA_NPEAW4XmlNodeType@@@Z; XmlReader::FirstChild(XmlNodeType *)
0x18001ddf5  test    al, al
0x18001ddf7  jz      loc_18001DEC8
0x18001ddfd  mov     eax, [rbp+arg_0]
0x18001de00  cmp     eax, 0Dh
0x18001de03  setz    dil
0x18001de07  test    r14, r14
0x18001de0a  jnz     short loc_18001DE22
0x18001de0c  test    dil, dil
0x18001de0f  jz      short loc_18001DE22
0x18001de11  lea     rdx, [rbp+arg_0]; enum XmlNodeType *
0x18001de15  mov     rcx, rsi; this
0x18001de18  call    ?Read@XmlReader@@QEAA_NPEAW4XmlNodeType@@@Z; XmlReader::Read(XmlNodeType *)
0x18001de1d  jmp     loc_18001DEBC
0x18001de22  mov     rcx, [r15]
0x18001de25  mov     rax, [rcx]
0x18001de28  xor     r8d, r8d
0x18001de2b  mov     rdx, [rsi]
0x18001de2e  mov     rax, [rax+0A0h]
0x18001de35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de3a  mov     r8d, eax; int
0x18001de3d  lea     rdx, aWritenode; "WriteNode"
0x18001de44  mov     rcx, rsi; this
0x18001de47  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x18001de4c  mov     dword ptr [rbp+arg_8], 0
0x18001de53  mov     rcx, [rsi]
0x18001de56  mov     rax, [rcx]
0x18001de59  lea     rdx, [rbp+arg_8]
0x18001de5d  mov     rax, [rax+38h]
0x18001de61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de66  mov     r8d, eax; int
0x18001de69  lea     rdx, aGetnodetype; "GetNodeType"
0x18001de70  mov     rcx, rsi; this
0x18001de73  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x18001de78  mov     eax, dword ptr [rbp+arg_8]
0x18001de7b  mov     [rbp+arg_0], eax
0x18001de7e  test    dil, dil
0x18001de81  jz      short loc_18001DE8C
0x18001de83  cmp     eax, 0Fh
0x18001de86  jnz     loc_18001DE00
0x18001de8c  mov     rcx, [r15]
0x18001de8f  mov     rax, [rcx]
0x18001de92  mov     rax, [rax+0F0h]
0x18001de99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de9e  mov     r8d, eax; int
0x18001dea1  lea     rdx, aFlush; "Flush"
0x18001dea8  mov     rcx, rsi; this
0x18001deab  call    ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
0x18001deb0  test    dil, dil
0x18001deb3  jnz     short loc_18001DEBC
0x18001deb5  mov     r14, [rsi+18h]
0x18001deb9  sub     r14, [rbx]
0x18001debc  mov     eax, [rbp+arg_0]
0x18001debf  cmp     eax, 0Fh
0x18001dec2  jnz     loc_18001DE00
0x18001dec8  shr     r14, 1
0x18001decb  lea     rdi, [r14+r14]
0x18001decf  mov     rdx, [rbx]
0x18001ded2  mov     r15, [rbx+8]
0x18001ded6  mov     rcx, r15
0x18001ded9  sub     rcx, rdx
0x18001dedc  cmp     rdi, rcx
0x18001dedf  jnb     short loc_18001DEE7
0x18001dee1  lea     rax, [rdx+rdi]
0x18001dee5  jmp     short loc_18001DF16
0x18001dee7  jbe     short loc_18001DF1A
0x18001dee9  mov     rax, [rbx+10h]
0x18001deed  sub     rax, rdx
0x18001def0  cmp     rdi, rax
0x18001def3  jbe     short loc_18001DF02
0x18001def5  mov     rdx, rdi
0x18001def8  mov     rcx, rbx
0x18001defb  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001df00  jmp     short loc_18001DF1A
0x18001df02  sub     rdi, rcx
0x18001df05  mov     r8, rdi; Size
0x18001df08  xor     edx, edx; Val
0x18001df0a  mov     rcx, r15; void *
0x18001df0d  call    memset_0
0x18001df12  lea     rax, [rdi+r15]
0x18001df16  mov     [rbx+8], rax
0x18001df1a  lea     rax, word_18005775E
0x18001df21  mov     [rsp+40h+var_20], rax
0x18001df26  lea     r9, pszFormat
0x18001df2d  mov     r8, [rsi+18h]
0x18001df31  lea     rdx, [rbp+arg_8]
0x18001df35  mov     rcx, rbx
0x18001df38  call    ??$insert@PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE1@Z; std::vector<uchar>::insert<uchar const *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,uchar const *)
0x18001df3d  mov     rax, [rbx]
0x18001df40  mov     [r12], rax
0x18001df44  mov     [r12+8], r14
0x18001df49  mov     rax, r12
0x18001df4c  add     rsp, 40h
0x18001df50  pop     r15
0x18001df52  pop     r14
0x18001df54  pop     r12
0x18001df56  pop     rdi
0x18001df57  pop     rsi
0x18001df58  pop     rbx
0x18001df59  pop     rbp
0x18001df5a  retn
```
