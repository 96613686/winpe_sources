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
  __int64 v45; // rdx
  unsigned int v46; // ebx
  void *v47; // r8
  int v49; // r9d
  int v50; // r9d
  int v51; // r9d
  int v52; // r8d
  int v53; // eax
  int v54; // r9d
  int v55; // r9d
  int v56; // r9d
  int DISPID; // eax
  int v58; // r11d
  unsigned int v59; // edi
  int v60; // eax
  unsigned __int16 *v61; // rdx
  const wchar_t *v62; // rbx
  const WCHAR *v63; // r10
  const wchar_t *lpString2; // r9
  WCHAR v65; // r8
  WCHAR v66; // cx
  int v67; // eax
  int v68; // eax
  const WCHAR *v69; // r10
  const wchar_t *v70; // r9
  WCHAR v71; // r8
  WCHAR v72; // cx
  int v73; // eax
  int v74; // eax
  const WCHAR *v75; // r10
  const wchar_t *v76; // r9
  WCHAR v77; // r8
  WCHAR v78; // cx
  int v79; // eax
  const WCHAR *bstrVal; // r10
  WCHAR v81; // r8
  WCHAR v82; // cx
  int v83; // eax
  IRecordInfo *pRecInfo; // rsi
  int v85; // ebx
  __int64 Inl; // rax
  char v87; // cl
  int v88; // ebx
  void *v89; // r8
  void *v90; // rdi
  unsigned __int16 *v91; // rax
  MemoryProtection *v92; // rcx
  unsigned __int16 *v93; // rbx
  void *v94; // r8
  int v95; // eax
  bool v96; // sf
  int v97; // eax
  int v98; // r10d
  int v99; // eax
  int v100; // r10d
  int v101; // eax
  int v102; // r11d
  int v103; // eax
  int v104; // r11d
  int i; // r11d
  int v106; // r11d
  CAttrValue *v107; // rcx
  int ii; // r9d
  int v109; // eax
  int v110; // r9d
  int j; // r10d
  int v112; // eax
  int v113; // r10d
  int k; // r10d
  int v115; // eax
  int v116; // r10d
  int m; // r11d
  int v118; // r11d
  int n; // r11d
  int v120; // r11d
  int v121; // eax
  int v122; // eax
  int v123; // eax
  int v124; // eax
  bool v125; // zf
  __int64 v126; // rcx
  int v127; // eax
  VARIANTARG bstrString; // [rsp+30h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-18h] BYREF
  struct CAttrArray *v130; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 **v131; // [rsp+A8h] [rbp+48h]

  v131 = a2;
  v130 = a1;
  *(_OWORD *)&bstrString.vt = 0u;
  memset(&pvarg, 0, sizeof(pvarg));
  *a2 = 0;
  if ( !v130 )
    return 1;
  VariantInit(&pvarg);
  v2 = *((_DWORD *)v130 + 1);
  v3 = *((_QWORD *)v130 + 1);
  v4 = -2147413085;
  v5 = v2;
  if ( v2 < 11 )
  {
    v6 = *((_QWORD *)v130 + 1);
    goto LABEL_4;
  }
  v55 = 0;
  while ( 1 )
  {
    if ( v55 >= v5 )
    {
      v9 = 0;
LABEL_107:
      v10 = v3;
LABEL_108:
      v56 = 0;
      v12 = v2;
      while ( 1 )
      {
        if ( v56 >= v12 )
          goto LABEL_21;
        DISPID = CAttrValue::GetDISPID((CAttrValue *)(v10 + 24LL * ((v12 + v56) / 2)));
        if ( DISPID <= -2147413088 )
        {
          if ( DISPID < -2147413088 )
          {
            v56 = v58 + 1;
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
            for ( i = v58 - 1; i >= v56 && (unsigned int)CAttrValue::GetDISPID(v15) == -2147413088; i = v106 - 1 )
            {
              if ( !*(_BYTE *)v15 )
                goto LABEL_22;
              if ( v106 == v56 )
                break;
              v15 = (CAttrValue *)((char *)v15 - 24);
            }
            goto LABEL_14;
          }
        }
        v12 = v58;
LABEL_112:
        if ( v12 - v56 < 10 )
        {
          v11 = v10 + 24LL * v56;
          goto LABEL_14;
        }
      }
    }
    v97 = CAttrValue::GetDISPID((CAttrValue *)(v3 + 24LL * ((v5 + v55) / 2)));
    if ( v97 <= v4 )
    {
      if ( v97 < v4 )
      {
        v55 = v98 + 1;
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
    v5 = v98;
LABEL_250:
    if ( v5 - v55 < 10 )
    {
      v6 = v3 + 24LL * v55;
      goto LABEL_4;
    }
  }
  v9 = (CAttrValue *)(v6 - 24);
  for ( j = v98 - 1; j >= v55; j = v113 - 1 )
  {
    v112 = CAttrValue::GetDISPID(v9);
    if ( v112 != v4 )
      break;
    if ( !*(_BYTE *)v9 )
      goto LABEL_107;
    if ( v113 == v55 )
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
  v49 = 0;
  while ( 2 )
  {
    if ( v49 >= v16 )
    {
      v21 = 0;
LABEL_84:
      v22 = v3;
      goto LABEL_85;
    }
    v99 = CAttrValue::GetDISPID((CAttrValue *)(v3 + 24LL * ((v16 + v49) / 2)));
    if ( v99 > v17 )
    {
LABEL_253:
      v16 = v100;
      goto LABEL_254;
    }
    if ( v99 < v17 )
    {
      v49 = v100 + 1;
LABEL_254:
      if ( v16 - v49 < 10 )
      {
        v18 = v3 + 24LL * v49;
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
  for ( k = v100 - 1; k >= v49; k = v116 - 1 )
  {
    v115 = CAttrValue::GetDISPID(v21);
    if ( v115 != v17 )
      break;
    if ( !*(_BYTE *)v21 )
      goto LABEL_84;
    if ( v116 == v49 )
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
  v50 = 0;
  v24 = v2;
  while ( 2 )
  {
    if ( v50 >= v24 )
    {
      v27 = 0;
LABEL_88:
      v28 = v3;
      goto LABEL_89;
    }
    v101 = CAttrValue::GetDISPID((CAttrValue *)(v22 + 24LL * ((v24 + v50) / 2)));
    if ( v101 > -2147413093 )
    {
LABEL_257:
      v24 = v102;
      goto LABEL_258;
    }
    if ( v101 < -2147413093 )
    {
      v50 = v102 + 1;
LABEL_258:
      if ( v24 - v50 < 10 )
      {
        v23 = v22 + 24LL * v50;
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
  for ( m = v102 - 1; m >= v50 && (unsigned int)CAttrValue::GetDISPID(v27) == -2147413093; m = v118 - 1 )
  {
    if ( !*(_BYTE *)v27 )
      goto LABEL_88;
    if ( v118 == v50 )
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
  v51 = 0;
  v30 = v2;
  while ( 2 )
  {
    if ( v51 >= v30 )
    {
      v33 = 0;
      goto LABEL_92;
    }
    v103 = CAttrValue::GetDISPID((CAttrValue *)(v28 + 24LL * ((v30 + v51) / 2)));
    if ( v103 > -2147413106 )
    {
LABEL_261:
      v30 = v104;
      goto LABEL_262;
    }
    if ( v103 < -2147413106 )
    {
      v51 = v104 + 1;
LABEL_262:
      if ( v30 - v51 < 10 )
      {
        v29 = v28 + 24LL * v51;
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
  for ( n = v104 - 1; n >= v51 && (unsigned int)CAttrValue::GetDISPID(v33) == -2147413106; n = v120 - 1 )
  {
    if ( !*(_BYTE *)v33 )
      goto LABEL_92;
    if ( v120 == v51 )
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
  v52 = 0;
  v35 = 2;
  while ( 2 )
  {
    if ( v52 < v2 )
    {
      v53 = CAttrValue::GetDISPID((CAttrValue *)(v3 + 24LL * ((v2 + v52) / v35)));
      if ( v53 > v36 )
        goto LABEL_95;
      if ( v53 < v36 )
      {
        v52 = v54 + 1;
      }
      else
      {
        if ( !*(_BYTE *)v34 )
          goto LABEL_61;
        if ( *(_BYTE *)v34 <= (unsigned __int8)v35 )
        {
          v107 = (CAttrValue *)(v34 - 24);
          for ( ii = v54 - 1; ii >= v52; ii = v110 - 1 )
          {
            v109 = CAttrValue::GetDISPID(v107);
            if ( v109 != v36 )
              break;
            if ( !*v38 )
              goto LABEL_61;
            if ( v110 == v52 )
              break;
            v107 = (CAttrValue *)(v38 - 24);
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
        v2 = v54;
      }
      if ( v2 - v52 < 10 )
      {
        v34 = v3 + 24LL * v52;
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
      v46 = FormsAllocStringW(L"inherit", v131);
      goto LABEL_80;
    }
LABEL_364:
    *v131 = 0;
    return 0;
  }
  if ( v41 || v42 || v43 || v44 || v40 )
    goto LABEL_364;
  *(_QWORD *)&bstrString.vt = 0;
  v59 = 0;
  LOBYTE(v60) = PROPERTYDESC::HandleNumProperty(
                  (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontWeight,
                  0x20000004u,
                  &bstrString,
                  0,
                  (struct CVoid *)&v130);
  if ( v60 < 0 )
    v60 = CBase::WriteErrorInfo(0, v60, -2147413085, INVOKE_PROPERTYGET);
  v61 = *(unsigned __int16 **)&bstrString.vt;
  if ( v60 || !*(_QWORD *)&bstrString.vt || !**(_WORD **)&bstrString.vt )
    goto LABEL_186;
  v62 = L"normal";
  v63 = *(const WCHAR **)&bstrString.vt;
  lpString2 = L"normal";
  while ( 2 )
  {
    v65 = *v63;
    v66 = *lpString2;
    if ( !*v63 )
    {
      v67 = -(v66 != 0);
      goto LABEL_141;
    }
    if ( v65 == v66 )
    {
LABEL_139:
      ++v63;
      ++lpString2;
      continue;
    }
    break;
  }
  if ( (unsigned __int16)(v65 - 65) <= 0x19u )
  {
    v65 += 32;
    if ( (unsigned __int16)(v66 - 65) <= 0x19u )
      goto LABEL_197;
  }
  else
  {
    if ( (unsigned __int16)(v66 - 65) > 0x19u )
      goto LABEL_200;
LABEL_197:
    v66 += 32;
  }
  if ( v65 == v66 )
    goto LABEL_139;
LABEL_200:
  if ( ((v65 | v66) & 0xFF80) == 0 )
    goto LABEL_201;
  v121 = CompareStringW(0x409u, 0x30001u, v63, -1, lpString2, -1);
  v61 = *(unsigned __int16 **)&bstrString.vt;
  if ( v121 <= 0 )
    goto LABEL_201;
  v67 = v121 - 2;
LABEL_141:
  if ( v67 )
  {
LABEL_201:
    v59 = CStr::Append((CStr *)&bstrString.decVal.8, v61);
    if ( !v59 )
    {
      v59 = CStr::Append((CStr *)&bstrString.decVal.8, L" ");
      if ( !v59 )
      {
        v61 = *(unsigned __int16 **)&bstrString.vt;
        goto LABEL_142;
      }
    }
    goto LABEL_234;
  }
LABEL_142:
  SysFreeString(v61);
  *(_QWORD *)&bstrString.vt = 0;
  LOBYTE(v68) = PROPERTYDESC::HandleNumProperty(
                  (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontStyle,
                  0x20000004u,
                  &bstrString,
                  0,
                  (struct CVoid *)&v130);
  if ( v68 < 0 )
    v68 = CBase::WriteErrorInfo(0, v68, -2147413088, INVOKE_PROPERTYGET);
  v61 = *(unsigned __int16 **)&bstrString.vt;
  if ( v68 || !*(_QWORD *)&bstrString.vt || !**(_WORD **)&bstrString.vt )
    goto LABEL_186;
  v69 = *(const WCHAR **)&bstrString.vt;
  v70 = L"normal";
  while ( 2 )
  {
    v71 = *v69;
    v72 = *v70;
    if ( !*v69 )
    {
      v73 = -(v72 != 0);
      goto LABEL_152;
    }
    if ( v71 == v72 )
    {
LABEL_150:
      ++v69;
      ++v70;
      continue;
    }
    break;
  }
  if ( (unsigned __int16)(v71 - 65) <= 0x19u )
  {
    v71 += 32;
    if ( (unsigned __int16)(v72 - 65) <= 0x19u )
      goto LABEL_206;
  }
  else
  {
    if ( (unsigned __int16)(v72 - 65) > 0x19u )
      goto LABEL_209;
LABEL_206:
    v72 += 32;
  }
  if ( v71 == v72 )
    goto LABEL_150;
LABEL_209:
  if ( ((v71 | v72) & 0xFF80) == 0 )
    goto LABEL_210;
  v122 = CompareStringW(0x409u, 0x30001u, v69, -1, v70, -1);
  v61 = *(unsigned __int16 **)&bstrString.vt;
  if ( v122 <= 0 )
    goto LABEL_210;
  v73 = v122 - 2;
LABEL_152:
  if ( v73 )
  {
LABEL_210:
    v59 = CStr::Append((CStr *)&bstrString.decVal.8, v61);
    if ( !v59 )
    {
      v59 = CStr::Append((CStr *)&bstrString.decVal.8, L" ");
      if ( !v59 )
      {
        v61 = *(unsigned __int16 **)&bstrString.vt;
        goto LABEL_153;
      }
    }
    goto LABEL_234;
  }
LABEL_153:
  SysFreeString(v61);
  *(_QWORD *)&bstrString.vt = 0;
  LOBYTE(v74) = PROPERTYDESC::HandleNumProperty(
                  (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontVariant,
                  0x20000004u,
                  &bstrString,
                  0,
                  (struct CVoid *)&v130);
  if ( v74 < 0 )
    v74 = CBase::WriteErrorInfo(0, v74, -2147413087, INVOKE_PROPERTYGET);
  v61 = *(unsigned __int16 **)&bstrString.vt;
  if ( v74 || !*(_QWORD *)&bstrString.vt || !**(_WORD **)&bstrString.vt )
    goto LABEL_186;
  v75 = *(const WCHAR **)&bstrString.vt;
  v76 = L"normal";
  while ( 2 )
  {
    v77 = *v75;
    v78 = *v76;
    if ( !*v75 )
    {
      v79 = -(v78 != 0);
      goto LABEL_163;
    }
    if ( v77 == v78 )
    {
LABEL_161:
      ++v75;
      ++v76;
      continue;
    }
    break;
  }
  if ( (unsigned __int16)(v77 - 65) <= 0x19u )
  {
    v77 += 32;
    if ( (unsigned __int16)(v78 - 65) <= 0x19u )
      goto LABEL_215;
  }
  else
  {
    if ( (unsigned __int16)(v78 - 65) > 0x19u )
      goto LABEL_218;
LABEL_215:
    v78 += 32;
  }
  if ( v77 == v78 )
    goto LABEL_161;
LABEL_218:
  if ( ((v77 | v78) & 0xFF80) == 0 )
    goto LABEL_219;
  v123 = CompareStringW(0x409u, 0x30001u, v75, -1, v76, -1);
  v61 = *(unsigned __int16 **)&bstrString.vt;
  if ( v123 <= 0 )
    goto LABEL_219;
  v79 = v123 - 2;
LABEL_163:
  if ( v79 )
  {
LABEL_219:
    v59 = CStr::Append((CStr *)&bstrString.decVal.8, v61);
    if ( !v59 )
    {
      v59 = CStr::Append((CStr *)&bstrString.decVal.8, L" ");
      if ( !v59 )
      {
        v61 = *(unsigned __int16 **)&bstrString.vt;
        goto LABEL_164;
      }
    }
    goto LABEL_234;
  }
LABEL_164:
  SysFreeString(v61);
  *(_QWORD *)&bstrString.vt = 0;
  if ( (unsigned int)PROPERTYDESC::HandleTypedValueProperty(
                       (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontSize,
                       0x30000004u,
                       &pvarg,
                       0,
                       (struct CVoid *)&v130)
    || pvarg.vt != 8
    || !pvarg.llVal
    || !*pvarg.bstrVal )
  {
    goto LABEL_185;
  }
  v59 = CStr::Append((CStr *)&bstrString.decVal.8, pvarg.bstrVal);
  if ( v59 )
  {
LABEL_234:
    v61 = *(unsigned __int16 **)&bstrString.vt;
    v88 = 1;
    goto LABEL_187;
  }
  VariantClear(&pvarg);
  if ( (unsigned int)PROPERTYDESC::HandleTypedValueProperty(
                       (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationlineHeight,
                       0x30000004u,
                       &pvarg,
                       0,
                       (struct CVoid *)&v130)
    || pvarg.vt != 8
    || (bstrVal = pvarg.bstrVal) == 0
    || !*pvarg.bstrVal )
  {
LABEL_185:
    v61 = *(unsigned __int16 **)&bstrString.vt;
    goto LABEL_186;
  }
  while ( 2 )
  {
    v81 = *bstrVal;
    v82 = *v62;
    if ( !*bstrVal )
    {
      v83 = -(v82 != 0);
      goto LABEL_177;
    }
    if ( v81 == v82 )
      goto LABEL_175;
    if ( (unsigned __int16)(v81 - 65) <= 0x19u )
    {
      v81 += 32;
      if ( (unsigned __int16)(v82 - 65) <= 0x19u )
        goto LABEL_266;
    }
    else
    {
      if ( (unsigned __int16)(v82 - 65) > 0x19u )
        break;
LABEL_266:
      v82 += 32;
    }
    if ( v81 == v82 )
    {
LABEL_175:
      ++bstrVal;
      ++v62;
      continue;
    }
    break;
  }
  if ( ((v81 | v82) & 0xFF80) == 0 )
    goto LABEL_270;
  v124 = CompareStringW(0x409u, 0x30001u, bstrVal, -1, v62, -1);
  if ( v124 <= 0 )
    goto LABEL_270;
  v83 = v124 - 2;
LABEL_177:
  if ( !v83 )
    goto LABEL_178;
LABEL_270:
  v59 = CStr::Append((CStr *)&bstrString.decVal.8, L"/");
  if ( v59 )
    goto LABEL_234;
  v59 = CStr::Append((CStr *)&bstrString.decVal.8, pvarg.bstrVal);
  if ( v59 )
    goto LABEL_234;
LABEL_178:
  v59 = CStr::Append((CStr *)&bstrString.decVal.8, L" ");
  if ( v59 )
    goto LABEL_234;
  v61 = 0;
  *(_QWORD *)&bstrString.vt = 0;
  pRecInfo = 0;
  bstrString.pRecInfo = 0;
  v85 = 0;
  if ( !v130 )
  {
LABEL_223:
    v96 = v85 < 0;
    if ( !v85 )
      goto LABEL_224;
    goto LABEL_228;
  }
  Inl = CAttrArray::PrivateFindInl((__int64)v130, -2147413094, 0);
  if ( !Inl )
    goto LABEL_224;
  v87 = *(_BYTE *)(Inl + 1);
  if ( (*(_BYTE *)(Inl + 2) & 0x20) != 0 )
  {
    v125 = ((v87 - 9) & 0xFB) == 0;
    v126 = 0;
    if ( v125 )
      v126 = *(_QWORD *)(Inl + 16);
    v95 = (*(__int64 (__fastcall **)(__int64, DECIMAL *))(*(_QWORD *)v126 + 24LL))(v126, &bstrString.decVal + 1);
    v61 = *(unsigned __int16 **)&bstrString.vt;
    v85 = v95;
    pRecInfo = bstrString.pRecInfo;
    goto LABEL_223;
  }
  if ( v87 == 31 )
    pRecInfo = *(IRecordInfo **)(Inl + 16);
  bstrString.pRecInfo = pRecInfo;
LABEL_224:
  if ( pRecInfo )
  {
    *(_QWORD *)&bstrString.vt = SysAllocString((const OLECHAR *)pRecInfo);
    v61 = *(unsigned __int16 **)&bstrString.vt;
    if ( !*(_QWORD *)&bstrString.vt )
      v85 = -2147024882;
  }
  else
  {
    v61 = 0;
    *(_QWORD *)&bstrString.vt = 0;
  }
  v96 = v85 < 0;
LABEL_228:
  if ( v96 )
  {
    v127 = CBase::WriteErrorInfo(0, v85, -2147413094, INVOKE_PROPERTYGET);
    v61 = *(unsigned __int16 **)&bstrString.vt;
    v85 = v127;
  }
  if ( !v85 && v61 && *v61 )
  {
    v59 = CStr::Append((CStr *)&bstrString.decVal.8, v61);
    goto LABEL_234;
  }
LABEL_186:
  v88 = 0;
LABEL_187:
  SysFreeString(v61);
  VariantClear(&pvarg);
  if ( !v59 )
  {
    if ( v88 || (v46 = CStr::Set((const unsigned __int16 **)&bstrString.bstrVal, &Source)) == 0 )
    {
      if ( bstrString.llVal )
      {
        v90 = (void *)(bstrString.llVal - 4);
        v91 = SysAllocStringLen(bstrString.bstrVal, *(_DWORD *)(bstrString.llVal - 4) >> 1);
        v92 = (MemoryProtection *)g_hProcessHeap;
        v93 = v91;
        *v131 = v91;
        MemoryProtection::HeapFree(v92, v90, v94);
        return v93 == 0 ? 0x8007000E : 0;
      }
      else
      {
        *v131 = 0;
        return 0;
      }
    }
LABEL_80:
    CStr::_Free((CStr *)&bstrString.decVal.8, v45, v47);
    return v46;
  }
  if ( bstrString.llVal )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)(bstrString.llVal - 4), v89);
  return v59;
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
