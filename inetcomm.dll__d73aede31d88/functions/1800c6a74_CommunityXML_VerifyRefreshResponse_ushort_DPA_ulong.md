# CommunityXML_VerifyRefreshResponse(ushort *,_DPA * *,ulong *)

- ea: `0x1800c6a74`
- end: `0x1800c70f0`
- name: `?CommunityXML_VerifyRefreshResponse@@YAJPEAGPEAPEAU_DPA@@PEAK@Z`
- size: `1660`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _DPA **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800af91c`

## callees

- `0x180002098`
- `0x18002489c`
- `0x1800a4d70`
- `0x1800ad63c`
- `0x1800c6a74`
- `0x1800c9fe8`
- `0x1800cb6a0`
- `0x1800cb6ec`
- `0x1800cb790`
- `0x1800cbb54`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c6ae1`
- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c6ae1`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c6b37`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c6d34`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c6e12`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c6b37`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c6d34`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c6e12`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c6b54`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c6d51`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c6e75`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c6b54`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c6d51`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c6e75`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c6b6a`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c6b6a`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6d73`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6e9b`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6d73`
- `MSOERT2!__imp_XMLNode_GetAttributeValue` at `0x1800c6e9b`
- `SHLWAPI!StrToIntW` at `0x1800c6d84`
- `SHLWAPI!StrToIntW` at `0x1800c6d84`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c6ecb`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800c6ecb`
- `ole32!CoCreateInstance` at `0x1800c6bd9`
- `ole32!CoCreateInstance` at `0x1800c6bd9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6ca1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6d91`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7015`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7092`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6ca1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c6d91`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7015`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c7092`

## pseudocode

```c
__int64 __fastcall CommunityXML_VerifyRefreshResponse(unsigned __int16 *a1, struct _DPA **a2, unsigned int *a3)
{
  unsigned int *v3; // r15
  struct _DPA **v4; // r12
  HRESULT ElementsByTagName; // ebx
  int v6; // eax
  BSTR v7; // r14
  struct _DPA *v8; // rdi
  unsigned int v9; // esi
  PCWSTR v10; // rcx
  LPVOID v11; // rcx
  int v12; // eax
  __int64 (__fastcall *v13)(_QWORD); // rax
  unsigned int v14; // r12d
  char *v15; // r14
  int v16; // eax
  unsigned int (__fastcall *v17)(struct _DPA *, _QWORD, char *); // rax
  unsigned int v18; // r13d
  PCWSTR pszSrc; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  struct _DPA **v26; // [rsp+60h] [rbp-A0h]
  BSTR v27; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v28; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v29; // [rsp+78h] [rbp-88h]
  CHAR pszDst[256]; // [rsp+80h] [rbp-80h] BYREF

  v29 = a3;
  v26 = a2;
  v3 = a3;
  v27 = 0;
  v4 = a2;
  if ( a1 && a2 && a3 )
  {
    v24 = 0;
    ElementsByTagName = XMLDOMFromBStr(a1, &v24);
    if ( ElementsByTagName >= 0 )
    {
      v21 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 360LL))(v24, &v21);
      ElementsByTagName = v6;
      if ( v6 == 1 )
      {
        ElementsByTagName = -2147023728;
      }
      else if ( v6 >= 0 )
      {
        ppv = 0;
        ElementsByTagName = XMLElem_GetElementsByTagName(v21, L"QueryResult", &ppv);
        if ( ElementsByTagName >= 0 )
        {
          pszSrc = 0;
          ElementsByTagName = XMLNodeList_GetChild(ppv, 0, &pszSrc);
          if ( ElementsByTagName >= 0 )
          {
            ElementsByTagName = XMLNode_GetTagText(pszSrc, &v27);
            OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&pszSrc);
          }
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppv);
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v21);
      }
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v24);
    }
    if ( ElementsByTagName < 0 )
      goto LABEL_79;
    v7 = v27;
    v8 = 0;
    ppv = 0;
    v9 = 0;
    if ( !v27 )
    {
      ElementsByTagName = -2147024809;
      goto LABEL_75;
    }
    ElementsByTagName = CoCreateInstance(&CLSID_DOMDocument2, 0, 1u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &ppv);
    if ( ElementsByTagName >= 0 )
    {
      LOWORD(v23) = 0;
      ElementsByTagName = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 520LL))(ppv, v7, &v23);
      if ( ElementsByTagName < 0 )
      {
LABEL_20:
        pszSrc = 0;
        if ( (*(int (__fastcall **)(LPVOID, PCWSTR *))(*(_QWORD *)ppv + 480LL))(ppv, &pszSrc) >= 0 )
        {
          bstrString = 0;
          if ( (*(int (__fastcall **)(PCWSTR, BSTR *))(*(_QWORD *)pszSrc + 72LL))(pszSrc, &bstrString) >= 0 )
          {
            LODWORD(v24) = 0;
            LODWORD(v21) = 0;
            (*(void (__fastcall **)(PCWSTR, __int64 *))(*(_QWORD *)pszSrc + 88LL))(pszSrc, &v24);
            (*(void (__fastcall **)(PCWSTR, __int64 *))(*(_QWORD *)pszSrc + 96LL))(pszSrc, &v21);
            SysFreeString(bstrString);
          }
          v10 = pszSrc;
          if ( pszSrc )
          {
            pszSrc = 0;
            (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)v10 + 16LL))(v10);
          }
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppv);
        v11 = 0;
        ppv = 0;
LABEL_27:
        if ( ElementsByTagName < 0 )
        {
LABEL_75:
          SysFreeString(v27);
          if ( ElementsByTagName >= 0 )
          {
            *v4 = v8;
LABEL_80:
            *v3 = v9;
            return (unsigned int)ElementsByTagName;
          }
          if ( v8 )
          {
            DPA_DeleteAllPtrs(v8);
            DPA_Destroy(v8);
          }
LABEL_79:
          v9 = 0;
          goto LABEL_80;
        }
        v24 = 0;
        v12 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v11 + 360LL))(v11, &v24);
        ElementsByTagName = v12;
        if ( v12 == 1 )
        {
          ElementsByTagName = -2147023728;
LABEL_73:
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppv);
          goto LABEL_75;
        }
        if ( v12 < 0 )
          goto LABEL_73;
        if ( v24 )
        {
          v23 = 0;
          ElementsByTagName = XMLElem_GetElementsByTagName(v24, L"Message1", &v23);
          if ( ElementsByTagName >= 0 )
          {
            v21 = 0;
            ElementsByTagName = XMLNodeList_GetChild(v23, 0, &v21);
            if ( ElementsByTagName >= 0 )
            {
              pszSrc = 0;
              ElementsByTagName = XMLNode_GetAttributeValue(v21, L"MsgCountTotal", &pszSrc);
              if ( ElementsByTagName >= 0 )
              {
                v9 = StrToIntW(pszSrc);
                SysFreeString((BSTR)pszSrc);
              }
              OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v21);
            }
            OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v23);
          }
          if ( ElementsByTagName >= 0 && v9 )
          {
            v13 = (__int64 (__fastcall *)(_QWORD))qword_1800F2348;
            if ( qword_1800F2348 == -1 )
            {
              GetProcFromComCtl32(&qword_1800F2348, 328);
              v13 = (__int64 (__fastcall *)(_QWORD))qword_1800F2348;
            }
            if ( v13 && (v8 = (struct _DPA *)v13(v9)) != 0 )
            {
              v21 = 0;
              ElementsByTagName = XMLElem_GetElementsByTagName(v24, L"Message", &v21);
              if ( ElementsByTagName >= 0 )
              {
                LODWORD(v23) = 0;
                ElementsByTagName = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 64LL))(v21, &v23);
                if ( ElementsByTagName >= 0 )
                {
                  v14 = 0;
                  if ( (int)v23 > 0 )
                  {
                    while ( 1 )
                    {
                      if ( ElementsByTagName < 0 )
                        goto LABEL_66;
                      pszSrc = 0;
                      ElementsByTagName = XMLNodeList_GetChild(v21, v14, &pszSrc);
                      if ( ElementsByTagName >= 0 )
                        break;
LABEL_65:
                      if ( (int)++v14 >= (int)v23 )
                        goto LABEL_66;
                    }
                    bstrString = 0;
                    ElementsByTagName = XMLNode_GetAttributeValue(pszSrc, L"ExternalID", &bstrString);
                    if ( ElementsByTagName < 0 )
                    {
LABEL_64:
                      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&pszSrc);
                      goto LABEL_65;
                    }
                    memset_0(pszDst, 0, 0xFFu);
                    if ( SHUnicodeToAnsi(bstrString, pszDst, 255) )
                    {
                      if ( DPA_Search(v8, pszDst, 1, DPACompare, 0, 0) != -1 )
                      {
                        ElementsByTagName = 0;
                        goto LABEL_63;
                      }
                      v15 = (char *)ZeroAllocate(0x144u);
                      if ( v15 )
                      {
                        v28 = 0;
                        ElementsByTagName = StringCchLengthA(pszDst, 0xFFu, &v28);
                        if ( ElementsByTagName < 0
                          || (ElementsByTagName = StringCchCopyNA(v15, 0x100u, pszDst, v28), ElementsByTagName < 0) )
                        {
                          ((void (__fastcall *)(LPMALLOC, char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v15);
                          goto LABEL_63;
                        }
                        *((_DWORD *)v15 + 64) = 5;
                        *(_QWORD *)(v15 + 260) = 5;
                        v16 = 2;
                        *((GUID *)v15 + 17) = GUID_NULL;
                        *((GUID *)v15 + 18) = GUID_NULL;
                        *((GUID *)v15 + 19) = GUID_NULL;
                        *((_WORD *)v15 + 160) = 0;
                        do
                          --v16;
                        while ( v16 );
                        ElementsByTagName = CommunityXML_VerifyRefreshNode(
                                              (struct IXMLDOMNode *)pszSrc,
                                              (struct __MIDL_ICommunityTransport_0006 *)v15);
                        if ( ElementsByTagName < 0 )
                          goto LABEL_63;
                        v17 = (unsigned int (__fastcall *)(struct _DPA *, _QWORD, char *))qword_1800F2330;
                        v18 = *(_DWORD *)v8;
                        if ( qword_1800F2330 == -1 )
                        {
                          GetProcFromComCtl32(&qword_1800F2330, 334);
                          v17 = (unsigned int (__fastcall *)(struct _DPA *, _QWORD, char *))qword_1800F2330;
                        }
                        if ( v17 && v17(v8, v18, v15) != -1 )
                          goto LABEL_63;
                      }
                    }
                    ElementsByTagName = -2147024882;
LABEL_63:
                    SysFreeString(bstrString);
                    goto LABEL_64;
                  }
LABEL_66:
                  v4 = v26;
                }
                OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v21);
              }
            }
            else
            {
              ElementsByTagName = -2147024882;
            }
          }
        }
        else
        {
          ElementsByTagName = -2147024809;
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v24);
        v3 = v29;
        goto LABEL_73;
      }
      if ( (_WORD)v23 != 0xFFFF )
      {
        ElementsByTagName = -2147467259;
        goto LABEL_20;
      }
    }
    v11 = ppv;
    goto LABEL_27;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800c6a74  mov     [rsp-8+arg_18], rbx
0x1800c6a79  push    rbp
0x1800c6a7a  push    rsi
0x1800c6a7b  push    rdi
0x1800c6a7c  push    r12
0x1800c6a7e  push    r13
0x1800c6a80  push    r14
0x1800c6a82  push    r15
0x1800c6a84  lea     rbp, [rsp-90h]
0x1800c6a8c  sub     rsp, 190h
0x1800c6a93  mov     rax, cs:__security_cookie
0x1800c6a9a  xor     rax, rsp
0x1800c6a9d  mov     [rbp+0C0h+var_40], rax
0x1800c6aa4  xor     r13d, r13d
0x1800c6aa7  mov     [rsp+1C0h+var_148], r8
0x1800c6aac  mov     [rsp+1C0h+var_160], rdx
0x1800c6ab1  mov     r15, r8
0x1800c6ab4  mov     [rsp+1C0h+var_158], r13
0x1800c6ab9  mov     r12, rdx
0x1800c6abc  test    rcx, rcx
0x1800c6abf  jz      loc_1800C70C1
0x1800c6ac5  test    rdx, rdx
0x1800c6ac8  jz      loc_1800C70C1
0x1800c6ace  test    r8, r8
0x1800c6ad1  jz      loc_1800C70C1
0x1800c6ad7  lea     rdx, [rsp+1C0h+var_170]
0x1800c6adc  mov     [rsp+1C0h+var_170], r13
0x1800c6ae1  call    cs:__imp_XMLDOMFromBStr
0x1800c6ae7  mov     ebx, eax
0x1800c6ae9  test    eax, eax
0x1800c6aeb  js      loc_1800C6B9A
0x1800c6af1  mov     rcx, [rsp+1C0h+var_170]
0x1800c6af6  lea     rdx, [rsp+1C0h+var_188]
0x1800c6afb  mov     [rsp+1C0h+var_188], r13
0x1800c6b00  mov     rax, [rcx]
0x1800c6b03  mov     rax, [rax+168h]
0x1800c6b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6b0f  mov     ebx, eax
0x1800c6b11  cmp     eax, 1
0x1800c6b14  jnz     short loc_1800C6B1D
0x1800c6b16  mov     ebx, 80070490h
0x1800c6b1b  jmp     short loc_1800C6B90
0x1800c6b1d  test    eax, eax
0x1800c6b1f  js      short loc_1800C6B90
0x1800c6b21  mov     rcx, [rsp+1C0h+var_188]
0x1800c6b26  lea     r8, [rsp+1C0h+var_180]
0x1800c6b2b  lea     rdx, aQueryresult; "QueryResult"
0x1800c6b32  mov     [rsp+1C0h+var_180], r13
0x1800c6b37  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c6b3d  mov     ebx, eax
0x1800c6b3f  test    eax, eax
0x1800c6b41  js      short loc_1800C6B86
0x1800c6b43  mov     rcx, [rsp+1C0h+var_180]
0x1800c6b48  lea     r8, [rsp+1C0h+pszSrc]
0x1800c6b4d  xor     edx, edx
0x1800c6b4f  mov     [rsp+1C0h+pszSrc], r13
0x1800c6b54  call    cs:__imp_XMLNodeList_GetChild
0x1800c6b5a  mov     ebx, eax
0x1800c6b5c  test    eax, eax
0x1800c6b5e  js      short loc_1800C6B7C
0x1800c6b60  mov     rcx, [rsp+1C0h+pszSrc]
0x1800c6b65  lea     rdx, [rsp+1C0h+var_158]
0x1800c6b6a  call    cs:__imp_XMLNode_GetTagText
0x1800c6b70  lea     rcx, [rsp+1C0h+pszSrc]
0x1800c6b75  mov     ebx, eax
0x1800c6b77  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6b7c  lea     rcx, [rsp+1C0h+var_180]
0x1800c6b81  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6b86  lea     rcx, [rsp+1C0h+var_188]
0x1800c6b8b  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6b90  lea     rcx, [rsp+1C0h+var_170]
0x1800c6b95  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6b9a  test    ebx, ebx
0x1800c6b9c  js      loc_1800C70B7
0x1800c6ba2  mov     r14, [rsp+1C0h+var_158]
0x1800c6ba7  mov     rdi, r13
0x1800c6baa  mov     [rsp+1C0h+var_180], r13
0x1800c6baf  mov     esi, r13d
0x1800c6bb2  test    r14, r14
0x1800c6bb5  jz      loc_1800C7088
0x1800c6bbb  xor     edx, edx; pUnkOuter
0x1800c6bbd  lea     rax, [rsp+1C0h+var_180]
0x1800c6bc2  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1800c6bc9  mov     [rsp+1C0h+ppv], rax; ppv
0x1800c6bce  lea     rcx, CLSID_DOMDocument2; rclsid
0x1800c6bd5  lea     r8d, [rdx+1]; dwClsContext
0x1800c6bd9  call    cs:__imp_CoCreateInstance
0x1800c6bdf  mov     ebx, eax
0x1800c6be1  test    eax, eax
0x1800c6be3  js      loc_1800C6CD6
0x1800c6be9  mov     rcx, [rsp+1C0h+var_180]
0x1800c6bee  lea     r8, [rsp+1C0h+var_178]
0x1800c6bf3  mov     word ptr [rsp+1C0h+var_178], r13w
0x1800c6bf9  mov     rdx, r14
0x1800c6bfc  mov     rax, [rcx]
0x1800c6bff  mov     rax, [rax+208h]
0x1800c6c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c0b  mov     ebx, eax
0x1800c6c0d  test    eax, eax
0x1800c6c0f  js      short loc_1800C6C25
0x1800c6c11  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c6c15  cmp     ax, word ptr [rsp+1C0h+var_178]
0x1800c6c1a  jz      loc_1800C6CD6
0x1800c6c20  mov     ebx, 80004005h
0x1800c6c25  mov     rcx, [rsp+1C0h+var_180]
0x1800c6c2a  lea     rdx, [rsp+1C0h+pszSrc]
0x1800c6c2f  mov     [rsp+1C0h+pszSrc], r13
0x1800c6c34  mov     rax, [rcx]
0x1800c6c37  mov     rax, [rax+1E0h]
0x1800c6c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c43  test    eax, eax
0x1800c6c45  js      short loc_1800C6CC2
0x1800c6c47  mov     rcx, [rsp+1C0h+pszSrc]
0x1800c6c4c  lea     rdx, [rsp+1C0h+bstrString]
0x1800c6c51  mov     [rsp+1C0h+bstrString], r13
0x1800c6c56  mov     rax, [rcx]
0x1800c6c59  mov     rax, [rax+48h]
0x1800c6c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c62  test    eax, eax
0x1800c6c64  js      short loc_1800C6CA7
0x1800c6c66  mov     rcx, [rsp+1C0h+pszSrc]
0x1800c6c6b  lea     rdx, [rsp+1C0h+var_170]
0x1800c6c70  mov     dword ptr [rsp+1C0h+var_170], r13d
0x1800c6c75  mov     dword ptr [rsp+1C0h+var_188], r13d
0x1800c6c7a  mov     rax, [rcx]
0x1800c6c7d  mov     rax, [rax+58h]
0x1800c6c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c86  mov     rcx, [rsp+1C0h+pszSrc]
0x1800c6c8b  lea     rdx, [rsp+1C0h+var_188]
0x1800c6c90  mov     rax, [rcx]
0x1800c6c93  mov     rax, [rax+60h]
0x1800c6c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c9c  mov     rcx, [rsp+1C0h+bstrString]; bstrString
0x1800c6ca1  call    cs:__imp_SysFreeString
0x1800c6ca7  mov     rcx, [rsp+1C0h+pszSrc]
0x1800c6cac  test    rcx, rcx
0x1800c6caf  jz      short loc_1800C6CC2
0x1800c6cb1  mov     [rsp+1C0h+pszSrc], r13
0x1800c6cb6  mov     rax, [rcx]
0x1800c6cb9  mov     rax, [rax+10h]
0x1800c6cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6cc2  lea     rcx, [rsp+1C0h+var_180]
0x1800c6cc7  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6ccc  mov     rcx, r13
0x1800c6ccf  mov     [rsp+1C0h+var_180], rcx
0x1800c6cd4  jmp     short loc_1800C6CDB
0x1800c6cd6  mov     rcx, [rsp+1C0h+var_180]
0x1800c6cdb  test    ebx, ebx
0x1800c6cdd  js      loc_1800C708D
0x1800c6ce3  mov     [rsp+1C0h+var_170], r13
0x1800c6ce8  lea     rdx, [rsp+1C0h+var_170]
0x1800c6ced  mov     rax, [rcx]
0x1800c6cf0  mov     rax, [rax+168h]
0x1800c6cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6cfc  mov     ebx, eax
0x1800c6cfe  cmp     eax, 1
0x1800c6d01  jnz     short loc_1800C6D0D
0x1800c6d03  mov     ebx, 80070490h
0x1800c6d08  jmp     loc_1800C707C
0x1800c6d0d  test    eax, eax
0x1800c6d0f  js      loc_1800C707C
0x1800c6d15  mov     rcx, [rsp+1C0h+var_170]
0x1800c6d1a  test    rcx, rcx
0x1800c6d1d  jz      loc_1800C7068
0x1800c6d23  lea     r8, [rsp+1C0h+var_178]
0x1800c6d28  mov     [rsp+1C0h+var_178], r13
0x1800c6d2d  lea     rdx, aMessage1; "Message1"
0x1800c6d34  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c6d3a  mov     ebx, eax
0x1800c6d3c  test    eax, eax
0x1800c6d3e  js      short loc_1800C6DAB
0x1800c6d40  mov     rcx, [rsp+1C0h+var_178]
0x1800c6d45  lea     r8, [rsp+1C0h+var_188]
0x1800c6d4a  xor     edx, edx
0x1800c6d4c  mov     [rsp+1C0h+var_188], r13
0x1800c6d51  call    cs:__imp_XMLNodeList_GetChild
0x1800c6d57  mov     ebx, eax
0x1800c6d59  test    eax, eax
0x1800c6d5b  js      short loc_1800C6DA1
0x1800c6d5d  mov     rcx, [rsp+1C0h+var_188]
0x1800c6d62  lea     r8, [rsp+1C0h+pszSrc]
0x1800c6d67  lea     rdx, aMsgcounttotal; "MsgCountTotal"
0x1800c6d6e  mov     [rsp+1C0h+pszSrc], r13
0x1800c6d73  call    cs:__imp_XMLNode_GetAttributeValue
0x1800c6d79  mov     ebx, eax
0x1800c6d7b  test    eax, eax
0x1800c6d7d  js      short loc_1800C6D97
0x1800c6d7f  mov     rcx, [rsp+1C0h+pszSrc]; pszSrc
0x1800c6d84  call    cs:__imp_StrToIntW
0x1800c6d8a  mov     rcx, [rsp+1C0h+pszSrc]; bstrString
0x1800c6d8f  mov     esi, eax
0x1800c6d91  call    cs:__imp_SysFreeString
0x1800c6d97  lea     rcx, [rsp+1C0h+var_188]
0x1800c6d9c  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6da1  lea     rcx, [rsp+1C0h+var_178]
0x1800c6da6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c6dab  test    ebx, ebx
0x1800c6dad  js      loc_1800C706D
0x1800c6db3  test    esi, esi
0x1800c6db5  jz      loc_1800C706D
0x1800c6dbb  mov     rax, cs:qword_1800F2348
0x1800c6dc2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c6dc6  jnz     short loc_1800C6DE0
0x1800c6dc8  mov     edx, 148h
0x1800c6dcd  lea     rcx, qword_1800F2348
0x1800c6dd4  call    _GetProcFromComCtl32
0x1800c6dd9  mov     rax, cs:qword_1800F2348
0x1800c6de0  test    rax, rax
0x1800c6de3  jz      loc_1800C7061
0x1800c6de9  mov     ecx, esi
0x1800c6deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6df0  mov     rdi, rax
0x1800c6df3  test    rax, rax
0x1800c6df6  jz      loc_1800C7061
0x1800c6dfc  mov     rcx, [rsp+1C0h+var_170]
0x1800c6e01  lea     r8, [rsp+1C0h+var_188]
0x1800c6e06  lea     rdx, aMessage; "Message"
0x1800c6e0d  mov     [rsp+1C0h+var_188], r13
0x1800c6e12  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c6e18  mov     ebx, eax
0x1800c6e1a  test    eax, eax
0x1800c6e1c  js      loc_1800C706D
0x1800c6e22  mov     rcx, [rsp+1C0h+var_188]
0x1800c6e27  lea     rdx, [rsp+1C0h+var_178]
0x1800c6e2c  mov     dword ptr [rsp+1C0h+var_178], r13d
0x1800c6e31  mov     rax, [rcx]
0x1800c6e34  mov     rax, [rax+40h]
0x1800c6e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e3d  mov     ebx, eax
0x1800c6e3f  test    eax, eax
0x1800c6e41  js      loc_1800C7038
0x1800c6e47  mov     r12d, r13d
0x1800c6e4a  cmp     dword ptr [rsp+1C0h+var_178], r13d
0x1800c6e4f  jle     loc_1800C7033
0x1800c6e55  mov     r15d, 8007000Eh
0x1800c6e5b  test    ebx, ebx
0x1800c6e5d  js      loc_1800C7033
0x1800c6e63  mov     rcx, [rsp+1C0h+var_188]
0x1800c6e68  lea     r8, [rsp+1C0h+pszSrc]
0x1800c6e6d  mov     edx, r12d
0x1800c6e70  mov     [rsp+1C0h+pszSrc], r13
0x1800c6e75  call    cs:__imp_XMLNodeList_GetChild
0x1800c6e7b  mov     ebx, eax
0x1800c6e7d  test    eax, eax
0x1800c6e7f  js      loc_1800C7025
0x1800c6e85  mov     rcx, [rsp+1C0h+pszSrc]
0x1800c6e8a  lea     r8, [rsp+1C0h+bstrString]
0x1800c6e8f  lea     rdx, aExternalid; "ExternalID"
0x1800c6e96  mov     [rsp+1C0h+bstrString], r13
0x1800c6e9b  call    cs:__imp_XMLNode_GetAttributeValue
0x1800c6ea1  mov     ebx, eax
0x1800c6ea3  test    eax, eax
0x1800c6ea5  js      loc_1800C701B
0x1800c6eab  xor     edx, edx; Val
0x1800c6ead  lea     rcx, [rbp+0C0h+pszDst]; void *
0x1800c6eb1  mov     r8d, 0FFh; Size
0x1800c6eb7  call    memset_0
0x1800c6ebc  mov     rcx, [rsp+1C0h+bstrString]; pwszSrc
0x1800c6ec1  lea     rdx, [rbp+0C0h+pszDst]; pszDst
0x1800c6ec5  mov     r8d, 0FFh; cchBuf
0x1800c6ecb  call    cs:__imp_SHUnicodeToAnsi
0x1800c6ed1  test    eax, eax
0x1800c6ed3  jz      loc_1800C700D
0x1800c6ed9  mov     [rsp+1C0h+options], r13d; options
0x1800c6ede  lea     r9, ?DPACompare@@YAHPEAX0_J@Z; pfnCompare
0x1800c6ee5  mov     r8d, 1; iStart
0x1800c6eeb  mov     [rsp+1C0h+ppv], r13; lParam
0x1800c6ef0  lea     rdx, [rbp+0C0h+pszDst]; pFind
0x1800c6ef4  mov     rcx, rdi; hdpa
0x1800c6ef7  call    DPA_Search
0x1800c6efc  cmp     eax, 0FFFFFFFFh
0x1800c6eff  jnz     loc_1800C705C
0x1800c6f05  mov     ecx, 144h; Size
0x1800c6f0a  call    ?ZeroAllocate@@YAPEAXK@Z; ZeroAllocate(ulong)
0x1800c6f0f  mov     r14, rax
0x1800c6f12  test    rax, rax
0x1800c6f15  jz      loc_1800C700D
0x1800c6f1b  lea     r8, [rsp+1C0h+var_150]; unsigned __int64 *
0x1800c6f20  mov     [rsp+1C0h+var_150], r13
0x1800c6f25  mov     edx, 0FFh; unsigned __int64
0x1800c6f2a  lea     rcx, [rbp+0C0h+pszDst]; char *
0x1800c6f2e  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800c6f33  mov     ebx, eax
0x1800c6f35  test    eax, eax
0x1800c6f37  js      loc_1800C7044
0x1800c6f3d  mov     r9, [rsp+1C0h+var_150]; unsigned __int64
0x1800c6f42  lea     r8, [rbp+0C0h+pszDst]; char *
0x1800c6f46  mov     edx, 100h; unsigned __int64
0x1800c6f4b  mov     rcx, r14; char *
0x1800c6f4e  call    ?StringCchCopyNA@@YAJPEAD_KPEBD1@Z; StringCchCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x1800c6f53  mov     ebx, eax
0x1800c6f55  test    eax, eax
0x1800c6f57  js      loc_1800C7044
0x1800c6f5d  mov     eax, 5
0x1800c6f62  mov     [r14+100h], eax
0x1800c6f69  mov     [r14+104h], rax
0x1800c6f70  mov     eax, 2
0x1800c6f75  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800c6f7c  movdqu  xmmword ptr [r14+110h], xmm0
0x1800c6f85  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
  ... truncated ...
```
