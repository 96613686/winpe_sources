# CMsiEngine::SecureRepair(void)

- ea: `0x1800be418`
- end: `0x1800bfb47`
- name: `?SecureRepair@CMsiEngine@@QEAAPEAVIMsiRecord@@XZ`
- size: `5935`
- prototype: `struct IMsiRecord *__fastcall(CMsiEngine *__hidden this)`
- caller_count: `3`
- callee_count: `27`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800be1b0`
- `0x18013c0b8`
- `0x18017fa90`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18000c4bc`
- `0x180014528`
- `0x180014e38`
- `0x180018ee0`
- `0x18001f57c`
- `0x180058790`
- `0x180067fec`
- `0x180086264`
- `0x18008c93c`
- `0x180097c78`
- `0x1800af3bc`
- `0x1800be418`
- `0x1800d04fc`
- `0x1800dcef8`
- `0x1800ee66c`
- `0x18013ca64`
- `0x18013fa30`
- `0x18014676c`
- `0x18014eebc`
- `0x18015c768`
- `0x180212a48`
- `0x180214260`
- `0x180214334`
- `0x180214c5c`
- `0x180266010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800bf7db`
- `KERNEL32!DeleteFileW` at `0x1800bf7db`

## string_xrefs

- `0x1800be6e6`: `SECREPAIR: Error in CreatePath`
- `0x1800be806`: `SECREPAIR: Error in CreatePath`
- `0x1800be90c`: `SECREPAIR: Source location is URL. Initial Installation or Advertising.`
- `0x1800be8f6`: `SECREPAIR: Source location is URL. User is elevated.`
- `0x1800be915`: `SECREPAIR: Secure repair not needed`
- `0x1800be61b`: `SECREPAIR: Error determining package source type`
- `0x1800bea0f`: `SECREPAIR: Source Subpath Temporary column index unavailable`
- `0x1800bfaa4`: `SECREPAIR: Error Installer folder does not exist`
- `0x1800beb95`: `SECREPAIR: Error determining whether source hash file already exists`
- `0x1800bebf8`: `SECREPAIR: Re-Create hashes`
- `0x1800bec6d`: `SECREPAIR: Hash Database: %s`
- `0x1800bf791`: `SECREPAIR: SourceHash database file already exists. Deleting it.`
- `0x1800bfa86`: `SECREPAIR: Error in CreateDatabase for write`
- `0x1800bef59`: `SECREPAIR: Failed to commit the hash database`
- `0x1800bf9ae`: `SECREPAIR: New Hash Database creation complete.`
- `0x1800bfa04`: `SECREPAIR: Failed to create hash for the install source files`
- `0x1800bfa41`: `SECREPAIR: Failed to create hash for the CustomAction source files`
- `0x1800bee14`: `SECREPAIR: SourceHash file is not found`
- `0x1800be6f2`: `SECREPAIR: Admin consent through REGISTRY to not show HashMissing UAC`
- `0x1800bf076`: `SECREPAIR: UAC not supported and could not take approval from user`
- `0x1800bf713`: `SECREPAIR: UAC not supported and could not take approval from user`
- `0x1800bf39d`: `SECREPAIR: Error in Creating File Hash Storage Path`
- `0x1800bf533`: `SECREPAIR: File Hash Storage Path contains Junction`
- `0x1800beeb7`: `SECREPAIR: Error in CreateDatabase for read`
- `0x1800bf3e8`: `SECREPAIR: Failed to verify hash for the install source files`
- `0x1800bf63d`: `SECREPAIR: Failed to verify hash for the CustomAction source files`
- `0x1800bf677`: `SECREPAIR: Hash mismatch`
- `0x1800bee4d`: `SECREPAIR: Source files have been tampered`
- `0x1800becf1`: `SECREPAIR: Neither a installation/repair nor an advertisement scenario`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiEngine::SecureRepair(CMsiEngine *this)
{
  __int64 v2; // rdi
  CMsiSecureRepairManager *v3; // rax
  __int64 v4; // rbx
  unsigned int v5; // r15d
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rsi
  void (*v9)(void); // rax
  int v11; // eax
  CMsiSecureRepairManager *v12; // rax
  __int64 (__fastcall *v13)(CMsiEngine *, struct IMsiRecord **, __int64 *, int *); // rsi
  const unsigned __int16 *v14; // r9
  __int64 (__fastcall *v15)(__int64, __int64, __int64); // r14
  __int64 v16; // rsi
  __int64 v17; // rax
  const unsigned __int16 *v18; // r9
  int v19; // esi
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  struct IMsiRecord *Record; // rdi
  __int64 (__fastcall *v25)(__int64, __int64, __int64); // r14
  __int64 v26; // rsi
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // r14
  __int64 (__fastcall *v30)(__int64, __int64, int *, _QWORD); // rsi
  __int64 v31; // rax
  const unsigned __int16 *v32; // rax
  int v33; // esi
  __int64 v34; // rsi
  __int64 v35; // r14
  __int64 v36; // r15
  __int64 v37; // r12
  __int64 v38; // r13
  CMsiSecureRepairManager **v39; // rdi
  unsigned int v40; // ecx
  const unsigned __int16 *v41; // r9
  void (*v42)(void); // rax
  __int64 v43; // r8
  __int64 v44; // r8
  __int64 v45; // rdi
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rax
  int v57; // eax
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rax
  struct IMsiRecord *v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rax
  CMsiSecureRepairManager **v73; // rdi
  int v74; // ecx
  __int64 v75; // r8
  const WCHAR *v76; // rax
  __int64 (__fastcall *v77)(__int64, __int64, __int64, __int64); // r14
  __int64 v78; // rsi
  __int64 v79; // rax
  struct IMsiDatabase *v80; // r14
  __int64 (__fastcall *v81)(struct IMsiDatabase *, _QWORD, _QWORD, __int64); // rsi
  __int64 v82; // rdi
  MsiString *v83; // rax
  __int64 v84; // rsi
  __int64 (__fastcall *v85)(__int64, __int64, _QWORD); // rdi
  MsiString *v86; // rax
  int v87; // r14d
  __int64 v88; // rsi
  __int64 (__fastcall *v89)(__int64, __int64, _QWORD); // rdi
  MsiString *v90; // rax
  __int64 v91; // rsi
  __int64 (__fastcall *v92)(__int64, __int64, _QWORD); // rdi
  MsiString *v93; // rax
  int v94; // edi
  const unsigned __int16 *v95; // r9
  __int64 v96; // [rsp+60h] [rbp-59h] BYREF
  __int64 v97; // [rsp+68h] [rbp-51h] BYREF
  struct IMsiString *MsiDirectory; // [rsp+70h] [rbp-49h] BYREF
  __int64 v99; // [rsp+78h] [rbp-41h] BYREF
  struct IMsiDatabase *v100; // [rsp+80h] [rbp-39h] BYREF
  __int64 v101; // [rsp+88h] [rbp-31h] BYREF
  __int64 v102; // [rsp+90h] [rbp-29h] BYREF
  __int64 v103; // [rsp+98h] [rbp-21h] BYREF
  __int64 v104; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v105; // [rsp+A8h] [rbp-11h]
  __int64 v106; // [rsp+B0h] [rbp-9h] BYREF
  __int64 (__fastcall *v107)(__int64, __int64, struct IMsiRecord *); // [rsp+B8h] [rbp-1h]
  _DWORD v108[20]; // [rsp+C0h] [rbp+7h] BYREF
  CMsiSecureRepairManager **v109; // [rsp+120h] [rbp+67h] BYREF
  int v110; // [rsp+128h] [rbp+6Fh] BYREF
  struct IMsiRecord *v111; // [rsp+130h] [rbp+77h] BYREF
  int v112; // [rsp+138h] [rbp+7Fh] BYREF

  v109 = (CMsiSecureRepairManager **)this;
  v96 = (*(__int64 (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 296LL))(this);
  v2 = (*(__int64 (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 56LL))(this);
  v99 = v2;
  v3 = *(CMsiSecureRepairManager **)this;
  LODWORD(v111) = 0;
  v4 = (*((__int64 (__fastcall **)(CMsiEngine *, const unsigned __int16 *))v3 + 23))(this, L"SourceDir");
  v97 = 0;
  v5 = (*(__int64 (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 504LL))(this);
  LODWORD(v105) = v5;
  if ( g_scServerContext != 2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    goto LABEL_11;
  }
  v6 = *((_QWORD *)this + 276);
  if ( v6 )
  {
    v7 = *(_QWORD *)(v6 + 48);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    v8 = *(_QWORD *)(v6 + 48);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    v9 = *(void (**)(void))(*(_QWORD *)v96 + 16LL);
    goto LABEL_8;
  }
  if ( *(_WORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 66) + 80LL))(*((_QWORD *)this + 66)) == 58
    && *((_QWORD *)this + 22) )
  {
    goto LABEL_27;
  }
  v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v2 + 120LL);
  v16 = CComPointer<IEnumMsiRecord>::operator=(&v97);
  v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 80LL))(v4);
  v8 = v15(v2, v17, v16);
  if ( v8 )
  {
    if ( !g_dmDiagnosticMode )
      goto LABEL_29;
    v14 = L"SECREPAIR: Error in CreatePath";
    goto LABEL_17;
  }
  v106 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v97 + 72LL))(v97);
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 144LL))(v106);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v106);
  if ( v19 )
  {
    if ( v5 <= 1 )
    {
      if ( g_dmDiagnosticMode )
      {
        v20 = L"SECREPAIR: Source location is URL. Initial Installation or Advertising.";
        goto LABEL_38;
      }
LABEL_27:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v99);
LABEL_11:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
      return 0;
    }
    if ( IsAdmin() || *((_BYTE *)this + 601) )
    {
      if ( g_dmDiagnosticMode )
      {
        v20 = L"SECREPAIR: Source location is URL. User is elevated.";
LABEL_38:
        DebugString(9, 0, 0, v20, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_27;
      }
      goto LABEL_27;
    }
  }
  v21 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v96 + 80LL))(v96);
  if ( !CMsiSecureRepairManager::NeedsSecureRepair(v21, (enum eSecRepairModeEnum *)&v111) )
  {
    if ( !g_dmDiagnosticMode )
      goto LABEL_27;
    v20 = L"SECREPAIR: Secure repair not needed";
    goto LABEL_38;
  }
  v22 = operator new(0x40u);
  v23 = v22;
  if ( !v22 )
  {
    *((_QWORD *)this + 276) = 0;
    Record = (struct IMsiRecord *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 48LL))(v2, 1);
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)Record + 104LL))(Record, 1, 8);
LABEL_170:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    goto LABEL_171;
  }
  *v22 = this;
  v22[1] = 0;
  *((_WORD *)v22 + 8) = 0;
  *((_BYTE *)v22 + 18) = 0;
  *((_DWORD *)v22 + 5) = 0;
  *(_QWORD *)((char *)v22 + 28) = 0;
  *(_QWORD *)((char *)v22 + 36) = 0;
  v22[6] = 0;
  v22[7] = -1;
  v11 = (int)v111;
  *((_QWORD *)this + 276) = v23;
  *((_DWORD *)v23 + 6) = v11;
  *(_DWORD *)(*((_QWORD *)this + 276) + 40LL) = CMsiEngine::GetDeploymentFlags(this);
  v12 = *(CMsiSecureRepairManager **)this;
  v112 = 0;
  v13 = (__int64 (__fastcall *)(CMsiEngine *, struct IMsiRecord **, __int64 *, int *))*((_QWORD *)v12 + 68);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  v111 = (struct IMsiRecord *)v2;
  v8 = v13(this, &v111, &v96, &v112);
  if ( v8 )
  {
    if ( !g_dmDiagnosticMode )
    {
LABEL_29:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v99);
      v9 = *(void (**)(void))(*(_QWORD *)v96 + 16LL);
LABEL_8:
      v9();
      return (struct IMsiRecord *)v8;
    }
    v14 = L"SECREPAIR: Error determining package source type";
LABEL_17:
    DebugString(9, 0, 0, v14, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
    goto LABEL_29;
  }
  if ( (v112 & 2) != 0 )
    *(_BYTE *)(*((_QWORD *)this + 276) + 17LL) = 1;
  if ( !*((_DWORD *)this + 463) && g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"SECREPAIR: Source Subpath Temporary column index unavailable",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  *(_DWORD *)(*((_QWORD *)this + 276) + 20LL) = *((_DWORD *)this + 463);
  v102 = (*(__int64 (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 72LL))(this);
  v101 = 0;
  MsiDirectory = GetMsiDirectory();
  if ( !(*(unsigned int (__fastcall **)(struct IMsiString *, __int64, const unsigned __int16 *))(*(_QWORD *)MsiDirectory
                                                                                               + 200LL))(
          MsiDirectory,
          4,
          L"\\") )
    MsiString::operator+=(&MsiDirectory, L"\\");
  v25 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v2 + 120LL);
  v26 = CComPointer<IEnumMsiRecord>::operator=(&v101);
  v27 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
  v8 = v25(v2, v27, v26);
  if ( v8 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Error in CreatePath",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
LABEL_28:
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
    goto LABEL_29;
  }
  v108[0] = 0;
  v28 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v101 + 160LL))(v101, v108);
  if ( !v108[0] || v28 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Error Installer folder does not exist",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    Record = PostError(2362, MsiDirectory);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
    goto LABEL_170;
  }
  MsiString::MsiString((MsiString *)&v104, L"SourceHash");
  MsiString::operator+=(&v104, &v96);
  v110 = 0;
  v29 = v101;
  v30 = *(__int64 (__fastcall **)(__int64, __int64, int *, _QWORD))(*(_QWORD *)v101 + 120LL);
  v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v104 + 80LL))(v104);
  v8 = v30(v29, v31, &v110, 0);
  if ( v8 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Error determining whether source hash file already exists",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
    goto LABEL_28;
  }
  if ( *((_BYTE *)this + 601) )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Re-Create hashes",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    *(_BYTE *)(*((_QWORD *)this + 276) + 18LL) = 1;
  }
  v100 = 0;
  v103 = 0;
  MsiString::operator+=(&MsiDirectory, &v104);
  if ( g_dmDiagnosticMode )
  {
    v32 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
    DebugString(
      9,
      0,
      0,
      L"SECREPAIR: Hash Database: %s",
      v32,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  v33 = v105;
  if ( (unsigned int)v105 > 1
    && !CMsiSecureRepairManager::IsGPDeployFirstInstall(*((CMsiSecureRepairManager **)this + 276))
    && !*(_BYTE *)(*((_QWORD *)this + 276) + 18LL) )
  {
    if ( ((v33 - 2) & 0xFFFFFFFD) != 0 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SECREPAIR: Neither a installation/repair nor an advertisement scenario",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      goto LABEL_26;
    }
    v34 = (*(__int64 (__fastcall **)(CMsiEngine *, const WCHAR *))(*(_QWORD *)this + 184LL))(this, L"ProductName");
    v35 = (*(__int64 (__fastcall **)(CMsiEngine *, const unsigned __int16 *))(*(_QWORD *)this + 184LL))(
            this,
            L"ProductVersion");
    v36 = (*(__int64 (__fastcall **)(CMsiEngine *, const unsigned __int16 *))(*(_QWORD *)this + 184LL))(
            this,
            L"ProductLanguage");
    v37 = (*(__int64 (__fastcall **)(CMsiEngine *, const unsigned __int16 *))(*(_QWORD *)this + 184LL))(
            this,
            L"Manufacturer");
    v38 = (*(__int64 (__fastcall **)(CMsiEngine *, const unsigned __int16 *))(*(_QWORD *)this + 184LL))(
            this,
            L"DATABASE");
    v105 = (*((__int64 (__fastcall **)(CMsiSecureRepairManager **, const unsigned __int16 *))*v109 + 23))(
             v109,
             L"OriginalDatabase");
    if ( !v110 )
    {
      v39 = v109;
      if ( *((_DWORD *)v109[276] + 6) == 1 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR: SourceHash file is not found",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        v40 = 1;
        goto LABEL_79;
      }
      if ( CMsiSecureRepairManager::DonotShowHashMissingUAC(0) )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_24;
        v18 = L"SECREPAIR: Admin consent through REGISTRY to not show HashMissing UAC";
LABEL_23:
        DebugString(9, 0, 0, v18, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
LABEL_24:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
LABEL_25:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
LABEL_26:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
        (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
        goto LABEL_27;
      }
      if ( g_iMajorVersion <= 6
        && (g_iMajorVersion != 6 || g_iMinorVersion <= 1 && (g_iMinorVersion != 1 || g_iServicePackLevel < 0)) )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_24;
        v18 = L"SECREPAIR: UAC not supported and could not take approval from user";
        goto LABEL_23;
      }
      LODWORD(v109) = GetIntegerPolicyValue(5, 1, v43);
      if ( (unsigned int)GetIntegerPolicyValue(5, 0, v44) == 1 && (_DWORD)v109 == 1
        || IsAdmin()
        || ((*((__int64 (__fastcall **)(CMsiSecureRepairManager **))*v39 + 12))(v39) & 1) != 0 )
      {
        goto LABEL_24;
      }
      v45 = v105;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v105 + 80LL))(v105);
      v47 = *(_QWORD *)v38;
      v109 = (CMsiSecureRepairManager **)v46;
      v48 = (*(__int64 (__fastcall **)(__int64))(v47 + 80))(v38);
      v49 = *(_QWORD *)v37;
      v111 = (struct IMsiRecord *)v48;
      v50 = (*(__int64 (__fastcall **)(__int64))(v49 + 80))(v37);
      v51 = *(_QWORD *)v36;
      v106 = v50;
      v52 = (*(__int64 (__fastcall **)(__int64))(v51 + 80))(v36);
      v53 = *(_QWORD *)v35;
      v105 = v52;
      v54 = (*(__int64 (__fastcall **)(__int64))(v53 + 80))(v35);
      v55 = *(_QWORD *)v34;
      v107 = (__int64 (__fastcall *)(__int64, __int64, struct IMsiRecord *))v54;
      v56 = (*(__int64 (__fastcall **)(__int64))(v55 + 80))(v34);
      v57 = InstallPromptForElevatedCredentials(v102, 7, v56, v107, v105, v106, v111, v109, 0, 0, 0);
LABEL_100:
      if ( v57 < 0 )
      {
        v69 = PostError(3);
        v70 = *(_QWORD *)v45;
        v109 = (CMsiSecureRepairManager **)v69;
        (*(void (__fastcall **)(__int64))(v70 + 16))(v45);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
        (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v99);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
        return (struct IMsiRecord *)v109;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      goto LABEL_25;
    }
    v106 = 0;
    v107 = *(__int64 (__fastcall **)(__int64, __int64, struct IMsiRecord *))(*(_QWORD *)v2 + 120LL);
    v111 = (struct IMsiRecord *)CComPointer<IEnumMsiRecord>::operator=(&v106);
    v71 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
    v111 = (struct IMsiRecord *)v107(v2, v71, v111);
    if ( v111 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SECREPAIR: Error in Creating File Hash Storage Path",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v106);
LABEL_107:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v99);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
      return v111;
    }
    LODWORD(v111) = 0;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v106 + 584LL))(v106) )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SECREPAIR: File Hash Storage Path contains Junction",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      LODWORD(v111) = 1;
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v106);
    if ( !(_DWORD)v111 )
    {
      v107 = *(__int64 (__fastcall **)(__int64, __int64, struct IMsiRecord *))(*(_QWORD *)v2 + 104LL);
      v111 = (struct IMsiRecord *)CComPointer<IEnumMsiRecord>::operator=(&v100);
      v72 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
      Record = (struct IMsiRecord *)((__int64 (__fastcall *)(__int64, __int64, _QWORD, struct IMsiRecord *))v107)(
                                      v2,
                                      v72,
                                      0,
                                      v111);
      if ( Record || !v100 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR: Error in CreateDatabase for read",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_80;
      }
      v73 = v109;
      CMsiSecureRepairManager::SetHashDatabase(v109[276], v100);
      v111 = CMsiSecureRepairManager::AllFilesHash(v73[276]);
      if ( v111 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR: Failed to verify hash for the install source files",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_107;
      }
      v111 = CMsiSecureRepairManager::SecureCustomActions(v73[276]);
      if ( v111 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR: Failed to verify hash for the CustomAction source files",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_107;
      }
      if ( *((_BYTE *)v73[276] + 16) != 1 )
        goto LABEL_24;
      v74 = g_dmDiagnosticMode;
      if ( !g_dmDiagnosticMode )
      {
LABEL_127:
        if ( *((_DWORD *)v109[276] + 6) == 1 )
        {
          if ( !v74 )
            goto LABEL_78;
          v41 = L"SECREPAIR: Source files have been tampered";
        }
        else
        {
          if ( g_iMajorVersion > 6
            || g_iMajorVersion == 6 && (g_iMinorVersion > 1 || g_iMinorVersion == 1 && g_iServicePackLevel >= 0) )
          {
            LODWORD(v111) = GetIntegerPolicyValue(5, 1, 0);
            if ( (unsigned int)GetIntegerPolicyValue(5, 0, v75) == 1 && (_DWORD)v111 == 1
              || IsAdmin()
              || ((*((__int64 (__fastcall **)(CMsiSecureRepairManager **))*v109 + 12))(v109) & 1) != 0 )
            {
              goto LABEL_24;
            }
            v45 = v105;
            v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v105 + 80LL))(v105);
            v59 = *(_QWORD *)v38;
            v109 = (CMsiSecureRepairManager **)v58;
            v60 = (*(__int64 (__fastcall **)(__int64))(v59 + 80))(v38);
            v61 = *(_QWORD *)v37;
            v111 = (struct IMsiRecord *)v60;
            v62 = (*(__int64 (__fastcall **)(__int64))(v61 + 80))(v37);
            v63 = *(_QWORD *)v36;
            v107 = (__int64 (__fastcall *)(__int64, __int64, struct IMsiRecord *))v62;
            v64 = (*(__int64 (__fastcall **)(__int64))(v63 + 80))(v36);
            v65 = *(_QWORD *)v35;
            v106 = v64;
            v66 = (*(__int64 (__fastcall **)(__int64))(v65 + 80))(v35);
            v67 = *(_QWORD *)v34;
            v105 = v66;
            v68 = (*(__int64 (__fastcall **)(__int64))(v67 + 80))(v34);
            v57 = InstallPromptForElevatedCredentials(v102, 6, v68, v105, v106, v107, v111, v109, 0, 0, 0);
            goto LABEL_100;
          }
          if ( !v74 )
          {
LABEL_78:
            v40 = 2;
LABEL_79:
            Record = CreateRecord(v40);
            (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)Record + 104LL))(Record, 1, 1260);
LABEL_80:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            goto LABEL_82;
          }
          v41 = L"SECREPAIR: UAC not supported and could not take approval from user";
        }
        DebugString(9, 0, 0, v41, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_78;
      }
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Hash mismatch",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    v74 = g_dmDiagnosticMode;
    goto LABEL_127;
  }
  CElevate::CElevate((CElevate *)&v109, 1);
  if ( v110 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: SourceHash database file already exists. Deleting it.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    v76 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
    DeleteFileW(v76);
  }
  v77 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v2 + 104LL);
  v78 = CComPointer<IEnumMsiRecord>::operator=(&v100);
  v79 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
  Record = (struct IMsiRecord *)v77(v2, v79, 3, v78);
  CElevate::~CElevate((CElevate *)&v109);
  if ( Record || !v100 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Error in CreateDatabase for write",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_82;
  }
  CMsiSecureRepairManager::SetHashDatabase(*((CMsiSecureRepairManager **)this + 276), v100);
  v80 = v100;
  v81 = *(__int64 (__fastcall **)(struct IMsiDatabase *, _QWORD, _QWORD, __int64))(*(_QWORD *)v100 + 88LL);
  v82 = CComPointer<IEnumMsiRecord>::operator=(&v103);
  v83 = MsiString::MsiString((MsiString *)&v109, L"SourceHash");
  Record = (struct IMsiRecord *)v81(v80, *(_QWORD *)v83, 0, v82);
  (*((void (__fastcall **)(CMsiSecureRepairManager **))*v109 + 2))(v109);
  if ( !Record )
  {
    v84 = v103;
    v85 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v103 + 120LL);
    v86 = MsiString::MsiString((MsiString *)&v109, L"FileName");
    v87 = v85(v84, 11520, *(_QWORD *)v86);
    (*((void (__fastcall **)(CMsiSecureRepairManager **))*v109 + 2))(v109);
    v88 = v103;
    v89 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v103 + 120LL);
    v90 = MsiString::MsiString((MsiString *)&v111, L"HashAlgo");
    LODWORD(v109) = v89(v88, 256, *(_QWORD *)v90);
    (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v111 + 16LL))(v111);
    v91 = v103;
    v92 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v103 + 120LL);
    v93 = MsiString::MsiString((MsiString *)&v111, L"FileHashValue");
    v94 = v92(v91, 3328, *(_QWORD *)v93);
    (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v111 + 16LL))(v111);
    if ( !v87 || !(_DWORD)v109 || !v94 )
    {
      Record = PostError(2728, L"SourceHash");
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
      v42 = *(void (**)(void))(*(_QWORD *)MsiDirectory + 16LL);
      goto LABEL_84;
    }
    Record = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiDatabase *))(*(_QWORD *)v100 + 152LL))(v100);
    if ( !Record )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SECREPAIR: New Hash Database creation complete.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      Record = CMsiSecureRepairManager::AllFilesHash(*((CMsiSecureRepairManager **)this + 276));
      if ( Record )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_82;
        v95 = L"SECREPAIR: Failed to create hash for the install source files";
        goto LABEL_81;
      }
      Record = CMsiSecureRepairManager::SecureCustomActions(*((CMsiSecureRepairManager **)this + 276));
      if ( Record )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_82;
        v95 = L"SECREPAIR: Failed to create hash for the CustomAction source files";
LABEL_81:
        DebugString(9, 0, 0, v95, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_82;
      }
      Record = (struct IMsiRecord *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 276) + 8LL)
                                                                      + 152LL))(*(_QWORD *)(*((_QWORD *)this + 276) + 8LL));
      if ( !Record )
        goto LABEL_26;
    }
    if ( !g_dmDiagnosticMode )
      goto LABEL_82;
    v95 = L"SECREPAIR: Failed to commit the hash database";
    goto LABEL_81;
  }
LABEL_82:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
  v42 = *(void (**)(void))(*(_QWORD *)MsiDirectory + 16LL);
LABEL_84:
  v42();
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
LABEL_171:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v99);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  return Record;
}

```

## disassembly

```asm
0x1800be418  mov     [rsp-8+arg_0], rcx
0x1800be41d  push    rbp
0x1800be41e  push    rbx
0x1800be41f  push    rsi
0x1800be420  push    rdi
0x1800be421  push    r12
0x1800be423  push    r13
0x1800be425  push    r14
0x1800be427  push    r15
0x1800be429  lea     rbp, [rsp-1Fh]
0x1800be42e  sub     rsp, 0D8h
0x1800be435  mov     rax, [rcx]
0x1800be438  mov     r13, rcx
0x1800be43b  mov     rax, [rax+128h]
0x1800be442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be447  mov     [rbp+57h+var_B0], rax
0x1800be44b  mov     rcx, r13
0x1800be44e  mov     rax, [r13+0]
0x1800be452  mov     rax, [rax+38h]
0x1800be456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be45b  mov     rdi, rax
0x1800be45e  mov     [rbp+57h+var_98], rax
0x1800be462  mov     rax, [r13+0]
0x1800be466  lea     rdx, aSourcedir; "SourceDir"
0x1800be46d  xor     r12d, r12d
0x1800be470  mov     rcx, r13
0x1800be473  mov     dword ptr [rbp+57h+arg_10], r12d
0x1800be477  mov     rax, [rax+0B8h]
0x1800be47e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be483  mov     rbx, rax
0x1800be486  mov     [rbp+57h+var_A8], r12
0x1800be48a  mov     rax, [r13+0]
0x1800be48e  mov     rcx, r13
0x1800be491  mov     rax, [rax+1F8h]
0x1800be498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be49d  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1800be4a4  mov     r15d, eax
0x1800be4a7  mov     dword ptr [rbp+57h+var_68], eax
0x1800be4aa  jnz     loc_1800BE531
0x1800be4b0  mov     rsi, [r13+8A0h]
0x1800be4b7  test    rsi, rsi
0x1800be4ba  jz      loc_1800BE674
0x1800be4c0  mov     rcx, [rsi+30h]
0x1800be4c4  test    rcx, rcx
0x1800be4c7  jnz     loc_1800BE663
0x1800be4cd  mov     rcx, [rbp+57h+var_A8]
0x1800be4d1  mov     rsi, [rsi+30h]
0x1800be4d5  test    rcx, rcx
0x1800be4d8  jz      short loc_1800BE4E6
0x1800be4da  mov     rax, [rcx]
0x1800be4dd  mov     rax, [rax+10h]
0x1800be4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be4e6  mov     rax, [rbx]
0x1800be4e9  mov     rcx, rbx
0x1800be4ec  mov     rax, [rax+10h]
0x1800be4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be4f5  test    rdi, rdi
0x1800be4f8  jz      short loc_1800BE509
0x1800be4fa  mov     rcx, [rdi]
0x1800be4fd  mov     rax, [rcx+10h]
0x1800be501  mov     rcx, rdi
0x1800be504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be509  mov     rcx, [rbp+57h+var_B0]
0x1800be50d  mov     rdx, [rcx]
0x1800be510  mov     rax, [rdx+10h]
0x1800be514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be519  mov     rax, rsi
0x1800be51c  add     rsp, 0D8h
0x1800be523  pop     r15
0x1800be525  pop     r14
0x1800be527  pop     r13
0x1800be529  pop     r12
0x1800be52b  pop     rdi
0x1800be52c  pop     rsi
0x1800be52d  pop     rbx
0x1800be52e  pop     rbp
0x1800be52f  retn
0x1800be531  mov     rcx, [rbp+57h+var_A8]
0x1800be535  test    rcx, rcx
0x1800be538  jz      short loc_1800BE546
0x1800be53a  mov     rax, [rcx]
0x1800be53d  mov     rax, [rax+10h]
0x1800be541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be546  mov     rax, [rbx]
0x1800be549  mov     rcx, rbx
0x1800be54c  mov     rax, [rax+10h]
0x1800be550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be555  test    rdi, rdi
0x1800be558  jz      short loc_1800BE569
0x1800be55a  mov     rax, [rdi]
0x1800be55d  mov     rcx, rdi
0x1800be560  mov     rax, [rax+10h]
0x1800be564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be569  mov     rcx, [rbp+57h+var_B0]
0x1800be56d  mov     rax, [rcx]
0x1800be570  mov     rax, [rax+10h]
0x1800be574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be579  xor     eax, eax
0x1800be57b  jmp     short loc_1800BE51C
0x1800be57d  mov     [rax], r13
0x1800be580  mov     [rax+8], r12
0x1800be584  mov     [rax+10h], r12w
0x1800be589  mov     [rax+12h], r12b
0x1800be58d  mov     [rax+14h], r12d
0x1800be591  mov     [rax+1Ch], r12
0x1800be595  mov     [rax+24h], r12
0x1800be599  mov     [rax+30h], r12
0x1800be59d  mov     qword ptr [rax+38h], 0FFFFFFFFFFFFFFFFh
0x1800be5a5  mov     eax, dword ptr [rbp+57h+arg_10]
0x1800be5a8  mov     [r13+8A0h], rcx
0x1800be5af  mov     [rcx+18h], eax
0x1800be5b2  mov     rcx, r13; this
0x1800be5b5  call    ?GetDeploymentFlags@CMsiEngine@@IEAAHXZ; CMsiEngine::GetDeploymentFlags(void)
0x1800be5ba  mov     rcx, [r13+8A0h]
0x1800be5c1  mov     [rcx+28h], eax
0x1800be5c4  mov     rax, [r13+0]
0x1800be5c8  mov     [rbp+57h+arg_18], r12d
0x1800be5cc  mov     rsi, [rax+220h]
0x1800be5d3  test    rdi, rdi
0x1800be5d6  jz      short loc_1800BE5E7
0x1800be5d8  mov     rcx, [rdi]
0x1800be5db  mov     rax, [rcx+8]
0x1800be5df  mov     rcx, rdi
0x1800be5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be5e7  lea     r9, [rbp+57h+arg_18]
0x1800be5eb  mov     [rbp+57h+arg_10], rdi
0x1800be5ef  lea     r8, [rbp+57h+var_B0]
0x1800be5f3  mov     rcx, r13
0x1800be5f6  lea     rdx, [rbp+57h+arg_10]
0x1800be5fa  mov     rax, rsi
0x1800be5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be602  mov     rsi, rax
0x1800be605  test    rax, rax
0x1800be608  jz      loc_1800BE9DB
0x1800be60e  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x1800be615  jz      loc_1800BE85F
0x1800be61b  lea     r9, aSecrepairError_9; "SECREPAIR: Error determining package so"...
0x1800be622  mov     [rsp+110h+var_B8], r12; void *
0x1800be627  lea     rax, aNull; "(NULL)"
0x1800be62e  mov     [rsp+110h+var_C0], r12d; unsigned int
0x1800be633  xor     edx, edx; unsigned __int16
0x1800be635  mov     [rsp+110h+var_C8], rax; unsigned __int16 *
0x1800be63a  xor     r8d, r8d; int
0x1800be63d  mov     [rsp+110h+var_D0], rax; unsigned __int16 *
0x1800be642  mov     [rsp+110h+var_D8], rax; unsigned __int16 *
0x1800be647  mov     [rsp+110h+var_E0], rax; unsigned __int16 *
0x1800be64c  lea     ecx, [rdx+9]; int
0x1800be64f  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x1800be654  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be659  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800be65e  jmp     loc_1800BE85F
0x1800be663  mov     rax, [rcx]
0x1800be666  mov     rax, [rax+8]
0x1800be66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be66f  jmp     loc_1800BE4CD
0x1800be674  mov     rcx, [r13+210h]
0x1800be67b  mov     rax, [rcx]
0x1800be67e  mov     rax, [rax+50h]
0x1800be682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be687  cmp     word ptr [rax], 3Ah ; ':'
0x1800be68b  jnz     short loc_1800BE69A
0x1800be68d  cmp     [r13+0B0h], r12
0x1800be694  jnz     loc_1800BE7DB
0x1800be69a  mov     rax, [rdi]
0x1800be69d  lea     rcx, [rbp+57h+var_A8]
0x1800be6a1  mov     r14, [rax+78h]
0x1800be6a5  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1800be6aa  mov     rcx, [rbx]
0x1800be6ad  mov     rsi, rax
0x1800be6b0  mov     rax, [rcx+50h]
0x1800be6b4  mov     rcx, rbx
0x1800be6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be6bc  mov     rdx, rax
0x1800be6bf  mov     r8, rsi
0x1800be6c2  mov     rax, r14
0x1800be6c5  mov     rcx, rdi
0x1800be6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be6cd  mov     rsi, rax
0x1800be6d0  test    rax, rax
0x1800be6d3  jz      loc_1800BE890
0x1800be6d9  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x1800be6e0  jz      loc_1800BE85F
0x1800be6e6  lea     r9, aSecrepairError_10; "SECREPAIR: Error in CreatePath"
0x1800be6ed  jmp     loc_1800BE622
0x1800be6f2  lea     r9, aSecrepairAdmin; "SECREPAIR: Admin consent through REGIST"...
0x1800be6f9  mov     [rsp+110h+var_B8], rcx; void *
0x1800be6fe  lea     rax, aNull; "(NULL)"
0x1800be705  mov     [rsp+110h+var_C0], ecx; unsigned int
0x1800be709  xor     edx, edx; unsigned __int16
0x1800be70b  mov     [rsp+110h+var_C8], rax; unsigned __int16 *
0x1800be710  xor     r8d, r8d; int
0x1800be713  mov     [rsp+110h+var_D0], rax; unsigned __int16 *
0x1800be718  mov     [rsp+110h+var_D8], rax; unsigned __int16 *
0x1800be71d  mov     [rsp+110h+var_E0], rax; unsigned __int16 *
0x1800be722  lea     ecx, [rdx+9]; int
0x1800be725  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x1800be72a  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800be72f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800be734  mov     rax, [rbp+57h+var_68]
0x1800be738  mov     rcx, [rax]
0x1800be73b  mov     rdx, [rcx+10h]
0x1800be73f  mov     rcx, rax
0x1800be742  mov     rax, rdx
0x1800be745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be74a  mov     rax, [r13+0]
0x1800be74e  mov     rcx, r13
0x1800be751  mov     rax, [rax+10h]
0x1800be755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be75a  mov     rax, [r12]
0x1800be75e  mov     rcx, r12
0x1800be761  mov     rax, [rax+10h]
0x1800be765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be76a  mov     rax, [r15]
0x1800be76d  mov     rcx, r15
0x1800be770  mov     rax, [rax+10h]
0x1800be774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be779  mov     rax, [r14]
0x1800be77c  mov     rcx, r14
0x1800be77f  mov     rax, [rax+10h]
0x1800be783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be788  mov     rax, [rsi]
0x1800be78b  mov     rcx, rsi
0x1800be78e  mov     rax, [rax+10h]
0x1800be792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be797  lea     rcx, [rbp+57h+var_78]
0x1800be79b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be7a0  lea     rcx, [rbp+57h+var_90]
0x1800be7a4  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be7a9  mov     rcx, [rbp+57h+var_70]
0x1800be7ad  mov     rax, [rcx]
0x1800be7b0  mov     rax, [rax+10h]
0x1800be7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be7b9  mov     rcx, [rbp+57h+var_A0]
0x1800be7bd  mov     rax, [rcx]
0x1800be7c0  mov     rax, [rax+10h]
0x1800be7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be7c9  lea     rcx, [rbp+57h+var_88]
0x1800be7cd  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be7d2  lea     rcx, [rbp+57h+var_80]
0x1800be7d6  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be7db  lea     rcx, [rbp+57h+var_A8]
0x1800be7df  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be7e4  mov     rax, [rbx]
0x1800be7e7  mov     rcx, rbx
0x1800be7ea  mov     rax, [rax+10h]
0x1800be7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be7f3  lea     rcx, [rbp+57h+var_98]
0x1800be7f7  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be7fc  jmp     loc_1800BE569
0x1800be801  mov     [rsp+110h+var_B8], r14; void *
0x1800be806  lea     r9, aSecrepairError_10; "SECREPAIR: Error in CreatePath"
0x1800be80d  mov     [rsp+110h+var_C0], r14d; unsigned int
0x1800be812  xor     edx, edx; unsigned __int16
0x1800be814  mov     [rsp+110h+var_C8], r15; unsigned __int16 *
0x1800be819  xor     r8d, r8d; int
0x1800be81c  mov     [rsp+110h+var_D0], r15; unsigned __int16 *
0x1800be821  mov     ecx, r12d; int
0x1800be824  mov     [rsp+110h+var_D8], r15; unsigned __int16 *
0x1800be829  mov     [rsp+110h+var_E0], r15; unsigned __int16 *
0x1800be82e  mov     [rsp+110h+var_E8], r15; unsigned __int16 *
0x1800be833  mov     [rsp+110h+var_F0], r15; unsigned __int16 *
0x1800be838  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800be83d  mov     rcx, [rbp+57h+var_A0]
0x1800be841  mov     rax, [rcx]
0x1800be844  mov     rax, [rax+10h]
0x1800be848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be84d  lea     rcx, [rbp+57h+var_88]
0x1800be851  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be856  lea     rcx, [rbp+57h+var_80]
0x1800be85a  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be85f  lea     rcx, [rbp+57h+var_A8]
0x1800be863  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be868  mov     rax, [rbx]
0x1800be86b  mov     rcx, rbx
0x1800be86e  mov     rax, [rax+10h]
0x1800be872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be877  lea     rcx, [rbp+57h+var_98]
0x1800be87b  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be880  mov     rcx, [rbp+57h+var_B0]
0x1800be884  mov     rax, [rcx]
0x1800be887  mov     rax, [rax+10h]
0x1800be88b  jmp     loc_1800BE514
0x1800be890  mov     rcx, [rbp+57h+var_A8]
0x1800be894  mov     rax, [rcx]
0x1800be897  mov     rax, [rax+48h]
0x1800be89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8a0  mov     rdx, rax
0x1800be8a3  mov     [rbp+57h+var_60], rax
0x1800be8a7  mov     rcx, [rax]
0x1800be8aa  mov     rax, [rcx+90h]
0x1800be8b1  mov     rcx, rdx
0x1800be8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8b9  lea     rcx, [rbp+57h+var_60]
0x1800be8bd  mov     esi, eax
0x1800be8bf  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800be8c4  mov     r14d, 1
0x1800be8ca  test    esi, esi
0x1800be8cc  jz      loc_1800BE95D
0x1800be8d2  cmp     r15d, r14d
0x1800be8d5  jbe     short loc_1800BE8FF
  ... truncated ...
```
