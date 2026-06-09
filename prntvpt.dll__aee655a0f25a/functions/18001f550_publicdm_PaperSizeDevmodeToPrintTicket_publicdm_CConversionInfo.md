# publicdm::PaperSizeDevmodeToPrintTicket(publicdm::CConversionInfo &)

- ea: `0x18001f550`
- end: `0x18001f624`
- name: `?PaperSizeDevmodeToPrintTicket@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `212`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x18000c224`
- `0x18000ca58`
- `0x18000e084`
- `0x18000e334`
- `0x18000e59c`
- `0x18001f550`
- `0x180023010`

## string_xrefs

- `0x18001f5d8`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::PaperSizeDevmodeToPrintTicket(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  __int64 v2; // rax
  const unsigned __int16 *v4; // rbx
  struct _devicemodeW *v5; // rdi
  struct NPrintTicketUtil::IPrinterWrapper *v6; // rax
  int SizeFromDevmode; // ebx
  NPrintTicketUtil::CPrintTicketWrapper *v8; // rcx
  __int128 v10; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h]
  __int64 v12; // [rsp+48h] [rbp-20h]
  __int16 v13; // [rsp+50h] [rbp-18h]
  struct IXMLDOMElement *v14; // [rsp+90h] [rbp+28h] BYREF

  v11 = 0;
  v13 = 0;
  v2 = *(_QWORD *)this;
  v10 = 0;
  v12 = 0;
  v4 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(publicdm *, struct publicdm::CConversionInfo *))(v2 + 8))(
                                   this,
                                   a2);
  v5 = (struct _devicemodeW *)*((_QWORD *)this + 2);
  v6 = (struct NPrintTicketUtil::IPrinterWrapper *)(*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 16LL))(this);
  SizeFromDevmode = PaperSizeOption::ReadSizeFromDevmode((PaperSizeOption *)&v10, v6, v5, v4);
  if ( SizeFromDevmode >= 0 && (unsigned int)PaperSizeOption::IsConfigured((PaperSizeOption *)&v10) )
  {
    v8 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
    v14 = 0;
    SizeFromDevmode = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                        v8,
                        0,
                        L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                        L"PageMediaSize",
                        &v14);
    if ( SizeFromDevmode >= 0 )
      SizeFromDevmode = PaperSizeOption::WriteToPrintTicket(
                          (__int64)&v10,
                          *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                          &v14);
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v14);
  }
  PaperSizeOption::~PaperSizeOption((PaperSizeOption *)&v10);
  return (unsigned int)SizeFromDevmode;
}

```

## disassembly

```asm
0x18001f550  push    rbp
0x18001f552  push    rbx
0x18001f553  push    rsi
0x18001f554  push    rdi
0x18001f555  mov     rbp, rsp
0x18001f558  sub     rsp, 68h
0x18001f55c  xor     eax, eax
0x18001f55e  mov     [rbp+var_28], 0
0x18001f566  mov     [rbp+var_18], ax
0x18001f56a  xorps   xmm0, xmm0
0x18001f56d  mov     rax, [rcx]
0x18001f570  mov     rsi, rcx
0x18001f573  movdqu  [rbp+var_38], xmm0
0x18001f578  mov     [rbp+var_20], 0
0x18001f580  mov     rax, [rax+8]
0x18001f584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f589  mov     rcx, [rsi]
0x18001f58c  mov     rbx, rax
0x18001f58f  mov     rdi, [rsi+10h]
0x18001f593  mov     rax, [rcx+10h]
0x18001f597  mov     rcx, rsi
0x18001f59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f59f  mov     r9, rbx; unsigned __int16 *
0x18001f5a2  lea     rcx, [rbp+var_38]; this
0x18001f5a6  mov     r8, rdi; struct _devicemodeW *
0x18001f5a9  mov     rdx, rax; struct NPrintTicketUtil::IPrinterWrapper *
0x18001f5ac  call    ?ReadSizeFromDevmode@PaperSizeOption@@QEAAJAEAVIPrinterWrapper@NPrintTicketUtil@@PEAU_devicemodeW@@PEBG@Z; PaperSizeOption::ReadSizeFromDevmode(NPrintTicketUtil::IPrinterWrapper &,_devicemodeW *,ushort const *)
0x18001f5b1  mov     ebx, eax
0x18001f5b3  test    eax, eax
0x18001f5b5  js      short loc_18001F610
0x18001f5b7  lea     rcx, [rbp+var_38]; this
0x18001f5bb  call    ?IsConfigured@PaperSizeOption@@QEAAHXZ; PaperSizeOption::IsConfigured(void)
0x18001f5c0  test    eax, eax
0x18001f5c2  jz      short loc_18001F610
0x18001f5c4  mov     rcx, [rsi+60h]; this
0x18001f5c8  lea     rax, [rbp+arg_0]
0x18001f5cc  lea     r9, aPagemediasize; "PageMediaSize"
0x18001f5d3  mov     [rsp+68h+var_48], rax; struct IXMLDOMElement **
0x18001f5d8  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001f5df  mov     [rbp+arg_0], 0
0x18001f5e7  xor     edx, edx; struct IXMLDOMElement *
0x18001f5e9  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001f5ee  mov     ebx, eax
0x18001f5f0  test    eax, eax
0x18001f5f2  js      short loc_18001F607
0x18001f5f4  mov     rdx, [rsi+60h]
0x18001f5f8  lea     r8, [rbp+arg_0]
0x18001f5fc  lea     rcx, [rbp+var_38]
0x18001f600  call    ?WriteToPrintTicket@PaperSizeOption@@QEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@@Z; PaperSizeOption::WriteToPrintTicket(NPrintTicketUtil::CPrintTicketWrapper *,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &)
0x18001f605  mov     ebx, eax
0x18001f607  lea     rcx, [rbp+arg_0]
0x18001f60b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001f610  lea     rcx, [rbp+var_38]; this
0x18001f614  call    ??1PaperSizeOption@@QEAA@XZ; PaperSizeOption::~PaperSizeOption(void)
0x18001f619  mov     eax, ebx
0x18001f61b  add     rsp, 68h
0x18001f61f  pop     rdi
0x18001f620  pop     rsi
0x18001f621  pop     rbx
0x18001f622  pop     rbp
0x18001f623  retn
```
