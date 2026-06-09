# CPrintTicketValidationFilter::ValueVisitor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *)

- ea: `0x18000cd50`
- end: `0x18000d073`
- name: `?ValueVisitor@CPrintTicketValidationFilter@@UEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@@Z`
- size: `803`
- prototype: `__int64 __fastcall(CPrintTicketValidationFilter *this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003318`
- `0x1800056e0`
- `0x1800057f0`
- `0x180006940`
- `0x18000a070`
- `0x18000a2a4`
- `0x18000cd50`
- `0x18000e2a8`
- `0x18001b204`
- `0x18001e824`
- `0x180022594`
- `0x180023010`

## string_xrefs

- `0x18000cef3`: `http://www.w3.org/2001/XMLSchema`
- `0x18000ce8d`: `The prefix of type '%s' does not resolve to a URI defined in the document.`
- `0x18000cfef`: `A value of type QName contains the text '%s', the prefix of which does not resolve to a defined Uri.`

## pseudocode

```c
__int64 __fastcall CPrintTicketValidationFilter::ValueVisitor(
        CPrintTicketValidationFilter *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int Uri; // ebx
  unsigned __int16 *v9; // rdx
  CValidationStatus *v10; // rdi
  NPrintTicketUtil *v11; // rsi
  bool v12; // zf
  const wchar_t *v13; // r14
  NPrintTicketUtil::CPrintTicketWrapper *v14; // rcx
  wchar_t *v15; // rsi
  int LocalName; // eax
  int v17; // eax
  unsigned __int16 *v18; // rdx
  NPrintTicketUtil *v19; // rsi
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // rdx
  unsigned __int16 *v22; // rdx
  unsigned __int16 *v23; // rdx
  unsigned __int16 *v24; // rdx
  int IsValidQName; // eax
  const unsigned __int16 *v26; // [rsp+28h] [rbp-38h]
  NPrintTicketUtil *v27; // [rsp+30h] [rbp-30h] BYREF
  __int64 v28; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v29; // [rsp+40h] [rbp-20h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v31[2]; // [rsp+50h] [rbp-10h] BYREF
  int v32; // [rsp+A0h] [rbp+40h] BYREF
  NPrintTicketUtil *v33; // [rsp+B8h] [rbp+58h] BYREF

  if ( *((char *)this + 48) >= 0 )
    return (*(__int64 (__fastcall **)(CPrintTicketValidationFilter *))(*(_QWORD *)this + 72LL))(this);
  ++*((_DWORD *)this + 17);
  lpVtbl = a3->lpVtbl;
  v28 = 0;
  v32 = 0;
  v33 = 0;
  Uri = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))lpVtbl->get_attributes)(a3, &v28);
  if ( Uri < 0 )
    goto LABEL_43;
  Uri = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 88LL))(v28, &v32);
  if ( Uri < 0 )
    goto LABEL_43;
  Uri = CPrintTicketValidationFilter::CheckAttributesAndGetTypeName(
          (_DWORD)this,
          (unsigned int)&v28,
          v32,
          (_DWORD)a3,
          (__int64)&v33);
  if ( Uri < 0 )
    goto LABEL_43;
  v10 = (CPrintTicketValidationFilter *)((char *)this + 8);
  if ( !*(_DWORD *)v10 )
    goto LABEL_10;
  v11 = v33;
  if ( v33 && !(unsigned int)NPrintTicketUtil::IsValidQName(v33, v9) )
  {
    Uri = CValidationStatus::SetValidationFailure(
            v10,
            L"The type name '%s' on Value is not a valid QName.",
            (const unsigned __int16 *)v11,
            0,
            0,
            v26);
    if ( Uri < 0 )
      goto LABEL_43;
LABEL_10:
    v11 = v33;
  }
  v12 = *(_DWORD *)v10 == 0;
  if ( !*(_DWORD *)v10 )
    goto LABEL_41;
  if ( !v11 )
  {
LABEL_40:
    v12 = *(_DWORD *)v10 == 0;
LABEL_41:
    if ( v12 )
      Uri = 1;
    goto LABEL_43;
  }
  v31[0] = 0;
  String1 = 0;
  v27 = 0;
  v13 = 0;
  Uri = NPrintTicketUtil::CPrintTicketWrapper::getUri(a2, a3, (const unsigned __int16 *)v11, &String1);
  if ( Uri < 0 )
    goto LABEL_39;
  v15 = String1;
  if ( String1 )
  {
    LocalName = NPrintTicketUtil::CPrintTicketWrapper::getLocalName(v14, (const unsigned __int16 *)v33, v31);
    v13 = v31[0];
  }
  else
  {
    LocalName = CValidationStatus::SetValidationFailure(
                  v10,
                  L"The prefix of type '%s' does not resolve to a URI defined in the document.",
                  (const unsigned __int16 *)v33,
                  0,
                  0,
                  v26);
  }
  Uri = LocalName;
  if ( LocalName < 0 )
    goto LABEL_39;
  if ( !*(_DWORD *)v10 )
    goto LABEL_39;
  Uri = ((__int64 (__fastcall *)(struct IXMLDOMElement *, NPrintTicketUtil **))a3->lpVtbl->get_text)(a3, &v27);
  if ( Uri < 0 || !*(_DWORD *)v10 || wcscmp_0(v15, L"http://www.w3.org/2001/XMLSchema") )
    goto LABEL_39;
  v17 = wcscmp_0(v13, L"integer");
  v19 = v27;
  if ( !v17 && !(unsigned int)NPrintTicketUtil::IsValidInteger(v27, v18) )
  {
    v20 = (const unsigned __int16 *)v19;
    v21 = L"A Value of type integer contains content '%s', which is not a valid integer.";
LABEL_34:
    Uri = CValidationStatus::SetValidationFailure(v10, v21, v20, 0, 0, v26);
    goto LABEL_39;
  }
  if ( !wcscmp_0(v13, L"decimal") && !(unsigned int)NPrintTicketUtil::IsValidDecimal(v19, v22) )
  {
    v20 = (const unsigned __int16 *)v19;
    v21 = L"A Value of type decimal contains content '%s', which is not a valid decimal.";
    goto LABEL_34;
  }
  if ( !wcscmp_0(v13, L"IDREF") && !(unsigned int)NPrintTicketUtil::IsValidNCName(v19, v23) )
  {
    v20 = (const unsigned __int16 *)v19;
    v21 = L"A Value of type IDREF contains content '%s', which is not a valid IDREF.";
    goto LABEL_34;
  }
  if ( wcscmp_0(v13, L"QName") )
    goto LABEL_39;
  IsValidQName = NPrintTicketUtil::IsValidQName(v19, v24);
  v20 = (const unsigned __int16 *)v19;
  if ( !IsValidQName )
  {
    v21 = L"A Value of type QName contains content '%s', which is not a valid QName.";
    goto LABEL_34;
  }
  v29 = 0;
  Uri = NPrintTicketUtil::CPrintTicketWrapper::getUri(a2, a3, (const unsigned __int16 *)v19, &v29);
  if ( Uri >= 0 && !v29 )
    Uri = CValidationStatus::SetValidationFailure(
            v10,
            L"A value of type QName contains the text '%s', the prefix of which does not resolve to a defined Uri.",
            (const unsigned __int16 *)v27,
            0,
            0,
            v26);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v29);
LABEL_39:
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v27);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&String1);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v31);
  if ( Uri >= 0 )
    goto LABEL_40;
LABEL_43:
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v33);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x18000cd50  mov     [rsp-38h+arg_8], rbx
0x18000cd55  push    rbp
0x18000cd56  push    rsi
0x18000cd57  push    rdi
0x18000cd58  push    r12
0x18000cd5a  push    r13
0x18000cd5c  push    r14
0x18000cd5e  push    r15
0x18000cd60  mov     rbp, rsp
0x18000cd63  sub     rsp, 60h
0x18000cd67  test    byte ptr [rcx+30h], 80h
0x18000cd6b  mov     r15, r8
0x18000cd6e  mov     r12, rdx
0x18000cd71  mov     rdi, rcx
0x18000cd74  jnz     short loc_18000CD87
0x18000cd76  mov     rax, [rcx]
0x18000cd79  mov     rax, [rax+48h]
0x18000cd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd82  jmp     loc_18000D05B
0x18000cd87  inc     dword ptr [rcx+44h]
0x18000cd8a  lea     rdx, [rbp+var_28]
0x18000cd8e  mov     rax, [r8]
0x18000cd91  xor     r13d, r13d
0x18000cd94  mov     rcx, r15
0x18000cd97  mov     [rbp+var_28], r13
0x18000cd9b  mov     [rbp+arg_0], r13d
0x18000cd9f  mov     [rbp+arg_18], r13
0x18000cda3  mov     rax, [rax+88h]
0x18000cdaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdaf  mov     ebx, eax
0x18000cdb1  test    eax, eax
0x18000cdb3  js      loc_18000D03B
0x18000cdb9  mov     rcx, [rbp+var_28]
0x18000cdbd  lea     rdx, [rbp+arg_0]
0x18000cdc1  mov     rax, [rcx]
0x18000cdc4  mov     rax, [rax+58h]
0x18000cdc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdcd  mov     ebx, eax
0x18000cdcf  test    eax, eax
0x18000cdd1  js      loc_18000D03B
0x18000cdd7  mov     r8d, [rbp+arg_0]
0x18000cddb  lea     rax, [rbp+arg_18]
0x18000cddf  mov     r9, r15
0x18000cde2  mov     [rsp+60h+var_40], rax
0x18000cde7  lea     rdx, [rbp+var_28]
0x18000cdeb  mov     rcx, rdi
0x18000cdee  call    ?CheckAttributesAndGetTypeName@CPrintTicketValidationFilter@@QEAAJAEBV?$TAutoPtrCOM@UIXMLDOMNamedNodeMap@@@NCoreLibrary@@JPEAUIXMLDOMElement@@AEAVTAutoPtrBSTR@3@@Z; CPrintTicketValidationFilter::CheckAttributesAndGetTypeName(NCoreLibrary::TAutoPtrCOM<IXMLDOMNamedNodeMap> const &,long,IXMLDOMElement *,NCoreLibrary::TAutoPtrBSTR &)
0x18000cdf3  mov     ebx, eax
0x18000cdf5  test    eax, eax
0x18000cdf7  js      loc_18000D03B
0x18000cdfd  add     rdi, 8
0x18000ce01  cmp     [rdi], r13d
0x18000ce04  jz      short loc_18000CE3F
0x18000ce06  mov     rsi, [rbp+arg_18]
0x18000ce0a  test    rsi, rsi
0x18000ce0d  jz      short loc_18000CE43
0x18000ce0f  mov     rcx, rsi; this
0x18000ce12  call    ?IsValidQName@NPrintTicketUtil@@YAHPEAG@Z; NPrintTicketUtil::IsValidQName(ushort *)
0x18000ce17  test    eax, eax
0x18000ce19  jnz     short loc_18000CE43
0x18000ce1b  xor     r9d, r9d; unsigned __int16 *
0x18000ce1e  mov     [rsp+60h+var_40], r13; unsigned __int16 *
0x18000ce23  mov     r8, rsi; unsigned __int16 *
0x18000ce26  lea     rdx, aTheTypeNameSOn; "The type name '%s' on Value is not a va"...
0x18000ce2d  mov     rcx, rdi; this
0x18000ce30  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000ce35  mov     ebx, eax
0x18000ce37  test    eax, eax
0x18000ce39  js      loc_18000D03B
0x18000ce3f  mov     rsi, [rbp+arg_18]
0x18000ce43  cmp     [rdi], r13d
0x18000ce46  jz      loc_18000D033
0x18000ce4c  test    rsi, rsi
0x18000ce4f  jz      loc_18000D030
0x18000ce55  lea     r9, [rbp+String1]; unsigned __int16 **
0x18000ce59  mov     [rbp+var_10], r13
0x18000ce5d  mov     r8, rsi; unsigned __int16 *
0x18000ce60  mov     [rbp+String1], r13
0x18000ce64  mov     rdx, r15; struct IXMLDOMElement *
0x18000ce67  mov     [rbp+var_30], r13
0x18000ce6b  mov     rcx, r12; this
0x18000ce6e  mov     r14, r13
0x18000ce71  call    ?getUri@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getUri(IXMLDOMElement *,ushort const *,ushort * *)
0x18000ce76  mov     ebx, eax
0x18000ce78  test    eax, eax
0x18000ce7a  js      loc_18000D011
0x18000ce80  mov     rsi, [rbp+String1]
0x18000ce84  test    rsi, rsi
0x18000ce87  jnz     short loc_18000CEA6
0x18000ce89  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x18000ce8d  lea     rdx, aThePrefixOfTyp; "The prefix of type '%s' does not resolv"...
0x18000ce94  xor     r9d, r9d; unsigned __int16 *
0x18000ce97  mov     [rsp+60h+var_40], r13; unsigned __int16 *
0x18000ce9c  mov     rcx, rdi; this
0x18000ce9f  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000cea4  jmp     short loc_18000CEB7
0x18000cea6  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18000ceaa  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18000ceae  call    ?getLocalName@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getLocalName(ushort const *,ushort * *)
0x18000ceb3  mov     r14, [rbp+var_10]
0x18000ceb7  mov     ebx, eax
0x18000ceb9  test    eax, eax
0x18000cebb  js      loc_18000D011
0x18000cec1  cmp     [rdi], r13d
0x18000cec4  jz      loc_18000D011
0x18000ceca  mov     rax, [r15]
0x18000cecd  lea     rdx, [rbp+var_30]
0x18000ced1  mov     rcx, r15
0x18000ced4  mov     rax, [rax+0D0h]
0x18000cedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cee0  mov     ebx, eax
0x18000cee2  test    eax, eax
0x18000cee4  js      loc_18000D011
0x18000ceea  cmp     [rdi], r13d
0x18000ceed  jz      loc_18000D011
0x18000cef3  lea     rdx, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x18000cefa  mov     rcx, rsi; String1
0x18000cefd  call    wcscmp_0
0x18000cf02  test    eax, eax
0x18000cf04  jnz     loc_18000D011
0x18000cf0a  lea     rdx, aInteger; "integer"
0x18000cf11  mov     rcx, r14; String1
0x18000cf14  call    wcscmp_0
0x18000cf19  mov     rsi, [rbp+var_30]
0x18000cf1d  test    eax, eax
0x18000cf1f  jnz     short loc_18000CF39
0x18000cf21  mov     rcx, rsi; this
0x18000cf24  call    ?IsValidInteger@NPrintTicketUtil@@YAHPEAG@Z; NPrintTicketUtil::IsValidInteger(ushort *)
0x18000cf29  test    eax, eax
0x18000cf2b  jnz     short loc_18000CF39
0x18000cf2d  mov     r8, rsi
0x18000cf30  lea     rdx, aAValueOfTypeIn; "A Value of type integer contains conten"...
0x18000cf37  jmp     short loc_18000CFB8
0x18000cf39  lea     rdx, aDecimal; "decimal"
0x18000cf40  mov     rcx, r14; String1
0x18000cf43  call    wcscmp_0
0x18000cf48  test    eax, eax
0x18000cf4a  jnz     short loc_18000CF64
0x18000cf4c  mov     rcx, rsi; this
0x18000cf4f  call    ?IsValidDecimal@NPrintTicketUtil@@YAHPEAG@Z; NPrintTicketUtil::IsValidDecimal(ushort *)
0x18000cf54  test    eax, eax
0x18000cf56  jnz     short loc_18000CF64
0x18000cf58  mov     r8, rsi
0x18000cf5b  lea     rdx, aAValueOfTypeDe; "A Value of type decimal contains conten"...
0x18000cf62  jmp     short loc_18000CFB8
0x18000cf64  lea     rdx, aIdref; "IDREF"
0x18000cf6b  mov     rcx, r14; String1
0x18000cf6e  call    wcscmp_0
0x18000cf73  test    eax, eax
0x18000cf75  jnz     short loc_18000CF8F
0x18000cf77  mov     rcx, rsi; this
0x18000cf7a  call    ?IsValidNCName@NPrintTicketUtil@@YAHPEAG@Z; NPrintTicketUtil::IsValidNCName(ushort *)
0x18000cf7f  test    eax, eax
0x18000cf81  jnz     short loc_18000CF8F
0x18000cf83  mov     r8, rsi
0x18000cf86  lea     rdx, aAValueOfTypeId; "A Value of type IDREF contains content "...
0x18000cf8d  jmp     short loc_18000CFB8
0x18000cf8f  lea     rdx, aQname; "QName"
0x18000cf96  mov     rcx, r14; String1
0x18000cf99  call    wcscmp_0
0x18000cf9e  test    eax, eax
0x18000cfa0  jnz     short loc_18000D011
0x18000cfa2  mov     rcx, rsi; this
0x18000cfa5  call    ?IsValidQName@NPrintTicketUtil@@YAHPEAG@Z; NPrintTicketUtil::IsValidQName(ushort *)
0x18000cfaa  mov     r8, rsi; unsigned __int16 *
0x18000cfad  test    eax, eax
0x18000cfaf  jnz     short loc_18000CFCC
0x18000cfb1  lea     rdx, aAValueOfTypeQn; "A Value of type QName contains content "...
0x18000cfb8  xor     r9d, r9d; unsigned __int16 *
0x18000cfbb  mov     [rsp+60h+var_40], r13; unsigned __int16 *
0x18000cfc0  mov     rcx, rdi; this
0x18000cfc3  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000cfc8  mov     ebx, eax
0x18000cfca  jmp     short loc_18000D011
0x18000cfcc  lea     r9, [rbp+var_20]; unsigned __int16 **
0x18000cfd0  mov     [rbp+var_20], r13
0x18000cfd4  mov     rdx, r15; struct IXMLDOMElement *
0x18000cfd7  mov     rcx, r12; this
0x18000cfda  call    ?getUri@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getUri(IXMLDOMElement *,ushort const *,ushort * *)
0x18000cfdf  mov     ebx, eax
0x18000cfe1  test    eax, eax
0x18000cfe3  js      short loc_18000D008
0x18000cfe5  cmp     [rbp+var_20], r13
0x18000cfe9  jnz     short loc_18000D008
0x18000cfeb  mov     r8, [rbp+var_30]; unsigned __int16 *
0x18000cfef  lea     rdx, aAValueOfTypeQn_0; "A value of type QName contains the text"...
0x18000cff6  xor     r9d, r9d; unsigned __int16 *
0x18000cff9  mov     [rsp+60h+var_40], r13; unsigned __int16 *
0x18000cffe  mov     rcx, rdi; this
0x18000d001  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000d006  mov     ebx, eax
0x18000d008  lea     rcx, [rbp+var_20]
0x18000d00c  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000d011  lea     rcx, [rbp+var_30]
0x18000d015  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000d01a  lea     rcx, [rbp+String1]
0x18000d01e  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000d023  lea     rcx, [rbp+var_10]
0x18000d027  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000d02c  test    ebx, ebx
0x18000d02e  js      short loc_18000D03B
0x18000d030  cmp     [rdi], r13d
0x18000d033  mov     eax, 1
0x18000d038  cmovz   ebx, eax
0x18000d03b  lea     rcx, [rbp+arg_18]
0x18000d03f  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000d044  mov     rcx, [rbp+var_28]
0x18000d048  test    rcx, rcx
0x18000d04b  jz      short loc_18000D059
0x18000d04d  mov     rax, [rcx]
0x18000d050  mov     rax, [rax+10h]
0x18000d054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d059  mov     eax, ebx
0x18000d05b  mov     rbx, [rsp+60h+arg_8]
0x18000d063  add     rsp, 60h
0x18000d067  pop     r15
0x18000d069  pop     r14
0x18000d06b  pop     r13
0x18000d06d  pop     r12
0x18000d06f  pop     rdi
0x18000d070  pop     rsi
0x18000d071  pop     rbp
0x18000d072  retn
```
