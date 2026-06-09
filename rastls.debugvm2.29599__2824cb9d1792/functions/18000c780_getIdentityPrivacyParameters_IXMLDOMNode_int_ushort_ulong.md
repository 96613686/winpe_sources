# getIdentityPrivacyParameters(IXMLDOMNode *,int *,ushort * *,ulong *)

- ea: `0x18000c780`
- end: `0x18000cba3`
- name: `?getIdentityPrivacyParameters@@YAKPEAUIXMLDOMNode@@PEAHPEAPEAGPEAK@Z`
- size: `1059`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, int *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cbb0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000c780`
- `0x18000f350`
- `0x18000f690`
- `0x180019c80`
- `0x1800200b4`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000cab1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000cab1`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c7c0`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c818`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c8f8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c7c0`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c818`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c8f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c807`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c8ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c969`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ca14`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ca57`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cae3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb56`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c807`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c8ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c969`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ca14`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ca57`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cae3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb56`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cabf`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cabf`

## string_xrefs

- `0x18000c7b9`: `mspeapconnectionpropertiesv1:PeapExtensions[1]`
- `0x18000c8af`: `mspeapconnectionpropertiesv1:PeapExtensions[1]`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall getIdentityPrivacyParameters(
        struct IXMLDOMNode *a1,
        int *a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  BSTR v8; // rax
  int v9; // ecx
  OLECHAR *v10; // rbx
  __int64 v11; // rdi
  BSTR v12; // rax
  int v13; // ecx
  OLECHAR *v14; // rbx
  char v15; // r13
  int v16; // edi
  BSTR v17; // rax
  int v18; // ecx
  unsigned int v19; // ebx
  const unsigned __int16 *v20; // rdx
  int SingleNode; // eax
  unsigned int v22; // eax
  const unsigned __int16 *v23; // rdx
  int v24; // ecx
  unsigned __int16 *v25; // rcx
  __int64 v26; // r9
  int v27; // eax
  struct IXMLDOMNode *v29; // [rsp+20h] [rbp-20h] BYREF
  LPCWSTR lpString2; // [rsp+28h] [rbp-18h] BYREF
  __int64 v31; // [rsp+30h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-8h] BYREF
  BSTR v33; // [rsp+88h] [rbp+48h] BYREF
  struct IXMLDOMNode *v34; // [rsp+90h] [rbp+50h] BYREF
  struct IXMLDOMNode *v35; // [rsp+98h] [rbp+58h] BYREF

  v34 = 0;
  v31 = 0;
  lpString2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a2 = 0;
  v8 = SysAllocString(L"mspeapconnectionpropertiesv1:PeapExtensions[1]");
  v10 = v8;
  v33 = v8;
  if ( !v8 )
    ATL::AtlThrowImpl(v9);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))a1->lpVtbl->selectSingleNode)(a1, v8, &v31)
    || !v31 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"mspeapconnectionpropertiesv1:PeapExtensions[1]");
    SysFreeString(v10);
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    v17 = SysAllocString(L"mspeapconnectionpropertiesv1:IdentityPrivacy[1]");
    v14 = v17;
    v33 = v17;
    if ( !v17 )
      ATL::AtlThrowImpl(v18);
    v15 = 0;
    v16 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))a1->lpVtbl->selectSingleNode)(
            a1,
            v17,
            &v34);
    if ( v16 || !v34 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          252,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          L"mspeapconnectionpropertiesv1:IdentityPrivacy[1]");
      v16 = -2147024809;
    }
  }
  else
  {
    SysFreeString(v10);
    v11 = v31;
    v12 = SysAllocString(L"mspeapconnectionpropertiesv2:IdentityPrivacy[1]");
    v14 = v12;
    v33 = v12;
    if ( !v12 )
      ATL::AtlThrowImpl(v13);
    v15 = 1;
    v16 = (*(__int64 (__fastcall **)(__int64, BSTR, struct IXMLDOMNode **))(*(_QWORD *)v11 + 296LL))(v11, v12, &v34);
    if ( v16 || !v34 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          252,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          L"mspeapconnectionpropertiesv2:IdentityPrivacy[1]");
      v16 = -2147024809;
    }
  }
  SysFreeString(v14);
  if ( v16 )
  {
    v19 = 0;
    goto LABEL_53;
  }
  v29 = 0;
  v35 = 0;
  *a2 = 0;
  v20 = L"mspeapconnectionpropertiesv2:EnableIdentityPrivacy";
  if ( !v15 )
    v20 = L"mspeapconnectionpropertiesv1:EnableIdentityPrivacy";
  SingleNode = getSingleNode(v34, v20, &v29);
  if ( SingleNode )
  {
    if ( SingleNode == -2147024882 )
    {
      v19 = 14;
      goto LABEL_52;
    }
  }
  else
  {
    LOBYTE(v33) = 0;
    bstrString = 0;
    if ( (unsigned int)ReadBOOLEANFromXMLNode(v29, (bool *)&v33, &bstrString) )
    {
      v19 = 13;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      SysFreeString(bstrString);
      goto LABEL_52;
    }
    v22 = (unsigned __int8)v33;
    if ( (_BYTE)v33 )
      *a2 = 1;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v22);
    SysFreeString(bstrString);
  }
  v19 = 0;
  v23 = L"mspeapconnectionpropertiesv2:AnonymousUserName";
  if ( !v15 )
    v23 = L"mspeapconnectionpropertiesv1:AnonymousUserName";
  v24 = getSingleNode(v34, v23, &v35);
  if ( v24 )
  {
    v27 = 0;
    if ( v24 == -2147024882 )
      v27 = 14;
    v19 = v27;
    goto LABEL_52;
  }
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, LPCWSTR *))v35->lpVtbl->get_text)(v35, &lpString2)
    || !lstrcmpW(&String, lpString2) )
  {
    *a4 = 0;
    v26 = 0;
LABEL_47:
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v26);
    goto LABEL_52;
  }
  *a4 = SysStringLen((BSTR)lpString2);
  v25 = (unsigned __int16 *)lpString2;
  lpString2 = 0;
  *a3 = v25;
  v26 = *a4;
  if ( (unsigned int)v26 <= 0x100 )
    goto LABEL_47;
  v19 = 13;
  SysFreeString(v25);
  *a3 = 0;
LABEL_52:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v35);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v29);
LABEL_53:
  SysFreeString((BSTR)lpString2);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v34 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v34->lpVtbl->Release)(v34);
  return v19;
}

```

## disassembly

```asm
0x18000c780  mov     [rsp-38h+arg_0], rbx
0x18000c785  push    rbp
0x18000c786  push    rsi
0x18000c787  push    rdi
0x18000c788  push    r12
0x18000c78a  push    r13
0x18000c78c  push    r14
0x18000c78e  push    r15
0x18000c790  mov     rbp, rsp
0x18000c793  sub     rsp, 40h
0x18000c797  mov     rsi, r9
0x18000c79a  mov     r15, r8
0x18000c79d  mov     r14, rdx
0x18000c7a0  mov     rdi, rcx
0x18000c7a3  xor     eax, eax
0x18000c7a5  mov     [rbp+arg_10], rax
0x18000c7a9  mov     [rbp+var_10], rax
0x18000c7ad  mov     [rbp+lpString2], rax
0x18000c7b1  mov     [r8], rax
0x18000c7b4  mov     [r9], eax
0x18000c7b7  mov     [rdx], eax
0x18000c7b9  lea     rcx, aMspeapconnecti_18; "mspeapconnectionpropertiesv1:PeapExtens"...
0x18000c7c0  call    cs:__imp_SysAllocString
0x18000c7c6  mov     rbx, rax
0x18000c7c9  mov     [rbp+arg_8], rax
0x18000c7cd  test    rax, rax
0x18000c7d0  jnz     short loc_18000C7D8
0x18000c7d2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c7d8  mov     rax, [rdi]
0x18000c7db  lea     r8, [rbp+var_10]
0x18000c7df  mov     rdx, rbx
0x18000c7e2  mov     rcx, rdi
0x18000c7e5  mov     rax, [rax+128h]
0x18000c7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f1  test    eax, eax
0x18000c7f3  jnz     loc_18000C897
0x18000c7f9  cmp     [rbp+var_10], 0
0x18000c7fe  jz      loc_18000C897
0x18000c804  mov     rcx, rbx; bstrString
0x18000c807  call    cs:__imp_SysFreeString
0x18000c80d  mov     rdi, [rbp+var_10]
0x18000c811  lea     rcx, aMspeapconnecti_16; "mspeapconnectionpropertiesv2:IdentityPr"...
0x18000c818  call    cs:__imp_SysAllocString
0x18000c81e  mov     rbx, rax
0x18000c821  mov     [rbp+arg_8], rax
0x18000c825  test    rax, rax
0x18000c828  jnz     short loc_18000C830
0x18000c82a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c830  mov     r13b, 1
0x18000c833  mov     rax, [rdi]
0x18000c836  lea     r8, [rbp+arg_10]
0x18000c83a  mov     rdx, rbx
0x18000c83d  mov     rcx, rdi
0x18000c840  mov     rax, [rax+128h]
0x18000c847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c84c  mov     edi, eax
0x18000c84e  lea     r12, WPP_GLOBAL_Control
0x18000c855  test    eax, eax
0x18000c857  jnz     short loc_18000C865
0x18000c859  cmp     [rbp+arg_10], 0
0x18000c85e  jz      short loc_18000C865
0x18000c860  jmp     loc_18000C966
0x18000c865  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c86c  cmp     rcx, r12
0x18000c86f  jz      short loc_18000C88D
0x18000c871  mov     edx, 0FCh
0x18000c876  lea     r9, aMspeapconnecti_16; "mspeapconnectionpropertiesv2:IdentityPr"...
0x18000c87d  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000c884  mov     rcx, [rcx+10h]
0x18000c888  call    WPP_SF_S
0x18000c88d  mov     edi, 80070057h
0x18000c892  jmp     loc_18000C966
0x18000c897  lea     r12, WPP_GLOBAL_Control
0x18000c89e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8a5  cmp     rcx, r12
0x18000c8a8  jz      short loc_18000C8C7
0x18000c8aa  mov     edx, 0FCh
0x18000c8af  lea     r9, aMspeapconnecti_18; "mspeapconnectionpropertiesv1:PeapExtens"...
0x18000c8b6  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000c8bd  mov     rcx, [rcx+10h]
0x18000c8c1  call    WPP_SF_S
0x18000c8c6  nop
0x18000c8c7  mov     rcx, rbx; bstrString
0x18000c8ca  call    cs:__imp_SysFreeString
0x18000c8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8d7  cmp     rcx, r12
0x18000c8da  jz      short loc_18000C8F1
0x18000c8dc  mov     edx, 0A6h
0x18000c8e1  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000c8e8  mov     rcx, [rcx+10h]
0x18000c8ec  call    WPP_SF_
0x18000c8f1  lea     rcx, aMspeapconnecti_2; "mspeapconnectionpropertiesv1:IdentityPr"...
0x18000c8f8  call    cs:__imp_SysAllocString
0x18000c8fe  mov     rbx, rax
0x18000c901  mov     [rbp+arg_8], rax
0x18000c905  test    rax, rax
0x18000c908  jnz     short loc_18000C910
0x18000c90a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c910  xor     r13b, r13b
0x18000c913  mov     rax, [rdi]
0x18000c916  lea     r8, [rbp+arg_10]
0x18000c91a  mov     rdx, rbx
0x18000c91d  mov     rcx, rdi
0x18000c920  mov     rax, [rax+128h]
0x18000c927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c92c  mov     edi, eax
0x18000c92e  test    eax, eax
0x18000c930  jnz     short loc_18000C939
0x18000c932  cmp     [rbp+arg_10], 0
0x18000c937  jnz     short loc_18000C966
0x18000c939  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c940  cmp     rcx, r12
0x18000c943  jz      short loc_18000C961
0x18000c945  mov     edx, 0FCh
0x18000c94a  lea     r9, aMspeapconnecti_2; "mspeapconnectionpropertiesv1:IdentityPr"...
0x18000c951  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000c958  mov     rcx, [rcx+10h]
0x18000c95c  call    WPP_SF_S
0x18000c961  mov     edi, 80070057h
0x18000c966  mov     rcx, rbx; bstrString
0x18000c969  call    cs:__imp_SysFreeString
0x18000c96f  test    edi, edi
0x18000c971  jz      short loc_18000C988
0x18000c973  mov     ebx, 0Eh
0x18000c978  xor     eax, eax
0x18000c97a  cmp     edi, 8007000Eh
0x18000c980  cmovnz  ebx, eax
0x18000c983  jmp     loc_18000CB52
0x18000c988  mov     [rbp+var_20], 0
0x18000c990  mov     [rbp+arg_18], 0
0x18000c998  mov     dword ptr [r14], 0
0x18000c99f  lea     rax, aMspeapconnecti_7; "mspeapconnectionpropertiesv1:EnableIden"...
0x18000c9a6  lea     rdx, aMspeapconnecti_6; "mspeapconnectionpropertiesv2:EnableIden"...
0x18000c9ad  test    r13b, r13b
0x18000c9b0  cmovz   rdx, rax; unsigned __int16 *
0x18000c9b4  lea     r8, [rbp+var_20]; struct IXMLDOMNode **
0x18000c9b8  mov     rcx, [rbp+arg_10]; struct IXMLDOMNode *
0x18000c9bc  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000c9c1  test    eax, eax
0x18000c9c3  jnz     loc_18000CAF2
0x18000c9c9  mov     byte ptr [rbp+arg_8], al
0x18000c9cc  mov     [rbp+bstrString], 0
0x18000c9d4  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18000c9d8  lea     rdx, [rbp+arg_8]; bool *
0x18000c9dc  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x18000c9e0  call    ?ReadBOOLEANFromXMLNode@@YAJPEAUIXMLDOMNode@@PEA_NPEAPEAG@Z; ReadBOOLEANFromXMLNode(IXMLDOMNode *,bool *,ushort * *)
0x18000c9e5  test    eax, eax
0x18000c9e7  jz      short loc_18000CA1F
0x18000c9e9  mov     ebx, 0Dh
0x18000c9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9f5  cmp     rcx, r12
0x18000c9f8  jz      short loc_18000CA10
0x18000c9fa  mov     edx, 0A7h
0x18000c9ff  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000ca06  mov     rcx, [rcx+10h]
0x18000ca0a  call    WPP_SF_
0x18000ca0f  nop
0x18000ca10  mov     rcx, [rbp+bstrString]; bstrString
0x18000ca14  call    cs:__imp_SysFreeString
0x18000ca1a  jmp     loc_18000CB3E
0x18000ca1f  movzx   eax, byte ptr [rbp+arg_8]
0x18000ca23  test    al, al
0x18000ca25  jz      short loc_18000CA2E
0x18000ca27  mov     dword ptr [r14], 1
0x18000ca2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca35  cmp     rcx, r12
0x18000ca38  jz      short loc_18000CA53
0x18000ca3a  mov     r9d, eax
0x18000ca3d  mov     edx, 0A8h
0x18000ca42  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000ca49  mov     rcx, [rcx+10h]
0x18000ca4d  call    WPP_SF_d
0x18000ca52  nop
0x18000ca53  mov     rcx, [rbp+bstrString]; bstrString
0x18000ca57  call    cs:__imp_SysFreeString
0x18000ca5d  xor     ebx, ebx
0x18000ca5f  lea     rax, aMspeapconnecti_17; "mspeapconnectionpropertiesv1:AnonymousU"...
0x18000ca66  lea     rdx, aMspeapconnecti_11; "mspeapconnectionpropertiesv2:AnonymousU"...
0x18000ca6d  test    r13b, r13b
0x18000ca70  cmovz   rdx, rax; unsigned __int16 *
0x18000ca74  lea     r8, [rbp+arg_18]; struct IXMLDOMNode **
0x18000ca78  mov     rcx, [rbp+arg_10]; struct IXMLDOMNode *
0x18000ca7c  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000ca81  mov     ecx, eax
0x18000ca83  test    eax, eax
0x18000ca85  jnz     loc_18000CB2C
0x18000ca8b  mov     rcx, [rbp+arg_18]
0x18000ca8f  mov     rax, [rcx]
0x18000ca92  lea     rdx, [rbp+lpString2]
0x18000ca96  mov     rax, [rax+0D0h]
0x18000ca9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caa2  test    eax, eax
0x18000caa4  jnz     short loc_18000CB04
0x18000caa6  mov     rdx, [rbp+lpString2]; lpString2
0x18000caaa  lea     rcx, String; lpString1
0x18000cab1  call    cs:__imp_lstrcmpW
0x18000cab7  test    eax, eax
0x18000cab9  jz      short loc_18000CB04
0x18000cabb  mov     rcx, [rbp+lpString2]; pbstr
0x18000cabf  call    cs:__imp_SysStringLen
0x18000cac5  mov     [rsi], eax
0x18000cac7  mov     rcx, [rbp+lpString2]; bstrString
0x18000cacb  mov     [rbp+lpString2], rbx
0x18000cacf  mov     [r15], rcx
0x18000cad2  mov     r9d, [rsi]
0x18000cad5  cmp     r9d, 100h
0x18000cadc  jbe     short loc_18000CB09
0x18000cade  mov     ebx, 0Dh
0x18000cae3  call    cs:__imp_SysFreeString
0x18000cae9  mov     qword ptr [r15], 0
0x18000caf0  jmp     short loc_18000CB3E
0x18000caf2  cmp     eax, 8007000Eh
0x18000caf7  jnz     loc_18000CA5D
0x18000cafd  mov     ebx, 0Eh
0x18000cb02  jmp     short loc_18000CB3E
0x18000cb04  mov     [rsi], ebx
0x18000cb06  xor     r9d, r9d
0x18000cb09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb10  cmp     rcx, r12
0x18000cb13  jz      short loc_18000CB3E
0x18000cb15  mov     edx, 0A9h
0x18000cb1a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000cb21  mov     rcx, [rcx+10h]
0x18000cb25  call    WPP_SF_d
0x18000cb2a  jmp     short loc_18000CB3E
0x18000cb2c  mov     eax, ebx
0x18000cb2e  mov     ebx, 0Eh
0x18000cb33  cmp     ecx, 8007000Eh
0x18000cb39  cmovz   eax, ebx
0x18000cb3c  mov     ebx, eax
0x18000cb3e  lea     rcx, [rbp+arg_18]
0x18000cb42  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000cb47  nop
0x18000cb48  lea     rcx, [rbp+var_20]
0x18000cb4c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000cb51  nop
0x18000cb52  mov     rcx, [rbp+lpString2]; bstrString
0x18000cb56  call    cs:__imp_SysFreeString
0x18000cb5c  nop
0x18000cb5d  mov     rcx, [rbp+var_10]
0x18000cb61  test    rcx, rcx
0x18000cb64  jz      short loc_18000CB73
0x18000cb66  mov     rax, [rcx]
0x18000cb69  mov     rax, [rax+10h]
0x18000cb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb72  nop
0x18000cb73  mov     rcx, [rbp+arg_10]
0x18000cb77  test    rcx, rcx
0x18000cb7a  jz      short loc_18000CB89
0x18000cb7c  mov     rax, [rcx]
0x18000cb7f  mov     rax, [rax+10h]
0x18000cb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb88  nop
0x18000cb89  mov     eax, ebx
0x18000cb8b  mov     rbx, [rsp+40h+arg_0]
0x18000cb93  add     rsp, 40h
0x18000cb97  pop     r15
0x18000cb99  pop     r14
0x18000cb9b  pop     r13
0x18000cb9d  pop     r12
0x18000cb9f  pop     rdi
0x18000cba0  pop     rsi
0x18000cba1  pop     rbp
0x18000cba2  retn
```
