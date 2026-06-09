# publicdm::MediaTypeDevmodeToPrintTicket(publicdm::CConversionInfo &)

- ea: `0x18001ecf0`
- end: `0x18001ee10`
- name: `?MediaTypeDevmodeToPrintTicket@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `288`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180006c74`
- `0x18000e084`
- `0x18000f370`
- `0x18001ecf0`
- `0x180021ebc`
- `0x180023010`

## string_xrefs

- `0x18001ed67`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::MediaTypeDevmodeToPrintTicket(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  __int64 v2; // r8
  int PrintTicketNameFromDriverID; // ebx
  int v5; // esi
  int i; // edx
  const unsigned __int16 **v7; // rbp
  unsigned __int16 **v8; // r8
  __int64 v9; // rcx
  __int64 **v10; // rbx
  const unsigned __int16 *v11; // rax
  struct IXMLDOMElement *v13; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int16 *v14; // [rsp+58h] [rbp+10h] BYREF

  v2 = *((_QWORD *)this + 2);
  PrintTicketNameFromDriverID = 0;
  v13 = 0;
  if ( (*(_DWORD *)(v2 + 72) & 0x2000000) != 0 )
  {
    v5 = 0;
    for ( i = 0; ; ++i )
    {
      v7 = (const unsigned __int16 **)&qword_180031540[6 * i];
      if ( *(_WORD *)v7 == 0xFFFF )
        break;
      if ( *(unsigned __int16 *)v7 == *(_DWORD *)(v2 + 196) )
      {
        v5 = 1;
        break;
      }
    }
    PrintTicketNameFromDriverID = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                                    *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                                    0,
                                    L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                    L"PageMediaType",
                                    &v13);
    if ( PrintTicketNameFromDriverID >= 0 )
    {
      if ( v5 )
      {
        PrintTicketNameFromDriverID = WriteMediaType(
                                        *((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                                        v13,
                                        v7,
                                        0);
      }
      else
      {
        v9 = *((_QWORD *)this + 2);
        v14 = 0;
        PrintTicketNameFromDriverID = publicdm::CreatePrintTicketNameFromDriverID(
                                        (publicdm *)*(unsigned int *)(v9 + 196),
                                        (unsigned int)&v14,
                                        v8);
        if ( PrintTicketNameFromDriverID >= 0 )
        {
          v10 = (__int64 **)*((_QWORD *)this + 12);
          v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 8LL))(this);
          PrintTicketNameFromDriverID = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(v10, v13, v11, v14, 0);
        }
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v14);
      }
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v13);
  return (unsigned int)PrintTicketNameFromDriverID;
}

```

## disassembly

```asm
0x18001ecf0  mov     [rsp+arg_10], rbx
0x18001ecf5  push    rbp
0x18001ecf6  push    rsi
0x18001ecf7  push    rdi
0x18001ecf8  sub     rsp, 30h
0x18001ecfc  mov     r8, [rcx+10h]
0x18001ed00  xor     ebx, ebx
0x18001ed02  mov     rdi, rcx
0x18001ed05  mov     [rsp+48h+arg_0], rbx
0x18001ed0a  test    dword ptr [r8+48h], 2000000h
0x18001ed12  jz      loc_18001EDF7
0x18001ed18  xor     esi, esi
0x18001ed1a  xor     edx, edx
0x18001ed1c  movsxd  rax, edx
0x18001ed1f  lea     rbp, [rax+rax*2]
0x18001ed23  shl     rbp, 4
0x18001ed27  lea     rax, qword_180031540
0x18001ed2e  add     rbp, rax
0x18001ed31  mov     eax, 0FFFFh
0x18001ed36  cmp     [rbp+0], ax
0x18001ed3a  jz      short loc_18001ED52
0x18001ed3c  movzx   eax, word ptr [rbp+0]
0x18001ed40  cmp     eax, [r8+0C4h]
0x18001ed47  jz      short loc_18001ED4D
0x18001ed49  inc     edx
0x18001ed4b  jmp     short loc_18001ED1C
0x18001ed4d  mov     esi, 1
0x18001ed52  mov     rcx, [rcx+60h]; this
0x18001ed56  lea     rax, [rsp+48h+arg_0]
0x18001ed5b  lea     r9, aPagemediatype; "PageMediaType"
0x18001ed62  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x18001ed67  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001ed6e  xor     edx, edx; struct IXMLDOMElement *
0x18001ed70  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001ed75  mov     ebx, eax
0x18001ed77  test    eax, eax
0x18001ed79  js      short loc_18001EDF7
0x18001ed7b  test    esi, esi
0x18001ed7d  jz      short loc_18001ED97
0x18001ed7f  mov     rdx, [rsp+48h+arg_0]; struct IXMLDOMElement *
0x18001ed84  xor     r9d, r9d; struct IXMLDOMElement **
0x18001ed87  mov     rcx, [rdi+60h]; this
0x18001ed8b  mov     r8, rbp; struct publicdm::MediaTypeEntry *
0x18001ed8e  call    ?WriteMediaType@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUMediaTypeEntry@publicdm@@PEAPEAU3@@Z; WriteMediaType(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,publicdm::MediaTypeEntry *,IXMLDOMElement * *)
0x18001ed93  mov     ebx, eax
0x18001ed95  jmp     short loc_18001EDF7
0x18001ed97  mov     rcx, [rdi+10h]
0x18001ed9b  lea     rdx, [rsp+48h+arg_8]; unsigned int
0x18001eda0  mov     [rsp+48h+arg_8], 0
0x18001eda9  mov     ecx, [rcx+0C4h]; this
0x18001edaf  call    ?CreatePrintTicketNameFromDriverID@publicdm@@YAJKPEAPEAG@Z; publicdm::CreatePrintTicketNameFromDriverID(ulong,ushort * *)
0x18001edb4  mov     ebx, eax
0x18001edb6  test    eax, eax
0x18001edb8  js      short loc_18001EDED
0x18001edba  mov     rax, [rdi]
0x18001edbd  mov     rcx, rdi
0x18001edc0  mov     rbx, [rdi+60h]
0x18001edc4  mov     rax, [rax+8]
0x18001edc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edcd  mov     r9, [rsp+48h+arg_8]; unsigned __int16 *
0x18001edd2  mov     r8, rax; unsigned __int16 *
0x18001edd5  mov     rdx, [rsp+48h+arg_0]; struct IXMLDOMElement *
0x18001edda  mov     rcx, rbx; this
0x18001eddd  mov     [rsp+48h+var_28], 0; struct IXMLDOMElement **
0x18001ede6  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001edeb  mov     ebx, eax
0x18001eded  lea     rcx, [rsp+48h+arg_8]
0x18001edf2  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001edf7  lea     rcx, [rsp+48h+arg_0]
0x18001edfc  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001ee01  mov     eax, ebx
0x18001ee03  mov     rbx, [rsp+48h+arg_10]
0x18001ee08  add     rsp, 30h
0x18001ee0c  pop     rdi
0x18001ee0d  pop     rsi
0x18001ee0e  pop     rbp
0x18001ee0f  retn
```
