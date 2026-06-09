# CommunityXML_VerifyMetadataResponse(ushort *,_DPA *)

- ea: `0x1800c6614`
- end: `0x1800c6a6d`
- name: `?CommunityXML_VerifyMetadataResponse@@YAJPEAGPEAU_DPA@@@Z`
- size: `1113`
- prototype: `int(unsigned __int16 *, struct _DPA *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800af87c`

## callees

- `0x180002098`
- `0x1800c6298`
- `0x1800c6614`
- `0x1800cb738`
- `0x1800cb790`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c6663`
- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c6663`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c66b9`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c68a6`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c6a04`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c66b9`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c68a6`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c6a04`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c66d6`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c6900`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c66d6`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c6900`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c66ec`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c66ec`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6926`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6926`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c6958`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c6958`
- `ole32!CoCreateInstance` at `0x1800c6755`
- `ole32!CoCreateInstance` at `0x1800c6755`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c681c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c69cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6a3a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c681c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c69cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6a3a`

## pseudocode

```c
__int64 __fastcall CommunityXML_VerifyMetadataResponse(unsigned __int16 *a1, struct _DPA *a2)
{
  HRESULT ElementsByTagName; // ebx
  int v4; // eax
  BSTR v5; // rdi
  struct IXMLDOMNode *v6; // rcx
  LPVOID v7; // rcx
  int v8; // eax
  unsigned int i; // edi
  int v10; // eax
  struct __MIDL_ICommunityTransport_0006 *Ptr; // rax
  BSTR *p_bstrString; // rcx
  struct IXMLDOMNode *v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR pszDst[256]; // [rsp+70h] [rbp-90h] BYREF

  v20[0] = 0;
  if ( a1 && a2 )
  {
    v17 = 0;
    ElementsByTagName = XMLDOMFromBStr(a1, &v17);
    if ( ElementsByTagName >= 0 )
    {
      v18 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 360LL))(v17, &v18);
      ElementsByTagName = v4;
      if ( v4 == 1 )
      {
        ElementsByTagName = -2147023728;
      }
      else if ( v4 >= 0 )
      {
        ppv = 0;
        ElementsByTagName = XMLElem_GetElementsByTagName(v18, L"QueryResult", &ppv);
        if ( ElementsByTagName >= 0 )
        {
          v14 = 0;
          ElementsByTagName = XMLNodeList_GetChild(ppv, 0, &v14);
          if ( ElementsByTagName >= 0 )
          {
            ElementsByTagName = XMLNode_GetTagText(v14, v20);
            OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v14);
          }
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppv);
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v18);
      }
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v17);
    }
    if ( ElementsByTagName < 0 )
      return (unsigned int)ElementsByTagName;
    v5 = v20[0];
    ppv = 0;
    if ( !v20[0] )
    {
      ElementsByTagName = -2147024809;
      goto LABEL_54;
    }
    ElementsByTagName = CoCreateInstance(&CLSID_DOMDocument2, 0, 1u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &ppv);
    if ( ElementsByTagName >= 0 )
    {
      LOWORD(v15) = 0;
      ElementsByTagName = (*(__int64 (__fastcall **)(LPVOID, BSTR, int *))(*(_QWORD *)ppv + 520LL))(ppv, v5, &v15);
      if ( ElementsByTagName < 0 )
      {
LABEL_19:
        v14 = 0;
        if ( (*(int (__fastcall **)(LPVOID, struct IXMLDOMNode **))(*(_QWORD *)ppv + 480LL))(ppv, &v14) >= 0 )
        {
          bstrString = 0;
          if ( ((int (__fastcall *)(struct IXMLDOMNode *, BSTR *))v14->lpVtbl->put_nodeValue)(v14, &bstrString) >= 0 )
          {
            LODWORD(v17) = 0;
            LODWORD(v18) = 0;
            ((void (__fastcall *)(struct IXMLDOMNode *, __int64 *))v14->lpVtbl->get_parentNode)(v14, &v17);
            ((void (__fastcall *)(struct IXMLDOMNode *, __int64 *))v14->lpVtbl->get_childNodes)(v14, &v18);
            SysFreeString(bstrString);
          }
          v6 = v14;
          if ( v14 )
          {
            v14 = 0;
            ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
          }
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppv);
        v7 = 0;
        ppv = 0;
LABEL_26:
        if ( ElementsByTagName < 0 )
        {
LABEL_54:
          SysFreeString(v20[0]);
          return (unsigned int)ElementsByTagName;
        }
        v17 = 0;
        v8 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v7 + 360LL))(v7, &v17);
        ElementsByTagName = v8;
        if ( v8 == 1 )
        {
          ElementsByTagName = -2147023728;
LABEL_52:
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppv);
          goto LABEL_54;
        }
        if ( v8 < 0 )
          goto LABEL_52;
        v18 = 0;
        if ( (int)XMLElem_GetElementsByTagName(v17, L"Message", &v18) < 0 )
        {
          bstrString = 0;
          ElementsByTagName = XMLElem_GetElementsByTagName(v17, L"Message", &bstrString);
          if ( ElementsByTagName < 0 )
          {
LABEL_51:
            OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v17);
            goto LABEL_52;
          }
          p_bstrString = &bstrString;
        }
        else
        {
          v15 = 0;
          ElementsByTagName = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 64LL))(v18, &v15);
          if ( ElementsByTagName >= 0 )
          {
            for ( i = 0; (int)i < v15; ++i )
            {
              if ( ElementsByTagName < 0 )
                break;
              v14 = 0;
              ElementsByTagName = XMLNodeList_GetChild(v18, i, &v14);
              if ( ElementsByTagName >= 0 )
              {
                bstrString = 0;
                ElementsByTagName = XMLNode_GetAttributeValue(v14, L"ExternalID", &bstrString);
                if ( ElementsByTagName >= 0 )
                {
                  memset_0(pszDst, 0, 0xFFu);
                  if ( SHUnicodeToAnsi(bstrString, pszDst, 255) )
                  {
                    v10 = DPA_Search(a2, pszDst, 1, DPACompare, 0, 0);
                    if ( v10 != -1 )
                    {
                      Ptr = (struct __MIDL_ICommunityTransport_0006 *)DPA_GetPtr(a2, v10);
                      if ( Ptr )
                      {
                        if ( *((_BYTE *)Ptr + 321) )
                          ElementsByTagName = 0;
                        else
                          ElementsByTagName = CommunityXML_VerifyMessageNode(v14, Ptr);
                      }
                      else
                      {
                        ElementsByTagName = -2147467259;
                      }
                    }
                  }
                  else
                  {
                    ElementsByTagName = -2147024882;
                  }
                  SysFreeString(bstrString);
                }
                OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v14);
              }
            }
          }
          p_bstrString = (BSTR *)&v18;
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(p_bstrString);
        goto LABEL_51;
      }
      if ( (_WORD)v15 != 0xFFFF )
      {
        ElementsByTagName = -2147467259;
        goto LABEL_19;
      }
    }
    v7 = ppv;
    goto LABEL_26;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800c6614  mov     [rsp-8+arg_10], rbx
0x1800c6619  mov     [rsp-8+arg_18], rsi
0x1800c661e  push    rbp
0x1800c661f  push    rdi
0x1800c6620  push    r14
0x1800c6622  lea     rbp, [rsp-80h]
0x1800c6627  sub     rsp, 180h
0x1800c662e  mov     rax, cs:__security_cookie
0x1800c6635  xor     rax, rsp
0x1800c6638  mov     [rbp+90h+var_20], rax
0x1800c663c  xor     r14d, r14d
0x1800c663f  mov     rsi, rdx
0x1800c6642  mov     [rsp+190h+var_130], r14
0x1800c6647  test    rcx, rcx
0x1800c664a  jz      loc_1800C6A44
0x1800c6650  test    rdx, rdx
0x1800c6653  jz      loc_1800C6A44
0x1800c6659  lea     rdx, [rsp+190h+var_148]
0x1800c665e  mov     [rsp+190h+var_148], r14
0x1800c6663  call    cs:__imp_XMLDOMFromBStr
0x1800c6669  mov     ebx, eax
0x1800c666b  test    eax, eax
0x1800c666d  js      loc_1800C671C
0x1800c6673  mov     rcx, [rsp+190h+var_148]
0x1800c6678  lea     rdx, [rsp+190h+var_140]
0x1800c667d  mov     [rsp+190h+var_140], r14
0x1800c6682  mov     rax, [rcx]
0x1800c6685  mov     rax, [rax+168h]
0x1800c668c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6691  mov     ebx, eax
0x1800c6693  cmp     eax, 1
0x1800c6696  jnz     short loc_1800C669F
0x1800c6698  mov     ebx, 80070490h
0x1800c669d  jmp     short loc_1800C6712
0x1800c669f  test    eax, eax
0x1800c66a1  js      short loc_1800C6712
0x1800c66a3  mov     rcx, [rsp+190h+var_140]
0x1800c66a8  lea     r8, [rsp+190h+var_150]
0x1800c66ad  lea     rdx, aQueryresult; "QueryResult"
0x1800c66b4  mov     [rsp+190h+var_150], r14
0x1800c66b9  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c66bf  mov     ebx, eax
0x1800c66c1  test    eax, eax
0x1800c66c3  js      short loc_1800C6708
0x1800c66c5  mov     rcx, [rsp+190h+var_150]
0x1800c66ca  lea     r8, [rsp+190h+var_160]
0x1800c66cf  xor     edx, edx
0x1800c66d1  mov     [rsp+190h+var_160], r14
0x1800c66d6  call    cs:__imp_XMLNodeList_GetChild
0x1800c66dc  mov     ebx, eax
0x1800c66de  test    eax, eax
0x1800c66e0  js      short loc_1800C66FE
0x1800c66e2  mov     rcx, [rsp+190h+var_160]
0x1800c66e7  lea     rdx, [rsp+190h+var_130]
0x1800c66ec  call    cs:__imp_XMLNode_GetTagText
0x1800c66f2  lea     rcx, [rsp+190h+var_160]
0x1800c66f7  mov     ebx, eax
0x1800c66f9  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c66fe  lea     rcx, [rsp+190h+var_150]
0x1800c6703  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6708  lea     rcx, [rsp+190h+var_140]
0x1800c670d  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6712  lea     rcx, [rsp+190h+var_148]
0x1800c6717  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c671c  test    ebx, ebx
0x1800c671e  js      loc_1800C6A40
0x1800c6724  mov     rdi, [rsp+190h+var_130]
0x1800c6729  mov     [rsp+190h+var_150], r14
0x1800c672e  test    rdi, rdi
0x1800c6731  jz      loc_1800C6A30
0x1800c6737  xor     edx, edx; pUnkOuter
0x1800c6739  lea     rax, [rsp+190h+var_150]
0x1800c673e  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1800c6745  mov     [rsp+190h+ppv], rax; ppv
0x1800c674a  lea     rcx, CLSID_DOMDocument2; rclsid
0x1800c6751  lea     r8d, [rdx+1]; dwClsContext
0x1800c6755  call    cs:__imp_CoCreateInstance
0x1800c675b  mov     ebx, eax
0x1800c675d  test    eax, eax
0x1800c675f  js      loc_1800C6851
0x1800c6765  mov     rcx, [rsp+190h+var_150]
0x1800c676a  lea     r8, [rsp+190h+var_158]
0x1800c676f  mov     word ptr [rsp+190h+var_158], r14w
0x1800c6775  mov     rdx, rdi
0x1800c6778  mov     rax, [rcx]
0x1800c677b  mov     rax, [rax+208h]
0x1800c6782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6787  mov     ebx, eax
0x1800c6789  test    eax, eax
0x1800c678b  js      short loc_1800C67A0
0x1800c678d  or      eax, 0FFFFFFFFh
0x1800c6790  cmp     ax, word ptr [rsp+190h+var_158]
0x1800c6795  jz      loc_1800C6851
0x1800c679b  mov     ebx, 80004005h
0x1800c67a0  mov     rcx, [rsp+190h+var_150]
0x1800c67a5  lea     rdx, [rsp+190h+var_160]
0x1800c67aa  mov     [rsp+190h+var_160], r14
0x1800c67af  mov     rax, [rcx]
0x1800c67b2  mov     rax, [rax+1E0h]
0x1800c67b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c67be  test    eax, eax
0x1800c67c0  js      short loc_1800C683D
0x1800c67c2  mov     rcx, [rsp+190h+var_160]
0x1800c67c7  lea     rdx, [rsp+190h+bstrString]
0x1800c67cc  mov     [rsp+190h+bstrString], r14
0x1800c67d1  mov     rax, [rcx]
0x1800c67d4  mov     rax, [rax+48h]
0x1800c67d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c67dd  test    eax, eax
0x1800c67df  js      short loc_1800C6822
0x1800c67e1  mov     rcx, [rsp+190h+var_160]
0x1800c67e6  lea     rdx, [rsp+190h+var_148]
0x1800c67eb  mov     dword ptr [rsp+190h+var_148], r14d
0x1800c67f0  mov     dword ptr [rsp+190h+var_140], r14d
0x1800c67f5  mov     rax, [rcx]
0x1800c67f8  mov     rax, [rax+58h]
0x1800c67fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6801  mov     rcx, [rsp+190h+var_160]
0x1800c6806  lea     rdx, [rsp+190h+var_140]
0x1800c680b  mov     rax, [rcx]
0x1800c680e  mov     rax, [rax+60h]
0x1800c6812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6817  mov     rcx, [rsp+190h+bstrString]; bstrString
0x1800c681c  call    cs:__imp_SysFreeString
0x1800c6822  mov     rcx, [rsp+190h+var_160]
0x1800c6827  test    rcx, rcx
0x1800c682a  jz      short loc_1800C683D
0x1800c682c  mov     [rsp+190h+var_160], r14
0x1800c6831  mov     rax, [rcx]
0x1800c6834  mov     rax, [rax+10h]
0x1800c6838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c683d  lea     rcx, [rsp+190h+var_150]
0x1800c6842  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6847  mov     rcx, r14
0x1800c684a  mov     [rsp+190h+var_150], rcx
0x1800c684f  jmp     short loc_1800C6856
0x1800c6851  mov     rcx, [rsp+190h+var_150]
0x1800c6856  test    ebx, ebx
0x1800c6858  js      loc_1800C6A35
0x1800c685e  mov     [rsp+190h+var_148], r14
0x1800c6863  lea     rdx, [rsp+190h+var_148]
0x1800c6868  mov     rax, [rcx]
0x1800c686b  mov     rax, [rax+168h]
0x1800c6872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6877  mov     ebx, eax
0x1800c6879  cmp     eax, 1
0x1800c687c  jnz     short loc_1800C6888
0x1800c687e  mov     ebx, 80070490h
0x1800c6883  jmp     loc_1800C6A24
0x1800c6888  test    eax, eax
0x1800c688a  js      loc_1800C6A24
0x1800c6890  mov     rcx, [rsp+190h+var_148]
0x1800c6895  lea     r8, [rsp+190h+var_140]
0x1800c689a  lea     rdx, aMessage; "Message"
0x1800c68a1  mov     [rsp+190h+var_140], r14
0x1800c68a6  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c68ac  test    eax, eax
0x1800c68ae  js      loc_1800C69EE
0x1800c68b4  mov     rcx, [rsp+190h+var_140]
0x1800c68b9  lea     rdx, [rsp+190h+var_158]
0x1800c68be  mov     [rsp+190h+var_158], r14d
0x1800c68c3  mov     rax, [rcx]
0x1800c68c6  mov     rax, [rax+40h]
0x1800c68ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c68cf  mov     ebx, eax
0x1800c68d1  test    eax, eax
0x1800c68d3  js      loc_1800C69E7
0x1800c68d9  mov     edi, r14d
0x1800c68dc  cmp     [rsp+190h+var_158], r14d
0x1800c68e1  jle     loc_1800C69E7
0x1800c68e7  test    ebx, ebx
0x1800c68e9  js      loc_1800C69E7
0x1800c68ef  mov     rcx, [rsp+190h+var_140]
0x1800c68f4  lea     r8, [rsp+190h+var_160]
0x1800c68f9  mov     edx, edi
0x1800c68fb  mov     [rsp+190h+var_160], r14
0x1800c6900  call    cs:__imp_XMLNodeList_GetChild
0x1800c6906  mov     ebx, eax
0x1800c6908  test    eax, eax
0x1800c690a  js      loc_1800C69DB
0x1800c6910  mov     rcx, [rsp+190h+var_160]
0x1800c6915  lea     r8, [rsp+190h+bstrString]
0x1800c691a  lea     rdx, aExternalid; "ExternalID"
0x1800c6921  mov     [rsp+190h+bstrString], r14
0x1800c6926  call    cs:__imp_XMLNode_GetAttributeValue
0x1800c692c  mov     ebx, eax
0x1800c692e  test    eax, eax
0x1800c6930  js      loc_1800C69D1
0x1800c6936  xor     edx, edx; Val
0x1800c6938  lea     rcx, [rsp+190h+pszDst]; void *
0x1800c693d  mov     r8d, 0FFh; Size
0x1800c6943  call    memset_0
0x1800c6948  mov     rcx, [rsp+190h+bstrString]; pwszSrc
0x1800c694d  lea     rdx, [rsp+190h+pszDst]; pszDst
0x1800c6952  mov     r8d, 0FFh; cchBuf
0x1800c6958  call    cs:__imp_SHUnicodeToAnsi
0x1800c695e  test    eax, eax
0x1800c6960  jz      short loc_1800C69C1
0x1800c6962  mov     [rsp+190h+options], r14d; options
0x1800c6967  lea     r9, ?DPACompare@@YAHPEAX0_J@Z; pfnCompare
0x1800c696e  mov     r8d, 1; iStart
0x1800c6974  mov     [rsp+190h+ppv], r14; lParam
0x1800c6979  lea     rdx, [rsp+190h+pszDst]; pFind
0x1800c697e  mov     rcx, rsi; hdpa
0x1800c6981  call    DPA_Search
0x1800c6986  cmp     eax, 0FFFFFFFFh
0x1800c6989  jz      short loc_1800C69C6
0x1800c698b  movsxd  rdx, eax; i
0x1800c698e  mov     rcx, rsi; hdpa
0x1800c6991  call    DPA_GetPtr
0x1800c6996  test    rax, rax
0x1800c6999  jz      short loc_1800C69BA
0x1800c699b  cmp     [rax+141h], r14b
0x1800c69a2  jnz     short loc_1800C69B5
0x1800c69a4  mov     rcx, [rsp+190h+var_160]; struct IXMLDOMNode *
0x1800c69a9  mov     rdx, rax; struct __MIDL_ICommunityTransport_0006 *
0x1800c69ac  call    ?CommunityXML_VerifyMessageNode@@YAJPEAUIXMLDOMNode@@PEAU__MIDL_ICommunityTransport_0006@@@Z; CommunityXML_VerifyMessageNode(IXMLDOMNode *,__MIDL_ICommunityTransport_0006 *)
0x1800c69b1  mov     ebx, eax
0x1800c69b3  jmp     short loc_1800C69C6
0x1800c69b5  mov     ebx, r14d
0x1800c69b8  jmp     short loc_1800C69C6
0x1800c69ba  mov     ebx, 80004005h
0x1800c69bf  jmp     short loc_1800C69C6
0x1800c69c1  mov     ebx, 8007000Eh
0x1800c69c6  mov     rcx, [rsp+190h+bstrString]; bstrString
0x1800c69cb  call    cs:__imp_SysFreeString
0x1800c69d1  lea     rcx, [rsp+190h+var_160]
0x1800c69d6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c69db  inc     edi
0x1800c69dd  cmp     edi, [rsp+190h+var_158]
0x1800c69e1  jl      loc_1800C68E7
0x1800c69e7  lea     rcx, [rsp+190h+var_140]
0x1800c69ec  jmp     short loc_1800C6A15
0x1800c69ee  mov     rcx, [rsp+190h+var_148]
0x1800c69f3  lea     r8, [rsp+190h+bstrString]
0x1800c69f8  lea     rdx, aMessage; "Message"
0x1800c69ff  mov     [rsp+190h+bstrString], r14
0x1800c6a04  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c6a0a  mov     ebx, eax
0x1800c6a0c  test    eax, eax
0x1800c6a0e  js      short loc_1800C6A1A
0x1800c6a10  lea     rcx, [rsp+190h+bstrString]
0x1800c6a15  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6a1a  lea     rcx, [rsp+190h+var_148]
0x1800c6a1f  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6a24  lea     rcx, [rsp+190h+var_150]
0x1800c6a29  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6a2e  jmp     short loc_1800C6A35
0x1800c6a30  mov     ebx, 80070057h
0x1800c6a35  mov     rcx, [rsp+190h+var_130]; bstrString
0x1800c6a3a  call    cs:__imp_SysFreeString
0x1800c6a40  mov     eax, ebx
0x1800c6a42  jmp     short loc_1800C6A49
0x1800c6a44  mov     eax, 80070057h
0x1800c6a49  mov     rcx, [rbp+90h+var_20]
0x1800c6a4d  xor     rcx, rsp; StackCookie
0x1800c6a50  call    __security_check_cookie
0x1800c6a55  lea     r11, [rsp+190h+var_10]
0x1800c6a5d  mov     rbx, [r11+30h]
0x1800c6a61  mov     rsi, [r11+38h]
0x1800c6a65  mov     rsp, r11
0x1800c6a68  pop     r14
0x1800c6a6a  pop     rdi
0x1800c6a6b  pop     rbp
0x1800c6a6c  retn
```
