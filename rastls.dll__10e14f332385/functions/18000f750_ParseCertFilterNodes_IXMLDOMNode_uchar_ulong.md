# ParseCertFilterNodes(IXMLDOMNode *,uchar * *,ulong *)

- ea: `0x18000f750`
- end: `0x18000ffa5`
- name: `?ParseCertFilterNodes@@YAKPEAUIXMLDOMNode@@PEAPEAEPEAK@Z`
- size: `2133`
- prototype: `unsigned int(struct IXMLDOMNode *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c1e0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f350`
- `0x18000f3b8`
- `0x18000f690`
- `0x18000f750`
- `0x18000ffe0`
- `0x180010030`
- `0x180019c80`
- `0x18001d4e0`
- `0x1800200b4`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fcf6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fcf6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f7df`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f837`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f8b0`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f9f7`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fade`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fbb3`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f7df`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f837`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f8b0`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f9f7`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fade`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fbb3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f826`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f87e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f8f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f98a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fa36`
- `OLEAUT32!__imp_SysFreeString` at `0x18000faac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fb1d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fb81`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fbf2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fc59`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fd09`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fe16`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fe40`
- `OLEAUT32!__imp_SysFreeString` at `0x18000febd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fee7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f826`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f87e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f8f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f98a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fa36`
- `OLEAUT32!__imp_SysFreeString` at `0x18000faac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fb1d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fb81`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fbf2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fc59`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fd09`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fe16`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fe40`
- `OLEAUT32!__imp_SysFreeString` at `0x18000febd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fee7`

## string_xrefs

- `0x18000f7d8`: `eaptlsconnectionpropertiesv2:TLSExtensions`
- `0x18000fea2`: `eaptlsconnectionpropertiesv2:TLSExtensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall ParseCertFilterNodes(struct IXMLDOMNode *a1, unsigned __int8 **a2, unsigned int *a3)
{
  OLECHAR *v6; // rdi
  BSTR v7; // rax
  int v8; // ecx
  OLECHAR *v9; // rbx
  __int64 v10; // rsi
  BSTR v11; // rax
  int v12; // ecx
  OLECHAR *v13; // rbx
  struct IXMLDOMNode *v14; // rsi
  BSTR v15; // rax
  int v16; // ecx
  OLECHAR *v17; // rbx
  unsigned int NewFilterBlob; // ebx
  char v19; // bl
  const wchar_t *v20; // r9
  struct IXMLDOMNode *v21; // rsi
  BSTR v22; // rax
  int v23; // ecx
  OLECHAR *v24; // rbx
  unsigned int EKUMaps; // eax
  struct _EAPTLS_CONTROL_BLOCK *v26; // rcx
  __int64 v27; // rdx
  struct IXMLDOMNode *v28; // rsi
  BSTR v29; // rax
  int v30; // ecx
  OLECHAR *v31; // rbx
  struct IXMLDOMNode *v32; // rsi
  BSTR v33; // rax
  int v34; // ecx
  OLECHAR *v35; // rbx
  int SingleNode; // eax
  struct IXMLDOMNode *v38; // [rsp+40h] [rbp-39h] BYREF
  struct IXMLDOMNode *v39; // [rsp+48h] [rbp-31h] BYREF
  struct IXMLDOMNode *v40; // [rsp+50h] [rbp-29h] BYREF
  __int64 v41; // [rsp+58h] [rbp-21h] BYREF
  struct IXMLDOMNode *v42; // [rsp+60h] [rbp-19h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-11h] BYREF
  HLOCAL hMem[2]; // [rsp+70h] [rbp-9h] BYREF
  HLOCAL v45[2]; // [rsp+80h] [rbp+7h]
  BSTR v46; // [rsp+90h] [rbp+17h]
  BSTR v47; // [rsp+E8h] [rbp+6Fh] BYREF
  struct IXMLDOMNode *v48; // [rsp+F0h] [rbp+77h] BYREF
  struct IXMLDOMNode *v49; // [rsp+F8h] [rbp+7Fh] BYREF

  v48 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  v49 = 0;
  v42 = 0;
  LOBYTE(v47) = 0;
  v6 = 0;
  bstrString = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v45 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  v7 = SysAllocString(L"eaptlsconnectionpropertiesv2:TLSExtensions");
  v9 = v7;
  v46 = v7;
  if ( !v7 )
    ATL::AtlThrowImpl(v8);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))a1->lpVtbl->selectSingleNode)(a1, v7, &v41)
    || !v41 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv2:TLSExtensions");
    SysFreeString(v9);
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    SysFreeString(0);
    if ( v42 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v42->lpVtbl->Release)(v42);
    if ( v49 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v49->lpVtbl->Release)(v49);
    if ( v38 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v38->lpVtbl->Release)(v38);
    if ( v39 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v39->lpVtbl->Release)(v39);
    if ( v40 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v40->lpVtbl->Release)(v40);
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    if ( v48 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v48->lpVtbl->Release)(v48);
    return 0;
  }
  SysFreeString(v9);
  v10 = v41;
  v11 = SysAllocString(L"eaptlsconnectionpropertiesv3:FilteringInfo");
  v13 = v11;
  v46 = v11;
  if ( !v11 )
    ATL::AtlThrowImpl(v12);
  if ( (*(unsigned int (__fastcall **)(__int64, BSTR, struct IXMLDOMNode **))(*(_QWORD *)v10 + 296LL))(v10, v11, &v48)
    || !v48 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv3:FilteringInfo");
    SysFreeString(v13);
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    SysFreeString(0);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v42);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v49);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v38);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v39);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v40);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v41);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v48);
    return 0;
  }
  SysFreeString(v13);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  v14 = v48;
  v15 = SysAllocString(L"eaptlsconnectionpropertiesv3:AllPurposeEnabled");
  v17 = v15;
  v46 = v15;
  if ( !v15 )
    ATL::AtlThrowImpl(v16);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))v14->lpVtbl->selectSingleNode)(
         v14,
         v15,
         &v40)
    || !v40 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv3:AllPurposeEnabled");
    SysFreeString(v17);
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  }
  else
  {
    SysFreeString(v17);
    if ( (unsigned int)ReadBOOLEANFromXMLNode(v40, (bool *)&v47, &bstrString) )
    {
      v6 = bstrString;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, bstrString);
      NewFilterBlob = 13;
      goto LABEL_72;
    }
    v19 = (char)v47;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v20 = L"TRUE";
      if ( !(_BYTE)v47 )
        v20 = L"FALSE";
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v20);
    }
    if ( v19 )
      LOWORD(hMem[0]) |= 8u;
    SysFreeString(bstrString);
    v6 = 0;
    bstrString = 0;
  }
  v21 = v48;
  v22 = SysAllocString(L"eaptlsconnectionpropertiesv3:CAHashList");
  v24 = v22;
  v47 = v22;
  if ( !v22 )
    ATL::AtlThrowImpl(v23);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))v21->lpVtbl->selectSingleNode)(
         v21,
         v22,
         &v39)
    || !v39 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv3:CAHashList");
    SysFreeString(v24);
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
LABEL_44:
    v28 = v48;
    v29 = SysAllocString(L"eaptlsconnectionpropertiesv3:EKUMapping");
    v31 = v29;
    v47 = v29;
    if ( !v29 )
      ATL::AtlThrowImpl(v30);
    if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))v28->lpVtbl->selectSingleNode)(
           v28,
           v29,
           &v38)
      || !v38 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          252,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          L"eaptlsconnectionpropertiesv3:EKUMapping");
      SysFreeString(v31);
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 204, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    }
    else
    {
      SysFreeString(v31);
      EKUMaps = ReadEKUMaps(v38, 0, 0, (struct _EAPTLS_FILTER_PROP *)hMem);
      NewFilterBlob = EKUMaps;
      if ( EKUMaps )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_72;
        v27 = 205;
        goto LABEL_39;
      }
    }
    v32 = v48;
    v33 = SysAllocString(L"eaptlsconnectionpropertiesv3:ClientAuthEKUList");
    v35 = v33;
    v47 = v33;
    if ( !v33 )
      ATL::AtlThrowImpl(v34);
    if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))v32->lpVtbl->selectSingleNode)(
           v32,
           v33,
           &v49)
      || !v49 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          252,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          L"eaptlsconnectionpropertiesv3:ClientAuthEKUList");
      SysFreeString(v35);
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 206, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    }
    else
    {
      SysFreeString(v35);
      EKUMaps = ReadEKUMaps(v49, 1, 0, (struct _EAPTLS_FILTER_PROP *)hMem);
      NewFilterBlob = EKUMaps;
      if ( EKUMaps )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_72;
        v27 = 207;
        goto LABEL_39;
      }
    }
    SingleNode = getSingleNode(v48, L"eaptlsconnectionpropertiesv3:AnyPurposeEKUList", &v42);
    if ( SingleNode )
    {
      if ( SingleNode == -2147024882 )
      {
        NewFilterBlob = 14;
        goto LABEL_72;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    }
    else
    {
      EKUMaps = ReadEKUMaps(v42, 0, 1, (struct _EAPTLS_FILTER_PROP *)hMem);
      NewFilterBlob = EKUMaps;
      if ( EKUMaps )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_72;
        v27 = 209;
        goto LABEL_39;
      }
    }
    NewFilterBlob = CreateNewFilterBlob(
                      (__int16)hMem[0],
                      (struct _EAPTLS_HASH *)hMem[1],
                      WORD1(hMem[0]),
                      (struct _EAPTLS_EKU_NODE *)v45[0],
                      0,
                      a2,
                      a3);
    goto LABEL_72;
  }
  SysFreeString(v24);
  EKUMaps = ReadCAHashListTags(v39, (struct _EAPTLS_FILTER_PROP *)hMem);
  NewFilterBlob = EKUMaps;
  if ( !EKUMaps )
    goto LABEL_44;
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v27 = 203;
LABEL_39:
    WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, EKUMaps);
  }
LABEL_72:
  LocalFree(hMem[1]);
  FreeEKUList(v45[0]);
  SysFreeString(v6);
  if ( v42 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v42->lpVtbl->Release)(v42);
  if ( v49 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v49->lpVtbl->Release)(v49);
  if ( v38 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v38->lpVtbl->Release)(v38);
  if ( v39 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v39->lpVtbl->Release)(v39);
  if ( v40 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v40->lpVtbl->Release)(v40);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v48 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v48->lpVtbl->Release)(v48);
  return NewFilterBlob;
}

```

## disassembly

```asm
0x18000f750  mov     [rsp-8+arg_0], rbx
0x18000f755  push    rbp
0x18000f756  push    rsi
0x18000f757  push    rdi
0x18000f758  push    r12
0x18000f75a  push    r13
0x18000f75c  push    r14
0x18000f75e  push    r15
0x18000f760  lea     rbp, [rsp-27h]
0x18000f765  sub     rsp, 0A0h
0x18000f76c  mov     r14, r8
0x18000f76f  mov     r15, rdx
0x18000f772  mov     rsi, rcx
0x18000f775  xor     r12d, r12d
0x18000f778  mov     [rbp+57h+arg_10], r12
0x18000f77c  mov     [rbp+57h+var_78], r12
0x18000f780  mov     [rbp+57h+var_80], r12
0x18000f784  mov     [rbp+57h+var_88], r12
0x18000f788  mov     [rbp+57h+var_90], r12
0x18000f78c  mov     [rbp+57h+arg_18], r12
0x18000f790  mov     [rbp+57h+var_70], r12
0x18000f794  mov     byte ptr [rbp+57h+arg_8], r12b
0x18000f798  mov     edi, r12d
0x18000f79b  mov     [rbp+57h+bstrString], r12
0x18000f79f  xorps   xmm0, xmm0
0x18000f7a2  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x18000f7a6  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18000f7aa  mov     [rdx], r12
0x18000f7ad  mov     [r8], r12d
0x18000f7b0  lea     r13, WPP_GLOBAL_Control
0x18000f7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7be  cmp     rcx, r13
0x18000f7c1  jz      short loc_18000F7D8
0x18000f7c3  mov     edx, 0C3h
0x18000f7c8  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000f7cf  mov     rcx, [rcx+10h]
0x18000f7d3  call    WPP_SF_
0x18000f7d8  lea     rcx, aEaptlsconnecti_22; "eaptlsconnectionpropertiesv2:TLSExtensi"...
0x18000f7df  call    cs:__imp_SysAllocString
0x18000f7e5  mov     rbx, rax
0x18000f7e8  mov     [rbp+57h+var_40], rax
0x18000f7ec  test    rax, rax
0x18000f7ef  jnz     short loc_18000F7F7
0x18000f7f1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f7f7  mov     rax, [rsi]
0x18000f7fa  lea     r8, [rbp+57h+var_78]
0x18000f7fe  mov     rdx, rbx
0x18000f801  mov     rcx, rsi
0x18000f804  mov     rax, [rax+128h]
0x18000f80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f810  test    eax, eax
0x18000f812  jnz     loc_18000FE91
0x18000f818  cmp     [rbp+57h+var_78], 0
0x18000f81d  jz      loc_18000FE91
0x18000f823  mov     rcx, rbx; bstrString
0x18000f826  call    cs:__imp_SysFreeString
0x18000f82c  mov     rsi, [rbp+57h+var_78]
0x18000f830  lea     rcx, aEaptlsconnecti_9; "eaptlsconnectionpropertiesv3:FilteringI"...
0x18000f837  call    cs:__imp_SysAllocString
0x18000f83d  mov     rbx, rax
0x18000f840  mov     [rbp+57h+var_40], rax
0x18000f844  test    rax, rax
0x18000f847  jnz     short loc_18000F84F
0x18000f849  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f84f  mov     rax, [rsi]
0x18000f852  lea     r8, [rbp+57h+arg_10]
0x18000f856  mov     rdx, rbx
0x18000f859  mov     rcx, rsi
0x18000f85c  mov     rax, [rax+128h]
0x18000f863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f868  test    eax, eax
0x18000f86a  jnz     loc_18000FDEA
0x18000f870  cmp     [rbp+57h+arg_10], 0
0x18000f875  jz      loc_18000FDEA
0x18000f87b  mov     rcx, rbx; bstrString
0x18000f87e  call    cs:__imp_SysFreeString
0x18000f884  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f88b  cmp     rcx, r13
0x18000f88e  jz      short loc_18000F8A5
0x18000f890  mov     edx, 0C6h
0x18000f895  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000f89c  mov     rcx, [rcx+10h]
0x18000f8a0  call    WPP_SF_
0x18000f8a5  mov     rsi, [rbp+57h+arg_10]
0x18000f8a9  lea     rcx, aEaptlsconnecti_10; "eaptlsconnectionpropertiesv3:AllPurpose"...
0x18000f8b0  call    cs:__imp_SysAllocString
0x18000f8b6  mov     rbx, rax
0x18000f8b9  mov     [rbp+57h+var_40], rax
0x18000f8bd  test    rax, rax
0x18000f8c0  jnz     short loc_18000F8C8
0x18000f8c2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f8c8  mov     rax, [rsi]
0x18000f8cb  lea     r8, [rbp+57h+var_80]
0x18000f8cf  mov     rdx, rbx
0x18000f8d2  mov     rcx, rsi
0x18000f8d5  mov     rax, [rax+128h]
0x18000f8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8e1  test    eax, eax
0x18000f8e3  jnz     loc_18000F999
0x18000f8e9  cmp     [rbp+57h+var_80], 0
0x18000f8ee  jz      loc_18000F999
0x18000f8f4  mov     rcx, rbx; bstrString
0x18000f8f7  call    cs:__imp_SysFreeString
0x18000f8fd  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18000f901  lea     rdx, [rbp+57h+arg_8]; bool *
0x18000f905  mov     rcx, [rbp+57h+var_80]; struct IXMLDOMNode *
0x18000f909  call    ?ReadBOOLEANFromXMLNode@@YAJPEAUIXMLDOMNode@@PEA_NPEAPEAG@Z; ReadBOOLEANFromXMLNode(IXMLDOMNode *,bool *,ushort * *)
0x18000f90e  test    eax, eax
0x18000f910  jz      short loc_18000F944
0x18000f912  mov     rdi, [rbp+57h+bstrString]
0x18000f916  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f91d  cmp     rcx, r13
0x18000f920  jz      short loc_18000F93A
0x18000f922  mov     edx, 0C8h
0x18000f927  mov     r9, rdi
0x18000f92a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000f931  mov     rcx, [rcx+10h]
0x18000f935  call    WPP_SF_S
0x18000f93a  mov     ebx, 0Dh
0x18000f93f  jmp     loc_18000FCF2
0x18000f944  movzx   ebx, byte ptr [rbp+57h+arg_8]
0x18000f948  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f94f  cmp     rcx, r13
0x18000f952  jz      short loc_18000F97D
0x18000f954  lea     r9, aTrue_1; "TRUE"
0x18000f95b  lea     rax, aFalse_1; "FALSE"
0x18000f962  test    bl, bl
0x18000f964  cmovz   r9, rax
0x18000f968  mov     edx, 0C9h
0x18000f96d  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000f974  mov     rcx, [rcx+10h]
0x18000f978  call    WPP_SF_S
0x18000f97d  test    bl, bl
0x18000f97f  jz      short loc_18000F986
0x18000f981  or      word ptr [rbp+57h+hMem], 8
0x18000f986  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000f98a  call    cs:__imp_SysFreeString
0x18000f990  mov     rdi, r12
0x18000f993  mov     [rbp+57h+bstrString], r12
0x18000f997  jmp     short loc_18000F9EC
0x18000f999  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9a0  cmp     rcx, r13
0x18000f9a3  jz      short loc_18000F9C2
0x18000f9a5  mov     edx, 0FCh
0x18000f9aa  lea     r9, aEaptlsconnecti_10; "eaptlsconnectionpropertiesv3:AllPurpose"...
0x18000f9b1  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000f9b8  mov     rcx, [rcx+10h]
0x18000f9bc  call    WPP_SF_S
0x18000f9c1  nop
0x18000f9c2  mov     rcx, rbx; bstrString
0x18000f9c5  call    cs:__imp_SysFreeString
0x18000f9cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9d2  cmp     rcx, r13
0x18000f9d5  jz      short loc_18000F9EC
0x18000f9d7  mov     edx, 0C7h
0x18000f9dc  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000f9e3  mov     rcx, [rcx+10h]
0x18000f9e7  call    WPP_SF_
0x18000f9ec  mov     rsi, [rbp+57h+arg_10]
0x18000f9f0  lea     rcx, aEaptlsconnecti_7; "eaptlsconnectionpropertiesv3:CAHashList"
0x18000f9f7  call    cs:__imp_SysAllocString
0x18000f9fd  mov     rbx, rax
0x18000fa00  mov     [rbp+57h+arg_8], rax
0x18000fa04  test    rax, rax
0x18000fa07  jnz     short loc_18000FA0F
0x18000fa09  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000fa0f  mov     rax, [rsi]
0x18000fa12  lea     r8, [rbp+57h+var_88]
0x18000fa16  mov     rdx, rbx
0x18000fa19  mov     rcx, rsi
0x18000fa1c  mov     rax, [rax+128h]
0x18000fa23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa28  test    eax, eax
0x18000fa2a  jnz     short loc_18000FA80
0x18000fa2c  cmp     [rbp+57h+var_88], 0
0x18000fa31  jz      short loc_18000FA80
0x18000fa33  mov     rcx, rbx; bstrString
0x18000fa36  call    cs:__imp_SysFreeString
0x18000fa3c  lea     rdx, [rbp+57h+hMem]; struct _EAPTLS_FILTER_PROP *
0x18000fa40  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x18000fa44  call    ?ReadCAHashListTags@@YAKPEAUIXMLDOMNode@@PEAU_EAPTLS_FILTER_PROP@@@Z; ReadCAHashListTags(IXMLDOMNode *,_EAPTLS_FILTER_PROP *)
0x18000fa49  mov     ebx, eax
0x18000fa4b  test    eax, eax
0x18000fa4d  jz      loc_18000FAD3
0x18000fa53  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa5a  cmp     rcx, r13
0x18000fa5d  jz      loc_18000FCF2
0x18000fa63  mov     edx, 0CBh
0x18000fa68  mov     r9d, eax
0x18000fa6b  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000fa72  mov     rcx, [rcx+10h]
0x18000fa76  call    WPP_SF_d
0x18000fa7b  jmp     loc_18000FCF2
0x18000fa80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa87  cmp     rcx, r13
0x18000fa8a  jz      short loc_18000FAA9
0x18000fa8c  mov     edx, 0FCh
0x18000fa91  lea     r9, aEaptlsconnecti_7; "eaptlsconnectionpropertiesv3:CAHashList"
0x18000fa98  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000fa9f  mov     rcx, [rcx+10h]
0x18000faa3  call    WPP_SF_S
0x18000faa8  nop
0x18000faa9  mov     rcx, rbx; bstrString
0x18000faac  call    cs:__imp_SysFreeString
0x18000fab2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fab9  cmp     rcx, r13
0x18000fabc  jz      short loc_18000FAD3
0x18000fabe  mov     edx, 0CAh
0x18000fac3  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000faca  mov     rcx, [rcx+10h]
0x18000face  call    WPP_SF_
0x18000fad3  mov     rsi, [rbp+57h+arg_10]
0x18000fad7  lea     rcx, aEaptlsconnecti_1; "eaptlsconnectionpropertiesv3:EKUMapping"
0x18000fade  call    cs:__imp_SysAllocString
0x18000fae4  mov     rbx, rax
0x18000fae7  mov     [rbp+57h+arg_8], rax
0x18000faeb  test    rax, rax
0x18000faee  jnz     short loc_18000FAF6
0x18000faf0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000faf6  mov     rax, [rsi]
0x18000faf9  lea     r8, [rbp+57h+var_90]
0x18000fafd  mov     rdx, rbx
0x18000fb00  mov     rcx, rsi
0x18000fb03  mov     rax, [rax+128h]
0x18000fb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb0f  test    eax, eax
0x18000fb11  jnz     short loc_18000FB55
0x18000fb13  cmp     [rbp+57h+var_90], 0
0x18000fb18  jz      short loc_18000FB55
0x18000fb1a  mov     rcx, rbx; bstrString
0x18000fb1d  call    cs:__imp_SysFreeString
0x18000fb23  lea     r9, [rbp+57h+hMem]; struct _EAPTLS_FILTER_PROP *
0x18000fb27  xor     r8d, r8d; int
0x18000fb2a  xor     edx, edx; int
0x18000fb2c  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x18000fb30  call    ?ReadEKUMaps@@YAKPEAUIXMLDOMNode@@HHPEAU_EAPTLS_FILTER_PROP@@@Z; ReadEKUMaps(IXMLDOMNode *,int,int,_EAPTLS_FILTER_PROP *)
0x18000fb35  mov     ebx, eax
0x18000fb37  test    eax, eax
0x18000fb39  jz      short loc_18000FBA8
0x18000fb3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb42  cmp     rcx, r13
0x18000fb45  jz      loc_18000FCF2
0x18000fb4b  mov     edx, 0CDh
0x18000fb50  jmp     loc_18000FA68
0x18000fb55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb5c  cmp     rcx, r13
0x18000fb5f  jz      short loc_18000FB7E
0x18000fb61  mov     edx, 0FCh
0x18000fb66  lea     r9, aEaptlsconnecti_1; "eaptlsconnectionpropertiesv3:EKUMapping"
0x18000fb6d  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000fb74  mov     rcx, [rcx+10h]
0x18000fb78  call    WPP_SF_S
0x18000fb7d  nop
0x18000fb7e  mov     rcx, rbx; bstrString
0x18000fb81  call    cs:__imp_SysFreeString
0x18000fb87  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb8e  cmp     rcx, r13
0x18000fb91  jz      short loc_18000FBA8
0x18000fb93  mov     edx, 0CCh
0x18000fb98  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000fb9f  mov     rcx, [rcx+10h]
0x18000fba3  call    WPP_SF_
0x18000fba8  mov     rsi, [rbp+57h+arg_10]
0x18000fbac  lea     rcx, aEaptlsconnecti_23; "eaptlsconnectionpropertiesv3:ClientAuth"...
0x18000fbb3  call    cs:__imp_SysAllocString
0x18000fbb9  mov     rbx, rax
0x18000fbbc  mov     [rbp+57h+arg_8], rax
0x18000fbc0  test    rax, rax
0x18000fbc3  jnz     short loc_18000FBCB
0x18000fbc5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000fbcb  mov     rax, [rsi]
0x18000fbce  lea     r8, [rbp+57h+arg_18]
0x18000fbd2  mov     rdx, rbx
0x18000fbd5  mov     rcx, rsi
0x18000fbd8  mov     rax, [rax+128h]
0x18000fbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbe4  test    eax, eax
0x18000fbe6  jnz     short loc_18000FC2D
0x18000fbe8  cmp     [rbp+57h+arg_18], 0
0x18000fbed  jz      short loc_18000FC2D
0x18000fbef  mov     rcx, rbx; bstrString
0x18000fbf2  call    cs:__imp_SysFreeString
0x18000fbf8  lea     r9, [rbp+57h+hMem]; struct _EAPTLS_FILTER_PROP *
0x18000fbfc  xor     r8d, r8d; int
0x18000fbff  mov     edx, 1; int
0x18000fc04  mov     rcx, [rbp+57h+arg_18]; struct IXMLDOMNode *
0x18000fc08  call    ?ReadEKUMaps@@YAKPEAUIXMLDOMNode@@HHPEAU_EAPTLS_FILTER_PROP@@@Z; ReadEKUMaps(IXMLDOMNode *,int,int,_EAPTLS_FILTER_PROP *)
0x18000fc0d  mov     ebx, eax
0x18000fc0f  test    eax, eax
0x18000fc11  jz      short loc_18000FC80
0x18000fc13  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc1a  cmp     rcx, r13
0x18000fc1d  jz      loc_18000FCF2
0x18000fc23  mov     edx, 0CFh
0x18000fc28  jmp     loc_18000FA68
0x18000fc2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc34  cmp     rcx, r13
0x18000fc37  jz      short loc_18000FC56
0x18000fc39  mov     edx, 0FCh
0x18000fc3e  lea     r9, aEaptlsconnecti_23; "eaptlsconnectionpropertiesv3:ClientAuth"...
  ... truncated ...
```
