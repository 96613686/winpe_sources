# WriteMediaType(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,publicdm::MediaTypeEntry *,IXMLDOMElement * *)

- ea: `0x180021ebc`
- end: `0x180021f43`
- name: `?WriteMediaType@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUMediaTypeEntry@publicdm@@PEAPEAU3@@Z`
- size: `135`
- prototype: `__int64 __fastcall(struct NPrintTicketUtil::CPrintTicketWrapper *this, struct IXMLDOMElement *, struct publicdm::MediaTypeEntry *, struct IXMLDOMElement **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b5a0`
- `0x18001ecf0`

## callees

- `0x180005e70`
- `0x180006c74`
- `0x180021ebc`
- `0x180021f4c`

## string_xrefs

- `0x180021ee3`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall WriteMediaType(
        struct NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 **a3,
        struct IXMLDOMElement **a4)
{
  struct NPrintTicketUtil::CPrintTicketWrapper *v7; // rdx
  int Option; // edi
  struct IXMLDOMElement *lpVtbl; // rax
  struct IXMLDOMElement **v11; // [rsp+20h] [rbp-48h]
  struct IXMLDOMElement v12; // [rsp+30h] [rbp-38h] BYREF

  v12.lpVtbl = 0;
  Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
             this,
             a2,
             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
             a3[1],
             (struct IXMLDOMElement **)&v12);
  if ( Option >= 0 )
  {
    Option = publicdm::WriteMediaTypeProperties(
               this,
               v7,
               (struct IXMLDOMElement *)a3,
               (struct publicdm::MediaTypeEntry *)v12.lpVtbl,
               (struct IXMLDOMElement *)v11);
    if ( Option >= 0 )
    {
      if ( a4 )
      {
        lpVtbl = 0;
        if ( v12.lpVtbl )
        {
          lpVtbl = (struct IXMLDOMElement *)v12.lpVtbl;
          v12.lpVtbl = 0;
        }
        *a4 = lpVtbl;
      }
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v12);
  return (unsigned int)Option;
}

```

## disassembly

```asm
0x180021ebc  push    rbp
0x180021ebe  push    rsi
0x180021ebf  push    rdi
0x180021ec0  push    r14
0x180021ec2  sub     rsp, 48h
0x180021ec6  mov     rsi, r9
0x180021ec9  mov     [rsp+68h+var_38.lpVtbl], 0
0x180021ed2  mov     r9, [r8+8]; unsigned __int16 *
0x180021ed6  lea     rax, [rsp+68h+var_38]
0x180021edb  mov     rbp, r8
0x180021ede  mov     [rsp+68h+var_48], rax; struct IXMLDOMElement *
0x180021ee3  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180021eea  mov     r14, rcx
0x180021eed  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021ef2  mov     edi, eax
0x180021ef4  test    eax, eax
0x180021ef6  js      short loc_180021F2D
0x180021ef8  mov     r9, [rsp+68h+var_38.lpVtbl]; struct publicdm::MediaTypeEntry *
0x180021efd  mov     r8, rbp; struct IXMLDOMElement *
0x180021f00  mov     rcx, r14; this
0x180021f03  call    ?WriteMediaTypeProperties@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUMediaTypeEntry@1@1@Z; publicdm::WriteMediaTypeProperties(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,publicdm::MediaTypeEntry *,IXMLDOMElement *)
0x180021f08  mov     edi, eax
0x180021f0a  test    eax, eax
0x180021f0c  js      short loc_180021F2D
0x180021f0e  test    rsi, rsi
0x180021f11  jz      short loc_180021F2D
0x180021f13  xor     eax, eax
0x180021f15  cmp     [rsp+68h+var_38.lpVtbl], rax
0x180021f1a  jz      short loc_180021F2A
0x180021f1c  mov     rax, [rsp+68h+var_38.lpVtbl]
0x180021f21  mov     [rsp+68h+var_38.lpVtbl], 0
0x180021f2a  mov     [rsi], rax
0x180021f2d  lea     rcx, [rsp+68h+var_38]
0x180021f32  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021f37  mov     eax, edi
0x180021f39  add     rsp, 48h
0x180021f3d  pop     r14
0x180021f3f  pop     rdi
0x180021f40  pop     rsi
0x180021f41  pop     rbp
0x180021f42  retn
```
