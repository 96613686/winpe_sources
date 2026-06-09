# AdjustCcdDatabasePermissions

- ea: `0x1402e9fc0`
- end: `0x1402ea8c1`
- name: `AdjustCcdDatabasePermissions`
- size: `2305`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1402e9fc0`
- `0x1402ec578`

## callees

- `0x14001b890`
- `0x14004bfbc`
- `0x1400615b8`
- `0x1400623f4`
- `0x140062814`
- `0x140071d70`
- `0x140092970`
- `0x1400a0540`
- `0x1402e9fc0`
- `0x1403be3f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1402ea07b`
- `ntoskrnl!ExAllocatePool2` at `0x1402ea248`
- `ntoskrnl!ExAllocatePool2` at `0x1402ea513`
- `ntoskrnl!ExAllocatePool2` at `0x1402ea63f`
- `ntoskrnl!ExAllocatePool2` at `0x1402ea07b`
- `ntoskrnl!ExAllocatePool2` at `0x1402ea248`
- `ntoskrnl!ExAllocatePool2` at `0x1402ea513`
- `ntoskrnl!ExAllocatePool2` at `0x1402ea63f`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402ea418`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402ea418`
- `ntoskrnl!RtlLengthSid` at `0x1402ea22a`
- `ntoskrnl!RtlLengthSid` at `0x1402ea22a`
- `ntoskrnl!RtlCreateAcl` at `0x1402ea2d1`
- `ntoskrnl!RtlCreateAcl` at `0x1402ea2d1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402ea457`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402ea457`
- `ntoskrnl!RtlEqualSid` at `0x1402ea18c`
- `ntoskrnl!RtlEqualSid` at `0x1402ea18c`
- `ntoskrnl!ZwEnumerateKey` at `0x1402ea689`
- `ntoskrnl!ZwEnumerateKey` at `0x1402ea689`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1402ea0f6`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1402ea0f6`
- `ntoskrnl!RtlGetAce` at `0x1402ea158`
- `ntoskrnl!RtlGetAce` at `0x1402ea313`
- `ntoskrnl!RtlGetAce` at `0x1402ea158`
- `ntoskrnl!RtlGetAce` at `0x1402ea313`
- `ntoskrnl!RtlAddAce` at `0x1402ea395`
- `ntoskrnl!RtlAddAce` at `0x1402ea395`
- `ntoskrnl!ZwSetSecurityObject` at `0x1402ea5da`
- `ntoskrnl!ZwSetSecurityObject` at `0x1402ea5da`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1402ea57d`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1402ea57d`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1402ea4ca`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1402ea4ca`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1402ea0b9`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1402ea0b9`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x1402ea34e`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x1402ea34e`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1402ea3dc`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1402ea3dc`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1402ea48e`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1402ea48e`
- `watchdog!WdLogSingleEntry0` at `0x1402e9ff0`
- `watchdog!WdLogSingleEntry0` at `0x1402ea1d8`
- `watchdog!WdLogSingleEntry0` at `0x1402ea7ad`
- `watchdog!WdLogSingleEntry0` at `0x1402e9ff0`
- `watchdog!WdLogSingleEntry0` at `0x1402ea1d8`
- `watchdog!WdLogSingleEntry0` at `0x1402ea7ad`
- `watchdog!WdLogSingleEntry1` at `0x1402ea047`
- `watchdog!WdLogSingleEntry1` at `0x1402ea10e`
- `watchdog!WdLogSingleEntry1` at `0x1402ea26d`
- `watchdog!WdLogSingleEntry1` at `0x1402ea2ae`
- `watchdog!WdLogSingleEntry1` at `0x1402ea2e9`
- `watchdog!WdLogSingleEntry1` at `0x1402ea32b`
- `watchdog!WdLogSingleEntry1` at `0x1402ea366`
- `watchdog!WdLogSingleEntry1` at `0x1402ea3ad`
- `watchdog!WdLogSingleEntry1` at `0x1402ea3f4`
- `watchdog!WdLogSingleEntry1` at `0x1402ea430`
- `watchdog!WdLogSingleEntry1` at `0x1402ea46f`
- `watchdog!WdLogSingleEntry1` at `0x1402ea4ab`
- `watchdog!WdLogSingleEntry1` at `0x1402ea4eb`
- `watchdog!WdLogSingleEntry1` at `0x1402ea545`
- `watchdog!WdLogSingleEntry1` at `0x1402ea596`
- `watchdog!WdLogSingleEntry1` at `0x1402ea5f2`
- `watchdog!WdLogSingleEntry1` at `0x1402ea71d`
- `watchdog!WdLogSingleEntry1` at `0x1402ea77c`
- `watchdog!WdLogSingleEntry1` at `0x1402ea7cd`
- `watchdog!WdLogSingleEntry1` at `0x1402ea842`
- `watchdog!WdLogSingleEntry1` at `0x1402ea879`
- `watchdog!WdLogSingleEntry1` at `0x1402ea047`
- `watchdog!WdLogSingleEntry1` at `0x1402ea10e`
- `watchdog!WdLogSingleEntry1` at `0x1402ea26d`
- `watchdog!WdLogSingleEntry1` at `0x1402ea2ae`
- `watchdog!WdLogSingleEntry1` at `0x1402ea2e9`
- `watchdog!WdLogSingleEntry1` at `0x1402ea32b`
- `watchdog!WdLogSingleEntry1` at `0x1402ea366`
- `watchdog!WdLogSingleEntry1` at `0x1402ea3ad`
- `watchdog!WdLogSingleEntry1` at `0x1402ea3f4`
- `watchdog!WdLogSingleEntry1` at `0x1402ea430`
- `watchdog!WdLogSingleEntry1` at `0x1402ea46f`
- `watchdog!WdLogSingleEntry1` at `0x1402ea4ab`
- `watchdog!WdLogSingleEntry1` at `0x1402ea4eb`
- `watchdog!WdLogSingleEntry1` at `0x1402ea545`
- `watchdog!WdLogSingleEntry1` at `0x1402ea596`
- `watchdog!WdLogSingleEntry1` at `0x1402ea5f2`
- `watchdog!WdLogSingleEntry1` at `0x1402ea71d`
- `watchdog!WdLogSingleEntry1` at `0x1402ea77c`
- `watchdog!WdLogSingleEntry1` at `0x1402ea7cd`
- `watchdog!WdLogSingleEntry1` at `0x1402ea842`
- `watchdog!WdLogSingleEntry1` at `0x1402ea879`

## string_xrefs

- `0x1402ea1e9`: `Dacl->AclSize >= sizeof(ACL)`

## pseudocode

```c
__int64 __fastcall AdjustCcdDatabasePermissions(int a1, const WCHAR *a2, unsigned int a3, void *a4)
{
  ULONG v7; // r14d
  NTSTATUS DaclSecurityDescriptor; // ebx
  ULONG v9; // eax
  __int64 Pool2; // rax
  PSECURITY_DESCRIPTOR v11; // rbx
  NTSTATUS v12; // eax
  unsigned int v13; // edi
  PACL v14; // rcx
  ULONG v15; // edi
  unsigned __int8 v16; // al
  int AclSize; // ebx
  ULONG v18; // ebx
  struct _ACL *v19; // rax
  struct _ACL *v20; // rdi
  ULONG v21; // eax
  __int64 v22; // rax
  PSECURITY_DESCRIPTOR v23; // rbx
  NTSTATUS v24; // edi
  unsigned int *v25; // rbx
  unsigned int v26; // r15d
  __int64 v27; // rax
  NTSTATUS v28; // eax
  __int64 v29; // rdi
  unsigned int *v30; // [rsp+50h] [rbp-49h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-41h] BYREF
  PSECURITY_DESCRIPTOR SelfRelativeSecurityDescriptor; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int8 DaclDefaulted[8]; // [rsp+68h] [rbp-31h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-29h] BYREF
  ULONG Length; // [rsp+78h] [rbp-21h] BYREF
  PACL Dacl; // [rsp+80h] [rbp-19h] BYREF
  ULONG AceListLength; // [rsp+88h] [rbp-11h] BYREF
  ULONG Size; // [rsp+8Ch] [rbp-Dh] BYREF
  ULONG Size_4; // [rsp+90h] [rbp-9h] BYREF
  PVOID Ace; // [rsp+98h] [rbp-1h] BYREF
  PVOID AceList; // [rsp+A0h] [rbp+7h] BYREF
  _OWORD AbsoluteSecurityDescriptor[2]; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v43; // [rsp+C8h] [rbp+2Fh]
  unsigned __int8 DaclPresent; // [rsp+110h] [rbp+77h] BYREF

  if ( a3 > 5 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2502;
    return 0;
  }
  v7 = 0;
  Size_4 = 2;
  Handle = 0;
  DaclSecurityDescriptor = CcdOpenRegistrySubkey((int)&Handle, 983103, a1, a2, &Size_4);
  if ( DaclSecurityDescriptor < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 2510;
LABEL_75:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Handle);
    return (unsigned int)DaclSecurityDescriptor;
  }
  v9 = 336;
  SecurityDescriptor = 0;
  for ( Length = 336; ; v9 = Length )
  {
    Pool2 = ExAllocatePool2(256, v9, 1265072196);
    _reset___unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAAXPEAU_KEY_BASIC_INFORMATION___Z(
      &SecurityDescriptor,
      Pool2);
    v11 = SecurityDescriptor;
    if ( !SecurityDescriptor )
    {
      v13 = -1073741801;
      goto LABEL_77;
    }
    v12 = ZwQuerySecurityObject(Handle, 4u, SecurityDescriptor, Length, &Length);
    v13 = v12;
    if ( v12 != -1073741789 )
      break;
  }
  if ( v12 < 0 )
  {
LABEL_77:
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 2532;
    __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Handle);
    return v13;
  }
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  Dacl = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(v11, &DaclPresent, &Dacl, DaclDefaulted);
  if ( DaclSecurityDescriptor < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 2539;
LABEL_74:
    __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
    goto LABEL_75;
  }
  if ( !DaclPresent || (v14 = Dacl) == 0 )
  {
    DaclSecurityDescriptor = -1073741275;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 2543;
    goto LABEL_74;
  }
  DaclPresent = 0;
  v15 = 0;
  if ( !Dacl->AceCount )
    goto LABEL_23;
  while ( 1 )
  {
    Ace = 0;
    DaclSecurityDescriptor = RtlGetAce(v14, v15, &Ace);
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2552;
      goto LABEL_74;
    }
    if ( !*(_BYTE *)Ace && (*((_DWORD *)Ace + 1) & 0x2001F) == 0x2001F && RtlEqualSid((char *)Ace + 8, a4) )
      break;
    v14 = Dacl;
    if ( ++v15 >= Dacl->AceCount )
    {
      v16 = DaclPresent;
      goto LABEL_22;
    }
  }
  v14 = Dacl;
  v16 = 1;
  DaclPresent = 1;
LABEL_22:
  if ( !v16 )
  {
LABEL_23:
    SelfRelativeSecurityDescriptor = 0;
    memset(AbsoluteSecurityDescriptor, 0, sizeof(AbsoluteSecurityDescriptor));
    v43 = 0;
    if ( v14->AclSize < 8u )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2578;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"Dacl->AclSize >= sizeof(ACL)", 2578, 0, 0, 0, 0);
      v14 = Dacl;
    }
    AclSize = v14->AclSize;
    v18 = RtlLengthSid(a4) + 8 + AclSize;
    v19 = (struct _ACL *)ExAllocatePool2(256, v18, 1265072196);
    v30 = (unsigned int *)v19;
    v20 = v19;
    if ( !v19 )
    {
      DaclSecurityDescriptor = -1073741670;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2586;
      goto LABEL_27;
    }
    DaclSecurityDescriptor = RtlCreateAcl(v19, v18, 2u);
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2589;
      goto LABEL_27;
    }
    AceList = 0;
    AceListLength = 0;
    DaclSecurityDescriptor = RtlGetAce(Dacl, 0, &AceList);
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2594;
      goto LABEL_27;
    }
    DaclSecurityDescriptor = RtlGetAcesBufferSize(Dacl, &AceListLength);
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2595;
      goto LABEL_27;
    }
    DaclSecurityDescriptor = RtlAddAce(v20, 2u, 0, AceList, AceListLength);
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2596;
      goto LABEL_27;
    }
    DaclSecurityDescriptor = RtlAddAccessAllowedAceEx(v20, 2u, 2u, 0x2001Fu, a4);
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2599;
      goto LABEL_27;
    }
    DaclSecurityDescriptor = RtlCreateSecurityDescriptor(AbsoluteSecurityDescriptor, 1u);
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2602;
      goto LABEL_27;
    }
    DaclSecurityDescriptor = RtlSetDaclSecurityDescriptor(AbsoluteSecurityDescriptor, 1u, v20, 0);
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2605;
      goto LABEL_27;
    }
    if ( !RtlValidSecurityDescriptor(AbsoluteSecurityDescriptor) )
    {
      DaclSecurityDescriptor = -1073741595;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2609;
      goto LABEL_27;
    }
    v21 = RtlLengthSecurityDescriptor(AbsoluteSecurityDescriptor);
    Size = v21;
    if ( v21 < 0x28 )
    {
      DaclSecurityDescriptor = -1073741595;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2617;
      goto LABEL_27;
    }
    v22 = ExAllocatePool2(256, v21, 1265072196);
    _reset___unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAAXPEAU_KEY_BASIC_INFORMATION___Z(
      &SelfRelativeSecurityDescriptor,
      v22);
    if ( (unsigned __int8)____8V__unique_storage_U__resource_policy_PEAX__A6AXPEAX__E_1_FreePoolWithTag___pool_helpers_PEAX_0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__YA_NAEBV__unique_any_t_V__unique_storage_U__resource_policy_PEAX__A6AXPEAX__E_1_FreePoolWithTag___pool_helpers_PEAX_0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___0___T_Z(&SelfRelativeSecurityDescriptor) )
    {
      DaclSecurityDescriptor = -1073741670;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2624;
      goto LABEL_27;
    }
    v23 = SelfRelativeSecurityDescriptor;
    memset(SelfRelativeSecurityDescriptor, 0, Size);
    v24 = RtlAbsoluteToSelfRelativeSD(AbsoluteSecurityDescriptor, v23, &Size);
    if ( v24 < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2629;
      __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SelfRelativeSecurityDescriptor);
      __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v30);
      __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
      DaclSecurityDescriptor = v24;
      goto LABEL_75;
    }
    DaclSecurityDescriptor = ZwSetSecurityObject(Handle, 4u, v23);
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 2634;
LABEL_27:
      __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SelfRelativeSecurityDescriptor);
      __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v30);
      goto LABEL_74;
    }
    __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SelfRelativeSecurityDescriptor);
    __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v30);
  }
  v25 = 0;
  v26 = 544;
  v30 = 0;
  do
  {
LABEL_56:
    if ( !v25 )
    {
      v27 = ExAllocatePool2(256, v26, 1265072196);
      _reset___unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAAXPEAU_KEY_BASIC_INFORMATION___Z(
        &v30,
        v27);
      v25 = v30;
      if ( !v30 )
      {
        DaclSecurityDescriptor = -1073741670;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 2651;
        __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v30);
        goto LABEL_74;
      }
    }
    LODWORD(SelfRelativeSecurityDescriptor) = 0;
    v28 = ZwEnumerateKey(Handle, v7, KeyBasicInformation, v25, v26 - 2, (PULONG)&SelfRelativeSecurityDescriptor);
    v29 = v28;
    if ( v28 != -2147483643 && v28 != -1073741789 )
      break;
    v26 = (_DWORD)SelfRelativeSecurityDescriptor + 2;
    _reset___unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAAXPEAU_KEY_BASIC_INFORMATION___Z(
      &v30,
      0);
    v25 = v30;
  }
  while ( (_DWORD)v29 == -2147483643 || (_DWORD)v29 == -1073741789 );
  if ( (int)v29 >= 0 )
  {
    *((_WORD *)v25 + ((unsigned __int64)v25[3] >> 1) + 8) = 0;
    AdjustCcdDatabasePermissions(Handle, v25 + 4, a3 + 1, a4);
LABEL_67:
    ++v7;
    goto LABEL_56;
  }
  if ( (_DWORD)v29 == -2147483622 )
    goto LABEL_72;
  if ( !(unsigned int)Feature_FixCleanCCDDataBaseRace__private_IsEnabledDeviceUsageNoInline() )
  {
    WdLogSingleEntry1(1);
    WdLogGlobalForLineNumber = 2700;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"Failed to enumerate key with status 0x%I64x",
      v29,
      0,
      0,
      0,
      0);
    goto LABEL_67;
  }
  if ( (_DWORD)v29 == -1073741444 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 2687;
  }
  else
  {
    WdLogSingleEntry1(1);
    WdLogGlobalForLineNumber = 2693;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"Failed to enumerate key with status 0x%I64x",
      v29,
      0,
      0,
      0,
      0);
  }
LABEL_72:
  __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v30);
  __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Handle);
  return 0;
}

```

## disassembly

```asm
0x1402e9fc0  mov     [rsp-8+arg_0], rbx
0x1402e9fc5  mov     [rsp-8+arg_8], rdi
0x1402e9fca  push    rbp
0x1402e9fcb  push    r12
0x1402e9fcd  push    r13
0x1402e9fcf  push    r14
0x1402e9fd1  push    r15
0x1402e9fd3  lea     rbp, [rsp-37h]
0x1402e9fd8  sub     rsp, 0D0h
0x1402e9fdf  mov     r12, r9
0x1402e9fe2  mov     r13d, r8d
0x1402e9fe5  cmp     r8d, 5
0x1402e9fe9  jbe     short loc_1402EA00D
0x1402e9feb  mov     ecx, 1
0x1402e9ff0  call    cs:__imp_WdLogSingleEntry0
0x1402e9ff7  nop     dword ptr [rax+rax+00h]
0x1402e9ffc  mov     cs:WdLogGlobalForLineNumber, 9C6h
0x1402ea006  xor     eax, eax
0x1402ea008  jmp     loc_1402EA8A3
0x1402ea00d  lea     rax, [rbp+57h+Size+4]
0x1402ea011  mov     r9, rdx; SourceString
0x1402ea014  mov     r8, rcx; int
0x1402ea017  mov     [rsp+0F0h+LengthNeeded], rax; PULONG
0x1402ea01c  mov     r15d, 2
0x1402ea022  lea     rcx, [rbp+57h+Handle]; int
0x1402ea026  xor     r14d, r14d
0x1402ea029  mov     dword ptr [rbp+57h+Size+4], r15d
0x1402ea02d  mov     edx, 0F003Fh; int
0x1402ea032  mov     [rbp+57h+Handle], r14
0x1402ea036  call    _CcdOpenRegistrySubkey
0x1402ea03b  mov     ebx, eax
0x1402ea03d  test    eax, eax
0x1402ea03f  jns     short loc_1402EA062
0x1402ea041  movsxd  rdx, eax
0x1402ea044  mov     ecx, r15d
0x1402ea047  call    cs:__imp_WdLogSingleEntry1
0x1402ea04e  nop     dword ptr [rax+rax+00h]
0x1402ea053  mov     cs:WdLogGlobalForLineNumber, 9CEh
0x1402ea05d  jmp     loc_1402EA861
0x1402ea062  mov     eax, 150h
0x1402ea067  mov     [rbp+57h+SecurityDescriptor], r14
0x1402ea06b  mov     [rbp+57h+Length], eax
0x1402ea06e  mov     edx, eax
0x1402ea070  mov     ecx, 100h
0x1402ea075  mov     r8d, 4B677844h
0x1402ea07b  call    cs:__imp_ExAllocatePool2
0x1402ea082  nop     dword ptr [rax+rax+00h]
0x1402ea087  mov     rdx, rax
0x1402ea08a  lea     rcx, [rbp+57h+SecurityDescriptor]
0x1402ea08e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_KEY_BASIC_INFORMATION@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_KEY_BASIC_INFORMATION@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_KEY_BASIC_INFORMATION@@@Z
0x1402ea093  mov     rbx, [rbp+57h+SecurityDescriptor]
0x1402ea097  test    rbx, rbx
0x1402ea09a  jz      loc_1402EA86E
0x1402ea0a0  mov     r9d, [rbp+57h+Length]; Length
0x1402ea0a4  lea     rax, [rbp+57h+Length]
0x1402ea0a8  mov     rcx, [rbp+57h+Handle]; Handle
0x1402ea0ac  mov     r8, rbx; SecurityDescriptor
0x1402ea0af  mov     edx, 4; SecurityInformation
0x1402ea0b4  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x1402ea0b9  call    cs:__imp_ZwQuerySecurityObject
0x1402ea0c0  nop     dword ptr [rax+rax+00h]
0x1402ea0c5  mov     edi, eax
0x1402ea0c7  cmp     eax, 0C0000023h
0x1402ea0cc  jnz     short loc_1402EA0D3
0x1402ea0ce  mov     eax, [rbp+57h+Length]
0x1402ea0d1  jmp     short loc_1402EA06E
0x1402ea0d3  test    eax, eax
0x1402ea0d5  js      loc_1402EA873
0x1402ea0db  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x1402ea0df  mov     [rbp+57h+DaclPresent], r14b
0x1402ea0e3  lea     r8, [rbp+57h+Dacl]; Dacl
0x1402ea0e7  mov     [rbp+57h+DaclDefaulted], r14b
0x1402ea0eb  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x1402ea0ef  mov     [rbp+57h+Dacl], r14
0x1402ea0f3  mov     rcx, rbx; SecurityDescriptor
0x1402ea0f6  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1402ea0fd  nop     dword ptr [rax+rax+00h]
0x1402ea102  mov     ebx, eax
0x1402ea104  test    eax, eax
0x1402ea106  jns     short loc_1402EA129
0x1402ea108  movsxd  rdx, eax
0x1402ea10b  mov     ecx, r15d
0x1402ea10e  call    cs:__imp_WdLogSingleEntry1
0x1402ea115  nop     dword ptr [rax+rax+00h]
0x1402ea11a  mov     cs:WdLogGlobalForLineNumber, 9EBh
0x1402ea124  jmp     loc_1402EA858
0x1402ea129  cmp     [rbp+57h+DaclPresent], r14b
0x1402ea12d  jz      loc_1402EA835
0x1402ea133  mov     rcx, [rbp+57h+Dacl]; Acl
0x1402ea137  test    rcx, rcx
0x1402ea13a  jz      loc_1402EA835
0x1402ea140  mov     [rbp+57h+DaclPresent], r14b
0x1402ea144  mov     edi, r14d
0x1402ea147  cmp     r14w, [rcx+4]
0x1402ea14c  jnb     short loc_1402EA1B9
0x1402ea14e  lea     r8, [rbp+57h+Ace]; Ace
0x1402ea152  mov     [rbp+57h+Ace], r14
0x1402ea156  mov     edx, edi; AceIndex
0x1402ea158  call    cs:__imp_RtlGetAce
0x1402ea15f  nop     dword ptr [rax+rax+00h]
0x1402ea164  mov     ebx, eax
0x1402ea166  test    eax, eax
0x1402ea168  js      loc_1402EA2A8
0x1402ea16e  mov     rcx, [rbp+57h+Ace]
0x1402ea172  cmp     [rcx], r14b
0x1402ea175  jnz     short loc_1402EA1A0
0x1402ea177  mov     eax, [rcx+4]
0x1402ea17a  mov     ebx, 2001Fh
0x1402ea17f  and     eax, ebx
0x1402ea181  cmp     eax, ebx
0x1402ea183  jnz     short loc_1402EA1A0
0x1402ea185  add     rcx, 8; Sid1
0x1402ea189  mov     rdx, r12; Sid2
0x1402ea18c  call    cs:__imp_RtlEqualSid
0x1402ea193  nop     dword ptr [rax+rax+00h]
0x1402ea198  test    al, al
0x1402ea19a  jnz     loc_1402EA29A
0x1402ea1a0  mov     rcx, [rbp+57h+Dacl]
0x1402ea1a4  inc     edi
0x1402ea1a6  movzx   eax, word ptr [rcx+4]
0x1402ea1aa  cmp     edi, eax
0x1402ea1ac  jb      short loc_1402EA14E
0x1402ea1ae  mov     al, [rbp+57h+DaclPresent]
0x1402ea1b1  test    al, al
0x1402ea1b3  jnz     loc_1402EA61F
0x1402ea1b9  xorps   xmm0, xmm0
0x1402ea1bc  mov     [rbp+57h+SelfRelativeSecurityDescriptor], r14
0x1402ea1c0  xor     eax, eax
0x1402ea1c2  movups  [rbp+57h+AbsoluteSecurityDescriptor], xmm0
0x1402ea1c6  mov     [rbp+57h+var_28], rax
0x1402ea1ca  movups  [rbp+57h+var_38], xmm0
0x1402ea1ce  cmp     word ptr [rcx+2], 8
0x1402ea1d3  jnb     short loc_1402EA223
0x1402ea1d5  lea     ecx, [rax+1]
0x1402ea1d8  call    cs:__imp_WdLogSingleEntry0
0x1402ea1df  nop     dword ptr [rax+rax+00h]
0x1402ea1e4  mov     [rsp+0F0h+var_B0], r14
0x1402ea1e9  lea     r9, aDaclAclsizeSiz; "Dacl->AclSize >= sizeof(ACL)"
0x1402ea1f0  mov     [rsp+0F0h+var_B8], r14
0x1402ea1f5  mov     eax, 0A12h
0x1402ea1fa  mov     [rsp+0F0h+var_C0], r14
0x1402ea1ff  or      r8d, 0FFFFFFFFh
0x1402ea203  mov     [rsp+0F0h+ResultLength], r14
0x1402ea208  mov     edx, 40002h
0x1402ea20d  xor     ecx, ecx
0x1402ea20f  mov     [rsp+0F0h+LengthNeeded], rax
0x1402ea214  mov     cs:WdLogGlobalForLineNumber, eax
0x1402ea21a  call    DxgkLogInternalTriageEvent
0x1402ea21f  mov     rcx, [rbp+57h+Dacl]
0x1402ea223  movzx   ebx, word ptr [rcx+2]
0x1402ea227  mov     rcx, r12; Sid
0x1402ea22a  call    cs:__imp_RtlLengthSid
0x1402ea231  nop     dword ptr [rax+rax+00h]
0x1402ea236  mov     ecx, 100h
0x1402ea23b  mov     r8d, 4B677844h
0x1402ea241  add     eax, 8
0x1402ea244  add     ebx, eax
0x1402ea246  mov     edx, ebx
0x1402ea248  call    cs:__imp_ExAllocatePool2
0x1402ea24f  nop     dword ptr [rax+rax+00h]
0x1402ea254  mov     [rbp+57h+var_A0], rax
0x1402ea258  mov     rdi, rax
0x1402ea25b  test    rax, rax
0x1402ea25e  jnz     short loc_1402EA2C9
0x1402ea260  mov     rbx, 0FFFFFFFFC000009Ah
0x1402ea267  mov     ecx, r15d
0x1402ea26a  mov     rdx, rbx
0x1402ea26d  call    cs:__imp_WdLogSingleEntry1
0x1402ea274  nop     dword ptr [rax+rax+00h]
0x1402ea279  mov     cs:WdLogGlobalForLineNumber, 0A1Ah
0x1402ea283  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x1402ea287  call    ??1?$unique_storage@U?$resource_policy@PEAU_KEY_BASIC_INFORMATION@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_KEY_BASIC_INFORMATION@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1402ea28c  lea     rcx, [rbp+57h+var_A0]
0x1402ea290  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_ACL@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1402ea295  jmp     loc_1402EA858
0x1402ea29a  mov     rcx, [rbp+57h+Dacl]
0x1402ea29e  mov     al, 1
0x1402ea2a0  mov     [rbp+57h+DaclPresent], al
0x1402ea2a3  jmp     loc_1402EA1B1
0x1402ea2a8  movsxd  rdx, eax
0x1402ea2ab  mov     ecx, r15d
0x1402ea2ae  call    cs:__imp_WdLogSingleEntry1
0x1402ea2b5  nop     dword ptr [rax+rax+00h]
0x1402ea2ba  mov     cs:WdLogGlobalForLineNumber, 9F8h
0x1402ea2c4  jmp     loc_1402EA858
0x1402ea2c9  mov     r8d, r15d; AclRevision
0x1402ea2cc  mov     edx, ebx; AclLength
0x1402ea2ce  mov     rcx, rdi; Acl
0x1402ea2d1  call    cs:__imp_RtlCreateAcl
0x1402ea2d8  nop     dword ptr [rax+rax+00h]
0x1402ea2dd  mov     ebx, eax
0x1402ea2df  test    eax, eax
0x1402ea2e1  jns     short loc_1402EA301
0x1402ea2e3  movsxd  rdx, eax
0x1402ea2e6  mov     ecx, r15d
0x1402ea2e9  call    cs:__imp_WdLogSingleEntry1
0x1402ea2f0  nop     dword ptr [rax+rax+00h]
0x1402ea2f5  mov     cs:WdLogGlobalForLineNumber, 0A1Dh
0x1402ea2ff  jmp     short loc_1402EA283
0x1402ea301  mov     rcx, [rbp+57h+Dacl]; Acl
0x1402ea305  lea     r8, [rbp+57h+AceList]; Ace
0x1402ea309  xor     edx, edx; AceIndex
0x1402ea30b  mov     [rbp+57h+AceList], r14
0x1402ea30f  mov     [rbp+57h+AceListLength], r14d
0x1402ea313  call    cs:__imp_RtlGetAce
0x1402ea31a  nop     dword ptr [rax+rax+00h]
0x1402ea31f  mov     ebx, eax
0x1402ea321  test    eax, eax
0x1402ea323  jns     short loc_1402EA346
0x1402ea325  movsxd  rdx, eax
0x1402ea328  mov     ecx, r15d
0x1402ea32b  call    cs:__imp_WdLogSingleEntry1
0x1402ea332  nop     dword ptr [rax+rax+00h]
0x1402ea337  mov     cs:WdLogGlobalForLineNumber, 0A22h
0x1402ea341  jmp     loc_1402EA283
0x1402ea346  mov     rcx, [rbp+57h+Dacl]
0x1402ea34a  lea     rdx, [rbp+57h+AceListLength]
0x1402ea34e  call    cs:__imp_RtlGetAcesBufferSize
0x1402ea355  nop     dword ptr [rax+rax+00h]
0x1402ea35a  mov     ebx, eax
0x1402ea35c  test    eax, eax
0x1402ea35e  jns     short loc_1402EA381
0x1402ea360  movsxd  rdx, eax
0x1402ea363  mov     ecx, r15d
0x1402ea366  call    cs:__imp_WdLogSingleEntry1
0x1402ea36d  nop     dword ptr [rax+rax+00h]
0x1402ea372  mov     cs:WdLogGlobalForLineNumber, 0A23h
0x1402ea37c  jmp     loc_1402EA283
0x1402ea381  mov     eax, [rbp+57h+AceListLength]
0x1402ea384  xor     r8d, r8d; StartingAceIndex
0x1402ea387  mov     r9, [rbp+57h+AceList]; AceList
0x1402ea38b  mov     edx, r15d; AceRevision
0x1402ea38e  mov     rcx, rdi; Acl
0x1402ea391  mov     dword ptr [rsp+0F0h+LengthNeeded], eax; AceListLength
0x1402ea395  call    cs:__imp_RtlAddAce
0x1402ea39c  nop     dword ptr [rax+rax+00h]
0x1402ea3a1  mov     ebx, eax
0x1402ea3a3  test    eax, eax
0x1402ea3a5  jns     short loc_1402EA3C8
0x1402ea3a7  movsxd  rdx, eax
0x1402ea3aa  mov     ecx, r15d
0x1402ea3ad  call    cs:__imp_WdLogSingleEntry1
0x1402ea3b4  nop     dword ptr [rax+rax+00h]
0x1402ea3b9  mov     cs:WdLogGlobalForLineNumber, 0A24h
0x1402ea3c3  jmp     loc_1402EA283
0x1402ea3c8  mov     r9d, 2001Fh; AccessMask
0x1402ea3ce  mov     [rsp+0F0h+LengthNeeded], r12; Sid
0x1402ea3d3  mov     r8d, r15d; AceFlags
0x1402ea3d6  mov     edx, r15d; AceRevision
0x1402ea3d9  mov     rcx, rdi; Acl
0x1402ea3dc  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1402ea3e3  nop     dword ptr [rax+rax+00h]
0x1402ea3e8  mov     ebx, eax
0x1402ea3ea  test    eax, eax
0x1402ea3ec  jns     short loc_1402EA40F
0x1402ea3ee  movsxd  rdx, eax
0x1402ea3f1  mov     ecx, r15d
0x1402ea3f4  call    cs:__imp_WdLogSingleEntry1
0x1402ea3fb  nop     dword ptr [rax+rax+00h]
0x1402ea400  mov     cs:WdLogGlobalForLineNumber, 0A27h
0x1402ea40a  jmp     loc_1402EA283
0x1402ea40f  mov     edx, 1; Revision
0x1402ea414  lea     rcx, [rbp+57h+AbsoluteSecurityDescriptor]; SecurityDescriptor
0x1402ea418  call    cs:__imp_RtlCreateSecurityDescriptor
0x1402ea41f  nop     dword ptr [rax+rax+00h]
0x1402ea424  mov     ebx, eax
0x1402ea426  test    eax, eax
0x1402ea428  jns     short loc_1402EA44B
0x1402ea42a  movsxd  rdx, eax
0x1402ea42d  mov     ecx, r15d
0x1402ea430  call    cs:__imp_WdLogSingleEntry1
0x1402ea437  nop     dword ptr [rax+rax+00h]
0x1402ea43c  mov     cs:WdLogGlobalForLineNumber, 0A2Ah
0x1402ea446  jmp     loc_1402EA283
0x1402ea44b  xor     r9d, r9d; DaclDefaulted
0x1402ea44e  lea     rcx, [rbp+57h+AbsoluteSecurityDescriptor]; SecurityDescriptor
0x1402ea452  mov     r8, rdi; Dacl
0x1402ea455  mov     dl, 1; DaclPresent
0x1402ea457  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1402ea45e  nop     dword ptr [rax+rax+00h]
0x1402ea463  mov     ebx, eax
0x1402ea465  test    eax, eax
0x1402ea467  jns     short loc_1402EA48A
0x1402ea469  movsxd  rdx, eax
0x1402ea46c  mov     ecx, r15d
0x1402ea46f  call    cs:__imp_WdLogSingleEntry1
0x1402ea476  nop     dword ptr [rax+rax+00h]
0x1402ea47b  mov     cs:WdLogGlobalForLineNumber, 0A2Dh
0x1402ea485  jmp     loc_1402EA283
0x1402ea48a  lea     rcx, [rbp+57h+AbsoluteSecurityDescriptor]; SecurityDescriptor
0x1402ea48e  call    cs:__imp_RtlValidSecurityDescriptor
0x1402ea495  nop     dword ptr [rax+rax+00h]
0x1402ea49a  test    al, al
0x1402ea49c  jnz     short loc_1402EA4C6
0x1402ea49e  mov     rbx, 0FFFFFFFFC00000E5h
0x1402ea4a5  mov     ecx, r15d
0x1402ea4a8  mov     rdx, rbx
0x1402ea4ab  call    cs:__imp_WdLogSingleEntry1
0x1402ea4b2  nop     dword ptr [rax+rax+00h]
0x1402ea4b7  mov     cs:WdLogGlobalForLineNumber, 0A31h
  ... truncated ...
```
