# CPrintTicketMergeFilter::ValueVisitor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *)

- ea: `0x1800064a0`
- end: `0x18000687e`
- name: `?ValueVisitor@CPrintTicketMergeFilter@@UEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@@Z`
- size: `990`
- prototype: `int(CPrintTicketMergeFilter *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004acc`
- `0x1800056e0`
- `0x180005e70`
- `0x1800064a0`
- `0x180006884`
- `0x180006940`
- `0x180006d70`
- `0x1800070e0`
- `0x18000a070`
- `0x180022594`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006593`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065e9`
- `OLEAUT32!__imp_SysFreeString` at `0x180006691`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066a6`
- `OLEAUT32!__imp_SysFreeString` at `0x180006759`
- `OLEAUT32!__imp_SysFreeString` at `0x18000676f`
- `OLEAUT32!__imp_SysFreeString` at `0x180006593`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065e9`
- `OLEAUT32!__imp_SysFreeString` at `0x180006691`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066a6`
- `OLEAUT32!__imp_SysFreeString` at `0x180006759`
- `OLEAUT32!__imp_SysFreeString` at `0x18000676f`

## string_xrefs

- `0x180006844`: `http://www.w3.org/2001/XMLSchema`
- `0x180006736`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c
__int64 __fastcall CPrintTicketMergeFilter::ValueVisitor(
        CPrintTicketMergeFilter *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  NPrintTicketUtil::CPrintTicketWrapper *v4; // r14
  int v6; // r15d
  int Uri; // ebx
  __int64 v9; // rcx
  wchar_t *v10; // rsi
  unsigned __int16 *v11; // rdi
  struct NPrintTicketUtil::CPrintTicketWrapper *v13; // r9
  struct IXMLDOMElement *v14; // r8
  NPrintTicketUtil::CPrintTicketWrapper *v15; // rcx
  struct IXMLDOMElement *v16; // rdx
  NPrintTicketUtil *v17; // rcx
  OLECHAR *v18; // rcx
  OLECHAR *v19; // r14
  OLECHAR *v20; // rbx
  int v21; // eax
  OLECHAR *v22; // rdi
  int v23; // esi
  int LocalName; // eax
  int v25; // eax
  unsigned __int16 *v26; // [rsp+28h] [rbp-38h]
  BSTR v27; // [rsp+30h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-28h] BYREF
  __int64 v29; // [rsp+40h] [rbp-20h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-18h] BYREF
  BSTR v31[2]; // [rsp+50h] [rbp-10h] BYREF
  __int64 v33; // [rsp+B8h] [rbp+58h] BYREF

  lpVtbl = a3->lpVtbl;
  v4 = a2;
  v6 = 0;
  v29 = 0;
  Uri = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))lpVtbl->get_attributes)(a3, &v29);
  if ( Uri >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 120LL))(v29);
    v33 = 0;
    v23 = 0;
    v27 = 0;
    while ( 1 )
    {
      Uri = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v29 + 112LL))(v29, &v27);
      if ( Uri || v23 )
        break;
      if ( !(**(unsigned int (__fastcall ***)(BSTR, GUID *, __int64 *))v27)(v27, &IID_IXMLDOMAttribute, &v33) )
      {
        String1 = 0;
        v31[0] = 0;
        if ( (*(int (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v33 + 312LL))(v33, &String1) >= 0 )
          (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v33 + 328LL))(v33, v31);
        v20 = String1;
        v21 = wcscmp_0(String1, L"http://www.w3.org/2001/XMLSchema-instance");
        v22 = v31[0];
        if ( !v21 && !wcscmp_0(v31[0], L"type") )
          v23 = 1;
        if ( v22 )
        {
          SysFreeString(v22);
          v20 = String1;
          v31[0] = 0;
        }
        if ( v20 )
          SysFreeString(v20);
      }
      if ( v27 )
      {
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)v27 + 16LL))(v27);
        v27 = 0;
      }
      if ( !v23 )
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v33);
    }
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v27);
    v9 = v33;
    v4 = a2;
  }
  else
  {
    v9 = 0;
    v33 = 0;
  }
  String1 = 0;
  v10 = 0;
  bstrString = 0;
  v11 = 0;
  v31[0] = 0;
  if ( Uri >= 0 )
  {
    if ( v9 )
    {
      v27 = 0;
      Uri = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v9 + 208LL))(v9, &v27);
      if ( Uri >= 0 )
      {
        Uri = NPrintTicketUtil::CPrintTicketWrapper::getUri(v4, a3, v27, v31);
        if ( Uri >= 0 )
        {
          LocalName = NPrintTicketUtil::CPrintTicketWrapper::getLocalName(v15, v27, &String1);
          v10 = String1;
          Uri = LocalName;
          v25 = wcscmp_0(String1, L"QName");
          v11 = v31[0];
          if ( !v25 && !wcscmp_0(v31[0], L"http://www.w3.org/2001/XMLSchema") )
            v6 = 1;
          if ( Uri >= 0 )
          {
            v16 = (struct IXMLDOMElement *)*((_QWORD *)this + 4);
            v17 = (NPrintTicketUtil *)*((_QWORD *)this + 1);
            v31[0] = 0;
            Uri = NPrintTicketUtil::CreateQName(
                    v17,
                    v16,
                    (struct IXMLDOMElement *)v10,
                    v11,
                    (const unsigned __int16 *)v31,
                    (unsigned __int16 **)v26,
                    v27);
            if ( Uri >= 0 )
            {
              v18 = v27;
              if ( v27 )
              {
                SysFreeString(v27);
                v18 = 0;
                v27 = 0;
              }
              v19 = v31[0];
              if ( v18 )
                SysFreeString(v18);
              v27 = v19;
              v4 = a2;
            }
          }
        }
        else
        {
          v11 = v31[0];
        }
      }
      if ( v27 )
        SysFreeString(v27);
      if ( Uri < 0 )
        goto LABEL_10;
    }
    ((void (__fastcall *)(struct IXMLDOMElement *, BSTR *))a3->lpVtbl->get_text)(a3, &bstrString);
    if ( v6 )
    {
      v13 = (struct NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 4);
      v14 = (struct IXMLDOMElement *)*((_QWORD *)this + 1);
      v31[0] = 0;
      Uri = NPrintTicketUtil::MigrateQName(
              v4,
              (struct NPrintTicketUtil::CPrintTicketWrapper *)a3,
              v14,
              v13,
              (struct IXMLDOMElement *)bstrString,
              (const unsigned __int16 *)v31,
              (unsigned __int16 **)v27);
      if ( Uri < 0 )
      {
LABEL_10:
        if ( v11 )
          SysFreeString(v11);
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        if ( v10 )
          SysFreeString(v10);
        v9 = v33;
        goto LABEL_4;
      }
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&bstrString);
      NCoreLibrary::TAutoPtrBSTR::operator=(&bstrString, v31[0]);
    }
    Uri = NPrintTicketUtil::CPrintTicketWrapper::CreateValue(
            *((__int64 ***)this + 1),
            *((struct IXMLDOMElement **)this + 4),
            bstrString,
            v11,
            (struct IXMLDOMElement *)v10,
            (struct IXMLDOMElement **)v26);
    goto LABEL_10;
  }
LABEL_4:
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v33 = 0;
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x1800064a0  mov     [rsp-38h+arg_0], rbx
0x1800064a5  mov     [rsp-38h+arg_8], rdx
0x1800064aa  push    rbp
0x1800064ab  push    rsi
0x1800064ac  push    rdi
0x1800064ad  push    r12
0x1800064af  push    r13
0x1800064b1  push    r14
0x1800064b3  push    r15
0x1800064b5  mov     rbp, rsp
0x1800064b8  sub     rsp, 60h
0x1800064bc  mov     rax, [r8]
0x1800064bf  mov     r14, rdx
0x1800064c2  mov     r13, rcx
0x1800064c5  lea     rdx, [rbp+var_20]
0x1800064c9  xor     r15d, r15d
0x1800064cc  mov     rcx, r8
0x1800064cf  mov     r12, r8
0x1800064d2  mov     [rbp+var_20], r15
0x1800064d6  mov     rax, [rax+88h]
0x1800064dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e2  mov     ebx, eax
0x1800064e4  test    eax, eax
0x1800064e6  jns     loc_1800067BA
0x1800064ec  mov     ecx, r15d
0x1800064ef  mov     [rbp+arg_18], rcx
0x1800064f3  mov     [rbp+String1], r15
0x1800064f7  mov     rsi, r15
0x1800064fa  mov     [rbp+bstrString], r15
0x1800064fe  mov     rdi, r15
0x180006501  mov     [rbp+var_10], r15
0x180006505  test    ebx, ebx
0x180006507  jns     loc_1800066B9
0x18000650d  test    rcx, rcx
0x180006510  jz      short loc_180006522
0x180006512  mov     rax, [rcx]
0x180006515  mov     rax, [rax+10h]
0x180006519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000651e  mov     [rbp+arg_18], r15
0x180006522  mov     rcx, [rbp+var_20]
0x180006526  test    rcx, rcx
0x180006529  jz      short loc_180006537
0x18000652b  mov     rax, [rcx]
0x18000652e  mov     rax, [rax+10h]
0x180006532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006537  mov     eax, ebx
0x180006539  mov     rbx, [rsp+60h+arg_0]
0x180006541  add     rsp, 60h
0x180006545  pop     r15
0x180006547  pop     r14
0x180006549  pop     r13
0x18000654b  pop     r12
0x18000654d  pop     rdi
0x18000654e  pop     rsi
0x18000654f  pop     rbp
0x180006550  retn
0x180006551  mov     rax, [rbp+bstrString]
0x180006555  lea     rcx, [rbp+var_10]
0x180006559  mov     r9, [r13+20h]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18000655d  mov     rdx, r12; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180006560  mov     r8, [r13+8]; struct IXMLDOMElement *
0x180006564  mov     [rsp+60h+var_38], rcx; unsigned __int16 *
0x180006569  mov     rcx, r14; this
0x18000656c  mov     [rbp+var_10], 0
0x180006574  mov     [rsp+60h+var_40], rax; struct IXMLDOMElement *
0x180006579  call    ?MigrateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@01PEBGPEAPEAG@Z; NPrintTicketUtil::MigrateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort * *)
0x18000657e  mov     ebx, eax
0x180006580  test    eax, eax
0x180006582  jns     loc_180006863
0x180006588  xor     r15d, r15d
0x18000658b  test    rdi, rdi
0x18000658e  jz      short loc_180006599
0x180006590  mov     rcx, rdi; bstrString
0x180006593  call    cs:__imp_SysFreeString
0x180006599  mov     rcx, [rbp+bstrString]; bstrString
0x18000659d  test    rcx, rcx
0x1800065a0  jz      short loc_1800065AC
0x1800065a2  call    cs:__imp_SysFreeString
0x1800065a8  mov     [rbp+bstrString], r15
0x1800065ac  test    rsi, rsi
0x1800065af  jz      short loc_1800065BA
0x1800065b1  mov     rcx, rsi; bstrString
0x1800065b4  call    cs:__imp_SysFreeString
0x1800065ba  mov     rcx, [rbp+arg_18]
0x1800065be  jmp     loc_18000650D
0x1800065c3  mov     [rbp+var_30], rsi
0x1800065c7  lea     rdx, [rbp+var_30]
0x1800065cb  mov     rax, [rcx]
0x1800065ce  mov     rax, [rax+0D0h]
0x1800065d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065da  mov     ebx, eax
0x1800065dc  test    eax, eax
0x1800065de  jns     short loc_180006633
0x1800065e0  mov     rcx, [rbp+var_30]; bstrString
0x1800065e4  test    rcx, rcx
0x1800065e7  jz      short loc_1800065EF
0x1800065e9  call    cs:__imp_SysFreeString
0x1800065ef  test    ebx, ebx
0x1800065f1  js      short loc_180006588
0x1800065f3  mov     rax, [r12]
0x1800065f7  lea     rdx, [rbp+bstrString]
0x1800065fb  mov     rcx, r12
0x1800065fe  mov     rax, [rax+0D0h]
0x180006605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000660a  test    r15d, r15d
0x18000660d  jnz     loc_180006551
0x180006613  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x180006617  mov     r9, rdi; unsigned __int16 *
0x18000661a  mov     rdx, [r13+20h]; struct IXMLDOMElement *
0x18000661e  mov     rcx, [r13+8]; this
0x180006622  mov     [rsp+60h+var_40], rsi; unsigned __int16 *
0x180006627  call    ?CreateValue@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG11PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateValue(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18000662c  mov     ebx, eax
0x18000662e  jmp     loc_180006588
0x180006633  mov     r8, [rbp+var_30]; unsigned __int16 *
0x180006637  lea     r9, [rbp+var_10]; unsigned __int16 **
0x18000663b  mov     rdx, r12; struct IXMLDOMElement *
0x18000663e  mov     rcx, r14; this
0x180006641  call    ?getUri@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getUri(IXMLDOMElement *,ushort const *,ushort * *)
0x180006646  mov     ebx, eax
0x180006648  test    eax, eax
0x18000664a  jns     loc_180006816
0x180006650  mov     rdi, [rbp+var_10]
0x180006654  jmp     short loc_1800065E0
0x180006656  test    ebx, ebx
0x180006658  js      short loc_1800065E0
0x18000665a  mov     rdx, [r13+20h]; struct IXMLDOMElement *
0x18000665e  lea     rax, [rbp+var_10]
0x180006662  mov     rcx, [r13+8]; this
0x180006666  mov     r9, rdi; unsigned __int16 *
0x180006669  mov     r8, rsi; struct IXMLDOMElement *
0x18000666c  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x180006671  mov     [rbp+var_10], 0
0x180006679  call    ?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z; NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18000667e  mov     ebx, eax
0x180006680  test    eax, eax
0x180006682  js      loc_1800065E0
0x180006688  mov     rcx, [rbp+var_30]; bstrString
0x18000668c  test    rcx, rcx
0x18000668f  jz      short loc_18000669D
0x180006691  call    cs:__imp_SysFreeString
0x180006697  xor     ecx, ecx; bstrString
0x180006699  mov     [rbp+var_30], rcx
0x18000669d  mov     r14, [rbp+var_10]
0x1800066a1  test    rcx, rcx
0x1800066a4  jz      short loc_1800066AC
0x1800066a6  call    cs:__imp_SysFreeString
0x1800066ac  mov     [rbp+var_30], r14
0x1800066b0  mov     r14, [rbp+arg_8]
0x1800066b4  jmp     loc_1800065E0
0x1800066b9  test    rcx, rcx
0x1800066bc  jz      loc_1800065F3
0x1800066c2  jmp     loc_1800065C3
0x1800066c7  mov     rcx, [rbp+var_20]
0x1800066cb  lea     rdx, [rbp+var_30]
0x1800066cf  mov     rax, [rcx]
0x1800066d2  mov     rax, [rax+70h]
0x1800066d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066db  mov     ebx, eax
0x1800066dd  test    eax, eax
0x1800066df  jnz     loc_1800067A4
0x1800066e5  test    esi, esi
0x1800066e7  jnz     loc_1800067A4
0x1800066ed  mov     rcx, [rbp+var_30]
0x1800066f1  lea     r8, [rbp+arg_18]
0x1800066f5  lea     rdx, IID_IXMLDOMAttribute
0x1800066fc  mov     rax, [rcx]
0x1800066ff  mov     rax, [rax]
0x180006702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006707  test    eax, eax
0x180006709  jnz     short loc_180006775
0x18000670b  mov     rcx, [rbp+arg_18]
0x18000670f  lea     rdx, [rbp+String1]
0x180006713  mov     [rbp+String1], r15
0x180006717  mov     [rbp+var_10], r15
0x18000671b  mov     rax, [rcx]
0x18000671e  mov     rax, [rax+138h]
0x180006725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000672a  test    eax, eax
0x18000672c  jns     loc_1800067E0
0x180006732  mov     rbx, [rbp+String1]
0x180006736  lea     rdx, aHttpWwwW3Org20_0; "http://www.w3.org/2001/XMLSchema-instan"...
0x18000673d  mov     rcx, rbx; String1
0x180006740  call    wcscmp_0
0x180006745  mov     rdi, [rbp+var_10]
0x180006749  test    eax, eax
0x18000674b  jz      loc_1800067FC
0x180006751  test    rdi, rdi
0x180006754  jz      short loc_180006767
0x180006756  mov     rcx, rdi; bstrString
0x180006759  call    cs:__imp_SysFreeString
0x18000675f  mov     rbx, [rbp+String1]
0x180006763  mov     [rbp+var_10], r15
0x180006767  test    rbx, rbx
0x18000676a  jz      short loc_180006775
0x18000676c  mov     rcx, rbx; bstrString
0x18000676f  call    cs:__imp_SysFreeString
0x180006775  mov     rcx, [rbp+var_30]
0x180006779  test    rcx, rcx
0x18000677c  jz      short loc_18000678E
0x18000677e  mov     rax, [rcx]
0x180006781  mov     rax, [rax+10h]
0x180006785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000678a  mov     [rbp+var_30], r15
0x18000678e  test    esi, esi
0x180006790  jnz     loc_1800066C7
0x180006796  lea     rcx, [rbp+arg_18]
0x18000679a  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18000679f  jmp     loc_1800066C7
0x1800067a4  lea     rcx, [rbp+var_30]
0x1800067a8  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x1800067ad  mov     rcx, [rbp+arg_18]
0x1800067b1  mov     r14, [rbp+arg_8]
0x1800067b5  jmp     loc_1800064F3
0x1800067ba  mov     rcx, [rbp+var_20]
0x1800067be  mov     rax, [rcx]
0x1800067c1  mov     rax, [rax+78h]
0x1800067c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067ca  mov     [rbp+arg_18], r15
0x1800067ce  mov     esi, r15d
0x1800067d1  mov     [rbp+var_30], r15
0x1800067d5  mov     r14d, 1
0x1800067db  jmp     loc_1800066C7
0x1800067e0  mov     rcx, [rbp+arg_18]
0x1800067e4  lea     rdx, [rbp+var_10]
0x1800067e8  mov     rax, [rcx]
0x1800067eb  mov     rax, [rax+148h]
0x1800067f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067f7  jmp     loc_180006732
0x1800067fc  lea     rdx, aType; "type"
0x180006803  mov     rcx, rdi; String1
0x180006806  call    wcscmp_0
0x18000680b  test    eax, eax
0x18000680d  cmovz   esi, r14d
0x180006811  jmp     loc_180006751
0x180006816  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x18000681a  lea     r8, [rbp+String1]; unsigned __int16 **
0x18000681e  call    ?getLocalName@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBGPEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::getLocalName(ushort const *,ushort * *)
0x180006823  mov     rsi, [rbp+String1]
0x180006827  lea     rdx, aQname; "QName"
0x18000682e  mov     rcx, rsi; String1
0x180006831  mov     ebx, eax
0x180006833  call    wcscmp_0
0x180006838  mov     rdi, [rbp+var_10]
0x18000683c  test    eax, eax
0x18000683e  jnz     loc_180006656
0x180006844  lea     rdx, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x18000684b  mov     rcx, rdi; String1
0x18000684e  call    wcscmp_0
0x180006853  test    eax, eax
0x180006855  mov     eax, 1
0x18000685a  cmovz   r15d, eax
0x18000685e  jmp     loc_180006656
0x180006863  lea     rcx, [rbp+bstrString]
0x180006867  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000686c  mov     rdx, [rbp+var_10]
0x180006870  lea     rcx, [rbp+bstrString]
0x180006874  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEAGPEAG@Z; NCoreLibrary::TAutoPtrBSTR::operator=(ushort *)
0x180006879  jmp     loc_180006613
```
