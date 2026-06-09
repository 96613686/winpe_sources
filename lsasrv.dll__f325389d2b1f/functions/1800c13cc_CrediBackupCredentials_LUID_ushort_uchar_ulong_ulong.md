# CrediBackupCredentials(_LUID *,ushort *,uchar *,ulong,ulong)

- ea: `0x1800c13cc`
- end: `0x1800c1cf4`
- name: `?CrediBackupCredentials@@YAJPEAU_LUID@@PEAGPEAEKK@Z`
- size: `2344`
- prototype: `__int64 __fastcall(struct _LUID *, unsigned __int16 *, unsigned __int8 *, DWORD, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f4070`

## callees

- `0x18000124c`
- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x1800284d4`
- `0x18003a804`
- `0x18003ff10`
- `0x180040814`
- `0x18004091c`
- `0x180040af0`
- `0x180041e80`
- `0x180070ff0`
- `0x18007e71c`
- `0x18008e360`
- `0x180097c3c`
- `0x1800ada18`
- `0x1800b1db8`
- `0x1800bc2c4`
- `0x1800bd6e0`
- `0x1800c13cc`
- `0x1800c49e8`
- `0x1800d28b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c19f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c19f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1b44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c192b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c192b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c147f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1543`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c147f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1543`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c1ada`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c1ada`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800c1b61`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800c1b9f`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800c1b61`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800c1b9f`
- `ntdll!NtSetInformationThread` at `0x1800c197c`
- `ntdll!NtSetInformationThread` at `0x1800c1c8e`
- `ntdll!NtSetInformationThread` at `0x1800c197c`
- `ntdll!NtSetInformationThread` at `0x1800c1c8e`
- `ntdll!NtOpenThreadToken` at `0x1800c1946`
- `ntdll!NtOpenThreadToken` at `0x1800c1946`
- `ntdll!RtlInitUnicodeString` at `0x1800c199d`
- `ntdll!RtlInitUnicodeString` at `0x1800c199d`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditCredentialsBackupRestore` at `0x1800c1c6b`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditCredentialsBackupRestore` at `0x1800c1c6b`

## pseudocode

```c
__int64 __fastcall CrediBackupCredentials(
        struct _LUID *a1,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        DWORD a4,
        unsigned int a5)
{
  struct _RTL_BALANCED_NODE *v5; // r15
  struct _RTL_BALANCED_NODE *v6; // rsi
  struct _RTL_BALANCED_NODE *v7; // r14
  unsigned int v8; // r13d
  struct _LUID *v10; // r12
  LsaHandleCache **v11; // rdx
  NTSTATUS Use; // ebx
  unsigned int v13; // edi
  __int64 v14; // rcx
  struct _RTL_BALANCED_NODE *v15; // rax
  struct _RTL_BALANCED_NODE *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  struct _RTL_BALANCED_NODE *v19; // rax
  __int64 v20; // rcx
  struct _RTL_BALANCED_NODE *v21; // rax
  __int64 v22; // rax
  unsigned int i; // esi
  __int64 v24; // r14
  _QWORD **v25; // r14
  _QWORD *v26; // rdi
  int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // r14
  struct _RTL_BALANCED_NODE *v31; // rax
  __int64 v32; // rcx
  unsigned __int8 *v33; // r13
  unsigned __int8 *v34; // r12
  unsigned int j; // esi
  __int64 v36; // rax
  _QWORD *v37; // r15
  _QWORD *v38; // rdi
  int v39; // eax
  int v40; // eax
  void *v41; // rdx
  int v42; // ebx
  struct _RTL_BALANCED_NODE *v43; // rax
  __int64 v44; // rdi
  struct _RTL_BALANCED_NODE *v45; // rax
  __int64 v46; // rbx
  void *v47; // rdx
  struct _RTL_BALANCED_NODE *v48; // rax
  HANDLE CurrentThread; // rax
  void *v50; // rdx
  DWORD v51; // eax
  unsigned int v52; // edi
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  struct _RTL_BALANCED_NODE *v56; // rax
  HANDLE FileW; // rax
  void *v58; // rbx
  char LastError; // al
  DWORD v60; // eax
  char FileType; // al
  int v62; // eax
  __int64 v63; // r8
  unsigned int v65; // [rsp+68h] [rbp-A0h]
  char v66; // [rsp+6Ch] [rbp-9Ch]
  size_t Size; // [rsp+70h] [rbp-98h] BYREF
  struct _RTL_BALANCED_NODE *v68; // [rsp+78h] [rbp-90h]
  unsigned int v69; // [rsp+80h] [rbp-88h] BYREF
  struct _RTL_BALANCED_NODE *v70; // [rsp+88h] [rbp-80h]
  unsigned int v71; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v72; // [rsp+94h] [rbp-74h] BYREF
  unsigned int v73; // [rsp+98h] [rbp-70h]
  void *Src; // [rsp+A0h] [rbp-68h] BYREF
  struct _RTL_BALANCED_NODE *v75; // [rsp+A8h] [rbp-60h]
  HANDLE hObject; // [rsp+B0h] [rbp-58h] BYREF
  struct _RTL_BALANCED_NODE *v77; // [rsp+B8h] [rbp-50h] BYREF
  HANDLE hFile; // [rsp+C0h] [rbp-48h]
  _OWORD v79[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 ThreadInformation; // [rsp+E8h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-18h] BYREF

  memset(v79, 0, sizeof(v79));
  v66 = 0;
  v5 = 0;
  v6 = 0;
  v70 = 0;
  Src = 0;
  v7 = 0;
  v77 = 0;
  v8 = 0;
  v68 = 0;
  v65 = 0;
  v10 = a1;
  v71 = 0;
  v72 = 0;
  v69 = 0;
  LODWORD(Size) = 0;
  v73 = 0;
  hFile = 0;
  ThreadInformation = 0;
  hObject = 0;
  DestinationString = 0;
  Use = CredpLoadOnFirstUse(a1);
  if ( Use < 0 )
    goto LABEL_5;
  if ( a5 && (a5 & 0xFFFFFFFE) != 0 )
  {
    Use = -1073741581;
LABEL_5:
    v13 = 0;
    goto LABEL_6;
  }
  if ( !a2 )
  {
    Use = -1073741583;
    goto LABEL_5;
  }
  Use = CredpReferenceCredSets(v10, 0, (struct _CREDENTIAL_SETS *)v79);
  if ( Use < 0 )
    goto LABEL_5;
  CredpLockAndRefreshCredSets((struct _CREDENTIAL_SETS *)v79, v10, 0, 0);
  v66 = 1;
  if ( !*(_BYTE *)(*((_QWORD *)&v79[0] + 1) + 308LL) )
  {
    Use = -1073741729;
    v11 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 408, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids);
    }
    goto LABEL_5;
  }
  v22 = *(_QWORD *)&v79[0];
  for ( i = 1; i <= 3; ++i )
  {
    if ( i != 1 )
    {
      v24 = i == 2 ? *(_QWORD *)(v22 + 32) : *(_QWORD *)(v22 + 24);
      v25 = (_QWORD **)(v24 + 8);
      v26 = *v25;
      if ( *v25 != v25 )
      {
        while ( 1 )
        {
          v27 = CredpMarshalCredential((struct _CANONICAL_CREDENTIAL *)(v26 - 11), 0, &v71, 0);
          Use = v27;
          if ( v27 < 0 )
            break;
          v26 = (_QWORD *)*v26;
          v28 = (v71 + 1) & 0xFFFFFFFE;
          v29 = v28 + v65;
          v65 += v28;
          if ( v26 == v25 )
          {
            v22 = *(_QWORD *)&v79[0];
            goto LABEL_50;
          }
        }
        v11 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            409,
            WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
            (unsigned int)v27);
        }
        goto LABEL_58;
      }
    }
    v29 = v65;
LABEL_50:
    ;
  }
  if ( !(_DWORD)v29 )
  {
    Use = -1073741275;
    v11 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 410, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids);
    }
LABEL_58:
    v7 = 0;
LABEL_59:
    v6 = v70;
    goto LABEL_60;
  }
  v30 = (unsigned int)v29;
  v31 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v29);
  v75 = v31;
  v5 = v31;
  if ( !v31 )
  {
    Use = -1073741801;
    goto LABEL_58;
  }
  v32 = *(_QWORD *)&v79[0];
  v33 = (unsigned __int8 *)v31 + v30;
  v34 = (unsigned __int8 *)v31;
  for ( j = 1; j <= 3; ++j )
  {
    if ( j != 1 )
    {
      v36 = j == 2 ? *(_QWORD *)(v32 + 32) : *(_QWORD *)(v32 + 24);
      v37 = (_QWORD *)(v36 + 8);
      v38 = *(_QWORD **)(v36 + 8);
      if ( v38 != (_QWORD *)(v36 + 8) )
      {
        while ( 1 )
        {
          v39 = CredpMarshalCredential((struct _CANONICAL_CREDENTIAL *)(v38 - 11), v34, &v71, v33);
          Use = v39;
          if ( v39 < 0 )
            break;
          v38 = (_QWORD *)*v38;
          v34 += (v71 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL;
          if ( v38 == v37 )
          {
            v32 = *(_QWORD *)&v79[0];
            goto LABEL_72;
          }
        }
        v11 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            411,
            WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
            (unsigned int)v39);
        }
        v7 = v68;
        v5 = v75;
        v8 = (unsigned int)v68;
        v10 = a1;
        goto LABEL_59;
      }
    }
LABEL_72:
    ;
  }
  v10 = a1;
  CredpUnlockAndFlushCredSets(a1, (struct _CREDENTIAL_SETS *)v79);
  v66 = 0;
  if ( a3 )
  {
    v5 = v75;
    v13 = v65;
    v40 = CredpEncryptDataBySecret((unsigned __int8 *)v75, v65, a3, a4, (unsigned __int8 **)&Src, (unsigned int *)&Size);
    Use = v40;
    if ( v40 < 0 )
    {
      v11 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          412,
          WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
          (unsigned int)v40);
      }
      v6 = (struct _RTL_BALANCED_NODE *)Src;
      v8 = Size;
      v7 = v68;
      goto LABEL_6;
    }
    v42 = 1;
    v43 = v5;
    do
    {
      LOBYTE(v43->Children[0]) = 0;
      v43 = (struct _RTL_BALANCED_NODE *)((char *)v43 + 1);
      --v30;
    }
    while ( v30 );
    LsapSubProv_FreeRoutine(v5, v41);
    v6 = (struct _RTL_BALANCED_NODE *)Src;
    v8 = Size;
  }
  else
  {
    v6 = v75;
    v42 = 2;
    v8 = v65;
  }
  v5 = 0;
  v73 = v8 + 12;
  v44 = v8 + 12;
  v45 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v44);
  v7 = v45;
  if ( !v45 )
  {
    Use = -1073741801;
    goto LABEL_60;
  }
  LODWORD(v45->Right) = v42;
  v46 = v8;
  LODWORD(v45->Children[0]) = 1;
  HIDWORD(v45->Left) = v8;
  memcpy_0((char *)&v45->Right + 4, v6, v8);
  if ( v6 )
  {
    v48 = v6;
    if ( v8 )
    {
      do
      {
        LOBYTE(v48->Children[0]) = 0;
        v48 = (struct _RTL_BALANCED_NODE *)((char *)v48 + 1);
        --v46;
      }
      while ( v46 );
    }
    LsapSubProv_FreeRoutine(v6, v47);
    v6 = 0;
  }
  CurrentThread = GetCurrentThread();
  Use = NtOpenThreadToken(CurrentThread, 0xCu, 1u, &hObject);
  if ( Use >= 0 )
  {
    if ( !hObject )
      goto LABEL_12;
    Use = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( Use >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"Credman Backup Credentials");
      if ( (unsigned __int8)LsaICryptProtectDataEx(
                              (_DWORD)v7,
                              v73,
                              (unsigned int)&DestinationString,
                              0,
                              0,
                              0,
                              0,
                              1,
                              0,
                              0,
                              (__int64)&v77,
                              (__int64)&v72) )
      {
        v56 = v7;
        if ( v8 != -12 )
        {
          do
          {
            LOBYTE(v56->Children[0]) = 0;
            v56 = (struct _RTL_BALANCED_NODE *)((char *)v56 + 1);
            --v44;
          }
          while ( v44 );
        }
        LsapSubProv_FreeRoutine(v7, v50);
        v7 = 0;
        FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x80u, 0);
        hFile = FileW;
        v58 = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          hFile = 0;
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            LastError = GetLastError();
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              414,
              (unsigned int)WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
              (_DWORD)a2,
              LastError);
          }
          v60 = GetLastError();
          Use = CredpWinStatusToNtStatus(v60);
        }
        else if ( GetFileType(FileW) == 1 )
        {
          v62 = CredpWriteFile(v58, 0, (unsigned __int8 *)v77, v72);
          Use = v62;
          if ( v62 >= 0 )
          {
            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 417, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, a2);
            }
            if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent() )
            {
              LOBYTE(v63) = 1;
              LsapAdtAuditCredentialsBackupRestore(a1, a2, v63);
            }
            Use = 0;
          }
          else if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              416,
              (unsigned int)WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
              (_DWORD)a2,
              v62);
          }
        }
        else
        {
          Use = -1073741811;
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          {
            FileType = GetFileType(hFile);
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              415,
              (unsigned int)WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
              (_DWORD)a2,
              FileType);
          }
        }
      }
      else
      {
        v51 = GetLastError();
        v52 = v51;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 413, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, v51);
        }
        Use = CredpWinStatusToNtStatus(v52);
        if ( (unsigned int)dword_18019A2B0 > 2 )
        {
          Src = a2;
          LODWORD(Size) = (unsigned __int8)byte_1801A0BC9;
          v69 = v52;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            v53,
            (unsigned int)&byte_18017ED17,
            v54,
            v55,
            (__int64)&Size,
            (__int64)&v69,
            (__int64)&Src);
        }
      }
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &hObject, 8u);
    }
  }
LABEL_60:
  v13 = v65;
LABEL_6:
  if ( hObject )
    CloseHandle(hObject);
  if ( v5 )
  {
    v14 = v13;
    v15 = v5;
    if ( v13 )
    {
      do
      {
        LOBYTE(v15->Children[0]) = 0;
        v15 = (struct _RTL_BALANCED_NODE *)((char *)v15 + 1);
        --v14;
      }
      while ( v14 );
    }
    LsapSubProv_FreeRoutine(v5, v11);
  }
LABEL_12:
  v16 = v77;
  if ( v77 )
  {
    v17 = v72;
    if ( v72 )
    {
      do
      {
        LOBYTE(v16->Children[0]) = 0;
        v16 = (struct _RTL_BALANCED_NODE *)((char *)v16 + 1);
        --v17;
      }
      while ( v17 );
      v16 = v77;
    }
    LsapSubProv_FreeRoutine(v16, v11);
  }
  if ( v7 )
  {
    v18 = v73;
    v19 = v7;
    if ( v73 )
    {
      do
      {
        LOBYTE(v19->Children[0]) = 0;
        v19 = (struct _RTL_BALANCED_NODE *)((char *)v19 + 1);
        --v18;
      }
      while ( v18 );
    }
    LsapSubProv_FreeRoutine(v7, v11);
  }
  if ( v6 )
  {
    v20 = v8;
    v21 = v6;
    if ( v8 )
    {
      do
      {
        LOBYTE(v21->Children[0]) = 0;
        v21 = (struct _RTL_BALANCED_NODE *)((char *)v21 + 1);
        --v20;
      }
      while ( v20 );
    }
    LsapSubProv_FreeRoutine(v6, v11);
  }
  if ( v66 )
    CredpUnlockAndFlushCredSets(v10, (struct _CREDENTIAL_SETS *)v79);
  CredpDereferenceCredSets((struct _CREDENTIAL_SETS *)v79);
  if ( hFile )
    CloseHandle(hFile);
  if ( Use >= 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        419,
        WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
        v10->LowPart,
        v10->HighPart);
    }
  }
  else if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_DDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      418,
      WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids,
      v10->LowPart,
      v10->HighPart,
      Use);
  }
  return (unsigned int)Use;
}

```

## disassembly

```asm
0x1800c13cc  mov     rax, rsp
0x1800c13cf  mov     [rax+20h], r9d
0x1800c13d3  mov     [rax+18h], r8
0x1800c13d7  mov     [rax+10h], rdx
0x1800c13db  mov     [rax+8], rcx
0x1800c13df  push    rbp
0x1800c13e0  push    rbx
0x1800c13e1  push    rsi
0x1800c13e2  push    rdi
0x1800c13e3  push    r12
0x1800c13e5  push    r13
0x1800c13e7  push    r14
0x1800c13e9  push    r15
0x1800c13eb  lea     rbp, [rax-48h]
0x1800c13ef  sub     rsp, 108h
0x1800c13f6  xor     eax, eax
0x1800c13f8  xorps   xmm0, xmm0
0x1800c13fb  movups  [rbp+40h+var_80], xmm0
0x1800c13ff  mov     byte ptr [rsp+140h+var_E0+4], al
0x1800c1403  mov     r15d, eax
0x1800c1406  movups  [rbp+40h+var_70], xmm0
0x1800c140a  mov     esi, eax
0x1800c140c  mov     [rbp+40h+var_C0], rax
0x1800c1410  mov     [rbp+40h+Src], rax
0x1800c1414  mov     r14d, eax
0x1800c1417  mov     [rbp+40h+var_90], rax
0x1800c141b  mov     r13d, eax
0x1800c141e  mov     [rsp+140h+var_D0], rax
0x1800c1423  mov     rdi, rdx
0x1800c1426  mov     dword ptr [rsp+140h+var_E0], eax
0x1800c142a  mov     r12, rcx
0x1800c142d  mov     [rbp+40h+var_B8], eax
0x1800c1430  mov     [rbp+40h+var_B4], eax
0x1800c1433  mov     [rsp+140h+var_C8], eax
0x1800c1437  mov     dword ptr [rsp+140h+Size], eax
0x1800c143b  mov     [rbp+40h+var_B0], eax
0x1800c143e  mov     [rbp+40h+hFile], rax
0x1800c1442  mov     [rbp+40h+ThreadInformation], rax
0x1800c1446  mov     [rbp+40h+hObject], rax
0x1800c144a  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x1800c144e  call    ?CredpLoadOnFirstUse@@YAJPEAU_LUID@@@Z; CredpLoadOnFirstUse(_LUID *)
0x1800c1453  mov     ebx, eax
0x1800c1455  test    eax, eax
0x1800c1457  js      short loc_1800C1474
0x1800c1459  mov     eax, [rbp+40h+arg_20]
0x1800c145c  test    eax, eax
0x1800c145e  jz      loc_1800C15A6
0x1800c1464  test    eax, 0FFFFFFFEh
0x1800c1469  jz      loc_1800C15A6
0x1800c146f  mov     ebx, 0C00000F3h
0x1800c1474  mov     edi, esi
0x1800c1476  mov     rcx, [rbp+40h+hObject]; hObject
0x1800c147a  test    rcx, rcx
0x1800c147d  jz      short loc_1800C148B
0x1800c147f  call    cs:__imp_CloseHandle
0x1800c1486  nop     dword ptr [rax+rax+00h]
0x1800c148b  test    r15, r15
0x1800c148e  jz      short loc_1800C14AD
0x1800c1490  mov     ecx, edi
0x1800c1492  mov     rax, r15
0x1800c1495  test    edi, edi
0x1800c1497  jz      short loc_1800C14A5
0x1800c1499  mov     byte ptr [rax], 0
0x1800c149c  inc     rax
0x1800c149f  sub     rcx, 1
0x1800c14a3  jnz     short loc_1800C1499
0x1800c14a5  mov     rcx, r15; struct _RTL_BALANCED_NODE *
0x1800c14a8  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800c14ad  mov     rcx, [rbp+40h+var_90]
0x1800c14b1  test    rcx, rcx
0x1800c14b4  jz      short loc_1800C14D3
0x1800c14b6  mov     eax, [rbp+40h+var_B4]
0x1800c14b9  test    rax, rax
0x1800c14bc  jz      short loc_1800C14CE
0x1800c14be  mov     byte ptr [rcx], 0
0x1800c14c1  inc     rcx
0x1800c14c4  sub     rax, 1
0x1800c14c8  jnz     short loc_1800C14BE
0x1800c14ca  mov     rcx, [rbp+40h+var_90]; struct _RTL_BALANCED_NODE *
0x1800c14ce  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800c14d3  test    r14, r14
0x1800c14d6  jz      short loc_1800C14F7
0x1800c14d8  mov     ecx, [rbp+40h+var_B0]
0x1800c14db  mov     rax, r14
0x1800c14de  test    rcx, rcx
0x1800c14e1  jz      short loc_1800C14EF
0x1800c14e3  mov     byte ptr [rax], 0
0x1800c14e6  inc     rax
0x1800c14e9  sub     rcx, 1
0x1800c14ed  jnz     short loc_1800C14E3
0x1800c14ef  mov     rcx, r14; struct _RTL_BALANCED_NODE *
0x1800c14f2  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800c14f7  test    rsi, rsi
0x1800c14fa  jz      short loc_1800C151B
0x1800c14fc  mov     ecx, r13d
0x1800c14ff  mov     rax, rsi
0x1800c1502  test    r13d, r13d
0x1800c1505  jz      short loc_1800C1513
0x1800c1507  mov     byte ptr [rax], 0
0x1800c150a  inc     rax
0x1800c150d  sub     rcx, 1
0x1800c1511  jnz     short loc_1800C1507
0x1800c1513  mov     rcx, rsi; struct _RTL_BALANCED_NODE *
0x1800c1516  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800c151b  cmp     byte ptr [rsp+140h+var_E0+4], 0
0x1800c1520  jz      short loc_1800C152E
0x1800c1522  lea     rdx, [rbp+40h+var_80]; struct _CREDENTIAL_SETS *
0x1800c1526  mov     rcx, r12; struct _LUID *
0x1800c1529  call    ?CredpUnlockAndFlushCredSets@@YAXPEAU_LUID@@PEAU_CREDENTIAL_SETS@@@Z; CredpUnlockAndFlushCredSets(_LUID *,_CREDENTIAL_SETS *)
0x1800c152e  lea     rcx, [rbp+40h+var_80]; struct _CREDENTIAL_SETS *
0x1800c1532  call    ?CredpDereferenceCredSets@@YAXPEAU_CREDENTIAL_SETS@@@Z; CredpDereferenceCredSets(_CREDENTIAL_SETS *)
0x1800c1537  mov     rax, [rbp+40h+hFile]
0x1800c153b  test    rax, rax
0x1800c153e  jz      short loc_1800C154F
0x1800c1540  mov     rcx, rax; hObject
0x1800c1543  call    cs:__imp_CloseHandle
0x1800c154a  nop     dword ptr [rax+rax+00h]
0x1800c154f  test    ebx, ebx
0x1800c1551  jns     loc_1800C1C9F
0x1800c1557  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c155e  lea     rax, WPP_GLOBAL_Control
0x1800c1565  cmp     rcx, rax
0x1800c1568  jz      loc_1800C1CDD
0x1800c156e  test    dword ptr [rcx+1Ch], 200h
0x1800c1575  jz      loc_1800C1CDD
0x1800c157b  mov     eax, [r12+4]
0x1800c1580  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c1587  mov     r9d, [r12]
0x1800c158b  mov     edx, 1A2h
0x1800c1590  mov     rcx, [rcx+10h]
0x1800c1594  mov     [rsp+140h+dwFlagsAndAttributes], ebx
0x1800c1598  mov     [rsp+140h+dwCreationDisposition], eax
0x1800c159c  call    WPP_SF_DDD
0x1800c15a1  jmp     loc_1800C1CDD
0x1800c15a6  test    rdi, rdi
0x1800c15a9  jnz     short loc_1800C15B5
0x1800c15ab  mov     ebx, 0C00000F1h
0x1800c15b0  jmp     loc_1800C1474
0x1800c15b5  lea     r8, [rbp+40h+var_80]; struct _CREDENTIAL_SETS *
0x1800c15b9  xor     edx, edx; unsigned __int8
0x1800c15bb  mov     rcx, r12; struct _LUID *
0x1800c15be  call    ?CredpReferenceCredSets@@YAJPEAU_LUID@@EPEAU_CREDENTIAL_SETS@@@Z; CredpReferenceCredSets(_LUID *,uchar,_CREDENTIAL_SETS *)
0x1800c15c3  mov     ebx, eax
0x1800c15c5  test    eax, eax
0x1800c15c7  js      loc_1800C1474
0x1800c15cd  xor     r9d, r9d; unsigned int
0x1800c15d0  lea     rcx, [rbp+40h+var_80]; struct _CREDENTIAL_SETS *
0x1800c15d4  xor     r8d, r8d; unsigned __int16 **
0x1800c15d7  mov     rdx, r12; struct _LUID *
0x1800c15da  call    ?CredpLockAndRefreshCredSets@@YAXPEAU_CREDENTIAL_SETS@@PEAU_LUID@@PEAPEBGK@Z; CredpLockAndRefreshCredSets(_CREDENTIAL_SETS *,_LUID *,ushort const * *,ulong)
0x1800c15df  mov     rax, qword ptr [rbp+40h+var_80+8]
0x1800c15e3  mov     byte ptr [rsp+140h+var_E0+4], 1
0x1800c15e8  cmp     [rax+134h], sil
0x1800c15ef  jnz     short loc_1800C1634
0x1800c15f1  mov     ebx, 0C000005Fh
0x1800c15f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c15fd  lea     rdx, WPP_GLOBAL_Control
0x1800c1604  cmp     rcx, rdx
0x1800c1607  jz      loc_1800C1474
0x1800c160d  test    dword ptr [rcx+1Ch], 200h
0x1800c1614  jz      loc_1800C1474
0x1800c161a  mov     rcx, [rcx+10h]
0x1800c161e  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c1625  mov     edx, 198h
0x1800c162a  call    WPP_SF_
0x1800c162f  jmp     loc_1800C1474
0x1800c1634  mov     rax, qword ptr [rbp+40h+var_80]
0x1800c1638  mov     esi, 1
0x1800c163d  cmp     esi, 1
0x1800c1640  jz      short loc_1800C1695
0x1800c1642  cmp     esi, 2
0x1800c1645  jnz     short loc_1800C164D
0x1800c1647  mov     r14, [rax+20h]
0x1800c164b  jmp     short loc_1800C1651
0x1800c164d  mov     r14, [rax+18h]
0x1800c1651  add     r14, 8
0x1800c1655  mov     rdi, [r14]
0x1800c1658  cmp     rdi, r14
0x1800c165b  jz      short loc_1800C1695
0x1800c165d  lea     rcx, [rdi-58h]; struct _CANONICAL_CREDENTIAL *
0x1800c1661  xor     r9d, r9d; unsigned __int8 *
0x1800c1664  lea     r8, [rbp+40h+var_B8]; unsigned int *
0x1800c1668  xor     edx, edx; unsigned __int8 *
0x1800c166a  call    ?CredpMarshalCredential@@YAJPEAU_CANONICAL_CREDENTIAL@@PEAEPEAK1@Z; CredpMarshalCredential(_CANONICAL_CREDENTIAL *,uchar *,ulong *,uchar *)
0x1800c166f  mov     ebx, eax
0x1800c1671  test    eax, eax
0x1800c1673  js      short loc_1800C16DC
0x1800c1675  mov     ecx, dword ptr [rsp+140h+var_E0]
0x1800c1679  mov     eax, [rbp+40h+var_B8]
0x1800c167c  mov     rdi, [rdi]
0x1800c167f  inc     eax
0x1800c1681  and     eax, 0FFFFFFFEh
0x1800c1684  add     ecx, eax
0x1800c1686  mov     dword ptr [rsp+140h+var_E0], ecx
0x1800c168a  cmp     rdi, r14
0x1800c168d  jnz     short loc_1800C165D
0x1800c168f  mov     rax, qword ptr [rbp+40h+var_80]
0x1800c1693  jmp     short loc_1800C1699
0x1800c1695  mov     ecx, dword ptr [rsp+140h+var_E0]
0x1800c1699  inc     esi
0x1800c169b  cmp     esi, 3
0x1800c169e  jbe     short loc_1800C163D
0x1800c16a0  test    ecx, ecx
0x1800c16a2  jnz     short loc_1800C1720
0x1800c16a4  mov     ebx, 0C0000225h
0x1800c16a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c16b0  lea     rdx, WPP_GLOBAL_Control
0x1800c16b7  cmp     rcx, rdx
0x1800c16ba  jz      short loc_1800C1710
0x1800c16bc  test    dword ptr [rcx+1Ch], 200h
0x1800c16c3  jz      short loc_1800C1710
0x1800c16c5  mov     rcx, [rcx+10h]
0x1800c16c9  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c16d0  mov     edx, 19Ah
0x1800c16d5  call    WPP_SF_
0x1800c16da  jmp     short loc_1800C1710
0x1800c16dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c16e3  lea     rdx, WPP_GLOBAL_Control
0x1800c16ea  cmp     rcx, rdx
0x1800c16ed  jz      short loc_1800C1710
0x1800c16ef  test    dword ptr [rcx+1Ch], 200h
0x1800c16f6  jz      short loc_1800C1710
0x1800c16f8  mov     rcx, [rcx+10h]
0x1800c16fc  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c1703  mov     edx, 199h
0x1800c1708  mov     r9d, eax
0x1800c170b  call    WPP_SF_d
0x1800c1710  mov     r14, r13
0x1800c1713  mov     rsi, [rbp+40h+var_C0]
0x1800c1717  mov     edi, dword ptr [rsp+140h+var_E0]
0x1800c171b  jmp     loc_1800C1476
0x1800c1720  mov     r14d, ecx
0x1800c1723  call    LsapAllocate
0x1800c1728  mov     [rbp+40h+var_A0], rax
0x1800c172c  mov     r15, rax
0x1800c172f  test    rax, rax
0x1800c1732  jnz     short loc_1800C173B
0x1800c1734  mov     ebx, 0C0000017h
0x1800c1739  jmp     short loc_1800C1710
0x1800c173b  mov     rcx, qword ptr [rbp+40h+var_80]
0x1800c173f  lea     r13, [r14+rax]
0x1800c1743  mov     r12, rax
0x1800c1746  mov     esi, 1
0x1800c174b  cmp     esi, 1
0x1800c174e  jz      short loc_1800C17A1
0x1800c1750  cmp     esi, 2
0x1800c1753  jnz     short loc_1800C175B
0x1800c1755  mov     rax, [rcx+20h]
0x1800c1759  jmp     short loc_1800C175F
0x1800c175b  mov     rax, [rcx+18h]
0x1800c175f  lea     r15, [rax+8]
0x1800c1763  mov     rdi, [r15]
0x1800c1766  cmp     rdi, r15
0x1800c1769  jz      short loc_1800C17A1
0x1800c176b  lea     rcx, [rdi-58h]; struct _CANONICAL_CREDENTIAL *
0x1800c176f  mov     r9, r13; unsigned __int8 *
0x1800c1772  lea     r8, [rbp+40h+var_B8]; unsigned int *
0x1800c1776  mov     rdx, r12; unsigned __int8 *
0x1800c1779  call    ?CredpMarshalCredential@@YAJPEAU_CANONICAL_CREDENTIAL@@PEAEPEAK1@Z; CredpMarshalCredential(_CANONICAL_CREDENTIAL *,uchar *,ulong *,uchar *)
0x1800c177e  mov     ebx, eax
0x1800c1780  test    eax, eax
0x1800c1782  js      loc_1800C1847
0x1800c1788  mov     eax, [rbp+40h+var_B8]
0x1800c178b  mov     rdi, [rdi]
0x1800c178e  inc     rax
0x1800c1791  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800c1795  add     r12, rax
0x1800c1798  cmp     rdi, r15
0x1800c179b  jnz     short loc_1800C176B
0x1800c179d  mov     rcx, qword ptr [rbp+40h+var_80]
0x1800c17a1  inc     esi
0x1800c17a3  cmp     esi, 3
0x1800c17a6  jbe     short loc_1800C174B
0x1800c17a8  mov     r12, [rbp+40h+arg_0]
0x1800c17ac  lea     rdx, [rbp+40h+var_80]; struct _CREDENTIAL_SETS *
0x1800c17b0  mov     rcx, r12; struct _LUID *
0x1800c17b3  call    ?CredpUnlockAndFlushCredSets@@YAXPEAU_LUID@@PEAU_CREDENTIAL_SETS@@@Z; CredpUnlockAndFlushCredSets(_LUID *,_CREDENTIAL_SETS *)
0x1800c17b8  mov     rax, [rbp+40h+arg_10]
0x1800c17bc  mov     byte ptr [rsp+140h+var_E0+4], 0
0x1800c17c1  test    rax, rax
0x1800c17c4  jz      loc_1800C18B6
0x1800c17ca  mov     r15, [rbp+40h+var_A0]
0x1800c17ce  lea     rcx, [rsp+140h+Size]
0x1800c17d3  mov     edi, dword ptr [rsp+140h+var_E0]
0x1800c17d7  mov     r8, rax; BYTE *
0x1800c17da  mov     r9d, [rbp+40h+dwDataLen]; dwDataLen
0x1800c17de  mov     edx, edi; Size
0x1800c17e0  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rcx; unsigned int *
0x1800c17e5  lea     rcx, [rbp+40h+Src]
0x1800c17e9  mov     qword ptr [rsp+140h+dwCreationDisposition], rcx; unsigned __int8 **
0x1800c17ee  mov     rcx, r15; Src
0x1800c17f1  call    ?CredpEncryptDataBySecret@@YAJPEAEK0KPEAPEAEPEAK@Z; CredpEncryptDataBySecret(uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x1800c17f6  mov     ebx, eax
0x1800c17f8  test    eax, eax
0x1800c17fa  jns     loc_1800C1890
0x1800c1800  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1807  lea     rdx, WPP_GLOBAL_Control
0x1800c180e  cmp     rcx, rdx
0x1800c1811  jz      short loc_1800C1834
0x1800c1813  test    dword ptr [rcx+1Ch], 200h
  ... truncated ...
```
