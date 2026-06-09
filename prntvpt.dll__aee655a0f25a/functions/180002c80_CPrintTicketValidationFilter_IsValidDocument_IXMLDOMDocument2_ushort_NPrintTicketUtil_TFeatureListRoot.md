# CPrintTicketValidationFilter::IsValidDocument(IXMLDOMDocument2 *,ushort * *,NPrintTicketUtil::TFeatureListRoot * *)

- ea: `0x180002c80`
- end: `0x180003310`
- name: `?IsValidDocument@CPrintTicketValidationFilter@@QEAAJPEAUIXMLDOMDocument2@@PEAPEAGPEAPEAUTFeatureListRoot@NPrintTicketUtil@@@Z`
- size: `1680`
- prototype: `__int64 __fastcall(CPrintTicketValidationFilter *__hidden this, struct IXMLDOMDocument2 *, unsigned __int16 **, struct NPrintTicketUtil::TFeatureListRoot **)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009180`
- `0x18000df24`
- `0x18001e948`

## callees

- `0x1800023d4`
- `0x180002450`
- `0x180002c80`
- `0x180003318`
- `0x1800042c0`
- `0x180005e70`
- `0x180009268`
- `0x180009c10`
- `0x18000aa10`
- `0x18001c920`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800030ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800030c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800030ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800030c4`
- `OLEAUT32!__imp_VariantInit` at `0x1800031d5`
- `OLEAUT32!__imp_VariantInit` at `0x1800031d5`
- `OLEAUT32!__imp_VariantClear` at `0x180003261`
- `OLEAUT32!__imp_VariantClear` at `0x180003261`
- `OLEAUT32!__imp_VariantChangeType` at `0x180003214`
- `OLEAUT32!__imp_VariantChangeType` at `0x180003214`

## string_xrefs

- `0x180002edb`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x18000315f`: `http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2`
- `0x180002f63`: `One or more XML elements in the document contain an invalid namespace prefix or namespace.`

## pseudocode

```c
__int64 __fastcall CPrintTicketValidationFilter::IsValidDocument(
        CPrintTicketValidationFilter *this,
        struct IXMLDOMDocument2 *a2,
        struct NPrintTicketUtil::TFeatureListRoot **a3,
        struct NPrintTicketUtil::TFeatureListRoot **a4)
{
  int v5; // edx
  struct NPrintTicketUtil::TFeatureListRoot **v6; // rsi
  struct IXMLDOMElement *DocumentRoot; // r12
  struct NPrintTicketUtil::TFeatureListRoot **v9; // r15
  HRESULT IsValidEncoding; // r14d
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  struct NPrintTicketUtil::TFeatureListRoot *v13; // rax
  __int64 v15; // rbx
  _DWORD *v16; // rdi
  _QWORD *v17; // r9
  int v18; // r10d
  unsigned __int16 *v19; // rax
  int v20; // ecx
  int v21; // edx
  unsigned __int16 *v22; // rax
  int v23; // ecx
  int v24; // edx
  const unsigned __int16 *v25; // rsi
  int v26; // r15d
  const unsigned __int16 *v27; // rdi
  CPrintTicketValidationFilter *v28; // rcx
  const unsigned __int16 *v29; // r9
  const unsigned __int16 *v30; // rax
  int v31; // ecx
  int v32; // edx
  _DWORD *v33; // rax
  const unsigned __int16 *v34; // rax
  int v35; // ecx
  int v36; // edx
  int PrintTicketFeatureList; // eax
  struct NPrintTicketUtil::TFeatureListRoot *v38; // rdx
  struct NPrintTicketUtil::TFeatureListEntry **v39; // rbx
  struct NPrintTicketUtil::TFeatureListEntry **v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rdx
  const unsigned __int16 *v43; // [rsp+30h] [rbp-31h]
  BSTR v44; // [rsp+38h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-21h] BYREF
  void **v46; // [rsp+58h] [rbp-9h] BYREF
  __int128 v47; // [rsp+60h] [rbp-1h]
  __int64 v48; // [rsp+70h] [rbp+Fh]
  __int16 v49; // [rsp+78h] [rbp+17h]
  int v50; // [rsp+7Ch] [rbp+1Bh]
  BSTR bstrString; // [rsp+C8h] [rbp+67h] BYREF
  struct NPrintTicketUtil::TFeatureListRoot **v52; // [rsp+D8h] [rbp+77h]
  struct NPrintTicketUtil::TFeatureListRoot **v53; // [rsp+E0h] [rbp+7Fh]

  v53 = a4;
  v52 = a3;
  v5 = *((_DWORD *)this + 16);
  v6 = a3;
  DocumentRoot = 0;
  v48 = 0;
  v46 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  v9 = a4;
  bstrString = 0;
  v49 = 0;
  v50 = 0;
  v47 = 0;
  switch ( v5 )
  {
    case 0:
      v25 = L"PrintTicket";
      goto LABEL_47;
    case 1:
      v25 = L"PrintCapabilities";
LABEL_47:
      v26 = 1;
      v27 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework";
      goto LABEL_48;
    case 2:
      v25 = L"PrintDeviceCapabilities";
      v26 = 2;
      v27 = L"http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2";
LABEL_48:
      IsValidEncoding = NPrintTicketUtil::CPrintTicketWrapper::SetDocument(
                          (NPrintTicketUtil::CPrintTicketWrapper *)&v46,
                          a2,
                          v5 == 1);
      if ( IsValidEncoding < 0 )
      {
LABEL_76:
        v6 = v52;
        v9 = v53;
        goto LABEL_5;
      }
      DocumentRoot = NPrintTicketUtil::CPrintTicketWrapper::GetDocumentRoot((NPrintTicketUtil::CPrintTicketWrapper *)&v46);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&bstrString);
      if ( !DocumentRoot )
      {
        IsValidEncoding = -2147467259;
        goto LABEL_76;
      }
      LODWORD(bstrString) = 0;
      IsValidEncoding = CPrintTicketValidationFilter::IsValidEncoding(v28, a2, (int *)&bstrString);
      if ( IsValidEncoding < 0 )
        goto LABEL_76;
      if ( !(_DWORD)bstrString )
      {
        IsValidEncoding = CValidationStatus::SetValidationFailure(
                            (CPrintTicketValidationFilter *)((char *)this + 8),
                            L"The document must be encoded in UTF-8 or UTF-16 format.",
                            0,
                            0,
                            0,
                            v43);
        if ( IsValidEncoding < 0 )
          goto LABEL_76;
      }
      if ( !*((_DWORD *)this + 2) )
      {
LABEL_95:
        if ( !*((_DWORD *)this + 2) )
          goto LABEL_76;
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v41 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, VARIANTARG *))DocumentRoot->lpVtbl->getAttribute)(
                DocumentRoot,
                L"version",
                &pvarg);
        IsValidEncoding = v41;
        if ( v41 )
        {
          if ( v41 >= 0 )
          {
            v42 = L"The version attribute must be specified.";
            goto LABEL_103;
          }
        }
        else
        {
          IsValidEncoding = VariantChangeType(&pvarg, &pvarg, 4u, 3u);
          if ( IsValidEncoding < 0 )
          {
            v42 = L"The version attribute is not a valid integer.";
            goto LABEL_103;
          }
          if ( pvarg.lVal != v26 )
          {
            v42 = L"The version attribute is not a valid value.  The expected value is '1' for PrintTicket/PrintCapabiliti"
                   "es and '2' for PrintDeviceCapabilities.";
LABEL_103:
            IsValidEncoding = CValidationStatus::SetValidationFailure(
                                (CPrintTicketValidationFilter *)((char *)this + 8),
                                v42,
                                0,
                                0,
                                0,
                                v43);
          }
        }
        VariantClear(&pvarg);
        goto LABEL_76;
      }
      v44 = 0;
      bstrString = 0;
      IsValidEncoding = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))DocumentRoot->lpVtbl->get_namespaceURI)(
                          DocumentRoot,
                          &bstrString);
      if ( IsValidEncoding < 0 )
      {
LABEL_71:
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
        if ( v44 )
          SysFreeString(v44);
        if ( IsValidEncoding < 0 )
          goto LABEL_76;
        goto LABEL_95;
      }
      if ( bstrString )
      {
        v29 = bstrString;
        v30 = v27;
        do
        {
          v31 = *(const unsigned __int16 *)((char *)v30 + (char *)bstrString - (char *)v27);
          v32 = *v30 - v31;
          if ( v32 )
            break;
          ++v30;
        }
        while ( v31 );
        if ( !v32 )
        {
          v33 = (_DWORD *)((char *)this + 8);
LABEL_63:
          if ( *v33 )
          {
            IsValidEncoding = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))DocumentRoot->lpVtbl->get_baseName)(
                                DocumentRoot,
                                &v44);
            if ( IsValidEncoding >= 0 )
            {
              v34 = v25;
              do
              {
                v35 = *(const unsigned __int16 *)((char *)v34 + (char *)v44 - (char *)v25);
                v36 = *v34 - v35;
                if ( v36 )
                  break;
                ++v34;
              }
              while ( v35 );
              if ( v36 )
                IsValidEncoding = CValidationStatus::SetValidationFailure(
                                    (CPrintTicketValidationFilter *)((char *)this + 8),
                                    L"The root element name is incorrect.  '%s' was expected, but the name is defined as '%s'.",
                                    v25,
                                    v44,
                                    0,
                                    v43);
            }
          }
          goto LABEL_71;
        }
      }
      else
      {
        v29 = 0;
      }
      IsValidEncoding = CValidationStatus::SetValidationFailure(
                          (CPrintTicketValidationFilter *)((char *)this + 8),
                          L"The root element namespace is incorrect.  '%s' was expected, but the namespace is defined as '%s'.",
                          v27,
                          v29,
                          0,
                          v43);
      v33 = (_DWORD *)((char *)this + 8);
      if ( IsValidEncoding < 0 )
        goto LABEL_71;
      goto LABEL_63;
  }
  IsValidEncoding = -2147467259;
LABEL_5:
  if ( *((_DWORD *)this + 16) != 2 )
  {
    if ( IsValidEncoding >= 0 )
    {
      if ( *((_DWORD *)this + 2) )
      {
        IsValidEncoding = NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(
                            (NPrintTicketUtil::CPrintTicketWrapper *)&v46,
                            this,
                            DocumentRoot);
        if ( IsValidEncoding == -2147155967 )
          IsValidEncoding = CValidationStatus::SetValidationFailure(
                              (CPrintTicketValidationFilter *)((char *)this + 8),
                              L"One or more XML elements in the document contain an invalid namespace prefix or namespace.",
                              0,
                              0,
                              0,
                              v43);
      }
    }
    v15 = *((_QWORD *)this + 4);
    if ( IsValidEncoding >= 0 )
    {
      v16 = (_DWORD *)((char *)this + 8);
      while ( v15 )
      {
        v16 = (_DWORD *)((char *)this + 8);
        if ( *((_DWORD *)this + 2) )
        {
          v17 = (_QWORD *)*((_QWORD *)this + 3);
          if ( v17 )
          {
            v18 = 0;
            while ( !v18 )
            {
              v19 = (unsigned __int16 *)v17[1];
              a3 = (struct NPrintTicketUtil::TFeatureListRoot **)(*(_QWORD *)(v15 + 8) - (_QWORD)v19);
              do
              {
                v20 = *(unsigned __int16 *)((char *)a3 + (_QWORD)v19);
                v21 = *v19 - v20;
                if ( v21 )
                  break;
                ++v19;
              }
              while ( v20 );
              if ( !v21 )
              {
                v22 = (unsigned __int16 *)v17[2];
                a3 = (struct NPrintTicketUtil::TFeatureListRoot **)(*(_QWORD *)(v15 + 16) - (_QWORD)v22);
                do
                {
                  v23 = *(unsigned __int16 *)((char *)a3 + (_QWORD)v22);
                  v24 = *v22 - v23;
                  if ( v24 )
                    break;
                  ++v22;
                }
                while ( v23 );
                if ( !v24 )
                  v18 = 1;
              }
              v17 = (_QWORD *)v17[3];
              if ( !v17 )
              {
                if ( !v18 )
                  goto LABEL_45;
                break;
              }
            }
            v15 = *(_QWORD *)(v15 + 24);
          }
          else
          {
LABEL_45:
            IsValidEncoding = CValidationStatus::SetValidationFailure(
                                (CPrintTicketValidationFilter *)((char *)this + 8),
                                L"Parameter %s:%s is referenced, but not defined.",
                                *(const unsigned __int16 **)(v15 + 16),
                                *(const unsigned __int16 **)(v15 + 8),
                                0,
                                v43);
          }
          if ( IsValidEncoding >= 0 )
            continue;
        }
        goto LABEL_6;
      }
      if ( *v16 )
      {
        bstrString = 0;
        PrintTicketFeatureList = NPrintTicketUtil::CreatePrintTicketFeatureList(
                                   (NPrintTicketUtil *)&v46,
                                   (struct NPrintTicketUtil::CPrintTicketWrapper *)&bstrString,
                                   a3);
        v39 = (struct NPrintTicketUtil::TFeatureListEntry **)bstrString;
        IsValidEncoding = PrintTicketFeatureList;
        if ( PrintTicketFeatureList >= 0 )
        {
          IsValidEncoding = CPrintTicketValidationFilter::FindDuplicatesInFeatureListInternal(
                              this,
                              *(struct NPrintTicketUtil::TFeatureListEntry **)bstrString,
                              1);
          if ( IsValidEncoding >= 0 )
          {
            if ( *v16 )
              IsValidEncoding = CPrintTicketValidationFilter::FindDuplicatesInFeatureListInternal(this, v39[1], 1);
          }
        }
        if ( v9 )
        {
          v40 = 0;
          if ( v39 )
          {
            v40 = v39;
            v39 = 0;
          }
          *v9 = (struct NPrintTicketUtil::TFeatureListRoot *)v40;
        }
        if ( v39 )
          NPrintTicketUtil::DeletePrintTicketFeatureList((NPrintTicketUtil *)v39, v38);
      }
    }
  }
LABEL_6:
  v11 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
  if ( v11 )
    (**v11)(v11, 1);
  v12 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
  if ( v12 )
    (**v12)(v12, 1);
  if ( IsValidEncoding >= 0 )
  {
    if ( *((_DWORD *)this + 2) )
    {
      IsValidEncoding = 0;
      v13 = 0;
    }
    else
    {
      v13 = 0;
      if ( *((_QWORD *)this + 2) )
      {
        v13 = (struct NPrintTicketUtil::TFeatureListRoot *)*((_QWORD *)this + 2);
        *((_QWORD *)this + 2) = 0;
      }
      IsValidEncoding = 1;
    }
  }
  else
  {
    v13 = 0;
    if ( *((_QWORD *)this + 2) )
    {
      v13 = (struct NPrintTicketUtil::TFeatureListRoot *)*((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = 0;
    }
  }
  *v6 = v13;
  if ( DocumentRoot )
    ((void (__fastcall *)(struct IXMLDOMElement *))DocumentRoot->lpVtbl->Release)(DocumentRoot);
  v46 = &NPrintTicketUtil::CPrintTicketWrapper::`vftable';
  if ( (_QWORD)v47 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v47 + 16LL))(v47);
  if ( *((_QWORD *)&v47 + 1) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v47 + 1) + 16LL))(*((_QWORD *)&v47 + 1));
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  return (unsigned int)IsValidEncoding;
}

```

## disassembly

```asm
0x180002c80  mov     rax, rsp
0x180002c83  mov     [rax+20h], r9
0x180002c87  mov     [rax+18h], r8
0x180002c8b  push    rbp
0x180002c8c  push    r14
0x180002c8e  lea     rbp, [rax-5Fh]
0x180002c92  sub     rsp, 0A8h
0x180002c99  mov     [rax+10h], rbx
0x180002c9d  xorps   xmm0, xmm0
0x180002ca0  mov     [rax-18h], rsi
0x180002ca4  mov     rbx, rdx
0x180002ca7  mov     edx, [rcx+40h]
0x180002caa  mov     rsi, r8
0x180002cad  mov     [rax-20h], rdi
0x180002cb1  mov     [rax-28h], r12
0x180002cb5  xor     r12d, r12d
0x180002cb8  mov     [rax-30h], r13
0x180002cbc  mov     r13, rcx
0x180002cbf  mov     [rax-38h], r15
0x180002cc3  mov     ecx, edx
0x180002cc5  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x180002ccc  mov     [rbp+57h+var_48], 0
0x180002cd4  mov     [rbp+57h+var_60], rax
0x180002cd8  mov     r15, r9
0x180002cdb  xor     eax, eax
0x180002cdd  mov     [rbp+57h+bstrString], r12
0x180002ce1  mov     [rbp+57h+var_40], ax
0x180002ce5  mov     [rbp+57h+var_3C], eax
0x180002ce8  movdqu  [rbp+57h+var_58], xmm0
0x180002ced  test    edx, edx
0x180002cef  jz      loc_18000316B
0x180002cf5  sub     ecx, 1
0x180002cf8  jz      loc_180002ECE
0x180002cfe  cmp     ecx, 1
0x180002d01  jz      loc_180003152
0x180002d07  mov     r14d, 80004005h
0x180002d0d  cmp     dword ptr [r13+40h], 2
0x180002d12  jnz     loc_180002DE2
0x180002d18  mov     rcx, [r13+20h]
0x180002d1c  mov     r15, [rsp+0B0h+var_30]
0x180002d24  mov     rdi, [rsp+0B0h+var_18]
0x180002d2c  mov     rbx, [rsp+0B0h+arg_8]
0x180002d34  test    rcx, rcx
0x180002d37  jnz     loc_1800032B5
0x180002d3d  mov     rcx, [r13+18h]
0x180002d41  test    rcx, rcx
0x180002d44  jnz     loc_180002E94
0x180002d4a  test    r14d, r14d
0x180002d4d  jns     loc_1800032CA
0x180002d53  mov     rcx, [r13+10h]
0x180002d57  xor     eax, eax
0x180002d59  test    rcx, rcx
0x180002d5c  jnz     loc_1800032EF
0x180002d62  mov     [rsi], rax
0x180002d65  mov     r13, [rsp+0B0h+var_28]
0x180002d6d  mov     rsi, [rsp+0A0h]
0x180002d75  test    r12, r12
0x180002d78  jz      short loc_180002D8A
0x180002d7a  mov     rax, [r12]
0x180002d7e  mov     rcx, r12
0x180002d81  mov     rax, [rax+10h]
0x180002d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d8a  mov     rcx, qword ptr [rbp+57h+var_58]
0x180002d8e  lea     rax, ??_7CPrintTicketWrapper@NPrintTicketUtil@@6B@; const NPrintTicketUtil::CPrintTicketWrapper::`vftable'
0x180002d95  mov     r12, [rsp+0B0h+var_20]
0x180002d9d  mov     [rbp+57h+var_60], rax
0x180002da1  test    rcx, rcx
0x180002da4  jz      short loc_180002DB2
0x180002da6  mov     rax, [rcx]
0x180002da9  mov     rax, [rax+10h]
0x180002dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002db2  mov     rcx, qword ptr [rbp+57h+var_58+8]
0x180002db6  test    rcx, rcx
0x180002db9  jz      short loc_180002DC7
0x180002dbb  mov     rax, [rcx]
0x180002dbe  mov     rax, [rax+10h]
0x180002dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dc7  mov     rcx, [rbp+57h+var_48]
0x180002dcb  test    rcx, rcx
0x180002dce  jnz     loc_1800032FF
0x180002dd4  mov     eax, r14d
0x180002dd7  add     rsp, 0A8h
0x180002dde  pop     r14
0x180002de0  pop     rbp
0x180002de1  retn
0x180002de2  test    r14d, r14d
0x180002de5  jns     loc_180002F2C
0x180002deb  mov     rbx, [r13+20h]
0x180002def  test    r14d, r14d
0x180002df2  js      loc_180002D18
0x180002df8  lea     rdi, [r13+8]
0x180002dfc  test    rbx, rbx
0x180002dff  jz      loc_1800030E0
0x180002e05  cmp     dword ptr [r13+8], 0
0x180002e0a  lea     rdi, [r13+8]
0x180002e0e  jz      loc_180002D18
0x180002e14  mov     r9, [r13+18h]
0x180002e18  test    r9, r9
0x180002e1b  jz      loc_180002EA9
0x180002e21  xor     r10d, r10d
0x180002e24  test    r10d, r10d
0x180002e27  jnz     short loc_180002E5A
0x180002e29  mov     rax, [r9+8]
0x180002e2d  mov     r8, [rbx+8]
0x180002e31  sub     r8, rax
0x180002e34  movzx   edx, word ptr [rax]
0x180002e37  movzx   ecx, word ptr [rax+r8]
0x180002e3c  sub     edx, ecx
0x180002e3e  jnz     short loc_180002E48
0x180002e40  add     rax, 2
0x180002e44  test    ecx, ecx
0x180002e46  jnz     short loc_180002E34
0x180002e48  test    edx, edx
0x180002e4a  jz      short loc_180002E68
0x180002e4c  mov     r9, [r9+18h]
0x180002e50  test    r9, r9
0x180002e53  jnz     short loc_180002E24
0x180002e55  test    r10d, r10d
0x180002e58  jz      short loc_180002EA9
0x180002e5a  mov     rbx, [rbx+18h]
0x180002e5e  test    r14d, r14d
0x180002e61  jns     short loc_180002DFC
0x180002e63  jmp     loc_180002D18
0x180002e68  mov     rax, [r9+10h]
0x180002e6c  mov     r8, [rbx+10h]
0x180002e70  sub     r8, rax
0x180002e73  movzx   edx, word ptr [rax]
0x180002e76  movzx   ecx, word ptr [rax+r8]
0x180002e7b  sub     edx, ecx
0x180002e7d  jnz     short loc_180002E87
0x180002e7f  add     rax, 2
0x180002e83  test    ecx, ecx
0x180002e85  jnz     short loc_180002E73
0x180002e87  test    edx, edx
0x180002e89  mov     eax, 1
0x180002e8e  cmovz   r10d, eax
0x180002e92  jmp     short loc_180002E4C
0x180002e94  mov     rax, [rcx]
0x180002e97  mov     edx, 1
0x180002e9c  mov     rax, [rax]
0x180002e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea4  jmp     loc_180002D4A
0x180002ea9  mov     r9, [rbx+8]; unsigned __int16 *
0x180002ead  lea     rdx, aParameterSSIsR; "Parameter %s:%s is referenced, but not "...
0x180002eb4  mov     r8, [rbx+10h]; unsigned __int16 *
0x180002eb8  mov     rcx, rdi; this
0x180002ebb  mov     qword ptr [rsp+20h], 0; unsigned __int16 *
0x180002ec4  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180002ec9  mov     r14d, eax
0x180002ecc  jmp     short loc_180002E5E
0x180002ece  lea     rsi, aPrintcapabilit; "PrintCapabilities"
0x180002ed5  mov     r15d, 1
0x180002edb  lea     rdi, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x180002ee2  xor     r8d, r8d
0x180002ee5  lea     rcx, [rbp+57h+var_60]; this
0x180002ee9  cmp     edx, 1
0x180002eec  mov     rdx, rbx; struct IXMLDOMDocument2 *
0x180002eef  setz    r8b; int
0x180002ef3  call    ?SetDocument@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMDocument2@@H@Z; NPrintTicketUtil::CPrintTicketWrapper::SetDocument(IXMLDOMDocument2 *,int)
0x180002ef8  mov     r14d, eax
0x180002efb  test    eax, eax
0x180002efd  js      loc_1800030D3
0x180002f03  lea     rcx, [rbp+57h+var_60]; this
0x180002f07  call    ?GetDocumentRoot@CPrintTicketWrapper@NPrintTicketUtil@@QEAAPEAUIXMLDOMElement@@XZ; NPrintTicketUtil::CPrintTicketWrapper::GetDocumentRoot(void)
0x180002f0c  lea     rcx, [rbp+57h+bstrString]
0x180002f10  mov     r12, rax
0x180002f13  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180002f18  test    r12, r12
0x180002f1b  jnz     loc_180003177
0x180002f21  mov     r14d, 80004005h
0x180002f27  jmp     loc_1800030D3
0x180002f2c  cmp     dword ptr [r13+8], 0
0x180002f31  jz      loc_180002DEB
0x180002f37  mov     r8, r12; struct IXMLDOMElement *
0x180002f3a  lea     rcx, [rbp+57h+var_60]; this
0x180002f3e  mov     rdx, r13; struct NPrintTicketUtil::CAbstractPrintTicketVisitors *
0x180002f41  call    ?VisitNodes@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAVCAbstractPrintTicketVisitors@2@PEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::VisitNodes(NPrintTicketUtil::CAbstractPrintTicketVisitors *,IXMLDOMElement *)
0x180002f46  mov     r14d, eax
0x180002f49  cmp     eax, 80050001h
0x180002f4e  jnz     loc_180002DEB
0x180002f54  xor     r9d, r9d; unsigned __int16 *
0x180002f57  mov     qword ptr [rsp+20h], 0; unsigned __int16 *
0x180002f60  xor     r8d, r8d; unsigned __int16 *
0x180002f63  lea     rdx, aOneOrMoreXmlEl; "One or more XML elements in the documen"...
0x180002f6a  lea     rcx, [r13+8]; this
0x180002f6e  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180002f73  mov     r14d, eax
0x180002f76  jmp     loc_180002DEB
0x180002f7b  xor     r9d, r9d; unsigned __int16 *
0x180002f7e  mov     qword ptr [rsp+20h], 0; unsigned __int16 *
0x180002f87  xor     r8d, r8d; unsigned __int16 *
0x180002f8a  lea     rdx, aTheDocumentMus; "The document must be encoded in UTF-8 o"...
0x180002f91  mov     rcx, rbx; this
0x180002f94  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180002f99  mov     r14d, eax
0x180002f9c  test    eax, eax
0x180002f9e  js      loc_1800030D3
0x180002fa4  cmp     dword ptr [rbx], 0
0x180002fa7  jz      loc_1800031B9
0x180002fad  xor     eax, eax
0x180002faf  lea     rdx, [rbp+57h+bstrString]
0x180002fb3  mov     [rbp+57h+var_80], rax
0x180002fb7  mov     rcx, r12
0x180002fba  mov     [rbp+57h+bstrString], rax
0x180002fbe  mov     rax, [r12]
0x180002fc2  mov     rax, [rax+138h]
0x180002fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fce  mov     r14d, eax
0x180002fd1  test    eax, eax
0x180002fd3  js      loc_1800030A4
0x180002fd9  cmp     [rbp+57h+bstrString], 0
0x180002fde  jz      loc_1800031A8
0x180002fe4  mov     r9, [rbp+57h+bstrString]
0x180002fe8  mov     rax, rdi
0x180002feb  mov     r10, r9
0x180002fee  sub     r10, rdi
0x180002ff1  movzx   edx, word ptr [rax]
0x180002ff4  movzx   ecx, word ptr [rax+r10]
0x180002ff9  sub     edx, ecx
0x180002ffb  jnz     short loc_180003005
0x180002ffd  add     rax, 2
0x180003001  test    ecx, ecx
0x180003003  jnz     short loc_180002FF1
0x180003005  test    edx, edx
0x180003007  jnz     loc_1800031B2
0x18000300d  mov     rax, rbx
0x180003010  cmp     dword ptr [rax], 0
0x180003013  jz      loc_1800030A4
0x180003019  mov     rax, [r12]
0x18000301d  lea     rdx, [rbp+57h+var_80]
0x180003021  mov     rcx, r12
0x180003024  mov     rax, [rax+148h]
0x18000302b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003030  mov     r14d, eax
0x180003033  test    eax, eax
0x180003035  js      short loc_1800030A4
0x180003037  mov     r9, [rbp+57h+var_80]
0x18000303b  mov     rax, rsi
0x18000303e  sub     r9, rsi
0x180003041  movzx   edx, word ptr [rax]
0x180003044  movzx   ecx, word ptr [rax+r9]
0x180003049  sub     edx, ecx
0x18000304b  jnz     short loc_180003055
0x18000304d  add     rax, 2
0x180003051  test    ecx, ecx
0x180003053  jnz     short loc_180003041
0x180003055  test    edx, edx
0x180003057  jz      short loc_1800030A4
0x180003059  mov     r9, [rbp+57h+var_80]; unsigned __int16 *
0x18000305d  lea     rdx, aTheRootElement; "The root element name is incorrect.  '%"...
0x180003064  mov     r8, rsi; unsigned __int16 *
0x180003067  mov     qword ptr [rsp+20h], 0; unsigned __int16 *
0x180003070  mov     rcx, rbx; this
0x180003073  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180003078  mov     r14d, eax
0x18000307b  jmp     short loc_1800030A4
0x18000307d  mov     r8, rdi; unsigned __int16 *
0x180003080  mov     [rsp+20h], rax; unsigned __int16 *
0x180003085  lea     rdx, aTheRootElement_0; "The root element namespace is incorrect"...
0x18000308c  mov     rcx, rbx; this
0x18000308f  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180003094  mov     r14d, eax
0x180003097  lea     rax, [r13+8]
0x18000309b  test    r14d, r14d
0x18000309e  jns     loc_180003010
0x1800030a4  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800030a8  test    rcx, rcx
0x1800030ab  jz      short loc_1800030BB
0x1800030ad  call    cs:__imp_SysFreeString
0x1800030b3  mov     [rbp+57h+bstrString], 0
0x1800030bb  mov     rcx, [rbp+57h+var_80]; bstrString
0x1800030bf  test    rcx, rcx
0x1800030c2  jz      short loc_1800030CA
0x1800030c4  call    cs:__imp_SysFreeString
0x1800030ca  test    r14d, r14d
0x1800030cd  jns     loc_1800031B9
0x1800030d3  mov     rsi, [rbp+57h+arg_10]
0x1800030d7  mov     r15, [rbp+57h+arg_18]
0x1800030db  jmp     loc_180002D0D
0x1800030e0  cmp     dword ptr [rdi], 0
0x1800030e3  jz      loc_180002D18
0x1800030e9  lea     rdx, [rbp+57h+bstrString]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x1800030ed  mov     [rbp+57h+bstrString], 0
0x1800030f5  lea     rcx, [rbp+57h+var_60]; this
0x1800030f9  call    ?CreatePrintTicketFeatureList@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAPEAUTFeatureListRoot@1@@Z; NPrintTicketUtil::CreatePrintTicketFeatureList(NPrintTicketUtil::CPrintTicketWrapper *,NPrintTicketUtil::TFeatureListRoot * *)
0x1800030fe  mov     rbx, [rbp+57h+bstrString]
0x180003102  mov     r14d, eax
0x180003105  test    eax, eax
0x180003107  jns     loc_18000326C
0x18000310d  test    r15, r15
0x180003110  jnz     short loc_180003128
0x180003112  test    rbx, rbx
0x180003115  jz      loc_180002D18
0x18000311b  mov     rcx, rbx; this
0x18000311e  call    ?DeletePrintTicketFeatureList@NPrintTicketUtil@@YAXPEAUTFeatureListRoot@1@@Z; NPrintTicketUtil::DeletePrintTicketFeatureList(NPrintTicketUtil::TFeatureListRoot *)
0x180003123  jmp     loc_180002D18
0x180003128  xor     eax, eax
0x18000312a  test    rbx, rbx
0x18000312d  jnz     loc_1800032AB
0x180003133  mov     [r15], rax
  ... truncated ...
```
