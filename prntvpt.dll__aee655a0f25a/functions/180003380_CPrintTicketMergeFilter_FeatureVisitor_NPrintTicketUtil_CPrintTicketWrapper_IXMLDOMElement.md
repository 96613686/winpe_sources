# CPrintTicketMergeFilter::FeatureVisitor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *)

- ea: `0x180003380`
- end: `0x18000349b`
- name: `?FeatureVisitor@CPrintTicketMergeFilter@@UEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(CPrintTicketMergeFilter *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180002404`
- `0x180003380`
- `0x180004b00`
- `0x1800095a0`
- `0x18000e084`
- `0x18000e364`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003478`
- `OLEAUT32!__imp_SysFreeString` at `0x180003489`
- `OLEAUT32!__imp_SysFreeString` at `0x180003478`
- `OLEAUT32!__imp_SysFreeString` at `0x180003489`

## pseudocode

```c
__int64 __fastcall CPrintTicketMergeFilter::FeatureVisitor(
        CPrintTicketMergeFilter *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3)
{
  struct IXMLDOMElement *v5; // rbx
  int NameAttribute; // eax
  unsigned int v7; // edi
  BSTR bstrString; // [rsp+30h] [rbp-18h] BYREF
  BSTR v10; // [rsp+38h] [rbp-10h] BYREF
  struct IXMLDOMElement *v11; // [rsp+88h] [rbp+40h] BYREF

  v10 = 0;
  bstrString = 0;
  v5 = 0;
  v11 = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(a2, a3, &bstrString, &v10, 0);
  if ( NameAttribute >= 0 )
  {
    NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetFeature(
                      *((NPrintTicketUtil::CPrintTicketWrapper **)this + 1),
                      *((struct IXMLDOMElement **)this + 4),
                      bstrString,
                      v10,
                      &v11);
    v5 = v11;
    if ( NameAttribute >= 0 )
    {
      if ( v11 )
      {
        NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(
                          *((NPrintTicketUtil::CPrintTicketWrapper **)this + 1),
                          (char *)L"Option",
                          (__int64 (__fastcall *)(NPrintTicketUtil::CPrintTicketWrapper *, __int64, void *))NPrintTicketUtil::DeleteElementOnVisit,
                          0,
                          v11);
        if ( NameAttribute < 0 )
          goto LABEL_8;
        if ( v5 )
          goto LABEL_7;
      }
      NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                        *((NPrintTicketUtil::CPrintTicketWrapper **)this + 1),
                        *((struct IXMLDOMElement **)this + 4),
                        bstrString,
                        v10,
                        &v11);
      v5 = v11;
      if ( NameAttribute >= 0 )
LABEL_7:
        NameAttribute = CPrintTicketMergeFilter::VisitContext(this, v5, a3);
    }
  }
LABEL_8:
  v7 = 0;
  if ( NameAttribute < 0 )
    v7 = NameAttribute;
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v5->lpVtbl->Release)(v5);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v10 )
    SysFreeString(v10);
  return v7;
}

```

## disassembly

```asm
0x180003380  push    rbp
0x180003382  push    rbx
0x180003383  push    rdi
0x180003384  push    r15
0x180003386  mov     rbp, rsp
0x180003389  sub     rsp, 48h
0x18000338d  mov     r15, r8
0x180003390  mov     [rbp+var_10], 0
0x180003398  mov     rax, rdx
0x18000339b  mov     [rbp+bstrString], 0
0x1800033a3  mov     rdi, rcx
0x1800033a6  lea     r9, [rbp+var_10]; unsigned __int16 **
0x1800033aa  xor     ebx, ebx
0x1800033ac  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x1800033b0  mov     rdx, r15; struct IXMLDOMElement *
0x1800033b3  mov     [rbp+arg_18], rbx
0x1800033b7  mov     rcx, rax; this
0x1800033ba  mov     dword ptr [rsp+48h+var_28], ebx; int
0x1800033be  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x1800033c3  test    eax, eax
0x1800033c5  js      loc_180003452
0x1800033cb  mov     r9, [rbp+var_10]; unsigned __int16 *
0x1800033cf  lea     rax, [rbp+arg_18]
0x1800033d3  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x1800033d7  mov     rdx, [rdi+20h]; struct IXMLDOMElement *
0x1800033db  mov     rcx, [rdi+8]; this
0x1800033df  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x1800033e4  call    ?GetFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800033e9  mov     rbx, [rbp+arg_18]
0x1800033ed  test    eax, eax
0x1800033ef  js      short loc_180003452
0x1800033f1  test    rbx, rbx
0x1800033f4  jz      short loc_18000341E
0x1800033f6  mov     rcx, [rdi+8]; this
0x1800033fa  lea     r8, ?DeleteElementOnVisit@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEAX@Z; int (*)(struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, void *)
0x180003401  xor     r9d, r9d; void *
0x180003404  mov     [rsp+48h+var_28], rbx; struct IXMLDOMElement *
0x180003409  lea     rdx, aOption; "Option"
0x180003410  call    ?VisitNodes@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBGP6AJPEAV12@PEAUIXMLDOMElement@@PEAX@Z32@Z; NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(ushort const *,long (*)(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,void *),void *,IXMLDOMElement *)
0x180003415  test    eax, eax
0x180003417  js      short loc_180003452
0x180003419  test    rbx, rbx
0x18000341c  jnz     short loc_180003444
0x18000341e  mov     r9, [rbp+var_10]; unsigned __int16 *
0x180003422  lea     rax, [rbp+arg_18]
0x180003426  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x18000342a  mov     rdx, [rdi+20h]; struct IXMLDOMElement *
0x18000342e  mov     rcx, [rdi+8]; this
0x180003432  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x180003437  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000343c  mov     rbx, [rbp+arg_18]
0x180003440  test    eax, eax
0x180003442  js      short loc_180003452
0x180003444  mov     r8, r15; struct IXMLDOMElement *
0x180003447  mov     rdx, rbx; struct IXMLDOMElement *
0x18000344a  mov     rcx, rdi; this
0x18000344d  call    ?VisitContext@CPrintTicketMergeFilter@@AEAAJPEAUIXMLDOMElement@@0@Z; CPrintTicketMergeFilter::VisitContext(IXMLDOMElement *,IXMLDOMElement *)
0x180003452  xor     edi, edi
0x180003454  test    eax, eax
0x180003456  cmovs   edi, eax
0x180003459  test    rbx, rbx
0x18000345c  jz      short loc_18000346D
0x18000345e  mov     rax, [rbx]
0x180003461  mov     rcx, rbx
0x180003464  mov     rax, [rax+10h]
0x180003468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000346d  cmp     [rbp+bstrString], 0
0x180003472  jz      short loc_18000347E
0x180003474  mov     rcx, [rbp+bstrString]; bstrString
0x180003478  call    cs:__imp_SysFreeString
0x18000347e  cmp     [rbp+var_10], 0
0x180003483  jz      short loc_18000348F
0x180003485  mov     rcx, [rbp+var_10]; bstrString
0x180003489  call    cs:__imp_SysFreeString
0x18000348f  mov     eax, edi
0x180003491  add     rsp, 48h
0x180003495  pop     r15
0x180003497  pop     rdi
0x180003498  pop     rbx
0x180003499  pop     rbp
0x18000349a  retn
```
