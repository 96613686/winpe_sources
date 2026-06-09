# DhcpInitializeDatabaseEx

- ea: `0x18000d644`
- end: `0x18000e197`
- name: `DhcpInitializeDatabaseEx`
- size: `2899`
- prototype: ``
- caller_count: `5`
- callee_count: `22`
- tags: `file_ops, registry_config`

## callers

- `0x18000e9d0`
- `0x18000eaa0`
- `0x180013d60`
- `0x180013e20`
- `0x180025144`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000c164`
- `0x18000c714`
- `0x18000ca98`
- `0x18000d644`
- `0x18000e814`
- `0x18000ed68`
- `0x18000f8e0`
- `0x180010a14`
- `0x180010bb8`
- `0x180016694`
- `0x18001c7ac`
- `0x180027f7c`
- `0x18008ddac`
- `0x18008e74c`
- `0x18009e464`
- `0x18009e90c`
- `0x18009ea58`
- `0x1800b546c`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetGetTableColumnInfo` at `0x18000ddbe`
- `ESENT!JetGetTableColumnInfo` at `0x18000ddbe`
- `ESENT!JetCloseTable` at `0x18000e0a0`
- `ESENT!JetCloseTable` at `0x18000e0a0`
- `ESENT!JetGetTableIndexInfo` at `0x18000df05`
- `ESENT!JetGetTableIndexInfo` at `0x18000df05`
- `ESENT!JetCloseDatabase` at `0x18000e0ff`
- `ESENT!JetCloseDatabase` at `0x18000e0ff`
- `ESENT!JetOpenTable` at `0x18000dd14`
- `ESENT!JetOpenTable` at `0x18000dd14`
- `ESENT!JetInit` at `0x18000d8a7`
- `ESENT!JetInit` at `0x18000d8a7`
- `ESENT!JetOpenDatabase` at `0x18000dc3a`
- `ESENT!JetOpenDatabase` at `0x18000dc3a`
- `ESENT!JetAttachDatabase` at `0x18000db97`
- `ESENT!JetAttachDatabase` at `0x18000db97`
- `ESENT!JetBeginSession` at `0x18000d97c`
- `ESENT!JetBeginSession` at `0x18000d97c`
- `ESENT!JetDetachDatabase` at `0x18000dae5`
- `ESENT!JetDetachDatabase` at `0x18000dae5`
- `ESENT!JetAddColumn` at `0x18000de61`
- `ESENT!JetAddColumn` at `0x18000de61`
- `KERNEL32!EnterCriticalSection` at `0x18000d836`
- `KERNEL32!EnterCriticalSection` at `0x18000d836`
- `KERNEL32!LeaveCriticalSection` at `0x18000e158`
- `KERNEL32!LeaveCriticalSection` at `0x18000e158`
- `USER32!OemToCharBuffA` at `0x18000d765`
- `USER32!OemToCharBuffA` at `0x18000da9f`
- `USER32!OemToCharBuffA` at `0x18000d765`
- `USER32!OemToCharBuffA` at `0x18000da9f`

## string_xrefs

- `0x18000dcac`: `CreateAndInitDb`
- `0x18000dd4c`: `OpenTable`

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
  if ( !dword_1800FCEA0 )
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
          while ( DhcpGlobalOemDatabasePath[v24] );
          v25 = -1;
          do
            ++v25;
          while ( DhcpGlobalOemDatabaseName[v25] );
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
                  ++dword_1800FCEA0;
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
0x18000d644  mov     rax, rsp
0x18000d647  mov     [rax+8], rbx
0x18000d64b  mov     [rax+10h], rsi
0x18000d64f  mov     [rax+18h], rdi
0x18000d653  push    rbp
0x18000d654  push    r12
0x18000d656  push    r13
0x18000d658  push    r14
0x18000d65a  push    r15
0x18000d65c  lea     rbp, [rax-128h]
0x18000d663  sub     rsp, 200h
0x18000d66a  mov     rax, cs:__security_cookie
0x18000d671  xor     rax, rsp
0x18000d674  mov     [rbp+120h+var_30], rax
0x18000d67b  xor     eax, eax
0x18000d67d  xor     r12d, r12d
0x18000d680  cmp     cs:dword_1800FCEA0, r12d
0x18000d687  xorps   xmm0, xmm0
0x18000d68a  mov     r14d, ecx
0x18000d68d  mov     [rsp+220h+var_1B0], rax
0x18000d692  movups  xmmword ptr [rsp+220h+var_1C8+8], xmm0
0x18000d697  mov     [rsp+220h+var_1A8], eax
0x18000d69b  mov     r15d, r12d
0x18000d69e  mov     [rbp+120h+szSrc], r12b
0x18000d6a2  jnz     loc_18000E166
0x18000d6a8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d6ac  lea     esi, [rax+1]
0x18000d6af  lea     r13, WPP_GLOBAL_Control
0x18000d6b6  mov     ebx, 104h
0x18000d6bb  test    ecx, ecx
0x18000d6bd  jnz     loc_18000D82F
0x18000d6c3  call    DhcpCheckIfDatabaseUpgraded
0x18000d6c8  cmp     eax, esi
0x18000d6ca  jnz     loc_18000D82F
0x18000d6d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6d7  cmp     rcx, r13
0x18000d6da  jz      short loc_18000D6F8
0x18000d6dc  test    dword ptr [rcx+1Ch], 8000h
0x18000d6e3  jz      short loc_18000D6F8
0x18000d6e5  mov     rcx, [rcx+10h]
0x18000d6e9  lea     edx, [rsi+40h]
0x18000d6ec  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d6f3  call    WPP_SF_
0x18000d6f8  mov     r8, cs:DhcpGlobalOemDatabasePath
0x18000d6ff  mov     r15d, esi
0x18000d702  mov     rax, rdi
0x18000d705  inc     rax
0x18000d708  cmp     [r8+rax], r12b
0x18000d70c  jnz     short loc_18000D705
0x18000d70e  cmp     rax, rbx
0x18000d711  jnb     short loc_18000D74D
0x18000d713  lea     rax, [rbp+120h+szSrc]
0x18000d717  mov     rdx, rbx
0x18000d71a  sub     r8, rax
0x18000d71d  lea     rcx, [rbp+120h+szSrc]
0x18000d721  lea     rax, [rdx+7FFFFEFAh]
0x18000d728  test    rax, rax
0x18000d72b  jz      short loc_18000D73F
0x18000d72d  mov     al, [rcx+r8]
0x18000d731  test    al, al
0x18000d733  jz      short loc_18000D73F
0x18000d735  mov     [rcx], al
0x18000d737  add     rcx, rsi
0x18000d73a  sub     rdx, rsi
0x18000d73d  jnz     short loc_18000D721
0x18000d73f  test    rdx, rdx
0x18000d742  lea     rax, [rcx-1]
0x18000d746  cmovnz  rax, rcx
0x18000d74a  mov     [rax], r12b
0x18000d74d  lea     rax, [rbp+120h+szSrc]
0x18000d751  mov     r8, rdi
0x18000d754  inc     r8; cchDstLength
0x18000d757  cmp     [rax+r8], r12b
0x18000d75b  jnz     short loc_18000D754
0x18000d75d  lea     rdx, [rbp+120h+szSrc]; lpszDst
0x18000d761  lea     rcx, [rbp+120h+szSrc]; lpszSrc
0x18000d765  call    cs:__imp_OemToCharBuffA
0x18000d76c  nop     dword ptr [rax+rax+00h]
0x18000d771  lea     rdx, FileName; "j50*"
0x18000d778  lea     rcx, [rbp+120h+szSrc]; lpPathName
0x18000d77c  call    DhcpDeleteFiles
0x18000d781  mov     ebx, eax
0x18000d783  test    eax, eax
0x18000d785  jz      short loc_18000D7BE
0x18000d787  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d78e  cmp     rcx, r13
0x18000d791  jz      loc_18000E164
0x18000d797  test    byte ptr [rcx+1Ch], 10h
0x18000d79b  jz      loc_18000E164
0x18000d7a1  mov     edx, 42h ; 'B'
0x18000d7a6  mov     rcx, [rcx+10h]
0x18000d7aa  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d7b1  mov     r9d, ebx
0x18000d7b4  call    WPP_SF_D
0x18000d7b9  jmp     loc_18000E164
0x18000d7be  lea     rdx, aResLog; "res*.log"
0x18000d7c5  lea     rcx, [rbp+120h+szSrc]; lpPathName
0x18000d7c9  call    DhcpDeleteFiles
0x18000d7ce  mov     ebx, eax
0x18000d7d0  test    eax, eax
0x18000d7d2  jz      short loc_18000D7F5
0x18000d7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7db  cmp     rcx, r13
0x18000d7de  jz      loc_18000E164
0x18000d7e4  test    byte ptr [rcx+1Ch], 10h
0x18000d7e8  jz      loc_18000E164
0x18000d7ee  mov     edx, 43h ; 'C'
0x18000d7f3  jmp     short loc_18000D7A6
0x18000d7f5  lea     rdx, aMdb; "*.mdb"
0x18000d7fc  lea     rcx, [rbp+120h+szSrc]; lpPathName
0x18000d800  call    DhcpDeleteFiles
0x18000d805  mov     ebx, eax
0x18000d807  test    eax, eax
0x18000d809  jz      short loc_18000D82F
0x18000d80b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d812  cmp     rcx, r13
0x18000d815  jz      loc_18000E164
0x18000d81b  test    byte ptr [rcx+1Ch], 10h
0x18000d81f  jz      loc_18000E164
0x18000d825  mov     edx, 44h ; 'D'
0x18000d82a  jmp     loc_18000D7A6
0x18000d82f  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18000d836  call    cs:__imp_EnterCriticalSection
0x18000d83d  nop     dword ptr [rax+rax+00h]
0x18000d842  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d849  cmp     rcx, r13
0x18000d84c  jz      short loc_18000D86C
0x18000d84e  test    dword ptr [rcx+1Ch], 8000h
0x18000d855  jz      short loc_18000D86C
0x18000d857  mov     rcx, [rcx+10h]
0x18000d85b  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d862  mov     edx, 45h ; 'E'
0x18000d867  call    WPP_SF_
0x18000d86c  call    DhcpSetJetParameters
0x18000d871  mov     ebx, eax
0x18000d873  test    eax, eax
0x18000d875  jnz     loc_18000DFC5
0x18000d87b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d882  cmp     rcx, r13
0x18000d885  jz      short loc_18000D8A0
0x18000d887  test    byte ptr [rcx+1Ch], 10h
0x18000d88b  jz      short loc_18000D8A0
0x18000d88d  mov     rcx, [rcx+10h]
0x18000d891  lea     edx, [rax+46h]
0x18000d894  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d89b  call    WPP_SF_
0x18000d8a0  lea     rcx, JetInstance; pinstance
0x18000d8a7  call    cs:__imp_JetInit
0x18000d8ae  nop     dword ptr [rax+rax+00h]
0x18000d8b3  mov     ebx, eax
0x18000d8b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8bc  cmp     rcx, r13
0x18000d8bf  jz      short loc_18000D909
0x18000d8c1  test    dword ptr [rcx+1Ch], 8000h
0x18000d8c8  jz      short loc_18000D8E9
0x18000d8ca  mov     rcx, [rcx+10h]
0x18000d8ce  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d8d5  mov     edx, 47h ; 'G'
0x18000d8da  mov     r9d, eax
0x18000d8dd  call    WPP_SF_D
0x18000d8e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8e9  cmp     rcx, r13
0x18000d8ec  jz      short loc_18000D909
0x18000d8ee  test    byte ptr [rcx+1Ch], 10h
0x18000d8f2  jz      short loc_18000D909
0x18000d8f4  mov     rcx, [rcx+10h]
0x18000d8f8  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d8ff  mov     edx, 48h ; 'H'
0x18000d904  call    WPP_SF_
0x18000d909  lea     rdx, aJetinit; "JetInit"
0x18000d910  mov     ecx, ebx
0x18000d912  call    DhcpMapJetError
0x18000d917  mov     ebx, eax
0x18000d919  test    eax, eax
0x18000d91b  jnz     loc_18000DFC5
0x18000d921  call    DhcpWriterInit
0x18000d926  mov     ebx, eax
0x18000d928  test    eax, eax
0x18000d92a  jz      short loc_18000D960
0x18000d92c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d933  cmp     rcx, r13
0x18000d936  jz      loc_18000E08D
0x18000d93c  test    byte ptr [rcx+1Ch], 10h
0x18000d940  jz      loc_18000DFCC
0x18000d946  mov     edx, 49h ; 'I'
0x18000d94b  mov     rcx, [rcx+10h]
0x18000d94f  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d956  call    WPP_SF_
0x18000d95b  jmp     loc_18000DFC5
0x18000d960  mov     rcx, cs:JetInstance
0x18000d967  lea     r9, SourceString
0x18000d96e  lea     r8, aAdmin; "admin"
0x18000d975  lea     rdx, DhcpGlobalJetServerSession
0x18000d97c  call    cs:__imp_JetBeginSession
0x18000d983  nop     dword ptr [rax+rax+00h]
0x18000d988  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d98f  mov     esi, eax
0x18000d991  cmp     dword ptr [rcx], 0FFFFFFFFh
0x18000d994  jnz     short loc_18000D9C0
0x18000d996  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d99d  cmp     rcx, r13
0x18000d9a0  jz      short loc_18000D9EA
0x18000d9a2  test    dword ptr [rcx+1Ch], 8000h
0x18000d9a9  jz      short loc_18000D9C7
0x18000d9ab  mov     rcx, [rcx+10h]
0x18000d9af  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d9b6  mov     edx, 4Ah ; 'J'
0x18000d9bb  call    WPP_SF_
0x18000d9c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9c7  cmp     rcx, r13
0x18000d9ca  jz      short loc_18000D9EA
0x18000d9cc  test    dword ptr [rcx+1Ch], 8000h
0x18000d9d3  jz      short loc_18000D9EA
0x18000d9d5  mov     rcx, [rcx+10h]
0x18000d9d9  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d9e0  mov     edx, 4Bh ; 'K'
0x18000d9e5  call    WPP_SF_
0x18000d9ea  lea     rdx, aJetbeginsessio; "JetBeginSEssion"
0x18000d9f1  mov     ecx, esi
0x18000d9f3  call    DhcpMapJetError
0x18000d9f8  mov     ebx, eax
0x18000d9fa  test    eax, eax
0x18000d9fc  jz      short loc_18000DA2B
0x18000d9fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da05  cmp     rcx, r13
0x18000da08  jz      loc_18000E08D
0x18000da0e  mov     r14d, 8000h
0x18000da14  test    [rcx+1Ch], r14d
0x18000da18  jz      loc_18000DFCC
0x18000da1e  mov     edx, 4Ch ; 'L'
0x18000da23  mov     r9d, esi
0x18000da26  jmp     loc_18000DFB5
0x18000da2b  mov     r9, cs:DhcpGlobalOemDatabasePath
0x18000da32  mov     rax, rdi
0x18000da35  mov     [rbp+120h+szSrc], r12b
0x18000da39  inc     rax
0x18000da3c  cmp     [r9+rax], r12b
0x18000da40  jnz     short loc_18000DA39
0x18000da42  mov     r8, cs:DhcpGlobalOemDatabaseName
0x18000da49  mov     rcx, rdi
0x18000da4c  inc     rcx
0x18000da4f  cmp     [r8+rcx], r12b
0x18000da53  jnz     short loc_18000DA4C
0x18000da55  add     rax, 2
0x18000da59  mov     edx, 104h; cbDest
0x18000da5e  add     rax, rcx
0x18000da61  cmp     rax, rdx
0x18000da64  jnb     short loc_18000DA87
0x18000da66  mov     [rsp+220h+var_1F8], r8
0x18000da6b  lea     rax, asc_1800DEB20; "\\"
0x18000da72  lea     r8, aSSS_0; "%s%s%s"
0x18000da79  mov     [rsp+220h+var_200], rax
0x18000da7e  lea     rcx, [rbp+120h+szSrc]; pszDest
0x18000da82  call    StringCbPrintfA
0x18000da87  lea     rax, [rbp+120h+szSrc]
0x18000da8b  inc     rdi
0x18000da8e  cmp     [rax+rdi], r12b
0x18000da92  jnz     short loc_18000DA8B
0x18000da94  mov     r8d, edi; cchDstLength
0x18000da97  lea     rdx, [rbp+120h+szSrc]; lpszDst
0x18000da9b  lea     rcx, [rbp+120h+szSrc]; lpszSrc
0x18000da9f  call    cs:__imp_OemToCharBuffA
0x18000daa6  nop     dword ptr [rax+rax+00h]
0x18000daab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dab2  cmp     rcx, r13
0x18000dab5  jz      short loc_18000DADC
0x18000dab7  test    dword ptr [rcx+1Ch], 8000h
0x18000dabe  jz      short loc_18000DADC
0x18000dac0  mov     r9d, dword ptr cs:DhcpGlobalJetServerSession
0x18000dac7  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000dace  mov     rcx, [rcx+10h]
0x18000dad2  mov     edx, 4Dh ; 'M'
0x18000dad7  call    WPP_SF_D
0x18000dadc  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000dae3  xor     edx, edx
0x18000dae5  call    cs:__imp_JetDetachDatabase
0x18000daec  nop     dword ptr [rax+rax+00h]
0x18000daf1  mov     edi, eax
0x18000daf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dafa  cmp     rcx, r13
0x18000dafd  jz      short loc_18000DB1D
0x18000daff  test    dword ptr [rcx+1Ch], 8000h
0x18000db06  jz      short loc_18000DB1D
0x18000db08  mov     rcx, [rcx+10h]
0x18000db0c  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000db13  mov     edx, 4Eh ; 'N'
0x18000db18  call    WPP_SF_
0x18000db1d  lea     rdx, aJetdetachdatab; "JetDetachDatabase"
0x18000db24  mov     ecx, edi
0x18000db26  call    DhcpMapJetError
0x18000db2b  mov     ebx, eax
0x18000db2d  test    eax, eax
0x18000db2f  jz      short loc_18000DB5B
0x18000db31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db38  cmp     rcx, r13
0x18000db3b  jz      loc_18000E08D
0x18000db41  test    dword ptr [rcx+1Ch], 8000h
0x18000db48  jz      loc_18000DFCC
0x18000db4e  mov     edx, 4Fh ; 'O'
0x18000db53  mov     r9d, edi
  ... truncated ...
```
