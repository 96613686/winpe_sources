# CMsiOpExecute::DoMachineVsUserInitialization(void)

- ea: `0x1801e7568`
- end: `0x1801e8579`
- name: `?DoMachineVsUserInitialization@CMsiOpExecute@@IEAA?AW4iesEnum@@XZ`
- size: `4113`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180203a70`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18000c4bc`
- `0x180013fe4`
- `0x180014e38`
- `0x18002e870`
- `0x180038e54`
- `0x180038e70`
- `0x18004cb88`
- `0x180058790`
- `0x18007cf38`
- `0x180086264`
- `0x18008c93c`
- `0x180097c78`
- `0x18009ad3c`
- `0x1800ada5c`
- `0x1800d8584`
- `0x1800fa370`
- `0x18012e4e8`
- `0x18013fa30`
- `0x18014ae8c`
- `0x1801526d8`
- `0x1801738a4`
- `0x1801e7568`
- `0x1801e8b7c`
- `0x1801e8be8`
- `0x1801e8da4`
- `0x1801faec4`
- `0x18021fd60`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1801e83f7`
- `ADVAPI32!RegCloseKey` at `0x1801e8497`
- `ADVAPI32!RegCloseKey` at `0x1801e8508`
- `ADVAPI32!RegCloseKey` at `0x1801e8529`
- `ADVAPI32!RegCloseKey` at `0x1801e83f7`
- `ADVAPI32!RegCloseKey` at `0x1801e8497`
- `ADVAPI32!RegCloseKey` at `0x1801e8508`
- `ADVAPI32!RegCloseKey` at `0x1801e8529`

## string_xrefs

- `0x1801e77e9`: `Error: Failed to create Cache Path`
- `0x1801e7b5f`: `Error: Failed to create Cache Path with Product key`
- `0x1801e7bb6`: `Error: Failed to Create AppData Cache Path with Product ID`
- `0x1801e7c62`: `Error: Failed to Generate Cache Security descriptor`
- `0x1801e7ce0`: `Error: Failed to Create AppData Microsoft Path`
- `0x1801e7d84`: `Error: Failed to Check AppData Microsoft Folder Path status`
- `0x1801e7e6a`: `Error: Failed to create lock file in AppData Microsoft Folder`
- `0x1801e7f05`: `Error: Failed to Create AppData Cache Path`
- `0x1801e7f9e`: `Error: Failed to Create AppData Cache Folder`
- `0x1801e807f`: `Error: Unexpected Junction was found in AppData Cache Folder`
- `0x1801e817c`: `Error: Failed to Check AppData Cache Product key Path status`
- `0x1801e8213`: `Error: Failed to Apply ACL to AppData Cache Product Key Folder`
- `0x1801e830a`: `Error: Unexpected Junction was found in AppData Cache Product Key Folder`

## pseudocode

```c
__int64 __fastcall CMsiOpExecute::DoMachineVsUserInitialization(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  unsigned int v5; // r12d
  int v6; // r14d
  struct IMsiRecord *v7; // rax
  _QWORD *v8; // r13
  _QWORD *v9; // rdi
  const struct IMsiString *ProductKey; // rbx
  __int64 v11; // rax
  char v12; // al
  __int64 v13; // r8
  int PublishKeyByUser; // eax
  const struct IMsiString *MsiDirectory; // rax
  __int64 **v16; // r13
  __int64 v17; // rcx
  const struct IMsiString *v18; // rbx
  __int64 v19; // r14
  __int64 (__fastcall *v20)(__int64, __int64, __int64); // rsi
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rax
  struct IMsiRecord *v24; // rdi
  struct IMsiRecord *v25; // r8
  _QWORD *v26; // r14
  _QWORD *v27; // r13
  const struct IMsiString *v28; // rbx
  __int64 v29; // rax
  char v30; // al
  int v31; // eax
  __int64 v32; // rdx
  const struct IMsiString *v33; // rbx
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  __int64 *v37; // rsi
  __int64 (__fastcall *v38)(__int64 *, const struct IMsiString *); // rdi
  const struct IMsiString *v39; // r14
  __int64 v40; // rax
  struct IMsiPath **v41; // rax
  struct IMsiRecord *AppDataCachePathWithProductKey; // rax
  BOOL v43; // edi
  int v44; // eax
  struct IMsiStream **v45; // rax
  struct IMsiPath **v46; // rax
  struct IMsiRecord *AppDataMicrosoftPath; // rax
  struct IMsiRecord *v48; // rdi
  const struct IMsiString *v49; // rdi
  __int64 v50; // rax
  struct IMsiRecord *v51; // rsi
  struct IMsiRecord *v52; // r8
  const WCHAR *v53; // rax
  struct IMsiRecord *v54; // rax
  struct IMsiPath **v55; // rax
  struct IMsiRecord *AppDataCachePath; // rax
  struct IMsiRecord *v57; // rsi
  unsigned int Folder; // esi
  const struct IMsiString *v59; // rsi
  const unsigned __int16 *v60; // rax
  struct IMsiRecord *v61; // r8
  __int64 *v62; // rcx
  __int64 v63; // rax
  struct IMsiRecord *v64; // r14
  unsigned int v65; // r14d
  __int64 v66; // r14
  const unsigned __int16 *v67; // rax
  struct IMsiRecord *v68; // rax
  HKEY v69; // rcx
  const unsigned __int16 *v70; // rax
  unsigned int v71; // r8d
  unsigned __int16 *v72; // r9
  int v73; // eax
  const struct IMsiString *v74; // rdx
  struct IMsiRecord *v75; // rax
  HKEY v76; // rcx
  const unsigned __int16 *v77; // rax
  unsigned int v78; // r8d
  unsigned __int16 *v79; // r9
  HKEY v80; // rcx
  HKEY v81; // rcx
  unsigned int v83; // [rsp+20h] [rbp-59h]
  unsigned int v84; // [rsp+20h] [rbp-59h]
  struct _SECURITY_ATTRIBUTES *v85; // [rsp+30h] [rbp-49h]
  struct _SECURITY_ATTRIBUTES *v86; // [rsp+30h] [rbp-49h]
  __int64 v87; // [rsp+60h] [rbp-19h] BYREF
  struct IMsiString *v88; // [rsp+68h] [rbp-11h] BYREF
  __int64 v89; // [rsp+70h] [rbp-9h] BYREF
  __int64 *v90; // [rsp+78h] [rbp-1h] BYREF
  _QWORD v91[10]; // [rsp+80h] [rbp+7h] BYREF
  struct IMsiRecord *v92; // [rsp+E0h] [rbp+67h] BYREF
  struct IMsiRecord *v93; // [rsp+E8h] [rbp+6Fh] BYREF
  struct IMsiRecord *v94; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v95; // [rsp+F8h] [rbp+7Fh] BYREF

  v3 = (*(_BYTE *)(a1 + 864) & 8) == 0;
  v94 = 0;
  v5 = 3;
  *(_BYTE *)(a1 + 907) = 0;
  if ( !v3 )
  {
    v6 = RunningAsLocalSystem();
    if ( v6 == -1 )
    {
LABEL_3:
      v7 = PostError(1501);
LABEL_4:
      v92 = v7;
      CMsiOpExecute::Message(a1, 0x1000000, v7);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v92);
      goto LABEL_135;
    }
    v8 = (_QWORD *)(a1 + 696);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 696) + 16LL))(*(_QWORD *)(a1 + 696));
    *(_QWORD *)(a1 + 696) = &MsiString::s_NullString;
    v9 = (_QWORD *)(a1 + 688);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 688) + 16LL))(*(_QWORD *)(a1 + 688));
    *(_QWORD *)(a1 + 688) = &MsiString::s_NullString;
    ProductKey = CMsiOpExecute::GetProductKey((CMsiOpExecute *)a1);
    v11 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)ProductKey + 80LL))(ProductKey);
    v83 = a1 + 688;
    v12 = VerifyProduct(2, v11, a1 + 664, a1 + 672);
    *(_BYTE *)(a1 + 906) = v12;
    *(_BYTE *)(a1 + 907) = v12;
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)ProductKey + 16LL))(ProductKey);
    if ( !*(_BYTE *)(a1 + 906) )
    {
      if ( IsImpersonating(1) && !IsAdmin() )
      {
        if ( (*(_DWORD *)(a1 + 864) & 0x20000000) == 0 || v6 != 1 )
        {
          v13 = 1925;
LABEL_11:
          CMsiOpExecute::DispatchError(a1, 0x1000000, v13);
          goto LABEL_135;
        }
        v9 = (_QWORD *)(a1 + 688);
      }
      *(_BYTE *)(a1 + 906) = 1;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 16LL))(*v8);
      *v8 = &MsiString::s_NullString;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 16LL))(*v9);
      *v9 = &MsiString::s_NullString;
      v83 = (unsigned int)v9;
      PublishKeyByUser = GetPublishKeyByUser(0, 2, a1 + 664, a1 + 672);
      if ( PublishKeyByUser )
      {
LABEL_14:
        v7 = PostError(2929, PublishKeyByUser);
        goto LABEL_4;
      }
      goto LABEL_19;
    }
    if ( *(_DWORD *)(a1 + 500) != 3 || !*(_DWORD *)(a1 + 656) || (*(_DWORD *)(a1 + 864) & 0x20000000) != 0 && v6 == 1 )
      goto LABEL_19;
LABEL_41:
    v13 = 1945;
    goto LABEL_11;
  }
  if ( (unsigned int)GetIntegerPolicyValue(0, 1, a3) )
  {
    v13 = 1934;
    goto LABEL_11;
  }
  v26 = (_QWORD *)(a1 + 696);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 696) + 16LL))(*(_QWORD *)(a1 + 696));
  *(_QWORD *)(a1 + 696) = &MsiString::s_NullString;
  v27 = (_QWORD *)(a1 + 688);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 688) + 16LL))(*(_QWORD *)(a1 + 688));
  *(_QWORD *)(a1 + 688) = &MsiString::s_NullString;
  v28 = CMsiOpExecute::GetProductKey((CMsiOpExecute *)a1);
  v29 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v28 + 80LL))(v28);
  v83 = a1 + 688;
  v30 = VerifyProduct(0, v29, a1 + 664, a1 + 672);
  *(_BYTE *)(a1 + 906) = v30;
  *(_BYTE *)(a1 + 907) = v30;
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v28 + 16LL))(v28);
  v31 = RunningAsLocalSystem();
  v3 = *(_BYTE *)(a1 + 906) == 0;
  LODWORD(v92) = v31;
  if ( v3 )
  {
    if ( v31 == -1 )
      goto LABEL_3;
    if ( (*(_DWORD *)(a1 + 864) & 0x20000000) != 0 && v31 == 1 )
    {
      *(_BYTE *)(a1 + 906) = 1;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 16LL))(*v26);
      *v26 = &MsiString::s_NullString;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 16LL))(*v27);
      v32 = 0;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 16LL))(*v26);
      *v26 = &MsiString::s_NullString;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 16LL))(*v27);
      *v27 = &MsiString::s_NullString;
      v33 = CMsiOpExecute::GetProductKey((CMsiOpExecute *)a1);
      v34 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v33 + 80LL))(v33);
      v83 = a1 + 688;
      *(_BYTE *)(a1 + 907) = VerifyProduct(1, v34, a1 + 664, a1 + 672);
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v33 + 16LL))(v33);
      if ( *(_BYTE *)(a1 + 907) )
      {
        v31 = (int)v92;
        goto LABEL_36;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 16LL))(*v26);
      *v26 = &MsiString::s_NullString;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 16LL))(*v27);
      v32 = 1;
    }
    v83 = a1 + 688;
    *v27 = &MsiString::s_NullString;
    PublishKeyByUser = GetPublishKeyByUser(0, v32, a1 + 664, a1 + 672);
    if ( PublishKeyByUser )
      goto LABEL_14;
    v31 = (int)v92;
  }
LABEL_36:
  if ( !*(_BYTE *)(a1 + 906) )
    goto LABEL_19;
  if ( *(_DWORD *)(a1 + 500) == 3 && *(_DWORD *)(a1 + 656) && ((*(_DWORD *)(a1 + 864) & 0x20000000) == 0 || v31 != 1) )
    goto LABEL_41;
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v92 = (struct IMsiRecord *)&MsiString::s_NullString;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 704) + 16LL))(*(_QWORD *)(a1 + 704));
  *(_QWORD *)(a1 + 704) = &MsiString::s_NullString;
  v83 = a1 + 704;
  v35 = GetPublishKeyByUser(0, 1, a1 + 680, &v93);
  if ( v35 )
  {
    v93 = PostError(2929, v35);
    CMsiOpExecute::Message(a1, 0x1000000, v93);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v93);
    v36 = *(_QWORD *)v92;
LABEL_96:
    (*(void (**)(void))(v36 + 16))();
    goto LABEL_135;
  }
  (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v92 + 16LL))(v92);
LABEL_19:
  *(_BYTE *)(a1 + 892) = 1;
  MsiDirectory = GetMsiDirectory();
  v16 = (__int64 **)(a1 + 616);
  v17 = a1 + 616;
  v18 = MsiDirectory;
  if ( (*(_BYTE *)(a1 + 864) & 8) != 0 )
  {
    v19 = *(_QWORD *)a1;
    v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(**(_QWORD **)a1 + 120LL);
    v21 = CComPointer<IEnumMsiRecord>::operator=(v17);
    v22 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v18 + 80LL))(v18);
    v23 = v20(v19, v22, v21);
    CComPointer<IMsiDatabase>::operator=(&v94, v23);
    v24 = v94;
    if ( v94 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: Failed to create Cache Path",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
LABEL_23:
      v25 = v24;
LABEL_119:
      CMsiOpExecute::Message(a1, 0x1000000, v25);
      goto LABEL_95;
    }
    v37 = *v16;
    v38 = *(__int64 (__fastcall **)(__int64 *, const struct IMsiString *))(**v16 + 104);
    v39 = CMsiOpExecute::GetProductKey((CMsiOpExecute *)a1);
    v40 = v38(v37, v39);
    CComPointer<IMsiDatabase>::operator=(&v94, v40);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v39 + 16LL))(v39);
    v24 = v94;
    if ( v94 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: Failed to create Cache Path with Product key",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      goto LABEL_23;
    }
    *(_BYTE *)(a1 + 892) = 0;
    goto LABEL_113;
  }
  v41 = (struct IMsiPath **)CComPointer<IEnumMsiRecord>::operator=(v17);
  AppDataCachePathWithProductKey = CMsiOpExecute::GetAppDataCachePathWithProductKey((CMsiOpExecute *)a1, v41, 0);
  CComPointer<IMsiDatabase>::operator=(&v94, AppDataCachePathWithProductKey);
  v24 = v94;
  if ( v94 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"Error: Failed to Create AppData Cache Path with Product ID",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_23;
  }
  v43 = 1;
  v44 = RunningAsLocalSystem();
  if ( g_scServerContext != 2 )
    v43 = v44 != 0;
  v89 = (*(__int64 (__fastcall **)(__int64 *))(**v16 + 72))(*v16);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v89 + 56LL))(v89) != 4 && v43 )
  {
    v95 = 0;
    MsiString::MsiString((MsiString *)&v88, L"O:BAG:SYD:PAI(A;OICI;0x1200a9;;;WD)(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)");
    v45 = (struct IMsiStream **)CComPointer<IEnumMsiRecord>::operator=(&v95);
    if ( !GenerateSDFromSDDL(v88, v45) )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: Failed to Generate Cache Security descriptor",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      goto LABEL_94;
    }
    v87 = 0;
    v46 = (struct IMsiPath **)CComPointer<IEnumMsiRecord>::operator=(&v87);
    AppDataMicrosoftPath = CMsiOpExecute::GetAppDataMicrosoftPath((CMsiOpExecute *)a1, v46);
    CComPointer<IMsiDatabase>::operator=(&v94, AppDataMicrosoftPath);
    v48 = v94;
    if ( v94 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: Failed to Create AppData Microsoft Path",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      CMsiOpExecute::Message(a1, 0x1000000, v48);
      goto LABEL_93;
    }
    v49 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v87 + 56LL))(v87);
    LODWORD(v92) = 0;
    v50 = (*(__int64 (__fastcall **)(__int64, struct IMsiRecord **))(*(_QWORD *)v87 + 160LL))(v87, &v92);
    CComPointer<IMsiDatabase>::operator=(&v94, v50);
    v51 = v94;
    if ( v94 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: Failed to Check AppData Microsoft Folder Path status",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v52 = v51;
LABEL_67:
      CMsiOpExecute::Message(a1, 0x1000000, v52);
LABEL_92:
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v49 + 16LL))(v49);
LABEL_93:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v87);
LABEL_94:
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v88 + 16LL))(v88);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v95);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v89);
LABEL_95:
      v36 = *(_QWORD *)v18;
      goto LABEL_96;
    }
    if ( !(_DWORD)v92 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: AppData Microsoft Folder does not exist",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v52 = PostError(1805, v49);
      goto LABEL_67;
    }
    v53 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v49 + 80LL))(v49);
    v91[0] = CreateLockFileImpersonation(v53);
    if ( v91[0] == -1 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: Failed to create lock file in AppData Microsoft Folder",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v54 = PostError(1314, v49);
      CMsiOpExecute::Message(a1, 0x1000000, v54);
      goto LABEL_91;
    }
    v90 = 0;
    v55 = (struct IMsiPath **)CComPointer<IEnumMsiRecord>::operator=(&v90);
    AppDataCachePath = CMsiOpExecute::GetAppDataCachePath((CMsiOpExecute *)a1, v55);
    CComPointer<IMsiDatabase>::operator=(&v94, AppDataCachePath);
    v57 = v94;
    if ( v94 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: Failed to Create AppData Cache Path",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      CMsiOpExecute::Message(a1, 0x1000000, v57);
      goto LABEL_90;
    }
    Folder = CMsiOpExecute::CreateFolder(a1, v90, 0, 0, v95, 1, 1, 0);
    if ( Folder != 1 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: Failed to Create AppData Cache Folder",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v90);
      CHandle::~CHandle((CHandle *)v91);
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v49 + 16LL))(v49);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v87);
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v88 + 16LL))(v88);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v95);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v89);
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v18 + 16LL))(v18);
      v5 = Folder;
      goto LABEL_135;
    }
    v59 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *))(*v90 + 56))(v90);
    v60 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v59 + 80LL))(v59);
    if ( IsJunctionFolder(v60) )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: Unexpected Junction was found in AppData Cache Folder",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v61 = PostError(1314, v59);
LABEL_88:
      CMsiOpExecute::Message(a1, 0x1000000, v61);
LABEL_89:
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v59 + 16LL))(v59);
LABEL_90:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v90);
LABEL_91:
      CHandle::~CHandle((CHandle *)v91);
      goto LABEL_92;
    }
    v62 = *v16;
    LODWORD(v93) = 0;
    v63 = (*(__int64 (__fastcall **)(__int64 *, struct IMsiRecord **))(*v62 + 160))(v62, &v93);
    CComPointer<IMsiDatabase>::operator=(&v94, v63);
    v64 = v94;
    if ( v94 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Error: Failed to Check AppData Cache Product key Path status",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v61 = v64;
      goto LABEL_88;
    }
    if ( (_DWORD)v93 )
    {
      v65 = CMsiOpExecute::CreateFolder(a1, *v16, 0, 0, v95, 1, 1, (int)v94);
      if ( v65 != 1 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Error: Failed to Apply ACL to AppData Cache Product Key Folder",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v59 + 16LL))(v59);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v90);
        CHandle::~CHandle((CHandle *)v91);
        (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v49 + 16LL))(v49);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v87);
        (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v88 + 16LL))(v88);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v95);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v89);
        (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v18 + 16LL))(v18);
        v5 = v65;
        goto LABEL_135;
      }
      v66 = (*(__int64 (__fastcall **)(__int64 *))(**v16 + 56))(*v16);
      v67 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v66 + 80LL))(v66);
      if ( IsJunctionFolder(v67) )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Error: Unexpected Junction was found in AppData Cache Product Key Folder",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        v68 = PostError(1314, v59);
        CMsiOpExecute::Message(a1, 0x1000000, v68);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
        goto LABEL_89;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    }
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v59 + 16LL))(v59);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v90);
    CHandle::~CHandle((CHandle *)v91);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v49 + 16LL))(v49);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v87);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v88 + 16LL))(v88);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v95);
  }
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v89);
LABEL_113:
  if ( (*(_BYTE *)(a1 + 864) & 0x20) != 0 )
  {
    v69 = *(HKEY *)(a1 + 624);
    if ( v69 )
    {
      RegCloseKey(v69);
      *(_QWORD *)(a1 + 624) = 0;
    }
    v70 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 688) + 80LL))(*(_QWORD *)(a1 + 688));
    v73 = MsiRegCreate64bitKey(*(HKEY *)(a1 + 664), v70, v71, v72, v83, 0x2001Fu, v85, (HKEY *)(a1 + 624), 0);
    if ( v73 )
    {
      v74 = *(const struct IMsiString **)(a1 + 688);
LABEL_118:
      v75 = PostError(1401, v74, v73);
      CComPointer<IMsiDatabase>::operator=(&v94, v75);
      v25 = v94;
      goto LABEL_119;
    }
    if ( *(_BYTE *)(a1 + 906) && (*(_BYTE *)(a1 + 864) & 8) == 0 )
    {
      v76 = *(HKEY *)(a1 + 648);
      if ( v76 )
      {
        RegCloseKey(v76);
        *(_QWORD *)(a1 + 648) = 0;
      }
      v77 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 704) + 80LL))(*(_QWORD *)(a1 + 704));
      v73 = MsiRegCreate64bitKey(*(HKEY *)(a1 + 680), v77, v78, v79, v84, 0x2001Fu, v86, (HKEY *)(a1 + 648), 0);
      if ( v73 )
      {
        v74 = *(const struct IMsiString **)(a1 + 704);
        goto LABEL_118;
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 864) & 0x180) != 0 && *(_DWORD *)(a1 + 656) )
  {
    v80 = *(HKEY *)(a1 + 632);
    if ( v80 )
      RegCloseKey(v80);
    v81 = *(HKEY *)(a1 + 640);
    if ( v81 && v81 != *(HKEY *)(a1 + 632) )
      RegCloseKey(v81);
    *(_QWORD *)(a1 + 640) = 0;
    *(_QWORD *)(a1 + 632) = 0;
  }
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v18 + 16LL))(v18);
  v5 = 1;
LABEL_135:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v94);
  return v5;
}

```

## disassembly

```asm
0x1801e7568  push    rbp
0x1801e756a  push    rbx
0x1801e756b  push    rsi
0x1801e756c  push    rdi
0x1801e756d  push    r12
0x1801e756f  push    r13
0x1801e7571  push    r14
0x1801e7573  push    r15
0x1801e7575  lea     rbp, [rsp-1Fh]
0x1801e757a  sub     rsp, 98h
0x1801e7581  test    byte ptr [rcx+360h], 8
0x1801e7588  mov     r15, rcx
0x1801e758b  mov     [rbp+57h+arg_10], 0
0x1801e7593  mov     r12d, 3
0x1801e7599  mov     byte ptr [rcx+38Bh], 0
0x1801e75a0  jz      loc_1801E782E
0x1801e75a6  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x1801e75ab  mov     r14d, eax
0x1801e75ae  cmp     eax, 0FFFFFFFFh
0x1801e75b1  jnz     short loc_1801E75DF
0x1801e75b3  mov     ecx, 5DDh; int
0x1801e75b8  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1801e75bd  mov     r8, rax
0x1801e75c0  mov     [rbp+57h+arg_0], rax
0x1801e75c4  mov     edx, 1000000h
0x1801e75c9  mov     rcx, r15
0x1801e75cc  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1801e75d1  lea     rcx, [rbp+57h+arg_0]
0x1801e75d5  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801e75da  jmp     loc_1801E8558
0x1801e75df  lea     r13, [r15+2B8h]
0x1801e75e6  mov     rcx, [r13+0]
0x1801e75ea  mov     rax, [rcx]
0x1801e75ed  mov     rax, [rax+10h]
0x1801e75f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e75f6  lea     rsi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801e75fd  mov     [r13+0], rsi
0x1801e7601  lea     rdi, [r15+2B0h]
0x1801e7608  mov     rcx, [rdi]
0x1801e760b  mov     rax, [rcx]
0x1801e760e  mov     rax, [rax+10h]
0x1801e7612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7617  mov     rcx, r15; this
0x1801e761a  mov     [rdi], rsi
0x1801e761d  call    ?GetProductKey@CMsiOpExecute@@IEAAAEBVIMsiString@@XZ; CMsiOpExecute::GetProductKey(void)
0x1801e7622  mov     rbx, rax
0x1801e7625  mov     rcx, [rax]
0x1801e7628  mov     rax, [rcx+50h]
0x1801e762c  mov     rcx, rbx
0x1801e762f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7634  lea     r9, [r15+2A0h]
0x1801e763b  mov     [rsp+0D0h+var_A8], r13
0x1801e7640  lea     r8, [r15+298h]
0x1801e7647  mov     [rsp+0D0h+var_B0], rdi
0x1801e764c  mov     rdx, rax
0x1801e764f  mov     ecx, 2
0x1801e7654  call    ?VerifyProduct@@YA_NW4iaaAppAssignment@@PEBGAEAPEAUHKEY__@@2AEAPEBVIMsiString@@3@Z; VerifyProduct(iaaAppAssignment,ushort const *,HKEY__ * &,HKEY__ * &,IMsiString const * &,IMsiString const * &)
0x1801e7659  mov     [r15+38Ah], al
0x1801e7660  mov     rcx, rbx
0x1801e7663  mov     [r15+38Bh], al
0x1801e766a  mov     rax, [rbx]
0x1801e766d  mov     rax, [rax+10h]
0x1801e7671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7676  cmp     byte ptr [r15+38Ah], 0
0x1801e767e  jnz     loc_1801E7735
0x1801e7684  mov     cl, 1; bool
0x1801e7686  call    ?IsImpersonating@@YA_N_N@Z; IsImpersonating(bool)
0x1801e768b  test    al, al
0x1801e768d  jz      short loc_1801E76CB
0x1801e768f  call    ?IsAdmin@@YA_NXZ; IsAdmin(void)
0x1801e7694  test    al, al
0x1801e7696  jnz     short loc_1801E76CB
0x1801e7698  mov     edi, 20000000h
0x1801e769d  test    [r15+360h], edi
0x1801e76a4  jz      short loc_1801E76AC
0x1801e76a6  cmp     r14d, 1
0x1801e76aa  jz      short loc_1801E76C4
0x1801e76ac  mov     r8d, 785h
0x1801e76b2  mov     edx, 1000000h
0x1801e76b7  mov     rcx, r15
0x1801e76ba  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@H@Z; CMsiOpExecute::DispatchError(imtEnum,int)
0x1801e76bf  jmp     loc_1801E8558
0x1801e76c4  lea     rdi, [r15+2B0h]
0x1801e76cb  mov     byte ptr [r15+38Ah], 1
0x1801e76d3  mov     rcx, [r13+0]
0x1801e76d7  mov     rax, [rcx]
0x1801e76da  mov     rax, [rax+10h]
0x1801e76de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e76e3  mov     [r13+0], rsi
0x1801e76e7  mov     rcx, [rdi]
0x1801e76ea  mov     rax, [rcx]
0x1801e76ed  mov     rax, [rax+10h]
0x1801e76f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e76f6  lea     r9, [r15+2A0h]
0x1801e76fd  mov     [rsp+0D0h+var_A8], r13
0x1801e7702  lea     r8, [r15+298h]
0x1801e7709  mov     [rdi], rsi
0x1801e770c  mov     edx, 2
0x1801e7711  mov     [rsp+0D0h+var_B0], rdi
0x1801e7716  xor     ecx, ecx
0x1801e7718  call    ?GetPublishKeyByUser@@YAJPEBGW4iaaAppAssignment@@AEAPEAUHKEY__@@2AEAPEBVIMsiString@@3@Z; GetPublishKeyByUser(ushort const *,iaaAppAssignment,HKEY__ * &,HKEY__ * &,IMsiString const * &,IMsiString const * &)
0x1801e771d  xor     r14d, r14d
0x1801e7720  test    eax, eax
0x1801e7722  jz      short loc_1801E7767
0x1801e7724  mov     edx, eax; int
0x1801e7726  mov     ecx, 0B71h; int
0x1801e772b  call    ?PostError@@YAPEAVIMsiRecord@@HH@Z; PostError(int,int)
0x1801e7730  jmp     loc_1801E75BD
0x1801e7735  cmp     [r15+1F4h], r12d
0x1801e773c  jnz     short loc_1801E7764
0x1801e773e  cmp     dword ptr [r15+290h], 0
0x1801e7746  jz      short loc_1801E7764
0x1801e7748  mov     edi, 20000000h
0x1801e774d  test    [r15+360h], edi
0x1801e7754  jz      loc_1801E7A54
0x1801e775a  cmp     r14d, 1
0x1801e775e  jnz     loc_1801E7A54
0x1801e7764  xor     r14d, r14d
0x1801e7767  mov     byte ptr [r15+37Ch], 1
0x1801e776f  call    ?GetMsiDirectory@@YAAEBVIMsiString@@XZ; GetMsiDirectory(void)
0x1801e7774  test    byte ptr [r15+360h], 8
0x1801e777c  lea     r13, [r15+268h]
0x1801e7783  mov     rcx, r13
0x1801e7786  mov     rbx, rax
0x1801e7789  jz      loc_1801E7B7C
0x1801e778f  mov     r14, [r15]
0x1801e7792  mov     rax, [r14]
0x1801e7795  mov     rsi, [rax+78h]
0x1801e7799  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1801e779e  mov     rdx, [rbx]
0x1801e77a1  mov     rdi, rax
0x1801e77a4  mov     rcx, rbx
0x1801e77a7  mov     rax, [rdx+50h]
0x1801e77ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e77b0  mov     rdx, rax
0x1801e77b3  mov     r8, rdi
0x1801e77b6  mov     rax, rsi
0x1801e77b9  mov     rcx, r14
0x1801e77bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e77c1  mov     rdx, rax
0x1801e77c4  lea     rcx, [rbp+57h+arg_10]
0x1801e77c8  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1801e77cd  mov     rdi, [rbp+57h+arg_10]
0x1801e77d1  xor     eax, eax
0x1801e77d3  test    rdi, rdi
0x1801e77d6  jz      loc_1801E7B02
0x1801e77dc  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x1801e77e2  jz      short loc_1801E7826
0x1801e77e4  mov     [rsp+0D0h+var_78], rax; void *
0x1801e77e9  lea     r9, aErrorFailedToC_11; "Error: Failed to create Cache Path"
0x1801e77f0  mov     [rsp+0D0h+var_80], eax; unsigned int
0x1801e77f4  lea     rax, aNull; "(NULL)"
0x1801e77fb  xor     edx, edx; unsigned __int16
0x1801e77fd  mov     [rsp+0D0h+var_88], rax; unsigned __int16 *
0x1801e7802  xor     r8d, r8d; int
0x1801e7805  mov     [rsp+0D0h+var_90], rax; unsigned __int16 *
0x1801e780a  mov     [rsp+0D0h+var_98], rax; unsigned __int16 *
0x1801e780f  mov     [rsp+0D0h+var_A0], rax; unsigned __int16 *
0x1801e7814  lea     ecx, [rdx+9]; int
0x1801e7817  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 *
0x1801e781c  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x1801e7821  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801e7826  mov     r8, rdi
0x1801e7829  jmp     loc_1801E8463
0x1801e782e  mov     edx, 1
0x1801e7833  xor     ecx, ecx
0x1801e7835  call    ?GetIntegerPolicyValue@@YAIW4iePolicyIndex@@W4Bool@@PEAW42@@Z; GetIntegerPolicyValue(iePolicyIndex,Bool,Bool *)
0x1801e783a  test    eax, eax
0x1801e783c  jz      short loc_1801E7849
0x1801e783e  mov     r8d, 78Eh
0x1801e7844  jmp     loc_1801E76B2
0x1801e7849  lea     r14, [r15+2B8h]
0x1801e7850  mov     rcx, [r14]
0x1801e7853  mov     rax, [rcx]
0x1801e7856  mov     rax, [rax+10h]
0x1801e785a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e785f  lea     rsi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801e7866  mov     [r14], rsi
0x1801e7869  lea     r13, [r15+2B0h]
0x1801e7870  mov     rcx, [r13+0]
0x1801e7874  mov     rax, [rcx]
0x1801e7877  mov     rax, [rax+10h]
0x1801e787b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7880  mov     rcx, r15; this
0x1801e7883  mov     [r13+0], rsi
0x1801e7887  call    ?GetProductKey@CMsiOpExecute@@IEAAAEBVIMsiString@@XZ; CMsiOpExecute::GetProductKey(void)
0x1801e788c  mov     rbx, rax
0x1801e788f  mov     rcx, [rax]
0x1801e7892  mov     rax, [rcx+50h]
0x1801e7896  mov     rcx, rbx
0x1801e7899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e789e  lea     r9, [r15+2A0h]
0x1801e78a5  mov     [rsp+0D0h+var_A8], r14
0x1801e78aa  lea     r8, [r15+298h]
0x1801e78b1  mov     [rsp+0D0h+var_B0], r13
0x1801e78b6  mov     rdx, rax
0x1801e78b9  xor     ecx, ecx
0x1801e78bb  call    ?VerifyProduct@@YA_NW4iaaAppAssignment@@PEBGAEAPEAUHKEY__@@2AEAPEBVIMsiString@@3@Z; VerifyProduct(iaaAppAssignment,ushort const *,HKEY__ * &,HKEY__ * &,IMsiString const * &,IMsiString const * &)
0x1801e78c0  mov     [r15+38Ah], al
0x1801e78c7  mov     rcx, rbx
0x1801e78ca  mov     [r15+38Bh], al
0x1801e78d1  mov     rax, [rbx]
0x1801e78d4  mov     rax, [rax+10h]
0x1801e78d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e78dd  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x1801e78e2  cmp     byte ptr [r15+38Ah], 0
0x1801e78ea  mov     edi, 20000000h
0x1801e78ef  mov     dword ptr [rbp+57h+arg_0], eax
0x1801e78f2  jnz     loc_1801E7A24
0x1801e78f8  cmp     eax, 0FFFFFFFFh
0x1801e78fb  jz      loc_1801E75B3
0x1801e7901  test    [r15+360h], edi
0x1801e7908  jz      short loc_1801E7970
0x1801e790a  cmp     eax, 1
0x1801e790d  jnz     short loc_1801E7970
0x1801e790f  mov     [r15+38Ah], al
0x1801e7916  mov     rcx, [r14]
0x1801e7919  mov     rax, [rcx]
0x1801e791c  mov     rax, [rax+10h]
0x1801e7920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7925  mov     [r14], rsi
0x1801e7928  mov     rcx, [r13+0]
0x1801e792c  mov     rax, [rcx]
0x1801e792f  mov     rax, [rax+10h]
0x1801e7933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7938  xor     edx, edx
0x1801e793a  mov     [rsp+0D0h+var_A8], r14
0x1801e793f  lea     r8, [r15+298h]
0x1801e7946  lea     r9, [r15+2A0h]
0x1801e794d  mov     [rsp+0D0h+var_B0], r13
0x1801e7952  xor     ecx, ecx
0x1801e7954  mov     [r13+0], rsi
0x1801e7958  call    ?GetPublishKeyByUser@@YAJPEBGW4iaaAppAssignment@@AEAPEAUHKEY__@@2AEAPEBVIMsiString@@3@Z; GetPublishKeyByUser(ushort const *,iaaAppAssignment,HKEY__ * &,HKEY__ * &,IMsiString const * &,IMsiString const * &)
0x1801e795d  xor     r14d, r14d
0x1801e7960  test    eax, eax
0x1801e7962  jnz     loc_1801E7724
0x1801e7968  mov     eax, dword ptr [rbp+57h+arg_0]
0x1801e796b  jmp     loc_1801E7A27
0x1801e7970  mov     rcx, [r14]
0x1801e7973  mov     rax, [rcx]
0x1801e7976  mov     rax, [rax+10h]
0x1801e797a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e797f  mov     [r14], rsi
0x1801e7982  mov     rcx, [r13+0]
0x1801e7986  mov     rax, [rcx]
0x1801e7989  mov     rax, [rax+10h]
0x1801e798d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7992  mov     rcx, r15; this
0x1801e7995  mov     [r13+0], rsi
0x1801e7999  call    ?GetProductKey@CMsiOpExecute@@IEAAAEBVIMsiString@@XZ; CMsiOpExecute::GetProductKey(void)
0x1801e799e  mov     rbx, rax
0x1801e79a1  mov     rcx, [rax]
0x1801e79a4  mov     rax, [rcx+50h]
0x1801e79a8  mov     rcx, rbx
0x1801e79ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e79b0  lea     r9, [r15+2A0h]
0x1801e79b7  mov     [rsp+0D0h+var_A8], r14
0x1801e79bc  lea     r8, [r15+298h]
0x1801e79c3  mov     [rsp+0D0h+var_B0], r13
0x1801e79c8  mov     rdx, rax
0x1801e79cb  mov     ecx, 1
0x1801e79d0  call    ?VerifyProduct@@YA_NW4iaaAppAssignment@@PEBGAEAPEAUHKEY__@@2AEAPEBVIMsiString@@3@Z; VerifyProduct(iaaAppAssignment,ushort const *,HKEY__ * &,HKEY__ * &,IMsiString const * &,IMsiString const * &)
0x1801e79d5  mov     [r15+38Bh], al
0x1801e79dc  mov     rcx, rbx
0x1801e79df  mov     rax, [rbx]
0x1801e79e2  mov     rax, [rax+10h]
0x1801e79e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e79eb  cmp     byte ptr [r15+38Bh], 0
0x1801e79f3  jnz     short loc_1801E7A21
0x1801e79f5  mov     rcx, [r14]
0x1801e79f8  mov     rax, [rcx]
0x1801e79fb  mov     rax, [rax+10h]
0x1801e79ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7a04  mov     [r14], rsi
0x1801e7a07  mov     rcx, [r13+0]
0x1801e7a0b  mov     rax, [rcx]
0x1801e7a0e  mov     rax, [rax+10h]
0x1801e7a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7a17  mov     edx, 1
0x1801e7a1c  jmp     loc_1801E793A
0x1801e7a21  mov     eax, dword ptr [rbp+57h+arg_0]
0x1801e7a24  xor     r14d, r14d
0x1801e7a27  cmp     [r15+38Ah], r14b
0x1801e7a2e  jz      loc_1801E7767
0x1801e7a34  cmp     [r15+1F4h], r12d
0x1801e7a3b  jnz     short loc_1801E7A5F
0x1801e7a3d  cmp     [r15+290h], r14d
0x1801e7a44  jz      short loc_1801E7A5F
0x1801e7a46  test    [r15+360h], edi
0x1801e7a4d  jz      short loc_1801E7A54
0x1801e7a4f  cmp     eax, 1
0x1801e7a52  jz      short loc_1801E7A5F
0x1801e7a54  mov     r8d, 799h
0x1801e7a5a  jmp     loc_1801E76B2
0x1801e7a5f  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801e7a66  mov     rcx, rsi
0x1801e7a69  mov     rax, [rax+10h]
0x1801e7a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7a72  lea     rbx, [r15+2C0h]
0x1801e7a79  mov     [rbp+57h+arg_0], rsi
  ... truncated ...
```
