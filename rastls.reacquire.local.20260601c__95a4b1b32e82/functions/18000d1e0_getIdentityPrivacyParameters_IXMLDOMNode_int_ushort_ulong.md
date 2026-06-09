# getIdentityPrivacyParameters(IXMLDOMNode *,int *,ushort * *,ulong *)

- ea: `0x18000d1e0`
- end: `0x18000d64c`
- name: `?getIdentityPrivacyParameters@@YAKPEAUIXMLDOMNode@@PEAHPEAPEAGPEAK@Z`
- size: `1132`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, int *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d660`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18000d1e0`
- `0x180010140`
- `0x1800104b0`
- `0x18001b4b0`
- `0x180021e74`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000d541`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000d541`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d220`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d284`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d370`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d220`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d284`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d370`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d26d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d33c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d498`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d4e1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d57f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d5f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d26d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d33c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d3e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d498`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d4e1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d57f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d5f8`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d555`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d555`

## string_xrefs

- `0x18000d219`: `mspeapconnectionpropertiesv1:PeapExtensions[1]`
- `0x18000d321`: `mspeapconnectionpropertiesv1:PeapExtensions[1]`

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
0x18000d1e0  mov     [rsp-38h+arg_0], rbx
0x18000d1e5  push    rbp
0x18000d1e6  push    rsi
0x18000d1e7  push    rdi
0x18000d1e8  push    r12
0x18000d1ea  push    r13
0x18000d1ec  push    r14
0x18000d1ee  push    r15
0x18000d1f0  mov     rbp, rsp
0x18000d1f3  sub     rsp, 40h
0x18000d1f7  mov     rsi, r9
0x18000d1fa  mov     r15, r8
0x18000d1fd  mov     r14, rdx
0x18000d200  mov     rdi, rcx
0x18000d203  xor     eax, eax
0x18000d205  mov     [rbp+arg_10], rax
0x18000d209  mov     [rbp+var_10], rax
0x18000d20d  mov     [rbp+lpString2], rax
0x18000d211  mov     [r8], rax
0x18000d214  mov     [r9], eax
0x18000d217  mov     [rdx], eax
0x18000d219  lea     rcx, aMspeapconnecti_18; "mspeapconnectionpropertiesv1:PeapExtens"...
0x18000d220  call    cs:__imp_SysAllocString
0x18000d227  nop     dword ptr [rax+rax+00h]
0x18000d22c  mov     rbx, rax
0x18000d22f  mov     [rbp+arg_8], rax
0x18000d233  test    rax, rax
0x18000d236  jnz     short loc_18000D23E
0x18000d238  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d23e  mov     rax, [rdi]
0x18000d241  lea     r8, [rbp+var_10]
0x18000d245  mov     rdx, rbx
0x18000d248  mov     rcx, rdi
0x18000d24b  mov     rax, [rax+128h]
0x18000d252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d257  test    eax, eax
0x18000d259  jnz     loc_18000D309
0x18000d25f  cmp     [rbp+var_10], 0
0x18000d264  jz      loc_18000D309
0x18000d26a  mov     rcx, rbx; bstrString
0x18000d26d  call    cs:__imp_SysFreeString
0x18000d274  nop     dword ptr [rax+rax+00h]
0x18000d279  mov     rdi, [rbp+var_10]
0x18000d27d  lea     rcx, aMspeapconnecti_16; "mspeapconnectionpropertiesv2:IdentityPr"...
0x18000d284  call    cs:__imp_SysAllocString
0x18000d28b  nop     dword ptr [rax+rax+00h]
0x18000d290  mov     rbx, rax
0x18000d293  mov     [rbp+arg_8], rax
0x18000d297  test    rax, rax
0x18000d29a  jnz     short loc_18000D2A2
0x18000d29c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d2a2  mov     r13b, 1
0x18000d2a5  mov     rax, [rdi]
0x18000d2a8  lea     r8, [rbp+arg_10]
0x18000d2ac  mov     rdx, rbx
0x18000d2af  mov     rcx, rdi
0x18000d2b2  mov     rax, [rax+128h]
0x18000d2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2be  mov     edi, eax
0x18000d2c0  lea     r12, WPP_GLOBAL_Control
0x18000d2c7  test    eax, eax
0x18000d2c9  jnz     short loc_18000D2D7
0x18000d2cb  cmp     [rbp+arg_10], 0
0x18000d2d0  jz      short loc_18000D2D7
0x18000d2d2  jmp     loc_18000D3E4
0x18000d2d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2de  cmp     rcx, r12
0x18000d2e1  jz      short loc_18000D2FF
0x18000d2e3  mov     edx, 0FCh
0x18000d2e8  lea     r9, aMspeapconnecti_16; "mspeapconnectionpropertiesv2:IdentityPr"...
0x18000d2ef  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000d2f6  mov     rcx, [rcx+10h]
0x18000d2fa  call    WPP_SF_S
0x18000d2ff  mov     edi, 80070057h
0x18000d304  jmp     loc_18000D3E4
0x18000d309  lea     r12, WPP_GLOBAL_Control
0x18000d310  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d317  cmp     rcx, r12
0x18000d31a  jz      short loc_18000D339
0x18000d31c  mov     edx, 0FCh
0x18000d321  lea     r9, aMspeapconnecti_18; "mspeapconnectionpropertiesv1:PeapExtens"...
0x18000d328  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000d32f  mov     rcx, [rcx+10h]
0x18000d333  call    WPP_SF_S
0x18000d338  nop
0x18000d339  mov     rcx, rbx; bstrString
0x18000d33c  call    cs:__imp_SysFreeString
0x18000d343  nop     dword ptr [rax+rax+00h]
0x18000d348  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d34f  cmp     rcx, r12
0x18000d352  jz      short loc_18000D369
0x18000d354  mov     edx, 0A6h
0x18000d359  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000d360  mov     rcx, [rcx+10h]
0x18000d364  call    WPP_SF_
0x18000d369  lea     rcx, aMspeapconnecti_2; "mspeapconnectionpropertiesv1:IdentityPr"...
0x18000d370  call    cs:__imp_SysAllocString
0x18000d377  nop     dword ptr [rax+rax+00h]
0x18000d37c  mov     rbx, rax
0x18000d37f  mov     [rbp+arg_8], rax
0x18000d383  test    rax, rax
0x18000d386  jnz     short loc_18000D38E
0x18000d388  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d38e  xor     r13b, r13b
0x18000d391  mov     rax, [rdi]
0x18000d394  lea     r8, [rbp+arg_10]
0x18000d398  mov     rdx, rbx
0x18000d39b  mov     rcx, rdi
0x18000d39e  mov     rax, [rax+128h]
0x18000d3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3aa  mov     edi, eax
0x18000d3ac  test    eax, eax
0x18000d3ae  jnz     short loc_18000D3B7
0x18000d3b0  cmp     [rbp+arg_10], 0
0x18000d3b5  jnz     short loc_18000D3E4
0x18000d3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3be  cmp     rcx, r12
0x18000d3c1  jz      short loc_18000D3DF
0x18000d3c3  mov     edx, 0FCh
0x18000d3c8  lea     r9, aMspeapconnecti_2; "mspeapconnectionpropertiesv1:IdentityPr"...
0x18000d3cf  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000d3d6  mov     rcx, [rcx+10h]
0x18000d3da  call    WPP_SF_S
0x18000d3df  mov     edi, 80070057h
0x18000d3e4  mov     rcx, rbx; bstrString
0x18000d3e7  call    cs:__imp_SysFreeString
0x18000d3ee  nop     dword ptr [rax+rax+00h]
0x18000d3f3  test    edi, edi
0x18000d3f5  jz      short loc_18000D40C
0x18000d3f7  mov     ebx, 0Eh
0x18000d3fc  xor     eax, eax
0x18000d3fe  cmp     edi, 8007000Eh
0x18000d404  cmovnz  ebx, eax
0x18000d407  jmp     loc_18000D5F4
0x18000d40c  mov     [rbp+var_20], 0
0x18000d414  mov     [rbp+arg_18], 0
0x18000d41c  mov     dword ptr [r14], 0
0x18000d423  lea     rax, aMspeapconnecti_7; "mspeapconnectionpropertiesv1:EnableIden"...
0x18000d42a  lea     rdx, aMspeapconnecti_6; "mspeapconnectionpropertiesv2:EnableIden"...
0x18000d431  test    r13b, r13b
0x18000d434  cmovz   rdx, rax; unsigned __int16 *
0x18000d438  lea     r8, [rbp+var_20]; struct IXMLDOMNode **
0x18000d43c  mov     rcx, [rbp+arg_10]; struct IXMLDOMNode *
0x18000d440  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000d445  test    eax, eax
0x18000d447  jnz     loc_18000D594
0x18000d44d  mov     byte ptr [rbp+arg_8], al
0x18000d450  mov     [rbp+bstrString], 0
0x18000d458  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18000d45c  lea     rdx, [rbp+arg_8]; bool *
0x18000d460  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x18000d464  call    ?ReadBOOLEANFromXMLNode@@YAJPEAUIXMLDOMNode@@PEA_NPEAPEAG@Z; ReadBOOLEANFromXMLNode(IXMLDOMNode *,bool *,ushort * *)
0x18000d469  test    eax, eax
0x18000d46b  jz      short loc_18000D4A9
0x18000d46d  mov     ebx, 0Dh
0x18000d472  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d479  cmp     rcx, r12
0x18000d47c  jz      short loc_18000D494
0x18000d47e  mov     edx, 0A7h
0x18000d483  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000d48a  mov     rcx, [rcx+10h]
0x18000d48e  call    WPP_SF_
0x18000d493  nop
0x18000d494  mov     rcx, [rbp+bstrString]; bstrString
0x18000d498  call    cs:__imp_SysFreeString
0x18000d49f  nop     dword ptr [rax+rax+00h]
0x18000d4a4  jmp     loc_18000D5E0
0x18000d4a9  movzx   eax, byte ptr [rbp+arg_8]
0x18000d4ad  test    al, al
0x18000d4af  jz      short loc_18000D4B8
0x18000d4b1  mov     dword ptr [r14], 1
0x18000d4b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4bf  cmp     rcx, r12
0x18000d4c2  jz      short loc_18000D4DD
0x18000d4c4  mov     r9d, eax
0x18000d4c7  mov     edx, 0A8h
0x18000d4cc  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000d4d3  mov     rcx, [rcx+10h]
0x18000d4d7  call    WPP_SF_d
0x18000d4dc  nop
0x18000d4dd  mov     rcx, [rbp+bstrString]; bstrString
0x18000d4e1  call    cs:__imp_SysFreeString
0x18000d4e8  nop     dword ptr [rax+rax+00h]
0x18000d4ed  xor     ebx, ebx
0x18000d4ef  lea     rax, aMspeapconnecti_17; "mspeapconnectionpropertiesv1:AnonymousU"...
0x18000d4f6  lea     rdx, aMspeapconnecti_11; "mspeapconnectionpropertiesv2:AnonymousU"...
0x18000d4fd  test    r13b, r13b
0x18000d500  cmovz   rdx, rax; unsigned __int16 *
0x18000d504  lea     r8, [rbp+arg_18]; struct IXMLDOMNode **
0x18000d508  mov     rcx, [rbp+arg_10]; struct IXMLDOMNode *
0x18000d50c  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000d511  mov     ecx, eax
0x18000d513  test    eax, eax
0x18000d515  jnz     loc_18000D5CE
0x18000d51b  mov     rcx, [rbp+arg_18]
0x18000d51f  mov     rax, [rcx]
0x18000d522  lea     rdx, [rbp+lpString2]
0x18000d526  mov     rax, [rax+0D0h]
0x18000d52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d532  test    eax, eax
0x18000d534  jnz     short loc_18000D5A6
0x18000d536  mov     rdx, [rbp+lpString2]; lpString2
0x18000d53a  lea     rcx, String; lpString1
0x18000d541  call    cs:__imp_lstrcmpW
0x18000d548  nop     dword ptr [rax+rax+00h]
0x18000d54d  test    eax, eax
0x18000d54f  jz      short loc_18000D5A6
0x18000d551  mov     rcx, [rbp+lpString2]; pbstr
0x18000d555  call    cs:__imp_SysStringLen
0x18000d55c  nop     dword ptr [rax+rax+00h]
0x18000d561  mov     [rsi], eax
0x18000d563  mov     rcx, [rbp+lpString2]; bstrString
0x18000d567  mov     [rbp+lpString2], rbx
0x18000d56b  mov     [r15], rcx
0x18000d56e  mov     r9d, [rsi]
0x18000d571  cmp     r9d, 100h
0x18000d578  jbe     short loc_18000D5AB
0x18000d57a  mov     ebx, 0Dh
0x18000d57f  call    cs:__imp_SysFreeString
0x18000d586  nop     dword ptr [rax+rax+00h]
0x18000d58b  mov     qword ptr [r15], 0
0x18000d592  jmp     short loc_18000D5E0
0x18000d594  cmp     eax, 8007000Eh
0x18000d599  jnz     loc_18000D4ED
0x18000d59f  mov     ebx, 0Eh
0x18000d5a4  jmp     short loc_18000D5E0
0x18000d5a6  mov     [rsi], ebx
0x18000d5a8  xor     r9d, r9d
0x18000d5ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5b2  cmp     rcx, r12
0x18000d5b5  jz      short loc_18000D5E0
0x18000d5b7  mov     edx, 0A9h
0x18000d5bc  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000d5c3  mov     rcx, [rcx+10h]
0x18000d5c7  call    WPP_SF_d
0x18000d5cc  jmp     short loc_18000D5E0
0x18000d5ce  mov     eax, ebx
0x18000d5d0  mov     ebx, 0Eh
0x18000d5d5  cmp     ecx, 8007000Eh
0x18000d5db  cmovz   eax, ebx
0x18000d5de  mov     ebx, eax
0x18000d5e0  lea     rcx, [rbp+arg_18]
0x18000d5e4  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000d5e9  nop
0x18000d5ea  lea     rcx, [rbp+var_20]
0x18000d5ee  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000d5f3  nop
0x18000d5f4  mov     rcx, [rbp+lpString2]; bstrString
0x18000d5f8  call    cs:__imp_SysFreeString
0x18000d5ff  nop     dword ptr [rax+rax+00h]
0x18000d604  nop
0x18000d605  mov     rcx, [rbp+var_10]
0x18000d609  test    rcx, rcx
0x18000d60c  jz      short loc_18000D61B
0x18000d60e  mov     rax, [rcx]
0x18000d611  mov     rax, [rax+10h]
0x18000d615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d61a  nop
0x18000d61b  mov     rcx, [rbp+arg_10]
0x18000d61f  test    rcx, rcx
0x18000d622  jz      short loc_18000D631
0x18000d624  mov     rax, [rcx]
0x18000d627  mov     rax, [rax+10h]
0x18000d62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d630  nop
0x18000d631  mov     eax, ebx
0x18000d633  mov     rbx, [rsp+40h+arg_0]
0x18000d63b  add     rsp, 40h
0x18000d63f  pop     r15
0x18000d641  pop     r14
0x18000d643  pop     r13
0x18000d645  pop     r12
0x18000d647  pop     rdi
0x18000d648  pop     rsi
0x18000d649  pop     rbp
0x18000d64a  retn
```
