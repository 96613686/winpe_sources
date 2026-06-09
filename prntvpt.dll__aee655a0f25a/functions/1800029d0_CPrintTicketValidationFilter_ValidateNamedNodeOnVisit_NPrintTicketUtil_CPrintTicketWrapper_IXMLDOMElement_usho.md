# CPrintTicketValidationFilter::ValidateNamedNodeOnVisit(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *)

- ea: `0x1800029d0`
- end: `0x180002c6e`
- name: `?ValidateNamedNodeOnVisit@CPrintTicketValidationFilter@@IEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEBG@Z`
- size: `670`
- prototype: `__int64 __fastcall(CPrintTicketValidationFilter *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800025f0`
- `0x1800026c0`
- `0x180002810`
- `0x1800028a0`
- `0x180002930`

## callees

- `0x180002450`
- `0x1800029d0`
- `0x180003318`
- `0x180004b00`
- `0x1800056e0`
- `0x180005990`
- `0x18001e004`
- `0x180023010`

## string_xrefs

- `0x180002a54`: `Unexpected XML attributes exist on a %s element.  Only 'name' or Namespace is allowed.`
- `0x180002a64`: `%s elements must have an XML attribute 'name'.`
- `0x180002ab5`: `The name on %s is invalid.  Either the name is malformed, or the prefix does not map to a defined URI.`
- `0x180002ad1`: `Elements of type %s must have an XML attribute 'name'.`
- `0x180002bea`: `Invalid XML content exists in %s.  '%s' elements may only contain elements and comments.`

## pseudocode

```c
__int64 __fastcall CPrintTicketValidationFilter::ValidateNamedNodeOnVisit(
        CPrintTicketValidationFilter *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3,
        const unsigned __int16 *a4)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_attributes)(IXMLDOMElement *, IXMLDOMNamedNodeMap **); // rax
  int HasOnlyChildTypes; // ebx
  __int64 v11; // rcx
  bool v12; // cc
  const unsigned __int16 *v13; // rdx
  CValidationStatus *v14; // rdi
  struct IXMLDOMNode *v15; // rdx
  unsigned int v16; // r8d
  int NameAttribute; // eax
  unsigned __int16 *v18; // rdi
  const unsigned __int16 *v19; // rdx
  bool v20; // zf
  bool v21; // zf
  const unsigned __int16 *v23; // [rsp+28h] [rbp-30h]
  int v24; // [rsp+30h] [rbp-28h] BYREF
  __int64 v25; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 *v27[2]; // [rsp+48h] [rbp-10h] BYREF

  lpVtbl = a3->lpVtbl;
  v25 = 0;
  get_attributes = lpVtbl->get_attributes;
  v24 = 0;
  HasOnlyChildTypes = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))get_attributes)(a3, &v25);
  if ( HasOnlyChildTypes < 0 )
    goto LABEL_52;
  HasOnlyChildTypes = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 88LL))(v25, &v24);
  if ( HasOnlyChildTypes < 0 )
    goto LABEL_52;
  v12 = v24 < 1;
  if ( v24 > 1 )
  {
    if ( !(unsigned __int8)CPrintTicketValidationFilter::HasValidNameSpaceOrNameAttributes(v11, &v25, (unsigned int)v24) )
    {
      v13 = L"Unexpected XML attributes exist on a %s element.  Only 'name' or Namespace is allowed.";
LABEL_9:
      v14 = (CPrintTicketValidationFilter *)((char *)this + 8);
      HasOnlyChildTypes = CValidationStatus::SetValidationFailure(
                            (CPrintTicketValidationFilter *)((char *)this + 8),
                            v13,
                            a4,
                            0,
                            0,
                            v23);
      goto LABEL_40;
    }
    v12 = v24 < 1;
  }
  if ( v12 )
  {
    v13 = L"%s elements must have an XML attribute 'name'.";
    goto LABEL_9;
  }
  v27[0] = 0;
  v26 = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(a2, a3, &v26, v27, 1);
  v18 = v27[0];
  HasOnlyChildTypes = NameAttribute;
  if ( NameAttribute == -1072897499 )
  {
    v19 = L"The name on %s is invalid.  Either the name is malformed, or the prefix does not map to a defined URI.";
    goto LABEL_16;
  }
  if ( NameAttribute < 0 )
    goto LABEL_39;
  if ( !v26 || !v27[0] )
  {
    v19 = L"Elements of type %s must have an XML attribute 'name'.";
LABEL_16:
    HasOnlyChildTypes = CValidationStatus::SetValidationFailure(
                          (CPrintTicketValidationFilter *)((char *)this + 8),
                          v19,
                          a4,
                          0,
                          0,
                          v23);
    if ( HasOnlyChildTypes < 0 )
      goto LABEL_39;
  }
  if ( !*((_DWORD *)this + 2)
    || *((_DWORD *)this + 13) > 1u
    || a4 != L"Feature" && a4 != L"ParameterDef" && a4 != L"ParameterInit" )
  {
    goto LABEL_39;
  }
  if ( *v18 == 68 )
  {
    if ( v18[1] != 111 || v18[2] != 99 || v18[3] != 117 || v18[4] != 109 || v18[5] != 101 || v18[6] != 110 )
      goto LABEL_38;
    v20 = v18[7] == 116;
  }
  else if ( *v18 == 74 )
  {
    if ( v18[1] != 111 )
    {
LABEL_38:
      HasOnlyChildTypes = CValidationStatus::SetValidationFailure(
                            (CPrintTicketValidationFilter *)((char *)this + 8),
                            L"'%s' is an invalid name.  Root-level feature and parameter names must start with 'Job', 'Doc"
                             "ument', or 'Page'.",
                            v18,
                            0,
                            0,
                            v23);
      goto LABEL_39;
    }
    v20 = v18[2] == 98;
  }
  else
  {
    if ( *v18 != 80 || v18[1] != 97 || v18[2] != 103 )
      goto LABEL_38;
    v20 = v18[3] == 101;
  }
  if ( !v20 )
    goto LABEL_38;
LABEL_39:
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v26);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v27);
  v14 = (CPrintTicketValidationFilter *)((char *)this + 8);
LABEL_40:
  if ( HasOnlyChildTypes < 0 )
    goto LABEL_52;
  v21 = *(_DWORD *)v14 == 0;
  if ( !*(_DWORD *)v14 )
    goto LABEL_50;
  HasOnlyChildTypes = NPrintTicketUtil::HasOnlyChildTypes((NPrintTicketUtil *)a3, v15, v16);
  if ( HasOnlyChildTypes == 1 )
    HasOnlyChildTypes = CValidationStatus::SetValidationFailure(
                          v14,
                          L"Invalid XML content exists in %s.  '%s' elements may only contain elements and comments.",
                          a4,
                          a4,
                          0,
                          v23);
  if ( HasOnlyChildTypes >= 0 )
  {
    v21 = *(_DWORD *)v14 == 0;
    if ( !*(_DWORD *)v14 )
      goto LABEL_50;
    HasOnlyChildTypes = NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(a2, this, a3);
    if ( HasOnlyChildTypes == -2147155967 )
      HasOnlyChildTypes = CValidationStatus::SetValidationFailure(
                            v14,
                            L"One or more children of the %s element contain an invalid namespace prefix or namespace.",
                            a4,
                            0,
                            0,
                            v23);
    if ( HasOnlyChildTypes >= 0 )
    {
      v21 = *(_DWORD *)v14 == 0;
LABEL_50:
      if ( v21 )
        HasOnlyChildTypes = 1;
    }
  }
LABEL_52:
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return (unsigned int)HasOnlyChildTypes;
}

```

## disassembly

```asm
0x1800029d0  push    rbp
0x1800029d2  push    rbx
0x1800029d3  push    rsi
0x1800029d4  push    rdi
0x1800029d5  push    r12
0x1800029d7  push    r13
0x1800029d9  push    r14
0x1800029db  push    r15
0x1800029dd  mov     rbp, rsp
0x1800029e0  sub     rsp, 58h
0x1800029e4  mov     rax, [r8]
0x1800029e7  mov     r12, rdx
0x1800029ea  mov     r14, rcx
0x1800029ed  lea     rdx, [rbp+var_20]
0x1800029f1  xor     r13d, r13d
0x1800029f4  mov     rcx, r8
0x1800029f7  mov     rsi, r9
0x1800029fa  mov     [rbp+var_20], r13
0x1800029fe  mov     rax, [rax+88h]
0x180002a05  mov     r15, r8
0x180002a08  mov     [rbp+var_28], r13d
0x180002a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a11  mov     ebx, eax
0x180002a13  test    eax, eax
0x180002a15  js      loc_180002C46
0x180002a1b  mov     rcx, [rbp+var_20]
0x180002a1f  lea     rdx, [rbp+var_28]
0x180002a23  mov     rax, [rcx]
0x180002a26  mov     rax, [rax+58h]
0x180002a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a2f  mov     ebx, eax
0x180002a31  test    eax, eax
0x180002a33  js      loc_180002C46
0x180002a39  mov     eax, [rbp+var_28]
0x180002a3c  lea     ebx, [r13+1]
0x180002a40  cmp     eax, ebx
0x180002a42  jle     short loc_180002A62
0x180002a44  mov     r8d, eax
0x180002a47  lea     rdx, [rbp+var_20]
0x180002a4b  call    ?HasValidNameSpaceOrNameAttributes@CPrintTicketValidationFilter@@IEAA_NAEBV?$TAutoPtrCOM@UIXMLDOMNamedNodeMap@@@NCoreLibrary@@J@Z; CPrintTicketValidationFilter::HasValidNameSpaceOrNameAttributes(NCoreLibrary::TAutoPtrCOM<IXMLDOMNamedNodeMap> const &,long)
0x180002a50  test    al, al
0x180002a52  jnz     short loc_180002A5D
0x180002a54  lea     rdx, aUnexpectedXmlA; "Unexpected XML attributes exist on a %s"...
0x180002a5b  jmp     short loc_180002A6B
0x180002a5d  mov     eax, [rbp+var_28]
0x180002a60  cmp     eax, ebx
0x180002a62  jge     short loc_180002A89
0x180002a64  lea     rdx, aSElementsMustH; "%s elements must have an XML attribute "...
0x180002a6b  lea     rdi, [r14+8]
0x180002a6f  mov     [rsp+58h+var_38], r13; unsigned __int16 *
0x180002a74  mov     rcx, rdi; this
0x180002a77  mov     r8, rsi; unsigned __int16 *
0x180002a7a  xor     r9d, r9d; unsigned __int16 *
0x180002a7d  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180002a82  mov     ebx, eax
0x180002a84  jmp     loc_180002BC7
0x180002a89  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180002a8d  mov     [rbp+var_10], r13
0x180002a91  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180002a95  mov     [rbp+var_18], r13
0x180002a99  mov     rdx, r15; struct IXMLDOMElement *
0x180002a9c  mov     dword ptr [rsp+58h+var_38], ebx; int
0x180002aa0  mov     rcx, r12; this
0x180002aa3  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x180002aa8  mov     rdi, [rbp+var_10]
0x180002aac  mov     ebx, eax
0x180002aae  cmp     eax, 0C00CE225h
0x180002ab3  jnz     short loc_180002ABE
0x180002ab5  lea     rdx, aTheNameOnSIsIn; "The name on %s is invalid.  Either the "...
0x180002abc  jmp     short loc_180002AD8
0x180002abe  test    eax, eax
0x180002ac0  js      loc_180002BB1
0x180002ac6  cmp     [rbp+var_18], r13
0x180002aca  jz      short loc_180002AD1
0x180002acc  test    rdi, rdi
0x180002acf  jnz     short loc_180002AF6
0x180002ad1  lea     rdx, aElementsOfType; "Elements of type %s must have an XML at"...
0x180002ad8  xor     r9d, r9d; unsigned __int16 *
0x180002adb  mov     [rsp+58h+var_38], r13; unsigned __int16 *
0x180002ae0  mov     r8, rsi; unsigned __int16 *
0x180002ae3  lea     rcx, [r14+8]; this
0x180002ae7  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180002aec  mov     ebx, eax
0x180002aee  test    eax, eax
0x180002af0  js      loc_180002BB1
0x180002af6  lea     rcx, [r14+8]; this
0x180002afa  cmp     [rcx], r13d
0x180002afd  jz      loc_180002BB1
0x180002b03  cmp     dword ptr [r14+34h], 1
0x180002b08  ja      loc_180002BB1
0x180002b0e  lea     rax, aFeature; "Feature"
0x180002b15  cmp     rsi, rax
0x180002b18  jz      short loc_180002B32
0x180002b1a  lea     rax, aParameterdef; "ParameterDef"
0x180002b21  cmp     rsi, rax
0x180002b24  jz      short loc_180002B32
0x180002b26  lea     rax, aParameterinit; "ParameterInit"
0x180002b2d  cmp     rsi, rax
0x180002b30  jnz     short loc_180002BB1
0x180002b32  cmp     word ptr [rdi], 44h ; 'D'
0x180002b36  jz      short loc_180002B67
0x180002b38  cmp     word ptr [rdi], 4Ah ; 'J'
0x180002b3c  jz      short loc_180002B59
0x180002b3e  cmp     word ptr [rdi], 50h ; 'P'
0x180002b42  jnz     short loc_180002B98
0x180002b44  cmp     word ptr [rdi+2], 61h ; 'a'
0x180002b49  jnz     short loc_180002B98
0x180002b4b  cmp     word ptr [rdi+4], 67h ; 'g'
0x180002b50  jnz     short loc_180002B98
0x180002b52  cmp     word ptr [rdi+6], 65h ; 'e'
0x180002b57  jmp     short loc_180002B96
0x180002b59  cmp     word ptr [rdi+2], 6Fh ; 'o'
0x180002b5e  jnz     short loc_180002B98
0x180002b60  cmp     word ptr [rdi+4], 62h ; 'b'
0x180002b65  jmp     short loc_180002B96
0x180002b67  cmp     word ptr [rdi+2], 6Fh ; 'o'
0x180002b6c  jnz     short loc_180002B98
0x180002b6e  cmp     word ptr [rdi+4], 63h ; 'c'
0x180002b73  jnz     short loc_180002B98
0x180002b75  cmp     word ptr [rdi+6], 75h ; 'u'
0x180002b7a  jnz     short loc_180002B98
0x180002b7c  cmp     word ptr [rdi+8], 6Dh ; 'm'
0x180002b81  jnz     short loc_180002B98
0x180002b83  cmp     word ptr [rdi+0Ah], 65h ; 'e'
0x180002b88  jnz     short loc_180002B98
0x180002b8a  cmp     word ptr [rdi+0Ch], 6Eh ; 'n'
0x180002b8f  jnz     short loc_180002B98
0x180002b91  cmp     word ptr [rdi+0Eh], 74h ; 't'
0x180002b96  jz      short loc_180002BB1
0x180002b98  xor     r9d, r9d; unsigned __int16 *
0x180002b9b  mov     [rsp+58h+var_38], r13; unsigned __int16 *
0x180002ba0  mov     r8, rdi; unsigned __int16 *
0x180002ba3  lea     rdx, aSIsAnInvalidNa; "'%s' is an invalid name.  Root-level fe"...
0x180002baa  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180002baf  mov     ebx, eax
0x180002bb1  lea     rcx, [rbp+var_18]
0x180002bb5  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180002bba  lea     rcx, [rbp+var_10]
0x180002bbe  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180002bc3  lea     rdi, [r14+8]
0x180002bc7  test    ebx, ebx
0x180002bc9  js      short loc_180002C46
0x180002bcb  cmp     [rdi], r13d
0x180002bce  jz      short loc_180002C3E
0x180002bd0  mov     rcx, r15; this
0x180002bd3  call    ?HasOnlyChildTypes@NPrintTicketUtil@@YAJPEAUIXMLDOMNode@@I@Z; NPrintTicketUtil::HasOnlyChildTypes(IXMLDOMNode *,uint)
0x180002bd8  mov     ebx, eax
0x180002bda  cmp     eax, 1
0x180002bdd  jnz     short loc_180002BFB
0x180002bdf  mov     r9, rsi; unsigned __int16 *
0x180002be2  mov     [rsp+58h+var_38], r13; unsigned __int16 *
0x180002be7  mov     r8, rsi; unsigned __int16 *
0x180002bea  lea     rdx, aInvalidXmlCont; "Invalid XML content exists in %s.  '%s'"...
0x180002bf1  mov     rcx, rdi; this
0x180002bf4  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180002bf9  mov     ebx, eax
0x180002bfb  test    ebx, ebx
0x180002bfd  js      short loc_180002C46
0x180002bff  cmp     [rdi], r13d
0x180002c02  jz      short loc_180002C3E
0x180002c04  mov     r8, r15; struct IXMLDOMElement *
0x180002c07  mov     rdx, r14; struct NPrintTicketUtil::CAbstractPrintTicketVisitors *
0x180002c0a  mov     rcx, r12; this
0x180002c0d  call    ?VisitNodes@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAVCAbstractPrintTicketVisitors@2@PEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(NPrintTicketUtil::CAbstractPrintTicketVisitors *,IXMLDOMElement *)
0x180002c12  mov     ebx, eax
0x180002c14  cmp     eax, 80050001h
0x180002c19  jnz     short loc_180002C37
0x180002c1b  xor     r9d, r9d; unsigned __int16 *
0x180002c1e  mov     [rsp+58h+var_38], r13; unsigned __int16 *
0x180002c23  mov     r8, rsi; unsigned __int16 *
0x180002c26  lea     rdx, aOneOrMoreChild; "One or more children of the %s element "...
0x180002c2d  mov     rcx, rdi; this
0x180002c30  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180002c35  mov     ebx, eax
0x180002c37  test    ebx, ebx
0x180002c39  js      short loc_180002C46
0x180002c3b  cmp     [rdi], r13d
0x180002c3e  mov     eax, 1
0x180002c43  cmovz   ebx, eax
0x180002c46  mov     rcx, [rbp+var_20]
0x180002c4a  test    rcx, rcx
0x180002c4d  jz      short loc_180002C5B
0x180002c4f  mov     rax, [rcx]
0x180002c52  mov     rax, [rax+10h]
0x180002c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c5b  mov     eax, ebx
0x180002c5d  add     rsp, 58h
0x180002c61  pop     r15
0x180002c63  pop     r14
0x180002c65  pop     r13
0x180002c67  pop     r12
0x180002c69  pop     rdi
0x180002c6a  pop     rsi
0x180002c6b  pop     rbx
0x180002c6c  pop     rbp
0x180002c6d  retn
```
