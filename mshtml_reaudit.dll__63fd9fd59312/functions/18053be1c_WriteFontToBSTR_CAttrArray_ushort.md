# WriteFontToBSTR(CAttrArray *,ushort * *)

- ea: `0x18053be1c`
- end: `0x18053d005`
- name: `?WriteFontToBSTR@@YAJPEAVCAttrArray@@PEAPEAG@Z`
- size: `4585`
- prototype: `__int64 __fastcall(struct CAttrArray *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180284db0`
- `0x18053d00c`

## callees

- `0x18003b1f0`
- `0x18003bc8c`
- `0x18003dcd8`
- `0x180111b30`
- `0x1801bf344`
- `0x1801c0acc`
- `0x1801c0b08`
- `0x18053be1c`
- `0x18053d574`
- `0x1809cad44`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18053cded`
- `KERNEL32!CompareStringW` at `0x18053ce23`
- `KERNEL32!CompareStringW` at `0x18053ce59`
- `KERNEL32!CompareStringW` at `0x18053ce8f`
- `KERNEL32!CompareStringW` at `0x18053cded`
- `KERNEL32!CompareStringW` at `0x18053ce23`
- `KERNEL32!CompareStringW` at `0x18053ce59`
- `KERNEL32!CompareStringW` at `0x18053ce8f`
- `OLEAUT32!__imp_SysAllocString` at `0x18053c589`
- `OLEAUT32!__imp_SysAllocString` at `0x18053c589`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18053c636`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18053c636`
- `OLEAUT32!__imp_SysFreeString` at `0x18053c269`
- `OLEAUT32!__imp_SysFreeString` at `0x18053c2f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18053c3d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18053c5ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18053c269`
- `OLEAUT32!__imp_SysFreeString` at `0x18053c2f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18053c3d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18053c5ce`
- `OLEAUT32!__imp_VariantInit` at `0x18053be6a`
- `OLEAUT32!__imp_VariantInit` at `0x18053be6a`
- `OLEAUT32!__imp_VariantClear` at `0x18053c444`
- `OLEAUT32!__imp_VariantClear` at `0x18053c5d8`
- `OLEAUT32!__imp_VariantClear` at `0x18053c444`
- `OLEAUT32!__imp_VariantClear` at `0x18053c5d8`

## pseudocode

```c
__int64 __fastcall WriteFontToBSTR(struct CAttrArray *a1, unsigned __int16 **a2)
{
  int v2; // r12d
  int v3; // r8d
  unsigned __int64 v4; // r13
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // r8
  int v7; // eax
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // r11
  unsigned __int64 v10; // rdx
  int v11; // r8d
  unsigned __int64 v12; // r8
  int v13; // eax
  unsigned __int64 v14; // r9
  unsigned __int64 v15; // r10
  unsigned __int64 v16; // rdx
  int v17; // r11d
  int v18; // eax
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rdi
  unsigned __int64 v21; // rdx
  int v22; // r11d
  unsigned __int64 v23; // rdi
  int v24; // r10d
  unsigned __int64 v25; // r10
  unsigned __int64 v26; // rsi
  unsigned __int64 v27; // rdx
  int v28; // edi
  int v29; // r11d
  int v30; // r9d
  int v31; // r10d
  int v32; // edi
  int v33; // esi
  int v34; // r14d
  unsigned __int64 v35; // r11
  int v36; // edi
  __int64 v37; // rsi
  unsigned __int64 v38; // rdx
  int v39; // eax
  unsigned __int64 v40; // r12
  int v41; // ecx
  unsigned __int64 v42; // rcx
  char v43; // di
  char v44; // al
  char v45; // bl
  char v46; // r9
  char v47; // r8
  char v48; // dl
  unsigned int v49; // ebx
  int v50; // eax
  unsigned __int16 *v51; // rdx
  const wchar_t *v52; // rdi
  BSTR v53; // r10
  const wchar_t *lpString2; // r9
  WCHAR v55; // r8
  WCHAR v56; // cx
  int v57; // eax
  int v58; // eax
  BSTR v59; // r10
  const wchar_t *v60; // r9
  WCHAR v61; // r8
  WCHAR v62; // cx
  int v63; // eax
  int v64; // eax
  BSTR v65; // r10
  const wchar_t *v66; // r9
  WCHAR v67; // r8
  WCHAR v68; // cx
  int v69; // eax
  const WCHAR *bstrVal; // r10
  WCHAR v71; // r8
  WCHAR v72; // cx
  int v73; // eax
  int String; // eax
  int v75; // edi
  int v76; // edi
  void *v77; // r8
  OLECHAR *v79; // rdi
  unsigned __int16 *v80; // rax
  MemoryProtection *v81; // rcx
  unsigned __int16 *v82; // rbx
  void *v83; // r8
  __int64 v84; // r10
  int v85; // ecx
  __int64 v86; // rdi
  int v87; // ecx
  __int64 v88; // rsi
  int v89; // ecx
  __int64 v90; // r14
  int v91; // ecx
  __int64 v92; // r15
  int v93; // ecx
  int i; // r10d
  int v95; // eax
  int j; // edi
  int v97; // eax
  int k; // esi
  int v99; // r15d
  int m; // r15d
  int v101; // r12d
  int n; // r13d
  int v103; // eax
  int ii; // esi
  int v105; // eax
  int v106; // eax
  int v107; // eax
  int v108; // eax
  int v109; // eax
  int v110; // [rsp+30h] [rbp-40h]
  int v111; // [rsp+30h] [rbp-40h]
  BSTR bstrString; // [rsp+38h] [rbp-38h] BYREF
  OLECHAR *strIn; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v114; // [rsp+48h] [rbp-28h]
  OLECHAR *psz; // [rsp+50h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  struct CAttrArray *v117; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 **v118; // [rsp+B8h] [rbp+48h]

  v118 = a2;
  v117 = a1;
  strIn = 0;
  bstrString = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  *a2 = 0;
  if ( !v117 )
    return 1;
  VariantInit(&pvarg);
  v2 = *((_DWORD *)v117 + 1);
  v3 = v2;
  v4 = *((_QWORD *)v117 + 1);
  v114 = v4;
  v110 = v2;
  if ( v2 < 11 )
  {
    v5 = v4;
    goto LABEL_4;
  }
  v30 = 0;
  while ( 1 )
  {
    if ( v30 >= v3 )
    {
      v8 = 0;
LABEL_51:
      v9 = v4;
      goto LABEL_52;
    }
    v84 = (v3 + v30) / 2;
    v5 = v4 + 24 * v84;
    v85 = *(char *)(v5 + 3) >= 0 ? *(_DWORD *)(*(_QWORD *)(v5 + 8) + 48LL) : *(_DWORD *)(v5 + 8);
    if ( v85 <= -2147413085 )
    {
      if ( v85 < -2147413085 )
      {
        v30 = v84 + 1;
        goto LABEL_234;
      }
      if ( !*(_BYTE *)v5 )
      {
        v8 = v4 + 24 * v84;
        goto LABEL_51;
      }
      if ( *(_BYTE *)v5 <= 2u )
        break;
    }
    v3 = (v3 + v30) / 2;
LABEL_234:
    if ( v3 - v30 < 10 )
    {
      v5 = v4 + 24LL * v30;
      goto LABEL_4;
    }
  }
  v8 = v5 - 24;
  for ( i = v84 - 1; i >= v30; --i )
  {
    v95 = *(char *)(v8 + 3) >= 0 ? *(_DWORD *)(*(_QWORD *)(v8 + 8) + 48LL) : *(_DWORD *)(v8 + 8);
    if ( v95 != -2147413085 )
      break;
    if ( !*(_BYTE *)v8 )
      goto LABEL_51;
    if ( i == v30 )
      break;
    v8 -= 24LL;
  }
LABEL_4:
  v6 = v4 + 24LL * v3;
  while ( 2 )
  {
    if ( v5 >= v6 )
    {
LABEL_11:
      v8 = 0;
      goto LABEL_12;
    }
    if ( *(char *)(v5 + 3) >= 0 )
      v7 = *(_DWORD *)(*(_QWORD *)(v5 + 8) + 48LL);
    else
      v7 = *(_DWORD *)(v5 + 8);
    if ( v7 < -2147413085 )
    {
LABEL_9:
      v5 += 24LL;
      continue;
    }
    break;
  }
  if ( v7 != -2147413085 )
    goto LABEL_11;
  if ( *(_BYTE *)v5 )
  {
    if ( *(_BYTE *)v5 > 2u )
      goto LABEL_11;
    goto LABEL_9;
  }
  v8 = v5;
LABEL_12:
  v9 = v4;
  if ( v2 < 11 )
  {
    v10 = v4;
    v11 = v2;
    goto LABEL_14;
  }
LABEL_52:
  v31 = 0;
  v11 = v2;
  while ( 2 )
  {
    if ( v31 >= v11 )
    {
      v14 = 0;
LABEL_55:
      v15 = v4;
      goto LABEL_56;
    }
    v86 = (v11 + v31) / 2;
    v10 = v9 + 24 * v86;
    if ( *(char *)(v10 + 3) >= 0 )
      v87 = *(_DWORD *)(*(_QWORD *)(v10 + 8) + 48LL);
    else
      v87 = *(_DWORD *)(v10 + 8);
    if ( v87 > -2147413088 )
    {
LABEL_239:
      v11 = (v11 + v31) / 2;
      goto LABEL_240;
    }
    if ( v87 < -2147413088 )
    {
      v31 = v86 + 1;
LABEL_240:
      if ( v11 - v31 < 10 )
      {
        v10 = v9 + 24LL * v31;
        goto LABEL_14;
      }
      continue;
    }
    break;
  }
  if ( !*(_BYTE *)v10 )
  {
    v14 = v9 + 24 * v86;
    goto LABEL_55;
  }
  if ( *(_BYTE *)v10 > 2u )
    goto LABEL_239;
  v14 = v10 - 24;
  for ( j = v86 - 1; j >= v31; --j )
  {
    v97 = *(char *)(v14 + 3) >= 0 ? *(_DWORD *)(*(_QWORD *)(v14 + 8) + 48LL) : *(_DWORD *)(v14 + 8);
    if ( v97 != -2147413088 )
      break;
    if ( !*(_BYTE *)v14 )
      goto LABEL_55;
    if ( j == v31 )
      break;
    v14 -= 24LL;
  }
LABEL_14:
  v12 = v9 + 24LL * v11;
  while ( 2 )
  {
    if ( v10 >= v12 )
    {
LABEL_21:
      v14 = 0;
      goto LABEL_22;
    }
    if ( *(char *)(v10 + 3) >= 0 )
      v13 = *(_DWORD *)(*(_QWORD *)(v10 + 8) + 48LL);
    else
      v13 = *(_DWORD *)(v10 + 8);
    if ( v13 < -2147413088 )
    {
LABEL_19:
      v10 += 24LL;
      continue;
    }
    break;
  }
  if ( v13 != -2147413088 )
    goto LABEL_21;
  if ( *(_BYTE *)v10 )
  {
    if ( *(_BYTE *)v10 > 2u )
      goto LABEL_21;
    goto LABEL_19;
  }
  v14 = v10;
LABEL_22:
  v15 = v4;
  if ( v2 < 11 )
  {
    v16 = v4;
    v17 = v2;
    goto LABEL_24;
  }
LABEL_56:
  v32 = 0;
  v17 = v2;
  while ( 2 )
  {
    if ( v32 >= v17 )
    {
      v19 = 0;
LABEL_59:
      v20 = v4;
      goto LABEL_60;
    }
    v88 = (v17 + v32) / 2;
    v16 = v15 + 24 * v88;
    if ( *(char *)(v16 + 3) >= 0 )
      v89 = *(_DWORD *)(*(_QWORD *)(v16 + 8) + 48LL);
    else
      v89 = *(_DWORD *)(v16 + 8);
    if ( v89 > -2147413087 )
    {
LABEL_245:
      v17 = (v17 + v32) / 2;
      goto LABEL_246;
    }
    if ( v89 < -2147413087 )
    {
      v32 = v88 + 1;
LABEL_246:
      if ( v17 - v32 < 10 )
      {
        v16 = v15 + 24LL * v32;
        goto LABEL_24;
      }
      continue;
    }
    break;
  }
  if ( !*(_BYTE *)v16 )
  {
    v19 = v15 + 24 * v88;
    goto LABEL_59;
  }
  if ( *(_BYTE *)v16 > 2u )
    goto LABEL_245;
  v19 = v16 - 24;
  for ( k = v88 - 1; k >= v32; --k )
  {
    v99 = *(char *)(v19 + 3) >= 0 ? *(_DWORD *)(*(_QWORD *)(v19 + 8) + 48LL) : *(_DWORD *)(v19 + 8);
    if ( v99 != -2147413087 )
      break;
    if ( !*(_BYTE *)v19 )
      goto LABEL_59;
    if ( k == v32 )
      break;
    v19 -= 24LL;
  }
LABEL_24:
  while ( 2 )
  {
    if ( v16 >= v15 + 24LL * v17 )
    {
LABEL_30:
      v19 = 0;
      goto LABEL_31;
    }
    if ( *(char *)(v16 + 3) >= 0 )
      v18 = *(_DWORD *)(*(_QWORD *)(v16 + 8) + 48LL);
    else
      v18 = *(_DWORD *)(v16 + 8);
    if ( v18 < -2147413087 )
    {
LABEL_28:
      v16 += 24LL;
      continue;
    }
    break;
  }
  if ( v18 != -2147413087 )
    goto LABEL_30;
  if ( *(_BYTE *)v16 )
  {
    if ( *(_BYTE *)v16 > 2u )
      goto LABEL_30;
    goto LABEL_28;
  }
  v19 = v16;
LABEL_31:
  v20 = v4;
  if ( v2 < 11 )
  {
    v21 = v4;
    v22 = v2;
    goto LABEL_33;
  }
LABEL_60:
  v33 = 0;
  v22 = v2;
  while ( 2 )
  {
    if ( v33 >= v22 )
    {
      v25 = 0;
LABEL_63:
      v26 = v4;
      goto LABEL_64;
    }
    v90 = (v22 + v33) / 2;
    v21 = v20 + 24 * v90;
    if ( *(char *)(v21 + 3) >= 0 )
      v91 = *(_DWORD *)(*(_QWORD *)(v21 + 8) + 48LL);
    else
      v91 = *(_DWORD *)(v21 + 8);
    if ( v91 > -2147413093 )
    {
LABEL_251:
      v22 = (v22 + v33) / 2;
      goto LABEL_252;
    }
    if ( v91 < -2147413093 )
    {
      v33 = v90 + 1;
LABEL_252:
      if ( v22 - v33 < 10 )
      {
        v21 = v20 + 24LL * v33;
        goto LABEL_33;
      }
      continue;
    }
    break;
  }
  if ( !*(_BYTE *)v21 )
  {
    v25 = v20 + 24 * v90;
    goto LABEL_63;
  }
  if ( *(_BYTE *)v21 > 2u )
    goto LABEL_251;
  v25 = v21 - 24;
  for ( m = v90 - 1; m >= v33; --m )
  {
    v101 = *(char *)(v25 + 3) >= 0 ? *(_DWORD *)(*(_QWORD *)(v25 + 8) + 48LL) : *(_DWORD *)(v25 + 8);
    if ( v101 != -2147413093 )
      break;
    if ( !*(_BYTE *)v25 )
    {
      v2 = v110;
      goto LABEL_63;
    }
    if ( m == v33 )
      break;
    v25 -= 24LL;
  }
  v2 = v110;
LABEL_33:
  v23 = v20 + 24LL * v22;
  while ( 2 )
  {
    if ( v21 >= v23 )
    {
LABEL_40:
      v25 = 0;
      goto LABEL_41;
    }
    if ( *(char *)(v21 + 3) >= 0 )
      v24 = *(_DWORD *)(*(_QWORD *)(v21 + 8) + 48LL);
    else
      v24 = *(_DWORD *)(v21 + 8);
    if ( v24 < -2147413093 )
    {
LABEL_38:
      v21 += 24LL;
      continue;
    }
    break;
  }
  if ( v24 != -2147413093 )
    goto LABEL_40;
  if ( *(_BYTE *)v21 )
  {
    if ( *(_BYTE *)v21 > 2u )
      goto LABEL_40;
    goto LABEL_38;
  }
  v25 = v21;
LABEL_41:
  v26 = v4;
  if ( v2 < 11 )
  {
    v27 = v4;
    v28 = v2;
    goto LABEL_43;
  }
LABEL_64:
  v34 = 0;
  v28 = v2;
  while ( 2 )
  {
    if ( v34 >= v28 )
    {
      v35 = 0;
      goto LABEL_67;
    }
    v92 = (v28 + v34) / 2;
    v27 = v26 + 24 * v92;
    if ( *(char *)(v27 + 3) >= 0 )
      v93 = *(_DWORD *)(*(_QWORD *)(v27 + 8) + 48LL);
    else
      v93 = *(_DWORD *)(v27 + 8);
    if ( v93 > -2147413106 )
    {
LABEL_257:
      v28 = (v28 + v34) / 2;
      goto LABEL_258;
    }
    if ( v93 < -2147413106 )
    {
      v34 = v92 + 1;
LABEL_258:
      if ( v28 - v34 < 10 )
      {
        v27 = v26 + 24LL * v34;
        goto LABEL_43;
      }
      continue;
    }
    break;
  }
  if ( !*(_BYTE *)v27 )
  {
    v35 = v26 + 24 * v92;
    goto LABEL_67;
  }
  if ( *(_BYTE *)v27 > 2u )
    goto LABEL_257;
  v35 = v27 - 24;
  for ( n = v92 - 1; n >= v34; --n )
  {
    v103 = *(char *)(v35 + 3) >= 0 ? *(_DWORD *)(*(_QWORD *)(v35 + 8) + 48LL) : *(_DWORD *)(v35 + 8);
    if ( v103 != -2147413106 )
      break;
    if ( !*(_BYTE *)v35 )
    {
      v4 = v114;
      v2 = v110;
      goto LABEL_67;
    }
    if ( n == v34 )
      break;
    v35 -= 24LL;
  }
  v4 = v114;
  v2 = v110;
LABEL_43:
  while ( 2 )
  {
    if ( v27 >= v26 + 24LL * v28 )
    {
LABEL_76:
      v35 = 0;
      goto LABEL_77;
    }
    if ( *(char *)(v27 + 3) >= 0 )
      v29 = *(_DWORD *)(*(_QWORD *)(v27 + 8) + 48LL);
    else
      v29 = *(_DWORD *)(v27 + 8);
    if ( v29 < -2147413106 )
    {
LABEL_47:
      v27 += 24LL;
      continue;
    }
    break;
  }
  if ( v29 != -2147413106 )
    goto LABEL_76;
  if ( *(_BYTE *)v27 )
  {
    if ( *(_BYTE *)v27 > 2u )
      goto LABEL_76;
    goto LABEL_47;
  }
  v35 = v27;
LABEL_77:
  if ( v2 >= 11 )
  {
LABEL_67:
    v36 = 0;
    v111 = v2;
    while ( 1 )
    {
      if ( v36 >= v2 )
        goto LABEL_86;
      v37 = (v2 + v36) / 2;
      v38 = v4 + 24 * v37;
      if ( *(char *)(v38 + 3) >= 0 )
        v39 = *(_DWORD *)(*(_QWORD *)(v38 + 8) + 48LL);
      else
        v39 = *(_DWORD *)(v38 + 8);
      if ( v39 <= -2147413094 )
      {
        if ( v39 < -2147413094 )
        {
          v36 = v37 + 1;
          goto LABEL_73;
        }
        if ( !*(_BYTE *)v38 )
        {
          v42 = v4 + 24 * v37;
          goto LABEL_87;
        }
        if ( *(_BYTE *)v38 <= 2u )
        {
          v42 = v38 - 24;
          for ( ii = v37 - 1; ii >= v36; --ii )
          {
            v105 = *(char *)(v42 + 3) >= 0 ? *(_DWORD *)(*(_QWORD *)(v42 + 8) + 48LL) : *(_DWORD *)(v42 + 8);
            if ( v105 != -2147413094 )
              break;
            if ( !*(_BYTE *)v42 )
              goto LABEL_87;
            if ( ii == v36 )
              break;
            v42 -= 24LL;
          }
          v2 = v111;
          goto LABEL_79;
        }
      }
      v111 = (v2 + v36) / 2;
      v2 = v111;
LABEL_73:
      if ( v2 - v36 < 10 )
      {
        v38 = v4 + 24LL * v36;
        goto LABEL_79;
      }
    }
  }
  v38 = v4;
LABEL_79:
  v40 = v4 + 24LL * v2;
  while ( v38 < v40 )
  {
    if ( *(char *)(v38 + 3) >= 0 )
      v41 = *(_DWORD *)(*(_QWORD *)(v38 + 8) + 48LL);
    else
      v41 = *(_DWORD *)(v38 + 8);
    if ( v41 >= -2147413094 )
    {
      if ( v41 != -2147413094 )
        break;
      if ( !*(_BYTE *)v38 )
      {
        v42 = v38;
        goto LABEL_87;
      }
      if ( *(_BYTE *)v38 > 2u )
        break;
    }
    v38 += 24LL;
  }
LABEL_86:
  v42 = 0;
LABEL_87:
  if ( v8 && (*(_BYTE *)(v8 + 3) & 0x10) != 0 )
  {
    v44 = 1;
    v43 = 1;
  }
  else
  {
    v43 = 0;
    v44 = 1;
  }
  if ( !v14 || (v45 = 1, (*(_BYTE *)(v14 + 3) & 0x10) == 0) )
    v45 = 0;
  if ( !v19 || (v46 = 1, (*(_BYTE *)(v19 + 3) & 0x10) == 0) )
    v46 = 0;
  if ( !v25 || (v47 = 1, (*(_BYTE *)(v25 + 3) & 0x10) == 0) )
    v47 = 0;
  if ( !v35 || (v48 = 1, (*(_BYTE *)(v35 + 3) & 0x10) == 0) )
    v48 = 0;
  if ( !v42 || (*(_BYTE *)(v42 + 3) & 0x10) == 0 )
    v44 = 0;
  if ( v43 )
  {
    if ( v45 && v46 && v47 && v48 && v44 )
    {
      v49 = FormsAllocStringW(L"inherit", v118);
      goto LABEL_398;
    }
LABEL_399:
    *v118 = 0;
    return 0;
  }
  if ( v45 || v46 || v47 || v48 || v44 )
    goto LABEL_399;
  bstrString = 0;
  v49 = 0;
  v50 = PROPERTYDESC::HandleNumProperty(
          (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontWeight,
          0x20000004u,
          &bstrString,
          0,
          (struct CVoid *)&v117);
  if ( v50 < 0 )
    v50 = CBase::WriteErrorInfo(0, v50, -2147413085, INVOKE_PROPERTYGET);
  v51 = bstrString;
  if ( v50 || !bstrString || !*bstrString )
    goto LABEL_180;
  v52 = L"normal";
  v53 = bstrString;
  lpString2 = L"normal";
  while ( 2 )
  {
    v55 = *v53;
    v56 = *lpString2;
    if ( !*v53 )
    {
      v57 = -(v56 != 0);
      goto LABEL_115;
    }
    if ( v55 == v56 )
    {
LABEL_113:
      ++v53;
      ++lpString2;
      continue;
    }
    break;
  }
  if ( (unsigned __int16)(v55 - 65) <= 0x19u )
  {
    v55 += 32;
    if ( (unsigned __int16)(v56 - 65) <= 0x19u )
      goto LABEL_191;
  }
  else
  {
    if ( (unsigned __int16)(v56 - 65) > 0x19u )
      goto LABEL_194;
LABEL_191:
    v56 += 32;
  }
  if ( v55 == v56 )
    goto LABEL_113;
LABEL_194:
  if ( ((v55 | v56) & 0xFF80) == 0 )
    goto LABEL_195;
  v106 = CompareStringW(0x409u, 0x30001u, v53, -1, lpString2, -1);
  v51 = bstrString;
  if ( v106 <= 0 )
    goto LABEL_195;
  v57 = v106 - 2;
LABEL_115:
  if ( v57 )
  {
LABEL_195:
    v49 = CStr::Append((CStr *)&strIn, v51);
    if ( !v49 )
    {
      v49 = CStr::Append((CStr *)&strIn, L" ");
      if ( !v49 )
      {
        v51 = bstrString;
        goto LABEL_116;
      }
    }
    goto LABEL_178;
  }
LABEL_116:
  SysFreeString(v51);
  bstrString = 0;
  v58 = PROPERTYDESC::HandleNumProperty(
          (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontStyle,
          0x20000004u,
          &bstrString,
          0,
          (struct CVoid *)&v117);
  if ( v58 < 0 )
    v58 = CBase::WriteErrorInfo(0, v58, -2147413088, INVOKE_PROPERTYGET);
  v51 = bstrString;
  if ( v58 || !bstrString || !*bstrString )
    goto LABEL_180;
  v59 = bstrString;
  v60 = L"normal";
  while ( 2 )
  {
    v61 = *v59;
    v62 = *v60;
    if ( !*v59 )
    {
      v63 = -(v62 != 0);
      goto LABEL_126;
    }
    if ( v61 == v62 )
    {
LABEL_124:
      ++v59;
      ++v60;
      continue;
    }
    break;
  }
  if ( (unsigned __int16)(v61 - 65) <= 0x19u )
  {
    v61 += 32;
    if ( (unsigned __int16)(v62 - 65) <= 0x19u )
      goto LABEL_200;
  }
  else
  {
    if ( (unsigned __int16)(v62 - 65) > 0x19u )
      goto LABEL_203;
LABEL_200:
    v62 += 32;
  }
  if ( v61 == v62 )
    goto LABEL_124;
LABEL_203:
  if ( ((v61 | v62) & 0xFF80) == 0 )
    goto LABEL_204;
  v107 = CompareStringW(0x409u, 0x30001u, v59, -1, v60, -1);
  v51 = bstrString;
  if ( v107 <= 0 )
    goto LABEL_204;
  v63 = v107 - 2;
LABEL_126:
  if ( v63 )
  {
LABEL_204:
    v49 = CStr::Append((CStr *)&strIn, v51);
    if ( !v49 )
    {
      v49 = CStr::Append((CStr *)&strIn, L" ");
      if ( !v49 )
      {
        v51 = bstrString;
        goto LABEL_127;
      }
    }
    goto LABEL_178;
  }
LABEL_127:
  SysFreeString(v51);
  bstrString = 0;
  v64 = PROPERTYDESC::HandleNumProperty(
          (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontVariant,
          0x20000004u,
          &bstrString,
          0,
          (struct CVoid *)&v117);
  if ( v64 < 0 )
    v64 = CBase::WriteErrorInfo(0, v64, -2147413087, INVOKE_PROPERTYGET);
  v51 = bstrString;
  if ( v64 || !bstrString || !*bstrString )
    goto LABEL_180;
  v65 = bstrString;
  v66 = L"normal";
  while ( 2 )
  {
    v67 = *v65;
    v68 = *v66;
    if ( !*v65 )
    {
      v69 = -(v68 != 0);
      goto LABEL_143;
    }
    if ( v67 == v68 )
    {
LABEL_135:
      ++v65;
      ++v66;
      continue;
    }
    break;
  }
  if ( (unsigned __int16)(v67 - 65) <= 0x19u )
  {
    v67 += 32;
    if ( (unsigned __int16)(v68 - 65) <= 0x19u )
      goto LABEL_209;
  }
  else
  {
    if ( (unsigned __int16)(v68 - 65) > 0x19u )
      goto LABEL_212;
LABEL_209:
    v68 += 32;
  }
  if ( v67 == v68 )
    goto LABEL_135;
LABEL_212:
  if ( ((v67 | v68) & 0xFF80) == 0 )
    goto LABEL_213;
  v108 = CompareStringW(0x409u, 0x30001u, v65, -1, v66, -1);
  v51 = bstrString;
  if ( v108 <= 0 )
    goto LABEL_213;
  v69 = v108 - 2;
LABEL_143:
  if ( v69 )
  {
LABEL_213:
    v49 = CStr::Append((CStr *)&strIn, v51);
    if ( !v49 )
    {
      v49 = CStr::Append((CStr *)&strIn, L" ");
      if ( !v49 )
      {
        v51 = bstrString;
        goto LABEL_144;
      }
    }
    goto LABEL_178;
  }
LABEL_144:
  SysFreeString(v51);
  bstrString = 0;
  if ( (unsigned int)PROPERTYDESC::HandleTypedValueProperty(
                       (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationfontSize,
                       0x30000004u,
                       (unsigned __int16 **)&pvarg,
                       0,
                       (struct CVoid *)&v117)
    || pvarg.vt != 8
    || !pvarg.llVal
    || !*pvarg.bstrVal )
  {
    goto LABEL_179;
  }
  v49 = CStr::Append((CStr *)&strIn, pvarg.bstrVal);
  if ( v49 )
  {
LABEL_178:
    v51 = bstrString;
    v76 = 1;
    goto LABEL_181;
  }
  VariantClear(&pvarg);
  if ( (unsigned int)PROPERTYDESC::HandleTypedValueProperty(
                       (PROPERTYDESC *)&s_propdescCCSSStyleDeclarationlineHeight,
                       0x30000004u,
                       (unsigned __int16 **)&pvarg,
                       0,
                       (struct CVoid *)&v117)
    || pvarg.vt != 8
    || (bstrVal = pvarg.bstrVal) == 0
    || !*pvarg.bstrVal )
  {
LABEL_179:
    v51 = bstrString;
    goto LABEL_180;
  }
  while ( 2 )
  {
    v71 = *bstrVal;
    v72 = *v52;
    if ( !*bstrVal )
    {
      v73 = -(v72 != 0);
      goto LABEL_169;
    }
    if ( v71 == v72 )
      goto LABEL_155;
    if ( (unsigned __int16)(v71 - 65) <= 0x19u )
    {
      v71 += 32;
      if ( (unsigned __int16)(v72 - 65) <= 0x19u )
        goto LABEL_262;
    }
    else
    {
      if ( (unsigned __int16)(v72 - 65) > 0x19u )
        break;
LABEL_262:
      v72 += 32;
    }
    if ( v71 == v72 )
    {
LABEL_155:
      ++bstrVal;
      ++v52;
      continue;
    }
    break;
  }
  if ( ((v71 | v72) & 0xFF80) == 0 )
    goto LABEL_266;
  v109 = CompareStringW(0x409u, 0x30001u, bstrVal, -1, v52, -1);
  if ( v109 <= 0 )
    goto LABEL_266;
  v73 = v109 - 2;
LABEL_169:
  if ( !v73 )
    goto LABEL_170;
LABEL_266:
  v49 = CStr::Append((CStr *)&strIn, L"/");
  if ( v49 )
    goto LABEL_178;
  v49 = CStr::Append((CStr *)&strIn, pvarg.bstrVal);
  if ( v49 )
    goto LABEL_178;
LABEL_170:
  v49 = CStr::Append((CStr *)&strIn, L" ");
  if ( v49 )
    goto LABEL_178;
  bstrString = 0;
  psz = 0;
  String = BASICPROPPARAMS::GetString(
             (BASICPROPPARAMS *)&unk_1810E1E08,
             0,
             (struct CVoid *)&v117,
             (const unsigned __int16 **)&psz,
             0);
  v75 = String;
  if ( String )
  {
    if ( String < 0 )
      goto LABEL_388;
    goto LABEL_382;
  }
  if ( psz )
  {
    bstrString = SysAllocString(psz);
    v51 = bstrString;
    if ( bstrString )
      goto LABEL_174;
    v75 = -2147024882;
LABEL_388:
    v75 = CBase::WriteErrorInfo(0, v75, -2147413094, INVOKE_PROPERTYGET);
LABEL_382:
    v51 = bstrString;
  }
  else
  {
    v51 = 0;
    bstrString = 0;
  }
LABEL_174:
  if ( !v75 && v51 && *v51 )
  {
    v49 = CStr::Append((CStr *)&strIn, v51);
    goto LABEL_178;
  }
LABEL_180:
  v76 = 0;
LABEL_181:
  SysFreeString(v51);
  VariantClear(&pvarg);
  if ( !v49 )
  {
    if ( v76 || (v49 = CStr::Set((CStr *)&strIn, &LocaleName)) == 0 )
    {
      if ( strIn )
      {
        v79 = strIn - 2;
        v80 = SysAllocStringLen(strIn, *((_DWORD *)strIn - 1) >> 1);
        v81 = (MemoryProtection *)g_hProcessHeap;
        v82 = v80;
        *v118 = v80;
        MemoryProtection::HeapFree(v81, v79, v83);
        return v82 == 0 ? 0x8007000E : 0;
      }
      else
      {
        *v118 = 0;
        return 0;
      }
    }
LABEL_398:
    CStr::_Free((CStr *)&strIn);
    return v49;
  }
  if ( strIn )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, strIn - 2, v77);
  return v49;
}

```

## disassembly

```asm
0x18053be1c  mov     [rsp-38h+arg_10], rbx
0x18053be21  mov     [rsp-38h+arg_8], rdx
0x18053be26  mov     [rsp-38h+arg_0], rcx
0x18053be2b  push    rbp
0x18053be2c  push    rsi
0x18053be2d  push    rdi
0x18053be2e  push    r12
0x18053be30  push    r13
0x18053be32  push    r14
0x18053be34  push    r15
0x18053be36  mov     rbp, rsp
0x18053be39  sub     rsp, 70h
0x18053be3d  xor     r15d, r15d
0x18053be40  xor     eax, eax
0x18053be42  xorps   xmm0, xmm0
0x18053be45  mov     qword ptr [rbp+pvarg+10h], rax
0x18053be49  mov     rax, [rbp+arg_8]
0x18053be4d  mov     [rbp+strIn], r15
0x18053be51  mov     [rbp+bstrString], r15
0x18053be55  movups  xmmword ptr [rbp+pvarg], xmm0
0x18053be59  mov     [rax], r15
0x18053be5c  cmp     [rbp+arg_0], r15
0x18053be60  jz      loc_18053C663
0x18053be66  lea     rcx, [rbp+pvarg]; pvarg
0x18053be6a  call    cs:__imp_VariantInit
0x18053be70  mov     rax, [rbp+arg_0]
0x18053be74  lea     esi, [r15+1]
0x18053be78  lea     r14d, [r15+2]
0x18053be7c  mov     r11d, 800113A3h
0x18053be82  mov     r12d, [rax+4]
0x18053be86  mov     r8d, r12d
0x18053be89  mov     r13, [rax+8]
0x18053be8d  mov     [rbp+var_28], r13
0x18053be91  mov     [rbp+var_40], r12d
0x18053be95  cmp     r12d, 0Bh
0x18053be99  jge     loc_18053BFFE
0x18053be9f  mov     rdx, r13
0x18053bea2  movsxd  rax, r8d
0x18053bea5  lea     rcx, [rax+rax*2]
0x18053bea9  lea     r8, ds:0[rcx*8]
0x18053beb1  add     r8, r13
0x18053beb4  cmp     rdx, r8
0x18053beb7  jnb     short loc_18053BED7
0x18053beb9  cmp     [rdx+3], r15b
0x18053bebd  jge     loc_18053C37C
0x18053bec3  mov     eax, [rdx+8]
0x18053bec6  cmp     eax, r11d
0x18053bec9  jge     short loc_18053BED1
0x18053becb  add     rdx, 18h
0x18053becf  jmp     short loc_18053BEB4
0x18053bed1  jz      loc_18053C7F6
0x18053bed7  mov     rbx, r15
0x18053beda  mov     r11, r13
0x18053bedd  cmp     r12d, 0Bh
0x18053bee1  jge     loc_18053C010
0x18053bee7  mov     rdx, r13
0x18053beea  mov     r8d, r12d
0x18053beed  mov     r9d, 800113A0h
0x18053bef3  movsxd  rax, r8d
0x18053bef6  lea     rcx, [rax+rax*2]
0x18053befa  lea     r8, [r11+rcx*8]
0x18053befe  cmp     rdx, r8
0x18053bf01  jnb     short loc_18053BF21
0x18053bf03  cmp     [rdx+3], r15b
0x18053bf07  jge     loc_18053C388
0x18053bf0d  mov     eax, [rdx+8]
0x18053bf10  cmp     eax, r9d
0x18053bf13  jge     short loc_18053BF1B
0x18053bf15  add     rdx, 18h
0x18053bf19  jmp     short loc_18053BEFE
0x18053bf1b  jz      loc_18053C808
0x18053bf21  mov     r9, r15
0x18053bf24  mov     r10, r13
0x18053bf27  cmp     r12d, 0Bh
0x18053bf2b  jge     loc_18053C02B
0x18053bf31  mov     rdx, r13
0x18053bf34  mov     r11d, r12d
0x18053bf37  movsxd  rax, r11d
0x18053bf3a  lea     rcx, [rax+rax*2]
0x18053bf3e  lea     r8, [r10+rcx*8]
0x18053bf42  mov     ecx, 800113A1h
0x18053bf47  cmp     rdx, r8
0x18053bf4a  jnb     short loc_18053BF69
0x18053bf4c  cmp     [rdx+3], r15b
0x18053bf50  jge     loc_18053C394
0x18053bf56  mov     eax, [rdx+8]
0x18053bf59  cmp     eax, ecx
0x18053bf5b  jge     short loc_18053BF63
0x18053bf5d  add     rdx, 18h
0x18053bf61  jmp     short loc_18053BF47
0x18053bf63  jz      loc_18053C81A
0x18053bf69  mov     r8, r15
0x18053bf6c  mov     rdi, r13
0x18053bf6f  cmp     r12d, 0Bh
0x18053bf73  jge     loc_18053C040
0x18053bf79  mov     rdx, r13
0x18053bf7c  mov     r11d, r12d
0x18053bf7f  movsxd  rax, r11d
0x18053bf82  mov     esi, 8001139Bh
0x18053bf87  lea     rcx, [rax+rax*2]
0x18053bf8b  lea     rdi, [rdi+rcx*8]
0x18053bf8f  cmp     rdx, rdi
0x18053bf92  jnb     short loc_18053BFB3
0x18053bf94  cmp     [rdx+3], r15b
0x18053bf98  jge     loc_18053C3A0
0x18053bf9e  mov     r10d, [rdx+8]
0x18053bfa2  cmp     r10d, esi
0x18053bfa5  jge     short loc_18053BFAD
0x18053bfa7  add     rdx, 18h
0x18053bfab  jmp     short loc_18053BF8F
0x18053bfad  jz      loc_18053C82C
0x18053bfb3  mov     r10, r15
0x18053bfb6  mov     rsi, r13
0x18053bfb9  cmp     r12d, 0Bh
0x18053bfbd  jge     loc_18053C05B
0x18053bfc3  mov     rdx, r13
0x18053bfc6  mov     edi, r12d
0x18053bfc9  movsxd  rax, edi
0x18053bfcc  lea     rcx, [rax+rax*2]
0x18053bfd0  lea     r14, [rsi+rcx*8]
0x18053bfd4  cmp     rdx, r14
0x18053bfd7  jnb     loc_18053C0EA
0x18053bfdd  cmp     [rdx+3], r15b
0x18053bfe1  jge     loc_18053C3AD
0x18053bfe7  mov     r11d, [rdx+8]
0x18053bfeb  cmp     r11d, 8001138Eh
0x18053bff2  jge     loc_18053C0E4
0x18053bff8  add     rdx, 18h
0x18053bffc  jmp     short loc_18053BFD4
0x18053bffe  mov     r9d, r15d
0x18053c001  cmp     r9d, r8d
0x18053c004  jl      loc_18053C86E
0x18053c00a  mov     rbx, r15
0x18053c00d  mov     r11, r13
0x18053c010  mov     r10d, r15d
0x18053c013  mov     r8d, r12d
0x18053c016  mov     r9d, 800113A0h
0x18053c01c  cmp     r10d, r8d
0x18053c01f  jl      loc_18053C8C7
0x18053c025  mov     r9, r15
0x18053c028  mov     r10, r13
0x18053c02b  mov     edi, r15d
0x18053c02e  mov     r11d, r12d
0x18053c031  cmp     edi, r11d
0x18053c034  jl      loc_18053C912
0x18053c03a  mov     r8, r15
0x18053c03d  mov     rdi, r13
0x18053c040  mov     esi, r15d
0x18053c043  mov     r11d, r12d
0x18053c046  mov     r10d, 2
0x18053c04c  cmp     esi, r11d
0x18053c04f  jl      loc_18053C960
0x18053c055  mov     r10, r15
0x18053c058  mov     rsi, r13
0x18053c05b  mov     r14d, r15d
0x18053c05e  mov     edi, r12d
0x18053c061  mov     r11d, 2
0x18053c067  cmp     r14d, edi
0x18053c06a  jl      loc_18053C9AE
0x18053c070  xor     r15d, r15d
0x18053c073  mov     r11d, r15d
0x18053c076  mov     edi, r15d
0x18053c079  mov     [rbp+var_40], r12d
0x18053c07d  mov     r14d, 2
0x18053c083  cmp     edi, r12d
0x18053c086  jge     loc_18053C137
0x18053c08c  lea     eax, [r12+rdi]
0x18053c090  cdq
0x18053c091  idiv    r14d
0x18053c094  movsxd  rsi, eax
0x18053c097  lea     rdx, [rsi+rsi*2]
0x18053c09b  lea     rdx, ds:0[rdx*8]
0x18053c0a3  add     rdx, r13
0x18053c0a6  cmp     [rdx+3], r15b
0x18053c0aa  jge     loc_18053CB52
0x18053c0b0  mov     eax, [rdx+8]
0x18053c0b3  mov     ecx, 8001139Ah
0x18053c0b8  cmp     eax, ecx
0x18053c0ba  jle     loc_18053CAFE
0x18053c0c0  mov     [rbp+var_40], esi
0x18053c0c3  mov     r12d, esi
0x18053c0c6  mov     eax, r12d
0x18053c0c9  sub     eax, edi
0x18053c0cb  cmp     eax, 0Ah
0x18053c0ce  jge     short loc_18053C083
0x18053c0d0  movsxd  rax, edi
0x18053c0d3  lea     rcx, [rax+rax*2]
0x18053c0d7  lea     rdx, ds:0[rcx*8]
0x18053c0df  add     rdx, r13
0x18053c0e2  jmp     short loc_18053C0F6
0x18053c0e4  jz      loc_18053C83D
0x18053c0ea  mov     r11, r15
0x18053c0ed  cmp     r12d, 0Bh
0x18053c0f1  jge     short loc_18053C076
0x18053c0f3  mov     rdx, r13
0x18053c0f6  movsxd  rax, r12d
0x18053c0f9  lea     rcx, [rax+rax*2]
0x18053c0fd  lea     r12, ds:0[rcx*8]
0x18053c105  add     r12, r13
0x18053c108  mov     r13d, 8001139Ah
0x18053c10e  cmp     rdx, r12
0x18053c111  jnb     short loc_18053C137
0x18053c113  cmp     [rdx+3], r15b
0x18053c117  jge     loc_18053C3BA
0x18053c11d  mov     ecx, [rdx+8]
0x18053c120  cmp     ecx, r13d
0x18053c123  jge     short loc_18053C12E
0x18053c125  add     rdx, 18h
0x18053c129  xor     r15d, r15d
0x18053c12c  jmp     short loc_18053C10E
0x18053c12e  jz      loc_18053C84E
0x18053c134  xor     r15d, r15d
0x18053c137  mov     rcx, r15
0x18053c13a  mov     sil, 10h
0x18053c13d  test    rbx, rbx
0x18053c140  jnz     loc_18053C4C0
0x18053c146  mov     dil, r15b
0x18053c149  mov     eax, 1
0x18053c14e  test    r9, r9
0x18053c151  jnz     loc_18053C4D7
0x18053c157  mov     bl, r15b
0x18053c15a  test    r8, r8
0x18053c15d  jnz     loc_18053C4E8
0x18053c163  mov     r9b, r15b
0x18053c166  test    r10, r10
0x18053c169  jnz     loc_18053C4FA
0x18053c16f  mov     r8b, r15b
0x18053c172  test    r11, r11
0x18053c175  jnz     loc_18053C50C
0x18053c17b  mov     dl, r15b
0x18053c17e  test    rcx, rcx
0x18053c181  jnz     loc_18053C51D
0x18053c187  mov     al, r15b
0x18053c18a  test    dil, dil
0x18053c18d  jnz     loc_18053CFC1
0x18053c193  test    bl, bl
0x18053c195  jnz     loc_18053CFF7
0x18053c19b  test    r9b, r9b
0x18053c19e  jnz     loc_18053CFF7
0x18053c1a4  test    r8b, r8b
0x18053c1a7  jnz     loc_18053CFF7
0x18053c1ad  test    dl, dl
0x18053c1af  jnz     loc_18053CFF7
0x18053c1b5  test    al, al
0x18053c1b7  jnz     loc_18053CFF7
0x18053c1bd  lea     rax, [rbp+arg_0]
0x18053c1c1  mov     [rbp+bstrString], r15
0x18053c1c5  mov     esi, 20000004h
0x18053c1ca  mov     [rsp+70h+lpString2], rax; struct CVoid *
0x18053c1cf  mov     edx, esi; unsigned int
0x18053c1d1  lea     r8, [rbp+bstrString]; void *
0x18053c1d5  xor     r9d, r9d; struct CBase *
0x18053c1d8  lea     rcx, s_propdescCCSSStyleDeclarationfontWeight; this
0x18053c1df  mov     ebx, r15d
0x18053c1e2  call    ?HandleNumProperty@PROPERTYDESC@@QEBAJKPEAXPEAVCBase@@PEAVCVoid@@@Z; PROPERTYDESC::HandleNumProperty(ulong,void *,CBase *,CVoid *)
0x18053c1e7  test    eax, eax
0x18053c1e9  js      loc_18053CF2B
0x18053c1ef  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18053c1f3  test    eax, eax
0x18053c1f5  jnz     loc_18053C5C8
0x18053c1fb  test    rdx, rdx
0x18053c1fe  jz      loc_18053C5C8
0x18053c204  cmp     [rdx], r15w
0x18053c208  jz      loc_18053C5C8
0x18053c20e  or      r11d, 0FFFFFFFFh
0x18053c212  lea     rdi, aNormal_0; "normal"
0x18053c219  mov     r10, rdx
0x18053c21c  mov     r12w, 41h ; 'A'
0x18053c221  mov     r13w, 19h
0x18053c226  mov     r14w, 20h ; ' '
0x18053c22b  test    rdx, rdx
0x18053c22e  jz      loc_18053C6B8
0x18053c234  mov     r9, rdi
0x18053c237  movzx   r8d, word ptr [r10]
0x18053c23b  movzx   ecx, word ptr [r9]
0x18053c23f  test    r8w, r8w
0x18053c243  jz      short loc_18053C259
0x18053c245  cmp     r8w, cx
0x18053c249  jnz     loc_18053C66A
0x18053c24f  add     r10, 2
0x18053c253  add     r9, 2
0x18053c257  jmp     short loc_18053C237
0x18053c259  neg     cx
0x18053c25c  sbb     eax, eax
0x18053c25e  test    eax, eax
0x18053c260  jnz     loc_18053C6B8
0x18053c266  mov     rcx, rdx; bstrString
0x18053c269  call    cs:__imp_SysFreeString
0x18053c26f  lea     rax, [rbp+arg_0]
0x18053c273  mov     [rbp+bstrString], r15
0x18053c277  xor     r9d, r9d; struct CBase *
0x18053c27a  mov     [rsp+70h+lpString2], rax; struct CVoid *
0x18053c27f  lea     r8, [rbp+bstrString]; void *
0x18053c283  mov     edx, esi; unsigned int
0x18053c285  lea     rcx, s_propdescCCSSStyleDeclarationfontStyle; this
0x18053c28c  call    ?HandleNumProperty@PROPERTYDESC@@QEBAJKPEAXPEAVCBase@@PEAVCVoid@@@Z; PROPERTYDESC::HandleNumProperty(ulong,void *,CBase *,CVoid *)
0x18053c291  test    eax, eax
0x18053c293  js      loc_18053CF45
0x18053c299  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18053c29d  test    eax, eax
  ... truncated ...
```
