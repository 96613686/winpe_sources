# CImpIIndexDef::CreateIndex(tagDBID *,tagDBID *,ulong,tagDBINDEXCOLUMNDESC const * const,ulong,tagDBPROPSET * const,tagDBID * *)

- ea: `0x1001d7f0`
- end: `0x1001df12`
- name: `?CreateIndex@CImpIIndexDef@@UAGJPAUtagDBID@@0KQBUtagDBINDEXCOLUMNDESC@@KQAUtagDBPROPSET@@PAPAU2@@Z`
- size: `1826`
- prototype: `int(CImpIIndexDef *__hidden this, struct tagDBID *, struct tagDBID *, unsigned int, const struct tagDBINDEXCOLUMNDESC *const, unsigned int, struct tagDBPROPSET *const, struct tagDBID **)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x1000d4a0`
- `0x1000e8d0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001d7f0`
- `0x1001e800`
- `0x1001ea50`
- `0x1001fb90`
- `0x1001fc50`
- `0x100201c0`
- `0x10020410`
- `0x100207d0`
- `0x100225b0`
- `0x10022660`
- `0x10025750`
- `0x1004cc50`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001dee4`
- `KERNEL32!LeaveCriticalSection` at `0x1001dee4`
- `KERNEL32!EnterCriticalSection` at `0x1001d8a3`
- `KERNEL32!EnterCriticalSection` at `0x1001d8a3`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001d88a`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001d88a`
- `msjet40!__imp__JetCloseTable@8` at `0x1001de33`
- `msjet40!__imp__JetCloseTable@8` at `0x1001de33`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001de0a`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001de0a`

## pseudocode

```c
int __stdcall CImpIIndexDef::CreateIndex(
        CImpIIndexDef *this,
        struct tagDBID *a2,
        struct tagDBID *a3,
        unsigned int a4,
        const struct tagDBINDEXCOLUMNDESC *const a5,
        unsigned int a6,
        struct tagDBPROPSET *const a7,
        struct tagDBID **a8)
{
  struct _RTL_CRITICAL_SECTION *v8; // esi
  int v9; // ecx
  int v10; // eax
  struct tagDBID *v11; // ecx
  const DBID *v12; // edx
  unsigned int v13; // edi
  bool v14; // cf
  int IntValue; // edi
  int v16; // edx
  LPOLESTR pwszName; // ecx
  _WORD *v18; // edi
  int v20; // eax
  struct tagDBID **v21; // edx
  unsigned __int16 *v22; // ecx
  int v23; // eax
  JoltProperties *v24; // edi
  unsigned int v25; // eax
  int v26; // eax
  struct tagDBPROPSET *v27; // ecx
  int (__thiscall *v28)(_DWORD, int, unsigned int); // ecx
  unsigned __int16 *v29; // eax
  unsigned __int16 *v30; // ecx
  unsigned int v31; // eax
  DBID *pColumnID; // edi
  DBINDEX_COL_ORDER eIndexColOrder; // eax
  __int16 v34; // ax
  unsigned __int16 *v35; // edx
  unsigned int v36; // ecx
  int v37; // ecx
  unsigned __int16 *v38; // eax
  int v39; // edx
  int v40; // eax
  int v41; // edi
  unsigned __int16 *v42; // edx
  int v43; // ecx
  unsigned __int16 *v44; // esi
  unsigned __int16 v45; // ax
  unsigned __int16 *v46; // eax
  LPOLESTR v47; // ecx
  _WORD *v48; // edx
  unsigned int v50; // ecx
  unsigned int v51; // eax
  CImpIIndexDef *v52; // edx
  int v53; // eax
  int v54; // ecx
  int v55; // eax
  int v56; // eax
  int v57; // eax
  struct tagDBID **v58; // edi
  LPOLESTR v59; // edx
  unsigned int v61; // [esp-14h] [ebp-A8h]
  unsigned __int16 *v62; // [esp-10h] [ebp-A4h]
  struct _GUID v63; // [esp-10h] [ebp-A4h]
  unsigned __int16 *v64; // [esp+0h] [ebp-94h]
  struct CCommand *v65; // [esp+4h] [ebp-90h]
  unsigned int v66; // [esp+8h] [ebp-8Ch]
  struct _RTL_CRITICAL_SECTION *v67; // [esp+10h] [ebp-84h]
  _DWORD v68[2]; // [esp+18h] [ebp-7Ch] BYREF
  JoltProperties *v69; // [esp+20h] [ebp-74h]
  int v70; // [esp+24h] [ebp-70h]
  DBID *v71; // [esp+28h] [ebp-6Ch] BYREF
  int v72; // [esp+2Ch] [ebp-68h]
  const struct tagDBINDEXCOLUMNDESC *v73; // [esp+30h] [ebp-64h]
  JET_TABLEID tableid; // [esp+34h] [ebp-60h] BYREF
  unsigned int v75; // [esp+38h] [ebp-5Ch]
  BOOL v76; // [esp+3Ch] [ebp-58h]
  unsigned __int16 *v77; // [esp+40h] [ebp-54h]
  int v78; // [esp+44h] [ebp-50h]
  struct tagDBID *v79; // [esp+48h] [ebp-4Ch]
  unsigned int v80; // [esp+4Ch] [ebp-48h] BYREF
  unsigned __int16 v81[2]; // [esp+50h] [ebp-44h] BYREF
  struct tagDBID **v82; // [esp+54h] [ebp-40h]
  struct tagDBPROPSET *v83; // [esp+58h] [ebp-3Ch]
  struct tagDBID *v84; // [esp+5Ch] [ebp-38h]
  unsigned __int16 *v85; // [esp+60h] [ebp-34h]
  CImpIIndexDef *v86; // [esp+64h] [ebp-30h]
  int v87; // [esp+68h] [ebp-2Ch]
  char v88; // [esp+6Ch] [ebp-28h] BYREF
  int v89; // [esp+7Ch] [ebp-18h]
  int v91; // [esp+90h] [ebp-4h]

  v79 = a2;
  v84 = a3;
  v73 = a5;
  v86 = this;
  v83 = a7;
  v82 = a8;
  *(_DWORD *)v81 = 0;
  tableid = -1;
  v77 = 0;
  v68[1] = 0;
  v69 = 0;
  v70 = 0;
  v68[0] = &CIndexProperties::`vftable';
  v91 = 0;
  v72 = 0;
  v75 = 0;
  SetErrorInfo(0, 0);
  v8 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  v67 = v8;
  EnterCriticalSection(v8);
  LOBYTE(v91) = 1;
  if ( a8 )
    *v82 = 0;
  if ( !v79 || !v84 && !a8 || !a4 || !v73 || a6 && !a7 )
  {
LABEL_100:
    IntValue = -2147024809;
    goto LABEL_101;
  }
  v9 = 0;
  if ( a6 )
  {
    while ( a7[v9].rgProperties || !a7[v9].cProperties )
    {
      if ( ++v9 >= a6 )
        goto LABEL_14;
    }
    goto LABEL_100;
  }
LABEL_14:
  if ( v84 )
  {
LABEL_18:
    v11 = v79;
    v12 = &DB_NULLID;
    v13 = 20;
    while ( v11->uGuid.guid.Data1 == v12->uGuid.guid.Data1 )
    {
      v11 = (struct tagDBID *)((char *)v11 + 4);
      v12 = (const DBID *)((char *)v12 + 4);
      v14 = v13 < 4;
      v13 -= 4;
      if ( v14 )
        goto LABEL_21;
    }
    if ( v79->eKind != 2 || !v79->uName.ulPropid )
    {
LABEL_21:
      IntValue = -2147217865;
      goto LABEL_101;
    }
    if ( v84->eKind != 2 || !v84->uName.ulPropid )
    {
      IntValue = -2147217806;
      goto LABEL_101;
    }
    if ( v82 )
    {
      v16 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(*(_DWORD *)(*(_DWORD *)Sys + 12), Sys, 24);
      *v82 = (struct tagDBID *)v16;
      if ( !v16 )
      {
        v87 = -2147024882;
        goto LABEL_104;
      }
      pwszName = v84->uName.pwszName;
      v18 = pwszName + 1;
      while ( *pwszName++ )
        ;
      *(_DWORD *)(v16 + 16) = 2;
      v85 = (unsigned __int16 *)(2 * (pwszName - v18) + 2);
      v20 = (*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)Sys + 12))(
              *(_DWORD *)(*(_DWORD *)Sys + 12),
              Sys,
              v85);
      v21 = v82;
      (*v82)->uName.ulPropid = v20;
      v22 = (*v21)->uName.pwszName;
      if ( !v22 )
      {
        v87 = -2147024882;
        goto LABEL_104;
      }
      WCSCPY(v84->uName.pwszName, v22, v85, v64, (unsigned int)v65);
    }
    IntValue = CIndexProperties::FInit((CIndexProperties *)v68);
    v87 = IntValue;
    if ( IntValue >= 0 )
    {
      IntValue = CIndexProperties::CopyPropertiesFromStaticTable(
                   (CIndexProperties *)v68,
                   (const struct DBInfoProps *)&rgDBInfoProps);
      v87 = IntValue;
      if ( IntValue >= 0 )
      {
        v23 = CSettableProperties::SetProperties((CSettableProperties *)v68, a6, v83, 0);
        IntValue = v23;
        v87 = v23;
        if ( v23 >= 0 )
        {
          v24 = v69;
          v76 = v23 == 265946;
          v85 = (unsigned __int16 *)JoltProperties::IsbPropertySet(v69, 0x36u);
          v25 = JoltProperties::IsbPropertySet(v24, 0x39u);
          v80 = v25;
          v78 = v76;
          if ( v85 == (unsigned __int16 *)1 )
          {
            v78 = v76;
            if ( !v25 )
            {
              v78 = v76;
              if ( (*((_DWORD *)JoltProperties::GetRowbyProp(v24, 0x39u) + 10) & 1) != 0 )
              {
                *(_QWORD *)v63.Data4 = (unsigned int)v83 | 0x800000000LL;
                *(_DWORD *)&v63.Data2 = a6;
                v63.Data1 = 0;
                IntValue = HandleInvalidPropertyValue(
                             *(_OWORD *)&DBPROPSET_INDEX,
                             v63,
                             (struct CSettableProperties *)v64,
                             v65,
                             v66,
                             (struct tagDBPROPSET *const)v8,
                             (unsigned int)v8);
                v87 = IntValue;
                if ( IntValue < 0 )
                  goto LABEL_97;
                v24 = v69;
                if ( (*((_BYTE *)JoltProperties::GetRowbyProp(v69, 0x39u) + 40) & 2) != 0 )
                {
                  IntValue = -2147217887;
LABEL_101:
                  v87 = IntValue;
                  v56 = *((_DWORD *)v86 + 2);
                  v54 = *(_DWORD *)(v56 + 20);
                  v55 = *(_DWORD *)(v56 + 16);
LABEL_102:
                  if ( !JetGetDatabaseInfo(v55, v54, &v71, 4, 3) )
                    CExtError::SendHRtoOLEAuto(
                      IntValue,
                      (__int128 *)&IID_IIndexDefinition,
                      0,
                      (const struct _GUID *)v64,
                      (int)v65);
                  goto LABEL_104;
                }
                v78 = 1;
              }
            }
          }
          v26 = 2;
          if ( v85 != (unsigned __int16 *)1 )
            v26 = 0;
          v27 = (struct tagDBPROPSET *)(v26 | 1);
          if ( v80 != 1 )
            v27 = (struct tagDBPROPSET *)v26;
          v83 = v27;
          IntValue = JoltProperties::GetIntValue(v24, 0x35u, &v80);
          v87 = IntValue;
          if ( IntValue >= 0 )
          {
            if ( v80 == 1 )
            {
              v83 = (struct tagDBPROPSET *)((unsigned int)v83 | 4);
            }
            else if ( v80 == 2 )
            {
              v83 = (struct tagDBPROPSET *)((unsigned int)v83 | 8);
            }
            v28 = *(int (__thiscall **)(_DWORD, int, unsigned int))(*(_DWORD *)Sys + 12);
            v80 = 132 * a4 + 2;
            v29 = (unsigned __int16 *)v28(v28, Sys, v80);
            v77 = v29;
            if ( !v29 )
            {
              v87 = -2147024882;
              goto LABEL_104;
            }
            v30 = v29;
            v31 = 0;
            v76 = 0;
            do
            {
              pColumnID = v73[v31].pColumnID;
              eIndexColOrder = v73[v31].eIndexColOrder;
              v71 = pColumnID;
              if ( !pColumnID || pColumnID->eKind != 2 || !pColumnID->uName.ulPropid )
              {
LABEL_88:
                IntValue = -2147217903;
                v51 = 0;
                v87 = -2147217903;
                goto LABEL_94;
              }
              if ( eIndexColOrder )
              {
                if ( eIndexColOrder != 1 )
                {
                  IntValue = -2147024809;
                  v51 = 0;
                  v87 = -2147024809;
                  goto LABEL_94;
                }
                v34 = 45;
              }
              else
              {
                v34 = 43;
              }
              *v30 = v34;
              v35 = v30 + 1;
              v36 = v80;
              *v35 = 0;
              v87 = (int)pColumnID->uName.pwszName;
              v85 = v35;
              v37 = v36 - (v35 - v77);
              if ( v37 > 0 )
              {
                v38 = v85;
                v39 = v37;
                do
                {
                  if ( !*v38 )
                    break;
                  ++v38;
                  --v39;
                }
                while ( v39 );
                v40 = v39 ? v37 - v39 : 0;
                if ( v39 )
                {
                  v41 = 64;
                  v42 = &v85[v40];
                  v43 = v37 - v40;
                  if ( v43 )
                  {
                    v44 = (unsigned __int16 *)v87;
                    do
                    {
                      if ( !v41 )
                        break;
                      v45 = *v44;
                      if ( !*v44 )
                        break;
                      v44 = (unsigned __int16 *)(v87 + 2);
                      *v42++ = v45;
                      v87 = (int)v44;
                      --v41;
                      --v43;
                    }
                    while ( v43 );
                    v8 = v67;
                  }
                  pColumnID = v71;
                  v46 = v42 - 1;
                  if ( v43 )
                    v46 = v42;
                  *v46 = 0;
                }
              }
              v47 = pColumnID->uName.pwszName;
              v48 = v47 + 1;
              while ( *v47++ )
                ;
              v50 = v47 - v48;
              if ( v50 > 0x40 )
                goto LABEL_88;
              v75 += v50 + 3;
              v30 = &v85[v50 + 1];
              v31 = v76 + 1;
              v76 = v31;
            }
            while ( v31 < a4 );
            *v30 = 0;
            IntValue = CJOLT::JOLTJetOpenTable(
                         *(_DWORD *)(*((_DWORD *)v86 + 2) + 20),
                         *(_DWORD *)(*((_DWORD *)v86 + 2) + 16),
                         v79->uName.ulPropid,
                         v61,
                         v62,
                         (const void *)2,
                         &tableid,
                         (int *)v81,
                         (unsigned int *)v64,
                         (int *)v65);
            v87 = IntValue;
            if ( IntValue >= 0 )
            {
              IntValue = CJOLT::JOLTJetCreateIndex(
                           tableid,
                           *(_DWORD *)(*((_DWORD *)v86 + 2) + 16),
                           v84->uName.ulPropid,
                           (unsigned int)v83,
                           v77,
                           v75,
                           v81,
                           (int *)v81,
                           (unsigned int)v64,
                           (int *)v65);
              v87 = IntValue;
              if ( IntValue < 0 )
              {
                v51 = *(_DWORD *)v81;
                if ( *(_DWORD *)v81 == -1002 )
                {
                  IntValue = -2147217806;
                  v87 = -2147217806;
LABEL_95:
                  CExtError::SendJetErrortoOLEAuto(
                    IntValue,
                    *(char **)(*((_DWORD *)v86 + 2) + 16),
                    v51,
                    (int)&IID_IIndexDefinition,
                    (int)v64,
                    (const struct _GUID *)v65);
                  goto LABEL_104;
                }
LABEL_94:
                if ( v51 )
                  goto LABEL_95;
                if ( IntValue >= 0 )
                  goto LABEL_104;
                goto LABEL_97;
              }
              IntValue = 0;
              if ( v78 == 1 )
                IntValue = 265946;
              v87 = IntValue;
            }
            v51 = *(_DWORD *)v81;
            goto LABEL_94;
          }
        }
      }
    }
LABEL_97:
    v52 = v86;
    v53 = *((_DWORD *)v86 + 2);
    v54 = *(_DWORD *)(v53 + 20);
    v55 = *(_DWORD *)(v53 + 16);
    if ( IntValue == -2147024882 )
      goto LABEL_105;
    goto LABEL_102;
  }
  v84 = (struct tagDBID *)&v88;
  v10 = *(_DWORD *)Sys;
  v89 = 2;
  if ( (*(int (__thiscall **)(_DWORD, int, int))(v10 + 12))(*(_DWORD *)(v10 + 12), Sys, 128) )
  {
    v72 = 1;
    GenerateRandomName(v64, (unsigned int)v65);
    goto LABEL_18;
  }
  v87 = -2147024882;
LABEL_104:
  v52 = v86;
LABEL_105:
  if ( tableid != -1 )
    JetCloseTable(*(_DWORD *)(*((_DWORD *)v52 + 2) + 16), tableid);
  if ( v72 != 1 || !v84->uName.ulPropid )
    goto LABEL_111;
  v57 = Sys;
  if ( Sys )
  {
    (*(void (__thiscall **)(_DWORD, int, ULONG))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v84->uName.ulPropid);
LABEL_111:
    v57 = Sys;
  }
  if ( v87 < 0 )
  {
    v58 = v82;
    if ( v82 )
    {
      if ( *v82 )
      {
        v59 = (*v82)->uName.pwszName;
        if ( v59 )
        {
          if ( !v57 )
          {
LABEL_120:
            *v82 = 0;
            v57 = Sys;
            goto LABEL_121;
          }
          (*(void (__thiscall **)(_DWORD, int, LPOLESTR))(*(_DWORD *)v57 + 20))(
            *(_DWORD *)(*(_DWORD *)v57 + 20),
            v57,
            v59);
          v57 = Sys;
          v58 = v82;
        }
        if ( v57 )
          (*(void (__thiscall **)(_DWORD, int, struct tagDBID *))(*(_DWORD *)v57 + 20))(
            *(_DWORD *)(*(_DWORD *)v57 + 20),
            v57,
            *v58);
        goto LABEL_120;
      }
    }
  }
LABEL_121:
  if ( v77 && v57 )
    (*(void (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)v57 + 20))(
      *(_DWORD *)(*(_DWORD *)v57 + 20),
      v57,
      v77);
  if ( v8 )
    LeaveCriticalSection(v8);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v68);
  return v87;
}

```

## disassembly

```asm
0x1001d7f0  mov     edi, edi
0x1001d7f2  push    ebp
0x1001d7f3  mov     ebp, esp
0x1001d7f5  push    0FFFFFFFFh
0x1001d7f7  push    offset ?CreateIndex@CImpIIndexDef@@UAGJPAUtagDBID@@0KQBUtagDBINDEXCOLUMNDESC@@KQAUtagDBPROPSET@@PAPAU2@@Z_SEH
0x1001d7fc  mov     eax, large fs:0
0x1001d802  push    eax
0x1001d803  sub     esp, 7Ch
0x1001d806  mov     eax, ___security_cookie
0x1001d80b  xor     eax, ebp
0x1001d80d  mov     [ebp+var_10], eax
0x1001d810  push    esi; unsigned int
0x1001d811  push    edi; int
0x1001d812  push    eax; struct _GUID *
0x1001d813  lea     eax, [ebp+var_C]
0x1001d816  mov     large fs:0, eax
0x1001d81c  mov     eax, [ebp+arg_4]
0x1001d81f  mov     esi, [ebp+this]
0x1001d822  mov     edi, [ebp+arg_18]
0x1001d825  mov     [ebp+var_4C], eax
0x1001d828  mov     eax, [ebp+arg_8]
0x1001d82b  mov     [ebp+var_38], eax
0x1001d82e  mov     eax, [ebp+arg_10]
0x1001d831  mov     [ebp+var_64], eax
0x1001d834  mov     eax, [ebp+arg_1C]
0x1001d837  mov     [ebp+var_30], esi
0x1001d83a  mov     [ebp+var_3C], edi
0x1001d83d  mov     [ebp+var_40], eax
0x1001d840  mov     dword ptr [ebp+var_44], 0
0x1001d847  mov     [ebp+tableid], 0FFFFFFFFh
0x1001d84e  mov     [ebp+var_54], 0
0x1001d855  mov     [ebp+var_78], 0
0x1001d85c  mov     [ebp+var_74], 0
0x1001d863  mov     [ebp+var_70], 0
0x1001d86a  mov     [ebp+var_7C], offset ??_7CIndexProperties@@6B@; const CIndexProperties::`vftable'
0x1001d871  push    0; perrinfo
0x1001d873  push    0; dwReserved
0x1001d875  mov     [ebp+var_4], 0
0x1001d87c  mov     [ebp+var_68], 0
0x1001d883  mov     [ebp+var_5C], 0
0x1001d88a  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1001d890  mov     esi, [esi+8]
0x1001d893  add     esi, 68h ; 'h'
0x1001d896  push    esi; lpCriticalSection
0x1001d897  mov     [ebp+var_84], esi
0x1001d89d  mov     [ebp+var_88], esi
0x1001d8a3  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001d8a9  mov     eax, [ebp+var_40]
0x1001d8ac  mov     byte ptr [ebp+var_4], 1
0x1001d8b0  test    eax, eax
0x1001d8b2  jz      short loc_1001D8BA
0x1001d8b4  mov     dword ptr [eax], 0
0x1001d8ba  cmp     [ebp+var_4C], 0
0x1001d8be  jz      loc_1001DDEC
0x1001d8c4  cmp     [ebp+var_38], 0
0x1001d8c8  jnz     short loc_1001D8D2
0x1001d8ca  test    eax, eax
0x1001d8cc  jz      loc_1001DDEC
0x1001d8d2  cmp     [ebp+arg_C], 0
0x1001d8d6  jz      loc_1001DDEC
0x1001d8dc  cmp     [ebp+var_64], 0
0x1001d8e0  jz      loc_1001DDEC
0x1001d8e6  mov     edx, [ebp+arg_14]
0x1001d8e9  test    edx, edx
0x1001d8eb  jz      short loc_1001D8F5
0x1001d8ed  test    edi, edi
0x1001d8ef  jz      loc_1001DDEC
0x1001d8f5  xor     ecx, ecx
0x1001d8f7  test    edx, edx
0x1001d8f9  jz      short loc_1001D919
0x1001d8fb  nop     dword ptr [eax+eax+00h]
0x1001d900  lea     eax, [ecx+ecx*2]
0x1001d903  cmp     dword ptr [edi+eax*8], 0
0x1001d907  jnz     short loc_1001D914
0x1001d909  cmp     dword ptr [edi+eax*8+4], 0
0x1001d90e  jnz     loc_1001DDEC
0x1001d914  inc     ecx
0x1001d915  cmp     ecx, edx
0x1001d917  jb      short loc_1001D900
0x1001d919  cmp     [ebp+var_38], 0
0x1001d91d  jnz     short loc_1001D968
0x1001d91f  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1001d925  lea     eax, [ebp+var_28]
0x1001d928  mov     [ebp+var_38], eax
0x1001d92b  push    80h
0x1001d930  push    ecx
0x1001d931  mov     eax, [ecx]
0x1001d933  mov     [ebp+var_18], 2
0x1001d93a  mov     edi, [eax+0Ch]
0x1001d93d  mov     ecx, edi
0x1001d93f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001d945  call    edi
0x1001d947  mov     [ebp+var_14], eax
0x1001d94a  test    eax, eax
0x1001d94c  jnz     short loc_1001D95A
0x1001d94e  mov     [ebp+var_2C], 8007000Eh
0x1001d955  jmp     loc_1001DE21
0x1001d95a  mov     ecx, eax
0x1001d95c  mov     [ebp+var_68], 1
0x1001d963  call    ?GenerateRandomName@@YGJPAGK@Z; GenerateRandomName(ushort *,ulong)
0x1001d968  mov     ecx, [ebp+var_4C]
0x1001d96b  mov     edx, offset _DB_NULLID
0x1001d970  mov     edi, 14h
0x1001d975  mov     eax, [ecx]
0x1001d977  cmp     eax, [edx]
0x1001d979  jnz     short loc_1001D990
0x1001d97b  add     ecx, 4
0x1001d97e  add     edx, 4
0x1001d981  sub     edi, 4
0x1001d984  jnb     short loc_1001D975
0x1001d986  mov     edi, 80040E37h
0x1001d98b  jmp     loc_1001DDF1
0x1001d990  mov     eax, [ebp+var_4C]
0x1001d993  cmp     dword ptr [eax+10h], 2
0x1001d997  jnz     short loc_1001D986
0x1001d999  cmp     dword ptr [eax+14h], 0
0x1001d99d  jz      short loc_1001D986
0x1001d99f  mov     eax, [ebp+var_38]
0x1001d9a2  cmp     dword ptr [eax+10h], 2
0x1001d9a6  jnz     loc_1001DDE5
0x1001d9ac  cmp     dword ptr [eax+14h], 0
0x1001d9b0  jz      loc_1001DDE5
0x1001d9b6  cmp     [ebp+var_40], 0
0x1001d9ba  jz      loc_1001DA66
0x1001d9c0  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1001d9c6  push    18h
0x1001d9c8  push    ecx
0x1001d9c9  mov     eax, [ecx]
0x1001d9cb  mov     edi, [eax+0Ch]
0x1001d9ce  mov     ecx, edi
0x1001d9d0  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001d9d6  call    edi
0x1001d9d8  mov     edx, eax
0x1001d9da  mov     eax, [ebp+var_40]
0x1001d9dd  mov     [eax], edx
0x1001d9df  test    edx, edx
0x1001d9e1  jnz     short loc_1001D9EF
0x1001d9e3  mov     [ebp+var_2C], 8007000Eh
0x1001d9ea  jmp     loc_1001DE21
0x1001d9ef  mov     eax, [ebp+var_38]
0x1001d9f2  mov     ecx, [eax+14h]
0x1001d9f5  lea     edi, [ecx+2]
0x1001d9f8  nop     dword ptr [eax+eax+00000000h]
0x1001da00  mov     ax, [ecx]
0x1001da03  add     ecx, 2
0x1001da06  test    ax, ax
0x1001da09  jnz     short loc_1001DA00
0x1001da0b  sub     ecx, edi
0x1001da0d  mov     dword ptr [edx+10h], 2
0x1001da14  sar     ecx, 1
0x1001da16  lea     eax, ds:2[ecx*2]
0x1001da1d  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1001da23  mov     [ebp+var_34], eax
0x1001da26  push    [ebp+var_34]
0x1001da29  mov     eax, [ecx]
0x1001da2b  push    ecx
0x1001da2c  mov     edi, [eax+0Ch]
0x1001da2f  mov     ecx, edi
0x1001da31  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001da37  call    edi
0x1001da39  mov     edx, [ebp+var_40]
0x1001da3c  mov     ecx, eax
0x1001da3e  mov     eax, [edx]
0x1001da40  mov     [eax+14h], ecx
0x1001da43  mov     eax, [edx]
0x1001da45  mov     ecx, [eax+14h]
0x1001da48  test    ecx, ecx
0x1001da4a  jnz     short loc_1001DA58
0x1001da4c  mov     [ebp+var_2C], 8007000Eh
0x1001da53  jmp     loc_1001DE21
0x1001da58  mov     eax, [ebp+var_38]
0x1001da5b  push    [ebp+var_34]; unsigned __int16 *
0x1001da5e  mov     edx, [eax+14h]
0x1001da61  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x1001da66  lea     ecx, [ebp+var_7C]; this
0x1001da69  call    ?FInit@CIndexProperties@@QAEJXZ; CIndexProperties::FInit(void)
0x1001da6e  mov     edi, eax
0x1001da70  mov     [ebp+var_2C], edi
0x1001da73  test    edi, edi
0x1001da75  js      loc_1001DDCF
0x1001da7b  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; struct DBInfoProps *
0x1001da80  lea     ecx, [ebp+var_7C]; this
0x1001da83  call    ?CopyPropertiesFromStaticTable@CIndexProperties@@QAEJPBUDBInfoProps@@@Z; CIndexProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)
0x1001da88  mov     edi, eax
0x1001da8a  mov     [ebp+var_2C], edi
0x1001da8d  test    edi, edi
0x1001da8f  js      loc_1001DDCF
0x1001da95  push    0; struct CDBSession *
0x1001da97  push    [ebp+var_3C]; struct tagDBPROPSET *
0x1001da9a  lea     ecx, [ebp+var_7C]; this
0x1001da9d  push    [ebp+arg_14]; unsigned int
0x1001daa0  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x1001daa5  mov     edi, eax
0x1001daa7  mov     [ebp+var_2C], edi
0x1001daaa  test    edi, edi
0x1001daac  js      loc_1001DDCF
0x1001dab2  xor     eax, eax
0x1001dab4  cmp     edi, 40EDAh
0x1001daba  mov     edi, [ebp+var_74]
0x1001dabd  mov     ecx, edi; this
0x1001dabf  setz    al
0x1001dac2  push    36h ; '6'; unsigned int
0x1001dac4  mov     [ebp+var_58], eax
0x1001dac7  call    ?IsbPropertySet@JoltProperties@@QBEHK@Z; JoltProperties::IsbPropertySet(ulong)
0x1001dacc  push    39h ; '9'; unsigned int
0x1001dace  mov     ecx, edi; this
0x1001dad0  mov     [ebp+var_34], eax
0x1001dad3  call    ?IsbPropertySet@JoltProperties@@QBEHK@Z; JoltProperties::IsbPropertySet(ulong)
0x1001dad8  cmp     [ebp+var_34], 1
0x1001dadc  mov     ecx, [ebp+var_58]
0x1001dadf  mov     [ebp+var_48], eax
0x1001dae2  mov     [ebp+var_50], ecx
0x1001dae5  jnz     short loc_1001DB59
0x1001dae7  mov     [ebp+var_50], ecx
0x1001daea  test    eax, eax
0x1001daec  jnz     short loc_1001DB59
0x1001daee  mov     [ebp+var_50], ecx
0x1001daf1  mov     ecx, edi; this
0x1001daf3  push    39h ; '9'; unsigned int
0x1001daf5  call    ?GetRowbyProp@JoltProperties@@QBEPAVJoltProperty@@K@Z; JoltProperties::GetRowbyProp(ulong)
0x1001dafa  test    dword ptr [eax+28h], 1
0x1001db01  jz      short loc_1001DB59
0x1001db03  movups  xmm0, xmmword ptr ds:_DBPROPSET_INDEX.Data1
0x1001db0a  push    8
0x1001db0c  push    [ebp+var_3C]
0x1001db0f  lea     edx, [ebp+var_7C]
0x1001db12  mov     ecx, 39h ; '9'
0x1001db17  push    [ebp+arg_14]
0x1001db1a  push    0; unsigned __int16 *
0x1001db1c  sub     esp, 10h
0x1001db1f  mov     eax, esp
0x1001db21  movups  xmmword ptr [eax], xmm0
0x1001db24  call    ?HandleInvalidPropertyValue@@YGJKU_GUID@@AAVCSettableProperties@@PAVCCommand@@KQAUtagDBPROPSET@@K@Z; HandleInvalidPropertyValue(ulong,_GUID,CSettableProperties &,CCommand *,ulong,tagDBPROPSET * const,ulong)
0x1001db29  mov     edi, eax
0x1001db2b  mov     [ebp+var_2C], edi
0x1001db2e  test    edi, edi
0x1001db30  js      loc_1001DDCF
0x1001db36  mov     edi, [ebp+var_74]
0x1001db39  mov     ecx, edi; this
0x1001db3b  push    39h ; '9'; unsigned int
0x1001db3d  call    ?GetRowbyProp@JoltProperties@@QBEPAVJoltProperty@@K@Z; JoltProperties::GetRowbyProp(ulong)
0x1001db42  test    byte ptr [eax+28h], 2
0x1001db46  jz      short loc_1001DB52
0x1001db48  mov     edi, 80040E21h
0x1001db4d  jmp     loc_1001DDF1
0x1001db52  mov     [ebp+var_50], 1
0x1001db59  xor     ecx, ecx
0x1001db5b  mov     eax, 2
0x1001db60  cmp     [ebp+var_34], 1
0x1001db64  cmovnz  eax, ecx
0x1001db67  mov     ecx, eax
0x1001db69  or      ecx, 1
0x1001db6c  cmp     [ebp+var_48], 1
0x1001db70  cmovnz  ecx, eax
0x1001db73  lea     eax, [ebp+var_48]
0x1001db76  push    eax; unsigned int *
0x1001db77  mov     [ebp+var_3C], ecx
0x1001db7a  mov     ecx, edi; this
0x1001db7c  push    35h ; '5'; unsigned int
0x1001db7e  call    ?GetIntValue@JoltProperties@@QBEJKAAK@Z; JoltProperties::GetIntValue(ulong,ulong &)
0x1001db83  mov     edi, eax
0x1001db85  mov     [ebp+var_2C], edi
0x1001db88  test    edi, edi
0x1001db8a  js      loc_1001DDCF
0x1001db90  mov     eax, [ebp+var_48]
0x1001db93  cmp     eax, 1
0x1001db96  jnz     short loc_1001DB9E
0x1001db98  or      [ebp+var_3C], 4
0x1001db9c  jmp     short loc_1001DBA7
0x1001db9e  cmp     eax, 2
0x1001dba1  jnz     short loc_1001DBA7
0x1001dba3  or      [ebp+var_3C], 8
0x1001dba7  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1001dbad  imul    edx, [ebp+arg_C], 84h
0x1001dbb4  mov     eax, [ecx]
0x1001dbb6  add     edx, 2
0x1001dbb9  push    edx
0x1001dbba  mov     edi, [eax+0Ch]
0x1001dbbd  push    ecx
0x1001dbbe  mov     ecx, edi
0x1001dbc0  mov     [ebp+var_48], edx
0x1001dbc3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001dbc9  call    edi
0x1001dbcb  mov     [ebp+var_54], eax
0x1001dbce  test    eax, eax
0x1001dbd0  jnz     short loc_1001DBDE
0x1001dbd2  mov     [ebp+var_2C], 8007000Eh
0x1001dbd9  jmp     loc_1001DE21
0x1001dbde  mov     ecx, eax
0x1001dbe0  xor     eax, eax
0x1001dbe2  mov     [ebp+var_58], eax
0x1001dbe5  cmp     [ebp+arg_C], eax
0x1001dbe8  jbe     loc_1001DD0F
0x1001dbee  mov     edi, edi
0x1001dbf0  mov     edx, [ebp+var_64]
0x1001dbf3  mov     edi, [edx+eax*8]
0x1001dbf6  mov     eax, [edx+eax*8+4]
0x1001dbfa  mov     [ebp+var_6C], edi
0x1001dbfd  test    edi, edi
0x1001dbff  jz      loc_1001DD83
  ... truncated ...
```
