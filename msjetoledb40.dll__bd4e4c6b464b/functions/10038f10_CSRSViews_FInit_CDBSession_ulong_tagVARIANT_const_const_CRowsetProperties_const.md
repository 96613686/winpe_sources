# CSRSViews::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x10038f10`
- end: `0x100395a8`
- name: `?FInit@CSRSViews@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `1688`
- prototype: `int(CSRSViews *__hidden this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x1000d570`
- `0x10013100`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10028340`
- `0x10035d90`
- `0x10035e60`
- `0x10038f10`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x100391bd`
- `msvcrt!_wcsicmp` at `0x100391bd`
- `msjet40!__imp__JetCloseTable@8` at `0x1003921b`
- `msjet40!__imp__JetCloseTable@8` at `0x1003928a`
- `msjet40!__imp__JetCloseTable@8` at `0x100394dc`
- `msjet40!__imp__JetCloseTable@8` at `0x10039551`
- `msjet40!__imp__JetCloseTable@8` at `0x1003921b`
- `msjet40!__imp__JetCloseTable@8` at `0x1003928a`
- `msjet40!__imp__JetCloseTable@8` at `0x100394dc`
- `msjet40!__imp__JetCloseTable@8` at `0x10039551`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003952f`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003952f`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1003906f`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x1003906f`
- `msjet40!__imp__JetMove@16` at `0x10039093`
- `msjet40!__imp__JetMove@16` at `0x10039412`
- `msjet40!__imp__JetMove@16` at `0x10039093`
- `msjet40!__imp__JetMove@16` at `0x10039412`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x100392fa`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x100392fa`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003910c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003916a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100392b6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100392e2`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003910c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003916a`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100392b6`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100392e2`
- `msjet40!__imp__JetSetColumn@28` at `0x10039326`
- `msjet40!__imp__JetSetColumn@28` at `0x10039344`
- `msjet40!__imp__JetSetColumn@28` at `0x10039361`
- `msjet40!__imp__JetSetColumn@28` at `0x1003937e`
- `msjet40!__imp__JetSetColumn@28` at `0x100393a7`
- `msjet40!__imp__JetSetColumn@28` at `0x10039326`
- `msjet40!__imp__JetSetColumn@28` at `0x10039344`
- `msjet40!__imp__JetSetColumn@28` at `0x10039361`
- `msjet40!__imp__JetSetColumn@28` at `0x1003937e`
- `msjet40!__imp__JetSetColumn@28` at `0x100393a7`
- `msjet40!__imp__JetUpdate@20` at `0x100393f7`
- `msjet40!__imp__JetUpdate@20` at `0x100393f7`
- `msjet40!__imp__JetGetQueryParameterInfo@24` at `0x100391ed`
- `msjet40!__imp__JetGetQueryParameterInfo@24` at `0x100391ed`
- `msjet40!__imp__JetOpenQueryDef@16` at `0x10039240`
- `msjet40!__imp__JetOpenQueryDef@16` at `0x10039240`
- `msjet40!__imp__JetRetrieveQoSql@36` at `0x10039269`
- `msjet40!__imp__JetRetrieveQoSql@36` at `0x10039269`

## pseudocode

```c
int __userpurge CSRSViews::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSViews *this,
        struct CDBSession *a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  JET_SESID v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // ebx
  JET_COLUMNID *v13; // eax
  unsigned int v14; // esi
  JET_ERR v15; // eax
  CSRSViews *v16; // ebx
  BOOL v17; // eax
  JET_TABLEID v18; // eax
  CSchemaRowset *v19; // ecx
  ColumnDataWithFakeNamesAndDBTYPES *v20; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v21; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v22; // esi
  int v23; // ecx
  _DWORD *v24; // esi
  unsigned int v26; // [esp-24h] [ebp-17Ch]
  ColumnDataWithFakeNamesAndDBTYPES *v27; // [esp-14h] [ebp-16Ch]
  const struct _GUID *v28; // [esp+0h] [ebp-158h]
  const struct _GUID *v29; // [esp+4h] [ebp-154h]
  unsigned int ObjectInfo; // [esp+14h] [ebp-144h] BYREF
  JET_TABLEID v32; // [esp+18h] [ebp-140h] BYREF
  JET_COLUMNID *v33; // [esp+1Ch] [ebp-13Ch]
  int v34; // [esp+20h] [ebp-138h] BYREF
  BOOL v35; // [esp+24h] [ebp-134h]
  unsigned int cbData; // [esp+28h] [ebp-130h] BYREF
  void *Block; // [esp+2Ch] [ebp-12Ch]
  unsigned int pcbActual; // [esp+30h] [ebp-128h] BYREF
  JET_TABLEID v39; // [esp+34h] [ebp-124h] BYREF
  int v40; // [esp+38h] [ebp-120h]
  ColumnDataWithFakeNamesAndDBTYPES *v41; // [esp+3Ch] [ebp-11Ch] BYREF
  int pvData; // [esp+40h] [ebp-118h] BYREF
  unsigned int v43; // [esp+44h] [ebp-114h] BYREF
  unsigned int v44; // [esp+48h] [ebp-110h]
  int v45; // [esp+4Ch] [ebp-10Ch]
  _BYTE v46[8]; // [esp+50h] [ebp-108h] BYREF
  _BYTE v47[8]; // [esp+58h] [ebp-100h] BYREF
  int v48; // [esp+60h] [ebp-F8h] BYREF
  JET_TABLEID tableid; // [esp+64h] [ebp-F4h]
  unsigned int v50; // [esp+68h] [ebp-F0h]
  JET_COLUMNID v51; // [esp+70h] [ebp-E8h]
  JET_COLUMNID v52; // [esp+78h] [ebp-E0h]
  JET_COLUMNID v53; // [esp+7Ch] [ebp-DCh]
  JET_COLUMNID columnid; // [esp+84h] [ebp-D4h]
  int v55; // [esp+90h] [ebp-C8h] BYREF
  int v56; // [esp+94h] [ebp-C4h]
  int v57; // [esp+98h] [ebp-C0h]
  wchar_t String1[70]; // [esp+C8h] [ebp-90h] BYREF

  v44 = a5;
  v8 = a1[4];
  v45 = a2;
  cbData = (unsigned int)a4;
  ObjectInfo = 0;
  v33 = 0;
  v35 = 1;
  tableid = -1;
  Block = operator new(0x20000u);
  if ( !Block )
    goto LABEL_66;
  v56 = -1;
  if ( this )
  {
    if ( !a4
      || (unsigned int)this > 3
      || (v9 = *(unsigned __int16 *)a4, (_WORD)v9) && v9 != 1 && (v9 != 8 || *((_DWORD *)a4 + 2))
      || (unsigned int)this > 1
      && (v10 = *((unsigned __int16 *)a4 + 8), (_WORD)v10)
      && v10 != 1
      && (v10 != 8 || *((_DWORD *)a4 + 6))
      || (unsigned int)this > 2 && (v11 = *((unsigned __int16 *)a4 + 16), (_WORD)v11) && v11 != 1 && v11 != 8 )
    {
      v12 = -2147024809;
LABEL_67:
      v24 = a1;
      goto LABEL_68;
    }
  }
  v13 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          36);
  v33 = v13;
  if ( !v13 )
    goto LABEL_66;
  v12 = SRSCreateTempTable(4, a1, &v32, v13, 0);
  if ( v12 < 0 )
    goto LABEL_67;
  v14 = cbData;
  if ( (unsigned int)this >= 3 )
    v35 = *(_WORD *)(cbData + 32) != 1;
  ObjectInfo = JetGetObjectInfo(v8, a1[5], 5, L"tables", 0, &v48, 48, 1);
  if ( ObjectInfo )
  {
LABEL_24:
    v12 = -2147467259;
    goto LABEL_67;
  }
  v15 = JetMove(v8, tableid, 0x80000000, 0);
  ObjectInfo = v15;
  if ( v15 != -1603 && v15 )
    goto LABEL_67;
  v16 = this;
  if ( (unsigned int)this <= 2 )
  {
    v17 = v35;
  }
  else
  {
    v17 = v35;
    if ( *(_WORD *)(v14 + 32) == 8 )
    {
      if ( !*(_DWORD *)(v14 + 40) )
        v17 = 0;
      v35 = v17;
    }
  }
  v40 = 0;
  if ( v50 )
  {
    while ( v17 )
    {
      ObjectInfo = JetRetrieveColumn(v8, tableid, columnid, &pvData, 4u, &pcbActual, 0, 0);
      if ( ObjectInfo )
        goto LABEL_24;
      if ( !(_WORD)pvData )
      {
        HIBYTE(v34) = 1;
        *(_WORD *)Block = 0;
        String1[0] = 0;
        v57 = 0;
        ObjectInfo = JetRetrieveColumn(v8, tableid, v51, String1, 0x81u, &pcbActual, 0, 0);
        if ( ObjectInfo )
          goto LABEL_24;
        if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
          __report_rangecheckfailure();
        *(wchar_t *)((char *)String1 + (pcbActual & 0xFFFFFFFE)) = 0;
        if ( !v16
          || (unsigned int)v16 >= 3
          && (!*(_WORD *)(v14 + 32) || !*(_DWORD *)(v14 + 40) || !__wcsicmp(String1, *(const wchar_t **)(v14 + 40))) )
        {
          ObjectInfo = JetGetQueryParameterInfo(v8, a1[5], String1, &v55, 56, &v41);
          if ( (ObjectInfo & 0x80000000) == 0 )
          {
            v18 = v56;
          }
          else
          {
            v18 = -1;
            v57 = 1;
            v56 = -1;
          }
          JetCloseTable(v8, v18);
          if ( !v57 )
          {
            ObjectInfo = JetOpenQueryDef(v8, a1[5], String1, &v39);
            if ( ObjectInfo )
              goto LABEL_24;
            ObjectInfo = JetRetrieveQoSql(v8, v39, Block, 0x10000, &cbData, 0, 0, 0, 0);
            if ( ObjectInfo )
              goto LABEL_24;
            cbData *= 2;
            ObjectInfo = JetCloseTable(v8, v39);
            if ( ObjectInfo )
              goto LABEL_24;
            ObjectInfo = JetRetrieveColumn(v8, tableid, v52, v46, 8u, &v43, 0, 0);
            if ( ObjectInfo )
              goto LABEL_24;
            ObjectInfo = JetRetrieveColumn(v8, tableid, v53, v47, 8u, &v43, 0, 0);
            if ( ObjectInfo )
              goto LABEL_24;
            ObjectInfo = JetPrepareUpdate(v8, v32, 0);
            if ( ObjectInfo )
              goto LABEL_24;
            JetSetColumn(v8, v32, v33[2], String1, pcbActual, 0, 0);
            JetSetColumn(v8, v32, v33[3], Block, cbData, 0, 0);
            JetSetColumn(v8, v32, v33[5], (char *)&v34 + 3, 1u, 0, 0);
            ObjectInfo = JetSetColumn(v8, v32, v33[7], v46, 8u, 0, 0);
            if ( (ObjectInfo & 0x80000000) != 0 )
              goto LABEL_24;
            ObjectInfo = JetSetColumn(v8, v32, v33[8], v47, 8u, 0, 0);
            if ( (ObjectInfo & 0x80000000) != 0 )
              goto LABEL_24;
            v12 = CSchemaRowset::MapStringPropertyValueToColumn(
                    v19,
                    v8,
                    a1[5],
                    (const unsigned __int16 *)v19,
                    String1,
                    0,
                    L"Description",
                    v32,
                    v33[6],
                    (int *)&ObjectInfo);
            if ( v12 < 0 )
              goto LABEL_67;
            ObjectInfo = JetUpdate(v8, v32, 0, 0, 0);
            if ( ObjectInfo )
              goto LABEL_24;
          }
        }
      }
      ObjectInfo = JetMove(v8, tableid, 1, 0);
      if ( ++v40 >= v50 )
        break;
      v16 = this;
      v17 = v35;
    }
  }
  v20 = (ColumnDataWithFakeNamesAndDBTYPES *)operator new(0x20u);
  v41 = v20;
  if ( !v20 || (v21 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(v20), (v22 = v21) == 0) )
  {
LABEL_66:
    v12 = -2147024882;
    goto LABEL_67;
  }
  *((_DWORD *)v21 + 4) = dword_10007BF4;
  *((_DWORD *)v21 + 5) = &SRSViewsDefNames;
  *((_DWORD *)v21 + 7) = 0;
  v12 = ColumnData::FInit(v21, v8, a1[5], v32, (int *)&ObjectInfo, 0, (int)&SRSViewsDefNames);
  if ( v12 < 0 )
    goto LABEL_67;
  v23 = v45;
  v27 = v22;
  v26 = v44;
  *((_DWORD *)v22 + 1) = 9;
  v24 = a1;
  v12 = CRowset::FInit(v23, 0, a1, 0, 0, 0, v32, v26, 1, 0, 0, v27, 1, 0, 0, &GUID_NULL);
  if ( tableid != -1 )
  {
    ObjectInfo = JetCloseTable(v8, tableid);
    if ( ObjectInfo )
      v12 = -2147467259;
  }
LABEL_68:
  if ( ObjectInfo )
  {
    CExtError::SendJetErrortoOLEAuto(ObjectInfo, (int)&IID_IDBSchemaRowset, (int)v28, v29);
  }
  else if ( v12 < 0 && v12 != -2147024882 && !JetGetDatabaseInfo(v24[4], v24[5], &v41, 4, 3) )
  {
    CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v28, (int)v29);
  }
  if ( tableid != -1 )
    JetCloseTable(v8, tableid);
  if ( Block )
    operator delete(Block);
  if ( v33 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v33);
  return v12;
}

```

## disassembly

```asm
0x10038f10  mov     edi, edi
0x10038f12  push    ebp
0x10038f13  mov     ebp, esp
0x10038f15  and     esp, 0FFFFFFF8h
0x10038f18  sub     esp, 14Ch
0x10038f1e  mov     eax, ___security_cookie
0x10038f23  xor     eax, esp
0x10038f25  mov     [esp+14Ch+var_4], eax
0x10038f2c  mov     eax, [ebp+arg_8]
0x10038f2f  push    ebx
0x10038f30  push    esi; int
0x10038f31  mov     esi, [ebp+arg_4]
0x10038f34  mov     ebx, edx
0x10038f36  push    edi; struct _GUID *
0x10038f37  mov     [esp+158h+var_110], eax
0x10038f3b  mov     eax, 1
0x10038f40  push    20000h; Size
0x10038f45  mov     edi, [ebx+10h]
0x10038f48  mov     [esp+15Ch+var_148], ebx
0x10038f4c  mov     [esp+15Ch+var_10C], ecx
0x10038f50  mov     [esp+15Ch+cbData], esi
0x10038f54  mov     [esp+15Ch+var_144], 0
0x10038f5c  mov     [esp+15Ch+var_13C], 0
0x10038f64  mov     [esp+15Ch+var_134], eax
0x10038f68  mov     [esp+15Ch+tableid], 0FFFFFFFFh
0x10038f70  call    ??2@YAPAXI@Z; operator new(uint)
0x10038f75  add     esp, 4
0x10038f78  mov     [esp+158h+Block], eax
0x10038f7c  test    eax, eax
0x10038f7e  jz      loc_100394F1
0x10038f84  mov     ecx, [ebp+this]
0x10038f87  mov     [esp+158h+var_C4], 0FFFFFFFFh
0x10038f92  test    ecx, ecx
0x10038f94  jz      short loc_10038FF7
0x10038f96  test    esi, esi
0x10038f98  jz      short loc_10038FED
0x10038f9a  cmp     ecx, 3
0x10038f9d  ja      short loc_10038FED
0x10038f9f  movzx   eax, word ptr [esi]
0x10038fa2  test    ax, ax
0x10038fa5  jz      short loc_10038FB7
0x10038fa7  cmp     eax, 1
0x10038faa  jz      short loc_10038FB7
0x10038fac  cmp     eax, 8
0x10038faf  jnz     short loc_10038FED
0x10038fb1  cmp     dword ptr [esi+8], 0
0x10038fb5  jnz     short loc_10038FED
0x10038fb7  cmp     ecx, 1
0x10038fba  jbe     short loc_10038FD5
0x10038fbc  movzx   eax, word ptr [esi+10h]
0x10038fc0  test    ax, ax
0x10038fc3  jz      short loc_10038FD5
0x10038fc5  cmp     eax, 1
0x10038fc8  jz      short loc_10038FD5
0x10038fca  cmp     eax, 8
0x10038fcd  jnz     short loc_10038FED
0x10038fcf  cmp     dword ptr [esi+18h], 0
0x10038fd3  jnz     short loc_10038FED
0x10038fd5  cmp     ecx, 2
0x10038fd8  jbe     short loc_10038FF7
0x10038fda  movzx   eax, word ptr [esi+20h]
0x10038fde  test    ax, ax
0x10038fe1  jz      short loc_10038FF7
0x10038fe3  cmp     eax, 1
0x10038fe6  jz      short loc_10038FF7
0x10038fe8  cmp     eax, 8
0x10038feb  jz      short loc_10038FF7
0x10038fed  mov     ebx, 80070057h
0x10038ff2  jmp     loc_100394F6
0x10038ff7  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10038ffd  push    24h ; '$'
0x10038fff  push    ecx
0x10039000  mov     eax, [ecx]
0x10039002  mov     esi, [eax+0Ch]
0x10039005  mov     ecx, esi
0x10039007  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003900d  call    esi
0x1003900f  mov     [esp+158h+var_13C], eax
0x10039013  test    eax, eax
0x10039015  jz      loc_100394F1
0x1003901b  push    0
0x1003901d  push    eax
0x1003901e  lea     eax, [esp+160h+var_140]
0x10039022  mov     edx, ebx
0x10039024  push    eax
0x10039025  mov     ecx, 4
0x1003902a  call    SRSCreateTempTable
0x1003902f  mov     ebx, eax
0x10039031  test    ebx, ebx
0x10039033  js      loc_100394F6
0x10039039  cmp     [ebp+this], 3
0x1003903d  mov     esi, [esp+158h+cbData]
0x10039041  jb      short loc_10039055
0x10039043  xor     eax, eax
0x10039045  mov     ecx, 1
0x1003904a  cmp     cx, [esi+20h]
0x1003904e  setnz   al
0x10039051  mov     [esp+158h+var_134], eax
0x10039055  push    1
0x10039057  push    30h ; '0'
0x10039059  lea     eax, [esp+160h+var_F8]
0x1003905d  push    eax
0x1003905e  mov     eax, [esp+164h+var_148]
0x10039062  push    0
0x10039064  push    offset aTables_0; "tables"
0x10039069  push    5
0x1003906b  push    dword ptr [eax+14h]
0x1003906e  push    edi
0x1003906f  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x10039075  mov     [esp+158h+var_144], eax
0x10039079  test    eax, eax
0x1003907b  jz      short loc_10039087
0x1003907d  mov     ebx, 80004005h
0x10039082  jmp     loc_100394F6
0x10039087  push    0; grbit
0x10039089  push    80000000h; cRow
0x1003908e  push    [esp+160h+tableid]; tableid
0x10039092  push    edi; sesid
0x10039093  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10039099  mov     [esp+158h+var_144], eax
0x1003909d  cmp     eax, 0FFFFF9BDh
0x100390a2  jz      short loc_100390AC
0x100390a4  test    eax, eax
0x100390a6  jnz     loc_100394F6
0x100390ac  mov     ebx, [ebp+this]
0x100390af  cmp     ebx, 2
0x100390b2  jbe     short loc_100390D1
0x100390b4  mov     eax, 8
0x100390b9  cmp     ax, [esi+20h]
0x100390bd  mov     eax, [esp+158h+var_134]
0x100390c1  jnz     short loc_100390D5
0x100390c3  xor     ecx, ecx
0x100390c5  cmp     [esi+28h], ecx
0x100390c8  cmovz   eax, ecx
0x100390cb  mov     [esp+158h+var_134], eax
0x100390cf  jmp     short loc_100390D5
0x100390d1  mov     eax, [esp+158h+var_134]
0x100390d5  cmp     [esp+158h+var_F0], 0
0x100390da  mov     [esp+158h+var_120], 0
0x100390e2  jbe     loc_10039437
0x100390e8  test    eax, eax
0x100390ea  jz      loc_10039437
0x100390f0  push    0; pretinfo
0x100390f2  push    0; grbit
0x100390f4  lea     eax, [esp+160h+pcbActual]
0x100390f8  push    eax; pcbActual
0x100390f9  push    4; cbData
0x100390fb  lea     eax, [esp+168h+pvData]
0x100390ff  push    eax; pvData
0x10039100  push    [esp+16Ch+columnid]; columnid
0x10039107  push    [esp+170h+tableid]; tableid
0x1003910b  push    edi; sesid
0x1003910c  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10039112  mov     [esp+158h+var_144], eax
0x10039116  test    eax, eax
0x10039118  jnz     loc_1003907D
0x1003911e  movzx   eax, word ptr [esp+158h+pvData]
0x10039123  test    eax, eax
0x10039125  jnz     loc_10039409
0x1003912b  mov     eax, [esp+158h+Block]
0x1003912f  xor     ecx, ecx
0x10039131  mov     byte ptr [esp+158h+var_138+3], 1
0x10039136  mov     [eax], cx
0x10039139  xor     eax, eax
0x1003913b  push    eax; pretinfo
0x1003913c  push    eax; grbit
0x1003913d  mov     [esp+160h+String1], ax
0x10039145  mov     [esp+160h+var_C0], eax
0x1003914c  lea     eax, [esp+160h+pcbActual]
0x10039150  push    eax; pcbActual
0x10039151  push    81h; cbData
0x10039156  lea     eax, [esp+168h+String1]
0x1003915d  push    eax; pvData
0x1003915e  push    [esp+16Ch+var_E8]; columnid
0x10039165  push    [esp+170h+tableid]; tableid
0x10039169  push    edi; sesid
0x1003916a  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10039170  mov     [esp+158h+var_144], eax
0x10039174  test    eax, eax
0x10039176  jnz     loc_1003907D
0x1003917c  mov     eax, [esp+158h+pcbActual]
0x10039180  and     eax, 0FFFFFFFEh
0x10039183  cmp     eax, 82h
0x10039188  jnb     loc_100395A3
0x1003918e  xor     ecx, ecx
0x10039190  mov     [esp+eax+158h+String1], cx
0x10039198  test    ebx, ebx
0x1003919a  jz      short loc_100391CE
0x1003919c  cmp     ebx, 3
0x1003919f  jb      loc_10039409
0x100391a5  xor     eax, eax
0x100391a7  cmp     ax, [esi+20h]
0x100391ab  jz      short loc_100391CE
0x100391ad  mov     eax, [esi+28h]
0x100391b0  test    eax, eax
0x100391b2  jz      short loc_100391CE
0x100391b4  push    eax; String2
0x100391b5  lea     eax, [esp+15Ch+String1]
0x100391bc  push    eax; String1
0x100391bd  call    ds:__imp___wcsicmp
0x100391c3  add     esp, 8
0x100391c6  test    eax, eax
0x100391c8  jnz     loc_10039409
0x100391ce  mov     ebx, [esp+158h+var_148]
0x100391d2  lea     eax, [esp+158h+var_11C]
0x100391d6  push    eax
0x100391d7  push    38h ; '8'
0x100391d9  lea     eax, [esp+160h+var_C8]
0x100391e0  push    eax
0x100391e1  lea     eax, [esp+164h+String1]
0x100391e8  push    eax
0x100391e9  push    dword ptr [ebx+14h]
0x100391ec  push    edi
0x100391ed  call    ds:__imp__JetGetQueryParameterInfo@24; JetGetQueryParameterInfo(x,x,x,x,x,x)
0x100391f3  mov     [esp+158h+var_144], eax
0x100391f7  test    eax, eax
0x100391f9  jns     short loc_10039212
0x100391fb  or      eax, 0FFFFFFFFh
0x100391fe  mov     [esp+158h+var_C0], 1
0x10039209  mov     [esp+158h+var_C4], eax
0x10039210  jmp     short loc_10039219
0x10039212  mov     eax, [esp+158h+var_C4]
0x10039219  push    eax; tableid
0x1003921a  push    edi; sesid
0x1003921b  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10039221  cmp     [esp+158h+var_C0], 0
0x10039229  jnz     loc_10039409
0x1003922f  lea     eax, [esp+158h+var_124]
0x10039233  push    eax
0x10039234  lea     eax, [esp+15Ch+String1]
0x1003923b  push    eax
0x1003923c  push    dword ptr [ebx+14h]
0x1003923f  push    edi
0x10039240  call    ds:__imp__JetOpenQueryDef@16; JetOpenQueryDef(x,x,x,x)
0x10039246  mov     [esp+158h+var_144], eax
0x1003924a  test    eax, eax
0x1003924c  jnz     loc_1003907D
0x10039252  push    eax
0x10039253  push    eax
0x10039254  push    eax
0x10039255  push    eax
0x10039256  lea     eax, [esp+168h+cbData]
0x1003925a  push    eax
0x1003925b  push    10000h
0x10039260  push    [esp+170h+Block]
0x10039264  push    [esp+174h+var_124]
0x10039268  push    edi
0x10039269  call    ds:__imp__JetRetrieveQoSql@36; JetRetrieveQoSql(x,x,x,x,x,x,x,x,x)
0x1003926f  mov     [esp+158h+var_144], eax
0x10039273  test    eax, eax
0x10039275  jnz     loc_1003907D
0x1003927b  mov     eax, [esp+158h+cbData]
0x1003927f  push    [esp+158h+var_124]; tableid
0x10039283  add     eax, eax
0x10039285  push    edi; sesid
0x10039286  mov     [esp+160h+cbData], eax
0x1003928a  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x10039290  mov     [esp+158h+var_144], eax
0x10039294  test    eax, eax
0x10039296  jnz     loc_1003907D
0x1003929c  push    eax; pretinfo
0x1003929d  push    eax; grbit
0x1003929e  lea     eax, [esp+160h+var_114]
0x100392a2  push    eax; pcbActual
0x100392a3  push    8; cbData
0x100392a5  lea     eax, [esp+168h+var_108]
0x100392a9  push    eax; pvData
0x100392aa  push    [esp+16Ch+var_E0]; columnid
0x100392b1  push    [esp+170h+tableid]; tableid
0x100392b5  push    edi; sesid
0x100392b6  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x100392bc  mov     [esp+158h+var_144], eax
0x100392c0  test    eax, eax
0x100392c2  jnz     loc_1003907D
0x100392c8  push    eax; pretinfo
0x100392c9  push    eax; grbit
0x100392ca  lea     eax, [esp+160h+var_114]
0x100392ce  push    eax; pcbActual
0x100392cf  push    8; cbData
0x100392d1  lea     eax, [esp+168h+var_100]
0x100392d5  push    eax; pvData
0x100392d6  push    [esp+16Ch+var_DC]; columnid
0x100392dd  push    [esp+170h+tableid]; tableid
0x100392e1  push    edi; sesid
0x100392e2  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x100392e8  mov     [esp+158h+var_144], eax
0x100392ec  test    eax, eax
0x100392ee  jnz     loc_1003907D
0x100392f4  push    eax; prep
0x100392f5  push    [esp+15Ch+var_140]; tableid
0x100392f9  push    edi; sesid
0x100392fa  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x10039300  mov     [esp+158h+var_144], eax
0x10039304  test    eax, eax
0x10039306  jnz     loc_1003907D
0x1003930c  push    eax; psetinfo
0x1003930d  push    eax; grbit
0x1003930e  push    [esp+160h+pcbActual]; cbData
0x10039312  lea     eax, [esp+164h+String1]
0x10039319  push    eax; pvData
  ... truncated ...
```
