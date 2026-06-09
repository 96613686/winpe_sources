# CmpInitCmRM

- ea: `0x1408ad910`
- end: `0x1408ae39a`
- name: `CmpInitCmRM`
- size: `2698`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `40`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1404b1374`
- `0x1407f5074`
- `0x140ae5900`

## callees

- `0x140224f70`
- `0x140224f90`
- `0x1402268e0`
- `0x140296e70`
- `0x14029b7c0`
- `0x1402f8270`
- `0x140389680`
- `0x1403f4830`
- `0x14042e7b0`
- `0x14051136c`
- `0x140697724`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406dc130`
- `0x1406dc290`
- `0x1406dcf30`
- `0x1406dd7b0`
- `0x1406dd7d0`
- `0x1406f4480`
- `0x140806484`
- `0x140856b34`
- `0x140856b9c`
- `0x1408820b0`
- `0x14088c344`
- `0x1408a4070`
- `0x1408ad040`
- `0x1408ad910`
- `0x1408af21c`
- `0x1408af8e4`
- `0x1408afccc`
- `0x1408b0708`
- `0x1408eeff0`
- `0x14092bbb0`
- `0x140acc74c`
- `0x140aec58c`
- `0x140bae410`
- `0x140bae8c0`
- `0x140bae8e0`
- `0x140bf7870`
- `0x140bf7950`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x1408adc8c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateLogFile` at `0x1408adc8c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtRegisterManagedClient` at `0x1408add18`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtRegisterManagedClient` at `0x1408add18`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1408adda2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1408adda2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408ae0a7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408ae246`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x140b51041`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408ae0a7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408ae246`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x140b51041`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x1408ae077`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x1408ae25f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x140b51024`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x1408ae077`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x1408ae25f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtDeregisterManagedClient` at `0x140b51024`

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
  __int64 Pool2; // rsi
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
  __int64 *v36; // rax
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
  Pool2 = ExAllocatePool2(256, 136, 1834110275);
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
    ExFreePoolWithTag((PVOID)Pool2, 0x6D524D43u);
    *(_DWORD *)(v4 + 4176) = 2;
    goto LABEL_84;
  }
  *(_QWORD *)(Pool2 + 24) = Pool2 + 16;
  *(_QWORD *)(Pool2 + 16) = Pool2 + 16;
  *(_QWORD *)(Pool2 + 88) = 0;
  *(_QWORD *)(Pool2 + 96) = 0;
  *(_DWORD *)(Pool2 + 104) = (_BYTE)v2 != 0 ? 4 : 0;
  *(_QWORD *)(Pool2 + 108) = 0;
  *(_DWORD *)(Pool2 + 68) = 0;
  *(_QWORD *)(Pool2 + 72) = 0;
  *(_QWORD *)(Pool2 + 128) = v10;
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
    v51 = *(void **)(Pool2 + 48);
    if ( v51 )
      ZwClose(v51);
    v52 = *(void **)(Pool2 + 40);
    if ( v52 )
      ObfDereferenceObject(v52);
    v53 = *(void **)(Pool2 + 32);
    if ( v53 )
      ZwClose(v53);
    ExFreePoolWithTag((PVOID)Pool2, 0x6D524D43u);
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
  memmove((void *)(v26 + 18), off_140E0D748, (unsigned __int16)TmContainerExt);
  IsFileInSystemConfig = ClfsMgmtInstallPolicy(pplfoLog, v27, (unsigned __int16)TmContainerExt + 24);
  ExFreePoolWithTag(v27, 0);
  if ( IsFileInSystemConfig < 0 )
  {
    *(_DWORD *)(v4 + 4176) = 10;
    goto LABEL_136;
  }
  v29 = (HANDLE *)(Pool2 + 32);
  LogFileName.Length = Destination_8.Length - CmpClfsLogPrefix.Length;
  ObjectAttributes.Length = 48;
  LogFileName.MaximumLength = Destination_8.MaximumLength - CmpClfsLogPrefix.Length;
  ObjectAttributes.RootDirectory = 0;
  LogFileName.Buffer = (wchar_t *)((char *)Destination_8.Buffer + CmpClfsLogPrefix.Length);
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v30 = ZwCreateTransactionManager(
          (PHANDLE)(Pool2 + 32),
          0xF003Fu,
          &ObjectAttributes,
          &LogFileName,
          CreateOptions[0],
          0);
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
                           (POBJECT_TYPE)stru_140FBF218.WaitBlock[2].WaitListEntry.Blink,
                           0,
                           &P,
                           0);
  *(_QWORD *)(Pool2 + 40) = P;
  if ( IsFileInSystemConfig < 0 )
  {
    *(_DWORD *)(v4 + 4176) = 12;
    goto LABEL_136;
  }
  v32 = (HANDLE *)(Pool2 + 48);
  v33 = *(GUID *)(*(_QWORD *)(v4 + 64) + 112LL);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ResourceManagerGuid = v33;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IsFileInSystemConfig = ZwCreateResourceManager(
                           (PHANDLE)(Pool2 + 48),
                           0x1F007Fu,
                           *v29,
                           &ResourceManagerGuid,
                           &ObjectAttributes,
                           0,
                           0);
  if ( IsFileInSystemConfig == -1073741771 )
    IsFileInSystemConfig = ZwOpenResourceManager(
                             (PHANDLE)(Pool2 + 48),
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
  IsFileInSystemConfig = ObReferenceObjectByHandle(
                           v34,
                           0x1F007Fu,
                           *(POBJECT_TYPE *)&stru_140FBF218.WaitBlockFill11[112],
                           0,
                           &P,
                           0);
  *(_QWORD *)(Pool2 + 56) = P;
  if ( IsFileInSystemConfig < 0 )
  {
    *(_DWORD *)(v4 + 4176) = 15;
    goto LABEL_136;
  }
  v35 = v64;
  if ( v64 )
  {
    *(_QWORD *)(v64 + 4168) = Pool2;
    *(_DWORD *)(Pool2 + 64) = 1;
    goto LABEL_56;
  }
  v43 = 0;
  WheapPfaLock.Timer.TimerListEntry.Blink = (struct _LIST_ENTRY *)Pool2;
  v44 = 0;
  while ( 2 )
  {
    v48 = CmpMachineHiveList[v44 + 6];
    if ( v48 && (*((_DWORD *)v48 + 40) & 2) == 0 )
    {
      ++*(_DWORD *)(Pool2 + 64);
      v49 = CmpMachineHiveList[v44 + 6];
      goto LABEL_133;
    }
    v50 = CmpMachineHiveList[v44 + 3];
    if ( v50 && (*((_DWORD *)v50 + 40) & 2) == 0 )
    {
      ++*(_DWORD *)(Pool2 + 64);
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
  ++*(_DWORD *)(Pool2 + 64);
LABEL_56:
  *(_QWORD *)(Pool2 + 80) = v35;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(&CmpRmListLock);
  v36 = (__int64 *)qword_140EDF528;
  if ( *(__int64 **)qword_140EDF528 != &CmpRmListHead )
    __fastfail(3u);
  *(_QWORD *)Pool2 = &CmpRmListHead;
  *(_QWORD *)(Pool2 + 8) = v36;
  *v36 = Pool2;
  qword_140EDF528 = Pool2;
  ExReleaseFastMutexUnsafe(&CmpRmListLock);
  KeLeaveCriticalRegion();
  if ( (_BYTE)v57 )
    CmpStartRMLog(Pool2, 0);
  return 0;
}

```

## disassembly

```asm
0x1408ad910  mov     rax, rsp
0x1408ad913  push    rbp
0x1408ad914  push    rbx
0x1408ad915  push    rsi
0x1408ad916  push    rdi
0x1408ad917  push    r12
0x1408ad919  push    r13
0x1408ad91b  push    r14
0x1408ad91d  push    r15
0x1408ad91f  lea     rbp, [rax-0F8h]
0x1408ad926  sub     rsp, 1B8h
0x1408ad92d  movaps  xmmword ptr [rax-58h], xmm6
0x1408ad931  movaps  xmmword ptr [rax-68h], xmm7
0x1408ad935  mov     rax, cs:__security_cookie
0x1408ad93c  xor     rax, rsp
0x1408ad93f  mov     [rbp+0F0h+var_68], rax
0x1408ad946  xor     r13d, r13d
0x1408ad949  mov     [rbp+0F0h+var_130], rcx
0x1408ad94d  xorps   xmm0, xmm0
0x1408ad950  mov     qword ptr [rbp+0F0h+Source.Length], r13
0x1408ad954  xor     eax, eax
0x1408ad956  mov     [rbp+0F0h+Source.Buffer], r13
0x1408ad95a  cmp     byte ptr cs:NlsMbOemCodePageTag+6, r13b
0x1408ad961  xorps   xmm1, xmm1
0x1408ad964  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.ObjectName], xmm0
0x1408ad968  mov     r15b, dl
0x1408ad96b  mov     r12, rcx
0x1408ad96e  movups  xmmword ptr [rbp+0F0h+ObjectAttributes+1Ch], xmm0
0x1408ad972  mov     qword ptr [rbp+0F0h+UnicodeString.Length], r13
0x1408ad976  movups  [rbp+0F0h+var_A8], xmm0
0x1408ad97a  mov     [rbp+0F0h+UnicodeString.Buffer], r13
0x1408ad97e  movups  xmmword ptr [rbp+0F0h+ResourceManagerGuid.Data1], xmm1
0x1408ad982  mov     [rsp+1F0h+Destination.Buffer], r13
0x1408ad987  movups  xmmword ptr [rbp+0F0h+Uuid.Data1], xmm0
0x1408ad98b  mov     [rsp+1F0h+var_180], r13
0x1408ad990  movups  xmmword ptr [rbp+0F0h+var_78.Data1], xmm1
0x1408ad994  mov     [rbp+0F0h+pplfoLog], r13
0x1408ad998  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.Length], xmm0
0x1408ad99c  mov     qword ptr [rbp+0F0h+LogFileName.Length], r13
0x1408ad9a0  mov     [rbp+0F0h+LogFileName.Buffer], r13
0x1408ad9a4  mov     [rbp+0F0h+P], r13
0x1408ad9a8  mov     [rbp+0F0h+ClientCookie], r13
0x1408ad9ac  movups  xmmword ptr [rbp+0F0h+RegistrationData.Version], xmm0
0x1408ad9b0  mov     dword ptr [rbp+0F0h+RegistrationData.LogUnpinnedCallbackData], eax
0x1408ad9b3  movups  xmmword ptr [rbp+0F0h+RegistrationData.AdvanceTailCallbackData], xmm0
0x1408ad9b7  mov     byte ptr [rsp+1F0h+Destination.Length], r13b
0x1408ad9bc  movups  xmmword ptr [rbp+0F0h+RegistrationData.LogGrowthCompleteCallbackData], xmm0
0x1408ad9c0  jnz     loc_1408AE127
0x1408ad9c6  mov     rbx, cs:qword_140E0D200
0x1408ad9cd  test    rcx, rcx
0x1408ad9d0  cmovnz  rbx, rcx
0x1408ad9d4  test    dword ptr [rbx+0A0h], 8001h
0x1408ad9de  jnz     loc_1408AE127
0x1408ad9e4  mov     esi, 0C000022Dh
0x1408ad9e9  mov     r14, 0FFFFFFFFFF676980h
0x1408ad9f0  lea     rcx, [rbp+0F0h+Uuid]; Uuid
0x1408ad9f4  call    ExUuidCreate
0x1408ad9f9  mov     edi, eax
0x1408ad9fb  cmp     eax, esi
0x1408ad9fd  jz      loc_1408AE15B
0x1408ada03  test    eax, eax
0x1408ada05  js      loc_1408AE171
0x1408ada0b  lea     rcx, [rbp+0F0h+var_78]; Uuid
0x1408ada0f  call    ExUuidCreate
0x1408ada14  mov     edi, eax
0x1408ada16  cmp     eax, esi
0x1408ada18  jz      loc_1408AE1A3
0x1408ada1e  test    eax, eax
0x1408ada20  js      loc_1408AE171
0x1408ada26  mov     edx, 88h
0x1408ada2b  mov     edi, 6D524D43h
0x1408ada30  mov     r8d, edi
0x1408ada33  lea     ecx, [rdx+78h]
0x1408ada36  call    ExAllocatePool2
0x1408ada3b  mov     rsi, rax
0x1408ada3e  test    rax, rax
0x1408ada41  jz      loc_1408AE17D
0x1408ada47  mov     edx, 68h ; 'h'
0x1408ada4c  mov     r8d, 6C724D43h
0x1408ada52  lea     ecx, [rdx-28h]
0x1408ada55  call    ExAllocatePool2
0x1408ada5a  mov     [rbp+0F0h+Resource], rax
0x1408ada5e  mov     rdx, rax
0x1408ada61  test    rax, rax
0x1408ada64  jz      loc_1408AE1B9
0x1408ada6a  lea     rax, [rsi+10h]
0x1408ada6e  mov     [rax+8], rax
0x1408ada72  mov     [rax], rax
0x1408ada75  mov     al, r15b
0x1408ada78  neg     al
0x1408ada7a  mov     [rsi+58h], r13
0x1408ada7e  mov     [rsi+60h], r13
0x1408ada82  sbb     ecx, ecx
0x1408ada84  and     ecx, 4
0x1408ada87  mov     [rsi+68h], ecx
0x1408ada8a  mov     rcx, rdx; Resource
0x1408ada8d  mov     [rsi+6Ch], r13
0x1408ada91  mov     [rsi+44h], r13d
0x1408ada95  mov     [rsi+48h], r13
0x1408ada99  mov     [rsi+80h], rdx
0x1408adaa0  call    ExInitializeResourceLite
0x1408adaa5  mov     r8, [rbx+40h]
0x1408adaa9  mov     eax, 6D746D72h
0x1408adaae  movups  xmm6, xmmword ptr [rbp+0F0h+Uuid.Data1]
0x1408adab2  mov     r14d, 1
0x1408adab8  movups  xmm7, xmmword ptr [rbp+0F0h+var_78.Data1]
0x1408adabc  cmp     [r8+0A4h], eax
0x1408adac3  jz      loc_1408AE1CF
0x1408adac9  mov     [rbp+0F0h+CreateOptions], r13d
0x1408adacd  mov     r13d, 200h
0x1408adad3  mov     [r8+0A4h], eax
0x1408adada  mov     rax, [rbx+40h]
0x1408adade  test    r12, r12
0x1408adae1  movzx   r15d, r15b
0x1408adae5  cmovz   r15d, r14d
0x1408adae9  mov     [rsp+1F0h+var_178], r14d
0x1408adaee  mov     [rsp+1F0h+var_174], r15d
0x1408adaf3  movdqu  xmmword ptr [rax+94h], xmm7
0x1408adafb  mov     rax, [rbx+40h]
0x1408adaff  movdqu  xmmword ptr [rax+70h], xmm6
0x1408adb04  mov     rax, [rbx+40h]
0x1408adb08  movdqu  xmmword ptr [rax+80h], xmm6
0x1408adb10  call    CmpLockRegistry
0x1408adb15  mov     rcx, rbx
0x1408adb18  call    HvLockHiveFlusherShared
0x1408adb1d  mov     rcx, rbx
0x1408adb20  call    HvLockHiveWriter
0x1408adb25  mov     rcx, rbx
0x1408adb28  call    HvMarkBaseBlockDirty
0x1408adb2d  mov     rcx, rbx
0x1408adb30  call    HvUnlockHiveWriter
0x1408adb35  mov     rcx, rbx
0x1408adb38  call    HvUnlockHiveFlusherShared
0x1408adb3d  call    CmpUnlockRegistry
0x1408adb42  jmp     short loc_1408ADB53
0x1408adb44  mov     [rbp+0F0h+CreateOptions], r13d
0x1408adb48  mov     r13d, 200h
0x1408adb4e  test    r9b, r9b
0x1408adb51  jnz     short loc_1408ADB10
0x1408adb53  mov     rcx, [rbx+40h]
0x1408adb57  lea     rdx, [rbp+0F0h+Source]
0x1408adb5b  mov     r15, [rbx+610h]
0x1408adb62  add     rcx, 94h
0x1408adb69  mov     r8b, r14b
0x1408adb6c  call    RtlStringFromGUIDEx
0x1408adb71  mov     edi, eax
0x1408adb73  test    eax, eax
0x1408adb75  js      loc_1408AE38B
0x1408adb7b  test    r12, r12
0x1408adb7e  jnz     loc_1408ADFDD
0x1408adb84  lea     r12, CmpLogPath
0x1408adb8b  mov     [rbp+0F0h+CreateOptions], 34h ; '4'
0x1408adb92  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x1408adb98  test    al, 10h
0x1408adb9a  jnz     loc_1408AE1FB
0x1408adba0  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x1408adba5  test    eax, eax
0x1408adba7  jz      short loc_1408ADBAE
0x1408adba9  bts     r13d, 18h
0x1408adbae  movzx   eax, cs:CmpLogPath.Length
0x1408adbb5  add     ax, cs:TmLogExt.Length
0x1408adbbc  mov     ecx, 100h
0x1408adbc1  add     ax, cs:CmpClfsLogPrefix.Length
0x1408adbc8  mov     r8d, 67727453h
0x1408adbce  add     ax, [rbp+0F0h+Source.Length]
0x1408adbd2  movzx   edx, ax
0x1408adbd5  mov     word ptr [rsp+1F0h+Destination.Buffer+2], dx
0x1408adbda  call    ExAllocatePool2
0x1408adbdf  mov     [rsp+1F0h+var_180], rax
0x1408adbe4  test    rax, rax
0x1408adbe7  jz      loc_1408AE359
0x1408adbed  lea     rdx, CmpClfsLogPrefix; Source
0x1408adbf4  lea     rcx, [rsp+1F0h+Destination.Buffer]; Destination
0x1408adbf9  call    RtlAppendUnicodeStringToString
0x1408adbfe  mov     rdx, r12; Source
0x1408adc01  lea     rcx, [rsp+1F0h+Destination.Buffer]; Destination
0x1408adc06  call    RtlAppendUnicodeStringToString
0x1408adc0b  lea     rdx, [rbp+0F0h+Source]; Source
0x1408adc0f  lea     rcx, [rsp+1F0h+Destination.Buffer]; Destination
0x1408adc14  call    RtlAppendUnicodeStringToString
0x1408adc19  lea     rdx, TmLogExt; Source
0x1408adc20  lea     rcx, [rsp+1F0h+Destination.Buffer]; Destination
0x1408adc25  call    RtlAppendUnicodeStringToString
0x1408adc2a  lea     rdx, [rbp+0F0h+P]
0x1408adc2e  mov     rcx, r15; Handle
0x1408adc31  call    CmpQueryFileSecurityDescriptor
0x1408adc36  mov     edi, eax
0x1408adc38  test    eax, eax
0x1408adc3a  js      loc_1408AE34A
0x1408adc40  mov     r15, [rbp+0F0h+P]
0x1408adc44  lea     rdx, [rsp+1F0h+Destination.Buffer]; puszLogFileName
0x1408adc49  mov     [rsp+1F0h+cbContext], 0; cbContext
0x1408adc51  lea     rcx, [rbp+0F0h+pplfoLog]; pplfoLog
0x1408adc55  mov     [rsp+1F0h+pvContext], 0; pvContext
0x1408adc5e  mov     r9d, 7; dwShareMode
0x1408adc64  mov     [rsp+1F0h+fLogOptionFlag], r13d; fLogOptionFlag
0x1408adc69  mov     r8d, 0C0000000h; fDesiredAccess
0x1408adc6f  mov     [rsp+1F0h+fFlagsAndAttributes], 0; fFlagsAndAttributes
0x1408adc77  mov     dword ptr [rsp+1F0h+fCreateOptions], 8; fCreateOptions
0x1408adc7f  mov     [rsp+1F0h+fCreateDisposition], 3; fCreateDisposition
0x1408adc87  mov     [rsp+1F0h+psdLogFile], r15; psdLogFile
0x1408adc8c  call    cs:__imp_ClfsCreateLogFile
0x1408adc93  nop     dword ptr [rax+rax+00h]
0x1408adc98  mov     edi, eax
0x1408adc9a  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x1408adca0  test    al, 10h
0x1408adca2  jnz     loc_1408AE20B
0x1408adca8  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x1408adcad  test    eax, eax
0x1408adcaf  jnz     loc_1408AE213
0x1408adcb5  mov     rcx, [rbp+0F0h+Source.Buffer]; P
0x1408adcb9  test    rcx, rcx
0x1408adcbc  jz      short loc_1408ADCD4
0x1408adcbe  call    ExFreePool
0x1408adcc3  xorps   xmm0, xmm0
0x1408adcc6  movups  xmmword ptr [rbp+0F0h+Source.Length], xmm0
0x1408adcca  psrldq  xmm0, 8
0x1408adccf  movq    [rbp+0F0h+Source.Buffer], xmm0
0x1408adcd4  mov     r12, [rbp+0F0h+var_130]
0x1408adcd8  test    r12, r12
0x1408adcdb  jnz     loc_1408AE229
0x1408adce1  xor     edx, edx; Tag
0x1408adce3  mov     rcx, r15; P
0x1408adce6  call    ExFreePoolWithTag
0x1408adceb  test    edi, edi
0x1408adced  js      loc_1408AE040
0x1408adcf3  mov     rcx, [rbp+0F0h+pplfoLog]; LogFile
0x1408adcf7  lea     r8, [rbp+0F0h+ClientCookie]; ClientCookie
0x1408adcfb  xorps   xmm0, xmm0
0x1408adcfe  lea     rdx, [rbp+0F0h+RegistrationData]; RegistrationData
0x1408add02  xor     eax, eax
0x1408add04  movups  xmmword ptr [rbp+0F0h+RegistrationData.Version], xmm0
0x1408add08  mov     [rbp+0F0h+RegistrationData.Version], r14d
0x1408add0c  movups  xmmword ptr [rbp+0F0h+RegistrationData.AdvanceTailCallbackData], xmm0
0x1408add10  mov     [rbp+0F0h+RegistrationData.LogUnpinnedCallbackData], rax
0x1408add14  movups  xmmword ptr [rbp+0F0h+RegistrationData.LogGrowthCompleteCallbackData], xmm0
0x1408add18  call    cs:__imp_ClfsMgmtRegisterManagedClient
0x1408add1f  nop     dword ptr [rax+rax+00h]
0x1408add24  mov     edi, eax
0x1408add26  test    eax, eax
0x1408add28  js      loc_1408AE33B
0x1408add2e  movzx   edx, cs:TmContainerExt
0x1408add35  mov     ecx, 100h
0x1408add3a  add     rdx, 18h
0x1408add3e  mov     r8d, 6D524D43h
0x1408add44  call    ExAllocatePool2
0x1408add49  mov     r15, rax
0x1408add4c  test    rax, rax
0x1408add4f  jz      loc_1408AE32C
0x1408add55  mov     [rax], r14d
0x1408add58  movzx   ecx, cs:TmContainerExt
0x1408add5f  add     ecx, 18h
0x1408add62  mov     dword ptr [rax+0Ch], 9
0x1408add69  mov     [rax+4], ecx
0x1408add6c  movzx   ecx, cs:TmContainerExt
0x1408add73  mov     [rax+10h], cx
0x1408add77  lea     rcx, [rax+12h]; void *
0x1408add7b  movzx   r8d, cs:TmContainerExt; Size
0x1408add83  mov     rdx, cs:off_140E0D748; Src
0x1408add8a  call    memmove
0x1408add8f  movzx   r8d, cs:TmContainerExt
0x1408add97  mov     rdx, r15; Policy
0x1408add9a  mov     rcx, [rbp+0F0h+pplfoLog]; LogFile
0x1408add9e  add     r8d, 18h; PolicyLength
0x1408adda2  call    cs:__imp_ClfsMgmtInstallPolicy
0x1408adda9  nop     dword ptr [rax+rax+00h]
0x1408addae  xor     edx, edx; Tag
0x1408addb0  mov     rcx, r15; P
0x1408addb3  mov     edi, eax
0x1408addb5  call    ExFreePoolWithTag
0x1408addba  test    edi, edi
0x1408addbc  js      loc_1408AE31D
0x1408addc2  movzx   ecx, cs:CmpClfsLogPrefix.Length
0x1408addc9  lea     r12, [rsi+20h]
0x1408addcd  movzx   eax, word ptr [rsp+1F0h+Destination.Buffer]
0x1408addd2  lea     r9, [rbp+0F0h+LogFileName]; LogFileName
0x1408addd6  sub     ax, cx
0x1408addd9  mov     [rsp+1F0h+fCreateDisposition], 0; CommitStrength
0x1408adde1  mov     [rbp+0F0h+LogFileName.Length], ax
0x1408adde5  lea     r8, [rbp+0F0h+ObjectAttributes]; ObjectAttributes
0x1408adde9  movzx   eax, word ptr [rsp+1F0h+Destination.Buffer+2]
0x1408addee  xorps   xmm0, xmm0
0x1408addf1  sub     ax, cx
0x1408addf4  mov     [rbp+0F0h+ObjectAttributes.Length], 30h ; '0'
0x1408addfb  mov     [rbp+0F0h+LogFileName.MaximumLength], ax
0x1408addff  mov     r15d, 0F003Fh
0x1408ade05  mov     eax, ecx
0x1408ade07  mov     [rbp+0F0h+ObjectAttributes.RootDirectory], 0
0x1408ade0f  add     rax, [rsp+1F0h+var_180]
0x1408ade14  mov     edx, r15d; DesiredAccess
0x1408ade17  mov     [rbp+0F0h+LogFileName.Buffer], rax
0x1408ade1b  mov     rcx, r12; TmHandle
0x1408ade1e  mov     eax, [rbp+0F0h+CreateOptions]
0x1408ade21  mov     dword ptr [rsp+1F0h+psdLogFile], eax; CreateOptions
0x1408ade25  mov     [rbp+0F0h+ObjectAttributes.Attributes], 240h
0x1408ade2c  mov     [rbp+0F0h+ObjectAttributes.ObjectName], 0
0x1408ade34  movdqu  xmmword ptr [rbp+0F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1408ade39  call    ZwCreateTransactionManager
0x1408ade3e  mov     edi, eax
0x1408ade40  cmp     eax, 0C0000035h
  ... truncated ...
```
