# NPrintTicketUtil::CPrintTicketWrapper::CreateParameterInitializer(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x180007a04`
- end: `0x180007b1f`
- name: `?CreateParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0000PEAPEAUIXMLDOMElement@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *this, const unsigned __int16 *, struct IXMLDOMElement *, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001c1e8`
- `0x18001fb60`

## callees

- `0x180006d70`
- `0x180006f80`
- `0x1800070e0`
- `0x1800076e8`
- `0x180007a04`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180007af5`
- `OLEAUT32!__imp_SysFreeString` at `0x180007af5`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateParameterInitializer(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        const unsigned __int16 *a2,
        struct IXMLDOMElement *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        struct IXMLDOMElement **a7)
{
  struct IXMLDOMElement *v12; // rdx
  int XMLAttribute; // ebx
  int QName; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v15; // rcx
  OLECHAR *v16; // rdi
  struct IXMLDOMElement *v17; // rcx
  struct IXMLDOMElement *v18; // rdx
  unsigned __int16 **v19; // [rsp+28h] [rbp-20h]
  struct IXMLDOMElement **v20; // [rsp+28h] [rbp-20h]
  BSTR bstrString[3]; // [rsp+30h] [rbp-18h] BYREF
  struct IXMLDOMElement *v22; // [rsp+90h] [rbp+48h] BYREF

  if ( !a3 )
    return 2147942487LL;
  v12 = (struct IXMLDOMElement *)*((_QWORD *)this + 3);
  v22 = 0;
  bstrString[0] = 0;
  XMLAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(this, v12, L"ParameterInit", a4, &v22);
  if ( XMLAttribute >= 0 )
  {
    QName = NPrintTicketUtil::CreateQName(this, v22, a3, a2, (const unsigned __int16 *)bstrString, v19, bstrString[0]);
    v16 = bstrString[0];
    XMLAttribute = QName;
    if ( QName < 0
      || (XMLAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(v15, v22, L"name", bstrString[0]),
          XMLAttribute < 0)
      || a4
      && (XMLAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateValue(this, v22, a4, a5, a6, v20), XMLAttribute < 0)
      || !a7 )
    {
      v17 = v22;
    }
    else
    {
      v17 = v22;
      v18 = 0;
      if ( v22 )
      {
        v18 = v22;
        v17 = 0;
        v22 = 0;
      }
      *a7 = v18;
    }
    if ( !v16 )
      goto LABEL_16;
    SysFreeString(v16);
  }
  v17 = v22;
LABEL_16:
  if ( v17 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v17->lpVtbl->Release)(v17);
  return (unsigned int)XMLAttribute;
}

```

## disassembly

```asm
0x180007a04  push    rbp
0x180007a06  push    rbx
0x180007a07  push    rsi
0x180007a08  push    rdi
0x180007a09  push    r14
0x180007a0b  push    r15
0x180007a0d  mov     rbp, rsp
0x180007a10  sub     rsp, 48h
0x180007a14  mov     r14, r9
0x180007a17  mov     rdi, r8
0x180007a1a  mov     r15, rdx
0x180007a1d  mov     rsi, rcx
0x180007a20  test    r8, r8
0x180007a23  jnz     short loc_180007A2F
0x180007a25  mov     eax, 80070057h
0x180007a2a  jmp     loc_180007B12
0x180007a2f  mov     rdx, [rcx+18h]; struct IXMLDOMElement *
0x180007a33  lea     rax, [rbp+arg_10]
0x180007a37  lea     r8, aParameterinit; "ParameterInit"
0x180007a3e  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x180007a43  mov     [rbp+arg_10], 0
0x180007a4b  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180007a50  mov     [rbp+bstrString], 0
0x180007a58  mov     ebx, eax
0x180007a5a  test    eax, eax
0x180007a5c  js      loc_180007AFB
0x180007a62  mov     rdx, [rbp+arg_10]; struct IXMLDOMElement *
0x180007a66  lea     rax, [rbp+bstrString]
0x180007a6a  mov     r9, r15; unsigned __int16 *
0x180007a6d  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180007a72  mov     r8, rdi; struct IXMLDOMElement *
0x180007a75  mov     rcx, rsi; this
0x180007a78  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x180007a7d  mov     rdi, [rbp+bstrString]
0x180007a81  mov     ebx, eax
0x180007a83  test    eax, eax
0x180007a85  js      short loc_180007AE9
0x180007a87  mov     rdx, [rbp+arg_10]; struct IXMLDOMElement *
0x180007a8b  lea     r8, aName; "name"
0x180007a92  mov     r9, rdi; unsigned __int16 *
0x180007a95  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180007a9a  mov     ebx, eax
0x180007a9c  test    eax, eax
0x180007a9e  js      short loc_180007AE9
0x180007aa0  test    r14, r14
0x180007aa3  jz      short loc_180007AC7
0x180007aa5  mov     rax, [rbp+arg_28]
0x180007aa9  mov     r8, r14; unsigned __int16 *
0x180007aac  mov     r9, [rbp+arg_20]; unsigned __int16 *
0x180007ab0  mov     rcx, rsi; this
0x180007ab3  mov     rdx, [rbp+arg_10]; struct IXMLDOMElement *
0x180007ab7  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180007abc  call    ?CreateValue@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG11PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateValue(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180007ac1  mov     ebx, eax
0x180007ac3  test    eax, eax
0x180007ac5  js      short loc_180007AE9
0x180007ac7  mov     rax, [rbp+arg_30]
0x180007acb  test    rax, rax
0x180007ace  jz      short loc_180007AE9
0x180007ad0  mov     rcx, [rbp+arg_10]
0x180007ad4  xor     edx, edx
0x180007ad6  test    rcx, rcx
0x180007ad9  jz      short loc_180007AE4
0x180007adb  mov     rdx, rcx
0x180007ade  xor     ecx, ecx
0x180007ae0  mov     [rbp+arg_10], rcx
0x180007ae4  mov     [rax], rdx
0x180007ae7  jmp     short loc_180007AED
0x180007ae9  mov     rcx, [rbp+arg_10]
0x180007aed  test    rdi, rdi
0x180007af0  jz      short loc_180007AFF
0x180007af2  mov     rcx, rdi; bstrString
0x180007af5  call    cs:__imp_SysFreeString
0x180007afb  mov     rcx, [rbp+arg_10]
0x180007aff  test    rcx, rcx
0x180007b02  jz      short loc_180007B10
0x180007b04  mov     rax, [rcx]
0x180007b07  mov     rax, [rax+10h]
0x180007b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b10  mov     eax, ebx
0x180007b12  add     rsp, 48h
0x180007b16  pop     r15
0x180007b18  pop     r14
0x180007b1a  pop     rdi
0x180007b1b  pop     rsi
0x180007b1c  pop     rbx
0x180007b1d  pop     rbp
0x180007b1e  retn
```
