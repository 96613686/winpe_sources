# publicdm::WriteInputBinProperties(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,publicdm::BinMappingEntry *)

- ea: `0x180021dfc`
- end: `0x180021eb5`
- name: `?WriteInputBinProperties@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUBinMappingEntry@1@@Z`
- size: `185`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct IXMLDOMElement *, struct IXMLDOMElement *, struct publicdm::BinMappingEntry *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c514`

## callees

- `0x18001c37c`
- `0x180021dfc`

## string_xrefs

- `0x180021e08`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::WriteInputBinProperties(
        publicdm *this,
        struct IXMLDOMElement *a2,
        struct IXMLDOMElement *a3,
        struct publicdm::BinMappingEntry *a4)
{
  struct IXMLDOMElement *lpVtbl; // rcx
  __int64 result; // rax
  struct IXMLDOMElement *v9; // rcx
  struct IXMLDOMElement *v10; // rcx
  struct IXMLDOMElement **v11; // [rsp+38h] [rbp-30h]

  lpVtbl = (struct IXMLDOMElement *)a3[3].lpVtbl;
  result = 0;
  if ( !lpVtbl
    || (result = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                   this,
                   a2,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"BinType",
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   lpVtbl,
                   1,
                   v11),
        (int)result >= 0) )
  {
    v9 = (struct IXMLDOMElement *)a3[4].lpVtbl;
    if ( !v9
      || (result = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                     this,
                     a2,
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     L"FeedType",
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     v9,
                     1,
                     v11),
          (int)result >= 0) )
    {
      v10 = (struct IXMLDOMElement *)a3[5].lpVtbl;
      if ( v10 )
        return NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                 this,
                 a2,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 L"MediaCapacity",
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 v10,
                 1,
                 v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021dfc  push    rbx
0x180021dfe  push    rbp
0x180021dff  push    rsi
0x180021e00  push    rdi
0x180021e01  sub     rsp, 48h
0x180021e05  mov     rsi, rcx
0x180021e08  lea     rbp, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180021e0f  mov     rcx, [r8+18h]
0x180021e13  xor     eax, eax
0x180021e15  mov     rbx, r8
0x180021e18  mov     rdi, rdx
0x180021e1b  test    rcx, rcx
0x180021e1e  jz      short loc_180021E48
0x180021e20  mov     [rsp+68h+var_38], 1; int
0x180021e28  lea     r9, aBintype; "BinType"
0x180021e2f  mov     [rsp+68h+var_40], rcx; unsigned __int16 *
0x180021e34  mov     r8, rbp; unsigned __int16 *
0x180021e37  mov     rcx, rsi; this
0x180021e3a  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x180021e3f  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180021e44  test    eax, eax
0x180021e46  js      short loc_180021EAC
0x180021e48  mov     rcx, [rbx+20h]
0x180021e4c  test    rcx, rcx
0x180021e4f  jz      short loc_180021E7C
0x180021e51  mov     [rsp+68h+var_38], 1; int
0x180021e59  lea     r9, aFeedtype; "FeedType"
0x180021e60  mov     [rsp+68h+var_40], rcx; unsigned __int16 *
0x180021e65  mov     r8, rbp; unsigned __int16 *
0x180021e68  mov     rcx, rsi; this
0x180021e6b  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x180021e70  mov     rdx, rdi; struct IXMLDOMElement *
0x180021e73  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180021e78  test    eax, eax
0x180021e7a  js      short loc_180021EAC
0x180021e7c  mov     rcx, [rbx+28h]
0x180021e80  test    rcx, rcx
0x180021e83  jz      short loc_180021EAC
0x180021e85  mov     [rsp+68h+var_38], 1; int
0x180021e8d  lea     r9, aMediacapacity; "MediaCapacity"
0x180021e94  mov     [rsp+68h+var_40], rcx; unsigned __int16 *
0x180021e99  mov     r8, rbp; unsigned __int16 *
0x180021e9c  mov     rcx, rsi; this
0x180021e9f  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x180021ea4  mov     rdx, rdi; struct IXMLDOMElement *
0x180021ea7  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180021eac  add     rsp, 48h
0x180021eb0  pop     rdi
0x180021eb1  pop     rsi
0x180021eb2  pop     rbp
0x180021eb3  pop     rbx
0x180021eb4  retn
```
