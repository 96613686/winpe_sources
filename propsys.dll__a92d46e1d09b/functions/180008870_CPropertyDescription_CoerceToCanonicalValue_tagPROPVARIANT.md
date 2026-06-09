# CPropertyDescription::CoerceToCanonicalValue(tagPROPVARIANT *)

- ea: `0x180008870`
- end: `0x180009230`
- name: `?CoerceToCanonicalValue@CPropertyDescription@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `2496`
- prototype: `__int64 __fastcall(CPropertyDescription *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `4`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x180081a70`
- `0x180081a80`
- `0x180081a90`
- `0x180081aa0`

## callees

- `0x180008814`
- `0x180008870`
- `0x180009240`
- `0x18000bc6c`
- `0x18000c234`
- `0x18000c54c`
- `0x18000c5a4`
- `0x18000ca30`
- `0x18000fa10`
- `0x18002bd14`
- `0x18002cfd0`
- `0x18002f9e0`
- `0x1800328b0`
- `0x180041ce8`
- `0x180041f14`
- `0x180042094`
- `0x180069094`
- `0x18006ed20`
- `0x18006fb8c`
- `0x180083bc0`
- `0x180095ee0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!IsCharSpaceW` at `0x18000894f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!IsCharSpaceW` at `0x180008968`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!IsCharSpaceW` at `0x18000910d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!IsCharSpaceW` at `0x18000911e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!IsCharSpaceW` at `0x18000894f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!IsCharSpaceW` at `0x180008968`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!IsCharSpaceW` at `0x18000910d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!IsCharSpaceW` at `0x18000911e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000897e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008996`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800089d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008af8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008b14`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008c61`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800090bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009189`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000897e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008996`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800089d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008af8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008b14`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008c61`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800090bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009136`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009136`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180008df4`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180008df4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180008e2d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180008e2d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180008e11`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180008e11`

## pseudocode

```c
__int64 __fastcall CPropertyDescription::CoerceToCanonicalValue(CPropertyDescription *this, PROPVARIANT *a2, int a3)
{
  unsigned int v5; // edx
  LONG v6; // r15d
  int v7; // ecx
  BOOL v8; // esi
  WCHAR *v9; // rdi
  WCHAR v10; // cx
  HRESULT inited; // esi
  void *v12; // rdi
  BYTE *v13; // xmm1_8
  __int64 v14; // rcx
  VARTYPE v16; // cx
  BYTE *v17; // xmm1_8
  VARTYPE v18; // dx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  unsigned int v22; // eax
  __int64 v23; // r13
  BYTE *v24; // rax
  __int64 v25; // rdi
  unsigned __int16 *v26; // r12
  __int64 v27; // r15
  unsigned __int16 *ValueStart; // rax
  __int64 v29; // rax
  _WORD *v30; // rcx
  unsigned int v31; // r10d
  __int64 v32; // rdx
  BOOL v33; // eax
  LONG v34; // eax
  BYTE *v35; // r8
  __int64 v36; // r9
  int StringPropVariantCanonical; // eax
  LONG v38; // edx
  __int64 v39; // rcx
  SAFEARRAY *v40; // rdi
  __int64 v41; // rcx
  __int64 v42; // r8
  bool v43; // zf
  __int64 v44; // rdx
  HRESULT v45; // edi
  unsigned int v46; // r12d
  __int64 v47; // rdi
  int v48; // r15d
  const unsigned __int16 *v49; // r13
  __int64 v50; // rsi
  const unsigned __int16 *v51; // r8
  const unsigned __int16 *v52; // rax
  BYTE *v53; // rax
  BOOL v54; // eax
  _BYTE *v55; // rdi
  WCHAR v56; // cx
  int v57; // [rsp+20h] [rbp-49h]
  LPVOID pv; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v59; // [rsp+38h] [rbp-31h]
  __int64 v60; // [rsp+40h] [rbp-29h]
  VARTYPE v61[2]; // [rsp+48h] [rbp-21h] BYREF
  LONG plLbound; // [rsp+4Ch] [rbp-1Dh] BYREF
  LONG plUbound; // [rsp+50h] [rbp-19h] BYREF
  PROPVARIANT ppropvarDest[2]; // [rsp+58h] [rbp-11h] BYREF
  BYTE *v65; // [rsp+68h] [rbp-1h]
  __int64 v66; // [rsp+70h] [rbp+7h]
  LONG *p_plUbound; // [rsp+78h] [rbp+Fh]
  __int64 v68; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( (*((_BYTE *)this + 176) & 1) == 0 )
  {
    inited = -2147418113;
LABEL_16:
    PropVariantClear(a2);
    return (unsigned int)inited;
  }
  if ( (byte_1800F1382 & 0x10) != 0 )
  {
    v41 = *((_QWORD *)this + 5) + 36LL;
    v66 = 16;
    v65 = (BYTE *)v41;
    v68 = 4;
    plUbound = *(_DWORD *)(v41 + 16);
    p_plUbound = &plUbound;
    McGenEventWrite_EtwEventWriteTransfer(
      v41,
      (unsigned int)ShellTraceId_PropertyDescription_CoerceToCanonicalValue_Start,
      a3,
      3,
      (__int64)ppropvarDest);
  }
  v61[0] = 0;
  (*(void (__fastcall **)(CPropertyDescription *, VARTYPE *))(*(_QWORD *)this + 40LL))(this, v61);
  v5 = *(unsigned __int16 *)a2;
  if ( v61[0] == (_WORD)v5 )
  {
    v14 = 65533;
    if ( ((v61[0] - 19) & 0xFFFD) == 0 && *(_DWORD *)(*((_QWORD *)this + 5) + 88LL) != 4 )
    {
      inited = 0;
      goto LABEL_22;
    }
  }
  v6 = 0;
  if ( !(_WORD)v5 )
    goto LABEL_39;
  if ( (_WORD)v5 == 1 )
  {
    *(_WORD *)a2 = 0;
    goto LABEL_39;
  }
  if ( v5 != 8 )
  {
    if ( v5 <= 0xFFF )
    {
      if ( v5 != 4095 )
      {
        switch ( *(_WORD *)a2 )
        {
          case 2:
          case 3:
          case 4:
          case 5:
          case 6:
          case 7:
          case 9:
          case 0xA:
          case 0xB:
          case 0xC:
          case 0xD:
          case 0xE:
          case 0x10:
          case 0x11:
          case 0x12:
          case 0x13:
          case 0x14:
          case 0x15:
          case 0x16:
          case 0x17:
          case 0x1E:
          case 0x1F:
          case 0x40:
          case 0x41:
          case 0x42:
          case 0x43:
          case 0x44:
          case 0x45:
          case 0x47:
          case 0x48:
          case 0x49:
            break;
          default:
            goto LABEL_70;
        }
      }
    }
    else
    {
LABEL_70:
      if ( (v5 & 0x4000) == 0 )
      {
        if ( (v5 & 0x1000) != 0 )
        {
          v34 = *((_DWORD *)a2 + 2);
        }
        else
        {
          if ( (v5 & 0x2000) == 0 )
            goto LABEL_38;
          v40 = (SAFEARRAY *)a2[1];
          if ( SafeArrayGetDim(v40) != 1 )
            goto LABEL_38;
          plLbound = 0;
          if ( SafeArrayGetLBound(v40, 1u, &plLbound) < 0 )
            goto LABEL_38;
          plUbound = 0;
          if ( SafeArrayGetUBound(v40, 1u, &plUbound) < 0 || plUbound < plLbound )
            goto LABEL_38;
          v34 = plUbound - plLbound + 1;
        }
        if ( !v34 )
        {
LABEL_38:
          PropVariantClear(a2);
          goto LABEL_39;
        }
      }
    }
  }
  v7 = *(unsigned __int16 *)a2;
  v8 = 0;
  if ( v7 == 8 )
  {
LABEL_9:
    v9 = (WCHAR *)a2[1];
    if ( v9 )
    {
      if ( *v9 )
      {
        if ( IsCharSpaceW(*v9) )
        {
          do
          {
            v10 = v9[1];
            ++v9;
          }
          while ( IsCharSpaceW(v10) );
        }
        if ( !*v9 )
        {
LABEL_14:
          PropVariantClear(a2);
          inited = 262560;
          goto LABEL_40;
        }
        goto LABEL_30;
      }
      goto LABEL_110;
    }
    goto LABEL_38;
  }
  v19 = v7 - 1;
  if ( !v19 )
    goto LABEL_38;
  v20 = v19 - 29;
  if ( v20 )
  {
    v21 = v20 - 1;
    if ( v21 )
    {
      if ( v21 != 33 )
        goto LABEL_30;
      v54 = (unsigned __int64)a2[1] < 0xC92A69C000LL;
      v8 = v54;
      goto LABEL_29;
    }
    goto LABEL_9;
  }
  v55 = a2[1];
  if ( !v55 )
    goto LABEL_38;
  if ( *v55 )
  {
    if ( IsCharSpaceW((char)*v55) )
    {
      do
        v56 = (char)*++v55;
      while ( IsCharSpaceW(v56) );
    }
    if ( !*v55 )
      goto LABEL_14;
    goto LABEL_30;
  }
LABEL_110:
  v54 = ((*(_DWORD *)(*((_QWORD *)this + 5) + 60LL) >> 11) & 1) == 0;
LABEL_29:
  if ( v54 )
  {
    PropVariantClear(a2);
    if ( v8 )
    {
      inited = 262560;
      goto LABEL_40;
    }
    goto LABEL_39;
  }
LABEL_30:
  if ( v61[0] != 31 || *(_WORD *)a2 != 4127 )
  {
    if ( !(unsigned int)IsPropVariantValidForVista((const struct tagPROPVARIANT *)a2) )
    {
      inited = -2147024809;
      goto LABEL_22;
    }
    if ( v61[0] != 1 )
    {
      v16 = *(_WORD *)a2;
      if ( *(_WORD *)a2 )
      {
        if ( v16 != v61[0] )
        {
          if ( v61[0] != 4127 || v16 != 8 && (unsigned __int16)(v16 - 30) > 1u )
          {
            v65 = 0;
            *(_OWORD *)ppropvarDest = 0;
            inited = PropVariantChangeType(ppropvarDest, a2, 0, v61[0]);
            if ( inited < 0 )
            {
              if ( inited != -2147024809 )
                inited = -2147316576;
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x9A6,
                (unsigned int)"onecoreuap\\shell\\propsys\\propdesc.cpp",
                (const char *)(unsigned int)inited,
                v57);
              goto LABEL_22;
            }
            PropVariantClear(a2);
            v17 = v65;
            *(_OWORD *)a2 = *(_OWORD *)ppropvarDest;
            a2[2] = v17;
            goto LABEL_40;
          }
          pv = 0;
          inited = PropVariantToStringAlloc(a2, (PWSTR *)&pv);
          if ( inited < 0 )
            goto LABEL_22;
          v12 = pv;
          v65 = 0;
          *(_OWORD *)ppropvarDest = 0;
          if ( pv )
          {
            inited = InitPropVariantFromStringEx((unsigned __int16 *)pv);
            if ( inited < 0 )
            {
LABEL_20:
              CoTaskMemFree(v12);
              goto LABEL_21;
            }
          }
          else
          {
            inited = 0;
          }
          PropVariantClear(a2);
          v13 = v65;
          *(_OWORD *)a2 = *(_OWORD *)ppropvarDest;
          a2[2] = v13;
          goto LABEL_20;
        }
      }
    }
LABEL_39:
    inited = 0;
    goto LABEL_40;
  }
  v22 = *((_DWORD *)a2 + 2);
  inited = 0;
  v23 = 0;
  plUbound = 0;
  v59 = v22;
  while ( (unsigned int)v23 < v22 )
  {
    v24 = (BYTE *)a2[2];
    v25 = 8 * v23;
    v60 = 8 * v23;
    v26 = *(unsigned __int16 **)&v24[8 * v23];
    if ( !v26 )
      goto LABEL_65;
    v27 = -1;
    do
      ++v27;
    while ( v26[v27] );
    if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 60LL) & 0x20) != 0 )
    {
      if ( !(unsigned int)IsTreeValueCanonical(v26) )
      {
        pv = 0;
        inited = MakeTreeValueCanonical(v26);
        if ( inited >= 0 )
        {
          v44 = -1;
          do
            ++v44;
          while ( v26[v44] );
          v45 = StringCchCopyW(v26, v44 + 1, (const unsigned __int16 *)pv);
          CoTaskMemFree(pv);
          inited = 0;
          if ( v45 != -2147024774 )
            inited = v45;
          v25 = v60;
        }
        goto LABEL_58;
      }
    }
    else
    {
      *_FindValueEnd(v26) = 0;
      ValueStart = _FindValueStart(v26);
      if ( ValueStart != v26 )
      {
        v42 = -1;
        do
          v43 = ValueStart[++v42] == 0;
        while ( !v43 );
        memmove_0(v26, ValueStart, 2 * v42 + 2);
      }
    }
    inited = 0;
LABEL_58:
    v29 = -1;
    do
      ++v29;
    while ( v26[v29] );
    if ( inited >= 0 && (*(_DWORD *)(*((_QWORD *)this + 5) + 60LL) & 0x800) == 0 )
    {
      v30 = *(_WORD **)((char *)a2[2] + v25);
      if ( !*v30 )
      {
        CoTaskMemFree(v30);
        *(_QWORD *)((char *)a2[2] + v25) = 0;
LABEL_99:
        v6 = 1;
        plUbound = 1;
        goto LABEL_65;
      }
    }
    if ( (_DWORD)v27 != (_DWORD)v29 )
      goto LABEL_99;
    v6 = plUbound;
LABEL_65:
    v22 = v59;
    v23 = (unsigned int)(v23 + 1);
    if ( inited < 0 )
    {
      plLbound = 0;
      goto LABEL_67;
    }
  }
  plLbound = 0;
  v46 = *((_DWORD *)a2 + 2);
  if ( v46 >= 0xA )
  {
    inited = CPropertyDescription::_FindDuplicateStringValuesUsingAlloc(
               this,
               (struct tagPROPVARIANT *)a2,
               (int (*)(unsigned __int16 **, int *))_MarkDuplicateStringCB,
               &plLbound);
  }
  else
  {
    v47 = 0;
    v48 = 1;
    do
    {
      if ( (unsigned int)v47 >= v46 )
        break;
      v49 = (const unsigned __int16 *)*((_QWORD *)a2[2] + v47);
      if ( v49 )
      {
        v50 = (unsigned int)(v47 + 1);
        while ( (unsigned int)v50 < v46 )
        {
          v51 = (const unsigned __int16 *)*((_QWORD *)a2[2] + v50);
          if ( v51 )
          {
            v52 = CPropertyDescription::_IsStringDuplicate(this, v49, v51);
            if ( v52 )
            {
              v43 = v52 == v49;
              v53 = (BYTE *)a2[2];
              if ( v43 )
              {
                v48 = _MarkDuplicateStringCB((unsigned __int16 **)&v53[8 * v47], &plLbound);
                break;
              }
              v48 = _MarkDuplicateStringCB((unsigned __int16 **)&v53[8 * v50], &plLbound);
              if ( (_DWORD)v50 == (_DWORD)v47 )
                break;
            }
          }
          v50 = (unsigned int)(v50 + 1);
          if ( !v48 )
            break;
        }
      }
      v47 = (unsigned int)(v47 + 1);
    }
    while ( v48 );
    v6 = plUbound;
    inited = 0;
  }
LABEL_67:
  v31 = *((_DWORD *)a2 + 2);
  v32 = 0;
  v14 = 0;
  if ( !v31 )
    goto LABEL_68;
  do
  {
    v35 = (BYTE *)a2[2];
    v36 = *(_QWORD *)&v35[8 * v14];
    if ( v36 )
    {
      *(_QWORD *)&v35[8 * v32] = v36;
      v32 = (unsigned int)(v32 + 1);
    }
    v14 = (unsigned int)(v14 + 1);
  }
  while ( (unsigned int)v14 < v31 );
  if ( (_DWORD)v32 )
  {
    *((_DWORD *)a2 + 2) = v32;
    v33 = v32 != v31;
  }
  else
  {
LABEL_68:
    PropVariantClear(a2);
    v33 = 1;
  }
  if ( v6 || plLbound || v33 )
    v6 = 1;
  if ( inited >= 0 )
  {
    if ( *(_WORD *)a2 )
    {
      pv = 0;
      inited = PropVariantToStringAlloc(a2, (PWSTR *)&pv);
      if ( inited >= 0 )
      {
        PropVariantClear(a2);
        a2[1] = pv;
        *(_WORD *)a2 = 31;
      }
    }
  }
LABEL_21:
  if ( inited >= 0 )
  {
LABEL_40:
    v18 = *(_WORD *)a2;
    v14 = 0;
    if ( !*(_WORD *)a2 )
    {
LABEL_41:
      if ( v6 || (_DWORD)v14 )
        inited = 262560;
      goto LABEL_22;
    }
    if ( v18 != v61[0] )
    {
      StringPropVariantCanonical = -2147418113;
      if ( v61[0] != 1 )
      {
LABEL_96:
        inited = StringPropVariantCanonical;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x9B8,
          (unsigned int)"onecoreuap\\shell\\propsys\\propdesc.cpp",
          (const char *)(unsigned int)StringPropVariantCanonical,
          v57);
        goto LABEL_22;
      }
    }
    plLbound = 0;
    if ( v18 == 31 )
    {
      StringPropVariantCanonical = CPropertyDescription::_MakeStringPropVariantCanonical(
                                     this,
                                     (struct tagPROPVARIANT *)a2,
                                     &plLbound);
    }
    else
    {
      if ( v18 != 4127 )
      {
        StringPropVariantCanonical = 0;
        v38 = 0;
        plUbound = 0;
LABEL_92:
        v39 = *((_QWORD *)this + 5);
        if ( *(_DWORD *)(v39 + 88) == 4 && !*(_DWORD *)(v39 + 168) )
        {
          StringPropVariantCanonical = CPropertyDescription::_MakeEnumPropVariantCanonical(
                                         this,
                                         (struct tagPROPVARIANT *)a2,
                                         &plUbound);
          v38 = plUbound;
        }
LABEL_93:
        if ( plLbound || (v14 = 0, v38) )
          v14 = 1;
        if ( StringPropVariantCanonical >= 0 )
          goto LABEL_41;
        goto LABEL_96;
      }
      StringPropVariantCanonical = CPropertyDescription::_MakeStringPropVariantVectorCanonical(
                                     this,
                                     (struct tagPROPVARIANT *)a2,
                                     &plLbound);
    }
    v38 = 0;
    plUbound = 0;
    if ( StringPropVariantCanonical < 0 )
      goto LABEL_93;
    goto LABEL_92;
  }
LABEL_22:
  if ( (byte_1800F1382 & 0x10) != 0 )
    McTemplateU0jq_EtwEventWriteTransfer(
      v14,
      ShellTraceId_PropertyDescription_CoerceToCanonicalValue_Stop,
      *((_QWORD *)this + 5) + 36LL,
      *(unsigned int *)(*((_QWORD *)this + 5) + 52LL));
  if ( inited < 0 )
    goto LABEL_16;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180008870  push    rbp
0x180008872  push    rbx
0x180008873  push    rsi
0x180008874  push    r14
0x180008876  lea     rbp, [rsp-3Fh]
0x18000887b  sub     rsp, 0A8h
0x180008882  mov     rax, cs:__security_cookie
0x180008889  xor     rax, rsp
0x18000888c  mov     [rbp+57h+var_38], rax
0x180008890  test    byte ptr [rcx+0B0h], 1
0x180008897  mov     rbx, rdx
0x18000889a  mov     r14, rcx
0x18000889d  jz      loc_18000898E
0x1800088a3  test    cs:byte_1800F1382, 10h
0x1800088aa  jnz     loc_180008E68
0x1800088b0  xor     eax, eax
0x1800088b2  lea     rdx, [rbp+57h+var_78]
0x1800088b6  mov     [rbp+57h+var_78], ax
0x1800088ba  mov     rcx, r14
0x1800088bd  mov     rax, [r14]
0x1800088c0  mov     rax, [rax+28h]
0x1800088c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088c9  movzx   edx, word ptr [rbx]
0x1800088cc  movzx   eax, [rbp+57h+var_78]
0x1800088d0  cmp     ax, dx
0x1800088d3  jz      loc_180008A4B
0x1800088d9  mov     [rsp+0C0h+arg_10], rdi
0x1800088e1  xor     eax, eax
0x1800088e3  mov     [rsp+0C0h+var_20], r12
0x1800088eb  mov     r12d, 1
0x1800088f1  mov     [rsp+0C0h+var_28], r13
0x1800088f9  mov     r13d, 101Fh
0x1800088ff  mov     [rsp+0C0h+var_30], r15
0x180008907  xor     r15d, r15d
0x18000890a  cmp     ax, dx
0x18000890d  jz      loc_180008B1A
0x180008913  cmp     r12w, dx
0x180008917  jz      loc_1800090D5
0x18000891d  mov     eax, edx
0x18000891f  cmp     edx, 8
0x180008922  jnz     loc_180008C6C
0x180008928  movzx   ecx, word ptr [rbx]; jumptable 0000000180008DCE cases 2-7,9-14,16-23,30,31,64-69,71-73
0x18000892b  xor     esi, esi
0x18000892d  cmp     ecx, 8
0x180008930  jnz     loc_180008B49
0x180008936  mov     rdi, [rbx+8]
0x18000893a  test    rdi, rdi
0x18000893d  jz      loc_180008B11
0x180008943  movzx   ecx, word ptr [rdi]; wch
0x180008946  test    cx, cx
0x180008949  jz      loc_180008ED6
0x18000894f  call    cs:__imp_IsCharSpaceW
0x180008955  test    eax, eax
0x180008957  jz      short loc_180008972
0x180008959  nop     dword ptr [rax+00000000h]
0x180008960  movzx   ecx, word ptr [rdi+2]; wch
0x180008964  add     rdi, 2
0x180008968  call    cs:__imp_IsCharSpaceW
0x18000896e  test    eax, eax
0x180008970  jnz     short loc_180008960
0x180008972  cmp     [rdi], si
0x180008975  jnz     loc_180008A8E
0x18000897b  mov     rcx, rbx; pvar
0x18000897e  call    cs:__imp_PropVariantClear
0x180008984  mov     esi, 401A0h
0x180008989  jmp     loc_180008B1C
0x18000898e  mov     esi, 8000FFFFh
0x180008993  mov     rcx, rbx; pvar
0x180008996  call    cs:__imp_PropVariantClear
0x18000899c  jmp     loc_180008A30
0x1800089a1  mov     rdi, [rbp+57h+pv]
0x1800089a5  xor     eax, eax
0x1800089a7  mov     [rbp+57h+var_58], rax
0x1800089ab  xorps   xmm0, xmm0
0x1800089ae  movups  xmmword ptr [rbp+57h+ppropvarDest], xmm0
0x1800089b2  test    rdi, rdi
0x1800089b5  jz      loc_180008F76
0x1800089bb  mov     edx, r13d
0x1800089be  lea     r8, [rbp+57h+ppropvarDest]
0x1800089c2  mov     rcx, rdi; unsigned __int16 *
0x1800089c5  call    InitPropVariantFromStringEx
0x1800089ca  mov     esi, eax
0x1800089cc  test    eax, eax
0x1800089ce  js      short loc_1800089EA
0x1800089d0  mov     rcx, rbx; pvar
0x1800089d3  call    cs:__imp_PropVariantClear
0x1800089d9  movups  xmm0, xmmword ptr [rbp+57h+ppropvarDest]
0x1800089dd  movsd   xmm1, [rbp+57h+var_58]
0x1800089e2  movups  xmmword ptr [rbx], xmm0
0x1800089e5  movsd   qword ptr [rbx+10h], xmm1
0x1800089ea  mov     rcx, rdi; pv
0x1800089ed  call    cs:__imp_CoTaskMemFree
0x1800089f3  test    esi, esi
0x1800089f5  jns     loc_180008B1C
0x1800089fb  mov     r13, [rsp+0C0h+var_28]
0x180008a03  mov     r12, [rsp+0C0h+var_20]
0x180008a0b  mov     rdi, [rsp+0C0h+arg_10]
0x180008a13  mov     r15, [rsp+0C0h+var_30]
0x180008a1b  test    cs:byte_1800F1382, 10h
0x180008a22  jnz     loc_180008F59
0x180008a28  test    esi, esi
0x180008a2a  js      loc_180008993
0x180008a30  mov     eax, esi
0x180008a32  mov     rcx, [rbp+57h+var_38]
0x180008a36  xor     rcx, rsp; StackCookie
0x180008a39  call    __security_check_cookie
0x180008a3e  add     rsp, 0A8h
0x180008a45  pop     r14
0x180008a47  pop     rsi
0x180008a48  pop     rbx
0x180008a49  pop     rbp
0x180008a4a  retn
0x180008a4b  sub     ax, 13h
0x180008a4f  mov     ecx, 0FFFDh
0x180008a54  test    cx, ax
0x180008a57  jnz     loc_1800088D9
0x180008a5d  mov     rax, [r14+28h]
0x180008a61  cmp     dword ptr [rax+58h], 4
0x180008a65  jz      loc_1800088D9
0x180008a6b  xor     esi, esi
0x180008a6d  jmp     short loc_180008A1B
0x180008a6f  cmp     dword ptr [rbx+0Ch], 0C9h
0x180008a76  jz      loc_1800090DD
0x180008a7c  jb      loc_1800090EA
0x180008a82  xor     eax, eax
0x180008a84  mov     esi, eax
0x180008a86  test    eax, eax
0x180008a88  jnz     loc_1800090BA
0x180008a8e  cmp     [rbp+57h+var_78], 1Fh
0x180008a93  jz      loc_180008B6E
0x180008a99  mov     rcx, rbx; struct tagPROPVARIANT *
0x180008a9c  call    ?IsPropVariantValidForVista@@YAHAEBUtagPROPVARIANT@@@Z; IsPropVariantValidForVista(tagPROPVARIANT const &)
0x180008aa1  test    eax, eax
0x180008aa3  jz      loc_180008F06
0x180008aa9  movzx   eax, [rbp+57h+var_78]
0x180008aad  cmp     ax, r12w
0x180008ab1  jz      short loc_180008B1A
0x180008ab3  movzx   ecx, word ptr [rbx]
0x180008ab6  test    cx, cx
0x180008ab9  jz      short loc_180008B1A
0x180008abb  cmp     cx, ax
0x180008abe  jz      short loc_180008B1A
0x180008ac0  cmp     ax, r13w
0x180008ac4  jz      loc_180008CF7
0x180008aca  movzx   r9d, [rbp+57h+var_78]; vt
0x180008acf  lea     rcx, [rbp+57h+ppropvarDest]; ppropvarDest
0x180008ad3  xorps   xmm0, xmm0
0x180008ad6  xor     eax, eax
0x180008ad8  xor     r8d, r8d; flags
0x180008adb  mov     [rbp+57h+var_58], rax
0x180008adf  mov     rdx, rbx; propvarSrc
0x180008ae2  movups  xmmword ptr [rbp+57h+ppropvarDest], xmm0
0x180008ae6  call    PropVariantChangeType
0x180008aeb  mov     esi, eax
0x180008aed  test    eax, eax
0x180008aef  js      loc_1800091B4
0x180008af5  mov     rcx, rbx; pvar
0x180008af8  call    cs:__imp_PropVariantClear
0x180008afe  movups  xmm0, xmmword ptr [rbp+57h+ppropvarDest]
0x180008b02  movsd   xmm1, [rbp+57h+var_58]
0x180008b07  movups  xmmword ptr [rbx], xmm0
0x180008b0a  movsd   qword ptr [rbx+10h], xmm1
0x180008b0f  jmp     short loc_180008B1C
0x180008b11  mov     rcx, rbx; pvar
0x180008b14  call    cs:__imp_PropVariantClear
0x180008b1a  xor     esi, esi
0x180008b1c  movzx   edx, word ptr [rbx]
0x180008b1f  xor     ecx, ecx
0x180008b21  test    dx, dx
0x180008b24  jnz     loc_180008D20
0x180008b2a  test    esi, esi
0x180008b2c  js      loc_1800089FB
0x180008b32  test    r15d, r15d
0x180008b35  jnz     short loc_180008B3F
0x180008b37  test    ecx, ecx
0x180008b39  jz      loc_1800089FB
0x180008b3f  mov     esi, 401A0h
0x180008b44  jmp     loc_1800089FB
0x180008b49  sub     ecx, r12d
0x180008b4c  jz      short loc_180008B11
0x180008b4e  sub     ecx, 1Dh
0x180008b51  jz      loc_1800090F2
0x180008b57  sub     ecx, r12d
0x180008b5a  jz      loc_180008936
0x180008b60  cmp     ecx, 21h ; '!'
0x180008b63  jnz     loc_180008A8E
0x180008b69  jmp     loc_180008A6F
0x180008b6e  cmp     [rbx], r13w
0x180008b72  jnz     loc_180008A99
0x180008b78  mov     eax, [rbx+8]
0x180008b7b  xor     esi, esi
0x180008b7d  xor     r13d, r13d
0x180008b80  mov     [rbp+57h+plUbound], r15d
0x180008b84  mov     [rbp+57h+var_88], eax
0x180008b87  cmp     r13d, eax
0x180008b8a  jnb     loc_180008FF4
0x180008b90  mov     rax, [rbx+10h]
0x180008b94  lea     rdi, ds:0[r13*8]
0x180008b9c  mov     [rbp+57h+var_80], rdi
0x180008ba0  mov     r12, [rdi+rax]
0x180008ba4  test    r12, r12
0x180008ba7  jz      loc_180008C36
0x180008bad  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180008bb4  inc     r15
0x180008bb7  cmp     word ptr [r12+r15*2], 0
0x180008bbd  jnz     short loc_180008BB4
0x180008bbf  mov     rax, [r14+28h]
0x180008bc3  mov     rcx, r12; unsigned __int16 *
0x180008bc6  test    byte ptr [rax+3Ch], 20h
0x180008bca  jnz     loc_180008F85
0x180008bd0  call    ?_FindValueEnd@@YAPEAGPEAG@Z; _FindValueEnd(ushort *)
0x180008bd5  xor     ecx, ecx
0x180008bd7  mov     [rax], cx
0x180008bda  mov     rcx, r12; unsigned __int16 *
0x180008bdd  call    ?_FindValueStart@@YAPEAGPEAG@Z; _FindValueStart(ushort *)
0x180008be2  cmp     rax, r12
0x180008be5  jnz     loc_180008F10
0x180008beb  xor     esi, esi
0x180008bed  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008bf4  inc     rax
0x180008bf7  cmp     word ptr [r12+rax*2], 0
0x180008bfd  jnz     short loc_180008BF4
0x180008bff  xor     edx, edx
0x180008c01  cmp     r15d, eax
0x180008c04  setnz   dl
0x180008c07  test    esi, esi
0x180008c09  js      short loc_180008C2A
0x180008c0b  mov     rax, [r14+28h]
0x180008c0f  test    dword ptr [rax+3Ch], 800h
0x180008c16  jnz     short loc_180008C2A
0x180008c18  mov     rax, [rbx+10h]
0x180008c1c  mov     rcx, [rdi+rax]; pv
0x180008c20  cmp     word ptr [rcx], 0
0x180008c24  jz      loc_180009136
0x180008c2a  test    edx, edx
0x180008c2c  jnz     loc_180008DD0
0x180008c32  mov     r15d, [rbp+57h+plUbound]
0x180008c36  mov     r12d, 1
0x180008c3c  mov     eax, [rbp+57h+var_88]
0x180008c3f  inc     r13d
0x180008c42  test    esi, esi
0x180008c44  jns     loc_180008B87
0x180008c4a  mov     [rbp+57h+plLbound], 0
0x180008c51  mov     r10d, [rbx+8]
0x180008c55  xor     edx, edx
0x180008c57  xor     ecx, ecx
0x180008c59  test    r10d, r10d
0x180008c5c  jnz     short loc_180008CA0
0x180008c5e  mov     rcx, rbx; pvar
0x180008c61  call    cs:__imp_PropVariantClear
0x180008c67  mov     eax, r12d
0x180008c6a  jmp     short loc_180008CC9
0x180008c6c  cmp     eax, 0FFFh
0x180008c71  jbe     loc_180008D9F
0x180008c77  bt      dx, 0Eh; jumptable 0000000180008DCE default case, cases 8,15,24-29,32-63,70
0x180008c7c  jb      loc_180008928; jumptable 0000000180008DCE cases 2-7,9-14,16-23,30,31,64-69,71-73
0x180008c82  bt      dx, 0Ch
0x180008c87  jnb     loc_180008DE2
0x180008c8d  mov     eax, [rbx+8]
0x180008c90  test    eax, eax
0x180008c92  jnz     loc_180008928; jumptable 0000000180008DCE cases 2-7,9-14,16-23,30,31,64-69,71-73
0x180008c98  jmp     loc_180008B11
0x180008ca0  mov     r8, [rbx+10h]
0x180008ca4  mov     r9, [r8+rcx*8]
0x180008ca8  test    r9, r9
0x180008cab  jz      short loc_180008CB3
0x180008cad  mov     [r8+rdx*8], r9
0x180008cb1  inc     edx
0x180008cb3  inc     ecx
0x180008cb5  cmp     ecx, r10d
0x180008cb8  jb      short loc_180008CA0
0x180008cba  test    edx, edx
0x180008cbc  jz      short loc_180008C5E
0x180008cbe  xor     eax, eax
0x180008cc0  mov     [rbx+8], edx
0x180008cc3  cmp     edx, r10d
0x180008cc6  setnz   al
0x180008cc9  test    r15d, r15d
0x180008ccc  jnz     loc_180008EEA
0x180008cd2  cmp     [rbp+57h+plLbound], r15d
0x180008cd6  jnz     loc_180008EEA
0x180008cdc  test    eax, eax
0x180008cde  jnz     loc_180008EEA
0x180008ce4  test    esi, esi
0x180008ce6  jns     loc_18000915E
0x180008cec  mov     r13d, 101Fh
0x180008cf2  jmp     loc_1800089F3
0x180008cf7  cmp     cx, 8
0x180008cfb  jnz     loc_1800091A1
0x180008d01  lea     rdx, [rbp+57h+pv]; ppszOut
0x180008d05  mov     [rbp+57h+pv], r15
0x180008d09  mov     rcx, rbx; propvar
0x180008d0c  call    PropVariantToStringAlloc
0x180008d11  mov     esi, eax
0x180008d13  test    eax, eax
0x180008d15  js      loc_1800089FB
0x180008d1b  jmp     loc_1800089A1
0x180008d20  movzx   ecx, [rbp+57h+var_78]
0x180008d24  cmp     dx, cx
0x180008d27  jnz     loc_180008F45
  ... truncated ...
```
