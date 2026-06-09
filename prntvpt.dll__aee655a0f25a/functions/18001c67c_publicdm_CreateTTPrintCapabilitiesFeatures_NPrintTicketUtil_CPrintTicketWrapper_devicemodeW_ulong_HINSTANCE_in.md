# publicdm::CreateTTPrintCapabilitiesFeatures(NPrintTicketUtil::CPrintTicketWrapper *,_devicemodeW *,ulong,HINSTANCE__ *,int)

- ea: `0x18001c67c`
- end: `0x18001c918`
- name: `?CreateTTPrintCapabilitiesFeatures@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAU_devicemodeW@@KPEAUHINSTANCE__@@H@Z`
- size: `668`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct _devicemodeW *, unsigned int, HINSTANCE, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021da0`

## callees

- `0x180005e70`
- `0x180006344`
- `0x180006c74`
- `0x18000e084`
- `0x18001c67c`

## string_xrefs

- `0x18001c692`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::CreateTTPrintCapabilitiesFeatures(
        publicdm *this,
        struct IXMLDOMElement *a2,
        struct _devicemodeW *a3,
        struct IXMLDOMElement *a4)
{
  int Option; // ebx
  char v6; // si
  struct IXMLDOMElement *v8; // rsi
  struct IXMLDOMElement *v10[3]; // [rsp+30h] [rbp-18h] BYREF
  struct IXMLDOMElement *v11; // [rsp+88h] [rbp+40h] BYREF

  v11 = a2;
  Option = 0;
  v6 = (char)a3;
  if ( ((unsigned __int8)a3 & 0xB) == 0 )
    goto LABEL_17;
  v11 = 0;
  Option = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
             this,
             0,
             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
             L"PageTrueTypeFontMode",
             &v11);
  if ( Option >= 0 )
  {
    Option = publicdm::WriteDisplayNameFromResourceString(
               this,
               (struct NPrintTicketUtil::CPrintTicketWrapper *)v11,
               a4,
               (HINSTANCE)0xFCEA);
    if ( Option >= 0 )
    {
      if ( (v6 & 1) == 0 )
        goto LABEL_30;
      v10[0] = 0;
      Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                 this,
                 v11,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 L"RenderAsBitmap",
                 v10);
      if ( Option >= 0 )
        Option = publicdm::WriteDisplayNameFromResourceString(
                   this,
                   (struct NPrintTicketUtil::CPrintTicketWrapper *)v10[0],
                   a4,
                   (HINSTANCE)0xFD04);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v10);
      if ( Option >= 0 )
      {
LABEL_30:
        if ( (v6 & 2) == 0 )
          goto LABEL_12;
        v10[0] = 0;
        Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                   this,
                   v11,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"DownloadAsRasterFont",
                   v10);
        if ( Option >= 0 )
          Option = publicdm::WriteDisplayNameFromResourceString(
                     this,
                     (struct NPrintTicketUtil::CPrintTicketWrapper *)v10[0],
                     a4,
                     (HINSTANCE)0xFD05);
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v10);
        if ( Option >= 0 )
        {
LABEL_12:
          if ( (v6 & 8) != 0 )
          {
            v10[0] = 0;
            Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                       this,
                       v11,
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                       L"DownloadAsOutlineFont",
                       v10);
            if ( Option >= 0 )
              Option = publicdm::WriteDisplayNameFromResourceString(
                         this,
                         (struct NPrintTicketUtil::CPrintTicketWrapper *)v10[0],
                         a4,
                         (HINSTANCE)0xFD06);
            NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v10);
          }
        }
      }
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v11);
  if ( Option >= 0 )
  {
LABEL_17:
    if ( (v6 & 4) != 0 )
    {
      v10[0] = 0;
      Option = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                 this,
                 0,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 L"PageDeviceFontSubstitution",
                 v10);
      if ( Option >= 0 )
      {
        v8 = v10[0];
        Option = publicdm::WriteDisplayNameFromResourceString(
                   this,
                   (struct NPrintTicketUtil::CPrintTicketWrapper *)v10[0],
                   a4,
                   (HINSTANCE)0xFD07);
        if ( Option >= 0 )
        {
          v11 = 0;
          Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                     this,
                     v8,
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     L"On",
                     &v11);
          if ( Option >= 0 )
            Option = publicdm::WriteDisplayNameFromResourceString(
                       this,
                       (struct NPrintTicketUtil::CPrintTicketWrapper *)v11,
                       a4,
                       (HINSTANCE)0xFCDB);
          NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v11);
          if ( Option >= 0 )
          {
            v11 = 0;
            Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                       this,
                       v8,
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                       L"Off",
                       &v11);
            if ( Option >= 0 )
              Option = publicdm::WriteDisplayNameFromResourceString(
                         this,
                         (struct NPrintTicketUtil::CPrintTicketWrapper *)v11,
                         a4,
                         (HINSTANCE)0xFCDA);
            NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v11);
          }
        }
      }
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v10);
    }
  }
  return (unsigned int)Option;
}

```

## disassembly

```asm
0x18001c67c  mov     [rsp-30h+arg_8], rdx
0x18001c681  push    rbp
0x18001c682  push    rbx
0x18001c683  push    rsi
0x18001c684  push    rdi
0x18001c685  push    r13
0x18001c687  push    r14
0x18001c689  mov     rbp, rsp
0x18001c68c  sub     rsp, 48h
0x18001c690  xor     ebx, ebx
0x18001c692  lea     r13, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001c699  mov     r14, r9
0x18001c69c  mov     esi, r8d
0x18001c69f  mov     rdi, rcx
0x18001c6a2  test    r8b, 0Bh
0x18001c6a6  jz      loc_18001C809
0x18001c6ac  lea     rax, [rbp+arg_8]
0x18001c6b0  mov     [rbp+arg_8], rbx
0x18001c6b4  lea     r9, aPagetruetypefo; "PageTrueTypeFontMode"
0x18001c6bb  mov     [rsp+48h+var_28], rax; unsigned int
0x18001c6c0  mov     r8, r13; unsigned __int16 *
0x18001c6c3  xor     edx, edx; struct IXMLDOMElement *
0x18001c6c5  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c6ca  mov     ebx, eax
0x18001c6cc  test    eax, eax
0x18001c6ce  js      loc_18001C7F8
0x18001c6d4  mov     rdx, [rbp+arg_8]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001c6d8  mov     r9d, 0FCEAh; HINSTANCE
0x18001c6de  mov     r8, r14; struct IXMLDOMElement *
0x18001c6e1  mov     rcx, rdi; this
0x18001c6e4  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001c6e9  mov     ebx, eax
0x18001c6eb  test    eax, eax
0x18001c6ed  js      loc_18001C7F8
0x18001c6f3  test    sil, 1
0x18001c6f7  jz      short loc_18001C74E
0x18001c6f9  mov     rdx, [rbp+arg_8]; struct IXMLDOMElement *
0x18001c6fd  lea     rax, [rbp+var_18]
0x18001c701  lea     r9, aRenderasbitmap; "RenderAsBitmap"
0x18001c708  mov     [rsp+48h+var_28], rax; unsigned int
0x18001c70d  mov     r8, r13; unsigned __int16 *
0x18001c710  mov     [rbp+var_18], 0
0x18001c718  mov     rcx, rdi; this
0x18001c71b  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c720  mov     ebx, eax
0x18001c722  test    eax, eax
0x18001c724  js      short loc_18001C73D
0x18001c726  mov     rdx, [rbp+var_18]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001c72a  mov     r9d, 0FD04h; HINSTANCE
0x18001c730  mov     r8, r14; struct IXMLDOMElement *
0x18001c733  mov     rcx, rdi; this
0x18001c736  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001c73b  mov     ebx, eax
0x18001c73d  lea     rcx, [rbp+var_18]
0x18001c741  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c746  test    ebx, ebx
0x18001c748  js      loc_18001C7F8
0x18001c74e  test    sil, 2
0x18001c752  jz      short loc_18001C7A5
0x18001c754  mov     rdx, [rbp+arg_8]; struct IXMLDOMElement *
0x18001c758  lea     rax, [rbp+var_18]
0x18001c75c  lea     r9, aDownloadasrast; "DownloadAsRasterFont"
0x18001c763  mov     [rsp+48h+var_28], rax; unsigned int
0x18001c768  mov     r8, r13; unsigned __int16 *
0x18001c76b  mov     [rbp+var_18], 0
0x18001c773  mov     rcx, rdi; this
0x18001c776  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c77b  mov     ebx, eax
0x18001c77d  test    eax, eax
0x18001c77f  js      short loc_18001C798
0x18001c781  mov     rdx, [rbp+var_18]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001c785  mov     r9d, 0FD05h; HINSTANCE
0x18001c78b  mov     r8, r14; struct IXMLDOMElement *
0x18001c78e  mov     rcx, rdi; this
0x18001c791  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001c796  mov     ebx, eax
0x18001c798  lea     rcx, [rbp+var_18]
0x18001c79c  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c7a1  test    ebx, ebx
0x18001c7a3  js      short loc_18001C7F8
0x18001c7a5  test    sil, 8
0x18001c7a9  jz      short loc_18001C7F8
0x18001c7ab  mov     rdx, [rbp+arg_8]; struct IXMLDOMElement *
0x18001c7af  lea     rax, [rbp+var_18]
0x18001c7b3  lea     r9, aDownloadasoutl; "DownloadAsOutlineFont"
0x18001c7ba  mov     [rsp+48h+var_28], rax; unsigned int
0x18001c7bf  mov     r8, r13; unsigned __int16 *
0x18001c7c2  mov     [rbp+var_18], 0
0x18001c7ca  mov     rcx, rdi; this
0x18001c7cd  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c7d2  mov     ebx, eax
0x18001c7d4  test    eax, eax
0x18001c7d6  js      short loc_18001C7EF
0x18001c7d8  mov     rdx, [rbp+var_18]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001c7dc  mov     r9d, 0FD06h; HINSTANCE
0x18001c7e2  mov     r8, r14; struct IXMLDOMElement *
0x18001c7e5  mov     rcx, rdi; this
0x18001c7e8  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001c7ed  mov     ebx, eax
0x18001c7ef  lea     rcx, [rbp+var_18]
0x18001c7f3  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c7f8  lea     rcx, [rbp+arg_8]
0x18001c7fc  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c801  test    ebx, ebx
0x18001c803  js      loc_18001C909
0x18001c809  test    sil, 4
0x18001c80d  jz      loc_18001C909
0x18001c813  lea     rax, [rbp+var_18]
0x18001c817  mov     [rbp+var_18], 0
0x18001c81f  lea     r9, aPagedevicefont; "PageDeviceFontSubstitution"
0x18001c826  mov     [rsp+48h+var_28], rax; unsigned int
0x18001c82b  mov     r8, r13; unsigned __int16 *
0x18001c82e  xor     edx, edx; struct IXMLDOMElement *
0x18001c830  mov     rcx, rdi; this
0x18001c833  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c838  mov     ebx, eax
0x18001c83a  test    eax, eax
0x18001c83c  js      loc_18001C900
0x18001c842  mov     rsi, [rbp+var_18]
0x18001c846  mov     r9d, 0FD07h; HINSTANCE
0x18001c84c  mov     rdx, rsi; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001c84f  mov     r8, r14; struct IXMLDOMElement *
0x18001c852  mov     rcx, rdi; this
0x18001c855  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001c85a  mov     ebx, eax
0x18001c85c  test    eax, eax
0x18001c85e  js      loc_18001C900
0x18001c864  lea     rax, [rbp+arg_8]
0x18001c868  mov     [rbp+arg_8], 0
0x18001c870  lea     r9, aOn; "On"
0x18001c877  mov     [rsp+48h+var_28], rax; unsigned int
0x18001c87c  mov     r8, r13; unsigned __int16 *
0x18001c87f  mov     rdx, rsi; struct IXMLDOMElement *
0x18001c882  mov     rcx, rdi; this
0x18001c885  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c88a  mov     ebx, eax
0x18001c88c  test    eax, eax
0x18001c88e  js      short loc_18001C8A7
0x18001c890  mov     rdx, [rbp+arg_8]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001c894  mov     r9d, 0FCDBh; HINSTANCE
0x18001c89a  mov     r8, r14; struct IXMLDOMElement *
0x18001c89d  mov     rcx, rdi; this
0x18001c8a0  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001c8a5  mov     ebx, eax
0x18001c8a7  lea     rcx, [rbp+arg_8]
0x18001c8ab  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c8b0  test    ebx, ebx
0x18001c8b2  js      short loc_18001C900
0x18001c8b4  lea     rax, [rbp+arg_8]
0x18001c8b8  mov     [rbp+arg_8], 0
0x18001c8c0  lea     r9, aOff; "Off"
0x18001c8c7  mov     [rsp+48h+var_28], rax; unsigned int
0x18001c8cc  mov     r8, r13; unsigned __int16 *
0x18001c8cf  mov     rdx, rsi; struct IXMLDOMElement *
0x18001c8d2  mov     rcx, rdi; this
0x18001c8d5  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c8da  mov     ebx, eax
0x18001c8dc  test    eax, eax
0x18001c8de  js      short loc_18001C8F7
0x18001c8e0  mov     rdx, [rbp+arg_8]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001c8e4  mov     r9d, 0FCDAh; HINSTANCE
0x18001c8ea  mov     r8, r14; struct IXMLDOMElement *
0x18001c8ed  mov     rcx, rdi; this
0x18001c8f0  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001c8f5  mov     ebx, eax
0x18001c8f7  lea     rcx, [rbp+arg_8]
0x18001c8fb  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c900  lea     rcx, [rbp+var_18]
0x18001c904  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c909  mov     eax, ebx
0x18001c90b  add     rsp, 48h
0x18001c90f  pop     r14
0x18001c911  pop     r13
0x18001c913  pop     rdi
0x18001c914  pop     rsi
0x18001c915  pop     rbx
0x18001c916  pop     rbp
0x18001c917  retn
```
