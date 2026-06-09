# sub_18063AEAC

- ea: `0x18063aeac`
- end: `0x18063b3e1`
- name: `sub_18063AEAC`
- size: `1333`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18062ca64`

## callees

- `0x1800789a4`
- `0x18063aeac`
- `0x1809fb5cc`

## string_xrefs

- `0x18063b19e`: `DROP TABLE IF EXISTS AnomalyInfo; CREATE TABLE AnomalyInfo(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, UnbiasedTime INTEGER NULL); DROP INDEX IF EXISTS IDX_AnomalyInfo_Key; CREATE INDEX IDX_AnomalyInfo_Key ON AnomalyInfo(Key);`
- `0x18063b150`: `DROP TABLE IF EXISTS AmsiFileCache; CREATE TABLE AmsiFileCache(ID INTEGER PRIMARY KEY NOT NULL, PersistId VARCHAR NOT NULL,PersistIdBlob BLOB NOT NULL,ExpirationDate TEXT NOT NULL); DROP INDEX IF EXISTS IDX_AmsiFileCachePersistId; CREATE INDEX IDX_AmsiFileCachePersistId ON AmsiFileCache(PersistId);DROP INDEX IF EXISTS IDX_AmsiFileCacheDate; CREATE INDEX IDX_AmsiFileCacheDate ON AmsiFileCache(ExpirationDate);`
- `0x18063b177`: `DROP TABLE IF EXISTS AttributeCounts; CREATE TABLE AttributeCounts(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, Name NVARCHAR NULL, Count INTEGER NULL, InsertTime INTEGER NULL, ExpireTime INTEGER NULL); DROP INDEX IF EXISTS IDX_AttributeCounts_Key; CREATE INDEX IDX_AttributeCounts_Key ON AttributeCounts(Key);`
- `0x18063b1c5`: `DROP TABLE IF EXISTS AnomalyTables; CREATE TABLE AnomalyTables(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, TableKey INTEGER NULL, TableName TEXT NULL, UnbiasedTableAge INTEGER NULL, KeyName TEXT NULL, FirstSeen INTEGER NULL, LastSeen INTEGER NULL, UnbiasedTime INTEGER NULL, Value REAL NULL, Order_ INTEGER NULL); DROP INDEX IF EXISTS IDX_AnomalyTables_Key; CREATE INDEX IDX_AnomalyTables_Key ON AnomalyTables(Key);`
- `0x18063b23a`: `DROP TABLE IF EXISTS AtomicCounters; CREATE TABLE AtomicCounters(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, Name NVARCHAR NULL, Count INTEGER NULL, InsertTime INTEGER NULL, ExpireTime INTEGER NULL, UpdateTime INTEGER NULL, ScalarFactor INTEGER NULL, LinearFactor INTEGER NULL, DecayInterval INTEGER NULL, HighCount INTEGER NULL, LastDecayTime INTEGER NULL, Namespace NVARCHAR DEFAULT ''); DROP INDEX IF EXISTS IDX_AtomicCounters_Key; CREATE INDEX IDX_AtomicCounters_Key ON AtomicCounters(Key)`
- `0x18063b2af`: `DROP TABLE IF EXISTS DnRevisions; CREATE TABLE DnRevisions(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, Revision INTEGER NULL); DROP INDEX IF EXISTS IDX_DnRevisions; CREATE INDEX IDX_DnRevisions ON DnRevisions(Key);`
- `0x18063aff1`: `DROP TABLE IF EXISTS DynSigRevisions; CREATE TABLE DynSigRevisions(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, SdnRevision INTEGER NULL, EsuRevision INTEGER NULL, BFRevision INTEGER NULL, EntCertRevision INTEGER NULL, TamperRevision INTEGER NULL, AGBlobRevision INTEGER NULL, BFFileAllowRevision INTEGER NULL,BFFileBlockRevision INTEGER NULL,BFCertAllowRevision INTEGER NULL,BFCertBlockRevision INTEGER NULL); DROP INDEX IF EXISTS IDX_DynSigRevisions; CREATE INDEX IDX_DynSigRevisions ON DynSi`
- `0x18063b018`: `DROP TABLE IF EXISTS Engine; CREATE TABLE Engine(ID INTEGER PRIMARY KEY NOT NULL, EngineVersion VARCHAR(20) NULL, SigVersion VARCHAR(20) NULL);`
- `0x18063b129`: `DROP TABLE IF EXISTS FileHashes; CREATE TABLE FileHashes(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, VSN INTEGER NULL, FileID INTEGER NULL, USN INTEGER NULL, InstanceTimeStamp INTEGER NULL, SHA1 BLOB NULL, MD5 BLOB NULL, SHA256 BLOB NULL, LSHASH BLOB NULL, LSHASHS BLOB NULL, CTPH BLOB NULL, PartialCRC1 UNSIGNED INT NULL, PartialCRC2 UNSIGNED INT NULL, PartialCRC3 UNSIGNED INT NULL, KCRC1 UNSIGNED INT NULL, KCRC2 UNSIGNED INT NULL, KCRC3 UNSIGNED INT NULL, KCRC3n UNSIGNED INT NULL); DROP I`
- `0x18063aee0`: `DROP TABLE IF EXISTS AttributePersistContext; CREATE TABLE AttributePersistContext(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, FilePath NVARCHAR NULL, Context NVARCHAR NULL, InsertTime INTEGER NULL, ExpireTime INTEGER NULL); DROP INDEX IF EXISTS IDX_AttributePersistContext_Key; CREATE INDEX IDX_AttributePersistContext_Key ON AttributePersistContext(Key);`
- `0x18063af2e`: `DROP TABLE IF EXISTS BmFileActions; CREATE TABLE BmFileActions(ID INTEGER PRIMARY KEY NOT NULL, FileInfoId INTEGER NOT NULL, ThreatRecordId INTEGER, Action INTEGER); DROP INDEX IF EXISTS IDX_BmFileActions_FileInfoId; CREATE INDEX IDX_BmFileActions_FileInfoId ON BmFileActions(FileInfoId);`
- `0x18063af55`: `DROP TABLE IF EXISTS BmFileInfo; CREATE TABLE BmFileInfo(ID INTEGER PRIMARY KEY NOT NULL, NormalizedPathHash INTEGER, DosPathHash INTEGER, StructVersion INTEGER NOT NULL, NormalizedPath NVARCHAR NOT NULL, DosPath NVARCHAR NOT NULL, Wow64Context BLOB, MetaContext BLOB, IsFromWeb TINYINT DEFAULT 0, IsExecutable TINYINT DEFAULT 0); DROP INDEX IF EXISTS IDX_BmFileInfo_NormalizedPath; CREATE INDEX IDX_BmFileInfo_NormalizedPath ON BmFileInfo(NormalizedPathHash); DROP INDEX IF EXISTS IDX_BmFileInfo_Dos`
- `0x18063af07`: `DROP TABLE IF EXISTS BackupProcessInfo; CREATE TABLE BackupProcessInfo(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, FilePath NVARCHAR NULL, FirstStartTime INTEGER NULL, NextUSN INTEGER NULL, AutomaticRemovalPolicy INTEGER NULL, ImpactedCBPNameSpaces NVARCHAR NULL, InstanceTimeStamp INTEGER NULL); DROP INDEX IF EXISTS IDX_BackupProcessInfo; CREATE INDEX IDX_BackupProcessInfo ON BackupProcessInfo(Key);`
- `0x18063afa3`: `DROP TABLE IF EXISTS BmHipsRuleInfo; CREATE TABLE BmHipsRuleInfo(ID INTEGER PRIMARY KEY NOT NULL, ProcessInfoId INTEGER NOT NULL, RuleAction INTEGER NOT NULL, RuleId BLOB, IsAudit INTEGER NOT NULL DEFAULT 0, IsInherited INTEGER NOT NULL DEFAULT 0, State INTEGER NULL); DROP INDEX IF EXISTS IDX_BmHipsRuleInfo_ProcessInfoId; CREATE INDEX IDX_BmHipsRuleInfo_ProcessInfoId ON BmHipsRuleInfo(ProcessInfoId);`
- `0x18063af7c`: `DROP TABLE IF EXISTS BmFileStartupActions; CREATE TABLE BmFileStartupActions(ID INTEGER PRIMARY KEY NOT NULL, FilePathHash INTEGER NULL, FilePath NVARCHAR NULL, ActionFlags INTEGER NULL, ProcessStartCount INTEGER NULL, FdrFlags INTEGER NULL, FdrThreatRecordId INTEGER NULL, EvaluatorThreatRecordId INTEGER NULL, TrustedInstallerThreatRecordId INTEGER NULL, LFRThreatRecordId INTEGER NULL); DROP INDEX IF EXISTS IDX_BmFileStartupActions; CREATE INDEX IDX_BmFileStartupActions ON BmFileStartupActions(F`
- `0x18063afca`: `DROP TABLE IF EXISTS BmProcessInfo; CREATE TABLE BmProcessInfo(ID INTEGER PRIMARY KEY NOT NULL, PPIDHash INTEGER NOT NULL, ProcessStartTime INTEGER NOT NULL, PID INTEGER NOT NULL, StructVersion INTEGER, ImageFileName NVARCHAR, MonitoringFlags_Flags INTEGER NOT NULL, MonitoringFlags_VmHardenType INTEGER NOT NULL, MonitoringFlags_ExemptVmHardenedTypes INTEGER NOT NULL, CommandLineArgs NVARCHAR, HipsInjectionId BLOB, FolderGuardId BLOB, Flags INTEGER, LsassReadMemId BLOB, MonitoringFlags_Flags2Low `
- `0x18063b261`: `DROP TABLE IF EXISTS RollingQueuesValues; CREATE TABLE RollingQueuesValues(ID INTEGER PRIMARY KEY NOT NULL, EntryTable NVARCHAR NULL, EntryKey NVARCHAR NULL, EntryValue NVARCHAR NULL, InsertTime INTEGER NULL, ExpireTime INTEGER NULL); DROP INDEX IF EXISTS IDX_RollingQueuesValues_EntryTable; CREATE INDEX IDX_RollingQueuesValues_EntryTable ON RollingQueuesValues(EntryTable);`
- `0x18063aeb9`: `DROP TABLE IF EXISTS SQLiteGlobals; CREATE TABLE SQLiteGlobals(ID INTEGER PRIMARY KEY NOT NULL, Version INTEGER NOT NULL, Current BOOLEAN NOT NULL, LastUpdated TEXT NULL);`
- `0x18063b1ec`: `DROP TABLE IF EXISTS NetworkIpFirewallRules; CREATE TABLE NetworkIpFirewallRules(ID INTEGER PRIMARY KEY NOT NULL, Key VARCHAR NOT NULL, FirewallRuleName VARCHAR NOT NULL, ExpiryTime INTEGER NOT NULL);DROP INDEX IF EXISTS IDX_NetworkIpFirewallRules; CREATE INDEX IDX_NetworkIpFirewallRules ON NetworkIpFirewallRules(Key);`
- `0x18063b213`: `DROP TABLE IF EXISTS NetworkIpFirewallRulesOutgoing; CREATE TABLE NetworkIpFirewallRulesOutgoing(ID INTEGER PRIMARY KEY NOT NULL, Key VARCHAR NOT NULL, FirewallRuleName VARCHAR NOT NULL, ExpiryTime INTEGER NOT NULL);DROP INDEX IF EXISTS IDX_NetworkIpFirewallRulesOutgoing; CREATE INDEX IDX_NetworkIpFirewallRulesOutgoing ON NetworkIpFirewallRulesOutgoing(Key);`
- `0x18063b03f`: `DROP TABLE IF EXISTS FileLowFiAsync; CREATE TABLE FileLowFiAsync(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, FileName NVARCHAR NULL, SigSeq INTEGER NULL, SigSha BLOB NULL, SigIsSync BOOLEAN NULL, InstanceTimeStamp INTEGER NULL); DROP INDEX IF EXISTS IDX_FileLowFiAsync; CREATE INDEX IDX_FileLowFiAsync ON FileLowFiAsync(Key);`
- `0x18063b066`: `DROP TABLE IF EXISTS FolderGuardPaths; CREATE TABLE FolderGuardPaths(ID INTEGER PRIMARY KEY NOT NULL, UserIdHash INTEGER NOT NULL, UserId NVARCHAR, GUID BLOB, Path NVARCHAR); DROP INDEX IF EXISTS IDX_FolderGuardPaths; CREATE INDEX IDX_FolderGuardPaths ON FolderGuardPaths(UserIdHash);`
- `0x18063b08d`: `DROP TABLE IF EXISTS ProcessBlockHistory; CREATE TABLE ProcessBlockHistory(ID INTEGER PRIMARY KEY NOT NULL, ProcessPath TEXT NOT NULL, TimeStamp INTEGER NOT NULL, TargetPath TEXT, RuleId BLOB, IsAudit BOOLEAN NOT NULL DEFAULT 0, Action INTEGER NOT NULL, ProcessTaintReason INTEGER NOT NULL DEFAULT 0, ProcessIntegrity INTEGER NOT NULL); DROP INDEX IF EXISTS IDX_ProcessBlockHistory; CREATE UNIQUE INDEX IDX_ProcessBlockHistoryPathTime ON ProcessBlockHistory(ProcessPath,TimeStamp); CREATE INDEX IDX_P`
- `0x18063b0b4`: `DROP TABLE IF EXISTS RansomwareDetections; CREATE TABLE RansomwareDetections(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, DetectionGuid NVARCHAR NULL, LkgTS INTEGER NULL, NextUSN INTEGER NULL, DetectionTS INTEGER NULL, ProvisionalRemedComplTS INTEGER NULL, RemedComplTS INTEGER NULL, ImpactedCBPNameSpaces NVARCHAR NULL, InstanceTimeStamp INTEGER NULL); DROP INDEX IF EXISTS IDX_RansomwareDetections; CREATE INDEX IDX_RansomwareDetections ON RansomwareDetections(Key);`
- `0x18063b288`: `DROP TABLE IF EXISTS RollingQueuesTables; CREATE TABLE RollingQueuesTables(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, Name NVARCHAR NULL, Capacity INTEGER NULL, TimeToLive INTEGER NULL, Mode INTEGER NULL, Namespace NVARCHAR DEFAULT ''); DROP INDEX IF EXISTS IDX_RollingQueuesTables_Key; CREATE INDEX IDX_RollingQueuesTables_Key ON RollingQueuesTables(Key); DROP INDEX IF EXISTS IDX_RollingQueuesTables_Name; CREATE INDEX IDX_RollingQueuesTables_Name ON RollingQueuesTables(Name); DROP TRIGGER`
- `0x18063b0db`: `DROP TABLE IF EXISTS SdnEx; CREATE TABLE SdnEx(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, CurrentCount INTEGER NULL); DROP INDEX IF EXISTS IDX_SdnEx; CREATE INDEX IDX_SdnEx ON SdnEx(Key);`
- `0x18063b102`: `DROP TABLE IF EXISTS ValueMapArray; CREATE TABLE ValueMapArray(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, RecordType INTEGER NULL, ValueMapArrayBlob BLOB NULL, InstanceTimeStamp INTEGER NULL); DROP INDEX IF EXISTS IDX_ValueMapArray; CREATE INDEX IDX_ValueMapArray ON ValueMapArray(Key);`

## pseudocode

```c
__int64 __fastcall sub_18063AEAC(__int64 a1)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 result; // rax
  const char *v30; // [rsp+20h] [rbp-10h] BYREF
  __int64 v31; // [rsp+28h] [rbp-8h]

  v31 = 171;
  v30 = "DROP TABLE IF EXISTS SQLiteGlobals; CREATE TABLE SQLiteGlobals(ID INTEGER PRIMARY KEY NOT NULL, Version INTEGER "
        "NOT NULL, Current BOOLEAN NOT NULL, LastUpdated TEXT NULL);";
  v2 = sub_1809FB5CC(a1, &v30);
  if ( v2 < 0 )
    sub_1800789A4((unsigned int)v2);
  v31 = 363;
  v30 = "DROP TABLE IF EXISTS AttributePersistContext; CREATE TABLE AttributePersistContext(ID INTEGER PRIMARY KEY NOT NU"
        "LL, Key INTEGER NULL, FilePath NVARCHAR NULL, Context NVARCHAR NULL, InsertTime INTEGER NULL, ExpireTime INTEGER"
        " NULL); DROP INDEX IF EXISTS IDX_AttributePersistContext_Key; CREATE INDEX IDX_AttributePersistContext_Key ON At"
        "tributePersistContext(Key);";
  v3 = sub_1809FB5CC(a1, &v30);
  if ( v3 < 0 )
    sub_1800789A4((unsigned int)v3);
  v31 = 409;
  v30 = "DROP TABLE IF EXISTS BackupProcessInfo; CREATE TABLE BackupProcessInfo(ID INTEGER PRIMARY KEY NOT NULL, Key INTE"
        "GER NULL, FilePath NVARCHAR NULL, FirstStartTime INTEGER NULL, NextUSN INTEGER NULL, AutomaticRemovalPolicy INTE"
        "GER NULL, ImpactedCBPNameSpaces NVARCHAR NULL, InstanceTimeStamp INTEGER NULL); DROP INDEX IF EXISTS IDX_BackupP"
        "rocessInfo; CREATE INDEX IDX_BackupProcessInfo ON BackupProcessInfo(Key);";
  v4 = sub_1809FB5CC(a1, &v30);
  if ( v4 < 0 )
    sub_1800789A4((unsigned int)v4);
  v31 = 288;
  v30 = "DROP TABLE IF EXISTS BmFileActions; CREATE TABLE BmFileActions(ID INTEGER PRIMARY KEY NOT NULL, FileInfoId INTEG"
        "ER NOT NULL, ThreatRecordId INTEGER, Action INTEGER); DROP INDEX IF EXISTS IDX_BmFileActions_FileInfoId; CREATE "
        "INDEX IDX_BmFileActions_FileInfoId ON BmFileActions(FileInfoId);";
  v5 = sub_1809FB5CC(a1, &v30);
  if ( v5 < 0 )
    sub_1800789A4((unsigned int)v5);
  v31 = 758;
  v30 = "DROP TABLE IF EXISTS BmFileInfo; CREATE TABLE BmFileInfo(ID INTEGER PRIMARY KEY NOT NULL, NormalizedPathHash INT"
        "EGER, DosPathHash INTEGER, StructVersion INTEGER NOT NULL, NormalizedPath NVARCHAR NOT NULL, DosPath NVARCHAR NO"
        "T NULL, Wow64Context BLOB, MetaContext BLOB, IsFromWeb TINYINT DEFAULT 0, IsExecutable TINYINT DEFAULT 0); DROP "
        "INDEX IF EXISTS IDX_BmFileInfo_NormalizedPath; CREATE INDEX IDX_BmFileInfo_NormalizedPath ON BmFileInfo(Normaliz"
        "edPathHash); DROP INDEX IF EXISTS IDX_BmFileInfo_DosPath; CREATE INDEX IDX_BmFileInfo_DosPath ON BmFileInfo(DosP"
        "athHash); DROP TRIGGER IF EXISTS TGR_BmFileInfo_DeleteActions; CREATE TRIGGER TGR_BmFileInfo_DeleteActions AFTER"
        " DELETE ON BmFileInfo BEGIN  DELETE FROM BmFileActions WHERE FileInfoId = OLD.ID; END;";
  v6 = sub_1809FB5CC(a1, &v30);
  if ( v6 < 0 )
    sub_1800789A4((unsigned int)v6);
  v31 = 513;
  v30 = "DROP TABLE IF EXISTS BmFileStartupActions; CREATE TABLE BmFileStartupActions(ID INTEGER PRIMARY KEY NOT NULL, Fi"
        "lePathHash INTEGER NULL, FilePath NVARCHAR NULL, ActionFlags INTEGER NULL, ProcessStartCount INTEGER NULL, FdrFl"
        "ags INTEGER NULL, FdrThreatRecordId INTEGER NULL, EvaluatorThreatRecordId INTEGER NULL, TrustedInstallerThreatRe"
        "cordId INTEGER NULL, LFRThreatRecordId INTEGER NULL); DROP INDEX IF EXISTS IDX_BmFileStartupActions; CREATE INDE"
        "X IDX_BmFileStartupActions ON BmFileStartupActions(FilePathHash);";
  v7 = sub_1809FB5CC(a1, &v30);
  if ( v7 < 0 )
    sub_1800789A4((unsigned int)v7);
  v31 = 403;
  v30 = "DROP TABLE IF EXISTS BmHipsRuleInfo; CREATE TABLE BmHipsRuleInfo(ID INTEGER PRIMARY KEY NOT NULL, ProcessInfoId "
        "INTEGER NOT NULL, RuleAction INTEGER NOT NULL, RuleId BLOB, IsAudit INTEGER NOT NULL DEFAULT 0, IsInherited INTE"
        "GER NOT NULL DEFAULT 0, State INTEGER NULL); DROP INDEX IF EXISTS IDX_BmHipsRuleInfo_ProcessInfoId; CREATE INDEX"
        " IDX_BmHipsRuleInfo_ProcessInfoId ON BmHipsRuleInfo(ProcessInfoId);";
  v8 = sub_1809FB5CC(a1, &v30);
  if ( v8 < 0 )
    sub_1800789A4((unsigned int)v8);
  v31 = 859;
  v30 = "DROP TABLE IF EXISTS BmProcessInfo; CREATE TABLE BmProcessInfo(ID INTEGER PRIMARY KEY NOT NULL, PPIDHash INTEGER"
        " NOT NULL, ProcessStartTime INTEGER NOT NULL, PID INTEGER NOT NULL, StructVersion INTEGER, ImageFileName NVARCHA"
        "R, MonitoringFlags_Flags INTEGER NOT NULL, MonitoringFlags_VmHardenType INTEGER NOT NULL, MonitoringFlags_Exempt"
        "VmHardenedTypes INTEGER NOT NULL, CommandLineArgs NVARCHAR, HipsInjectionId BLOB, FolderGuardId BLOB, Flags INTE"
        "GER, LsassReadMemId BLOB, MonitoringFlags_Flags2Low INTEGER, MonitoringFlags_Flags2High INTEGER);DROP INDEX IF E"
        "XISTS IDX_BmProcessInfo_PPID; CREATE INDEX IDX_BmProcessInfo_PPID ON BmProcessInfo(PPIDHash); DROP TRIGGER IF EX"
        "ISTS TGR_BmProcessInfo_DeleteHipsRules; CREATE TRIGGER TGR_BmProcessInfo_DeleteHipsRules AFTER DELETE ON BmProce"
        "ssInfo BEGIN  DELETE FROM BmHipsRuleInfo WHERE ProcessInfoId = OLD.ID; END;";
  v9 = sub_1809FB5CC(a1, &v30);
  if ( v9 < 0 )
    sub_1800789A4((unsigned int)v9);
  v31 = 516;
  v30 = "DROP TABLE IF EXISTS DynSigRevisions; CREATE TABLE DynSigRevisions(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER "
        "NULL, SdnRevision INTEGER NULL, EsuRevision INTEGER NULL, BFRevision INTEGER NULL, EntCertRevision INTEGER NULL,"
        " TamperRevision INTEGER NULL, AGBlobRevision INTEGER NULL, BFFileAllowRevision INTEGER NULL,BFFileBlockRevision "
        "INTEGER NULL,BFCertAllowRevision INTEGER NULL,BFCertBlockRevision INTEGER NULL); DROP INDEX IF EXISTS IDX_DynSig"
        "Revisions; CREATE INDEX IDX_DynSigRevisions ON DynSigRevisions(Key);";
  v10 = sub_1809FB5CC(a1, &v30);
  if ( v10 < 0 )
    sub_1800789A4((unsigned int)v10);
  v31 = 143;
  v30 = "DROP TABLE IF EXISTS Engine; CREATE TABLE Engine(ID INTEGER PRIMARY KEY NOT NULL, EngineVersion VARCHAR(20) NULL"
        ", SigVersion VARCHAR(20) NULL);";
  v11 = sub_1809FB5CC(a1, &v30);
  if ( v11 < 0 )
    sub_1800789A4((unsigned int)v11);
  v31 = 332;
  v30 = "DROP TABLE IF EXISTS FileLowFiAsync; CREATE TABLE FileLowFiAsync(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NU"
        "LL, FileName NVARCHAR NULL, SigSeq INTEGER NULL, SigSha BLOB NULL, SigIsSync BOOLEAN NULL, InstanceTimeStamp INT"
        "EGER NULL); DROP INDEX IF EXISTS IDX_FileLowFiAsync; CREATE INDEX IDX_FileLowFiAsync ON FileLowFiAsync(Key);";
  v12 = sub_1809FB5CC(a1, &v30);
  if ( v12 < 0 )
    sub_1800789A4((unsigned int)v12);
  v31 = 284;
  v30 = "DROP TABLE IF EXISTS FolderGuardPaths; CREATE TABLE FolderGuardPaths(ID INTEGER PRIMARY KEY NOT NULL, UserIdHash"
        " INTEGER NOT NULL, UserId NVARCHAR, GUID BLOB, Path NVARCHAR); DROP INDEX IF EXISTS IDX_FolderGuardPaths; CREATE"
        " INDEX IDX_FolderGuardPaths ON FolderGuardPaths(UserIdHash);";
  v13 = sub_1809FB5CC(a1, &v30);
  if ( v13 < 0 )
    sub_1800789A4((unsigned int)v13);
  v31 = 557;
  v30 = "DROP TABLE IF EXISTS ProcessBlockHistory; CREATE TABLE ProcessBlockHistory(ID INTEGER PRIMARY KEY NOT NULL, Proc"
        "essPath TEXT NOT NULL, TimeStamp INTEGER NOT NULL, TargetPath TEXT, RuleId BLOB, IsAudit BOOLEAN NOT NULL DEFAUL"
        "T 0, Action INTEGER NOT NULL, ProcessTaintReason INTEGER NOT NULL DEFAULT 0, ProcessIntegrity INTEGER NOT NULL);"
        " DROP INDEX IF EXISTS IDX_ProcessBlockHistory; CREATE UNIQUE INDEX IDX_ProcessBlockHistoryPathTime ON ProcessBlo"
        "ckHistory(ProcessPath,TimeStamp); CREATE INDEX IDX_ProcessBlockHistoryTime ON ProcessBlockHistory(TimeStamp);";
  v14 = sub_1809FB5CC(a1, &v30);
  if ( v14 < 0 )
    sub_1800789A4((unsigned int)v14);
  v31 = 474;
  v30 = "DROP TABLE IF EXISTS RansomwareDetections; CREATE TABLE RansomwareDetections(ID INTEGER PRIMARY KEY NOT NULL, Ke"
        "y INTEGER NULL, DetectionGuid NVARCHAR NULL, LkgTS INTEGER NULL, NextUSN INTEGER NULL, DetectionTS INTEGER NULL,"
        " ProvisionalRemedComplTS INTEGER NULL, RemedComplTS INTEGER NULL, ImpactedCBPNameSpaces NVARCHAR NULL, InstanceT"
        "imeStamp INTEGER NULL); DROP INDEX IF EXISTS IDX_RansomwareDetections; CREATE INDEX IDX_RansomwareDetections ON "
        "RansomwareDetections(Key);";
  v15 = sub_1809FB5CC(a1, &v30);
  if ( v15 < 0 )
    sub_1800789A4((unsigned int)v15);
  v31 = 195;
  v30 = "DROP TABLE IF EXISTS SdnEx; CREATE TABLE SdnEx(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, CurrentCount I"
        "NTEGER NULL); DROP INDEX IF EXISTS IDX_SdnEx; CREATE INDEX IDX_SdnEx ON SdnEx(Key);";
  v16 = sub_1809FB5CC(a1, &v30);
  if ( v16 < 0 )
    sub_1800789A4((unsigned int)v16);
  v31 = 294;
  v30 = "DROP TABLE IF EXISTS ValueMapArray; CREATE TABLE ValueMapArray(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL"
        ", RecordType INTEGER NULL, ValueMapArrayBlob BLOB NULL, InstanceTimeStamp INTEGER NULL); DROP INDEX IF EXISTS ID"
        "X_ValueMapArray; CREATE INDEX IDX_ValueMapArray ON ValueMapArray(Key);";
  v17 = sub_1809FB5CC(a1, &v30);
  if ( v17 < 0 )
    sub_1800789A4((unsigned int)v17);
  v31 = 578;
  v30 = "DROP TABLE IF EXISTS FileHashes; CREATE TABLE FileHashes(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, VSN "
        "INTEGER NULL, FileID INTEGER NULL, USN INTEGER NULL, InstanceTimeStamp INTEGER NULL, SHA1 BLOB NULL, MD5 BLOB NU"
        "LL, SHA256 BLOB NULL, LSHASH BLOB NULL, LSHASHS BLOB NULL, CTPH BLOB NULL, PartialCRC1 UNSIGNED INT NULL, Partia"
        "lCRC2 UNSIGNED INT NULL, PartialCRC3 UNSIGNED INT NULL, KCRC1 UNSIGNED INT NULL, KCRC2 UNSIGNED INT NULL, KCRC3 "
        "UNSIGNED INT NULL, KCRC3n UNSIGNED INT NULL); DROP INDEX IF EXISTS IDX_FileHashes; CREATE INDEX IDX_FileHashes O"
        "N FileHashes(Key);";
  v18 = sub_1809FB5CC(a1, &v30);
  if ( v18 < 0 )
    sub_1800789A4((unsigned int)v18);
  v31 = 411;
  v30 = "DROP TABLE IF EXISTS AmsiFileCache; CREATE TABLE AmsiFileCache(ID INTEGER PRIMARY KEY NOT NULL, PersistId VARCHA"
        "R NOT NULL,PersistIdBlob BLOB NOT NULL,ExpirationDate TEXT NOT NULL); DROP INDEX IF EXISTS IDX_AmsiFileCachePers"
        "istId; CREATE INDEX IDX_AmsiFileCachePersistId ON AmsiFileCache(PersistId);DROP INDEX IF EXISTS IDX_AmsiFileCach"
        "eDate; CREATE INDEX IDX_AmsiFileCacheDate ON AmsiFileCache(ExpirationDate);";
  v19 = sub_1809FB5CC(a1, &v30);
  if ( v19 < 0 )
    sub_1800789A4((unsigned int)v19);
  v31 = 316;
  v30 = "DROP TABLE IF EXISTS AttributeCounts; CREATE TABLE AttributeCounts(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER "
        "NULL, Name NVARCHAR NULL, Count INTEGER NULL, InsertTime INTEGER NULL, ExpireTime INTEGER NULL); DROP INDEX IF E"
        "XISTS IDX_AttributeCounts_Key; CREATE INDEX IDX_AttributeCounts_Key ON AttributeCounts(Key);";
  v20 = sub_1809FB5CC(a1, &v30);
  if ( v20 < 0 )
    sub_1800789A4((unsigned int)v20);
  v31 = 233;
  v30 = "DROP TABLE IF EXISTS AnomalyInfo; CREATE TABLE AnomalyInfo(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, Un"
        "biasedTime INTEGER NULL); DROP INDEX IF EXISTS IDX_AnomalyInfo_Key; CREATE INDEX IDX_AnomalyInfo_Key ON AnomalyInfo(Key);";
  v21 = sub_1809FB5CC(a1, &v30);
  if ( v21 < 0 )
    sub_1800789A4((unsigned int)v21);
  v31 = 422;
  v30 = "DROP TABLE IF EXISTS AnomalyTables; CREATE TABLE AnomalyTables(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL"
        ", TableKey INTEGER NULL, TableName TEXT NULL, UnbiasedTableAge INTEGER NULL, KeyName TEXT NULL, FirstSeen INTEGE"
        "R NULL, LastSeen INTEGER NULL, UnbiasedTime INTEGER NULL, Value REAL NULL, Order_ INTEGER NULL); DROP INDEX IF E"
        "XISTS IDX_AnomalyTables_Key; CREATE INDEX IDX_AnomalyTables_Key ON AnomalyTables(Key);";
  v22 = sub_1809FB5CC(a1, &v30);
  if ( v22 < 0 )
    sub_1800789A4((unsigned int)v22);
  v31 = 320;
  v30 = "DROP TABLE IF EXISTS NetworkIpFirewallRules; CREATE TABLE NetworkIpFirewallRules(ID INTEGER PRIMARY KEY NOT NULL"
        ", Key VARCHAR NOT NULL, FirewallRuleName VARCHAR NOT NULL, ExpiryTime INTEGER NOT NULL);DROP INDEX IF EXISTS IDX"
        "_NetworkIpFirewallRules; CREATE INDEX IDX_NetworkIpFirewallRules ON NetworkIpFirewallRules(Key);";
  v23 = sub_1809FB5CC(a1, &v30);
  if ( v23 < 0 )
    sub_1800789A4((unsigned int)v23);
  v31 = 360;
  v30 = "DROP TABLE IF EXISTS NetworkIpFirewallRulesOutgoing; CREATE TABLE NetworkIpFirewallRulesOutgoing(ID INTEGER PRIM"
        "ARY KEY NOT NULL, Key VARCHAR NOT NULL, FirewallRuleName VARCHAR NOT NULL, ExpiryTime INTEGER NOT NULL);DROP IND"
        "EX IF EXISTS IDX_NetworkIpFirewallRulesOutgoing; CREATE INDEX IDX_NetworkIpFirewallRulesOutgoing ON NetworkIpFir"
        "ewallRulesOutgoing(Key);";
  v24 = sub_1809FB5CC(a1, &v30);
  if ( v24 < 0 )
    sub_1800789A4((unsigned int)v24);
  v31 = 501;
  v30 = "DROP TABLE IF EXISTS AtomicCounters; CREATE TABLE AtomicCounters(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NU"
        "LL, Name NVARCHAR NULL, Count INTEGER NULL, InsertTime INTEGER NULL, ExpireTime INTEGER NULL, UpdateTime INTEGER"
        " NULL, ScalarFactor INTEGER NULL, LinearFactor INTEGER NULL, DecayInterval INTEGER NULL, HighCount INTEGER NULL,"
        " LastDecayTime INTEGER NULL, Namespace NVARCHAR DEFAULT ''); DROP INDEX IF EXISTS IDX_AtomicCounters_Key; CREATE"
        " INDEX IDX_AtomicCounters_Key ON AtomicCounters(Key);";
  v25 = sub_1809FB5CC(a1, &v30);
  if ( v25 < 0 )
    sub_1800789A4((unsigned int)v25);
  v31 = 375;
  v30 = "DROP TABLE IF EXISTS RollingQueuesValues; CREATE TABLE RollingQueuesValues(ID INTEGER PRIMARY KEY NOT NULL, Entr"
        "yTable NVARCHAR NULL, EntryKey NVARCHAR NULL, EntryValue NVARCHAR NULL, InsertTime INTEGER NULL, ExpireTime INTE"
        "GER NULL); DROP INDEX IF EXISTS IDX_RollingQueuesValues_EntryTable; CREATE INDEX IDX_RollingQueuesValues_EntryTa"
        "ble ON RollingQueuesValues(EntryTable);";
  v26 = sub_1809FB5CC(a1, &v30);
  if ( v26 < 0 )
    sub_1800789A4((unsigned int)v26);
  v31 = 731;
  v30 = "DROP TABLE IF EXISTS RollingQueuesTables; CREATE TABLE RollingQueuesTables(ID INTEGER PRIMARY KEY NOT NULL, Key "
        "INTEGER NULL, Name NVARCHAR NULL, Capacity INTEGER NULL, TimeToLive INTEGER NULL, Mode INTEGER NULL, Namespace N"
        "VARCHAR DEFAULT ''); DROP INDEX IF EXISTS IDX_RollingQueuesTables_Key; CREATE INDEX IDX_RollingQueuesTables_Key "
        "ON RollingQueuesTables(Key); DROP INDEX IF EXISTS IDX_RollingQueuesTables_Name; CREATE INDEX IDX_RollingQueuesTa"
        "bles_Name ON RollingQueuesTables(Name); DROP TRIGGER IF EXISTS TGR_RollingQueuesTables_DeleteActions; CREATE TRI"
        "GGER TGR_RollingQueuesTables_DeleteActions AFTER DELETE ON RollingQueuesTables BEGIN  DELETE FROM RollingQueuesV"
        "alues WHERE EntryTable = (OLD.Namespace || OLD.Name); END; ";
  v27 = sub_1809FB5CC(a1, &v30);
  if ( v27 < 0 )
    sub_1800789A4((unsigned int)v27);
  v31 = 221;
  v30 = "DROP TABLE IF EXISTS DnRevisions; CREATE TABLE DnRevisions(ID INTEGER PRIMARY KEY NOT NULL, Key INTEGER NULL, Re"
        "vision INTEGER NULL); DROP INDEX IF EXISTS IDX_DnRevisions; CREATE INDEX IDX_DnRevisions ON DnRevisions(Key);";
  v28 = sub_1809FB5CC(a1, &v30);
  if ( v28 < 0 )
    sub_1800789A4((unsigned int)v28);
  v30 = 0;
  v31 = 0;
  result = sub_1809FB5CC(a1, &v30);
  if ( (int)result < 0 )
    sub_1800789A4((unsigned int)result);
  return result;
}

```

## disassembly

```asm
0x18063aeac  mov     [rsp-8+arg_0], rbx
0x18063aeb1  push    rbp
0x18063aeb2  mov     rbp, rsp
0x18063aeb5  sub     rsp, 30h
0x18063aeb9  lea     rax, aDropTableIfExi; "DROP TABLE IF EXISTS SQLiteGlobals; CRE"...
0x18063aec0  mov     [rbp+var_8], 0ABh
0x18063aec8  lea     rdx, [rbp+var_10]
0x18063aecc  mov     [rbp+var_10], rax
0x18063aed0  mov     rbx, rcx
0x18063aed3  call    sub_1809FB5CC
0x18063aed8  test    eax, eax
0x18063aeda  js      loc_18063B309
0x18063aee0  lea     rax, aDropTableIfExi_0; "DROP TABLE IF EXISTS AttributePersistCo"...
0x18063aee7  mov     [rbp+var_8], 16Bh
0x18063aeef  lea     rdx, [rbp+var_10]
0x18063aef3  mov     [rbp+var_10], rax
0x18063aef7  mov     rcx, rbx
0x18063aefa  call    sub_1809FB5CC
0x18063aeff  test    eax, eax
0x18063af01  js      loc_18063B311
0x18063af07  lea     rax, aDropTableIfExi_1; "DROP TABLE IF EXISTS BackupProcessInfo;"...
0x18063af0e  mov     [rbp+var_8], 199h
0x18063af16  lea     rdx, [rbp+var_10]
0x18063af1a  mov     [rbp+var_10], rax
0x18063af1e  mov     rcx, rbx
0x18063af21  call    sub_1809FB5CC
0x18063af26  test    eax, eax
0x18063af28  js      loc_18063B319
0x18063af2e  lea     rax, aDropTableIfExi_2; "DROP TABLE IF EXISTS BmFileActions; CRE"...
0x18063af35  mov     [rbp+var_8], 120h
0x18063af3d  lea     rdx, [rbp+var_10]
0x18063af41  mov     [rbp+var_10], rax
0x18063af45  mov     rcx, rbx
0x18063af48  call    sub_1809FB5CC
0x18063af4d  test    eax, eax
0x18063af4f  js      loc_18063B321
0x18063af55  lea     rax, aDropTableIfExi_3; "DROP TABLE IF EXISTS BmFileInfo; CREATE"...
0x18063af5c  mov     [rbp+var_8], 2F6h
0x18063af64  lea     rdx, [rbp+var_10]
0x18063af68  mov     [rbp+var_10], rax
0x18063af6c  mov     rcx, rbx
0x18063af6f  call    sub_1809FB5CC
0x18063af74  test    eax, eax
0x18063af76  js      loc_18063B329
0x18063af7c  lea     rax, aDropTableIfExi_4; "DROP TABLE IF EXISTS BmFileStartupActio"...
0x18063af83  mov     [rbp+var_8], 201h
0x18063af8b  lea     rdx, [rbp+var_10]
0x18063af8f  mov     [rbp+var_10], rax
0x18063af93  mov     rcx, rbx
0x18063af96  call    sub_1809FB5CC
0x18063af9b  test    eax, eax
0x18063af9d  js      loc_18063B331
0x18063afa3  lea     rax, aDropTableIfExi_5; "DROP TABLE IF EXISTS BmHipsRuleInfo; CR"...
0x18063afaa  mov     [rbp+var_8], 193h
0x18063afb2  lea     rdx, [rbp+var_10]
0x18063afb6  mov     [rbp+var_10], rax
0x18063afba  mov     rcx, rbx
0x18063afbd  call    sub_1809FB5CC
0x18063afc2  test    eax, eax
0x18063afc4  js      loc_18063B339
0x18063afca  lea     rax, aDropTableIfExi_6; "DROP TABLE IF EXISTS BmProcessInfo; CRE"...
0x18063afd1  mov     [rbp+var_8], 35Bh
0x18063afd9  lea     rdx, [rbp+var_10]
0x18063afdd  mov     [rbp+var_10], rax
0x18063afe1  mov     rcx, rbx
0x18063afe4  call    sub_1809FB5CC
0x18063afe9  test    eax, eax
0x18063afeb  js      loc_18063B341
0x18063aff1  lea     rax, aDropTableIfExi_7; "DROP TABLE IF EXISTS DynSigRevisions; C"...
0x18063aff8  mov     [rbp+var_8], 204h
0x18063b000  lea     rdx, [rbp+var_10]
0x18063b004  mov     [rbp+var_10], rax
0x18063b008  mov     rcx, rbx
0x18063b00b  call    sub_1809FB5CC
0x18063b010  test    eax, eax
0x18063b012  js      loc_18063B349
0x18063b018  lea     rax, aDropTableIfExi_8; "DROP TABLE IF EXISTS Engine; CREATE TAB"...
0x18063b01f  mov     [rbp+var_8], 8Fh
0x18063b027  lea     rdx, [rbp+var_10]
0x18063b02b  mov     [rbp+var_10], rax
0x18063b02f  mov     rcx, rbx
0x18063b032  call    sub_1809FB5CC
0x18063b037  test    eax, eax
0x18063b039  js      loc_18063B351
0x18063b03f  lea     rax, aDropTableIfExi_9; "DROP TABLE IF EXISTS FileLowFiAsync; CR"...
0x18063b046  mov     [rbp+var_8], 14Ch
0x18063b04e  lea     rdx, [rbp+var_10]
0x18063b052  mov     [rbp+var_10], rax
0x18063b056  mov     rcx, rbx
0x18063b059  call    sub_1809FB5CC
0x18063b05e  test    eax, eax
0x18063b060  js      loc_18063B359
0x18063b066  lea     rax, aDropTableIfExi_10; "DROP TABLE IF EXISTS FolderGuardPaths; "...
0x18063b06d  mov     [rbp+var_8], 11Ch
0x18063b075  lea     rdx, [rbp+var_10]
0x18063b079  mov     [rbp+var_10], rax
0x18063b07d  mov     rcx, rbx
0x18063b080  call    sub_1809FB5CC
0x18063b085  test    eax, eax
0x18063b087  js      loc_18063B361
0x18063b08d  lea     rax, aDropTableIfExi_11; "DROP TABLE IF EXISTS ProcessBlockHistor"...
0x18063b094  mov     [rbp+var_8], 22Dh
0x18063b09c  lea     rdx, [rbp+var_10]
0x18063b0a0  mov     [rbp+var_10], rax
0x18063b0a4  mov     rcx, rbx
0x18063b0a7  call    sub_1809FB5CC
0x18063b0ac  test    eax, eax
0x18063b0ae  js      loc_18063B369
0x18063b0b4  lea     rax, aDropTableIfExi_12; "DROP TABLE IF EXISTS RansomwareDetectio"...
0x18063b0bb  mov     [rbp+var_8], 1DAh
0x18063b0c3  lea     rdx, [rbp+var_10]
0x18063b0c7  mov     [rbp+var_10], rax
0x18063b0cb  mov     rcx, rbx
0x18063b0ce  call    sub_1809FB5CC
0x18063b0d3  test    eax, eax
0x18063b0d5  js      loc_18063B371
0x18063b0db  lea     rax, aDropTableIfExi_13; "DROP TABLE IF EXISTS SdnEx; CREATE TABL"...
0x18063b0e2  mov     [rbp+var_8], 0C3h
0x18063b0ea  lea     rdx, [rbp+var_10]
0x18063b0ee  mov     [rbp+var_10], rax
0x18063b0f2  mov     rcx, rbx
0x18063b0f5  call    sub_1809FB5CC
0x18063b0fa  test    eax, eax
0x18063b0fc  js      loc_18063B379
0x18063b102  lea     rax, aDropTableIfExi_14; "DROP TABLE IF EXISTS ValueMapArray; CRE"...
0x18063b109  mov     [rbp+var_8], 126h
0x18063b111  lea     rdx, [rbp+var_10]
0x18063b115  mov     [rbp+var_10], rax
0x18063b119  mov     rcx, rbx
0x18063b11c  call    sub_1809FB5CC
0x18063b121  test    eax, eax
0x18063b123  js      loc_18063B381
0x18063b129  lea     rax, aDropTableIfExi_15; "DROP TABLE IF EXISTS FileHashes; CREATE"...
0x18063b130  mov     [rbp+var_8], 242h
0x18063b138  lea     rdx, [rbp+var_10]
0x18063b13c  mov     [rbp+var_10], rax
0x18063b140  mov     rcx, rbx
0x18063b143  call    sub_1809FB5CC
0x18063b148  test    eax, eax
0x18063b14a  js      loc_18063B389
0x18063b150  lea     rax, aDropTableIfExi_16; "DROP TABLE IF EXISTS AmsiFileCache; CRE"...
0x18063b157  mov     [rbp+var_8], 19Bh
0x18063b15f  lea     rdx, [rbp+var_10]
0x18063b163  mov     [rbp+var_10], rax
0x18063b167  mov     rcx, rbx
0x18063b16a  call    sub_1809FB5CC
0x18063b16f  test    eax, eax
0x18063b171  js      loc_18063B391
0x18063b177  lea     rax, aDropTableIfExi_17; "DROP TABLE IF EXISTS AttributeCounts; C"...
0x18063b17e  mov     [rbp+var_8], 13Ch
0x18063b186  lea     rdx, [rbp+var_10]
0x18063b18a  mov     [rbp+var_10], rax
0x18063b18e  mov     rcx, rbx
0x18063b191  call    sub_1809FB5CC
0x18063b196  test    eax, eax
0x18063b198  js      loc_18063B399
0x18063b19e  lea     rax, aDropTableIfExi_18; "DROP TABLE IF EXISTS AnomalyInfo; CREAT"...
0x18063b1a5  mov     [rbp+var_8], 0E9h
0x18063b1ad  lea     rdx, [rbp+var_10]
0x18063b1b1  mov     [rbp+var_10], rax
0x18063b1b5  mov     rcx, rbx
0x18063b1b8  call    sub_1809FB5CC
0x18063b1bd  test    eax, eax
0x18063b1bf  js      loc_18063B3A1
0x18063b1c5  lea     rax, aDropTableIfExi_19; "DROP TABLE IF EXISTS AnomalyTables; CRE"...
0x18063b1cc  mov     [rbp+var_8], 1A6h
0x18063b1d4  lea     rdx, [rbp+var_10]
0x18063b1d8  mov     [rbp+var_10], rax
0x18063b1dc  mov     rcx, rbx
0x18063b1df  call    sub_1809FB5CC
0x18063b1e4  test    eax, eax
0x18063b1e6  js      loc_18063B3A9
0x18063b1ec  lea     rax, aDropTableIfExi_20; "DROP TABLE IF EXISTS NetworkIpFirewallR"...
0x18063b1f3  mov     [rbp+var_8], 140h
0x18063b1fb  lea     rdx, [rbp+var_10]
0x18063b1ff  mov     [rbp+var_10], rax
0x18063b203  mov     rcx, rbx
0x18063b206  call    sub_1809FB5CC
0x18063b20b  test    eax, eax
0x18063b20d  js      loc_18063B3B1
0x18063b213  lea     rax, aDropTableIfExi_21; "DROP TABLE IF EXISTS NetworkIpFirewallR"...
0x18063b21a  mov     [rbp+var_8], 168h
0x18063b222  lea     rdx, [rbp+var_10]
0x18063b226  mov     [rbp+var_10], rax
0x18063b22a  mov     rcx, rbx
0x18063b22d  call    sub_1809FB5CC
0x18063b232  test    eax, eax
0x18063b234  js      loc_18063B3B9
0x18063b23a  lea     rax, aDropTableIfExi_22; "DROP TABLE IF EXISTS AtomicCounters; CR"...
0x18063b241  mov     [rbp+var_8], 1F5h
0x18063b249  lea     rdx, [rbp+var_10]
0x18063b24d  mov     [rbp+var_10], rax
0x18063b251  mov     rcx, rbx
0x18063b254  call    sub_1809FB5CC
0x18063b259  test    eax, eax
0x18063b25b  js      loc_18063B3C1
0x18063b261  lea     rax, aDropTableIfExi_23; "DROP TABLE IF EXISTS RollingQueuesValue"...
0x18063b268  mov     [rbp+var_8], 177h
0x18063b270  lea     rdx, [rbp+var_10]
0x18063b274  mov     [rbp+var_10], rax
0x18063b278  mov     rcx, rbx
0x18063b27b  call    sub_1809FB5CC
0x18063b280  test    eax, eax
0x18063b282  js      loc_18063B3C9
0x18063b288  lea     rax, aDropTableIfExi_24; "DROP TABLE IF EXISTS RollingQueuesTable"...
0x18063b28f  mov     [rbp+var_8], 2DBh
0x18063b297  lea     rdx, [rbp+var_10]
0x18063b29b  mov     [rbp+var_10], rax
0x18063b29f  mov     rcx, rbx
0x18063b2a2  call    sub_1809FB5CC
0x18063b2a7  test    eax, eax
0x18063b2a9  js      loc_18063B3D1
0x18063b2af  lea     rax, aDropTableIfExi_25; "DROP TABLE IF EXISTS DnRevisions; CREAT"...
0x18063b2b6  mov     [rbp+var_8], 0DDh
0x18063b2be  lea     rdx, [rbp+var_10]
0x18063b2c2  mov     [rbp+var_10], rax
0x18063b2c6  mov     rcx, rbx
0x18063b2c9  call    sub_1809FB5CC
0x18063b2ce  test    eax, eax
0x18063b2d0  js      loc_18063B3D9
0x18063b2d6  lea     rdx, [rbp+var_10]
0x18063b2da  mov     [rbp+var_10], 0
0x18063b2e2  mov     rcx, rbx
0x18063b2e5  mov     [rbp+var_8], 0
0x18063b2ed  call    sub_1809FB5CC
0x18063b2f2  test    eax, eax
0x18063b2f4  js      short loc_18063B301
0x18063b2f6  mov     rbx, [rsp+30h+arg_0]
0x18063b2fb  add     rsp, 30h
0x18063b2ff  pop     rbp
0x18063b300  retn
0x18063b301  mov     ecx, eax
0x18063b303  call    sub_1800789A4
0x18063b309  mov     ecx, eax
0x18063b30b  call    sub_1800789A4
0x18063b311  mov     ecx, eax
0x18063b313  call    sub_1800789A4
0x18063b319  mov     ecx, eax
0x18063b31b  call    sub_1800789A4
0x18063b321  mov     ecx, eax
0x18063b323  call    sub_1800789A4
0x18063b329  mov     ecx, eax
0x18063b32b  call    sub_1800789A4
0x18063b331  mov     ecx, eax
0x18063b333  call    sub_1800789A4
0x18063b339  mov     ecx, eax
0x18063b33b  call    sub_1800789A4
0x18063b341  mov     ecx, eax
0x18063b343  call    sub_1800789A4
0x18063b349  mov     ecx, eax
0x18063b34b  call    sub_1800789A4
0x18063b351  mov     ecx, eax
0x18063b353  call    sub_1800789A4
0x18063b359  mov     ecx, eax
0x18063b35b  call    sub_1800789A4
0x18063b361  mov     ecx, eax
0x18063b363  call    sub_1800789A4
0x18063b369  mov     ecx, eax
0x18063b36b  call    sub_1800789A4
0x18063b371  mov     ecx, eax
0x18063b373  call    sub_1800789A4
0x18063b379  mov     ecx, eax
0x18063b37b  call    sub_1800789A4
0x18063b381  mov     ecx, eax
0x18063b383  call    sub_1800789A4
0x18063b389  mov     ecx, eax
0x18063b38b  call    sub_1800789A4
0x18063b391  mov     ecx, eax
0x18063b393  call    sub_1800789A4
0x18063b399  mov     ecx, eax
0x18063b39b  call    sub_1800789A4
0x18063b3a1  mov     ecx, eax
0x18063b3a3  call    sub_1800789A4
0x18063b3a9  mov     ecx, eax
0x18063b3ab  call    sub_1800789A4
0x18063b3b1  mov     ecx, eax
0x18063b3b3  call    sub_1800789A4
0x18063b3b9  mov     ecx, eax
0x18063b3bb  call    sub_1800789A4
0x18063b3c1  mov     ecx, eax
0x18063b3c3  call    sub_1800789A4
0x18063b3c9  mov     ecx, eax
0x18063b3cb  call    sub_1800789A4
0x18063b3d1  mov     ecx, eax
0x18063b3d3  call    sub_1800789A4
0x18063b3d9  mov     ecx, eax
0x18063b3db  call    sub_1800789A4
```
