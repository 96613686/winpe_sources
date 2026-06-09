# ReadPrintSchemaPropertyValue(NPrintTicketUtil::CPrintTicketWrapper *,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &,ushort const *,NCoreLibrary::TAutoPtrBSTR &)

- ea: `0x180020020`
- end: `0x1800200f5`
- name: `?ReadPrintSchemaPropertyValue@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@PEBGAEAVTAutoPtrBSTR@4@@Z`
- size: `213`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020324`

## callees

- `0x1800019f0`
- `0x1800056e0`
- `0x180005e70`
- `0x18001ddc4`
- `0x180020020`

## string_xrefs

- `0x18002003e`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall ReadPrintSchemaPropertyValue(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement **a2,
        char *a3,
        unsigned __int16 *a4)
{
  struct IXMLDOMElement *v4; // rdx
  unsigned __int16 *v5; // rbx
  int ChildWithName; // edi
  char *v9; // rsi
  int v10; // ecx
  int v11; // eax
  unsigned int v12; // ebx
  int v14; // [rsp+20h] [rbp-48h]
  unsigned __int16 *v15[2]; // [rsp+40h] [rbp-28h] BYREF
  struct IXMLDOMElement *v16; // [rsp+78h] [rbp+10h] BYREF

  v4 = *a2;
  v5 = 0;
  v15[0] = 0;
  v16 = 0;
  ChildWithName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
                    this,
                    v4,
                    L"ScoredProperty",
                    a4,
                    a3,
                    L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                    &v16);
  if ( ChildWithName >= 0 )
  {
    if ( v16 )
    {
      ChildWithName = NPrintTicketUtil::CPrintTicketWrapper::GetValueAsQName(
                        this,
                        v16,
                        v15,
                        (unsigned __int16 **)a4,
                        v14);
      if ( ChildWithName < 0 )
        goto LABEL_12;
      v5 = v15[0];
    }
    if ( v5 && *(_QWORD *)a4 )
    {
      v9 = (char *)((char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords" - (char *)v5);
      do
      {
        v10 = *(unsigned __int16 *)&v9[(_QWORD)v5];
        v11 = *v5 - v10;
        if ( v11 )
          break;
        ++v5;
      }
      while ( v10 );
      if ( v11 )
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(a4);
    }
  }
LABEL_12:
  v12 = 0;
  if ( ChildWithName < 0 )
    v12 = ChildWithName;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v16);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v15);
  return v12;
}

```

## disassembly

```asm
0x180020020  mov     r11, rsp
0x180020023  mov     [r11+8], rbx
0x180020027  mov     [r11+18h], rbp
0x18002002b  push    rsi
0x18002002c  push    rdi
0x18002002d  push    r14
0x18002002f  sub     rsp, 50h
0x180020033  mov     rdx, [rdx]; struct IXMLDOMElement *
0x180020036  lea     rax, [r11+10h]
0x18002003a  mov     [r11-38h], rax
0x18002003e  lea     rsi, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180020045  mov     [r11-40h], rsi
0x180020049  xor     ebx, ebx
0x18002004b  mov     [r11-48h], r8
0x18002004f  mov     rbp, r9
0x180020052  lea     r8, aScoredproperty_0; "ScoredProperty"
0x180020059  mov     [rsp+68h+var_28], rbx
0x18002005e  mov     r14, rcx
0x180020061  mov     [r11+10h], rbx
0x180020065  call    ?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18002006a  mov     edi, eax
0x18002006c  test    eax, eax
0x18002006e  js      short loc_1800200C3
0x180020070  mov     rdx, [rsp+68h+arg_8]; struct IXMLDOMElement *
0x180020075  test    rdx, rdx
0x180020078  jz      short loc_180020095
0x18002007a  mov     r9, rbp; unsigned __int16 **
0x18002007d  lea     r8, [rsp+68h+var_28]; unsigned __int16 **
0x180020082  mov     rcx, r14; this
0x180020085  call    ?GetValueAsQName@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetValueAsQName(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18002008a  mov     edi, eax
0x18002008c  test    eax, eax
0x18002008e  js      short loc_1800200C3
0x180020090  mov     rbx, [rsp+68h+var_28]
0x180020095  test    rbx, rbx
0x180020098  jz      short loc_1800200C3
0x18002009a  cmp     qword ptr [rbp+0], 0
0x18002009f  jz      short loc_1800200C3
0x1800200a1  sub     rsi, rbx
0x1800200a4  movzx   eax, word ptr [rbx]
0x1800200a7  movzx   ecx, word ptr [rbx+rsi]
0x1800200ab  sub     eax, ecx
0x1800200ad  jnz     short loc_1800200B7
0x1800200af  add     rbx, 2
0x1800200b3  test    ecx, ecx
0x1800200b5  jnz     short loc_1800200A4
0x1800200b7  test    eax, eax
0x1800200b9  jz      short loc_1800200C3
0x1800200bb  mov     rcx, rbp
0x1800200be  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x1800200c3  xor     ebx, ebx
0x1800200c5  lea     rcx, [rsp+68h+arg_8]
0x1800200ca  test    edi, edi
0x1800200cc  cmovs   ebx, edi
0x1800200cf  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x1800200d4  lea     rcx, [rsp+68h+var_28]
0x1800200d9  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x1800200de  lea     r11, [rsp+68h+var_18]
0x1800200e3  mov     eax, ebx
0x1800200e5  mov     rbx, [r11+20h]
0x1800200e9  mov     rbp, [r11+30h]
0x1800200ed  mov     rsp, r11
0x1800200f0  pop     r14
0x1800200f2  pop     rdi
0x1800200f3  pop     rsi
0x1800200f4  retn
```
