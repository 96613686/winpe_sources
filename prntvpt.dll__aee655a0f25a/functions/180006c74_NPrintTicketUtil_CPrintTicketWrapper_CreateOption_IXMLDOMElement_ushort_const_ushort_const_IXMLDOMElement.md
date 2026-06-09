# NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x180006c74`
- end: `0x180006d68`
- name: `?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z`
- size: `244`
- prototype: `__int64 __usercall@<rax>(NPrintTicketUtil::CPrintTicketWrapper *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct IXMLDOMElement **)`
- caller_count: `22`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006130`
- `0x1800077f0`
- `0x18000b5a0`
- `0x18000c224`
- `0x18000e460`
- `0x18001b4b0`
- `0x18001b590`
- `0x18001b6f0`
- `0x18001bbac`
- `0x18001c46c`
- `0x18001c514`
- `0x18001c67c`
- `0x18001cdd0`
- `0x18001d090`
- `0x18001e3b0`
- `0x18001e520`
- `0x18001ecf0`
- `0x18001f070`
- `0x180020f00`
- `0x180021260`
- `0x180021900`
- `0x180021ebc`

## callees

- `0x180006c74`
- `0x180006f80`
- `0x1800070e0`
- `0x1800076e8`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006d38`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d38`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
        __int64 **this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IXMLDOMElement **a5)
{
  int XMLAttribute; // edi
  int QName; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v11; // rcx
  OLECHAR *v12; // rbx
  struct IXMLDOMElement *v13; // rcx
  struct IXMLDOMElement *v14; // rdx
  unsigned __int16 **v15; // [rsp+28h] [rbp-18h]
  BSTR bstrString[2]; // [rsp+30h] [rbp-10h] BYREF
  struct IXMLDOMElement *v17; // [rsp+68h] [rbp+28h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v17 = 0;
  bstrString[0] = 0;
  XMLAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
                   this,
                   a2,
                   (struct IXMLDOMElement *)L"Option",
                   a4,
                   &v17);
  if ( XMLAttribute >= 0 )
  {
    QName = NPrintTicketUtil::CreateQName(
              (NPrintTicketUtil *)this,
              v17,
              (struct IXMLDOMElement *)a4,
              a3,
              (const unsigned __int16 *)bstrString,
              v15,
              bstrString[0]);
    v12 = bstrString[0];
    XMLAttribute = QName;
    if ( QName >= 0
      && (XMLAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(v11, v17, L"name", bstrString[0]),
          XMLAttribute >= 0)
      && a5 )
    {
      v13 = v17;
      v14 = 0;
      if ( v17 )
      {
        v14 = v17;
        v13 = 0;
        v17 = 0;
      }
      *a5 = v14;
    }
    else
    {
      v13 = v17;
    }
    if ( !v12 )
      goto LABEL_14;
    SysFreeString(v12);
  }
  v13 = v17;
LABEL_14:
  if ( v13 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v13->lpVtbl->Release)(v13);
  return (unsigned int)XMLAttribute;
}

```

## disassembly

```asm
0x180006c74  mov     [rsp-18h+arg_0], rbx
0x180006c79  mov     [rsp-18h+arg_10], rsi
0x180006c7e  push    rbp
0x180006c7f  push    rdi
0x180006c80  push    r14
0x180006c82  mov     rbp, rsp
0x180006c85  sub     rsp, 40h
0x180006c89  mov     rsi, r9
0x180006c8c  mov     r14, r8
0x180006c8f  mov     rbx, rcx
0x180006c92  test    rdx, rdx
0x180006c95  jnz     short loc_180006CA1
0x180006c97  mov     eax, 80070057h
0x180006c9c  jmp     loc_180006D55
0x180006ca1  lea     rax, [rbp+arg_8]
0x180006ca5  mov     [rbp+arg_8], 0
0x180006cad  lea     r8, aOption; "Option"
0x180006cb4  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x180006cb9  mov     [rbp+bstrString], 0
0x180006cc1  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180006cc6  mov     edi, eax
0x180006cc8  test    eax, eax
0x180006cca  js      short loc_180006D3E
0x180006ccc  mov     rdx, [rbp+arg_8]; struct IXMLDOMElement *
0x180006cd0  lea     rax, [rbp+bstrString]
0x180006cd4  mov     r9, r14; unsigned __int16 *
0x180006cd7  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x180006cdc  mov     r8, rsi; struct IXMLDOMElement *
0x180006cdf  mov     rcx, rbx; this
0x180006ce2  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x180006ce7  mov     rbx, [rbp+bstrString]
0x180006ceb  mov     edi, eax
0x180006ced  test    eax, eax
0x180006cef  js      short loc_180006D2C
0x180006cf1  mov     rdx, [rbp+arg_8]; struct IXMLDOMElement *
0x180006cf5  lea     r8, aName; "name"
0x180006cfc  mov     r9, rbx; unsigned __int16 *
0x180006cff  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x180006d04  mov     edi, eax
0x180006d06  test    eax, eax
0x180006d08  js      short loc_180006D2C
0x180006d0a  mov     rax, [rbp+arg_20]
0x180006d0e  test    rax, rax
0x180006d11  jz      short loc_180006D2C
0x180006d13  mov     rcx, [rbp+arg_8]
0x180006d17  xor     edx, edx
0x180006d19  test    rcx, rcx
0x180006d1c  jz      short loc_180006D27
0x180006d1e  mov     rdx, rcx
0x180006d21  xor     ecx, ecx
0x180006d23  mov     [rbp+arg_8], rcx
0x180006d27  mov     [rax], rdx
0x180006d2a  jmp     short loc_180006D30
0x180006d2c  mov     rcx, [rbp+arg_8]
0x180006d30  test    rbx, rbx
0x180006d33  jz      short loc_180006D42
0x180006d35  mov     rcx, rbx; bstrString
0x180006d38  call    cs:__imp_SysFreeString
0x180006d3e  mov     rcx, [rbp+arg_8]
0x180006d42  test    rcx, rcx
0x180006d45  jz      short loc_180006D53
0x180006d47  mov     rax, [rcx]
0x180006d4a  mov     rax, [rax+10h]
0x180006d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d53  mov     eax, edi
0x180006d55  mov     rbx, [rsp+40h+arg_0]
0x180006d5a  mov     rsi, [rsp+40h+arg_10]
0x180006d5f  add     rsp, 40h
0x180006d63  pop     r14
0x180006d65  pop     rdi
0x180006d66  pop     rbp
0x180006d67  retn
```
