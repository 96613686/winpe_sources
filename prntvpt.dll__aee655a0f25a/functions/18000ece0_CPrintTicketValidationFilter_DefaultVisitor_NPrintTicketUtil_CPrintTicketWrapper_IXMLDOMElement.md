# CPrintTicketValidationFilter::DefaultVisitor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *)

- ea: `0x18000ece0`
- end: `0x18000ee50`
- name: `?DefaultVisitor@CPrintTicketValidationFilter@@UEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@@Z`
- size: `368`
- prototype: `int(CPrintTicketValidationFilter *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003318`
- `0x1800056e0`
- `0x180005e70`
- `0x18000ece0`
- `0x18001d30c`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CPrintTicketValidationFilter::DefaultVisitor(
        CPrintTicketValidationFilter *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int ElementDescriptor; // ebx
  struct IXMLDOMElementVtbl *v8; // rax
  const unsigned __int16 *v10; // [rsp+28h] [rbp-28h]
  struct IXMLDOMElement v11; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v12; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v13[2]; // [rsp+40h] [rbp-10h] BYREF
  struct IXMLDOMElement *v14; // [rsp+80h] [rbp+30h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, GUID *, struct IXMLDOMElement **); // [rsp+88h] [rbp+38h] BYREF

  v13[0] = 0;
  v12 = 0;
  v11.lpVtbl = 0;
  v15 = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v15);
  v15 = 0;
  v14 = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v14);
  lpVtbl = a3->lpVtbl;
  v14 = 0;
  ElementDescriptor = ((__int64 (__fastcall *)(struct IXMLDOMElement *, unsigned __int16 **))lpVtbl->get_baseName)(
                        a3,
                        &v12);
  if ( ElementDescriptor >= 0 )
  {
    ElementDescriptor = ((__int64 (__fastcall *)(struct IXMLDOMElement *, unsigned __int16 **))a3->lpVtbl->get_namespaceURI)(
                          a3,
                          v13);
    if ( ElementDescriptor >= 0 )
    {
      ElementDescriptor = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 (__fastcall ****)(_QWORD, GUID *, struct IXMLDOMElement **)))a3->lpVtbl->get_parentNode)(
                            a3,
                            &v15);
      if ( ElementDescriptor >= 0 )
        ElementDescriptor = (**v15)(v15, &IID_IXMLDOMElement, &v14);
    }
  }
  if ( ElementDescriptor == -2147467262 )
    goto LABEL_9;
  if ( ElementDescriptor < 0 )
    goto LABEL_12;
  ElementDescriptor = NPrintTicketUtil::GetElementDescriptor(a2, v14, &v11, (unsigned __int16 **)1);
  if ( ElementDescriptor < 0 )
    goto LABEL_12;
  v8 = v11.lpVtbl;
  if ( !v11.lpVtbl )
LABEL_9:
    v8 = 0;
  ElementDescriptor = CValidationStatus::SetValidationFailure(
                        (CPrintTicketValidationFilter *)((char *)this + 8),
                        L"Element %s:%s is not allowed within node %s.",
                        v13[0],
                        v12,
                        (const unsigned __int16 *)v8,
                        v10);
  if ( ElementDescriptor >= 0 )
    ElementDescriptor = 1;
LABEL_12:
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v14);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v15);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v11);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v12);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v13);
  return (unsigned int)ElementDescriptor;
}

```

## disassembly

```asm
0x18000ece0  mov     [rsp-18h+arg_0], rbx
0x18000ece5  mov     [rsp-18h+arg_8], rsi
0x18000ecea  push    rbp
0x18000eceb  push    rdi
0x18000ecec  push    r14
0x18000ecee  mov     rbp, rsp
0x18000ecf1  sub     rsp, 50h
0x18000ecf5  mov     r14, rcx
0x18000ecf8  mov     [rbp+var_10], 0
0x18000ed00  lea     rcx, [rbp+arg_18]
0x18000ed04  mov     [rbp+var_18], 0
0x18000ed0c  mov     rdi, r8
0x18000ed0f  mov     [rbp+var_20.lpVtbl], 0
0x18000ed17  mov     rsi, rdx
0x18000ed1a  mov     [rbp+arg_18], 0
0x18000ed22  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000ed27  lea     rcx, [rbp+arg_10]
0x18000ed2b  mov     [rbp+arg_18], 0
0x18000ed33  mov     [rbp+arg_10], 0
0x18000ed3b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000ed40  mov     rax, [rdi]
0x18000ed43  lea     rdx, [rbp+var_18]
0x18000ed47  mov     rcx, rdi
0x18000ed4a  mov     [rbp+arg_10], 0
0x18000ed52  mov     rax, [rax+148h]
0x18000ed59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed5e  mov     ebx, eax
0x18000ed60  test    eax, eax
0x18000ed62  js      short loc_18000EDB5
0x18000ed64  mov     rax, [rdi]
0x18000ed67  lea     rdx, [rbp+var_10]
0x18000ed6b  mov     rcx, rdi
0x18000ed6e  mov     rax, [rax+138h]
0x18000ed75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed7a  mov     ebx, eax
0x18000ed7c  test    eax, eax
0x18000ed7e  js      short loc_18000EDB5
0x18000ed80  mov     rax, [rdi]
0x18000ed83  lea     rdx, [rbp+arg_18]
0x18000ed87  mov     rcx, rdi
0x18000ed8a  mov     rax, [rax+58h]
0x18000ed8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed93  mov     ebx, eax
0x18000ed95  test    eax, eax
0x18000ed97  js      short loc_18000EDB5
0x18000ed99  mov     rcx, [rbp+arg_18]
0x18000ed9d  lea     r8, [rbp+arg_10]
0x18000eda1  lea     rdx, IID_IXMLDOMElement
0x18000eda8  mov     rax, [rcx]
0x18000edab  mov     rax, [rax]
0x18000edae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edb3  mov     ebx, eax
0x18000edb5  mov     edi, 1
0x18000edba  cmp     ebx, 80004002h
0x18000edc0  jz      short loc_18000EDE8
0x18000edc2  test    ebx, ebx
0x18000edc4  js      short loc_18000EE0E
0x18000edc6  mov     rdx, [rbp+arg_10]; struct IXMLDOMElement *
0x18000edca  lea     r8, [rbp+var_20]; struct IXMLDOMElement *
0x18000edce  mov     r9d, edi; unsigned __int16 **
0x18000edd1  mov     rcx, rsi; this
0x18000edd4  call    ?GetElementDescriptor@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEAPEAGH@Z; NPrintTicketUtil::GetElementDescriptor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort * *,int)
0x18000edd9  mov     ebx, eax
0x18000eddb  test    eax, eax
0x18000eddd  js      short loc_18000EE0E
0x18000eddf  mov     rax, [rbp+var_20.lpVtbl]
0x18000ede3  test    rax, rax
0x18000ede6  jnz     short loc_18000EDEA
0x18000ede8  xor     eax, eax
0x18000edea  mov     r9, [rbp+var_18]; unsigned __int16 *
0x18000edee  lea     rcx, [r14+8]; this
0x18000edf2  mov     r8, [rbp+var_10]; unsigned __int16 *
0x18000edf6  lea     rdx, aElementSSIsNot; "Element %s:%s is not allowed within nod"...
0x18000edfd  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x18000ee02  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000ee07  test    eax, eax
0x18000ee09  mov     ebx, eax
0x18000ee0b  cmovns  ebx, edi
0x18000ee0e  lea     rcx, [rbp+arg_10]
0x18000ee12  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000ee17  lea     rcx, [rbp+arg_18]
0x18000ee1b  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000ee20  lea     rcx, [rbp+var_20]
0x18000ee24  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000ee29  lea     rcx, [rbp+var_18]
0x18000ee2d  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000ee32  lea     rcx, [rbp+var_10]
0x18000ee36  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000ee3b  mov     rsi, [rsp+50h+arg_8]
0x18000ee40  mov     eax, ebx
0x18000ee42  mov     rbx, [rsp+50h+arg_0]
0x18000ee47  add     rsp, 50h
0x18000ee4b  pop     r14
0x18000ee4d  pop     rdi
0x18000ee4e  pop     rbp
0x18000ee4f  retn
```
