# publicdm::OrientationDevmodeToPrintTicket(publicdm::CConversionInfo &)

- ea: `0x18001f070`
- end: `0x18001f119`
- name: `?OrientationDevmodeToPrintTicket@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `169`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006c74`
- `0x18000e084`
- `0x18001f070`

## string_xrefs

- `0x18001f0c6`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001f0df`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::OrientationDevmodeToPrintTicket(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  __int64 v2; // rax
  int Option; // ebx
  int v5; // edx
  int v6; // edx
  const unsigned __int16 *v7; // rdi
  struct IXMLDOMElement *v9; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 2);
  Option = 0;
  if ( (*(_BYTE *)(v2 + 72) & 1) != 0 )
  {
    v5 = *(__int16 *)(v2 + 76);
    v9 = 0;
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
      {
LABEL_8:
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v9);
        return (unsigned int)Option;
      }
      v7 = L"Landscape";
    }
    else
    {
      v7 = L"Portrait";
    }
    Option = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
               *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
               0,
               L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
               (unsigned __int16 *)&stru_180029930,
               &v9);
    if ( Option >= 0 )
      Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                 *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                 v9,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 v7,
                 0);
    goto LABEL_8;
  }
  return (unsigned int)Option;
}

```

## disassembly

```asm
0x18001f070  mov     [rsp+arg_8], rbx
0x18001f075  mov     [rsp+arg_10], rsi
0x18001f07a  push    rdi
0x18001f07b  sub     rsp, 30h
0x18001f07f  mov     rax, [rcx+10h]
0x18001f083  xor     ebx, ebx
0x18001f085  mov     rsi, rcx
0x18001f088  test    byte ptr [rax+48h], 1
0x18001f08c  jz      short loc_18001F107
0x18001f08e  movsx   edx, word ptr [rax+4Ch]
0x18001f092  mov     [rsp+38h+arg_0], rbx
0x18001f097  sub     edx, 1
0x18001f09a  jz      short loc_18001F0AA
0x18001f09c  cmp     edx, 1
0x18001f09f  jnz     short loc_18001F0FD
0x18001f0a1  lea     rdi, aLandscape; "Landscape"
0x18001f0a8  jmp     short loc_18001F0B1
0x18001f0aa  lea     rdi, aPortrait; "Portrait"
0x18001f0b1  mov     rcx, [rcx+60h]; this
0x18001f0b5  lea     rax, [rsp+38h+arg_0]
0x18001f0ba  lea     r9, stru_180029930; unsigned __int16 *
0x18001f0c1  mov     [rsp+38h+var_18], rax; struct IXMLDOMElement **
0x18001f0c6  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001f0cd  xor     edx, edx; struct IXMLDOMElement *
0x18001f0cf  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001f0d4  mov     ebx, eax
0x18001f0d6  test    eax, eax
0x18001f0d8  js      short loc_18001F0FD
0x18001f0da  mov     rdx, [rsp+38h+arg_0]; struct IXMLDOMElement *
0x18001f0df  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001f0e6  mov     rcx, [rsi+60h]; this
0x18001f0ea  mov     r9, rdi; unsigned __int16 *
0x18001f0ed  mov     [rsp+38h+var_18], 0; struct IXMLDOMElement **
0x18001f0f6  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001f0fb  mov     ebx, eax
0x18001f0fd  lea     rcx, [rsp+38h+arg_0]
0x18001f102  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001f107  mov     rsi, [rsp+38h+arg_10]
0x18001f10c  mov     eax, ebx
0x18001f10e  mov     rbx, [rsp+38h+arg_8]
0x18001f113  add     rsp, 30h
0x18001f117  pop     rdi
0x18001f118  retn
```
