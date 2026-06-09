# CPrintTicketValidationFilter::OptionVisitor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *)

- ea: `0x180004ec0`
- end: `0x1800056cd`
- name: `?OptionVisitor@CPrintTicketValidationFilter@@UEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@@Z`
- size: `2061`
- prototype: `int(CPrintTicketValidationFilter *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003318`
- `0x180004ec0`
- `0x1800056e0`
- `0x18000570c`
- `0x1800057f0`
- `0x180005990`
- `0x18001d30c`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180005359`
- `OLEAUT32!__imp_SysAllocString` at `0x180005359`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005509`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800055b8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005509`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800055b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000514f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000515e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005171`
- `OLEAUT32!__imp_SysFreeString` at `0x18000538d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005581`
- `OLEAUT32!__imp_SysFreeString` at `0x180005642`
- `OLEAUT32!__imp_SysFreeString` at `0x18000514f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000515e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005171`
- `OLEAUT32!__imp_SysFreeString` at `0x18000538d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005581`
- `OLEAUT32!__imp_SysFreeString` at `0x180005642`
- `OLEAUT32!__imp_SysStringLen` at `0x180005074`
- `OLEAUT32!__imp_SysStringLen` at `0x180005377`
- `OLEAUT32!__imp_SysStringLen` at `0x180005074`
- `OLEAUT32!__imp_SysStringLen` at `0x180005377`

## string_xrefs

- `0x180005460`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180005494`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x180004f96`: `%s contains an unexpected XML attribute.  Only 'name' is allowed.`
- `0x180005663`: `The prefix of '%s' in the %s attribute '%s' does not map to a valid URI.`
- `0x18000568e`: `Invalid content exists in %s.  %s elements may only contain elements and comments.`

## pseudocode

```c
__int64 __fastcall CPrintTicketValidationFilter::OptionVisitor(
        CPrintTicketValidationFilter *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3)
{
  int v3; // r14d
  NPrintTicketUtil *v5; // r15
  int v7; // esi
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  signed int ElementDescriptor; // edi
  struct IXMLDOMNode *v10; // rdx
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // eax
  struct IXMLDOMElementVtbl *v14; // rax
  int v15; // r15d
  int v16; // ebx
  BSTR v17; // rcx
  BSTR v18; // rax
  int v19; // edx
  int v20; // r8d
  int v21; // eax
  int v22; // edx
  unsigned __int16 *Message; // rdi
  char v24; // al
  bool v25; // zf
  int v26; // eax
  unsigned __int16 *v27; // rdx
  const OLECHAR *v28; // rdi
  OLECHAR *v29; // rbx
  UINT v30; // edx
  __int64 v31; // rcx
  OLECHAR *v32; // rsi
  __int64 v33; // rcx
  BSTR v35; // rax
  int v36; // ecx
  int v37; // edx
  unsigned __int16 *v38; // rdi
  char v39; // al
  int v40; // r14d
  bool v41; // sf
  int v42; // eax
  BSTR v43; // rax
  int v44; // [rsp+28h] [rbp-39h]
  const unsigned __int16 *v45; // [rsp+30h] [rbp-31h]
  BSTR pbstr; // [rsp+38h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-21h] BYREF
  __int64 v48; // [rsp+48h] [rbp-19h] BYREF
  BSTR v49; // [rsp+50h] [rbp-11h] BYREF
  int v50; // [rsp+58h] [rbp-9h]
  __int64 v51; // [rsp+60h] [rbp-1h] BYREF
  __int64 v52; // [rsp+68h] [rbp+7h] BYREF
  __int64 v53; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v54; // [rsp+78h] [rbp+17h] BYREF
  int v55; // [rsp+C8h] [rbp+67h] BYREF
  struct NPrintTicketUtil::CPrintTicketWrapper *v56; // [rsp+D0h] [rbp+6Fh]
  struct IXMLDOMElement v57; // [rsp+E0h] [rbp+7Fh] BYREF

  v56 = a2;
  v3 = *((_DWORD *)this + 12);
  v50 = v3;
  v5 = a2;
  if ( (v3 & 2) == 0 )
    return (*(__int64 (__fastcall **)(CPrintTicketValidationFilter *))(*(_QWORD *)this + 72LL))(this);
  v7 = 0;
  *((_DWORD *)this + 12) = 24;
  lpVtbl = a3->lpVtbl;
  v55 = 0;
  v53 = 0;
  ElementDescriptor = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))lpVtbl->get_attributes)(a3, &v53);
  if ( ElementDescriptor < 0 )
    goto LABEL_91;
  ElementDescriptor = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v53 + 88LL))(v53, &v55);
  if ( ElementDescriptor < 0 )
    goto LABEL_91;
  v12 = *((_DWORD *)this + 16);
  if ( !v12 )
  {
    v13 = v55;
    if ( v55 <= 1 )
      goto LABEL_11;
    goto LABEL_7;
  }
  if ( v12 != 1 )
  {
LABEL_10:
    v13 = v55;
    goto LABEL_11;
  }
  v13 = v55;
  if ( v55 > 2 )
  {
LABEL_7:
    v57.lpVtbl = 0;
    ElementDescriptor = NPrintTicketUtil::GetElementDescriptor(v5, a3, &v57, (unsigned __int16 **)1, v44);
    if ( ElementDescriptor >= 0 )
      ElementDescriptor = CValidationStatus::SetValidationFailure(
                            (CPrintTicketValidationFilter *)((char *)this + 8),
                            L"%s contains an unexpected XML attribute.  Only 'name' is allowed.",
                            (const unsigned __int16 *)v57.lpVtbl,
                            0,
                            0,
                            v45);
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v57);
    if ( ElementDescriptor < 0 )
      goto LABEL_91;
    goto LABEL_10;
  }
LABEL_11:
  if ( v13 < 1 )
    goto LABEL_46;
  v14 = a3->lpVtbl;
  v52 = 0;
  ElementDescriptor = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))v14->get_attributes)(a3, &v52);
  v15 = 0;
  if ( ElementDescriptor < 0 )
    goto LABEL_42;
  while ( v15 < v55 )
  {
    v51 = 0;
    v48 = 0;
    pbstr = 0;
    v49 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 80LL))(v52, (unsigned int)v15, &v51);
    if ( v16 >= 0 )
    {
      v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v51)(v51, &IID_IXMLDOMAttribute, &v48);
      if ( v16 >= 0 )
        v16 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v48 + 312LL))(v48, &pbstr);
    }
    if ( !SysStringLen(pbstr) )
      goto LABEL_18;
    v35 = pbstr;
    do
    {
      v36 = *(BSTR)((char *)v35
                  + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework"
                  - (char *)pbstr);
      v37 = *v35 - v36;
      if ( v37 )
        break;
      ++v35;
    }
    while ( v36 );
    if ( !v37 )
    {
LABEL_18:
      bstrString = 0;
      if ( v16 < 0 || (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v48 + 328LL))(v48, &v49) < 0 )
        goto LABEL_27;
      v17 = v49;
      v18 = v49;
      do
      {
        v19 = *(BSTR)((char *)v18 + (char *)L"name" - (char *)v49);
        v20 = *v18 - v19;
        if ( v20 )
          break;
        ++v18;
      }
      while ( v19 );
      if ( v20 )
      {
        do
        {
          v21 = *(BSTR)((char *)v17 + (char *)L"constrained" - (char *)v49);
          v22 = *v17 - v21;
          if ( v22 )
            break;
          ++v17;
        }
        while ( v21 );
        if ( v22 )
          goto LABEL_27;
      }
      if ( (*(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v48 + 208LL))(v48, &bstrString)
        || (v28 = bstrString, !(unsigned int)NPrintTicketUtil::IsValidQName((NPrintTicketUtil *)bstrString, v27)) )
      {
LABEL_27:
        *((_DWORD *)this + 2) = 0;
        Message = NPrintTicketUtil::CreateMessage(
                    (NPrintTicketUtil *)L"Attribute content in the %s is invalid.",
                    L"Option",
                    0,
                    0,
                    0,
                    v45);
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset((char *)this + 16);
        if ( Message )
        {
          *((_QWORD *)this + 2) = Message;
          v24 = 0;
        }
        else
        {
          *((_QWORD *)this + 2) = 0;
          v24 = 1;
        }
        ElementDescriptor = v24 != 0 ? 0x8007000E : 0;
      }
      else
      {
        v54 = 0;
        if ( v28 )
        {
          v29 = 0;
          LODWORD(v57.lpVtbl) = 0;
          v30 = 0;
          v31 = -1;
          do
            ++v31;
          while ( v28[v31] );
          if ( (int)v31 > 0 )
          {
            while ( v28[v30] != 58 )
            {
              if ( (int)++v30 >= (int)v31 )
                goto LABEL_68;
            }
            v32 = SysAllocStringLen(v28, v30);
            if ( v32 )
              goto LABEL_106;
LABEL_69:
            ElementDescriptor = -2147024882;
          }
          else
          {
LABEL_68:
            v32 = SysAllocString(&psz);
            if ( !v32 )
              goto LABEL_69;
LABEL_106:
            v40 = 0;
            ElementDescriptor = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, __int64))(**((_QWORD **)v56 + 2) + 56LL))(
                                  *((_QWORD *)v56 + 2),
                                  a3,
                                  1);
            if ( ElementDescriptor >= 0 )
            {
              v40 = 1;
              ElementDescriptor = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD, struct IXMLDOMElement *))(**((_QWORD **)v56 + 2) + 96LL))(
                                    *((_QWORD *)v56 + 2),
                                    v32,
                                    0,
                                    0,
                                    &v57);
            }
            v41 = ElementDescriptor < 0;
            if ( ElementDescriptor )
            {
LABEL_109:
              if ( v41 && v29 )
              {
                SysFreeString(v29);
                v29 = 0;
              }
            }
            else
            {
              ++LODWORD(v57.lpVtbl);
              v43 = SysAllocStringLen(0, (UINT)v57.lpVtbl);
              v29 = v43;
              if ( v43 )
              {
                ElementDescriptor = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, BSTR, struct IXMLDOMElement *))(**((_QWORD **)v56 + 2) + 96LL))(
                                      *((_QWORD *)v56 + 2),
                                      v32,
                                      0,
                                      v43,
                                      &v57);
                v41 = ElementDescriptor < 0;
                goto LABEL_109;
              }
              ElementDescriptor = -2147024882;
            }
            if ( v40 )
            {
              v42 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v56 + 2) + 64LL))(*((_QWORD *)v56 + 2));
              if ( v42 < 0 )
                ElementDescriptor = v42;
            }
            SysFreeString(v32);
          }
          if ( ElementDescriptor >= 0 && !SysStringLen(v29) )
            ElementDescriptor = CValidationStatus::SetValidationFailure(
                                  (CPrintTicketValidationFilter *)((char *)this + 8),
                                  L"The prefix of '%s' in the %s attribute '%s' does not map to a valid URI.",
                                  bstrString,
                                  L"Option",
                                  v49,
                                  v45);
          if ( v29 )
            SysFreeString(v29);
          v7 = 0;
        }
        else
        {
          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v54);
          ElementDescriptor = -2147024809;
        }
      }
      if ( bstrString )
        SysFreeString(bstrString);
      goto LABEL_32;
    }
    *((_DWORD *)this + 2) = 0;
    v38 = NPrintTicketUtil::CreateMessage(
            (NPrintTicketUtil *)L"Attribute content in the %s does not map to the namespace %s.",
            L"Option",
            L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework",
            0,
            0,
            v45);
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset((char *)this + 16);
    if ( v38 )
    {
      *((_QWORD *)this + 2) = v38;
      v39 = 0;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
      v39 = 1;
    }
    ElementDescriptor = v39 != 0 ? 0x8007000E : 0;
LABEL_32:
    if ( v49 )
    {
      SysFreeString(v49);
      v49 = 0;
    }
    if ( pbstr )
    {
      SysFreeString(pbstr);
      pbstr = 0;
    }
    if ( v48 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      v48 = 0;
    }
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    ++v15;
    if ( ElementDescriptor < 0 )
      break;
  }
  v3 = v50;
LABEL_42:
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  if ( ElementDescriptor >= 0 )
  {
    v5 = v56;
LABEL_46:
    v25 = *((_DWORD *)this + 2) == 0;
    if ( !*((_DWORD *)this + 2) )
      goto LABEL_89;
    ElementDescriptor = NPrintTicketUtil::HasOnlyChildTypes((NPrintTicketUtil *)a3, v10, v11);
    if ( ElementDescriptor == 1 )
      ElementDescriptor = CValidationStatus::SetValidationFailure(
                            (CPrintTicketValidationFilter *)((char *)this + 8),
                            L"Invalid content exists in %s.  %s elements may only contain elements and comments.",
                            L"Option",
                            L"Option",
                            0,
                            v45);
    if ( ElementDescriptor < 0 )
      goto LABEL_91;
    v25 = *((_DWORD *)this + 2) == 0;
    if ( !*((_DWORD *)this + 2) )
    {
LABEL_89:
      if ( v25 )
        ElementDescriptor = 1;
      goto LABEL_91;
    }
    pbstr = 0;
    ElementDescriptor = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))a3->lpVtbl->get_childNodes)(
                          a3,
                          &pbstr);
    if ( ElementDescriptor >= 0 )
    {
      ElementDescriptor = (*(__int64 (__fastcall **)(BSTR))(*(_QWORD *)pbstr + 80LL))(pbstr);
      if ( ElementDescriptor >= 0 )
      {
        v57.lpVtbl = 0;
        while ( 1 )
        {
          ElementDescriptor = (*(__int64 (__fastcall **)(BSTR, struct IXMLDOMElement *))(*(_QWORD *)pbstr + 72LL))(
                                pbstr,
                                &v57);
          if ( ElementDescriptor )
            break;
          bstrString = 0;
          if ( (*(int (__fastcall **)(struct IXMLDOMElementVtbl *, GUID *, BSTR *))v57.lpVtbl->QueryInterface)(
                 v57.lpVtbl,
                 &IID_IXMLDOMElement,
                 &bstrString) >= 0 )
          {
            v26 = (**(__int64 (__fastcall ***)(CPrintTicketValidationFilter *, NPrintTicketUtil *, BSTR))this)(
                    this,
                    v5,
                    bstrString);
            ElementDescriptor = v26;
            if ( v26 < 0 || v26 == 1 )
            {
              v7 = 1;
              if ( bstrString )
                (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
              break;
            }
          }
          if ( v57.lpVtbl )
          {
            (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v57.lpVtbl->QueryInterface + 2))(v57.lpVtbl);
            v57.lpVtbl = 0;
          }
          if ( bstrString )
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
        }
        if ( v57.lpVtbl )
          (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v57.lpVtbl->QueryInterface + 2))(v57.lpVtbl);
        if ( ElementDescriptor >= 0 )
          ElementDescriptor = v7 != 0;
      }
    }
    if ( pbstr )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)pbstr + 16LL))(pbstr);
    if ( ElementDescriptor == -2147155967 )
      ElementDescriptor = CValidationStatus::SetValidationFailure(
                            (CPrintTicketValidationFilter *)((char *)this + 8),
                            L"One or more children of the %s element contain an invalid namespace prefix or namespace.",
                            L"Option",
                            0,
                            0,
                            v45);
    if ( ElementDescriptor >= 0 )
    {
      v25 = *((_DWORD *)this + 2) == 0;
      goto LABEL_89;
    }
  }
LABEL_91:
  v33 = v53;
  *((_DWORD *)this + 12) = v3;
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return (unsigned int)ElementDescriptor;
}

```

## disassembly

```asm
0x180004ec0  mov     rax, rsp
0x180004ec3  mov     [rax+10h], rdx
0x180004ec7  push    rbp
0x180004ec8  push    r12
0x180004eca  push    r13
0x180004ecc  push    r14
0x180004ece  push    r15
0x180004ed0  lea     rbp, [rax-5Fh]
0x180004ed4  sub     rsp, 90h
0x180004edb  mov     r14d, [rcx+30h]
0x180004edf  mov     r13, r8
0x180004ee2  mov     [rbp+57h+var_60], r14d
0x180004ee6  mov     r15, rdx
0x180004ee9  mov     r12, rcx
0x180004eec  test    r14b, 2
0x180004ef0  jz      loc_1800055F2
0x180004ef6  mov     [rax-30h], rsi
0x180004efa  lea     rdx, [rbp+57h+var_48]
0x180004efe  mov     [rax-38h], rdi
0x180004f02  xor     esi, esi
0x180004f04  mov     dword ptr [rcx+30h], 18h
0x180004f0b  mov     rcx, r8
0x180004f0e  mov     rax, [r8]
0x180004f11  mov     [rbp+57h+arg_0], esi
0x180004f14  mov     [rbp+57h+var_48], rsi
0x180004f18  mov     rax, [rax+88h]
0x180004f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f24  mov     edi, eax
0x180004f26  test    eax, eax
0x180004f28  js      loc_18000541F
0x180004f2e  mov     rcx, [rbp+57h+var_48]
0x180004f32  lea     rdx, [rbp+57h+arg_0]
0x180004f36  mov     rax, [rcx]
0x180004f39  mov     rax, [rax+58h]
0x180004f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f42  mov     edi, eax
0x180004f44  test    eax, eax
0x180004f46  js      loc_18000541F
0x180004f4c  mov     eax, [r12+40h]
0x180004f51  test    eax, eax
0x180004f53  jz      loc_18000560F
0x180004f59  cmp     eax, 1
0x180004f5c  jnz     short loc_180004FB5
0x180004f5e  mov     eax, [rbp+57h+arg_0]
0x180004f61  cmp     eax, 2
0x180004f64  jle     short loc_180004FB8
0x180004f66  mov     r9d, 1; unsigned __int16 **
0x180004f6c  mov     [rbp+57h+arg_18.lpVtbl], rsi
0x180004f70  lea     r8, [rbp+57h+arg_18]; struct IXMLDOMElement *
0x180004f74  mov     rdx, r13; struct IXMLDOMElement *
0x180004f77  mov     rcx, r15; this
0x180004f7a  call    ?GetElementDescriptor@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEAPEAGH@Z; NPrintTicketUtil::GetElementDescriptor(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort * *,int)
0x180004f7f  mov     edi, eax
0x180004f81  test    eax, eax
0x180004f83  js      short loc_180004FA4
0x180004f85  mov     r8, [rbp+57h+arg_18.lpVtbl]; unsigned __int16 *
0x180004f89  lea     rcx, [r12+8]; this
0x180004f8e  xor     r9d, r9d; unsigned __int16 *
0x180004f91  mov     [rsp+20h], rsi; unsigned __int16 *
0x180004f96  lea     rdx, aSContainsAnUne; "%s contains an unexpected XML attribute"...
0x180004f9d  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180004fa2  mov     edi, eax
0x180004fa4  lea     rcx, [rbp+57h+arg_18]
0x180004fa8  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180004fad  test    edi, edi
0x180004faf  js      loc_18000541F
0x180004fb5  mov     eax, [rbp+57h+arg_0]
0x180004fb8  mov     [rsp+0B0h+arg_10], rbx
0x180004fc0  cmp     eax, 1
0x180004fc3  jl      loc_1800051D9
0x180004fc9  mov     rax, [r13+0]
0x180004fcd  lea     rdx, [rbp+57h+var_50]
0x180004fd1  mov     rcx, r13
0x180004fd4  mov     [rbp+57h+var_50], rsi
0x180004fd8  mov     rax, [rax+88h]
0x180004fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe4  mov     edi, eax
0x180004fe6  mov     r15d, esi
0x180004fe9  test    eax, eax
0x180004feb  js      loc_1800051B8
0x180004ff1  lea     r14, aName; "name"
0x180004ff8  nop     dword ptr [rax+rax+00000000h]
0x180005000  cmp     r15d, [rbp+57h+arg_0]
0x180005004  jge     loc_1800051B4
0x18000500a  mov     rcx, [rbp+57h+var_50]
0x18000500e  lea     r8, [rbp+57h+var_58]
0x180005012  mov     [rbp+57h+var_58], rsi
0x180005016  mov     edx, r15d
0x180005019  mov     [rbp+57h+var_70], rsi
0x18000501d  mov     [rbp+57h+pbstr], rsi
0x180005021  mov     [rbp+57h+var_68], rsi
0x180005025  mov     rax, [rcx]
0x180005028  mov     rax, [rax+50h]
0x18000502c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005031  mov     ebx, eax
0x180005033  test    eax, eax
0x180005035  js      short loc_180005070
0x180005037  mov     rcx, [rbp+57h+var_58]
0x18000503b  lea     r8, [rbp+57h+var_70]
0x18000503f  lea     rdx, IID_IXMLDOMAttribute
0x180005046  mov     rax, [rcx]
0x180005049  mov     rax, [rax]
0x18000504c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005051  mov     ebx, eax
0x180005053  test    eax, eax
0x180005055  js      short loc_180005070
0x180005057  mov     rcx, [rbp+57h+var_70]
0x18000505b  lea     rdx, [rbp+57h+pbstr]
0x18000505f  mov     rax, [rcx]
0x180005062  mov     rax, [rax+138h]
0x180005069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000506e  mov     ebx, eax
0x180005070  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180005074  call    cs:__imp_SysStringLen
0x18000507a  test    eax, eax
0x18000507c  jnz     loc_18000545C
0x180005082  mov     [rbp+57h+bstrString], rsi
0x180005086  test    ebx, ebx
0x180005088  js      short loc_1800050FC
0x18000508a  mov     rcx, [rbp+57h+var_70]
0x18000508e  lea     rdx, [rbp+57h+var_68]
0x180005092  mov     rax, [rcx]
0x180005095  mov     rax, [rax+148h]
0x18000509c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050a1  test    eax, eax
0x1800050a3  js      short loc_1800050FC
0x1800050a5  mov     rcx, [rbp+57h+var_68]
0x1800050a9  mov     r9, r14
0x1800050ac  mov     rax, rcx
0x1800050af  sub     r9, rcx
0x1800050b2  movzx   r8d, word ptr [rax]
0x1800050b6  movzx   edx, word ptr [rax+r9]
0x1800050bb  sub     r8d, edx
0x1800050be  jnz     short loc_1800050C8
0x1800050c0  add     rax, 2
0x1800050c4  test    edx, edx
0x1800050c6  jnz     short loc_1800050B2
0x1800050c8  test    r8d, r8d
0x1800050cb  jz      loc_1800052EF
0x1800050d1  lea     r8, aConstrained; "constrained"
0x1800050d8  sub     r8, rcx
0x1800050db  nop     dword ptr [rax+rax+00h]
0x1800050e0  movzx   edx, word ptr [rcx]
0x1800050e3  movzx   eax, word ptr [rcx+r8]
0x1800050e8  sub     edx, eax
0x1800050ea  jnz     short loc_1800050F4
0x1800050ec  add     rcx, 2
0x1800050f0  test    eax, eax
0x1800050f2  jnz     short loc_1800050E0
0x1800050f4  test    edx, edx
0x1800050f6  jz      loc_1800052EF
0x1800050fc  xor     r9d, r9d; unsigned __int16 *
0x1800050ff  mov     [r12+8], esi
0x180005104  xor     r8d, r8d; unsigned __int16 *
0x180005107  mov     [rsp+20h], rsi; unsigned __int16 *
0x18000510c  lea     rdx, aOption; "Option"
0x180005113  lea     rcx, aAttributeConte; "Attribute content in the %s is invalid."
0x18000511a  call    ?CreateMessage@NPrintTicketUtil@@YAPEAGPEBG0000@Z; NPrintTicketUtil::CreateMessage(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000511f  lea     rcx, [r12+10h]
0x180005124  mov     rdi, rax
0x180005127  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000512c  test    rdi, rdi
0x18000512f  jz      loc_18000539A
0x180005135  mov     [r12+10h], rdi
0x18000513a  xor     al, al
0x18000513c  neg     al
0x18000513e  sbb     edi, edi
0x180005140  and     edi, 8007000Eh
0x180005146  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000514a  test    rcx, rcx
0x18000514d  jz      short loc_180005155
0x18000514f  call    cs:__imp_SysFreeString
0x180005155  mov     rcx, [rbp+57h+var_68]; bstrString
0x180005159  test    rcx, rcx
0x18000515c  jz      short loc_180005168
0x18000515e  call    cs:__imp_SysFreeString
0x180005164  mov     [rbp+57h+var_68], rsi
0x180005168  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18000516c  test    rcx, rcx
0x18000516f  jz      short loc_18000517B
0x180005171  call    cs:__imp_SysFreeString
0x180005177  mov     [rbp+57h+pbstr], rsi
0x18000517b  mov     rcx, [rbp+57h+var_70]
0x18000517f  test    rcx, rcx
0x180005182  jz      short loc_180005194
0x180005184  mov     rax, [rcx]
0x180005187  mov     rax, [rax+10h]
0x18000518b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005190  mov     [rbp+57h+var_70], rsi
0x180005194  mov     rcx, [rbp+57h+var_58]
0x180005198  test    rcx, rcx
0x18000519b  jz      short loc_1800051A9
0x18000519d  mov     rax, [rcx]
0x1800051a0  mov     rax, [rax+10h]
0x1800051a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a9  inc     r15d
0x1800051ac  test    edi, edi
0x1800051ae  jns     loc_180005000
0x1800051b4  mov     r14d, [rbp+57h+var_60]
0x1800051b8  mov     rcx, [rbp+57h+var_50]
0x1800051bc  test    rcx, rcx
0x1800051bf  jz      short loc_1800051CD
0x1800051c1  mov     rax, [rcx]
0x1800051c4  mov     rax, [rax+10h]
0x1800051c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051cd  test    edi, edi
0x1800051cf  js      loc_180005417
0x1800051d5  mov     r15, [rbp+57h+arg_8]
0x1800051d9  cmp     dword ptr [r12+8], 0
0x1800051df  jz      loc_18000540F
0x1800051e5  mov     rcx, r13; this
0x1800051e8  call    ?HasOnlyChildTypes@NPrintTicketUtil@@YAJPEAUIXMLDOMNode@@I@Z; NPrintTicketUtil::HasOnlyChildTypes(IXMLDOMNode *,uint)
0x1800051ed  mov     edi, eax
0x1800051ef  cmp     eax, 1
0x1800051f2  jz      loc_18000567B
0x1800051f8  test    edi, edi
0x1800051fa  js      loc_180005417
0x180005200  cmp     dword ptr [r12+8], 0
0x180005206  jz      loc_18000540F
0x18000520c  mov     [rbp+57h+pbstr], rsi
0x180005210  lea     rdx, [rbp+57h+pbstr]
0x180005214  mov     rax, [r13+0]
0x180005218  mov     rcx, r13
0x18000521b  mov     rax, [rax+60h]
0x18000521f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005224  mov     edi, eax
0x180005226  test    eax, eax
0x180005228  js      loc_1800053E4
0x18000522e  mov     rcx, [rbp+57h+pbstr]
0x180005232  mov     rax, [rcx]
0x180005235  mov     rax, [rax+50h]
0x180005239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000523e  mov     edi, eax
0x180005240  test    eax, eax
0x180005242  js      loc_1800053E4
0x180005248  xor     r13d, r13d
0x18000524b  mov     [rbp+57h+arg_18.lpVtbl], r13
0x18000524f  mov     rcx, [rbp+57h+pbstr]
0x180005253  lea     rdx, [rbp+57h+arg_18]
0x180005257  mov     rax, [rcx]
0x18000525a  mov     rax, [rax+48h]
0x18000525e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005263  mov     edi, eax
0x180005265  test    eax, eax
0x180005267  jnz     loc_1800053C0
0x18000526d  mov     rcx, [rbp+57h+arg_18.lpVtbl]
0x180005271  lea     r8, [rbp+57h+bstrString]
0x180005275  mov     [rbp+57h+bstrString], r13
0x180005279  lea     rdx, IID_IXMLDOMElement
0x180005280  mov     rax, [rcx]
0x180005283  mov     rax, [rax]
0x180005286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528b  test    eax, eax
0x18000528d  js      short loc_1800052B8
0x18000528f  mov     rax, [r12]
0x180005293  mov     rdx, r15
0x180005296  mov     r8, [rbp+57h+bstrString]
0x18000529a  mov     rcx, r12
0x18000529d  mov     rax, [rax]
0x1800052a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a5  mov     edi, eax
0x1800052a7  test    eax, eax
0x1800052a9  js      loc_1800053A6
0x1800052af  cmp     eax, 1
0x1800052b2  jz      loc_1800053A6
0x1800052b8  mov     rcx, [rbp+57h+arg_18.lpVtbl]
0x1800052bc  test    rcx, rcx
0x1800052bf  jz      short loc_1800052D1
0x1800052c1  mov     rax, [rcx]
0x1800052c4  mov     rax, [rax+10h]
0x1800052c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052cd  mov     [rbp+57h+arg_18.lpVtbl], r13
0x1800052d1  mov     rcx, [rbp+57h+bstrString]
0x1800052d5  test    rcx, rcx
0x1800052d8  jz      loc_18000524F
0x1800052de  mov     rax, [rcx]
0x1800052e1  mov     rax, [rax+10h]
0x1800052e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ea  jmp     loc_18000524F
0x1800052ef  mov     rcx, [rbp+57h+var_70]
0x1800052f3  lea     rdx, [rbp+57h+bstrString]
0x1800052f7  mov     rax, [rcx]
0x1800052fa  mov     rax, [rax+0D0h]
0x180005301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005306  test    eax, eax
0x180005308  jnz     loc_1800050FC
0x18000530e  mov     rdi, [rbp+57h+bstrString]
0x180005312  mov     rcx, rdi; this
0x180005315  call    ?IsValidQName@NPrintTicketUtil@@YAHPEAG@Z; NPrintTicketUtil::IsValidQName(ushort *)
0x18000531a  test    eax, eax
0x18000531c  jz      loc_1800050FC
0x180005322  mov     [rbp+57h+var_40], rsi
0x180005326  test    rdi, rdi
0x180005329  jz      loc_1800054DF
0x18000532f  mov     rbx, rsi
0x180005332  mov     dword ptr [rbp+57h+arg_18.lpVtbl], esi
0x180005335  mov     edx, esi; ui
0x180005337  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000533e  xchg    ax, ax
0x180005340  inc     rcx
  ... truncated ...
```
