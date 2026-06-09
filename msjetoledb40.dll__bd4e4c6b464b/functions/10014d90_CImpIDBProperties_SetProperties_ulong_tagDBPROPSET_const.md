# CImpIDBProperties::SetProperties(ulong,tagDBPROPSET * const)

- ea: `0x10014d90`
- end: `0x10015294`
- name: `?SetProperties@CImpIDBProperties@@UAGJKQAUtagDBPROPSET@@@Z`
- size: `1284`
- prototype: `int(CImpIDBProperties *__hidden this, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1000ba90`
- `0x10014a70`
- `0x10014d90`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001f2d0`
- `0x1001ffe0`
- `0x100207d0`
- `0x1004b910`
- `0x1004ce5d`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10015279`
- `KERNEL32!LeaveCriticalSection` at `0x10015279`
- `KERNEL32!EnterCriticalSection` at `0x10014ddd`
- `KERNEL32!EnterCriticalSection` at `0x10014ddd`
- `OLEAUT32!__imp__VariantCopy@8` at `0x10015057`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100150c9`
- `OLEAUT32!__imp__VariantCopy@8` at `0x10015057`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100150c9`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10014dca`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10014dca`

## pseudocode

```c
int __stdcall CImpIDBProperties::SetProperties(CImpIDBProperties *this, unsigned int a2, struct tagDBPROPSET *const a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  int v4; // edi
  unsigned int v5; // ecx
  struct tagDBPROPSET *v6; // edi
  unsigned int v7; // eax
  int v8; // eax
  struct tagDBPROPSET *v9; // ecx
  GUID *p_guidPropertySet; // edi
  const GUID *v11; // ecx
  GUID *v12; // edx
  bool v13; // cf
  int *v14; // ecx
  GUID *v15; // edx
  int v16; // ecx
  int v17; // ecx
  int v18; // eax
  bool v19; // zf
  int v20; // ecx
  struct tagDBPROPSET *v21; // edi
  ULONG i; // edx
  int v23; // ecx
  const GUID *v24; // ecx
  GUID *v25; // edx
  char *v26; // edi
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  JoltProperties *v29; // edi
  VARIANTARG *v30; // eax
  JoltProperties *v31; // edi
  VARIANTARG *v32; // eax
  VARIANTARG *v33; // eax
  VARIANTARG *v34; // eax
  unsigned int v35; // ecx
  signed int v36; // eax
  signed int v37; // ecx
  int v38; // eax
  const GUID *v39; // ecx
  unsigned int v40; // edx
  char *v41; // ecx
  struct CSettableProperties *v43; // [esp-8h] [ebp-54h]
  struct CDBSession *v44; // [esp-4h] [ebp-50h]
  const struct _GUID *v45; // [esp+0h] [ebp-4Ch]
  int *v46; // [esp+4h] [ebp-48h]
  unsigned int v47; // [esp+10h] [ebp-3Ch] BYREF
  unsigned int v48; // [esp+14h] [ebp-38h] BYREF
  unsigned int v49; // [esp+18h] [ebp-34h] BYREF
  unsigned int v50; // [esp+1Ch] [ebp-30h] BYREF
  unsigned int v51; // [esp+20h] [ebp-2Ch]
  VARIANTARG *pvargSrc; // [esp+24h] [ebp-28h]
  JoltProperties *v53; // [esp+28h] [ebp-24h]
  JoltProperties *v54; // [esp+2Ch] [ebp-20h]
  HRESULT v55; // [esp+30h] [ebp-1Ch]
  struct tagDBPROPSET *v56; // [esp+34h] [ebp-18h]
  int v57; // [esp+38h] [ebp-14h]
  int v58; // [esp+3Ch] [ebp-10h]
  int v59; // [esp+48h] [ebp-4h]

  v58 = 0;
  v55 = 0;
  v57 = 0;
  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v3);
  v59 = 0;
  if ( !a2 )
  {
    v4 = 0;
    goto LABEL_77;
  }
  if ( !a3 )
  {
LABEL_3:
    v4 = -2147024809;
    CExtError::SendHRtoOLEAuto((int)&IID_IDBProperties, 0, v45, (int)v46);
    goto LABEL_77;
  }
  v5 = 0;
  v6 = a3;
  do
  {
    if ( a3[v5].cProperties && !a3[v5].rgProperties )
      goto LABEL_3;
    ++v5;
  }
  while ( v5 < a2 );
  v7 = 0;
  v51 = 0;
  while ( 2 )
  {
    pvargSrc = (VARIANTARG *)12;
    v8 = v7;
    v9 = &v6[v8];
    p_guidPropertySet = &v6[v8].guidPropertySet;
    v56 = v9;
    v11 = &DBPROPSET_DBINIT;
    v12 = p_guidPropertySet;
    while ( v11->Data1 == v12->Data1 )
    {
      v11 = (const GUID *)((char *)v11 + 4);
      v12 = (GUID *)((char *)v12 + 4);
      v13 = (unsigned int)pvargSrc < 4;
      pvargSrc = (VARIANTARG *)((char *)pvargSrc - 4);
      if ( v13 )
      {
LABEL_17:
        v16 = *((_DWORD *)this + 2);
        if ( *(_DWORD *)(v16 + 128) )
        {
          v21 = v56;
          for ( i = 0; i < v21->cProperties; v21->rgProperties[v23].colid = DB_NULLID )
          {
            v23 = i++;
            v21->rgProperties[v23].dwStatus = 6;
          }
        }
        else
        {
          v17 = CSettableProperties::SetProperties((CSettableProperties *)(v16 + 152), 1u, v56, 0);
          if ( v17 >= 0 )
          {
            v18 = v57;
            v19 = v17 == 265946;
            v20 = 1;
            if ( v19 )
              v18 = 1;
            v58 = 1;
            v57 = v18;
            goto LABEL_61;
          }
        }
LABEL_59:
        v57 = 1;
        goto LABEL_60;
      }
    }
    v14 = dword_10004BC0;
    pvargSrc = (VARIANTARG *)12;
    v15 = p_guidPropertySet;
    while ( *v14 == v15->Data1 )
    {
      ++v14;
      v15 = (GUID *)((char *)v15 + 4);
      v13 = (unsigned int)pvargSrc < 4;
      pvargSrc = (VARIANTARG *)((char *)pvargSrc - 4);
      if ( v13 )
        goto LABEL_17;
    }
    v24 = &DBPROPSET_DATASOURCEINFO;
    pvargSrc = (VARIANTARG *)12;
    v25 = p_guidPropertySet;
    do
    {
      if ( v24->Data1 != v25->Data1 )
      {
        v39 = &DBPROPSET_DATASOURCE;
        v40 = 12;
        do
        {
          if ( v39->Data1 != p_guidPropertySet->Data1 )
            goto LABEL_58;
          v39 = (const GUID *)((char *)v39 + 4);
          p_guidPropertySet = (GUID *)((char *)p_guidPropertySet + 4);
          v13 = v40 < 4;
          v40 -= 4;
        }
        while ( !v13 );
        v41 = (char *)operator new(0x28u);
        v53 = (JoltProperties *)v41;
        if ( !v41 )
          goto LABEL_64;
        *(_DWORD *)v41 = &JoltProperties::`vftable';
        *((_DWORD *)v41 + 1) = 0;
        *((_DWORD *)v41 + 2) = 0;
        *((_DWORD *)v41 + 3) = 0;
        *((_DWORD *)v41 + 4) = 0;
        *((_DWORD *)v41 + 9) = 0;
        *(GUID *)(v41 + 20) = DBPROPSET_ROWSET;
        if ( !*(_DWORD *)(*((_DWORD *)this + 2) + 128) )
        {
LABEL_58:
          SetPropSetNotSupported(0, (unsigned int)v45, v46);
          goto LABEL_59;
        }
        v4 = (*(int (__thiscall **)(JoltProperties *, const struct DBInfoProps *const *, int, int, unsigned int, _DWORD, _DWORD, _DWORD))(*(_DWORD *)v41 + 4))(
               v53,
               &rgDBInfoProps,
               7,
               1,
               DBPROPSET_DATASOURCE.Data1,
               *(_DWORD *)&DBPROPSET_DATASOURCE.Data2,
               *(_DWORD *)DBPROPSET_DATASOURCE.Data4,
               *(_DWORD *)&DBPROPSET_DATASOURCE.Data4[4]);
        v55 = v4;
        if ( v4 >= 0 )
        {
          v31 = v53;
          goto LABEL_46;
        }
        JoltProperties::`scalar deleting destructor'(v53, v35);
        goto LABEL_68;
      }
      v24 = (const GUID *)((char *)v24 + 4);
      v25 = (GUID *)((char *)v25 + 4);
      v13 = (unsigned int)pvargSrc < 4;
      pvargSrc = (VARIANTARG *)((char *)pvargSrc - 4);
    }
    while ( !v13 );
    v26 = (char *)operator new(0x28u);
    v54 = (JoltProperties *)v26;
    if ( !v26 )
    {
LABEL_64:
      v4 = -2147024882;
      goto LABEL_68;
    }
    *(_DWORD *)v26 = &JoltProperties::`vftable';
    *((_DWORD *)v26 + 1) = 0;
    *((_DWORD *)v26 + 2) = 0;
    *((_DWORD *)v26 + 3) = 0;
    *((_DWORD *)v26 + 4) = 0;
    *((_DWORD *)v26 + 9) = 0;
    *(GUID *)(v26 + 20) = DBPROPSET_ROWSET;
    if ( !*(_DWORD *)(*((_DWORD *)this + 2) + 128) )
    {
      SetPropSetNotSupported(0, (unsigned int)v45, v46);
      v57 = 1;
      JoltProperties::`scalar deleting destructor'((JoltProperties *)v26, v27);
      goto LABEL_60;
    }
    v4 = (*(int (__thiscall **)(JoltProperties *, const struct DBInfoProps *const *, int, int, unsigned int, _DWORD, _DWORD, _DWORD))(*(_DWORD *)v26 + 4))(
           v54,
           &rgDBInfoProps,
           8,
           49,
           DBPROPSET_DATASOURCEINFO.Data1,
           *(_DWORD *)&DBPROPSET_DATASOURCEINFO.Data2,
           *(_DWORD *)DBPROPSET_DATASOURCEINFO.Data4,
           *(_DWORD *)&DBPROPSET_DATASOURCEINFO.Data4[4]);
    if ( v4 < 0 )
    {
      JoltProperties::`scalar deleting destructor'(v54, v28);
LABEL_68:
      v20 = v58;
      goto LABEL_69;
    }
    v29 = *(JoltProperties **)(*((_DWORD *)this + 2) + 160);
    if ( JoltProperties::BinarySearch(v29, 0x3Bu, &v50) < 0 )
      v30 = 0;
    else
      v30 = (VARIANTARG *)(*((_DWORD *)v29 + 4) + 48 * v50);
    v31 = v54;
    pvargSrc = v30 + 1;
    if ( JoltProperties::BinarySearch(v54, 0x26u, &v49) < 0 )
      v32 = 0;
    else
      v32 = (VARIANTARG *)(*((_DWORD *)v31 + 4) + 48 * v49);
    v55 = VariantCopy(v32 + 1, pvargSrc);
    if ( v55 < 0
      || ((pvargSrc = *(VARIANTARG **)(*((_DWORD *)this + 2) + 160),
           JoltProperties::BinarySearch((JoltProperties *)pvargSrc, 0xCu, &v48) < 0)
        ? (v33 = 0)
        : (v33 = (VARIANTARG *)(*(_DWORD *)&pvargSrc[1].vt + 48 * v48)),
          (pvargSrc = v33 + 1, JoltProperties::BinarySearch(v31, 0x76u, &v47) < 0)
        ? (v34 = 0)
        : (v34 = (VARIANTARG *)(*((_DWORD *)v31 + 4) + 48 * v47)),
          v55 = VariantCopy(v34 + 1, pvargSrc),
          v55 < 0) )
    {
      v4 = v55;
      goto LABEL_68;
    }
LABEL_46:
    v36 = JoltProperties::SetProperties(v31, v35, v56, v43, v44);
    v37 = v36;
    if ( v36 >= 0 )
    {
      v38 = v57;
      if ( v37 == 265946 )
        v38 = 1;
      v58 = 1;
      v57 = v38;
      JoltProperties::`scalar deleting destructor'(v31, 1u);
    }
    else
    {
      v57 = 1;
      JoltProperties::`scalar deleting destructor'(v31, v36);
    }
LABEL_60:
    v20 = v58;
LABEL_61:
    v7 = v51 + 1;
    v51 = v7;
    if ( v7 < a2 )
    {
      v6 = a3;
      continue;
    }
    break;
  }
  v4 = v55;
LABEL_69:
  if ( v57 == 1 )
  {
    if ( v20 == 1 )
    {
      v4 = 265946;
    }
    else
    {
      v4 = -2147217887;
      CExtError::SendHRtoOLEAuto((int)&IID_IDBProperties, 0, v45, (int)v46);
    }
  }
  else if ( v4 < 0 && v4 != -2147024882 )
  {
    CExtError::SendHRtoOLEAuto((int)&IID_IDBProperties, 0, v45, (int)v46);
  }
LABEL_77:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v4;
}

```

## disassembly

```asm
0x10014d90  mov     edi, edi
0x10014d92  push    ebp
0x10014d93  mov     ebp, esp
0x10014d95  push    0FFFFFFFFh
0x10014d97  push    offset ?SetProperties@CImpIDBProperties@@UAGJKQAUtagDBPROPSET@@@Z_SEH
0x10014d9c  mov     eax, large fs:0
0x10014da2  push    eax
0x10014da3  sub     esp, 34h
0x10014da6  push    esi
0x10014da7  push    edi; int
0x10014da8  mov     eax, ___security_cookie
0x10014dad  xor     eax, ebp
0x10014daf  push    eax; struct _GUID *
0x10014db0  lea     eax, [ebp+var_C]
0x10014db3  mov     large fs:0, eax
0x10014db9  xor     eax, eax
0x10014dbb  xor     ecx, ecx
0x10014dbd  push    eax; perrinfo
0x10014dbe  xor     edi, edi
0x10014dc0  mov     [ebp+var_10], ecx
0x10014dc3  push    eax; dwReserved
0x10014dc4  mov     [ebp+var_1C], edi
0x10014dc7  mov     [ebp+var_14], eax
0x10014dca  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10014dd0  mov     esi, [ebp+this]
0x10014dd3  mov     esi, [esi+8]
0x10014dd6  add     esi, 64h ; 'd'
0x10014dd9  push    esi; lpCriticalSection
0x10014dda  mov     [ebp+var_40], esi
0x10014ddd  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10014de3  mov     edx, [ebp+arg_4]
0x10014de6  mov     [ebp+var_4], edi
0x10014de9  test    edx, edx
0x10014deb  jz      loc_10015272
0x10014df1  cmp     [ebp+arg_8], edi
0x10014df4  jnz     short loc_10014E0E
0x10014df6  push    0; int
0x10014df8  mov     edi, 80070057h
0x10014dfd  push    offset _IID_IDBProperties; int
0x10014e02  mov     edx, edi
0x10014e04  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10014e09  jmp     loc_10015274
0x10014e0e  xor     ecx, ecx
0x10014e10  test    edx, edx
0x10014e12  jz      loc_10015274
0x10014e18  mov     edi, [ebp+arg_8]
0x10014e1b  nop     dword ptr [eax+eax+00h]
0x10014e20  lea     eax, [ecx+ecx*2]
0x10014e23  cmp     dword ptr [edi+eax*8+4], 0
0x10014e28  jz      short loc_10014E30
0x10014e2a  cmp     dword ptr [edi+eax*8], 0
0x10014e2e  jz      short loc_10014DF6
0x10014e30  inc     ecx
0x10014e31  cmp     ecx, edx
0x10014e33  jb      short loc_10014E20
0x10014e35  xor     eax, eax
0x10014e37  mov     [ebp+var_2C], eax
0x10014e3a  nop     word ptr [eax+eax+00h]
0x10014e40  lea     eax, [eax+eax*2]
0x10014e43  mov     [ebp+pvargSrc], 0Ch
0x10014e4a  shl     eax, 3
0x10014e4d  lea     ecx, [eax+edi]
0x10014e50  add     edi, 8
0x10014e53  add     edi, eax
0x10014e55  mov     [ebp+var_18], ecx
0x10014e58  mov     ecx, offset _DBPROPSET_DBINIT
0x10014e5d  mov     edx, edi
0x10014e5f  nop
0x10014e60  mov     eax, [ecx]
0x10014e62  cmp     eax, [edx]
0x10014e64  jnz     short loc_10014E74
0x10014e66  add     ecx, 4
0x10014e69  add     edx, 4
0x10014e6c  sub     [ebp+pvargSrc], 4
0x10014e70  jnb     short loc_10014E60
0x10014e72  jmp     short loc_10014E98
0x10014e74  mov     ecx, offset dword_10004BC0
0x10014e79  mov     [ebp+pvargSrc], 0Ch
0x10014e80  mov     edx, edi
0x10014e82  mov     eax, [ecx]
0x10014e84  cmp     eax, [edx]
0x10014e86  jnz     loc_10014F24
0x10014e8c  add     ecx, 4
0x10014e8f  add     edx, 4
0x10014e92  sub     [ebp+pvargSrc], 4
0x10014e96  jnb     short loc_10014E82
0x10014e98  mov     eax, [ebp+this]
0x10014e9b  mov     ecx, [eax+8]
0x10014e9e  cmp     dword ptr [ecx+80h], 0
0x10014ea5  jnz     short loc_10014EDF
0x10014ea7  push    0; struct CDBSession *
0x10014ea9  push    [ebp+var_18]; struct tagDBPROPSET *
0x10014eac  add     ecx, 98h; this
0x10014eb2  push    1; unsigned int
0x10014eb4  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x10014eb9  mov     ecx, eax
0x10014ebb  test    ecx, ecx
0x10014ebd  js      loc_100151E9
0x10014ec3  mov     eax, [ebp+var_14]
0x10014ec6  cmp     ecx, 40EDAh
0x10014ecc  mov     ecx, 1
0x10014ed1  cmovz   eax, ecx
0x10014ed4  mov     [ebp+var_10], ecx
0x10014ed7  mov     [ebp+var_14], eax
0x10014eda  jmp     loc_100151F3
0x10014edf  mov     edi, [ebp+var_18]
0x10014ee2  xor     edx, edx
0x10014ee4  cmp     [edi+4], edx
0x10014ee7  jbe     loc_100151E9
0x10014eed  nop     dword ptr [eax]
0x10014ef0  mov     eax, [edi]
0x10014ef2  imul    ecx, edx, 34h ; '4'
0x10014ef5  inc     edx
0x10014ef6  mov     dword ptr [ecx+eax+8], 6
0x10014efe  mov     eax, [edi]
0x10014f00  movups  xmm0, xmmword ptr ds:_DB_NULLID.uGuid
0x10014f07  movups  xmmword ptr [ecx+eax+0Ch], xmm0
0x10014f0c  movq    xmm0, qword ptr ds:_DB_NULLID.eKind
0x10014f14  movq    qword ptr [ecx+eax+1Ch], xmm0
0x10014f1a  cmp     edx, [edi+4]
0x10014f1d  jb      short loc_10014EF0
0x10014f1f  jmp     loc_100151E9
0x10014f24  mov     ecx, offset _DBPROPSET_DATASOURCEINFO
0x10014f29  mov     [ebp+pvargSrc], 0Ch
0x10014f30  mov     edx, edi
0x10014f32  mov     eax, [ecx]
0x10014f34  cmp     eax, [edx]
0x10014f36  jnz     loc_10015126
0x10014f3c  add     ecx, 4
0x10014f3f  add     edx, 4
0x10014f42  sub     [ebp+pvargSrc], 4
0x10014f46  jnb     short loc_10014F32
0x10014f48  push    28h ; '('; Size
0x10014f4a  call    ??2@YAPAXI@Z; operator new(uint)
0x10014f4f  mov     edi, eax
0x10014f51  add     esp, 4
0x10014f54  mov     [ebp+var_20], edi
0x10014f57  test    edi, edi
0x10014f59  jz      loc_10015212
0x10014f5f  mov     eax, [ebp+this]
0x10014f62  mov     dword ptr [edi], offset ??_7JoltProperties@@6B@; const JoltProperties::`vftable'
0x10014f68  mov     dword ptr [edi+4], 0
0x10014f6f  mov     dword ptr [edi+8], 0
0x10014f76  mov     dword ptr [edi+0Ch], 0
0x10014f7d  mov     dword ptr [edi+10h], 0
0x10014f84  movups  xmm0, xmmword ptr ds:_DBPROPSET_ROWSET.Data1
0x10014f8b  mov     dword ptr [edi+24h], 0
0x10014f92  movups  xmmword ptr [edi+14h], xmm0
0x10014f96  mov     eax, [eax+8]
0x10014f99  cmp     dword ptr [eax+80h], 0
0x10014fa0  jnz     short loc_10014FC5
0x10014fa2  mov     ecx, [ebp+var_18]
0x10014fa5  mov     edx, 1
0x10014faa  push    0; struct tagDBPROPSET *
0x10014fac  call    ?SetPropSetNotSupported@@YGJPAUtagDBPROPSET@@KPAJ@Z; SetPropSetNotSupported(tagDBPROPSET *,ulong,long *)
0x10014fb1  push    ecx; unsigned int
0x10014fb2  mov     ecx, edi; this
0x10014fb4  mov     [ebp+var_14], 1
0x10014fbb  call    ??_GJoltProperties@@QAEPAXI@Z; JoltProperties::`scalar deleting destructor'(uint)
0x10014fc0  jmp     loc_100151F0
0x10014fc5  mov     eax, [edi]
0x10014fc7  sub     esp, 10h
0x10014fca  movups  xmm0, xmmword ptr ds:_DBPROPSET_DATASOURCEINFO.Data1
0x10014fd1  mov     edi, [eax+4]
0x10014fd4  mov     eax, esp
0x10014fd6  push    31h ; '1'
0x10014fd8  push    8
0x10014fda  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; DBInfoProps const * const rgDBInfoProps
0x10014fdf  mov     ecx, edi
0x10014fe1  movups  xmmword ptr [eax], xmm0
0x10014fe4  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10014fea  mov     ecx, [ebp+var_20]
0x10014fed  call    edi
0x10014fef  mov     edi, eax
0x10014ff1  test    edi, edi
0x10014ff3  js      loc_10015207
0x10014ff9  mov     eax, [ebp+this]
0x10014ffc  mov     eax, [eax+8]
0x10014fff  mov     edi, [eax+0A0h]
0x10015005  lea     eax, [ebp+var_30]
0x10015008  push    eax; unsigned int *
0x10015009  push    3Bh ; ';'; unsigned int
0x1001500b  mov     ecx, edi; this
0x1001500d  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10015012  test    eax, eax
0x10015014  js      short loc_10015024
0x10015016  mov     eax, [ebp+var_30]
0x10015019  lea     eax, [eax+eax*2]
0x1001501c  shl     eax, 4
0x1001501f  add     eax, [edi+10h]
0x10015022  jmp     short loc_10015026
0x10015024  xor     eax, eax
0x10015026  mov     edi, [ebp+var_20]
0x10015029  add     eax, 10h
0x1001502c  mov     [ebp+pvargSrc], eax
0x1001502f  mov     ecx, edi; this
0x10015031  lea     eax, [ebp+var_34]
0x10015034  push    eax; unsigned int *
0x10015035  push    26h ; '&'; unsigned int
0x10015037  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1001503c  test    eax, eax
0x1001503e  js      short loc_1001504E
0x10015040  mov     eax, [ebp+var_34]
0x10015043  lea     eax, [eax+eax*2]
0x10015046  shl     eax, 4
0x10015049  add     eax, [edi+10h]
0x1001504c  jmp     short loc_10015050
0x1001504e  xor     eax, eax
0x10015050  push    [ebp+pvargSrc]; pvargSrc
0x10015053  add     eax, 10h
0x10015056  push    eax; pvargDest
0x10015057  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1001505d  mov     [ebp+var_1C], eax
0x10015060  test    eax, eax
0x10015062  js      loc_10015229
0x10015068  mov     eax, [ebp+this]
0x1001506b  lea     ecx, [ebp+var_38]
0x1001506e  push    ecx; unsigned int *
0x1001506f  push    0Ch; unsigned int
0x10015071  mov     eax, [eax+8]
0x10015074  mov     eax, [eax+0A0h]
0x1001507a  mov     ecx, eax; this
0x1001507c  mov     [ebp+pvargSrc], eax
0x1001507f  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10015084  test    eax, eax
0x10015086  js      short loc_10015099
0x10015088  mov     eax, [ebp+var_38]
0x1001508b  mov     ecx, [ebp+pvargSrc]
0x1001508e  lea     eax, [eax+eax*2]
0x10015091  shl     eax, 4
0x10015094  add     eax, [ecx+10h]
0x10015097  jmp     short loc_1001509B
0x10015099  xor     eax, eax
0x1001509b  add     eax, 10h
0x1001509e  mov     ecx, edi; this
0x100150a0  mov     [ebp+pvargSrc], eax
0x100150a3  lea     eax, [ebp+var_3C]
0x100150a6  push    eax; unsigned int *
0x100150a7  push    76h ; 'v'; unsigned int
0x100150a9  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100150ae  test    eax, eax
0x100150b0  js      short loc_100150C0
0x100150b2  mov     eax, [ebp+var_3C]
0x100150b5  lea     eax, [eax+eax*2]
0x100150b8  shl     eax, 4
0x100150bb  add     eax, [edi+10h]
0x100150be  jmp     short loc_100150C2
0x100150c0  xor     eax, eax
0x100150c2  push    [ebp+pvargSrc]; struct CDBSession *
0x100150c5  add     eax, 10h
0x100150c8  push    eax; struct CSettableProperties *
0x100150c9  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x100150cf  mov     [ebp+var_1C], eax
0x100150d2  test    eax, eax
0x100150d4  js      loc_10015229
0x100150da  sub     esp, 8
0x100150dd  push    [ebp+var_18]; struct tagDBPROPSET *
0x100150e0  push    ecx; unsigned int
0x100150e1  mov     ecx, edi; this
0x100150e3  call    ?SetProperties@JoltProperties@@QAEJKPAUtagDBPROPSET@@PAVCSettableProperties@@PAVCDBSession@@@Z; JoltProperties::SetProperties(ulong,tagDBPROPSET *,CSettableProperties *,CDBSession *)
0x100150e8  mov     ecx, eax
0x100150ea  test    ecx, ecx
0x100150ec  jns     short loc_10015102
0x100150ee  push    ecx; unsigned int
0x100150ef  mov     ecx, edi; this
0x100150f1  mov     [ebp+var_14], 1
0x100150f8  call    ??_GJoltProperties@@QAEPAXI@Z; JoltProperties::`scalar deleting destructor'(uint)
0x100150fd  jmp     loc_100151F0
0x10015102  mov     eax, [ebp+var_14]
0x10015105  cmp     ecx, 40EDAh
0x1001510b  mov     ecx, 1
0x10015110  cmovz   eax, ecx
0x10015113  mov     [ebp+var_10], ecx
0x10015116  push    ecx; unsigned int
0x10015117  mov     ecx, edi; this
0x10015119  mov     [ebp+var_14], eax
0x1001511c  call    ??_GJoltProperties@@QAEPAXI@Z; JoltProperties::`scalar deleting destructor'(uint)
0x10015121  jmp     loc_100151F0
0x10015126  mov     ecx, offset _DBPROPSET_DATASOURCE
0x1001512b  mov     edx, 0Ch
0x10015130  mov     eax, [ecx]
0x10015132  cmp     eax, [edi]
0x10015134  jnz     loc_100151DA
0x1001513a  add     ecx, 4
0x1001513d  add     edi, 4
0x10015140  sub     edx, 4
0x10015143  jnb     short loc_10015130
0x10015145  push    28h ; '('; Size
0x10015147  call    ??2@YAPAXI@Z; operator new(uint)
0x1001514c  mov     ecx, eax
0x1001514e  add     esp, 4
0x10015151  mov     [ebp+var_24], ecx
0x10015154  test    ecx, ecx
0x10015156  jz      loc_10015212
0x1001515c  mov     eax, [ebp+this]
0x1001515f  mov     dword ptr [ecx], offset ??_7JoltProperties@@6B@; const JoltProperties::`vftable'
0x10015165  mov     dword ptr [ecx+4], 0
0x1001516c  mov     dword ptr [ecx+8], 0
0x10015173  mov     dword ptr [ecx+0Ch], 0
0x1001517a  mov     dword ptr [ecx+10h], 0
  ... truncated ...
```
