# InsertTLSExtensionTags(IXMLDOMDocument2 * *,IXMLDOMNode * *,_EAPTLS_CONN_PROPERTIES_V1 *)

- ea: `0x1800162e0`
- end: `0x180016a10`
- name: `?InsertTLSExtensionTags@@YAKPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z`
- size: `1840`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 **, struct IXMLDOMNode **, struct _EAPTLS_CONN_PROPERTIES_V1 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800086a0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x1800162e0`
- `0x180016a18`
- `0x180016e90`
- `0x180019730`
- `0x18001c3a0`
- `0x18001d8a0`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001695a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016974`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016994`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800169a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001695a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016974`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016994`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800169a6`
- `OLEAUT32!__imp_SysAllocString` at `0x180016436`
- `OLEAUT32!__imp_SysAllocString` at `0x180016468`
- `OLEAUT32!__imp_SysAllocString` at `0x18001662b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001665d`
- `OLEAUT32!__imp_SysAllocString` at `0x180016436`
- `OLEAUT32!__imp_SysAllocString` at `0x180016468`
- `OLEAUT32!__imp_SysAllocString` at `0x18001662b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001665d`
- `OLEAUT32!__imp_SysFreeString` at `0x180016423`
- `OLEAUT32!__imp_SysFreeString` at `0x1800165c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800165d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001661c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800167b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800167c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800169e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180016423`
- `OLEAUT32!__imp_SysFreeString` at `0x1800165c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800165d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001661c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800167b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800167c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800169e6`
- `OLEAUT32!__imp_VariantInit` at `0x180016494`
- `OLEAUT32!__imp_VariantInit` at `0x1800164c8`
- `OLEAUT32!__imp_VariantInit` at `0x180016689`
- `OLEAUT32!__imp_VariantInit` at `0x1800166be`
- `OLEAUT32!__imp_VariantInit` at `0x180016494`
- `OLEAUT32!__imp_VariantInit` at `0x1800164c8`
- `OLEAUT32!__imp_VariantInit` at `0x180016689`
- `OLEAUT32!__imp_VariantInit` at `0x1800166be`
- `OLEAUT32!__imp_VariantClear` at `0x180016521`
- `OLEAUT32!__imp_VariantClear` at `0x180016567`
- `OLEAUT32!__imp_VariantClear` at `0x180016717`
- `OLEAUT32!__imp_VariantClear` at `0x18001675d`
- `OLEAUT32!__imp_VariantClear` at `0x180016521`
- `OLEAUT32!__imp_VariantClear` at `0x180016567`
- `OLEAUT32!__imp_VariantClear` at `0x180016717`
- `OLEAUT32!__imp_VariantClear` at `0x18001675d`

## string_xrefs

- `0x18001642f`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2`
- `0x1800168db`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2`
- `0x180016461`: `TLSExtensions`
- `0x18001660d`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall InsertTLSExtensionTags(
        struct IXMLDOMDocument2 **a1,
        struct IXMLDOMNode **a2,
        struct _EAPTLS_CONN_PROPERTIES_V1 *a3)
{
  unsigned int v5; // edi
  unsigned __int16 *v6; // r14
  int v7; // r12d
  char *v8; // rdx
  __int64 v9; // rax
  BYTE *v10; // rcx
  unsigned int v11; // r8d
  char *v12; // r9
  DWORD v13; // edx
  __int64 v14; // rax
  unsigned int SelectedHashesAndEKUList; // eax
  struct _EAPTLS_CONTROL_BLOCK *v16; // rcx
  __int64 v17; // rdx
  int v18; // esi
  int v19; // ecx
  int v20; // ecx
  OLECHAR *v21; // rbx
  __int64 v22; // r13
  struct IXMLDOMDocument2 *v23; // rdi
  struct _EAPTLS_CONTROL_BLOCK *v24; // rcx
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // ecx
  OLECHAR *v28; // rbx
  struct IXMLDOMNode *v29; // r12
  struct IXMLDOMDocument2 *v30; // rdi
  char v31; // bl
  unsigned int v32; // eax
  HLOCAL *v33; // rbx
  HLOCAL *v34; // rcx
  __int64 v36; // [rsp+30h] [rbp-79h] BYREF
  struct IXMLDOMNode *v37; // [rsp+38h] [rbp-71h] BYREF
  VARIANTARG v38; // [rsp+40h] [rbp-69h] BYREF
  __int64 v39; // [rsp+58h] [rbp-51h]
  VARIANTARG pvarg; // [rsp+60h] [rbp-49h] BYREF
  HLOCAL hMem[2]; // [rsp+78h] [rbp-31h] BYREF
  HLOCAL v42[2]; // [rsp+88h] [rbp-21h]
  OLECHAR *v43; // [rsp+98h] [rbp-11h]
  OLECHAR *v44; // [rsp+A0h] [rbp-9h]
  VARIANTARG v45[3]; // [rsp+B0h] [rbp+7h] BYREF
  unsigned __int16 *v47; // [rsp+120h] [rbp+77h] BYREF
  struct IXMLDOMNode *v48; // [rsp+128h] [rbp+7Fh] BYREF

  v5 = 0;
  v6 = 0;
  v47 = 0;
  v37 = 0;
  v48 = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v42 = 0;
  v7 = 0;
  v8 = (char *)a3 + 24 * *((unsigned int *)a3 + 3);
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&v8[2 * v9 + 16] );
  v10 = (BYTE *)&v8[2 * v9 + 18];
  v11 = (_DWORD)a3 + *((_DWORD *)a3 + 1) - (_DWORD)v10;
  if ( v11 >= 6 && *(_WORD *)v10 == 254 )
  {
    v12 = &v8[2 * v9 + 18];
    v13 = 0;
    do
    {
      if ( (unsigned __int16)(*(_WORD *)v12 - 250) > 4u )
        break;
      v14 = *((unsigned __int16 *)v12 + 1);
      v13 += v14;
      v12 += v14;
      v11 -= v14;
    }
    while ( v11 >= 6 );
    SelectedHashesAndEKUList = GetSelectedHashesAndEKUList(v10, v13, (struct _EAPTLS_FILTER_PROP *)hMem);
    v5 = SelectedHashesAndEKUList;
    if ( SelectedHashesAndEKUList )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_74;
      v17 = 84;
      goto LABEL_11;
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    v7 = 1;
  }
  v18 = *((_DWORD *)a3 + 2) & 1;
  if ( v7 || !v18 )
  {
    SysFreeString(0);
    v6 = SysAllocString(L"http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2");
    v47 = v6;
    if ( !v6 )
      ATL::AtlThrowImpl(v19);
    memset(&pvarg, 0, sizeof(pvarg));
    v21 = SysAllocString(L"TLSExtensions");
    v43 = v21;
    if ( !v21 )
      ATL::AtlThrowImpl(v20);
    v44 = 0;
    v39 = 0;
    VariantInit(&pvarg);
    pvarg.vt = 0;
    v22 = (__int64)*a2;
    v23 = *a1;
    v36 = 0;
    memset(&v38, 0, sizeof(v38));
    VariantInit(&v38);
    v38.vt = 3;
    v38.lVal = 1;
    v45[0] = v38;
    v5 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *, OLECHAR *, unsigned __int16 *, __int64 *))v23->lpVtbl->createNode)(
           v23,
           v45,
           v21,
           v6,
           &v36);
    VariantClear(&v38);
    if ( !v5 )
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, struct IXMLDOMNode **))(*(_QWORD *)v22 + 168LL))(v22, v36, &v48);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    VariantClear(&pvarg);
    if ( v5 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v5);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    SysFreeString(0);
    SysFreeString(v21);
    if ( v5 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_74;
      v25 = 86;
      goto LABEL_73;
    }
    if ( v7 )
    {
      if ( L"http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3" != v6 )
      {
        SysFreeString(v6);
        v6 = SysAllocString(L"http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3");
        v47 = v6;
        if ( !v6 )
          ATL::AtlThrowImpl(v26);
      }
      memset(&pvarg, 0, sizeof(pvarg));
      v28 = SysAllocString(L"FilteringInfo");
      v44 = v28;
      if ( !v28 )
        ATL::AtlThrowImpl(v27);
      v43 = 0;
      v39 = 0;
      VariantInit(&pvarg);
      pvarg.vt = 0;
      v29 = v48;
      v30 = *a1;
      v36 = 0;
      memset(&v38, 0, sizeof(v38));
      VariantInit(&v38);
      v38.vt = 3;
      v38.lVal = 1;
      v45[0] = v38;
      v5 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *, OLECHAR *, unsigned __int16 *, __int64 *))v30->lpVtbl->createNode)(
             v30,
             v45,
             v28,
             v6,
             &v36);
      VariantClear(&v38);
      if ( !v5 )
        v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, struct IXMLDOMNode **))v29->lpVtbl->appendChild)(
               v29,
               v36,
               &v37);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      VariantClear(&pvarg);
      if ( v5 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v5);
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      SysFreeString(0);
      SysFreeString(v28);
      if ( v5 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_74;
        v25 = 87;
        goto LABEL_73;
      }
      v31 = (char)hMem[0];
      if ( ((__int64)hMem[0] & 8) != 0 )
      {
        SelectedHashesAndEKUList = AddXMLTag(a1, &v37, v6, L"AllPurposeEnabled", L"true", 0);
        v5 = SelectedHashesAndEKUList;
        if ( SelectedHashesAndEKUList )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_74;
          v17 = 88;
          goto LABEL_11;
        }
      }
      if ( (v31 & 1) != 0 || WORD1(hMem[0]) )
      {
        SelectedHashesAndEKUList = InsertCAFilterTags(a1, &v37, v6, (struct _EAPTLS_FILTER_PROP *)hMem);
        v5 = SelectedHashesAndEKUList;
        if ( SelectedHashesAndEKUList )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_74;
          v17 = 89;
          goto LABEL_11;
        }
        v31 = (char)hMem[0];
      }
      if ( v42[0] || (v31 & 6) != 0 )
      {
        SelectedHashesAndEKUList = InsertEKUFilterTags(a1, &v37, v6, (struct _EAPTLS_FILTER_PROP *)hMem);
        v5 = SelectedHashesAndEKUList;
        if ( SelectedHashesAndEKUList )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_74;
          v17 = 90;
LABEL_11:
          WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, SelectedHashesAndEKUList);
          goto LABEL_74;
        }
      }
    }
    if ( !v18 )
    {
      ATL::CComBSTR::operator=(&v47, L"http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2");
      v6 = v47;
      v32 = (*((_DWORD *)a3 + 2) & 0x400) != 0
          ? AddXMLTag(a1, &v48, v47, L"GroupSmartCardCerts", L"false", 0)
          : AddXMLTag(a1, &v48, v47, L"GroupSmartCardCerts", L"true", 0);
      v5 = v32;
      if ( v32 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v25 = 91;
LABEL_73:
          WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v5);
        }
      }
    }
  }
LABEL_74:
  LocalFree(hMem[1]);
  v33 = (HLOCAL *)v42[0];
  if ( v42[0] )
  {
    do
    {
      LocalFree(v33[1]);
      LocalFree(v33[2]);
      LocalFree(v33[3]);
      v34 = v33;
      v33 = (HLOCAL *)*v33;
      LocalFree(v34);
    }
    while ( v33 );
  }
  if ( v48 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v48->lpVtbl->Release)(v48);
  if ( v37 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v37->lpVtbl->Release)(v37);
  SysFreeString(v6);
  return v5;
}

```

## disassembly

```asm
0x1800162e0  mov     [rsp-8+arg_8], rbx
0x1800162e5  mov     [rsp-8+arg_0], rcx
0x1800162ea  push    rbp
0x1800162eb  push    rsi
0x1800162ec  push    rdi
0x1800162ed  push    r12
0x1800162ef  push    r13
0x1800162f1  push    r14
0x1800162f3  push    r15
0x1800162f5  lea     rbp, [rsp-27h]
0x1800162fa  sub     rsp, 0D0h
0x180016301  mov     r15, r8
0x180016304  mov     r13, rdx
0x180016307  xor     r10d, r10d
0x18001630a  mov     edi, r10d
0x18001630d  mov     r14d, r10d
0x180016310  mov     [rbp+57h+arg_10], r10
0x180016314  mov     [rbp+57h+var_C8], r10
0x180016318  mov     [rbp+57h+arg_18], r10
0x18001631c  xorps   xmm0, xmm0
0x18001631f  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x180016323  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x180016327  mov     r12d, r10d
0x18001632a  mov     eax, [r8+0Ch]
0x18001632e  lea     rcx, [rax+rax*2]
0x180016332  lea     rdx, [r8+rcx*8]
0x180016336  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001633d  nop     dword ptr [rax]
0x180016340  lea     rax, [rax+1]
0x180016344  cmp     [rdx+rax*2+10h], r12w
0x18001634a  jnz     short loc_180016340
0x18001634c  lea     rcx, [rdx+12h]
0x180016350  lea     rcx, [rcx+rax*2]; lpbBytes
0x180016354  mov     r8d, [r8+4]
0x180016358  sub     r8d, ecx
0x18001635b  add     r8d, r15d
0x18001635e  lea     rbx, WPP_GLOBAL_Control
0x180016365  cmp     r8d, 6
0x180016369  jb      loc_18001640D
0x18001636f  mov     eax, 0FEh
0x180016374  cmp     [rcx], ax
0x180016377  jnz     loc_18001640D
0x18001637d  mov     r9, rcx
0x180016380  mov     edx, r10d
0x180016383  mov     r10d, 0FAh
0x180016389  movzx   eax, word ptr [r9]
0x18001638d  sub     ax, r10w
0x180016391  cmp     ax, 4
0x180016395  ja      short loc_1800163AA
0x180016397  movzx   eax, word ptr [r9+2]
0x18001639c  add     edx, eax; dwByteCount
0x18001639e  add     r9, rax
0x1800163a1  sub     r8d, eax
0x1800163a4  cmp     r8d, 6
0x1800163a8  jnb     short loc_180016389
0x1800163aa  lea     r8, [rbp+57h+hMem]; struct _EAPTLS_FILTER_PROP *
0x1800163ae  call    ?GetSelectedHashesAndEKUList@@YAKPEAEKPEAU_EAPTLS_FILTER_PROP@@@Z; GetSelectedHashesAndEKUList(uchar *,ulong,_EAPTLS_FILTER_PROP *)
0x1800163b3  mov     edi, eax
0x1800163b5  test    eax, eax
0x1800163b7  jz      short loc_1800163E6
0x1800163b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163c0  cmp     rcx, rbx
0x1800163c3  jz      loc_180016956
0x1800163c9  mov     edx, 54h ; 'T'
0x1800163ce  mov     r9d, eax
0x1800163d1  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800163d8  mov     rcx, [rcx+10h]
0x1800163dc  call    WPP_SF_d
0x1800163e1  jmp     loc_180016956
0x1800163e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163ed  cmp     rcx, rbx
0x1800163f0  jz      short loc_180016407
0x1800163f2  mov     edx, 55h ; 'U'
0x1800163f7  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800163fe  mov     rcx, [rcx+10h]
0x180016402  call    WPP_SF_
0x180016407  mov     r12d, 1
0x18001640d  mov     esi, [r15+8]
0x180016411  and     esi, 1
0x180016414  test    r12d, r12d
0x180016417  jnz     short loc_180016421
0x180016419  test    esi, esi
0x18001641b  jnz     loc_180016956
0x180016421  xor     ecx, ecx; bstrString
0x180016423  call    cs:__imp_SysFreeString
0x18001642a  nop     dword ptr [rax+rax+00h]
0x18001642f  lea     rcx, aHttpWwwMicroso_9; "http://www.microsoft.com/provisioning/E"...
0x180016436  call    cs:__imp_SysAllocString
0x18001643d  nop     dword ptr [rax+rax+00h]
0x180016442  mov     r14, rax
0x180016445  mov     [rbp+57h+arg_10], rax
0x180016449  test    rax, rax
0x18001644c  jnz     short loc_180016454
0x18001644e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180016454  xorps   xmm0, xmm0
0x180016457  xor     eax, eax
0x180016459  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001645d  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180016461  lea     rcx, aTlsextensions; "TLSExtensions"
0x180016468  call    cs:__imp_SysAllocString
0x18001646f  nop     dword ptr [rax+rax+00h]
0x180016474  mov     rbx, rax
0x180016477  mov     [rbp+57h+var_68], rax
0x18001647b  test    rax, rax
0x18001647e  jnz     short loc_180016486
0x180016480  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180016486  xor     edi, edi
0x180016488  mov     [rbp+57h+var_60], rdi
0x18001648c  mov     [rbp+57h+var_A8], rdi
0x180016490  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180016494  call    cs:__imp_VariantInit
0x18001649b  nop     dword ptr [rax+rax+00h]
0x1800164a0  mov     word ptr [rbp+57h+pvarg], di
0x1800164a4  mov     r13, [r13+0]
0x1800164a8  mov     rdi, [rbp+57h+arg_0]
0x1800164ac  mov     rdi, [rdi]
0x1800164af  mov     [rbp+57h+var_D0], 0
0x1800164b7  xorps   xmm0, xmm0
0x1800164ba  xor     eax, eax
0x1800164bc  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800164c0  mov     qword ptr [rbp+57h+var_C0+10h], rax
0x1800164c4  lea     rcx, [rbp+57h+var_C0]; pvarg
0x1800164c8  call    cs:__imp_VariantInit
0x1800164cf  nop     dword ptr [rax+rax+00h]
0x1800164d4  mov     eax, 3
0x1800164d9  mov     word ptr [rbp+57h+var_C0], ax
0x1800164dd  mov     dword ptr [rbp+57h+var_C0+8], 1
0x1800164e4  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x1800164e8  movaps  [rbp+57h+var_50], xmm0
0x1800164ec  movsd   xmm1, qword ptr [rbp+57h+var_C0+10h]
0x1800164f1  movsd   [rbp+57h+var_40], xmm1
0x1800164f6  mov     rax, [rdi]
0x1800164f9  lea     rcx, [rbp+57h+var_D0]
0x1800164fd  mov     [rsp+100h+var_E0], rcx
0x180016502  mov     r9, r14
0x180016505  mov     r8, rbx
0x180016508  lea     rdx, [rbp+57h+var_50]
0x18001650c  mov     rcx, rdi
0x18001650f  mov     rax, [rax+1C0h]
0x180016516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001651b  mov     edi, eax
0x18001651d  lea     rcx, [rbp+57h+var_C0]; pvarg
0x180016521  call    cs:__imp_VariantClear
0x180016528  nop     dword ptr [rax+rax+00h]
0x18001652d  test    edi, edi
0x18001652f  jnz     short loc_18001654E
0x180016531  mov     rax, [r13+0]
0x180016535  lea     r8, [rbp+57h+arg_18]
0x180016539  mov     rdx, [rbp+57h+var_D0]
0x18001653d  mov     rcx, r13
0x180016540  mov     rax, [rax+0A8h]
0x180016547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001654c  mov     edi, eax
0x18001654e  mov     rcx, [rbp+57h+var_D0]
0x180016552  test    rcx, rcx
0x180016555  jz      short loc_180016563
0x180016557  mov     rax, [rcx]
0x18001655a  mov     rax, [rax+10h]
0x18001655e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016563  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180016567  call    cs:__imp_VariantClear
0x18001656e  nop     dword ptr [rax+rax+00h]
0x180016573  test    edi, edi
0x180016575  jz      short loc_1800165A4
0x180016577  mov     rcx, cs:WPP_GLOBAL_Control
0x18001657e  lea     r13, WPP_GLOBAL_Control
0x180016585  cmp     rcx, r13
0x180016588  jz      short loc_1800165AB
0x18001658a  mov     edx, 45h ; 'E'
0x18001658f  mov     r9d, edi
0x180016592  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180016599  mov     rcx, [rcx+10h]
0x18001659d  call    WPP_SF_d
0x1800165a2  jmp     short loc_1800165AB
0x1800165a4  lea     r13, WPP_GLOBAL_Control
0x1800165ab  mov     rcx, [rbp+57h+var_A8]
0x1800165af  test    rcx, rcx
0x1800165b2  jz      short loc_1800165C1
0x1800165b4  mov     rax, [rcx]
0x1800165b7  mov     rax, [rax+10h]
0x1800165bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165c0  nop
0x1800165c1  xor     ecx, ecx; bstrString
0x1800165c3  call    cs:__imp_SysFreeString
0x1800165ca  nop     dword ptr [rax+rax+00h]
0x1800165cf  nop
0x1800165d0  mov     rcx, rbx; bstrString
0x1800165d3  call    cs:__imp_SysFreeString
0x1800165da  nop     dword ptr [rax+rax+00h]
0x1800165df  test    edi, edi
0x1800165e1  jz      short loc_1800165FD
0x1800165e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165ea  cmp     rcx, r13
0x1800165ed  jz      loc_180016956
0x1800165f3  mov     edx, 56h ; 'V'
0x1800165f8  jmp     loc_180016943
0x1800165fd  lea     rbx, String2; "true"
0x180016604  test    r12d, r12d
0x180016607  jz      loc_1800168D7
0x18001660d  lea     rbx, aHttpWwwMicroso_7; "http://www.microsoft.com/provisioning/E"...
0x180016614  cmp     rbx, r14
0x180016617  jz      short loc_180016649
0x180016619  mov     rcx, r14; bstrString
0x18001661c  call    cs:__imp_SysFreeString
0x180016623  nop     dword ptr [rax+rax+00h]
0x180016628  mov     rcx, rbx; psz
0x18001662b  call    cs:__imp_SysAllocString
0x180016632  nop     dword ptr [rax+rax+00h]
0x180016637  mov     r14, rax
0x18001663a  mov     [rbp+57h+arg_10], rax
0x18001663e  test    rax, rax
0x180016641  jnz     short loc_180016649
0x180016643  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180016649  xorps   xmm0, xmm0
0x18001664c  xor     eax, eax
0x18001664e  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180016652  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180016656  lea     rcx, aFilteringinfo; "FilteringInfo"
0x18001665d  call    cs:__imp_SysAllocString
0x180016664  nop     dword ptr [rax+rax+00h]
0x180016669  mov     rbx, rax
0x18001666c  mov     [rbp+57h+var_60], rax
0x180016670  test    rax, rax
0x180016673  jnz     short loc_18001667B
0x180016675  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001667b  xor     edi, edi
0x18001667d  mov     [rbp+57h+var_68], rdi
0x180016681  mov     [rbp+57h+var_A8], rdi
0x180016685  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180016689  call    cs:__imp_VariantInit
0x180016690  nop     dword ptr [rax+rax+00h]
0x180016695  mov     word ptr [rbp+57h+pvarg], di
0x180016699  mov     r12, [rbp+57h+arg_18]
0x18001669d  mov     r13, [rbp+57h+arg_0]
0x1800166a1  mov     rdi, [r13+0]
0x1800166a5  mov     [rbp+57h+var_D0], 0
0x1800166ad  xorps   xmm0, xmm0
0x1800166b0  xor     eax, eax
0x1800166b2  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800166b6  mov     qword ptr [rbp+57h+var_C0+10h], rax
0x1800166ba  lea     rcx, [rbp+57h+var_C0]; pvarg
0x1800166be  call    cs:__imp_VariantInit
0x1800166c5  nop     dword ptr [rax+rax+00h]
0x1800166ca  mov     eax, 3
0x1800166cf  mov     word ptr [rbp+57h+var_C0], ax
0x1800166d3  mov     dword ptr [rbp+57h+var_C0+8], 1
0x1800166da  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x1800166de  movaps  [rbp+57h+var_50], xmm0
0x1800166e2  movsd   xmm1, qword ptr [rbp+57h+var_C0+10h]
0x1800166e7  movsd   [rbp+57h+var_40], xmm1
0x1800166ec  mov     rax, [rdi]
0x1800166ef  lea     rcx, [rbp+57h+var_D0]
0x1800166f3  mov     [rsp+100h+var_E0], rcx
0x1800166f8  mov     r9, r14
0x1800166fb  mov     r8, rbx
0x1800166fe  lea     rdx, [rbp+57h+var_50]
0x180016702  mov     rcx, rdi
0x180016705  mov     rax, [rax+1C0h]
0x18001670c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016711  mov     edi, eax
0x180016713  lea     rcx, [rbp+57h+var_C0]; pvarg
0x180016717  call    cs:__imp_VariantClear
0x18001671e  nop     dword ptr [rax+rax+00h]
0x180016723  test    edi, edi
0x180016725  jnz     short loc_180016744
0x180016727  mov     rax, [r12]
0x18001672b  lea     r8, [rbp+57h+var_C8]
0x18001672f  mov     rdx, [rbp+57h+var_D0]
0x180016733  mov     rcx, r12
0x180016736  mov     rax, [rax+0A8h]
0x18001673d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016742  mov     edi, eax
0x180016744  mov     rcx, [rbp+57h+var_D0]
0x180016748  test    rcx, rcx
0x18001674b  jz      short loc_180016759
0x18001674d  mov     rax, [rcx]
0x180016750  mov     rax, [rax+10h]
0x180016754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016759  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001675d  call    cs:__imp_VariantClear
0x180016764  nop     dword ptr [rax+rax+00h]
0x180016769  test    edi, edi
0x18001676b  jz      short loc_18001679A
0x18001676d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016774  lea     r12, WPP_GLOBAL_Control
0x18001677b  cmp     rcx, r12
0x18001677e  jz      short loc_1800167A1
0x180016780  mov     edx, 45h ; 'E'
0x180016785  mov     r9d, edi
0x180016788  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001678f  mov     rcx, [rcx+10h]
0x180016793  call    WPP_SF_d
0x180016798  jmp     short loc_1800167A1
0x18001679a  lea     r12, WPP_GLOBAL_Control
0x1800167a1  mov     rcx, [rbp+57h+var_A8]
0x1800167a5  test    rcx, rcx
0x1800167a8  jz      short loc_1800167B7
0x1800167aa  mov     rax, [rcx]
0x1800167ad  mov     rax, [rax+10h]
0x1800167b1  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
