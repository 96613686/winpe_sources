# NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x18000e084`
- end: `0x18000e1b7`
- name: `?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z`
- size: `307`
- prototype: `__int64 __usercall@<rax>(NPrintTicketUtil::CPrintTicketWrapper *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct IXMLDOMElement **)`
- caller_count: `21`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003380`
- `0x18000b5a0`
- `0x18001b4b0`
- `0x18001b590`
- `0x18001b6f0`
- `0x18001bbac`
- `0x18001c46c`
- `0x18001c67c`
- `0x18001cdd0`
- `0x18001d090`
- `0x18001e3b0`
- `0x18001e520`
- `0x18001ecf0`
- `0x18001f070`
- `0x18001f550`
- `0x18001f720`
- `0x180020710`
- `0x180020bd0`
- `0x180020f00`
- `0x180021260`
- `0x180021900`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180006f80`
- `0x1800070e0`
- `0x1800076e8`
- `0x18000e084`
- `0x18001c37c`

## string_xrefs

- `0x18000e14d`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x18000e154`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IXMLDOMElement **a5)
{
  int QName; // ebx
  NPrintTicketUtil::CPrintTicketWrapper *v10; // rcx
  struct IXMLDOMElement *v11; // rdx
  unsigned __int16 *v12; // [rsp+28h] [rbp-28h]
  const unsigned __int16 *v13; // [rsp+30h] [rbp-20h]
  struct IXMLDOMElement **v14; // [rsp+38h] [rbp-18h]
  unsigned __int16 *v15[2]; // [rsp+40h] [rbp-10h] BYREF
  struct IXMLDOMElement *v16; // [rsp+88h] [rbp+38h] BYREF

  if ( !a4 )
    return 2147942487LL;
  v16 = 0;
  if ( !a2 )
    a2 = (struct IXMLDOMElement *)*((_QWORD *)this + 3);
  v15[0] = 0;
  QName = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(this, a2, L"Feature", a4, &v16);
  if ( QName >= 0 )
  {
    QName = NPrintTicketUtil::CreateQName(
              this,
              v16,
              (struct IXMLDOMElement *)a4,
              a3,
              (const unsigned __int16 *)v15,
              (unsigned __int16 **)v12,
              v13);
    if ( QName >= 0 )
    {
      QName = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(v10, v16, L"name", v15[0]);
      if ( QName >= 0 )
      {
        if ( !*((_DWORD *)this + 9)
          || (QName = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                        this,
                        v16,
                        L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
                        L"SelectionType",
                        L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                        L"PickOne",
                        0,
                        v14),
              QName >= 0) )
        {
          if ( a5 )
          {
            v11 = 0;
            if ( v16 )
            {
              v11 = v16;
              v16 = 0;
            }
            *a5 = v11;
          }
        }
      }
    }
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v15);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v16);
  return (unsigned int)QName;
}

```

## disassembly

```asm
0x18000e084  mov     [rsp-18h+arg_0], rbx
0x18000e089  mov     [rsp-18h+arg_8], rsi
0x18000e08e  push    rbp
0x18000e08f  push    rdi
0x18000e090  push    r14
0x18000e092  mov     rbp, rsp
0x18000e095  sub     rsp, 50h
0x18000e099  mov     rsi, r9
0x18000e09c  mov     r14, r8
0x18000e09f  mov     rdi, rcx
0x18000e0a2  test    r9, r9
0x18000e0a5  jnz     short loc_18000E0B1
0x18000e0a7  mov     eax, 80070057h
0x18000e0ac  jmp     loc_18000E1A4
0x18000e0b1  mov     [rbp+arg_18], 0
0x18000e0b9  test    rdx, rdx
0x18000e0bc  jnz     short loc_18000E0C2
0x18000e0be  mov     rdx, [rcx+18h]; struct IXMLDOMElement *
0x18000e0c2  lea     rax, [rbp+arg_18]
0x18000e0c6  lea     r8, aFeature; "Feature"
0x18000e0cd  mov     [rsp+50h+var_30], rax; struct IXMLDOMElement **
0x18000e0d2  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000e0d7  mov     [rbp+var_10], 0
0x18000e0df  mov     ebx, eax
0x18000e0e1  test    eax, eax
0x18000e0e3  js      loc_18000E190
0x18000e0e9  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18000e0ed  lea     rax, [rbp+var_10]
0x18000e0f1  mov     r9, r14; unsigned __int16 *
0x18000e0f4  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x18000e0f9  mov     r8, rsi; struct IXMLDOMElement *
0x18000e0fc  mov     rcx, rdi; this
0x18000e0ff  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18000e104  mov     ebx, eax
0x18000e106  test    eax, eax
0x18000e108  js      loc_18000E190
0x18000e10e  mov     r9, [rbp+var_10]; unsigned __int16 *
0x18000e112  lea     r8, aName; "name"
0x18000e119  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18000e11d  call    ?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18000e122  mov     ebx, eax
0x18000e124  test    eax, eax
0x18000e126  js      short loc_18000E190
0x18000e128  cmp     dword ptr [rdi+24h], 0
0x18000e12c  jz      short loc_18000E16E
0x18000e12e  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18000e132  lea     rax, aPickone; "PickOne"
0x18000e139  mov     dword ptr [rsp+50h+var_20], 0; int
0x18000e141  lea     r9, aSelectiontype; "SelectionType"
0x18000e148  mov     [rsp+50h+var_28], rax; unsigned __int16 *
0x18000e14d  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18000e154  lea     rax, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18000e15b  mov     rcx, rdi; this
0x18000e15e  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x18000e163  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x18000e168  mov     ebx, eax
0x18000e16a  test    eax, eax
0x18000e16c  js      short loc_18000E190
0x18000e16e  mov     rcx, [rbp+arg_20]
0x18000e172  test    rcx, rcx
0x18000e175  jz      short loc_18000E190
0x18000e177  mov     rax, [rbp+arg_18]
0x18000e17b  xor     edx, edx
0x18000e17d  test    rax, rax
0x18000e180  jz      short loc_18000E18D
0x18000e182  mov     rdx, rax
0x18000e185  mov     [rbp+arg_18], 0
0x18000e18d  mov     [rcx], rdx
0x18000e190  lea     rcx, [rbp+var_10]
0x18000e194  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000e199  lea     rcx, [rbp+arg_18]
0x18000e19d  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000e1a2  mov     eax, ebx
0x18000e1a4  mov     rbx, [rsp+50h+arg_0]
0x18000e1a9  mov     rsi, [rsp+50h+arg_8]
0x18000e1ae  add     rsp, 50h
0x18000e1b2  pop     r14
0x18000e1b4  pop     rdi
0x18000e1b5  pop     rbp
0x18000e1b6  retn
```
