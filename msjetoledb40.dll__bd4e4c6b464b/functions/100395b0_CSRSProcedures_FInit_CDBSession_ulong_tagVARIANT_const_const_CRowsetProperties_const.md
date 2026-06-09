# CSRSProcedures::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x100395b0`
- end: `0x10039cb8`
- name: `?FInit@CSRSProcedures@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `1800`
- prototype: `int(CSRSProcedures *__hidden this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
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
- `0x100395b0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1003987b`
- `msvcrt!_wcsicmp` at `0x1003987b`
- `msjet40!__imp__JetCloseTable@8` at `0x100398ec`
- `msjet40!__imp__JetCloseTable@8` at `0x100399ac`
- `msjet40!__imp__JetCloseTable@8` at `0x10039c72`
- `msjet40!__imp__JetCloseTable@8` at `0x100398ec`
- `msjet40!__imp__JetCloseTable@8` at `0x100399ac`
- `msjet40!__imp__JetCloseTable@8` at `0x10039c72`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10039c3f`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10039c3f`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10039744`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10039744`
- `msjet40!__imp__JetMove@16` at `0x10039768`
- `msjet40!__imp__JetMove@16` at `0x10039891`
- `msjet40!__imp__JetMove@16` at `0x10039b30`
- `msjet40!__imp__JetMove@16` at `0x10039768`
- `msjet40!__imp__JetMove@16` at `0x10039891`
- `msjet40!__imp__JetMove@16` at `0x10039b30`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10039a1c`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10039a1c`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100397fd`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003982f`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100399d8`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10039a04`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100397fd`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x1003982f`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x100399d8`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10039a04`
- `msjet40!__imp__JetSetColumn@28` at `0x10039a48`
- `msjet40!__imp__JetSetColumn@28` at `0x10039a66`
- `msjet40!__imp__JetSetColumn@28` at `0x10039a83`
- `msjet40!__imp__JetSetColumn@28` at `0x10039ad3`
- `msjet40!__imp__JetSetColumn@28` at `0x10039af8`
- `msjet40!__imp__JetSetColumn@28` at `0x10039a48`
- `msjet40!__imp__JetSetColumn@28` at `0x10039a66`
- `msjet40!__imp__JetSetColumn@28` at `0x10039a83`
- `msjet40!__imp__JetSetColumn@28` at `0x10039ad3`
- `msjet40!__imp__JetSetColumn@28` at `0x10039af8`
- `msjet40!__imp__JetUpdate@20` at `0x10039b15`
- `msjet40!__imp__JetUpdate@20` at `0x10039b15`
- `msjet40!__imp__JetGetQueryParameterInfo@24` at `0x100398d6`
- `msjet40!__imp__JetGetQueryParameterInfo@24` at `0x100398d6`
- `msjet40!__imp__JetOpenQueryDef@16` at `0x10039948`
- `msjet40!__imp__JetOpenQueryDef@16` at `0x10039948`
- `msjet40!__imp__JetRetrieveQoSql@36` at `0x1003998b`
- `msjet40!__imp__JetRetrieveQoSql@36` at `0x1003998b`

## pseudocode

```c
int __userpurge CSRSProcedures::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSProcedures *this,
        struct CDBSession *a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  _DWORD *v7; // esi
  JET_SESID v8; // edi
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  int v14; // ebx
  int v15; // ecx
  JET_COLUMNID *v16; // eax
  unsigned int v17; // esi
  JET_ERR v18; // eax
  int v19; // eax
  __int16 v20; // cx
  signed int v21; // eax
  CSchemaRowset *v22; // ecx
  JET_COLUMNID *v23; // ebx
  ColumnDataWithFakeNamesAndDBTYPES *v24; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v25; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v26; // esi
  int v27; // ecx
  unsigned int v29; // [esp-24h] [ebp-17Ch]
  ColumnDataWithFakeNamesAndDBTYPES *v30; // [esp-14h] [ebp-16Ch]
  const struct _GUID *v31; // [esp+0h] [ebp-158h]
  const struct _GUID *v32; // [esp+4h] [ebp-154h]
  unsigned int ObjectInfo; // [esp+14h] [ebp-144h] BYREF
  JET_TABLEID v35; // [esp+18h] [ebp-140h] BYREF
  JET_COLUMNID *v36; // [esp+1Ch] [ebp-13Ch]
  int v37; // [esp+20h] [ebp-138h] BYREF
  void *Block; // [esp+24h] [ebp-134h]
  int v39; // [esp+28h] [ebp-130h]
  unsigned int cbData; // [esp+2Ch] [ebp-12Ch] BYREF
  unsigned int pcbActual; // [esp+30h] [ebp-128h] BYREF
  JET_TABLEID v42; // [esp+34h] [ebp-124h] BYREF
  unsigned int v43; // [esp+38h] [ebp-120h] BYREF
  int v44; // [esp+3Ch] [ebp-11Ch]
  ColumnDataWithFakeNamesAndDBTYPES *v45; // [esp+40h] [ebp-118h] BYREF
  int pvData; // [esp+44h] [ebp-114h] BYREF
  unsigned int v47; // [esp+48h] [ebp-110h]
  int v48; // [esp+4Ch] [ebp-10Ch]
  _BYTE v49[8]; // [esp+50h] [ebp-108h] BYREF
  _BYTE v50[8]; // [esp+58h] [ebp-100h] BYREF
  int v51; // [esp+60h] [ebp-F8h] BYREF
  JET_TABLEID tableid; // [esp+64h] [ebp-F4h]
  unsigned int v53; // [esp+68h] [ebp-F0h]
  JET_COLUMNID v54; // [esp+70h] [ebp-E8h]
  JET_COLUMNID v55; // [esp+78h] [ebp-E0h]
  JET_COLUMNID v56; // [esp+7Ch] [ebp-DCh]
  JET_COLUMNID columnid; // [esp+84h] [ebp-D4h]
  int v58; // [esp+90h] [ebp-C8h] BYREF
  JET_TABLEID v59; // [esp+94h] [ebp-C4h]
  int v60; // [esp+98h] [ebp-C0h]
  wchar_t String1[70]; // [esp+C8h] [ebp-90h] BYREF

  v7 = a1;
  v48 = a2;
  cbData = (unsigned int)a4;
  v47 = a5;
  ObjectInfo = 0;
  v36 = 0;
  v39 = 1;
  Block = 0;
  tableid = -1;
  v8 = a1[4];
  if ( this )
  {
    if ( !a4
      || (unsigned int)this > 4
      || (v9 = *(unsigned __int16 *)a4, (_WORD)v9) && v9 != 1 && (v9 != 8 || *((_DWORD *)a4 + 2))
      || (unsigned int)this > 1
      && (v10 = *((unsigned __int16 *)a4 + 8), (_WORD)v10)
      && v10 != 1
      && (v10 != 8 || *((_DWORD *)a4 + 6))
      || (unsigned int)this > 2 && (v11 = *((unsigned __int16 *)a4 + 16), (_WORD)v11) && v11 != 1 && v11 != 8
      || (unsigned int)this > 3 && (v12 = *((unsigned __int16 *)a4 + 24), (_WORD)v12) && v12 != 1 && v12 != 2 )
    {
      v13 = a1[5];
      v14 = -2147024809;
      v15 = a1[4];
LABEL_84:
      if ( !JetGetDatabaseInfo(v15, v13, &v45, 4, 3) )
        CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v31, (int)v32);
      goto LABEL_86;
    }
  }
  Block = operator new(0x20000u);
  if ( !Block )
  {
    v14 = -2147024882;
    goto LABEL_80;
  }
  v16 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          32);
  v36 = v16;
  if ( !v16 )
  {
    v14 = -2147024882;
    goto LABEL_80;
  }
  v14 = SRSCreateTempTable(5, a1, &v35, v16, 0);
  if ( v14 >= 0 )
  {
    v17 = cbData;
    if ( (unsigned int)this >= 3
      && (*(_WORD *)(cbData + 32) == 1 || (unsigned int)this >= 4 && *(_WORD *)(cbData + 48) == 1) )
    {
      v39 = 0;
    }
    ObjectInfo = JetGetObjectInfo(v8, a1[5], 5, L"tables", 0, &v51, 48, 1);
    if ( ObjectInfo )
    {
LABEL_33:
      v14 = -2147467259;
LABEL_79:
      v7 = a1;
      goto LABEL_80;
    }
    v18 = JetMove(v8, tableid, 0x80000000, 0);
    ObjectInfo = v18;
    if ( v18 != -1603 && v18 )
      goto LABEL_79;
    if ( (unsigned int)this <= 2 )
    {
      v19 = v39;
    }
    else
    {
      v19 = v39;
      if ( *(_WORD *)(v17 + 32) == 8 )
      {
        if ( !*(_DWORD *)(v17 + 40) )
          v19 = 0;
        v39 = v19;
      }
    }
    v44 = 0;
    if ( !v53 )
    {
LABEL_74:
      v24 = (ColumnDataWithFakeNamesAndDBTYPES *)operator new(0x20u);
      v45 = v24;
      if ( v24 && (v25 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(v24), (v26 = v25) != 0) )
      {
        *((_DWORD *)v25 + 4) = 0;
        *((_DWORD *)v25 + 5) = &SRSProceduresDefNames;
        *((_DWORD *)v25 + 7) = 0;
        v14 = ColumnData::FInit(v25, v8, a1[5], v35, (int *)&ObjectInfo, 0, (int)&SRSProceduresDefNames);
        if ( v14 >= 0 )
        {
          v27 = v48;
          v30 = v26;
          v29 = v47;
          *((_DWORD *)v26 + 1) = 8;
          v7 = a1;
          v14 = CRowset::FInit(v27, 0, a1, 0, 0, 0, v35, v29, 1, 0, 0, v30, 1, 0, 0, &GUID_NULL);
          goto LABEL_80;
        }
      }
      else
      {
        v14 = -2147024882;
      }
      goto LABEL_79;
    }
    while ( 1 )
    {
      if ( !v19 )
        goto LABEL_74;
      v43 = 0;
      *(_WORD *)Block = 0;
      String1[0] = 0;
      ObjectInfo = JetRetrieveColumn(v8, tableid, columnid, &pvData, 4u, &pcbActual, 0, 0);
      if ( ObjectInfo )
        goto LABEL_33;
      ObjectInfo = JetRetrieveColumn(v8, tableid, v54, String1, 0x81u, &pcbActual, 0, 0);
      if ( ObjectInfo )
        goto LABEL_33;
      if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
        __report_rangecheckfailure();
      *(wchar_t *)((char *)String1 + (pcbActual & 0xFFFFFFFE)) = 0;
      if ( (unsigned int)this < 3
        || !*(_WORD *)(v17 + 32)
        || *(_DWORD *)(v17 + 40) && !__wcsicmp(String1, *(const wchar_t **)(v17 + 40)) )
      {
        v20 = 2;
        LOWORD(v37) = 2;
        if ( !(_WORD)pvData )
        {
          LOWORD(v37) = 3;
          ObjectInfo = JetGetQueryParameterInfo(v8, a1[5], String1, &v58, 56, &v45);
          if ( (ObjectInfo & 0x80000000) == 0 )
          {
            ObjectInfo = JetCloseTable(v8, v59);
            v59 = -1;
            if ( (ObjectInfo & 0x80000000) != 0 )
              goto LABEL_33;
            if ( !v60 )
              goto LABEL_72;
          }
          v20 = v37;
        }
        if ( this != (CSRSProcedures *)4 || *(_WORD *)(v17 + 48) != 2 || *(_WORD *)(v17 + 56) == v20 )
        {
          v21 = JetOpenQueryDef(v8, a1[5], String1, &v42);
          ObjectInfo = v21;
          if ( v21 != -1907 && v21 != -1809 )
          {
            if ( v21 < 0 )
              goto LABEL_33;
            ObjectInfo = JetRetrieveQoSql(v8, v42, Block, 0x10000, &cbData, 0, 0, 0, 0);
            if ( ObjectInfo )
              goto LABEL_33;
            cbData *= 2;
            ObjectInfo = JetCloseTable(v8, v42);
            if ( ObjectInfo )
              goto LABEL_33;
            ObjectInfo = JetRetrieveColumn(v8, tableid, v55, v49, 8u, &v43, 0, 0);
            if ( ObjectInfo )
              goto LABEL_33;
            ObjectInfo = JetRetrieveColumn(v8, tableid, v56, v50, 8u, &v43, 0, 0);
            if ( ObjectInfo )
              goto LABEL_33;
            ObjectInfo = JetPrepareUpdate(v8, v35, 0);
            if ( ObjectInfo )
              goto LABEL_33;
            JetSetColumn(v8, v35, v36[2], String1, pcbActual, 0, 0);
            JetSetColumn(v8, v35, v36[4], Block, cbData, 0, 0);
            JetSetColumn(v8, v35, v36[3], &v37, 2u, 0, 0);
            v14 = CSchemaRowset::MapStringPropertyValueToColumn(
                    v22,
                    v8,
                    a1[5],
                    (const unsigned __int16 *)v22,
                    String1,
                    0,
                    L"Description",
                    v35,
                    v36[5],
                    (int *)&ObjectInfo);
            if ( v14 < 0 )
              goto LABEL_79;
            v23 = v36;
            ObjectInfo = JetSetColumn(v8, v35, v36[6], v49, 8u, 0, 0);
            if ( (ObjectInfo & 0x80000000) != 0 )
              goto LABEL_33;
            ObjectInfo = JetSetColumn(v8, v35, v23[7], v50, 8u, 0, 0);
            if ( (ObjectInfo & 0x80000000) != 0 )
              goto LABEL_33;
            ObjectInfo = JetUpdate(v8, v35, 0, 0, 0);
            if ( ObjectInfo )
              goto LABEL_33;
          }
        }
      }
LABEL_72:
      ObjectInfo = JetMove(v8, tableid, 1, 0);
      if ( ++v44 >= v53 )
        goto LABEL_74;
      v19 = v39;
    }
  }
LABEL_80:
  if ( ObjectInfo )
  {
    CExtError::SendJetErrortoOLEAuto(ObjectInfo, (int)&IID_IDBSchemaRowset, (int)v31, v32);
    goto LABEL_86;
  }
  if ( v14 < 0 )
  {
    v13 = v7[5];
    v15 = v7[4];
    if ( v14 != -2147024882 )
      goto LABEL_84;
  }
LABEL_86:
  if ( Block )
    operator delete(Block);
  if ( tableid != -1 )
    JetCloseTable(v8, tableid);
  if ( v36 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v36);
  return v14;
}

```

## disassembly

```asm
0x100395b0  mov     edi, edi
0x100395b2  push    ebp
0x100395b3  mov     ebp, esp
0x100395b5  and     esp, 0FFFFFFF8h
0x100395b8  sub     esp, 14Ch
0x100395be  mov     eax, ___security_cookie
0x100395c3  xor     eax, esp
0x100395c5  mov     [esp+14Ch+var_4], eax
0x100395cc  mov     eax, [ebp+arg_4]
0x100395cf  push    ebx
0x100395d0  push    esi; int
0x100395d1  mov     esi, edx
0x100395d3  mov     [esp+154h+var_10C], ecx
0x100395d7  mov     edx, [ebp+this]
0x100395da  mov     ecx, [ebp+arg_8]
0x100395dd  mov     [esp+154h+var_148], esi
0x100395e1  mov     [esp+154h+cbData], eax
0x100395e5  mov     [esp+154h+var_110], ecx
0x100395e9  mov     [esp+154h+var_144], 0
0x100395f1  mov     [esp+154h+var_13C], 0
0x100395f9  mov     [esp+154h+var_130], 1
0x10039601  mov     [esp+154h+Block], 0
0x10039609  mov     [esp+154h+tableid], 0FFFFFFFFh
0x10039611  push    edi; struct _GUID *
0x10039612  mov     edi, [esi+10h]
0x10039615  test    edx, edx
0x10039617  jz      short loc_10039697
0x10039619  test    eax, eax
0x1003961b  jz      short loc_10039688
0x1003961d  cmp     edx, 4
0x10039620  ja      short loc_10039688
0x10039622  movzx   ecx, word ptr [eax]
0x10039625  test    cx, cx
0x10039628  jz      short loc_1003963A
0x1003962a  cmp     ecx, 1
0x1003962d  jz      short loc_1003963A
0x1003962f  cmp     ecx, 8
0x10039632  jnz     short loc_10039688
0x10039634  cmp     dword ptr [eax+8], 0
0x10039638  jnz     short loc_10039688
0x1003963a  cmp     edx, 1
0x1003963d  jbe     short loc_10039658
0x1003963f  movzx   ecx, word ptr [eax+10h]
0x10039643  test    cx, cx
0x10039646  jz      short loc_10039658
0x10039648  cmp     ecx, 1
0x1003964b  jz      short loc_10039658
0x1003964d  cmp     ecx, 8
0x10039650  jnz     short loc_10039688
0x10039652  cmp     dword ptr [eax+18h], 0
0x10039656  jnz     short loc_10039688
0x10039658  cmp     edx, 2
0x1003965b  jbe     short loc_10039670
0x1003965d  movzx   ecx, word ptr [eax+20h]
0x10039661  test    cx, cx
0x10039664  jz      short loc_10039670
0x10039666  cmp     ecx, 1
0x10039669  jz      short loc_10039670
0x1003966b  cmp     ecx, 8
0x1003966e  jnz     short loc_10039688
0x10039670  cmp     edx, 3
0x10039673  jbe     short loc_10039697
0x10039675  movzx   eax, word ptr [eax+30h]
0x10039679  test    ax, ax
0x1003967c  jz      short loc_10039697
0x1003967e  cmp     eax, 1
0x10039681  jz      short loc_10039697
0x10039683  cmp     eax, 2
0x10039686  jz      short loc_10039697
0x10039688  mov     eax, [esi+14h]
0x1003968b  mov     ebx, 80070057h
0x10039690  mov     ecx, edi
0x10039692  jmp     loc_10039C34
0x10039697  push    20000h; Size
0x1003969c  call    ??2@YAPAXI@Z; operator new(uint)
0x100396a1  add     esp, 4
0x100396a4  mov     [esp+158h+Block], eax
0x100396a8  test    eax, eax
0x100396aa  jnz     short loc_100396B6
0x100396ac  mov     ebx, 8007000Eh
0x100396b1  jmp     loc_10039BF6
0x100396b6  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x100396bc  push    20h ; ' '
0x100396be  push    ecx
0x100396bf  mov     eax, [ecx]
0x100396c1  mov     esi, [eax+0Ch]
0x100396c4  mov     ecx, esi
0x100396c6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100396cc  call    esi
0x100396ce  mov     esi, [esp+158h+var_148]
0x100396d2  mov     [esp+158h+var_13C], eax
0x100396d6  test    eax, eax
0x100396d8  jnz     short loc_100396E4
0x100396da  mov     ebx, 8007000Eh
0x100396df  jmp     loc_10039BF6
0x100396e4  push    0
0x100396e6  push    eax
0x100396e7  lea     eax, [esp+160h+var_140]
0x100396eb  mov     edx, esi
0x100396ed  push    eax
0x100396ee  mov     ecx, 5
0x100396f3  call    SRSCreateTempTable
0x100396f8  mov     ebx, eax
0x100396fa  test    ebx, ebx
0x100396fc  js      loc_10039BF6
0x10039702  mov     eax, [ebp+this]
0x10039705  mov     esi, [esp+158h+cbData]
0x10039709  cmp     eax, 3
0x1003970c  jb      short loc_1003972A
0x1003970e  mov     ecx, 1
0x10039713  cmp     cx, [esi+20h]
0x10039717  jz      short loc_10039724
0x10039719  cmp     eax, 4
0x1003971c  jb      short loc_1003972A
0x1003971e  cmp     cx, [esi+30h]
0x10039722  jnz     short loc_1003972A
0x10039724  xor     ecx, ecx
0x10039726  mov     [esp+158h+var_130], ecx
0x1003972a  push    1
0x1003972c  push    30h ; '0'
0x1003972e  lea     eax, [esp+160h+var_F8]
0x10039732  push    eax
0x10039733  mov     eax, [esp+164h+var_148]
0x10039737  push    0
0x10039739  push    offset aTables_0; "tables"
0x1003973e  push    5
0x10039740  push    dword ptr [eax+14h]
0x10039743  push    edi
0x10039744  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x1003974a  mov     [esp+158h+var_144], eax
0x1003974e  test    eax, eax
0x10039750  jz      short loc_1003975C
0x10039752  mov     ebx, 80004005h
0x10039757  jmp     loc_10039BF2
0x1003975c  push    0; grbit
0x1003975e  push    80000000h; cRow
0x10039763  push    [esp+160h+tableid]; tableid
0x10039767  push    edi; sesid
0x10039768  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003976e  mov     [esp+158h+var_144], eax
0x10039772  cmp     eax, 0FFFFF9BDh
0x10039777  jz      short loc_10039781
0x10039779  test    eax, eax
0x1003977b  jnz     loc_10039BF2
0x10039781  cmp     [ebp+this], 2
0x10039785  jbe     short loc_100397A4
0x10039787  mov     eax, 8
0x1003978c  cmp     ax, [esi+20h]
0x10039790  mov     eax, [esp+158h+var_130]
0x10039794  jnz     short loc_100397A8
0x10039796  xor     ecx, ecx
0x10039798  cmp     [esi+28h], ecx
0x1003979b  cmovz   eax, ecx
0x1003979e  mov     [esp+158h+var_130], eax
0x100397a2  jmp     short loc_100397A8
0x100397a4  mov     eax, [esp+158h+var_130]
0x100397a8  cmp     [esp+158h+var_F0], 0
0x100397ad  mov     [esp+158h+var_11C], 0
0x100397b5  jbe     loc_10039B57
0x100397bb  mov     ebx, 2
0x100397c0  test    eax, eax
0x100397c2  jz      loc_10039B57
0x100397c8  mov     eax, [esp+158h+Block]
0x100397cc  xor     ecx, ecx
0x100397ce  mov     [esp+158h+var_120], 0
0x100397d6  mov     [eax], cx
0x100397d9  xor     eax, eax
0x100397db  push    eax; pretinfo
0x100397dc  push    eax; grbit
0x100397dd  mov     [esp+160h+String1], ax
0x100397e5  lea     eax, [esp+160h+pcbActual]
0x100397e9  push    eax; pcbActual
0x100397ea  push    4; cbData
0x100397ec  lea     eax, [esp+168h+pvData]
0x100397f0  push    eax; pvData
0x100397f1  push    [esp+16Ch+columnid]; columnid
0x100397f8  push    [esp+170h+tableid]; tableid
0x100397fc  push    edi; sesid
0x100397fd  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10039803  mov     [esp+158h+var_144], eax
0x10039807  test    eax, eax
0x10039809  jnz     loc_10039752
0x1003980f  push    eax; pretinfo
0x10039810  push    eax; grbit
0x10039811  lea     eax, [esp+160h+pcbActual]
0x10039815  push    eax; pcbActual
0x10039816  push    81h; cbData
0x1003981b  lea     eax, [esp+168h+String1]
0x10039822  push    eax; pvData
0x10039823  push    [esp+16Ch+var_E8]; columnid
0x1003982a  push    [esp+170h+tableid]; tableid
0x1003982e  push    edi; sesid
0x1003982f  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10039835  mov     [esp+158h+var_144], eax
0x10039839  test    eax, eax
0x1003983b  jnz     loc_10039752
0x10039841  mov     eax, [esp+158h+pcbActual]
0x10039845  and     eax, 0FFFFFFFEh
0x10039848  cmp     eax, 82h
0x1003984d  jnb     loc_10039CB3
0x10039853  xor     ecx, ecx
0x10039855  cmp     [ebp+this], 3
0x10039859  mov     [esp+eax+158h+String1], cx
0x10039861  jb      short loc_1003989C
0x10039863  xor     eax, eax
0x10039865  cmp     ax, [esi+20h]
0x10039869  jz      short loc_1003989C
0x1003986b  mov     eax, [esi+28h]
0x1003986e  test    eax, eax
0x10039870  jz      short loc_10039888
0x10039872  push    eax; String2
0x10039873  lea     eax, [esp+15Ch+String1]
0x1003987a  push    eax; String1
0x1003987b  call    ds:__imp___wcsicmp
0x10039881  add     esp, 8
0x10039884  test    eax, eax
0x10039886  jz      short loc_1003989C
0x10039888  push    0; grbit
0x1003988a  push    1; cRow
0x1003988c  push    [esp+160h+tableid]; tableid
0x10039890  push    edi; sesid
0x10039891  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10039897  jmp     loc_10039B3B
0x1003989c  movzx   eax, word ptr [esp+158h+pvData]
0x100398a1  mov     cx, bx
0x100398a4  mov     ebx, [esp+158h+var_148]
0x100398a8  mov     word ptr [esp+158h+var_138], cx
0x100398ad  test    eax, eax
0x100398af  jnz     short loc_1003991C
0x100398b1  mov     eax, 3
0x100398b6  mov     word ptr [esp+158h+var_138], ax
0x100398bb  lea     eax, [esp+158h+var_118]
0x100398bf  push    eax
0x100398c0  push    38h ; '8'
0x100398c2  lea     eax, [esp+160h+var_C8]
0x100398c9  push    eax
0x100398ca  lea     eax, [esp+164h+String1]
0x100398d1  push    eax
0x100398d2  push    dword ptr [ebx+14h]
0x100398d5  push    edi
0x100398d6  call    ds:__imp__JetGetQueryParameterInfo@24; JetGetQueryParameterInfo(x,x,x,x,x,x)
0x100398dc  mov     [esp+158h+var_144], eax
0x100398e0  test    eax, eax
0x100398e2  js      short loc_10039917
0x100398e4  push    [esp+158h+var_C4]; tableid
0x100398eb  push    edi; sesid
0x100398ec  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x100398f2  mov     [esp+158h+var_144], eax
0x100398f6  mov     [esp+158h+var_C4], 0FFFFFFFFh
0x10039901  test    eax, eax
0x10039903  js      loc_10039752
0x10039909  cmp     [esp+158h+var_C0], 0
0x10039911  jz      loc_10039B27
0x10039917  mov     cx, word ptr [esp+158h+var_138]
0x1003991c  cmp     [ebp+this], 4
0x10039920  jnz     short loc_10039937
0x10039922  mov     eax, 2
0x10039927  cmp     ax, [esi+30h]
0x1003992b  jnz     short loc_10039937
0x1003992d  cmp     [esi+38h], cx
0x10039931  jnz     loc_10039B27
0x10039937  lea     eax, [esp+158h+var_124]
0x1003993b  push    eax
0x1003993c  lea     eax, [esp+15Ch+String1]
0x10039943  push    eax
0x10039944  push    dword ptr [ebx+14h]
0x10039947  push    edi
0x10039948  call    ds:__imp__JetOpenQueryDef@16; JetOpenQueryDef(x,x,x,x)
0x1003994e  mov     [esp+158h+var_144], eax
0x10039952  cmp     eax, 0FFFFF88Dh
0x10039957  jz      loc_10039B27
0x1003995d  cmp     eax, 0FFFFF8EFh
0x10039962  jz      loc_10039B27
0x10039968  test    eax, eax
0x1003996a  js      loc_10039752
0x10039970  push    0
0x10039972  push    0
0x10039974  push    0
0x10039976  push    0
0x10039978  lea     eax, [esp+168h+cbData]
0x1003997c  push    eax
0x1003997d  push    10000h
0x10039982  push    [esp+170h+Block]
0x10039986  push    [esp+174h+var_124]
0x1003998a  push    edi
0x1003998b  call    ds:__imp__JetRetrieveQoSql@36; JetRetrieveQoSql(x,x,x,x,x,x,x,x,x)
0x10039991  mov     [esp+158h+var_144], eax
0x10039995  test    eax, eax
0x10039997  jnz     loc_10039752
0x1003999d  mov     eax, [esp+158h+cbData]
0x100399a1  push    [esp+158h+var_124]; tableid
0x100399a5  add     eax, eax
0x100399a7  push    edi; sesid
0x100399a8  mov     [esp+160h+cbData], eax
0x100399ac  call    ds:__imp__JetCloseTable@8; JetCloseTable(x,x)
0x100399b2  mov     [esp+158h+var_144], eax
0x100399b6  test    eax, eax
0x100399b8  jnz     loc_10039752
0x100399be  push    eax; pretinfo
0x100399bf  push    eax; grbit
  ... truncated ...
```
