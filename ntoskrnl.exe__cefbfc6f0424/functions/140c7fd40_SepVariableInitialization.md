# SepVariableInitialization

- ea: `0x140c7fd40`
- end: `0x140c81772`
- name: `SepVariableInitialization`
- size: `6706`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140c81944`

## callees

- `0x14046c370`
- `0x140634644`
- `0x1406877f8`
- `0x1406f7380`
- `0x1407cbe48`
- `0x1409e3990`
- `0x140a04560`
- `0x140c7f280`
- `0x140c7fd40`

## string_xrefs

- `0x140c7fd75`: `lpacCom`
- `0x140c7fd88`: `lpacCryptoServices`
- `0x140c7fd93`: `lpacIdentityServices`
- `0x140c7fe4b`: `lpacDeviceAccess`
- `0x140c7fdcd`: `registryRead`
- `0x140c7fddb`: `lpacServicesManagement`
- `0x140c7fea1`: `isolatedWin32-promptForAccess`
- `0x140c7feaf`: `isolatedWin32-accessToPublisherDirectory`
- `0x140c7fe6f`: `sessionImpersonation`
- `0x140c7fe7a`: `constrainedImpersonation`

## pseudocode

```c
bool SepVariableInitialization()
{
  int v0; // edx
  bool v1; // al
  void *v2; // rax
  _DWORD *v3; // r12
  _DWORD *v4; // r13
  _DWORD *v5; // r15
  _DWORD *v6; // r14
  _DWORD *v7; // rsi
  _DWORD *v8; // rdi
  _DWORD *v9; // rbx
  _DWORD *v10; // rax
  ULONG v11; // eax
  _DWORD *v12; // r12
  _DWORD *v13; // r13
  _DWORD *v14; // r15
  _DWORD *v15; // r14
  _DWORD *v16; // rsi
  _DWORD *v17; // rdi
  _DWORD *v18; // rbx
  __int64 v19; // r10
  __int64 v20; // r9
  ULONG_PTR v21; // r8
  _DWORD *v22; // rdx
  _DWORD *v23; // rcx
  _DWORD *v24; // rax
  PSID v25; // rdx
  _DWORD *v26; // rbx
  _DWORD *v27; // rax
  _DWORD *v28; // rax
  _DWORD *v29; // rax
  _DWORD *v30; // rax
  _DWORD *v31; // rax
  _DWORD *v32; // rax
  _DWORD *v33; // rax
  _DWORD *v34; // rax
  PSID v35; // r8
  PSID v36; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v38; // rcx
  __int64 v39; // rax
  _DWORD *v41; // [rsp+20h] [rbp-E0h]
  __int64 v42; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v43; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  __int64 IdentifierAuthority; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  ULONG_PTR v50; // [rsp+68h] [rbp-98h]
  __int64 v51; // [rsp+70h] [rbp-90h]
  __int64 v52; // [rsp+78h] [rbp-88h]
  __int64 v53; // [rsp+80h] [rbp-80h]
  __int64 v54; // [rsp+88h] [rbp-78h]
  __int64 v55; // [rsp+90h] [rbp-70h]
  __int64 v56; // [rsp+98h] [rbp-68h]
  __int64 v57; // [rsp+A0h] [rbp-60h]
  __int64 v58; // [rsp+A8h] [rbp-58h]
  __int64 v59; // [rsp+B0h] [rbp-50h]
  UNICODE_STRING String2; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING v61; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING v62; // [rsp+D8h] [rbp-28h] BYREF
  UNICODE_STRING v63; // [rsp+E8h] [rbp-18h] BYREF
  UNICODE_STRING v64; // [rsp+F8h] [rbp-8h] BYREF
  UNICODE_STRING v65; // [rsp+108h] [rbp+8h] BYREF
  UNICODE_STRING v66; // [rsp+118h] [rbp+18h] BYREF
  UNICODE_STRING v67; // [rsp+128h] [rbp+28h] BYREF
  UNICODE_STRING v68; // [rsp+138h] [rbp+38h] BYREF
  UNICODE_STRING v69; // [rsp+148h] [rbp+48h] BYREF
  UNICODE_STRING v70; // [rsp+158h] [rbp+58h] BYREF
  UNICODE_STRING v71; // [rsp+168h] [rbp+68h] BYREF
  UNICODE_STRING v72; // [rsp+178h] [rbp+78h] BYREF
  UNICODE_STRING v73; // [rsp+188h] [rbp+88h] BYREF
  UNICODE_STRING v74; // [rsp+198h] [rbp+98h] BYREF
  UNICODE_STRING v75; // [rsp+1A8h] [rbp+A8h] BYREF
  UNICODE_STRING v76; // [rsp+1B8h] [rbp+B8h] BYREF
  UNICODE_STRING v77; // [rsp+1C8h] [rbp+C8h] BYREF
  UNICODE_STRING v78; // [rsp+1D8h] [rbp+D8h] BYREF
  UNICODE_STRING v79; // [rsp+1E8h] [rbp+E8h] BYREF
  UNICODE_STRING v80; // [rsp+1F8h] [rbp+F8h] BYREF
  UNICODE_STRING v81; // [rsp+208h] [rbp+108h] BYREF
  UNICODE_STRING v82; // [rsp+218h] [rbp+118h] BYREF
  UNICODE_STRING v83; // [rsp+228h] [rbp+128h] BYREF
  UNICODE_STRING v84; // [rsp+238h] [rbp+138h] BYREF
  UNICODE_STRING v85; // [rsp+248h] [rbp+148h] BYREF
  _DWORD *v86; // [rsp+258h] [rbp+158h]
  _DWORD *v87; // [rsp+260h] [rbp+160h]
  _DWORD *v88; // [rsp+268h] [rbp+168h]
  _DWORD *v89; // [rsp+270h] [rbp+170h]
  _DWORD *v90; // [rsp+278h] [rbp+178h]
  _DWORD *v91; // [rsp+280h] [rbp+180h]
  ULONG Size; // [rsp+2E0h] [rbp+1E0h]
  ULONG BugCheckParameter2; // [rsp+2E8h] [rbp+1E8h]
  _DWORD *BugCheckParameter2a; // [rsp+2E8h] [rbp+1E8h]
  ULONG v95; // [rsp+2F0h] [rbp+1F0h]
  _DWORD *v96; // [rsp+2F0h] [rbp+1F0h]
  ULONG v97; // [rsp+2F8h] [rbp+1F8h]
  _DWORD *v98; // [rsp+2F8h] [rbp+1F8h]

  *(_QWORD *)&String2.Length = 2359330;
  String2.Buffer = L"lpacAppExperience";
  *(_QWORD *)&v67.Length = 1048590;
  v67.Buffer = L"lpacCom";
  v68.Buffer = L"lpacCryptoServices";
  v69.Buffer = L"lpacIdentityServices";
  v70.Buffer = L"lpacInstrumentation";
  v71.Buffer = L"lpacEnterprisePolicyChangeNotifications";
  v66.Buffer = L"lpacMedia";
  v72.Buffer = L"lpacPnpNotifications";
  v73.Buffer = L"registryRead";
  v74.Buffer = L"lpacServicesManagement";
  v75.Buffer = L"lpacSessionManagement";
  v76.Buffer = L"lpacPrinting";
  v77.Buffer = L"lpacWebPlatform";
  v78.Buffer = L"lpacPayments";
  v79.Buffer = L"lpacClipboard";
  v80.Buffer = L"lpacIME";
  v81.Buffer = L"lpacPackageManagerOperation";
  v82.Buffer = L"lpacDeviceAccess";
  v62.Buffer = L"learningModeLogging";
  v63.Buffer = L"permissiveLearningMode";
  v65.Buffer = L"sessionImpersonation";
  v64.Buffer = L"constrainedImpersonation";
  v83.Buffer = L"isolatedWin32-volumeRootMinimal";
  v84.Buffer = L"isolatedWin32-profilesRootMinimal";
  v85.Buffer = L"isolatedWin32-promptForAccess";
  v61.Buffer = L"isolatedWin32-accessToPublisherDirectory";
  LODWORD(IdentifierAuthority) = dword_141203188;
  *(_QWORD *)&v68.Length = 2490404;
  *(_QWORD *)&v69.Length = 2752552;
  *(_QWORD *)&v70.Length = 2621478;
  *(_QWORD *)&v71.Length = 5242958;
  *(_QWORD *)&v66.Length = 1310738;
  *(_QWORD *)&v72.Length = 2752552;
  *(_QWORD *)&v73.Length = 1703960;
  *(_QWORD *)&v74.Length = 3014700;
  *(_QWORD *)&v75.Length = 2883626;
  *(_QWORD *)&v76.Length = 1703960;
  *(_QWORD *)&v77.Length = 2097182;
  *(_QWORD *)&v78.Length = 1703960;
  *(_QWORD *)&v79.Length = 1835034;
  *(_QWORD *)&v80.Length = 1048590;
  *(_QWORD *)&v81.Length = 3670070;
  *(_QWORD *)&v82.Length = 2228256;
  *(_QWORD *)&v62.Length = 2621478;
  *(_QWORD *)&v63.Length = 3014700;
  *(_QWORD *)&v65.Length = 2752552;
  *(_QWORD *)&v64.Length = 3276848;
  *(_QWORD *)&v83.Length = 4194366;
  *(_QWORD *)&v84.Length = 4456514;
  *(_QWORD *)&v85.Length = 3932218;
  *(_QWORD *)&v61.Length = 5374032;
  WORD2(IdentifierAuthority) = word_14120318C;
  LODWORD(v48) = dword_141203190;
  WORD2(v48) = word_141203194;
  LODWORD(v49) = dword_141203198;
  WORD2(v49) = word_14120319C;
  LODWORD(v44) = dword_1412031A0;
  WORD2(v44) = word_1412031A4;
  LODWORD(v42) = dword_1412031A8;
  WORD2(v42) = word_1412031AC;
  LODWORD(v45) = dword_1412031B0;
  WORD2(v45) = word_1412031B4;
  LODWORD(v46) = dword_1412031B8;
  WORD2(v46) = word_1412031BC;
  LODWORD(v43) = dword_1412031C0;
  WORD2(v43) = word_1412031C4;
  v0 = *(_DWORD *)(*(_QWORD *)(KeLoaderBlock_0 + 240) + 132LL);
  v1 = (v0 & 0x40) == 0 && MEMORY[0xFFFFF78000000264] == 1 && MEMORY[0xFFFFF78000000310] <= 0x83400u;
  SepTokenSidSharingEnabled = v1;
  SepOsLoaderTpmDriverLoaded = (v0 & 0x80) != 0;
  SepTokenCapabilitySidSharingEnabled = v1;
  BugCheckParameter2 = RtlLengthRequiredSid(1u);
  v95 = RtlLengthRequiredSid(2u);
  Size = RtlLengthRequiredSid(6u);
  LODWORD(v50) = RtlLengthRequiredSid(9u);
  v97 = RtlLengthRequiredSid(0xAu);
  SeNullSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeCreatorOwnerSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeCreatorGroupSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeCreatorOwnerServerSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeCreatorGroupServerSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeWorldSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeLocalSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  v2 = (void *)ExKdproPoolAllocate(BugCheckParameter2);
  v3 = SeNullSid;
  SeOwnerRightsSid = v2;
  RtlInitializeSid(SeNullSid, (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority, 1u);
  v4 = SeWorldSid;
  RtlInitializeSid(SeWorldSid, (PSID_IDENTIFIER_AUTHORITY)&v48, 1u);
  v5 = SeLocalSid;
  RtlInitializeSid(SeLocalSid, (PSID_IDENTIFIER_AUTHORITY)&v49, 1u);
  v6 = SeCreatorOwnerSid;
  RtlInitializeSid(SeCreatorOwnerSid, (PSID_IDENTIFIER_AUTHORITY)&v44, 1u);
  v7 = SeCreatorGroupSid;
  RtlInitializeSid(SeCreatorGroupSid, (PSID_IDENTIFIER_AUTHORITY)&v44, 1u);
  v8 = SeCreatorOwnerServerSid;
  RtlInitializeSid(SeCreatorOwnerServerSid, (PSID_IDENTIFIER_AUTHORITY)&v44, 1u);
  v9 = SeCreatorGroupServerSid;
  RtlInitializeSid(SeCreatorGroupServerSid, (PSID_IDENTIFIER_AUTHORITY)&v44, 1u);
  RtlInitializeSid(SeOwnerRightsSid, (PSID_IDENTIFIER_AUTHORITY)&v44, 1u);
  v3[2] = 0;
  v4[2] = 0;
  v5[2] = 0;
  v6[2] = 0;
  v10 = SeOwnerRightsSid;
  v7[2] = 1;
  v8[2] = 2;
  v9[2] = 3;
  v10[2] = 4;
  v11 = RtlLengthRequiredSid(0);
  SeNtAuthoritySid = (PSID)ExKdproPoolAllocate(v11);
  SeDialupSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeNetworkSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeBatchSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeInteractiveSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SePrincipalSelfSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeServiceSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeLocalSystemSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeAuthenticatedUsersSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeRestrictedSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeAnonymousLogonSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeLocalServiceSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeNetworkServiceSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeIUserSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeAliasAdminsSid = (PSID)ExKdproPoolAllocate(v95);
  SeAliasUsersSid = (PSID)ExKdproPoolAllocate(v95);
  SeAliasGuestsSid = (PSID)ExKdproPoolAllocate(v95);
  SeAliasPowerUsersSid = (PSID)ExKdproPoolAllocate(v95);
  SeAliasAccountOpsSid = (PSID)ExKdproPoolAllocate(v95);
  SeAliasSystemOpsSid = (PSID)ExKdproPoolAllocate(v95);
  SeAliasPrintOpsSid = (PSID)ExKdproPoolAllocate(v95);
  SeAliasBackupOpsSid = (PSID)ExKdproPoolAllocate(v95);
  SeUntrustedMandatorySid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeLowMandatorySid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeMediumMandatorySid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeHighMandatorySid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeSystemMandatorySid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SePackagePrefixSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeCapabilityPrefixSid = (PSID)ExKdproPoolAllocate(BugCheckParameter2);
  SeAllAppPackagesSid = (PSID)ExKdproPoolAllocate(v95);
  SeAllRestrictedAppPackagesSid = (PSID)ExKdproPoolAllocate(v95);
  SeLpacAppExperienceCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacComCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacCryptoServicesCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacIdentityServicesCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacInstrumentationCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacEnterprisePolicyChangeNotificationsCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacMediaCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacPnpNotificationsCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeRegistryReadCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacServicesManagementCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacSessionManagementCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacPrintingCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacWebPlatformCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacPaymentsCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacClipboardCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacImeCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacPackageManagerOperationCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeLpacDeviceAccessCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeUserModeDriversSid = (PSID)ExKdproPoolAllocate(Size);
  SeTrustedInstallerSid = (PSID)ExKdproPoolAllocate(Size);
  SeProcTrustWinTcbSid = (PSID)ExKdproPoolAllocate(v95);
  SeProcTrustWinSid = (PSID)ExKdproPoolAllocate(v95);
  SeProcTrustAuthenticodeSid = (PSID)ExKdproPoolAllocate(v95);
  SeProcTrustLiteAntimalwareSid = (PSID)ExKdproPoolAllocate(v95);
  SeProcTrustLiteWinTcbSid = (PSID)ExKdproPoolAllocate(v95);
  SeProcTrustLiteWinSid = (PSID)ExKdproPoolAllocate(v95);
  SeProcTrustLiteAppSid = (PSID)ExKdproPoolAllocate(v95);
  SeProcTrustNoneSid = (PSID)ExKdproPoolAllocate(v95);
  SeDefaultAccountAliasSid = (PSID)ExKdproPoolAllocate(v95);
  SeLearningModeLoggingCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SePermissiveLearningModeCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeConstrainedImpersonationCapabilityGroupSid = (PSID)ExKdproPoolAllocate((unsigned int)v50);
  SeConstrainedImpersonationCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeSessionImpersonationCapabilityGroupSid = (PSID)ExKdproPoolAllocate((unsigned int)v50);
  SeSessionImpersonationCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeAppSiloSid = (PSID)ExKdproPoolAllocate(v95);
  SeAppSiloVolumeRootMinimalCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeAppSiloProfilesRootMinimalCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeAppSiloPromptForAccessCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  SeAppSiloAccessToPublisherDirectoryCapabilitySid = (PSID)ExKdproPoolAllocate(v97);
  RtlInitializeSid(SeNtAuthoritySid, (PSID_IDENTIFIER_AUTHORITY)&v42, 0);
  v98 = SeDialupSid;
  RtlInitializeSid(SeDialupSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v41 = SeNetworkSid;
  RtlInitializeSid(SeNetworkSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v59 = (__int64)SeBatchSid;
  RtlInitializeSid(SeBatchSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v58 = (__int64)SeInteractiveSid;
  RtlInitializeSid(SeInteractiveSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v57 = (__int64)SeServiceSid;
  RtlInitializeSid(SeServiceSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v56 = (__int64)SePrincipalSelfSid;
  RtlInitializeSid(SePrincipalSelfSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v55 = (__int64)SeLocalSystemSid;
  RtlInitializeSid(SeLocalSystemSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v54 = (__int64)SeAuthenticatedUsersSid;
  RtlInitializeSid(SeAuthenticatedUsersSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v53 = (__int64)SeRestrictedSid;
  RtlInitializeSid(SeRestrictedSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v52 = (__int64)SeAnonymousLogonSid;
  RtlInitializeSid(SeAnonymousLogonSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v51 = (__int64)SeLocalServiceSid;
  RtlInitializeSid(SeLocalServiceSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v49 = (__int64)SeNetworkServiceSid;
  RtlInitializeSid(SeNetworkServiceSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  v48 = (__int64)SeIUserSid;
  RtlInitializeSid(SeIUserSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 1u);
  BugCheckParameter2a = SeAliasAdminsSid;
  RtlInitializeSid(SeAliasAdminsSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 2u);
  v96 = SeAliasUsersSid;
  RtlInitializeSid(SeAliasUsersSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 2u);
  IdentifierAuthority = (__int64)SeAliasGuestsSid;
  RtlInitializeSid(SeAliasGuestsSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 2u);
  v44 = (__int64)SeAliasPowerUsersSid;
  RtlInitializeSid(SeAliasPowerUsersSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 2u);
  v50 = (ULONG_PTR)SeAliasAccountOpsSid;
  RtlInitializeSid(SeAliasAccountOpsSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 2u);
  v91 = SeAliasSystemOpsSid;
  RtlInitializeSid(SeAliasSystemOpsSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 2u);
  v86 = SeAliasPrintOpsSid;
  RtlInitializeSid(SeAliasPrintOpsSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 2u);
  v87 = SeAliasBackupOpsSid;
  RtlInitializeSid(SeAliasBackupOpsSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 2u);
  RtlInitializeSid(SeTrustedInstallerSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 6u);
  v88 = SeUntrustedMandatorySid;
  RtlInitializeSid(SeUntrustedMandatorySid, (PSID_IDENTIFIER_AUTHORITY)&v45, 1u);
  v89 = SeLowMandatorySid;
  RtlInitializeSid(SeLowMandatorySid, (PSID_IDENTIFIER_AUTHORITY)&v45, 1u);
  v90 = SeMediumMandatorySid;
  RtlInitializeSid(SeMediumMandatorySid, (PSID_IDENTIFIER_AUTHORITY)&v45, 1u);
  v12 = SeHighMandatorySid;
  RtlInitializeSid(SeHighMandatorySid, (PSID_IDENTIFIER_AUTHORITY)&v45, 1u);
  v13 = SeSystemMandatorySid;
  RtlInitializeSid(SeSystemMandatorySid, (PSID_IDENTIFIER_AUTHORITY)&v45, 1u);
  v14 = SePackagePrefixSid;
  RtlInitializeSid(SePackagePrefixSid, (PSID_IDENTIFIER_AUTHORITY)&v46, 1u);
  v15 = SeCapabilityPrefixSid;
  RtlInitializeSid(SeCapabilityPrefixSid, (PSID_IDENTIFIER_AUTHORITY)&v46, 1u);
  v16 = SeAllAppPackagesSid;
  RtlInitializeSid(SeAllAppPackagesSid, (PSID_IDENTIFIER_AUTHORITY)&v46, 2u);
  v17 = SeAllRestrictedAppPackagesSid;
  RtlInitializeSid(SeAllRestrictedAppPackagesSid, (PSID_IDENTIFIER_AUTHORITY)&v46, 2u);
  memset_0(SeUserModeDriversSid, 0, Size);
  RtlInitializeSid(SeUserModeDriversSid, (PSID_IDENTIFIER_AUTHORITY)&v42, 6u);
  RtlInitializeSid(SeProcTrustNoneSid, (PSID_IDENTIFIER_AUTHORITY)&v43, 2u);
  RtlInitializeSid(SeProcTrustWinTcbSid, (PSID_IDENTIFIER_AUTHORITY)&v43, 2u);
  RtlInitializeSid(SeProcTrustWinSid, (PSID_IDENTIFIER_AUTHORITY)&v43, 2u);
  RtlInitializeSid(SeProcTrustAuthenticodeSid, (PSID_IDENTIFIER_AUTHORITY)&v43, 2u);
  RtlInitializeSid(SeProcTrustLiteAntimalwareSid, (PSID_IDENTIFIER_AUTHORITY)&v43, 2u);
  RtlInitializeSid(SeProcTrustLiteWinTcbSid, (PSID_IDENTIFIER_AUTHORITY)&v43, 2u);
  RtlInitializeSid(SeProcTrustLiteWinSid, (PSID_IDENTIFIER_AUTHORITY)&v43, 2u);
  RtlInitializeSid(SeProcTrustLiteAppSid, (PSID_IDENTIFIER_AUTHORITY)&v43, 2u);
  v18 = SeAppSiloSid;
  RtlInitializeSid(SeAppSiloSid, (PSID_IDENTIFIER_AUTHORITY)&v46, 2u);
  v98[2] = 1;
  v41[2] = 2;
  *(_DWORD *)(v59 + 8) = 3;
  *(_DWORD *)(v58 + 8) = 4;
  *(_DWORD *)(v57 + 8) = 6;
  *(_DWORD *)(v56 + 8) = 10;
  *(_DWORD *)(v55 + 8) = 18;
  *(_DWORD *)(v54 + 8) = 11;
  *(_DWORD *)(v53 + 8) = 12;
  *(_DWORD *)(v52 + 8) = 7;
  *(_DWORD *)(v51 + 8) = 19;
  *(_DWORD *)(v49 + 8) = 20;
  *(_DWORD *)(v48 + 8) = 17;
  BugCheckParameter2a[2] = 32;
  v19 = IdentifierAuthority;
  v20 = v44;
  v21 = v50;
  v22 = v91;
  v23 = v86;
  v96[2] = 32;
  *(_DWORD *)(v19 + 8) = 32;
  *(_DWORD *)(v20 + 8) = 32;
  *(_DWORD *)(v21 + 8) = 32;
  v22[2] = 32;
  v23[2] = 32;
  v24 = v87;
  v87[2] = 32;
  BugCheckParameter2a[3] = 544;
  v96[3] = 545;
  *(_DWORD *)(v19 + 12) = 546;
  *(_DWORD *)(v20 + 12) = 547;
  *(_DWORD *)(v21 + 12) = 548;
  v22[3] = 549;
  v25 = SeConstrainedImpersonationCapabilityGroupSid;
  v23[3] = 550;
  v24[3] = 551;
  v88[2] = 0;
  v89[2] = 4096;
  v90[2] = 0x2000;
  v12[2] = 12288;
  v13[2] = 0x4000;
  v14[2] = 2;
  v15[2] = 3;
  v16[2] = 2;
  v16[3] = 1;
  v17[2] = 2;
  v17[3] = 2;
  v18[2] = 3;
  v18[3] = 0x10000;
  if ( (int)RtlDeriveCapabilitySidsFromName(&String2, v25, SeLpacAppExperienceCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(&v67, SeConstrainedImpersonationCapabilityGroupSid, SeLpacComCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v68,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacCryptoServicesCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v69,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacIdentityServicesCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v70,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacInstrumentationCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v71,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacEnterprisePolicyChangeNotificationsCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v66,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacMediaCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v72,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacPnpNotificationsCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v73,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeRegistryReadCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v74,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacServicesManagementCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v75,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacSessionManagementCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v76,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacPrintingCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v77,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacWebPlatformCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v78,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacPaymentsCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v79,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacClipboardCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(&v80, SeConstrainedImpersonationCapabilityGroupSid, SeLpacImeCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v81,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacPackageManagerOperationCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v82,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeLpacDeviceAccessCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v83,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeAppSiloVolumeRootMinimalCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v84,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeAppSiloProfilesRootMinimalCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v85,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeAppSiloPromptForAccessCapabilitySid) < 0 )
    return 0;
  if ( (int)RtlDeriveCapabilitySidsFromName(
              &v61,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeAppSiloAccessToPublisherDirectoryCapabilitySid) < 0 )
    return 0;
  v26 = SeDefaultAccountAliasSid;
  *((_DWORD *)SeUserModeDriversSid + 2) = 84;
  *((_QWORD *)SeProcTrustNoneSid + 1) = 0;
  v27 = SeProcTrustWinTcbSid;
  *((_DWORD *)SeProcTrustWinTcbSid + 2) = 1024;
  v27[3] = 0x2000;
  v28 = SeProcTrustWinSid;
  *((_DWORD *)SeProcTrustWinSid + 2) = 1024;
  v28[3] = 4096;
  v29 = SeProcTrustAuthenticodeSid;
  *((_DWORD *)SeProcTrustAuthenticodeSid + 2) = 1024;
  v29[3] = 1024;
  v30 = SeProcTrustLiteAntimalwareSid;
  *((_DWORD *)SeProcTrustLiteAntimalwareSid + 2) = 512;
  v30[3] = 1536;
  v31 = SeProcTrustLiteWinTcbSid;
  *((_DWORD *)SeProcTrustLiteWinTcbSid + 2) = 512;
  v31[3] = 0x2000;
  v32 = SeProcTrustLiteWinSid;
  *((_DWORD *)SeProcTrustLiteWinSid + 2) = 512;
  v32[3] = 4096;
  v33 = SeProcTrustLiteAppSid;
  *((_DWORD *)SeProcTrustLiteAppSid + 2) = 512;
  v33[3] = 2048;
  v34 = SeTrustedInstallerSid;
  *((_DWORD *)SeTrustedInstallerSid + 2) = 80;
  v34[3] = 956008885;
  v34[4] = -876444647;
  v34[5] = 1831038044;
  v34[6] = 1853292631;
  v34[7] = -2023488832;
  RtlInitializeSid(v26, (PSID_IDENTIFIER_AUTHORITY)&v42, 2u);
  v35 = SeLearningModeLoggingCapabilitySid;
  v36 = SeConstrainedImpersonationCapabilityGroupSid;
  v26[2] = 32;
  v26[3] = 581;
  if ( (int)RtlDeriveCapabilitySidsFromName(&v62, v36, v35) < 0
    || (int)RtlDeriveCapabilitySidsFromName(
              &v63,
              SeConstrainedImpersonationCapabilityGroupSid,
              SePermissiveLearningModeCapabilitySid) < 0
    || (int)RtlDeriveCapabilitySidsFromName(
              &v64,
              SeConstrainedImpersonationCapabilityGroupSid,
              SeConstrainedImpersonationCapabilitySid) < 0
    || (int)RtlDeriveCapabilitySidsFromName(
              &v65,
              SeSessionImpersonationCapabilityGroupSid,
              SeSessionImpersonationCapabilitySid) < 0 )
  {
    return 0;
  }
  SepInitSystemDacls();
  SeCreateTokenPrivilege = (LUID)2LL;
  SeAssignPrimaryTokenPrivilege = (LUID)3LL;
  SeLockMemoryPrivilege = (LUID)4LL;
  SeIncreaseQuotaPrivilege = (LUID)5LL;
  v49 = 6;
  SeUnsolicitedInputPrivilege = 6;
  v48 = 7;
  SeTcbPrivilege = (LUID)7LL;
  IdentifierAuthority = 8;
  SeSecurityPrivilege = (LUID)8LL;
  v46 = 9;
  SeTakeOwnershipPrivilege = 9;
  v45 = 10;
  SeLoadDriverPrivilege = (LUID)10LL;
  v44 = 15;
  SeCreatePagefilePrivilege = (LUID)15LL;
  v43 = 14;
  SeIncreaseBasePriorityPrivilege = (LUID)14LL;
  v42 = 11;
  SeSystemProfilePrivilege = (LUID)11LL;
  v50 = 12;
  SeSystemtimePrivilege = (LUID)12LL;
  v51 = 13;
  SeProfileSingleProcessPrivilege = (LUID)13LL;
  v52 = 16;
  SeCreatePermanentPrivilege = (LUID)16LL;
  v53 = 17;
  SeBackupPrivilege = (LUID)17LL;
  v54 = 18;
  SeRestorePrivilege = (LUID)18LL;
  v55 = 19;
  SeShutdownPrivilege = (LUID)19LL;
  v56 = 20;
  SeDebugPrivilege = (LUID)20LL;
  v57 = 21;
  v58 = 22;
  v59 = 23;
  SeAuditPrivilege = 21;
  SeSystemEnvironmentPrivilege = (LUID)22LL;
  SeChangeNotifyPrivilege = 23;
  SeRemoteShutdownPrivilege = 24;
  SeUndockPrivilege = 25;
  SeSyncAgentPrivilege = 26;
  SeEnableDelegationPrivilege = 27;
  qword_141203848 = (__int64)SeNullSid;
  qword_141203850 = (__int64)SeWorldSid;
  qword_141203858 = (__int64)SeLocalSid;
  qword_141203860 = (__int64)SeCreatorOwnerSid;
  qword_141203868 = (__int64)SeCreatorGroupSid;
  qword_141203990 = (__int64)SeOwnerRightsSid;
  qword_141203870 = (__int64)SeNtAuthoritySid;
  qword_141203878 = (__int64)SeDialupSid;
  qword_141203880 = (__int64)SeNetworkSid;
  qword_141203888 = (__int64)SeBatchSid;
  qword_141203890 = (__int64)SeInteractiveSid;
  qword_141203898 = (__int64)SeLocalSystemSid;
  qword_1412038E0 = (__int64)SeAuthenticatedUsersSid;
  qword_1412038E8 = (__int64)SeRestrictedSid;
  qword_1412038F0 = (__int64)SeAnonymousLogonSid;
  qword_141203910 = (__int64)SeLocalServiceSid;
  qword_141203918 = (__int64)SeNetworkServiceSid;
  qword_141203960 = (__int64)SeIUserSid;
  qword_1412038A0 = (__int64)SeAliasAdminsSid;
  qword_1412038A8 = (__int64)SeAliasUsersSid;
  qword_1412038B0 = (__int64)SeAliasGuestsSid;
  qword_1412038B8 = (__int64)SeAliasPowerUsersSid;
  qword_1412038C0 = (__int64)SeAliasAccountOpsSid;
  qword_1412038C8 = (__int64)SeAliasSystemOpsSid;
  qword_1412038D0 = (__int64)SeAliasPrintOpsSid;
  qword_1412038D8 = (__int64)SeAliasBackupOpsSid;
  qword_141203968 = (__int64)SeUntrustedMandatorySid;
  qword_141203970 = (__int64)SeLowMandatorySid;
  SeManageVolumePrivilege = 28;
  SeImpersonatePrivilege = 29;
  SeCreateGlobalPrivilege = (LUID)30LL;
  SeTrustedCredManAccessPrivilege = 31;
  SeRelabelPrivilege = 32;
  SeIncreaseWorkingSetPrivilege = 33;
  SeTimeZonePrivilege = (LUID)34LL;
  SeCreateSymbolicLinkPrivilege = 35;
  SeDelegateSessionUserImpersonatePrivilege = 36;
  qword_141203978 = (__int64)SeMediumMandatorySid;
  qword_141203980 = (__int64)SeHighMandatorySid;
  qword_141203988 = (__int64)SeSystemMandatorySid;
  qword_141203998 = (__int64)SeAllAppPackagesSid;
  qword_1412039A0 = (__int64)SeUserModeDriversSid;
  qword_1412039A8 = (__int64)SeProcTrustWinTcbSid;
  qword_1412039B0 = (__int64)SeTrustedInstallerSid;
  qword_1412039C0 = (__int64)SeAppSiloSid;
  SepExports = 2;
  qword_141203798 = 3;
  qword_1412037A0 = 4;
  qword_1412037A8 = 5;
  qword_1412037B0 = 6;
  qword_1412037B8 = 7;
  qword_1412037C0 = 8;
  qword_1412037C8 = 9;
  qword_1412037D0 = 10;
  qword_1412037D8 = 15;
  qword_1412037E0 = 14;
  qword_1412037E8 = 11;
  qword_1412037F0 = 12;
  qword_1412037F8 = 13;
  qword_141203800 = 16;
  qword_141203808 = 17;
  qword_141203810 = 18;
  qword_141203818 = 19;
  qword_1412039B8 = 36;
  qword_141203820 = 20;
  qword_1412039C8 = (__int64)SeAppSiloVolumeRootMinimalCapabilitySid;
  qword_141203828 = 21;
  qword_1412039D0 = (__int64)SeAppSiloProfilesRootMinimalCapabilitySid;
  qword_141203830 = 22;
  qword_1412039D8 = (__int64)SeAppSiloPromptForAccessCapabilitySid;
  qword_141203838 = 23;
  qword_141203840 = 24;
  qword_1412038F8 = 25;
  qword_141203900 = 26;
  qword_141203908 = 27;
  qword_141203920 = 28;
  qword_141203928 = 29;
  qword_141203930 = 30;
  qword_141203938 = 31;
  qword_141203940 = 32;
  qword_141203948 = 33;
  qword_141203950 = 34;
  qword_141203958 = 35;
  qword_1412039E0 = (__int64)SeAppSiloAccessToPublisherDirectoryCapabilitySid;
  if ( (Feature_AgenticAppContainerBfsSupport__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_AgenticAppContainerBfsSupport__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
    qword_1412039E8 = (__int64)SeAllRestrictedAppPackagesSid;
  v38 = 0;
  SeExports = (PSE_EXPORTS)&SepExports;
  v39 = 0;
  do
  {
    ++v38;
    LOBYTE(g_SessionLowboxArray[v39 + 4]) = 0;
    g_SessionLowboxArray[v39 + 3] = 0;
    g_SessionLowboxArray[v39] = 0;
    v39 += 5;
  }
  while ( v38 != 5 );
  LowboxSessionMapLock = 0;
  g_SessionLowboxMap = 0;
  return (int)SepInitializeSharedSidMap(5, g_SessionLowboxArray) >= 0;
}

```

## disassembly

```asm
0x140c7fd40  push    rbp
0x140c7fd42  push    rbx
0x140c7fd43  push    rsi
0x140c7fd44  push    rdi
0x140c7fd45  push    r12
0x140c7fd47  push    r13
0x140c7fd49  push    r14
0x140c7fd4b  push    r15
0x140c7fd4d  lea     rbp, [rsp-198h]
0x140c7fd55  sub     rsp, 298h
0x140c7fd5c  lea     rax, aLpacappexperie; "lpacAppExperience"
0x140c7fd63  mov     qword ptr [rbp+1D0h+String2.Length], 240022h
0x140c7fd6b  mov     [rbp+1D0h+String2.Buffer], rax
0x140c7fd6f  mov     r8d, 40h ; '@'
0x140c7fd75  lea     rax, aLpaccom; "lpacCom"
0x140c7fd7c  mov     qword ptr [rbp+1D0h+var_1A8.Length], 10000Eh
0x140c7fd84  mov     [rbp+1D0h+var_1A8.Buffer], rax
0x140c7fd88  lea     rax, aLpaccryptoserv; "lpacCryptoServices"
0x140c7fd8f  mov     [rbp+1D0h+var_198.Buffer], rax
0x140c7fd93  lea     rax, aLpacidentityse; "lpacIdentityServices"
0x140c7fd9a  mov     [rbp+1D0h+var_188.Buffer], rax
0x140c7fd9e  lea     rax, aLpacinstrument_0; "lpacInstrumentation"
0x140c7fda5  mov     [rbp+1D0h+var_178.Buffer], rax
0x140c7fda9  lea     rax, aLpacenterprise; "lpacEnterprisePolicyChangeNotifications"
0x140c7fdb0  mov     [rbp+1D0h+var_168.Buffer], rax
0x140c7fdb4  lea     rax, aLpacmedia; "lpacMedia"
0x140c7fdbb  mov     [rbp+1D0h+var_1B8.Buffer], rax
0x140c7fdbf  lea     rax, aLpacpnpnotific; "lpacPnpNotifications"
0x140c7fdc6  mov     [rbp+1D0h+var_158.Buffer], rax
0x140c7fdcd  lea     rax, aRegistryread_0; "registryRead"
0x140c7fdd4  mov     [rbp+1D0h+var_148.Buffer], rax
0x140c7fddb  lea     rax, aLpacservicesma; "lpacServicesManagement"
0x140c7fde2  mov     [rbp+1D0h+var_138.Buffer], rax
0x140c7fde9  lea     rax, aLpacsessionman; "lpacSessionManagement"
0x140c7fdf0  mov     [rbp+1D0h+var_128.Buffer], rax
0x140c7fdf7  lea     rax, aLpacprinting; "lpacPrinting"
0x140c7fdfe  mov     [rbp+1D0h+var_118.Buffer], rax
0x140c7fe05  lea     rax, aLpacwebplatfor; "lpacWebPlatform"
0x140c7fe0c  mov     [rbp+1D0h+var_108.Buffer], rax
0x140c7fe13  lea     rax, aLpacpayments; "lpacPayments"
0x140c7fe1a  mov     [rbp+1D0h+var_F8.Buffer], rax
0x140c7fe21  lea     rax, aLpacclipboard; "lpacClipboard"
0x140c7fe28  mov     [rbp+1D0h+var_E8.Buffer], rax
0x140c7fe2f  lea     rax, aLpacime; "lpacIME"
0x140c7fe36  mov     [rbp+1D0h+var_D8.Buffer], rax
0x140c7fe3d  lea     rax, aLpacpackageman; "lpacPackageManagerOperation"
0x140c7fe44  mov     [rbp+1D0h+var_C8.Buffer], rax
0x140c7fe4b  lea     rax, aLpacdeviceacce; "lpacDeviceAccess"
0x140c7fe52  mov     [rbp+1D0h+var_B8.Buffer], rax
0x140c7fe59  lea     rax, aLearningmodelo; "learningModeLogging"
0x140c7fe60  mov     [rbp+1D0h+var_1F8.Buffer], rax
0x140c7fe64  lea     rax, aPermissivelear; "permissiveLearningMode"
0x140c7fe6b  mov     [rbp+1D0h+var_1E8.Buffer], rax
0x140c7fe6f  lea     rax, aSessionimperso; "sessionImpersonation"
0x140c7fe76  mov     [rbp+1D0h+var_1C8.Buffer], rax
0x140c7fe7a  lea     rax, aConstrainedimp; "constrainedImpersonation"
0x140c7fe81  mov     [rbp+1D0h+var_1D8.Buffer], rax
0x140c7fe85  lea     rax, aIsolatedwin32V; "isolatedWin32-volumeRootMinimal"
0x140c7fe8c  mov     [rbp+1D0h+var_A8.Buffer], rax
0x140c7fe93  lea     rax, aIsolatedwin32P_0; "isolatedWin32-profilesRootMinimal"
0x140c7fe9a  mov     [rbp+1D0h+var_98.Buffer], rax
0x140c7fea1  lea     rax, aIsolatedwin32P; "isolatedWin32-promptForAccess"
0x140c7fea8  mov     [rbp+1D0h+var_88.Buffer], rax
0x140c7feaf  lea     rax, aIsolatedwin32A; "isolatedWin32-accessToPublisherDirector"...
0x140c7feb6  mov     [rbp+1D0h+var_208.Buffer], rax
0x140c7feba  mov     eax, cs:dword_141203188
0x140c7fec0  mov     dword ptr [rsp+2D0h+IdentifierAuthority], eax
0x140c7fec4  mov     qword ptr [rbp+1D0h+var_198.Length], 260024h
0x140c7fecc  mov     qword ptr [rbp+1D0h+var_188.Length], 2A0028h
0x140c7fed4  mov     qword ptr [rbp+1D0h+var_178.Length], 280026h
0x140c7fedc  mov     qword ptr [rbp+1D0h+var_168.Length], 50004Eh
0x140c7fee4  mov     qword ptr [rbp+1D0h+var_1B8.Length], 140012h
0x140c7feec  mov     qword ptr [rbp+1D0h+var_158.Length], 2A0028h
0x140c7fef4  mov     qword ptr [rbp+1D0h+var_148.Length], 1A0018h
0x140c7feff  mov     qword ptr [rbp+1D0h+var_138.Length], 2E002Ch
0x140c7ff0a  mov     qword ptr [rbp+1D0h+var_128.Length], 2C002Ah
0x140c7ff15  mov     qword ptr [rbp+1D0h+var_118.Length], 1A0018h
0x140c7ff20  mov     qword ptr [rbp+1D0h+var_108.Length], 20001Eh
0x140c7ff2b  mov     qword ptr [rbp+1D0h+var_F8.Length], 1A0018h
0x140c7ff36  mov     qword ptr [rbp+1D0h+var_E8.Length], 1C001Ah
0x140c7ff41  mov     qword ptr [rbp+1D0h+var_D8.Length], 10000Eh
0x140c7ff4c  mov     qword ptr [rbp+1D0h+var_C8.Length], 380036h
0x140c7ff57  mov     qword ptr [rbp+1D0h+var_B8.Length], 220020h
0x140c7ff62  mov     qword ptr [rbp+1D0h+var_1F8.Length], 280026h
0x140c7ff6a  mov     qword ptr [rbp+1D0h+var_1E8.Length], 2E002Ch
0x140c7ff72  mov     qword ptr [rbp+1D0h+var_1C8.Length], 2A0028h
0x140c7ff7a  mov     qword ptr [rbp+1D0h+var_1D8.Length], 320030h
0x140c7ff82  mov     qword ptr [rbp+1D0h+var_A8.Length], 40003Eh
0x140c7ff8d  mov     qword ptr [rbp+1D0h+var_98.Length], 440042h
0x140c7ff98  mov     qword ptr [rbp+1D0h+var_88.Length], 3C003Ah
0x140c7ffa3  mov     qword ptr [rbp+1D0h+var_208.Length], 520050h
0x140c7ffab  movzx   eax, cs:word_14120318C
0x140c7ffb2  mov     word ptr [rsp+2D0h+IdentifierAuthority+4], ax
0x140c7ffb7  mov     eax, cs:dword_141203190
0x140c7ffbd  mov     dword ptr [rsp+2D0h+var_278], eax
0x140c7ffc1  movzx   eax, cs:word_141203194
0x140c7ffc8  mov     word ptr [rsp+2D0h+var_278+4], ax
0x140c7ffcd  mov     eax, cs:dword_141203198
0x140c7ffd3  mov     dword ptr [rsp+2D0h+var_270], eax
0x140c7ffd7  movzx   eax, cs:word_14120319C
0x140c7ffde  mov     word ptr [rsp+2D0h+var_270+4], ax
0x140c7ffe3  mov     eax, cs:dword_1412031A0
0x140c7ffe9  mov     dword ptr [rsp+2D0h+var_298], eax
0x140c7ffed  movzx   eax, cs:word_1412031A4
0x140c7fff4  mov     word ptr [rsp+2D0h+var_298+4], ax
0x140c7fff9  mov     eax, cs:dword_1412031A8
0x140c7ffff  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x140c80003  movzx   eax, cs:word_1412031AC
0x140c8000a  mov     word ptr [rsp+2D0h+var_2A8+4], ax
0x140c8000f  mov     eax, cs:dword_1412031B0
0x140c80015  mov     dword ptr [rsp+2D0h+var_290], eax
0x140c80019  movzx   eax, cs:word_1412031B4
0x140c80020  mov     word ptr [rsp+2D0h+var_290+4], ax
0x140c80025  mov     eax, cs:dword_1412031B8
0x140c8002b  mov     dword ptr [rsp+2D0h+var_288], eax
0x140c8002f  movzx   eax, cs:word_1412031BC
0x140c80036  mov     word ptr [rsp+2D0h+var_288+4], ax
0x140c8003b  mov     eax, cs:dword_1412031C0
0x140c80041  mov     dword ptr [rsp+2D0h+var_2A0], eax
0x140c80045  movzx   eax, cs:word_1412031C4
0x140c8004c  mov     word ptr [rsp+2D0h+var_2A0+4], ax
0x140c80051  mov     rax, cs:KeLoaderBlock_0
0x140c80058  mov     rcx, [rax+0F0h]
0x140c8005f  mov     edx, [rcx+84h]
0x140c80065  test    r8b, dl
0x140c80068  jnz     short loc_140C80090
0x140c8006a  mov     rax, 0FFFFF78000000264h
0x140c80074  cmp     dword ptr [rax], 1
0x140c80077  jnz     short loc_140C80090
0x140c80079  mov     rax, 0FFFFF78000000310h
0x140c80083  cmp     qword ptr [rax], 83400h
0x140c8008a  ja      short loc_140C80090
0x140c8008c  mov     al, 1
0x140c8008e  jmp     short loc_140C80092
0x140c80090  xor     al, al
0x140c80092  shr     edx, 7
0x140c80095  mov     ecx, 1; SubAuthorityCount
0x140c8009a  and     dl, 1
0x140c8009d  mov     cs:SepTokenSidSharingEnabled, al
0x140c800a3  mov     cs:SepOsLoaderTpmDriverLoaded, dl
0x140c800a9  mov     cs:SepTokenCapabilitySidSharingEnabled, al
0x140c800af  call    RtlLengthRequiredSid
0x140c800b4  mov     ecx, 2; SubAuthorityCount
0x140c800b9  mov     dword ptr [rbp+1D0h+BugCheckParameter2], eax
0x140c800bf  mov     ebx, eax
0x140c800c1  call    RtlLengthRequiredSid
0x140c800c6  mov     ecx, 6; SubAuthorityCount
0x140c800cb  mov     dword ptr [rbp+1D0h+arg_10], eax
0x140c800d1  call    RtlLengthRequiredSid
0x140c800d6  mov     ecx, 9; SubAuthorityCount
0x140c800db  mov     dword ptr [rbp+1D0h+Size], eax
0x140c800e1  call    RtlLengthRequiredSid
0x140c800e6  mov     ecx, 0Ah; SubAuthorityCount
0x140c800eb  mov     dword ptr [rsp+2D0h+var_268], eax
0x140c800ef  call    RtlLengthRequiredSid
0x140c800f4  mov     ecx, ebx; BugCheckParameter2
0x140c800f6  mov     dword ptr [rbp+1D0h+arg_18], eax
0x140c800fc  call    ExKdproPoolAllocate
0x140c80101  mov     ecx, ebx; BugCheckParameter2
0x140c80103  mov     cs:SeNullSid, rax
0x140c8010a  call    ExKdproPoolAllocate
0x140c8010f  mov     ecx, ebx; BugCheckParameter2
0x140c80111  mov     cs:SeCreatorOwnerSid, rax
0x140c80118  call    ExKdproPoolAllocate
0x140c8011d  mov     ecx, ebx; BugCheckParameter2
0x140c8011f  mov     cs:SeCreatorGroupSid, rax
0x140c80126  call    ExKdproPoolAllocate
0x140c8012b  mov     ecx, ebx; BugCheckParameter2
0x140c8012d  mov     cs:SeCreatorOwnerServerSid, rax
0x140c80134  call    ExKdproPoolAllocate
0x140c80139  mov     ecx, ebx; BugCheckParameter2
0x140c8013b  mov     cs:SeCreatorGroupServerSid, rax
0x140c80142  call    ExKdproPoolAllocate
0x140c80147  mov     ecx, ebx; BugCheckParameter2
0x140c80149  mov     cs:SeWorldSid, rax
0x140c80150  call    ExKdproPoolAllocate
0x140c80155  mov     ecx, ebx; BugCheckParameter2
0x140c80157  mov     cs:SeLocalSid, rax
0x140c8015e  call    ExKdproPoolAllocate
0x140c80163  mov     r12, cs:SeNullSid
0x140c8016a  lea     rdx, [rsp+2D0h+IdentifierAuthority]; IdentifierAuthority
0x140c8016f  mov     rcx, r12; Sid
0x140c80172  mov     cs:SeOwnerRightsSid, rax
0x140c80179  mov     r8b, 1; SubAuthorityCount
0x140c8017c  call    RtlInitializeSid
0x140c80181  mov     r13, cs:SeWorldSid
0x140c80188  lea     rdx, [rsp+2D0h+var_278]; IdentifierAuthority
0x140c8018d  mov     rcx, r13; Sid
0x140c80190  mov     r8b, 1; SubAuthorityCount
0x140c80193  call    RtlInitializeSid
0x140c80198  mov     r15, cs:SeLocalSid
0x140c8019f  lea     rdx, [rsp+2D0h+var_270]; IdentifierAuthority
0x140c801a4  mov     rcx, r15; Sid
0x140c801a7  mov     r8b, 1; SubAuthorityCount
0x140c801aa  call    RtlInitializeSid
0x140c801af  mov     r14, cs:SeCreatorOwnerSid
0x140c801b6  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c801bb  mov     rcx, r14; Sid
0x140c801be  mov     r8b, 1; SubAuthorityCount
0x140c801c1  call    RtlInitializeSid
0x140c801c6  mov     rsi, cs:SeCreatorGroupSid
0x140c801cd  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c801d2  mov     rcx, rsi; Sid
0x140c801d5  mov     r8b, 1; SubAuthorityCount
0x140c801d8  call    RtlInitializeSid
0x140c801dd  mov     rdi, cs:SeCreatorOwnerServerSid
0x140c801e4  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c801e9  mov     rcx, rdi; Sid
0x140c801ec  mov     r8b, 1; SubAuthorityCount
0x140c801ef  call    RtlInitializeSid
0x140c801f4  mov     rbx, cs:SeCreatorGroupServerSid
0x140c801fb  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c80200  mov     rcx, rbx; Sid
0x140c80203  mov     r8b, 1; SubAuthorityCount
0x140c80206  call    RtlInitializeSid
0x140c8020b  mov     r8b, 1; SubAuthorityCount
0x140c8020e  mov     rcx, cs:SeOwnerRightsSid; Sid
0x140c80215  lea     rdx, [rsp+2D0h+var_298]; IdentifierAuthority
0x140c8021a  call    RtlInitializeSid
0x140c8021f  xor     eax, eax
0x140c80221  xor     ecx, ecx; SubAuthorityCount
0x140c80223  mov     [r12+8], eax
0x140c80228  mov     [r13+8], eax
0x140c8022c  mov     [r15+8], eax
0x140c80230  mov     [r14+8], eax
0x140c80234  mov     rax, cs:SeOwnerRightsSid
0x140c8023b  mov     dword ptr [rsi+8], 1
0x140c80242  mov     dword ptr [rdi+8], 2
0x140c80249  mov     dword ptr [rbx+8], 3
0x140c80250  mov     dword ptr [rax+8], 4
0x140c80257  call    RtlLengthRequiredSid
0x140c8025c  mov     ecx, eax; BugCheckParameter2
0x140c8025e  call    ExKdproPoolAllocate
0x140c80263  mov     ebx, dword ptr [rbp+1D0h+BugCheckParameter2]
0x140c80269  mov     ecx, ebx; BugCheckParameter2
0x140c8026b  mov     cs:SeNtAuthoritySid, rax
0x140c80272  call    ExKdproPoolAllocate
0x140c80277  mov     ecx, ebx; BugCheckParameter2
0x140c80279  mov     cs:SeDialupSid, rax
0x140c80280  call    ExKdproPoolAllocate
0x140c80285  mov     ecx, ebx; BugCheckParameter2
0x140c80287  mov     cs:SeNetworkSid, rax
0x140c8028e  call    ExKdproPoolAllocate
0x140c80293  mov     ecx, ebx; BugCheckParameter2
0x140c80295  mov     cs:SeBatchSid, rax
0x140c8029c  call    ExKdproPoolAllocate
0x140c802a1  mov     ecx, ebx; BugCheckParameter2
0x140c802a3  mov     cs:SeInteractiveSid, rax
0x140c802aa  call    ExKdproPoolAllocate
0x140c802af  mov     ecx, ebx; BugCheckParameter2
0x140c802b1  mov     cs:SePrincipalSelfSid, rax
0x140c802b8  call    ExKdproPoolAllocate
0x140c802bd  mov     ecx, ebx; BugCheckParameter2
0x140c802bf  mov     cs:SeServiceSid, rax
0x140c802c6  call    ExKdproPoolAllocate
0x140c802cb  mov     ecx, ebx; BugCheckParameter2
0x140c802cd  mov     cs:SeLocalSystemSid, rax
0x140c802d4  call    ExKdproPoolAllocate
0x140c802d9  mov     ecx, ebx; BugCheckParameter2
0x140c802db  mov     cs:SeAuthenticatedUsersSid, rax
0x140c802e2  call    ExKdproPoolAllocate
0x140c802e7  mov     ecx, ebx; BugCheckParameter2
0x140c802e9  mov     cs:SeRestrictedSid, rax
0x140c802f0  call    ExKdproPoolAllocate
0x140c802f5  mov     ecx, ebx; BugCheckParameter2
0x140c802f7  mov     cs:SeAnonymousLogonSid, rax
0x140c802fe  call    ExKdproPoolAllocate
0x140c80303  mov     ecx, ebx; BugCheckParameter2
0x140c80305  mov     cs:SeLocalServiceSid, rax
0x140c8030c  call    ExKdproPoolAllocate
0x140c80311  mov     ecx, ebx; BugCheckParameter2
0x140c80313  mov     cs:SeNetworkServiceSid, rax
0x140c8031a  call    ExKdproPoolAllocate
0x140c8031f  mov     edi, dword ptr [rbp+1D0h+arg_10]
0x140c80325  mov     ecx, edi; BugCheckParameter2
0x140c80327  mov     cs:SeIUserSid, rax
0x140c8032e  call    ExKdproPoolAllocate
0x140c80333  mov     ecx, edi; BugCheckParameter2
0x140c80335  mov     cs:SeAliasAdminsSid, rax
0x140c8033c  call    ExKdproPoolAllocate
0x140c80341  mov     ecx, edi; BugCheckParameter2
0x140c80343  mov     cs:SeAliasUsersSid, rax
0x140c8034a  call    ExKdproPoolAllocate
0x140c8034f  mov     ecx, edi; BugCheckParameter2
0x140c80351  mov     cs:SeAliasGuestsSid, rax
0x140c80358  call    ExKdproPoolAllocate
0x140c8035d  mov     ecx, edi; BugCheckParameter2
0x140c8035f  mov     cs:SeAliasPowerUsersSid, rax
0x140c80366  call    ExKdproPoolAllocate
0x140c8036b  mov     ecx, edi; BugCheckParameter2
0x140c8036d  mov     cs:SeAliasAccountOpsSid, rax
0x140c80374  call    ExKdproPoolAllocate
0x140c80379  mov     ecx, edi; BugCheckParameter2
0x140c8037b  mov     cs:SeAliasSystemOpsSid, rax
0x140c80382  call    ExKdproPoolAllocate
0x140c80387  mov     cs:SeAliasPrintOpsSid, rax
0x140c8038e  mov     ecx, edi; BugCheckParameter2
0x140c80390  call    ExKdproPoolAllocate
0x140c80395  mov     ecx, ebx; BugCheckParameter2
0x140c80397  mov     cs:SeAliasBackupOpsSid, rax
  ... truncated ...
```
