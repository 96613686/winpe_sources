# CPrintTicketMergeFilter::OptionVisitor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *)

- ea: `0x18000e460`
- end: `0x18000e56b`
- name: `?OptionVisitor@CPrintTicketMergeFilter@@UEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(CPrintTicketMergeFilter *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180002404`
- `0x180004b00`
- `0x180006c74`
- `0x180006f80`
- `0x18000e460`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000e542`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e553`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e542`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e553`

## pseudocode

```c
__int64 __fastcall CPrintTicketMergeFilter::OptionVisitor(
        CPrintTicketMergeFilter *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3)
{
  int NameAttribute; // eax
  const unsigned __int16 *v6; // r9
  struct IXMLDOMElement *v7; // rdx
  unsigned int v8; // edi
  BSTR bstrString; // [rsp+30h] [rbp-10h] BYREF
  BSTR v11; // [rsp+38h] [rbp-8h] BYREF
  struct IXMLDOMElement *v12; // [rsp+68h] [rbp+28h] BYREF

  v11 = 0;
  bstrString = 0;
  v12 = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(a2, a3, &bstrString, &v11, 0);
  if ( NameAttribute )
  {
    if ( NameAttribute < 0 )
      goto LABEL_7;
    NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
                      *((__int64 ***)this + 1),
                      *((struct IXMLDOMElement **)this + 4),
                      (struct IXMLDOMElement *)L"Option",
                      v6,
                      &v12);
  }
  else
  {
    NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                      *((__int64 ***)this + 1),
                      *((struct IXMLDOMElement **)this + 4),
                      bstrString,
                      v11,
                      &v12);
  }
  if ( NameAttribute >= 0 )
  {
    v7 = v12;
    *((_DWORD *)this + 6) = 1;
    NameAttribute = CPrintTicketMergeFilter::VisitContext(this, v7, a3);
    *((_DWORD *)this + 6) = 0;
  }
LABEL_7:
  v8 = 0;
  if ( NameAttribute != 1 )
    v8 = NameAttribute;
  if ( v12 )
  {
    ((void (*)(void))v12->lpVtbl->Release)();
    v12 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v11 )
    SysFreeString(v11);
  return v8;
}

```

## disassembly

```asm
0x18000e460  mov     [rsp-8+arg_0], rdi
0x18000e465  mov     [rsp-8+arg_8], r14
0x18000e46a  push    rbp
0x18000e46b  mov     rbp, rsp
0x18000e46e  sub     rsp, 40h
0x18000e472  mov     r14, r8
0x18000e475  mov     [rbp+var_8], 0
0x18000e47d  mov     rax, rdx
0x18000e480  mov     [rbp+bstrString], 0
0x18000e488  mov     rdi, rcx
0x18000e48b  mov     [rbp+arg_18], 0
0x18000e493  mov     rdx, r14; struct IXMLDOMElement *
0x18000e496  mov     dword ptr [rsp+40h+var_20], 0; int
0x18000e49e  mov     rcx, rax; this
0x18000e4a1  lea     r9, [rbp+var_8]; unsigned __int16 **
0x18000e4a5  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18000e4a9  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18000e4ae  test    eax, eax
0x18000e4b0  jnz     short loc_18000E4D2
0x18000e4b2  mov     r9, [rbp+var_8]; unsigned __int16 *
0x18000e4b6  lea     rax, [rbp+arg_18]
0x18000e4ba  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x18000e4be  mov     rdx, [rdi+20h]; struct IXMLDOMElement *
0x18000e4c2  mov     rcx, [rdi+8]; this
0x18000e4c6  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x18000e4cb  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000e4d0  jmp     short loc_18000E4F1
0x18000e4d2  js      short loc_18000E512
0x18000e4d4  mov     rdx, [rdi+20h]; struct IXMLDOMElement *
0x18000e4d8  lea     rax, [rbp+arg_18]
0x18000e4dc  mov     rcx, [rdi+8]; this
0x18000e4e0  lea     r8, aOption; "Option"
0x18000e4e7  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x18000e4ec  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000e4f1  test    eax, eax
0x18000e4f3  js      short loc_18000E512
0x18000e4f5  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18000e4f9  mov     r8, r14; struct IXMLDOMElement *
0x18000e4fc  mov     rcx, rdi; this
0x18000e4ff  mov     dword ptr [rdi+18h], 1
0x18000e506  call    ?VisitContext@CPrintTicketMergeFilter@@AEAAJPEAUIXMLDOMElement@@0@Z; CPrintTicketMergeFilter::VisitContext(IXMLDOMElement *,IXMLDOMElement *)
0x18000e50b  mov     dword ptr [rdi+18h], 0
0x18000e512  mov     rcx, [rbp+arg_18]
0x18000e516  xor     edi, edi
0x18000e518  cmp     eax, 1
0x18000e51b  cmovnz  edi, eax
0x18000e51e  test    rcx, rcx
0x18000e521  jz      short loc_18000E537
0x18000e523  mov     rax, [rcx]
0x18000e526  mov     rax, [rax+10h]
0x18000e52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e52f  mov     [rbp+arg_18], 0
0x18000e537  cmp     [rbp+bstrString], 0
0x18000e53c  jz      short loc_18000E548
0x18000e53e  mov     rcx, [rbp+bstrString]; bstrString
0x18000e542  call    cs:__imp_SysFreeString
0x18000e548  cmp     [rbp+var_8], 0
0x18000e54d  jz      short loc_18000E559
0x18000e54f  mov     rcx, [rbp+var_8]; bstrString
0x18000e553  call    cs:__imp_SysFreeString
0x18000e559  mov     r14, [rsp+40h+arg_8]
0x18000e55e  mov     eax, edi
0x18000e560  mov     rdi, [rsp+40h+arg_0]
0x18000e565  add     rsp, 40h
0x18000e569  pop     rbp
0x18000e56a  retn
```
