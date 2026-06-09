# TextizeJetErrorHresult(long)

- ea: `0x18011031c`
- end: `0x1801118c3`
- name: `?TextizeJetErrorHresult@@YAPEBDJ@Z`
- size: `5543`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180035970`

## callees

- `0x18011031c`

## string_xrefs

- `0x1801103dc`: `JET_errOutOfThreads`
- `0x180110429`: `JET_errTaskDropped`
- `0x18011046f`: `JET_errBadParentPageLink`
- `0x180110493`: `JET_errBadPageLink`
- `0x1801104e1`: `JET_errSPAvailExtCacheOutOfMemory`
- `0x1801104a5`: `JET_errSPAvailExtCacheOutOfSync`
- `0x18011054c`: `JET_errNoBackupDirectory`
- `0x18011053a`: `JET_errBackupDirectoryNotEmpty`
- `0x180110599`: `JET_errCannotLogDuringRecoveryRedo`
- `0x1801105b4`: `JET_errLogWriteFail`
- `0x180110652`: `JET_errMakeBackupDirectoryFail`
- `0x180110649`: `JET_errDeleteBackupFileFail`
- `0x1801107b6`: `JET_errDatabaseIncompleteUpgrade`
- `0x1801107ad`: `JET_errDatabaseAlreadyUpgraded`
- `0x1801107f5`: `JET_errLogCorruptDuringHardRestore`
- `0x1801107ec`: `JET_errLogTornWriteDuringHardRecovery`
- `0x1801107e3`: `JET_errLogTornWriteDuringHardRestore`
- `0x1801107fe`: `JET_errLogCorruptDuringHardRecovery`
- `0x1801108b3`: `JET_errCommittedLogFilesMissing`
- `0x18011088f`: `JET_errCommittedLogFileCorrupt`
- `0x180111701`: `JET_wrnCommittedLogFilesLost`
- `0x1801116ef`: `JET_wrnDatabaseRepaired`
- `0x1801116f8`: `JET_wrnCommittedLogFilesRemoved`
- `0x1801108ee`: `JET_errLogReadVerifyFailure`
- `0x1801109ca`: `JET_errDatabaseFileReadOnly`
- `0x180110a32`: `JET_errReadVerifyFailure`
- `0x180110a29`: `JET_errRecordDeleted`
- `0x180110a68`: `JET_errInvalidLogDirectory`
- `0x180110a5f`: `JET_errInvalidSystemPath`
- `0x180110a56`: `JET_errInvalidPath`
- `0x180110a7a`: `JET_errTooManyOpenDatabases`
- `0x180110aa7`: `JET_errFileAccessDenied`
- `0x180110a95`: `JET_errAlreadyInitialized`
- `0x180110ac2`: `JET_errContainerNotEmpty`
- `0x180110b32`: `JET_errLinkNotSupported`
- `0x1801117c9`: `JET_wrnNoWriteLock`
- `0x180110b9e`: `JET_errRecordNotDeleted`
- `0x180110bf8`: `JET_errSystemPathInUse`
- `0x180110bef`: `JET_errSystemParamsAlreadySet`
- `0x180110c0a`: `JET_errTempPathInUse`
- `0x180110c01`: `JET_errLogFilePathInUse`
- `0x180110c40`: `JET_errWriteConflict`
- `0x180110c5b`: `JET_errWriteConflictPrimaryIndex`
- `0x180110c52`: `JET_errInvalidSesid`
- `0x180110c88`: `JET_errRecordTooBigForBackwardCompatibility`
- `0x180110c7f`: `JET_errSessionWriteConflict`
- `0x180110c76`: `JET_errTransReadOnly`
- `0x180110c6d`: `JET_errRollbackRequired`
- `0x180110c9a`: `JET_errSesidTableIdMismatch`
- `0x180110e17`: `JET_errDatabaseInvalidPath`
- `0x180110eaf`: `JET_errInvalidCreateDbVersion`
- `0x180110eb8`: `JET_errDatabaseCorruptedNoRepair`
- `0x180110f0e`: `JET_errTableNotEmpty`
- `0x180110f20`: `JET_errTooManyOpenTablesAndCleanupTimedOut`
- `0x180110efc`: `JET_errTooManyOpenTables`
- `0x180110f54`: `JET_errCannotDeleteTemplateTable`
- `0x180110f66`: `JET_errCannotDeleteSystemTable`
- `0x180110f6f`: `JET_errCannotDeleteTempTable`
- `0x18011105f`: `JET_errClientRequestToStopJetService`
- `0x1801110ac`: `JET_errInvalidCreateIndex`
- `0x1801110a3`: `JET_errTooManyOpenIndexes`
- `0x1801117a5`: `JET_wrnCorruptIndexDeleted`
- `0x180111811`: `JET_wrnCopyLongValue`
- `0x1801112ff`: `JET_errRecordNoCopy`
- `0x180111370`: `JET_errAlreadyPrepared`
- `0x18011135e`: `JET_errUpdateNotPrepared`
- `0x1801113d1`: `JET_errTempFileOpenError`
- `0x180111877`: `JET_wrnFileOpenReadOnly`
- `0x180111431`: `JET_errAccessDenied`
- `0x18011148a`: `JET_errSessionContextAlreadySet`
- `0x180111478`: `JET_errSessionContextNotSetByThisThread`
- `0x1801118b2`: `JET_wrnDefragAlreadyRunning`
- `0x1801114f2`: `JET_errRollbackError`
- `0x180111577`: `JET_errLSAlreadySet`
- `0x180111644`: `JET_errFileCompressed`

## pseudocode

```c
const char *__fastcall TextizeJetErrorHresult(int a1)
{
  const char *v1; // rdx
  bool v2; // zf
  const char *result; // rax
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx

  if ( a1 > -1906441125 )
  {
    if ( a1 > -1906440711 )
    {
      if ( a1 > -1906438237 )
      {
        if ( a1 > 241042466 )
        {
          if ( a1 > 241042942 )
          {
            if ( a1 > 241043221 )
            {
              v26 = a1 - 241043316;
              if ( !v26 )
                return "JET_wrnIdleFull";
              v27 = v26 - 92;
              if ( !v27 )
                return "JET_wrnDefragAlreadyRunning";
              v28 = v27 - 1;
              if ( !v28 )
                return "JET_wrnDefragNotRunning";
              if ( v28 == 99 )
                return "JET_wrnCallbackNotRegistered";
            }
            else
            {
              if ( a1 == 241043221 )
                return "JET_wrnFileOpenReadOnly";
              v22 = a1 - 241042943;
              if ( !v22 )
                return "JET_wrnColumnPresent";
              v23 = v22 - 1;
              if ( !v23 )
                return "JET_wrnColumnSingleValue";
              v24 = v23 - 1;
              if ( !v24 )
                return "JET_wrnColumnDefault";
              v25 = v24 - 73;
              if ( !v25 )
                return "JET_wrnDataHasChanged";
              if ( v25 == 8 )
                return "JET_wrnKeyChanged";
            }
          }
          else
          {
            if ( a1 == 241042942 )
              return "JET_wrnColumnTruncated";
            if ( a1 > 241042920 )
            {
              v19 = a1 - 241042928;
              if ( !v19 )
                return "JET_wrnCopyLongValue";
              v20 = v19 - 11;
              if ( !v20 )
                return "JET_wrnColumnSkipped";
              v21 = v20 - 1;
              if ( !v21 )
                return "JET_wrnColumnNotLocal";
              if ( v21 == 1 )
                return "JET_wrnColumnMoreTags";
            }
            else
            {
              if ( a1 == 241042920 )
                return "JET_wrnColumnMaxTruncated";
              v15 = a1 - 241042475;
              if ( !v15 )
                return "JET_wrnNoWriteLock";
              v16 = v15 - 1;
              if ( !v16 )
                return "JET_wrnColumnSetNull";
              v17 = v16 - 233;
              if ( !v17 )
                return "JET_wrnTableEmpty";
              v18 = v17 - 26;
              if ( !v18 )
                return "JET_wrnTableInUseBySystem";
              if ( v18 == 88 )
                return "JET_wrnCorruptIndexDeleted";
            }
          }
        }
        else
        {
          if ( a1 == 241042466 )
            return "JET_wrnNoIdleActivity";
          if ( a1 > 241041972 )
          {
            if ( a1 > 241042414 )
            {
              v12 = a1 - 241042415;
              if ( !v12 )
                return "JET_wrnDatabaseAttached";
              v13 = v12 - 2;
              if ( !v13 )
                return "JET_wrnSortOverflow";
              v14 = v13 - 30;
              if ( !v14 )
                return "JET_wrnSeekNotEqual";
              if ( v14 == 16 )
                return "JET_wrnNoErrorInfo";
            }
            else
            {
              if ( a1 == 241042414 )
                return "JET_wrnBufferTruncated";
              v8 = a1 - 241041986;
              if ( !v8 )
                return "JET_wrnTargetInstanceRunning";
              v9 = v8 - 7;
              if ( !v9 )
                return "JET_wrnCommittedLogFilesLost";
              v10 = v9 - 2;
              if ( !v10 )
                return "JET_wrnCommittedLogFilesRemoved";
              v11 = v10 - 8;
              if ( !v11 )
                return "JET_wrnDatabaseRepaired";
              if ( v11 == 409 )
                return "JET_wrnColumnNull";
            }
          }
          else
          {
            if ( a1 == 241041972 )
              return "JET_wrnSkipThisRecord";
            if ( a1 <= 241041507 )
            {
              switch ( a1 )
              {
                case 241041507:
                  return "JET_errIndexTuplesTextColumnsOnly";
                case -1906438236:
                  return "JET_errFileIOFail";
                case -1906438235:
                  return "JET_errFileCompressed";
                case 0:
                  return "JET_errSuccess";
                case 241041489:
                  return "JET_errDatabaseInconsistent";
              }
              v1 = "JET_errIndexTuplesOneColumnOnly";
              v2 = a1 == 241041498;
              goto LABEL_514;
            }
            v4 = a1 - 241041729;
            if ( !v4 )
              return "JET_wrnRemainingVersions";
            v5 = v4 - 24;
            if ( !v5 )
              return "JET_wrnUniqueKey";
            v6 = v5 - 61;
            if ( !v6 )
              return "JET_wrnSeparateLongValue";
            v7 = v6 - 152;
            if ( !v7 )
              return "JET_wrnExistingLogFileHasBadSignature";
            if ( v7 == 1 )
              return "JET_wrnExistingLogFileIsNotContiguous";
          }
        }
        return "Unknown Error";
      }
      if ( a1 == -1906438237 )
        return "JET_errFileIORetry";
      if ( a1 > -1906440333 )
      {
        if ( a1 > -1906440137 )
        {
          if ( a1 > -1906439239 )
          {
            switch ( a1 )
            {
              case -1906439238:
                return "JET_errLSNotSet";
              case -1906438240:
                return "JET_errFileIOSparse";
              case -1906438239:
                return "JET_errFileIOBeyondEOF";
            }
            v1 = "JET_errFileIOAbort";
            v2 = a1 == -1906438238;
          }
          else
          {
            switch ( a1 )
            {
              case -1906439239:
                return "JET_errLSAlreadySet";
              case -1906439839:
                return "JET_errOSSnapshotInvalidSequence";
              case -1906439838:
                return "JET_errOSSnapshotTimeOut";
              case -1906439837:
                return "JET_errOSSnapshotNotAllowed";
              case -1906439836:
                return "JET_errOSSnapshotInvalidSnapId";
            }
            v1 = "JET_errLSCallbackNotSpecified";
            v2 = a1 == -1906439240;
          }
        }
        else
        {
          if ( a1 == -1906440137 )
            return "JET_errSpaceHintsInvalid";
          if ( a1 > -1906440326 )
          {
            switch ( a1 )
            {
              case -1906440325:
                return "JET_errRecordFormatConversionFailed";
              case -1906440324:
                return "JET_errOneDatabasePerSession";
              case -1906440323:
                return "JET_errRollbackError";
              case -1906440139:
                return "JET_errCallbackFailed";
            }
            v1 = "JET_errCallbackNotResolved";
            v2 = a1 == -1906440138;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440326:
                return "JET_errSessionInUse";
              case -1906440331:
                return "JET_errTooManySplits";
              case -1906440330:
                return "JET_errSessionSharingViolation";
              case -1906440329:
                return "JET_errEntryPointNotFound";
              case -1906440328:
                return "JET_errSessionContextAlreadySet";
            }
            v1 = "JET_errSessionContextNotSetByThisThread";
            v2 = a1 == -1906440327;
          }
        }
      }
      else
      {
        if ( a1 == -1906440333 )
          return "JET_errAccessDenied";
        if ( a1 > -1906440539 )
        {
          if ( a1 > -1906440429 )
          {
            switch ( a1 )
            {
              case -1906440428:
                return "JET_errFileInvalidType";
              case -1906440390:
                return "JET_errAfterInitialization";
              case -1906440388:
                return "JET_errLogCorrupted";
            }
            v1 = "JET_errInvalidOperation";
            v2 = a1 == -1906440334;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440429:
                return "JET_errFileNotFound";
              case -1906440538:
                return "JET_errInvalidOnSort";
              case -1906440437:
                return "JET_errTempFileOpenError";
              case -1906440435:
                return "JET_errTooManyAttachedDatabases";
              case -1906440432:
                return "JET_errDiskFull";
            }
            v1 = "JET_errPermissionDenied";
            v2 = a1 == -1906440431;
          }
        }
        else
        {
          if ( a1 == -1906440539 )
            return "JET_errTooManySorts";
          if ( a1 > -1906440635 )
          {
            switch ( a1 )
            {
              case -1906440633:
                return "JET_errAlreadyPrepared";
              case -1906440632:
                return "JET_errKeyNotMade";
              case -1906440631:
                return "JET_errUpdateNotPrepared";
              case -1906440629:
                return "JET_errDataHasChanged";
            }
            v1 = "JET_errLanguageNotSupported";
            v2 = a1 == -1906440621;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440635:
                return "JET_errKeyDuplicate";
              case -1906440710:
                return "JET_errInvalidPlaceholderColumn";
              case -1906440639:
                return "JET_errRecordNotFound";
              case -1906440638:
                return "JET_errRecordNoCopy";
              case -1906440637:
                return "JET_errNoCurrentRecord";
            }
            v1 = "JET_errRecordPrimaryChanged";
            v2 = a1 == -1906440636;
          }
        }
      }
LABEL_514:
      result = "Unknown Error";
      if ( v2 )
        return v1;
      return result;
    }
    if ( a1 == -1906440711 )
      return "JET_errDerivedColumnCorruption";
    if ( a1 > -1906440912 )
    {
      if ( a1 <= -1906440803 )
      {
        if ( a1 == -1906440803 )
          return "JET_errIndexTuplesKeyTooSmall";
        if ( a1 > -1906440828 )
        {
          if ( a1 > -1906440808 )
          {
            switch ( a1 )
            {
              case -1906440807:
                return "JET_errIndexTuplesTextBinaryColumnsOnly";
              case -1906440806:
                return "JET_errIndexTuplesVarSegMacNotAllowed";
              case -1906440805:
                return "JET_errIndexTuplesInvalidLimits";
            }
            v1 = "JET_errIndexTuplesCannotRetrieveFromIndex";
            v2 = a1 == -1906440804;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440808:
                return "JET_errIndexTuplesNonUniqueOnly";
              case -1906440827:
                return "JET_errPrimaryIndexCorrupted";
              case -1906440826:
                return "JET_errSecondaryIndexCorrupted";
              case -1906440824:
                return "JET_errInvalidIndexId";
              case -1906440810:
                return "JET_errIndexTuplesSecondaryIndexOnly";
            }
            v1 = "JET_errIndexTuplesTooManyColumns";
            v2 = a1 == -1906440809;
          }
        }
        else
        {
          if ( a1 == -1906440828 )
            return "JET_errIndexBuildCorrupted";
          if ( a1 > -1906440836 )
          {
            switch ( a1 )
            {
              case -1906440835:
                return "JET_errIndexMustStay";
              case -1906440834:
                return "JET_errIndexInvalidDef";
              case -1906440831:
                return "JET_errInvalidCreateIndex";
              case -1906440830:
                return "JET_errTooManyOpenIndexes";
            }
            v1 = "JET_errMultiValuedIndexViolation";
            v2 = a1 == -1906440829;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440836:
                return "JET_errIndexNotFound";
              case -1906440911:
                return "JET_errClientRequestToStopJetService";
              case -1906440910:
                return "JET_errCannotAddFixedVarColumnToDerivedTable";
              case -1906440839:
                return "JET_errIndexCantBuild";
              case -1906440838:
                return "JET_errIndexHasPrimary";
            }
            v1 = "JET_errIndexDuplicate";
            v2 = a1 == -1906440837;
          }
        }
        goto LABEL_514;
      }
      switch ( a1 )
      {
        case -1906440739:
          result = "JET_errColumnLong";
          break;
        case -1906440738:
          result = "JET_errColumnNoChunk";
          break;
        case -1906440737:
          result = "JET_errColumnDoesNotFit";
          break;
        case -1906440736:
          result = "JET_errNullInvalid";
          break;
        case -1906440735:
          result = "JET_errColumnIndexed";
          break;
        case -1906440734:
          result = "JET_errColumnTooBig";
          break;
        case -1906440733:
          result = "JET_errColumnNotFound";
          break;
        case -1906440732:
          result = "JET_errColumnDuplicate";
          break;
        case -1906440731:
          result = "JET_errMultiValuedColumnMustBeTagged";
          break;
        case -1906440730:
          result = "JET_errColumnRedundant";
          break;
        case -1906440729:
          result = "JET_errInvalidColumnType";
          break;
        case -1906440726:
          result = "JET_errTaggedNotNULL";
          break;
        case -1906440725:
          result = "JET_errNoCurrentIndex";
          break;
        case -1906440724:
          result = "JET_errKeyIsMade";
          break;
        case -1906440723:
          result = "JET_errBadColumnId";
          break;
        case -1906440722:
          result = "JET_errBadItagSequence";
          break;
        case -1906440721:
          result = "JET_errColumnInRelationship";
          break;
        case -1906440719:
          result = "JET_errCannotBeTagged";
          break;
        case -1906440716:
          result = "JET_errDefaultValueTooBig";
          break;
        case -1906440715:
          result = "JET_errMultiValuedDuplicate";
          break;
        case -1906440714:
          result = "JET_errLVCorrupted";
          break;
        case -1906440712:
          result = "JET_errMultiValuedDuplicateAfterTruncation";
          break;
        default:
          return "Unknown Error";
      }
    }
    else
    {
      if ( a1 == -1906440912 )
        return "JET_errInvalidSettings";
      if ( a1 > -1906441018 )
      {
        if ( a1 > -1906440927 )
        {
          if ( a1 > -1906440918 )
          {
            switch ( a1 )
            {
              case -1906440917:
                return "JET_errFixedDDL";
              case -1906440916:
                return "JET_errFixedInheritedDDL";
              case -1906440915:
                return "JET_errCannotNestDDL";
            }
            v1 = "JET_errDDLNotInheritable";
            v2 = a1 == -1906440914;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440918:
                return "JET_errExclusiveTableLockRequired";
              case -1906440926:
                return "JET_errObjectDuplicate";
              case -1906440924:
                return "JET_errInvalidObject";
              case -1906440923:
                return "JET_errCannotDeleteTempTable";
              case -1906440922:
                return "JET_errCannotDeleteSystemTable";
            }
            v1 = "JET_errCannotDeleteTemplateTable";
            v2 = a1 == -1906440921;
          }
        }
        else
        {
          if ( a1 == -1906440927 )
            return "JET_errTooManyOpenTablesAndCleanupTimedOut";
          if ( a1 > -1906440935 )
          {
            switch ( a1 )
            {
              case -1906440933:
                return "JET_errDensityInvalid";
              case -1906440932:
                return "JET_errTableNotEmpty";
              case -1906440930:
                return "JET_errInvalidTableId";
              case -1906440929:
                return "JET_errTooManyOpenTables";
            }
            v1 = "JET_errIllegalOperation";
            v2 = a1 == -1906440928;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440935:
                return "JET_errObjectNotFound";
              case -1906441016:
                return "JET_errDatabaseCorruptedNoRepair";
              case -1906441015:
                return "JET_errInvalidCreateDbVersion";
              case -1906440938:
                return "JET_errTableLocked";
              case -1906440937:
                return "JET_errTableDuplicate";
            }
            v1 = "JET_errTableInUse";
            v2 = a1 == -1906440936;
          }
        }
        goto LABEL_514;
      }
      if ( a1 == -1906441018 )
        return "JET_errDatabaseSignInUse";
      if ( a1 <= -1906441029 )
      {
        if ( a1 == -1906441029 )
          return "JET_errDatabase400Format";
        if ( a1 > -1906441035 )
        {
          switch ( a1 )
          {
            case -1906441034:
              return "JET_errDatabaseCorrupted";
            case -1906441033:
              return "JET_errDatabaseLocked";
            case -1906441032:
              return "JET_errCannotDisableVersioning";
            case -1906441031:
              return "JET_errInvalidDatabaseVersion";
          }
          v1 = "JET_errDatabase200Format";
          v2 = a1 == -1906441030;
        }
        else
        {
          switch ( a1 )
          {
            case -1906441035:
              return "JET_errDatabaseInvalidPages";
            case -1906441124:
              return "JET_errDirtyShutdown";
            case -1906441039:
              return "JET_errDatabaseDuplicate";
            case -1906441038:
              return "JET_errDatabaseInUse";
            case -1906441037:
              return "JET_errDatabaseNotFound";
          }
          v1 = "JET_errDatabaseInvalidName";
          v2 = a1 == -1906441036;
        }
        goto LABEL_514;
      }
      switch ( a1 )
      {
        case -1906441028:
          result = "JET_errDatabase500Format";
          break;
        case -1906441027:
          result = "JET_errPageSizeMismatch";
          break;
        case -1906441026:
          result = "JET_errTooManyInstances";
          break;
        case -1906441025:
          result = "JET_errDatabaseSharingViolation";
          break;
        case -1906441024:
          result = "JET_errAttachedDatabaseMismatch";
          break;
        case -1906441023:
          result = "JET_errDatabaseInvalidPath";
          break;
        case -1906441022:
          result = "JET_errDatabaseIdInUse";
          break;
        case -1906441021:
          result = "JET_errForceDetachNotAllowed";
          break;
        case -1906441020:
          result = "JET_errCatalogCorrupted";
          break;
        case -1906441019:
          result = "JET_errPartiallyAttachedDB";
          break;
        default:
          return "Unknown Error";
      }
    }
  }
  else
  {
    if ( a1 == -1906441125 )
      return "JET_errInvalidInstance";
    if ( a1 > -1906441660 )
    {
      if ( a1 > -1906441195 )
      {
        switch ( a1 )
        {
          case -1906441194:
            result = "JET_errColumnInUse";
            break;
          case -1906441193:
            result = "JET_errInvalidBufferSize";
            break;
          case -1906441192:
            result = "JET_errColumnNotUpdatable";
            break;
          case -1906441189:
            result = "JET_errIndexInUse";
            break;
          case -1906441188:
            result = "JET_errLinkNotSupported";
            break;
          case -1906441187:
            result = "JET_errNullKeyDisallowed";
            break;
          case -1906441186:
            result = "JET_errNotInTransaction";
            break;
          case -1906441181:
            result = "JET_errTooManyActiveUsers";
            break;
          case -1906441179:
            result = "JET_errInvalidCountry";
            break;
          case -1906441178:
            result = "JET_errInvalidLanguageId";
            break;
          case -1906441177:
            result = "JET_errInvalidCodePage";
            break;
          case -1906441176:
            result = "JET_errInvalidLCMapStringFlags";
            break;
          case -1906441175:
            result = "JET_errVersionStoreEntryTooBig";
            break;
          case -1906441174:
            result = "JET_errVersionStoreOutOfMemoryAndCleanupTimedOut";
            break;
          case -1906441171:
            result = "JET_errVersionStoreOutOfMemory";
            break;
          case -1906441169:
            result = "JET_errCannotIndex";
            break;
          case -1906441168:
            result = "JET_errRecordNotDeleted";
            break;
          case -1906441167:
            result = "JET_errTooManyMempoolEntries";
            break;
          case -1906441166:
            result = "JET_errOutOfObjectIDs";
            break;
          case -1906441165:
            result = "JET_errOutOfLongValueIDs";
            break;
          case -1906441164:
            result = "JET_errOutOfAutoincrementValues";
            break;
          case -1906441163:
            result = "JET_errOutOfDbtimeValues";
            break;
          case -1906441162:
            result = "JET_errOutOfSequentialIndexValues";
            break;
          case -1906441160:
            result = "JET_errRunningInOneInstanceMode";
            break;
          case -1906441159:
            result = "JET_errRunningInMultiInstanceMode";
            break;
          case -1906441158:
            result = "JET_errSystemParamsAlreadySet";
            break;
          case -1906441157:
            result = "JET_errSystemPathInUse";
            break;
          case -1906441156:
            result = "JET_errLogFilePathInUse";
            break;
          case -1906441155:
            result = "JET_errTempPathInUse";
            break;
          case -1906441154:
            result = "JET_errInstanceNameInUse";
            break;
          case -1906441150:
            result = "JET_errInstanceUnavailable";
            break;
          case -1906441149:
            result = "JET_errDatabaseUnavailable";
            break;
          case -1906441148:
            result = "JET_errInstanceUnavailableDueToFatalLogDiskFull";
            break;
          case -1906441139:
            result = "JET_errOutOfSessions";
            break;
          case -1906441138:
            result = "JET_errWriteConflict";
            break;
          case -1906441137:
            result = "JET_errTransTooDeep";
            break;
          case -1906441136:
            result = "JET_errInvalidSesid";
            break;
          case -1906441135:
            result = "JET_errWriteConflictPrimaryIndex";
            break;
          case -1906441132:
            result = "JET_errInTransaction";
            break;
          case -1906441131:
            result = "JET_errRollbackRequired";
            break;
          case -1906441130:
            result = "JET_errTransReadOnly";
            break;
          case -1906441129:
            result = "JET_errSessionWriteConflict";
            break;
          case -1906441128:
            result = "JET_errRecordTooBigForBackwardCompatibility";
            break;
          case -1906441127:
            result = "JET_errCannotMaterializeForwardOnlySort";
            break;
          case -1906441126:
            result = "JET_errSesidTableIdMismatch";
            break;
          default:
            return "Unknown Error";
        }
      }
      else
      {
        if ( a1 == -1906441195 )
          return "JET_errInvalidBookmark";
        if ( a1 <= -1906441227 )
        {
          if ( a1 == -1906441227 )
            return "JET_errOutOfCursors";
          if ( a1 > -1906441626 )
          {
            if ( a1 > -1906441238 )
            {
              switch ( a1 )
              {
                case -1906441237:
                  return "JET_errInvalidParameter";
                case -1906441232:
                  return "JET_errDatabaseFileReadOnly";
                case -1906441230:
                  return "JET_errInvalidDatabaseId";
              }
              v1 = "JET_errOutOfDatabaseSpace";
              v2 = a1 == -1906441228;
            }
            else
            {
              switch ( a1 )
              {
                case -1906441238:
                  return "JET_errInvalidName";
                case -1906441625:
                  return "JET_errRestoreOfNonBackupDatabase";
                case -1906441624:
                  return "JET_errLogFileNotCopied";
                case -1906441340:
                  return "JET_errInvalidGrbit";
                case -1906441240:
                  return "JET_errTermInProgress";
              }
              v1 = "JET_errFeatureNotAvailable";
              v2 = a1 == -1906441239;
            }
          }
          else
          {
            if ( a1 == -1906441626 )
              return "JET_errCheckpointDepthTooDeep";
            if ( a1 > -1906441639 )
            {
              switch ( a1 )
              {
                case -1906441638:
                  return "JET_errUnicodeTranslationFail";
                case -1906441637:
                  return "JET_errUnicodeNormalizationNotSupported";
                case -1906441630:
                  return "JET_errExistingLogFileHasBadSignature";
                case -1906441629:
                  return "JET_errExistingLogFileIsNotContiguous";
              }
              v1 = "JET_errLogReadVerifyFailure";
              v2 = a1 == -1906441628;
            }
            else
            {
              switch ( a1 )
              {
                case -1906441639:
                  return "JET_errUnicodeTranslationBufferTooSmall";
                case -1906441659:
                  return "JET_errSoftRecoveryOnSnapshot";
                case -1906441658:
                  return "JET_errCommittedLogFilesMissing";
                case -1906441657:
                  return "JET_errSectorSizeNotSupported";
                case -1906441656:
                  return "JET_errRecoveredWithoutUndoDatabasesConsistent";
              }
              v1 = "JET_errCommittedLogFileCorrupt";
              v2 = a1 == -1906441654;
            }
          }
          goto LABEL_514;
        }
        switch ( a1 )
        {
          case -1906441226:
            result = "JET_errOutOfBuffers";
            break;
          case -1906441225:
            result = "JET_errTooManyIndexes";
            break;
          case -1906441224:
            result = "JET_errTooManyKeys";
            break;
          case -1906441223:
            result = "JET_errRecordDeleted";
            break;
          case -1906441222:
            result = "JET_errReadVerifyFailure";
            break;
          case -1906441221:
            result = "JET_errPageNotInitialized";
            break;
          case -1906441220:
            result = "JET_errOutOfFileHandles";
            break;
          case -1906441218:
            result = "JET_errDiskIO";
            break;
          case -1906441217:
            result = "JET_errInvalidPath";
            break;
          case -1906441216:
            result = "JET_errInvalidSystemPath";
            break;
          case -1906441215:
            result = "JET_errInvalidLogDirectory";
            break;
          case -1906441214:
            result = "JET_errRecordTooBig";
            break;
          case -1906441213:
            result = "JET_errTooManyOpenDatabases";
            break;
          case -1906441212:
            result = "JET_errInvalidDatabase";
            break;
          case -1906441211:
            result = "JET_errNotInitialized";
            break;
          case -1906441210:
            result = "JET_errAlreadyInitialized";
            break;
          case -1906441209:
            result = "JET_errInitInProgress";
            break;
          case -1906441208:
            result = "JET_errFileAccessDenied";
            break;
          case -1906441202:
            result = "JET_errBufferTooSmall";
            break;
          case -1906441200:
            result = "JET_errTooManyColumns";
            break;
          case -1906441197:
            result = "JET_errContainerNotEmpty";
            break;
          case -1906441196:
            result = "JET_errInvalidFilename";
            break;
          default:
            return "Unknown Error";
        }
      }
    }
    else
    {
      if ( a1 == -1906441660 )
        return "JET_errDatabasesNotFromSameSnapshot";
      if ( a1 > -1906441714 )
      {
        switch ( a1 )
        {
          case -1906441713:
            result = "JET_errRecoveredWithErrors";
            break;
          case -1906441712:
            result = "JET_errMissingLogFile";
            break;
          case -1906441711:
            result = "JET_errLogDiskFull";
            break;
          case -1906441710:
            result = "JET_errBadLogSignature";
            break;
          case -1906441709:
            result = "JET_errBadDbSignature";
            break;
          case -1906441708:
            result = "JET_errBadCheckpointSignature";
            break;
          case -1906441707:
            result = "JET_errCheckpointCorrupt";
            break;
          case -1906441706:
            result = "JET_errMissingPatchPage";
            break;
          case -1906441705:
            result = "JET_errBadPatchPage";
            break;
          case -1906441704:
            result = "JET_errRedoAbruptEnded";
            break;
          case -1906441702:
            result = "JET_errPatchFileMissing";
            break;
          case -1906441701:
            result = "JET_errDatabaseLogSetMismatch";
            break;
          case -1906441700:
            result = "JET_errDatabaseStreamingFileMismatch";
            break;
          case -1906441699:
            result = "JET_errLogFileSizeMismatch";
            break;
          case -1906441698:
            result = "JET_errCheckpointFileNotFound";
            break;
          case -1906441697:
            result = "JET_errRequiredLogFilesMissing";
            break;
          case -1906441696:
            result = "JET_errSoftRecoveryOnBackupDatabase";
            break;
          case -1906441695:
            result = "JET_errLogFileSizeMismatchDatabasesConsistent";
            break;
          case -1906441694:
            result = "JET_errLogSectorSizeMismatch";
            break;
          case -1906441693:
            result = "JET_errLogSectorSizeMismatchDatabasesConsistent";
            break;
          case -1906441692:
            result = "JET_errLogSequenceEndDatabasesConsistent";
            break;
          case -1906441691:
            result = "JET_errStreamingDataNotLogged";
            break;
          case -1906441690:
            result = "JET_errDatabaseDirtyShutdown";
            break;
          case -1906441689:
            result = "JET_errConsistentTimeMismatch";
            break;
          case -1906441688:
            result = "JET_errDatabasePatchFileMismatch";
            break;
          case -1906441687:
            result = "JET_errEndingRestoreLogTooLow";
            break;
          case -1906441686:
            result = "JET_errStartingRestoreLogTooHigh";
            break;
          case -1906441685:
            result = "JET_errGivenLogFileHasBadSignature";
            break;
          case -1906441684:
            result = "JET_errGivenLogFileIsNotContiguous";
            break;
          case -1906441683:
            result = "JET_errMissingRestoreLogFiles";
            break;
          case -1906441680:
            result = "JET_errMissingFullBackup";
            break;
          case -1906441679:
            result = "JET_errBadBackupDatabaseSize";
            break;
          case -1906441678:
            result = "JET_errDatabaseAlreadyUpgraded";
            break;
          case -1906441677:
            result = "JET_errDatabaseIncompleteUpgrade";
            break;
          case -1906441675:
            result = "JET_errMissingCurrentLogFiles";
            break;
          case -1906441674:
            result = "JET_errDbTimeTooOld";
            break;
          case -1906441673:
            result = "JET_errDbTimeTooNew";
            break;
          case -1906441671:
            result = "JET_errMissingFileToBackup";
            break;
          case -1906441670:
            result = "JET_errLogTornWriteDuringHardRestore";
            break;
          case -1906441669:
            result = "JET_errLogTornWriteDuringHardRecovery";
            break;
          case -1906441667:
            result = "JET_errLogCorruptDuringHardRestore";
            break;
          case -1906441666:
            result = "JET_errLogCorruptDuringHardRecovery";
            break;
          case -1906441665:
            result = "JET_errMustDisableLoggingForDbUpgrade";
            break;
          case -1906441663:
            result = "JET_errBadRestoreTargetInstance";
            break;
          case -1906441661:
            result = "JET_errRecoveredWithoutUndo";
            break;
          default:
            return "Unknown Error";
        }
      }
      else
      {
        if ( a1 == -1906441714 )
          return "JET_errInvalidBackup";
        if ( a1 <= -1906441894 )
        {
          if ( a1 == -1906441894 )
            return "JET_errKeyTruncated";
          if ( a1 > -1906441917 )
          {
            if ( a1 > -1906441900 )
            {
              switch ( a1 )
              {
                case -1906441899:
                  return "JET_errSPAvailExtCorrupted";
                case -1906441898:
                  return "JET_errSPAvailExtCacheOutOfMemory";
                case -1906441897:
                  return "JET_errSPOwnExtCorrupted";
              }
              v1 = "JET_errDbTimeCorrupted";
              v2 = a1 == -1906441896;
            }
            else
            {
              switch ( a1 )
              {
                case -1906441900:
                  return "JET_errSPAvailExtCacheOutOfSync";
                case -1906441916:
                  return "JET_errKeyBoundary";
                case -1906441913:
                  return "JET_errBadPageLink";
                case -1906441912:
                  return "JET_errBadBookmark";
                case -1906441906:
                  return "JET_errNTSystemCallFailed";
              }
              v1 = "JET_errBadParentPageLink";
              v2 = a1 == -1906441902;
            }
          }
          else
          {
            if ( a1 == -1906441917 )
              return "JET_errPageBoundary";
            if ( a1 > -1906442137 )
            {
              switch ( a1 )
              {
                case -1906442135:
                  return "JET_errTooManyIO";
                case -1906442134:
                  return "JET_errTaskDropped";
                case -1906442133:
                  return "JET_errInternalError";
                case -1906441985:
                  return "JET_errDatabaseBufferDependenciesCorrupted";
              }
              v1 = "JET_errPreviousVersion";
              v2 = a1 == -1906441918;
            }
            else
            {
              switch ( a1 )
              {
                case -1906442137:
                  return "JET_errOutOfThreads";
                case -2147024882:
                  return "JET_errOutOfMemory";
                case -1906442239:
                  return "JET_wrnNyi";
                case -1906442140:
                  return "JET_errRfsFailure";
                case -1906442139:
                  return "JET_errRfsNotArmed";
              }
              v1 = "JET_errFileClose";
              v2 = a1 == -1906442138;
            }
          }
          goto LABEL_514;
        }
        if ( a1 <= -1906441727 )
        {
          if ( a1 == -1906441727 )
            return "JET_errLogGenerationMismatch";
          if ( a1 > -1906441735 )
          {
            switch ( a1 )
            {
              case -1906441734:
                return "JET_errRestoreInProgress";
              case -1906441731:
                return "JET_errMissingPreviousLogFile";
              case -1906441730:
                return "JET_errLogWriteFail";
              case -1906441729:
                return "JET_errLogDisabledDueToRecoveryFailure";
            }
            v1 = "JET_errCannotLogDuringRecoveryRedo";
            v2 = a1 == -1906441728;
          }
          else
          {
            switch ( a1 )
            {
              case -1906441735:
                return "JET_errBackupInProgress";
              case -1906441832:
                return "JET_errKeyTooBig";
              case -1906441740:
                return "JET_errInvalidLoggedOperation";
              case -1906441739:
                return "JET_errLogFileCorrupt";
              case -1906441737:
                return "JET_errNoBackupDirectory";
            }
            v1 = "JET_errBackupDirectoryNotEmpty";
            v2 = a1 == -1906441736;
          }
          goto LABEL_514;
        }
        switch ( a1 )
        {
          case -1906441726:
            result = "JET_errBadLogVersion";
            break;
          case -1906441725:
            result = "JET_errInvalidLogSequence";
            break;
          case -1906441724:
            result = "JET_errLoggingDisabled";
            break;
          case -1906441723:
            result = "JET_errLogBufferTooSmall";
            break;
          case -1906441721:
            result = "JET_errLogSequenceEnd";
            break;
          case -1906441720:
            result = "JET_errNoBackup";
            break;
          case -1906441719:
            result = "JET_errInvalidBackupSequence";
            break;
          case -1906441717:
            result = "JET_errBackupNotAllowedYet";
            break;
          case -1906441716:
            result = "JET_errDeleteBackupFileFail";
            break;
          case -1906441715:
            result = "JET_errMakeBackupDirectoryFail";
            break;
          default:
            return "Unknown Error";
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18011031c  mov     eax, 8E5E045Bh
0x180110321  cmp     ecx, eax
0x180110323  jg      loc_180110CAC
0x180110329  jz      loc_180110CA3
0x18011032f  mov     eax, 8E5E0244h
0x180110334  cmp     ecx, eax
0x180110336  jg      loc_18011082B
0x18011033c  jz      loc_180110822
0x180110342  mov     eax, 8E5E020Eh
0x180110347  cmp     ecx, eax
0x180110349  jg      loc_180110664
0x18011034f  jz      loc_18011065B
0x180110355  mov     eax, 8E5E015Ah
0x18011035a  cmp     ecx, eax
0x18011035c  jg      loc_1801104FC
0x180110362  jz      loc_1801104F3
0x180110368  mov     eax, 8E5E0143h
0x18011036d  cmp     ecx, eax
0x18011036f  jg      loc_180110444
0x180110375  jz      loc_18011043B
0x18011037b  mov     eax, 8E5E0067h
0x180110380  cmp     ecx, eax
0x180110382  jg      short loc_1801103E5
0x180110384  jz      short loc_1801103DC
0x180110386  cmp     ecx, 8007000Eh
0x18011038c  jz      short loc_1801103D3
0x18011038e  cmp     ecx, 8E5E0001h
0x180110394  jz      short loc_1801103CA
0x180110396  cmp     ecx, 8E5E0064h
0x18011039c  jz      short loc_1801103C1
0x18011039e  cmp     ecx, 8E5E0065h
0x1801103a4  jz      short loc_1801103B8
0x1801103a6  lea     rdx, aJetErrfileclos; "JET_errFileClose"
0x1801103ad  cmp     ecx, 8E5E0066h
0x1801103b3  jmp     loc_180111625
0x1801103b8  lea     rax, aJetErrrfsnotar; "JET_errRfsNotArmed"
0x1801103bf  retn
0x1801103c1  lea     rax, aJetErrrfsfailu; "JET_errRfsFailure"
0x1801103c8  retn
0x1801103ca  lea     rax, aJetWrnnyi; "JET_wrnNyi"
0x1801103d1  retn
0x1801103d3  lea     rax, aJetErroutofmem; "JET_errOutOfMemory"
0x1801103da  retn
0x1801103dc  lea     rax, aJetErroutofthr; "JET_errOutOfThreads"
0x1801103e3  retn
0x1801103e5  cmp     ecx, 8E5E0069h
0x1801103eb  jz      short loc_180110432
0x1801103ed  cmp     ecx, 8E5E006Ah
0x1801103f3  jz      short loc_180110429
0x1801103f5  cmp     ecx, 8E5E006Bh
0x1801103fb  jz      short loc_180110420
0x1801103fd  cmp     ecx, 8E5E00FFh
0x180110403  jz      short loc_180110417
0x180110405  lea     rdx, aJetErrprevious; "JET_errPreviousVersion"
0x18011040c  cmp     ecx, 8E5E0142h
0x180110412  jmp     loc_180111625
0x180110417  lea     rax, aJetErrdatabase_13; "JET_errDatabaseBufferDependenciesCorrup"...
0x18011041e  retn
0x180110420  lea     rax, aJetErrinternal; "JET_errInternalError"
0x180110427  retn
0x180110429  lea     rax, aJetErrtaskdrop; "JET_errTaskDropped"
0x180110430  retn
0x180110432  lea     rax, aJetErrtoomanyi; "JET_errTooManyIO"
0x180110439  retn
0x18011043b  lea     rax, aJetErrpageboun; "JET_errPageBoundary"
0x180110442  retn
0x180110444  mov     eax, 8E5E0154h
0x180110449  cmp     ecx, eax
0x18011044b  jg      short loc_1801104AE
0x18011044d  jz      short loc_1801104A5
0x18011044f  cmp     ecx, 8E5E0144h
0x180110455  jz      short loc_18011049C
0x180110457  cmp     ecx, 8E5E0147h
0x18011045d  jz      short loc_180110493
0x18011045f  cmp     ecx, 8E5E0148h
0x180110465  jz      short loc_18011048A
0x180110467  cmp     ecx, 8E5E014Eh
0x18011046d  jz      short loc_180110481
0x18011046f  lea     rdx, aJetErrbadparen; "JET_errBadParentPageLink"
0x180110476  cmp     ecx, 8E5E0152h
0x18011047c  jmp     loc_180111625
0x180110481  lea     rax, aJetErrntsystem; "JET_errNTSystemCallFailed"
0x180110488  retn
0x18011048a  lea     rax, aJetErrbadbookm; "JET_errBadBookmark"
0x180110491  retn
0x180110493  lea     rax, aJetErrbadpagel; "JET_errBadPageLink"
0x18011049a  retn
0x18011049c  lea     rax, aJetErrkeybound; "JET_errKeyBoundary"
0x1801104a3  retn
0x1801104a5  lea     rax, aJetErrspavaile_1; "JET_errSPAvailExtCacheOutOfSync"
0x1801104ac  retn
0x1801104ae  cmp     ecx, 8E5E0155h
0x1801104b4  jz      short loc_1801104EA
0x1801104b6  cmp     ecx, 8E5E0156h
0x1801104bc  jz      short loc_1801104E1
0x1801104be  cmp     ecx, 8E5E0157h
0x1801104c4  jz      short loc_1801104D8
0x1801104c6  lea     rdx, aJetErrdbtimeco; "JET_errDbTimeCorrupted"
0x1801104cd  cmp     ecx, 8E5E0158h
0x1801104d3  jmp     loc_180111625
0x1801104d8  lea     rax, aJetErrspownext; "JET_errSPOwnExtCorrupted"
0x1801104df  retn
0x1801104e1  lea     rax, aJetErrspavaile_0; "JET_errSPAvailExtCacheOutOfMemory"
0x1801104e8  retn
0x1801104ea  lea     rax, aJetErrspavaile; "JET_errSPAvailExtCorrupted"
0x1801104f1  retn
0x1801104f3  lea     rax, aJetErrkeytrunc; "JET_errKeyTruncated"
0x1801104fa  retn
0x1801104fc  mov     eax, 8E5E0201h
0x180110501  cmp     ecx, eax
0x180110503  jg      loc_1801105D8
0x180110509  jz      loc_1801105CF
0x18011050f  mov     eax, 8E5E01F9h
0x180110514  cmp     ecx, eax
0x180110516  jg      short loc_180110579
0x180110518  jz      short loc_180110570
0x18011051a  cmp     ecx, 8E5E0198h
0x180110520  jz      short loc_180110567
0x180110522  cmp     ecx, 8E5E01F4h
0x180110528  jz      short loc_18011055E
0x18011052a  cmp     ecx, 8E5E01F5h
0x180110530  jz      short loc_180110555
0x180110532  cmp     ecx, 8E5E01F7h
0x180110538  jz      short loc_18011054C
0x18011053a  lea     rdx, aJetErrbackupdi; "JET_errBackupDirectoryNotEmpty"
0x180110541  cmp     ecx, 8E5E01F8h
0x180110547  jmp     loc_180111625
0x18011054c  lea     rax, aJetErrnobackup_0; "JET_errNoBackupDirectory"
0x180110553  retn
0x180110555  lea     rax, aJetErrlogfilec; "JET_errLogFileCorrupt"
0x18011055c  retn
0x18011055e  lea     rax, aJetErrinvalidl_0; "JET_errInvalidLoggedOperation"
0x180110565  retn
0x180110567  lea     rax, aJetErrkeytoobi; "JET_errKeyTooBig"
0x18011056e  retn
0x180110570  lea     rax, aJetErrbackupin; "JET_errBackupInProgress"
0x180110577  retn
0x180110579  cmp     ecx, 8E5E01FAh
0x18011057f  jz      short loc_1801105C6
0x180110581  cmp     ecx, 8E5E01FDh
0x180110587  jz      short loc_1801105BD
0x180110589  cmp     ecx, 8E5E01FEh
0x18011058f  jz      short loc_1801105B4
0x180110591  cmp     ecx, 8E5E01FFh
0x180110597  jz      short loc_1801105AB
0x180110599  lea     rdx, aJetErrcannotlo; "JET_errCannotLogDuringRecoveryRedo"
0x1801105a0  cmp     ecx, 8E5E0200h
0x1801105a6  jmp     loc_180111625
0x1801105ab  lea     rax, aJetErrlogdisab; "JET_errLogDisabledDueToRecoveryFailure"
0x1801105b2  retn
0x1801105b4  lea     rax, aJetErrlogwrite; "JET_errLogWriteFail"
0x1801105bb  retn
0x1801105bd  lea     rax, aJetErrmissingp; "JET_errMissingPreviousLogFile"
0x1801105c4  retn
0x1801105c6  lea     rax, aJetErrrestorei; "JET_errRestoreInProgress"
0x1801105cd  retn
0x1801105cf  lea     rax, aJetErrloggener; "JET_errLogGenerationMismatch"
0x1801105d6  retn
0x1801105d8  add     ecx, 71A1FDFEh; switch 12 cases
0x1801105de  cmp     ecx, 0Bh
0x1801105e1  ja      def_1801105FB; jumptable 00000001801105FB default case, cases -1906441722,-1906441718
0x1801105e7  lea     rdx, __ImageBase
0x1801105ee  movsxd  rax, ecx
0x1801105f1  mov     eax, ds:(jpt_1801105FB - 180000000h)[rdx+rax*4]
0x1801105f8  add     rax, rdx
0x1801105fb  jmp     rax; switch jump
0x180110601  lea     rax, aJetErrbadlogve; jumptable 00000001801105FB case -1906441726
0x180110608  retn
0x18011060a  lea     rax, aJetErrinvalidl; jumptable 00000001801105FB case -1906441725
0x180110611  retn
0x180110613  lea     rax, aJetErrloggingd; jumptable 00000001801105FB case -1906441724
0x18011061a  retn
0x18011061c  lea     rax, aJetErrlogbuffe; jumptable 00000001801105FB case -1906441723
0x180110623  retn
0x180110625  lea     rax, aJetErrlogseque; jumptable 00000001801105FB case -1906441721
0x18011062c  retn
0x18011062e  lea     rax, aJetErrnobackup; jumptable 00000001801105FB case -1906441720
0x180110635  retn
0x180110637  lea     rax, aJetErrinvalidb_1; jumptable 00000001801105FB case -1906441719
0x18011063e  retn
0x180110640  lea     rax, aJetErrbackupno; jumptable 00000001801105FB case -1906441717
0x180110647  retn
0x180110649  lea     rax, aJetErrdeleteba; jumptable 00000001801105FB case -1906441716
0x180110650  retn
0x180110652  lea     rax, aJetErrmakeback; jumptable 00000001801105FB case -1906441715
0x180110659  retn
0x18011065b  lea     rax, aJetErrinvalidb_0; "JET_errInvalidBackup"
0x180110662  retn
0x180110664  add     ecx, 71A1FDF1h; switch 53 cases
0x18011066a  cmp     ecx, 34h
0x18011066d  ja      def_1801105FB; jumptable 00000001801105FB default case, cases -1906441722,-1906441718
0x180110673  lea     rdx, __ImageBase
0x18011067a  movsxd  rax, ecx
0x18011067d  mov     eax, ds:(jpt_180110687 - 180000000h)[rdx+rax*4]
0x180110684  add     rax, rdx
0x180110687  jmp     rax; switch jump
0x18011068d  lea     rax, aJetErrrecovere; jumptable 0000000180110687 case -1906441713
0x180110694  retn
0x180110696  lea     rax, aJetErrmissingl; jumptable 0000000180110687 case -1906441712
0x18011069d  retn
0x18011069f  lea     rax, aJetErrlogdiskf; jumptable 0000000180110687 case -1906441711
0x1801106a6  retn
0x1801106a8  lea     rax, aJetErrbadlogsi; jumptable 0000000180110687 case -1906441710
0x1801106af  retn
0x1801106b1  lea     rax, aJetErrbaddbsig; jumptable 0000000180110687 case -1906441709
0x1801106b8  retn
0x1801106ba  lea     rax, aJetErrbadcheck; jumptable 0000000180110687 case -1906441708
0x1801106c1  retn
0x1801106c3  lea     rax, aJetErrcheckpoi; jumptable 0000000180110687 case -1906441707
0x1801106ca  retn
0x1801106cc  lea     rax, aJetErrmissingp_0; jumptable 0000000180110687 case -1906441706
0x1801106d3  retn
0x1801106d5  lea     rax, aJetErrbadpatch; jumptable 0000000180110687 case -1906441705
0x1801106dc  retn
0x1801106de  lea     rax, aJetErrredoabru; jumptable 0000000180110687 case -1906441704
0x1801106e5  retn
0x1801106e7  lea     rax, aJetErrpatchfil; jumptable 0000000180110687 case -1906441702
0x1801106ee  retn
0x1801106f0  lea     rax, aJetErrdatabase_12; jumptable 0000000180110687 case -1906441701
0x1801106f7  retn
0x1801106f9  lea     rax, aJetErrdatabase_9; jumptable 0000000180110687 case -1906441700
0x180110700  retn
0x180110702  lea     rax, aJetErrlogfiles; jumptable 0000000180110687 case -1906441699
0x180110709  retn
0x18011070b  lea     rax, aJetErrcheckpoi_0; jumptable 0000000180110687 case -1906441698
0x180110712  retn
0x180110714  lea     rax, aJetErrrequired; jumptable 0000000180110687 case -1906441697
0x18011071b  retn
0x18011071d  lea     rax, aJetErrsoftreco_0; jumptable 0000000180110687 case -1906441696
0x180110724  retn
0x180110726  lea     rax, aJetErrlogfiles_0; jumptable 0000000180110687 case -1906441695
0x18011072d  retn
0x18011072f  lea     rax, aJetErrlogsecto_0; jumptable 0000000180110687 case -1906441694
0x180110736  retn
0x180110738  lea     rax, aJetErrlogsecto; jumptable 0000000180110687 case -1906441693
0x18011073f  retn
0x180110741  lea     rax, aJetErrlogseque_0; jumptable 0000000180110687 case -1906441692
0x180110748  retn
0x18011074a  lea     rax, aJetErrstreamin; jumptable 0000000180110687 case -1906441691
0x180110751  retn
0x180110753  lea     rax, aJetErrdatabase_0; jumptable 0000000180110687 case -1906441690
0x18011075a  retn
0x18011075c  lea     rax, aJetErrconsiste; jumptable 0000000180110687 case -1906441689
0x180110763  retn
0x180110765  lea     rax, aJetErrdatabase_6; jumptable 0000000180110687 case -1906441688
0x18011076c  retn
0x18011076e  lea     rax, aJetErrendingre; jumptable 0000000180110687 case -1906441687
0x180110775  retn
0x180110777  lea     rax, aJetErrstarting; jumptable 0000000180110687 case -1906441686
0x18011077e  retn
0x180110780  lea     rax, aJetErrgivenlog; jumptable 0000000180110687 case -1906441685
0x180110787  retn
0x180110789  lea     rax, aJetErrgivenlog_0; jumptable 0000000180110687 case -1906441684
0x180110790  retn
0x180110792  lea     rax, aJetErrmissingr; jumptable 0000000180110687 case -1906441683
0x180110799  retn
0x18011079b  lea     rax, aJetErrmissingf; jumptable 0000000180110687 case -1906441680
0x1801107a2  retn
0x1801107a4  lea     rax, aJetErrbadbacku; jumptable 0000000180110687 case -1906441679
0x1801107ab  retn
0x1801107ad  lea     rax, aJetErrdatabase_24; jumptable 0000000180110687 case -1906441678
0x1801107b4  retn
0x1801107b6  lea     rax, aJetErrdatabase_4; jumptable 0000000180110687 case -1906441677
0x1801107bd  retn
0x1801107bf  lea     rax, aJetErrmissingc; jumptable 0000000180110687 case -1906441675
0x1801107c6  retn
0x1801107c8  lea     rax, aJetErrdbtimeto; jumptable 0000000180110687 case -1906441674
0x1801107cf  retn
0x1801107d1  lea     rax, aJetErrdbtimeto_0; jumptable 0000000180110687 case -1906441673
0x1801107d8  retn
0x1801107da  lea     rax, aJetErrmissingf_0; jumptable 0000000180110687 case -1906441671
0x1801107e1  retn
0x1801107e3  lea     rax, aJetErrlogtornw_0; jumptable 0000000180110687 case -1906441670
0x1801107ea  retn
0x1801107ec  lea     rax, aJetErrlogtornw; jumptable 0000000180110687 case -1906441669
0x1801107f3  retn
0x1801107f5  lea     rax, aJetErrlogcorru_1; jumptable 0000000180110687 case -1906441667
0x1801107fc  retn
0x1801107fe  lea     rax, aJetErrlogcorru; jumptable 0000000180110687 case -1906441666
0x180110805  retn
0x180110807  lea     rax, aJetErrmustdisa; jumptable 0000000180110687 case -1906441665
0x18011080e  retn
0x180110810  lea     rax, aJetErrbadresto; jumptable 0000000180110687 case -1906441663
0x180110817  retn
0x180110819  lea     rax, aJetErrrecovere_0; jumptable 0000000180110687 case -1906441661
0x180110820  retn
0x180110822  lea     rax, aJetErrdatabase_19; "JET_errDatabasesNotFromSameSnapshot"
0x180110829  retn
0x18011082b  mov     eax, 8E5E0415h
0x180110830  cmp     ecx, eax
0x180110832  jg      loc_180110ADD
0x180110838  jz      loc_180110AD4
0x18011083e  mov     eax, 8E5E03F5h
0x180110843  cmp     ecx, eax
0x180110845  jg      loc_1801109E5
0x18011084b  jz      loc_1801109DC
0x180110851  mov     eax, 8E5E0266h
0x180110856  cmp     ecx, eax
0x180110858  jg      loc_18011092D
0x18011085e  jz      loc_180110924
  ... truncated ...
```
