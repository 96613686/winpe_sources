# CSRSIsamStats::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x1003eb30`
- end: `0x1003ed95`
- name: `?FInit@CSRSIsamStats@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `613`
- prototype: `int(CSRSIsamStats *__hidden this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x1000d570`
- `0x10013100`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1001f2d0`
- `0x10028340`
- `0x10035e60`
- `0x1003eb30`
- `0x1004ce5d`

## import_xrefs

- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003ed55`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003ed55`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003ebf6`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x1003ebf6`
- `msjet40!__imp__JetSetColumn@28` at `0x1003ec40`
- `msjet40!__imp__JetSetColumn@28` at `0x1003ec40`
- `msjet40!__imp__JetUpdate@20` at `0x1003ec70`
- `msjet40!__imp__JetUpdate@20` at `0x1003ec70`
- `msjet40!__imp__JetGetISAMStatCount@8` at `0x1003ec1c`
- `msjet40!__imp__JetGetISAMStatCount@8` at `0x1003ec1c`
- `msjet40!__imp__JetResetISAMStatCount@4` at `0x1003ec4c`
- `msjet40!__imp__JetResetISAMStatCount@4` at `0x1003ec4c`

## pseudocode

```c
int __userpurge CSRSIsamStats::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSIsamStats *this,
        struct CDBSession *a4,
        struct CSettableProperties *a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  JET_COLUMNID *v8; // ebx
  JoltProperties *v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // ecx
  JET_COLUMNID *v13; // eax
  _DWORD *v14; // esi
  unsigned int v15; // edi
  unsigned int i; // esi
  JET_SESID v17; // edi
  ColumnDataWithFakeNamesAndDBTYPES *v18; // eax
  ColumnDataWithFakeNamesAndDBTYPES *v19; // eax
  int v20; // ecx
  int v22; // [esp-14h] [ebp-38h]
  const struct _GUID *v23; // [esp+0h] [ebp-24h]
  const struct _GUID *v24; // [esp+4h] [ebp-20h]
  int v25; // [esp+Ch] [ebp-18h] BYREF
  unsigned int pvData; // [esp+10h] [ebp-14h] BYREF
  JET_SESID sesid; // [esp+14h] [ebp-10h]
  unsigned int ISAMStatCount; // [esp+18h] [ebp-Ch] BYREF
  JET_TABLEID tableid; // [esp+1Ch] [ebp-8h] BYREF
  _DWORD *v30; // [esp+20h] [ebp-4h]

  v25 = a2;
  v30 = a1;
  v8 = 0;
  ISAMStatCount = 0;
  v9 = (JoltProperties *)a1[37];
  sesid = a1[4];
  tableid = -1;
  pvData = JoltProperties::BinarySearch(v9, 0x104u, &pvData) >= 0
        && *(_WORD *)(*((_DWORD *)v9 + 4) + 48 * pvData + 24) == 0xFFFF;
  if ( this )
  {
    v10 = a1[5];
    v11 = -2147024809;
    v12 = a1[4];
LABEL_27:
    if ( !JetGetDatabaseInfo(v12, v10, &v25, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v23, (int)v24);
    goto LABEL_29;
  }
  v13 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          48);
  v14 = v30;
  v8 = v13;
  if ( v13 )
  {
    v11 = SRSCreateTempTable(17, v30, &tableid, v13, 0);
    if ( v11 >= 0 )
    {
      ISAMStatCount = JetPrepareUpdate(sesid, tableid, 0);
      if ( ISAMStatCount )
      {
LABEL_22:
        v11 = -2147467259;
      }
      else
      {
        v15 = pvData;
        for ( i = 0; i < 0xC; ++i )
        {
          pvData = 0;
          ISAMStatCount = JetGetISAMStatCount(i, &pvData);
          if ( (ISAMStatCount & 0x80000000) != 0 )
            goto LABEL_21;
          JetSetColumn(sesid, tableid, v8[i], &pvData, 4u, 0, 0);
          if ( v15 == 1 )
          {
            ISAMStatCount = JetResetISAMStatCount(i);
            if ( (ISAMStatCount & 0x80000000) != 0 )
              goto LABEL_21;
          }
        }
        v17 = sesid;
        ISAMStatCount = JetUpdate(sesid, tableid, 0, 0, 0);
        if ( ISAMStatCount )
        {
LABEL_21:
          v14 = v30;
          goto LABEL_22;
        }
        v18 = (ColumnDataWithFakeNamesAndDBTYPES *)operator new(0x20u);
        pvData = (unsigned int)v18;
        if ( v18
          && (v19 = ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(v18),
              (pvData = (unsigned int)v19) != 0) )
        {
          v14 = v30;
          *((_DWORD *)v19 + 4) = 0;
          *((_DWORD *)v19 + 5) = &SRSIsamStatsNames;
          *((_DWORD *)v19 + 7) = 0;
          v11 = ColumnData::FInit(v19, v17, v14[5], tableid, (int *)&ISAMStatCount, 0, (int)&SRSIsamStatsNames);
          if ( v11 >= 0 )
          {
            v20 = v25;
            v22 = pvData;
            *(_DWORD *)(pvData + 4) = 12;
            v11 = CRowset::FInit(v20, (int)v14, 0, 0, 0, tableid, a5, 1, 0, 0, v22, 1, 0, 0, &GUID_NULL);
          }
        }
        else
        {
          v14 = v30;
          v11 = -2147024882;
        }
      }
    }
  }
  else
  {
    v11 = -2147024882;
  }
  if ( ISAMStatCount )
  {
    CExtError::SendJetErrortoOLEAuto(v11, (char *)v14[4], ISAMStatCount, (int)&IID_IDBSchemaRowset, (int)v23, v24);
    goto LABEL_29;
  }
  if ( v11 < 0 )
  {
    v10 = v14[5];
    v12 = v14[4];
    if ( v11 != -2147024882 )
      goto LABEL_27;
  }
LABEL_29:
  if ( v8 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v8);
  return v11;
}

```

## disassembly

```asm
0x1003eb30  mov     edi, edi
0x1003eb32  push    ebp
0x1003eb33  mov     ebp, esp
0x1003eb35  sub     esp, 18h
0x1003eb38  push    ebx
0x1003eb39  push    esi; int
0x1003eb3a  mov     esi, edx
0x1003eb3c  mov     [ebp+var_18], ecx
0x1003eb3f  push    edi; struct _GUID *
0x1003eb40  mov     [ebp+var_4], esi
0x1003eb43  xor     ebx, ebx
0x1003eb45  mov     [ebp+var_C], 0
0x1003eb4c  mov     eax, [esi+10h]
0x1003eb4f  mov     edi, [esi+94h]
0x1003eb55  mov     ecx, edi; this
0x1003eb57  mov     [ebp+sesid], eax
0x1003eb5a  lea     eax, [ebp+pvData]
0x1003eb5d  push    eax; unsigned int *
0x1003eb5e  push    104h; unsigned int
0x1003eb63  mov     [ebp+tableid], 0FFFFFFFFh
0x1003eb6a  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x1003eb6f  test    eax, eax
0x1003eb71  js      short loc_1003EB8E
0x1003eb73  mov     eax, [ebp+pvData]
0x1003eb76  xor     edx, edx
0x1003eb78  lea     ecx, [eax+eax*2]
0x1003eb7b  mov     eax, [edi+10h]
0x1003eb7e  add     ecx, ecx
0x1003eb80  cmp     word ptr [eax+ecx*8+18h], 0FFFFh
0x1003eb86  setz    dl
0x1003eb89  mov     [ebp+pvData], edx
0x1003eb8c  jmp     short loc_1003EB91
0x1003eb8e  mov     [ebp+pvData], ebx
0x1003eb91  cmp     [ebp+this], ebx
0x1003eb94  jz      short loc_1003EBA6
0x1003eb96  mov     eax, [esi+14h]
0x1003eb99  mov     edi, 80070057h
0x1003eb9e  mov     ecx, [esi+10h]
0x1003eba1  jmp     loc_1003ED4B
0x1003eba6  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1003ebac  push    30h ; '0'
0x1003ebae  push    ecx
0x1003ebaf  mov     eax, [ecx]
0x1003ebb1  mov     esi, [eax+0Ch]
0x1003ebb4  mov     ecx, esi
0x1003ebb6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003ebbc  call    esi
0x1003ebbe  mov     esi, [ebp+var_4]
0x1003ebc1  mov     ebx, eax
0x1003ebc3  test    ebx, ebx
0x1003ebc5  jnz     short loc_1003EBD1
0x1003ebc7  mov     edi, 8007000Eh
0x1003ebcc  jmp     loc_1003ED1E
0x1003ebd1  push    0
0x1003ebd3  push    ebx
0x1003ebd4  lea     eax, [ebp+tableid]
0x1003ebd7  mov     edx, esi
0x1003ebd9  push    eax
0x1003ebda  mov     ecx, 11h
0x1003ebdf  call    SRSCreateTempTable
0x1003ebe4  mov     edi, eax
0x1003ebe6  test    edi, edi
0x1003ebe8  js      loc_1003ED1E
0x1003ebee  push    0; prep
0x1003ebf0  push    [ebp+tableid]; tableid
0x1003ebf3  push    [ebp+sesid]; sesid
0x1003ebf6  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x1003ebfc  mov     [ebp+var_C], eax
0x1003ebff  test    eax, eax
0x1003ec01  jnz     loc_1003ED19
0x1003ec07  mov     edi, [ebp+pvData]
0x1003ec0a  xor     esi, esi
0x1003ec0c  nop     dword ptr [eax+00h]
0x1003ec10  lea     eax, [ebp+pvData]
0x1003ec13  mov     [ebp+pvData], 0
0x1003ec1a  push    eax
0x1003ec1b  push    esi
0x1003ec1c  call    ds:__imp__JetGetISAMStatCount@8; JetGetISAMStatCount(x,x)
0x1003ec22  mov     [ebp+var_C], eax
0x1003ec25  test    eax, eax
0x1003ec27  js      loc_1003ED16
0x1003ec2d  push    0; psetinfo
0x1003ec2f  push    0; grbit
0x1003ec31  push    4; cbData
0x1003ec33  lea     eax, [ebp+pvData]
0x1003ec36  push    eax; pvData
0x1003ec37  push    dword ptr [ebx+esi*4]; columnid
0x1003ec3a  push    [ebp+tableid]; tableid
0x1003ec3d  push    [ebp+sesid]; sesid
0x1003ec40  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x1003ec46  cmp     edi, 1
0x1003ec49  jnz     short loc_1003EC5D
0x1003ec4b  push    esi
0x1003ec4c  call    ds:__imp__JetResetISAMStatCount@4; JetResetISAMStatCount(x)
0x1003ec52  mov     [ebp+var_C], eax
0x1003ec55  test    eax, eax
0x1003ec57  js      loc_1003ED16
0x1003ec5d  inc     esi
0x1003ec5e  cmp     esi, 0Ch
0x1003ec61  jb      short loc_1003EC10
0x1003ec63  mov     edi, [ebp+sesid]
0x1003ec66  push    0; pcbActual
0x1003ec68  push    0; cbBookmark
0x1003ec6a  push    0; pvBookmark
0x1003ec6c  push    [ebp+tableid]; tableid
0x1003ec6f  push    edi; sesid
0x1003ec70  call    ds:__imp__JetUpdate@20; JetUpdate(x,x,x,x,x)
0x1003ec76  mov     [ebp+var_C], eax
0x1003ec79  test    eax, eax
0x1003ec7b  jnz     loc_1003ED16
0x1003ec81  push    20h ; ' '; Size
0x1003ec83  call    ??2@YAPAXI@Z; operator new(uint)
0x1003ec88  add     esp, 4
0x1003ec8b  mov     [ebp+pvData], eax
0x1003ec8e  test    eax, eax
0x1003ec90  jz      short loc_1003ED0C
0x1003ec92  mov     ecx, eax; this
0x1003ec94  call    ??0ColumnDataWithFakeNamesAndDBTYPES@@QAE@XZ; ColumnDataWithFakeNamesAndDBTYPES::ColumnDataWithFakeNamesAndDBTYPES(void)
0x1003ec99  mov     [ebp+pvData], eax
0x1003ec9c  test    eax, eax
0x1003ec9e  jz      short loc_1003ED0C
0x1003eca0  mov     esi, [ebp+var_4]
0x1003eca3  mov     dword ptr [eax+10h], 0
0x1003ecaa  mov     ecx, ds:off_10003428
0x1003ecb0  push    ecx; int
0x1003ecb1  mov     [eax+14h], ecx
0x1003ecb4  lea     ecx, [ebp+var_C]
0x1003ecb7  push    0; int
0x1003ecb9  push    ecx; int *
0x1003ecba  mov     dword ptr [eax+1Ch], 0
0x1003ecc1  mov     ecx, eax; this
0x1003ecc3  push    [ebp+tableid]; unsigned int
0x1003ecc6  push    dword ptr [esi+14h]; unsigned int
0x1003ecc9  push    edi; sesid
0x1003ecca  call    ?FInit@ColumnData@@QAEJKKKAAJHH@Z; ColumnData::FInit(ulong,ulong,ulong,long &,int,int)
0x1003eccf  mov     edi, eax
0x1003ecd1  test    edi, edi
0x1003ecd3  js      short loc_1003ED1E
0x1003ecd5  mov     eax, [ebp+pvData]
0x1003ecd8  xor     edx, edx
0x1003ecda  push    offset _GUID_NULL
0x1003ecdf  push    0
0x1003ece1  push    0
0x1003ece3  push    1
0x1003ece5  mov     ecx, [ebp+var_18]
0x1003ece8  push    eax
0x1003ece9  push    0
0x1003eceb  push    0
0x1003eced  push    1
0x1003ecef  push    [ebp+arg_8]
0x1003ecf2  mov     dword ptr [eax+4], 0Ch
0x1003ecf9  push    [ebp+tableid]
0x1003ecfc  push    0
0x1003ecfe  push    0
0x1003ed00  push    0
0x1003ed02  push    esi
0x1003ed03  call    ?FInit@CRowset@@QAGJKPAVCDBSession@@PAVCCommand@@PAG2KABVCRowsetProperties@@W4eJetCursorType@@PAXPAKPAVColumnData@@HKQAUtagDBPROPSET@@ABU_GUID@@@Z; CRowset::FInit(ulong,CDBSession *,CCommand *,ushort *,ushort *,ulong,CRowsetProperties const &,eJetCursorType,void *,ulong *,ColumnData *,int,ulong,tagDBPROPSET * const,_GUID const &)
0x1003ed08  mov     edi, eax
0x1003ed0a  jmp     short loc_1003ED1E
0x1003ed0c  mov     esi, [ebp+var_4]
0x1003ed0f  mov     edi, 8007000Eh
0x1003ed14  jmp     short loc_1003ED1E
0x1003ed16  mov     esi, [ebp+var_4]
0x1003ed19  mov     edi, 80004005h
0x1003ed1e  mov     eax, [ebp+var_C]
0x1003ed21  mov     edx, edi
0x1003ed23  test    eax, eax
0x1003ed25  jz      short loc_1003ED37
0x1003ed27  mov     ecx, [esi+10h]
0x1003ed2a  push    offset _IID_IDBSchemaRowset; int
0x1003ed2f  push    eax; unsigned int
0x1003ed30  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1003ed35  jmp     short loc_1003ED6C
0x1003ed37  test    edi, edi
0x1003ed39  jns     short loc_1003ED6C
0x1003ed3b  mov     eax, [esi+14h]
0x1003ed3e  mov     edi, edx
0x1003ed40  mov     ecx, [esi+10h]
0x1003ed43  cmp     edx, 8007000Eh
0x1003ed49  jz      short loc_1003ED6C
0x1003ed4b  push    3
0x1003ed4d  push    4
0x1003ed4f  lea     edx, [ebp+var_18]
0x1003ed52  push    edx
0x1003ed53  push    eax
0x1003ed54  push    ecx
0x1003ed55  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1003ed5b  test    eax, eax
0x1003ed5d  jnz     short loc_1003ED6C
0x1003ed5f  push    eax; int
0x1003ed60  push    offset _IID_IDBSchemaRowset; int
0x1003ed65  mov     edx, edi
0x1003ed67  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1003ed6c  test    ebx, ebx
0x1003ed6e  jz      short loc_1003ED8A
0x1003ed70  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1003ed75  test    eax, eax
0x1003ed77  jz      short loc_1003ED8A
0x1003ed79  mov     ecx, [eax]
0x1003ed7b  push    ebx
0x1003ed7c  push    eax
0x1003ed7d  mov     esi, [ecx+14h]
0x1003ed80  mov     ecx, esi
0x1003ed82  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1003ed88  call    esi
0x1003ed8a  mov     eax, edi
0x1003ed8c  pop     edi
0x1003ed8d  pop     esi
0x1003ed8e  pop     ebx
0x1003ed8f  mov     esp, ebp
0x1003ed91  pop     ebp
0x1003ed92  retn    0Ch
```
