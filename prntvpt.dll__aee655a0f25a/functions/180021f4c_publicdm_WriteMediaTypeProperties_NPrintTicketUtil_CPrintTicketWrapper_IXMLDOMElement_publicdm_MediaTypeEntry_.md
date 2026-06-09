# publicdm::WriteMediaTypeProperties(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,publicdm::MediaTypeEntry *,IXMLDOMElement *)

- ea: `0x180021f4c`
- end: `0x18002208b`
- name: `?WriteMediaTypeProperties@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUMediaTypeEntry@1@1@Z`
- size: `319`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, struct publicdm::MediaTypeEntry *, struct IXMLDOMElement *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021ebc`

## callees

- `0x18001c37c`
- `0x180021f4c`

## string_xrefs

- `0x180021f5b`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::WriteMediaTypeProperties(
        publicdm *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3,
        struct IXMLDOMElement *a4)
{
  struct IXMLDOMElement *lpVtbl; // rax
  __int64 result; // rax
  struct IXMLDOMElement *v9; // rax
  struct IXMLDOMElement *v10; // rax
  struct IXMLDOMElement **v11; // [rsp+38h] [rbp-30h]
  struct IXMLDOMElement **v12; // [rsp+38h] [rbp-30h]
  struct IXMLDOMElement **v13; // [rsp+38h] [rbp-30h]

  lpVtbl = (struct IXMLDOMElement *)a3[2].lpVtbl;
  if ( !lpVtbl
    || (result = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                   this,
                   a4,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"BackCoating",
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   lpVtbl,
                   1,
                   v11),
        (int)result >= 0) )
  {
    v9 = (struct IXMLDOMElement *)a3[3].lpVtbl;
    if ( !v9
      || (result = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                     this,
                     a4,
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     L"FrontCoating",
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     v9,
                     1,
                     v11),
          (int)result >= 0) )
    {
      v10 = (struct IXMLDOMElement *)a3[4].lpVtbl;
      if ( !v10
        || (result = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                       this,
                       a4,
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                       L"Material",
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                       v10,
                       1,
                       v11),
            (int)result >= 0) )
      {
        result = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                   this,
                   a4,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"PrePrinted",
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   (struct IXMLDOMElement *)L"None",
                   1,
                   v11);
        if ( (int)result >= 0 )
        {
          result = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                     this,
                     a4,
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     L"PrePunched",
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     (struct IXMLDOMElement *)L"None",
                     1,
                     v12);
          if ( (int)result >= 0 )
            return NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                     this,
                     a4,
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     L"Recycled",
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     (struct IXMLDOMElement *)L"None",
                     1,
                     v13);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021f4c  push    rbx
0x180021f4e  push    rbp
0x180021f4f  push    rsi
0x180021f50  push    rdi
0x180021f51  push    r14
0x180021f53  sub     rsp, 40h
0x180021f57  mov     rax, [r8+10h]
0x180021f5b  lea     rbp, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180021f62  mov     rdi, r9
0x180021f65  mov     rbx, r8
0x180021f68  mov     rsi, rcx
0x180021f6b  mov     r14d, 1
0x180021f71  test    rax, rax
0x180021f74  jz      short loc_180021F9F
0x180021f76  mov     [rsp+68h+var_38], r14d; int
0x180021f7b  lea     r9, aBackcoating; "BackCoating"
0x180021f82  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180021f87  mov     r8, rbp; unsigned __int16 *
0x180021f8a  mov     rdx, rdi; struct IXMLDOMElement *
0x180021f8d  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x180021f92  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180021f97  test    eax, eax
0x180021f99  js      loc_180022080
0x180021f9f  mov     rax, [rbx+18h]
0x180021fa3  test    rax, rax
0x180021fa6  jz      short loc_180021FD4
0x180021fa8  mov     [rsp+68h+var_38], r14d; int
0x180021fad  lea     r9, aFrontcoating; "FrontCoating"
0x180021fb4  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180021fb9  mov     r8, rbp; unsigned __int16 *
0x180021fbc  mov     rdx, rdi; struct IXMLDOMElement *
0x180021fbf  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x180021fc4  mov     rcx, rsi; this
0x180021fc7  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180021fcc  test    eax, eax
0x180021fce  js      loc_180022080
0x180021fd4  mov     rax, [rbx+20h]
0x180021fd8  test    rax, rax
0x180021fdb  jz      short loc_180022005
0x180021fdd  mov     [rsp+68h+var_38], r14d; int
0x180021fe2  lea     r9, aMaterial; "Material"
0x180021fe9  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180021fee  mov     r8, rbp; unsigned __int16 *
0x180021ff1  mov     rdx, rdi; struct IXMLDOMElement *
0x180021ff4  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x180021ff9  mov     rcx, rsi; this
0x180021ffc  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180022001  test    eax, eax
0x180022003  js      short loc_180022080
0x180022005  mov     [rsp+68h+var_38], r14d; int
0x18002200a  lea     rbx, aNone_0; "None"
0x180022011  mov     [rsp+68h+var_40], rbx; unsigned __int16 *
0x180022016  lea     r9, aPreprinted; "PrePrinted"
0x18002201d  mov     r8, rbp; unsigned __int16 *
0x180022020  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x180022025  mov     rdx, rdi; struct IXMLDOMElement *
0x180022028  mov     rcx, rsi; this
0x18002202b  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180022030  test    eax, eax
0x180022032  js      short loc_180022080
0x180022034  mov     [rsp+68h+var_38], r14d; int
0x180022039  lea     r9, aPrepunched; "PrePunched"
0x180022040  mov     [rsp+68h+var_40], rbx; unsigned __int16 *
0x180022045  mov     r8, rbp; unsigned __int16 *
0x180022048  mov     rdx, rdi; struct IXMLDOMElement *
0x18002204b  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x180022050  mov     rcx, rsi; this
0x180022053  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180022058  test    eax, eax
0x18002205a  js      short loc_180022080
0x18002205c  mov     [rsp+68h+var_38], r14d; int
0x180022061  lea     r9, aRecycled; "Recycled"
0x180022068  mov     [rsp+68h+var_40], rbx; unsigned __int16 *
0x18002206d  mov     r8, rbp; unsigned __int16 *
0x180022070  mov     rdx, rdi; struct IXMLDOMElement *
0x180022073  mov     [rsp+68h+var_48], rbp; unsigned __int16 *
0x180022078  mov     rcx, rsi; this
0x18002207b  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180022080  add     rsp, 40h
0x180022084  pop     r14
0x180022086  pop     rdi
0x180022087  pop     rsi
0x180022088  pop     rbp
0x180022089  pop     rbx
0x18002208a  retn
```
