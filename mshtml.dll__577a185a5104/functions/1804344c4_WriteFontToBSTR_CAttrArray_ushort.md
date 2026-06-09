# WriteFontToBSTR(CAttrArray *,ushort * *)

- ea: `0x1804344c4`
- end: `0x1804355e2`
- name: `?WriteFontToBSTR@@YAJPEAVCAttrArray@@PEAPEAG@Z`
- size: `4382`
- prototype: `__int64 __fastcall(struct CAttrArray *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180315500`
- `0x180433db0`

## callees

- `0x18000e610`
- `0x1800168c0`
- `0x1800170d0`
- `0x18005ce98`
- `0x18005e648`
- `0x18005e684`
- `0x1803d0178`
- `0x18042ebb0`
- `0x180431d50`
- `0x1804344c4`
- `0x1809db23c`
- `0x181104010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180435449`
- `KERNEL32!CompareStringW` at `0x180435485`
- `KERNEL32!CompareStringW` at `0x1804354c1`
- `KERNEL32!CompareStringW` at `0x1804354fd`
- `KERNEL32!CompareStringW` at `0x180435449`
- `KERNEL32!CompareStringW` at `0x180435485`
- `KERNEL32!CompareStringW` at `0x1804354c1`
- `KERNEL32!CompareStringW` at `0x1804354fd`
- `OLEAUT32!__imp_SysAllocString` at `0x180434f0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180434f0b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180434d1f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180434d1f`
- `OLEAUT32!__imp_SysFreeString` at `0x180434a05`
- `OLEAUT32!__imp_SysFreeString` at `0x180434a9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180434b34`
- `OLEAUT32!__imp_SysFreeString` at `0x180434caa`
- `OLEAUT32!__imp_SysFreeString` at `0x180434a05`
- `OLEAUT32!__imp_SysFreeString` at `0x180434a9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180434b34`
- `OLEAUT32!__imp_SysFreeString` at `0x180434caa`
- `OLEAUT32!__imp_VariantInit` at `0x180434511`
- `OLEAUT32!__imp_VariantInit` at `0x180434511`
- `OLEAUT32!__imp_VariantClear` at `0x180434ba8`
- `OLEAUT32!__imp_VariantClear` at `0x180434cba`
- `OLEAUT32!__imp_VariantClear` at `0x180434ba8`
- `OLEAUT32!__imp_VariantClear` at `0x180434cba`

## pseudocode

```c
__int64 __fastcall WriteFontToBSTR(struct CAttrArray *a1, unsigned __int16 **a2)
{
  int v2; // esi
  unsigned __int64 v3; // rbx
  int v4; // r11d
  int v5; // r8d
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  int v8; // eax
  CAttrValue *v9; // r13
  unsigned __int64 v10; // r10
  unsigned __int64 v11; // rdx
  int v12; // r8d
  unsigned __int64 v13; // r8
  int v14; // eax
  CAttrValue *v15; // r12
  int v16; // r8d
  int v17; // r11d
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // r8
  int v20; // eax
  CAttrValue *v21; // r15
  unsigned __int64 v22; // r10
  unsigned __int64 v23; // rdx
  int v24; // r8d
  unsigned __int64 v25; // r8
  int v26; // eax
  CAttrValue *v27; // r14
  unsigned __int64 v28; // r10
  unsigned __int64 v29; // rdx
  int v30; // r8d
  unsigned __int64 v31; // r8
  int v32; // eax
  CAttrValue *v33; // rdi
  unsigned __int64 v34; // rdx
  int v35; // r10d
  int v36; // r11d
  int v37; // eax
  _BYTE *v38; // rcx
  char v39; // r11
  char v40; // al
  char v41; // r10
  char v42; // r9
  char v43; // r8
  char v44; // dl
  unsigned int v45; // ebx
  int v47; // r9d
  int v48; // r9d
  int v49; // r9d
  int v50; // r8d
  int v51; // eax
  int v52; // r9d
  int v53; // r9d
  int v54; // r9d
  int DISPID; // eax
  int v56; // r11d
  unsigned int v57; // edi
  int v58; // eax
  unsigned __int16 *v59; // rdx
  const WCHAR *v60; // rbx
  BSTR v61; // r10
  const WCHAR *lpString2; // r9
  WCHAR v63; // r8
  WCHAR v64; // cx
  int v65; // eax
  int v66; // eax
  BSTR v67; // r10
  const WCHAR *v68; // r9
  WCHAR v69; // r8
  WCHAR v70; // cx
  int v71; // eax
  int v72; // eax
  BSTR v73; // r10
  const WCHAR *v74; // r9
  WCHAR v75; // r8
  WCHAR v76; // cx
  int v77; // eax
  const WCHAR *bstrVal; // r10
  WCHAR v79; // r8
  WCHAR v80; // cx
  int v81; // eax
  __int64 v82; // r9
  const OLECHAR *v83; // rsi
  int v84; // ebx
  __int64 Inl; // rax
  char v86; // cl
  int v87; // ebx
  void *v88; // r8
  OLECHAR *v89; // rdi
  unsigned __int16 *v90; // rax
  MemoryProtection *v91; // rcx
  unsigned __int16 *v92; // rbx
  void *v93; // r8
  int v94; // eax
  bool v95; // sf
  int v96; // eax
  int v97; // r10d
  int v98; // eax
  int v99; // r10d
  int v100; // eax
  int v101; // r11d
  int v102; // eax
  int v103; // r11d
  int i; // r11d
  int v105; // r11d
  CAttrValue *v106; // rcx
  int ii; // r9d
  int v108; // eax
  int v109; // r9d
  int j; // r10d
  int v111; // eax
  int v112; // r10d
  int k; // r10d
  int v114; // eax
  int v115; // r10d
  int m; // r11d
  int v117; // r11d
  int n; // r11d
  int v119; // r11d
  int v120; // eax
  int v121; // eax
  int v122; // eax
  int v123; // eax
  bool v124; // zf
  __int64 v125; // rcx
  int v126; // eax
  BSTR bstrString; // [rsp+30h] [rbp-30h] BYREF
  OLECHAR *strIn; // [rsp+38h] [rbp-28h] BYREF
  const OLECHAR *v129; // [rsp+40h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-18h] BYREF
  struct CAttrArray *v131; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 **v132; // [rsp+A8h] [rbp+48h]

  v132 = a2;
  v131 = a1;
  strIn = 0;
  bstrString = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  *a2 = 0;
  if ( !v131 )
    return 1;
  VariantInit(&pvarg);
  v2 = *((_DWORD *)v131 + 1);
  v3 = *((_QWORD *)v131 + 1);
  v4 = -2147413085;
  v5 = v2;
  if ( v2 < 11 )
  {
    v6 = *((_QWORD *)v131 + 1);
    goto LABEL_4;
  }
  v53 = 0;
  while ( 1 )
  {
    if ( v53 >= v5 )
    {
      v9 = 0;
LABEL_107:
      v10 = v3;
LABEL_108:
      v54 = 0;
      v12 = v2;
      while ( 1 )
      {
        if ( v54 >= v12 )
          goto LABEL_21;
        DISPID = CAttrValue::GetDISPID((CAttrValue *)(v10 + 24LL * ((v12 + v54) / 2)));
        if ( DISPID <= -2147413088 )
        {
          if ( DISPID < -2147413088 )
          {
            v54 = v56 + 1;
            goto LABEL_112;
          }
          if ( !*(_BYTE *)v11 )
          {
LABEL_236:
            v15 = (CAttrValue *)v11;
            goto LABEL_22;
          }
          if ( *(_BYTE *)v11 <= 2u )
          {
            v15 = (CAttrValue *)(v11 - 24);
            for ( i = v56 - 1; i >= v54 && (unsigned int)CAttrValue::GetDISPID(v15) == -2147413088; i = v105 - 1 )
            {
              if ( !*(_BYTE *)v15 )
                goto LABEL_22;
              if ( v105 == v54 )
                break;
              v15 = (CAttrValue *)((char *)v15 - 24);
            }
            goto LABEL_14;
          }
        }
        v12 = v56;
LABEL_112:
        if ( v12 - v54 < 10 )
        {
          v11 = v10 + 24LL * v54;
          goto LABEL_14;
        }
      }
    }
    v96 = CAttrValue::GetDISPID((CAttrValue *)(v3 + 24LL * ((v5 + v53) / 2)));
    if ( v96 <= v4 )
    {
      if ( v96 < v4 )
      {
        v53 = v97 + 1;
        goto LABEL_250;
      }
      if ( !*(_BYTE *)v6 )
      {
        v9 = (CAttrValue *)v6;
        goto LABEL_107;
      }
      if ( *(_BYTE *)v6 <= 2u )
        break;
    }
    v5 = v97;
LABEL_250:
    if ( v5 - v53 < 10 )
    {
      v6 = v3 + 24LL * v53;
      goto LABEL_4;
    }
  }
  v9 = (CAttrValue *)(v6 - 24);
  for ( j = v97 - 1; j >= v53; j = v112 - 1 )
  {
    v111 = CAttrValue::GetDISPID(v9);
    if ( v111 != v4 )
      break;
    if ( !*(_BYTE *)v9 )
      goto LABEL_107;
    if ( v112 == v53 )
      break;
    v9 = (CAttrValue *)((char *)v9 - 24);
  }
LABEL_4:
  v7 = v3 + 24LL * v5;
  while ( 2 )
  {
    if ( v6 >= v7 )
    {
LABEL_11:
      v9 = 0;
      goto LABEL_12;
    }
    if ( *(char *)(v6 + 3) >= 0 )
      v8 = *(_DWORD *)(*(_QWORD *)(v6 + 8) + 48LL);
    else
      v8 = *(_DWORD *)(v6 + 8);
    if ( v8 < v4 )
    {
LABEL_9:
      v6 += 24LL;
      continue;
    }
    break;
  }
  if ( v8 != v4 )
    goto LABEL_11;
  if ( *(_BYTE *)v6 )
  {
    if ( *(_BYTE *)v6 > 2u )
      goto LABEL_11;
    goto LABEL_9;
  }
  v9 = (CAttrValue *)v6;
LABEL_12:
  v10 = v3;
  if ( v2 >= 11 )
    goto LABEL_108;
  v11 = v3;
  v12 = v2;
LABEL_14:
  v13 = v10 + 24LL * v12;
  while ( v11 < v13 )
  {
    if ( *(char *)(v11 + 3) >= 0 )
      v14 = *(_DWORD *)(*(_QWORD *)(v11 + 8) + 48LL);
    else
      v14 = *(_DWORD *)(v11 + 8);
    if ( v14 >= -2147413088 )
    {
      if ( v14 != -2147413088 )
        break;
      if ( !*(_BYTE *)v11 )
        goto LABEL_236;
      if ( *(_BYTE *)v11 > 2u )
        break;
    }
    v11 += 24LL;
  }
LABEL_21:
  v15 = 0;
LABEL_22:
  v16 = v2;
  v17 = -2147413087;
  if ( v2 < 11 )
  {
    v18 = v3;
    goto LABEL_24;
  }
  v47 = 0;
  while ( 2 )
  {
    if ( v47 >= v16 )
    {
      v21 = 0;
LABEL_84:
      v22 = v3;
      goto LABEL_85;
    }
    v98 = CAttrValue::GetDISPID((CAttrValue *)(v3 + 24LL * ((v16 + v47) / 2)));
    if ( v98 > v17 )
    {
LABEL_253:
      v16 = v99;
      goto LABEL_254;
    }
    if ( v98 < v17 )
    {
      v47 = v99 + 1;
LABEL_254:
      if ( v16 - v47 < 10 )
      {
        v18 = v3 + 24LL * v47;
        goto LABEL_24;
      }
      continue;
    }
    break;
  }
  if ( !*(_BYTE *)v18 )
  {
    v21 = (CAttrValue *)v18;
    goto LABEL_84;
  }
  if ( *(_BYTE *)v18 > 2u )
    goto LABEL_253;
  v21 = (CAttrValue *)(v18 - 24);
  for ( k = v99 - 1; k >= v47; k = v115 - 1 )
  {
    v114 = CAttrValue::GetDISPID(v21);
    if ( v114 != v17 )
      break;
    if ( !*(_BYTE *)v21 )
      goto LABEL_84;
    if ( v115 == v47 )
      break;
    v21 = (CAttrValue *)((char *)v21 - 24);
  }
LABEL_24:
  v19 = v3 + 24LL * v16;
  while ( 2 )
  {
    if ( v18 >= v19 )
    {
LABEL_31:
      v21 = 0;
      goto LABEL_32;
    }
    if ( *(char *)(v18 + 3) >= 0 )
      v20 = *(_DWORD *)(*(_QWORD *)(v18 + 8) + 48LL);
    else
      v20 = *(_DWORD *)(v18 + 8);
    if ( v20 < v17 )
    {
LABEL_29:
      v18 += 24LL;
      continue;
    }
    break;
  }
  if ( v20 != v17 )
    goto LABEL_31;
  if ( *(_BYTE *)v18 )
  {
    if ( *(_BYTE *)v18 > 2u )
      goto LABEL_31;
    goto LABEL_29;
  }
  v21 = (CAttrValue *)v18;
LABEL_32:
  v22 = v3;
  if ( v2 < 11 )
  {
    v23 = v3;
    v24 = v2;
    goto LABEL_34;
  }
LABEL_85:
  v48 = 0;
  v24 = v2;
  while ( 2 )
  {
    if ( v48 >= v24 )
    {
      v27 = 0;
LABEL_88:
      v28 = v3;
      goto LABEL_89;
    }
    v100 = CAttrValue::GetDISPID((CAttrValue *)(v22 + 24LL * ((v24 + v48) / 2)));
    if ( v100 > -2147413093 )
    {
LABEL_257:
      v24 = v101;
      goto LABEL_258;
    }
    if ( v100 < -2147413093 )
    {
      v48 = v101 + 1;
LABEL_258:
      if ( v24 - v48 < 10 )
      {
        v23 = v22 + 24LL * v48;
        goto LABEL_34;
      }
      continue;
    }
    break;
  }
  if ( !*(_BYTE *)v23 )
  {
    v27 = (CAttrValue *)v23;
    goto LABEL_88;
  }
  if ( *(_BYTE *)v23 > 2u )
    goto LABEL_257;
  v27 = (CAttrValue *)(v23 - 24);
  for ( m = v101 - 1; m >= v48 && (unsigned int)CAttrValue::GetDISPID(v27) == -2147413093; m = v117 - 1 )
  {
    if ( !*(_BYTE *)v27 )
      goto LABEL_88;
    if ( v117 == v48 )
      break;
    v27 = (CAttrValue *)((char *)v27 - 24);
  }
LABEL_34:
  v25 = v22 + 24LL * v24;
  while ( 2 )
  {
    if ( v23 >= v25 )
    {
LABEL_41:
      v27 = 0;
      goto LABEL_42;
    }
    if ( *(char *)(v23 + 3) >= 0 )
      v26 = *(_DWORD *)(*(_QWORD *)(v23 + 8) + 48LL);
    else
      v26 = *(_DWORD *)(v23 + 8);
    if ( v26 < -2147413093 )
    {
LABEL_39:
      v23 += 24LL;
      continue;
    }
    break;
  }
  if ( v26 != -2147413093 )
    goto LABEL_41;
  if ( *(_BYTE *)v23 )
  {
    if ( *(_BYTE *)v23 > 2u )
      goto LABEL_41;
    goto LABEL_39;
  }
  v27 = (CAttrValue *)v23;
LABEL_42:
  v28 = v3;
  if ( v2 < 11 )
  {
    v29 = v3;
    v30 = v2;
    goto LABEL_44;
  }
LABEL_89:
  v49 = 0;
  v30 = v2;
  while ( 2 )
  {
    if ( v49 >= v30 )
    {
      v33 = 0;
      goto LABEL_92;
    }
    v102 = CAttrValue::GetDISPID((CAttrValue *)(v28 + 24LL * ((v30 + v49) / 2)));
    if ( v102 > -2147413106 )
    {
LABEL_261:
      v30 = v103;
      goto LABEL_262;
    }
    if ( v102 < -2147413106 )
    {
      v49 = v103 + 1;
LABEL_262:
      if ( v30 - v49 < 10 )
      {
        v29 = v28 + 24LL * v49;
        goto LABEL_44;
      }
      continue;
    }
    break;
  }
  if ( !*(_BYTE *)v29 )
  {
    v33 = (CAttrValue *)v29;
    goto LABEL_92;
  }
  if ( *(_BYTE *)v29 > 2u )
    goto LABEL_261;
  v33 = (CAttrValue *)(v29 - 24);
  for ( n = v103 - 1; n >= v49 && (unsigned int)CAttrValue::GetDISPID(v33) == -2147413106; n = v119 - 1 )
  {
    if ( !*(_BYTE *)v33 )
      goto LABEL_92;
    if ( v119 == v49 )
      break;
    v33 = (CAttrValue *)((char *)v33 - 24);
  }
LABEL_44:
  v31 = v28 + 24LL * v30;
  while ( 2 )
  {
    if ( v29 >= v31 )
    {
LABEL_51:
      v33 = 0;
      goto LABEL_52;
    }
    if ( *(char *)(v29 + 3) >= 0 )
      v32 = *(_DWORD *)(*(_QWORD *)(v29 + 8) + 48LL);
    else
      v32 = *(_DWORD *)(v29 + 8);
    if ( v32 < -2147413106 )
    {
LABEL_49:
      v29 += 24LL;
      continue;
    }
    break;
  }
  if ( v32 != -2147413106 )
    goto LABEL_51;
  if ( *(_BYTE *)v29 )
  {
    if ( *(_BYTE *)v29 > 2u )
      goto LABEL_51;
    goto LABEL_49;
  }
  v33 = (CAttrValue *)v29;
LABEL_52:
  if ( v2 < 11 )
  {
    v34 = v3;
    LOBYTE(v35) = 2;
    v36 = -2147413094;
    goto LABEL_54;
  }
LABEL_92:
  v50 = 0;
  v35 = 2;
  while ( 2 )
  {
    if ( v50 < v2 )
    {
      v51 = CAttrValue::GetDISPID((CAttrValue *)(v3 + 24LL * ((v2 + v50) / v35)));
      if ( v51 > v36 )
        goto LABEL_95;
      if ( v51 < v36 )
      {
        v50 = v52 + 1;
      }
      else
      {
        if ( !*(_BYTE *)v34 )
          goto LABEL_61;
        if ( *(_BYTE *)v34 <= (unsigned __int8)v35 )
        {
          v106 = (CAttrValue *)(v34 - 24);
          for ( ii = v52 - 1; ii >= v50; ii = v109 - 1 )
          {
            v108 = CAttrValue::GetDISPID(v106);
            if ( v108 != v36 )
              break;
            if ( !*v38 )
              goto LABEL_61;
            if ( v109 == v50 )
              break;
            v106 = (CAttrValue *)(v38 - 24);
          }
LABEL_54:
          while ( v34 < v3 + 24LL * v2 )
          {
            if ( *(char *)(v34 + 3) >= 0 )
              v37 = *(_DWORD *)(*(_QWORD *)(v34 + 8) + 48LL);
            else
              v37 = *(_DWORD *)(v34 + 8);
            if ( v37 >= v36 )
            {
              if ( v37 != v36 )
                goto LABEL_60;
              if ( !*(_BYTE *)v34 )
              {
                v38 = (_BYTE *)v34;
                goto LABEL_61;
              }
              if ( *(_BYTE *)v34 > (unsigned __int8)v35 )
                goto LABEL_60;
            }
            v34 += 24LL;
          }
          break;
        }
LABEL_95:
        v2 = v52;
      }
      if ( v2 - v50 < 10 )
      {
        v34 = v3 + 24LL * v50;
        goto LABEL_54;
      }
      continue;
    }
    break;
  }
LABEL_60:
  v38 = 0;
LABEL_61:
  if ( v9 && (*((_BYTE *)v9 + 3) & 0x10) != 0 )
  {
    v40 = 1;
    v39 = 1;
  }
  else
  {
    v39 = 0;
    v40 = 1;
  }
  if ( !v15 || (v41 = 1, (*((_BYTE *)v15 + 3) & 0x10) == 0) )
    v41 = 0;
  if ( !v21 || (v42 = 1, (*((_BYTE *)v21 + 3) & 0x10) == 0) )
    v42 = 0;
  if ( !v27 || (v43 = 1, (*((_BYTE *)v27 + 3) & 0x10) == 0) )
    v43 = 0;
  if ( !v33 || (v44 = 1, (*((_BYTE *)v33 + 3) & 0x10) == 0) )
    v44 = 0;
  if ( !v38 || (v38[3] & 0x10) == 0 )
    v40 = 0;
  if ( v39 )
  {
    if ( v41 && v42 && v43 && v44 && v40 )
    {
      v45 = FormsAllocStringW(L"inherit", v132);
      goto LABEL_80;
    }
LABEL_364:
    *v132 = 0;
    return 0;
  }
  if ( v41 || v42 || v43 || v44 || v40 )
    goto LABEL_364;
  bstrString = 0;
  v57 = 0;
  v58 = PROPERTYDESC::HandleNumProperty(
          (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontWeight,
          0x20000004u,
          &bstrString,
          0,
          (struct CVoid *)&v131);
  if ( v58 < 0 )
    v58 = CBase::WriteErrorInfo(0, v58, -2147413085, INVOKE_PROPERTYGET);
  v59 = bstrString;
  if ( v58 || !bstrString || !*bstrString )
    goto LABEL_186;
  v60 = L"normal";
  v61 = bstrString;
  lpString2 = L"normal";
  while ( 2 )
  {
    v63 = *v61;
    v64 = *lpString2;
    if ( !*v61 )
    {
      v65 = -(v64 != 0);
      goto LABEL_141;
    }
    if ( v63 == v64 )
    {
LABEL_139:
      ++v61;
      ++lpString2;
      continue;
    }
    break;
  }
  if ( (unsigned __int16)(v63 - 65) <= 0x19u )
  {
    v63 += 32;
    if ( (unsigned __int16)(v64 - 65) <= 0x19u )
      goto LABEL_197;
  }
  else
  {
    if ( (unsigned __int16)(v64 - 65) > 0x19u )
      goto LABEL_200;
LABEL_197:
    v64 += 32;
  }
  if ( v63 == v64 )
    goto LABEL_139;
LABEL_200:
  if ( ((v63 | v64) & 0xFF80) == 0 )
    goto LABEL_201;
  v120 = CompareStringW(0x409u, 0x30001u, v61, -1, lpString2, -1);
  v59 = bstrString;
  if ( v120 <= 0 )
    goto LABEL_201;
  v65 = v120 - 2;
LABEL_141:
  if ( v65 )
  {
LABEL_201:
    v57 = CStr::Append((CStr *)&strIn, v59);
    if ( !v57 )
    {
      v57 = CStr::Append((CStr *)&strIn, L" ");
      if ( !v57 )
      {
        v59 = bstrString;
        goto LABEL_142;
      }
    }
    goto LABEL_234;
  }
LABEL_142:
  SysFreeString(v59);
  bstrString = 0;
  v66 = PROPERTYDESC::HandleNumProperty(
          (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontStyle,
          0x20000004u,
          &bstrString,
          0,
          (struct CVoid *)&v131);
  if ( v66 < 0 )
    v66 = CBase::WriteErrorInfo(0, v66, -2147413088, INVOKE_PROPERTYGET);
  v59 = bstrString;
  if ( v66 || !bstrString || !*bstrString )
    goto LABEL_186;
  v67 = bstrString;
  v68 = L"normal";
  while ( 2 )
  {
    v69 = *v67;
    v70 = *v68;
    if ( !*v67 )
    {
      v71 = -(v70 != 0);
      goto LABEL_152;
    }
    if ( v69 == v70 )
    {
LABEL_150:
      ++v67;
      ++v68;
      continue;
    }
    break;
  }
  if ( (unsigned __int16)(v69 - 65) <= 0x19u )
  {
    v69 += 32;
    if ( (unsigned __int16)(v70 - 65) <= 0x19u )
      goto LABEL_206;
  }
  else
  {
    if ( (unsigned __int16)(v70 - 65) > 0x19u )
      goto LABEL_209;
LABEL_206:
    v70 += 32;
  }
  if ( v69 == v70 )
    goto LABEL_150;
LABEL_209:
  if ( ((v69 | v70) & 0xFF80) == 0 )
    goto LABEL_210;
  v121 = CompareStringW(0x409u, 0x30001u, v67, -1, v68, -1);
  v59 = bstrString;
  if ( v121 <= 0 )
    goto LABEL_210;
  v71 = v121 - 2;
LABEL_152:
  if ( v71 )
  {
LABEL_210:
    v57 = CStr::Append((CStr *)&strIn, v59);
    if ( !v57 )
    {
      v57 = CStr::Append((CStr *)&strIn, L" ");
      if ( !v57 )
      {
        v59 = bstrString;
        goto LABEL_153;
      }
    }
    goto LABEL_234;
  }
LABEL_153:
  SysFreeString(v59);
  bstrString = 0;
  v72 = PROPERTYDESC::HandleNumProperty(
          (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontVariant,
          0x20000004u,
          &bstrString,
          0,
          (struct CVoid *)&v131);
  if ( v72 < 0 )
    v72 = CBase::WriteErrorInfo(0, v72, -2147413087, INVOKE_PROPERTYGET);
  v59 = bstrString;
  if ( v72 || !bstrString || !*bstrString )
    goto LABEL_186;
  v73 = bstrString;
  v74 = L"normal";
  while ( 2 )
  {
    v75 = *v73;
    v76 = *v74;
    if ( !*v73 )
    {
      v77 = -(v76 != 0);
      goto LABEL_163;
    }
    if ( v75 == v76 )
    {
LABEL_161:
      ++v73;
      ++v74;
      continue;
    }
    break;
  }
  if ( (unsigned __int16)(v75 - 65) <= 0x19u )
  {
    v75 += 32;
    if ( (unsigned __int16)(v76 - 65) <= 0x19u )
      goto LABEL_215;
  }
  else
  {
    if ( (unsigned __int16)(v76 - 65) > 0x19u )
      goto LABEL_218;
LABEL_215:
    v76 += 32;
  }
  if ( v75 == v76 )
    goto LABEL_161;
LABEL_218:
  if ( ((v75 | v76) & 0xFF80) == 0 )
    goto LABEL_219;
  v122 = CompareStringW(0x409u, 0x30001u, v73, -1, v74, -1);
  v59 = bstrString;
  if ( v122 <= 0 )
    goto LABEL_219;
  v77 = v122 - 2;
LABEL_163:
  if ( v77 )
  {
LABEL_219:
    v57 = CStr::Append((CStr *)&strIn, v59);
    if ( !v57 )
    {
      v57 = CStr::Append((CStr *)&strIn, L" ");
      if ( !v57 )
      {
        v59 = bstrString;
        goto LABEL_164;
      }
    }
    goto LABEL_234;
  }
LABEL_164:
  SysFreeString(v59);
  bstrString = 0;
  if ( (unsigned int)PROPERTYDESC::HandleTypedValueProperty(
                       (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontSize,
                       0x30000004u,
                       &pvarg,
                       0,
                       &v131)
    || pvarg.vt != 8
    || !pvarg.llVal
    || !*pvarg.bstrVal )
  {
    goto LABEL_185;
  }
  v57 = CStr::Append((CStr *)&strIn, pvarg.bstrVal);
  if ( v57 )
  {
LABEL_234:
    v59 = bstrString;
    v87 = 1;
    goto LABEL_187;
  }
  VariantClear(&pvarg);
  if ( (unsigned int)PROPERTYDESC::HandleTypedValueProperty(
                       (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationlineHeight,
                       0x30000004u,
                       &pvarg,
                       0,
                       &v131)
    || pvarg.vt != 8
    || (bstrVal = pvarg.bstrVal) == 0
    || !*pvarg.bstrVal )
  {
LABEL_185:
    v59 = bstrString;
    goto LABEL_186;
  }
  while ( 2 )
  {
    v79 = *bstrVal;
    v80 = *v60;
    if ( !*bstrVal )
    {
      v81 = -(v80 != 0);
      goto LABEL_177;
    }
    if ( v79 == v80 )
      goto LABEL_175;
    if ( (unsigned __int16)(v79 - 65) <= 0x19u )
    {
      v79 += 32;
      if ( (unsigned __int16)(v80 - 65) <= 0x19u )
        goto LABEL_266;
    }
    else
    {
      if ( (unsigned __int16)(v80 - 65) > 0x19u )
        break;
LABEL_266:
      v80 += 32;
    }
    if ( v79 == v80 )
    {
LABEL_175:
      ++bstrVal;
      ++v60;
      continue;
    }
    break;
  }
  if ( ((v79 | v80) & 0xFF80) == 0 )
    goto LABEL_270;
  v123 = CompareStringW(0x409u, 0x30001u, bstrVal, -1, v60, -1);
  if ( v123 <= 0 )
    goto LABEL_270;
  v81 = v123 - 2;
LABEL_177:
  if ( !v81 )
    goto LABEL_178;
LABEL_270:
  v57 = CStr::Append((CStr *)&strIn, L"/");
  if ( v57 )
    goto LABEL_234;
  v57 = CStr::Append((CStr *)&strIn, pvarg.bstrVal);
  if ( v57 )
    goto LABEL_234;
LABEL_178:
  v57 = CStr::Append((CStr *)&strIn, L" ");
  if ( v57 )
    goto LABEL_234;
  v59 = 0;
  bstrString = 0;
  v83 = 0;
  v129 = 0;
  v84 = 0;
  if ( !v131 )
  {
LABEL_223:
    v95 = v84 < 0;
    if ( !v84 )
      goto LABEL_224;
    goto LABEL_228;
  }
  Inl = CAttrArray::PrivateFindInl(v131, 2147554202LL, 0, v82);
  if ( !Inl )
    goto LABEL_224;
  v86 = *(_BYTE *)(Inl + 1);
  if ( (*(_BYTE *)(Inl + 2) & 0x20) != 0 )
  {
    v124 = ((v86 - 9) & 0xFB) == 0;
    v125 = 0;
    if ( v124 )
      v125 = *(_QWORD *)(Inl + 16);
    v94 = (*(__int64 (__fastcall **)(__int64, const OLECHAR **))(*(_QWORD *)v125 + 24LL))(v125, &v129);
    v59 = bstrString;
    v84 = v94;
    v83 = v129;
    goto LABEL_223;
  }
  if ( v86 == 31 )
    v83 = *(const OLECHAR **)(Inl + 16);
  v129 = v83;
LABEL_224:
  if ( v83 )
  {
    bstrString = SysAllocString(v83);
    v59 = bstrString;
    if ( !bstrString )
      v84 = -2147024882;
  }
  else
  {
    v59 = 0;
    bstrString = 0;
  }
  v95 = v84 < 0;
LABEL_228:
  if ( v95 )
  {
    v126 = CBase::WriteErrorInfo(0, v84, -2147413094, INVOKE_PROPERTYGET);
    v59 = bstrString;
    v84 = v126;
  }
  if ( !v84 && v59 && *v59 )
  {
    v57 = CStr::Append((CStr *)&strIn, v59);
    goto LABEL_234;
  }
LABEL_186:
  v87 = 0;
LABEL_187:
  SysFreeString(v59);
  VariantClear(&pvarg);
  if ( !v57 )
  {
    if ( v87 || (v45 = CStr::Set((const unsigned __int16 **)&strIn, &Source)) == 0 )
    {
      if ( strIn )
      {
        v89 = strIn - 2;
        v90 = SysAllocStringLen(strIn, *((_DWORD *)strIn - 1) >> 1);
        v91 = (MemoryProtection *)g_hProcessHeap;
        v92 = v90;
        *v132 = v90;
        MemoryProtection::HeapFree(v91, v89, v93);
        return v92 == 0 ? 0x8007000E : 0;
      }
      else
      {
        *v132 = 0;
        return 0;
      }
    }
LABEL_80:
    CStr::_Free((CStr *)&strIn);
    return v45;
  }
  if ( strIn )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, strIn - 2, v88);
  return v57;
}

```

## disassembly

```asm
0x1804344c4  mov     [rsp-38h+arg_10], rbx
0x1804344c9  mov     [rsp-38h+arg_8], rdx
0x1804344ce  mov     [rsp-38h+arg_0], rcx
0x1804344d3  push    rbp
0x1804344d4  push    rsi
0x1804344d5  push    rdi
0x1804344d6  push    r12
0x1804344d8  push    r13
0x1804344da  push    r14
0x1804344dc  push    r15
0x1804344de  mov     rbp, rsp
0x1804344e1  sub     rsp, 60h
0x1804344e5  xor     ecx, ecx
0x1804344e7  xor     eax, eax
0x1804344e9  xorps   xmm0, xmm0
0x1804344ec  mov     qword ptr [rbp+pvarg+10h], rax
0x1804344f0  mov     rax, [rbp+arg_8]
0x1804344f4  mov     [rbp+strIn], rcx
0x1804344f8  mov     [rbp+bstrString], rcx
0x1804344fc  movups  xmmword ptr [rbp+pvarg], xmm0
0x180434500  mov     [rax], rcx
0x180434503  cmp     [rbp+arg_0], rcx
0x180434507  jz      loc_180434D52
0x18043450d  lea     rcx, [rbp+pvarg]; pvarg
0x180434511  call    cs:__imp_VariantInit
0x180434518  nop     dword ptr [rax+rax+00h]
0x18043451d  mov     rax, [rbp+arg_0]
0x180434521  mov     edi, 1
0x180434526  mov     r14d, 800113A0h
0x18043452c  mov     esi, [rax+4]
0x18043452f  lea     r15d, [rdi+1]
0x180434533  mov     rbx, [rax+8]
0x180434537  lea     r11d, [r14+3]
0x18043453b  mov     r8d, esi
0x18043453e  cmp     esi, 0Bh
0x180434541  jge     loc_18043485C
0x180434547  mov     rdx, rbx
0x18043454a  movsxd  rax, r8d
0x18043454d  lea     rcx, [rax+rax*2]
0x180434551  lea     r8, [rbx+rcx*8]
0x180434555  cmp     rdx, r8
0x180434558  jnb     short loc_180434578
0x18043455a  cmp     byte ptr [rdx+3], 0
0x18043455e  jge     loc_180434814
0x180434564  mov     eax, [rdx+8]
0x180434567  cmp     eax, r11d
0x18043456a  jge     short loc_180434572
0x18043456c  add     rdx, 18h
0x180434570  jmp     short loc_180434555
0x180434572  jz      loc_180434F75
0x180434578  xor     r13d, r13d
0x18043457b  mov     r10, rbx
0x18043457e  cmp     esi, 0Bh
0x180434581  jge     loc_18043486E
0x180434587  mov     rdx, rbx
0x18043458a  mov     r8d, esi
0x18043458d  movsxd  rax, r8d
0x180434590  lea     rcx, [rax+rax*2]
0x180434594  lea     r8, [r10+rcx*8]
0x180434598  cmp     rdx, r8
0x18043459b  jnb     short loc_1804345BB
0x18043459d  cmp     byte ptr [rdx+3], 0
0x1804345a1  jge     loc_180434820
0x1804345a7  mov     eax, [rdx+8]
0x1804345aa  cmp     eax, r14d
0x1804345ad  jge     short loc_1804345B5
0x1804345af  add     rdx, 18h
0x1804345b3  jmp     short loc_180434598
0x1804345b5  jz      loc_180434F63
0x1804345bb  xor     r12d, r12d
0x1804345be  mov     r14d, 8001139Bh
0x1804345c4  mov     r8d, esi
0x1804345c7  lea     r11d, [r14+6]
0x1804345cb  cmp     esi, 0Bh
0x1804345ce  jge     loc_180434780
0x1804345d4  mov     rdx, rbx
0x1804345d7  movsxd  rax, r8d
0x1804345da  lea     rcx, [rax+rax*2]
0x1804345de  lea     r8, [rbx+rcx*8]
0x1804345e2  cmp     rdx, r8
0x1804345e5  jnb     short loc_180434605
0x1804345e7  cmp     byte ptr [rdx+3], 0
0x1804345eb  jge     loc_18043482C
0x1804345f1  mov     eax, [rdx+8]
0x1804345f4  cmp     eax, r11d
0x1804345f7  jge     short loc_1804345FF
0x1804345f9  add     rdx, 18h
0x1804345fd  jmp     short loc_1804345E2
0x1804345ff  jz      loc_180434F87
0x180434605  xor     r15d, r15d
0x180434608  mov     r10, rbx
0x18043460b  cmp     esi, 0Bh
0x18043460e  jge     loc_180434792
0x180434614  mov     rdx, rbx
0x180434617  mov     r8d, esi
0x18043461a  movsxd  rax, r8d
0x18043461d  lea     rcx, [rax+rax*2]
0x180434621  lea     r8, [r10+rcx*8]
0x180434625  cmp     rdx, r8
0x180434628  jnb     short loc_180434648
0x18043462a  cmp     byte ptr [rdx+3], 0
0x18043462e  jge     loc_180434838
0x180434634  mov     eax, [rdx+8]
0x180434637  cmp     eax, r14d
0x18043463a  jge     short loc_180434642
0x18043463c  add     rdx, 18h
0x180434640  jmp     short loc_180434625
0x180434642  jz      loc_180434F99
0x180434648  xor     r14d, r14d
0x18043464b  mov     r10, rbx
0x18043464e  cmp     esi, 0Bh
0x180434651  jge     loc_1804347A7
0x180434657  mov     rdx, rbx
0x18043465a  mov     r8d, esi
0x18043465d  mov     edi, 8001138Eh
0x180434662  movsxd  rax, r8d
0x180434665  lea     rcx, [rax+rax*2]
0x180434669  lea     r8, [r10+rcx*8]
0x18043466d  cmp     rdx, r8
0x180434670  jnb     short loc_18043468F
0x180434672  cmp     byte ptr [rdx+3], 0
0x180434676  jge     loc_180434844
0x18043467c  mov     eax, [rdx+8]
0x18043467f  cmp     eax, edi
0x180434681  jge     short loc_180434689
0x180434683  add     rdx, 18h
0x180434687  jmp     short loc_18043466D
0x180434689  jz      loc_180434FAB
0x18043468f  xor     edi, edi
0x180434691  cmp     esi, 0Bh
0x180434694  jge     loc_1804347BD
0x18043469a  mov     rdx, rbx
0x18043469d  mov     r10d, 2
0x1804346a3  mov     r11d, 8001139Ah
0x1804346a9  movsxd  rax, esi
0x1804346ac  lea     rcx, [rax+rax*2]
0x1804346b0  lea     r8, [rbx+rcx*8]
0x1804346b4  cmp     rdx, r8
0x1804346b7  jnb     short loc_1804346D7
0x1804346b9  cmp     byte ptr [rdx+3], 0
0x1804346bd  jge     loc_180434850
0x1804346c3  mov     eax, [rdx+8]
0x1804346c6  cmp     eax, r11d
0x1804346c9  jge     short loc_1804346D1
0x1804346cb  add     rdx, 18h
0x1804346cf  jmp     short loc_1804346B4
0x1804346d1  jz      loc_180434FBD
0x1804346d7  xor     ecx, ecx
0x1804346d9  mov     bl, 10h
0x1804346db  test    r13, r13
0x1804346de  jnz     loc_1804348BF
0x1804346e4  xor     r13d, r13d
0x1804346e7  mov     r11b, r13b
0x1804346ea  lea     eax, [r13+1]
0x1804346ee  test    r12, r12
0x1804346f1  jnz     loc_1804348D9
0x1804346f7  mov     r10b, r13b
0x1804346fa  test    r15, r15
0x1804346fd  jnz     loc_1804348EC
0x180434703  mov     r9b, r13b
0x180434706  test    r14, r14
0x180434709  jnz     loc_1804348FE
0x18043470f  mov     r8b, r13b
0x180434712  test    rdi, rdi
0x180434715  jnz     loc_180434910
0x18043471b  mov     dl, r13b
0x18043471e  test    rcx, rcx
0x180434721  jnz     loc_180434920
0x180434727  mov     al, r13b
0x18043472a  test    r11b, r11b
0x18043472d  jz      loc_18043492E
0x180434733  test    r10b, r10b
0x180434736  jz      loc_1804355D4
0x18043473c  test    r9b, r9b
0x18043473f  jz      loc_1804355D4
0x180434745  test    r8b, r8b
0x180434748  jz      loc_1804355D4
0x18043474e  test    dl, dl
0x180434750  jz      loc_1804355D4
0x180434756  test    al, al
0x180434758  jz      loc_1804355D4
0x18043475e  mov     rdx, [rbp+arg_8]; unsigned __int16 **
0x180434762  lea     rcx, aInherit; "inherit"
0x180434769  call    ?FormsAllocStringW@@YAJPEBGPEAPEAG@Z; FormsAllocStringW(ushort const *,ushort * *)
0x18043476e  mov     ebx, eax
0x180434770  lea     rcx, [rbp+strIn]; this
0x180434774  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x180434779  mov     eax, ebx
0x18043477b  jmp     loc_180434CE5
0x180434780  xor     r9d, r9d
0x180434783  cmp     r9d, r8d
0x180434786  jl      loc_180435021
0x18043478c  xor     r15d, r15d
0x18043478f  mov     r10, rbx
0x180434792  xor     r9d, r9d
0x180434795  mov     r8d, esi
0x180434798  cmp     r9d, r8d
0x18043479b  jl      loc_180435067
0x1804347a1  xor     r14d, r14d
0x1804347a4  mov     r10, rbx
0x1804347a7  xor     r9d, r9d
0x1804347aa  mov     r8d, esi
0x1804347ad  mov     edi, 8001138Eh
0x1804347b2  cmp     r9d, r8d
0x1804347b5  jl      loc_1804350B1
0x1804347bb  xor     edi, edi
0x1804347bd  xor     r8d, r8d
0x1804347c0  mov     r11d, 8001139Ah
0x1804347c6  lea     r10d, [r8+2]
0x1804347ca  cmp     r8d, esi
0x1804347cd  jge     loc_1804346D7
0x1804347d3  lea     eax, [rsi+r8]
0x1804347d7  cdq
0x1804347d8  idiv    r10d
0x1804347db  movsxd  r9, eax
0x1804347de  lea     rdx, [r9+r9*2]
0x1804347e2  lea     rdx, [rbx+rdx*8]
0x1804347e6  mov     rcx, rdx; this
0x1804347e9  call    ?GetDISPID@CAttrValue@@QEBAJXZ; CAttrValue::GetDISPID(void)
0x1804347ee  cmp     eax, r11d
0x1804347f1  jle     loc_180435235
0x1804347f7  mov     esi, r9d
0x1804347fa  mov     eax, esi
0x1804347fc  sub     eax, r8d
0x1804347ff  cmp     eax, 0Ah
0x180434802  jge     short loc_1804347CA
0x180434804  movsxd  rax, r8d
0x180434807  lea     rcx, [rax+rax*2]
0x18043480b  lea     rdx, [rbx+rcx*8]
0x18043480f  jmp     loc_1804346A9
0x180434814  mov     rax, [rdx+8]
0x180434818  mov     eax, [rax+30h]
0x18043481b  jmp     loc_180434567
0x180434820  mov     rax, [rdx+8]
0x180434824  mov     eax, [rax+30h]
0x180434827  jmp     loc_1804345AA
0x18043482c  mov     rax, [rdx+8]
0x180434830  mov     eax, [rax+30h]
0x180434833  jmp     loc_1804345F4
0x180434838  mov     rax, [rdx+8]
0x18043483c  mov     eax, [rax+30h]
0x18043483f  jmp     loc_180434637
0x180434844  mov     rax, [rdx+8]
0x180434848  mov     eax, [rax+30h]
0x18043484b  jmp     loc_18043467F
0x180434850  mov     rax, [rdx+8]
0x180434854  mov     eax, [rax+30h]
0x180434857  jmp     loc_1804346C6
0x18043485c  xor     r9d, r9d
0x18043485f  cmp     r9d, r8d
0x180434862  jl      loc_180434FDB
0x180434868  xor     r13d, r13d
0x18043486b  mov     r10, rbx
0x18043486e  xor     r9d, r9d
0x180434871  mov     r8d, esi
0x180434874  cmp     r9d, r8d
0x180434877  jge     loc_1804345BB
0x18043487d  lea     eax, [r8+r9]
0x180434881  cdq
0x180434882  idiv    r15d
0x180434885  movsxd  r11, eax
0x180434888  lea     rdx, [r11+r11*2]
0x18043488c  lea     rdx, [r10+rdx*8]
0x180434890  mov     rcx, rdx; this
0x180434893  call    ?GetDISPID@CAttrValue@@QEBAJXZ; CAttrValue::GetDISPID(void)
0x180434898  cmp     eax, r14d
0x18043489b  jle     loc_180435196
0x1804348a1  mov     r8d, r11d
0x1804348a4  mov     eax, r8d
0x1804348a7  sub     eax, r9d
0x1804348aa  cmp     eax, 0Ah
0x1804348ad  jge     short loc_180434874
0x1804348af  movsxd  rax, r9d
0x1804348b2  lea     rcx, [rax+rax*2]
0x1804348b6  lea     rdx, [r10+rcx*8]
0x1804348ba  jmp     loc_18043458D
0x1804348bf  test    [r13+3], bl
0x1804348c3  jz      loc_1804346E4
0x1804348c9  mov     eax, 1
0x1804348ce  xor     r13d, r13d
0x1804348d1  mov     r11b, al
0x1804348d4  jmp     loc_1804346EE
0x1804348d9  mov     r10b, al
0x1804348dc  test    [r12+3], bl
0x1804348e1  jnz     loc_1804346FA
0x1804348e7  jmp     loc_1804346F7
0x1804348ec  mov     r9b, al
0x1804348ef  test    [r15+3], bl
0x1804348f3  jnz     loc_180434706
0x1804348f9  jmp     loc_180434703
0x1804348fe  mov     r8b, al
0x180434901  test    [r14+3], bl
0x180434905  jnz     loc_180434712
0x18043490b  jmp     loc_18043470F
0x180434910  mov     dl, al
0x180434912  test    [rdi+3], bl
0x180434915  jnz     loc_18043471E
0x18043491b  jmp     loc_18043471B
0x180434920  test    [rcx+3], bl
0x180434923  jnz     loc_18043472A
  ... truncated ...
```
