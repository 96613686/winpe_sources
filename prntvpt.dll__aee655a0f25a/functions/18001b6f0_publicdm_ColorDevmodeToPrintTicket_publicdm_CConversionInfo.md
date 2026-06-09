# publicdm::ColorDevmodeToPrintTicket(publicdm::CConversionInfo &)

- ea: `0x18001b6f0`
- end: `0x18001b79c`
- name: `?ColorDevmodeToPrintTicket@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `172`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006c74`
- `0x18000e084`
- `0x18001b6f0`

## string_xrefs

- `0x18001b744`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001b762`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::ColorDevmodeToPrintTicket(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  __int64 v2; // rax
  int Option; // ebx
  const unsigned __int16 *v5; // rdi
  NPrintTicketUtil::CPrintTicketWrapper *v6; // rcx
  struct IXMLDOMElement *v8; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 2);
  Option = 0;
  if ( (*(_DWORD *)(v2 + 72) & 0x800) != 0 )
  {
    if ( *(_WORD *)(v2 + 92) == 1 )
    {
      v5 = L"Monochrome";
    }
    else
    {
      if ( *(_WORD *)(v2 + 92) != 2 )
        return (unsigned int)Option;
      v5 = L"Color";
    }
    v6 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
    v8 = 0;
    Option = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
               v6,
               0,
               L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
               (unsigned __int16 *)&stru_18002A1F0,
               &v8);
    if ( Option >= 0 )
      Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                 *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                 v8,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 v5,
                 0);
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v8);
  }
  return (unsigned int)Option;
}

```

## disassembly

```asm
0x18001b6f0  mov     [rsp+arg_8], rbx
0x18001b6f5  mov     [rsp+arg_10], rsi
0x18001b6fa  push    rdi
0x18001b6fb  sub     rsp, 30h
0x18001b6ff  mov     rax, [rcx+10h]
0x18001b703  xor     ebx, ebx
0x18001b705  mov     rsi, rcx
0x18001b708  test    dword ptr [rax+48h], 800h
0x18001b70f  jz      short loc_18001B78A
0x18001b711  movsx   edx, word ptr [rax+5Ch]
0x18001b715  sub     edx, 1
0x18001b718  jz      short loc_18001B728
0x18001b71a  cmp     edx, 1
0x18001b71d  jnz     short loc_18001B78A
0x18001b71f  lea     rdi, aColor; "Color"
0x18001b726  jmp     short loc_18001B72F
0x18001b728  lea     rdi, aMonochrome; "Monochrome"
0x18001b72f  mov     rcx, [rcx+60h]; this
0x18001b733  lea     rax, [rsp+38h+arg_0]
0x18001b738  lea     r9, stru_18002A1F0; unsigned __int16 *
0x18001b73f  mov     [rsp+38h+var_18], rax; struct IXMLDOMElement **
0x18001b744  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001b74b  mov     [rsp+38h+arg_0], rbx
0x18001b750  xor     edx, edx; struct IXMLDOMElement *
0x18001b752  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001b757  mov     ebx, eax
0x18001b759  test    eax, eax
0x18001b75b  js      short loc_18001B780
0x18001b75d  mov     rdx, [rsp+38h+arg_0]; struct IXMLDOMElement *
0x18001b762  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001b769  mov     rcx, [rsi+60h]; this
0x18001b76d  mov     r9, rdi; unsigned __int16 *
0x18001b770  mov     [rsp+38h+var_18], 0; struct IXMLDOMElement **
0x18001b779  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001b77e  mov     ebx, eax
0x18001b780  lea     rcx, [rsp+38h+arg_0]
0x18001b785  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b78a  mov     rsi, [rsp+38h+arg_10]
0x18001b78f  mov     eax, ebx
0x18001b791  mov     rbx, [rsp+38h+arg_8]
0x18001b796  add     rsp, 30h
0x18001b79a  pop     rdi
0x18001b79b  retn
```
