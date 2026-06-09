# AdjustCcdDatabasePermissions

- ea: `0x1402f0a70`
- end: `0x1402f1371`
- name: `AdjustCcdDatabasePermissions`
- size: `2305`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1402f0a70`
- `0x1402f3028`

## callees

- `0x14001b9c0`
- `0x14004c1bc`
- `0x140061968`
- `0x1400627a4`
- `0x140062bc4`
- `0x1400723b0`
- `0x140093438`
- `0x1400a1000`
- `0x1402f0a70`
- `0x1403bd710`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1402f0b2b`
- `ntoskrnl!ExAllocatePool2` at `0x1402f0cf8`
- `ntoskrnl!ExAllocatePool2` at `0x1402f0fc3`
- `ntoskrnl!ExAllocatePool2` at `0x1402f10ef`
- `ntoskrnl!ExAllocatePool2` at `0x1402f0b2b`
- `ntoskrnl!ExAllocatePool2` at `0x1402f0cf8`
- `ntoskrnl!ExAllocatePool2` at `0x1402f0fc3`
- `ntoskrnl!ExAllocatePool2` at `0x1402f10ef`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402f0ec8`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1402f0ec8`
- `ntoskrnl!RtlLengthSid` at `0x1402f0cda`
- `ntoskrnl!RtlLengthSid` at `0x1402f0cda`
- `ntoskrnl!RtlCreateAcl` at `0x1402f0d81`
- `ntoskrnl!RtlCreateAcl` at `0x1402f0d81`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402f0f07`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1402f0f07`
- `ntoskrnl!RtlEqualSid` at `0x1402f0c3c`
- `ntoskrnl!RtlEqualSid` at `0x1402f0c3c`
- `ntoskrnl!ZwEnumerateKey` at `0x1402f1139`
- `ntoskrnl!ZwEnumerateKey` at `0x1402f1139`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1402f0ba6`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1402f0ba6`
- `ntoskrnl!RtlGetAce` at `0x1402f0c08`
- `ntoskrnl!RtlGetAce` at `0x1402f0dc3`
- `ntoskrnl!RtlGetAce` at `0x1402f0c08`
- `ntoskrnl!RtlGetAce` at `0x1402f0dc3`
- `ntoskrnl!RtlAddAce` at `0x1402f0e45`
- `ntoskrnl!RtlAddAce` at `0x1402f0e45`
- `ntoskrnl!ZwSetSecurityObject` at `0x1402f108a`
- `ntoskrnl!ZwSetSecurityObject` at `0x1402f108a`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1402f102d`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1402f102d`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1402f0f7a`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1402f0f7a`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1402f0b69`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1402f0b69`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x1402f0dfe`
- `ntoskrnl!RtlGetAcesBufferSize` at `0x1402f0dfe`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1402f0e8c`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1402f0e8c`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1402f0f3e`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1402f0f3e`
- `watchdog!WdLogSingleEntry0` at `0x1402f0aa0`
- `watchdog!WdLogSingleEntry0` at `0x1402f0c88`
- `watchdog!WdLogSingleEntry0` at `0x1402f125d`
- `watchdog!WdLogSingleEntry0` at `0x1402f0aa0`
- `watchdog!WdLogSingleEntry0` at `0x1402f0c88`
- `watchdog!WdLogSingleEntry0` at `0x1402f125d`
- `watchdog!WdLogSingleEntry1` at `0x1402f0af7`
- `watchdog!WdLogSingleEntry1` at `0x1402f0bbe`
- `watchdog!WdLogSingleEntry1` at `0x1402f0d1d`
- `watchdog!WdLogSingleEntry1` at `0x1402f0d5e`
- `watchdog!WdLogSingleEntry1` at `0x1402f0d99`
- `watchdog!WdLogSingleEntry1` at `0x1402f0ddb`
- `watchdog!WdLogSingleEntry1` at `0x1402f0e16`
- `watchdog!WdLogSingleEntry1` at `0x1402f0e5d`
- `watchdog!WdLogSingleEntry1` at `0x1402f0ea4`
- `watchdog!WdLogSingleEntry1` at `0x1402f0ee0`
- `watchdog!WdLogSingleEntry1` at `0x1402f0f1f`
- `watchdog!WdLogSingleEntry1` at `0x1402f0f5b`
- `watchdog!WdLogSingleEntry1` at `0x1402f0f9b`
- `watchdog!WdLogSingleEntry1` at `0x1402f0ff5`
- `watchdog!WdLogSingleEntry1` at `0x1402f1046`
- `watchdog!WdLogSingleEntry1` at `0x1402f10a2`
- `watchdog!WdLogSingleEntry1` at `0x1402f11cd`
- `watchdog!WdLogSingleEntry1` at `0x1402f122c`
- `watchdog!WdLogSingleEntry1` at `0x1402f127d`
- `watchdog!WdLogSingleEntry1` at `0x1402f12f2`
- `watchdog!WdLogSingleEntry1` at `0x1402f1329`
- `watchdog!WdLogSingleEntry1` at `0x1402f0af7`
- `watchdog!WdLogSingleEntry1` at `0x1402f0bbe`
- `watchdog!WdLogSingleEntry1` at `0x1402f0d1d`
- `watchdog!WdLogSingleEntry1` at `0x1402f0d5e`
- `watchdog!WdLogSingleEntry1` at `0x1402f0d99`
- `watchdog!WdLogSingleEntry1` at `0x1402f0ddb`
- `watchdog!WdLogSingleEntry1` at `0x1402f0e16`
- `watchdog!WdLogSingleEntry1` at `0x1402f0e5d`
- `watchdog!WdLogSingleEntry1` at `0x1402f0ea4`
- `watchdog!WdLogSingleEntry1` at `0x1402f0ee0`
- `watchdog!WdLogSingleEntry1` at `0x1402f0f1f`
- `watchdog!WdLogSingleEntry1` at `0x1402f0f5b`
- `watchdog!WdLogSingleEntry1` at `0x1402f0f9b`
- `watchdog!WdLogSingleEntry1` at `0x1402f0ff5`
- `watchdog!WdLogSingleEntry1` at `0x1402f1046`
- `watchdog!WdLogSingleEntry1` at `0x1402f10a2`
- `watchdog!WdLogSingleEntry1` at `0x1402f11cd`
- `watchdog!WdLogSingleEntry1` at `0x1402f122c`
- `watchdog!WdLogSingleEntry1` at `0x1402f127d`
- `watchdog!WdLogSingleEntry1` at `0x1402f12f2`
- `watchdog!WdLogSingleEntry1` at `0x1402f1329`

## string_xrefs

- `0x1402f0c99`: `Dacl->AclSize >= sizeof(ACL)`

## pseudocode

```c
__int64 __fastcall AdjustCcdDatabasePermissions(int a1, const WCHAR *a2, unsigned int a3, void *a4)
{
  ULONG v7; // r14d
  int v8; // eax
  unsigned int v9; // ebx
  ULONG v10; // eax
  __int64 Pool2; // rax
  PSECURITY_DESCRIPTOR v12; // rbx
  NTSTATUS v13; // eax
  int v14; // edi
  NTSTATUS DaclSecurityDescriptor; // eax
  PACL v16; // rcx
  ULONG v17; // edi
  NTSTATUS v18; // eax
  unsigned __int8 v19; // al
  int AclSize; // ebx
  ULONG v21; // ebx
  struct _ACL *v22; // rax
  struct _ACL *v23; // rdi
  NTSTATUS Acl; // eax
  NTSTATUS v25; // eax
  int AcesBufferSize; // eax
  NTSTATUS v27; // eax
  NTSTATUS v28; // eax
  NTSTATUS v29; // eax
  NTSTATUS v30; // eax
  ULONG v31; // eax
  __int64 v32; // rax
  PSECURITY_DESCRIPTOR v33; // rbx
  NTSTATUS v34; // eax
  NTSTATUS v35; // edi
  NTSTATUS v36; // eax
  unsigned int *v37; // rbx
  unsigned int v38; // r15d
  __int64 v39; // rax
  NTSTATUS v40; // eax
  __int64 v41; // rdi
  unsigned int *v42; // [rsp+50h] [rbp-49h] BYREF
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
  __int64 v55; // [rsp+C8h] [rbp+2Fh]
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
  v8 = CcdOpenRegistrySubkey((int)&Handle, 983103, a1, a2, &Size_4);
  v9 = v8;
  if ( v8 < 0 )
  {
    WdLogSingleEntry1(2, v8);
    WdLogGlobalForLineNumber = 2510;
LABEL_75:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Handle);
    return v9;
  }
  v10 = 336;
  SecurityDescriptor = 0;
  for ( Length = 336; ; v10 = Length )
  {
    Pool2 = ExAllocatePool2(256, v10, 1265072196);
    _reset___unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAAXPEAU_KEY_BASIC_INFORMATION___Z(
      &SecurityDescriptor,
      Pool2);
    v12 = SecurityDescriptor;
    if ( !SecurityDescriptor )
    {
      v14 = -1073741801;
      goto LABEL_77;
    }
    v13 = ZwQuerySecurityObject(Handle, 4u, SecurityDescriptor, Length, &Length);
    v14 = v13;
    if ( v13 != -1073741789 )
      break;
  }
  if ( v13 < 0 )
  {
LABEL_77:
    WdLogSingleEntry1(2, v14);
    WdLogGlobalForLineNumber = 2532;
    __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Handle);
    return (unsigned int)v14;
  }
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  Dacl = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(v12, &DaclPresent, &Dacl, DaclDefaulted);
  v9 = DaclSecurityDescriptor;
  if ( DaclSecurityDescriptor < 0 )
  {
    WdLogSingleEntry1(2, DaclSecurityDescriptor);
    WdLogGlobalForLineNumber = 2539;
LABEL_74:
    __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
    goto LABEL_75;
  }
  if ( !DaclPresent || (v16 = Dacl) == 0 )
  {
    v9 = -1073741275;
    WdLogSingleEntry1(2, -1073741275);
    WdLogGlobalForLineNumber = 2543;
    goto LABEL_74;
  }
  DaclPresent = 0;
  v17 = 0;
  if ( !Dacl->AceCount )
    goto LABEL_23;
  while ( 1 )
  {
    Ace = 0;
    v18 = RtlGetAce(v16, v17, &Ace);
    v9 = v18;
    if ( v18 < 0 )
    {
      WdLogSingleEntry1(2, v18);
      WdLogGlobalForLineNumber = 2552;
      goto LABEL_74;
    }
    if ( !*(_BYTE *)Ace && (*((_DWORD *)Ace + 1) & 0x2001F) == 0x2001F && RtlEqualSid((char *)Ace + 8, a4) )
      break;
    v16 = Dacl;
    if ( ++v17 >= Dacl->AceCount )
    {
      v19 = DaclPresent;
      goto LABEL_22;
    }
  }
  v16 = Dacl;
  v19 = 1;
  DaclPresent = 1;
LABEL_22:
  if ( !v19 )
  {
LABEL_23:
    SelfRelativeSecurityDescriptor = 0;
    memset(AbsoluteSecurityDescriptor, 0, sizeof(AbsoluteSecurityDescriptor));
    v55 = 0;
    if ( v16->AclSize < 8u )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2578;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"Dacl->AclSize >= sizeof(ACL)", 2578, 0, 0, 0, 0);
      v16 = Dacl;
    }
    AclSize = v16->AclSize;
    v21 = RtlLengthSid(a4) + 8 + AclSize;
    v22 = (struct _ACL *)ExAllocatePool2(256, v21, 1265072196);
    v42 = (unsigned int *)v22;
    v23 = v22;
    if ( !v22 )
    {
      v9 = -1073741670;
      WdLogSingleEntry1(2, -1073741670);
      WdLogGlobalForLineNumber = 2586;
      goto LABEL_27;
    }
    Acl = RtlCreateAcl(v22, v21, 2u);
    v9 = Acl;
    if ( Acl < 0 )
    {
      WdLogSingleEntry1(2, Acl);
      WdLogGlobalForLineNumber = 2589;
      goto LABEL_27;
    }
    AceList = 0;
    AceListLength = 0;
    v25 = RtlGetAce(Dacl, 0, &AceList);
    v9 = v25;
    if ( v25 < 0 )
    {
      WdLogSingleEntry1(2, v25);
      WdLogGlobalForLineNumber = 2594;
      goto LABEL_27;
    }
    AcesBufferSize = RtlGetAcesBufferSize(Dacl, &AceListLength);
    v9 = AcesBufferSize;
    if ( AcesBufferSize < 0 )
    {
      WdLogSingleEntry1(2, AcesBufferSize);
      WdLogGlobalForLineNumber = 2595;
      goto LABEL_27;
    }
    v27 = RtlAddAce(v23, 2u, 0, AceList, AceListLength);
    v9 = v27;
    if ( v27 < 0 )
    {
      WdLogSingleEntry1(2, v27);
      WdLogGlobalForLineNumber = 2596;
      goto LABEL_27;
    }
    v28 = RtlAddAccessAllowedAceEx(v23, 2u, 2u, 0x2001Fu, a4);
    v9 = v28;
    if ( v28 < 0 )
    {
      WdLogSingleEntry1(2, v28);
      WdLogGlobalForLineNumber = 2599;
      goto LABEL_27;
    }
    v29 = RtlCreateSecurityDescriptor(AbsoluteSecurityDescriptor, 1u);
    v9 = v29;
    if ( v29 < 0 )
    {
      WdLogSingleEntry1(2, v29);
      WdLogGlobalForLineNumber = 2602;
      goto LABEL_27;
    }
    v30 = RtlSetDaclSecurityDescriptor(AbsoluteSecurityDescriptor, 1u, v23, 0);
    v9 = v30;
    if ( v30 < 0 )
    {
      WdLogSingleEntry1(2, v30);
      WdLogGlobalForLineNumber = 2605;
      goto LABEL_27;
    }
    if ( !RtlValidSecurityDescriptor(AbsoluteSecurityDescriptor) )
    {
      v9 = -1073741595;
      WdLogSingleEntry1(2, -1073741595);
      WdLogGlobalForLineNumber = 2609;
      goto LABEL_27;
    }
    v31 = RtlLengthSecurityDescriptor(AbsoluteSecurityDescriptor);
    Size = v31;
    if ( v31 < 0x28 )
    {
      v9 = -1073741595;
      WdLogSingleEntry1(2, -1073741595);
      WdLogGlobalForLineNumber = 2617;
      goto LABEL_27;
    }
    v32 = ExAllocatePool2(256, v31, 1265072196);
    _reset___unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAAXPEAU_KEY_BASIC_INFORMATION___Z(
      &SelfRelativeSecurityDescriptor,
      v32);
    if ( (unsigned __int8)____8V__unique_storage_U__resource_policy_PEAX__A6AXPEAX__E_1_FreePoolWithTag___pool_helpers_PEAX_0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__YA_NAEBV__unique_any_t_V__unique_storage_U__resource_policy_PEAX__A6AXPEAX__E_1_FreePoolWithTag___pool_helpers_PEAX_0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___0___T_Z(&SelfRelativeSecurityDescriptor) )
    {
      v9 = -1073741670;
      WdLogSingleEntry1(2, -1073741670);
      WdLogGlobalForLineNumber = 2624;
      goto LABEL_27;
    }
    v33 = SelfRelativeSecurityDescriptor;
    memset(SelfRelativeSecurityDescriptor, 0, Size);
    v34 = RtlAbsoluteToSelfRelativeSD(AbsoluteSecurityDescriptor, v33, &Size);
    v35 = v34;
    if ( v34 < 0 )
    {
      WdLogSingleEntry1(2, v34);
      WdLogGlobalForLineNumber = 2629;
      __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SelfRelativeSecurityDescriptor);
      __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v42);
      __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
      v9 = v35;
      goto LABEL_75;
    }
    v36 = ZwSetSecurityObject(Handle, 4u, v33);
    v9 = v36;
    if ( v36 < 0 )
    {
      WdLogSingleEntry1(2, v36);
      WdLogGlobalForLineNumber = 2634;
LABEL_27:
      __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SelfRelativeSecurityDescriptor);
      __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v42);
      goto LABEL_74;
    }
    __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SelfRelativeSecurityDescriptor);
    __1__unique_storage_U__resource_policy_PEAU_ACL____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_ACL___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v42);
  }
  v37 = 0;
  v38 = 544;
  v42 = 0;
  do
  {
LABEL_56:
    if ( !v37 )
    {
      v39 = ExAllocatePool2(256, v38, 1265072196);
      _reset___unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAAXPEAU_KEY_BASIC_INFORMATION___Z(
        &v42,
        v39);
      v37 = v42;
      if ( !v42 )
      {
        v9 = -1073741670;
        WdLogSingleEntry1(2, -1073741670);
        WdLogGlobalForLineNumber = 2651;
        __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v42);
        goto LABEL_74;
      }
    }
    LODWORD(SelfRelativeSecurityDescriptor) = 0;
    v40 = ZwEnumerateKey(Handle, v7, KeyBasicInformation, v37, v38 - 2, (PULONG)&SelfRelativeSecurityDescriptor);
    v41 = v40;
    if ( v40 != -2147483643 && v40 != -1073741789 )
      break;
    v38 = (_DWORD)SelfRelativeSecurityDescriptor + 2;
    _reset___unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAAXPEAU_KEY_BASIC_INFORMATION___Z(
      &v42,
      0);
    v37 = v42;
  }
  while ( (_DWORD)v41 == -2147483643 || (_DWORD)v41 == -1073741789 );
  if ( (int)v41 >= 0 )
  {
    *((_WORD *)v37 + ((unsigned __int64)v37[3] >> 1) + 8) = 0;
    AdjustCcdDatabasePermissions(Handle, v37 + 4, a3 + 1, a4);
LABEL_67:
    ++v7;
    goto LABEL_56;
  }
  if ( (_DWORD)v41 == -2147483622 )
    goto LABEL_72;
  if ( !(unsigned int)Feature_FixCleanCCDDataBaseRace__private_IsEnabledDeviceUsageNoInline() )
  {
    WdLogSingleEntry1(1, v41);
    WdLogGlobalForLineNumber = 2700;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"Failed to enumerate key with status 0x%I64x",
      v41,
      0,
      0,
      0,
      0);
    goto LABEL_67;
  }
  if ( (_DWORD)v41 == -1073741444 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 2687;
  }
  else
  {
    WdLogSingleEntry1(1, v41);
    WdLogGlobalForLineNumber = 2693;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"Failed to enumerate key with status 0x%I64x",
      v41,
      0,
      0,
      0,
      0);
  }
LABEL_72:
  __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v42);
  __1__unique_storage_U__resource_policy_PEAU_KEY_BASIC_INFORMATION____A6AXPEAU1___E_1_FreePoolWithTag___pool_helpers_PEAU_KEY_BASIC_INFORMATION___0ELGHHIEE__details_wil__SAX0_ZU__integral_constant__K_0A__wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Handle);
  return 0;
}

```

## disassembly

```asm
0x1402f0a70  mov     [rsp-8+arg_0], rbx
0x1402f0a75  mov     [rsp-8+arg_8], rdi
0x1402f0a7a  push    rbp
0x1402f0a7b  push    r12
0x1402f0a7d  push    r13
0x1402f0a7f  push    r14
0x1402f0a81  push    r15
0x1402f0a83  lea     rbp, [rsp-37h]
0x1402f0a88  sub     rsp, 0D0h
0x1402f0a8f  mov     r12, r9
0x1402f0a92  mov     r13d, r8d
0x1402f0a95  cmp     r8d, 5
0x1402f0a99  jbe     short loc_1402F0ABD
0x1402f0a9b  mov     ecx, 1
0x1402f0aa0  call    cs:__imp_WdLogSingleEntry0
0x1402f0aa7  nop     dword ptr [rax+rax+00h]
0x1402f0aac  mov     cs:WdLogGlobalForLineNumber, 9C6h
0x1402f0ab6  xor     eax, eax
0x1402f0ab8  jmp     loc_1402F1353
0x1402f0abd  lea     rax, [rbp+57h+Size+4]
0x1402f0ac1  mov     r9, rdx; SourceString
0x1402f0ac4  mov     r8, rcx; int
0x1402f0ac7  mov     [rsp+0F0h+LengthNeeded], rax; PULONG
0x1402f0acc  mov     r15d, 2
0x1402f0ad2  lea     rcx, [rbp+57h+Handle]; int
0x1402f0ad6  xor     r14d, r14d
0x1402f0ad9  mov     dword ptr [rbp+57h+Size+4], r15d
0x1402f0add  mov     edx, 0F003Fh; int
0x1402f0ae2  mov     [rbp+57h+Handle], r14
0x1402f0ae6  call    _CcdOpenRegistrySubkey
0x1402f0aeb  mov     ebx, eax
0x1402f0aed  test    eax, eax
0x1402f0aef  jns     short loc_1402F0B12
0x1402f0af1  movsxd  rdx, eax
0x1402f0af4  mov     ecx, r15d
0x1402f0af7  call    cs:__imp_WdLogSingleEntry1
0x1402f0afe  nop     dword ptr [rax+rax+00h]
0x1402f0b03  mov     cs:WdLogGlobalForLineNumber, 9CEh
0x1402f0b0d  jmp     loc_1402F1311
0x1402f0b12  mov     eax, 150h
0x1402f0b17  mov     [rbp+57h+SecurityDescriptor], r14
0x1402f0b1b  mov     [rbp+57h+Length], eax
0x1402f0b1e  mov     edx, eax
0x1402f0b20  mov     ecx, 100h
0x1402f0b25  mov     r8d, 4B677844h
0x1402f0b2b  call    cs:__imp_ExAllocatePool2
0x1402f0b32  nop     dword ptr [rax+rax+00h]
0x1402f0b37  mov     rdx, rax
0x1402f0b3a  lea     rcx, [rbp+57h+SecurityDescriptor]
0x1402f0b3e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_KEY_BASIC_INFORMATION@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_KEY_BASIC_INFORMATION@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_KEY_BASIC_INFORMATION@@@Z
0x1402f0b43  mov     rbx, [rbp+57h+SecurityDescriptor]
0x1402f0b47  test    rbx, rbx
0x1402f0b4a  jz      loc_1402F131E
0x1402f0b50  mov     r9d, [rbp+57h+Length]; Length
0x1402f0b54  lea     rax, [rbp+57h+Length]
0x1402f0b58  mov     rcx, [rbp+57h+Handle]; Handle
0x1402f0b5c  mov     r8, rbx; SecurityDescriptor
0x1402f0b5f  mov     edx, 4; SecurityInformation
0x1402f0b64  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x1402f0b69  call    cs:__imp_ZwQuerySecurityObject
0x1402f0b70  nop     dword ptr [rax+rax+00h]
0x1402f0b75  mov     edi, eax
0x1402f0b77  cmp     eax, 0C0000023h
0x1402f0b7c  jnz     short loc_1402F0B83
0x1402f0b7e  mov     eax, [rbp+57h+Length]
0x1402f0b81  jmp     short loc_1402F0B1E
0x1402f0b83  test    eax, eax
0x1402f0b85  js      loc_1402F1323
0x1402f0b8b  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x1402f0b8f  mov     [rbp+57h+DaclPresent], r14b
0x1402f0b93  lea     r8, [rbp+57h+Dacl]; Dacl
0x1402f0b97  mov     [rbp+57h+DaclDefaulted], r14b
0x1402f0b9b  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x1402f0b9f  mov     [rbp+57h+Dacl], r14
0x1402f0ba3  mov     rcx, rbx; SecurityDescriptor
0x1402f0ba6  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1402f0bad  nop     dword ptr [rax+rax+00h]
0x1402f0bb2  mov     ebx, eax
0x1402f0bb4  test    eax, eax
0x1402f0bb6  jns     short loc_1402F0BD9
0x1402f0bb8  movsxd  rdx, eax
0x1402f0bbb  mov     ecx, r15d
0x1402f0bbe  call    cs:__imp_WdLogSingleEntry1
0x1402f0bc5  nop     dword ptr [rax+rax+00h]
0x1402f0bca  mov     cs:WdLogGlobalForLineNumber, 9EBh
0x1402f0bd4  jmp     loc_1402F1308
0x1402f0bd9  cmp     [rbp+57h+DaclPresent], r14b
0x1402f0bdd  jz      loc_1402F12E5
0x1402f0be3  mov     rcx, [rbp+57h+Dacl]; Acl
0x1402f0be7  test    rcx, rcx
0x1402f0bea  jz      loc_1402F12E5
0x1402f0bf0  mov     [rbp+57h+DaclPresent], r14b
0x1402f0bf4  mov     edi, r14d
0x1402f0bf7  cmp     r14w, [rcx+4]
0x1402f0bfc  jnb     short loc_1402F0C69
0x1402f0bfe  lea     r8, [rbp+57h+Ace]; Ace
0x1402f0c02  mov     [rbp+57h+Ace], r14
0x1402f0c06  mov     edx, edi; AceIndex
0x1402f0c08  call    cs:__imp_RtlGetAce
0x1402f0c0f  nop     dword ptr [rax+rax+00h]
0x1402f0c14  mov     ebx, eax
0x1402f0c16  test    eax, eax
0x1402f0c18  js      loc_1402F0D58
0x1402f0c1e  mov     rcx, [rbp+57h+Ace]
0x1402f0c22  cmp     [rcx], r14b
0x1402f0c25  jnz     short loc_1402F0C50
0x1402f0c27  mov     eax, [rcx+4]
0x1402f0c2a  mov     ebx, 2001Fh
0x1402f0c2f  and     eax, ebx
0x1402f0c31  cmp     eax, ebx
0x1402f0c33  jnz     short loc_1402F0C50
0x1402f0c35  add     rcx, 8; Sid1
0x1402f0c39  mov     rdx, r12; Sid2
0x1402f0c3c  call    cs:__imp_RtlEqualSid
0x1402f0c43  nop     dword ptr [rax+rax+00h]
0x1402f0c48  test    al, al
0x1402f0c4a  jnz     loc_1402F0D4A
0x1402f0c50  mov     rcx, [rbp+57h+Dacl]
0x1402f0c54  inc     edi
0x1402f0c56  movzx   eax, word ptr [rcx+4]
0x1402f0c5a  cmp     edi, eax
0x1402f0c5c  jb      short loc_1402F0BFE
0x1402f0c5e  mov     al, [rbp+57h+DaclPresent]
0x1402f0c61  test    al, al
0x1402f0c63  jnz     loc_1402F10CF
0x1402f0c69  xorps   xmm0, xmm0
0x1402f0c6c  mov     [rbp+57h+SelfRelativeSecurityDescriptor], r14
0x1402f0c70  xor     eax, eax
0x1402f0c72  movups  [rbp+57h+AbsoluteSecurityDescriptor], xmm0
0x1402f0c76  mov     [rbp+57h+var_28], rax
0x1402f0c7a  movups  [rbp+57h+var_38], xmm0
0x1402f0c7e  cmp     word ptr [rcx+2], 8
0x1402f0c83  jnb     short loc_1402F0CD3
0x1402f0c85  lea     ecx, [rax+1]
0x1402f0c88  call    cs:__imp_WdLogSingleEntry0
0x1402f0c8f  nop     dword ptr [rax+rax+00h]
0x1402f0c94  mov     [rsp+0F0h+var_B0], r14
0x1402f0c99  lea     r9, aDaclAclsizeSiz; "Dacl->AclSize >= sizeof(ACL)"
0x1402f0ca0  mov     [rsp+0F0h+var_B8], r14
0x1402f0ca5  mov     eax, 0A12h
0x1402f0caa  mov     [rsp+0F0h+var_C0], r14
0x1402f0caf  or      r8d, 0FFFFFFFFh
0x1402f0cb3  mov     [rsp+0F0h+ResultLength], r14
0x1402f0cb8  mov     edx, 40002h
0x1402f0cbd  xor     ecx, ecx
0x1402f0cbf  mov     [rsp+0F0h+LengthNeeded], rax
0x1402f0cc4  mov     cs:WdLogGlobalForLineNumber, eax
0x1402f0cca  call    DxgkLogInternalTriageEvent
0x1402f0ccf  mov     rcx, [rbp+57h+Dacl]
0x1402f0cd3  movzx   ebx, word ptr [rcx+2]
0x1402f0cd7  mov     rcx, r12; Sid
0x1402f0cda  call    cs:__imp_RtlLengthSid
0x1402f0ce1  nop     dword ptr [rax+rax+00h]
0x1402f0ce6  mov     ecx, 100h
0x1402f0ceb  mov     r8d, 4B677844h
0x1402f0cf1  add     eax, 8
0x1402f0cf4  add     ebx, eax
0x1402f0cf6  mov     edx, ebx
0x1402f0cf8  call    cs:__imp_ExAllocatePool2
0x1402f0cff  nop     dword ptr [rax+rax+00h]
0x1402f0d04  mov     [rbp+57h+var_A0], rax
0x1402f0d08  mov     rdi, rax
0x1402f0d0b  test    rax, rax
0x1402f0d0e  jnz     short loc_1402F0D79
0x1402f0d10  mov     rbx, 0FFFFFFFFC000009Ah
0x1402f0d17  mov     ecx, r15d
0x1402f0d1a  mov     rdx, rbx
0x1402f0d1d  call    cs:__imp_WdLogSingleEntry1
0x1402f0d24  nop     dword ptr [rax+rax+00h]
0x1402f0d29  mov     cs:WdLogGlobalForLineNumber, 0A1Ah
0x1402f0d33  lea     rcx, [rbp+57h+SelfRelativeSecurityDescriptor]
0x1402f0d37  call    ??1?$unique_storage@U?$resource_policy@PEAU_KEY_BASIC_INFORMATION@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_KEY_BASIC_INFORMATION@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1402f0d3c  lea     rcx, [rbp+57h+var_A0]
0x1402f0d40  call    ??1?$unique_storage@U?$resource_policy@PEAU_ACL@@$$A6AXPEAU1@@_E$1?FreePoolWithTag@?$pool_helpers@PEAU_ACL@@$0ELGHHIEE@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1402f0d45  jmp     loc_1402F1308
0x1402f0d4a  mov     rcx, [rbp+57h+Dacl]
0x1402f0d4e  mov     al, 1
0x1402f0d50  mov     [rbp+57h+DaclPresent], al
0x1402f0d53  jmp     loc_1402F0C61
0x1402f0d58  movsxd  rdx, eax
0x1402f0d5b  mov     ecx, r15d
0x1402f0d5e  call    cs:__imp_WdLogSingleEntry1
0x1402f0d65  nop     dword ptr [rax+rax+00h]
0x1402f0d6a  mov     cs:WdLogGlobalForLineNumber, 9F8h
0x1402f0d74  jmp     loc_1402F1308
0x1402f0d79  mov     r8d, r15d; AclRevision
0x1402f0d7c  mov     edx, ebx; AclLength
0x1402f0d7e  mov     rcx, rdi; Acl
0x1402f0d81  call    cs:__imp_RtlCreateAcl
0x1402f0d88  nop     dword ptr [rax+rax+00h]
0x1402f0d8d  mov     ebx, eax
0x1402f0d8f  test    eax, eax
0x1402f0d91  jns     short loc_1402F0DB1
0x1402f0d93  movsxd  rdx, eax
0x1402f0d96  mov     ecx, r15d
0x1402f0d99  call    cs:__imp_WdLogSingleEntry1
0x1402f0da0  nop     dword ptr [rax+rax+00h]
0x1402f0da5  mov     cs:WdLogGlobalForLineNumber, 0A1Dh
0x1402f0daf  jmp     short loc_1402F0D33
0x1402f0db1  mov     rcx, [rbp+57h+Dacl]; Acl
0x1402f0db5  lea     r8, [rbp+57h+AceList]; Ace
0x1402f0db9  xor     edx, edx; AceIndex
0x1402f0dbb  mov     [rbp+57h+AceList], r14
0x1402f0dbf  mov     [rbp+57h+AceListLength], r14d
0x1402f0dc3  call    cs:__imp_RtlGetAce
0x1402f0dca  nop     dword ptr [rax+rax+00h]
0x1402f0dcf  mov     ebx, eax
0x1402f0dd1  test    eax, eax
0x1402f0dd3  jns     short loc_1402F0DF6
0x1402f0dd5  movsxd  rdx, eax
0x1402f0dd8  mov     ecx, r15d
0x1402f0ddb  call    cs:__imp_WdLogSingleEntry1
0x1402f0de2  nop     dword ptr [rax+rax+00h]
0x1402f0de7  mov     cs:WdLogGlobalForLineNumber, 0A22h
0x1402f0df1  jmp     loc_1402F0D33
0x1402f0df6  mov     rcx, [rbp+57h+Dacl]
0x1402f0dfa  lea     rdx, [rbp+57h+AceListLength]
0x1402f0dfe  call    cs:__imp_RtlGetAcesBufferSize
0x1402f0e05  nop     dword ptr [rax+rax+00h]
0x1402f0e0a  mov     ebx, eax
0x1402f0e0c  test    eax, eax
0x1402f0e0e  jns     short loc_1402F0E31
0x1402f0e10  movsxd  rdx, eax
0x1402f0e13  mov     ecx, r15d
0x1402f0e16  call    cs:__imp_WdLogSingleEntry1
0x1402f0e1d  nop     dword ptr [rax+rax+00h]
0x1402f0e22  mov     cs:WdLogGlobalForLineNumber, 0A23h
0x1402f0e2c  jmp     loc_1402F0D33
0x1402f0e31  mov     eax, [rbp+57h+AceListLength]
0x1402f0e34  xor     r8d, r8d; StartingAceIndex
0x1402f0e37  mov     r9, [rbp+57h+AceList]; AceList
0x1402f0e3b  mov     edx, r15d; AceRevision
0x1402f0e3e  mov     rcx, rdi; Acl
0x1402f0e41  mov     dword ptr [rsp+0F0h+LengthNeeded], eax; AceListLength
0x1402f0e45  call    cs:__imp_RtlAddAce
0x1402f0e4c  nop     dword ptr [rax+rax+00h]
0x1402f0e51  mov     ebx, eax
0x1402f0e53  test    eax, eax
0x1402f0e55  jns     short loc_1402F0E78
0x1402f0e57  movsxd  rdx, eax
0x1402f0e5a  mov     ecx, r15d
0x1402f0e5d  call    cs:__imp_WdLogSingleEntry1
0x1402f0e64  nop     dword ptr [rax+rax+00h]
0x1402f0e69  mov     cs:WdLogGlobalForLineNumber, 0A24h
0x1402f0e73  jmp     loc_1402F0D33
0x1402f0e78  mov     r9d, 2001Fh; AccessMask
0x1402f0e7e  mov     [rsp+0F0h+LengthNeeded], r12; Sid
0x1402f0e83  mov     r8d, r15d; AceFlags
0x1402f0e86  mov     edx, r15d; AceRevision
0x1402f0e89  mov     rcx, rdi; Acl
0x1402f0e8c  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1402f0e93  nop     dword ptr [rax+rax+00h]
0x1402f0e98  mov     ebx, eax
0x1402f0e9a  test    eax, eax
0x1402f0e9c  jns     short loc_1402F0EBF
0x1402f0e9e  movsxd  rdx, eax
0x1402f0ea1  mov     ecx, r15d
0x1402f0ea4  call    cs:__imp_WdLogSingleEntry1
0x1402f0eab  nop     dword ptr [rax+rax+00h]
0x1402f0eb0  mov     cs:WdLogGlobalForLineNumber, 0A27h
0x1402f0eba  jmp     loc_1402F0D33
0x1402f0ebf  mov     edx, 1; Revision
0x1402f0ec4  lea     rcx, [rbp+57h+AbsoluteSecurityDescriptor]; SecurityDescriptor
0x1402f0ec8  call    cs:__imp_RtlCreateSecurityDescriptor
0x1402f0ecf  nop     dword ptr [rax+rax+00h]
0x1402f0ed4  mov     ebx, eax
0x1402f0ed6  test    eax, eax
0x1402f0ed8  jns     short loc_1402F0EFB
0x1402f0eda  movsxd  rdx, eax
0x1402f0edd  mov     ecx, r15d
0x1402f0ee0  call    cs:__imp_WdLogSingleEntry1
0x1402f0ee7  nop     dword ptr [rax+rax+00h]
0x1402f0eec  mov     cs:WdLogGlobalForLineNumber, 0A2Ah
0x1402f0ef6  jmp     loc_1402F0D33
0x1402f0efb  xor     r9d, r9d; DaclDefaulted
0x1402f0efe  lea     rcx, [rbp+57h+AbsoluteSecurityDescriptor]; SecurityDescriptor
0x1402f0f02  mov     r8, rdi; Dacl
0x1402f0f05  mov     dl, 1; DaclPresent
0x1402f0f07  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1402f0f0e  nop     dword ptr [rax+rax+00h]
0x1402f0f13  mov     ebx, eax
0x1402f0f15  test    eax, eax
0x1402f0f17  jns     short loc_1402F0F3A
0x1402f0f19  movsxd  rdx, eax
0x1402f0f1c  mov     ecx, r15d
0x1402f0f1f  call    cs:__imp_WdLogSingleEntry1
0x1402f0f26  nop     dword ptr [rax+rax+00h]
0x1402f0f2b  mov     cs:WdLogGlobalForLineNumber, 0A2Dh
0x1402f0f35  jmp     loc_1402F0D33
0x1402f0f3a  lea     rcx, [rbp+57h+AbsoluteSecurityDescriptor]; SecurityDescriptor
0x1402f0f3e  call    cs:__imp_RtlValidSecurityDescriptor
0x1402f0f45  nop     dword ptr [rax+rax+00h]
0x1402f0f4a  test    al, al
0x1402f0f4c  jnz     short loc_1402F0F76
0x1402f0f4e  mov     rbx, 0FFFFFFFFC00000E5h
0x1402f0f55  mov     ecx, r15d
0x1402f0f58  mov     rdx, rbx
0x1402f0f5b  call    cs:__imp_WdLogSingleEntry1
0x1402f0f62  nop     dword ptr [rax+rax+00h]
0x1402f0f67  mov     cs:WdLogGlobalForLineNumber, 0A31h
  ... truncated ...
```
