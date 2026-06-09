# publicdm::CreateCapabilitiesFromList(NPrintTicketUtil::CPrintTicketWrapper *,HINSTANCE__ *,ushort const *,ushort const *,ulong,publicdm::NamedOption *,ulong,int)

- ea: `0x18001bbac`
- end: `0x18001bc93`
- name: `?CreateCapabilitiesFromList@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUHINSTANCE__@@PEBG2KPEAUNamedOption@1@KH@Z`
- size: `231`
- prototype: `__int64 __usercall@<rax>(publicdm *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, HINSTANCE@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, unsigned int, struct publicdm::NamedOption *, unsigned int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e240`
- `0x18001e340`

## callees

- `0x180005e70`
- `0x180006344`
- `0x180006c74`
- `0x18000e084`
- `0x18001bbac`

## string_xrefs

- `0x18001bbdc`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::CreateCapabilitiesFromList(
        publicdm *this,
        struct IXMLDOMElement *a2,
        HINSTANCE a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        __int64 a6)
{
  __int64 v6; // r14
  int Option; // ebx
  __int64 v10; // rdi
  const unsigned __int16 *v11; // r9
  const unsigned __int16 *v12; // r8
  HINSTANCE v13; // r9
  struct IXMLDOMElement *v15[9]; // [rsp+30h] [rbp-48h] BYREF
  struct IXMLDOMElement *v16; // [rsp+90h] [rbp+18h] BYREF

  v6 = a6;
  v16 = 0;
  Option = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
             this,
             0,
             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
             a4,
             &v16);
  if ( Option >= 0 )
    Option = publicdm::WriteDisplayNameFromResourceString(
               this,
               (struct NPrintTicketUtil::CPrintTicketWrapper *)v16,
               a2,
               (HINSTANCE)(unsigned int)a5);
  v10 = 0;
  do
  {
    if ( Option < 0 )
      break;
    v11 = *(const unsigned __int16 **)(v6 + 24 * v10 + 8);
    v12 = *(const unsigned __int16 **)(v6 + 24 * v10);
    v15[0] = 0;
    Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(this, v16, v12, v11, v15);
    if ( Option >= 0 )
    {
      v13 = (HINSTANCE)*(unsigned int *)(v6 + 24 * v10 + 20);
      if ( (_DWORD)v13 )
        Option = publicdm::WriteDisplayNameFromResourceString(
                   this,
                   (struct NPrintTicketUtil::CPrintTicketWrapper *)v15[0],
                   a2,
                   v13);
    }
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v15);
    v10 = (unsigned int)(v10 + 1);
  }
  while ( (unsigned int)v10 < 4 );
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v16);
  return (unsigned int)Option;
}

```

## disassembly

```asm
0x18001bbac  mov     r11, rsp
0x18001bbaf  mov     [r11+18h], r8
0x18001bbb3  push    rbx
0x18001bbb4  push    rbp
0x18001bbb5  push    rsi
0x18001bbb6  push    rdi
0x18001bbb7  push    r14
0x18001bbb9  push    r15
0x18001bbbb  sub     rsp, 48h
0x18001bbbf  mov     r14, [rsp+78h+arg_28]
0x18001bbc7  lea     rax, [r11+18h]
0x18001bbcb  mov     r15, rdx
0x18001bbce  mov     [r11-58h], rax
0x18001bbd2  xor     edx, edx; struct IXMLDOMElement *
0x18001bbd4  mov     qword ptr [r11+18h], 0
0x18001bbdc  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001bbe3  mov     rsi, rcx
0x18001bbe6  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001bbeb  mov     ebx, eax
0x18001bbed  test    eax, eax
0x18001bbef  js      short loc_18001BC0E
0x18001bbf1  mov     r9d, dword ptr [rsp+78h+arg_20]; HINSTANCE
0x18001bbf9  mov     r8, r15; struct IXMLDOMElement *
0x18001bbfc  mov     rdx, [rsp+78h+arg_10]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001bc04  mov     rcx, rsi; this
0x18001bc07  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001bc0c  mov     ebx, eax
0x18001bc0e  xor     edi, edi
0x18001bc10  test    ebx, ebx
0x18001bc12  js      short loc_18001BC77
0x18001bc14  mov     rdx, [rsp+78h+arg_10]; struct IXMLDOMElement *
0x18001bc1c  lea     rbp, [rdi+rdi*2]
0x18001bc20  mov     r9, [r14+rbp*8+8]; unsigned __int16 *
0x18001bc25  lea     rax, [rsp+78h+var_48]
0x18001bc2a  mov     r8, [r14+rbp*8]; unsigned __int16 *
0x18001bc2e  mov     rcx, rsi; this
0x18001bc31  mov     [rsp+78h+var_48], 0
0x18001bc3a  mov     [rsp+78h+var_58], rax; unsigned int
0x18001bc3f  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001bc44  mov     ebx, eax
0x18001bc46  test    eax, eax
0x18001bc48  js      short loc_18001BC66
0x18001bc4a  mov     r9d, [r14+rbp*8+14h]; HINSTANCE
0x18001bc4f  test    r9d, r9d
0x18001bc52  jz      short loc_18001BC66
0x18001bc54  mov     rdx, [rsp+78h+var_48]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001bc59  mov     r8, r15; struct IXMLDOMElement *
0x18001bc5c  mov     rcx, rsi; this
0x18001bc5f  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001bc64  mov     ebx, eax
0x18001bc66  lea     rcx, [rsp+78h+var_48]
0x18001bc6b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001bc70  inc     edi
0x18001bc72  cmp     edi, 4
0x18001bc75  jb      short loc_18001BC10
0x18001bc77  lea     rcx, [rsp+78h+arg_10]
0x18001bc7f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001bc84  mov     eax, ebx
0x18001bc86  add     rsp, 48h
0x18001bc8a  pop     r15
0x18001bc8c  pop     r14
0x18001bc8e  pop     rdi
0x18001bc8f  pop     rsi
0x18001bc90  pop     rbp
0x18001bc91  pop     rbx
0x18001bc92  retn
```
