# CSRSStatistics::FInit(CDBSession *,ulong,tagVARIANT const * const,CRowsetProperties const &)

- ea: `0x10039cc0`
- end: `0x1003a18a`
- name: `?FInit@CSRSStatistics@@QAGJPAVCDBSession@@KQBUtagVARIANT@@ABVCRowsetProperties@@@Z`
- size: `1226`
- prototype: `int(CSRSStatistics *__hidden this, struct CDBSession *, unsigned int, const struct tagVARIANT *const, const struct CRowsetProperties *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x10034e00`

## callees

- `0x10013100`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10028340`
- `0x10035e60`
- `0x10039cc0`
- `0x1004ce5d`
- `0x1004d420`
- `0x1004d5a1`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x10039f05`
- `msvcrt!_wcsicmp` at `0x10039f05`
- `msjet40!__imp__JetCloseTable@8` at `0x1003a132`
- `msjet40!__imp__JetCloseTable@8` at `0x1003a144`
- `msjet40!__imp__JetCloseTable@8` at `0x1003a132`
- `msjet40!__imp__JetCloseTable@8` at `0x1003a144`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003a110`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003a110`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10039e12`
- `msjet40!__imp__JetGetObjectInfo@32` at `0x10039e12`
- `msjet40!__imp__JetMove@16` at `0x10039e36`
- `msjet40!__imp__JetMove@16` at `0x10039fd7`
- `msjet40!__imp__JetMove@16` at `0x10039e36`
- `msjet40!__imp__JetMove@16` at `0x10039fd7`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10039f47`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10039f47`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10039ebc`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10039f2f`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10039ebc`
- `msjet40!__imp__JetRetrieveColumn@32` at `0x10039f2f`
- `msjet40!__imp__JetSetColumn@28` at `0x10039f70`
- `msjet40!__imp__JetSetColumn@28` at `0x10039fab`
- `msjet40!__imp__JetSetColumn@28` at `0x10039f70`
- `msjet40!__imp__JetSetColumn@28` at `0x10039fab`
- `msjet40!__imp__JetUpdate@20` at `0x10039fbc`
- `msjet40!__imp__JetUpdate@20` at `0x10039fbc`

## pseudocode

```c
int __userpurge CSRSStatistics::FInit@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        CSRSStatistics *this,
        struct CDBSession *a4,
        unsigned int a5,
        const struct tagVARIANT *const a6,
        const struct CRowsetProperties *a7)
{
  _DWORD *v7; // esi
  JET_SESID v8; // edi
  int v9; // ecx
  int v10; // ecx
  int v11; // eax
  int v12; // eax
  int v13; // ebx
  int v14; // ecx
  JET_COLUMNID *v15; // eax
  struct CDBSession *v16; // esi
  JET_ERR v17; // eax
  BOOL v18; // eax
  bool v19; // cf
  ColumnData *v20; // eax
  int v21; // ecx
  ColumnData *v22; // esi
  int v23; // ecx
  unsigned int v25; // [esp-24h] [ebp-124h]
  ColumnData *v26; // [esp-14h] [ebp-114h]
  const struct _GUID *v27; // [esp+0h] [ebp-100h]
  const struct _GUID *v28; // [esp+4h] [ebp-FCh]
  unsigned int ObjectInfo; // [esp+10h] [ebp-F0h] BYREF
  JET_TABLEID v31; // [esp+14h] [ebp-ECh] BYREF
  BOOL v32; // [esp+18h] [ebp-E8h]
  JET_COLUMNID *v33; // [esp+1Ch] [ebp-E4h]
  struct CDBSession *v34; // [esp+20h] [ebp-E0h]
  unsigned int pcbActual; // [esp+24h] [ebp-DCh] BYREF
  unsigned int v36; // [esp+28h] [ebp-D8h] BYREF
  unsigned int v37; // [esp+2Ch] [ebp-D4h] BYREF
  unsigned int v38; // [esp+30h] [ebp-D0h]
  int v39; // [esp+34h] [ebp-CCh]
  double v40; // [esp+38h] [ebp-C8h] BYREF
  int v41; // [esp+40h] [ebp-C0h] BYREF
  JET_TABLEID tableid; // [esp+44h] [ebp-BCh]
  unsigned int v43; // [esp+48h] [ebp-B8h]
  JET_COLUMNID columnid; // [esp+50h] [ebp-B0h]
  JET_COLUMNID v45; // [esp+68h] [ebp-98h]
  wchar_t pvData[70]; // [esp+70h] [ebp-90h] BYREF

  v7 = a1;
  v39 = a2;
  v38 = a5;
  v34 = a4;
  ObjectInfo = 0;
  v33 = 0;
  v31 = -1;
  v32 = 1;
  tableid = -1;
  v8 = a1[4];
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
      v12 = a1[5];
      v13 = -2147024809;
      v14 = a1[4];
LABEL_55:
      if ( !JetGetDatabaseInfo(v14, v12, &v36, 4, 3) )
        CExtError::SendHRtoOLEAuto((int)&IID_IDBSchemaRowset, 0, v27, (int)v28);
      goto LABEL_57;
    }
  }
  v15 = (JET_COLUMNID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                          *(_DWORD *)(*(_DWORD *)Sys + 12),
                          Sys,
                          16);
  v33 = v15;
  if ( !v15 )
  {
    v13 = -2147024882;
    goto LABEL_51;
  }
  v13 = SRSCreateTempTable(6, a1, &v31, v15, 0);
  if ( v13 >= 0 )
  {
    v16 = v34;
    if ( (unsigned int)this >= 3 )
      v32 = *((_WORD *)v34 + 16) != 1;
    ObjectInfo = JetGetObjectInfo(v8, a1[5], 1, L"tables", 0, &v41, 48, 2);
    if ( ObjectInfo )
    {
LABEL_24:
      v13 = -2147467259;
      goto LABEL_50;
    }
    v17 = JetMove(v8, tableid, 0x80000000, 0);
    ObjectInfo = v17;
    if ( v17 != -1603 && v17 )
      goto LABEL_50;
    if ( (unsigned int)this <= 2 )
    {
      v18 = v32;
    }
    else
    {
      v18 = v32;
      if ( *((_WORD *)v16 + 16) == 8 )
      {
        if ( !*((_DWORD *)v16 + 10) )
          v18 = 0;
        v32 = v18;
      }
    }
    v34 = 0;
    if ( v43 )
    {
      while ( v18 )
      {
        pvData[0] = 0;
        ObjectInfo = JetRetrieveColumn(v8, tableid, columnid, pvData, 0x81u, &pcbActual, 0, 0);
        if ( ObjectInfo )
          goto LABEL_50;
        if ( (pcbActual & 0xFFFFFFFE) >= 0x82 )
          __report_rangecheckfailure();
        *(wchar_t *)((char *)pvData + (pcbActual & 0xFFFFFFFE)) = 0;
        if ( this != (CSRSStatistics *)3
          || *((_WORD *)v16 + 16) != 8
          || !*((_DWORD *)v16 + 10)
          || !__wcsicmp(pvData, *((const wchar_t **)v16 + 10)) )
        {
          ObjectInfo = JetRetrieveColumn(v8, tableid, v45, &v37, 4u, &v36, 0, 0);
          if ( ObjectInfo )
            goto LABEL_24;
          ObjectInfo = JetPrepareUpdate(v8, v31, 0);
          if ( ObjectInfo )
            goto LABEL_24;
          JetSetColumn(v8, v31, v33[2], pvData, pcbActual, 0, 0);
          v40 = (double)v37;
          JetSetColumn(v8, v31, v33[3], &v40, 8u, 0, 0);
          ObjectInfo = JetUpdate(v8, v31, 0, 0, 0);
          if ( ObjectInfo )
            goto LABEL_24;
        }
        ObjectInfo = JetMove(v8, tableid, 1, 0);
        v19 = (unsigned int)v34 + 1 < v43;
        v34 = (struct CDBSession *)((char *)v34 + 1);
        v18 = v32;
        if ( !v19 )
          break;
      }
    }
    v20 = (ColumnData *)operator new(0x20u);
    v22 = v20;
    v36 = (unsigned int)v20;
    if ( !v20 )
    {
      v13 = -2147024882;
      goto LABEL_50;
    }
    *((_DWORD *)v20 + 1) = 0;
    *((_DWORD *)v20 + 2) = 0;
    *((_DWORD *)v20 + 3) = 0;
    *(_DWORD *)v20 = &ColumnDataWithFakeNamesAndDBTYPES::`vftable';
    *((_DWORD *)v20 + 4) = 0;
    *((_DWORD *)v20 + 5) = 0;
    *((_DWORD *)v20 + 6) = 0;
    *((_DWORD *)v20 + 7) = 0;
    *((_DWORD *)v20 + 4) = dword_10008AE8;
    *((_DWORD *)v20 + 5) = &SRSStatisticsNames;
    *((_DWORD *)v20 + 7) = 0;
    v13 = ColumnData::FInit(v20, v8, a1[5], v31, (int *)&ObjectInfo, 0, v21);
    if ( v13 < 0 )
    {
LABEL_50:
      v7 = a1;
      goto LABEL_51;
    }
    v23 = v39;
    v26 = v22;
    v25 = v38;
    *((_DWORD *)v22 + 1) = 4;
    v7 = a1;
    v13 = CRowset::FInit(v23, 0, a1, 0, 0, 0, v31, v25, 1, 0, 0, v26, 1, 0, 0, &GUID_NULL);
    if ( v13 >= 0 )
      v31 = -1;
  }
LABEL_51:
  if ( ObjectInfo )
  {
    CExtError::SendJetErrortoOLEAuto(ObjectInfo, (int)&IID_IDBSchemaRowset, (int)v27, v28);
    goto LABEL_57;
  }
  if ( v13 < 0 )
  {
    v12 = v7[5];
    v14 = v7[4];
    if ( v13 != -2147024882 )
      goto LABEL_55;
  }
LABEL_57:
  if ( tableid != -1 )
  {
    JetCloseTable(v8, tableid);
    if ( tableid != -1 )
      JetCloseTable(v8, v31);
  }
  if ( v33 && Sys )
    (*(void (__thiscall **)(_DWORD, int, JET_COLUMNID *))(*(_DWORD *)Sys + 20))(
      *(_DWORD *)(*(_DWORD *)Sys + 20),
      Sys,
      v33);
  return v13;
}

```

## disassembly

```asm
0x10039cc0  mov     edi, edi
0x10039cc2  push    ebp
0x10039cc3  mov     ebp, esp
0x10039cc5  and     esp, 0FFFFFFF8h
0x10039cc8  sub     esp, 0F4h
0x10039cce  mov     eax, ___security_cookie
0x10039cd3  xor     eax, esp
0x10039cd5  mov     [esp+0F4h+var_4], eax
0x10039cdc  mov     eax, [ebp+arg_4]
0x10039cdf  push    ebx
0x10039ce0  push    esi; int
0x10039ce1  mov     esi, edx
0x10039ce3  mov     dword ptr [esp+0FCh+var_D0+4], ecx
0x10039ce7  mov     ecx, [ebp+arg_8]
0x10039cea  mov     edx, [ebp+this]
0x10039ced  mov     dword ptr [esp+0FCh+var_D0], ecx
0x10039cf1  mov     ecx, 1
0x10039cf6  mov     [esp+0FCh+var_F4], esi
0x10039cfa  mov     [esp+0FCh+var_E0], eax
0x10039cfe  mov     [esp+0FCh+var_F0], 0
0x10039d06  mov     [esp+0FCh+var_E4], 0
0x10039d0e  mov     [esp+0FCh+var_EC], 0FFFFFFFFh
0x10039d16  mov     [esp+0FCh+var_E8], ecx
0x10039d1a  mov     [esp+0FCh+tableid], 0FFFFFFFFh
0x10039d22  push    edi; struct _GUID *
0x10039d23  mov     edi, [esi+10h]
0x10039d26  test    edx, edx
0x10039d28  jz      short loc_10039D90
0x10039d2a  test    eax, eax
0x10039d2c  jz      short loc_10039D81
0x10039d2e  cmp     edx, 3
0x10039d31  ja      short loc_10039D81
0x10039d33  movzx   ecx, word ptr [eax]
0x10039d36  test    cx, cx
0x10039d39  jz      short loc_10039D4B
0x10039d3b  cmp     ecx, 1
0x10039d3e  jz      short loc_10039D4B
0x10039d40  cmp     ecx, 8
0x10039d43  jnz     short loc_10039D81
0x10039d45  cmp     dword ptr [eax+8], 0
0x10039d49  jnz     short loc_10039D81
0x10039d4b  cmp     edx, 1
0x10039d4e  jbe     short loc_10039D69
0x10039d50  movzx   ecx, word ptr [eax+10h]
0x10039d54  test    cx, cx
0x10039d57  jz      short loc_10039D69
0x10039d59  cmp     ecx, 1
0x10039d5c  jz      short loc_10039D69
0x10039d5e  cmp     ecx, 8
0x10039d61  jnz     short loc_10039D81
0x10039d63  cmp     dword ptr [eax+18h], 0
0x10039d67  jnz     short loc_10039D81
0x10039d69  cmp     edx, 2
0x10039d6c  jbe     short loc_10039D90
0x10039d6e  movzx   eax, word ptr [eax+20h]
0x10039d72  test    ax, ax
0x10039d75  jz      short loc_10039D90
0x10039d77  cmp     eax, 1
0x10039d7a  jz      short loc_10039D90
0x10039d7c  cmp     eax, 8
0x10039d7f  jz      short loc_10039D90
0x10039d81  mov     eax, [esi+14h]
0x10039d84  mov     ebx, 80070057h
0x10039d89  mov     ecx, edi
0x10039d8b  jmp     loc_1003A105
0x10039d90  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10039d96  push    10h
0x10039d98  push    ecx
0x10039d99  mov     eax, [ecx]
0x10039d9b  mov     esi, [eax+0Ch]
0x10039d9e  mov     ecx, esi
0x10039da0  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10039da6  call    esi
0x10039da8  mov     esi, [esp+100h+var_F4]
0x10039dac  mov     [esp+100h+var_E4], eax
0x10039db0  test    eax, eax
0x10039db2  jnz     short loc_10039DBE
0x10039db4  mov     ebx, 8007000Eh
0x10039db9  jmp     loc_1003A0CF
0x10039dbe  push    0
0x10039dc0  push    eax
0x10039dc1  lea     eax, [esp+108h+var_EC]
0x10039dc5  mov     edx, esi
0x10039dc7  push    eax
0x10039dc8  mov     ecx, 6
0x10039dcd  call    SRSCreateTempTable
0x10039dd2  mov     ebx, eax
0x10039dd4  test    ebx, ebx
0x10039dd6  js      loc_1003A0CF
0x10039ddc  cmp     [ebp+this], 3
0x10039de0  mov     esi, [esp+100h+var_E0]
0x10039de4  jb      short loc_10039DF8
0x10039de6  xor     ecx, ecx
0x10039de8  mov     eax, 1
0x10039ded  cmp     ax, [esi+20h]
0x10039df1  setnz   cl
0x10039df4  mov     [esp+100h+var_E8], ecx
0x10039df8  push    2
0x10039dfa  push    30h ; '0'
0x10039dfc  lea     eax, [esp+108h+var_C0]
0x10039e00  push    eax
0x10039e01  mov     eax, [esp+10Ch+var_F4]
0x10039e05  push    0
0x10039e07  push    offset aTables_0; "tables"
0x10039e0c  push    1
0x10039e0e  push    dword ptr [eax+14h]
0x10039e11  push    edi
0x10039e12  call    ds:__imp__JetGetObjectInfo@32; JetGetObjectInfo(x,x,x,x,x,x,x,x)
0x10039e18  mov     [esp+100h+var_F0], eax
0x10039e1c  test    eax, eax
0x10039e1e  jz      short loc_10039E2A
0x10039e20  mov     ebx, 80004005h
0x10039e25  jmp     loc_1003A0CB
0x10039e2a  push    0; grbit
0x10039e2c  push    80000000h; cRow
0x10039e31  push    [esp+108h+tableid]; tableid
0x10039e35  push    edi; sesid
0x10039e36  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10039e3c  mov     [esp+100h+var_F0], eax
0x10039e40  cmp     eax, 0FFFFF9BDh
0x10039e45  jz      short loc_10039E4F
0x10039e47  test    eax, eax
0x10039e49  jnz     loc_1003A0CB
0x10039e4f  cmp     [ebp+this], 2
0x10039e53  mov     eax, 8
0x10039e58  jbe     short loc_10039E72
0x10039e5a  cmp     ax, [esi+20h]
0x10039e5e  mov     eax, [esp+100h+var_E8]
0x10039e62  jnz     short loc_10039E76
0x10039e64  xor     ecx, ecx
0x10039e66  cmp     [esi+28h], ecx
0x10039e69  cmovz   eax, ecx
0x10039e6c  mov     [esp+100h+var_E8], eax
0x10039e70  jmp     short loc_10039E76
0x10039e72  mov     eax, [esp+100h+var_E8]
0x10039e76  cmp     [esp+100h+var_B8], 0
0x10039e7b  mov     [esp+100h+var_E0], 0
0x10039e83  jbe     loc_10039FF8
0x10039e89  nop     dword ptr [eax+00000000h]
0x10039e90  test    eax, eax
0x10039e92  jz      loc_10039FF8
0x10039e98  xor     eax, eax
0x10039e9a  push    eax; pretinfo
0x10039e9b  push    eax; grbit
0x10039e9c  mov     [esp+108h+pvData], ax
0x10039ea1  lea     eax, [esp+108h+pcbActual]
0x10039ea5  push    eax; pcbActual
0x10039ea6  push    81h; cbData
0x10039eab  lea     eax, [esp+110h+pvData]
0x10039eb2  push    eax; pvData
0x10039eb3  push    [esp+114h+columnid]; columnid
0x10039eb7  push    [esp+118h+tableid]; tableid
0x10039ebb  push    edi; sesid
0x10039ebc  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10039ec2  mov     [esp+100h+var_F0], eax
0x10039ec6  test    eax, eax
0x10039ec8  jnz     loc_1003A0CB
0x10039ece  mov     eax, [esp+100h+pcbActual]
0x10039ed2  and     eax, 0FFFFFFFEh
0x10039ed5  cmp     eax, 82h
0x10039eda  jnb     loc_1003A185
0x10039ee0  xor     ecx, ecx
0x10039ee2  cmp     [ebp+this], 3
0x10039ee6  mov     [esp+eax+100h+pvData], cx
0x10039eeb  jnz     short loc_10039F16
0x10039eed  mov     eax, 8
0x10039ef2  cmp     ax, [esi+20h]
0x10039ef6  jnz     short loc_10039F16
0x10039ef8  mov     eax, [esi+28h]
0x10039efb  test    eax, eax
0x10039efd  jz      short loc_10039F16
0x10039eff  push    eax; String2
0x10039f00  lea     eax, [esp+104h+pvData]
0x10039f04  push    eax; String1
0x10039f05  call    ds:__imp___wcsicmp
0x10039f0b  add     esp, 8
0x10039f0e  test    eax, eax
0x10039f10  jnz     loc_10039FCE
0x10039f16  push    0; pretinfo
0x10039f18  push    0; grbit
0x10039f1a  lea     eax, [esp+108h+var_D8]
0x10039f1e  push    eax; pcbActual
0x10039f1f  push    4; cbData
0x10039f21  lea     eax, [esp+110h+var_D4]
0x10039f25  push    eax; pvData
0x10039f26  push    [esp+114h+var_98]; columnid
0x10039f2a  push    [esp+118h+tableid]; tableid
0x10039f2e  push    edi; sesid
0x10039f2f  call    ds:__imp__JetRetrieveColumn@32; JetRetrieveColumn(x,x,x,x,x,x,x,x)
0x10039f35  mov     [esp+100h+var_F0], eax
0x10039f39  test    eax, eax
0x10039f3b  jnz     loc_10039E20
0x10039f41  push    eax; prep
0x10039f42  push    [esp+104h+var_EC]; tableid
0x10039f46  push    edi; sesid
0x10039f47  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x10039f4d  mov     [esp+100h+var_F0], eax
0x10039f51  test    eax, eax
0x10039f53  jnz     loc_10039E20
0x10039f59  push    eax; psetinfo
0x10039f5a  push    eax; grbit
0x10039f5b  push    [esp+108h+pcbActual]; cbData
0x10039f5f  lea     eax, [esp+10Ch+pvData]
0x10039f63  push    eax; pvData
0x10039f64  mov     eax, [esp+110h+var_E4]
0x10039f68  push    dword ptr [eax+8]; columnid
0x10039f6b  push    [esp+114h+var_EC]; tableid
0x10039f6f  push    edi; sesid
0x10039f70  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10039f76  mov     eax, [esp+100h+var_D4]
0x10039f7a  push    0; psetinfo
0x10039f7c  push    0; grbit
0x10039f7e  push    8; cbData
0x10039f80  movd    xmm0, eax
0x10039f84  cvtdq2pd xmm0, xmm0
0x10039f88  shr     eax, 1Fh
0x10039f8b  addsd   xmm0, ds:__xmm@41f00000000000000000000000000000[eax*8]
0x10039f94  lea     eax, [esp+10Ch+var_C8]
0x10039f98  push    eax; pvData
0x10039f99  mov     eax, [esp+110h+var_E4]
0x10039f9d  movsd   [esp+110h+var_C8], xmm0
0x10039fa3  push    dword ptr [eax+0Ch]; columnid
0x10039fa6  push    [esp+114h+var_EC]; tableid
0x10039faa  push    edi; sesid
0x10039fab  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10039fb1  push    0; pcbActual
0x10039fb3  push    0; cbBookmark
0x10039fb5  push    0; pvBookmark
0x10039fb7  push    [esp+10Ch+var_EC]; tableid
0x10039fbb  push    edi; sesid
0x10039fbc  call    ds:__imp__JetUpdate@20; JetUpdate(x,x,x,x,x)
0x10039fc2  mov     [esp+100h+var_F0], eax
0x10039fc6  test    eax, eax
0x10039fc8  jnz     loc_10039E20
0x10039fce  push    0; grbit
0x10039fd0  push    1; cRow
0x10039fd2  push    [esp+108h+tableid]; tableid
0x10039fd6  push    edi; sesid
0x10039fd7  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10039fdd  mov     [esp+100h+var_F0], eax
0x10039fe1  mov     eax, [esp+100h+var_E0]
0x10039fe5  inc     eax
0x10039fe6  cmp     eax, [esp+100h+var_B8]
0x10039fea  mov     [esp+100h+var_E0], eax
0x10039fee  mov     eax, [esp+100h+var_E8]
0x10039ff2  jb      loc_10039E90
0x10039ff8  push    20h ; ' '; Size
0x10039ffa  call    ??2@YAPAXI@Z; operator new(uint)
0x10039fff  mov     esi, eax
0x1003a001  add     esp, 4
0x1003a004  mov     [esp+100h+var_D8], esi
0x1003a008  test    esi, esi
0x1003a00a  jz      loc_1003A0C6
0x1003a010  mov     dword ptr [esi+4], 0
0x1003a017  mov     dword ptr [esi+8], 0
0x1003a01e  mov     dword ptr [esi+0Ch], 0
0x1003a025  mov     dword ptr [esi], offset ??_7ColumnDataWithFakeNamesAndDBTYPES@@6B@; const ColumnDataWithFakeNamesAndDBTYPES::`vftable'
0x1003a02b  mov     dword ptr [esi+10h], 0
0x1003a032  mov     dword ptr [esi+14h], 0
0x1003a039  mov     dword ptr [esi+18h], 0
0x1003a040  mov     dword ptr [esi+1Ch], 0
0x1003a047  mov     eax, ds:off_1000337C
0x1003a04c  mov     [esi+10h], eax
0x1003a04f  mov     eax, ds:off_10003378
0x1003a054  push    ecx; int
0x1003a055  mov     [esi+14h], eax
0x1003a058  mov     ecx, esi; this
0x1003a05a  push    0; int
0x1003a05c  lea     eax, [esp+108h+var_F0]
0x1003a060  mov     dword ptr [esi+1Ch], 0
0x1003a067  push    eax; int *
0x1003a068  mov     eax, [esp+10Ch+var_F4]
0x1003a06c  push    [esp+10Ch+var_EC]; unsigned int
0x1003a070  push    dword ptr [eax+14h]; unsigned int
0x1003a073  push    edi; sesid
0x1003a074  call    ?FInit@ColumnData@@QAEJKKKAAJHH@Z; ColumnData::FInit(ulong,ulong,ulong,long &,int,int)
0x1003a079  mov     ebx, eax
0x1003a07b  test    ebx, ebx
0x1003a07d  js      short loc_1003A0CB
0x1003a07f  push    offset _GUID_NULL
0x1003a084  push    0
0x1003a086  push    0
0x1003a088  push    1
0x1003a08a  mov     ecx, dword ptr [esp+110h+var_D0+4]
0x1003a08e  xor     edx, edx
0x1003a090  push    esi
0x1003a091  push    0
0x1003a093  push    0
0x1003a095  push    1
0x1003a097  push    dword ptr [esp+120h+var_D0]
0x1003a09b  mov     dword ptr [esi+4], 4
0x1003a0a2  push    [esp+124h+var_EC]
0x1003a0a6  mov     esi, [esp+128h+var_F4]
0x1003a0aa  push    0
0x1003a0ac  push    0
0x1003a0ae  push    0
0x1003a0b0  push    esi
0x1003a0b1  call    ?FInit@CRowset@@QAGJKPAVCDBSession@@PAVCCommand@@PAG2KABVCRowsetProperties@@W4eJetCursorType@@PAXPAKPAVColumnData@@HKQAUtagDBPROPSET@@ABU_GUID@@@Z; CRowset::FInit(ulong,CDBSession *,CCommand *,ushort *,ushort *,ulong,CRowsetProperties const &,eJetCursorType,void *,ulong *,ColumnData *,int,ulong,tagDBPROPSET * const,_GUID const &)
0x1003a0b6  mov     ebx, eax
0x1003a0b8  test    ebx, ebx
  ... truncated ...
```
