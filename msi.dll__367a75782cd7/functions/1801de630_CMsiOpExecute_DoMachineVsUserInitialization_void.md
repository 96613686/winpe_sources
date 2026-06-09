# CMsiOpExecute::DoMachineVsUserInitialization(void)

- ea: `0x1801de630`
- end: `0x1801df628`
- name: `?DoMachineVsUserInitialization@CMsiOpExecute@@IEAA?AW4iesEnum@@XZ`
- size: `4088`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801fa8f0`

## callees

- `0x180012604`
- `0x180012620`
- `0x180024f9c`
- `0x180025a18`
- `0x180027b54`
- `0x18002b35c`
- `0x180035a8c`
- `0x18004295c`
- `0x180056144`
- `0x180064a78`
- `0x180066074`
- `0x180071ab0`
- `0x180076e28`
- `0x18007ed2c`
- `0x1800861d4`
- `0x18008f3e8`
- `0x1800a55e0`
- `0x1800cb888`
- `0x180129200`
- `0x18013a830`
- `0x180146548`
- `0x18014bd74`
- `0x18016d7a4`
- `0x1801de630`
- `0x1801dfc20`
- `0x1801dfc8c`
- `0x1801dfe48`
- `0x1801f1dc8`
- `0x18021630c`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1801df4bf`
- `ADVAPI32!RegCloseKey` at `0x1801df559`
- `ADVAPI32!RegCloseKey` at `0x1801df5c4`
- `ADVAPI32!RegCloseKey` at `0x1801df5df`
- `ADVAPI32!RegCloseKey` at `0x1801df4bf`
- `ADVAPI32!RegCloseKey` at `0x1801df559`
- `ADVAPI32!RegCloseKey` at `0x1801df5c4`
- `ADVAPI32!RegCloseKey` at `0x1801df5df`

## string_xrefs

- `0x1801de8b1`: `Error: Failed to create Cache Path`
- `0x1801dec27`: `Error: Failed to create Cache Path with Product key`
- `0x1801dec7e`: `Error: Failed to Create AppData Cache Path with Product ID`
- `0x1801ded2a`: `Error: Failed to Generate Cache Security descriptor`
- `0x1801deda8`: `Error: Failed to Create AppData Microsoft Path`
- `0x1801dee4c`: `Error: Failed to Check AppData Microsoft Folder Path status`
- `0x1801def32`: `Error: Failed to create lock file in AppData Microsoft Folder`
- `0x1801defcd`: `Error: Failed to Create AppData Cache Path`
- `0x1801df066`: `Error: Failed to Create AppData Cache Folder`
- `0x1801df147`: `Error: Unexpected Junction was found in AppData Cache Folder`
- `0x1801df244`: `Error: Failed to Check AppData Cache Product key Path status`
- `0x1801df2db`: `Error: Failed to Apply ACL to AppData Cache Product Key Folder`
- `0x1801df3d2`: `Error: Unexpected Junction was found in AppData Cache Product Key Folder`

## pseudocode

```c
__int64 __fastcall CMsiOpExecute::DoMachineVsUserInitialization(__int64 a1)
{
  bool v1; // zf
  unsigned int v3; // r12d
  int v4; // r14d
  struct IMsiRecord *v5; // rax
  _QWORD *v6; // r13
  _QWORD *v7; // rdi
  const struct IMsiString *ProductKey; // rbx
  __int64 v9; // rax
  char v10; // al
  __int64 v11; // r8
  int PublishKeyByUser; // eax
  const struct IMsiString *MsiDirectory; // rax
  __int64 **v14; // r13
  __int64 v15; // rcx
  const struct IMsiString *v16; // rbx
  __int64 v17; // r14
  __int64 (__fastcall *v18)(__int64, __int64, __int64); // rsi
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // r8
  _QWORD *v24; // r14
  _QWORD *v25; // r13
  const struct IMsiString *v26; // rbx
  __int64 v27; // rax
  char v28; // al
  int v29; // eax
  int v30; // edx
  const struct IMsiString *v31; // rbx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  __int64 *v35; // rsi
  __int64 (__fastcall *v36)(__int64 *, const struct IMsiString *); // rdi
  const struct IMsiString *v37; // r14
  __int64 v38; // rax
  struct IMsiPath **v39; // rax
  struct IMsiRecord *AppDataCachePathWithProductKey; // rax
  BOOL v41; // edi
  int v42; // eax
  struct IMsiStream **v43; // rax
  struct IMsiPath **v44; // rax
  struct IMsiRecord *AppDataMicrosoftPath; // rax
  __int64 v46; // rdi
  const struct IMsiString *v47; // rdi
  __int64 v48; // rax
  __int64 v49; // rsi
  struct IMsiRecord *v50; // r8
  const WCHAR *v51; // rax
  struct IMsiRecord *v52; // rax
  struct IMsiPath **v53; // rax
  struct IMsiRecord *AppDataCachePath; // rax
  __int64 v55; // rsi
  unsigned int Folder; // esi
  const struct IMsiString *v57; // rsi
  const unsigned __int16 *v58; // rax
  struct IMsiRecord *v59; // r8
  __int64 *v60; // rcx
  __int64 v61; // rax
  __int64 v62; // r14
  unsigned int v63; // r14d
  __int64 v64; // r14
  const unsigned __int16 *v65; // rax
  struct IMsiRecord *v66; // rax
  HKEY v67; // rcx
  const unsigned __int16 *v68; // rax
  unsigned int v69; // r8d
  unsigned __int16 *v70; // r9
  int v71; // eax
  const struct IMsiString *v72; // rdx
  struct IMsiRecord *v73; // rax
  HKEY v74; // rcx
  const unsigned __int16 *v75; // rax
  unsigned int v76; // r8d
  unsigned __int16 *v77; // r9
  HKEY v78; // rcx
  HKEY v79; // rcx
  unsigned int v81; // [rsp+20h] [rbp-59h]
  unsigned int v82; // [rsp+20h] [rbp-59h]
  struct _SECURITY_ATTRIBUTES *v83; // [rsp+30h] [rbp-49h]
  struct _SECURITY_ATTRIBUTES *v84; // [rsp+30h] [rbp-49h]
  __int64 v85; // [rsp+60h] [rbp-19h] BYREF
  struct IMsiString *v86; // [rsp+68h] [rbp-11h] BYREF
  __int64 v87; // [rsp+70h] [rbp-9h] BYREF
  __int64 *v88; // [rsp+78h] [rbp-1h] BYREF
  _QWORD v89[10]; // [rsp+80h] [rbp+7h] BYREF
  struct IMsiRecord *v90; // [rsp+E0h] [rbp+67h] BYREF
  struct IMsiRecord *v91; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v92; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v93; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = (*(_BYTE *)(a1 + 864) & 8) == 0;
  v92 = 0;
  v3 = 3;
  *(_BYTE *)(a1 + 907) = 0;
  if ( !v1 )
  {
    v4 = RunningAsLocalSystem();
    if ( v4 == -1 )
    {
LABEL_3:
      v5 = PostError(1501);
LABEL_4:
      v90 = v5;
      CMsiOpExecute::Message(a1, 0x1000000, v5);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v90);
      goto LABEL_135;
    }
    v6 = (_QWORD *)(a1 + 696);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 696) + 16LL))(*(_QWORD *)(a1 + 696));
    *(_QWORD *)(a1 + 696) = &MsiString::s_NullString;
    v7 = (_QWORD *)(a1 + 688);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 688) + 16LL))(*(_QWORD *)(a1 + 688));
    *(_QWORD *)(a1 + 688) = &MsiString::s_NullString;
    ProductKey = CMsiOpExecute::GetProductKey((CMsiOpExecute *)a1);
    v9 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)ProductKey + 80LL))(ProductKey);
    v81 = a1 + 688;
    v10 = VerifyProduct(2, v9, a1 + 664, a1 + 672);
    *(_BYTE *)(a1 + 906) = v10;
    *(_BYTE *)(a1 + 907) = v10;
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)ProductKey + 16LL))(ProductKey);
    if ( !*(_BYTE *)(a1 + 906) )
    {
      if ( IsImpersonating(1) && !IsAdmin() )
      {
        if ( (*(_DWORD *)(a1 + 864) & 0x20000000) == 0 || v4 != 1 )
        {
          v11 = 1925;
LABEL_11:
          CMsiOpExecute::DispatchError(a1, 0x1000000, v11);
          goto LABEL_135;
        }
        v7 = (_QWORD *)(a1 + 688);
      }
      *(_BYTE *)(a1 + 906) = 1;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 16LL))(*v6);
      *v6 = &MsiString::s_NullString;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
      *v7 = &MsiString::s_NullString;
      PublishKeyByUser = GetPublishKeyByUser(0, 2, (_QWORD *)(a1 + 664), (_QWORD *)(a1 + 672), v7, (_QWORD *)(a1 + 696));
      if ( PublishKeyByUser )
      {
LABEL_14:
        v5 = PostError(2929, PublishKeyByUser);
        goto LABEL_4;
      }
      goto LABEL_19;
    }
    if ( *(_DWORD *)(a1 + 500) != 3 || !*(_DWORD *)(a1 + 656) || (*(_DWORD *)(a1 + 864) & 0x20000000) != 0 && v4 == 1 )
      goto LABEL_19;
LABEL_41:
    v11 = 1945;
    goto LABEL_11;
  }
  if ( (unsigned int)GetIntegerPolicyValue(0) )
  {
    v11 = 1934;
    goto LABEL_11;
  }
  v24 = (_QWORD *)(a1 + 696);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 696) + 16LL))(*(_QWORD *)(a1 + 696));
  *(_QWORD *)(a1 + 696) = &MsiString::s_NullString;
  v25 = (_QWORD *)(a1 + 688);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 688) + 16LL))(*(_QWORD *)(a1 + 688));
  *(_QWORD *)(a1 + 688) = &MsiString::s_NullString;
  v26 = CMsiOpExecute::GetProductKey((CMsiOpExecute *)a1);
  v27 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v26 + 80LL))(v26);
  v81 = a1 + 688;
  v28 = VerifyProduct(0, v27, a1 + 664, a1 + 672);
  *(_BYTE *)(a1 + 906) = v28;
  *(_BYTE *)(a1 + 907) = v28;
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v26 + 16LL))(v26);
  v29 = RunningAsLocalSystem();
  v1 = *(_BYTE *)(a1 + 906) == 0;
  LODWORD(v90) = v29;
  if ( v1 )
  {
    if ( v29 == -1 )
      goto LABEL_3;
    if ( (*(_DWORD *)(a1 + 864) & 0x20000000) != 0 && v29 == 1 )
    {
      *(_BYTE *)(a1 + 906) = 1;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 16LL))(*v24);
      *v24 = &MsiString::s_NullString;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 16LL))(*v25);
      v30 = 0;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 16LL))(*v24);
      *v24 = &MsiString::s_NullString;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 16LL))(*v25);
      *v25 = &MsiString::s_NullString;
      v31 = CMsiOpExecute::GetProductKey((CMsiOpExecute *)a1);
      v32 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v31 + 80LL))(v31);
      v81 = a1 + 688;
      *(_BYTE *)(a1 + 907) = VerifyProduct(1, v32, a1 + 664, a1 + 672);
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v31 + 16LL))(v31);
      if ( *(_BYTE *)(a1 + 907) )
      {
        v29 = (int)v90;
        goto LABEL_36;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 16LL))(*v24);
      *v24 = &MsiString::s_NullString;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 16LL))(*v25);
      v30 = 1;
    }
    *v25 = &MsiString::s_NullString;
    PublishKeyByUser = GetPublishKeyByUser(
                         0,
                         v30,
                         (_QWORD *)(a1 + 664),
                         (_QWORD *)(a1 + 672),
                         (_QWORD *)(a1 + 688),
                         (_QWORD *)(a1 + 696));
    if ( PublishKeyByUser )
      goto LABEL_14;
    v29 = (int)v90;
  }
LABEL_36:
  if ( !*(_BYTE *)(a1 + 906) )
    goto LABEL_19;
  if ( *(_DWORD *)(a1 + 500) == 3 && *(_DWORD *)(a1 + 656) && ((*(_DWORD *)(a1 + 864) & 0x20000000) == 0 || v29 != 1) )
    goto LABEL_41;
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v90 = (struct IMsiRecord *)&MsiString::s_NullString;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 704) + 16LL))(*(_QWORD *)(a1 + 704));
  *(_QWORD *)(a1 + 704) = &MsiString::s_NullString;
  v33 = GetPublishKeyByUser(0, 1, (_QWORD *)(a1 + 680), &v91, (_QWORD *)(a1 + 704), &v90);
  if ( v33 )
  {
    v91 = PostError(2929, v33);
    CMsiOpExecute::Message(a1, 0x1000000, v91);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v91);
    v34 = *(_QWORD *)v90;
LABEL_96:
    (*(void (**)(void))(v34 + 16))();
    goto LABEL_135;
  }
  (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v90 + 16LL))(v90);
LABEL_19:
  *(_BYTE *)(a1 + 892) = 1;
  MsiDirectory = GetMsiDirectory();
  v14 = (__int64 **)(a1 + 616);
  v15 = a1 + 616;
  v16 = MsiDirectory;
  if ( (*(_BYTE *)(a1 + 864) & 8) != 0 )
  {
    v17 = *(_QWORD *)a1;
    v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(**(_QWORD **)a1 + 120LL);
    v19 = CComPointer<IEnumMsiRecord>::operator=(v15);
    v20 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v16 + 80LL))(v16);
    v21 = v18(v17, v20, v19);
    CComPointer<IMsiDatabase>::operator=(&v92, v21);
    v22 = v92;
    if ( v92 )
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
      v23 = v22;
LABEL_119:
      CMsiOpExecute::Message(a1, 0x1000000, v23);
      goto LABEL_95;
    }
    v35 = *v14;
    v36 = *(__int64 (__fastcall **)(__int64 *, const struct IMsiString *))(**v14 + 104);
    v37 = CMsiOpExecute::GetProductKey((CMsiOpExecute *)a1);
    v38 = v36(v35, v37);
    CComPointer<IMsiDatabase>::operator=(&v92, v38);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v37 + 16LL))(v37);
    v22 = v92;
    if ( v92 )
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
  v39 = (struct IMsiPath **)CComPointer<IEnumMsiRecord>::operator=(v15);
  AppDataCachePathWithProductKey = CMsiOpExecute::GetAppDataCachePathWithProductKey((CMsiOpExecute *)a1, v39, 0);
  CComPointer<IMsiDatabase>::operator=(&v92, AppDataCachePathWithProductKey);
  v22 = v92;
  if ( v92 )
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
  v41 = 1;
  v42 = RunningAsLocalSystem();
  if ( g_scServerContext != 2 )
    v41 = v42 != 0;
  v87 = (*(__int64 (__fastcall **)(__int64 *))(**v14 + 72))(*v14);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v87 + 56LL))(v87) != 4 && v41 )
  {
    v93 = 0;
    MsiString::MsiString((MsiString *)&v86, L"O:BAG:SYD:PAI(A;OICI;0x1200a9;;;WD)(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)");
    v43 = (struct IMsiStream **)CComPointer<IEnumMsiRecord>::operator=(&v93);
    if ( !GenerateSDFromSDDL(v86, v43) )
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
    v85 = 0;
    v44 = (struct IMsiPath **)CComPointer<IEnumMsiRecord>::operator=(&v85);
    AppDataMicrosoftPath = CMsiOpExecute::GetAppDataMicrosoftPath((CMsiOpExecute *)a1, v44);
    CComPointer<IMsiDatabase>::operator=(&v92, AppDataMicrosoftPath);
    v46 = v92;
    if ( v92 )
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
      CMsiOpExecute::Message(a1, 0x1000000, v46);
      goto LABEL_93;
    }
    v47 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v85 + 56LL))(v85);
    LODWORD(v90) = 0;
    v48 = (*(__int64 (__fastcall **)(__int64, struct IMsiRecord **))(*(_QWORD *)v85 + 160LL))(v85, &v90);
    CComPointer<IMsiDatabase>::operator=(&v92, v48);
    v49 = v92;
    if ( v92 )
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
      v50 = (struct IMsiRecord *)v49;
LABEL_67:
      CMsiOpExecute::Message(a1, 0x1000000, v50);
LABEL_92:
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v47 + 16LL))(v47);
LABEL_93:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v85);
LABEL_94:
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v86 + 16LL))(v86);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v93);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v87);
LABEL_95:
      v34 = *(_QWORD *)v16;
      goto LABEL_96;
    }
    if ( !(_DWORD)v90 )
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
      v50 = PostError(1805, v47);
      goto LABEL_67;
    }
    v51 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v47 + 80LL))(v47);
    v89[0] = CreateLockFileImpersonation(v51);
    if ( v89[0] == -1 )
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
      v52 = PostError(1314, v47);
      CMsiOpExecute::Message(a1, 0x1000000, v52);
      goto LABEL_91;
    }
    v88 = 0;
    v53 = (struct IMsiPath **)CComPointer<IEnumMsiRecord>::operator=(&v88);
    AppDataCachePath = CMsiOpExecute::GetAppDataCachePath((CMsiOpExecute *)a1, v53);
    CComPointer<IMsiDatabase>::operator=(&v92, AppDataCachePath);
    v55 = v92;
    if ( v92 )
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
      CMsiOpExecute::Message(a1, 0x1000000, v55);
      goto LABEL_90;
    }
    Folder = CMsiOpExecute::CreateFolder(a1, v88, 0, 0, v93, 1, 1, 0);
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
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v88);
      CHandle::~CHandle((CHandle *)v89);
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v47 + 16LL))(v47);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v85);
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v86 + 16LL))(v86);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v93);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v87);
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v16 + 16LL))(v16);
      v3 = Folder;
      goto LABEL_135;
    }
    v57 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *))(*v88 + 56))(v88);
    v58 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v57 + 80LL))(v57);
    if ( IsJunctionFolder(v58) )
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
      v59 = PostError(1314, v57);
LABEL_88:
      CMsiOpExecute::Message(a1, 0x1000000, v59);
LABEL_89:
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v57 + 16LL))(v57);
LABEL_90:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v88);
LABEL_91:
      CHandle::~CHandle((CHandle *)v89);
      goto LABEL_92;
    }
    v60 = *v14;
    LODWORD(v91) = 0;
    v61 = (*(__int64 (__fastcall **)(__int64 *, struct IMsiRecord **))(*v60 + 160))(v60, &v91);
    CComPointer<IMsiDatabase>::operator=(&v92, v61);
    v62 = v92;
    if ( v92 )
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
      v59 = (struct IMsiRecord *)v62;
      goto LABEL_88;
    }
    if ( (_DWORD)v91 )
    {
      v63 = CMsiOpExecute::CreateFolder(a1, *v14, 0, 0, v93, 1, 1, v92);
      if ( v63 != 1 )
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
        (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v57 + 16LL))(v57);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v88);
        CHandle::~CHandle((CHandle *)v89);
        (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v47 + 16LL))(v47);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v85);
        (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v86 + 16LL))(v86);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v93);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v87);
        (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v16 + 16LL))(v16);
        v3 = v63;
        goto LABEL_135;
      }
      v64 = (*(__int64 (__fastcall **)(__int64 *))(**v14 + 56))(*v14);
      v65 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 80LL))(v64);
      if ( IsJunctionFolder(v65) )
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
        v66 = PostError(1314, v57);
        CMsiOpExecute::Message(a1, 0x1000000, v66);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
        goto LABEL_89;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v57 + 16LL))(v57);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v88);
    CHandle::~CHandle((CHandle *)v89);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v47 + 16LL))(v47);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v85);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v86 + 16LL))(v86);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v93);
  }
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v87);
LABEL_113:
  if ( (*(_BYTE *)(a1 + 864) & 0x20) != 0 )
  {
    v67 = *(HKEY *)(a1 + 624);
    if ( v67 )
    {
      RegCloseKey(v67);
      *(_QWORD *)(a1 + 624) = 0;
    }
    v68 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 688) + 80LL))(*(_QWORD *)(a1 + 688));
    v71 = MsiRegCreate64bitKey(*(HKEY *)(a1 + 664), v68, v69, v70, v81, 0x2001Fu, v83, (HKEY *)(a1 + 624), 0);
    if ( v71 )
    {
      v72 = *(const struct IMsiString **)(a1 + 688);
LABEL_118:
      v73 = PostError(1401, v72, v71);
      CComPointer<IMsiDatabase>::operator=(&v92, v73);
      v23 = v92;
      goto LABEL_119;
    }
    if ( *(_BYTE *)(a1 + 906) && (*(_BYTE *)(a1 + 864) & 8) == 0 )
    {
      v74 = *(HKEY *)(a1 + 648);
      if ( v74 )
      {
        RegCloseKey(v74);
        *(_QWORD *)(a1 + 648) = 0;
      }
      v75 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 704) + 80LL))(*(_QWORD *)(a1 + 704));
      v71 = MsiRegCreate64bitKey(*(HKEY *)(a1 + 680), v75, v76, v77, v82, 0x2001Fu, v84, (HKEY *)(a1 + 648), 0);
      if ( v71 )
      {
        v72 = *(const struct IMsiString **)(a1 + 704);
        goto LABEL_118;
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 864) & 0x180) != 0 && *(_DWORD *)(a1 + 656) )
  {
    v78 = *(HKEY *)(a1 + 632);
    if ( v78 )
      RegCloseKey(v78);
    v79 = *(HKEY *)(a1 + 640);
    if ( v79 && v79 != *(HKEY *)(a1 + 632) )
      RegCloseKey(v79);
    *(_QWORD *)(a1 + 640) = 0;
    *(_QWORD *)(a1 + 632) = 0;
  }
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v16 + 16LL))(v16);
  v3 = 1;
LABEL_135:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v92);
  return v3;
}

```

## disassembly

```asm
0x1801de630  push    rbp
0x1801de632  push    rbx
0x1801de633  push    rsi
0x1801de634  push    rdi
0x1801de635  push    r12
0x1801de637  push    r13
0x1801de639  push    r14
0x1801de63b  push    r15
0x1801de63d  lea     rbp, [rsp-1Fh]
0x1801de642  sub     rsp, 98h
0x1801de649  test    byte ptr [rcx+360h], 8
0x1801de650  mov     r15, rcx
0x1801de653  mov     [rbp+57h+arg_10], 0
0x1801de65b  mov     r12d, 3
0x1801de661  mov     byte ptr [rcx+38Bh], 0
0x1801de668  jz      loc_1801DE8F6
0x1801de66e  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x1801de673  mov     r14d, eax
0x1801de676  cmp     eax, 0FFFFFFFFh
0x1801de679  jnz     short loc_1801DE6A7
0x1801de67b  mov     ecx, 5DDh; int
0x1801de680  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1801de685  mov     r8, rax
0x1801de688  mov     [rbp+57h+arg_0], rax
0x1801de68c  mov     edx, 1000000h
0x1801de691  mov     rcx, r15
0x1801de694  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1801de699  lea     rcx, [rbp+57h+arg_0]
0x1801de69d  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1801de6a2  jmp     loc_1801DF608
0x1801de6a7  lea     r13, [r15+2B8h]
0x1801de6ae  mov     rcx, [r13+0]
0x1801de6b2  mov     rax, [rcx]
0x1801de6b5  mov     rax, [rax+10h]
0x1801de6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de6be  lea     rsi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801de6c5  mov     [r13+0], rsi
0x1801de6c9  lea     rdi, [r15+2B0h]
0x1801de6d0  mov     rcx, [rdi]
0x1801de6d3  mov     rax, [rcx]
0x1801de6d6  mov     rax, [rax+10h]
0x1801de6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de6df  mov     rcx, r15; this
0x1801de6e2  mov     [rdi], rsi
0x1801de6e5  call    ?GetProductKey@CMsiOpExecute@@IEAAAEBVIMsiString@@XZ; CMsiOpExecute::GetProductKey(void)
0x1801de6ea  mov     rbx, rax
0x1801de6ed  mov     rcx, [rax]
0x1801de6f0  mov     rax, [rcx+50h]
0x1801de6f4  mov     rcx, rbx
0x1801de6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de6fc  lea     r9, [r15+2A0h]
0x1801de703  mov     [rsp+0D0h+var_A8], r13
0x1801de708  lea     r8, [r15+298h]
0x1801de70f  mov     [rsp+0D0h+var_B0], rdi
0x1801de714  mov     rdx, rax
0x1801de717  mov     ecx, 2
0x1801de71c  call    ?VerifyProduct@@YA_NW4iaaAppAssignment@@PEBGAEAPEAUHKEY__@@2AEAPEBVIMsiString@@3@Z; VerifyProduct(iaaAppAssignment,ushort const *,HKEY__ * &,HKEY__ * &,IMsiString const * &,IMsiString const * &)
0x1801de721  mov     [r15+38Ah], al
0x1801de728  mov     rcx, rbx
0x1801de72b  mov     [r15+38Bh], al
0x1801de732  mov     rax, [rbx]
0x1801de735  mov     rax, [rax+10h]
0x1801de739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de73e  cmp     byte ptr [r15+38Ah], 0
0x1801de746  jnz     loc_1801DE7FD
0x1801de74c  mov     cl, 1; bool
0x1801de74e  call    ?IsImpersonating@@YA_N_N@Z; IsImpersonating(bool)
0x1801de753  test    al, al
0x1801de755  jz      short loc_1801DE793
0x1801de757  call    ?IsAdmin@@YA_NXZ; IsAdmin(void)
0x1801de75c  test    al, al
0x1801de75e  jnz     short loc_1801DE793
0x1801de760  mov     edi, 20000000h
0x1801de765  test    [r15+360h], edi
0x1801de76c  jz      short loc_1801DE774
0x1801de76e  cmp     r14d, 1
0x1801de772  jz      short loc_1801DE78C
0x1801de774  mov     r8d, 785h
0x1801de77a  mov     edx, 1000000h
0x1801de77f  mov     rcx, r15
0x1801de782  call    ?DispatchError@CMsiOpExecute@@QEAA?AW4imsEnum@@W4imtEnum@@H@Z; CMsiOpExecute::DispatchError(imtEnum,int)
0x1801de787  jmp     loc_1801DF608
0x1801de78c  lea     rdi, [r15+2B0h]
0x1801de793  mov     byte ptr [r15+38Ah], 1
0x1801de79b  mov     rcx, [r13+0]
0x1801de79f  mov     rax, [rcx]
0x1801de7a2  mov     rax, [rax+10h]
0x1801de7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de7ab  mov     [r13+0], rsi
0x1801de7af  mov     rcx, [rdi]
0x1801de7b2  mov     rax, [rcx]
0x1801de7b5  mov     rax, [rax+10h]
0x1801de7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de7be  lea     r9, [r15+2A0h]
0x1801de7c5  mov     [rsp+0D0h+var_A8], r13
0x1801de7ca  lea     r8, [r15+298h]
0x1801de7d1  mov     [rdi], rsi
0x1801de7d4  mov     edx, 2
0x1801de7d9  mov     [rsp+0D0h+var_B0], rdi
0x1801de7de  xor     ecx, ecx
0x1801de7e0  call    ?GetPublishKeyByUser@@YAJPEBGW4iaaAppAssignment@@AEAPEAUHKEY__@@2AEAPEBVIMsiString@@3@Z; GetPublishKeyByUser(ushort const *,iaaAppAssignment,HKEY__ * &,HKEY__ * &,IMsiString const * &,IMsiString const * &)
0x1801de7e5  xor     r14d, r14d
0x1801de7e8  test    eax, eax
0x1801de7ea  jz      short loc_1801DE82F
0x1801de7ec  mov     edx, eax; int
0x1801de7ee  mov     ecx, 0B71h; int
0x1801de7f3  call    ?PostError@@YAPEAVIMsiRecord@@HH@Z; PostError(int,int)
0x1801de7f8  jmp     loc_1801DE685
0x1801de7fd  cmp     [r15+1F4h], r12d
0x1801de804  jnz     short loc_1801DE82C
0x1801de806  cmp     dword ptr [r15+290h], 0
0x1801de80e  jz      short loc_1801DE82C
0x1801de810  mov     edi, 20000000h
0x1801de815  test    [r15+360h], edi
0x1801de81c  jz      loc_1801DEB1C
0x1801de822  cmp     r14d, 1
0x1801de826  jnz     loc_1801DEB1C
0x1801de82c  xor     r14d, r14d
0x1801de82f  mov     byte ptr [r15+37Ch], 1
0x1801de837  call    ?GetMsiDirectory@@YAAEBVIMsiString@@XZ; GetMsiDirectory(void)
0x1801de83c  test    byte ptr [r15+360h], 8
0x1801de844  lea     r13, [r15+268h]
0x1801de84b  mov     rcx, r13
0x1801de84e  mov     rbx, rax
0x1801de851  jz      loc_1801DEC44
0x1801de857  mov     r14, [r15]
0x1801de85a  mov     rax, [r14]
0x1801de85d  mov     rsi, [rax+78h]
0x1801de861  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1801de866  mov     rdx, [rbx]
0x1801de869  mov     rdi, rax
0x1801de86c  mov     rcx, rbx
0x1801de86f  mov     rax, [rdx+50h]
0x1801de873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de878  mov     rdx, rax
0x1801de87b  mov     r8, rdi
0x1801de87e  mov     rax, rsi
0x1801de881  mov     rcx, r14
0x1801de884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de889  mov     rdx, rax
0x1801de88c  lea     rcx, [rbp+57h+arg_10]
0x1801de890  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1801de895  mov     rdi, [rbp+57h+arg_10]
0x1801de899  xor     eax, eax
0x1801de89b  test    rdi, rdi
0x1801de89e  jz      loc_1801DEBCA
0x1801de8a4  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x1801de8aa  jz      short loc_1801DE8EE
0x1801de8ac  mov     [rsp+0D0h+var_78], rax; void *
0x1801de8b1  lea     r9, aErrorFailedToC_11; "Error: Failed to create Cache Path"
0x1801de8b8  mov     [rsp+0D0h+var_80], eax; unsigned int
0x1801de8bc  lea     rax, aNull; "(NULL)"
0x1801de8c3  xor     edx, edx; unsigned __int16
0x1801de8c5  mov     [rsp+0D0h+var_88], rax; unsigned __int16 *
0x1801de8ca  xor     r8d, r8d; int
0x1801de8cd  mov     [rsp+0D0h+var_90], rax; unsigned __int16 *
0x1801de8d2  mov     [rsp+0D0h+var_98], rax; unsigned __int16 *
0x1801de8d7  mov     [rsp+0D0h+var_A0], rax; unsigned __int16 *
0x1801de8dc  lea     ecx, [rdx+9]; int
0x1801de8df  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 *
0x1801de8e4  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x1801de8e9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801de8ee  mov     r8, rdi
0x1801de8f1  jmp     loc_1801DF525
0x1801de8f6  mov     edx, 1
0x1801de8fb  xor     ecx, ecx
0x1801de8fd  call    ?GetIntegerPolicyValue@@YAIW4iePolicyIndex@@W4Bool@@PEAW42@@Z; GetIntegerPolicyValue(iePolicyIndex,Bool,Bool *)
0x1801de902  test    eax, eax
0x1801de904  jz      short loc_1801DE911
0x1801de906  mov     r8d, 78Eh
0x1801de90c  jmp     loc_1801DE77A
0x1801de911  lea     r14, [r15+2B8h]
0x1801de918  mov     rcx, [r14]
0x1801de91b  mov     rax, [rcx]
0x1801de91e  mov     rax, [rax+10h]
0x1801de922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de927  lea     rsi, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801de92e  mov     [r14], rsi
0x1801de931  lea     r13, [r15+2B0h]
0x1801de938  mov     rcx, [r13+0]
0x1801de93c  mov     rax, [rcx]
0x1801de93f  mov     rax, [rax+10h]
0x1801de943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de948  mov     rcx, r15; this
0x1801de94b  mov     [r13+0], rsi
0x1801de94f  call    ?GetProductKey@CMsiOpExecute@@IEAAAEBVIMsiString@@XZ; CMsiOpExecute::GetProductKey(void)
0x1801de954  mov     rbx, rax
0x1801de957  mov     rcx, [rax]
0x1801de95a  mov     rax, [rcx+50h]
0x1801de95e  mov     rcx, rbx
0x1801de961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de966  lea     r9, [r15+2A0h]
0x1801de96d  mov     [rsp+0D0h+var_A8], r14
0x1801de972  lea     r8, [r15+298h]
0x1801de979  mov     [rsp+0D0h+var_B0], r13
0x1801de97e  mov     rdx, rax
0x1801de981  xor     ecx, ecx
0x1801de983  call    ?VerifyProduct@@YA_NW4iaaAppAssignment@@PEBGAEAPEAUHKEY__@@2AEAPEBVIMsiString@@3@Z; VerifyProduct(iaaAppAssignment,ushort const *,HKEY__ * &,HKEY__ * &,IMsiString const * &,IMsiString const * &)
0x1801de988  mov     [r15+38Ah], al
0x1801de98f  mov     rcx, rbx
0x1801de992  mov     [r15+38Bh], al
0x1801de999  mov     rax, [rbx]
0x1801de99c  mov     rax, [rax+10h]
0x1801de9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de9a5  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x1801de9aa  cmp     byte ptr [r15+38Ah], 0
0x1801de9b2  mov     edi, 20000000h
0x1801de9b7  mov     dword ptr [rbp+57h+arg_0], eax
0x1801de9ba  jnz     loc_1801DEAEC
0x1801de9c0  cmp     eax, 0FFFFFFFFh
0x1801de9c3  jz      loc_1801DE67B
0x1801de9c9  test    [r15+360h], edi
0x1801de9d0  jz      short loc_1801DEA38
0x1801de9d2  cmp     eax, 1
0x1801de9d5  jnz     short loc_1801DEA38
0x1801de9d7  mov     [r15+38Ah], al
0x1801de9de  mov     rcx, [r14]
0x1801de9e1  mov     rax, [rcx]
0x1801de9e4  mov     rax, [rax+10h]
0x1801de9e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801de9ed  mov     [r14], rsi
0x1801de9f0  mov     rcx, [r13+0]
0x1801de9f4  mov     rax, [rcx]
0x1801de9f7  mov     rax, [rax+10h]
0x1801de9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dea00  xor     edx, edx
0x1801dea02  mov     [rsp+0D0h+var_A8], r14
0x1801dea07  lea     r8, [r15+298h]
0x1801dea0e  lea     r9, [r15+2A0h]
0x1801dea15  mov     [rsp+0D0h+var_B0], r13
0x1801dea1a  xor     ecx, ecx
0x1801dea1c  mov     [r13+0], rsi
0x1801dea20  call    ?GetPublishKeyByUser@@YAJPEBGW4iaaAppAssignment@@AEAPEAUHKEY__@@2AEAPEBVIMsiString@@3@Z; GetPublishKeyByUser(ushort const *,iaaAppAssignment,HKEY__ * &,HKEY__ * &,IMsiString const * &,IMsiString const * &)
0x1801dea25  xor     r14d, r14d
0x1801dea28  test    eax, eax
0x1801dea2a  jnz     loc_1801DE7EC
0x1801dea30  mov     eax, dword ptr [rbp+57h+arg_0]
0x1801dea33  jmp     loc_1801DEAEF
0x1801dea38  mov     rcx, [r14]
0x1801dea3b  mov     rax, [rcx]
0x1801dea3e  mov     rax, [rax+10h]
0x1801dea42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dea47  mov     [r14], rsi
0x1801dea4a  mov     rcx, [r13+0]
0x1801dea4e  mov     rax, [rcx]
0x1801dea51  mov     rax, [rax+10h]
0x1801dea55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dea5a  mov     rcx, r15; this
0x1801dea5d  mov     [r13+0], rsi
0x1801dea61  call    ?GetProductKey@CMsiOpExecute@@IEAAAEBVIMsiString@@XZ; CMsiOpExecute::GetProductKey(void)
0x1801dea66  mov     rbx, rax
0x1801dea69  mov     rcx, [rax]
0x1801dea6c  mov     rax, [rcx+50h]
0x1801dea70  mov     rcx, rbx
0x1801dea73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dea78  lea     r9, [r15+2A0h]
0x1801dea7f  mov     [rsp+0D0h+var_A8], r14
0x1801dea84  lea     r8, [r15+298h]
0x1801dea8b  mov     [rsp+0D0h+var_B0], r13
0x1801dea90  mov     rdx, rax
0x1801dea93  mov     ecx, 1
0x1801dea98  call    ?VerifyProduct@@YA_NW4iaaAppAssignment@@PEBGAEAPEAUHKEY__@@2AEAPEBVIMsiString@@3@Z; VerifyProduct(iaaAppAssignment,ushort const *,HKEY__ * &,HKEY__ * &,IMsiString const * &,IMsiString const * &)
0x1801dea9d  mov     [r15+38Bh], al
0x1801deaa4  mov     rcx, rbx
0x1801deaa7  mov     rax, [rbx]
0x1801deaaa  mov     rax, [rax+10h]
0x1801deaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801deab3  cmp     byte ptr [r15+38Bh], 0
0x1801deabb  jnz     short loc_1801DEAE9
0x1801deabd  mov     rcx, [r14]
0x1801deac0  mov     rax, [rcx]
0x1801deac3  mov     rax, [rax+10h]
0x1801deac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801deacc  mov     [r14], rsi
0x1801deacf  mov     rcx, [r13+0]
0x1801dead3  mov     rax, [rcx]
0x1801dead6  mov     rax, [rax+10h]
0x1801deada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801deadf  mov     edx, 1
0x1801deae4  jmp     loc_1801DEA02
0x1801deae9  mov     eax, dword ptr [rbp+57h+arg_0]
0x1801deaec  xor     r14d, r14d
0x1801deaef  cmp     [r15+38Ah], r14b
0x1801deaf6  jz      loc_1801DE82F
0x1801deafc  cmp     [r15+1F4h], r12d
0x1801deb03  jnz     short loc_1801DEB27
0x1801deb05  cmp     [r15+290h], r14d
0x1801deb0c  jz      short loc_1801DEB27
0x1801deb0e  test    [r15+360h], edi
0x1801deb15  jz      short loc_1801DEB1C
0x1801deb17  cmp     eax, 1
0x1801deb1a  jz      short loc_1801DEB27
0x1801deb1c  mov     r8d, 799h
0x1801deb22  jmp     loc_1801DE77A
0x1801deb27  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801deb2e  mov     rcx, rsi
0x1801deb31  mov     rax, [rax+10h]
0x1801deb35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801deb3a  lea     rbx, [r15+2C0h]
0x1801deb41  mov     [rbp+57h+arg_0], rsi
  ... truncated ...
```
