# ParseCertFilterNodes(IXMLDOMNode *,uchar * *,ulong *)

- ea: `0x180010580`
- end: `0x180010e60`
- name: `?ParseCertFilterNodes@@YAKPEAUIXMLDOMNode@@PEAPEAEPEAK@Z`
- size: `2272`
- prototype: `unsigned int(struct IXMLDOMNode *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cbc4`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180010140`
- `0x1800101b0`
- `0x1800104b0`
- `0x180010580`
- `0x180010ea4`
- `0x180010f10`
- `0x18001b4b0`
- `0x18001f0b0`
- `0x180021e74`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b8c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001060f`
- `OLEAUT32!__imp_SysAllocString` at `0x180010673`
- `OLEAUT32!__imp_SysAllocString` at `0x1800106f8`
- `OLEAUT32!__imp_SysAllocString` at `0x180010857`
- `OLEAUT32!__imp_SysAllocString` at `0x180010950`
- `OLEAUT32!__imp_SysAllocString` at `0x180010a37`
- `OLEAUT32!__imp_SysAllocString` at `0x18001060f`
- `OLEAUT32!__imp_SysAllocString` at `0x180010673`
- `OLEAUT32!__imp_SysAllocString` at `0x1800106f8`
- `OLEAUT32!__imp_SysAllocString` at `0x180010857`
- `OLEAUT32!__imp_SysAllocString` at `0x180010950`
- `OLEAUT32!__imp_SysAllocString` at `0x180010a37`
- `OLEAUT32!__imp_SysFreeString` at `0x18001065c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800106c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180010745`
- `OLEAUT32!__imp_SysFreeString` at `0x1800107de`
- `OLEAUT32!__imp_SysFreeString` at `0x18001081f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001089c`
- `OLEAUT32!__imp_SysFreeString` at `0x180010918`
- `OLEAUT32!__imp_SysFreeString` at `0x180010995`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109ff`
- `OLEAUT32!__imp_SysFreeString` at `0x180010a7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180010ae9`
- `OLEAUT32!__imp_SysFreeString` at `0x180010ba5`
- `OLEAUT32!__imp_SysFreeString` at `0x180010cb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180010ce8`
- `OLEAUT32!__imp_SysFreeString` at `0x180010d6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180010d9b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001065c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800106c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180010745`
- `OLEAUT32!__imp_SysFreeString` at `0x1800107de`
- `OLEAUT32!__imp_SysFreeString` at `0x18001081f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001089c`
- `OLEAUT32!__imp_SysFreeString` at `0x180010918`
- `OLEAUT32!__imp_SysFreeString` at `0x180010995`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109ff`
- `OLEAUT32!__imp_SysFreeString` at `0x180010a7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180010ae9`
- `OLEAUT32!__imp_SysFreeString` at `0x180010ba5`
- `OLEAUT32!__imp_SysFreeString` at `0x180010cb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180010ce8`
- `OLEAUT32!__imp_SysFreeString` at `0x180010d6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180010d9b`

## string_xrefs

- `0x180010608`: `eaptlsconnectionpropertiesv2:TLSExtensions`
- `0x180010d50`: `eaptlsconnectionpropertiesv2:TLSExtensions`

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
                      (unsigned __int16)hMem[0],
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
0x180010580  mov     [rsp-8+arg_0], rbx
0x180010585  push    rbp
0x180010586  push    rsi
0x180010587  push    rdi
0x180010588  push    r12
0x18001058a  push    r13
0x18001058c  push    r14
0x18001058e  push    r15
0x180010590  lea     rbp, [rsp-27h]
0x180010595  sub     rsp, 0A0h
0x18001059c  mov     r14, r8
0x18001059f  mov     r15, rdx
0x1800105a2  mov     rsi, rcx
0x1800105a5  xor     r12d, r12d
0x1800105a8  mov     [rbp+57h+arg_10], r12
0x1800105ac  mov     [rbp+57h+var_78], r12
0x1800105b0  mov     [rbp+57h+var_80], r12
0x1800105b4  mov     [rbp+57h+var_88], r12
0x1800105b8  mov     [rbp+57h+var_90], r12
0x1800105bc  mov     [rbp+57h+arg_18], r12
0x1800105c0  mov     [rbp+57h+var_70], r12
0x1800105c4  mov     byte ptr [rbp+57h+arg_8], r12b
0x1800105c8  mov     edi, r12d
0x1800105cb  mov     [rbp+57h+bstrString], r12
0x1800105cf  xorps   xmm0, xmm0
0x1800105d2  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x1800105d6  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800105da  mov     [rdx], r12
0x1800105dd  mov     [r8], r12d
0x1800105e0  lea     r13, WPP_GLOBAL_Control
0x1800105e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105ee  cmp     rcx, r13
0x1800105f1  jz      short loc_180010608
0x1800105f3  mov     edx, 0C3h
0x1800105f8  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800105ff  mov     rcx, [rcx+10h]
0x180010603  call    WPP_SF_
0x180010608  lea     rcx, aEaptlsconnecti_22; "eaptlsconnectionpropertiesv2:TLSExtensi"...
0x18001060f  call    cs:__imp_SysAllocString
0x180010616  nop     dword ptr [rax+rax+00h]
0x18001061b  mov     rbx, rax
0x18001061e  mov     [rbp+57h+var_40], rax
0x180010622  test    rax, rax
0x180010625  jnz     short loc_18001062D
0x180010627  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001062d  mov     rax, [rsi]
0x180010630  lea     r8, [rbp+57h+var_78]
0x180010634  mov     rdx, rbx
0x180010637  mov     rcx, rsi
0x18001063a  mov     rax, [rax+128h]
0x180010641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010646  test    eax, eax
0x180010648  jnz     loc_180010D3F
0x18001064e  cmp     [rbp+57h+var_78], 0
0x180010653  jz      loc_180010D3F
0x180010659  mov     rcx, rbx; bstrString
0x18001065c  call    cs:__imp_SysFreeString
0x180010663  nop     dword ptr [rax+rax+00h]
0x180010668  mov     rsi, [rbp+57h+var_78]
0x18001066c  lea     rcx, aEaptlsconnecti_9; "eaptlsconnectionpropertiesv3:FilteringI"...
0x180010673  call    cs:__imp_SysAllocString
0x18001067a  nop     dword ptr [rax+rax+00h]
0x18001067f  mov     rbx, rax
0x180010682  mov     [rbp+57h+var_40], rax
0x180010686  test    rax, rax
0x180010689  jnz     short loc_180010691
0x18001068b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010691  mov     rax, [rsi]
0x180010694  lea     r8, [rbp+57h+arg_10]
0x180010698  mov     rdx, rbx
0x18001069b  mov     rcx, rsi
0x18001069e  mov     rax, [rax+128h]
0x1800106a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106aa  test    eax, eax
0x1800106ac  jnz     loc_180010C8C
0x1800106b2  cmp     [rbp+57h+arg_10], 0
0x1800106b7  jz      loc_180010C8C
0x1800106bd  mov     rcx, rbx; bstrString
0x1800106c0  call    cs:__imp_SysFreeString
0x1800106c7  nop     dword ptr [rax+rax+00h]
0x1800106cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106d3  cmp     rcx, r13
0x1800106d6  jz      short loc_1800106ED
0x1800106d8  mov     edx, 0C6h
0x1800106dd  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800106e4  mov     rcx, [rcx+10h]
0x1800106e8  call    WPP_SF_
0x1800106ed  mov     rsi, [rbp+57h+arg_10]
0x1800106f1  lea     rcx, aEaptlsconnecti_10; "eaptlsconnectionpropertiesv3:AllPurpose"...
0x1800106f8  call    cs:__imp_SysAllocString
0x1800106ff  nop     dword ptr [rax+rax+00h]
0x180010704  mov     rbx, rax
0x180010707  mov     [rbp+57h+var_40], rax
0x18001070b  test    rax, rax
0x18001070e  jnz     short loc_180010716
0x180010710  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010716  mov     rax, [rsi]
0x180010719  lea     r8, [rbp+57h+var_80]
0x18001071d  mov     rdx, rbx
0x180010720  mov     rcx, rsi
0x180010723  mov     rax, [rax+128h]
0x18001072a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001072f  test    eax, eax
0x180010731  jnz     loc_1800107F3
0x180010737  cmp     [rbp+57h+var_80], 0
0x18001073c  jz      loc_1800107F3
0x180010742  mov     rcx, rbx; bstrString
0x180010745  call    cs:__imp_SysFreeString
0x18001074c  nop     dword ptr [rax+rax+00h]
0x180010751  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x180010755  lea     rdx, [rbp+57h+arg_8]; bool *
0x180010759  mov     rcx, [rbp+57h+var_80]; struct IXMLDOMNode *
0x18001075d  call    ?ReadBOOLEANFromXMLNode@@YAJPEAUIXMLDOMNode@@PEA_NPEAPEAG@Z; ReadBOOLEANFromXMLNode(IXMLDOMNode *,bool *,ushort * *)
0x180010762  test    eax, eax
0x180010764  jz      short loc_180010798
0x180010766  mov     rdi, [rbp+57h+bstrString]
0x18001076a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010771  cmp     rcx, r13
0x180010774  jz      short loc_18001078E
0x180010776  mov     edx, 0C8h
0x18001077b  mov     r9, rdi
0x18001077e  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180010785  mov     rcx, [rcx+10h]
0x180010789  call    WPP_SF_S
0x18001078e  mov     ebx, 0Dh
0x180010793  jmp     loc_180010B88
0x180010798  movzx   ebx, byte ptr [rbp+57h+arg_8]
0x18001079c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107a3  cmp     rcx, r13
0x1800107a6  jz      short loc_1800107D1
0x1800107a8  lea     r9, aTrue_1; "TRUE"
0x1800107af  lea     rax, aFalse_1; "FALSE"
0x1800107b6  test    bl, bl
0x1800107b8  cmovz   r9, rax
0x1800107bc  mov     edx, 0C9h
0x1800107c1  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800107c8  mov     rcx, [rcx+10h]
0x1800107cc  call    WPP_SF_S
0x1800107d1  test    bl, bl
0x1800107d3  jz      short loc_1800107DA
0x1800107d5  or      word ptr [rbp+57h+hMem], 8
0x1800107da  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800107de  call    cs:__imp_SysFreeString
0x1800107e5  nop     dword ptr [rax+rax+00h]
0x1800107ea  mov     rdi, r12
0x1800107ed  mov     [rbp+57h+bstrString], r12
0x1800107f1  jmp     short loc_18001084C
0x1800107f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107fa  cmp     rcx, r13
0x1800107fd  jz      short loc_18001081C
0x1800107ff  mov     edx, 0FCh
0x180010804  lea     r9, aEaptlsconnecti_10; "eaptlsconnectionpropertiesv3:AllPurpose"...
0x18001080b  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180010812  mov     rcx, [rcx+10h]
0x180010816  call    WPP_SF_S
0x18001081b  nop
0x18001081c  mov     rcx, rbx; bstrString
0x18001081f  call    cs:__imp_SysFreeString
0x180010826  nop     dword ptr [rax+rax+00h]
0x18001082b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010832  cmp     rcx, r13
0x180010835  jz      short loc_18001084C
0x180010837  mov     edx, 0C7h
0x18001083c  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180010843  mov     rcx, [rcx+10h]
0x180010847  call    WPP_SF_
0x18001084c  mov     rsi, [rbp+57h+arg_10]
0x180010850  lea     rcx, aEaptlsconnecti_7; "eaptlsconnectionpropertiesv3:CAHashList"
0x180010857  call    cs:__imp_SysAllocString
0x18001085e  nop     dword ptr [rax+rax+00h]
0x180010863  mov     rbx, rax
0x180010866  mov     [rbp+57h+arg_8], rax
0x18001086a  test    rax, rax
0x18001086d  jnz     short loc_180010875
0x18001086f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010875  mov     rax, [rsi]
0x180010878  lea     r8, [rbp+57h+var_88]
0x18001087c  mov     rdx, rbx
0x18001087f  mov     rcx, rsi
0x180010882  mov     rax, [rax+128h]
0x180010889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001088e  test    eax, eax
0x180010890  jnz     short loc_1800108EC
0x180010892  cmp     [rbp+57h+var_88], 0
0x180010897  jz      short loc_1800108EC
0x180010899  mov     rcx, rbx; bstrString
0x18001089c  call    cs:__imp_SysFreeString
0x1800108a3  nop     dword ptr [rax+rax+00h]
0x1800108a8  lea     rdx, [rbp+57h+hMem]; struct _EAPTLS_FILTER_PROP *
0x1800108ac  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x1800108b0  call    ?ReadCAHashListTags@@YAKPEAUIXMLDOMNode@@PEAU_EAPTLS_FILTER_PROP@@@Z; ReadCAHashListTags(IXMLDOMNode *,_EAPTLS_FILTER_PROP *)
0x1800108b5  mov     ebx, eax
0x1800108b7  test    eax, eax
0x1800108b9  jz      loc_180010945
0x1800108bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108c6  cmp     rcx, r13
0x1800108c9  jz      loc_180010B88
0x1800108cf  mov     edx, 0CBh
0x1800108d4  mov     r9d, eax
0x1800108d7  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800108de  mov     rcx, [rcx+10h]
0x1800108e2  call    WPP_SF_d
0x1800108e7  jmp     loc_180010B88
0x1800108ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108f3  cmp     rcx, r13
0x1800108f6  jz      short loc_180010915
0x1800108f8  mov     edx, 0FCh
0x1800108fd  lea     r9, aEaptlsconnecti_7; "eaptlsconnectionpropertiesv3:CAHashList"
0x180010904  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001090b  mov     rcx, [rcx+10h]
0x18001090f  call    WPP_SF_S
0x180010914  nop
0x180010915  mov     rcx, rbx; bstrString
0x180010918  call    cs:__imp_SysFreeString
0x18001091f  nop     dword ptr [rax+rax+00h]
0x180010924  mov     rcx, cs:WPP_GLOBAL_Control
0x18001092b  cmp     rcx, r13
0x18001092e  jz      short loc_180010945
0x180010930  mov     edx, 0CAh
0x180010935  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001093c  mov     rcx, [rcx+10h]
0x180010940  call    WPP_SF_
0x180010945  mov     rsi, [rbp+57h+arg_10]
0x180010949  lea     rcx, aEaptlsconnecti_1; "eaptlsconnectionpropertiesv3:EKUMapping"
0x180010950  call    cs:__imp_SysAllocString
0x180010957  nop     dword ptr [rax+rax+00h]
0x18001095c  mov     rbx, rax
0x18001095f  mov     [rbp+57h+arg_8], rax
0x180010963  test    rax, rax
0x180010966  jnz     short loc_18001096E
0x180010968  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001096e  mov     rax, [rsi]
0x180010971  lea     r8, [rbp+57h+var_90]
0x180010975  mov     rdx, rbx
0x180010978  mov     rcx, rsi
0x18001097b  mov     rax, [rax+128h]
0x180010982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010987  test    eax, eax
0x180010989  jnz     short loc_1800109D3
0x18001098b  cmp     [rbp+57h+var_90], 0
0x180010990  jz      short loc_1800109D3
0x180010992  mov     rcx, rbx; bstrString
0x180010995  call    cs:__imp_SysFreeString
0x18001099c  nop     dword ptr [rax+rax+00h]
0x1800109a1  lea     r9, [rbp+57h+hMem]; struct _EAPTLS_FILTER_PROP *
0x1800109a5  xor     r8d, r8d; int
0x1800109a8  xor     edx, edx; int
0x1800109aa  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x1800109ae  call    ?ReadEKUMaps@@YAKPEAUIXMLDOMNode@@HHPEAU_EAPTLS_FILTER_PROP@@@Z; ReadEKUMaps(IXMLDOMNode *,int,int,_EAPTLS_FILTER_PROP *)
0x1800109b3  mov     ebx, eax
0x1800109b5  test    eax, eax
0x1800109b7  jz      short loc_180010A2C
0x1800109b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109c0  cmp     rcx, r13
0x1800109c3  jz      loc_180010B88
0x1800109c9  mov     edx, 0CDh
0x1800109ce  jmp     loc_1800108D4
0x1800109d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109da  cmp     rcx, r13
0x1800109dd  jz      short loc_1800109FC
0x1800109df  mov     edx, 0FCh
0x1800109e4  lea     r9, aEaptlsconnecti_1; "eaptlsconnectionpropertiesv3:EKUMapping"
0x1800109eb  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800109f2  mov     rcx, [rcx+10h]
0x1800109f6  call    WPP_SF_S
0x1800109fb  nop
0x1800109fc  mov     rcx, rbx; bstrString
0x1800109ff  call    cs:__imp_SysFreeString
0x180010a06  nop     dword ptr [rax+rax+00h]
0x180010a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a12  cmp     rcx, r13
0x180010a15  jz      short loc_180010A2C
0x180010a17  mov     edx, 0CCh
0x180010a1c  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180010a23  mov     rcx, [rcx+10h]
0x180010a27  call    WPP_SF_
0x180010a2c  mov     rsi, [rbp+57h+arg_10]
0x180010a30  lea     rcx, aEaptlsconnecti_23; "eaptlsconnectionpropertiesv3:ClientAuth"...
0x180010a37  call    cs:__imp_SysAllocString
0x180010a3e  nop     dword ptr [rax+rax+00h]
0x180010a43  mov     rbx, rax
0x180010a46  mov     [rbp+57h+arg_8], rax
0x180010a4a  test    rax, rax
0x180010a4d  jnz     short loc_180010A55
0x180010a4f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010a55  mov     rax, [rsi]
0x180010a58  lea     r8, [rbp+57h+arg_18]
0x180010a5c  mov     rdx, rbx
0x180010a5f  mov     rcx, rsi
0x180010a62  mov     rax, [rax+128h]
0x180010a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a6e  test    eax, eax
0x180010a70  jnz     short loc_180010ABD
0x180010a72  cmp     [rbp+57h+arg_18], 0
0x180010a77  jz      short loc_180010ABD
0x180010a79  mov     rcx, rbx; bstrString
0x180010a7c  call    cs:__imp_SysFreeString
0x180010a83  nop     dword ptr [rax+rax+00h]
0x180010a88  lea     r9, [rbp+57h+hMem]; struct _EAPTLS_FILTER_PROP *
0x180010a8c  xor     r8d, r8d; int
  ... truncated ...
```
