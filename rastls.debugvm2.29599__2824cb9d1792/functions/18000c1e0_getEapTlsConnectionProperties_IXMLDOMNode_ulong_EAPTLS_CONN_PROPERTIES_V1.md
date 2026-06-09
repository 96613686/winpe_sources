# getEapTlsConnectionProperties(IXMLDOMNode *,ulong,_EAPTLS_CONN_PROPERTIES_V1 * *)

- ea: `0x18000c1e0`
- end: `0x18000c773`
- name: `?getEapTlsConnectionProperties@@YAKPEAUIXMLDOMNode@@KPEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z`
- size: `1427`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, unsigned int, struct _EAPTLS_CONN_PROPERTIES_V1 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18005ea34`

## callees

- `0x1800075b0`
- `0x18000c1e0`
- `0x18000deb0`
- `0x18000f350`
- `0x18000f690`
- `0x18000f750`
- `0x180019c80`
- `0x18001e140`
- `0x18005e7c8`
- `0x18005f078`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c69f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c6a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c6b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c69f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c6a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c6b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c49f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c4b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c4c9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c4de`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c49f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c4b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c4c9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000c4de`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c251`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c2ac`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c426`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c251`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c2ac`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c426`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c297`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c2f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c3d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c415`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c46f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c505`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c55c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c670`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c6be`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c6c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c297`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c2f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c3d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c415`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c46f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c505`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c55c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c670`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c6be`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c6c9`

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
0x18000c1e0  mov     [rsp-8+arg_0], rbx
0x18000c1e5  mov     [rsp-8+arg_10], rdi
0x18000c1ea  push    rbp
0x18000c1eb  push    r12
0x18000c1ed  push    r13
0x18000c1ef  push    r14
0x18000c1f1  push    r15
0x18000c1f3  lea     rbp, [rsp-37h]
0x18000c1f8  sub     rsp, 0C0h
0x18000c1ff  mov     r13, r8
0x18000c202  mov     r12d, edx
0x18000c205  mov     rdi, rcx
0x18000c208  xor     r14d, r14d
0x18000c20b  mov     [rbp+57h+var_88], r14
0x18000c20f  mov     [rbp+57h+var_68], r14
0x18000c213  mov     [rbp+57h+var_28], r14
0x18000c217  mov     [rbp+57h+var_30], r14
0x18000c21b  mov     [rbp+57h+var_38], r14
0x18000c21f  mov     [rbp+57h+var_60], r14
0x18000c223  mov     [rbp+57h+var_40], r14
0x18000c227  mov     [rbp+57h+bstrString], r14
0x18000c22b  mov     dword ptr [rbp+57h+var_80+4], r14d
0x18000c22f  mov     [rbp+57h+var_78], r14d
0x18000c233  mov     [rbp+57h+hMem], r14
0x18000c237  mov     r15d, r14d
0x18000c23a  mov     [rbp+57h+var_58], r14
0x18000c23e  mov     [rbp+57h+arg_18], r14d
0x18000c242  mov     [rbp+57h+var_48], r14
0x18000c246  mov     dword ptr [rbp+57h+var_80], r14d
0x18000c24a  lea     rcx, aEaptlsconnecti_26; "eaptlsconnectionpropertiesv1:EapType[1]"
0x18000c251  call    cs:__imp_SysAllocString
0x18000c257  mov     rbx, rax
0x18000c25a  mov     [rbp+57h+lpString1], rax
0x18000c25e  test    rax, rax
0x18000c261  jnz     short loc_18000C269
0x18000c263  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c269  mov     rax, [rdi]
0x18000c26c  lea     r8, [rbp+57h+var_88]
0x18000c270  mov     rdx, rbx
0x18000c273  mov     rcx, rdi
0x18000c276  mov     rax, [rax+128h]
0x18000c27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c282  test    eax, eax
0x18000c284  jnz     loc_18000C63D
0x18000c28a  cmp     [rbp+57h+var_88], r14
0x18000c28e  jz      loc_18000C63D
0x18000c294  mov     rcx, rbx; bstrString
0x18000c297  call    cs:__imp_SysFreeString
0x18000c29d  or      [rbp+57h+arg_18], 15h
0x18000c2a1  mov     rdi, [rbp+57h+var_88]
0x18000c2a5  lea     rcx, aEaptlsconnecti_4; "eaptlsconnectionpropertiesv1:Credential"...
0x18000c2ac  call    cs:__imp_SysAllocString
0x18000c2b2  mov     rbx, rax
0x18000c2b5  mov     [rbp+57h+lpString1], rax
0x18000c2b9  test    rax, rax
0x18000c2bc  jnz     short loc_18000C2C4
0x18000c2be  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c2c4  mov     rax, [rdi]
0x18000c2c7  lea     r8, [rbp+57h+var_68]
0x18000c2cb  mov     rdx, rbx
0x18000c2ce  mov     rcx, rdi
0x18000c2d1  mov     rax, [rax+128h]
0x18000c2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2dd  lea     rdi, WPP_GLOBAL_Control
0x18000c2e4  test    eax, eax
0x18000c2e6  jnz     loc_18000C3E9
0x18000c2ec  cmp     [rbp+57h+var_68], r14
0x18000c2f0  jz      loc_18000C3E9
0x18000c2f6  mov     rcx, rbx; bstrString
0x18000c2f9  call    cs:__imp_SysFreeString
0x18000c2ff  lea     r8, [rbp+57h+var_28]; struct IXMLDOMNode **
0x18000c303  lea     rdx, aEaptlsconnecti_5; "eaptlsconnectionpropertiesv1:SmartCard["...
0x18000c30a  mov     rcx, [rbp+57h+var_68]; struct IXMLDOMNode *
0x18000c30e  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000c313  test    eax, eax
0x18000c315  jnz     short loc_18000C320
0x18000c317  and     [rbp+57h+arg_18], 0FFFFFFEEh
0x18000c31b  jmp     loc_18000C41B
0x18000c320  cmp     eax, 8007000Eh
0x18000c325  jnz     short loc_18000C331
0x18000c327  mov     ebx, 0Eh
0x18000c32c  jmp     loc_18000C69C
0x18000c331  mov     [rbp+57h+arg_8], 1
0x18000c335  lea     r8, [rbp+57h+var_38]; struct IXMLDOMNode **
0x18000c339  lea     rdx, aEaptlsconnecti_16; "eaptlsconnectionpropertiesv1:Certificat"...
0x18000c340  mov     rcx, [rbp+57h+var_68]; struct IXMLDOMNode *
0x18000c344  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000c349  mov     ebx, eax
0x18000c34b  test    eax, eax
0x18000c34d  jz      short loc_18000C367
0x18000c34f  and     eax, 1FFF0000h
0x18000c354  cmp     eax, 70000h
0x18000c359  jnz     loc_18000C69C
0x18000c35f  movzx   ebx, bx
0x18000c362  jmp     loc_18000C69C
0x18000c367  lea     r8, [rbp+57h+var_30]; struct IXMLDOMNode **
0x18000c36b  lea     rdx, aEaptlsconnecti_15; "eaptlsconnectionpropertiesv1:SimpleCert"...
0x18000c372  mov     rcx, [rbp+57h+var_38]; struct IXMLDOMNode *
0x18000c376  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000c37b  test    eax, eax
0x18000c37d  jnz     short loc_18000C3DD
0x18000c37f  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18000c383  lea     rdx, [rbp+57h+arg_8]; bool *
0x18000c387  mov     rcx, [rbp+57h+var_30]; struct IXMLDOMNode *
0x18000c38b  call    ?ReadBOOLEANFromXMLNode@@YAJPEAUIXMLDOMNode@@PEA_NPEAPEAG@Z; ReadBOOLEANFromXMLNode(IXMLDOMNode *,bool *,ushort * *)
0x18000c390  test    eax, eax
0x18000c392  jz      short loc_18000C3C3
0x18000c394  mov     ebx, 0Dh
0x18000c399  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3a0  cmp     rcx, rdi
0x18000c3a3  jz      loc_18000C69C
0x18000c3a9  mov     edx, 0D3h
0x18000c3ae  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000c3b5  mov     rcx, [rcx+10h]
0x18000c3b9  call    WPP_SF_
0x18000c3be  jmp     loc_18000C69C
0x18000c3c3  cmp     [rbp+57h+arg_8], r14b
0x18000c3c7  jnz     short loc_18000C3CD
0x18000c3c9  and     [rbp+57h+arg_18], 0FFFFFFEFh
0x18000c3cd  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000c3d1  call    cs:__imp_SysFreeString
0x18000c3d7  mov     [rbp+57h+bstrString], r14
0x18000c3db  jmp     short loc_18000C41B
0x18000c3dd  cmp     eax, 8007000Eh
0x18000c3e2  jnz     short loc_18000C41B
0x18000c3e4  jmp     loc_18000C327
0x18000c3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3f0  cmp     rcx, rdi
0x18000c3f3  jz      short loc_18000C412
0x18000c3f5  mov     edx, 0FCh
0x18000c3fa  lea     r9, aEaptlsconnecti_4; "eaptlsconnectionpropertiesv1:Credential"...
0x18000c401  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000c408  mov     rcx, [rcx+10h]
0x18000c40c  call    WPP_SF_S
0x18000c411  nop
0x18000c412  mov     rcx, rbx; bstrString
0x18000c415  call    cs:__imp_SysFreeString
0x18000c41b  mov     r14, [rbp+57h+var_88]
0x18000c41f  lea     rcx, aEaptlsconnecti_19; "eaptlsconnectionpropertiesv1:DifferentU"...
0x18000c426  call    cs:__imp_SysAllocString
0x18000c42c  mov     rbx, rax
0x18000c42f  mov     [rbp+57h+lpString1], rax
0x18000c433  test    rax, rax
0x18000c436  jnz     short loc_18000C43E
0x18000c438  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c43e  mov     rax, [r14]
0x18000c441  lea     r8, [rbp+57h+var_60]
0x18000c445  mov     rdx, rbx
0x18000c448  mov     rcx, r14
0x18000c44b  mov     rax, [rax+128h]
0x18000c452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c457  xor     r14d, r14d
0x18000c45a  test    eax, eax
0x18000c45c  jnz     loc_18000C530
0x18000c462  cmp     [rbp+57h+var_60], r14
0x18000c466  jz      loc_18000C530
0x18000c46c  mov     rcx, rbx; bstrString
0x18000c46f  call    cs:__imp_SysFreeString
0x18000c475  mov     rcx, [rbp+57h+var_60]
0x18000c479  mov     [rbp+57h+lpString1], r14
0x18000c47d  mov     rax, [rcx]
0x18000c480  lea     rdx, [rbp+57h+lpString1]
0x18000c484  mov     rax, [rax+0D0h]
0x18000c48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c490  test    eax, eax
0x18000c492  jnz     short loc_18000C511
0x18000c494  lea     rdx, String2; "true"
0x18000c49b  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000c49f  call    cs:__imp_lstrcmpiW
0x18000c4a5  test    eax, eax
0x18000c4a7  jz      short loc_18000C4ED
0x18000c4a9  lea     rdx, a1; "1"
0x18000c4b0  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000c4b4  call    cs:__imp_lstrcmpiW
0x18000c4ba  test    eax, eax
0x18000c4bc  jz      short loc_18000C4ED
0x18000c4be  lea     rdx, aFalse; "false"
0x18000c4c5  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000c4c9  call    cs:__imp_lstrcmpiW
0x18000c4cf  test    eax, eax
0x18000c4d1  jz      short loc_18000C4E8
0x18000c4d3  lea     rdx, a0; "0"
0x18000c4da  mov     rcx, [rbp+57h+lpString1]; lpString1
0x18000c4de  call    cs:__imp_lstrcmpiW
0x18000c4e4  test    eax, eax
0x18000c4e6  jnz     short loc_18000C511
0x18000c4e8  mov     al, r14b
0x18000c4eb  jmp     short loc_18000C4EF
0x18000c4ed  mov     al, 1
0x18000c4ef  test    al, al
0x18000c4f1  mov     eax, [rbp+57h+arg_18]
0x18000c4f4  jz      short loc_18000C4FB
0x18000c4f6  or      eax, 8
0x18000c4f9  jmp     short loc_18000C4FE
0x18000c4fb  and     eax, 0FFFFFFF7h
0x18000c4fe  mov     [rbp+57h+arg_18], eax
0x18000c501  mov     rcx, [rbp+57h+lpString1]; bstrString
0x18000c505  call    cs:__imp_SysFreeString
0x18000c50b  mov     [rbp+57h+bstrString], r14
0x18000c50f  jmp     short loc_18000C562
0x18000c511  mov     ebx, 0Dh
0x18000c516  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c51d  cmp     rcx, rdi
0x18000c520  jz      loc_18000C69C
0x18000c526  mov     edx, 0D4h
0x18000c52b  jmp     loc_18000C3AE
0x18000c530  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c537  cmp     rcx, rdi
0x18000c53a  jz      short loc_18000C559
0x18000c53c  mov     edx, 0FCh
0x18000c541  lea     r9, aEaptlsconnecti_19; "eaptlsconnectionpropertiesv1:DifferentU"...
0x18000c548  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000c54f  mov     rcx, [rcx+10h]
0x18000c553  call    WPP_SF_S
0x18000c558  nop
0x18000c559  mov     rcx, rbx; bstrString
0x18000c55c  call    cs:__imp_SysFreeString
0x18000c562  shr     r12d, 19h
0x18000c566  and     r12b, 1
0x18000c56a  lea     rax, [rbp+57h+var_80+4]
0x18000c56e  mov     [rsp+0E0h+Size], rax; unsigned int *
0x18000c573  lea     rax, [rbp+57h+var_40]
0x18000c577  mov     [rsp+0E0h+var_B0], rax; unsigned __int16 **
0x18000c57c  lea     rax, [rbp+57h+var_78]
0x18000c580  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x18000c585  lea     rax, [rbp+57h+hMem]
0x18000c589  mov     [rsp+0E0h+var_C0], rax; struct _EAPTLS_HASH **
0x18000c58e  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x18000c592  mov     r8b, r12b; bool
0x18000c595  xor     edx, edx; bool
0x18000c597  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x18000c59b  call    ?ParseServerValidationNode@@YAKPEAUIXMLDOMNode@@_N1PEAKPEAPEAU_EAPTLS_HASH@@2PEAPEAG2@Z; ParseServerValidationNode(IXMLDOMNode *,bool,bool,ulong *,_EAPTLS_HASH * *,ulong *,ushort * *,ulong *)
0x18000c5a0  mov     ebx, eax
0x18000c5a2  test    eax, eax
0x18000c5a4  jnz     loc_18000C69C
0x18000c5aa  lea     r8, [rbp+57h+var_80]; unsigned int *
0x18000c5ae  lea     rdx, [rbp+57h+var_48]; unsigned __int8 **
0x18000c5b2  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x18000c5b6  call    ?ParseCertFilterNodes@@YAKPEAUIXMLDOMNode@@PEAPEAEPEAK@Z; ParseCertFilterNodes(IXMLDOMNode *,uchar * *,ulong *)
0x18000c5bb  mov     ebx, eax
0x18000c5bd  test    eax, eax
0x18000c5bf  jnz     loc_18000C69C
0x18000c5c5  mov     ecx, [rbp+57h+arg_18]
0x18000c5c8  test    cl, 1
0x18000c5cb  jnz     short loc_18000C5E7
0x18000c5cd  lea     rdx, [rbp+57h+arg_18]; unsigned int *
0x18000c5d1  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x18000c5d5  call    ?ParseGroupSmartCardCertNode@@YAKPEAUIXMLDOMNode@@PEAK@Z; ParseGroupSmartCardCertNode(IXMLDOMNode *,ulong *)
0x18000c5da  mov     ebx, eax
0x18000c5dc  test    eax, eax
0x18000c5de  jnz     loc_18000C69C
0x18000c5e4  mov     ecx, [rbp+57h+arg_18]; unsigned int
0x18000c5e7  mov     eax, dword ptr [rbp+57h+var_80]
0x18000c5ea  mov     rdx, [rbp+57h+var_48]; unsigned int
0x18000c5ee  mov     r9, [rbp+57h+var_40]
0x18000c5f2  mov     r10d, dword ptr [rbp+57h+var_80+4]
0x18000c5f6  mov     [rsp+0E0h+var_98], r14; unsigned int *
0x18000c5fb  lea     r8, [rbp+57h+var_58]
0x18000c5ff  mov     [rsp+0E0h+var_A0], r8; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x18000c604  mov     dword ptr [rsp+0E0h+Size], eax; Size
0x18000c608  mov     [rsp+0E0h+var_B0], rdx; unsigned __int8 *
0x18000c60d  mov     [rsp+0E0h+var_B8], r9; unsigned __int16 *
0x18000c612  mov     dword ptr [rsp+0E0h+var_C0], r10d; unsigned int
0x18000c617  mov     r9, [rbp+57h+hMem]; struct _EAPTLS_HASH *
0x18000c61b  mov     r8d, [rbp+57h+var_78]; unsigned int
0x18000c61f  call    ?FinishEapTlsConnProvV1@@YAKKKKPEAU_EAPTLS_HASH@@KPEAGPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAK@Z; FinishEapTlsConnProvV1(ulong,ulong,ulong,_EAPTLS_HASH *,ulong,ushort *,uchar *,ulong,_EAPTLS_CONN_PROPERTIES_V1 * *,ulong *)
0x18000c624  mov     ebx, eax
0x18000c626  test    eax, eax
0x18000c628  jnz     short loc_18000C637
0x18000c62a  mov     rax, [rbp+57h+var_58]
0x18000c62e  mov     [r13+0], rax
0x18000c632  mov     r15, r14
0x18000c635  jmp     short loc_18000C69C
0x18000c637  mov     r15, [rbp+57h+var_58]
0x18000c63b  jmp     short loc_18000C69C
0x18000c63d  lea     rdi, WPP_GLOBAL_Control
0x18000c644  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c64b  cmp     rcx, rdi
0x18000c64e  jz      short loc_18000C66D
0x18000c650  mov     edx, 0FCh
0x18000c655  lea     r9, aEaptlsconnecti_26; "eaptlsconnectionpropertiesv1:EapType[1]"
0x18000c65c  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000c663  mov     rcx, [rcx+10h]
0x18000c667  call    WPP_SF_S
0x18000c66c  nop
0x18000c66d  mov     rcx, rbx; bstrString
0x18000c670  call    cs:__imp_SysFreeString
0x18000c676  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c67d  cmp     rcx, rdi
0x18000c680  jz      short loc_18000C697
0x18000c682  mov     edx, 0D2h
0x18000c687  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000c68e  mov     rcx, [rcx+10h]
0x18000c692  call    WPP_SF_
0x18000c697  mov     ebx, 57h ; 'W'
0x18000c69c  mov     rcx, r15; hMem
0x18000c69f  call    cs:__imp_LocalFree
0x18000c6a5  mov     rcx, [rbp+57h+hMem]; hMem
0x18000c6a9  call    cs:__imp_LocalFree
0x18000c6af  mov     rcx, [rbp+57h+var_48]; hMem
  ... truncated ...
```
