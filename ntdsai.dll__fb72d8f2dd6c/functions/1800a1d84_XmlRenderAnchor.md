# XmlRenderAnchor

- ea: `0x1800a1d84`
- end: `0x1800a2e39`
- name: `XmlRenderAnchor`
- size: `4277`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1803794f4`

## callees

- `0x1800a1d84`
- `0x1801057b8`
- `0x180105804`
- `0x180106b94`
- `0x180106f10`
- `0x1801070c8`
- `0x18016ba90`
- `0x18016c8e8`
- `0x18016c958`
- `0x18016ca34`
- `0x18016cbb0`
- `0x18016ccf8`
- `0x18016cd48`
- `0x18016cde8`
- `0x18016cea8`
- `0x18016cf14`
- `0x18016cf9c`
- `0x18016cfec`
- `0x18016d03c`
- `0x18016d118`
- `0x18016d180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2e12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2e12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18045a26b`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x1800a24d1`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x1800a2ca6`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x1800a24d1`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x1800a2ca6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1dee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1dee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2daa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18045a22a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18045a248`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a2daa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18045a22a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18045a248`

## string_xrefs

- `0x1800a1dfc`: `CSUpdate_initialized`
- `0x1800a1ec0`: `ReadOnlyNCs`
- `0x1800a1f06`: `ReadOnlyNCs`
- `0x1800a1f8a`: `XML-DUMP-UNIMPLEMENTED`
- `0x1800a2066`: `XML-DUMP-UNIMPLEMENTED`
- `0x1800a2057`: `SDRefDomSid`
- `0x1800a2093`: `fReferralSetIncomplete`
- `0x1800a21fa`: `pConfigDN`
- `0x1800a2210`: `dntConfig`
- `0x1800a2252`: `pDsSvcConfigDN`
- `0x1800a2387`: `fAmReadOnlyDC`
- `0x1800a2629`: `XML_DUMP_UNIMPLEMENTED`
- `0x1800a2630`: `MainGlobal_DNReadCache`
- `0x1800a26b5`: `LocalDRSExtensions`
- `0x1800a2794`: `LocalDRSExtensions`
- `0x1800a276b`: `ConfigObjGuid`
- `0x1800a2997`: `fLinkHistoryEnabled`
- `0x1800a29ad`: `fAlternateLinkDataStorageEnabled`
- `0x1800a29c3`: `fLinkQuotaEnabled`
- `0x1800a29d9`: `fSingleUpdateMasterEnabled`
- `0x1800a2a1b`: `fPrivilegedAccessManagementEnabled`
- `0x1800a2bf6`: `pComputerDN`
- `0x1800a2c38`: `fQuotaTableReady`
- `0x1800a2c4e`: `fStartLinkQuotaTableRebuild`
- `0x1800a2c90`: `linkQuotaUSN`

## pseudocode

```c
__int64 __fastcall XmlRenderAnchor(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rbx
  const wchar_t *v4; // r14
  const wchar_t *v5; // r8
  const wchar_t *v6; // r8
  const wchar_t *v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rbx
  const wchar_t *v10; // r8
  const wchar_t *v11; // r8
  const wchar_t *v12; // r8
  __int64 v13; // rcx
  __int64 i; // rbx
  __int64 j; // rbx
  __int64 k; // rbx
  __int64 v17; // r12
  __int64 m; // r15
  __int64 n; // rbx
  const wchar_t *v20; // r8
  const wchar_t *v21; // r8
  const wchar_t *v22; // r8
  __int64 ii; // r15
  __int64 jj; // rbx
  __int64 kk; // rbx
  __int64 v26; // r8
  __int64 v27; // rbx
  __int64 v28; // r8
  unsigned int mm; // r14d
  __int64 v30; // rbx
  __int64 v31; // rdx
  __int64 v32; // r15
  __int64 nn; // r14
  __int64 v35; // [rsp+70h] [rbp+18h] BYREF

  v35 = 0;
  XmlDumpBegin(a1, 0);
  XmlDumpAddTagHeader(a1, L"Anchor");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  EnterCriticalSection(&gAnchor);
  XmlDumpAddBOOL(a1, L"CSUpdate_initialized", (unsigned int)dword_18052B258);
  NCLEnumeratorInit(&v35, 2);
  XmlDumpAddTagHeader(a1, L"MasterNCs");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  v2 = v35;
  nclEnumeratorReset(v35, 2);
  while ( (unsigned int)nclEnumeratorMoveNext(v2) )
    XMLRenderNCLEnumerator(a1, v2);
  XmlDumpAddTagTrail(a1, L"MasterNCs");
  XmlDumpAddTagHeader(a1, L"ReplicaNCs");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  nclEnumeratorReset(v2, 0);
  while ( (unsigned int)nclEnumeratorMoveNext(v2) )
    XMLRenderNCLEnumerator(a1, v2);
  XmlDumpAddTagTrail(a1, L"ReplicaNCs");
  XmlDumpAddTagHeader(a1, L"ReadOnlyNCs");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  nclEnumeratorReset(v2, 1);
  while ( (unsigned int)nclEnumeratorMoveNext(v2) )
    XMLRenderNCLEnumerator(a1, v2);
  XmlDumpAddTagTrail(a1, L"ReadOnlyNCs");
  NCLEnumeratorRelease(&v35, 51194919);
  XmlDumpAddTagHeader(a1, L"pCRL");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  v3 = qword_18052B278;
  v4 = &pNodeName;
  while ( v3 )
  {
    XmlDumpAddTagHeader(a1, L"CR");
    WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
    XmlDumpAddDSName(a1, L"NC", *(_QWORD *)(v3 + 16));
    XmlDumpAddWString(a1, L"pNCBlock", L"XML-DUMP-UNIMPLEMENTED");
    XmlDumpAddDSName(a1, L"Obj", *(_QWORD *)(v3 + 32));
    v5 = &pNodeName;
    if ( *(_QWORD *)(v3 + 40) )
      v5 = *(const wchar_t **)(v3 + 40);
    XmlDumpAddWString(a1, L"NetbiosName", v5);
    v6 = &pNodeName;
    if ( *(_QWORD *)(v3 + 48) )
      v6 = *(const wchar_t **)(v3 + 48);
    XmlDumpAddWString(a1, L"DnsName", v6);
    v7 = &pNodeName;
    if ( *(_QWORD *)(v3 + 56) )
      v7 = *(const wchar_t **)(v3 + 56);
    XmlDumpAddWString(a1, L"DnsAliasName", v7);
    XmlDumpAddULONGHex(a1, L"flags", *(unsigned int *)(v3 + 64));
    XmlDumpAddULONG(a1, L"FirstNotifyDelay", *(unsigned int *)(v3 + 68));
    XmlDumpAddULONG(a1, L"SubsequentNotifyDelay", *(unsigned int *)(v3 + 72));
    XmlDumpAddDSName(a1, L"SDRefDom", *(_QWORD *)(v3 + 80));
    XmlDumpAddSID(a1, L"SDRefDomSid", *(_QWORD *)(v3 + 88));
    XmlDumpAddWString(a1, L"DnsReferral", L"XML-DUMP-UNIMPLEMENTED");
    XmlDumpAddULONG(a1, L"Enabled", *(unsigned int *)(v3 + 112));
    XmlDumpAddULONG(a1, L"fReferralSetIncomplete", *(unsigned int *)(v3 + 116));
    XmlDumpAddTagTrail(a1, L"CR");
    v3 = *(_QWORD *)(v3 + 8);
  }
  XmlDumpAddTagTrail(a1, L"pCRL");
  XmlDumpAddDSName(a1, L"pDMD", qword_18052B280);
  XmlDumpAddULONGHex(a1, L"dntDMD", (unsigned int)dword_18052B288);
  XmlDumpAddDSName(a1, L"pLDAPDMD", qword_18052B290);
  XmlDumpAddULONGHex(a1, L"dntLdapDmd", (unsigned int)dword_18052B298);
  XmlDumpAddDSNameString(a1, v8, qword_18052B2A0);
  XmlDumpAddDSName(a1, L"pDSADN", qword_18052B2A8);
  XmlDumpAddULONGHex(a1, L"dntDSA", (unsigned int)dword_18052B2B0);
  XmlDumpAddDSName(a1, L"pSiteDN", qword_18052B2B8);
  XmlDumpAddDSName(a1, L"pDomainDN", qword_18052B2C0);
  XmlDumpAddULONGHex(a1, L"dntDomain", (unsigned int)dword_18052B2C8);
  XmlDumpAddDSName(a1, L"pRootDomainDN", qword_18052B2D0);
  XmlDumpAddDSName(a1, L"pDefaultNC", qword_18052B2D8);
  XmlDumpAddDSName(a1, L"pQuotasDN", qword_18052B2E0);
  XmlDumpAddULONGHex(a1, L"dntQuotas", (unsigned int)dword_18052B2E8);
  XmlDumpAddDSName(a1, L"pConfigDN", qword_18052B2F0);
  XmlDumpAddULONGHex(a1, L"dntConfig", (unsigned int)dword_18052B2F8);
  XmlDumpAddDSName(a1, L"pExchangeDN", qword_18052B300);
  XmlDumpAddDSName(a1, L"pPartitionsDN", qword_18052B308);
  XmlDumpAddDSName(a1, L"pDsSvcConfigDN", Src);
  v9 = qword_18052B318;
  if ( qword_18052B318 )
  {
    XmlDumpAddTagHeader(a1, L"instDSA");
    if ( *(_DWORD *)(qword_18052B318 + 4) )
      v10 = (const wchar_t *)(v9 + *(unsigned int *)(qword_18052B318 + 4));
    else
      v10 = &pNodeName;
    XmlDumpAddWString(a1, L"Server", v10);
    if ( *(_DWORD *)(qword_18052B318 + 8) )
      v11 = (const wchar_t *)(v9 + *(unsigned int *)(qword_18052B318 + 8));
    else
      v11 = &pNodeName;
    XmlDumpAddWString(a1, L"Annotation", v11);
    if ( *(_DWORD *)(qword_18052B318 + 12) )
      v12 = (const wchar_t *)(v9 + *(unsigned int *)(qword_18052B318 + 12));
    else
      v12 = &pNodeName;
    XmlDumpAddWString(a1, L"Instance", v12);
    v13 = *(unsigned int *)(qword_18052B318 + 16);
    if ( (_DWORD)v13 )
      XmlDumpAddGUID(a1, L"GUID", v9 + v13);
    else
      XmlDumpAddWString(a1, L"GUID", &pNodeName);
    XmlDumpAddTagTrail(a1, L"instDSA");
  }
  else
  {
    XmlDumpAddWString(a1, L"instDSA", &pNodeName);
  }
  XmlDumpAddULONG(a1, L"cDomainsInForest", (unsigned int)dword_18052B320);
  XmlDumpAddULONG(a1, L"fAmGC", *(unsigned int *)dword_18052B324);
  XmlDumpAddULONG(a1, L"fAmVirtualGC", (unsigned int)dword_18052B328);
  XmlDumpAddULONG(a1, L"fAmReadOnlyDC", (unsigned int)dword_18052B32C);
  XmlDumpAddULONG(a1, L"fDisableInboundRepl", (unsigned int)dword_18052B330);
  XmlDumpAddULONG(a1, L"fDisableOutboundRepl", (unsigned int)dword_18052B334);
  XmlDumpAddTagHeader(a1, L"pdntAncestors");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  for ( i = 0; (unsigned int)i < dword_18052B340; i = (unsigned int)(i + 1) )
    XmlDumpAddULONGHex(a1, L"Ancestor", *(unsigned int *)(qword_18052B338 + 4 * i));
  XmlDumpAddTagTrail(a1, L"pdntAncestors");
  XmlDumpAddTagHeader(a1, L"pdntUnDeletable");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  for ( j = 0; (unsigned int)j < dword_18052B350; j = (unsigned int)(j + 1) )
    XmlDumpAddULONGHex(a1, L"dntUndeletable", *(unsigned int *)(qword_18052B348 + 4 * j));
  XmlDumpAddTagTrail(a1, L"pdntUnDeletable");
  XmlDumpAddTagHeader(a1, L"pdntUnDelAncestors");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  for ( k = 0; (unsigned int)k < dword_18052B378; k = (unsigned int)(k + 1) )
    XmlDumpAddULONGHex(a1, L"dntUnDelAncestor", *(unsigned int *)(qword_18052B358 + 4 * k));
  XmlDumpAddTagTrail(a1, L"pdntUnDelAncestors");
  if ( TryAcquireSRWLockShared(&stru_18052B370) )
  {
    v17 = qword_18052B368;
    XmlDumpAddTagHeader(a1, L"ProtectedMods");
    WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
    for ( m = 0; (unsigned int)m < dword_18052B360; m = (unsigned int)(m + 1) )
    {
      XmlDumpAddTagHeader(a1, L"ProtectedMod");
      WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
      XmlDumpAddULONGHex(a1, L"DNT", *(unsigned int *)(v17 + 8 * m));
      XmlDumpAddULONGHex(a1, L"AttrTyp", *(unsigned int *)(v17 + 8 * m + 4));
      XmlDumpAddTagTrail(a1, L"ProtectedMod");
    }
    XmlDumpAddTagTrail(a1, L"ProtectedMods");
    ReleaseSRWLockShared(&stru_18052B370);
  }
  else
  {
    XmlDumpAddWString(a1, L"ProtectedMods", L"UNAVAILABLE-LOCK-CONTENTION");
  }
  XmlDumpAddULONG(a1, L"ulDefaultLanguage", (unsigned int)qword_18052B37C);
  XmlDumpAddTagHeader(a1, L"pulLangs");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  for ( n = 0; (unsigned int)n < HIDWORD(qword_18052B37C); n = (unsigned int)(n + 1) )
    XmlDumpAddULONGHex(a1, L"ulLang", *(unsigned int *)(qword_18052B388 + 4 * n));
  XmlDumpAddTagTrail(a1, L"pulLangs");
  XmlDumpAddWString(a1, L"MainGlobal_DNReadCache", L"XML_DUMP_UNIMPLEMENTED");
  v20 = &pNodeName;
  if ( Str )
    v20 = Str;
  XmlDumpAddWString(a1, L"pwszRootDomainDnsName", v20);
  v21 = &pNodeName;
  if ( pName2 )
    v21 = pName2;
  XmlDumpAddWString(a1, L"pwszHostDnsName", v21);
  v22 = &pNodeName;
  if ( qword_18052B3A8 )
    v22 = qword_18052B3A8;
  XmlDumpAddWString(a1, L"pwszNetBiosName", v22);
  XmlDumpAddDSName(a1, L"pInfraStructureDN", qword_18052B3B0);
  XmlDumpAddTagHeader(a1, L"LocalDRSExtensions");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  if ( qword_18052B3B8 )
  {
    XmlDumpAddULONGHex(a1, L"dwFlags", *((unsigned int *)qword_18052B3B8 + 1));
    XmlDumpAddGUID(a1, L"SiteObjGuid", (char *)qword_18052B3B8 + 8);
    XmlDumpAddULONG(a1, L"pid", *((unsigned int *)qword_18052B3B8 + 6));
    XmlDumpAddULONG(a1, L"dwReplEpoch", *((unsigned int *)qword_18052B3B8 + 7));
    XmlDumpAddULONGHex(a1, L"dwFlagsExt", *((unsigned int *)qword_18052B3B8 + 8));
    XmlDumpAddGUID(a1, L"ConfigObjGuid", (char *)qword_18052B3B8 + 36);
    XmlDumpAddULONGHex(a1, L"dwExtCaps", *((unsigned int *)qword_18052B3B8 + 13));
  }
  XmlDumpAddTagTrail(a1, L"LocalDRSExtensions");
  XmlDumpAddSD(a1, L"pDomainSD", *(_QWORD *)&qword_18052B3C0);
  XmlDumpAddULONG(a1, L"fDomainSubrefList", (unsigned int)dword_18052B3C8);
  XmlDumpAddULONG(a1, L"cDomainSubrefList", (unsigned int)dword_18052B3CC);
  XmlDumpAddTagHeader(a1, L"DomainSubrefList");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  for ( ii = qword_18052B3D0; ii; ii = *(_QWORD *)ii )
  {
    XmlDumpAddTagHeader(a1, L"DomainSubref");
    WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
    XmlDumpAddDSName(a1, L"DSName", *(_QWORD *)(ii + 8));
    XmlDumpAddTagHeader(a1, L"dntAncestors");
    WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
    for ( jj = 0; (unsigned int)jj < *(_DWORD *)(ii + 24); jj = (unsigned int)(jj + 1) )
      XmlDumpAddULONGHex(a1, L"dntAncestor", *(unsigned int *)(*(_QWORD *)(ii + 16) + 4 * jj));
    XmlDumpAddTagTrail(a1, L"dntAncestors");
    XmlDumpAddTagTrail(a1, L"DomainSubref");
  }
  XmlDumpAddTagTrail(a1, L"DomainSubrefList");
  XmlDumpAddTagHeader(a1, L"pulLangs");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  for ( kk = 0; (unsigned int)kk < HIDWORD(qword_18052B37C); kk = (unsigned int)(kk + 1) )
    XmlDumpAddULONGHex(a1, L"ulLang", *(unsigned int *)(qword_18052B388 + 4 * kk));
  XmlDumpAddTagTrail(a1, L"pulLangs");
  XmlDumpAddULONG(a1, L"fAmRootDomainDC", (unsigned int)dword_18052B3D8);
  XmlDumpAddULONGHex(a1, L"ulSiteOptions", (unsigned int)dword_18052B3DC);
  XmlDumpAddULONG(a1, L"ForestBehaviorVersion", (unsigned int)dword_18052B3E0);
  XmlDumpAddULONG(a1, L"DomainBehaviorVersion", *(unsigned int *)dword_18052B3E4);
  XmlDumpAddULONG(a1, L"fRecycleBinEnabled", (unsigned int)dword_18052B3E8);
  XmlDumpAddULONG(a1, L"fLinkHistoryEnabled", (unsigned int)dword_18052B3F4);
  XmlDumpAddULONG(a1, L"fAlternateLinkDataStorageEnabled", (unsigned int)dword_18052B3F8);
  XmlDumpAddULONG(a1, L"fLinkQuotaEnabled", (unsigned int)dword_18052B3FC);
  XmlDumpAddULONG(a1, L"fSingleUpdateMasterEnabled", (unsigned int)dword_18052B400);
  XmlDumpAddULONG(a1, L"fMetaDataTableEnabled", (unsigned int)dword_18052B404);
  XmlDumpAddULONG(a1, L"fDirSyncSetEnabled", (unsigned int)dword_18052B408);
  XmlDumpAddULONG(a1, L"fPrivilegedAccessManagementEnabled", (unsigned int)dword_18052B40C);
  XmlDumpAddULONG(a1, L"JetDatabasePageSize", (unsigned int)dword_18052B3EC);
  XmlDumpAddULONG(a1, L"fDatabase32kPagesEnabled", (unsigned int)dword_18052B3F0);
  XmlDumpAddGUID(a1, L"CurrInvocationID", qword_18052B410);
  XmlDumpAddTagHeader(a1, L"ppwszAllowedDNSSuffixes");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  v26 = qword_18052B418;
  if ( qword_18052B418 )
  {
    v27 = 0;
    while ( 1 )
    {
      v28 = *(_QWORD *)(v26 + 8 * v27);
      if ( !v28 )
        break;
      XmlDumpAddWString(a1, L"ppwszAllowedDNSSuffixes", v28);
      v27 = (unsigned int)(v27 + 1);
      v26 = qword_18052B418;
    }
  }
  XmlDumpAddTagTrail(a1, L"ppwszAllowedDNSSuffixes");
  if ( qword_18052B420 )
    v4 = (const wchar_t *)qword_18052B420;
  XmlDumpAddWString(a1, L"pwszadditionalRootDomainName", v4);
  XmlDumpAddTagHeader(a1, L"SignatureVector");
  WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
  if ( qword_18052B428 )
  {
    XmlDumpAddULONG(a1, L"Version", *(unsigned int *)qword_18052B428);
    for ( mm = 0; mm < *(_DWORD *)(qword_18052B428 + 8); ++mm )
    {
      XmlDumpAddTagHeader(a1, L"Signature");
      WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
      v30 = 32LL * mm;
      XmlDumpAddGUID(a1, L"invocationID", v30 + qword_18052B428 + 16);
      XmlDumpAddDSTime(a1, v31, *(_QWORD *)(v30 + qword_18052B428 + 32));
      XmlDumpAddULONGLONG(a1, L"USNRetired", *(_QWORD *)(v30 + qword_18052B428 + 40));
      XmlDumpAddTagTrail(a1, L"Signature");
    }
  }
  XmlDumpAddTagTrail(a1, L"SignatureVector");
  XmlDumpAddDSName(a1, L"pComputerDN", qword_18052B430);
  XmlDumpAddULONGHex(a1, L"dntSystem", (unsigned int)dword_18052B438);
  XmlDumpAddULONGHex(a1, L"dntPasswordSettingsContainer", (unsigned int)dword_18052B43C);
  XmlDumpAddULONG(a1, L"fQuotaTableReady", (unsigned int)dword_18052B440);
  XmlDumpAddULONG(a1, L"fStartLinkQuotaTableRebuild", (unsigned int)dword_18052B444);
  XmlDumpAddULONGHex(a1, L"dntQuotaRebuildDNTLast", (unsigned int)dword_18052B448);
  XmlDumpAddULONGHex(a1, L"dntQuotaRebuildDNTMax", (unsigned int)dword_18052B44C);
  XmlDumpAddULONGLONG(a1, L"linkQuotaUSN", qword_18052B450);
  if ( TryAcquireSRWLockShared(&SRWLock) )
  {
    v32 = qword_18052B460;
    XmlDumpAddTagHeader(a1, L"PeriodicEvents");
    WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
    for ( nn = 0; (unsigned int)nn < dword_18052B458; nn = (unsigned int)(nn + 1) )
    {
      XmlDumpAddTagHeader(a1, L"PeriodicEvent");
      WStrCatWCHARs(a1, a1 + 6344, L"\r\n", 2);
      XmlDumpAddULONG(a1, L"Cat", *(unsigned int *)(v32 + 20 * nn + 8));
      XmlDumpAddULONG(a1, L"Sev", *(unsigned int *)(v32 + 20 * nn + 12));
      XmlDumpAddULONG(a1, L"ID", *(unsigned int *)(v32 + 20 * nn + 16));
      XmlDumpAddULONGHex(a1, L"DNT", *(unsigned int *)(v32 + 20 * nn));
      XmlDumpAddULONGHex(a1, L"AttrTyp", *(unsigned int *)(v32 + 20 * nn + 4));
      XmlDumpAddTagTrail(a1, L"PeriodicEvent");
    }
    XmlDumpAddTagTrail(a1, L"PeriodicEvents");
    ReleaseSRWLockShared(&SRWLock);
  }
  else
  {
    XmlDumpAddWString(a1, L"PeriodicEvents", L"UNAVAILABLE-LOCK-CONTENTION");
  }
  XmlDumpAddULONGHex(a1, L"ulDsSecretDomainNetlogonFlag", (unsigned int)dword_18052B470);
  XmlDumpAddULONGHex(a1, L"ulDsaOptions", (unsigned int)dword_18052B474);
  XmlDumpAddULONG(a1, L"LastSchemaVersionWrittenToReg", (unsigned int)dword_18052B478);
  LeaveCriticalSection(&gAnchor);
  return XmlDumpAddTagTrail(a1, L"Anchor");
}

```

## disassembly

```asm
0x1800a1d84  mov     [rsp+arg_0], rbx
0x1800a1d89  push    rsi
0x1800a1d8a  push    rdi
0x1800a1d8b  push    r12
0x1800a1d8d  push    r14
0x1800a1d8f  push    r15
0x1800a1d91  sub     rsp, 30h
0x1800a1d95  mov     rdi, rcx
0x1800a1d98  mov     [rsp+58h+arg_10], 0
0x1800a1da1  mov     r14d, 30D2C27h
0x1800a1da7  mov     [rsp+58h+arg_8], r14d
0x1800a1dac  xor     edx, edx
0x1800a1dae  call    XmlDumpBegin
0x1800a1db3  lea     rdx, aAnchor; "Anchor"
0x1800a1dba  mov     rcx, rdi
0x1800a1dbd  call    XmlDumpAddTagHeader
0x1800a1dc2  lea     rsi, [rdi+18C8h]
0x1800a1dc9  mov     r12d, 2
0x1800a1dcf  mov     r9d, r12d
0x1800a1dd2  lea     r15, asc_1804B1560; "\r\n"
0x1800a1dd9  mov     r8, r15
0x1800a1ddc  mov     rdx, rsi
0x1800a1ddf  mov     rcx, rdi
0x1800a1de2  call    WStrCatWCHARs
0x1800a1de7  lea     rcx, gAnchor; lpCriticalSection
0x1800a1dee  call    cs:__imp_EnterCriticalSection
0x1800a1df4  nop
0x1800a1df5  mov     r8d, cs:dword_18052B258
0x1800a1dfc  lea     rdx, aCsupdateInitia; "CSUpdate_initialized"
0x1800a1e03  mov     rcx, rdi
0x1800a1e06  call    XmlDumpAddBOOL
0x1800a1e0b  mov     r8d, r14d
0x1800a1e0e  mov     edx, r12d
0x1800a1e11  lea     rcx, [rsp+58h+arg_10]
0x1800a1e16  call    NCLEnumeratorInit
0x1800a1e1b  nop
0x1800a1e1c  lea     rdx, aMasterncs; "MasterNCs"
0x1800a1e23  mov     rcx, rdi
0x1800a1e26  call    XmlDumpAddTagHeader
0x1800a1e2b  mov     r9d, r12d
0x1800a1e2e  mov     r8, r15
0x1800a1e31  mov     rdx, rsi
0x1800a1e34  mov     rcx, rdi
0x1800a1e37  call    WStrCatWCHARs
0x1800a1e3c  mov     edx, r12d
0x1800a1e3f  mov     rbx, [rsp+58h+arg_10]
0x1800a1e44  mov     rcx, rbx
0x1800a1e47  call    nclEnumeratorReset
0x1800a1e4c  mov     rcx, rbx
0x1800a1e4f  call    nclEnumeratorMoveNext
0x1800a1e54  mov     rcx, rdi
0x1800a1e57  test    eax, eax
0x1800a1e59  jz      short loc_1800A1E65
0x1800a1e5b  mov     rdx, rbx
0x1800a1e5e  call    XMLRenderNCLEnumerator
0x1800a1e63  jmp     short loc_1800A1E4C
0x1800a1e65  lea     rdx, aMasterncs; "MasterNCs"
0x1800a1e6c  call    XmlDumpAddTagTrail
0x1800a1e71  lea     rdx, aReplicancs; "ReplicaNCs"
0x1800a1e78  mov     rcx, rdi
0x1800a1e7b  call    XmlDumpAddTagHeader
0x1800a1e80  mov     r9, r12
0x1800a1e83  mov     r8, r15
0x1800a1e86  mov     rdx, rsi
0x1800a1e89  mov     rcx, rdi
0x1800a1e8c  call    WStrCatWCHARs
0x1800a1e91  xor     edx, edx
0x1800a1e93  mov     rcx, rbx
0x1800a1e96  call    nclEnumeratorReset
0x1800a1e9b  mov     rcx, rbx
0x1800a1e9e  call    nclEnumeratorMoveNext
0x1800a1ea3  mov     rcx, rdi
0x1800a1ea6  test    eax, eax
0x1800a1ea8  jz      short loc_1800A1EB4
0x1800a1eaa  mov     rdx, rbx
0x1800a1ead  call    XMLRenderNCLEnumerator
0x1800a1eb2  jmp     short loc_1800A1E9B
0x1800a1eb4  lea     rdx, aReplicancs; "ReplicaNCs"
0x1800a1ebb  call    XmlDumpAddTagTrail
0x1800a1ec0  lea     rdx, aReadonlyncs; "ReadOnlyNCs"
0x1800a1ec7  mov     rcx, rdi
0x1800a1eca  call    XmlDumpAddTagHeader
0x1800a1ecf  mov     r9, r12
0x1800a1ed2  mov     r8, r15
0x1800a1ed5  mov     rdx, rsi
0x1800a1ed8  mov     rcx, rdi
0x1800a1edb  call    WStrCatWCHARs
0x1800a1ee0  mov     edx, 1
0x1800a1ee5  mov     rcx, rbx
0x1800a1ee8  call    nclEnumeratorReset
0x1800a1eed  mov     rcx, rbx
0x1800a1ef0  call    nclEnumeratorMoveNext
0x1800a1ef5  mov     rcx, rdi
0x1800a1ef8  test    eax, eax
0x1800a1efa  jz      short loc_1800A1F06
0x1800a1efc  mov     rdx, rbx
0x1800a1eff  call    XMLRenderNCLEnumerator
0x1800a1f04  jmp     short loc_1800A1EED
0x1800a1f06  lea     rdx, aReadonlyncs; "ReadOnlyNCs"
0x1800a1f0d  call    XmlDumpAddTagTrail
0x1800a1f12  nop
0x1800a1f13  mov     edx, r14d
0x1800a1f16  lea     rcx, [rsp+58h+arg_10]
0x1800a1f1b  call    NCLEnumeratorRelease
0x1800a1f20  lea     rdx, aPcrl; "pCRL"
0x1800a1f27  mov     rcx, rdi
0x1800a1f2a  call    XmlDumpAddTagHeader
0x1800a1f2f  mov     r9, r12
0x1800a1f32  mov     r8, r15
0x1800a1f35  mov     rdx, rsi
0x1800a1f38  mov     rcx, rdi
0x1800a1f3b  call    WStrCatWCHARs
0x1800a1f40  mov     rbx, cs:qword_18052B278
0x1800a1f47  lea     r14, pNodeName
0x1800a1f4e  mov     rcx, rdi
0x1800a1f51  test    rbx, rbx
0x1800a1f54  jz      loc_1800A20BA
0x1800a1f5a  lea     rdx, aCr; "CR"
0x1800a1f61  call    XmlDumpAddTagHeader
0x1800a1f66  mov     r9, r12
0x1800a1f69  mov     r8, r15
0x1800a1f6c  mov     rdx, rsi
0x1800a1f6f  mov     rcx, rdi
0x1800a1f72  call    WStrCatWCHARs
0x1800a1f77  mov     r8, [rbx+10h]
0x1800a1f7b  lea     rdx, aNc; "NC"
0x1800a1f82  mov     rcx, rdi
0x1800a1f85  call    XmlDumpAddDSName
0x1800a1f8a  lea     r8, aXmlDumpUnimple; "XML-DUMP-UNIMPLEMENTED"
0x1800a1f91  lea     rdx, aPncblock; "pNCBlock"
0x1800a1f98  mov     rcx, rdi
0x1800a1f9b  call    XmlDumpAddWString
0x1800a1fa0  mov     r8, [rbx+20h]
0x1800a1fa4  lea     rdx, aObj; "Obj"
0x1800a1fab  mov     rcx, rdi
0x1800a1fae  call    XmlDumpAddDSName
0x1800a1fb3  mov     r8, r14
0x1800a1fb6  cmp     qword ptr [rbx+28h], 0
0x1800a1fbb  cmovnz  r8, [rbx+28h]
0x1800a1fc0  lea     rdx, aNetbiosname; "NetbiosName"
0x1800a1fc7  mov     rcx, rdi
0x1800a1fca  call    XmlDumpAddWString
0x1800a1fcf  mov     r8, r14
0x1800a1fd2  cmp     qword ptr [rbx+30h], 0
0x1800a1fd7  cmovnz  r8, [rbx+30h]
0x1800a1fdc  lea     rdx, aDnsname; "DnsName"
0x1800a1fe3  mov     rcx, rdi
0x1800a1fe6  call    XmlDumpAddWString
0x1800a1feb  mov     r8, r14
0x1800a1fee  cmp     qword ptr [rbx+38h], 0
0x1800a1ff3  cmovnz  r8, [rbx+38h]
0x1800a1ff8  lea     rdx, aDnsaliasname; "DnsAliasName"
0x1800a1fff  mov     rcx, rdi
0x1800a2002  call    XmlDumpAddWString
0x1800a2007  mov     r8d, [rbx+40h]
0x1800a200b  lea     rdx, aFlags; "flags"
0x1800a2012  mov     rcx, rdi
0x1800a2015  call    XmlDumpAddULONGHex
0x1800a201a  mov     r8d, [rbx+44h]
0x1800a201e  lea     rdx, aFirstnotifydel; "FirstNotifyDelay"
0x1800a2025  mov     rcx, rdi
0x1800a2028  call    XmlDumpAddULONG
0x1800a202d  mov     r8d, [rbx+48h]
0x1800a2031  lea     rdx, aSubsequentnoti; "SubsequentNotifyDelay"
0x1800a2038  mov     rcx, rdi
0x1800a203b  call    XmlDumpAddULONG
0x1800a2040  mov     r8, [rbx+50h]
0x1800a2044  lea     rdx, aSdrefdom; "SDRefDom"
0x1800a204b  mov     rcx, rdi
0x1800a204e  call    XmlDumpAddDSName
0x1800a2053  mov     r8, [rbx+58h]
0x1800a2057  lea     rdx, aSdrefdomsid; "SDRefDomSid"
0x1800a205e  mov     rcx, rdi
0x1800a2061  call    XmlDumpAddSID
0x1800a2066  lea     r8, aXmlDumpUnimple; "XML-DUMP-UNIMPLEMENTED"
0x1800a206d  lea     rdx, aDnsreferral; "DnsReferral"
0x1800a2074  mov     rcx, rdi
0x1800a2077  call    XmlDumpAddWString
0x1800a207c  mov     r8d, [rbx+70h]
0x1800a2080  lea     rdx, aEnabled; "Enabled"
0x1800a2087  mov     rcx, rdi
0x1800a208a  call    XmlDumpAddULONG
0x1800a208f  mov     r8d, [rbx+74h]
0x1800a2093  lea     rdx, aFreferralsetin; "fReferralSetIncomplete"
0x1800a209a  mov     rcx, rdi
0x1800a209d  call    XmlDumpAddULONG
0x1800a20a2  lea     rdx, aCr; "CR"
0x1800a20a9  mov     rcx, rdi
0x1800a20ac  call    XmlDumpAddTagTrail
0x1800a20b1  mov     rbx, [rbx+8]
0x1800a20b5  jmp     loc_1800A1F4E
0x1800a20ba  lea     rdx, aPcrl; "pCRL"
0x1800a20c1  call    XmlDumpAddTagTrail
0x1800a20c6  mov     r8, cs:qword_18052B280
0x1800a20cd  lea     rdx, aPdmd; "pDMD"
0x1800a20d4  mov     rcx, rdi
0x1800a20d7  call    XmlDumpAddDSName
0x1800a20dc  mov     r8d, cs:dword_18052B288
0x1800a20e3  lea     rdx, aDntdmd; "dntDMD"
0x1800a20ea  mov     rcx, rdi
0x1800a20ed  call    XmlDumpAddULONGHex
0x1800a20f2  mov     r8, cs:qword_18052B290
0x1800a20f9  lea     rdx, aPldapdmd; "pLDAPDMD"
0x1800a2100  mov     rcx, rdi
0x1800a2103  call    XmlDumpAddDSName
0x1800a2108  mov     r8d, cs:dword_18052B298
0x1800a210f  lea     rdx, aDntldapdmd; "dntLdapDmd"
0x1800a2116  mov     rcx, rdi
0x1800a2119  call    XmlDumpAddULONGHex
0x1800a211e  mov     r8, cs:qword_18052B2A0
0x1800a2125  mov     rcx, rdi
0x1800a2128  call    XmlDumpAddDSNameString
0x1800a212d  mov     r8, cs:qword_18052B2A8
0x1800a2134  lea     rdx, aPdsadn; "pDSADN"
0x1800a213b  mov     rcx, rdi
0x1800a213e  call    XmlDumpAddDSName
0x1800a2143  mov     r8d, cs:dword_18052B2B0
0x1800a214a  lea     rdx, aDntdsa; "dntDSA"
0x1800a2151  mov     rcx, rdi
0x1800a2154  call    XmlDumpAddULONGHex
0x1800a2159  mov     r8, cs:qword_18052B2B8
0x1800a2160  lea     rdx, aPsitedn; "pSiteDN"
0x1800a2167  mov     rcx, rdi
0x1800a216a  call    XmlDumpAddDSName
0x1800a216f  mov     r8, cs:qword_18052B2C0
0x1800a2176  lea     rdx, aPdomaindn; "pDomainDN"
0x1800a217d  mov     rcx, rdi
0x1800a2180  call    XmlDumpAddDSName
0x1800a2185  mov     r8d, cs:dword_18052B2C8
0x1800a218c  lea     rdx, aDntdomain; "dntDomain"
0x1800a2193  mov     rcx, rdi
0x1800a2196  call    XmlDumpAddULONGHex
0x1800a219b  mov     r8, cs:qword_18052B2D0
0x1800a21a2  lea     rdx, aProotdomaindn; "pRootDomainDN"
0x1800a21a9  mov     rcx, rdi
0x1800a21ac  call    XmlDumpAddDSName
0x1800a21b1  mov     r8, cs:qword_18052B2D8
0x1800a21b8  lea     rdx, aPdefaultnc; "pDefaultNC"
0x1800a21bf  mov     rcx, rdi
0x1800a21c2  call    XmlDumpAddDSName
0x1800a21c7  mov     r8, cs:qword_18052B2E0
0x1800a21ce  lea     rdx, aPquotasdn; "pQuotasDN"
0x1800a21d5  mov     rcx, rdi
0x1800a21d8  call    XmlDumpAddDSName
0x1800a21dd  mov     r8d, cs:dword_18052B2E8
0x1800a21e4  lea     rdx, aDntquotas; "dntQuotas"
0x1800a21eb  mov     rcx, rdi
0x1800a21ee  call    XmlDumpAddULONGHex
0x1800a21f3  mov     r8, cs:qword_18052B2F0
0x1800a21fa  lea     rdx, aPconfigdn; "pConfigDN"
0x1800a2201  mov     rcx, rdi
0x1800a2204  call    XmlDumpAddDSName
0x1800a2209  mov     r8d, cs:dword_18052B2F8
0x1800a2210  lea     rdx, aDntconfig; "dntConfig"
0x1800a2217  mov     rcx, rdi
0x1800a221a  call    XmlDumpAddULONGHex
0x1800a221f  mov     r8, cs:qword_18052B300
0x1800a2226  lea     rdx, aPexchangedn; "pExchangeDN"
0x1800a222d  mov     rcx, rdi
0x1800a2230  call    XmlDumpAddDSName
0x1800a2235  mov     r8, cs:qword_18052B308
0x1800a223c  lea     rdx, aPpartitionsdn; "pPartitionsDN"
0x1800a2243  mov     rcx, rdi
0x1800a2246  call    XmlDumpAddDSName
0x1800a224b  mov     r8, cs:Src
0x1800a2252  lea     rdx, aPdssvcconfigdn; "pDsSvcConfigDN"
0x1800a2259  mov     rcx, rdi
0x1800a225c  call    XmlDumpAddDSName
0x1800a2261  mov     rbx, cs:qword_18052B318
0x1800a2268  lea     rdx, aInstdsa; "instDSA"
0x1800a226f  mov     rcx, rdi
0x1800a2272  test    rbx, rbx
0x1800a2275  jnz     short loc_1800A2284
0x1800a2277  mov     r8, r14
0x1800a227a  call    XmlDumpAddWString
0x1800a227f  jmp     loc_1800A233E
0x1800a2284  call    XmlDumpAddTagHeader
0x1800a2289  mov     rax, cs:qword_18052B318
0x1800a2290  cmp     dword ptr [rax+4], 0
0x1800a2294  jz      short loc_1800A229F
0x1800a2296  mov     r8d, [rax+4]
0x1800a229a  add     r8, rbx
0x1800a229d  jmp     short loc_1800A22A2
0x1800a229f  mov     r8, r14
0x1800a22a2  lea     rdx, aServer; "Server"
0x1800a22a9  mov     rcx, rdi
0x1800a22ac  call    XmlDumpAddWString
0x1800a22b1  mov     rax, cs:qword_18052B318
0x1800a22b8  cmp     dword ptr [rax+8], 0
0x1800a22bc  jz      short loc_1800A22C7
0x1800a22be  mov     r8d, [rax+8]
0x1800a22c2  add     r8, rbx
0x1800a22c5  jmp     short loc_1800A22CA
0x1800a22c7  mov     r8, r14
0x1800a22ca  lea     rdx, aAnnotation; "Annotation"
0x1800a22d1  mov     rcx, rdi
0x1800a22d4  call    XmlDumpAddWString
0x1800a22d9  mov     rax, cs:qword_18052B318
0x1800a22e0  cmp     dword ptr [rax+0Ch], 0
0x1800a22e4  jz      short loc_1800A22EF
  ... truncated ...
```
