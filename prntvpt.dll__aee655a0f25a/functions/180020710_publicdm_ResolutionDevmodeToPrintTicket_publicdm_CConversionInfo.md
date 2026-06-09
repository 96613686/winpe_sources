# publicdm::ResolutionDevmodeToPrintTicket(publicdm::CConversionInfo &)

- ea: `0x180020710`
- end: `0x180020901`
- name: `?ResolutionDevmodeToPrintTicket@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `497`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006f80`
- `0x18000b0a0`
- `0x18000e084`
- `0x18001c37c`
- `0x180020710`

## string_xrefs

- `0x1800207a0`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180020832`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::ResolutionDevmodeToPrintTicket(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  __int64 v2; // rax
  int Property; // ebx
  __int16 v5; // r15
  const unsigned __int16 *v6; // rsi
  int v7; // edx
  const unsigned __int16 *v8; // r9
  int v9; // eax
  const unsigned __int16 *v10; // r9
  struct IXMLDOMElement **v12; // [rsp+30h] [rbp-10h]
  struct IXMLDOMElement **v13; // [rsp+30h] [rbp-10h]
  struct IXMLDOMElement **v14; // [rsp+38h] [rbp-8h]
  struct IXMLDOMElement *v15; // [rsp+70h] [rbp+30h] BYREF
  struct IXMLDOMElement *v16; // [rsp+78h] [rbp+38h] BYREF

  v2 = *((_QWORD *)this + 2);
  v15 = 0;
  Property = 0;
  v16 = 0;
  if ( (*(_DWORD *)(v2 + 72) & 0x400) != 0 )
  {
    v5 = *(_WORD *)(v2 + 90);
    if ( v5 >= 0 )
    {
      if ( (*(_DWORD *)(v2 + 72) & 0x2000) != 0 )
        v5 = *(_WORD *)(v2 + 96);
      Property = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                   *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                   0,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"PageResolution",
                   &v16);
      if ( Property >= 0 )
      {
        Property = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
                     *((__int64 ***)this + 12),
                     v16,
                     (struct IXMLDOMElement *)L"Option",
                     v10,
                     &v15);
        if ( Property >= 0 )
        {
          Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                       *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                       v15,
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                       L"ResolutionX",
                       *(__int16 *)(*((_QWORD *)this + 2) + 90LL),
                       1,
                       v12);
          if ( Property >= 0 )
          {
            v9 = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                   *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                   v15,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"ResolutionY",
                   v5,
                   1,
                   v13);
            goto LABEL_18;
          }
        }
      }
    }
    else
    {
      v6 = 0;
      v7 = 0;
      while ( !v6 )
      {
        if ( v5 == *(&qword_180025440 + 12 * v7) )
          v6 = (const unsigned __int16 *)*((_QWORD *)&qword_180025440 + 3 * v7 + 1);
        if ( !*(&qword_180025440 + 12 * ++v7) )
        {
          if ( !v6 )
            goto LABEL_19;
          break;
        }
      }
      Property = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                   *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                   0,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"PageResolution",
                   &v16);
      if ( Property >= 0 )
      {
        Property = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
                     *((__int64 ***)this + 12),
                     v16,
                     (struct IXMLDOMElement *)L"Option",
                     v8,
                     &v15);
        if ( Property >= 0 )
        {
          v9 = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                 *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                 v15,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 L"QualitativeResolution",
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 v6,
                 1,
                 v14);
LABEL_18:
          Property = v9;
        }
      }
    }
  }
LABEL_19:
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v15);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v16);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180020710  mov     [rsp-28h+arg_10], rbx
0x180020715  mov     [rsp-28h+arg_18], rsi
0x18002071a  push    rbp
0x18002071b  push    rdi
0x18002071c  push    r12
0x18002071e  push    r14
0x180020720  push    r15
0x180020722  mov     rbp, rsp
0x180020725  sub     rsp, 40h
0x180020729  mov     rax, [rcx+10h]
0x18002072d  xor     r12d, r12d
0x180020730  mov     [rbp+arg_0], r12
0x180020734  mov     rdi, rcx
0x180020737  mov     ebx, r12d
0x18002073a  mov     [rbp+arg_8], r12
0x18002073e  test    dword ptr [rax+48h], 400h
0x180020745  jz      loc_1800208D4
0x18002074b  movzx   r15d, word ptr [rax+5Ah]
0x180020750  test    r15w, r15w
0x180020754  jns     loc_18002081C
0x18002075a  mov     esi, r12d
0x18002075d  lea     r8, qword_180025440
0x180020764  mov     edx, r12d
0x180020767  test    rsi, rsi
0x18002076a  jnz     short loc_180020798
0x18002076c  movsxd  rax, edx
0x18002076f  lea     rcx, [rax+rax*2]
0x180020773  cmp     r15w, [r8+rcx*8]
0x180020778  jnz     short loc_18002077F
0x18002077a  mov     rsi, [r8+rcx*8+8]
0x18002077f  inc     edx
0x180020781  movsxd  rax, edx
0x180020784  lea     rcx, [rax+rax*2]
0x180020788  cmp     [r8+rcx*8], r12w
0x18002078d  jnz     short loc_180020767
0x18002078f  test    rsi, rsi
0x180020792  jz      loc_1800208D4
0x180020798  mov     rcx, [rdi+60h]; this
0x18002079c  lea     rax, [rbp+arg_8]
0x1800207a0  lea     r14, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x1800207a7  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x1800207ac  mov     r8, r14; unsigned __int16 *
0x1800207af  lea     r9, aPageresolution; "PageResolution"
0x1800207b6  xor     edx, edx; struct IXMLDOMElement *
0x1800207b8  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800207bd  mov     ebx, eax
0x1800207bf  test    eax, eax
0x1800207c1  js      loc_1800208D4
0x1800207c7  mov     rdx, [rbp+arg_8]; struct IXMLDOMElement *
0x1800207cb  lea     rax, [rbp+arg_0]
0x1800207cf  mov     rcx, [rdi+60h]; this
0x1800207d3  lea     r8, aOption; "Option"
0x1800207da  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x1800207df  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800207e4  mov     ebx, eax
0x1800207e6  test    eax, eax
0x1800207e8  js      loc_1800208D4
0x1800207ee  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x1800207f2  lea     r9, aQualitativeres; "QualitativeResolution"
0x1800207f9  mov     rcx, [rdi+60h]; this
0x1800207fd  mov     r8, r14; unsigned __int16 *
0x180020800  mov     dword ptr [rsp+40h+var_10], 1; int
0x180020808  mov     [rsp+40h+var_18], rsi; unsigned __int16 *
0x18002080d  mov     [rsp+40h+var_20], r14; unsigned __int16 *
0x180020812  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180020817  jmp     loc_1800208D2
0x18002081c  test    dword ptr [rax+48h], 2000h
0x180020823  jz      short loc_18002082A
0x180020825  movzx   r15d, word ptr [rax+60h]
0x18002082a  mov     rcx, [rcx+60h]; this
0x18002082e  lea     rax, [rbp+arg_8]
0x180020832  lea     r14, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180020839  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x18002083e  mov     r8, r14; unsigned __int16 *
0x180020841  lea     r9, aPageresolution; "PageResolution"
0x180020848  xor     edx, edx; struct IXMLDOMElement *
0x18002084a  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18002084f  mov     ebx, eax
0x180020851  test    eax, eax
0x180020853  js      short loc_1800208D4
0x180020855  mov     rdx, [rbp+arg_8]; struct IXMLDOMElement *
0x180020859  lea     rax, [rbp+arg_0]
0x18002085d  mov     rcx, [rdi+60h]; this
0x180020861  lea     r8, aOption; "Option"
0x180020868  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x18002086d  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180020872  mov     ebx, eax
0x180020874  test    eax, eax
0x180020876  js      short loc_1800208D4
0x180020878  mov     rax, [rdi+10h]
0x18002087c  lea     r9, aResolutionx; "ResolutionX"
0x180020883  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x180020887  mov     rcx, [rdi+60h]; this
0x18002088b  mov     dword ptr [rsp+40h+var_18], 1; int
0x180020893  movsx   r8d, word ptr [rax+5Ah]
0x180020898  mov     dword ptr [rsp+40h+var_20], r8d; int
0x18002089d  mov     r8, r14; unsigned __int16 *
0x1800208a0  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800208a5  mov     ebx, eax
0x1800208a7  test    eax, eax
0x1800208a9  js      short loc_1800208D4
0x1800208ab  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x1800208af  lea     r9, aResolutiony; "ResolutionY"
0x1800208b6  mov     rcx, [rdi+60h]; this
0x1800208ba  mov     r8, r14; unsigned __int16 *
0x1800208bd  movsx   eax, r15w
0x1800208c1  mov     dword ptr [rsp+40h+var_18], 1; int
0x1800208c9  mov     dword ptr [rsp+40h+var_20], eax; int
0x1800208cd  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x1800208d2  mov     ebx, eax
0x1800208d4  lea     rcx, [rbp+arg_0]
0x1800208d8  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x1800208dd  lea     rcx, [rbp+arg_8]
0x1800208e1  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x1800208e6  lea     r11, [rsp+40h+var_s0]
0x1800208eb  mov     eax, ebx
0x1800208ed  mov     rbx, [r11+40h]
0x1800208f1  mov     rsi, [r11+48h]
0x1800208f5  mov     rsp, r11
0x1800208f8  pop     r15
0x1800208fa  pop     r14
0x1800208fc  pop     r12
0x1800208fe  pop     rdi
0x1800208ff  pop     rbp
0x180020900  retn
```
