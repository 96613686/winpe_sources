# CommunityXML_ParseSOAPFault(ushort *,tagCOMMUNITIESREQUEST,__MIDL_ICommunityTransport_0001,ushort const *,ushort * *)

- ea: `0x1800c57d4`
- end: `0x1800c5ddb`
- name: `?CommunityXML_ParseSOAPFault@@YAJPEAGW4tagCOMMUNITIESREQUEST@@W4__MIDL_ICommunityTransport_0001@@PEBGPEAPEAG@Z`
- size: `1543`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b0bb0`

## callees

- `0x180002098`
- `0x1800055bc`
- `0x18000910c`
- `0x18004bba4`
- `0x1800c57d4`
- `0x1800c9fe8`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cca90`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c5a07`
- `MSOERT2!__imp_XMLDOMFromBStr` at `0x1800c5a07`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c5a64`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c5b56`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c5a64`
- `MSOERT2!__imp_XMLElem_GetElementsByTagName` at `0x1800c5b56`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c5a85`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c5b73`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c5a85`
- `MSOERT2!__imp_XMLNodeList_GetChild` at `0x1800c5b73`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c5b8e`
- `MSOERT2!__imp_XMLNode_GetTagText` at `0x1800c5b8e`
- `MSOERT2!__imp_XMLNode_GetChildTagTextValue` at `0x1800c5aab`
- `MSOERT2!__imp_XMLNode_GetChildTagTextValue` at `0x1800c5af2`
- `MSOERT2!__imp_XMLNode_GetChildTagTextValue` at `0x1800c5aab`
- `MSOERT2!__imp_XMLNode_GetChildTagTextValue` at `0x1800c5af2`
- `USER32!LoadStringW` at `0x1800c593e`
- `USER32!LoadStringW` at `0x1800c59cb`
- `USER32!LoadStringW` at `0x1800c5c05`
- `USER32!LoadStringW` at `0x1800c593e`
- `USER32!LoadStringW` at `0x1800c59cb`
- `USER32!LoadStringW` at `0x1800c5c05`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5ad2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5b19`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5bb5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5ad2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5b19`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5bb5`

## string_xrefs

- `0x1800c58dd`: `GetUsernameTokenResult`
- `0x1800c5971`: `GetContribIDFromSIDResult`
- `0x1800c597a`: `UpdateResult`
- `0x1800c5996`: `UpdateMsgAttributeResult`
- `0x1800c5988`: `UpdateMsgRatingResult`

## pseudocode

```c
__int64 __fastcall CommunityXML_ParseSOAPFault(__int64 a1, int a2, int a3, __int64 a4, unsigned __int16 **a5)
{
  const wchar_t *v9; // rsi
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  UINT v17; // ebx
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  int v22; // edi
  UINT v23; // eax
  int ElementsByTagName; // ebx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rsi
  __int64 v28; // rdi
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // r15d
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // r14
  unsigned __int64 v34; // r11
  __int64 v36; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  BSTR v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[512]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v43[512]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v44[512]; // [rsp+860h] [rbp+760h] BYREF
  unsigned __int16 v45[512]; // [rsp+C60h] [rbp+B60h] BYREF
  unsigned __int16 v46[512]; // [rsp+1060h] [rbp+F60h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v44, 0, sizeof(v44));
  memset_0(v45, 0, sizeof(v45));
  memset_0(v43, 0, sizeof(v43));
  memset_0(v46, 0, sizeof(v46));
  if ( a1 && a4 && a5 )
  {
    v9 = 0;
    v10 = a2 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( !v12 )
        {
          v9 = L"UpdateMsgAttributeResult";
          v17 = 1326;
          goto LABEL_34;
        }
        v13 = v12 - 1;
        if ( !v13 )
        {
          v9 = L"UpdateMsgRatingResult";
          v17 = 1325;
          goto LABEL_34;
        }
        v14 = v13 - 1;
        if ( !v14 )
        {
          v9 = L"UpdateResult";
          v17 = 1327;
          goto LABEL_34;
        }
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            if ( v16 != 1 )
              goto LABEL_36;
            v9 = L"GetUsernameTokenResult";
            v17 = 1329;
            v18 = a3 - 1;
            if ( v18 && (v19 = v18 - 1) != 0 )
            {
              v20 = v19 - 1;
              if ( v20 )
              {
                v21 = v20 - 2;
                if ( v21 )
                {
                  v22 = v21 - 1;
                  if ( v22 )
                  {
                    if ( v22 == 1 )
                    {
                      v23 = 1328;
                      goto LABEL_23;
                    }
LABEL_34:
                    if ( LoadStringW(g_hLocRes, v17, Buffer, 512) )
                      StringCchPrintfW(v45, 0x200u, Buffer, a4);
LABEL_36:
                    v41 = 0;
                    ElementsByTagName = XMLDOMFromBStr(a1, &v41);
                    if ( ElementsByTagName < 0 )
                      return (unsigned int)ElementsByTagName;
                    v39 = 0;
                    v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 360LL))(v41, &v39);
                    ElementsByTagName = v25;
                    if ( v25 == 1 )
                    {
                      ElementsByTagName = -2147023728;
                    }
                    else if ( v25 >= 0 )
                    {
                      v40 = 0;
                      ElementsByTagName = XMLElem_GetElementsByTagName(v39, L"soap:Fault", &v40);
                      if ( ElementsByTagName < 0 )
                        goto LABEL_89;
                      v36 = 0;
                      ElementsByTagName = XMLNodeList_GetChild(v40, 0, &v36);
                      if ( ElementsByTagName >= 0 )
                      {
                        bstrString = 0;
                        ElementsByTagName = XMLNode_GetChildTagTextValue(v36, L"faultcode", &bstrString);
                        if ( ElementsByTagName >= 0 )
                        {
                          ElementsByTagName = StringCchCopyW(v43, 0x200u, bstrString);
                          SysFreeString(bstrString);
                          if ( ElementsByTagName >= 0 )
                          {
                            v38 = 0;
                            ElementsByTagName = XMLNode_GetChildTagTextValue(v36, L"faultstring", &v38);
                            if ( ElementsByTagName >= 0 )
                            {
                              ElementsByTagName = StringCchCopyW(v46, 0x200u, v38);
                              SysFreeString(v38);
                            }
                          }
                        }
                        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v36);
                      }
                      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v40);
                      if ( ElementsByTagName < 0 )
                      {
LABEL_89:
                        if ( v9 )
                        {
                          v36 = 0;
                          ElementsByTagName = XMLElem_GetElementsByTagName(v39, v9, &v36);
                          if ( ElementsByTagName >= 0 )
                          {
                            bstrString = 0;
                            ElementsByTagName = XMLNodeList_GetChild(v36, 0, &bstrString);
                            if ( ElementsByTagName >= 0 )
                            {
                              v38 = 0;
                              ElementsByTagName = XMLNode_GetTagText(bstrString, &v38);
                              if ( ElementsByTagName >= 0 )
                              {
                                ElementsByTagName = StringCchCopyW(v46, 0x200u, v38);
                                SysFreeString(v38);
                              }
                              OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&bstrString);
                            }
                            OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v36);
                          }
                        }
                      }
                      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v39);
                    }
                    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v41);
                    if ( ElementsByTagName < 0 )
                      return (unsigned int)ElementsByTagName;
                    Buffer[0] = 0;
                    if ( !LoadStringW(g_hLocRes, 0x51Cu, Buffer, 512) )
                      return (unsigned int)-2147024882;
                    if ( !v43[0] )
                      StringCchCopyW(v43, 0x200u, L"General");
                    v26 = -1;
                    LODWORD(v27) = 0;
                    if ( v44[0] )
                    {
                      v27 = -1;
                      do
                        ++v27;
                      while ( v44[v27] );
                    }
                    LODWORD(v28) = 0;
                    if ( v45[0] )
                    {
                      v28 = -1;
                      do
                        ++v28;
                      while ( v45[v28] );
                    }
                    v29 = -1;
                    do
                      ++v29;
                    while ( Buffer[v29] );
                    v30 = -1;
                    do
                      ++v30;
                    while ( v43[v30] );
                    do
                      ++v26;
                    while ( v46[v26] );
                    v31 = v27 + v26 + 1 + v29 + v28 + v30;
                    v32 = (unsigned __int16 *)ZeroAllocate((unsigned int)(2 * v31));
                    v33 = v32;
                    if ( v32 )
                    {
                      if ( (_DWORD)v27 )
                      {
                        ElementsByTagName = StringCchCopyW(v32, v31, v44);
                        if ( ElementsByTagName >= 0 )
                        {
                          ElementsByTagName = StringCchCatW(v33, v34, L" ");
                          if ( ElementsByTagName >= 0 )
                            LODWORD(v27) = v27 + 1;
                        }
                      }
                      if ( (_DWORD)v28 )
                      {
                        ElementsByTagName = StringCchCatW(v33, v31, v45);
                        if ( ElementsByTagName < 0 )
                          return (unsigned int)ElementsByTagName;
                        ElementsByTagName = StringCchCatW(v33, v31, L" ");
                        if ( ElementsByTagName < 0 )
                          return (unsigned int)ElementsByTagName;
                        LODWORD(v28) = v28 + 1;
                        goto LABEL_81;
                      }
                      if ( ElementsByTagName >= 0 )
                      {
LABEL_81:
                        ElementsByTagName = StringCchPrintfW(
                                              &v33[(int)v27 + (__int64)(int)v28],
                                              v31 - (int)v28 - (int)v27,
                                              Buffer,
                                              v43,
                                              v46);
                        if ( ElementsByTagName < 0 )
                          ((void (__fastcall *)(LPMALLOC, unsigned __int16 *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v33);
                        else
                          *a5 = v33;
                      }
                    }
                    else
                    {
                      return (unsigned int)-2147024882;
                    }
                    return (unsigned int)ElementsByTagName;
                  }
                  v23 = 1325;
                }
                else
                {
                  v23 = 1327;
                }
              }
              else
              {
                v23 = 1324;
              }
            }
            else
            {
              v23 = 1323;
            }
LABEL_23:
            if ( LoadStringW(g_hLocRes, v23, Buffer, 512) )
              StringCchPrintfW(v44, 0x200u, Buffer, a4);
            goto LABEL_34;
          }
          v9 = L"IsInRoleResult";
        }
        else
        {
          v9 = L"GetContribIDFromSIDResult";
        }
        v17 = 1328;
        goto LABEL_34;
      }
      v17 = 1324;
    }
    else
    {
      v17 = 1323;
    }
    v9 = L"QueryResult";
    goto LABEL_34;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800c57d4  mov     [rsp-8+arg_8], rbx
0x1800c57d9  push    rbp
0x1800c57da  push    rsi
0x1800c57db  push    rdi
0x1800c57dc  push    r12
0x1800c57de  push    r13
0x1800c57e0  push    r14
0x1800c57e2  push    r15
0x1800c57e4  lea     rbp, [rsp-1370h]
0x1800c57ec  mov     eax, 1470h
0x1800c57f1  call    _alloca_probe
0x1800c57f6  sub     rsp, rax
0x1800c57f9  mov     rax, cs:__security_cookie
0x1800c5800  xor     rax, rsp
0x1800c5803  mov     [rbp+13A0h+var_40], rax
0x1800c580a  mov     r13, [rbp+13A0h+arg_20]
0x1800c5811  mov     edi, r8d
0x1800c5814  mov     ebx, edx
0x1800c5816  mov     r15, rcx
0x1800c5819  mov     esi, 400h
0x1800c581e  lea     rcx, [rsp+14A0h+Buffer]; void *
0x1800c5823  mov     r8d, esi; Size
0x1800c5826  xor     edx, edx; Val
0x1800c5828  mov     r14, r9
0x1800c582b  call    memset_0
0x1800c5830  mov     r8d, esi; Size
0x1800c5833  lea     rcx, [rbp+13A0h+var_C40]; void *
0x1800c583a  xor     edx, edx; Val
0x1800c583c  call    memset_0
0x1800c5841  mov     r8d, esi; Size
0x1800c5844  lea     rcx, [rbp+13A0h+var_840]; void *
0x1800c584b  xor     edx, edx; Val
0x1800c584d  call    memset_0
0x1800c5852  mov     r8d, esi; Size
0x1800c5855  lea     rcx, [rbp+13A0h+var_1040]; void *
0x1800c585c  xor     edx, edx; Val
0x1800c585e  call    memset_0
0x1800c5863  mov     r8d, esi; Size
0x1800c5866  lea     rcx, [rbp+13A0h+var_440]; void *
0x1800c586d  xor     edx, edx; Val
0x1800c586f  call    memset_0
0x1800c5874  xor     r12d, r12d
0x1800c5877  test    r15, r15
0x1800c587a  jz      loc_1800C5DAC
0x1800c5880  test    r14, r14
0x1800c5883  jz      loc_1800C5DAC
0x1800c5889  test    r13, r13
0x1800c588c  jz      loc_1800C5DAC
0x1800c5892  mov     esi, r12d
0x1800c5895  sub     ebx, 1
0x1800c5898  jz      loc_1800C59AB
0x1800c589e  sub     ebx, 1
0x1800c58a1  jz      loc_1800C59A4
0x1800c58a7  sub     ebx, 1
0x1800c58aa  jz      loc_1800C5996
0x1800c58b0  sub     ebx, 1
0x1800c58b3  jz      loc_1800C5988
0x1800c58b9  sub     ebx, 1
0x1800c58bc  jz      loc_1800C597A
0x1800c58c2  sub     ebx, 1
0x1800c58c5  jz      loc_1800C5971
0x1800c58cb  sub     ebx, 1
0x1800c58ce  jz      loc_1800C5963
0x1800c58d4  cmp     ebx, 1
0x1800c58d7  jnz     loc_1800C59F4
0x1800c58dd  lea     rsi, aGetusernametok; "GetUsernameTokenResult"
0x1800c58e4  mov     ebx, 531h
0x1800c58e9  sub     edi, 1
0x1800c58ec  jz      short loc_1800C5925
0x1800c58ee  sub     edi, 1
0x1800c58f1  jz      short loc_1800C5925
0x1800c58f3  sub     edi, 1
0x1800c58f6  jz      short loc_1800C591E
0x1800c58f8  sub     edi, 2
0x1800c58fb  jz      short loc_1800C5917
0x1800c58fd  sub     edi, 1
0x1800c5900  jz      short loc_1800C5910
0x1800c5902  cmp     edi, 1
0x1800c5905  jnz     loc_1800C59B7
0x1800c590b  lea     eax, [rbx-1]
0x1800c590e  jmp     short loc_1800C592A
0x1800c5910  mov     eax, 52Dh
0x1800c5915  jmp     short loc_1800C592A
0x1800c5917  mov     eax, 52Fh
0x1800c591c  jmp     short loc_1800C592A
0x1800c591e  mov     eax, 52Ch
0x1800c5923  jmp     short loc_1800C592A
0x1800c5925  mov     eax, 52Bh
0x1800c592a  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800c5931  lea     r8, [rsp+14A0h+Buffer]; lpBuffer
0x1800c5936  mov     r9d, 200h; cchBufferMax
0x1800c593c  mov     edx, eax; uID
0x1800c593e  call    cs:__imp_LoadStringW
0x1800c5944  test    eax, eax
0x1800c5946  jz      short loc_1800C59B7
0x1800c5948  mov     r9, r14
0x1800c594b  lea     r8, [rsp+14A0h+Buffer]; unsigned __int16 *
0x1800c5950  mov     edx, 200h; unsigned __int64
0x1800c5955  lea     rcx, [rbp+13A0h+var_C40]; unsigned __int16 *
0x1800c595c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c5961  jmp     short loc_1800C59B7
0x1800c5963  lea     rsi, aIsinroleresult; "IsInRoleResult"
0x1800c596a  mov     ebx, 530h
0x1800c596f  jmp     short loc_1800C59B7
0x1800c5971  lea     rsi, aGetcontribidfr_1; "GetContribIDFromSIDResult"
0x1800c5978  jmp     short loc_1800C596A
0x1800c597a  lea     rsi, aUpdateresult; "UpdateResult"
0x1800c5981  mov     ebx, 52Fh
0x1800c5986  jmp     short loc_1800C59B7
0x1800c5988  lea     rsi, aUpdatemsgratin_1; "UpdateMsgRatingResult"
0x1800c598f  mov     ebx, 52Dh
0x1800c5994  jmp     short loc_1800C59B7
0x1800c5996  lea     rsi, aUpdatemsgattri; "UpdateMsgAttributeResult"
0x1800c599d  mov     ebx, 52Eh
0x1800c59a2  jmp     short loc_1800C59B7
0x1800c59a4  mov     ebx, 52Ch
0x1800c59a9  jmp     short loc_1800C59B0
0x1800c59ab  mov     ebx, 52Bh
0x1800c59b0  lea     rsi, aQueryresult; "QueryResult"
0x1800c59b7  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800c59be  lea     r8, [rsp+14A0h+Buffer]; lpBuffer
0x1800c59c3  mov     r9d, 200h; cchBufferMax
0x1800c59c9  mov     edx, ebx; uID
0x1800c59cb  call    cs:__imp_LoadStringW
0x1800c59d1  test    eax, eax
0x1800c59d3  jz      short loc_1800C59F4
0x1800c59d5  mov     r9, r14
0x1800c59d8  lea     r8, [rsp+14A0h+Buffer]; unsigned __int16 *
0x1800c59dd  mov     r14d, 200h
0x1800c59e3  lea     rcx, [rbp+13A0h+var_840]; unsigned __int16 *
0x1800c59ea  mov     edx, r14d; unsigned __int64
0x1800c59ed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c59f2  jmp     short loc_1800C59FA
0x1800c59f4  mov     r14d, 200h
0x1800c59fa  lea     rdx, [rsp+14A0h+var_1448]
0x1800c59ff  mov     [rsp+14A0h+var_1448], r12
0x1800c5a04  mov     rcx, r15
0x1800c5a07  call    cs:__imp_XMLDOMFromBStr
0x1800c5a0d  mov     ebx, eax
0x1800c5a0f  test    eax, eax
0x1800c5a11  js      loc_1800C5DA8
0x1800c5a17  mov     rcx, [rsp+14A0h+var_1448]
0x1800c5a1c  lea     rdx, [rsp+14A0h+var_1458]
0x1800c5a21  mov     [rsp+14A0h+var_1458], r12
0x1800c5a26  mov     rax, [rcx]
0x1800c5a29  mov     rax, [rax+168h]
0x1800c5a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5a35  mov     ebx, eax
0x1800c5a37  cmp     eax, 1
0x1800c5a3a  jnz     short loc_1800C5A46
0x1800c5a3c  mov     ebx, 80070490h
0x1800c5a41  jmp     loc_1800C5BD9
0x1800c5a46  test    eax, eax
0x1800c5a48  js      loc_1800C5BD9
0x1800c5a4e  mov     rcx, [rsp+14A0h+var_1458]
0x1800c5a53  lea     r8, [rsp+14A0h+var_1450]
0x1800c5a58  lea     rdx, aSoapFault; "soap:Fault"
0x1800c5a5f  mov     [rsp+14A0h+var_1450], r12
0x1800c5a64  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c5a6a  mov     ebx, eax
0x1800c5a6c  test    eax, eax
0x1800c5a6e  js      loc_1800C5B3B
0x1800c5a74  mov     rcx, [rsp+14A0h+var_1450]
0x1800c5a79  lea     r8, [rsp+14A0h+var_1470]
0x1800c5a7e  xor     edx, edx
0x1800c5a80  mov     [rsp+14A0h+var_1470], r12
0x1800c5a85  call    cs:__imp_XMLNodeList_GetChild
0x1800c5a8b  mov     ebx, eax
0x1800c5a8d  test    eax, eax
0x1800c5a8f  js      loc_1800C5B29
0x1800c5a95  mov     rcx, [rsp+14A0h+var_1470]
0x1800c5a9a  lea     r8, [rsp+14A0h+bstrString]
0x1800c5a9f  lea     rdx, aFaultcode; "faultcode"
0x1800c5aa6  mov     [rsp+14A0h+bstrString], r12
0x1800c5aab  call    cs:__imp_XMLNode_GetChildTagTextValue
0x1800c5ab1  mov     ebx, eax
0x1800c5ab3  test    eax, eax
0x1800c5ab5  js      short loc_1800C5B1F
0x1800c5ab7  mov     r8, [rsp+14A0h+bstrString]; unsigned __int16 *
0x1800c5abc  lea     rcx, [rbp+13A0h+var_1040]; unsigned __int16 *
0x1800c5ac3  mov     rdx, r14; unsigned __int64
0x1800c5ac6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c5acb  mov     rcx, [rsp+14A0h+bstrString]; bstrString
0x1800c5ad0  mov     ebx, eax
0x1800c5ad2  call    cs:__imp_SysFreeString
0x1800c5ad8  test    ebx, ebx
0x1800c5ada  js      short loc_1800C5B1F
0x1800c5adc  mov     rcx, [rsp+14A0h+var_1470]
0x1800c5ae1  lea     r8, [rsp+14A0h+var_1460]
0x1800c5ae6  lea     rdx, aFaultstring; "faultstring"
0x1800c5aed  mov     [rsp+14A0h+var_1460], r12
0x1800c5af2  call    cs:__imp_XMLNode_GetChildTagTextValue
0x1800c5af8  mov     ebx, eax
0x1800c5afa  test    eax, eax
0x1800c5afc  js      short loc_1800C5B1F
0x1800c5afe  mov     r8, [rsp+14A0h+var_1460]; unsigned __int16 *
0x1800c5b03  lea     rcx, [rbp+13A0h+var_440]; unsigned __int16 *
0x1800c5b0a  mov     rdx, r14; unsigned __int64
0x1800c5b0d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c5b12  mov     rcx, [rsp+14A0h+var_1460]; bstrString
0x1800c5b17  mov     ebx, eax
0x1800c5b19  call    cs:__imp_SysFreeString
0x1800c5b1f  lea     rcx, [rsp+14A0h+var_1470]
0x1800c5b24  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c5b29  lea     rcx, [rsp+14A0h+var_1450]
0x1800c5b2e  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c5b33  test    ebx, ebx
0x1800c5b35  jns     loc_1800C5BCF
0x1800c5b3b  test    rsi, rsi
0x1800c5b3e  jz      loc_1800C5BCF
0x1800c5b44  mov     rcx, [rsp+14A0h+var_1458]
0x1800c5b49  lea     r8, [rsp+14A0h+var_1470]
0x1800c5b4e  mov     rdx, rsi
0x1800c5b51  mov     [rsp+14A0h+var_1470], r12
0x1800c5b56  call    cs:__imp_XMLElem_GetElementsByTagName
0x1800c5b5c  mov     ebx, eax
0x1800c5b5e  test    eax, eax
0x1800c5b60  js      short loc_1800C5BCF
0x1800c5b62  mov     rcx, [rsp+14A0h+var_1470]
0x1800c5b67  lea     r8, [rsp+14A0h+bstrString]
0x1800c5b6c  xor     edx, edx
0x1800c5b6e  mov     [rsp+14A0h+bstrString], r12
0x1800c5b73  call    cs:__imp_XMLNodeList_GetChild
0x1800c5b79  mov     ebx, eax
0x1800c5b7b  test    eax, eax
0x1800c5b7d  js      short loc_1800C5BC5
0x1800c5b7f  mov     rcx, [rsp+14A0h+bstrString]
0x1800c5b84  lea     rdx, [rsp+14A0h+var_1460]
0x1800c5b89  mov     [rsp+14A0h+var_1460], r12
0x1800c5b8e  call    cs:__imp_XMLNode_GetTagText
0x1800c5b94  mov     ebx, eax
0x1800c5b96  test    eax, eax
0x1800c5b98  js      short loc_1800C5BBB
0x1800c5b9a  mov     r8, [rsp+14A0h+var_1460]; unsigned __int16 *
0x1800c5b9f  lea     rcx, [rbp+13A0h+var_440]; unsigned __int16 *
0x1800c5ba6  mov     rdx, r14; unsigned __int64
0x1800c5ba9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c5bae  mov     rcx, [rsp+14A0h+var_1460]; bstrString
0x1800c5bb3  mov     ebx, eax
0x1800c5bb5  call    cs:__imp_SysFreeString
0x1800c5bbb  lea     rcx, [rsp+14A0h+bstrString]
0x1800c5bc0  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c5bc5  lea     rcx, [rsp+14A0h+var_1470]
0x1800c5bca  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c5bcf  lea     rcx, [rsp+14A0h+var_1458]
0x1800c5bd4  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c5bd9  lea     rcx, [rsp+14A0h+var_1448]
0x1800c5bde  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800c5be3  test    ebx, ebx
0x1800c5be5  js      loc_1800C5DA8
0x1800c5beb  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800c5bf2  lea     r8, [rsp+14A0h+Buffer]; lpBuffer
0x1800c5bf7  mov     r9d, r14d; cchBufferMax
0x1800c5bfa  mov     [rsp+14A0h+Buffer], r12w
0x1800c5c00  mov     edx, 51Ch; uID
0x1800c5c05  call    cs:__imp_LoadStringW
0x1800c5c0b  test    eax, eax
0x1800c5c0d  jz      loc_1800C5DA3
0x1800c5c13  cmp     r12w, [rbp+13A0h+var_1040]
0x1800c5c1b  jnz     short loc_1800C5C33
0x1800c5c1d  lea     r8, aGeneral; "General"
0x1800c5c24  mov     rdx, r14; unsigned __int64
0x1800c5c27  lea     rcx, [rbp+13A0h+var_1040]; unsigned __int16 *
0x1800c5c2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c5c33  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800c5c37  mov     esi, r12d
0x1800c5c3a  cmp     r12w, [rbp+13A0h+var_C40]
0x1800c5c42  jz      short loc_1800C5C58
0x1800c5c44  lea     rax, [rbp+13A0h+var_C40]
0x1800c5c4b  mov     rsi, rcx
0x1800c5c4e  inc     rsi
0x1800c5c51  cmp     [rax+rsi*2], r12w
0x1800c5c56  jnz     short loc_1800C5C4E
0x1800c5c58  mov     edi, r12d
0x1800c5c5b  cmp     r12w, [rbp+13A0h+var_840]
0x1800c5c63  jz      short loc_1800C5C79
0x1800c5c65  lea     rax, [rbp+13A0h+var_840]
0x1800c5c6c  mov     rdi, rcx
0x1800c5c6f  inc     rdi
0x1800c5c72  cmp     [rax+rdi*2], r12w
0x1800c5c77  jnz     short loc_1800C5C6F
0x1800c5c79  lea     rax, [rsp+14A0h+Buffer]
0x1800c5c7e  mov     rdx, rcx
0x1800c5c81  inc     rdx
0x1800c5c84  cmp     [rax+rdx*2], r12w
0x1800c5c89  jnz     short loc_1800C5C81
0x1800c5c8b  lea     r8, [rbp+13A0h+var_1040]
0x1800c5c92  mov     rax, rcx
0x1800c5c95  inc     rax
0x1800c5c98  cmp     [r8+rax*2], r12w
0x1800c5c9d  jnz     short loc_1800C5C95
0x1800c5c9f  lea     r8, [rbp+13A0h+var_440]
0x1800c5ca6  inc     rcx
0x1800c5ca9  cmp     [r8+rcx*2], r12w
0x1800c5cae  jnz     short loc_1800C5CA6
0x1800c5cb0  inc     ecx
0x1800c5cb2  lea     r15d, [rdi+rax]
0x1800c5cb6  add     r15d, edx
0x1800c5cb9  add     r15d, ecx
0x1800c5cbc  add     r15d, esi
  ... truncated ...
```
