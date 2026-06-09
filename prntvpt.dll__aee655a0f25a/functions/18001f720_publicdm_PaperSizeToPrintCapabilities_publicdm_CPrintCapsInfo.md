# publicdm::PaperSizeToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x18001f720`
- end: `0x18001f7b6`
- name: `?PaperSizeToPrintCapabilities@publicdm@@YAJAEAVCPrintCapsInfo@1@@Z`
- size: `150`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CPrintCapsInfo *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006344`
- `0x18000be14`
- `0x18000e084`
- `0x18001f720`
- `0x18001fcc4`

## string_xrefs

- `0x18001f74a`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::PaperSizeToPrintCapabilities(publicdm *this, struct publicdm::CPrintCapsInfo *a2)
{
  int Feature; // ebx
  struct NPrintTicketUtil::CPrintTicketWrapper *v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  Feature = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
              *((NPrintTicketUtil::CPrintTicketWrapper **)this + 14),
              0,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              L"PageMediaSize",
              (struct IXMLDOMElement **)&v5);
  if ( Feature >= 0 )
  {
    Feature = publicdm::WriteDisplayNameFromResourceString(
                *((publicdm **)this + 14),
                v5,
                *((struct IXMLDOMElement **)this + 12),
                (HINSTANCE)0xFCEB);
    if ( Feature >= 0 )
    {
      Feature = CreateStandardPaperSizes(this, &v5);
      if ( Feature >= 0 && !*((_DWORD *)this + 16) )
        Feature = PrintableAreaToPrintCapabilities(this);
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v5);
  return (unsigned int)Feature;
}

```

## disassembly

```asm
0x18001f720  mov     r11, rsp
0x18001f723  mov     [r11+8], rbx
0x18001f727  push    rdi
0x18001f728  sub     rsp, 30h
0x18001f72c  mov     rdi, rcx
0x18001f72f  mov     qword ptr [r11+10h], 0
0x18001f737  mov     rcx, [rcx+70h]; this
0x18001f73b  lea     rax, [r11+10h]
0x18001f73f  lea     r9, aPagemediasize; "PageMediaSize"
0x18001f746  mov     [r11-18h], rax
0x18001f74a  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001f751  xor     edx, edx; struct IXMLDOMElement *
0x18001f753  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001f758  mov     ebx, eax
0x18001f75a  test    eax, eax
0x18001f75c  js      short loc_18001F79F
0x18001f75e  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x18001f762  mov     r9d, 0FCEBh; HINSTANCE
0x18001f768  mov     rdx, [rsp+38h+arg_8]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001f76d  mov     rcx, [rdi+70h]; this
0x18001f771  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001f776  mov     ebx, eax
0x18001f778  test    eax, eax
0x18001f77a  js      short loc_18001F79F
0x18001f77c  lea     rdx, [rsp+38h+arg_8]
0x18001f781  mov     rcx, rdi
0x18001f784  call    ?CreateStandardPaperSizes@@YAJAEAVCPrintCapsInfo@publicdm@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@@Z; CreateStandardPaperSizes(publicdm::CPrintCapsInfo &,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &)
0x18001f789  mov     ebx, eax
0x18001f78b  test    eax, eax
0x18001f78d  js      short loc_18001F79F
0x18001f78f  cmp     dword ptr [rdi+40h], 0
0x18001f793  jnz     short loc_18001F79F
0x18001f795  mov     rcx, rdi; struct publicdm::CPrintCapsInfo *
0x18001f798  call    ?PrintableAreaToPrintCapabilities@@YAJAEAVCPrintCapsInfo@publicdm@@@Z; PrintableAreaToPrintCapabilities(publicdm::CPrintCapsInfo &)
0x18001f79d  mov     ebx, eax
0x18001f79f  lea     rcx, [rsp+38h+arg_8]
0x18001f7a4  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001f7a9  mov     eax, ebx
0x18001f7ab  mov     rbx, [rsp+38h+arg_0]
0x18001f7b0  add     rsp, 30h
0x18001f7b4  pop     rdi
0x18001f7b5  retn
```
