# CmpInitCmRM

- ea: `0x1408e282c`
- end: `0x1408e32b6`
- name: `CmpInitCmRM`
- size: `2698`
- prototype: ``
- caller_count: `3`
- callee_count: `40`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1404c0780`
- `0x1407f7eb4`
- `0x140aeb590`

## callees

- `0x140214b10`
- `0x140214b30`
- `0x140216480`
- `0x14024c9f0`
- `0x140251fe0`
- `0x1402dff80`
- `0x14036f270`
- `0x140388750`
- `0x140442cb0`
- `0x14051754c`
- `0x14069cfd4`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dec80`
- `0x1406dede0`
- `0x1406dfa80`
- `0x1406e0300`
- `0x1406e0320`
- `0x1406f6f80`
- `0x140809174`
- `0x140886c74`
- `0x1408aa3e4`
- `0x1408aa44c`
- `0x1408b1580`
- `0x1408d9170`
- `0x1408e1e30`
- `0x1408e282c`
- `0x1408e4138`
- `0x1408e47f4`
- `0x1408e4bdc`
- `0x1408e5618`
- `0x140923cd0`
- `0x14094b120`
- `0x140ad175c`
- `0x140af265c`
- `0x140bb1410`
- `0x140bb19d0`
- `0x140bb19f0`
- `0x140bfa870`
- `0x140bfa950`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x1408e2ba8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x1408e2ba8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtRegisterManagedClient` at `0x1408e2c34`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtRegisterManagedClient` at `0x1408e2c34`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1408e2cbe`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1408e2cbe`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408e2fc3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408e3162`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x140b559bb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408e2fc3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408e3162`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x140b559bb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x1408e2f93`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x1408e317b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x140b5599e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x1408e2f93`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x1408e317b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x140b5599e`

## pseudocode

```c
__int64 __fastcall CmpInitCmRM(ULONG_PTR a1, char a2)
{
  int v2; // r15d
  ULONG_PTR v3; // r12
  ULONG_PTR v4; // rbx
  NTSTATUS v5; // eax
  __int64 v6; // rcx
  NTSTATUS IsFileInSystemConfig; // edi
  NTSTATUS v8; // eax
  _QWORD *Pool2; // rsi
  struct _ERESOURCE *v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // r8
  UUID v13; // xmm6
  UUID v14; // xmm7
  ULONG fLogOptionFlag; // r13d
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  void *v19; // r15
  wchar_t *v20; // rcx
  UNICODE_STRING *p_UnicodeString; // r12
  int v22; // eax
  unsigned __int16 Length; // ax
  PSECURITY_DESCRIPTOR v24; // r15
  int v25; // eax
  __int64 v26; // rax
  struct _CLFS_MGMT_POLICY *v27; // r15
  int v28; // ecx
  HANDLE *v29; // r12
  NTSTATUS v30; // eax
  HANDLE v31; // rcx
  HANDLE *v32; // r15
  GUID v33; // xmm0
  HANDLE v34; // rcx
  ULONG_PTR v35; // r8
  _QWORD *v36; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  wchar_t *Buffer; // rcx
  __int128 v40; // kr00_16
  __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  char v45; // r9
  __int64 v46; // rcx
  __int64 v47; // rdx
  wchar_t *v48; // rax
  wchar_t *v49; // rax
  wchar_t *v50; // rax
  void *v51; // rcx
  void *v52; // rcx
  void *v53; // rcx
  __int64 fCreateOptions; // [rsp+38h] [rbp-D0h]
  UNICODE_STRING Destination_8; // [rsp+70h] [rbp-98h] BYREF
  int v56; // [rsp+80h] [rbp-88h]
  int v57; // [rsp+84h] [rbp-84h]
  FILE_OBJECT *pplfoLog; // [rsp+88h] [rbp-80h] BYREF
  PSECURITY_DESCRIPTOR P; // [rsp+90h] [rbp-78h] BYREF
  ULONG CreateOptions[2]; // [rsp+98h] [rbp-70h] BYREF
  PVOID ClientCookie; // [rsp+A0h] [rbp-68h] BYREF
  UNICODE_STRING Source; // [rsp+A8h] [rbp-60h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+B8h] [rbp-50h] BYREF
  ULONG_PTR v64; // [rsp+C8h] [rbp-40h]
  UNICODE_STRING LogFileName; // [rsp+D0h] [rbp-38h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-28h] BYREF
  PERESOURCE Resource; // [rsp+110h] [rbp+8h]
  _CLFS_MGMT_CLIENT_REGISTRATION RegistrationData; // [rsp+118h] [rbp+10h] BYREF
  __int128 v69; // [rsp+150h] [rbp+48h]
  GUID ResourceManagerGuid; // [rsp+160h] [rbp+58h] BYREF
  UUID Uuid; // [rsp+170h] [rbp+68h] BYREF
  UUID v72; // [rsp+180h] [rbp+78h] BYREF

  v64 = a1;
  *(_QWORD *)&Source.Length = 0;
  Source.Buffer = 0;
  LOBYTE(v2) = a2;
  v3 = a1;
  *(_QWORD *)&UnicodeString.Length = 0;
  v69 = 0;
  UnicodeString.Buffer = 0;
  ResourceManagerGuid = 0;
  *(_QWORD *)&Destination_8.Length = 0;
  Uuid = 0;
  Destination_8.Buffer = 0;
  v72 = 0;
  pplfoLog = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_QWORD *)&LogFileName.Length = 0;
  LogFileName.Buffer = 0;
  P = 0;
  ClientCookie = 0;
  memset(&RegistrationData, 0, 52);
  if ( BYTE6(NlsMbOemCodePageTag) )
    return 0;
  v4 = qword_140E0D200;
  if ( a1 )
    v4 = a1;
  if ( (*(_DWORD *)(v4 + 160) & 0x8001) != 0 )
    return 0;
  while ( 1 )
  {
    v5 = ExUuidCreate(&Uuid);
    IsFileInSystemConfig = v5;
    if ( v5 != -1073741267 )
      break;
    *(_QWORD *)CreateOptions = -10000000;
    KeDelayExecutionThread(0, 0, (PLARGE_INTEGER)CreateOptions);
  }
  if ( v5 < 0 )
    goto LABEL_82;
  while ( 1 )
  {
    v8 = ExUuidCreate(&v72);
    IsFileInSystemConfig = v8;
    if ( v8 != -1073741267 )
      break;
    *(_QWORD *)CreateOptions = -10000000;
    KeDelayExecutionThread(0, 0, (PLARGE_INTEGER)CreateOptions);
  }
  if ( v8 < 0 )
  {
LABEL_82:
    *(_DWORD *)(v4 + 4176) = 1;
LABEL_85:
    *(_DWORD *)(v4 + 4180) = IsFileInSystemConfig;
    CmpLogTxrInitEvent(v6, v4, (unsigned int)IsFileInSystemConfig);
    return (unsigned int)IsFileInSystemConfig;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(256, 136, 1834110275);
  if ( !Pool2 )
  {
    *(_DWORD *)(v4 + 4176) = 1;
LABEL_84:
    IsFileInSystemConfig = -1073741670;
    goto LABEL_85;
  }
  Resource = (PERESOURCE)ExAllocatePool2(64, 104, 1819430211);
  v10 = Resource;
  if ( !Resource )
  {
    ExFreePoolWithTag(Pool2, 0x6D524D43u);
    *(_DWORD *)(v4 + 4176) = 2;
    goto LABEL_84;
  }
  Pool2[3] = Pool2 + 2;
  Pool2[2] = Pool2 + 2;
  Pool2[11] = 0;
  Pool2[12] = 0;
  *((_DWORD *)Pool2 + 26) = (_BYTE)v2 != 0 ? 4 : 0;
  *(_QWORD *)((char *)Pool2 + 108) = 0;
  *((_DWORD *)Pool2 + 17) = 0;
  Pool2[9] = 0;
  Pool2[16] = v10;
  ExInitializeResourceLite(v10);
  v12 = *(_QWORD *)(v4 + 64);
  v13 = Uuid;
  v14 = v72;
  if ( *(_DWORD *)(v12 + 164) == 1836346738 )
  {
    v40 = v69;
    v57 = v2;
    v41 = v69 - *(_QWORD *)(v12 + 148);
    if ( (_QWORD)v69 == *(_QWORD *)(v12 + 148) )
      v41 = *((_QWORD *)&v69 + 1) - *(_QWORD *)(v12 + 156);
    if ( v41 )
    {
      v56 = 0;
      v45 = 0;
    }
    else
    {
      v56 = 1;
      v45 = 1;
      *(UUID *)(v12 + 148) = v72;
    }
    v18 = *(_QWORD *)(v4 + 64);
    v46 = v40 - *(_QWORD *)(v18 + 112);
    if ( (_QWORD)v40 == *(_QWORD *)(v18 + 112) )
      v46 = *((_QWORD *)&v40 + 1) - *(_QWORD *)(v18 + 120);
    if ( !v46 )
    {
      v45 = 1;
      *(UUID *)(v18 + 112) = v13;
    }
    v11 = *(_QWORD **)(v4 + 64);
    v47 = v40 - v11[16];
    if ( !v47 )
      v47 = *((_QWORD *)&v40 + 1) - v11[17];
    if ( !v47 )
    {
      v45 = 1;
      *((_OWORD *)v11 + 8) = *((_OWORD *)v11 + 7);
    }
    CreateOptions[0] = 0;
    fLogOptionFlag = 512;
    if ( !v45 )
      goto LABEL_18;
    goto LABEL_16;
  }
  CreateOptions[0] = 0;
  fLogOptionFlag = 512;
  *(_DWORD *)(v12 + 164) = 1836346738;
  while ( 1 )
  {
    v16 = *(_QWORD *)(v4 + 64);
    v2 = (unsigned __int8)v2;
    if ( !v3 )
      v2 = 1;
    v56 = 1;
    v57 = v2;
    *(UUID *)(v16 + 148) = v14;
    *(UUID *)(*(_QWORD *)(v4 + 64) + 112LL) = v13;
    *(UUID *)(*(_QWORD *)(v4 + 64) + 128LL) = v13;
LABEL_16:
    CmpLockRegistry(v11);
    HvLockHiveFlusherShared(v4);
    HvLockHiveWriter(v4);
    HvMarkBaseBlockDirty(v4);
    HvUnlockHiveWriter(v4);
    HvUnlockHiveFlusherShared(v4);
    CmpUnlockRegistry(v17);
LABEL_18:
    v19 = *(void **)(v4 + 1552);
    LOBYTE(v18) = 1;
    IsFileInSystemConfig = RtlStringFromGUIDEx(*(_QWORD *)(v4 + 64) + 148LL, &Source, v18);
    if ( IsFileInSystemConfig < 0 )
    {
      *(_DWORD *)(v4 + 4176) = 3;
      goto LABEL_136;
    }
    if ( v3 )
    {
      IsFileInSystemConfig = CmpQueryNameString(*(_QWORD *)(v3 + 1552), &UnicodeString);
      if ( IsFileInSystemConfig < 0 )
      {
        *(_DWORD *)(v4 + 4176) = 4;
        goto LABEL_136;
      }
      p_UnicodeString = &UnicodeString;
      if ( (Feature_CLFS_Signing__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_CLFS_Signing__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline )
      {
        IsFileInSystemConfig = CmpIsFileInSystemConfig(&UnicodeString);
        if ( IsFileInSystemConfig < 0 )
        {
          *(_DWORD *)(v4 + 4176) = 16;
          goto LABEL_136;
        }
        fLogOptionFlag &= ~0x1000000u;
      }
      Length = UnicodeString.Length;
    }
    else
    {
      p_UnicodeString = (UNICODE_STRING *)&CmpLogPath;
      CreateOptions[0] = 52;
      if ( (Feature_CLFS_Signing__private_featureState & 0x10) != 0 )
        v22 = Feature_CLFS_Signing__private_featureState & 1;
      else
        v22 = Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline();
      if ( v22 )
        fLogOptionFlag |= 0x1000000u;
      Length = CmpLogPath.Length;
    }
    Destination_8.MaximumLength = Source.Length + CmpClfsLogPrefix.Length + TmLogExt.Length + Length;
    Destination_8.Buffer = (wchar_t *)ExAllocatePool2(256, Destination_8.MaximumLength, 1735554131);
    if ( !Destination_8.Buffer )
    {
      IsFileInSystemConfig = -1073741670;
      *(_DWORD *)(v4 + 4176) = 5;
      goto LABEL_136;
    }
    RtlAppendUnicodeStringToString(&Destination_8, &CmpClfsLogPrefix);
    RtlAppendUnicodeStringToString(&Destination_8, p_UnicodeString);
    RtlAppendUnicodeStringToString(&Destination_8, &Source);
    RtlAppendUnicodeStringToString(&Destination_8, &TmLogExt);
    IsFileInSystemConfig = CmpQueryFileSecurityDescriptor(v19);
    if ( IsFileInSystemConfig < 0 )
    {
      *(_DWORD *)(v4 + 4176) = 6;
      goto LABEL_136;
    }
    v24 = P;
    IsFileInSystemConfig = ClfsCreateLogFile(
                             &pplfoLog,
                             &Destination_8,
                             0xC0000000,
                             7u,
                             P,
                             3u,
                             8u,
                             0,
                             fLogOptionFlag,
                             0,
                             0);
    if ( (Feature_CLFS_Signing__private_featureState & 0x10) != 0 )
      v25 = Feature_CLFS_Signing__private_featureState & 1;
    else
      v25 = Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline();
    if ( v25 )
    {
      v42 = (Feature_AutoCleanupClfsLogfiles__private_featureState & 0x10) != 0
          ? Feature_AutoCleanupClfsLogfiles__private_featureState & 1
          : Feature_AutoCleanupClfsLogfiles__private_IsEnabledDeviceUsageNoInline();
      if ( v42 && IsFileInSystemConfig == -1072037875 )
      {
        LOWORD(fCreateOptions) = 70;
        CmpDeleteCorruptedLogfile(
          p_UnicodeString,
          &Source,
          &TmLogExt,
          &TmContainerExt,
          1,
          L"Container%020d",
          fCreateOptions);
      }
    }
    if ( Source.Buffer )
    {
      ExFreePool(Source.Buffer);
      *(_QWORD *)&Source.Length = 0;
      Source.Buffer = (wchar_t *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    }
    v3 = v64;
    if ( v64 )
      RtlFreeAnsiString(&UnicodeString);
    ExFreePoolWithTag(v24, 0);
    if ( IsFileInSystemConfig >= 0 )
      break;
    if ( v56 )
    {
      *(_DWORD *)(v4 + 4176) = 7;
      goto LABEL_136;
    }
    Buffer = Destination_8.Buffer;
    if ( Destination_8.Buffer )
    {
      ExFreePool(Destination_8.Buffer);
      Destination_8 = 0;
    }
    CmpLogTxrInitEvent(Buffer, v4, (unsigned int)IsFileInSystemConfig);
LABEL_69:
    LOBYTE(v2) = v57;
  }
  memset(&RegistrationData, 0, sizeof(RegistrationData));
  RegistrationData.Version = 1;
  IsFileInSystemConfig = ClfsMgmtRegisterManagedClient(pplfoLog, &RegistrationData, &ClientCookie);
  if ( IsFileInSystemConfig < 0 )
  {
    *(_DWORD *)(v4 + 4176) = 8;
    goto LABEL_136;
  }
  v26 = ExAllocatePool2(256, (unsigned __int16)TmContainerExt + 24LL, 1834110275);
  v27 = (struct _CLFS_MGMT_POLICY *)v26;
  if ( !v26 )
  {
    *(_DWORD *)(v4 + 4176) = 9;
LABEL_136:
    CmpLogTxrInitEvent(v20, v4, (unsigned int)IsFileInSystemConfig);
    if ( ClientCookie )
    {
      ClfsMgmtDeregisterManagedClient(ClientCookie);
      ClientCookie = 0;
    }
    if ( pplfoLog )
      ClfsCloseLogFileObject(pplfoLog);
    if ( Source.Buffer )
      RtlFreeAnsiString(&Source);
    if ( UnicodeString.Buffer )
      RtlFreeAnsiString(&UnicodeString);
    if ( Destination_8.Buffer )
      RtlFreeAnsiString(&Destination_8);
    v51 = (void *)Pool2[6];
    if ( v51 )
      ZwClose(v51);
    v52 = (void *)Pool2[5];
    if ( v52 )
      ObfDereferenceObject(v52);
    v53 = (void *)Pool2[4];
    if ( v53 )
      ZwClose(v53);
    ExFreePoolWithTag(Pool2, 0x6D524D43u);
    ExDeleteResourceLite(Resource);
    ExFreePoolWithTag(Resource, 0);
    *(_DWORD *)(v4 + 4180) = IsFileInSystemConfig;
    return (unsigned int)IsFileInSystemConfig;
  }
  *(_DWORD *)v26 = 1;
  v28 = (unsigned __int16)TmContainerExt + 24;
  *(_DWORD *)(v26 + 12) = 9;
  *(_DWORD *)(v26 + 4) = v28;
  *(_WORD *)(v26 + 16) = TmContainerExt;
  memmove((void *)(v26 + 18), off_140E0D758, (unsigned __int16)TmContainerExt);
  IsFileInSystemConfig = ClfsMgmtInstallPolicy(pplfoLog, v27, (unsigned __int16)TmContainerExt + 24);
  ExFreePoolWithTag(v27, 0);
  if ( IsFileInSystemConfig < 0 )
  {
    *(_DWORD *)(v4 + 4176) = 10;
    goto LABEL_136;
  }
  v29 = (HANDLE *)(Pool2 + 4);
  LogFileName.Length = Destination_8.Length - CmpClfsLogPrefix.Length;
  ObjectAttributes.Length = 48;
  LogFileName.MaximumLength = Destination_8.MaximumLength - CmpClfsLogPrefix.Length;
  ObjectAttributes.RootDirectory = 0;
  LogFileName.Buffer = (wchar_t *)((char *)Destination_8.Buffer + CmpClfsLogPrefix.Length);
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v30 = ZwCreateTransactionManager((PHANDLE)Pool2 + 4, 0xF003Fu, &ObjectAttributes, &LogFileName, CreateOptions[0], 0);
  IsFileInSystemConfig = v30;
  if ( v30 == -1073741771 )
  {
    if ( Destination_8.Buffer )
      RtlFreeAnsiString(&Destination_8);
    if ( pplfoLog )
    {
      ClfsCloseLogFileObject(pplfoLog);
      pplfoLog = 0;
    }
    v11 = ClientCookie;
    if ( ClientCookie )
    {
      ClfsMgmtDeregisterManagedClient(ClientCookie);
      ClientCookie = 0;
    }
    if ( v56 )
      goto LABEL_41;
    v3 = v64;
    goto LABEL_69;
  }
  if ( v30 >= 0 )
    IsFileInSystemConfig = ZwRecoverTransactionManager(*v29);
LABEL_41:
  v20 = Destination_8.Buffer;
  if ( Destination_8.Buffer )
  {
    ExFreePool(Destination_8.Buffer);
    Destination_8 = 0;
  }
  if ( IsFileInSystemConfig < 0 )
  {
    *(_DWORD *)(v4 + 4176) = 11;
    goto LABEL_136;
  }
  if ( pplfoLog )
  {
    ClfsCloseLogFileObject(pplfoLog);
    pplfoLog = 0;
  }
  if ( ClientCookie )
  {
    ClfsMgmtDeregisterManagedClient(ClientCookie);
    ClientCookie = 0;
  }
  v31 = *v29;
  P = 0;
  IsFileInSystemConfig = ObReferenceObjectByHandle(
                           v31,
                           0xF003Fu,
                           (POBJECT_TYPE)TmTransactionManagerObjectType,
                           0,
                           &P,
                           0);
  Pool2[5] = P;
  if ( IsFileInSystemConfig < 0 )
  {
    *(_DWORD *)(v4 + 4176) = 12;
    goto LABEL_136;
  }
  v32 = (HANDLE *)(Pool2 + 6);
  v33 = *(GUID *)(*(_QWORD *)(v4 + 64) + 112LL);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ResourceManagerGuid = v33;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IsFileInSystemConfig = ZwCreateResourceManager(
                           (PHANDLE)Pool2 + 6,
                           0x1F007Fu,
                           *v29,
                           &ResourceManagerGuid,
                           &ObjectAttributes,
                           0,
                           0);
  if ( IsFileInSystemConfig == -1073741771 )
    IsFileInSystemConfig = ZwOpenResourceManager(
                             (PHANDLE)Pool2 + 6,
                             0x1F007Fu,
                             *v29,
                             &ResourceManagerGuid,
                             &ObjectAttributes);
  if ( IsFileInSystemConfig < 0 )
  {
    *(_DWORD *)(v4 + 4176) = 13;
    goto LABEL_136;
  }
  IsFileInSystemConfig = ZwRecoverResourceManager(*v32);
  if ( IsFileInSystemConfig < 0 )
  {
    *(_DWORD *)(v4 + 4176) = 14;
    goto LABEL_136;
  }
  v34 = *v32;
  P = 0;
  IsFileInSystemConfig = ObReferenceObjectByHandle(v34, 0x1F007Fu, (POBJECT_TYPE)TmResourceManagerObjectType, 0, &P, 0);
  Pool2[7] = P;
  if ( IsFileInSystemConfig < 0 )
  {
    *(_DWORD *)(v4 + 4176) = 15;
    goto LABEL_136;
  }
  v35 = v64;
  if ( v64 )
  {
    *(_QWORD *)(v64 + 4168) = Pool2;
    *((_DWORD *)Pool2 + 16) = 1;
    goto LABEL_56;
  }
  v43 = 0;
  CmRmSystem = Pool2;
  v44 = 0;
  while ( 2 )
  {
    v48 = CmpMachineHiveList[v44 + 6];
    if ( v48 && (*((_DWORD *)v48 + 40) & 2) == 0 )
    {
      ++*((_DWORD *)Pool2 + 16);
      v49 = CmpMachineHiveList[v44 + 6];
      goto LABEL_133;
    }
    v50 = CmpMachineHiveList[v44 + 3];
    if ( v50 && (*((_DWORD *)v50 + 40) & 2) == 0 )
    {
      ++*((_DWORD *)Pool2 + 16);
      v49 = CmpMachineHiveList[v44 + 3];
LABEL_133:
      *((_QWORD *)v49 + 521) = Pool2;
    }
    ++v43;
    v44 += 23;
    if ( v43 != 7 )
      continue;
    break;
  }
  *(_QWORD *)(CmpMasterHive + 4168) = Pool2;
  ++*((_DWORD *)Pool2 + 16);
LABEL_56:
  Pool2[10] = v35;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(&CmpRmListLock);
  v36 = (_QWORD *)qword_140EDF4E8;
  if ( *(__int64 **)qword_140EDF4E8 != &CmpRmListHead )
    __fastfail(3u);
  *Pool2 = &CmpRmListHead;
  Pool2[1] = v36;
  *v36 = Pool2;
  qword_140EDF4E8 = (__int64)Pool2;
  ExReleaseFastMutexUnsafe(&CmpRmListLock);
  KeLeaveCriticalRegion();
  if ( (_BYTE)v57 )
    CmpStartRMLog((char *)Pool2, 0);
  return 0;
}

```

## disassembly

```asm
0x1408e282c  mov     rax, rsp
0x1408e282f  push    rbp
0x1408e2830  push    rbx
0x1408e2831  push    rsi
0x1408e2832  push    rdi
0x1408e2833  push    r12
0x1408e2835  push    r13
0x1408e2837  push    r14
0x1408e2839  push    r15
0x1408e283b  lea     rbp, [rax-0F8h]
0x1408e2842  sub     rsp, 1B8h
0x1408e2849  movaps  xmmword ptr [rax-58h], xmm6
0x1408e284d  movaps  xmmword ptr [rax-68h], xmm7
0x1408e2851  mov     rax, cs:__security_cookie
0x1408e2858  xor     rax, rsp
0x1408e285b  mov     [rbp+0F0h+var_68], rax
0x1408e2862  xor     r13d, r13d
0x1408e2865  mov     [rbp+0F0h+var_130], rcx
0x1408e2869  xorps   xmm0, xmm0
0x1408e286c  mov     qword ptr [rbp+0F0h+Source.Length], r13
0x1408e2870  xor     eax, eax
0x1408e2872  mov     [rbp+0F0h+Source.Buffer], r13
0x1408e2876  cmp     byte ptr cs:NlsMbOemCodePageTag+6, r13b
0x1408e287d  xorps   xmm1, xmm1
0x1408e2880  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.ObjectName], xmm0
0x1408e2884  mov     r15b, dl
0x1408e2887  mov     r12, rcx
0x1408e288a  movups  xmmword ptr [rbp+0F0h+ObjectAttributes+1Ch], xmm0
0x1408e288e  mov     qword ptr [rbp+0F0h+UnicodeString.Length], r13
0x1408e2892  movups  [rbp+0F0h+var_A8], xmm0
0x1408e2896  mov     [rbp+0F0h+UnicodeString.Buffer], r13
0x1408e289a  movups  xmmword ptr [rbp+0F0h+ResourceManagerGuid.Data1], xmm1
0x1408e289e  mov     [rsp+1F0h+Destination.Buffer], r13
0x1408e28a3  movups  xmmword ptr [rbp+0F0h+Uuid.Data1], xmm0
0x1408e28a7  mov     [rsp+1F0h+var_180], r13
0x1408e28ac  movups  xmmword ptr [rbp+0F0h+var_78.Data1], xmm1
0x1408e28b0  mov     [rbp+0F0h+pplfoLog], r13
0x1408e28b4  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.Length], xmm0
0x1408e28b8  mov     qword ptr [rbp+0F0h+LogFileName.Length], r13
0x1408e28bc  mov     [rbp+0F0h+LogFileName.Buffer], r13
0x1408e28c0  mov     [rbp+0F0h+P], r13
0x1408e28c4  mov     [rbp+0F0h+ClientCookie], r13
0x1408e28c8  movups  xmmword ptr [rbp+0F0h+RegistrationData.Version], xmm0
0x1408e28cc  mov     dword ptr [rbp+0F0h+RegistrationData.LogUnpinnedCallbackData], eax
0x1408e28cf  movups  xmmword ptr [rbp+0F0h+RegistrationData.AdvanceTailCallbackData], xmm0
0x1408e28d3  mov     byte ptr [rsp+1F0h+Destination.Length], r13b
0x1408e28d8  movups  xmmword ptr [rbp+0F0h+RegistrationData.LogGrowthCompleteCallbackData], xmm0
0x1408e28dc  jnz     loc_1408E3043
0x1408e28e2  mov     rbx, cs:qword_140E0D200
0x1408e28e9  test    rcx, rcx
0x1408e28ec  cmovnz  rbx, rcx
0x1408e28f0  test    dword ptr [rbx+0A0h], 8001h
0x1408e28fa  jnz     loc_1408E3043
0x1408e2900  mov     esi, 0C000022Dh
0x1408e2905  mov     r14, 0FFFFFFFFFF676980h
0x1408e290c  lea     rcx, [rbp+0F0h+Uuid]; Uuid
0x1408e2910  call    ExUuidCreate
0x1408e2915  mov     edi, eax
0x1408e2917  cmp     eax, esi
0x1408e2919  jz      loc_1408E3077
0x1408e291f  test    eax, eax
0x1408e2921  js      loc_1408E308D
0x1408e2927  lea     rcx, [rbp+0F0h+var_78]; Uuid
0x1408e292b  call    ExUuidCreate
0x1408e2930  mov     edi, eax
0x1408e2932  cmp     eax, esi
0x1408e2934  jz      loc_1408E30BF
0x1408e293a  test    eax, eax
0x1408e293c  js      loc_1408E308D
0x1408e2942  mov     edx, 88h
0x1408e2947  mov     edi, 6D524D43h
0x1408e294c  mov     r8d, edi
0x1408e294f  lea     ecx, [rdx+78h]
0x1408e2952  call    ExAllocatePool2
0x1408e2957  mov     rsi, rax
0x1408e295a  test    rax, rax
0x1408e295d  jz      loc_1408E3099
0x1408e2963  mov     edx, 68h ; 'h'
0x1408e2968  mov     r8d, 6C724D43h
0x1408e296e  lea     ecx, [rdx-28h]
0x1408e2971  call    ExAllocatePool2
0x1408e2976  mov     [rbp+0F0h+Resource], rax
0x1408e297a  mov     rdx, rax
0x1408e297d  test    rax, rax
0x1408e2980  jz      loc_1408E30D5
0x1408e2986  lea     rax, [rsi+10h]
0x1408e298a  mov     [rax+8], rax
0x1408e298e  mov     [rax], rax
0x1408e2991  mov     al, r15b
0x1408e2994  neg     al
0x1408e2996  mov     [rsi+58h], r13
0x1408e299a  mov     [rsi+60h], r13
0x1408e299e  sbb     ecx, ecx
0x1408e29a0  and     ecx, 4
0x1408e29a3  mov     [rsi+68h], ecx
0x1408e29a6  mov     rcx, rdx; Resource
0x1408e29a9  mov     [rsi+6Ch], r13
0x1408e29ad  mov     [rsi+44h], r13d
0x1408e29b1  mov     [rsi+48h], r13
0x1408e29b5  mov     [rsi+80h], rdx
0x1408e29bc  call    ExInitializeResourceLite
0x1408e29c1  mov     r8, [rbx+40h]
0x1408e29c5  mov     eax, 6D746D72h
0x1408e29ca  movups  xmm6, xmmword ptr [rbp+0F0h+Uuid.Data1]
0x1408e29ce  mov     r14d, 1
0x1408e29d4  movups  xmm7, xmmword ptr [rbp+0F0h+var_78.Data1]
0x1408e29d8  cmp     [r8+0A4h], eax
0x1408e29df  jz      loc_1408E30EB
0x1408e29e5  mov     [rbp+0F0h+CreateOptions], r13d
0x1408e29e9  mov     r13d, 200h
0x1408e29ef  mov     [r8+0A4h], eax
0x1408e29f6  mov     rax, [rbx+40h]
0x1408e29fa  test    r12, r12
0x1408e29fd  movzx   r15d, r15b
0x1408e2a01  cmovz   r15d, r14d
0x1408e2a05  mov     [rsp+1F0h+var_178], r14d
0x1408e2a0a  mov     [rsp+1F0h+var_174], r15d
0x1408e2a0f  movdqu  xmmword ptr [rax+94h], xmm7
0x1408e2a17  mov     rax, [rbx+40h]
0x1408e2a1b  movdqu  xmmword ptr [rax+70h], xmm6
0x1408e2a20  mov     rax, [rbx+40h]
0x1408e2a24  movdqu  xmmword ptr [rax+80h], xmm6
0x1408e2a2c  call    CmpLockRegistry
0x1408e2a31  mov     rcx, rbx
0x1408e2a34  call    HvLockHiveFlusherShared
0x1408e2a39  mov     rcx, rbx
0x1408e2a3c  call    HvLockHiveWriter
0x1408e2a41  mov     rcx, rbx
0x1408e2a44  call    HvMarkBaseBlockDirty
0x1408e2a49  mov     rcx, rbx
0x1408e2a4c  call    HvUnlockHiveWriter
0x1408e2a51  mov     rcx, rbx
0x1408e2a54  call    HvUnlockHiveFlusherShared
0x1408e2a59  call    CmpUnlockRegistry
0x1408e2a5e  jmp     short loc_1408E2A6F
0x1408e2a60  mov     [rbp+0F0h+CreateOptions], r13d
0x1408e2a64  mov     r13d, 200h
0x1408e2a6a  test    r9b, r9b
0x1408e2a6d  jnz     short loc_1408E2A2C
0x1408e2a6f  mov     rcx, [rbx+40h]
0x1408e2a73  lea     rdx, [rbp+0F0h+Source]
0x1408e2a77  mov     r15, [rbx+610h]
0x1408e2a7e  add     rcx, 94h
0x1408e2a85  mov     r8b, r14b
0x1408e2a88  call    RtlStringFromGUIDEx
0x1408e2a8d  mov     edi, eax
0x1408e2a8f  test    eax, eax
0x1408e2a91  js      loc_1408E32A7
0x1408e2a97  test    r12, r12
0x1408e2a9a  jnz     loc_1408E2EF9
0x1408e2aa0  lea     r12, CmpLogPath
0x1408e2aa7  mov     [rbp+0F0h+CreateOptions], 34h ; '4'
0x1408e2aae  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x1408e2ab4  test    al, 10h
0x1408e2ab6  jnz     loc_1408E3117
0x1408e2abc  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x1408e2ac1  test    eax, eax
0x1408e2ac3  jz      short loc_1408E2ACA
0x1408e2ac5  bts     r13d, 18h
0x1408e2aca  movzx   eax, cs:CmpLogPath.Length
0x1408e2ad1  add     ax, cs:TmLogExt.Length
0x1408e2ad8  mov     ecx, 100h
0x1408e2add  add     ax, cs:CmpClfsLogPrefix.Length
0x1408e2ae4  mov     r8d, 67727453h
0x1408e2aea  add     ax, [rbp+0F0h+Source.Length]
0x1408e2aee  movzx   edx, ax
0x1408e2af1  mov     word ptr [rsp+1F0h+Destination.Buffer+2], dx
0x1408e2af6  call    ExAllocatePool2
0x1408e2afb  mov     [rsp+1F0h+var_180], rax
0x1408e2b00  test    rax, rax
0x1408e2b03  jz      loc_1408E3275
0x1408e2b09  lea     rdx, CmpClfsLogPrefix; Source
0x1408e2b10  lea     rcx, [rsp+1F0h+Destination.Buffer]; Destination
0x1408e2b15  call    RtlAppendUnicodeStringToString
0x1408e2b1a  mov     rdx, r12; Source
0x1408e2b1d  lea     rcx, [rsp+1F0h+Destination.Buffer]; Destination
0x1408e2b22  call    RtlAppendUnicodeStringToString
0x1408e2b27  lea     rdx, [rbp+0F0h+Source]; Source
0x1408e2b2b  lea     rcx, [rsp+1F0h+Destination.Buffer]; Destination
0x1408e2b30  call    RtlAppendUnicodeStringToString
0x1408e2b35  lea     rdx, TmLogExt; Source
0x1408e2b3c  lea     rcx, [rsp+1F0h+Destination.Buffer]; Destination
0x1408e2b41  call    RtlAppendUnicodeStringToString
0x1408e2b46  lea     rdx, [rbp+0F0h+P]
0x1408e2b4a  mov     rcx, r15; Handle
0x1408e2b4d  call    CmpQueryFileSecurityDescriptor
0x1408e2b52  mov     edi, eax
0x1408e2b54  test    eax, eax
0x1408e2b56  js      loc_1408E3266
0x1408e2b5c  mov     r15, [rbp+0F0h+P]
0x1408e2b60  lea     rdx, [rsp+1F0h+Destination.Buffer]; puszLogFileName
0x1408e2b65  mov     [rsp+1F0h+cbContext], 0; cbContext
0x1408e2b6d  lea     rcx, [rbp+0F0h+pplfoLog]; pplfoLog
0x1408e2b71  mov     [rsp+1F0h+pvContext], 0; pvContext
0x1408e2b7a  mov     r9d, 7; dwShareMode
0x1408e2b80  mov     [rsp+1F0h+fLogOptionFlag], r13d; fLogOptionFlag
0x1408e2b85  mov     r8d, 0C0000000h; fDesiredAccess
0x1408e2b8b  mov     [rsp+1F0h+fFlagsAndAttributes], 0; fFlagsAndAttributes
0x1408e2b93  mov     dword ptr [rsp+1F0h+fCreateOptions], 8; fCreateOptions
0x1408e2b9b  mov     [rsp+1F0h+fCreateDisposition], 3; fCreateDisposition
0x1408e2ba3  mov     [rsp+1F0h+psdLogFile], r15; psdLogFile
0x1408e2ba8  call    cs:__imp_ClfsCreateLogFile
0x1408e2baf  nop     dword ptr [rax+rax+00h]
0x1408e2bb4  mov     edi, eax
0x1408e2bb6  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x1408e2bbc  test    al, 10h
0x1408e2bbe  jnz     loc_1408E3127
0x1408e2bc4  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x1408e2bc9  test    eax, eax
0x1408e2bcb  jnz     loc_1408E312F
0x1408e2bd1  mov     rcx, [rbp+0F0h+Source.Buffer]; P
0x1408e2bd5  test    rcx, rcx
0x1408e2bd8  jz      short loc_1408E2BF0
0x1408e2bda  call    ExFreePool
0x1408e2bdf  xorps   xmm0, xmm0
0x1408e2be2  movups  xmmword ptr [rbp+0F0h+Source.Length], xmm0
0x1408e2be6  psrldq  xmm0, 8
0x1408e2beb  movq    [rbp+0F0h+Source.Buffer], xmm0
0x1408e2bf0  mov     r12, [rbp+0F0h+var_130]
0x1408e2bf4  test    r12, r12
0x1408e2bf7  jnz     loc_1408E3145
0x1408e2bfd  xor     edx, edx; Tag
0x1408e2bff  mov     rcx, r15; P
0x1408e2c02  call    ExFreePoolWithTag
0x1408e2c07  test    edi, edi
0x1408e2c09  js      loc_1408E2F5C
0x1408e2c0f  mov     rcx, [rbp+0F0h+pplfoLog]; LogFile
0x1408e2c13  lea     r8, [rbp+0F0h+ClientCookie]; ClientCookie
0x1408e2c17  xorps   xmm0, xmm0
0x1408e2c1a  lea     rdx, [rbp+0F0h+RegistrationData]; RegistrationData
0x1408e2c1e  xor     eax, eax
0x1408e2c20  movups  xmmword ptr [rbp+0F0h+RegistrationData.Version], xmm0
0x1408e2c24  mov     [rbp+0F0h+RegistrationData.Version], r14d
0x1408e2c28  movups  xmmword ptr [rbp+0F0h+RegistrationData.AdvanceTailCallbackData], xmm0
0x1408e2c2c  mov     [rbp+0F0h+RegistrationData.LogUnpinnedCallbackData], rax
0x1408e2c30  movups  xmmword ptr [rbp+0F0h+RegistrationData.LogGrowthCompleteCallbackData], xmm0
0x1408e2c34  call    cs:__imp_ClfsMgmtRegisterManagedClient
0x1408e2c3b  nop     dword ptr [rax+rax+00h]
0x1408e2c40  mov     edi, eax
0x1408e2c42  test    eax, eax
0x1408e2c44  js      loc_1408E3257
0x1408e2c4a  movzx   edx, cs:TmContainerExt
0x1408e2c51  mov     ecx, 100h
0x1408e2c56  add     rdx, 18h
0x1408e2c5a  mov     r8d, 6D524D43h
0x1408e2c60  call    ExAllocatePool2
0x1408e2c65  mov     r15, rax
0x1408e2c68  test    rax, rax
0x1408e2c6b  jz      loc_1408E3248
0x1408e2c71  mov     [rax], r14d
0x1408e2c74  movzx   ecx, cs:TmContainerExt
0x1408e2c7b  add     ecx, 18h
0x1408e2c7e  mov     dword ptr [rax+0Ch], 9
0x1408e2c85  mov     [rax+4], ecx
0x1408e2c88  movzx   ecx, cs:TmContainerExt
0x1408e2c8f  mov     [rax+10h], cx
0x1408e2c93  lea     rcx, [rax+12h]; void *
0x1408e2c97  movzx   r8d, cs:TmContainerExt; Size
0x1408e2c9f  mov     rdx, cs:off_140E0D758; Src
0x1408e2ca6  call    memmove
0x1408e2cab  movzx   r8d, cs:TmContainerExt
0x1408e2cb3  mov     rdx, r15; Policy
0x1408e2cb6  mov     rcx, [rbp+0F0h+pplfoLog]; LogFile
0x1408e2cba  add     r8d, 18h; PolicyLength
0x1408e2cbe  call    cs:__imp_ClfsMgmtInstallPolicy
0x1408e2cc5  nop     dword ptr [rax+rax+00h]
0x1408e2cca  xor     edx, edx; Tag
0x1408e2ccc  mov     rcx, r15; P
0x1408e2ccf  mov     edi, eax
0x1408e2cd1  call    ExFreePoolWithTag
0x1408e2cd6  test    edi, edi
0x1408e2cd8  js      loc_1408E3239
0x1408e2cde  movzx   ecx, cs:CmpClfsLogPrefix.Length
0x1408e2ce5  lea     r12, [rsi+20h]
0x1408e2ce9  movzx   eax, word ptr [rsp+1F0h+Destination.Buffer]
0x1408e2cee  lea     r9, [rbp+0F0h+LogFileName]; LogFileName
0x1408e2cf2  sub     ax, cx
0x1408e2cf5  mov     [rsp+1F0h+fCreateDisposition], 0; CommitStrength
0x1408e2cfd  mov     [rbp+0F0h+LogFileName.Length], ax
0x1408e2d01  lea     r8, [rbp+0F0h+ObjectAttributes]; ObjectAttributes
0x1408e2d05  movzx   eax, word ptr [rsp+1F0h+Destination.Buffer+2]
0x1408e2d0a  xorps   xmm0, xmm0
0x1408e2d0d  sub     ax, cx
0x1408e2d10  mov     [rbp+0F0h+ObjectAttributes.Length], 30h ; '0'
0x1408e2d17  mov     [rbp+0F0h+LogFileName.MaximumLength], ax
0x1408e2d1b  mov     r15d, 0F003Fh
0x1408e2d21  mov     eax, ecx
0x1408e2d23  mov     [rbp+0F0h+ObjectAttributes.RootDirectory], 0
0x1408e2d2b  add     rax, [rsp+1F0h+var_180]
0x1408e2d30  mov     edx, r15d; DesiredAccess
0x1408e2d33  mov     [rbp+0F0h+LogFileName.Buffer], rax
0x1408e2d37  mov     rcx, r12; TmHandle
0x1408e2d3a  mov     eax, [rbp+0F0h+CreateOptions]
0x1408e2d3d  mov     dword ptr [rsp+1F0h+psdLogFile], eax; CreateOptions
0x1408e2d41  mov     [rbp+0F0h+ObjectAttributes.Attributes], 240h
0x1408e2d48  mov     [rbp+0F0h+ObjectAttributes.ObjectName], 0
0x1408e2d50  movdqu  xmmword ptr [rbp+0F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1408e2d55  call    ZwCreateTransactionManager
0x1408e2d5a  mov     edi, eax
0x1408e2d5c  cmp     eax, 0C0000035h
  ... truncated ...
```
