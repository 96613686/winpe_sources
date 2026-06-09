# GetExplanationForPkgDefMerge(PkgDefMergeReason)

- ea: `0x140036d00`
- end: `0x140036e1b`
- name: `?GetExplanationForPkgDefMerge@@YAPEBGW4PkgDefMergeReason@@@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14000ccfc`

## callees

- `0x140036d00`

## string_xrefs

- `0x140036d3a`: `FailedToAcquireCacheLock`
- `0x140036d5a`: `CacheCurrentFastCheckDefaultedToNo`
- `0x140036d86`: `AbandonedCacheLock`
- `0x140036d76`: `CacheMissingOrCorrupt`
- `0x140036d96`: `ExtensionManagerConfigChangedFileUpdated`
- `0x140036e13`: `PrivateRegistryTimestampUpdated`
- `0x140036e0b`: `HKLMTimestampUpdated`
- `0x140036deb`: `FailedToOpenInitRootKey`
- `0x140036de3`: `FailedToCreateBinaryFileList`
- `0x140036ddb`: `MissingConfigurationTimestamp`
- `0x140036dd3`: `PersistedConfigTimestampAndRegistryLastChangedTimeMismatch`

## pseudocode

```c
const wchar_t *__fastcall GetExplanationForPkgDefMerge(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
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

  if ( a1 <= 10 )
  {
    if ( a1 == 10 )
      return L"ExtensionManagerConfigChangedFileUpdated";
    if ( a1 > 5 )
    {
      v5 = a1 - 6;
      if ( !v5 )
        return L"ForcedDueToPkgDefManagmentFlag";
      v6 = v5 - 1;
      if ( !v6 )
        return L"AbandonedCacheLock";
      v7 = v6 - 1;
      if ( !v7 )
        return L"GotDefaultFileTimeValuesForAllTimestamps";
      if ( v7 == 1 )
        return L"CacheMissingOrCorrupt";
    }
    else
    {
      if ( a1 == 5 )
        return L"CacheCurrentFastCheckDefaultedToNo";
      if ( !a1 )
        return L"DidNotMerge";
      v1 = a1 - 1;
      if ( !v1 )
        return L"VolatileHive";
      v2 = v1 - 1;
      if ( !v2 )
        return L"OutOfDateTimeStamp";
      v3 = v2 - 1;
      if ( !v3 )
        return L"FailedToAcquireCacheLock";
      if ( v3 == 1 )
        return L"RunningInSafeMode";
    }
    return L"Unknown";
  }
  v8 = a1 - 11;
  if ( !v8 )
    return L"PrivateRegistryTimestampUpdated";
  v9 = v8 - 1;
  if ( !v9 )
    return L"HKLMTimestampUpdated";
  v10 = v9 - 1;
  if ( !v10 )
    return L"FailedToGetExistingBinaryFileList";
  v11 = v10 - 1;
  if ( !v11 )
    return L"BinaryFileListSizeMismatch";
  v12 = v11 - 1;
  if ( !v12 )
    return L"BinaryFileListContentMismatch";
  v13 = v12 - 1;
  if ( !v13 )
    return L"FailedToOpenInitRootKey";
  v14 = v13 - 1;
  if ( !v14 )
    return L"FailedToCreateBinaryFileList";
  v15 = v14 - 1;
  if ( !v15 )
    return L"MissingConfigurationTimestamp";
  if ( v15 != 1 )
    return L"Unknown";
  return L"PersistedConfigTimestampAndRegistryLastChangedTimeMismatch";
}

```

## disassembly

```asm
0x140036d00  cmp     ecx, 0Ah
0x140036d03  jg      loc_140036D9E
0x140036d09  jz      loc_140036D96
0x140036d0f  cmp     ecx, 5
0x140036d12  jg      short loc_140036D62
0x140036d14  jz      short loc_140036D5A
0x140036d16  test    ecx, ecx
0x140036d18  jz      short loc_140036D52
0x140036d1a  sub     ecx, 1
0x140036d1d  jz      short loc_140036D4A
0x140036d1f  sub     ecx, 1
0x140036d22  jz      short loc_140036D42
0x140036d24  sub     ecx, 1
0x140036d27  jz      short loc_140036D3A
0x140036d29  cmp     ecx, 1
0x140036d2c  jnz     loc_140036DCB
0x140036d32  lea     rax, aRunninginsafem; "RunningInSafeMode"
0x140036d39  retn
0x140036d3a  lea     rax, aFailedtoacquir; "FailedToAcquireCacheLock"
0x140036d41  retn
0x140036d42  lea     rax, aOutofdatetimes; "OutOfDateTimeStamp"
0x140036d49  retn
0x140036d4a  lea     rax, aVolatilehive; "VolatileHive"
0x140036d51  retn
0x140036d52  lea     rax, aDidnotmerge; "DidNotMerge"
0x140036d59  retn
0x140036d5a  lea     rax, aCachecurrentfa; "CacheCurrentFastCheckDefaultedToNo"
0x140036d61  retn
0x140036d62  sub     ecx, 6
0x140036d65  jz      short loc_140036D8E
0x140036d67  sub     ecx, 1
0x140036d6a  jz      short loc_140036D86
0x140036d6c  sub     ecx, 1
0x140036d6f  jz      short loc_140036D7E
0x140036d71  cmp     ecx, 1
0x140036d74  jnz     short loc_140036DCB
0x140036d76  lea     rax, aCachemissingor; "CacheMissingOrCorrupt"
0x140036d7d  retn
0x140036d7e  lea     rax, aGotdefaultfile; "GotDefaultFileTimeValuesForAllTimestamp"...
0x140036d85  retn
0x140036d86  lea     rax, aAbandonedcache; "AbandonedCacheLock"
0x140036d8d  retn
0x140036d8e  lea     rax, aForcedduetopkg; "ForcedDueToPkgDefManagmentFlag"
0x140036d95  retn
0x140036d96  lea     rax, aExtensionmanag_0; "ExtensionManagerConfigChangedFileUpdate"...
0x140036d9d  retn
0x140036d9e  sub     ecx, 0Bh
0x140036da1  jz      short loc_140036E13
0x140036da3  sub     ecx, 1
0x140036da6  jz      short loc_140036E0B
0x140036da8  sub     ecx, 1
0x140036dab  jz      short loc_140036E03
0x140036dad  sub     ecx, 1
0x140036db0  jz      short loc_140036DFB
0x140036db2  sub     ecx, 1
0x140036db5  jz      short loc_140036DF3
0x140036db7  sub     ecx, 1
0x140036dba  jz      short loc_140036DEB
0x140036dbc  sub     ecx, 1
0x140036dbf  jz      short loc_140036DE3
0x140036dc1  sub     ecx, 1
0x140036dc4  jz      short loc_140036DDB
0x140036dc6  cmp     ecx, 1
0x140036dc9  jz      short loc_140036DD3
0x140036dcb  lea     rax, aUnknown; "Unknown"
0x140036dd2  retn
0x140036dd3  lea     rax, aPersistedconfi; "PersistedConfigTimestampAndRegistryLast"...
0x140036dda  retn
0x140036ddb  lea     rax, aMissingconfigu; "MissingConfigurationTimestamp"
0x140036de2  retn
0x140036de3  lea     rax, aFailedtocreate; "FailedToCreateBinaryFileList"
0x140036dea  retn
0x140036deb  lea     rax, aFailedtoopenin; "FailedToOpenInitRootKey"
0x140036df2  retn
0x140036df3  lea     rax, aBinaryfilelist; "BinaryFileListContentMismatch"
0x140036dfa  retn
0x140036dfb  lea     rax, aBinaryfilelist_0; "BinaryFileListSizeMismatch"
0x140036e02  retn
0x140036e03  lea     rax, aFailedtogetexi; "FailedToGetExistingBinaryFileList"
0x140036e0a  retn
0x140036e0b  lea     rax, aHklmtimestampu; "HKLMTimestampUpdated"
0x140036e12  retn
0x140036e13  lea     rax, aPrivateregistr_0; "PrivateRegistryTimestampUpdated"
0x140036e1a  retn
```
