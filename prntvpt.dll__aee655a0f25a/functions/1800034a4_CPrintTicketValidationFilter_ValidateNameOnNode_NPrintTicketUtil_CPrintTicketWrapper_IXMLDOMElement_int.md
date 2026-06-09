# CPrintTicketValidationFilter::ValidateNameOnNode(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,int)

- ea: `0x1800034a4`
- end: `0x180003702`
- name: `?ValidateNameOnNode@CPrintTicketValidationFilter@@IEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@H@Z`
- size: `606`
- prototype: `int(CPrintTicketValidationFilter *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002734`
- `0x180005b10`

## callees

- `0x180003318`
- `0x1800034a4`
- `0x180004b00`
- `0x1800056e0`
- `0x180005e70`
- `0x18001d30c`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800035bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800035cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800035bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800035cc`

## string_xrefs

- `0x180003543`: `An unexpected error occured during validation of element %s: %s.`

## pseudocode

```c
__int64 __fastcall CPrintTicketValidationFilter::ValidateNameOnNode(
        CPrintTicketValidationFilter *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3)
{
  int NameAttribute; // r8d
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int ElementDescriptor; // ebx
  struct IXMLDOMElement *v9; // rcx
  HRESULT (__stdcall *get_attributes)(IXMLDOMElement *, IXMLDOMNamedNodeMap **); // rax
  bool v12; // sf
  int v13; // [rsp+20h] [rbp-58h]
  const unsigned __int16 *v14; // [rsp+28h] [rbp-50h]
  BSTR bstrString; // [rsp+30h] [rbp-48h] BYREF
  BSTR v16; // [rsp+38h] [rbp-40h] BYREF
  __int64 v17; // [rsp+40h] [rbp-38h] BYREF
  struct IXMLDOMElement v18; // [rsp+48h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-28h] BYREF
  struct IXMLDOMElement v20; // [rsp+58h] [rbp-20h] BYREF
  struct IXMLDOMElement v21; // [rsp+60h] [rbp-18h] BYREF

  v16 = 0;
  bstrString = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(a2, a3, &bstrString, &v16, 1);
  if ( NameAttribute >= 0 )
  {
    if ( bstrString && v16 )
    {
      ElementDescriptor = 0;
      goto LABEL_15;
    }
    v18.lpVtbl = 0;
    ElementDescriptor = NPrintTicketUtil::GetElementDescriptor(a2, a3, &v18, (unsigned __int16 **)1, v13);
    if ( ElementDescriptor >= 0 )
      ElementDescriptor = CValidationStatus::SetValidationFailure(
                            (CPrintTicketValidationFilter *)((char *)this + 8),
                            L"The element %s requires a name attribute.",
                            (const unsigned __int16 *)v18.lpVtbl,
                            0,
                            0,
                            v14);
    v9 = &v18;
  }
  else
  {
    lpVtbl = a3->lpVtbl;
    v21.lpVtbl = 0;
    v20.lpVtbl = 0;
    if ( NameAttribute == -1072897499 )
    {
      get_attributes = lpVtbl->get_attributes;
      v18.lpVtbl = 0;
      v17 = 0;
      ElementDescriptor = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))get_attributes)(a3, &v17);
      if ( ElementDescriptor >= 0 )
        ElementDescriptor = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct IXMLDOMElement *))(*(_QWORD *)v17 + 56LL))(
                              v17,
                              L"name",
                              &v18);
      v12 = ElementDescriptor < 0;
      if ( !ElementDescriptor )
      {
        v19 = 0;
        ElementDescriptor = (*(__int64 (__fastcall **)(struct IXMLDOMElementVtbl *, GUID *, __int64 *))v18.lpVtbl->QueryInterface)(
                              v18.lpVtbl,
                              &IID_IXMLDOMAttribute,
                              &v19);
        if ( ElementDescriptor >= 0 )
          ElementDescriptor = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMElement *))(*(_QWORD *)v19 + 208LL))(
                                v19,
                                &v21);
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v18);
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v19);
        v12 = ElementDescriptor < 0;
      }
      if ( !v12 )
      {
        ElementDescriptor = NPrintTicketUtil::GetElementDescriptor(a2, a3, &v20, 0, v13);
        if ( ElementDescriptor >= 0 )
          ElementDescriptor = CValidationStatus::SetValidationFailure(
                                (CPrintTicketValidationFilter *)((char *)this + 8),
                                L"The element %s contains the invalid name '%s'.",
                                (const unsigned __int16 *)v20.lpVtbl,
                                (const unsigned __int16 *)v21.lpVtbl,
                                0,
                                v14);
      }
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v17 = 0;
      }
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v18);
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v20);
      v9 = &v21;
    }
    else
    {
      ElementDescriptor = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement *))lpVtbl->get_text)(
                            a3,
                            &v20);
      if ( ElementDescriptor >= 0 )
      {
        ElementDescriptor = NPrintTicketUtil::GetElementDescriptor(a2, a3, &v21, (unsigned __int16 **)1, v13);
        if ( ElementDescriptor >= 0 )
          ElementDescriptor = CValidationStatus::SetValidationFailure(
                                (CPrintTicketValidationFilter *)((char *)this + 8),
                                L"An unexpected error occured during validation of element %s: %s.",
                                (const unsigned __int16 *)v21.lpVtbl,
                                (const unsigned __int16 *)v20.lpVtbl,
                                0,
                                v14);
      }
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v21);
      v9 = &v20;
    }
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v9);
  if ( ElementDescriptor >= 0 )
    ElementDescriptor = 1;
LABEL_15:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v16 )
    SysFreeString(v16);
  return (unsigned int)ElementDescriptor;
}

```

## disassembly

```asm
0x1800034a4  push    rbp
0x1800034a6  push    rbx
0x1800034a7  push    rdi
0x1800034a8  push    r12
0x1800034aa  push    r13
0x1800034ac  push    r15
0x1800034ae  mov     rbp, rsp
0x1800034b1  sub     rsp, 78h
0x1800034b5  xor     r12d, r12d
0x1800034b8  lea     r9, [rbp+var_40]; unsigned __int16 **
0x1800034bc  mov     rdi, r8
0x1800034bf  mov     [rbp+var_40], r12
0x1800034c3  mov     r15, rdx
0x1800034c6  mov     [rbp+bstrString], r12
0x1800034ca  mov     r13, rcx
0x1800034cd  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x1800034d1  lea     ebx, [r12+1]
0x1800034d6  mov     rdx, rdi; struct IXMLDOMElement *
0x1800034d9  mov     rcx, r15; this
0x1800034dc  mov     dword ptr [rsp+78h+var_58], ebx; int
0x1800034e0  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x1800034e5  mov     r8d, eax
0x1800034e8  test    eax, eax
0x1800034ea  jns     short loc_180003565
0x1800034ec  mov     rax, [rdi]
0x1800034ef  mov     rcx, rdi
0x1800034f2  mov     [rbp+var_18.lpVtbl], r12
0x1800034f6  mov     [rbp+var_20.lpVtbl], r12
0x1800034fa  cmp     r8d, 0C00CE225h
0x180003501  jz      loc_180003622
0x180003507  mov     rax, [rax+0D0h]
0x18000350e  lea     rdx, [rbp+var_20]
0x180003512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003517  mov     ebx, eax
0x180003519  test    eax, eax
0x18000351b  js      short loc_180003556
0x18000351d  lea     r9d, [r12+1]; unsigned __int16 **
0x180003522  mov     rdx, rdi; struct IXMLDOMElement *
0x180003525  lea     r8, [rbp+var_18]; struct IXMLDOMElement *
0x180003529  mov     rcx, r15; this
0x18000352c  call    ?GetElementDescriptor@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEAPEAGH@Z; NPrintTicketUtil::GetElementDescriptor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort * *,int)
0x180003531  mov     ebx, eax
0x180003533  test    eax, eax
0x180003535  js      short loc_180003556
0x180003537  mov     r9, [rbp+var_20.lpVtbl]; unsigned __int16 *
0x18000353b  lea     rcx, [r13+8]; this
0x18000353f  mov     r8, [rbp+var_18.lpVtbl]; unsigned __int16 *
0x180003543  lea     rdx, aAnUnexpectedEr; "An unexpected error occured during vali"...
0x18000354a  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x18000354f  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180003554  mov     ebx, eax
0x180003556  lea     rcx, [rbp+var_18]
0x18000355a  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000355f  lea     rcx, [rbp+var_20]
0x180003563  jmp     short loc_1800035A5
0x180003565  cmp     [rbp+bstrString], r12
0x180003569  jz      short loc_1800035E2
0x18000356b  cmp     [rbp+var_40], r12
0x18000356f  jz      short loc_1800035E2
0x180003571  mov     ebx, r12d
0x180003574  jmp     short loc_1800035B2
0x180003576  mov     rcx, [rbp+var_38]
0x18000357a  test    rcx, rcx
0x18000357d  jz      short loc_18000358F
0x18000357f  mov     rax, [rcx]
0x180003582  mov     rax, [rax+10h]
0x180003586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000358b  mov     [rbp+var_38], r12
0x18000358f  lea     rcx, [rbp+var_30]
0x180003593  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180003598  lea     rcx, [rbp+var_20]
0x18000359c  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x1800035a1  lea     rcx, [rbp+var_18]
0x1800035a5  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x1800035aa  test    ebx, ebx
0x1800035ac  jns     loc_1800036F8
0x1800035b2  cmp     [rbp+bstrString], r12
0x1800035b6  jz      short loc_1800035C2
0x1800035b8  mov     rcx, [rbp+bstrString]; bstrString
0x1800035bc  call    cs:__imp_SysFreeString
0x1800035c2  cmp     [rbp+var_40], r12
0x1800035c6  jz      short loc_1800035D2
0x1800035c8  mov     rcx, [rbp+var_40]; bstrString
0x1800035cc  call    cs:__imp_SysFreeString
0x1800035d2  mov     eax, ebx
0x1800035d4  add     rsp, 78h
0x1800035d8  pop     r15
0x1800035da  pop     r13
0x1800035dc  pop     r12
0x1800035de  pop     rdi
0x1800035df  pop     rbx
0x1800035e0  pop     rbp
0x1800035e1  retn
0x1800035e2  mov     r9d, ebx; unsigned __int16 **
0x1800035e5  mov     [rbp+var_30.lpVtbl], r12
0x1800035e9  lea     r8, [rbp+var_30]; struct IXMLDOMElement *
0x1800035ed  mov     rdx, rdi; struct IXMLDOMElement *
0x1800035f0  mov     rcx, r15; this
0x1800035f3  call    ?GetElementDescriptor@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEAPEAGH@Z; NPrintTicketUtil::GetElementDescriptor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort * *,int)
0x1800035f8  mov     ebx, eax
0x1800035fa  test    eax, eax
0x1800035fc  js      short loc_18000361C
0x1800035fe  mov     r8, [rbp+var_30.lpVtbl]; unsigned __int16 *
0x180003602  lea     rcx, [r13+8]; this
0x180003606  xor     r9d, r9d; unsigned __int16 *
0x180003609  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x18000360e  lea     rdx, aTheElementSReq; "The element %s requires a name attribut"...
0x180003615  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000361a  mov     ebx, eax
0x18000361c  lea     rcx, [rbp+var_30]
0x180003620  jmp     short loc_1800035A5
0x180003622  mov     rax, [rax+88h]
0x180003629  lea     rdx, [rbp+var_38]
0x18000362d  mov     [rbp+var_30.lpVtbl], r12
0x180003631  mov     [rbp+var_38], r12
0x180003635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000363a  mov     ebx, eax
0x18000363c  test    eax, eax
0x18000363e  js      short loc_18000365D
0x180003640  mov     rcx, [rbp+var_38]
0x180003644  lea     r8, [rbp+var_30]
0x180003648  lea     rdx, aName; "name"
0x18000364f  mov     rax, [rcx]
0x180003652  mov     rax, [rax+38h]
0x180003656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000365b  mov     ebx, eax
0x18000365d  test    ebx, ebx
0x18000365f  jnz     short loc_1800036B2
0x180003661  mov     rcx, [rbp+var_30.lpVtbl]
0x180003665  lea     r8, [rbp+var_28]
0x180003669  mov     [rbp+var_28], r12
0x18000366d  lea     rdx, IID_IXMLDOMAttribute
0x180003674  mov     rax, [rcx]
0x180003677  mov     rax, [rax]
0x18000367a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000367f  mov     ebx, eax
0x180003681  test    eax, eax
0x180003683  js      short loc_18000369E
0x180003685  mov     rcx, [rbp+var_28]
0x180003689  lea     rdx, [rbp+var_18]
0x18000368d  mov     rax, [rcx]
0x180003690  mov     rax, [rax+0D0h]
0x180003697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369c  mov     ebx, eax
0x18000369e  lea     rcx, [rbp+var_30]
0x1800036a2  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x1800036a7  lea     rcx, [rbp+var_28]
0x1800036ab  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x1800036b0  test    ebx, ebx
0x1800036b2  js      loc_180003576
0x1800036b8  xor     r9d, r9d; unsigned __int16 **
0x1800036bb  lea     r8, [rbp+var_20]; struct IXMLDOMElement *
0x1800036bf  mov     rdx, rdi; struct IXMLDOMElement *
0x1800036c2  mov     rcx, r15; this
0x1800036c5  call    ?GetElementDescriptor@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEAPEAGH@Z; NPrintTicketUtil::GetElementDescriptor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort * *,int)
0x1800036ca  mov     ebx, eax
0x1800036cc  test    eax, eax
0x1800036ce  js      loc_180003576
0x1800036d4  mov     r9, [rbp+var_18.lpVtbl]; unsigned __int16 *
0x1800036d8  lea     rcx, [r13+8]; this
0x1800036dc  mov     r8, [rbp+var_20.lpVtbl]; unsigned __int16 *
0x1800036e0  lea     rdx, aTheElementSCon; "The element %s contains the invalid nam"...
0x1800036e7  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x1800036ec  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800036f1  mov     ebx, eax
0x1800036f3  jmp     loc_180003576
0x1800036f8  mov     ebx, 1
0x1800036fd  jmp     loc_1800035B2
```
