# CImpIDBUserAttributes::GetAttributeRowset(IUnknown *,ushort *,ushort *,ushort *,ushort *,ulong,ulong,tagDBPROPSET *,_GUID const &,IUnknown * *)

- ea: `0x1000e140`
- end: `0x1000e8c9`
- name: `?GetAttributeRowset@CImpIDBUserAttributes@@UAGJPAUIUnknown@@PAG111KKPAUtagDBPROPSET@@ABU_GUID@@PAPAU2@@Z`
- size: `1929`
- prototype: `int(CImpIDBUserAttributes *__hidden this, struct IUnknown *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, struct tagDBPROPSET *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1000ba90`
- `0x1000d570`
- `0x1000e140`
- `0x1000e8d0`
- `0x10013100`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10020410`
- `0x100204c0`
- `0x100207d0`
- `0x100215b0`
- `0x10027cf0`
- `0x10028340`
- `0x1004ce5d`
- `0x1004d406`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000e893`
- `KERNEL32!LeaveCriticalSection` at `0x1000e893`
- `KERNEL32!EnterCriticalSection` at `0x1000e259`
- `KERNEL32!EnterCriticalSection` at `0x1000e259`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000e23c`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000e23c`
- `msjet40!__imp__JetOpenTempTable@24` at `0x1000e41a`
- `msjet40!__imp__JetOpenTempTable@24` at `0x1000e41a`
- `msjet40!__imp__JetCloseTable@8` at `0x1000e84b`
- `msjet40!__imp__JetCloseTable@8` at `0x1000e863`
- `msjet40!__imp__JetCloseTable@8` at `0x1000e84b`
- `msjet40!__imp__JetCloseTable@8` at `0x1000e863`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000e7ec`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000e7ec`
- `msjet40!__imp__JetMove@16` at `0x1000e447`
- `msjet40!__imp__JetMove@16` at `0x1000e63d`
- `msjet40!__imp__JetMove@16` at `0x1000e447`
- `msjet40!__imp__JetMove@16` at `0x1000e63d`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1000e4c6`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1000e4c6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1000e48c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1000e530`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1000e5b0`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1000e48c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1000e530`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1000e5b0`
- `msjet40!__imp__JetSetColumn@28` at `0x1000e4f8`
- `msjet40!__imp__JetSetColumn@28` at `0x1000e57b`
- `msjet40!__imp__JetSetColumn@28` at `0x1000e5ee`
- `msjet40!__imp__JetSetColumn@28` at `0x1000e4f8`
- `msjet40!__imp__JetSetColumn@28` at `0x1000e57b`
- `msjet40!__imp__JetSetColumn@28` at `0x1000e5ee`
- `msjet40!__imp__JetUpdate@20` at `0x1000e619`
- `msjet40!__imp__JetUpdate@20` at `0x1000e619`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1000e3ce`
- `msjet40!__imp__JetRetrieveProperty@48` at `0x1000e3ce`

## pseudocode

```c
int __stdcall CImpIDBUserAttributes::GetAttributeRowset(
        CImpIDBUserAttributes *this,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned int a8,
        struct tagDBPROPSET *a9,
        const struct _GUID *a10,
        struct IUnknown **a11)
{
  int v11; // eax
  JET_SESID v12; // edi
  struct _RTL_CRITICAL_SECTION *v13; // esi
  bool v14; // zf
  int v15; // ecx
  const struct _GUID *v16; // edx
  GUID *v17; // ecx
  unsigned int v18; // ebx
  bool v19; // cf
  int v20; // ebx
  int v21; // ecx
  CImpIDBUserAttributes *v22; // ebx
  unsigned int Property; // eax
  JET_ERR v24; // eax
  CRowset *v25; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v26; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v27; // eax
  CImpIDBUserAttributes *v28; // eax
  CImpIDBUserAttributes *v29; // edi
  ColumnDataWithFakeNamesAndDBTYPES *v31; // [esp-14h] [ebp-4B8h]
  unsigned int v32; // [esp-Ch] [ebp-4B0h]
  JET_TABLEID v33; // [esp-8h] [ebp-4ACh]
  const struct _GUID *v34; // [esp+0h] [ebp-4A4h]
  const struct _GUID *v35; // [esp+4h] [ebp-4A0h]
  _BYTE v36[4]; // [esp+10h] [ebp-494h] BYREF
  struct _RTL_CRITICAL_SECTION *v37; // [esp+14h] [ebp-490h]
  _DWORD v38[5]; // [esp+18h] [ebp-48Ch] BYREF
  unsigned int v39; // [esp+2Ch] [ebp-478h]
  const struct _GUID *v40; // [esp+30h] [ebp-474h]
  struct IUnknown *v41; // [esp+34h] [ebp-470h]
  unsigned __int16 *v42; // [esp+38h] [ebp-46Ch]
  unsigned __int16 *v43; // [esp+3Ch] [ebp-468h]
  unsigned __int16 *v44; // [esp+40h] [ebp-464h]
  struct IUnknown **v45; // [esp+44h] [ebp-460h]
  int v46; // [esp+48h] [ebp-45Ch] BYREF
  unsigned __int16 *pvBookmark; // [esp+4Ch] [ebp-458h] BYREF
  ColumnDataWithFakeNamesAndDBTYPES *v48; // [esp+50h] [ebp-454h]
  int v49; // [esp+54h] [ebp-450h] BYREF
  CImpIDBUserAttributes *v50; // [esp+58h] [ebp-44Ch]
  CRowset *v51; // [esp+5Ch] [ebp-448h]
  unsigned int pcbActual; // [esp+60h] [ebp-444h] BYREF
  JET_TABLEID ptableid; // [esp+64h] [ebp-440h] BYREF
  unsigned int v54; // [esp+68h] [ebp-43Ch] BYREF
  _BYTE v55[4]; // [esp+6Ch] [ebp-438h] BYREF
  JET_TABLEID tableid; // [esp+70h] [ebp-434h]
  JET_COLUMNID columnid; // [esp+74h] [ebp-430h]
  JET_COLUMNID v58; // [esp+78h] [ebp-42Ch]
  JET_COLUMNID v59; // [esp+7Ch] [ebp-428h]
  JET_COLUMNID prgcolumnid[3]; // [esp+88h] [ebp-41Ch] BYREF
  _WORD v61[256]; // [esp+94h] [ebp-410h] BYREF
  _WORD pvData[256]; // [esp+294h] [ebp-210h] BYREF
  int v63; // [esp+4A0h] [ebp-4h]

  v41 = a2;
  v42 = a3;
  v43 = a4;
  v44 = a5;
  pvBookmark = a6;
  pcbActual = (unsigned int)a9;
  v40 = a10;
  v50 = this;
  v45 = a11;
  v54 = 0;
  memset(&v38[1], 0, 16);
  v38[0] = &CRowsetProperties::`vftable';
  v63 = 0;
  v11 = *((_DWORD *)this + 2);
  v49 = 0;
  v46 = 0;
  ptableid = -1;
  v12 = *(_DWORD *)(v11 + 16);
  v51 = 0;
  v48 = 0;
  SetErrorInfo(0, 0);
  v13 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  tableid = -1;
  v37 = v13;
  EnterCriticalSection(v13);
  LOBYTE(v63) = 1;
  if ( !a11 )
    goto LABEL_56;
  v14 = v42 == 0;
  *v45 = 0;
  if ( v14 || !v43 || a8 && !pcbActual )
    goto LABEL_56;
  v15 = 0;
  if ( a8 )
  {
    while ( !*(_DWORD *)(pcbActual + 24 * v15 + 4) || *(_DWORD *)(pcbActual + 24 * v15) )
    {
      if ( ++v15 >= a8 )
        goto LABEL_10;
    }
    goto LABEL_56;
  }
LABEL_10:
  if ( (a7 & 0xFFFFFFFC) != 0 || (v39 = a7 & 1, (a7 & 1) != 0) && v44 )
  {
LABEL_56:
    v20 = -2147024809;
    goto LABEL_57;
  }
  if ( !v41 )
  {
LABEL_17:
    v20 = CSettableProperties::FInit((CSettableProperties *)v38);
    if ( v20 < 0 )
      goto LABEL_57;
    v20 = CRowsetProperties::CopyPropertiesFromStaticTable(
            (CRowsetProperties *)v38,
            (const struct DBInfoProps *)&rgDBInfoProps);
    if ( v20 < 0 )
      goto LABEL_57;
    v20 = CSettableProperties::SetProperties((CSettableProperties *)v38, a8, (struct tagDBPROPSET *)pcbActual, 0);
    if ( v20 < 0 )
      goto LABEL_57;
    v21 = v49;
    if ( (a7 & 2) != 0 )
    {
      v21 = v49 | 2;
      v49 |= 2u;
    }
    v22 = v50;
    Property = JetRetrieveProperty(
                 *(_DWORD *)(*((_DWORD *)v50 + 2) + 16),
                 *(_DWORD *)(*((_DWORD *)v50 + 2) + 20),
                 v42,
                 v43,
                 v44,
                 pvBookmark,
                 v55,
                 28,
                 v36,
                 0,
                 v21,
                 v39 | 2);
    v54 = Property;
    if ( Property == -1809 )
    {
      v20 = -2147217911;
      goto LABEL_57;
    }
    if ( Property )
    {
LABEL_24:
      v20 = -2147467259;
      goto LABEL_57;
    }
    v54 = JetOpenTempTable(*(_DWORD *)(*((_DWORD *)v22 + 2) + 16), &prgcolumndef, 3u, 8u, &ptableid, prgcolumnid);
    if ( (v54 & 0x80000000) != 0 )
    {
      v20 = -2147467259;
      goto LABEL_57;
    }
    v24 = JetMove(*(_DWORD *)(*((_DWORD *)v22 + 2) + 16), tableid, 0x80000000, 0);
    v54 = v24;
    if ( v24 == -1603 )
    {
LABEL_43:
      v54 = 0;
    }
    else
    {
      while ( v24 >= 0 )
      {
        v54 = JetRetrieveColumn(v12, tableid, columnid, pvData, 0x200u, &pcbActual, 0, 0);
        if ( (v54 & 0x80000000) != 0 )
          goto LABEL_24;
        if ( (pcbActual & 0xFFFFFFFE) >= 0x200 )
LABEL_77:
          __report_rangecheckfailure();
        v33 = ptableid;
        *(_WORD *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
        v54 = JetPrepareUpdate(v12, v33, 0);
        if ( (v54 & 0x80000000) != 0 )
          goto LABEL_24;
        v54 = JetSetColumn(v12, ptableid, prgcolumnid[0], pvData, pcbActual, 0, 0);
        if ( (v54 & 0x80000000) != 0 )
          goto LABEL_24;
        v54 = JetRetrieveColumn(v12, tableid, v58, v61, 0x200u, &pcbActual, 0, 0);
        if ( (v54 & 0x80000000) != 0 )
          goto LABEL_24;
        if ( (pcbActual & 0xFFFFFFFE) >= 0x200 )
          goto LABEL_77;
        v32 = pcbActual;
        *(_WORD *)((char *)v61 + (pcbActual & 0xFFFFFFFE)) = 0;
        v54 = JetSetColumn(v12, ptableid, prgcolumnid[1], v61, v32, 0, 0);
        if ( (v54 & 0x80000000) != 0 )
          goto LABEL_24;
        v54 = JetRetrieveColumn(v12, tableid, v59, &v49, 4u, &pcbActual, 0, 0);
        if ( (v54 & 0x80000000) != 0 )
          goto LABEL_24;
        if ( (v49 & 2) != 0 )
          v46 |= 2u;
        v54 = JetSetColumn(v12, ptableid, prgcolumnid[2], &v46, 4u, 0, 0);
        if ( (v54 & 0x80000000) != 0 )
          goto LABEL_24;
        v54 = JetUpdate(v12, ptableid, &pvBookmark, 4u, &pcbActual);
        if ( (v54 & 0x80000000) != 0 )
          goto LABEL_24;
        v24 = JetMove(*(_DWORD *)(*((_DWORD *)v22 + 2) + 16), tableid, 1, 0);
        v54 = v24;
        if ( v24 == -1603 )
          goto LABEL_43;
      }
    }
    v25 = (CRowset *)operator new(0xF0u);
    pvBookmark = (unsigned __int16 *)v25;
    if ( v25 )
    {
      v51 = CRowset::CRowset(v25, v41);
      if ( v51 )
      {
        v26 = (ColumnDataWithFakeNamesAndDBTYPES *)operator new(0x20u);
        pvBookmark = (unsigned __int16 *)v26;
        if ( v26 )
        {
          v27 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(v26);
          v48 = v27;
          if ( v27 )
          {
            *((_DWORD *)v27 + 7) = 0;
            *((_DWORD *)v27 + 5) = &UserAttributesDefNames;
            v20 = ColumnData::FInit(
                    v27,
                    v12,
                    *(_DWORD *)(*((_DWORD *)v22 + 2) + 20),
                    ptableid,
                    (int *)&v54,
                    0,
                    (int)v27);
            if ( v20 >= 0 )
            {
              v31 = v48;
              v28 = v50;
              *((_DWORD *)v48 + 1) = 3;
              v20 = CRowset::FInit(
                      v51,
                      0,
                      *((_DWORD *)v28 + 2),
                      0,
                      0,
                      0,
                      ptableid,
                      v38,
                      1,
                      0,
                      0,
                      v31,
                      1,
                      0,
                      0,
                      &GUID_NULL);
              if ( v20 >= 0 )
              {
                ptableid = -1;
                v20 = (**(int (__thiscall ***)(_DWORD, CRowset *, const struct _GUID *, struct IUnknown **))v51)(
                        **(_DWORD **)v51,
                        v51,
                        v40,
                        v45);
              }
            }
            goto LABEL_57;
          }
        }
        else
        {
          v48 = 0;
        }
        v20 = -2147024882;
        goto LABEL_57;
      }
    }
    else
    {
      v51 = 0;
    }
    v20 = -2147024882;
    goto LABEL_57;
  }
  v16 = v40;
  v17 = &IID_IUnknown;
  v18 = 12;
  while ( v17->Data1 == v16->Data1 )
  {
    v17 = (GUID *)((char *)v17 + 4);
    v16 = (const struct _GUID *)((char *)v16 + 4);
    v19 = v18 < 4;
    v18 -= 4;
    if ( v19 )
      goto LABEL_17;
  }
  v20 = -2147217886;
LABEL_57:
  if ( v54 )
  {
    CExtError::SendJetErrortoOLEAuto(v54, (int)&IID_IDBUserAttributes, (int)v34, v35);
  }
  else if ( v20 < 0
         && v20 != -2147024882
         && !JetGetDatabaseInfo(
               *(_DWORD *)(*((_DWORD *)v50 + 2) + 16),
               *(_DWORD *)(*((_DWORD *)v50 + 2) + 20),
               &pvBookmark,
               4,
               3) )
  {
    CExtError::SendHRtoOLEAuto((int)&IID_IDBUserAttributes, 0, v34, (int)v35);
  }
  if ( v45 && !*v45 && v51 )
    (*(void (__thiscall **)(CRowset *, int))(*(_DWORD *)v51 + 12))(v51, 1);
  v29 = v50;
  if ( tableid != -1 )
    JetCloseTable(*(_DWORD *)(*((_DWORD *)v50 + 2) + 16), tableid);
  if ( ptableid != -1 )
    JetCloseTable(*(_DWORD *)(*((_DWORD *)v29 + 2) + 16), ptableid);
  if ( v20 < 0 && v48 )
    (*(void (__thiscall **)(ColumnDataWithFakeNamesAndDBTYPES *, int))(*(_DWORD *)v48 + 4))(v48, 1);
  if ( v13 )
    LeaveCriticalSection(v13);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v38);
  return v20;
}

```

## disassembly

```asm
0x1000e140  mov     edi, edi
0x1000e142  push    ebp
0x1000e143  mov     ebp, esp
0x1000e145  push    0FFFFFFFFh
0x1000e147  push    offset ?GetAttributeRowset@CImpIDBUserAttributes@@UAGJPAUIUnknown@@PAG111KKPAUtagDBPROPSET@@ABU_GUID@@PAPAU2@@Z_SEH
0x1000e14c  mov     eax, large fs:0
0x1000e152  push    eax
0x1000e153  sub     esp, 488h
0x1000e159  mov     eax, ___security_cookie
0x1000e15e  xor     eax, ebp
0x1000e160  mov     [ebp+var_10], eax
0x1000e163  push    ebx
0x1000e164  push    esi
0x1000e165  push    edi; int
0x1000e166  push    eax; struct _GUID *
0x1000e167  lea     eax, [ebp+var_C]
0x1000e16a  mov     large fs:0, eax
0x1000e170  mov     eax, [ebp+arg_4]
0x1000e173  mov     ebx, [ebp+this]
0x1000e176  mov     [ebp+var_470], eax
0x1000e17c  mov     eax, [ebp+arg_8]
0x1000e17f  mov     [ebp+var_46C], eax
0x1000e185  mov     eax, [ebp+arg_C]
0x1000e188  mov     [ebp+var_468], eax
0x1000e18e  mov     eax, [ebp+arg_10]
0x1000e191  mov     [ebp+var_464], eax
0x1000e197  mov     eax, [ebp+arg_14]
0x1000e19a  mov     [ebp+pvBookmark], eax
0x1000e1a0  mov     eax, [ebp+arg_20]
0x1000e1a3  mov     [ebp+pcbActual], eax
0x1000e1a9  mov     eax, [ebp+arg_24]
0x1000e1ac  mov     [ebp+var_474], eax
0x1000e1b2  mov     eax, [ebp+arg_28]
0x1000e1b5  mov     [ebp+var_44C], ebx
0x1000e1bb  mov     [ebp+var_460], eax
0x1000e1c1  mov     [ebp+var_43C], 0
0x1000e1cb  mov     [ebp+var_488], 0
0x1000e1d5  mov     [ebp+var_484], 0
0x1000e1df  mov     [ebp+var_480], 0
0x1000e1e9  mov     [ebp+var_48C], offset ??_7CRowsetProperties@@6B@; const CRowsetProperties::`vftable'
0x1000e1f3  mov     [ebp+var_47C], 0
0x1000e1fd  mov     [ebp+var_4], 0
0x1000e204  xor     ecx, ecx
0x1000e206  mov     eax, [ebx+8]
0x1000e209  push    ecx; perrinfo
0x1000e20a  mov     [ebp+var_450], 0
0x1000e214  mov     [ebp+var_45C], 0
0x1000e21e  mov     [ebp+ptableid], 0FFFFFFFFh
0x1000e228  mov     edi, [eax+10h]
0x1000e22b  push    ecx; dwReserved
0x1000e22c  mov     [ebp+var_448], 0
0x1000e236  mov     [ebp+var_454], ecx
0x1000e23c  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000e242  mov     esi, [ebx+8]
0x1000e245  add     esi, 68h ; 'h'
0x1000e248  mov     [ebp+tableid], 0FFFFFFFFh
0x1000e252  push    esi; lpCriticalSection
0x1000e253  mov     [ebp+var_490], esi
0x1000e259  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000e25f  mov     eax, [ebp+var_460]
0x1000e265  mov     byte ptr [ebp+var_4], 1
0x1000e269  test    eax, eax
0x1000e26b  jz      loc_1000E79C
0x1000e271  cmp     [ebp+var_46C], 0
0x1000e278  mov     dword ptr [eax], 0
0x1000e27e  jz      loc_1000E79C
0x1000e284  cmp     [ebp+var_468], 0
0x1000e28b  jz      loc_1000E79C
0x1000e291  mov     edx, [ebp+arg_1C]
0x1000e294  mov     ebx, [ebp+pcbActual]
0x1000e29a  test    edx, edx
0x1000e29c  jz      short loc_1000E2A6
0x1000e29e  test    ebx, ebx
0x1000e2a0  jz      loc_1000E79C
0x1000e2a6  xor     ecx, ecx
0x1000e2a8  test    edx, edx
0x1000e2aa  jz      short loc_1000E2C9
0x1000e2ac  nop     dword ptr [eax+00h]
0x1000e2b0  lea     eax, [ecx+ecx*2]
0x1000e2b3  cmp     dword ptr [ebx+eax*8+4], 0
0x1000e2b8  jz      short loc_1000E2C4
0x1000e2ba  cmp     dword ptr [ebx+eax*8], 0
0x1000e2be  jz      loc_1000E79C
0x1000e2c4  inc     ecx
0x1000e2c5  cmp     ecx, edx
0x1000e2c7  jb      short loc_1000E2B0
0x1000e2c9  mov     eax, [ebp+arg_18]
0x1000e2cc  test    eax, 0FFFFFFFCh
0x1000e2d1  jnz     loc_1000E79C
0x1000e2d7  and     eax, 1
0x1000e2da  mov     [ebp+var_478], eax
0x1000e2e0  jz      short loc_1000E2EF
0x1000e2e2  cmp     [ebp+var_464], 0
0x1000e2e9  jnz     loc_1000E79C
0x1000e2ef  cmp     [ebp+var_470], 0
0x1000e2f6  jz      short loc_1000E325
0x1000e2f8  mov     edx, [ebp+var_474]
0x1000e2fe  mov     ecx, offset _IID_IUnknown
0x1000e303  mov     ebx, 0Ch
0x1000e308  nop     dword ptr [eax+eax+00000000h]
0x1000e310  mov     eax, [ecx]
0x1000e312  cmp     eax, [edx]
0x1000e314  jnz     loc_1000E3F3
0x1000e31a  add     ecx, 4
0x1000e31d  add     edx, 4
0x1000e320  sub     ebx, 4
0x1000e323  jnb     short loc_1000E310
0x1000e325  lea     ecx, [ebp+var_48C]; this
0x1000e32b  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x1000e330  mov     ebx, eax
0x1000e332  test    ebx, ebx
0x1000e334  js      loc_1000E7A1
0x1000e33a  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; struct DBInfoProps *
0x1000e33f  lea     ecx, [ebp+var_48C]; this
0x1000e345  call    ?CopyPropertiesFromStaticTable@CRowsetProperties@@QAEJPBUDBInfoProps@@@Z; CRowsetProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)
0x1000e34a  mov     ebx, eax
0x1000e34c  test    ebx, ebx
0x1000e34e  js      loc_1000E7A1
0x1000e354  mov     eax, [ebp+pcbActual]
0x1000e35a  lea     ecx, [ebp+var_48C]; this
0x1000e360  push    0; struct CDBSession *
0x1000e362  push    eax; struct tagDBPROPSET *
0x1000e363  push    [ebp+arg_1C]; unsigned int
0x1000e366  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x1000e36b  mov     ebx, eax
0x1000e36d  test    ebx, ebx
0x1000e36f  js      loc_1000E7A1
0x1000e375  test    byte ptr [ebp+arg_18], 2
0x1000e379  mov     ecx, [ebp+var_450]
0x1000e37f  jz      short loc_1000E38A
0x1000e381  or      ecx, 2
0x1000e384  mov     [ebp+var_450], ecx
0x1000e38a  mov     edx, [ebp+var_478]
0x1000e390  mov     ebx, [ebp+var_44C]
0x1000e396  or      edx, 2
0x1000e399  push    edx
0x1000e39a  push    ecx
0x1000e39b  push    0
0x1000e39d  mov     eax, [ebx+8]
0x1000e3a0  lea     ecx, [ebp+var_494]
0x1000e3a6  push    ecx
0x1000e3a7  push    1Ch
0x1000e3a9  lea     ecx, [ebp+var_438]
0x1000e3af  push    ecx
0x1000e3b0  push    [ebp+pvBookmark]
0x1000e3b6  push    [ebp+var_464]
0x1000e3bc  push    [ebp+var_468]
0x1000e3c2  push    [ebp+var_46C]
0x1000e3c8  push    dword ptr [eax+14h]
0x1000e3cb  push    dword ptr [eax+10h]
0x1000e3ce  call    ds:__imp__JetRetrieveProperty@48; JetRetrieveProperty(x,x,x,x,x,x,x,x,x,x,x,x)
0x1000e3d4  mov     [ebp+var_43C], eax
0x1000e3da  cmp     eax, 0FFFFF8EFh
0x1000e3df  jz      loc_1000E795
0x1000e3e5  test    eax, eax
0x1000e3e7  jz      short loc_1000E3FD
0x1000e3e9  mov     ebx, 80004005h
0x1000e3ee  jmp     loc_1000E7A1
0x1000e3f3  mov     ebx, 80040E22h
0x1000e3f8  jmp     loc_1000E7A1
0x1000e3fd  lea     eax, [ebp+prgcolumnid]
0x1000e403  push    eax; prgcolumnid
0x1000e404  lea     eax, [ebp+ptableid]
0x1000e40a  push    eax; ptableid
0x1000e40b  mov     eax, [ebx+8]
0x1000e40e  push    8; grbit
0x1000e410  push    3; ccolumn
0x1000e412  push    offset prgcolumndef; prgcolumndef
0x1000e417  push    dword ptr [eax+10h]; sesid
0x1000e41a  call    ds:__imp__JetOpenTempTable@24; JetOpenTempTable(x,x,x,x,x,x)
0x1000e420  mov     [ebp+var_43C], eax
0x1000e426  test    eax, eax
0x1000e428  jns     short loc_1000E434
0x1000e42a  mov     ebx, 80004005h
0x1000e42f  jmp     loc_1000E7A1
0x1000e434  mov     eax, [ebx+8]
0x1000e437  push    0; grbit
0x1000e439  push    80000000h; cRow
0x1000e43e  push    [ebp+tableid]; tableid
0x1000e444  push    dword ptr [eax+10h]; sesid
0x1000e447  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1000e44d  mov     [ebp+var_43C], eax
0x1000e453  cmp     eax, 0FFFFF9BDh
0x1000e458  jz      loc_1000E654
0x1000e45e  mov     edi, edi
0x1000e460  test    eax, eax
0x1000e462  js      loc_1000E65E
0x1000e468  push    0; pretinfo
0x1000e46a  push    0; grbit
0x1000e46c  lea     eax, [ebp+pcbActual]
0x1000e472  push    eax; pcbActual
0x1000e473  push    200h; cbData
0x1000e478  lea     eax, [ebp+pvData]
0x1000e47e  push    eax; pvData
0x1000e47f  push    [ebp+columnid]; columnid
0x1000e485  push    [ebp+tableid]; tableid
0x1000e48b  push    edi; sesid
0x1000e48c  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1000e492  mov     [ebp+var_43C], eax
0x1000e498  test    eax, eax
0x1000e49a  js      loc_1000E3E9
0x1000e4a0  mov     eax, [ebp+pcbActual]
0x1000e4a6  and     eax, 0FFFFFFFEh
0x1000e4a9  cmp     eax, 200h
0x1000e4ae  jnb     loc_1000E8C4
0x1000e4b4  xor     ecx, ecx
0x1000e4b6  push    ecx; prep
0x1000e4b7  push    [ebp+ptableid]; tableid
0x1000e4bd  mov     [ebp+eax+pvData], cx
0x1000e4c5  push    edi; sesid
0x1000e4c6  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x1000e4cc  mov     [ebp+var_43C], eax
0x1000e4d2  test    eax, eax
0x1000e4d4  js      loc_1000E3E9
0x1000e4da  push    0; psetinfo
0x1000e4dc  push    0; grbit
0x1000e4de  push    [ebp+pcbActual]; cbData
0x1000e4e4  lea     eax, [ebp+pvData]
0x1000e4ea  push    eax; pvData
0x1000e4eb  push    [ebp+prgcolumnid]; columnid
0x1000e4f1  push    [ebp+ptableid]; tableid
0x1000e4f7  push    edi; sesid
0x1000e4f8  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1000e4fe  mov     [ebp+var_43C], eax
0x1000e504  test    eax, eax
0x1000e506  js      loc_1000E3E9
0x1000e50c  push    0; pretinfo
0x1000e50e  push    0; grbit
0x1000e510  lea     eax, [ebp+pcbActual]
0x1000e516  push    eax; pcbActual
0x1000e517  push    200h; cbData
0x1000e51c  lea     eax, [ebp+var_410]
0x1000e522  push    eax; pvData
0x1000e523  push    [ebp+var_42C]; columnid
0x1000e529  push    [ebp+tableid]; tableid
0x1000e52f  push    edi; sesid
0x1000e530  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1000e536  mov     [ebp+var_43C], eax
0x1000e53c  test    eax, eax
0x1000e53e  js      loc_1000E3E9
0x1000e544  mov     ecx, [ebp+pcbActual]
0x1000e54a  mov     eax, ecx
0x1000e54c  and     eax, 0FFFFFFFEh
0x1000e54f  cmp     eax, 200h
0x1000e554  jnb     loc_1000E8C4
0x1000e55a  xor     edx, edx
0x1000e55c  push    edx; psetinfo
0x1000e55d  push    edx; grbit
0x1000e55e  push    ecx; cbData
0x1000e55f  mov     [ebp+eax+var_410], dx
0x1000e567  lea     eax, [ebp+var_410]
0x1000e56d  push    eax; pvData
0x1000e56e  push    [ebp+var_418]; columnid
0x1000e574  push    [ebp+ptableid]; tableid
0x1000e57a  push    edi; sesid
0x1000e57b  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1000e581  mov     [ebp+var_43C], eax
0x1000e587  test    eax, eax
0x1000e589  js      loc_1000E3E9
0x1000e58f  push    0; pretinfo
0x1000e591  push    0; grbit
0x1000e593  lea     eax, [ebp+pcbActual]
0x1000e599  push    eax; pcbActual
0x1000e59a  push    4; cbData
0x1000e59c  lea     eax, [ebp+var_450]
0x1000e5a2  push    eax; pvData
0x1000e5a3  push    [ebp+var_428]; columnid
0x1000e5a9  push    [ebp+tableid]; tableid
0x1000e5af  push    edi; sesid
0x1000e5b0  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1000e5b6  mov     [ebp+var_43C], eax
0x1000e5bc  test    eax, eax
0x1000e5be  js      loc_1000E3E9
0x1000e5c4  test    byte ptr [ebp+var_450], 2
0x1000e5cb  jz      short loc_1000E5D4
0x1000e5cd  or      [ebp+var_45C], 2
0x1000e5d4  push    0; psetinfo
0x1000e5d6  push    0; grbit
0x1000e5d8  push    4; cbData
0x1000e5da  lea     eax, [ebp+var_45C]
0x1000e5e0  push    eax; pvData
0x1000e5e1  push    [ebp+var_414]; columnid
0x1000e5e7  push    [ebp+ptableid]; tableid
0x1000e5ed  push    edi; sesid
0x1000e5ee  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1000e5f4  mov     [ebp+var_43C], eax
0x1000e5fa  test    eax, eax
0x1000e5fc  js      loc_1000E3E9
0x1000e602  lea     eax, [ebp+pcbActual]
0x1000e608  push    eax; pcbActual
0x1000e609  push    4; cbBookmark
0x1000e60b  lea     eax, [ebp+pvBookmark]
0x1000e611  push    eax; pvBookmark
0x1000e612  push    [ebp+ptableid]; tableid
0x1000e618  push    edi; sesid
0x1000e619  call    ds:__imp__JetUpdate@20; JetUpdate(x,x,x,x,x)
0x1000e61f  mov     [ebp+var_43C], eax
0x1000e625  test    eax, eax
0x1000e627  js      loc_1000E3E9
0x1000e62d  mov     eax, [ebx+8]
  ... truncated ...
```
