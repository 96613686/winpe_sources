# CPrintTicketMergeFilter::MergePropertyOnVisit(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,int)

- ea: `0x1800014e0`
- end: `0x180001660`
- name: `?MergePropertyOnVisit@CPrintTicketMergeFilter@@AEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@H@Z`
- size: `384`
- prototype: `__int64 __fastcall(CPrintTicketMergeFilter *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000e070`
- `0x180020010`

## callees

- `0x1800014e0`
- `0x1800019f0`
- `0x180002404`
- `0x180004b00`
- `0x1800095a0`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000163d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000164b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000163d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000164b`

## pseudocode

```c
__int64 __fastcall CPrintTicketMergeFilter::MergePropertyOnVisit(
        CPrintTicketMergeFilter *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3,
        int a4)
{
  int NameAttribute; // eax
  const unsigned __int16 *v8; // r9
  OLECHAR *v9; // rdi
  OLECHAR *v10; // rsi
  NPrintTicketUtil::CPrintTicketWrapper *v11; // rcx
  unsigned int v12; // ebx
  struct IXMLDOMElement *v14; // [rsp+50h] [rbp-28h] BYREF
  BSTR v15; // [rsp+58h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-18h] BYREF

  v15 = 0;
  bstrString = 0;
  v14 = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(a2, a3, &bstrString, &v15, 0);
  v9 = v15;
  v10 = bstrString;
  if ( NameAttribute >= 0 )
  {
    NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
                      *((NPrintTicketUtil::CPrintTicketWrapper **)this + 1),
                      *((struct IXMLDOMElement **)this + 4),
                      L"Property",
                      v8,
                      (char *)v15,
                      bstrString,
                      &v14);
    if ( NameAttribute >= 0 )
    {
      v11 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 1);
      if ( v14 )
      {
        NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(
                          v11,
                          (char *)&stru_180026B28,
                          (__int64 (__fastcall *)(NPrintTicketUtil::CPrintTicketWrapper *, __int64, void *))NPrintTicketUtil::DeleteElementOnVisit,
                          0,
                          v14);
        if ( NameAttribute < 0 )
          goto LABEL_9;
        NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(
                          *((NPrintTicketUtil::CPrintTicketWrapper **)this + 1),
                          (char *)L"ParameterRef",
                          (__int64 (__fastcall *)(NPrintTicketUtil::CPrintTicketWrapper *, __int64, void *))NPrintTicketUtil::DeleteElementOnVisit,
                          0,
                          v14);
      }
      else
      {
        NameAttribute = (*(__int64 (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper *, _QWORD, OLECHAR *, OLECHAR *, _QWORD, int, _QWORD, _QWORD, struct IXMLDOMElement **))(*(_QWORD *)v11 + 8LL))(
                          v11,
                          *((_QWORD *)this + 4),
                          v10,
                          v9,
                          0,
                          a4,
                          0,
                          0,
                          &v14);
      }
      if ( NameAttribute >= 0 )
        NameAttribute = CPrintTicketMergeFilter::VisitContext(this, v14, a3);
    }
  }
LABEL_9:
  v12 = 0;
  if ( NameAttribute < 0 )
    v12 = NameAttribute;
  if ( v14 )
  {
    ((void (*)(void))v14->lpVtbl->Release)();
    v14 = 0;
  }
  if ( v10 )
    SysFreeString(v10);
  if ( v9 )
    SysFreeString(v9);
  return v12;
}

```

## disassembly

```asm
0x1800014e0  push    rbp
0x1800014e2  push    rbx
0x1800014e3  push    rsi
0x1800014e4  push    rdi
0x1800014e5  push    r14
0x1800014e7  push    r15
0x1800014e9  mov     rbp, rsp
0x1800014ec  sub     rsp, 78h
0x1800014f0  mov     r14, r8
0x1800014f3  mov     [rbp+var_20], 0
0x1800014fb  mov     rax, rdx
0x1800014fe  mov     [rbp+bstrString], 0
0x180001506  mov     r15d, r9d
0x180001509  mov     [rbp+var_28], 0
0x180001511  mov     rbx, rcx
0x180001514  mov     dword ptr [rsp+78h+var_58], 0; int
0x18000151c  mov     rdx, r14; struct IXMLDOMElement *
0x18000151f  lea     r9, [rbp+var_20]; unsigned __int16 **
0x180001523  mov     rcx, rax; this
0x180001526  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18000152a  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18000152f  mov     rdi, [rbp+var_20]
0x180001533  mov     rsi, [rbp+bstrString]
0x180001537  test    eax, eax
0x180001539  js      loc_180001611
0x18000153f  mov     rdx, [rbx+20h]; struct IXMLDOMElement *
0x180001543  lea     rax, [rbp+var_28]
0x180001547  mov     rcx, [rbx+8]; this
0x18000154b  lea     r8, aProperty; "Property"
0x180001552  mov     [rsp+78h+var_48], rax; struct IXMLDOMElement **
0x180001557  mov     [rsp+78h+var_50], rsi; unsigned __int16 *
0x18000155c  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x180001561  call    ?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180001566  test    eax, eax
0x180001568  js      loc_180001611
0x18000156e  mov     rax, [rbp+var_28]
0x180001572  mov     rcx, [rbx+8]; this
0x180001576  test    rax, rax
0x180001579  jz      short loc_1800015BF
0x18000157b  xor     r9d, r9d; void *
0x18000157e  mov     [rsp+78h+var_58], rax; struct IXMLDOMElement *
0x180001583  lea     r8, ?DeleteElementOnVisit@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEAX@Z; int (*)(struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, void *)
0x18000158a  lea     rdx, stru_180026B28; unsigned __int16 *
0x180001591  call    ?VisitNodes@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBGP6AJPEAV12@PEAUIXMLDOMElement@@PEAX@Z32@Z; NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(ushort const *,long (*)(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,void *),void *,IXMLDOMElement *)
0x180001596  test    eax, eax
0x180001598  js      short loc_180001611
0x18000159a  mov     rax, [rbp+var_28]
0x18000159e  lea     r8, ?DeleteElementOnVisit@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEAX@Z; int (*)(struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, void *)
0x1800015a5  mov     rcx, [rbx+8]; this
0x1800015a9  lea     rdx, aParameterref; "ParameterRef"
0x1800015b0  xor     r9d, r9d; void *
0x1800015b3  mov     [rsp+78h+var_58], rax; struct IXMLDOMElement *
0x1800015b8  call    ?VisitNodes@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBGP6AJPEAV12@PEAUIXMLDOMElement@@PEAX@Z32@Z; NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(ushort const *,long (*)(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,void *),void *,IXMLDOMElement *)
0x1800015bd  jmp     short loc_1800015FE
0x1800015bf  mov     rax, [rcx]
0x1800015c2  lea     rdx, [rbp+var_28]
0x1800015c6  mov     [rsp+78h+var_38], rdx
0x1800015cb  mov     r9, rdi
0x1800015ce  mov     rdx, [rbx+20h]
0x1800015d2  mov     r8, rsi
0x1800015d5  mov     [rsp+78h+var_40], 0
0x1800015de  mov     rax, [rax+8]
0x1800015e2  mov     [rsp+78h+var_48], 0
0x1800015eb  mov     dword ptr [rsp+78h+var_50], r15d
0x1800015f0  mov     [rsp+78h+var_58], 0
0x1800015f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015fe  test    eax, eax
0x180001600  js      short loc_180001611
0x180001602  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x180001606  mov     r8, r14; struct IXMLDOMElement *
0x180001609  mov     rcx, rbx; this
0x18000160c  call    ?VisitContext@CPrintTicketMergeFilter@@AEAAJPEAUIXMLDOMElement@@0@Z; CPrintTicketMergeFilter::VisitContext(IXMLDOMElement *,IXMLDOMElement *)
0x180001611  mov     rcx, [rbp+var_28]
0x180001615  xor     ebx, ebx
0x180001617  test    eax, eax
0x180001619  cmovs   ebx, eax
0x18000161c  test    rcx, rcx
0x18000161f  jz      short loc_180001635
0x180001621  mov     rax, [rcx]
0x180001624  mov     rax, [rax+10h]
0x180001628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000162d  mov     [rbp+var_28], 0
0x180001635  test    rsi, rsi
0x180001638  jz      short loc_180001643
0x18000163a  mov     rcx, rsi; bstrString
0x18000163d  call    cs:__imp_SysFreeString
0x180001643  test    rdi, rdi
0x180001646  jz      short loc_180001651
0x180001648  mov     rcx, rdi; bstrString
0x18000164b  call    cs:__imp_SysFreeString
0x180001651  mov     eax, ebx
0x180001653  add     rsp, 78h
0x180001657  pop     r15
0x180001659  pop     r14
0x18000165b  pop     rdi
0x18000165c  pop     rsi
0x18000165d  pop     rbx
0x18000165e  pop     rbp
0x18000165f  retn
```
