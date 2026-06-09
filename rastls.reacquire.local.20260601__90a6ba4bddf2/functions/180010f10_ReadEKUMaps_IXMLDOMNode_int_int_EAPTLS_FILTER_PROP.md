# ReadEKUMaps(IXMLDOMNode *,int,int,_EAPTLS_FILTER_PROP *)

- ea: `0x180010f10`
- end: `0x1800119ec`
- name: `?ReadEKUMaps@@YAKPEAUIXMLDOMNode@@HHPEAU_EAPTLS_FILTER_PROP@@@Z`
- size: `2780`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, int, int, struct _EAPTLS_FILTER_PROP *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180010580`

## callees

- `0x180005010`
- `0x18000fe90`
- `0x180010140`
- `0x180010f10`
- `0x180011a00`
- `0x180011b24`
- `0x18001e0c0`
- `0x180032764`
- `0x1800339ec`
- `0x180061f9c`
- `0x180064000`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800114b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800114d5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800114b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800114d5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180011591`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800115ac`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180011591`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800115ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011515`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011545`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001156c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011515`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011545`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001156c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011610`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011621`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011632`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011641`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011610`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011621`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011632`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011641`
- `CRYPT32!CryptEnumOIDInfo` at `0x180011707`
- `CRYPT32!CryptEnumOIDInfo` at `0x1800117af`
- `CRYPT32!CryptEnumOIDInfo` at `0x180011707`
- `CRYPT32!CryptEnumOIDInfo` at `0x1800117af`
- `OLEAUT32!__imp_SysAllocString` at `0x180010fe9`
- `OLEAUT32!__imp_SysAllocString` at `0x180011098`
- `OLEAUT32!__imp_SysAllocString` at `0x180011205`
- `OLEAUT32!__imp_SysAllocString` at `0x180010fe9`
- `OLEAUT32!__imp_SysAllocString` at `0x180011098`
- `OLEAUT32!__imp_SysAllocString` at `0x180011205`
- `OLEAUT32!__imp_SysFreeString` at `0x180011036`
- `OLEAUT32!__imp_SysFreeString` at `0x1800110db`
- `OLEAUT32!__imp_SysFreeString` at `0x18001115e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011248`
- `OLEAUT32!__imp_SysFreeString` at `0x1800112cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180011422`
- `OLEAUT32!__imp_SysFreeString` at `0x180011433`
- `OLEAUT32!__imp_SysFreeString` at `0x18001186e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011882`
- `OLEAUT32!__imp_SysFreeString` at `0x1800119c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180011036`
- `OLEAUT32!__imp_SysFreeString` at `0x1800110db`
- `OLEAUT32!__imp_SysFreeString` at `0x18001115e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011248`
- `OLEAUT32!__imp_SysFreeString` at `0x1800112cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180011422`
- `OLEAUT32!__imp_SysFreeString` at `0x180011433`
- `OLEAUT32!__imp_SysFreeString` at `0x18001186e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011882`
- `OLEAUT32!__imp_SysFreeString` at `0x1800119c3`
- `OLEAUT32!__imp_SysStringLen` at `0x180011353`
- `OLEAUT32!__imp_SysStringLen` at `0x18001136f`
- `OLEAUT32!__imp_SysStringLen` at `0x180011353`
- `OLEAUT32!__imp_SysStringLen` at `0x18001136f`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ReadEKUMaps(struct IXMLDOMNode *a1, int a2, int a3, struct _EAPTLS_FILTER_PROP *a4)
{
  int v5; // r15d
  int v6; // r14d
  UINT v8; // r13d
  const OLECHAR *v9; // rsi
  const char *v10; // r9
  __int16 v11; // ax
  BSTR v12; // rax
  int v13; // ecx
  OLECHAR *v14; // rbx
  struct _EAPTLS_EKU_NODE *v15; // r12
  __int64 v16; // rdi
  BSTR v17; // rax
  int v18; // ecx
  OLECHAR *v19; // rbx
  unsigned int v20; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v21; // rax
  __int64 v22; // rdx
  int v23; // esi
  __int64 v24; // rdi
  BSTR v25; // rax
  int v26; // ecx
  OLECHAR *v27; // rbx
  __int64 v28; // rdx
  int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // r8
  UINT v32; // r15d
  __int64 i; // rdx
  OLECHAR *v34; // rbx
  UINT j; // ecx
  __int64 v36; // rax
  unsigned int v37; // edi
  _QWORD *v39; // rax
  BSTR v40; // r14
  _QWORD *v41; // rdi
  BSTR v42; // rdi
  HLOCAL v43; // rax
  HLOCAL v44; // rax
  char *v45; // rax
  DWORD LastError; // eax
  struct _EAPTLS_EKU_NODE *EKUNode; // rax
  struct _EAPTLS_FILTER_PROP *v48; // rax
  struct _EAPTLS_EKU_NODE **v49; // rdi
  struct _EAPTLS_EKU_NODE *v50; // rdx
  struct _EAPTLS_EKU_NODE *v51; // rax
  unsigned __int16 *v52; // r8
  unsigned __int16 *v53; // rcx
  __int64 v54; // r9
  __int64 v55; // rdx
  struct _EAPTLS_EKU_NODE *v56; // rax
  struct _EAPTLS_EKU_NODE *v57; // rdx
  struct _EAPTLS_EKU_NODE *v58; // rax
  unsigned __int16 *v59; // r8
  unsigned __int16 *v60; // rcx
  __int64 v61; // r9
  __int64 v62; // rdx
  struct _EAPTLS_EKU_NODE *v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rdx
  struct _EAPTLS_CONTROL_BLOCK *v66; // rcx
  __int64 v67; // rdx
  BSTR v68; // r9
  int v69; // [rsp+20h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-48h] BYREF
  BSTR pbstr; // [rsp+30h] [rbp-40h] BYREF
  BSTR v72; // [rsp+38h] [rbp-38h] BYREF
  __int64 v73; // [rsp+40h] [rbp-30h] BYREF
  struct _EAPTLS_EKU_NODE *pvArg; // [rsp+48h] [rbp-28h] BYREF
  __int64 v75; // [rsp+50h] [rbp-20h] BYREF
  int v76; // [rsp+58h] [rbp-18h] BYREF
  BSTR v77; // [rsp+60h] [rbp-10h]

  v5 = a3;
  v6 = a2;
  v8 = 0;
  v69 = 0;
  v75 = 0;
  v73 = 0;
  v76 = 0;
  pbstr = 0;
  bstrString = 0;
  pvArg = 0;
  if ( a2 || a3 )
  {
    if ( !GetAttributeValueFromNode(a1, L"Enabled", 0, &v69) && v69 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v10 = "Client Authentication";
        if ( !v6 )
          v10 = "Any Purpose";
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v10);
      }
      v11 = 2;
      if ( !v6 )
        v11 = 4;
      *(_WORD *)a4 |= v11;
    }
    v9 = L"eaptlsconnectionpropertiesv3:EKUMapInList";
  }
  else
  {
    v9 = L"eaptlsconnectionpropertiesv3:EKUMap";
  }
  v12 = SysAllocString(v9);
  v14 = v12;
  v72 = v12;
  if ( !v12 )
    ATL::AtlThrowImpl(v13);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))a1->lpVtbl->selectNodes)(a1, v12, &v75)
    || !v75 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v9);
    SysFreeString(v14);
    v20 = -2147024809;
    goto LABEL_179;
  }
  SysFreeString(v14);
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v75 + 64LL))(v75, &v76);
  v69 = 0;
  if ( v76 <= 0 )
  {
LABEL_175:
    v34 = bstrString;
LABEL_84:
    v37 = v69;
    goto LABEL_85;
  }
  v15 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v75 + 72LL))(v75, &v73);
  v69 = 0;
  while ( 1 )
  {
    v16 = v73;
    if ( !v73 )
      goto LABEL_175;
    v72 = 0;
    v17 = SysAllocString(L"eaptlsconnectionpropertiesv3:EKUName");
    v19 = v17;
    v77 = v17;
    if ( !v17 )
      ATL::AtlThrowImpl(v18);
    if ( !(*(unsigned int (__fastcall **)(__int64, BSTR, BSTR *))(*(_QWORD *)v16 + 296LL))(v16, v17, &v72) && v72 )
    {
      SysFreeString(v19);
      v20 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)v72 + 208LL))(v72, &pbstr);
      if ( !v20 )
        goto LABEL_33;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_34;
      v22 = 11;
LABEL_32:
      WPP_SF_S(
        *((_QWORD *)v21 + 2),
        v22,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv3:EKUName");
LABEL_33:
      v21 = WPP_GLOBAL_Control;
      goto LABEL_34;
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv3:EKUName");
    SysFreeString(v19);
    v20 = -2147024809;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v22 = 10;
      goto LABEL_32;
    }
LABEL_34:
    if ( v72 )
    {
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v72 + 16LL))(v72);
      v21 = WPP_GLOBAL_Control;
    }
    if ( v20 && !v6 && !v5 )
    {
      if ( v21 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_179;
      v65 = 181;
      goto LABEL_154;
    }
    v23 = 0;
    if ( !v20 )
    {
      v23 = 1;
      if ( v21 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_S(*((_QWORD *)v21 + 2), 182, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, pbstr);
    }
    v72 = 0;
    v24 = v73;
    v25 = SysAllocString(L"eaptlsconnectionpropertiesv3:EKUOID");
    v27 = v25;
    v77 = v25;
    if ( !v25 )
      ATL::AtlThrowImpl(v26);
    if ( !(*(unsigned int (__fastcall **)(__int64, BSTR, BSTR *))(*(_QWORD *)v24 + 296LL))(v24, v25, &v72) && v72 )
    {
      SysFreeString(v27);
      v20 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)v72 + 208LL))(v72, &bstrString);
      if ( !v20 )
        goto LABEL_54;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_55;
      v28 = 11;
LABEL_53:
      WPP_SF_S(
        *((_QWORD *)v21 + 2),
        v28,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv3:EKUOID");
LABEL_54:
      v21 = WPP_GLOBAL_Control;
      goto LABEL_55;
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv3:EKUOID");
    SysFreeString(v27);
    v20 = -2147024809;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v28 = 10;
      goto LABEL_53;
    }
LABEL_55:
    if ( v72 )
    {
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v72 + 16LL))(v72);
      v21 = WPP_GLOBAL_Control;
    }
    if ( v20 )
    {
      if ( v23 )
      {
        if ( !v6 && !v5 )
          goto LABEL_157;
        v29 = 0;
        goto LABEL_63;
      }
      if ( v6 || v5 )
      {
        if ( v21 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v65 = 183;
          goto LABEL_154;
        }
      }
      else
      {
LABEL_157:
        if ( v21 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v65 = 184;
LABEL_154:
          WPP_SF_d(*((_QWORD *)v21 + 2), v65, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v20);
        }
      }
LABEL_179:
      v37 = (unsigned __int16)v20;
      if ( (v20 & 0x1FFF0000) != 0x70000 )
        v37 = v20;
      goto LABEL_166;
    }
    v29 = 1;
    if ( !v23 )
      goto LABEL_65;
LABEL_63:
    v8 = SysStringLen(pbstr);
    if ( v29 )
    {
LABEL_65:
      v32 = SysStringLen(bstrString);
      goto LABEL_66;
    }
    v32 = 0;
LABEL_66:
    if ( v6 || a3 )
      break;
    if ( !v8 )
      goto LABEL_175;
    for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
    {
      if ( pbstr[i] == 59 )
        goto LABEL_175;
    }
    if ( !v32 )
      goto LABEL_175;
    v34 = bstrString;
    if ( bstrString[v32 - 1] == 46 || *bstrString == 46 )
      goto LABEL_84;
    v30 = 32;
    v31 = 0;
    for ( j = 0; j < v32; ++j )
    {
      v36 = j;
      if ( (_WORD)v30 == 46 && bstrString[v36] == 46 || (_DWORD)v31 )
        goto LABEL_84;
      v30 = bstrString[v36];
      if ( (_WORD)v30 != 46 )
      {
        if ( (_WORD)v30 == 42 )
        {
          v31 = 1;
        }
        else if ( (unsigned __int16)(v30 - 48) > 9u )
        {
          goto LABEL_84;
        }
      }
    }
    v39 = (_QWORD *)*((_QWORD *)a4 + 2);
    if ( v39 )
    {
      v40 = pbstr;
      v41 = (_QWORD *)*v39;
      if ( *v39 )
      {
        while ( (int)_o__wcsicmp(v41[1], v40) < 0 )
        {
          v41 = (_QWORD *)*v41;
          if ( !v41 )
            goto LABEL_98;
        }
        if ( (unsigned int)_o__wcsicmp(v40, v41[1]) )
        {
LABEL_98:
          v34 = bstrString;
          goto LABEL_99;
        }
        v66 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_165;
        v67 = 185;
LABEL_163:
        v68 = pbstr;
        goto LABEL_164;
      }
LABEL_99:
      v6 = a2;
    }
    v42 = pbstr;
    if ( !pbstr || !(_WORD)v8 || !v34 || !(_WORD)v32 || (v15 = (struct _EAPTLS_EKU_NODE *)LocalAlloc(0x40u, 0x30u)) == 0 )
    {
      v8 = 0;
      v15 = 0;
      goto LABEL_149;
    }
    v43 = LocalAlloc(0x40u, 2LL * (unsigned __int16)v8 + 2);
    *((_QWORD *)v15 + 1) = v43;
    if ( v43
      && (v44 = LocalAlloc(0x40u, 2LL * (unsigned __int16)v32 + 2), (*((_QWORD *)v15 + 2) = v44) != 0)
      && (_o_wcsncpy_s(*((_QWORD *)v15 + 1), (unsigned __int16)v8 + 1LL, v42, (unsigned __int16)v8),
          _o_wcsncpy_s(*((_QWORD *)v15 + 2), (unsigned __int16)v32 + 1LL, v34, (unsigned __int16)v32),
          v45 = StrdupWtoA(*((LPCWCH *)v15 + 2)),
          (*((_QWORD *)v15 + 3) = v45) != 0)
      || (LastError = GetLastError()) == 0 )
    {
      SortedEKUInsert((struct _EAPTLS_EKU_NODE **)a4 + 2, v15);
      v6 = a2;
LABEL_148:
      v8 = 0;
      goto LABEL_149;
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_c4e812f99669349517681909258710e2_Traceguids, LastError);
    LocalFree(*((HLOCAL *)v15 + 2));
    LocalFree(*((HLOCAL *)v15 + 3));
    LocalFree(*((HLOCAL *)v15 + 1));
    LocalFree(v15);
    v8 = 0;
    v15 = 0;
    v6 = a2;
LABEL_149:
    v64 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v64 + 16LL))(v64, v30, v31);
    }
    SysFreeString(pbstr);
    pbstr = 0;
    SysFreeString(bstrString);
    bstrString = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v75 + 72LL))(v75, &v73);
    v5 = a3;
  }
  if ( v23 )
  {
    if ( v29 )
    {
      v15 = isDuplicateEKUName(pbstr, *((struct _EAPTLS_EKU_NODE **)a4 + 2));
      if ( !v15 )
      {
        EKUNode = createEKUNode(pbstr, v8, bstrString, v32);
        v15 = EKUNode;
        if ( !EKUNode )
          goto LABEL_167;
        SortedEKUInsert((struct _EAPTLS_EKU_NODE **)a4 + 2, EKUNode);
      }
    }
    v48 = a4;
    v49 = (struct _EAPTLS_EKU_NODE **)((char *)a4 + 16);
    goto LABEL_131;
  }
  v49 = (struct _EAPTLS_EKU_NODE **)((char *)a4 + 16);
  v15 = isDuplicateEKUOID(bstrString, *((struct _EAPTLS_EKU_NODE **)a4 + 2));
  if ( v15 )
  {
LABEL_130:
    v48 = a4;
LABEL_131:
    if ( !v29 )
    {
      v15 = isDuplicateEKUName(pbstr, *v49);
      if ( !v15 )
      {
        v57 = pvArg;
        if ( pvArg )
        {
          CryptEnumOIDInfo(7u, 0, &pvArg, CryptEnumOIDCallBack);
          v57 = pvArg;
        }
        v58 = isDuplicateEKUName(pbstr, v57);
        if ( !v58 )
        {
          v66 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_165;
          v67 = 187;
          goto LABEL_163;
        }
        v59 = (unsigned __int16 *)*((_QWORD *)v58 + 2);
        v60 = (unsigned __int16 *)*((_QWORD *)v58 + 1);
        v61 = -1;
        do
          ++v61;
        while ( v59[v61] );
        v62 = -1;
        do
          ++v62;
        while ( v60[v62] );
        v63 = createEKUNode(v60, v62, v59, v61);
        v15 = v63;
        if ( !v63 )
        {
          v37 = 1359;
          goto LABEL_166;
        }
        SortedEKUInsert(v49, v63);
      }
      v48 = a4;
    }
    if ( v6 )
    {
      if ( !*((_DWORD *)v15 + 9) )
      {
        ++*((_WORD *)v48 + 12);
        *((_DWORD *)v15 + 9) = 1;
      }
    }
    else if ( !*((_DWORD *)v15 + 10) )
    {
      *((_DWORD *)v15 + 10) = 1;
      ++*((_WORD *)v48 + 13);
    }
    goto LABEL_148;
  }
  v50 = pvArg;
  if ( pvArg )
  {
    CryptEnumOIDInfo(7u, 0, &pvArg, CryptEnumOIDCallBack);
    v50 = pvArg;
  }
  v51 = isDuplicateEKUOID(bstrString, v50);
  if ( v51 )
  {
    v52 = (unsigned __int16 *)*((_QWORD *)v51 + 2);
    v53 = (unsigned __int16 *)*((_QWORD *)v51 + 1);
    v54 = -1;
    do
      ++v54;
    while ( v52[v54] );
    v55 = -1;
    do
      ++v55;
    while ( v53[v55] );
    v56 = createEKUNode(v53, v55, v52, v54);
    v15 = v56;
    if ( !v56 )
    {
LABEL_167:
      v37 = 1359;
      v34 = bstrString;
      goto LABEL_85;
    }
    SortedEKUInsert(v49, v56);
    goto LABEL_130;
  }
  v66 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v67 = 186;
    v68 = bstrString;
LABEL_164:
    WPP_SF_S(*((_QWORD *)v66 + 2), v67, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v68);
  }
LABEL_165:
  v37 = 13;
LABEL_166:
  v34 = bstrString;
LABEL_85:
  SysFreeString(v34);
  SysFreeString(pbstr);
  if ( v73 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
  if ( v75 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
  return v37;
}

```

## disassembly

```asm
0x180010f10  mov     [rsp-38h+arg_0], rbx
0x180010f15  mov     [rsp-38h+arg_18], r9
0x180010f1a  mov     [rsp-38h+arg_10], r8d
0x180010f1f  mov     [rsp-38h+arg_8], edx
0x180010f23  push    rbp
0x180010f24  push    rsi
0x180010f25  push    rdi
0x180010f26  push    r12
0x180010f28  push    r13
0x180010f2a  push    r14
0x180010f2c  push    r15
0x180010f2e  mov     rbp, rsp
0x180010f31  sub     rsp, 70h
0x180010f35  mov     rbx, r9
0x180010f38  mov     r15d, r8d
0x180010f3b  mov     r14d, edx
0x180010f3e  mov     rdi, rcx
0x180010f41  xor     r13d, r13d
0x180010f44  mov     [rbp+var_50], r13d
0x180010f48  mov     [rbp+var_20], r13
0x180010f4c  mov     [rbp+var_30], r13
0x180010f50  mov     [rbp+var_18], r13d
0x180010f54  mov     [rbp+pbstr], r13
0x180010f58  mov     [rbp+bstrString], r13
0x180010f5c  mov     [rbp+pvArg], r13
0x180010f60  lea     r12, WPP_GLOBAL_Control
0x180010f67  test    edx, edx
0x180010f69  jnz     short loc_180010F79
0x180010f6b  test    r8d, r8d
0x180010f6e  jnz     short loc_180010F79
0x180010f70  lea     rsi, aEaptlsconnecti_14; "eaptlsconnectionpropertiesv3:EKUMap"
0x180010f77  jmp     short loc_180010FE6
0x180010f79  lea     r9, [rbp+var_50]; int *
0x180010f7d  xor     r8d, r8d; int
0x180010f80  lea     rdx, aEnabled; "Enabled"
0x180010f87  call    ?GetAttributeValueFromNode@@YAJPEAUIXMLDOMNode@@PEAGHPEAH@Z; GetAttributeValueFromNode(IXMLDOMNode *,ushort *,int,int *)
0x180010f8c  test    eax, eax
0x180010f8e  jnz     short loc_180010FDF
0x180010f90  cmp     [rbp+var_50], eax
0x180010f93  jz      short loc_180010FDF
0x180010f95  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f9c  cmp     rcx, r12
0x180010f9f  jz      short loc_180010FCB
0x180010fa1  lea     rax, aAnyPurpose; "Any Purpose"
0x180010fa8  lea     r9, aClientAuthenti_0; "Client Authentication"
0x180010faf  test    r14d, r14d
0x180010fb2  cmovz   r9, rax
0x180010fb6  mov     edx, 0B4h
0x180010fbb  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180010fc2  mov     rcx, [rcx+10h]
0x180010fc6  call    WPP_SF_s
0x180010fcb  mov     eax, 2
0x180010fd0  mov     ecx, 4
0x180010fd5  test    r14d, r14d
0x180010fd8  cmovz   ax, cx
0x180010fdc  or      [rbx], ax
0x180010fdf  lea     rsi, aEaptlsconnecti_11; "eaptlsconnectionpropertiesv3:EKUMapInLi"...
0x180010fe6  mov     rcx, rsi; psz
0x180010fe9  call    cs:__imp_SysAllocString
0x180010ff0  nop     dword ptr [rax+rax+00h]
0x180010ff5  mov     rbx, rax
0x180010ff8  mov     [rbp+var_38], rax
0x180010ffc  test    rax, rax
0x180010fff  jnz     short loc_180011007
0x180011001  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011007  mov     rax, [rdi]
0x18001100a  lea     r8, [rbp+var_20]
0x18001100e  mov     rdx, rbx
0x180011011  mov     rcx, rdi
0x180011014  mov     rax, [rax+120h]
0x18001101b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011020  test    eax, eax
0x180011022  jnz     loc_18001199B
0x180011028  cmp     [rbp+var_20], 0
0x18001102d  jz      loc_18001199B
0x180011033  mov     rcx, rbx; bstrString
0x180011036  call    cs:__imp_SysFreeString
0x18001103d  nop     dword ptr [rax+rax+00h]
0x180011042  mov     rcx, [rbp+var_20]
0x180011046  mov     rax, [rcx]
0x180011049  lea     rdx, [rbp+var_18]
0x18001104d  mov     rax, [rax+40h]
0x180011051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011056  mov     [rbp+var_50], r13d
0x18001105a  cmp     [rbp+var_18], 0
0x18001105e  jle     loc_180011992
0x180011064  mov     r12, r13
0x180011067  mov     rcx, [rbp+var_20]
0x18001106b  mov     rax, [rcx]
0x18001106e  lea     rdx, [rbp+var_30]
0x180011072  mov     rax, [rax+48h]
0x180011076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001107b  mov     [rbp+var_50], r13d
0x18001107f  nop
0x180011080  mov     rdi, [rbp+var_30]
0x180011084  test    rdi, rdi
0x180011087  jz      loc_180011992
0x18001108d  mov     [rbp+var_38], r13
0x180011091  lea     rcx, aEaptlsconnecti_6; "eaptlsconnectionpropertiesv3:EKUName"
0x180011098  call    cs:__imp_SysAllocString
0x18001109f  nop     dword ptr [rax+rax+00h]
0x1800110a4  mov     rbx, rax
0x1800110a7  mov     [rbp+var_10], rax
0x1800110ab  test    rax, rax
0x1800110ae  jz      loc_18001198C
0x1800110b4  mov     rax, [rdi]
0x1800110b7  lea     r8, [rbp+var_38]
0x1800110bb  mov     rdx, rbx
0x1800110be  mov     rcx, rdi
0x1800110c1  mov     rax, [rax+128h]
0x1800110c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110cd  test    eax, eax
0x1800110cf  jnz     short loc_18001112B
0x1800110d1  cmp     [rbp+var_38], 0
0x1800110d6  jz      short loc_18001112B
0x1800110d8  mov     rcx, rbx; bstrString
0x1800110db  call    cs:__imp_SysFreeString
0x1800110e2  nop     dword ptr [rax+rax+00h]
0x1800110e7  mov     rcx, [rbp+var_38]
0x1800110eb  mov     rax, [rcx]
0x1800110ee  lea     rdx, [rbp+pbstr]
0x1800110f2  mov     rax, [rax+0D0h]
0x1800110f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110fe  mov     ebx, eax
0x180011100  test    eax, eax
0x180011102  jz      short loc_180011122
0x180011104  mov     rax, cs:WPP_GLOBAL_Control
0x18001110b  lea     rdi, WPP_GLOBAL_Control
0x180011112  cmp     rax, rdi
0x180011115  jz      loc_18001119E
0x18001111b  mov     edx, 0Bh
0x180011120  jmp     short loc_180011180
0x180011122  lea     rdi, WPP_GLOBAL_Control
0x180011129  jmp     short loc_180011197
0x18001112b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011132  lea     rdi, WPP_GLOBAL_Control
0x180011139  cmp     rcx, rdi
0x18001113c  jz      short loc_18001115B
0x18001113e  mov     edx, 0FCh
0x180011143  lea     r9, aEaptlsconnecti_6; "eaptlsconnectionpropertiesv3:EKUName"
0x18001114a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180011151  mov     rcx, [rcx+10h]
0x180011155  call    WPP_SF_S
0x18001115a  nop
0x18001115b  mov     rcx, rbx; bstrString
0x18001115e  call    cs:__imp_SysFreeString
0x180011165  nop     dword ptr [rax+rax+00h]
0x18001116a  mov     ebx, 80070057h
0x18001116f  mov     rax, cs:WPP_GLOBAL_Control
0x180011176  cmp     rax, rdi
0x180011179  jz      short loc_18001119E
0x18001117b  mov     edx, 0Ah
0x180011180  lea     r9, aEaptlsconnecti_6; "eaptlsconnectionpropertiesv3:EKUName"
0x180011187  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001118e  mov     rcx, [rax+10h]
0x180011192  call    WPP_SF_S
0x180011197  mov     rax, cs:WPP_GLOBAL_Control
0x18001119e  mov     rcx, [rbp+var_38]
0x1800111a2  test    rcx, rcx
0x1800111a5  jz      short loc_1800111BA
0x1800111a7  mov     rax, [rcx]
0x1800111aa  mov     rax, [rax+10h]
0x1800111ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800111ba  test    ebx, ebx
0x1800111bc  jz      short loc_1800111CC
0x1800111be  test    r14d, r14d
0x1800111c1  jnz     short loc_1800111CC
0x1800111c3  test    r15d, r15d
0x1800111c6  jz      loc_1800118AF
0x1800111cc  mov     esi, r13d
0x1800111cf  test    ebx, ebx
0x1800111d1  jnz     short loc_1800111F6
0x1800111d3  mov     esi, 1
0x1800111d8  cmp     rax, rdi
0x1800111db  jz      short loc_1800111F6
0x1800111dd  mov     edx, 0B6h
0x1800111e2  mov     r9, [rbp+pbstr]
0x1800111e6  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800111ed  mov     rcx, [rax+10h]
0x1800111f1  call    WPP_SF_S
0x1800111f6  mov     [rbp+var_38], r13
0x1800111fa  mov     rdi, [rbp+var_30]
0x1800111fe  lea     rcx, aEaptlsconnecti_12; "eaptlsconnectionpropertiesv3:EKUOID"
0x180011205  call    cs:__imp_SysAllocString
0x18001120c  nop     dword ptr [rax+rax+00h]
0x180011211  mov     rbx, rax
0x180011214  mov     [rbp+var_10], rax
0x180011218  test    rax, rax
0x18001121b  jz      loc_180011986
0x180011221  mov     rax, [rdi]
0x180011224  lea     r8, [rbp+var_38]
0x180011228  mov     rdx, rbx
0x18001122b  mov     rcx, rdi
0x18001122e  mov     rax, [rax+128h]
0x180011235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001123a  test    eax, eax
0x18001123c  jnz     short loc_180011298
0x18001123e  cmp     [rbp+var_38], 0
0x180011243  jz      short loc_180011298
0x180011245  mov     rcx, rbx; bstrString
0x180011248  call    cs:__imp_SysFreeString
0x18001124f  nop     dword ptr [rax+rax+00h]
0x180011254  mov     rcx, [rbp+var_38]
0x180011258  mov     rax, [rcx]
0x18001125b  lea     rdx, [rbp+bstrString]
0x18001125f  mov     rax, [rax+0D0h]
0x180011266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001126b  mov     ebx, eax
0x18001126d  test    eax, eax
0x18001126f  jz      short loc_18001128F
0x180011271  mov     rax, cs:WPP_GLOBAL_Control
0x180011278  lea     rdi, WPP_GLOBAL_Control
0x18001127f  cmp     rax, rdi
0x180011282  jz      loc_18001130B
0x180011288  mov     edx, 0Bh
0x18001128d  jmp     short loc_1800112ED
0x18001128f  lea     rdi, WPP_GLOBAL_Control
0x180011296  jmp     short loc_180011304
0x180011298  mov     rcx, cs:WPP_GLOBAL_Control
0x18001129f  lea     rdi, WPP_GLOBAL_Control
0x1800112a6  cmp     rcx, rdi
0x1800112a9  jz      short loc_1800112C8
0x1800112ab  mov     edx, 0FCh
0x1800112b0  lea     r9, aEaptlsconnecti_12; "eaptlsconnectionpropertiesv3:EKUOID"
0x1800112b7  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800112be  mov     rcx, [rcx+10h]
0x1800112c2  call    WPP_SF_S
0x1800112c7  nop
0x1800112c8  mov     rcx, rbx; bstrString
0x1800112cb  call    cs:__imp_SysFreeString
0x1800112d2  nop     dword ptr [rax+rax+00h]
0x1800112d7  mov     ebx, 80070057h
0x1800112dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800112e3  cmp     rax, rdi
0x1800112e6  jz      short loc_18001130B
0x1800112e8  mov     edx, 0Ah
0x1800112ed  lea     r9, aEaptlsconnecti_12; "eaptlsconnectionpropertiesv3:EKUOID"
0x1800112f4  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800112fb  mov     rcx, [rax+10h]
0x1800112ff  call    WPP_SF_S
0x180011304  mov     rax, cs:WPP_GLOBAL_Control
0x18001130b  mov     rcx, [rbp+var_38]
0x18001130f  test    rcx, rcx
0x180011312  jz      short loc_180011327
0x180011314  mov     rax, [rcx]
0x180011317  mov     rax, [rax+10h]
0x18001131b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011320  mov     rax, cs:WPP_GLOBAL_Control
0x180011327  test    ebx, ebx
0x180011329  jz      short loc_180011346
0x18001132b  test    esi, esi
0x18001132d  jz      loc_1800118D5
0x180011333  test    r14d, r14d
0x180011336  jnz     short loc_180011341
0x180011338  test    r15d, r15d
0x18001133b  jz      loc_1800118DF
0x180011341  mov     ebx, r13d
0x180011344  jmp     short loc_18001134F
0x180011346  mov     ebx, 1
0x18001134b  test    esi, esi
0x18001134d  jz      short loc_18001136B
0x18001134f  mov     rcx, [rbp+pbstr]; pbstr
0x180011353  call    cs:__imp_SysStringLen
0x18001135a  nop     dword ptr [rax+rax+00h]
0x18001135f  mov     r13d, eax
0x180011362  test    ebx, ebx
0x180011364  jnz     short loc_18001136B
0x180011366  xor     r15d, r15d
0x180011369  jmp     short loc_18001137E
0x18001136b  mov     rcx, [rbp+bstrString]; pbstr
0x18001136f  call    cs:__imp_SysStringLen
0x180011376  nop     dword ptr [rax+rax+00h]
0x18001137b  mov     r15d, eax
0x18001137e  test    r14d, r14d
0x180011381  jnz     loc_180011671
0x180011387  cmp     [rbp+arg_10], r14d
0x18001138b  jnz     loc_180011671
0x180011391  test    r13d, r13d
0x180011394  jz      loc_180011992
0x18001139a  xor     edx, edx
0x18001139c  cmp     edx, r13d
0x18001139f  jnb     short loc_1800113B4
0x1800113a1  mov     rax, [rbp+pbstr]
0x1800113a5  cmp     word ptr [rax+rdx*2], 3Bh ; ';'
0x1800113aa  jz      loc_180011992
0x1800113b0  inc     edx
0x1800113b2  jmp     short loc_18001139C
0x1800113b4  test    r15d, r15d
0x1800113b7  jz      loc_180011992
0x1800113bd  lea     eax, [r15-1]
0x1800113c1  mov     rbx, [rbp+bstrString]
0x1800113c5  cmp     word ptr [rbx+rax*2], 2Eh ; '.'
0x1800113ca  jz      short loc_18001141C
0x1800113cc  cmp     word ptr [rbx], 2Eh ; '.'
0x1800113d0  jz      short loc_18001141C
0x1800113d2  mov     edx, 20h ; ' '
0x1800113d7  xor     r8d, r8d
0x1800113da  xor     ecx, ecx
0x1800113dc  nop     dword ptr [rax+00h]
  ... truncated ...
```
