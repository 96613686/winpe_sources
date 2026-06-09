# CMsiOpExecute::GetBackupFolder(IMsiPath *,IMsiPath * &)

- ea: `0x180068e88`
- end: `0x180069bf4`
- name: `?GetBackupFolder@CMsiOpExecute@@IEAA?AW4iesEnum@@PEAVIMsiPath@@AEAPEAV3@@Z`
- size: `3436`
- prototype: ``
- caller_count: `7`
- callee_count: `26`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18005f600`
- `0x18006a410`
- `0x18006b2b0`
- `0x1801e8934`
- `0x1801fb680`
- `0x1801fc530`
- `0x180201b50`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18000c4bc`
- `0x180013fe4`
- `0x180014528`
- `0x18002e870`
- `0x180036bb0`
- `0x180038e70`
- `0x1800586a0`
- `0x180067fec`
- `0x180068e88`
- `0x180069bfc`
- `0x18007adb4`
- `0x18007b9e8`
- `0x180082d38`
- `0x18008c93c`
- `0x180097c78`
- `0x18009ad3c`
- `0x1800ada5c`
- `0x1800fa370`
- `0x18012be04`
- `0x18013fa30`
- `0x180149a1c`
- `0x180153e68`
- `0x1801b8f94`
- `0x180266010`

## import_xrefs

- `ntdll!NtSetSecurityObject` at `0x180069835`
- `ntdll!NtSetSecurityObject` at `0x180069853`
- `ntdll!NtSetSecurityObject` at `0x180069835`
- `ntdll!NtSetSecurityObject` at `0x180069853`
- `KERNEL32!CloseHandle` at `0x180069710`
- `KERNEL32!CloseHandle` at `0x18006986e`
- `KERNEL32!CloseHandle` at `0x180069ad7`
- `KERNEL32!CloseHandle` at `0x180069710`
- `KERNEL32!CloseHandle` at `0x18006986e`
- `KERNEL32!CloseHandle` at `0x180069ad7`
- `KERNEL32!CreateFileW` at `0x180069627`
- `KERNEL32!CreateFileW` at `0x180069627`
- `KERNEL32!RemoveDirectoryW` at `0x180069732`
- `KERNEL32!RemoveDirectoryW` at `0x180069732`

## string_xrefs

- `0x180068fff`: `Config.Msi`
- `0x18006927e`: `Config.Msi`
- `0x1800699f7`: `Error: Unexpected Junction was found`
- `0x1800692d8`: `Install target is remote drive`
- `0x1800693f4`: `Backup folder is created by user`
- `0x18006953f`: `Backup folder is in cache folder`
- `0x1800695c5`: `Error: Failed to check cache backup folder status`
- `0x18006965a`: `Folder is not accessible: %s`
- `0x180069760`: `Delete folder failed: %s`
- `0x18006997c`: `Create folder failed: %s`

## pseudocode

```c
__int64 __fastcall CMsiOpExecute::GetBackupFolder(CMsiOpExecute *a1, _QWORD *a2, __int64 *a3)
{
  struct IMsiRecord *BackupFolderCache; // rax
  int v8; // esi
  const struct IMsiString *TempDirectory; // rax
  __int64 v10; // rdi
  const struct IMsiString *v11; // rbx
  __int64 (__fastcall *v12)(__int64, __int64, _QWORD **); // r14
  __int64 v13; // rax
  __int64 v14; // rdi
  _QWORD *v15; // r14
  void (__fastcall *v16)(_QWORD *, _QWORD); // rdi
  MsiString *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // r14
  unsigned int v25; // r15d
  int v26; // eax
  __int64 v27; // r15
  int v28; // r12d
  void (__fastcall *v29)(__int64, __int64, __int64); // r14
  __int64 v30; // rbx
  __int64 v31; // rdi
  __int64 v32; // rax
  struct IMsiPath *v33; // rdi
  void (__fastcall *v34)(struct IMsiPath *, _QWORD); // rbx
  MsiString *v35; // rax
  const unsigned __int16 *v36; // r9
  __int64 v37; // rax
  const unsigned __int16 *v38; // r9
  struct IMsiServices *v39; // rcx
  struct IMsiRecord *v40; // rax
  __int64 v41; // rax
  __int64 *v42; // rdi
  __int64 v43; // rax
  int v44; // r12d
  const struct IMsiString *v45; // rbx
  __int64 v46; // r9
  int v47; // edx
  struct IMsiRecord *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  int v51; // eax
  __int64 FileW; // r12
  int v53; // ecx
  const WCHAR *v54; // rax
  const unsigned __int16 *v55; // rax
  const unsigned __int16 *v56; // rax
  const unsigned __int16 *v57; // rax
  const WCHAR *v58; // rax
  const unsigned __int16 *v59; // rax
  struct IMsiRecord *v60; // rax
  int SecureSecurityDescriptor; // eax
  __int64 v62; // rdx
  NTSTATUS v63; // esi
  __int64 v64; // rdi
  const unsigned __int16 *v65; // rax
  struct IMsiRecord *v66; // rax
  PSECURITY_DESCRIPTOR v67; // rax
  struct IMsiStream **v68; // rax
  struct IMsiRecord *v69; // rax
  const unsigned __int16 *v70; // rax
  const unsigned __int16 *v71; // rax
  struct IMsiRecord *v72; // rax
  __int64 v73; // rbx
  __int64 v74; // [rsp+60h] [rbp-39h] BYREF
  _QWORD *v75; // [rsp+68h] [rbp-31h] BYREF
  int v76; // [rsp+70h] [rbp-29h] BYREF
  int Folder; // [rsp+74h] [rbp-25h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp-21h] BYREF
  struct IMsiPath *v79; // [rsp+80h] [rbp-19h] BYREF
  __int64 v80; // [rsp+88h] [rbp-11h] BYREF
  __int64 *v81; // [rsp+90h] [rbp-9h] BYREF
  int v82; // [rsp+98h] [rbp-1h] BYREF
  int v83; // [rsp+9Ch] [rbp+3h] BYREF
  int v84; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v85; // [rsp+A8h] [rbp+Fh] BYREF
  _BYTE v86[64]; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v88; // [rsp+118h] [rbp+7Fh] BYREF

  CElevate::CElevate((CElevate *)v86, 1);
  BackupFolderCache = CMsiOpExecute::CreateBackupFolderCache(a1);
  v74 = (__int64)BackupFolderCache;
  if ( BackupFolderCache )
  {
    CMsiOpExecute::Message(a1, 0x1000000, BackupFolderCache);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v74);
    CElevate::~CElevate((CElevate *)v86);
    return 3;
  }
  *a3 = 0;
  v8 = 2;
  v79 = 0;
  v75 = 0;
  v81 = 0;
  Folder = 0;
  if ( a2 )
  {
    v18 = *a2;
    v75 = a2;
    (*(void (__fastcall **)(_QWORD *))(v18 + 8))(a2);
  }
  else
  {
    TempDirectory = GetTempDirectory();
    v10 = *(_QWORD *)a1;
    v11 = TempDirectory;
    v12 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(**(_QWORD **)a1 + 120LL);
    v75 = 0;
    v13 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v11 + 80LL))(v11);
    v14 = v12(v10, v13, &v75);
    if ( v74 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    v74 = v14;
    if ( v14 )
    {
      CMsiOpExecute::Message(a1, 0x1000000, v14);
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v75 )
        (*(void (__fastcall **)(_QWORD *))(*v75 + 16LL))(v75);
      if ( v79 )
        (*(void (__fastcall **)(struct IMsiPath *))(*(_QWORD *)v79 + 16LL))(v79);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      goto LABEL_119;
    }
    if ( g_scServerContext == 2 )
    {
      v15 = v75;
      v16 = *(void (__fastcall **)(_QWORD *, _QWORD))(*v75 + 104LL);
      v17 = MsiString::MsiString((MsiString *)&v88, L"Config.Msi");
      v16(v15, *(_QWORD *)v17);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      Folder = 1;
    }
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD *))(*v75 + 72LL))(v75);
  v85 = v19;
  v80 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 168LL))(v19);
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v80 + 208LL))(v80, &v80);
  (*(void (__fastcall **)(__int64))(**((_QWORD **)a1 + 123) + 32LL))(*((_QWORD *)a1 + 123));
  (*(void (__fastcall **)(__int64, _QWORD, __int64))(**((_QWORD **)a1 + 123) + 96LL))(
    *((_QWORD *)a1 + 123),
    *((unsigned int *)a1 + 248),
    v80);
  if ( (*(unsigned int (__fastcall **)(__int64))(**((_QWORD **)a1 + 123) + 40LL))(*((_QWORD *)a1 + 123)) )
  {
    v20 = *((_QWORD *)a1 + 123);
    v21 = *((unsigned int *)a1 + 249);
    v83 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 80LL))(v20, v21);
    v88 = v22;
    v23 = v22;
    if ( v22 )
    {
      v24 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 160LL))(v22, &v83);
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      v74 = v24;
      if ( !v24 && v83 == 1 )
      {
        *a3 = v23;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v75 )
          (*(void (__fastcall **)(_QWORD *))(*v75 + 16LL))(v75);
        if ( v79 )
          (*(void (__fastcall **)(struct IMsiPath *))(*(_QWORD *)v79 + 16LL))(v79);
        if ( v74 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        v25 = 1;
        goto LABEL_120;
      }
    }
    (*(void (__fastcall **)(__int64))(**((_QWORD **)a1 + 123) + 184LL))(*((_QWORD *)a1 + 123));
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v88);
  }
  v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 56LL))(v19);
  v27 = *(_QWORD *)a1;
  v28 = v26;
  v29 = *(void (__fastcall **)(__int64, __int64, __int64))(**(_QWORD **)a1 + 120LL);
  v30 = CComPointer<IEnumMsiRecord>::operator=(&v79);
  v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 168LL))(v19);
  v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
  v29(v27, v32, v30);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  v33 = v79;
  v34 = *(void (__fastcall **)(struct IMsiPath *, _QWORD))(*(_QWORD *)v79 + 104LL);
  v35 = MsiString::MsiString((MsiString *)&v88, L"Config.Msi");
  v34(v33, *(_QWORD *)v35);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
  v82 = 0;
  if ( v28 == 4 )
  {
    if ( g_dmDiagnosticMode )
    {
      v36 = L"Install target is remote drive";
LABEL_55:
      DebugString(9, 0, 0, v36, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      goto LABEL_56;
    }
    goto LABEL_56;
  }
  v37 = (*(__int64 (__fastcall **)(struct IMsiPath *, int *))(*(_QWORD *)v79 + 160LL))(v79, &v82);
  if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v74, v37) )
  {
    if ( !v82 )
      goto LABEL_48;
    v39 = *(struct IMsiServices **)a1;
    LODWORD(v88) = 0;
    v40 = IsFolderValueExists(v39, v79, (enum Bool *)&v88);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v74, v40) && g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"Error: Backup folder is not registered",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    if ( (_DWORD)v88 )
    {
LABEL_48:
      LODWORD(v88) = 0;
      v41 = (*(__int64 (__fastcall **)(struct IMsiPath *, __int64 *))(*(_QWORD *)v79 + 216LL))(v79, &v88);
      if ( !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v74, v41) && (_DWORD)v88 )
      {
        v76 = 0;
        LODWORD(v88) = 1;
        CComPointer<IMsiPath>::operator=(&v81, &v79);
        v42 = v81;
        v76 = v82;
        goto LABEL_51;
      }
      if ( g_dmDiagnosticMode )
      {
        v36 = L"Backup folder is not writable";
        goto LABEL_55;
      }
    }
    else if ( g_dmDiagnosticMode )
    {
      v36 = L"Backup folder is created by user";
      goto LABEL_55;
    }
LABEL_56:
    v84 = 0;
    v76 = 0;
    v49 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v75 + 216LL))(v75, &v84);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v74, v49) || !v84 )
    {
      v73 = (*(__int64 (__fastcall **)(_QWORD *))(*v75 + 56LL))(v75);
      CMsiOpExecute::DispatchError(a1, 0x1000000, 1315, v73);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      goto LABEL_118;
    }
    LODWORD(v88) = 0;
    if ( Folder )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Backup folder is in cache folder",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      LODWORD(v88) = 1;
    }
    CComPointer<IMsiPath>::operator=(&v81, &v75);
    v42 = v81;
    v50 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v81 + 160))(v81, &v76);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v74, v50) )
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_40;
      v38 = L"Error: Failed to check cache backup folder status";
      goto LABEL_39;
    }
LABEL_51:
    v43 = *v42;
    v44 = 1;
    Folder = 1;
    v45 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *))(v43 + 56))(v42);
    LODWORD(SecurityDescriptor) = RunningAsLocalSystem();
    v47 = (int)SecurityDescriptor;
    if ( (_DWORD)SecurityDescriptor == -1 )
    {
      v48 = PostError(1501);
      CComPointer<IMsiDatabase>::operator=(&v74, v48);
LABEL_114:
      if ( v74 )
      {
        CMsiOpExecute::Message(a1, 0x1000000, v74);
        v44 = 3;
      }
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v45 + 16LL))(v45);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v85);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v81);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v75);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v79);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v74);
      v25 = v44;
      goto LABEL_120;
    }
    v51 = v76;
    FileW = -1;
    if ( !v76 )
      goto LABEL_97;
    v53 = v88;
    if ( (_DWORD)SecurityDescriptor != 1 || !(_DWORD)v88 )
    {
LABEL_84:
      if ( v51 )
      {
        if ( v47 == 1 && v53 )
        {
          LOBYTE(v46) = 1;
          SecurityDescriptor = 0;
          LODWORD(v88) = 0;
          SecureSecurityDescriptor = GetSecureSecurityDescriptor(&SecurityDescriptor, &v88, 1, v46);
          if ( SecureSecurityDescriptor )
          {
            v60 = PostError(2907, SecureSecurityDescriptor);
LABEL_80:
            CComPointer<IMsiDatabase>::operator=(&v74, v60);
LABEL_111:
            if ( FileW != -1 )
              CloseHandle((HANDLE)FileW);
            v44 = Folder;
            goto LABEL_114;
          }
          LOBYTE(v62) = 1;
          if ( (unsigned __int8)RefCountedTokenPrivilegesCore(1, v62) )
            v8 = 1;
          LODWORD(v88) = v8;
          v63 = NtSetSecurityObject((HANDLE)FileW, 1u, SecurityDescriptor);
          if ( v63 < 0 || (v63 = NtSetSecurityObject((HANDLE)FileW, 4u, SecurityDescriptor), v63 < 0) )
          {
            v64 = (*(__int64 (__fastcall **)(__int64 *))(*v42 + 56))(v42);
            v65 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 80LL))(v64);
            v66 = PostError(1926, v63, v65);
            CComPointer<IMsiDatabase>::operator=(&v74, v66);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
            CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v88);
            goto LABEL_111;
          }
          if ( FileW != -1 )
          {
            CloseHandle((HANDLE)FileW);
            FileW = -1;
          }
          CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v88);
        }
LABEL_110:
        (*(void (__fastcall **)(__int64))(**((_QWORD **)a1 + 123) + 32LL))(*((_QWORD *)a1 + 123));
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(**((_QWORD **)a1 + 123) + 96LL))(
          *((_QWORD *)a1 + 123),
          *((unsigned int *)a1 + 248),
          v80);
        (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(**((_QWORD **)a1 + 123) + 112LL))(
          *((_QWORD *)a1 + 123),
          *((unsigned int *)a1 + 249),
          v42);
        (*(void (__fastcall **)(__int64))(**((_QWORD **)a1 + 123) + 144LL))(*((_QWORD *)a1 + 123));
        *a3 = (__int64)v42;
        (*(void (__fastcall **)(__int64 *))(*v42 + 8))(v42);
        goto LABEL_111;
      }
LABEL_97:
      v67 = 0;
      SecurityDescriptor = 0;
      if ( v47 == 1 && (_DWORD)v88 )
      {
        v68 = (struct IMsiStream **)CComPointer<IEnumMsiRecord>::operator=(&SecurityDescriptor);
        v69 = GetSecureSecurityDescriptor(*(struct IMsiServices **)a1, v68, 1);
        if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v74, v69) )
          goto LABEL_100;
        v67 = SecurityDescriptor;
      }
      Folder = CMsiOpExecute::CreateFolder(a1, v42, 0, 0, v67, 0, 0, 1);
      if ( Folder == 1 )
      {
        (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(*v42 + 392))(v42, 0, 6);
        v71 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v45 + 80LL))(v45);
        if ( !IsJunctionFolder(v71) )
        {
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&SecurityDescriptor);
          goto LABEL_110;
        }
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Error: Unexpected Junction was found",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        v72 = PostError(1314, v45);
        CComPointer<IMsiDatabase>::operator=(&v74, v72);
      }
      else if ( g_dmDiagnosticMode )
      {
        v70 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v45 + 80LL))(v45);
        DebugString(
          9,
          0,
          0,
          L"Create folder failed: %s",
          v70,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
LABEL_100:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&SecurityDescriptor);
      goto LABEL_111;
    }
    v54 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v45 + 80LL))(v45);
    FileW = (__int64)CreateFileW(v54, 0x400C0000u, 3u, 0, 3u, 0x2200000u, 0);
    if ( FileW == -1 )
    {
      if ( !g_dmDiagnosticMode )
      {
LABEL_74:
        if ( FileW != -1 )
        {
          CloseHandle((HANDLE)FileW);
          FileW = -1;
        }
        v58 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v45 + 80LL))(v45);
        if ( !RemoveDirectoryW(v58) )
        {
          if ( g_dmDiagnosticMode )
          {
            v59 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v45 + 80LL))(v45);
            DebugString(
              9,
              0,
              0,
              L"Delete folder failed: %s",
              v59,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          }
          v60 = PostError(1314, v45);
          goto LABEL_80;
        }
        v51 = 0;
        v76 = 0;
        goto LABEL_83;
      }
      v55 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v45 + 80LL))(v45);
      DebugString(
        9,
        0,
        0,
        L"Folder is not accessible: %s",
        v55,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    else
    {
      v56 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v45 + 80LL))(v45);
      if ( !IsJunctionFolder(v56) )
      {
        v51 = v76;
LABEL_83:
        v47 = (int)SecurityDescriptor;
        v53 = v88;
        goto LABEL_84;
      }
    }
    if ( g_dmDiagnosticMode )
    {
      v57 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v45 + 80LL))(v45);
      DebugString(9, 0, 0, L"Cleanup folder : %s", v57, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
    }
    goto LABEL_74;
  }
  if ( g_dmDiagnosticMode )
  {
    v38 = L"Error: Get backup folder status failed";
LABEL_39:
    DebugString(9, 0, 0, v38, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
  }
LABEL_40:
  CMsiOpExecute::Message(a1, 0x1000000, v74);
LABEL_118:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v85);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v81);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v75);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v79);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v74);
LABEL_119:
  v25 = 3;
LABEL_120:
  CElevate::~CElevate((CElevate *)v86);
  return v25;
}

```

## disassembly

```asm
0x180068e88  mov     [rsp-8+arg_0], rbx
0x180068e8d  mov     [rsp-8+arg_10], r8
0x180068e92  push    rbp
0x180068e93  push    rsi
0x180068e94  push    rdi
0x180068e95  push    r12
0x180068e97  push    r13
0x180068e99  push    r14
0x180068e9b  push    r15
0x180068e9d  lea     rbp, [rsp-27h]
0x180068ea2  sub     rsp, 0C0h
0x180068ea9  mov     rbx, rdx
0x180068eac  mov     r13, rcx
0x180068eaf  mov     dl, 1; bool
0x180068eb1  lea     rcx, [rbp+57h+var_40]; this
0x180068eb5  mov     r15, r8
0x180068eb8  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x180068ebd  mov     rcx, r13; this
0x180068ec0  call    ?CreateBackupFolderCache@CMsiOpExecute@@IEAAPEAVIMsiRecord@@XZ; CMsiOpExecute::CreateBackupFolderCache(void)
0x180068ec5  xor     r12d, r12d
0x180068ec8  mov     [rbp+57h+var_90], rax
0x180068ecc  test    rax, rax
0x180068ecf  jz      short loc_180068EFD
0x180068ed1  mov     r8, rax
0x180068ed4  mov     edx, 1000000h
0x180068ed9  mov     rcx, r13
0x180068edc  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x180068ee1  lea     rcx, [rbp+57h+var_90]
0x180068ee5  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180068eea  lea     rcx, [rbp+57h+var_40]; this
0x180068eee  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x180068ef3  lea     eax, [r12+3]
0x180068ef8  jmp     loc_180069BD8
0x180068efd  mov     [r15], r12
0x180068f00  mov     esi, 2
0x180068f05  mov     [rbp+57h+var_70], r12
0x180068f09  mov     [rbp+57h+var_88], r12
0x180068f0d  mov     [rbp+57h+var_60], r12
0x180068f11  mov     [rbp+57h+var_7C], r12d
0x180068f15  test    rbx, rbx
0x180068f18  jnz     loc_180069044
0x180068f1e  call    ?GetTempDirectory@@YAAEBVIMsiString@@XZ; GetTempDirectory(void)
0x180068f23  mov     rdi, [r13+0]
0x180068f27  mov     rbx, rax
0x180068f2a  mov     rcx, [rbp+57h+var_88]
0x180068f2e  mov     rax, [rdi]
0x180068f31  mov     r14, [rax+78h]
0x180068f35  test    rcx, rcx
0x180068f38  jz      short loc_180068F46
0x180068f3a  mov     rax, [rcx]
0x180068f3d  mov     rax, [rax+10h]
0x180068f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f46  mov     [rbp+57h+var_88], r12
0x180068f4a  mov     rcx, rbx
0x180068f4d  mov     rdx, [rbx]
0x180068f50  mov     rax, [rdx+50h]
0x180068f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f59  mov     rdx, rax
0x180068f5c  lea     r8, [rbp+57h+var_88]
0x180068f60  mov     rax, r14
0x180068f63  mov     rcx, rdi
0x180068f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f6b  mov     rcx, [rbp+57h+var_90]
0x180068f6f  mov     rdi, rax
0x180068f72  test    rcx, rcx
0x180068f75  jz      short loc_180068F83
0x180068f77  mov     rdx, [rcx]
0x180068f7a  mov     rax, [rdx+10h]
0x180068f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f83  mov     [rbp+57h+var_90], rdi
0x180068f87  test    rdi, rdi
0x180068f8a  jz      short loc_180068FF3
0x180068f8c  mov     r8, rdi
0x180068f8f  mov     edx, 1000000h
0x180068f94  mov     rcx, r13
0x180068f97  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x180068f9c  mov     rax, [rbx]
0x180068f9f  mov     rcx, rbx
0x180068fa2  mov     rax, [rax+10h]
0x180068fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fab  mov     rcx, [rbp+57h+var_88]
0x180068faf  test    rcx, rcx
0x180068fb2  jz      short loc_180068FC0
0x180068fb4  mov     rax, [rcx]
0x180068fb7  mov     rax, [rax+10h]
0x180068fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fc0  mov     rcx, [rbp+57h+var_70]
0x180068fc4  test    rcx, rcx
0x180068fc7  jz      short loc_180068FD5
0x180068fc9  mov     rax, [rcx]
0x180068fcc  mov     rax, [rax+10h]
0x180068fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fd5  mov     rcx, [rbp+57h+var_90]
0x180068fd9  test    rcx, rcx
0x180068fdc  jz      loc_180069BC6
0x180068fe2  mov     rax, [rcx]
0x180068fe5  mov     rax, [rax+10h]
0x180068fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fee  jmp     loc_180069BC6
0x180068ff3  cmp     cs:?g_scServerContext@@3W4scEnum@@A, esi; scEnum g_scServerContext
0x180068ff9  jnz     short loc_18006903B
0x180068ffb  mov     r14, [rbp+57h+var_88]
0x180068fff  lea     rdx, aConfigMsi; "Config.Msi"
0x180069006  lea     rcx, [rbp+57h+arg_18]; this
0x18006900a  mov     rax, [r14]
0x18006900d  mov     rdi, [rax+68h]
0x180069011  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x180069016  mov     rcx, r14
0x180069019  mov     rdx, [rax]
0x18006901c  mov     rax, rdi
0x18006901f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069024  mov     rcx, [rbp+57h+arg_18]
0x180069028  mov     rax, [rcx]
0x18006902b  mov     rax, [rax+10h]
0x18006902f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069034  mov     [rbp+57h+var_7C], 1
0x18006903b  mov     rax, [rbx]
0x18006903e  mov     rax, [rax+10h]
0x180069042  jmp     short loc_18006904F
0x180069044  mov     rax, [rbx]
0x180069047  mov     [rbp+57h+var_88], rbx
0x18006904b  mov     rax, [rax+8]
0x18006904f  mov     rcx, rbx
0x180069052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069057  mov     rcx, [rbp+57h+var_88]
0x18006905b  mov     rax, [rcx]
0x18006905e  mov     rax, [rax+48h]
0x180069062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069067  mov     rdi, rax
0x18006906a  mov     [rbp+57h+var_48], rax
0x18006906e  mov     rcx, rdi
0x180069071  mov     rax, [rax]
0x180069074  mov     rax, [rax+0A8h]
0x18006907b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069080  mov     [rbp+57h+var_68], rax
0x180069084  lea     rdx, [rbp+57h+var_68]
0x180069088  mov     rcx, [rax]
0x18006908b  mov     r8, [rcx+0D0h]
0x180069092  mov     rcx, rax
0x180069095  mov     rax, r8
0x180069098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006909d  mov     rcx, [r13+3D8h]
0x1800690a4  mov     rax, [rcx]
0x1800690a7  mov     rax, [rax+20h]
0x1800690ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690b0  mov     rcx, [r13+3D8h]
0x1800690b7  mov     r8, [rbp+57h+var_68]
0x1800690bb  mov     edx, [r13+3E0h]
0x1800690c2  mov     rax, [rcx]
0x1800690c5  mov     rax, [rax+60h]
0x1800690c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690ce  mov     rcx, [r13+3D8h]
0x1800690d5  mov     rax, [rcx]
0x1800690d8  mov     rax, [rax+28h]
0x1800690dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690e1  test    eax, eax
0x1800690e3  jz      loc_18006920D
0x1800690e9  mov     rcx, [r13+3D8h]
0x1800690f0  mov     edx, [r13+3E4h]
0x1800690f7  mov     [rbp+57h+var_54], r12d
0x1800690fb  mov     rax, [rcx]
0x1800690fe  mov     rax, [rax+50h]
0x180069102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069107  mov     [rbp+57h+arg_18], rax
0x18006910b  mov     rbx, rax
0x18006910e  test    rax, rax
0x180069111  jz      loc_1800691EE
0x180069117  mov     rax, [rax]
0x18006911a  lea     rdx, [rbp+57h+var_54]
0x18006911e  mov     rcx, rbx
0x180069121  mov     rax, [rax+0A0h]
0x180069128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006912d  mov     rcx, [rbp+57h+var_90]
0x180069131  mov     r14, rax
0x180069134  test    rcx, rcx
0x180069137  jz      short loc_180069145
0x180069139  mov     rdx, [rcx]
0x18006913c  mov     rax, [rdx+10h]
0x180069140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069145  mov     [rbp+57h+var_90], r14
0x180069149  test    r14, r14
0x18006914c  jnz     loc_1800691EE
0x180069152  mov     r14d, 1
0x180069158  cmp     [rbp+57h+var_54], r14d
0x18006915c  jnz     loc_1800691EE
0x180069162  mov     [r15], rbx
0x180069165  mov     rcx, rbx
0x180069168  mov     rax, [rbx]
0x18006916b  mov     rax, [rax+8]
0x18006916f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069174  mov     rax, [rbx]
0x180069177  mov     rcx, rbx
0x18006917a  mov     rax, [rax+10h]
0x18006917e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069183  mov     rcx, [rbp+57h+var_68]
0x180069187  mov     rax, [rcx]
0x18006918a  mov     rax, [rax+10h]
0x18006918e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069193  test    rdi, rdi
0x180069196  jz      short loc_1800691A7
0x180069198  mov     rax, [rdi]
0x18006919b  mov     rcx, rdi
0x18006919e  mov     rax, [rax+10h]
0x1800691a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691a7  mov     rcx, [rbp+57h+var_88]
0x1800691ab  test    rcx, rcx
0x1800691ae  jz      short loc_1800691BC
0x1800691b0  mov     rax, [rcx]
0x1800691b3  mov     rax, [rax+10h]
0x1800691b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691bc  mov     rcx, [rbp+57h+var_70]
0x1800691c0  test    rcx, rcx
0x1800691c3  jz      short loc_1800691D1
0x1800691c5  mov     rax, [rcx]
0x1800691c8  mov     rax, [rax+10h]
0x1800691cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691d1  mov     rcx, [rbp+57h+var_90]
0x1800691d5  test    rcx, rcx
0x1800691d8  jz      short loc_1800691E6
0x1800691da  mov     rax, [rcx]
0x1800691dd  mov     rax, [rax+10h]
0x1800691e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691e6  mov     r15d, r14d
0x1800691e9  jmp     loc_180069BCC
0x1800691ee  mov     rcx, [r13+3D8h]
0x1800691f5  mov     rax, [rcx]
0x1800691f8  mov     rax, [rax+0B8h]
0x1800691ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069204  lea     rcx, [rbp+57h+arg_18]
0x180069208  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18006920d  mov     rax, [rdi]
0x180069210  mov     rcx, rdi
0x180069213  mov     rax, [rax+38h]
0x180069217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006921c  mov     r15, [r13+0]
0x180069220  mov     r12d, eax
0x180069223  mov     rcx, [r15]
0x180069226  mov     r14, [rcx+78h]
0x18006922a  lea     rcx, [rbp+57h+var_70]
0x18006922e  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x180069233  mov     rcx, [rdi]
0x180069236  mov     rbx, rax
0x180069239  mov     rax, [rcx+0A8h]
0x180069240  mov     rcx, rdi
0x180069243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069248  mov     rdi, rax
0x18006924b  mov     rcx, rax
0x18006924e  mov     rdx, [rax]
0x180069251  mov     rax, [rdx+50h]
0x180069255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006925a  mov     rdx, rax
0x18006925d  mov     r8, rbx
0x180069260  mov     rax, r14
0x180069263  mov     rcx, r15
0x180069266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006926b  mov     rax, [rdi]
0x18006926e  mov     rcx, rdi
0x180069271  mov     rax, [rax+10h]
0x180069275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006927a  mov     rdi, [rbp+57h+var_70]
0x18006927e  lea     rdx, aConfigMsi; "Config.Msi"
0x180069285  lea     rcx, [rbp+57h+arg_18]; this
0x180069289  mov     rax, [rdi]
0x18006928c  mov     rbx, [rax+68h]
0x180069290  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x180069295  mov     rcx, rdi
0x180069298  mov     rdx, [rax]
0x18006929b  mov     rax, rbx
0x18006929e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800692a3  mov     rcx, [rbp+57h+arg_18]
0x1800692a7  mov     rax, [rcx]
0x1800692aa  mov     rax, [rax+10h]
0x1800692ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800692b3  xor     r15d, r15d
0x1800692b6  lea     r14, aNull; "(NULL)"
0x1800692bd  mov     [rbp+57h+var_58], r15d
0x1800692c1  lea     ebx, [r15+9]
0x1800692c5  cmp     r12d, 4
0x1800692c9  jnz     short loc_1800692E4
0x1800692cb  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1800692d2  jz      loc_1800694E7
0x1800692d8  lea     r9, aInstallTargetI; "Install target is remote drive"
0x1800692df  jmp     loc_1800694B3
0x1800692e4  mov     rcx, [rbp+57h+var_70]
0x1800692e8  lea     rdx, [rbp+57h+var_58]
0x1800692ec  mov     rax, [rcx]
0x1800692ef  mov     rax, [rax+0A0h]
0x1800692f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800692fb  mov     rdx, rax
0x1800692fe  lea     rcx, [rbp+57h+var_90]
0x180069302  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x180069307  cmp     [rax], r15
0x18006930a  jz      short loc_180069366
0x18006930c  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x180069313  jz      short loc_180069350
0x180069315  lea     r9, aErrorGetBackup; "Error: Get backup folder status failed"
0x18006931c  mov     [rsp+0F0h+var_98], r15; void *
0x180069321  xor     edx, edx; unsigned __int16
0x180069323  mov     [rsp+0F0h+var_A0], r15d; unsigned int
0x180069328  xor     r8d, r8d; int
  ... truncated ...
```
