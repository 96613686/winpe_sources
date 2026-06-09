# CImpIRowsetIndex::GetIndexInfo(ulong *,tagDBINDEXCOLUMNDESC * *,ulong *,tagDBPROPSET * *)

- ea: `0x1002ef90`
- end: `0x1002f655`
- name: `?GetIndexInfo@CImpIRowsetIndex@@UAGJPAKPAPAUtagDBINDEXCOLUMNDESC@@0PAPAUtagDBPROPSET@@@Z`
- size: `1733`
- prototype: `int(CImpIRowsetIndex *__hidden this, unsigned int *, struct tagDBINDEXCOLUMNDESC **, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation`

## callees

- `0x1000ba90`
- `0x1000d4a0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1002ef90`
- `0x100495b0`
- `0x1004c660`
- `0x1004d406`
- `0x1004d420`
- `0x1004d5a1`
- `0x1004dc8d`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1002f61f`
- `KERNEL32!LeaveCriticalSection` at `0x1002f61f`
- `KERNEL32!EnterCriticalSection` at `0x1002f0db`
- `KERNEL32!EnterCriticalSection` at `0x1002f0db`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1002f020`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1002f020`
- `msjet40!__imp__JetCloseTable@8` at `0x1002f614`
- `msjet40!__imp__JetCloseTable@8` at `0x1002f614`
- `msjet40!__imp__JetGetCurrentIndex@16` at `0x1002f13a`
- `msjet40!__imp__JetGetCurrentIndex@16` at `0x1002f13a`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1002f531`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1002f531`
- `msjet40!__imp__JetGetTableIndexInfo@24` at `0x1002f178`
- `msjet40!__imp__JetGetTableIndexInfo@24` at `0x1002f178`
- `msjet40!__imp__JetMove@16` at `0x1002f3bd`
- `msjet40!__imp__JetMove@16` at `0x1002f3bd`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002f1b3`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002f26d`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002f380`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002f1b3`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002f26d`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002f380`

## pseudocode

```c
int __stdcall CImpIRowsetIndex::GetIndexInfo(
        CImpIRowsetIndex *this,
        unsigned int *a2,
        struct tagDBINDEXCOLUMNDESC **a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  int Properties; // edi
  int v6; // eax
  JET_SESID v7; // ecx
  unsigned int *v8; // eax
  struct _RTL_CRITICAL_SECTION *v9; // esi
  struct _RTL_CRITICAL_SECTION *v10; // edx
  _DWORD *LockSemaphore; // eax
  CTransactionState *v12; // ecx
  int isZombie; // eax
  JET_ERR CurrentIndex; // eax
  bool v15; // zf
  JET_TABLEID v16; // ecx
  int v17; // eax
  struct tagDBINDEXCOLUMNDESC **v18; // edx
  unsigned int *v19; // edi
  unsigned int v20; // ecx
  unsigned int i; // eax
  int v22; // eax
  unsigned int v23; // kr00_4
  int v24; // ecx
  unsigned __int16 *v25; // ecx
  unsigned __int16 *v26; // eax
  DBPROPID v27; // edx
  DBPROPID *rgPropertyIDs; // eax
  struct tagDBPROPIDSET *v29; // esi
  _DWORD *v30; // ecx
  struct tagDBINDEXCOLUMNDESC **v31; // eax
  unsigned int v32; // edx
  int v33; // eax
  struct tagDBINDEXCOLUMNDESC **v34; // esi
  unsigned int *v35; // ecx
  unsigned __int16 *v37; // [esp+0h] [ebp-134h]
  const struct _GUID *v38; // [esp+4h] [ebp-130h]
  int v39; // [esp+Ch] [ebp-128h] BYREF
  struct _RTL_CRITICAL_SECTION *v40; // [esp+10h] [ebp-124h]
  unsigned int *v41; // [esp+14h] [ebp-120h] BYREF
  unsigned int pcbActual; // [esp+18h] [ebp-11Ch] BYREF
  struct _RTL_CRITICAL_SECTION *v43; // [esp+1Ch] [ebp-118h]
  int pvData; // [esp+20h] [ebp-114h] BYREF
  unsigned int v45; // [esp+24h] [ebp-110h]
  int v46; // [esp+28h] [ebp-10Ch]
  DBID *v47; // [esp+2Ch] [ebp-108h]
  CImpIRowsetIndex *v48; // [esp+30h] [ebp-104h]
  struct tagDBPROPIDSET *v49; // [esp+34h] [ebp-100h]
  JET_SESID sesid; // [esp+38h] [ebp-FCh]
  JET_ERR v51; // [esp+3Ch] [ebp-F8h]
  unsigned int *v52; // [esp+40h] [ebp-F4h]
  struct tagDBINDEXCOLUMNDESC **v53; // [esp+44h] [ebp-F0h]
  unsigned __int16 *v54; // [esp+48h] [ebp-ECh]
  int v55; // [esp+4Ch] [ebp-E8h]
  int v56; // [esp+50h] [ebp-E4h]
  GUID v57; // [esp+54h] [ebp-E0h]
  JET_TABLEID v58[15]; // [esp+64h] [ebp-D0h] BYREF
  unsigned __int16 v59[66]; // [esp+A0h] [ebp-94h] BYREF
  int v60; // [esp+130h] [ebp-4h]

  Properties = 0;
  v52 = a2;
  v53 = a3;
  v45 = (unsigned int)a4;
  v49 = (struct tagDBPROPIDSET *)a5;
  v48 = this;
  v54 = 0;
  memset(v58, 0, sizeof(v58));
  v6 = *(_DWORD *)(*((_DWORD *)this + 2) + 56);
  v7 = *(_DWORD *)(v6 + 16);
  v8 = *(unsigned int **)(v6 + 84);
  sesid = v7;
  v41 = v8;
  SetErrorInfo(0, 0);
  v9 = 0;
  v43 = 0;
  v40 = 0;
  v60 = 0;
  if ( a2 )
    *v52 = 0;
  if ( v53 )
    *v53 = 0;
  if ( v45 )
    *(_DWORD *)v45 = 0;
  if ( v49 )
    v49->rgPropertyIDs = 0;
  v10 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)v48 + 2);
  LockSemaphore = v10[2].LockSemaphore;
  if ( !LockSemaphore
    || (LockSemaphore[4] != 1 || (v12 = (CTransactionState *)LockSemaphore[2]) == 0
      ? (isZombie = LockSemaphore[3])
      : (isZombie = CTransactionState::isZombie(v12)),
        isZombie != 1) )
  {
    if ( v10[4].SpinCount || v10[9].SpinCount )
    {
      if ( ((int)v10[4].DebugInfo & 0x400) != 0 )
      {
        Properties = -2147217888;
        goto LABEL_65;
      }
      v9 = v10 + 3;
      v43 = v10 + 3;
      v40 = v10 + 3;
      EnterCriticalSection(v10 + 3);
      if ( !v52 || !v53 || !v45 || !v49 )
      {
        Properties = -2147024809;
        goto LABEL_65;
      }
      v58[1] = -1;
      CurrentIndex = JetGetCurrentIndex(sesid, *(_DWORD *)(*((_DWORD *)v48 + 2) + 108), v59, 65);
      if ( CurrentIndex >= 0 )
      {
        CurrentIndex = JetGetTableIndexInfo(sesid, *(_DWORD *)(*((_DWORD *)v48 + 2) + 108), v59, v58, 60, 1);
        if ( CurrentIndex >= 0 )
        {
          CurrentIndex = JetRetrieveColumn(sesid, v58[1], v58[4], &pvData, 4u, 0, 0, 0);
          v51 = CurrentIndex;
          v15 = CurrentIndex == 0;
          if ( CurrentIndex >= 0 )
          {
            v16 = v58[2];
            *v52 = v58[2];
            v17 = (*(int (__thiscall **)(_DWORD, int, JET_TABLEID))(*(_DWORD *)Sys + 12))(
                    *(_DWORD *)(*(_DWORD *)Sys + 12),
                    Sys,
                    8 * v16);
            v18 = v53;
            *v53 = (struct tagDBINDEXCOLUMNDESC *)v17;
            if ( v17 )
            {
              v19 = v52;
              v20 = 0;
              for ( i = *v52; v20 < *v19; i = *v19 )
                (*v18)[v20++].pColumnID = 0;
              v46 = 0;
              if ( i )
              {
                Properties = 0;
                do
                {
                  CurrentIndex = JetRetrieveColumn(sesid, v58[1], v58[14], v59, 0x82u, &pcbActual, 0, 0);
                  v51 = CurrentIndex;
                  if ( CurrentIndex < 0 )
                    goto LABEL_61;
                  if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
                    __report_rangecheckfailure();
                  *(unsigned __int16 *)((char *)v59 + (pcbActual & 0xFFFFFFFE)) = 0;
                  v22 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          24);
                  v47 = (DBID *)v22;
                  if ( !v22 )
                    goto LABEL_30;
                  *(_DWORD *)(v22 + 16) = 2;
                  v23 = wcslen(v59);
                  v24 = *(_DWORD *)Sys;
                  v54 = (unsigned __int16 *)(2 * v23 + 2);
                  v25 = (unsigned __int16 *)(*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(v24 + 12))(
                                              *(_DWORD *)(v24 + 12),
                                              Sys,
                                              v54);
                  v47->uName.ulPropid = (ULONG)v25;
                  if ( !v25 )
                    goto LABEL_30;
                  v26 = WCSCPY(v59, v25, v54, v37, (unsigned int)v38);
                  Properties = -2147467259;
                  if ( v26 )
                    Properties = 0;
                  v54 = (unsigned __int16 *)Properties;
                  if ( !v26 )
                    goto LABEL_59;
                  (*v53)[v46].pColumnID = v47;
                  CurrentIndex = JetRetrieveColumn(sesid, v58[1], v58[13], &v39, 4u, &pcbActual, 0, 0);
                  if ( CurrentIndex < 0 )
                    goto LABEL_61;
                  (*v53)[v46].eIndexColOrder = v39 != 0;
                  v51 = JetMove(sesid, v58[1], 1, 0);
                }
                while ( ++v46 < *v52 );
              }
              v55 = 0;
              v56 = 0;
              v57 = DBPROPSET_INDEX;
              Properties = GenericGetProperties(
                             v45,
                             v49,
                             v41,
                             0,
                             (struct CDataSource *)0x20,
                             (struct CSettableProperties *)v37,
                             (unsigned int)v38);
              v54 = (unsigned __int16 *)Properties;
              if ( Properties >= 0 )
              {
                v27 = 0;
                rgPropertyIDs = v49->rgPropertyIDs;
                if ( v49->rgPropertyIDs[1] )
                {
                  v29 = v49;
                  do
                  {
                    v30 = (_DWORD *)(*rgPropertyIDs + 52 * v27);
                    switch ( *v30 )
                    {
                      case '5':
                        if ( (pvData & 4) != 0 )
                        {
                          v30[11] = 1;
                        }
                        else if ( (pvData & 8) != 0 )
                        {
                          v30[11] = 2;
                        }
                        else
                        {
                          v30[11] = ((unsigned __int8)pvData >> 3) & 4;
                        }
                        break;
                      case '6':
                        *((_WORD *)v30 + 22) = -((pvData & 2) != 0);
                        break;
                      case '9':
                        *((_WORD *)v30 + 22) = -((pvData & 1) != 0);
                        break;
                    }
                    rgPropertyIDs = v29->rgPropertyIDs;
                    ++v27;
                  }
                  while ( v27 < v29->rgPropertyIDs[1] );
                  v9 = v43;
                }
              }
            }
            else
            {
LABEL_30:
              Properties = -2147024882;
              v54 = (unsigned __int16 *)-2147024882;
            }
LABEL_59:
            CurrentIndex = v51;
            v15 = v51 == 0;
          }
          if ( v15 )
          {
            if ( Properties >= 0 )
              goto LABEL_85;
            goto LABEL_66;
          }
        }
        else
        {
          Properties = -2147467259;
          v54 = (unsigned __int16 *)-2147467259;
        }
      }
      else
      {
        Properties = -2147467259;
        v54 = (unsigned __int16 *)-2147467259;
      }
LABEL_61:
      CExtError::SendJetErrortoOLEAuto(
        Properties,
        *(char **)(*(_DWORD *)(*((_DWORD *)v48 + 2) + 56) + 16),
        CurrentIndex,
        (int)&IID_IRowsetIndex,
        (int)v37,
        v38);
      goto LABEL_69;
    }
  }
  Properties = -2147418113;
LABEL_65:
  v54 = (unsigned __int16 *)Properties;
LABEL_66:
  if ( Properties != -2147024882
    && !JetGetDatabaseInfo(
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v48 + 2) + 56) + 16),
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v48 + 2) + 56) + 20),
          &v41,
          4,
          3) )
  {
    CExtError::SendHRtoOLEAuto(Properties, (__int128 *)&IID_IRowsetIndex, 0, (const struct _GUID *)v37, (int)v38);
  }
LABEL_69:
  if ( Properties >= 0 )
    goto LABEL_85;
  v31 = v53;
  if ( v53 && *v53 )
  {
    v32 = 0;
    v47 = 0;
    v33 = Sys;
    if ( *v52 )
    {
      v34 = v53;
      do
      {
        if ( (*v34)[v32].pColumnID && v33 )
        {
          (*(void (__thiscall **)(_DWORD, int, DBID *))(*(_DWORD *)v33 + 20))(
            *(_DWORD *)(*(_DWORD *)v33 + 20),
            v33,
            (*v34)[v32].pColumnID);
          v33 = Sys;
          v32 = (unsigned int)v47;
        }
        v47 = (DBID *)++v32;
      }
      while ( v32 < *v52 );
      v9 = v43;
    }
    if ( v33 )
      (*(void (__thiscall **)(_DWORD, int, struct tagDBINDEXCOLUMNDESC *))(*(_DWORD *)v33 + 20))(
        *(_DWORD *)(*(_DWORD *)v33 + 20),
        v33,
        *v53);
    v35 = v52;
    v31 = v53;
    goto LABEL_82;
  }
  v35 = v52;
  if ( v52 )
  {
LABEL_82:
    Properties = (int)v54;
    *v35 = 0;
  }
  if ( v31 )
    *v31 = 0;
LABEL_85:
  if ( v58[1] != -1 )
    JetCloseTable(sesid, v58[1]);
  if ( v9 )
    LeaveCriticalSection(v9);
  return Properties;
}

```

## disassembly

```asm
0x1002ef90  mov     edi, edi
0x1002ef92  push    ebp
0x1002ef93  mov     ebp, esp
0x1002ef95  push    0FFFFFFFFh
0x1002ef97  push    offset ?GetIndexInfo@CImpIRowsetIndex@@UAGJPAKPAPAUtagDBINDEXCOLUMNDESC@@0PAPAUtagDBPROPSET@@@Z_SEH
0x1002ef9c  mov     eax, large fs:0
0x1002efa2  push    eax
0x1002efa3  sub     esp, 11Ch
0x1002efa9  mov     eax, ___security_cookie
0x1002efae  xor     eax, ebp
0x1002efb0  mov     [ebp+var_10], eax
0x1002efb3  push    esi
0x1002efb4  push    edi; int
0x1002efb5  push    eax; struct _GUID *
0x1002efb6  lea     eax, [ebp+var_C]
0x1002efb9  mov     large fs:0, eax
0x1002efbf  mov     eax, [ebp+arg_4]
0x1002efc2  xor     edi, edi
0x1002efc4  mov     esi, [ebp+this]
0x1002efc7  mov     [ebp+var_F4], eax
0x1002efcd  mov     eax, [ebp+arg_8]
0x1002efd0  mov     [ebp+var_F0], eax
0x1002efd6  mov     eax, [ebp+arg_C]
0x1002efd9  mov     [ebp+var_110], eax
0x1002efdf  mov     eax, [ebp+arg_10]
0x1002efe2  push    3Ch ; '<'; Size
0x1002efe4  mov     [ebp+var_100], eax
0x1002efea  lea     eax, [ebp+var_D0]
0x1002eff0  push    edi; Val
0x1002eff1  push    eax; void *
0x1002eff2  mov     [ebp+var_104], esi
0x1002eff8  mov     [ebp+var_EC], edi
0x1002effe  call    _memset
0x1002f003  mov     eax, [esi+8]
0x1002f006  add     esp, 0Ch
0x1002f009  mov     eax, [eax+38h]
0x1002f00c  push    edi; perrinfo
0x1002f00d  push    edi; dwReserved
0x1002f00e  mov     ecx, [eax+10h]
0x1002f011  mov     eax, [eax+54h]
0x1002f014  mov     [ebp+sesid], ecx
0x1002f01a  mov     [ebp+var_120], eax
0x1002f020  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1002f026  xor     esi, esi
0x1002f028  mov     [ebp+var_118], esi
0x1002f02e  mov     [ebp+var_124], esi
0x1002f034  mov     eax, [ebp+var_F4]
0x1002f03a  mov     [ebp+var_4], esi
0x1002f03d  test    eax, eax
0x1002f03f  jz      short loc_1002F043
0x1002f041  mov     [eax], esi
0x1002f043  mov     edx, [ebp+var_F0]
0x1002f049  test    edx, edx
0x1002f04b  jz      short loc_1002F053
0x1002f04d  mov     dword ptr [edx], 0
0x1002f053  mov     eax, [ebp+var_110]
0x1002f059  test    eax, eax
0x1002f05b  jz      short loc_1002F063
0x1002f05d  mov     dword ptr [eax], 0
0x1002f063  mov     eax, [ebp+var_100]
0x1002f069  test    eax, eax
0x1002f06b  jz      short loc_1002F073
0x1002f06d  mov     dword ptr [eax], 0
0x1002f073  mov     edx, [ebp+var_104]
0x1002f079  mov     edx, [edx+8]
0x1002f07c  mov     eax, [edx+40h]
0x1002f07f  test    eax, eax
0x1002f081  jz      short loc_1002F09F
0x1002f083  cmp     dword ptr [eax+10h], 1
0x1002f087  jnz     short loc_1002F097
0x1002f089  mov     ecx, [eax+8]; this
0x1002f08c  test    ecx, ecx
0x1002f08e  jz      short loc_1002F097
0x1002f090  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x1002f095  jmp     short loc_1002F09A
0x1002f097  mov     eax, [eax+0Ch]
0x1002f09a  cmp     eax, 1
0x1002f09d  jz      short loc_1002F0AE
0x1002f09f  cmp     dword ptr [edx+74h], 0
0x1002f0a3  jnz     short loc_1002F0B8
0x1002f0a5  cmp     dword ptr [edx+0ECh], 0
0x1002f0ac  jnz     short loc_1002F0B8
0x1002f0ae  mov     edi, 8000FFFFh
0x1002f0b3  jmp     loc_1002F506
0x1002f0b8  test    dword ptr [edx+60h], 400h
0x1002f0bf  jz      short loc_1002F0CB
0x1002f0c1  mov     edi, 80040E20h
0x1002f0c6  jmp     loc_1002F506
0x1002f0cb  lea     esi, [edx+48h]
0x1002f0ce  push    esi; lpCriticalSection
0x1002f0cf  mov     [ebp+var_118], esi
0x1002f0d5  mov     [ebp+var_124], esi
0x1002f0db  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1002f0e1  cmp     [ebp+var_F4], 0
0x1002f0e8  jz      loc_1002F501
0x1002f0ee  cmp     [ebp+var_F0], 0
0x1002f0f5  jz      loc_1002F501
0x1002f0fb  cmp     [ebp+var_110], 0
0x1002f102  jz      loc_1002F501
0x1002f108  cmp     [ebp+var_100], 0
0x1002f10f  jz      loc_1002F501
0x1002f115  push    41h ; 'A'
0x1002f117  lea     eax, [ebp+var_94]
0x1002f11d  mov     [ebp+tableid], 0FFFFFFFFh
0x1002f127  push    eax
0x1002f128  mov     eax, [ebp+var_104]
0x1002f12e  mov     eax, [eax+8]
0x1002f131  push    dword ptr [eax+6Ch]
0x1002f134  push    [ebp+sesid]
0x1002f13a  call    ds:__imp__JetGetCurrentIndex@16; JetGetCurrentIndex(x,x,x,x)
0x1002f140  test    eax, eax
0x1002f142  jns     short loc_1002F154
0x1002f144  mov     edi, 80004005h
0x1002f149  mov     [ebp+var_EC], edi
0x1002f14f  jmp     loc_1002F4D9
0x1002f154  push    1
0x1002f156  push    3Ch ; '<'
0x1002f158  lea     eax, [ebp+var_D0]
0x1002f15e  push    eax
0x1002f15f  lea     eax, [ebp+var_94]
0x1002f165  push    eax
0x1002f166  mov     eax, [ebp+var_104]
0x1002f16c  mov     eax, [eax+8]
0x1002f16f  push    dword ptr [eax+6Ch]
0x1002f172  push    [ebp+sesid]
0x1002f178  call    ds:__imp__JetGetTableIndexInfo@24; JetGetTableIndexInfo(x,x,x,x,x,x)
0x1002f17e  test    eax, eax
0x1002f180  jns     short loc_1002F192
0x1002f182  mov     edi, 80004005h
0x1002f187  mov     [ebp+var_EC], edi
0x1002f18d  jmp     loc_1002F4D9
0x1002f192  push    0; pretinfo
0x1002f194  push    0; grbit
0x1002f196  push    0; pcbActual
0x1002f198  push    4; cbData
0x1002f19a  lea     eax, [ebp+pvData]
0x1002f1a0  push    eax; pvData
0x1002f1a1  push    [ebp+columnid]; columnid
0x1002f1a7  push    [ebp+tableid]; tableid
0x1002f1ad  push    [ebp+sesid]; sesid
0x1002f1b3  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002f1b9  mov     [ebp+var_F8], eax
0x1002f1bf  test    eax, eax
0x1002f1c1  js      loc_1002F4D7
0x1002f1c7  mov     eax, [ebp+var_F4]
0x1002f1cd  mov     ecx, [ebp+var_C8]
0x1002f1d3  mov     [eax], ecx
0x1002f1d5  mov     edx, ?Sys@@3VSystem@@A; System Sys
0x1002f1db  mov     eax, [edx]
0x1002f1dd  mov     edi, [eax+0Ch]
0x1002f1e0  lea     eax, ds:0[ecx*8]
0x1002f1e7  push    eax
0x1002f1e8  push    edx
0x1002f1e9  mov     ecx, edi
0x1002f1eb  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002f1f1  call    edi
0x1002f1f3  mov     edx, [ebp+var_F0]
0x1002f1f9  mov     [edx], eax
0x1002f1fb  test    eax, eax
0x1002f1fd  jnz     short loc_1002F20F
0x1002f1ff  mov     edi, 8007000Eh
0x1002f204  mov     [ebp+var_EC], edi
0x1002f20a  jmp     loc_1002F4CF
0x1002f20f  mov     edi, [ebp+var_F4]
0x1002f215  xor     ecx, ecx
0x1002f217  mov     eax, [edi]
0x1002f219  test    eax, eax
0x1002f21b  jz      short loc_1002F230
0x1002f21d  nop     dword ptr [eax]
0x1002f220  mov     eax, [edx]
0x1002f222  mov     dword ptr [eax+ecx*8], 0
0x1002f229  inc     ecx
0x1002f22a  mov     eax, [edi]
0x1002f22c  cmp     ecx, eax
0x1002f22e  jb      short loc_1002F220
0x1002f230  mov     [ebp+var_10C], 0
0x1002f23a  test    eax, eax
0x1002f23c  jz      loc_1002F3E4
0x1002f242  xor     edi, edi
0x1002f244  push    0; pretinfo
0x1002f246  push    0; grbit
0x1002f248  lea     eax, [ebp+pcbActual]
0x1002f24e  push    eax; pcbActual
0x1002f24f  push    82h; cbData
0x1002f254  lea     eax, [ebp+var_94]
0x1002f25a  push    eax; pvData
0x1002f25b  push    [ebp+var_98]; columnid
0x1002f261  push    [ebp+tableid]; tableid
0x1002f267  push    [ebp+sesid]; sesid
0x1002f26d  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002f273  mov     [ebp+var_F8], eax
0x1002f279  test    eax, eax
0x1002f27b  js      loc_1002F4D9
0x1002f281  mov     eax, [ebp+pcbActual]
0x1002f287  and     eax, 0FFFFFFFEh
0x1002f28a  cmp     eax, 82h
0x1002f28f  jnb     loc_1002F650
0x1002f295  xor     ecx, ecx
0x1002f297  mov     [ebp+eax+var_94], cx
0x1002f29f  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1002f2a5  push    18h
0x1002f2a7  push    ecx
0x1002f2a8  mov     eax, [ecx]
0x1002f2aa  mov     edi, [eax+0Ch]
0x1002f2ad  mov     ecx, edi
0x1002f2af  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002f2b5  call    edi
0x1002f2b7  mov     [ebp+var_108], eax
0x1002f2bd  test    eax, eax
0x1002f2bf  jz      loc_1002F1FF
0x1002f2c5  lea     ecx, [ebp+var_94]
0x1002f2cb  mov     dword ptr [eax+10h], 2
0x1002f2d2  lea     edx, [ecx+2]
0x1002f2d5  mov     ax, [ecx]
0x1002f2d8  add     ecx, 2
0x1002f2db  test    ax, ax
0x1002f2de  jnz     short loc_1002F2D5
0x1002f2e0  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1002f2e5  sub     ecx, edx
0x1002f2e7  sar     ecx, 1
0x1002f2e9  lea     edx, ds:2[ecx*2]
0x1002f2f0  mov     ecx, [eax]
0x1002f2f2  push    edx
0x1002f2f3  push    eax
0x1002f2f4  mov     [ebp+var_EC], edx
0x1002f2fa  mov     edi, [ecx+0Ch]
0x1002f2fd  mov     ecx, edi
0x1002f2ff  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002f305  call    edi
0x1002f307  mov     ecx, eax
0x1002f309  mov     eax, [ebp+var_108]
0x1002f30f  mov     [eax+14h], ecx
0x1002f312  test    ecx, ecx
0x1002f314  jz      loc_1002F1FF
0x1002f31a  push    [ebp+var_EC]; unsigned __int16 *
0x1002f320  lea     edx, [ebp+var_94]
0x1002f326  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x1002f32b  xor     ecx, ecx
0x1002f32d  mov     edi, 80004005h
0x1002f332  test    eax, eax
0x1002f334  cmovnz  edi, ecx
0x1002f337  mov     [ebp+var_EC], edi
0x1002f33d  jz      loc_1002F4CF
0x1002f343  mov     edx, [ebp+var_F0]
0x1002f349  mov     ecx, [ebp+var_108]
0x1002f34f  push    0; pretinfo
0x1002f351  push    0; grbit
0x1002f353  mov     eax, [edx]
0x1002f355  mov     edx, [ebp+var_10C]
0x1002f35b  mov     [eax+edx*8], ecx
0x1002f35e  lea     eax, [ebp+pcbActual]
0x1002f364  push    eax; pcbActual
0x1002f365  push    4; cbData
0x1002f367  lea     eax, [ebp+var_128]
0x1002f36d  push    eax; pvData
0x1002f36e  push    [ebp+var_9C]; columnid
0x1002f374  push    [ebp+tableid]; tableid
0x1002f37a  push    [ebp+sesid]; sesid
0x1002f380  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x1002f386  test    eax, eax
0x1002f388  js      loc_1002F4D9
0x1002f38e  mov     eax, [ebp+var_F0]
0x1002f394  mov     ecx, [ebp+var_10C]
0x1002f39a  push    0; grbit
0x1002f39c  push    1; cRow
0x1002f39e  mov     eax, [eax]
0x1002f3a0  lea     ecx, [eax+ecx*8]
0x1002f3a3  xor     eax, eax
0x1002f3a5  cmp     [ebp+var_128], eax
0x1002f3ab  setnz   al
0x1002f3ae  mov     [ecx+4], eax
0x1002f3b1  push    [ebp+tableid]; tableid
0x1002f3b7  push    [ebp+sesid]; sesid
0x1002f3bd  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1002f3c3  mov     ecx, [ebp+var_10C]
0x1002f3c9  mov     [ebp+var_F8], eax
0x1002f3cf  inc     ecx
0x1002f3d0  mov     eax, [ebp+var_F4]
0x1002f3d6  mov     [ebp+var_10C], ecx
0x1002f3dc  cmp     ecx, [eax]
0x1002f3de  jb      loc_1002F244
0x1002f3e4  movups  xmm0, xmmword ptr ds:_DBPROPSET_INDEX.Data1
0x1002f3eb  push    20h ; ' '; struct CDataSource *
0x1002f3ed  push    0; struct tagDBPROPSET **
0x1002f3ef  push    [ebp+var_120]; unsigned int *
0x1002f3f5  lea     edx, [ebp+var_E8]
0x1002f3fb  mov     [ebp+var_E8], 0
0x1002f405  push    [ebp+var_100]; struct tagDBPROPIDSET *
0x1002f40b  mov     ecx, 1
0x1002f410  mov     [ebp+var_E4], 0
0x1002f41a  push    [ebp+var_110]; unsigned int
0x1002f420  movups  [ebp+var_E0], xmm0
0x1002f427  call    ?GenericGetProperties@@YGJKQBUtagDBPROPIDSET@@PAKPAPAUtagDBPROPSET@@PAVCDataSource@@PAVCSettableProperties@@K@Z; GenericGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CDataSource *,CSettableProperties *,ulong)
0x1002f42c  mov     edi, eax
0x1002f42e  mov     [ebp+var_EC], edi
0x1002f434  test    edi, edi
0x1002f436  js      loc_1002F4CF
0x1002f43c  mov     eax, [ebp+var_100]
0x1002f442  xor     edx, edx
0x1002f444  mov     eax, [eax]
  ... truncated ...
```
