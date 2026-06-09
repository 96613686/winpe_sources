# CImpIAlterTable::AlterColumn(tagDBID *,tagDBID *,ulong,tagDBCOLUMNDESC *)

- ea: `0x100467c0`
- end: `0x10046ba0`
- name: `?AlterColumn@CImpIAlterTable@@UAGJPAUtagDBID@@0KPAUtagDBCOLUMNDESC@@@Z`
- size: `992`
- prototype: `int(CImpIAlterTable *__hidden this, struct tagDBID *, struct tagDBID *, unsigned int, struct tagDBCOLUMNDESC *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000e8d0`
- `0x10016e10`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10020410`
- `0x100207d0`
- `0x10023390`
- `0x100235b0`
- `0x10023d10`
- `0x100467c0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x10046a4e`
- `msvcrt!_wcsicmp` at `0x10046a4e`
- `KERNEL32!LeaveCriticalSection` at `0x10046b7d`
- `KERNEL32!LeaveCriticalSection` at `0x10046b7d`
- `KERNEL32!EnterCriticalSection` at `0x1004681a`
- `KERNEL32!EnterCriticalSection` at `0x1004681a`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10046807`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10046807`
- `msjet40!__imp__JetCloseTable@8` at `0x10046b60`
- `msjet40!__imp__JetCloseTable@8` at `0x10046b60`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10046b31`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10046b31`
- `msjet40!__imp__JetOpenTable@28` at `0x10046897`
- `msjet40!__imp__JetOpenTable@28` at `0x10046897`
- `msjet40!__imp__JetRenameColumn@16` at `0x10046a77`
- `msjet40!__imp__JetRenameColumn@16` at `0x10046a77`

## pseudocode

```c
int __stdcall CImpIAlterTable::AlterColumn(
        CImpIAlterTable *this,
        struct tagDBID *a2,
        struct tagDBID *a3,
        unsigned int a4,
        struct tagDBCOLUMNDESC *a5)
{
  int v5; // edi
  struct _RTL_CRITICAL_SECTION *v6; // esi
  LPOLESTR pwszName; // ecx
  signed int v8; // eax
  struct tagDBCOLUMNDESC *v9; // eax
  ULONG cPropertySets; // edx
  int v11; // ecx
  DBPROPSET *rgPropertySets; // edi
  const wchar_t *v13; // ecx
  CImpIAlterTable *v14; // ecx
  int v15; // eax
  int v16; // edx
  int v17; // eax
  int v18; // eax
  const struct _GUID *v20; // [esp+0h] [ebp-38h]
  const struct _GUID *v21; // [esp+4h] [ebp-34h]
  _DWORD v22[2]; // [esp+Ch] [ebp-2Ch] BYREF
  int (__thiscall ***v23)(_DWORD, const struct DBInfoProps *const *, _DWORD, _DWORD, unsigned int, _DWORD, _DWORD, _DWORD, int *, int); // [esp+14h] [ebp-24h]
  int (__thiscall ***v24)(_DWORD, const struct DBInfoProps *const *, _DWORD, _DWORD, int, int, int, int, int *, int); // [esp+18h] [ebp-20h]
  struct _RTL_CRITICAL_SECTION *v25; // [esp+1Ch] [ebp-1Ch]
  CDBSession *v26; // [esp+20h] [ebp-18h] BYREF
  unsigned int v27; // [esp+24h] [ebp-14h]
  JET_TABLEID tableid; // [esp+28h] [ebp-10h] BYREF
  int v29; // [esp+34h] [ebp-4h]

  v5 = 0;
  tableid = -1;
  v22[1] = 0;
  v23 = 0;
  v24 = 0;
  v22[0] = &CAlterColumnProperties::`vftable';
  v29 = 0;
  SetErrorInfo(0, 0);
  v6 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  v25 = v6;
  EnterCriticalSection(v6);
  LOBYTE(v29) = 1;
  if ( !a2 || !a3 || !a5 )
  {
LABEL_55:
    v5 = -2147024809;
    goto LABEL_56;
  }
  if ( (a4 & 0xFFFFFFDB) != 0 || !a4 )
  {
    v5 = -2147217837;
    goto LABEL_56;
  }
  if ( a2->eKind != 2 || (pwszName = a2->uName.pwszName) == 0 )
  {
    v5 = -2147217860;
    goto LABEL_56;
  }
  if ( a3->eKind != 2 || !a3->uName.ulPropid )
  {
    v5 = -2147217819;
    goto LABEL_56;
  }
  v8 = JetOpenTable(
         *(_DWORD *)(*((_DWORD *)this + 2) + 16),
         *(_DWORD *)(*((_DWORD *)this + 2) + 20),
         pwszName,
         0,
         0,
         3,
         &tableid);
  if ( v8 <= -1304 )
  {
    if ( v8 != -1304 )
    {
      if ( v8 != -1809 )
      {
        if ( v8 == -1305 )
        {
          v5 = -2147217865;
LABEL_48:
          CExtError::SendJetErrortoOLEAuto(
            v5,
            *(char **)(*((_DWORD *)this + 2) + 16),
            v8,
            (int)&IID_IAlterTable,
            (int)v20,
            v21);
LABEL_59:
          v14 = this;
          goto LABEL_60;
        }
LABEL_18:
        v5 = -2147467259;
        goto LABEL_48;
      }
LABEL_15:
      v5 = -2147217911;
      goto LABEL_48;
    }
LABEL_47:
    v5 = -2147217856;
    goto LABEL_48;
  }
  if ( v8 == -1302 )
    goto LABEL_47;
  if ( v8 )
    goto LABEL_18;
  v9 = a5;
  if ( (a4 & 4) != 0 )
  {
    cPropertySets = a5->cPropertySets;
    if ( cPropertySets )
    {
      if ( a5->rgPropertySets )
      {
        v11 = 0;
        rgPropertySets = a5->rgPropertySets;
        while ( !rgPropertySets[v11].cProperties || rgPropertySets[v11].rgProperties )
        {
          if ( ++v11 >= cPropertySets )
          {
            v5 = CColumnProperties::FInit((CColumnProperties *)v22);
            if ( v5 >= 0 )
            {
              v5 = (**v23)(
                     v23,
                     &rgDBInfoProps,
                     0,
                     0,
                     DBPROPSET_COLUMN.Data1,
                     *(_DWORD *)&DBPROPSET_COLUMN.Data2,
                     *(_DWORD *)DBPROPSET_COLUMN.Data4,
                     *(_DWORD *)&DBPROPSET_COLUMN.Data4[4],
                     dword_10005470,
                     4);
              if ( v5 >= 0 )
              {
                v5 = (**v24)(
                       v24,
                       &rgDBInfoProps,
                       0,
                       0,
                       -2113144542,
                       298937032,
                       -1073741153,
                       -524107185,
                       dword_10005490,
                       3);
                if ( v5 >= 0 )
                {
                  v5 = CSettableProperties::SetProperties(
                         (CSettableProperties *)v22,
                         a5->cPropertySets,
                         a5->rgPropertySets,
                         0);
                  if ( v5 >= 0 )
                  {
                    v5 = CColumnProperties::SetPropertiesToJetPropertyManager(
                           (CColumnProperties *)v22,
                           *(_DWORD *)(*((_DWORD *)this + 2) + 16),
                           (unsigned int)a2,
                           *(_DWORD *)(*((_DWORD *)this + 2) + 20),
                           a2->uName.pwszName,
                           a3->uName.pwszName,
                           a5->wType);
                    if ( v5 >= 0 )
                    {
                      v5 = CColumnProperties::SetPropertiesToJetModifyColumn(
                             (CColumnProperties *)v22,
                             *(_DWORD *)(*((_DWORD *)this + 2) + 16),
                             tableid,
                             a3->uName.pwszName);
                      if ( v5 >= 0 )
                      {
                        v9 = a5;
                        goto LABEL_33;
                      }
                    }
                  }
                }
              }
            }
            goto LABEL_49;
          }
        }
      }
      goto LABEL_55;
    }
  }
LABEL_33:
  if ( (a4 & 0x20) == 0 )
    goto LABEL_49;
  if ( v9->dbcid.eKind != 2 || (v13 = v9->dbcid.uName.pwszName) == 0 )
  {
    v5 = -2147217903;
LABEL_56:
    v18 = *((_DWORD *)this + 2);
    v16 = *(_DWORD *)(v18 + 20);
    v17 = *(_DWORD *)(v18 + 16);
    goto LABEL_57;
  }
  if ( __wcsicmp(v13, a3->uName.pwszName) )
  {
    v8 = JetRenameColumn(*(_DWORD *)(*((_DWORD *)this + 2) + 16), tableid, a3->uName.ulPropid, a5->dbcid.uName.ulPropid);
    if ( v8 <= -1507 )
    {
      if ( v8 != -1507 )
      {
        if ( v8 != -1809 )
        {
          if ( v8 == -1508 )
          {
            v5 = -2147217858;
            goto LABEL_48;
          }
          goto LABEL_18;
        }
        goto LABEL_15;
      }
LABEL_45:
      v5 = -2147217819;
      goto LABEL_48;
    }
    if ( v8 == -1002 )
      goto LABEL_45;
    if ( v8 )
    {
      v5 = -2147467259;
      goto LABEL_48;
    }
  }
LABEL_49:
  v27 = v5;
  if ( v5 >= 0 )
    goto LABEL_59;
  v14 = this;
  v15 = *((_DWORD *)this + 2);
  v16 = *(_DWORD *)(v15 + 20);
  v17 = *(_DWORD *)(v15 + 16);
  if ( v5 != -2147024882 )
  {
LABEL_57:
    if ( !JetGetDatabaseInfo(v17, v16, &v26, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IAlterTable, 0, v20, (int)v21);
    goto LABEL_59;
  }
LABEL_60:
  v27 = tableid;
  if ( tableid != -1 )
  {
    v26 = (CDBSession *)*((_DWORD *)v14 + 2);
    if ( JetCloseTable(*((_DWORD *)v26 + 4), tableid) == -1108 )
      CDBSession::AddJetTableId(v26, v27);
  }
  if ( v6 )
    LeaveCriticalSection(v6);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v22);
  return v5;
}

```

## disassembly

```asm
0x100467c0  mov     edi, edi
0x100467c2  push    ebp
0x100467c3  mov     ebp, esp
0x100467c5  push    0FFFFFFFFh
0x100467c7  push    offset ?AlterColumn@CImpIAlterTable@@UAGJPAUtagDBID@@0KPAUtagDBCOLUMNDESC@@@Z_SEH
0x100467cc  mov     eax, large fs:0
0x100467d2  push    eax
0x100467d3  sub     esp, 20h
0x100467d6  push    esi
0x100467d7  push    edi; int
0x100467d8  mov     eax, ___security_cookie
0x100467dd  xor     eax, ebp
0x100467df  push    eax; struct _GUID *
0x100467e0  lea     eax, [ebp+var_C]
0x100467e3  mov     large fs:0, eax
0x100467e9  xor     edi, edi
0x100467eb  mov     [ebp+tableid], 0FFFFFFFFh
0x100467f2  mov     [ebp+var_28], edi
0x100467f5  mov     [ebp+var_24], edi
0x100467f8  mov     [ebp+var_20], edi
0x100467fb  mov     [ebp+var_2C], offset ??_7CAlterColumnProperties@@6B@; const CAlterColumnProperties::`vftable'
0x10046802  push    edi; perrinfo
0x10046803  push    edi; dwReserved
0x10046804  mov     [ebp+var_4], edi
0x10046807  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1004680d  mov     esi, [ebp+this]
0x10046810  mov     esi, [esi+8]
0x10046813  add     esi, 68h ; 'h'
0x10046816  push    esi; lpCriticalSection
0x10046817  mov     [ebp+var_1C], esi
0x1004681a  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10046820  mov     edx, [ebp+arg_4]
0x10046823  mov     byte ptr [ebp+var_4], 1
0x10046827  test    edx, edx
0x10046829  jz      loc_10046B16
0x1004682f  mov     eax, [ebp+arg_8]
0x10046832  test    eax, eax
0x10046834  jz      loc_10046B16
0x1004683a  cmp     [ebp+arg_10], edi
0x1004683d  jz      loc_10046B16
0x10046843  mov     ecx, [ebp+arg_C]
0x10046846  test    ecx, 0FFFFFFDBh
0x1004684c  jnz     loc_10046B0F
0x10046852  test    ecx, ecx
0x10046854  jz      loc_10046B0F
0x1004685a  cmp     dword ptr [edx+10h], 2
0x1004685e  jnz     loc_10046B08
0x10046864  mov     ecx, [edx+14h]
0x10046867  test    ecx, ecx
0x10046869  jz      loc_10046B08
0x1004686f  cmp     dword ptr [eax+10h], 2
0x10046873  jnz     loc_10046B01
0x10046879  cmp     [eax+14h], edi
0x1004687c  jz      loc_10046B01
0x10046882  mov     eax, [ebp+this]
0x10046885  lea     edx, [ebp+tableid]
0x10046888  push    edx
0x10046889  push    3
0x1004688b  push    edi
0x1004688c  mov     eax, [eax+8]
0x1004688f  push    edi
0x10046890  push    ecx
0x10046891  push    dword ptr [eax+14h]
0x10046894  push    dword ptr [eax+10h]
0x10046897  call    ds:__imp__JetOpenTable@28; JetOpenTable(x,x,x,x,x,x,x)
0x1004689d  cmp     eax, 0FFFFFAE8h
0x100468a2  jg      short loc_100468CC
0x100468a4  jz      loc_10046AC3
0x100468aa  cmp     eax, 0FFFFF8EFh
0x100468af  jz      short loc_100468C2
0x100468b1  cmp     eax, 0FFFFFAE7h
0x100468b6  jnz     short loc_100468DB
0x100468b8  mov     edi, 80040E37h
0x100468bd  jmp     loc_10046ACC
0x100468c2  mov     edi, 80040E09h
0x100468c7  jmp     loc_10046ACC
0x100468cc  cmp     eax, 0FFFFFAEAh
0x100468d1  jz      loc_10046AC3
0x100468d7  test    eax, eax
0x100468d9  jz      short loc_100468E5
0x100468db  mov     edi, 80004005h
0x100468e0  jmp     loc_10046AC8
0x100468e5  test    byte ptr [ebp+arg_C], 4
0x100468e9  mov     eax, [ebp+arg_10]
0x100468ec  jz      loc_10046A30
0x100468f2  mov     edx, [eax+10h]
0x100468f5  test    edx, edx
0x100468f7  jz      loc_10046A30
0x100468fd  cmp     dword ptr [eax+8], 0
0x10046901  jz      loc_10046B16
0x10046907  xor     ecx, ecx
0x10046909  test    edx, edx
0x1004690b  jz      loc_10046A30
0x10046911  mov     edi, [eax+8]
0x10046914  lea     eax, [ecx+ecx*2]
0x10046917  cmp     dword ptr [edi+eax*8+4], 0
0x1004691c  jz      short loc_10046928
0x1004691e  cmp     dword ptr [edi+eax*8], 0
0x10046922  jz      loc_10046B16
0x10046928  inc     ecx
0x10046929  cmp     ecx, edx
0x1004692b  jb      short loc_10046914
0x1004692d  lea     ecx, [ebp+var_2C]; this
0x10046930  call    ?FInit@CColumnProperties@@QAEJXZ; CColumnProperties::FInit(void)
0x10046935  mov     edi, eax
0x10046937  test    edi, edi
0x10046939  js      loc_10046AE4
0x1004693f  mov     eax, [ebp+var_24]
0x10046942  movups  xmm0, xmmword ptr ds:_DBPROPSET_COLUMN.Data1
0x10046949  push    4
0x1004694b  push    offset dword_10005470
0x10046950  mov     eax, [eax]
0x10046952  sub     esp, 10h
0x10046955  mov     edi, [eax]
0x10046957  mov     eax, esp
0x10046959  push    0
0x1004695b  push    0
0x1004695d  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; DBInfoProps const * const rgDBInfoProps
0x10046962  mov     ecx, edi
0x10046964  movups  xmmword ptr [eax], xmm0
0x10046967  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004696d  mov     ecx, [ebp+var_24]
0x10046970  call    edi
0x10046972  mov     edi, eax
0x10046974  test    edi, edi
0x10046976  js      loc_10046AE4
0x1004697c  mov     eax, [ebp+var_20]
0x1004697f  movups  xmm0, ds:xmmword_10005420
0x10046986  push    3
0x10046988  push    offset dword_10005490
0x1004698d  mov     eax, [eax]
0x1004698f  sub     esp, 10h
0x10046992  mov     edi, [eax]
0x10046994  mov     eax, esp
0x10046996  push    0
0x10046998  push    0
0x1004699a  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; DBInfoProps const * const rgDBInfoProps
0x1004699f  mov     ecx, edi
0x100469a1  movups  xmmword ptr [eax], xmm0
0x100469a4  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100469aa  mov     ecx, [ebp+var_20]
0x100469ad  call    edi
0x100469af  mov     edi, eax
0x100469b1  test    edi, edi
0x100469b3  js      loc_10046AE4
0x100469b9  mov     eax, [ebp+arg_10]
0x100469bc  lea     ecx, [ebp+var_2C]; this
0x100469bf  push    0; struct CDBSession *
0x100469c1  push    dword ptr [eax+8]; struct tagDBPROPSET *
0x100469c4  push    dword ptr [eax+10h]; unsigned int
0x100469c7  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x100469cc  mov     edi, eax
0x100469ce  test    edi, edi
0x100469d0  js      loc_10046AE4
0x100469d6  mov     ecx, [ebp+arg_10]
0x100469d9  mov     eax, [ebp+this]
0x100469dc  movzx   ecx, word ptr [ecx+30h]
0x100469e0  mov     eax, [eax+8]
0x100469e3  push    ecx; unsigned __int16
0x100469e4  mov     ecx, [ebp+arg_8]
0x100469e7  push    dword ptr [ecx+14h]; unsigned __int16 *
0x100469ea  mov     ecx, [ebp+arg_4]
0x100469ed  push    dword ptr [ecx+14h]; unsigned __int16 *
0x100469f0  push    dword ptr [eax+14h]; unsigned int
0x100469f3  push    ecx; unsigned int
0x100469f4  push    dword ptr [eax+10h]; unsigned int
0x100469f7  lea     ecx, [ebp+var_2C]; this
0x100469fa  call    ?SetPropertiesToJetPropertyManager@CColumnProperties@@QAEJKKKPAG0G@Z; CColumnProperties::SetPropertiesToJetPropertyManager(ulong,ulong,ulong,ushort *,ushort *,ushort)
0x100469ff  mov     edi, eax
0x10046a01  test    edi, edi
0x10046a03  js      loc_10046AE4
0x10046a09  mov     ecx, [ebp+arg_8]
0x10046a0c  mov     eax, [ebp+this]
0x10046a0f  push    dword ptr [ecx+14h]; unsigned __int16 *
0x10046a12  mov     eax, [eax+8]
0x10046a15  lea     ecx, [ebp+var_2C]; this
0x10046a18  push    [ebp+tableid]; unsigned int
0x10046a1b  push    dword ptr [eax+10h]; unsigned int
0x10046a1e  call    ?SetPropertiesToJetModifyColumn@CColumnProperties@@QAEJKKPBG@Z; CColumnProperties::SetPropertiesToJetModifyColumn(ulong,ulong,ushort const *)
0x10046a23  mov     edi, eax
0x10046a25  test    edi, edi
0x10046a27  js      loc_10046AE4
0x10046a2d  mov     eax, [ebp+arg_10]
0x10046a30  test    byte ptr [ebp+arg_C], 20h
0x10046a34  jz      loc_10046AE4
0x10046a3a  cmp     dword ptr [eax+28h], 2
0x10046a3e  jnz     short loc_10046ABC
0x10046a40  mov     ecx, [eax+2Ch]
0x10046a43  test    ecx, ecx
0x10046a45  jz      short loc_10046ABC
0x10046a47  mov     eax, [ebp+arg_8]
0x10046a4a  push    dword ptr [eax+14h]; String2
0x10046a4d  push    ecx; String1
0x10046a4e  call    ds:__imp___wcsicmp
0x10046a54  add     esp, 8
0x10046a57  test    eax, eax
0x10046a59  jz      loc_10046AE4
0x10046a5f  mov     ecx, [ebp+arg_10]
0x10046a62  mov     eax, [ebp+this]
0x10046a65  push    dword ptr [ecx+2Ch]
0x10046a68  mov     ecx, [ebp+arg_8]
0x10046a6b  mov     eax, [eax+8]
0x10046a6e  push    dword ptr [ecx+14h]
0x10046a71  push    [ebp+tableid]
0x10046a74  push    dword ptr [eax+10h]
0x10046a77  call    ds:__imp__JetRenameColumn@16; JetRenameColumn(x,x,x,x)
0x10046a7d  cmp     eax, 0FFFFFA1Dh
0x10046a82  jg      short loc_10046AA3
0x10046a84  jz      short loc_10046AB5
0x10046a86  cmp     eax, 0FFFFF8EFh
0x10046a8b  jz      loc_100468C2
0x10046a91  cmp     eax, 0FFFFFA1Ch
0x10046a96  jnz     loc_100468DB
0x10046a9c  mov     edi, 80040E3Eh
0x10046aa1  jmp     short loc_10046ACC
0x10046aa3  cmp     eax, 0FFFFFC16h
0x10046aa8  jz      short loc_10046AB5
0x10046aaa  test    eax, eax
0x10046aac  jz      short loc_10046AE4
0x10046aae  mov     edi, 80004005h
0x10046ab3  jmp     short loc_10046AC8
0x10046ab5  mov     edi, 80040E65h
0x10046aba  jmp     short loc_10046AC8
0x10046abc  mov     edi, 80040E11h
0x10046ac1  jmp     short loc_10046B1B
0x10046ac3  mov     edi, 80040E40h
0x10046ac8  test    eax, eax
0x10046aca  jz      short loc_10046AE4
0x10046acc  push    offset _IID_IAlterTable; int
0x10046ad1  push    eax; unsigned int
0x10046ad2  mov     eax, [ebp+this]
0x10046ad5  mov     edx, edi
0x10046ad7  mov     ecx, [eax+8]
0x10046ada  mov     ecx, [ecx+10h]
0x10046add  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10046ae2  jmp     short loc_10046B48
0x10046ae4  mov     [ebp+var_14], edi
0x10046ae7  test    edi, edi
0x10046ae9  jns     short loc_10046B48
0x10046aeb  mov     ecx, [ebp+this]
0x10046aee  mov     eax, [ecx+8]
0x10046af1  mov     edx, [eax+14h]
0x10046af4  mov     eax, [eax+10h]
0x10046af7  cmp     edi, 8007000Eh
0x10046afd  jz      short loc_10046B4B
0x10046aff  jmp     short loc_10046B27
0x10046b01  mov     edi, 80040E65h
0x10046b06  jmp     short loc_10046B1B
0x10046b08  mov     edi, 80040E3Ch
0x10046b0d  jmp     short loc_10046B1B
0x10046b0f  mov     edi, 80040E53h
0x10046b14  jmp     short loc_10046B1B
0x10046b16  mov     edi, 80070057h
0x10046b1b  mov     eax, [ebp+this]
0x10046b1e  mov     eax, [eax+8]
0x10046b21  mov     edx, [eax+14h]
0x10046b24  mov     eax, [eax+10h]
0x10046b27  push    3
0x10046b29  push    4
0x10046b2b  lea     ecx, [ebp+var_18]
0x10046b2e  push    ecx
0x10046b2f  push    edx
0x10046b30  push    eax
0x10046b31  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10046b37  test    eax, eax
0x10046b39  jnz     short loc_10046B48
0x10046b3b  push    eax; int
0x10046b3c  push    offset _IID_IAlterTable; int
0x10046b41  mov     edx, edi
0x10046b43  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10046b48  mov     ecx, [ebp+this]
0x10046b4b  mov     eax, [ebp+tableid]
0x10046b4e  mov     [ebp+var_14], eax
0x10046b51  cmp     eax, 0FFFFFFFFh
0x10046b54  jz      short loc_10046B78
0x10046b56  mov     ecx, [ecx+8]
0x10046b59  push    eax; tableid
0x10046b5a  mov     [ebp+var_18], ecx
0x10046b5d  push    dword ptr [ecx+10h]; sesid
0x10046b60  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10046b66  cmp     eax, 0FFFFFBACh
0x10046b6b  jnz     short loc_10046B78
0x10046b6d  push    [ebp+var_14]; unsigned int
0x10046b70  mov     ecx, [ebp+var_18]; this
0x10046b73  call    ?AddJetTableId@CDBSession@@QAEJK@Z; CDBSession::AddJetTableId(ulong)
0x10046b78  test    esi, esi
0x10046b7a  jz      short loc_10046B83
0x10046b7c  push    esi; lpCriticalSection
0x10046b7d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10046b83  lea     ecx, [ebp+var_2C]; this
0x10046b86  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x10046b8b  mov     eax, edi
0x10046b8d  mov     ecx, [ebp+var_C]
0x10046b90  mov     large fs:0, ecx
0x10046b97  pop     ecx
0x10046b98  pop     edi
0x10046b99  pop     esi
0x10046b9a  mov     esp, ebp
0x10046b9c  pop     ebp
0x10046b9d  retn    14h
  ... truncated ...
```
