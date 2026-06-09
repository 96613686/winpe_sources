# publicdm::TrueTypeDevmodeToPrintTicket(publicdm::CConversionInfo &)

- ea: `0x180021900`
- end: `0x180021a4d`
- name: `?TrueTypeDevmodeToPrintTicket@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `333`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006c74`
- `0x18000e084`
- `0x180021900`

## string_xrefs

- `0x1800219a3`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x1800219bc`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x1800219f3`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180021a0c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::TrueTypeDevmodeToPrintTicket(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  __int64 v2; // rax
  int Option; // esi
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  const unsigned __int16 *v10; // rdi
  const unsigned __int16 *v11; // rbx
  struct IXMLDOMElement *v12; // [rsp+50h] [rbp+8h] BYREF
  struct IXMLDOMElement *v13; // [rsp+58h] [rbp+10h] BYREF

  v2 = *((_QWORD *)this + 2);
  Option = 0;
  if ( (*(_DWORD *)(v2 + 72) & 0x4000) != 0 )
  {
    v5 = *(__int16 *)(v2 + 98);
    v13 = 0;
    v12 = 0;
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( !v8 )
        {
          v11 = L"On";
          v10 = L"DownloadAsRasterFont";
          goto LABEL_12;
        }
        if ( v8 != 1 )
        {
          NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v12);
          NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v13);
          return 0;
        }
        v10 = L"DownloadAsOutlineFont";
      }
      else
      {
        v10 = L"DownloadAsRasterFont";
      }
    }
    else
    {
      v10 = L"RenderAsBitmap";
    }
    v11 = L"Off";
LABEL_12:
    Option = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
               *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
               0,
               L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
               L"PageTrueTypeFontMode",
               &v13);
    if ( Option >= 0 )
    {
      Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                 *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                 v13,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 v10,
                 0);
      if ( Option >= 0 )
      {
        Option = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                   *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                   0,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"PageDeviceFontSubstitution",
                   &v12);
        if ( Option >= 0 )
          Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                     *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                     v12,
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     v11,
                     0);
      }
    }
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v12);
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v13);
  }
  return (unsigned int)Option;
}

```

## disassembly

```asm
0x180021900  mov     r11, rsp
0x180021903  mov     [r11+18h], rbx
0x180021907  push    rbp
0x180021908  push    rsi
0x180021909  push    rdi
0x18002190a  sub     rsp, 30h
0x18002190e  mov     rax, [rcx+10h]
0x180021912  xor     esi, esi
0x180021914  mov     rbp, rcx
0x180021917  test    dword ptr [rax+48h], 4000h
0x18002191e  jz      loc_180021A3E
0x180021924  movsx   edx, word ptr [rax+62h]
0x180021928  mov     [r11+10h], rsi
0x18002192c  mov     [r11+8], rsi
0x180021930  sub     edx, 1
0x180021933  jz      short loc_180021980
0x180021935  sub     edx, 1
0x180021938  jz      short loc_180021977
0x18002193a  sub     edx, 1
0x18002193d  jz      short loc_180021967
0x18002193f  cmp     edx, 1
0x180021942  jz      short loc_18002195E
0x180021944  lea     rcx, [r11+8]
0x180021948  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18002194d  lea     rcx, [rsp+48h+arg_8]
0x180021952  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021957  xor     eax, eax
0x180021959  jmp     loc_180021A40
0x18002195e  lea     rdi, aDownloadasoutl; "DownloadAsOutlineFont"
0x180021965  jmp     short loc_180021987
0x180021967  lea     rbx, aOn; "On"
0x18002196e  lea     rdi, aDownloadasrast; "DownloadAsRasterFont"
0x180021975  jmp     short loc_18002198E
0x180021977  lea     rdi, aDownloadasrast; "DownloadAsRasterFont"
0x18002197e  jmp     short loc_180021987
0x180021980  lea     rdi, aRenderasbitmap; "RenderAsBitmap"
0x180021987  lea     rbx, aOff; "Off"
0x18002198e  mov     rcx, [rcx+60h]; this
0x180021992  lea     rax, [rsp+48h+arg_8]
0x180021997  lea     r9, aPagetruetypefo; "PageTrueTypeFontMode"
0x18002199e  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x1800219a3  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x1800219aa  xor     edx, edx; struct IXMLDOMElement *
0x1800219ac  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800219b1  mov     esi, eax
0x1800219b3  test    eax, eax
0x1800219b5  js      short loc_180021A2A
0x1800219b7  mov     rdx, [rsp+48h+arg_8]; struct IXMLDOMElement *
0x1800219bc  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x1800219c3  mov     rcx, [rbp+60h]; this
0x1800219c7  mov     r9, rdi; unsigned __int16 *
0x1800219ca  mov     [rsp+48h+var_28], 0; struct IXMLDOMElement **
0x1800219d3  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800219d8  mov     esi, eax
0x1800219da  test    eax, eax
0x1800219dc  js      short loc_180021A2A
0x1800219de  mov     rcx, [rbp+60h]; this
0x1800219e2  lea     rax, [rsp+48h+arg_0]
0x1800219e7  lea     r9, aPagedevicefont; "PageDeviceFontSubstitution"
0x1800219ee  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x1800219f3  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x1800219fa  xor     edx, edx; struct IXMLDOMElement *
0x1800219fc  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021a01  mov     esi, eax
0x180021a03  test    eax, eax
0x180021a05  js      short loc_180021A2A
0x180021a07  mov     rdx, [rsp+48h+arg_0]; struct IXMLDOMElement *
0x180021a0c  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180021a13  mov     rcx, [rbp+60h]; this
0x180021a17  mov     r9, rbx; unsigned __int16 *
0x180021a1a  mov     [rsp+48h+var_28], 0; struct IXMLDOMElement **
0x180021a23  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021a28  mov     esi, eax
0x180021a2a  lea     rcx, [rsp+48h+arg_0]
0x180021a2f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021a34  lea     rcx, [rsp+48h+arg_8]
0x180021a39  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021a3e  mov     eax, esi
0x180021a40  mov     rbx, [rsp+48h+arg_10]
0x180021a45  add     rsp, 30h
0x180021a49  pop     rdi
0x180021a4a  pop     rsi
0x180021a4b  pop     rbp
0x180021a4c  retn
```
