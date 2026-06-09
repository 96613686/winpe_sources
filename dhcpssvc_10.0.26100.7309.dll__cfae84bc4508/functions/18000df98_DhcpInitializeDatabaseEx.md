# DhcpInitializeDatabaseEx

- ea: `0x18000df98`
- end: `0x18000eaeb`
- name: `DhcpInitializeDatabaseEx`
- size: `2899`
- prototype: ``
- caller_count: `5`
- callee_count: `22`
- tags: `file_ops, registry_config`

## callers

- `0x18000f300`
- `0x18000f3d0`
- `0x180014600`
- `0x1800146b0`
- `0x180025bf4`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000c180`
- `0x18000d06c`
- `0x18000d3ec`
- `0x18000df98`
- `0x18000f144`
- `0x18000f690`
- `0x180010200`
- `0x18001130c`
- `0x1800114a4`
- `0x1800170e4`
- `0x18001d208`
- `0x1800289e8`
- `0x18008dc8c`
- `0x18008e60c`
- `0x18009d7ac`
- `0x18009dc58`
- `0x18009dda0`
- `0x1800b45f0`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetOpenTable` at `0x18000e668`
- `ESENT!JetOpenTable` at `0x18000e668`
- `ESENT!JetGetTableColumnInfo` at `0x18000e712`
- `ESENT!JetGetTableColumnInfo` at `0x18000e712`
- `ESENT!JetGetTableIndexInfo` at `0x18000e859`
- `ESENT!JetGetTableIndexInfo` at `0x18000e859`
- `ESENT!JetCloseTable` at `0x18000e9f4`
- `ESENT!JetCloseTable` at `0x18000e9f4`
- `ESENT!JetOpenDatabase` at `0x18000e58e`
- `ESENT!JetOpenDatabase` at `0x18000e58e`
- `ESENT!JetAttachDatabase` at `0x18000e4eb`
- `ESENT!JetAttachDatabase` at `0x18000e4eb`
- `ESENT!JetBeginSession` at `0x18000e2d0`
- `ESENT!JetBeginSession` at `0x18000e2d0`
- `ESENT!JetInit` at `0x18000e1fb`
- `ESENT!JetInit` at `0x18000e1fb`
- `ESENT!JetDetachDatabase` at `0x18000e439`
- `ESENT!JetDetachDatabase` at `0x18000e439`
- `ESENT!JetAddColumn` at `0x18000e7b5`
- `ESENT!JetAddColumn` at `0x18000e7b5`
- `ESENT!JetCloseDatabase` at `0x18000ea53`
- `ESENT!JetCloseDatabase` at `0x18000ea53`
- `KERNEL32!EnterCriticalSection` at `0x18000e18a`
- `KERNEL32!EnterCriticalSection` at `0x18000e18a`
- `KERNEL32!LeaveCriticalSection` at `0x18000eaac`
- `KERNEL32!LeaveCriticalSection` at `0x18000eaac`
- `USER32!OemToCharBuffA` at `0x18000e0b9`
- `USER32!OemToCharBuffA` at `0x18000e3f3`
- `USER32!OemToCharBuffA` at `0x18000e0b9`
- `USER32!OemToCharBuffA` at `0x18000e3f3`

## string_xrefs

- `0x18000e600`: `CreateAndInitDb`
- `0x18000e6a0`: `OpenTable`

## pseudocode

```c
__int64 __fastcall DhcpInitializeDatabaseEx(int a1)
{
  __int64 result; // rax
  int v3; // r15d
  __int64 v4; // rdi
  unsigned __int64 v5; // rax
  __int64 v6; // rdx
  signed __int64 v7; // r8
  CHAR *v8; // rcx
  CHAR v9; // al
  CHAR *v10; // rax
  __int64 v11; // r8
  unsigned int inited; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // esi
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rcx
  unsigned int v26; // edi
  unsigned int v27; // esi
  __int64 v28; // rdi
  unsigned int TableColumnInfo; // ebx
  __int64 v30; // r8
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // edi
  __int64 v36; // [rsp+48h] [rbp-C0h] BYREF
  int v37; // [rsp+50h] [rbp-B8h]
  int v38; // [rsp+54h] [rbp-B4h]
  __int64 v39; // [rsp+58h] [rbp-B0h]
  __m256i v40; // [rsp+60h] [rbp-A8h] BYREF
  int v41; // [rsp+80h] [rbp-88h]
  CHAR v42[96]; // [rsp+88h] [rbp-80h] BYREF
  CHAR szSrc[272]; // [rsp+E8h] [rbp-20h] BYREF

  result = 0;
  memset(&v40.m256i_u64[1], 0, 24);
  v41 = 0;
  v3 = 0;
  szSrc[0] = 0;
  if ( !dword_1800FAEB0 )
  {
    v4 = -1;
    if ( !a1 && (unsigned int)DhcpCheckIfDatabaseUpgraded() == 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
      v3 = 1;
      v5 = -1;
      do
        ++v5;
      while ( DhcpGlobalOemDatabasePath[v5] );
      if ( v5 < 0x104 )
      {
        v6 = 260;
        v7 = DhcpGlobalOemDatabasePath - szSrc;
        v8 = szSrc;
        do
        {
          if ( v6 == -2147483386 )
            break;
          v9 = v8[v7];
          if ( !v9 )
            break;
          *v8++ = v9;
          --v6;
        }
        while ( v6 );
        v10 = v8 - 1;
        if ( v6 )
          v10 = v8;
        *v10 = 0;
      }
      v11 = -1;
      do
        ++v11;
      while ( szSrc[v11] );
      OemToCharBuffA(szSrc, szSrc, v11);
      inited = DhcpDeleteFiles(szSrc, "j50*");
      if ( inited )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return inited;
        v14 = 66;
        goto LABEL_23;
      }
      inited = DhcpDeleteFiles(szSrc, "res*.log");
      if ( inited )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return inited;
        v14 = 67;
        goto LABEL_23;
      }
      inited = DhcpDeleteFiles(szSrc, "*.mdb");
      if ( inited )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return inited;
        v14 = 68;
LABEL_23:
        WPP_SF_D(v13[2], v14, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, inited);
        return inited;
      }
    }
    EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
    inited = DhcpSetJetParameters();
    if ( inited )
      goto LABEL_137;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
    v15 = JetInit(&JetInstance);
    v16 = v15;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, v15);
        v17 = WPP_GLOBAL_Control;
      }
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x10) != 0 )
        WPP_SF_(v17[2], 72, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
    }
    inited = DhcpMapJetError(v16, "JetInit");
    if ( inited )
      goto LABEL_137;
    inited = DhcpWriterInit();
    if ( inited )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v19 = 73;
LABEL_50:
          WPP_SF_(v18[2], v19, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
LABEL_137:
          v18 = WPP_GLOBAL_Control;
          goto LABEL_138;
        }
        goto LABEL_138;
      }
LABEL_151:
      if ( DhcpGlobalClientTableHandle )
      {
        v34 = JetCloseTable(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
        DhcpMapJetError(v34, "CloseTable");
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
        }
        DhcpGlobalClientTableHandle = 0;
      }
      if ( DhcpGlobalDatabaseHandle )
      {
        v35 = JetCloseDatabase(DhcpGlobalJetServerSession, DhcpGlobalDatabaseHandle, 0);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
        }
        DhcpMapJetError(v35, "CloseDatabse");
        DhcpGlobalDatabaseHandle = 0;
      }
      DhcpTerminateJet();
LABEL_162:
      LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      return inited;
    }
    v20 = JetBeginSession(JetInstance, &DhcpGlobalJetServerSession, "admin", SourceString);
    if ( *(_DWORD *)DhcpGlobalJetServerSession == -1 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_59;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      {
LABEL_56:
        if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x8000) != 0 )
          WPP_SF_(v21[2], 75, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
LABEL_59:
        inited = DhcpMapJetError(v20, "JetBeginSEssion");
        if ( inited )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_151;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
            goto LABEL_138;
          v22 = 76;
          v23 = v20;
        }
        else
        {
          v24 = -1;
          szSrc[0] = 0;
          do
            ++v24;
          while ( DhcpGlobalOemDatabaseName[v24] );
          v25 = -1;
          do
            ++v25;
          while ( DhcpGlobalOemDatabasePath[v25] );
          if ( (unsigned __int64)(v25 + v24 + 2) < 0x104 )
            StringCbPrintfA(szSrc, 0x104u, "%s%s%s", DhcpGlobalOemDatabasePath, "\\", DhcpGlobalOemDatabaseName);
          do
            ++v4;
          while ( szSrc[v4] );
          OemToCharBuffA(szSrc, szSrc, v4);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              77,
              &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids,
              (unsigned int)DhcpGlobalJetServerSession);
          }
          v26 = JetDetachDatabase(DhcpGlobalJetServerSession, 0);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
          }
          inited = DhcpMapJetError(v26, "JetDetachDatabase");
          if ( inited )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_151;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
              goto LABEL_138;
            v22 = 79;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
            {
              WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, szSrc);
            }
            v26 = JetAttachDatabase(DhcpGlobalJetServerSession, szSrc, 0);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
            }
            if ( v26 == -1811 || (inited = DhcpMapJetError(v26, "AttachDatabase")) == 0 )
            {
              DhcpGlobalClientTable = (__int64)&ClientTable;
              v26 = JetOpenDatabase(DhcpGlobalJetServerSession, szSrc, 0, &DhcpGlobalDatabaseHandle, 0);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
              }
              if ( !a1 && v26 == -1203 )
              {
                inited = DhcpCreateAndInitDatabase();
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                  goto LABEL_141;
                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
                {
                  v19 = 84;
                  goto LABEL_50;
                }
LABEL_138:
                if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x8000) != 0 )
                  WPP_SF_D(v18[2], 92, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, inited);
LABEL_141:
                if ( !inited )
                {
                  ++dword_1800FAEB0;
                  if ( !v3 )
                    goto LABEL_162;
                  v32 = DhcpOpenConfigTable(DhcpGlobalJetServerSession, DhcpGlobalDatabaseHandle);
                  inited = v32;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
                  {
                    WPP_SF_D(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      93,
                      &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids,
                      v32);
                  }
                  if ( !inited )
                  {
                    v33 = UpgradeDhcpDatabase();
                    inited = v33;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
                    {
                      WPP_SF_D(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        94,
                        &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids,
                        v33);
                    }
                    if ( !inited )
                      goto LABEL_162;
                  }
                }
                goto LABEL_151;
              }
              inited = DhcpMapJetError(v26, "CreateAndInitDb");
              if ( inited )
              {
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                  goto LABEL_151;
                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
                  goto LABEL_138;
                v22 = 85;
              }
              else
              {
                v26 = JetOpenTable(
                        DhcpGlobalJetServerSession,
                        DhcpGlobalDatabaseHandle,
                        "ClientTable",
                        0,
                        0,
                        0,
                        &DhcpGlobalClientTableHandle);
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
                }
                inited = DhcpMapJetError(v26, "OpenTable");
                if ( !inited )
                {
                  v27 = 0;
                  v28 = 0;
                  do
                  {
                    TableColumnInfo = JetGetTableColumnInfo(
                                        DhcpGlobalJetServerSession,
                                        DhcpGlobalClientTableHandle,
                                        *(_QWORD *)(v28 + DhcpGlobalClientTable),
                                        &v40.m256i_u64[1],
                                        28,
                                        0);
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
                    }
                    if ( TableColumnInfo == -1507 )
                    {
                      v36 = 28;
                      v37 = *(_DWORD *)(v28 + DhcpGlobalClientTable + 12);
                      v38 = 67698689;
                      v39 = 1252;
                      v30 = *(_QWORD *)(v28 + DhcpGlobalClientTable);
                      v40.m256i_i32[0] = 0;
                      TableColumnInfo = JetAddColumn(
                                          DhcpGlobalJetServerSession,
                                          DhcpGlobalClientTableHandle,
                                          v30,
                                          &v36,
                                          0,
                                          0,
                                          DhcpGlobalClientTable + 16LL * v27 + 8);
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
                      {
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          89,
                          &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
                      }
                    }
                    else if ( !TableColumnInfo )
                    {
                      *(_DWORD *)(v28 + DhcpGlobalClientTable + 8) = v40.m256i_i32[3];
                    }
                    v31 = DhcpMapJetError(TableColumnInfo, "AddColumn");
                    inited = v31;
                    if ( v31 )
                    {
                      v18 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                        goto LABEL_151;
                      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
                      {
                        v22 = 90;
                        goto LABEL_135;
                      }
                      goto LABEL_138;
                    }
                    ++v27;
                    v28 += 16;
                  }
                  while ( v27 < 0x17 );
                  memset_0(v42, 0, 0x58u);
                  if ( (unsigned int)JetGetTableIndexInfo(
                                       DhcpGlobalJetServerSession,
                                       DhcpGlobalClientTableHandle,
                                       "IpAddressBndMessageStatus",
                                       v42,
                                       88,
                                       0) )
                  {
                    inited = CreateClientTableWin8Indices();
                    if ( inited )
                      goto LABEL_137;
                  }
                  inited = DhcpOpenFilterDbTable(DhcpGlobalJetServerSession);
                  if ( inited )
                    goto LABEL_137;
                  inited = DhcpOpenFailoverDbTable(DhcpGlobalJetServerSession);
                  if ( inited )
                    goto LABEL_137;
                  inited = DhcpFOOpenDeletedAddressTable(DhcpGlobalJetServerSession);
                  if ( inited )
                    goto LABEL_137;
                  inited = DhcpOpenFailoverBitmaskTable(DhcpGlobalJetServerSession);
                  if ( inited )
                    goto LABEL_137;
                  v31 = DhcpOpenMCastDbTable(DhcpGlobalJetServerSession);
                  inited = v31;
                  v18 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    goto LABEL_141;
                  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
                  {
                    v22 = 91;
LABEL_135:
                    v23 = v31;
                    goto LABEL_136;
                  }
                  goto LABEL_138;
                }
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                  goto LABEL_151;
                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
                  goto LABEL_138;
                v22 = 87;
              }
            }
            else
            {
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_151;
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
                goto LABEL_138;
              v22 = 82;
            }
          }
          v23 = v26;
        }
LABEL_136:
        WPP_SF_D(v18[2], v22, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, v23);
        goto LABEL_137;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
    }
    v21 = WPP_GLOBAL_Control;
    goto LABEL_56;
  }
  return result;
}

```

## disassembly

```asm
0x18000df98  mov     rax, rsp
0x18000df9b  mov     [rax+8], rbx
0x18000df9f  mov     [rax+10h], rsi
0x18000dfa3  mov     [rax+18h], rdi
0x18000dfa7  push    rbp
0x18000dfa8  push    r12
0x18000dfaa  push    r13
0x18000dfac  push    r14
0x18000dfae  push    r15
0x18000dfb0  lea     rbp, [rax-128h]
0x18000dfb7  sub     rsp, 200h
0x18000dfbe  mov     rax, cs:__security_cookie
0x18000dfc5  xor     rax, rsp
0x18000dfc8  mov     [rbp+120h+var_30], rax
0x18000dfcf  xor     eax, eax
0x18000dfd1  xor     r12d, r12d
0x18000dfd4  cmp     cs:dword_1800FAEB0, r12d
0x18000dfdb  xorps   xmm0, xmm0
0x18000dfde  mov     r14d, ecx
0x18000dfe1  mov     [rsp+220h+var_1B0], rax
0x18000dfe6  movups  xmmword ptr [rsp+220h+var_1C8+8], xmm0
0x18000dfeb  mov     [rsp+220h+var_1A8], eax
0x18000dfef  mov     r15d, r12d
0x18000dff2  mov     [rbp+120h+szSrc], r12b
0x18000dff6  jnz     loc_18000EABA
0x18000dffc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e000  lea     esi, [rax+1]
0x18000e003  lea     r13, WPP_GLOBAL_Control
0x18000e00a  mov     ebx, 104h
0x18000e00f  test    ecx, ecx
0x18000e011  jnz     loc_18000E183
0x18000e017  call    DhcpCheckIfDatabaseUpgraded
0x18000e01c  cmp     eax, esi
0x18000e01e  jnz     loc_18000E183
0x18000e024  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e02b  cmp     rcx, r13
0x18000e02e  jz      short loc_18000E04C
0x18000e030  test    dword ptr [rcx+1Ch], 8000h
0x18000e037  jz      short loc_18000E04C
0x18000e039  mov     rcx, [rcx+10h]
0x18000e03d  lea     edx, [rsi+40h]
0x18000e040  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e047  call    WPP_SF_
0x18000e04c  mov     r8, cs:DhcpGlobalOemDatabasePath
0x18000e053  mov     r15d, esi
0x18000e056  mov     rax, rdi
0x18000e059  inc     rax
0x18000e05c  cmp     [r8+rax], r12b
0x18000e060  jnz     short loc_18000E059
0x18000e062  cmp     rax, rbx
0x18000e065  jnb     short loc_18000E0A1
0x18000e067  lea     rax, [rbp+120h+szSrc]
0x18000e06b  mov     rdx, rbx
0x18000e06e  sub     r8, rax
0x18000e071  lea     rcx, [rbp+120h+szSrc]
0x18000e075  lea     rax, [rdx+7FFFFEFAh]
0x18000e07c  test    rax, rax
0x18000e07f  jz      short loc_18000E093
0x18000e081  mov     al, [rcx+r8]
0x18000e085  test    al, al
0x18000e087  jz      short loc_18000E093
0x18000e089  mov     [rcx], al
0x18000e08b  add     rcx, rsi
0x18000e08e  sub     rdx, rsi
0x18000e091  jnz     short loc_18000E075
0x18000e093  test    rdx, rdx
0x18000e096  lea     rax, [rcx-1]
0x18000e09a  cmovnz  rax, rcx
0x18000e09e  mov     [rax], r12b
0x18000e0a1  lea     rax, [rbp+120h+szSrc]
0x18000e0a5  mov     r8, rdi
0x18000e0a8  inc     r8; cchDstLength
0x18000e0ab  cmp     [rax+r8], r12b
0x18000e0af  jnz     short loc_18000E0A8
0x18000e0b1  lea     rdx, [rbp+120h+szSrc]; lpszDst
0x18000e0b5  lea     rcx, [rbp+120h+szSrc]; lpszSrc
0x18000e0b9  call    cs:__imp_OemToCharBuffA
0x18000e0c0  nop     dword ptr [rax+rax+00h]
0x18000e0c5  lea     rdx, FileName; "j50*"
0x18000e0cc  lea     rcx, [rbp+120h+szSrc]; lpPathName
0x18000e0d0  call    DhcpDeleteFiles
0x18000e0d5  mov     ebx, eax
0x18000e0d7  test    eax, eax
0x18000e0d9  jz      short loc_18000E112
0x18000e0db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0e2  cmp     rcx, r13
0x18000e0e5  jz      loc_18000EAB8
0x18000e0eb  test    byte ptr [rcx+1Ch], 10h
0x18000e0ef  jz      loc_18000EAB8
0x18000e0f5  mov     edx, 42h ; 'B'
0x18000e0fa  mov     rcx, [rcx+10h]
0x18000e0fe  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e105  mov     r9d, ebx
0x18000e108  call    WPP_SF_D
0x18000e10d  jmp     loc_18000EAB8
0x18000e112  lea     rdx, aResLog; "res*.log"
0x18000e119  lea     rcx, [rbp+120h+szSrc]; lpPathName
0x18000e11d  call    DhcpDeleteFiles
0x18000e122  mov     ebx, eax
0x18000e124  test    eax, eax
0x18000e126  jz      short loc_18000E149
0x18000e128  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e12f  cmp     rcx, r13
0x18000e132  jz      loc_18000EAB8
0x18000e138  test    byte ptr [rcx+1Ch], 10h
0x18000e13c  jz      loc_18000EAB8
0x18000e142  mov     edx, 43h ; 'C'
0x18000e147  jmp     short loc_18000E0FA
0x18000e149  lea     rdx, aMdb; "*.mdb"
0x18000e150  lea     rcx, [rbp+120h+szSrc]; lpPathName
0x18000e154  call    DhcpDeleteFiles
0x18000e159  mov     ebx, eax
0x18000e15b  test    eax, eax
0x18000e15d  jz      short loc_18000E183
0x18000e15f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e166  cmp     rcx, r13
0x18000e169  jz      loc_18000EAB8
0x18000e16f  test    byte ptr [rcx+1Ch], 10h
0x18000e173  jz      loc_18000EAB8
0x18000e179  mov     edx, 44h ; 'D'
0x18000e17e  jmp     loc_18000E0FA
0x18000e183  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18000e18a  call    cs:__imp_EnterCriticalSection
0x18000e191  nop     dword ptr [rax+rax+00h]
0x18000e196  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e19d  cmp     rcx, r13
0x18000e1a0  jz      short loc_18000E1C0
0x18000e1a2  test    dword ptr [rcx+1Ch], 8000h
0x18000e1a9  jz      short loc_18000E1C0
0x18000e1ab  mov     rcx, [rcx+10h]
0x18000e1af  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e1b6  mov     edx, 45h ; 'E'
0x18000e1bb  call    WPP_SF_
0x18000e1c0  call    DhcpSetJetParameters
0x18000e1c5  mov     ebx, eax
0x18000e1c7  test    eax, eax
0x18000e1c9  jnz     loc_18000E919
0x18000e1cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1d6  cmp     rcx, r13
0x18000e1d9  jz      short loc_18000E1F4
0x18000e1db  test    byte ptr [rcx+1Ch], 10h
0x18000e1df  jz      short loc_18000E1F4
0x18000e1e1  mov     rcx, [rcx+10h]
0x18000e1e5  lea     edx, [rax+46h]
0x18000e1e8  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e1ef  call    WPP_SF_
0x18000e1f4  lea     rcx, JetInstance; pinstance
0x18000e1fb  call    cs:__imp_JetInit
0x18000e202  nop     dword ptr [rax+rax+00h]
0x18000e207  mov     ebx, eax
0x18000e209  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e210  cmp     rcx, r13
0x18000e213  jz      short loc_18000E25D
0x18000e215  test    dword ptr [rcx+1Ch], 8000h
0x18000e21c  jz      short loc_18000E23D
0x18000e21e  mov     rcx, [rcx+10h]
0x18000e222  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e229  mov     edx, 47h ; 'G'
0x18000e22e  mov     r9d, eax
0x18000e231  call    WPP_SF_D
0x18000e236  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e23d  cmp     rcx, r13
0x18000e240  jz      short loc_18000E25D
0x18000e242  test    byte ptr [rcx+1Ch], 10h
0x18000e246  jz      short loc_18000E25D
0x18000e248  mov     rcx, [rcx+10h]
0x18000e24c  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e253  mov     edx, 48h ; 'H'
0x18000e258  call    WPP_SF_
0x18000e25d  lea     rdx, aJetinit; "JetInit"
0x18000e264  mov     ecx, ebx
0x18000e266  call    DhcpMapJetError
0x18000e26b  mov     ebx, eax
0x18000e26d  test    eax, eax
0x18000e26f  jnz     loc_18000E919
0x18000e275  call    DhcpWriterInit
0x18000e27a  mov     ebx, eax
0x18000e27c  test    eax, eax
0x18000e27e  jz      short loc_18000E2B4
0x18000e280  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e287  cmp     rcx, r13
0x18000e28a  jz      loc_18000E9E1
0x18000e290  test    byte ptr [rcx+1Ch], 10h
0x18000e294  jz      loc_18000E920
0x18000e29a  mov     edx, 49h ; 'I'
0x18000e29f  mov     rcx, [rcx+10h]
0x18000e2a3  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e2aa  call    WPP_SF_
0x18000e2af  jmp     loc_18000E919
0x18000e2b4  mov     rcx, cs:JetInstance
0x18000e2bb  lea     r9, SourceString
0x18000e2c2  lea     r8, aAdmin; "admin"
0x18000e2c9  lea     rdx, DhcpGlobalJetServerSession
0x18000e2d0  call    cs:__imp_JetBeginSession
0x18000e2d7  nop     dword ptr [rax+rax+00h]
0x18000e2dc  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000e2e3  mov     esi, eax
0x18000e2e5  cmp     dword ptr [rcx], 0FFFFFFFFh
0x18000e2e8  jnz     short loc_18000E314
0x18000e2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2f1  cmp     rcx, r13
0x18000e2f4  jz      short loc_18000E33E
0x18000e2f6  test    dword ptr [rcx+1Ch], 8000h
0x18000e2fd  jz      short loc_18000E31B
0x18000e2ff  mov     rcx, [rcx+10h]
0x18000e303  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e30a  mov     edx, 4Ah ; 'J'
0x18000e30f  call    WPP_SF_
0x18000e314  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e31b  cmp     rcx, r13
0x18000e31e  jz      short loc_18000E33E
0x18000e320  test    dword ptr [rcx+1Ch], 8000h
0x18000e327  jz      short loc_18000E33E
0x18000e329  mov     rcx, [rcx+10h]
0x18000e32d  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e334  mov     edx, 4Bh ; 'K'
0x18000e339  call    WPP_SF_
0x18000e33e  lea     rdx, aJetbeginsessio; "JetBeginSEssion"
0x18000e345  mov     ecx, esi
0x18000e347  call    DhcpMapJetError
0x18000e34c  mov     ebx, eax
0x18000e34e  test    eax, eax
0x18000e350  jz      short loc_18000E37F
0x18000e352  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e359  cmp     rcx, r13
0x18000e35c  jz      loc_18000E9E1
0x18000e362  mov     r14d, 8000h
0x18000e368  test    [rcx+1Ch], r14d
0x18000e36c  jz      loc_18000E920
0x18000e372  mov     edx, 4Ch ; 'L'
0x18000e377  mov     r9d, esi
0x18000e37a  jmp     loc_18000E909
0x18000e37f  mov     r8, cs:DhcpGlobalOemDatabaseName
0x18000e386  mov     rax, rdi
0x18000e389  mov     [rbp+120h+szSrc], r12b
0x18000e38d  inc     rax
0x18000e390  cmp     [r8+rax], r12b
0x18000e394  jnz     short loc_18000E38D
0x18000e396  mov     r9, cs:DhcpGlobalOemDatabasePath
0x18000e39d  mov     rcx, rdi
0x18000e3a0  inc     rcx
0x18000e3a3  cmp     [r9+rcx], r12b
0x18000e3a7  jnz     short loc_18000E3A0
0x18000e3a9  add     rax, 2
0x18000e3ad  mov     edx, 104h; cbDest
0x18000e3b2  add     rax, rcx
0x18000e3b5  cmp     rax, rdx
0x18000e3b8  jnb     short loc_18000E3DB
0x18000e3ba  mov     [rsp+220h+var_1F8], r8
0x18000e3bf  lea     rax, asc_1800DCB80; "\\"
0x18000e3c6  lea     r8, aSSS_0; "%s%s%s"
0x18000e3cd  mov     [rsp+220h+var_200], rax
0x18000e3d2  lea     rcx, [rbp+120h+szSrc]; pszDest
0x18000e3d6  call    StringCbPrintfA
0x18000e3db  lea     rax, [rbp+120h+szSrc]
0x18000e3df  inc     rdi
0x18000e3e2  cmp     [rax+rdi], r12b
0x18000e3e6  jnz     short loc_18000E3DF
0x18000e3e8  mov     r8, rdi; cchDstLength
0x18000e3eb  lea     rdx, [rbp+120h+szSrc]; lpszDst
0x18000e3ef  lea     rcx, [rbp+120h+szSrc]; lpszSrc
0x18000e3f3  call    cs:__imp_OemToCharBuffA
0x18000e3fa  nop     dword ptr [rax+rax+00h]
0x18000e3ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e406  cmp     rcx, r13
0x18000e409  jz      short loc_18000E430
0x18000e40b  test    dword ptr [rcx+1Ch], 8000h
0x18000e412  jz      short loc_18000E430
0x18000e414  mov     r9d, dword ptr cs:DhcpGlobalJetServerSession
0x18000e41b  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e422  mov     rcx, [rcx+10h]
0x18000e426  mov     edx, 4Dh ; 'M'
0x18000e42b  call    WPP_SF_D
0x18000e430  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000e437  xor     edx, edx
0x18000e439  call    cs:__imp_JetDetachDatabase
0x18000e440  nop     dword ptr [rax+rax+00h]
0x18000e445  mov     edi, eax
0x18000e447  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e44e  cmp     rcx, r13
0x18000e451  jz      short loc_18000E471
0x18000e453  test    dword ptr [rcx+1Ch], 8000h
0x18000e45a  jz      short loc_18000E471
0x18000e45c  mov     rcx, [rcx+10h]
0x18000e460  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000e467  mov     edx, 4Eh ; 'N'
0x18000e46c  call    WPP_SF_
0x18000e471  lea     rdx, aJetdetachdatab; "JetDetachDatabase"
0x18000e478  mov     ecx, edi
0x18000e47a  call    DhcpMapJetError
0x18000e47f  mov     ebx, eax
0x18000e481  test    eax, eax
0x18000e483  jz      short loc_18000E4AF
0x18000e485  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e48c  cmp     rcx, r13
0x18000e48f  jz      loc_18000E9E1
0x18000e495  test    dword ptr [rcx+1Ch], 8000h
0x18000e49c  jz      loc_18000E920
0x18000e4a2  mov     edx, 4Fh ; 'O'
0x18000e4a7  mov     r9d, edi
  ... truncated ...
```
