# publicdm::CreateSelectedOption(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,publicdm::NamedOption *,ulong,ulong)

- ea: `0x18001c46c`
- end: `0x18001c50d`
- name: `?CreateSelectedOption@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG1PEAUNamedOption@1@KK@Z`
- size: `161`
- prototype: `__int64 __usercall@<rax>(publicdm *__hidden this@<rcx>, struct NPrintTicketUtil::CPrintTicketWrapper *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct publicdm::NamedOption *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e1b0`
- `0x18001e2b0`

## callees

- `0x180005e70`
- `0x180006c74`
- `0x18000e084`
- `0x18001c46c`

## string_xrefs

- `0x18001c4b0`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::CreateSelectedOption(
        publicdm *this,
        struct IXMLDOMElement *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct publicdm::NamedOption *a5,
        unsigned int a6)
{
  int Option; // ebx
  __int64 i; // rdx
  __int64 v10; // rdi
  struct IXMLDOMElement *v12[7]; // [rsp+30h] [rbp-38h] BYREF
  struct IXMLDOMElement *v13; // [rsp+78h] [rbp+10h] BYREF

  v13 = a2;
  Option = 0;
  for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
  {
    v10 = 3 * i;
    if ( *(_DWORD *)&a4[12 * i + 8] == a6 )
    {
      v13 = 0;
      v12[0] = 0;
      Option = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                 this,
                 0,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 a3,
                 &v13);
      if ( Option >= 0 )
        Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                   this,
                   v13,
                   *(const unsigned __int16 **)&a4[4 * v10],
                   *(const unsigned __int16 **)&a4[4 * v10 + 4],
                   v12);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v12);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v13);
      return (unsigned int)Option;
    }
  }
  return (unsigned int)Option;
}

```

## disassembly

```asm
0x18001c46c  mov     [rsp+arg_8], rdx
0x18001c471  push    rbx
0x18001c472  push    rbp
0x18001c473  push    rsi
0x18001c474  push    rdi
0x18001c475  sub     rsp, 48h
0x18001c479  xor     ebx, ebx
0x18001c47b  mov     rbp, rcx
0x18001c47e  mov     ecx, [rsp+68h+arg_28]
0x18001c485  xor     edx, edx
0x18001c487  mov     rsi, r9
0x18001c48a  cmp     edx, 4
0x18001c48d  jnb     short loc_18001C502
0x18001c48f  lea     rdi, [rdx+rdx*2]
0x18001c493  cmp     [r9+rdi*8+10h], ecx
0x18001c498  jz      short loc_18001C49E
0x18001c49a  inc     edx
0x18001c49c  jmp     short loc_18001C48A
0x18001c49e  lea     rax, [rsp+68h+arg_8]
0x18001c4a3  mov     [rsp+68h+arg_8], rbx
0x18001c4a8  mov     r9, r8; unsigned __int16 *
0x18001c4ab  mov     [rsp+68h+var_48], rax; struct IXMLDOMElement **
0x18001c4b0  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001c4b7  mov     [rsp+68h+var_38], rbx
0x18001c4bc  xor     edx, edx; struct IXMLDOMElement *
0x18001c4be  mov     rcx, rbp; this
0x18001c4c1  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c4c6  mov     ebx, eax
0x18001c4c8  test    eax, eax
0x18001c4ca  js      short loc_18001C4EE
0x18001c4cc  mov     r9, [rsi+rdi*8+8]; unsigned __int16 *
0x18001c4d1  lea     rax, [rsp+68h+var_38]
0x18001c4d6  mov     r8, [rsi+rdi*8]; unsigned __int16 *
0x18001c4da  mov     rcx, rbp; this
0x18001c4dd  mov     rdx, [rsp+68h+arg_8]; struct IXMLDOMElement *
0x18001c4e2  mov     [rsp+68h+var_48], rax; struct IXMLDOMElement **
0x18001c4e7  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c4ec  mov     ebx, eax
0x18001c4ee  lea     rcx, [rsp+68h+var_38]
0x18001c4f3  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c4f8  lea     rcx, [rsp+68h+arg_8]
0x18001c4fd  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001c502  mov     eax, ebx
0x18001c504  add     rsp, 48h
0x18001c508  pop     rdi
0x18001c509  pop     rsi
0x18001c50a  pop     rbp
0x18001c50b  pop     rbx
0x18001c50c  retn
```
