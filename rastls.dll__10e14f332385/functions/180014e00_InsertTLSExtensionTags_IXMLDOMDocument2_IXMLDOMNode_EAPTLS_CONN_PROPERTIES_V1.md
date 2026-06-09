# InsertTLSExtensionTags(IXMLDOMDocument2 * *,IXMLDOMNode * *,_EAPTLS_CONN_PROPERTIES_V1 *)

- ea: `0x180014e00`
- end: `0x1800154a1`
- name: `?InsertTLSExtensionTags@@YAKPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z`
- size: `1697`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 **, struct IXMLDOMNode **, struct _EAPTLS_CONN_PROPERTIES_V1 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007ec0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180014e00`
- `0x1800154a8`
- `0x1800158f0`
- `0x180017f00`
- `0x18001aa30`
- `0x18001bec0`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001540e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015424`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001542e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015438`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015444`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001540e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015424`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001542e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015438`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015444`
- `OLEAUT32!__imp_SysAllocString` at `0x180014f50`
- `OLEAUT32!__imp_SysAllocString` at `0x180014f7c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001510f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001513b`
- `OLEAUT32!__imp_SysAllocString` at `0x180014f50`
- `OLEAUT32!__imp_SysAllocString` at `0x180014f7c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001510f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001513b`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f43`
- `OLEAUT32!__imp_SysFreeString` at `0x1800150b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800150c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180015106`
- `OLEAUT32!__imp_SysFreeString` at `0x180015279`
- `OLEAUT32!__imp_SysFreeString` at `0x180015283`
- `OLEAUT32!__imp_SysFreeString` at `0x18001547e`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f43`
- `OLEAUT32!__imp_SysFreeString` at `0x1800150b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800150c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180015106`
- `OLEAUT32!__imp_SysFreeString` at `0x180015279`
- `OLEAUT32!__imp_SysFreeString` at `0x180015283`
- `OLEAUT32!__imp_SysFreeString` at `0x18001547e`
- `OLEAUT32!__imp_VariantInit` at `0x180014fa2`
- `OLEAUT32!__imp_VariantInit` at `0x180014fd0`
- `OLEAUT32!__imp_VariantInit` at `0x180015161`
- `OLEAUT32!__imp_VariantInit` at `0x180015190`
- `OLEAUT32!__imp_VariantInit` at `0x180014fa2`
- `OLEAUT32!__imp_VariantInit` at `0x180014fd0`
- `OLEAUT32!__imp_VariantInit` at `0x180015161`
- `OLEAUT32!__imp_VariantInit` at `0x180015190`
- `OLEAUT32!__imp_VariantClear` at `0x180015023`
- `OLEAUT32!__imp_VariantClear` at `0x180015063`
- `OLEAUT32!__imp_VariantClear` at `0x1800151e3`
- `OLEAUT32!__imp_VariantClear` at `0x180015223`
- `OLEAUT32!__imp_VariantClear` at `0x180015023`
- `OLEAUT32!__imp_VariantClear` at `0x180015063`
- `OLEAUT32!__imp_VariantClear` at `0x1800151e3`
- `OLEAUT32!__imp_VariantClear` at `0x180015223`

## string_xrefs

- `0x180014f49`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2`
- `0x18001538f`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2`
- `0x180014f75`: `TLSExtensions`
- `0x1800150f7`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3`

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
0x180014e00  mov     [rsp-8+arg_8], rbx
0x180014e05  mov     [rsp-8+arg_0], rcx
0x180014e0a  push    rbp
0x180014e0b  push    rsi
0x180014e0c  push    rdi
0x180014e0d  push    r12
0x180014e0f  push    r13
0x180014e11  push    r14
0x180014e13  push    r15
0x180014e15  lea     rbp, [rsp-27h]
0x180014e1a  sub     rsp, 0D0h
0x180014e21  mov     r15, r8
0x180014e24  mov     r13, rdx
0x180014e27  xor     r10d, r10d
0x180014e2a  mov     edi, r10d
0x180014e2d  mov     r14d, r10d
0x180014e30  mov     [rbp+57h+arg_10], r10
0x180014e34  mov     [rbp+57h+var_C8], r10
0x180014e38  mov     [rbp+57h+arg_18], r10
0x180014e3c  xorps   xmm0, xmm0
0x180014e3f  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x180014e43  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x180014e47  mov     r12d, r10d
0x180014e4a  mov     eax, [r8+0Ch]
0x180014e4e  lea     rcx, [rax+rax*2]
0x180014e52  lea     rdx, [r8+rcx*8]
0x180014e56  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180014e5d  nop     dword ptr [rax]
0x180014e60  lea     rax, [rax+1]
0x180014e64  cmp     [rdx+rax*2+10h], r12w
0x180014e6a  jnz     short loc_180014E60
0x180014e6c  lea     rcx, [rdx+12h]
0x180014e70  lea     rcx, [rcx+rax*2]; lpbBytes
0x180014e74  mov     r8d, [r8+4]
0x180014e78  sub     r8d, ecx
0x180014e7b  add     r8d, r15d
0x180014e7e  lea     rbx, WPP_GLOBAL_Control
0x180014e85  cmp     r8d, 6
0x180014e89  jb      loc_180014F2D
0x180014e8f  mov     eax, 0FEh
0x180014e94  cmp     [rcx], ax
0x180014e97  jnz     loc_180014F2D
0x180014e9d  mov     r9, rcx
0x180014ea0  mov     edx, r10d
0x180014ea3  mov     r10d, 0FAh
0x180014ea9  movzx   eax, word ptr [r9]
0x180014ead  sub     ax, r10w
0x180014eb1  cmp     ax, 4
0x180014eb5  ja      short loc_180014ECA
0x180014eb7  movzx   eax, word ptr [r9+2]
0x180014ebc  add     edx, eax; dwByteCount
0x180014ebe  add     r9, rax
0x180014ec1  sub     r8d, eax
0x180014ec4  cmp     r8d, 6
0x180014ec8  jnb     short loc_180014EA9
0x180014eca  lea     r8, [rbp+57h+hMem]; struct _EAPTLS_FILTER_PROP *
0x180014ece  call    ?GetSelectedHashesAndEKUList@@YAKPEAEKPEAU_EAPTLS_FILTER_PROP@@@Z; GetSelectedHashesAndEKUList(uchar *,ulong,_EAPTLS_FILTER_PROP *)
0x180014ed3  mov     edi, eax
0x180014ed5  test    eax, eax
0x180014ed7  jz      short loc_180014F06
0x180014ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ee0  cmp     rcx, rbx
0x180014ee3  jz      loc_18001540A
0x180014ee9  mov     edx, 54h ; 'T'
0x180014eee  mov     r9d, eax
0x180014ef1  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180014ef8  mov     rcx, [rcx+10h]
0x180014efc  call    WPP_SF_d
0x180014f01  jmp     loc_18001540A
0x180014f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f0d  cmp     rcx, rbx
0x180014f10  jz      short loc_180014F27
0x180014f12  mov     edx, 55h ; 'U'
0x180014f17  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180014f1e  mov     rcx, [rcx+10h]
0x180014f22  call    WPP_SF_
0x180014f27  mov     r12d, 1
0x180014f2d  mov     esi, [r15+8]
0x180014f31  and     esi, 1
0x180014f34  test    r12d, r12d
0x180014f37  jnz     short loc_180014F41
0x180014f39  test    esi, esi
0x180014f3b  jnz     loc_18001540A
0x180014f41  xor     ecx, ecx; bstrString
0x180014f43  call    cs:__imp_SysFreeString
0x180014f49  lea     rcx, aHttpWwwMicroso_9; "http://www.microsoft.com/provisioning/E"...
0x180014f50  call    cs:__imp_SysAllocString
0x180014f56  mov     r14, rax
0x180014f59  mov     [rbp+57h+arg_10], rax
0x180014f5d  test    rax, rax
0x180014f60  jnz     short loc_180014F68
0x180014f62  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180014f68  xorps   xmm0, xmm0
0x180014f6b  xor     eax, eax
0x180014f6d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180014f71  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180014f75  lea     rcx, aTlsextensions; "TLSExtensions"
0x180014f7c  call    cs:__imp_SysAllocString
0x180014f82  mov     rbx, rax
0x180014f85  mov     [rbp+57h+var_68], rax
0x180014f89  test    rax, rax
0x180014f8c  jnz     short loc_180014F94
0x180014f8e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180014f94  xor     edi, edi
0x180014f96  mov     [rbp+57h+var_60], rdi
0x180014f9a  mov     [rbp+57h+var_A8], rdi
0x180014f9e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180014fa2  call    cs:__imp_VariantInit
0x180014fa8  mov     word ptr [rbp+57h+pvarg], di
0x180014fac  mov     r13, [r13+0]
0x180014fb0  mov     rdi, [rbp+57h+arg_0]
0x180014fb4  mov     rdi, [rdi]
0x180014fb7  mov     [rbp+57h+var_D0], 0
0x180014fbf  xorps   xmm0, xmm0
0x180014fc2  xor     eax, eax
0x180014fc4  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x180014fc8  mov     qword ptr [rbp+57h+var_C0+10h], rax
0x180014fcc  lea     rcx, [rbp+57h+var_C0]; pvarg
0x180014fd0  call    cs:__imp_VariantInit
0x180014fd6  mov     eax, 3
0x180014fdb  mov     word ptr [rbp+57h+var_C0], ax
0x180014fdf  mov     dword ptr [rbp+57h+var_C0+8], 1
0x180014fe6  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x180014fea  movaps  [rbp+57h+var_50], xmm0
0x180014fee  movsd   xmm1, qword ptr [rbp+57h+var_C0+10h]
0x180014ff3  movsd   [rbp+57h+var_40], xmm1
0x180014ff8  mov     rax, [rdi]
0x180014ffb  lea     rcx, [rbp+57h+var_D0]
0x180014fff  mov     [rsp+100h+var_E0], rcx
0x180015004  mov     r9, r14
0x180015007  mov     r8, rbx
0x18001500a  lea     rdx, [rbp+57h+var_50]
0x18001500e  mov     rcx, rdi
0x180015011  mov     rax, [rax+1C0h]
0x180015018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001501d  mov     edi, eax
0x18001501f  lea     rcx, [rbp+57h+var_C0]; pvarg
0x180015023  call    cs:__imp_VariantClear
0x180015029  test    edi, edi
0x18001502b  jnz     short loc_18001504A
0x18001502d  mov     rax, [r13+0]
0x180015031  lea     r8, [rbp+57h+arg_18]
0x180015035  mov     rdx, [rbp+57h+var_D0]
0x180015039  mov     rcx, r13
0x18001503c  mov     rax, [rax+0A8h]
0x180015043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015048  mov     edi, eax
0x18001504a  mov     rcx, [rbp+57h+var_D0]
0x18001504e  test    rcx, rcx
0x180015051  jz      short loc_18001505F
0x180015053  mov     rax, [rcx]
0x180015056  mov     rax, [rax+10h]
0x18001505a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001505f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180015063  call    cs:__imp_VariantClear
0x180015069  test    edi, edi
0x18001506b  jz      short loc_18001509A
0x18001506d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015074  lea     r13, WPP_GLOBAL_Control
0x18001507b  cmp     rcx, r13
0x18001507e  jz      short loc_1800150A1
0x180015080  mov     edx, 45h ; 'E'
0x180015085  mov     r9d, edi
0x180015088  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001508f  mov     rcx, [rcx+10h]
0x180015093  call    WPP_SF_d
0x180015098  jmp     short loc_1800150A1
0x18001509a  lea     r13, WPP_GLOBAL_Control
0x1800150a1  mov     rcx, [rbp+57h+var_A8]
0x1800150a5  test    rcx, rcx
0x1800150a8  jz      short loc_1800150B7
0x1800150aa  mov     rax, [rcx]
0x1800150ad  mov     rax, [rax+10h]
0x1800150b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150b6  nop
0x1800150b7  xor     ecx, ecx; bstrString
0x1800150b9  call    cs:__imp_SysFreeString
0x1800150bf  nop
0x1800150c0  mov     rcx, rbx; bstrString
0x1800150c3  call    cs:__imp_SysFreeString
0x1800150c9  test    edi, edi
0x1800150cb  jz      short loc_1800150E7
0x1800150cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150d4  cmp     rcx, r13
0x1800150d7  jz      loc_18001540A
0x1800150dd  mov     edx, 56h ; 'V'
0x1800150e2  jmp     loc_1800153F7
0x1800150e7  lea     rbx, String2; "true"
0x1800150ee  test    r12d, r12d
0x1800150f1  jz      loc_18001538B
0x1800150f7  lea     rbx, aHttpWwwMicroso_7; "http://www.microsoft.com/provisioning/E"...
0x1800150fe  cmp     rbx, r14
0x180015101  jz      short loc_180015127
0x180015103  mov     rcx, r14; bstrString
0x180015106  call    cs:__imp_SysFreeString
0x18001510c  mov     rcx, rbx; psz
0x18001510f  call    cs:__imp_SysAllocString
0x180015115  mov     r14, rax
0x180015118  mov     [rbp+57h+arg_10], rax
0x18001511c  test    rax, rax
0x18001511f  jnz     short loc_180015127
0x180015121  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015127  xorps   xmm0, xmm0
0x18001512a  xor     eax, eax
0x18001512c  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180015130  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180015134  lea     rcx, aFilteringinfo; "FilteringInfo"
0x18001513b  call    cs:__imp_SysAllocString
0x180015141  mov     rbx, rax
0x180015144  mov     [rbp+57h+var_60], rax
0x180015148  test    rax, rax
0x18001514b  jnz     short loc_180015153
0x18001514d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015153  xor     edi, edi
0x180015155  mov     [rbp+57h+var_68], rdi
0x180015159  mov     [rbp+57h+var_A8], rdi
0x18001515d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180015161  call    cs:__imp_VariantInit
0x180015167  mov     word ptr [rbp+57h+pvarg], di
0x18001516b  mov     r12, [rbp+57h+arg_18]
0x18001516f  mov     r13, [rbp+57h+arg_0]
0x180015173  mov     rdi, [r13+0]
0x180015177  mov     [rbp+57h+var_D0], 0
0x18001517f  xorps   xmm0, xmm0
0x180015182  xor     eax, eax
0x180015184  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x180015188  mov     qword ptr [rbp+57h+var_C0+10h], rax
0x18001518c  lea     rcx, [rbp+57h+var_C0]; pvarg
0x180015190  call    cs:__imp_VariantInit
0x180015196  mov     eax, 3
0x18001519b  mov     word ptr [rbp+57h+var_C0], ax
0x18001519f  mov     dword ptr [rbp+57h+var_C0+8], 1
0x1800151a6  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x1800151aa  movaps  [rbp+57h+var_50], xmm0
0x1800151ae  movsd   xmm1, qword ptr [rbp+57h+var_C0+10h]
0x1800151b3  movsd   [rbp+57h+var_40], xmm1
0x1800151b8  mov     rax, [rdi]
0x1800151bb  lea     rcx, [rbp+57h+var_D0]
0x1800151bf  mov     [rsp+100h+var_E0], rcx
0x1800151c4  mov     r9, r14
0x1800151c7  mov     r8, rbx
0x1800151ca  lea     rdx, [rbp+57h+var_50]
0x1800151ce  mov     rcx, rdi
0x1800151d1  mov     rax, [rax+1C0h]
0x1800151d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151dd  mov     edi, eax
0x1800151df  lea     rcx, [rbp+57h+var_C0]; pvarg
0x1800151e3  call    cs:__imp_VariantClear
0x1800151e9  test    edi, edi
0x1800151eb  jnz     short loc_18001520A
0x1800151ed  mov     rax, [r12]
0x1800151f1  lea     r8, [rbp+57h+var_C8]
0x1800151f5  mov     rdx, [rbp+57h+var_D0]
0x1800151f9  mov     rcx, r12
0x1800151fc  mov     rax, [rax+0A8h]
0x180015203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015208  mov     edi, eax
0x18001520a  mov     rcx, [rbp+57h+var_D0]
0x18001520e  test    rcx, rcx
0x180015211  jz      short loc_18001521F
0x180015213  mov     rax, [rcx]
0x180015216  mov     rax, [rax+10h]
0x18001521a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001521f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180015223  call    cs:__imp_VariantClear
0x180015229  test    edi, edi
0x18001522b  jz      short loc_18001525A
0x18001522d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015234  lea     r12, WPP_GLOBAL_Control
0x18001523b  cmp     rcx, r12
0x18001523e  jz      short loc_180015261
0x180015240  mov     edx, 45h ; 'E'
0x180015245  mov     r9d, edi
0x180015248  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001524f  mov     rcx, [rcx+10h]
0x180015253  call    WPP_SF_d
0x180015258  jmp     short loc_180015261
0x18001525a  lea     r12, WPP_GLOBAL_Control
0x180015261  mov     rcx, [rbp+57h+var_A8]
0x180015265  test    rcx, rcx
0x180015268  jz      short loc_180015277
0x18001526a  mov     rax, [rcx]
0x18001526d  mov     rax, [rax+10h]
0x180015271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015276  nop
0x180015277  xor     ecx, ecx; bstrString
0x180015279  call    cs:__imp_SysFreeString
0x18001527f  nop
0x180015280  mov     rcx, rbx; bstrString
0x180015283  call    cs:__imp_SysFreeString
0x180015289  test    edi, edi
0x18001528b  jz      short loc_1800152A7
0x18001528d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015294  cmp     rcx, r12
0x180015297  jz      loc_18001540A
0x18001529d  mov     edx, 57h ; 'W'
0x1800152a2  jmp     loc_1800153F7
0x1800152a7  movzx   ebx, word ptr [rbp+57h+hMem]
0x1800152ab  test    bl, 8
0x1800152ae  jz      short loc_1800152FB
  ... truncated ...
```
