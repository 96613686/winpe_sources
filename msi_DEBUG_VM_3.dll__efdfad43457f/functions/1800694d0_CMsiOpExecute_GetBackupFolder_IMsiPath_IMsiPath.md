# CMsiOpExecute::GetBackupFolder(IMsiPath *,IMsiPath * &)

- ea: `0x1800694d0`
- end: `0x18006a211`
- name: `?GetBackupFolder@CMsiOpExecute@@IEAA?AW4iesEnum@@PEAVIMsiPath@@AEAPEAV3@@Z`
- size: `3393`
- prototype: ``
- caller_count: `7`
- callee_count: `26`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006aa24`
- `0x1800732a4`
- `0x1800d7a20`
- `0x1801df9d8`
- `0x1801f2570`
- `0x1801f3420`
- `0x1801f89f0`

## callees

- `0x18001036c`
- `0x180012620`
- `0x180024f9c`
- `0x180025904`
- `0x180025a18`
- `0x180027b54`
- `0x18002b35c`
- `0x180035a8c`
- `0x18004295c`
- `0x180066074`
- `0x180068680`
- `0x1800694d0`
- `0x18006a218`
- `0x180071ab0`
- `0x180076e28`
- `0x18007ccec`
- `0x18007d8cc`
- `0x18008bed8`
- `0x1800a55e0`
- `0x1800cb7a0`
- `0x180127748`
- `0x18013a830`
- `0x1801446ac`
- `0x18014e4d4`
- `0x1801b12a4`
- `0x18025c010`

## import_xrefs

- `ntdll!NtSetSecurityObject` at `0x180069e6b`
- `ntdll!NtSetSecurityObject` at `0x180069e83`
- `ntdll!NtSetSecurityObject` at `0x180069e6b`
- `ntdll!NtSetSecurityObject` at `0x180069e83`
- `KERNEL32!CloseHandle` at `0x180069d52`
- `KERNEL32!CloseHandle` at `0x180069e98`
- `KERNEL32!CloseHandle` at `0x18006a0fb`
- `KERNEL32!CloseHandle` at `0x180069d52`
- `KERNEL32!CloseHandle` at `0x180069e98`
- `KERNEL32!CloseHandle` at `0x18006a0fb`
- `KERNEL32!CreateFileW` at `0x180069c6f`
- `KERNEL32!CreateFileW` at `0x180069c6f`
- `KERNEL32!RemoveDirectoryW` at `0x180069d6e`
- `KERNEL32!RemoveDirectoryW` at `0x180069d6e`

## string_xrefs

- `0x180069647`: `Config.Msi`
- `0x1800698c6`: `Config.Msi`
- `0x18006a01b`: `Error: Unexpected Junction was found`
- `0x180069920`: `Install target is remote drive`
- `0x180069a3c`: `Backup folder is created by user`
- `0x180069b87`: `Backup folder is in cache folder`
- `0x180069c0d`: `Error: Failed to check cache backup folder status`
- `0x180069c9c`: `Folder is not accessible: %s`
- `0x180069d96`: `Delete folder failed: %s`
- `0x180069fa0`: `Create folder failed: %s`

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
0x1800694d0  mov     [rsp-8+arg_0], rbx
0x1800694d5  mov     [rsp-8+arg_10], r8
0x1800694da  push    rbp
0x1800694db  push    rsi
0x1800694dc  push    rdi
0x1800694dd  push    r12
0x1800694df  push    r13
0x1800694e1  push    r14
0x1800694e3  push    r15
0x1800694e5  lea     rbp, [rsp-27h]
0x1800694ea  sub     rsp, 0C0h
0x1800694f1  mov     rbx, rdx
0x1800694f4  mov     r13, rcx
0x1800694f7  mov     dl, 1; bool
0x1800694f9  lea     rcx, [rbp+57h+var_40]; this
0x1800694fd  mov     r15, r8
0x180069500  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x180069505  mov     rcx, r13; this
0x180069508  call    ?CreateBackupFolderCache@CMsiOpExecute@@IEAAPEAVIMsiRecord@@XZ; CMsiOpExecute::CreateBackupFolderCache(void)
0x18006950d  xor     r12d, r12d
0x180069510  mov     [rbp+57h+var_90], rax
0x180069514  test    rax, rax
0x180069517  jz      short loc_180069545
0x180069519  mov     r8, rax
0x18006951c  mov     edx, 1000000h
0x180069521  mov     rcx, r13
0x180069524  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x180069529  lea     rcx, [rbp+57h+var_90]
0x18006952d  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180069532  lea     rcx, [rbp+57h+var_40]; this
0x180069536  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18006953b  lea     eax, [r12+3]
0x180069540  jmp     loc_18006A1F6
0x180069545  mov     [r15], r12
0x180069548  mov     esi, 2
0x18006954d  mov     [rbp+57h+var_70], r12
0x180069551  mov     [rbp+57h+var_88], r12
0x180069555  mov     [rbp+57h+var_60], r12
0x180069559  mov     [rbp+57h+var_7C], r12d
0x18006955d  test    rbx, rbx
0x180069560  jnz     loc_18006968C
0x180069566  call    ?GetTempDirectory@@YAAEBVIMsiString@@XZ; GetTempDirectory(void)
0x18006956b  mov     rdi, [r13+0]
0x18006956f  mov     rbx, rax
0x180069572  mov     rcx, [rbp+57h+var_88]
0x180069576  mov     rax, [rdi]
0x180069579  mov     r14, [rax+78h]
0x18006957d  test    rcx, rcx
0x180069580  jz      short loc_18006958E
0x180069582  mov     rax, [rcx]
0x180069585  mov     rax, [rax+10h]
0x180069589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006958e  mov     [rbp+57h+var_88], r12
0x180069592  mov     rcx, rbx
0x180069595  mov     rdx, [rbx]
0x180069598  mov     rax, [rdx+50h]
0x18006959c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695a1  mov     rdx, rax
0x1800695a4  lea     r8, [rbp+57h+var_88]
0x1800695a8  mov     rax, r14
0x1800695ab  mov     rcx, rdi
0x1800695ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695b3  mov     rcx, [rbp+57h+var_90]
0x1800695b7  mov     rdi, rax
0x1800695ba  test    rcx, rcx
0x1800695bd  jz      short loc_1800695CB
0x1800695bf  mov     rdx, [rcx]
0x1800695c2  mov     rax, [rdx+10h]
0x1800695c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695cb  mov     [rbp+57h+var_90], rdi
0x1800695cf  test    rdi, rdi
0x1800695d2  jz      short loc_18006963B
0x1800695d4  mov     r8, rdi
0x1800695d7  mov     edx, 1000000h
0x1800695dc  mov     rcx, r13
0x1800695df  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1800695e4  mov     rax, [rbx]
0x1800695e7  mov     rcx, rbx
0x1800695ea  mov     rax, [rax+10h]
0x1800695ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695f3  mov     rcx, [rbp+57h+var_88]
0x1800695f7  test    rcx, rcx
0x1800695fa  jz      short loc_180069608
0x1800695fc  mov     rax, [rcx]
0x1800695ff  mov     rax, [rax+10h]
0x180069603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069608  mov     rcx, [rbp+57h+var_70]
0x18006960c  test    rcx, rcx
0x18006960f  jz      short loc_18006961D
0x180069611  mov     rax, [rcx]
0x180069614  mov     rax, [rax+10h]
0x180069618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006961d  mov     rcx, [rbp+57h+var_90]
0x180069621  test    rcx, rcx
0x180069624  jz      loc_18006A1E4
0x18006962a  mov     rax, [rcx]
0x18006962d  mov     rax, [rax+10h]
0x180069631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069636  jmp     loc_18006A1E4
0x18006963b  cmp     cs:?g_scServerContext@@3W4scEnum@@A, esi; scEnum g_scServerContext
0x180069641  jnz     short loc_180069683
0x180069643  mov     r14, [rbp+57h+var_88]
0x180069647  lea     rdx, aConfigMsi; "Config.Msi"
0x18006964e  lea     rcx, [rbp+57h+arg_18]; this
0x180069652  mov     rax, [r14]
0x180069655  mov     rdi, [rax+68h]
0x180069659  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x18006965e  mov     rcx, r14
0x180069661  mov     rdx, [rax]
0x180069664  mov     rax, rdi
0x180069667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006966c  mov     rcx, [rbp+57h+arg_18]
0x180069670  mov     rax, [rcx]
0x180069673  mov     rax, [rax+10h]
0x180069677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006967c  mov     [rbp+57h+var_7C], 1
0x180069683  mov     rax, [rbx]
0x180069686  mov     rax, [rax+10h]
0x18006968a  jmp     short loc_180069697
0x18006968c  mov     rax, [rbx]
0x18006968f  mov     [rbp+57h+var_88], rbx
0x180069693  mov     rax, [rax+8]
0x180069697  mov     rcx, rbx
0x18006969a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006969f  mov     rcx, [rbp+57h+var_88]
0x1800696a3  mov     rax, [rcx]
0x1800696a6  mov     rax, [rax+48h]
0x1800696aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696af  mov     rdi, rax
0x1800696b2  mov     [rbp+57h+var_48], rax
0x1800696b6  mov     rcx, rdi
0x1800696b9  mov     rax, [rax]
0x1800696bc  mov     rax, [rax+0A8h]
0x1800696c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696c8  mov     [rbp+57h+var_68], rax
0x1800696cc  lea     rdx, [rbp+57h+var_68]
0x1800696d0  mov     rcx, [rax]
0x1800696d3  mov     r8, [rcx+0D0h]
0x1800696da  mov     rcx, rax
0x1800696dd  mov     rax, r8
0x1800696e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696e5  mov     rcx, [r13+3D8h]
0x1800696ec  mov     rax, [rcx]
0x1800696ef  mov     rax, [rax+20h]
0x1800696f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696f8  mov     rcx, [r13+3D8h]
0x1800696ff  mov     r8, [rbp+57h+var_68]
0x180069703  mov     edx, [r13+3E0h]
0x18006970a  mov     rax, [rcx]
0x18006970d  mov     rax, [rax+60h]
0x180069711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069716  mov     rcx, [r13+3D8h]
0x18006971d  mov     rax, [rcx]
0x180069720  mov     rax, [rax+28h]
0x180069724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069729  test    eax, eax
0x18006972b  jz      loc_180069855
0x180069731  mov     rcx, [r13+3D8h]
0x180069738  mov     edx, [r13+3E4h]
0x18006973f  mov     [rbp+57h+var_54], r12d
0x180069743  mov     rax, [rcx]
0x180069746  mov     rax, [rax+50h]
0x18006974a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006974f  mov     [rbp+57h+arg_18], rax
0x180069753  mov     rbx, rax
0x180069756  test    rax, rax
0x180069759  jz      loc_180069836
0x18006975f  mov     rax, [rax]
0x180069762  lea     rdx, [rbp+57h+var_54]
0x180069766  mov     rcx, rbx
0x180069769  mov     rax, [rax+0A0h]
0x180069770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069775  mov     rcx, [rbp+57h+var_90]
0x180069779  mov     r14, rax
0x18006977c  test    rcx, rcx
0x18006977f  jz      short loc_18006978D
0x180069781  mov     rdx, [rcx]
0x180069784  mov     rax, [rdx+10h]
0x180069788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006978d  mov     [rbp+57h+var_90], r14
0x180069791  test    r14, r14
0x180069794  jnz     loc_180069836
0x18006979a  mov     r14d, 1
0x1800697a0  cmp     [rbp+57h+var_54], r14d
0x1800697a4  jnz     loc_180069836
0x1800697aa  mov     [r15], rbx
0x1800697ad  mov     rcx, rbx
0x1800697b0  mov     rax, [rbx]
0x1800697b3  mov     rax, [rax+8]
0x1800697b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697bc  mov     rax, [rbx]
0x1800697bf  mov     rcx, rbx
0x1800697c2  mov     rax, [rax+10h]
0x1800697c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697cb  mov     rcx, [rbp+57h+var_68]
0x1800697cf  mov     rax, [rcx]
0x1800697d2  mov     rax, [rax+10h]
0x1800697d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697db  test    rdi, rdi
0x1800697de  jz      short loc_1800697EF
0x1800697e0  mov     rax, [rdi]
0x1800697e3  mov     rcx, rdi
0x1800697e6  mov     rax, [rax+10h]
0x1800697ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697ef  mov     rcx, [rbp+57h+var_88]
0x1800697f3  test    rcx, rcx
0x1800697f6  jz      short loc_180069804
0x1800697f8  mov     rax, [rcx]
0x1800697fb  mov     rax, [rax+10h]
0x1800697ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069804  mov     rcx, [rbp+57h+var_70]
0x180069808  test    rcx, rcx
0x18006980b  jz      short loc_180069819
0x18006980d  mov     rax, [rcx]
0x180069810  mov     rax, [rax+10h]
0x180069814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069819  mov     rcx, [rbp+57h+var_90]
0x18006981d  test    rcx, rcx
0x180069820  jz      short loc_18006982E
0x180069822  mov     rax, [rcx]
0x180069825  mov     rax, [rax+10h]
0x180069829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006982e  mov     r15d, r14d
0x180069831  jmp     loc_18006A1EA
0x180069836  mov     rcx, [r13+3D8h]
0x18006983d  mov     rax, [rcx]
0x180069840  mov     rax, [rax+0B8h]
0x180069847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006984c  lea     rcx, [rbp+57h+arg_18]
0x180069850  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180069855  mov     rax, [rdi]
0x180069858  mov     rcx, rdi
0x18006985b  mov     rax, [rax+38h]
0x18006985f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069864  mov     r15, [r13+0]
0x180069868  mov     r12d, eax
0x18006986b  mov     rcx, [r15]
0x18006986e  mov     r14, [rcx+78h]
0x180069872  lea     rcx, [rbp+57h+var_70]
0x180069876  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18006987b  mov     rcx, [rdi]
0x18006987e  mov     rbx, rax
0x180069881  mov     rax, [rcx+0A8h]
0x180069888  mov     rcx, rdi
0x18006988b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069890  mov     rdi, rax
0x180069893  mov     rcx, rax
0x180069896  mov     rdx, [rax]
0x180069899  mov     rax, [rdx+50h]
0x18006989d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698a2  mov     rdx, rax
0x1800698a5  mov     r8, rbx
0x1800698a8  mov     rax, r14
0x1800698ab  mov     rcx, r15
0x1800698ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698b3  mov     rax, [rdi]
0x1800698b6  mov     rcx, rdi
0x1800698b9  mov     rax, [rax+10h]
0x1800698bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698c2  mov     rdi, [rbp+57h+var_70]
0x1800698c6  lea     rdx, aConfigMsi; "Config.Msi"
0x1800698cd  lea     rcx, [rbp+57h+arg_18]; this
0x1800698d1  mov     rax, [rdi]
0x1800698d4  mov     rbx, [rax+68h]
0x1800698d8  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1800698dd  mov     rcx, rdi
0x1800698e0  mov     rdx, [rax]
0x1800698e3  mov     rax, rbx
0x1800698e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698eb  mov     rcx, [rbp+57h+arg_18]
0x1800698ef  mov     rax, [rcx]
0x1800698f2  mov     rax, [rax+10h]
0x1800698f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698fb  xor     r15d, r15d
0x1800698fe  lea     r14, aNull; "(NULL)"
0x180069905  mov     [rbp+57h+var_58], r15d
0x180069909  lea     ebx, [r15+9]
0x18006990d  cmp     r12d, 4
0x180069911  jnz     short loc_18006992C
0x180069913  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18006991a  jz      loc_180069B2F
0x180069920  lea     r9, aInstallTargetI; "Install target is remote drive"
0x180069927  jmp     loc_180069AFB
0x18006992c  mov     rcx, [rbp+57h+var_70]
0x180069930  lea     rdx, [rbp+57h+var_58]
0x180069934  mov     rax, [rcx]
0x180069937  mov     rax, [rax+0A0h]
0x18006993e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069943  mov     rdx, rax
0x180069946  lea     rcx, [rbp+57h+var_90]
0x18006994a  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18006994f  cmp     [rax], r15
0x180069952  jz      short loc_1800699AE
0x180069954  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18006995b  jz      short loc_180069998
0x18006995d  lea     r9, aErrorGetBackup; "Error: Get backup folder status failed"
0x180069964  mov     [rsp+0F0h+var_98], r15; void *
0x180069969  xor     edx, edx; unsigned __int16
0x18006996b  mov     [rsp+0F0h+var_A0], r15d; unsigned int
0x180069970  xor     r8d, r8d; int
  ... truncated ...
```
