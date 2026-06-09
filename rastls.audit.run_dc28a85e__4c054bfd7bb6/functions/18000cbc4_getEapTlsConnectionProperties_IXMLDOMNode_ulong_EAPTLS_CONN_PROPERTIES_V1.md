# getEapTlsConnectionProperties(IXMLDOMNode *,ulong,_EAPTLS_CONN_PROPERTIES_V1 * *)

- ea: `0x18000cbc4`
- end: `0x18000d1d4`
- name: `?getEapTlsConnectionProperties@@YAKPEAUIXMLDOMNode@@KPEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z`
- size: `1552`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, unsigned int, struct _EAPTLS_CONN_PROPERTIES_V1 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180062228`

## callees

- `0x180007d00`
- `0x18000cbc4`
- `0x18000eb10`
- `0x180010140`
- `0x1800104b0`
- `0x180010580`
- `0x18001b4b0`
- `0x18001fe70`
- `0x180061f9c`
- `0x180062884`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d101`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d101`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ceb7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ced2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ceed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000cf08`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ceb7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ced2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ceed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000cf08`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cc35`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cc9c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ce2e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cc35`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cc9c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ce2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cc81`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ccef`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cdcd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce17`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf35`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf92`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d112`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d123`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cc81`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ccef`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cdcd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce17`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf35`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf92`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d0ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d112`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d123`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall getEapTlsConnectionProperties(
        struct IXMLDOMNode *a1,
        int a2,
        struct _EAPTLS_CONN_PROPERTIES_V1 **a3)
{
  struct _EAPTLS_CONN_PROPERTIES_V1 *v6; // r15
  const WCHAR *v7; // rax
  int v8; // ecx
  OLECHAR *v9; // rbx
  struct IXMLDOMNode *v10; // rdi
  const WCHAR *v11; // rax
  int v12; // ecx
  OLECHAR *v13; // rbx
  int SingleNode; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // eax
  struct _EAPTLS_CONTROL_BLOCK *v18; // rcx
  __int64 v19; // rdx
  struct IXMLDOMNode *v20; // r14
  const WCHAR *v21; // rax
  int v22; // ecx
  OLECHAR *v23; // rbx
  char v24; // al
  unsigned int v25; // eax
  unsigned int v26; // ecx
  size_t Size; // [rsp+38h] [rbp-51h]
  LPCWSTR lpString1; // [rsp+50h] [rbp-39h] BYREF
  struct IXMLDOMNode *v30; // [rsp+58h] [rbp-31h] BYREF
  size_t v31; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v32; // [rsp+68h] [rbp-21h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-19h] BYREF
  struct IXMLDOMNode *v34; // [rsp+78h] [rbp-11h] BYREF
  __int64 v35; // [rsp+80h] [rbp-9h] BYREF
  struct _EAPTLS_CONN_PROPERTIES_V1 *v36; // [rsp+88h] [rbp-1h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+7h] BYREF
  HLOCAL v38; // [rsp+98h] [rbp+Fh] BYREF
  BSTR v39; // [rsp+A0h] [rbp+17h] BYREF
  struct IXMLDOMNode *v40; // [rsp+A8h] [rbp+1Fh] BYREF
  struct IXMLDOMNode *v41; // [rsp+B0h] [rbp+27h] BYREF
  struct IXMLDOMNode *v42; // [rsp+B8h] [rbp+2Fh] BYREF
  bool v43; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned int v44; // [rsp+108h] [rbp+7Fh] BYREF

  v30 = 0;
  v34 = 0;
  v42 = 0;
  v41 = 0;
  v40 = 0;
  v35 = 0;
  v39 = 0;
  bstrString = 0;
  v32 = 0;
  hMem = 0;
  v6 = 0;
  v36 = 0;
  v44 = 0;
  v38 = 0;
  v31 = 0;
  v7 = SysAllocString(L"eaptlsconnectionpropertiesv1:EapType[1]");
  v9 = (OLECHAR *)v7;
  lpString1 = v7;
  if ( !v7 )
    ATL::AtlThrowImpl(v8);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, const WCHAR *, struct IXMLDOMNode **))a1->lpVtbl->selectSingleNode)(
         a1,
         v7,
         &v30)
    || !v30 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv1:EapType[1]");
    SysFreeString(v9);
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    v15 = 87;
    goto LABEL_62;
  }
  SysFreeString(v9);
  v44 |= 0x15u;
  v10 = v30;
  v11 = SysAllocString(L"eaptlsconnectionpropertiesv1:CredentialsSource[1]");
  v13 = (OLECHAR *)v11;
  lpString1 = v11;
  if ( !v11 )
    ATL::AtlThrowImpl(v12);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, const WCHAR *, struct IXMLDOMNode **))v10->lpVtbl->selectSingleNode)(
         v10,
         v11,
         &v34)
    || !v34 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv1:CredentialsSource[1]");
    SysFreeString(v13);
  }
  else
  {
    SysFreeString(v13);
    SingleNode = getSingleNode(v34, L"eaptlsconnectionpropertiesv1:SmartCard[1]", &v42);
    if ( !SingleNode )
    {
      v44 &= 0xFFFFFFEE;
      goto LABEL_29;
    }
    if ( SingleNode == -2147024882 )
    {
LABEL_12:
      v15 = 14;
      goto LABEL_62;
    }
    v43 = 1;
    v16 = getSingleNode(v34, L"eaptlsconnectionpropertiesv1:CertificateStore[1]", &v40);
    v15 = v16;
    if ( v16 )
    {
      if ( (v16 & 0x1FFF0000) == 0x70000 )
        v15 = (unsigned __int16)v16;
      goto LABEL_62;
    }
    v17 = getSingleNode(v40, L"eaptlsconnectionpropertiesv1:SimpleCertSelection[1]", &v41);
    if ( v17 )
    {
      if ( v17 == -2147024882 )
        goto LABEL_12;
    }
    else
    {
      if ( (unsigned int)ReadBOOLEANFromXMLNode(v41, &v43, &bstrString) )
      {
        v15 = 13;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_62;
        v19 = 211;
        goto LABEL_20;
      }
      if ( !v43 )
        v44 &= ~0x10u;
      SysFreeString(bstrString);
      bstrString = 0;
    }
  }
LABEL_29:
  v20 = v30;
  v21 = SysAllocString(L"eaptlsconnectionpropertiesv1:DifferentUsername[1]");
  v23 = (OLECHAR *)v21;
  lpString1 = v21;
  if ( !v21 )
    ATL::AtlThrowImpl(v22);
  if ( !((unsigned int (__fastcall *)(struct IXMLDOMNode *, const WCHAR *, __int64 *))v20->lpVtbl->selectSingleNode)(
          v20,
          v21,
          &v35)
    && v35 )
  {
    SysFreeString(v23);
    lpString1 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v35 + 208LL))(v35, &lpString1) )
    {
      if ( !lstrcmpiW(lpString1, L"true") || !lstrcmpiW(lpString1, L"1") )
      {
        v24 = 1;
        goto LABEL_40;
      }
      if ( !lstrcmpiW(lpString1, L"false") || !lstrcmpiW(lpString1, L"0") )
      {
        v24 = 0;
LABEL_40:
        if ( v24 )
          v25 = v44 | 8;
        else
          v25 = v44 & 0xFFFFFFF7;
        v44 = v25;
        SysFreeString((BSTR)lpString1);
        bstrString = 0;
        goto LABEL_49;
      }
    }
    v15 = 13;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_62;
    v19 = 212;
LABEL_20:
    WPP_SF_(*((_QWORD *)v18 + 2), v19, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    goto LABEL_62;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      252,
      WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
      L"eaptlsconnectionpropertiesv1:DifferentUsername[1]");
  SysFreeString(v23);
LABEL_49:
  v15 = ParseServerValidationNode(
          v30,
          0,
          (a2 & 0x2000000) != 0,
          &v44,
          (struct _EAPTLS_HASH **)&hMem,
          &v32,
          &v39,
          (unsigned int *)&v31 + 1);
  if ( !v15 )
  {
    v15 = ParseCertFilterNodes(v30, (unsigned __int8 **)&v38, (unsigned int *)&v31);
    if ( !v15 )
    {
      v26 = v44;
      if ( (v44 & 1) == 0 )
      {
        v15 = ParseGroupSmartCardCertNode(v30, &v44);
        if ( v15 )
          goto LABEL_62;
        v26 = v44;
      }
      LODWORD(Size) = v31;
      v15 = FinishEapTlsConnProvV1(
              v26,
              (unsigned int)v38,
              v32,
              (struct _EAPTLS_HASH *)hMem,
              HIDWORD(v31),
              v39,
              (unsigned __int8 *)v38,
              Size,
              &v36,
              0);
      if ( v15 )
      {
        v6 = v36;
      }
      else
      {
        *a3 = v36;
        v6 = 0;
      }
    }
  }
LABEL_62:
  LocalFree(v6);
  LocalFree(hMem);
  LocalFree(v38);
  SysFreeString(bstrString);
  SysFreeString(v39);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v40 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v40->lpVtbl->Release)(v40);
  if ( v41 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v41->lpVtbl->Release)(v41);
  if ( v42 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v42->lpVtbl->Release)(v42);
  if ( v34 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v34->lpVtbl->Release)(v34);
  if ( v30 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v30->lpVtbl->Release)(v30);
  return v15;
}

```

## disassembly

```asm
0x18000cbc4  mov     [rsp-8+arg_0], rbx
0x18000cbc9  mov     [rsp-8+arg_10], rdi
0x18000cbce  push    rbp
0x18000cbcf  push    r12
0x18000cbd1  push    r13
0x18000cbd3  push    r14
0x18000cbd5  push    r15
0x18000cbd7  lea     rbp, [rsp-37h]
0x18000cbdc  sub     rsp, 0C0h
0x18000cbe3  mov     r13, r8
0x18000cbe6  mov     r12d, edx
0x18000cbe9  mov     rdi, rcx
0x18000cbec  xor     r14d, r14d
0x18000cbef  mov     [rbp+57h+var_88], r14
0x18000cbf3  mov     [rbp+57h+var_68], r14
0x18000cbf7  mov     [rbp+57h+var_28], r14
0x18000cbfb  mov     [rbp+57h+var_30], r14
0x18000cbff  mov     [rbp+57h+var_38], r14
0x18000cc03  mov     [rbp+57h+var_60], r14
0x18000cc07  mov     [rbp+57h+var_40], r14
0x18000cc0b  mov     [rbp+57h+bstrString], r14
0x18000cc0f  mov     dword ptr [rbp+57h+var_80+4], r14d
0x18000cc13  mov     [rbp+57h+var_78], r14d
0x18000cc17  mov     [rbp+57h+hMem], r14
0x18000cc1b  mov     r15d, r14d
0x18000cc1e  mov     [rbp+57h+var_58], r14
0x18000cc22  mov     [rbp+57h+arg_18], r14d
0x18000cc26  mov     [rbp+57h+var_48], r14
0x18000cc2a  mov     dword ptr [rbp+57h+var_80], r14d
0x18000cc2e  lea     rcx, aEaptlsconnecti_26; "eaptlsconnectionpropertiesv1:EapType[1]"
0x18000cc35  call    cs:__imp_SysAllocString
0x18000cc3c  nop     dword ptr [rax+rax+00h]
0x18000cc41  mov     rbx, rax
0x18000cc44  mov     [rbp+57h+lpString1], rax
0x18000cc48  test    rax, rax
0x18000cc4b  jnz     short loc_18000CC53
0x18000cc4d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000cc53  mov     rax, [rdi]
0x18000cc56  lea     r8, [rbp+57h+var_88]
0x18000cc5a  mov     rdx, rbx
0x18000cc5d  mov     rcx, rdi
0x18000cc60  mov     rax, [rax+128h]
0x18000cc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc6c  test    eax, eax
0x18000cc6e  jnz     loc_18000D079
0x18000cc74  cmp     [rbp+57h+var_88], r14
0x18000cc78  jz      loc_18000D079
0x18000cc7e  mov     rcx, rbx; bstrString
0x18000cc81  call    cs:__imp_SysFreeString
0x18000cc88  nop     dword ptr [rax+rax+00h]
0x18000cc8d  or      [rbp+57h+arg_18], 15h
0x18000cc91  mov     rdi, [rbp+57h+var_88]
0x18000cc95  lea     rcx, aEaptlsconnecti_4; "eaptlsconnectionpropertiesv1:Credential"...
0x18000cc9c  call    cs:__imp_SysAllocString
0x18000cca3  nop     dword ptr [rax+rax+00h]
0x18000cca8  mov     rbx, rax
0x18000ccab  mov     [rbp+57h+lpString1], rax
0x18000ccaf  test    rax, rax
0x18000ccb2  jnz     short loc_18000CCBA
0x18000ccb4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ccba  mov     rax, [rdi]
0x18000ccbd  lea     r8, [rbp+57h+var_68]
0x18000ccc1  mov     rdx, rbx
0x18000ccc4  mov     rcx, rdi
0x18000ccc7  mov     rax, [rax+128h]
0x18000ccce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccd3  lea     rdi, WPP_GLOBAL_Control
0x18000ccda  test    eax, eax
0x18000ccdc  jnz     loc_18000CDEB
0x18000cce2  cmp     [rbp+57h+var_68], r14
0x18000cce6  jz      loc_18000CDEB
0x18000ccec  mov     rcx, rbx; bstrString
0x18000ccef  call    cs:__imp_SysFreeString
0x18000ccf6  nop     dword ptr [rax+rax+00h]
0x18000ccfb  lea     r8, [rbp+57h+var_28]; struct IXMLDOMNode **
0x18000ccff  lea     rdx, aEaptlsconnecti_5; "eaptlsconnectionpropertiesv1:SmartCard["...
0x18000cd06  mov     rcx, [rbp+57h+var_68]; struct IXMLDOMNode *
0x18000cd0a  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000cd0f  test    eax, eax
0x18000cd11  jnz     short loc_18000CD1C
0x18000cd13  and     [rbp+57h+arg_18], 0FFFFFFEEh
0x18000cd17  jmp     loc_18000CE23
0x18000cd1c  cmp     eax, 8007000Eh
0x18000cd21  jnz     short loc_18000CD2D
0x18000cd23  mov     ebx, 0Eh
0x18000cd28  jmp     loc_18000D0DE
0x18000cd2d  mov     [rbp+57h+arg_8], 1
0x18000cd31  lea     r8, [rbp+57h+var_38]; struct IXMLDOMNode **
0x18000cd35  lea     rdx, aEaptlsconnecti_16; "eaptlsconnectionpropertiesv1:Certificat"...
0x18000cd3c  mov     rcx, [rbp+57h+var_68]; struct IXMLDOMNode *
0x18000cd40  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000cd45  mov     ebx, eax
0x18000cd47  test    eax, eax
0x18000cd49  jz      short loc_18000CD63
0x18000cd4b  and     eax, 1FFF0000h
0x18000cd50  cmp     eax, 70000h
0x18000cd55  jnz     loc_18000D0DE
0x18000cd5b  movzx   ebx, bx
0x18000cd5e  jmp     loc_18000D0DE
0x18000cd63  lea     r8, [rbp+57h+var_30]; struct IXMLDOMNode **
0x18000cd67  lea     rdx, aEaptlsconnecti_15; "eaptlsconnectionpropertiesv1:SimpleCert"...
0x18000cd6e  mov     rcx, [rbp+57h+var_38]; struct IXMLDOMNode *
0x18000cd72  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000cd77  test    eax, eax
0x18000cd79  jnz     short loc_18000CDDF
0x18000cd7b  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18000cd7f  lea     rdx, [rbp+57h+arg_8]; bool *
0x18000cd83  mov     rcx, [rbp+57h+var_30]; struct IXMLDOMNode *
0x18000cd87  call    ?ReadBOOLEANFromXMLNode@@YAJPEAUIXMLDOMNode@@PEA_NPEAPEAG@Z; ReadBOOLEANFromXMLNode(IXMLDOMNode *,bool *,ushort * *)
0x18000cd8c  test    eax, eax
0x18000cd8e  jz      short loc_18000CDBF
0x18000cd90  mov     ebx, 0Dh
0x18000cd95  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd9c  cmp     rcx, rdi
0x18000cd9f  jz      loc_18000D0DE
0x18000cda5  mov     edx, 0D3h
0x18000cdaa  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000cdb1  mov     rcx, [rcx+10h]
0x18000cdb5  call    WPP_SF_
0x18000cdba  jmp     loc_18000D0DE
0x18000cdbf  cmp     [rbp+57h+arg_8], r14b
0x18000cdc3  jnz     short loc_18000CDC9
0x18000cdc5  and     [rbp+57h+arg_18], 0FFFFFFEFh
0x18000cdc9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000cdcd  call    cs:__imp_SysFreeString
0x18000cdd4  nop     dword ptr [rax+rax+00h]
0x18000cdd9  mov     [rbp+57h+bstrString], r14
0x18000cddd  jmp     short loc_18000CE23
0x18000cddf  cmp     eax, 8007000Eh
0x18000cde4  jnz     short loc_18000CE23
0x18000cde6  jmp     loc_18000CD23
0x18000cdeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdf2  cmp     rcx, rdi
0x18000cdf5  jz      short loc_18000CE14
0x18000cdf7  mov     edx, 0FCh
0x18000cdfc  lea     r9, aEaptlsconnecti_4; "eaptlsconnectionpropertiesv1:Credential"...
0x18000ce03  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000ce0a  mov     rcx, [rcx+10h]
0x18000ce0e  call    WPP_SF_S
0x18000ce13  nop
0x18000ce14  mov     rcx, rbx; bstrString
0x18000ce17  call    cs:__imp_SysFreeString
0x18000ce1e  nop     dword ptr [rax+rax+00h]
0x18000ce23  mov     r14, [rbp+57h+var_88]
0x18000ce27  lea     rcx, aEaptlsconnecti_19; "eaptlsconnectionpropertiesv1:DifferentU"...
0x18000ce2e  call    cs:__imp_SysAllocString
0x18000ce35  nop     dword ptr [rax+rax+00h]
0x18000ce3a  mov     rbx, rax
0x18000ce3d  mov     [rbp+57h+lpString1], rax
0x18000ce41  test    rax, rax
0x18000ce44  jnz     short loc_18000CE4C
0x18000ce46  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ce4c  mov     rax, [r14]
0x18000ce4f  lea     r8, [rbp+57h+var_60]
0x18000ce53  mov     rdx, rbx
0x18000ce56  mov     rcx, r14
0x18000ce59  mov     rax, [rax+128h]
0x18000ce60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce65  xor     r14d, r14d
0x18000ce68  test    eax, eax
0x18000ce6a  jnz     loc_18000CF66
0x18000ce70  cmp     [rbp+57h+var_60], r14
0x18000ce74  jz      loc_18000CF66
0x18000ce7a  mov     rcx, rbx; bstrString
0x18000ce7d  call    cs:__imp_SysFreeString
0x18000ce84  nop     dword ptr [rax+rax+00h]
0x18000ce89  mov     rcx, [rbp+57h+var_60]
0x18000ce8d  mov     [rbp+57h+lpString1], r14
0x18000ce91  mov     rax, [rcx]
0x18000ce94  lea     rdx, [rbp+57h+lpString1]
0x18000ce98  mov     rax, [rax+0D0h]
0x18000ce9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cea4  test    eax, eax
0x18000cea6  jnz     loc_18000CF47
0x18000ceac  lea     rdx, String2; "true"
0x18000ceb3  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000ceb7  call    cs:__imp_lstrcmpiW
0x18000cebe  nop     dword ptr [rax+rax+00h]
0x18000cec3  test    eax, eax
0x18000cec5  jz      short loc_18000CF1D
0x18000cec7  lea     rdx, a1; "1"
0x18000cece  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000ced2  call    cs:__imp_lstrcmpiW
0x18000ced9  nop     dword ptr [rax+rax+00h]
0x18000cede  test    eax, eax
0x18000cee0  jz      short loc_18000CF1D
0x18000cee2  lea     rdx, aFalse; "false"
0x18000cee9  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000ceed  call    cs:__imp_lstrcmpiW
0x18000cef4  nop     dword ptr [rax+rax+00h]
0x18000cef9  test    eax, eax
0x18000cefb  jz      short loc_18000CF18
0x18000cefd  lea     rdx, a0; "0"
0x18000cf04  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000cf08  call    cs:__imp_lstrcmpiW
0x18000cf0f  nop     dword ptr [rax+rax+00h]
0x18000cf14  test    eax, eax
0x18000cf16  jnz     short loc_18000CF47
0x18000cf18  mov     al, r14b
0x18000cf1b  jmp     short loc_18000CF1F
0x18000cf1d  mov     al, 1
0x18000cf1f  test    al, al
0x18000cf21  mov     eax, [rbp+57h+arg_18]
0x18000cf24  jz      short loc_18000CF2B
0x18000cf26  or      eax, 8
0x18000cf29  jmp     short loc_18000CF2E
0x18000cf2b  and     eax, 0FFFFFFF7h
0x18000cf2e  mov     [rbp+57h+arg_18], eax
0x18000cf31  mov     rcx, [rbp+57h+lpString1]; bstrString
0x18000cf35  call    cs:__imp_SysFreeString
0x18000cf3c  nop     dword ptr [rax+rax+00h]
0x18000cf41  mov     [rbp+57h+bstrString], r14
0x18000cf45  jmp     short loc_18000CF9E
0x18000cf47  mov     ebx, 0Dh
0x18000cf4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf53  cmp     rcx, rdi
0x18000cf56  jz      loc_18000D0DE
0x18000cf5c  mov     edx, 0D4h
0x18000cf61  jmp     loc_18000CDAA
0x18000cf66  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf6d  cmp     rcx, rdi
0x18000cf70  jz      short loc_18000CF8F
0x18000cf72  mov     edx, 0FCh
0x18000cf77  lea     r9, aEaptlsconnecti_19; "eaptlsconnectionpropertiesv1:DifferentU"...
0x18000cf7e  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000cf85  mov     rcx, [rcx+10h]
0x18000cf89  call    WPP_SF_S
0x18000cf8e  nop
0x18000cf8f  mov     rcx, rbx; bstrString
0x18000cf92  call    cs:__imp_SysFreeString
0x18000cf99  nop     dword ptr [rax+rax+00h]
0x18000cf9e  shr     r12d, 19h
0x18000cfa2  and     r12b, 1
0x18000cfa6  lea     rax, [rbp+57h+var_80+4]
0x18000cfaa  mov     [rsp+0E0h+Size], rax; unsigned int *
0x18000cfaf  lea     rax, [rbp+57h+var_40]
0x18000cfb3  mov     [rsp+0E0h+var_B0], rax; unsigned __int16 **
0x18000cfb8  lea     rax, [rbp+57h+var_78]
0x18000cfbc  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x18000cfc1  lea     rax, [rbp+57h+hMem]
0x18000cfc5  mov     [rsp+0E0h+var_C0], rax; struct _EAPTLS_HASH **
0x18000cfca  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x18000cfce  mov     r8b, r12b; bool
0x18000cfd1  xor     edx, edx; bool
0x18000cfd3  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x18000cfd7  call    ?ParseServerValidationNode@@YAKPEAUIXMLDOMNode@@_N1PEAKPEAPEAU_EAPTLS_HASH@@2PEAPEAG2@Z; ParseServerValidationNode(IXMLDOMNode *,bool,bool,ulong *,_EAPTLS_HASH * *,ulong *,ushort * *,ulong *)
0x18000cfdc  mov     ebx, eax
0x18000cfde  test    eax, eax
0x18000cfe0  jnz     loc_18000D0DE
0x18000cfe6  lea     r8, [rbp+57h+var_80]; unsigned int *
0x18000cfea  lea     rdx, [rbp+57h+var_48]; unsigned __int8 **
0x18000cfee  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x18000cff2  call    ?ParseCertFilterNodes@@YAKPEAUIXMLDOMNode@@PEAPEAEPEAK@Z; ParseCertFilterNodes(IXMLDOMNode *,uchar * *,ulong *)
0x18000cff7  mov     ebx, eax
0x18000cff9  test    eax, eax
0x18000cffb  jnz     loc_18000D0DE
0x18000d001  mov     ecx, [rbp+57h+arg_18]
0x18000d004  test    cl, 1
0x18000d007  jnz     short loc_18000D023
0x18000d009  lea     rdx, [rbp+57h+arg_18]; unsigned int *
0x18000d00d  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x18000d011  call    ?ParseGroupSmartCardCertNode@@YAKPEAUIXMLDOMNode@@PEAK@Z; ParseGroupSmartCardCertNode(IXMLDOMNode *,ulong *)
0x18000d016  mov     ebx, eax
0x18000d018  test    eax, eax
0x18000d01a  jnz     loc_18000D0DE
0x18000d020  mov     ecx, [rbp+57h+arg_18]; unsigned int
0x18000d023  mov     eax, dword ptr [rbp+57h+var_80]
0x18000d026  mov     rdx, [rbp+57h+var_48]; unsigned int
0x18000d02a  mov     r9, [rbp+57h+var_40]
0x18000d02e  mov     r10d, dword ptr [rbp+57h+var_80+4]
0x18000d032  mov     [rsp+0E0h+var_98], r14; unsigned int *
0x18000d037  lea     r8, [rbp+57h+var_58]
0x18000d03b  mov     [rsp+0E0h+var_A0], r8; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x18000d040  mov     dword ptr [rsp+0E0h+Size], eax; Size
0x18000d044  mov     [rsp+0E0h+var_B0], rdx; unsigned __int8 *
0x18000d049  mov     [rsp+0E0h+var_B8], r9; unsigned __int16 *
0x18000d04e  mov     dword ptr [rsp+0E0h+var_C0], r10d; unsigned int
0x18000d053  mov     r9, [rbp+57h+hMem]; struct _EAPTLS_HASH *
0x18000d057  mov     r8d, [rbp+57h+var_78]; unsigned int
0x18000d05b  call    ?FinishEapTlsConnProvV1@@YAKKKKPEAU_EAPTLS_HASH@@KPEAGPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAK@Z; FinishEapTlsConnProvV1(ulong,ulong,ulong,_EAPTLS_HASH *,ulong,ushort *,uchar *,ulong,_EAPTLS_CONN_PROPERTIES_V1 * *,ulong *)
0x18000d060  mov     ebx, eax
0x18000d062  test    eax, eax
0x18000d064  jnz     short loc_18000D073
0x18000d066  mov     rax, [rbp+57h+var_58]
0x18000d06a  mov     [r13+0], rax
0x18000d06e  mov     r15, r14
0x18000d071  jmp     short loc_18000D0DE
0x18000d073  mov     r15, [rbp+57h+var_58]
0x18000d077  jmp     short loc_18000D0DE
0x18000d079  lea     rdi, WPP_GLOBAL_Control
0x18000d080  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d087  cmp     rcx, rdi
0x18000d08a  jz      short loc_18000D0A9
0x18000d08c  mov     edx, 0FCh
0x18000d091  lea     r9, aEaptlsconnecti_26; "eaptlsconnectionpropertiesv1:EapType[1]"
0x18000d098  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000d09f  mov     rcx, [rcx+10h]
0x18000d0a3  call    WPP_SF_S
0x18000d0a8  nop
0x18000d0a9  mov     rcx, rbx; bstrString
  ... truncated ...
```
