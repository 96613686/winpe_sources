# NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,int,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x180006b10`
- end: `0x180006c6c`
- name: `?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@UEAAJPEAUIXMLDOMElement@@PEBG11H11PEAPEAU3@@Z`
- size: `348`
- prototype: `__int64 __usercall@<rax>(NPrintTicketUtil::CPrintTicketWrapper *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006b10`
- `0x180006d70`
- `0x180006f80`
- `0x1800070e0`
- `0x1800076e8`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006bd8`
- `OLEAUT32!__imp_SysFreeString` at `0x180006bd8`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        char *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        struct IXMLDOMElement **a9)
{
  unsigned __int16 *v12; // r8
  int XMLAttribute; // ebx
  struct IXMLDOMElement *v14; // rcx
  int QName; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v17; // rcx
  OLECHAR *v18; // rdi
  struct IXMLDOMElement *v19; // rdx
  unsigned __int16 **v20; // [rsp+28h] [rbp-18h]
  struct IXMLDOMElement **v21; // [rsp+28h] [rbp-18h]
  BSTR bstrString[2]; // [rsp+30h] [rbp-10h] BYREF
  struct IXMLDOMElement *v23; // [rsp+78h] [rbp+38h] BYREF

  v23 = 0;
  if ( !a4 || !a3 )
    return 2147942487LL;
  if ( a2 )
  {
    v12 = L"ScoredProperty";
    if ( a6 )
      goto LABEL_5;
  }
  else
  {
    if ( a6 )
    {
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v23);
      return 2147549183LL;
    }
    a2 = (struct IXMLDOMElement *)*((_QWORD *)this + 3);
  }
  v12 = L"Property";
LABEL_5:
  bstrString[0] = 0;
  XMLAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
                   (__int64 **)this,
                   a2,
                   (struct IXMLDOMElement *)v12,
                   a4,
                   &v23);
  if ( XMLAttribute >= 0 )
  {
    QName = NPrintTicketUtil::CreateQName(
              this,
              v23,
              (struct IXMLDOMElement *)a4,
              a3,
              (unsigned __int16 *)bstrString,
              v20);
    v18 = bstrString[0];
    XMLAttribute = QName;
    if ( QName < 0
      || (XMLAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(v17, v23, L"name", bstrString[0]),
          XMLAttribute < 0)
      || a5
      && (XMLAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateValue(
                           (__int64 **)this,
                           v23,
                           a5,
                           a7,
                           (struct IXMLDOMElement *)a8,
                           v21),
          XMLAttribute < 0)
      || !a9 )
    {
      v14 = v23;
    }
    else
    {
      v14 = v23;
      v19 = 0;
      if ( v23 )
      {
        v19 = v23;
        v14 = 0;
        v23 = 0;
      }
      *a9 = v19;
    }
    if ( !v18 )
      goto LABEL_7;
    SysFreeString(v18);
  }
  v14 = v23;
LABEL_7:
  if ( v14 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v14->lpVtbl->Release)(v14);
  return (unsigned int)XMLAttribute;
}

```

## disassembly

```asm
0x180006b10  mov     [rsp-18h+arg_0], rbx
0x180006b15  mov     [rsp-18h+arg_8], rsi
0x180006b1a  push    rbp
0x180006b1b  push    rdi
0x180006b1c  push    r14
0x180006b1e  mov     rbp, rsp
0x180006b21  sub     rsp, 40h
0x180006b25  mov     [rbp+arg_18], 0
0x180006b2d  mov     r14, r9
0x180006b30  mov     rdi, r8
0x180006b33  mov     rsi, rcx
0x180006b36  test    r9, r9
0x180006b39  jz      short loc_180006BA0
0x180006b3b  test    r8, r8
0x180006b3e  jz      short loc_180006BA0
0x180006b40  test    rdx, rdx
0x180006b43  jz      loc_180006C43
0x180006b49  cmp     [rbp+arg_28], 0
0x180006b4d  lea     r8, aScoredproperty_0; "ScoredProperty"
0x180006b54  jz      loc_180006C60
0x180006b5a  lea     rax, [rbp+arg_18]
0x180006b5e  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x180006b63  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180006b68  mov     [rbp+bstrString], 0
0x180006b70  mov     ebx, eax
0x180006b72  test    eax, eax
0x180006b74  jns     short loc_180006BA7
0x180006b76  mov     rcx, [rbp+arg_18]
0x180006b7a  test    rcx, rcx
0x180006b7d  jz      short loc_180006B8B
0x180006b7f  mov     rax, [rcx]
0x180006b82  mov     rax, [rax+10h]
0x180006b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b8b  mov     eax, ebx
0x180006b8d  mov     rbx, [rsp+40h+arg_0]
0x180006b92  mov     rsi, [rsp+40h+arg_8]
0x180006b97  add     rsp, 40h
0x180006b9b  pop     r14
0x180006b9d  pop     rdi
0x180006b9e  pop     rbp
0x180006b9f  retn
0x180006ba0  mov     eax, 80070057h
0x180006ba5  jmp     short loc_180006B8D
0x180006ba7  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x180006bab  lea     rax, [rbp+bstrString]
0x180006baf  mov     r9, rdi; unsigned __int16 *
0x180006bb2  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x180006bb7  mov     r8, r14; struct IXMLDOMElement *
0x180006bba  mov     rcx, rsi; this
0x180006bbd  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x180006bc2  mov     rdi, [rbp+bstrString]
0x180006bc6  mov     ebx, eax
0x180006bc8  test    eax, eax
0x180006bca  jns     short loc_180006BE0
0x180006bcc  mov     rcx, [rbp+arg_18]
0x180006bd0  test    rdi, rdi
0x180006bd3  jz      short loc_180006B7A
0x180006bd5  mov     rcx, rdi; bstrString
0x180006bd8  call    cs:__imp_SysFreeString
0x180006bde  jmp     short loc_180006B76
0x180006be0  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x180006be4  lea     r8, aName; "name"
0x180006beb  mov     r9, rdi; unsigned __int16 *
0x180006bee  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180006bf3  mov     ebx, eax
0x180006bf5  test    eax, eax
0x180006bf7  js      short loc_180006BCC
0x180006bf9  mov     r8, [rbp+arg_20]; unsigned __int16 *
0x180006bfd  test    r8, r8
0x180006c00  jz      short loc_180006C21
0x180006c02  mov     rax, [rbp+arg_38]
0x180006c06  mov     rcx, rsi; this
0x180006c09  mov     r9, [rbp+arg_30]; unsigned __int16 *
0x180006c0d  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x180006c11  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x180006c16  call    ?CreateValue@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG11PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateValue(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180006c1b  mov     ebx, eax
0x180006c1d  test    eax, eax
0x180006c1f  js      short loc_180006BCC
0x180006c21  mov     rax, [rbp+arg_40]
0x180006c25  test    rax, rax
0x180006c28  jz      short loc_180006BCC
0x180006c2a  mov     rcx, [rbp+arg_18]
0x180006c2e  xor     edx, edx
0x180006c30  test    rcx, rcx
0x180006c33  jz      short loc_180006C3E
0x180006c35  mov     rdx, rcx
0x180006c38  xor     ecx, ecx
0x180006c3a  mov     [rbp+arg_18], rcx
0x180006c3e  mov     [rax], rdx
0x180006c41  jmp     short loc_180006BD0
0x180006c43  cmp     [rbp+arg_28], 0
0x180006c47  jz      short loc_180006C5C
0x180006c49  lea     rcx, [rbp+arg_18]
0x180006c4d  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180006c52  mov     eax, 8000FFFFh
0x180006c57  jmp     loc_180006B8D
0x180006c5c  mov     rdx, [rcx+18h]
0x180006c60  lea     r8, aProperty; "Property"
0x180006c67  jmp     loc_180006B5A
```
