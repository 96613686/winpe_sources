# Config::XmlWriter::WriteReplicaSetConfig(Config::ReplicaSetConfig *,Config::PathParam *)

- ea: `0x140064360`
- end: `0x140064d54`
- name: `?WriteReplicaSetConfig@XmlWriter@Config@@QEAAPEAVFrsStatus@@PEAVReplicaSetConfig@2@PEAVPathParam@2@@Z`
- size: `2548`
- prototype: `struct FrsStatus *__fastcall(Config::XmlWriter *__hidden this, struct Config::ReplicaSetConfig *, struct Config::PathParam *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x14005ee30`

## callees

- `0x14000cd1c`
- `0x14000e34c`
- `0x14000ee94`
- `0x140010680`
- `0x140019358`
- `0x14001940c`
- `0x14001cfa0`
- `0x140022ce4`
- `0x1400248f4`
- `0x1400255c8`
- `0x14003ae94`
- `0x14004698c`
- `0x140047e14`
- `0x140047e4c`
- `0x14004d52c`
- `0x14004e00c`
- `0x14004faf8`
- `0x14005b8ec`
- `0x14005bbe8`
- `0x14005cf24`
- `0x14005e8ec`
- `0x1400632d0`
- `0x140064360`
- `0x140064d5c`
- `0x1401b9494`
- `0x1401bebc8`
- `0x1401bebec`
- `0x1401bf310`
- `0x1401c0b7c`
- `0x1401c25ec`
- `0x1401c2a6c`
- `0x1401d0618`
- `0x1401d81e4`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1400648df`
- `KERNEL32!DeleteFileW` at `0x1400648df`
- `KERNEL32!GetLastError` at `0x140064975`
- `KERNEL32!GetLastError` at `0x140064975`
- `KERNEL32!GetCurrentThreadId` at `0x14006449a`
- `KERNEL32!GetCurrentThreadId` at `0x140064c45`
- `KERNEL32!GetCurrentThreadId` at `0x140064cc5`
- `KERNEL32!GetCurrentThreadId` at `0x14006449a`
- `KERNEL32!GetCurrentThreadId` at `0x140064c45`
- `KERNEL32!GetCurrentThreadId` at `0x140064cc5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400646ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400646ec`

## string_xrefs

- `0x140064804`: `System\CurrentControlSet\Services\DFSR\Access Checks\Replication Groups`
- `0x140064b83`: `System\CurrentControlSet\Services\DFSR\Access Checks\Replication Groups`
- `0x1400647ae`: `System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups`
- `0x140064b29`: `System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups`
- `0x1400644c3`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140064c67`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140064ca6`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140064cbe`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140064672`: `Config`
- `0x1400648a4`: `[CLUSTER] (Ignored) Failed to remove registry check point to resource. path:%? regKey:%? Error:%?`
- `0x140064400`: `Config::XmlWriter::WriteReplicaSetConfig`
- `0x140064717`: `Config::XmlWriter::WriteReplicaSetConfig`
- `0x140064871`: `Config::XmlWriter::WriteReplicaSetConfig`
- `0x140064916`: `Config::XmlWriter::WriteReplicaSetConfig`
- `0x1400649b0`: `Config::XmlWriter::WriteReplicaSetConfig`
- `0x140064c02`: `Config::XmlWriter::WriteReplicaSetConfig`
- `0x14006448a`: `Can't overwrite Replication Group from different sourcergId:%? oldSource:%? newSource:%?`
- `0x1400644b7`: `Config::XmlWriter::WriteReplicaSetConfig`
- `0x1400646bd`: `Config::XmlWriter::WriteReplicaSetConfig`
- `0x140064537`: `Replica set config file not found. rgId:%?`
- `0x14006461f`: `(Ignored) Failed to create the volume's '\System Volume Information\DFSR\Config' directory. volPath:%? Error:%?`
- `0x140064960`: `Old replica set XML file:%? is deleted. rgId:%?`
- `0x140064a0f`: `(Ignored) Failed to delete old replica set XML file. filePath:%?. rgId:%?. Error:%?`
- `0x140064c35`: `[CLUSTER] Failed to add registry check point to resource. filePath:%? regKey:%?. Error:%?.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct FrsStatus *__fastcall Config::XmlWriter::WriteReplicaSetConfig(
        Config::XmlWriter *this,
        struct Config::ReplicaSetConfig *a2,
        struct Config::PathParam *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  struct FrsStatus *v8; // rax
  __int64 v9; // rcx
  int v10; // edx
  DWORD CurrentThreadId; // eax
  __int64 v12; // rcx
  __int64 v13; // r9
  struct FrsStatus *SviDfsrConfigDirectory; // rdi
  Config::XmlWriter *v15; // rcx
  __int64 SystemDriveRootDirectory; // rax
  __int64 v17; // rdi
  int v18; // edx
  const unsigned __int16 *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r15
  __int64 v23; // r12
  DWORD v24; // eax
  __int64 v25; // rcx
  struct FrsStatus *v26; // rax
  DWORD v27; // eax
  __int64 v28; // rcx
  unsigned __int16 *v30; // [rsp+50h] [rbp-B0h] BYREF
  struct FrsStatus *v31; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v32; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp-98h] BYREF
  void **v34; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  int v36; // [rsp+80h] [rbp-80h] BYREF
  DWORD LastError; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE v38[8]; // [rsp+88h] [rbp-78h] BYREF
  void **v39; // [rsp+90h] [rbp-70h] BYREF
  __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v41; // [rsp+A0h] [rbp-60h] BYREF
  int v42; // [rsp+A8h] [rbp-58h]
  int v43; // [rsp+ACh] [rbp-54h]
  const wchar_t *v44; // [rsp+B0h] [rbp-50h]
  __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v46; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v50; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v51; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v52; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v53; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v54[8]; // [rsp+100h] [rbp+0h] BYREF
  const wchar_t *v55; // [rsp+108h] [rbp+8h] BYREF
  int v56; // [rsp+110h] [rbp+10h]
  int v57; // [rsp+114h] [rbp+14h]
  __int64 v58; // [rsp+118h] [rbp+18h]
  const wchar_t *v59; // [rsp+120h] [rbp+20h] BYREF
  int v60; // [rsp+128h] [rbp+28h]
  int v61; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v62; // [rsp+130h] [rbp+30h]
  const wchar_t *v63; // [rsp+138h] [rbp+38h] BYREF
  int v64; // [rsp+140h] [rbp+40h]
  int v65; // [rsp+144h] [rbp+44h]
  const wchar_t *v66; // [rsp+148h] [rbp+48h]
  const wchar_t *v67; // [rsp+150h] [rbp+50h] BYREF
  int v68; // [rsp+158h] [rbp+58h]
  int v69; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v70; // [rsp+160h] [rbp+60h]
  const wchar_t *v71; // [rsp+168h] [rbp+68h] BYREF
  int v72; // [rsp+170h] [rbp+70h]
  int v73; // [rsp+174h] [rbp+74h]
  const wchar_t *v74; // [rsp+178h] [rbp+78h]
  const wchar_t *v75; // [rsp+180h] [rbp+80h] BYREF
  int v76; // [rsp+188h] [rbp+88h]
  int v77; // [rsp+18Ch] [rbp+8Ch]
  const wchar_t *v78; // [rsp+190h] [rbp+90h]
  void **v79; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v80[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  void **v81; // [rsp+1A8h] [rbp+A8h]
  void **v82; // [rsp+1B0h] [rbp+B0h]
  int v83; // [rsp+1F8h] [rbp+F8h] BYREF
  int v84; // [rsp+208h] [rbp+108h] BYREF

  v30 = &FrsStringImpl<unsigned short,char>::s_Empty;
  v6 = 0;
  if ( !byte_140315A80 )
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
  FilePath::FilePath((FilePath *)&v34);
  Win32FilePath::Win32FilePath((Win32FilePath *)&v39);
  v81 = &Config::RegReader::`vftable';
  v83 = 0;
  v8 = (struct FrsStatus *)Config::RegReader::ReadReplicaConfigValues(v7, *((_QWORD *)a2 + 18) + 352LL, &v30, &v83, 0);
  v31 = v8;
  if ( v8 )
  {
    if ( !(unsigned int)FrsStatus::IsFileDeletedError(v8)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v55 = L"Config::XmlWriter::WriteReplicaSetConfig";
      v56 = 4221;
      v57 = 4;
      v58 = v13;
      v46 = *((_QWORD *)a2 + 18) + 368LL;
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v55, L"Replica set config file not found. rgId:%?", &v46);
    }
  }
  else
  {
    v9 = *((_QWORD *)a2 + 18);
    v10 = *(_DWORD *)(v9 + 1024);
    if ( v83 != v10 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v41 = L"Config::XmlWriter::WriteReplicaSetConfig";
        v42 = 4207;
        v43 = 2;
        v44 = L"CXML";
        v84 = v10;
        v36 = v83;
        v45 = v9 + 368;
        dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned long,unsigned long>(
          (unsigned int)&v41,
          (unsigned int)L"Can't overwrite Replication Group from different sourcergId:%? oldSource:%? newSource:%?",
          (unsigned int)&v45,
          (unsigned int)&v36,
          (__int64)&v84);
      }
      CurrentThreadId = GetCurrentThreadId();
      v6 = FrsStatusList::PushNewError(
             v12,
             23,
             0,
             3,
             "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
             "Config::XmlWriter::WriteReplicaSetConfig",
             4213,
             CurrentThreadId,
             0);
      goto LABEL_74;
    }
  }
  CLEAR_ERROR(&v31);
  if ( a3 )
  {
    FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v38, *((_QWORD *)a3 + 5) + 18LL);
    FrsStringImpl<unsigned short,char>::Append(v38, L"\\");
    SviDfsrConfigDirectory = (struct FrsStatus *)Win32FilePath::Set(&v39, v38);
    v31 = SviDfsrConfigDirectory;
    FrsStringImpl<char,unsigned short>::ReleaseBody(v38);
  }
  else
  {
    SystemDriveRootDirectory = Util::GetSystemDriveRootDirectory(&v79);
    FrsStringImpl<unsigned short,char>::Set(&v40, SystemDriveRootDirectory + 8);
    v79 = &BaseFilePath::`vftable';
    FrsStringImpl<char,unsigned short>::ReleaseBody(v80);
    SviDfsrConfigDirectory = v31;
  }
  if ( SviDfsrConfigDirectory
    || (SviDfsrConfigDirectory = Config::XmlWriter::CreateSviDfsrConfigDirectory(
                                   v15,
                                   (const struct Win32FilePath *)&v39),
        (v31 = SviDfsrConfigDirectory) != 0) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v59 = L"Config::XmlWriter::WriteReplicaSetConfig";
      v60 = 4263;
      v61 = 3;
      v62 = L"CXML";
      dbgobj::DbgPrint<unsigned short,Win32FilePath,FrsStatus>(
        &v59,
        L"(Ignored) Failed to create the volume's '\\System Volume Information\\DFSR\\Config' directory. volPath:%? Error:%?",
        &v39,
        SviDfsrConfigDirectory);
    }
    CLEAR_ERROR(&v31);
    SviDfsrConfigDirectory = v31;
  }
  FilePath::Set((FilePath *)&v34, (const unsigned __int16 *)(v40 + 18));
  FilePath::Append((FilePath *)&v34, L"System Volume Information");
  FilePath::Append((FilePath *)&v34, L"DFSR");
  FilePath::Append((FilePath *)&v34, L"Config");
  FilePath::Append((FilePath *)&v34, L"Replica_");
  FilePath::operator+=(&v34, *((_QWORD *)a2 + 18) + 368LL);
  FilePath::operator+=(&v34, L".XML");
  if ( SviDfsrConfigDirectory )
    goto LABEL_53;
  if ( !*((_QWORD *)v30 + 1) )
    goto LABEL_56;
  v17 = v35 + 18;
  if ( !(unsigned int)_o__wcsicmp(v30 + 9, v35 + 18) )
    goto LABEL_56;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v63 = L"Config::XmlWriter::WriteReplicaSetConfig";
    v64 = 4297;
    v65 = 4;
    v66 = L"CXML";
    v47 = *((_QWORD *)a2 + 18) + 368LL;
    v48 = v17;
    v49 = v47;
    dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short const *,FrsStringImpl<unsigned short,char>,unsigned short const *>(
      (unsigned int)&v63,
      v18,
      (unsigned int)&v49,
      (unsigned int)&v48,
      (__int64)&v30,
      (__int64)&v47);
  }
  if ( !(unsigned int)Config::BoolParam::Get((Config::BoolParam *)(*((_QWORD *)a2 + 18) + 744LL)) )
    goto LABEL_77;
  v32 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !byte_140315A80 )
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
  FrsStringImpl<unsigned short,char>::Set(
    &v32,
    L"System\\CurrentControlSet\\Services\\DFSR\\Parameters\\Replication Groups");
  FrsStringImpl<unsigned short,char>::Append(&v32, L"\\");
  FrsStringImpl<unsigned short,char>::Append(&v32, *((_QWORD *)a2 + 18) + 368LL);
  SviDfsrConfigDirectory = (struct FrsStatus *)Cluster::ClusterUtil::RemoveRegistryCheckPointForPath(&v30, &v32);
  v31 = SviDfsrConfigDirectory;
  if ( SviDfsrConfigDirectory
    || (FrsStringImpl<unsigned short,char>::Set(
          &v32,
          L"System\\CurrentControlSet\\Services\\DFSR\\Access Checks\\Replication Groups"),
        FrsStringImpl<unsigned short,char>::Append(&v32, L"\\"),
        FrsStringImpl<unsigned short,char>::Append(&v32, *((_QWORD *)a2 + 18) + 368LL),
        SviDfsrConfigDirectory = (struct FrsStatus *)Cluster::ClusterUtil::RemoveRegistryCheckPointForPath(&v30, &v32),
        (v31 = SviDfsrConfigDirectory) != 0) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v67 = L"Config::XmlWriter::WriteReplicaSetConfig";
      v68 = 4331;
      v69 = 3;
      v70 = L"CXML";
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>,FrsStatus>(
        (unsigned int)&v67,
        (unsigned int)L"[CLUSTER] (Ignored) Failed to remove registry check point to resource. path:%? regKey:%? Error:%?",
        (unsigned int)&v30,
        (unsigned int)&v32,
        (__int64)SviDfsrConfigDirectory);
    }
    CLEAR_ERROR(&v31);
    SviDfsrConfigDirectory = v31;
  }
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v32);
  if ( SviDfsrConfigDirectory )
  {
LABEL_53:
    if ( *((_DWORD *)SviDfsrConfigDirectory + 1) == 1 )
    {
      CLEAR_ERROR(&v31);
      SviDfsrConfigDirectory = v31;
    }
    if ( SviDfsrConfigDirectory )
      goto LABEL_73;
  }
  else
  {
LABEL_77:
    if ( DeleteFileW(v30 + 9) )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v71 = L"Config::XmlWriter::WriteReplicaSetConfig";
        v72 = 4342;
        v73 = 4;
        v74 = L"CXML";
        v50 = *((_QWORD *)a2 + 18) + 368LL;
        v51 = v30 + 9;
        dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
          &v71,
          L"Old replica set XML file:%? is deleted. rgId:%?",
          &v51,
          &v50);
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 2
        && g_DebugLog
        && LODWORD(g_DebugLog[1].LockSemaphore)
        && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v75 = L"Config::XmlWriter::WriteReplicaSetConfig";
        v76 = 4350;
        v77 = 3;
        v78 = L"CXML";
        v52 = *((_QWORD *)a2 + 18) + 368LL;
        v53 = v30 + 9;
        dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short const *,unsigned long>(
          (unsigned int)&v75,
          (unsigned int)L"(Ignored) Failed to delete old replica set XML file. filePath:%?. rgId:%?. Error:%?",
          (unsigned int)&v53,
          (unsigned int)&v52,
          (__int64)&LastError);
      }
    }
  }
LABEL_56:
  FrsStringImpl<unsigned short,char>::Set(&v30, v35 + 18);
  SviDfsrConfigDirectory = Config::XmlWriter::WriteReplicaSetConfigFile(this, a2, (struct FilePath *)&v34);
  if ( SviDfsrConfigDirectory )
    goto LABEL_73;
  v82 = &Config::RegWriter::`vftable';
  v19 = Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)a2 + 18) + 784LL));
  FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v54, v19);
  SviDfsrConfigDirectory = (struct FrsStatus *)Config::RegWriter::WriteReplicaConfigValues(
                                                 *((_QWORD *)a2 + 18),
                                                 *((_QWORD *)a2 + 18) + 352LL,
                                                 &v30,
                                                 *((_QWORD *)a2 + 18) + 984LL);
  v31 = SviDfsrConfigDirectory;
  FrsStringImpl<char,unsigned short>::ReleaseBody(v54);
  if ( SviDfsrConfigDirectory )
    goto LABEL_73;
  if ( (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(*((_QWORD *)a2 + 18) + 744LL)) && a3 )
  {
    v33 = &FrsStringImpl<unsigned short,char>::s_Empty;
    if ( !byte_140315A80 )
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    FrsStringImpl<unsigned short,char>::Set(
      &v33,
      L"System\\CurrentControlSet\\Services\\DFSR\\Parameters\\Replication Groups");
    FrsStringImpl<unsigned short,char>::Append(&v33, L"\\");
    FrsStringImpl<unsigned short,char>::Append(&v33, *((_QWORD *)a2 + 18) + 368LL);
    v20 = Cluster::ClusterUtil::AddRegistryCheckPointForPath(&v30, &v33);
    SviDfsrConfigDirectory = (struct FrsStatus *)v20;
    v21 = v20;
    v22 = v20;
    v23 = v20;
    if ( !v20 )
    {
      FrsStringImpl<unsigned short,char>::Set(
        &v33,
        L"System\\CurrentControlSet\\Services\\DFSR\\Access Checks\\Replication Groups");
      FrsStringImpl<unsigned short,char>::Append(&v33, L"\\");
      FrsStringImpl<unsigned short,char>::Append(&v33, *((_QWORD *)a2 + 18) + 368LL);
      v20 = Cluster::ClusterUtil::AddRegistryCheckPointForPath(&v30, &v33);
      SviDfsrConfigDirectory = (struct FrsStatus *)v20;
      v21 = v20;
      v22 = v20;
      v23 = v20;
    }
    if ( v21 )
    {
      if ( *(_DWORD *)(v20 + 4) == 3 )
      {
        Config::XmlConfig::TranslateWin32StatusToConfigFrsStatus(SviDfsrConfigDirectory, 0);
        v22 = v23;
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v41 = L"Config::XmlWriter::WriteReplicaSetConfig";
          v42 = 4417;
          v43 = 2;
          v44 = L"CXML";
          dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>,FrsStatus>(
            (unsigned int)&v41,
            (unsigned int)L"[CLUSTER] Failed to add registry check point to resource. filePath:%? regKey:%?. Error:%?.",
            (unsigned int)&v30,
            (unsigned int)&v33,
            (__int64)SviDfsrConfigDirectory);
        }
        v24 = GetCurrentThreadId();
        v26 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v25,
                                    9198,
                                    0,
                                    3,
                                    "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                    "Config::XmlWriter::WriteReplicaSetConfig",
                                    4422,
                                    v24,
                                    0);
        SviDfsrConfigDirectory = PROPAGATE_ERROR_WITH_NEW_STATUS(SviDfsrConfigDirectory, v26);
        v22 = (__int64)SviDfsrConfigDirectory;
      }
    }
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v33);
    if ( v22 )
    {
LABEL_73:
      v27 = GetCurrentThreadId();
      v6 = FrsStatusList::PushNewError(
             v28,
             *((unsigned int *)SviDfsrConfigDirectory + 1),
             *((unsigned int *)SviDfsrConfigDirectory + 2),
             *(unsigned int *)SviDfsrConfigDirectory,
             "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
             "Config::XmlWriter::WriteReplicaSetConfig",
             4431,
             v27,
             SviDfsrConfigDirectory);
    }
  }
LABEL_74:
  v39 = &BaseFilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v40);
  v34 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v35);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v30);
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x140064360  mov     [rsp-8+arg_0], rbx
0x140064365  mov     [rsp-8+arg_10], rsi
0x14006436a  push    rbp
0x14006436b  push    rdi
0x14006436c  push    r12
0x14006436e  push    r13
0x140064370  push    r15
0x140064372  lea     rbp, [rsp-0C0h]
0x14006437a  sub     rsp, 1C0h
0x140064381  mov     r15, r8
0x140064384  mov     rsi, rdx
0x140064387  mov     r12, rcx
0x14006438a  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140064391  mov     [rsp+1E0h+var_190], rax
0x140064396  xor     ebx, ebx
0x140064398  cmp     cs:byte_140315A80, bl
0x14006439e  jnz     short loc_1400643A7
0x1400643a0  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400643a7  lea     rcx, [rsp+1E0h+var_170]; this
0x1400643ac  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x1400643b1  nop
0x1400643b2  lea     rcx, [rbp+0E0h+var_150]; this
0x1400643b6  call    ??0Win32FilePath@@QEAA@XZ; Win32FilePath::Win32FilePath(void)
0x1400643bb  nop
0x1400643bc  lea     rax, ??_7RegReader@Config@@6B@; const Config::RegReader::`vftable'
0x1400643c3  mov     [rbp+0E0h+var_38], rax
0x1400643ca  mov     [rbp+0E0h+arg_8], ebx
0x1400643d0  mov     rdx, [rsi+90h]
0x1400643d7  add     rdx, 160h
0x1400643de  mov     [rsp+1E0h+var_1C0], rbx
0x1400643e3  lea     r9, [rbp+0E0h+arg_8]
0x1400643ea  lea     r8, [rsp+1E0h+var_190]
0x1400643ef  call    ?ReadReplicaConfigValues@RegReader@Config@@QEAAPEAVFrsStatus@@PEBU_GUID@@PEAV?$FrsStringImpl@GD@@PEAW4_FRS_CONFIG_SOURCE@@1@Z; Config::RegReader::ReadReplicaConfigValues(_GUID const *,FrsStringImpl<ushort,char> *,_FRS_CONFIG_SOURCE *,FrsStringImpl<ushort,char> *)
0x1400643f4  mov     [rsp+1E0h+var_188], rax
0x1400643f9  lea     rdi, ??_7BaseFilePath@@6B@; const BaseFilePath::`vftable'
0x140064400  lea     r13, aConfigXmlwrite_10; "Config::XmlWriter::WriteReplicaSetConfi"...
0x140064407  lea     r9, aCxml; "CXML"
0x14006440e  test    rax, rax
0x140064411  jnz     loc_1400644E9
0x140064417  mov     rcx, [rsi+90h]
0x14006441e  mov     edx, [rcx+400h]
0x140064424  mov     r8d, [rbp+0E0h+arg_8]
0x14006442b  cmp     r8d, edx
0x14006442e  jz      loc_140064547
0x140064434  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14006443b  test    rax, rax
0x14006443e  jz      short loc_14006449A
0x140064440  cmp     [rax+40h], ebx
0x140064443  jz      short loc_14006449A
0x140064445  cmp     dword ptr [rax+38h], 2
0x140064449  jl      short loc_14006449A
0x14006444b  mov     [rbp+0E0h+var_140], r13
0x14006444f  mov     [rbp+0E0h+var_138], 106Fh
0x140064456  mov     [rbp+0E0h+var_134], 2
0x14006445d  mov     [rbp+0E0h+var_130], r9
0x140064461  mov     [rbp+0E0h+arg_18], edx
0x140064467  mov     [rbp+0E0h+var_160], r8d
0x14006446b  lea     rax, [rcx+170h]
0x140064472  mov     [rbp+0E0h+var_128], rax
0x140064476  lea     rax, [rbp+0E0h+arg_18]
0x14006447d  mov     [rsp+1E0h+var_1C0], rax
0x140064482  lea     r9, [rbp+0E0h+var_160]
0x140064486  lea     r8, [rbp+0E0h+var_128]
0x14006448a  lea     rdx, aCanTOverwriteR; "Can't overwrite Replication Group from "...
0x140064491  lea     rcx, [rbp+0E0h+var_140]
0x140064495  call    ??$DbgPrint@GPEBGKK@dbgobj@@QEAA_KPEBGAEBQEBGAEBK2@Z; dbgobj::DbgPrint<ushort,ushort const *,ulong,ulong>(ushort const *,ushort const * const &,ulong const &,ulong const &)
0x14006449a  call    cs:__imp_GetCurrentThreadId
0x1400644a1  nop     dword ptr [rax+rax+00h]
0x1400644a6  mov     [rsp+1E0h+var_1A0], rbx
0x1400644ab  mov     [rsp+1E0h+var_1A8], eax
0x1400644af  mov     dword ptr [rsp+1E0h+var_1B0], 1075h
0x1400644b7  lea     r13, aConfigXmlwrite_15; "Config::XmlWriter::WriteReplicaSetConfi"...
0x1400644be  mov     [rsp+1E0h+var_1B8], r13
0x1400644c3  lea     rax, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x1400644ca  mov     [rsp+1E0h+var_1C0], rax
0x1400644cf  mov     r9d, 3
0x1400644d5  xor     r8d, r8d
0x1400644d8  lea     edx, [r9+14h]
0x1400644dc  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400644e1  mov     rbx, rax
0x1400644e4  jmp     loc_140064D05
0x1400644e9  mov     rcx, rax; this
0x1400644ec  call    ?IsFileDeletedError@FrsStatus@@QEBAHXZ; FrsStatus::IsFileDeletedError(void)
0x1400644f1  test    eax, eax
0x1400644f3  jnz     short loc_140064547
0x1400644f5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400644fc  test    rax, rax
0x1400644ff  jz      short loc_140064547
0x140064501  cmp     [rax+40h], ebx
0x140064504  jz      short loc_140064547
0x140064506  cmp     dword ptr [rax+38h], 4
0x14006450a  jl      short loc_140064547
0x14006450c  mov     [rbp+0E0h+var_D8], r13
0x140064510  mov     [rbp+0E0h+var_D0], 107Dh
0x140064517  mov     [rbp+0E0h+var_CC], 4
0x14006451e  mov     [rbp+0E0h+var_C8], r9
0x140064522  mov     rax, [rsi+90h]
0x140064529  add     rax, 170h
0x14006452f  mov     [rbp+0E0h+var_120], rax
0x140064533  lea     r8, [rbp+0E0h+var_120]
0x140064537  lea     rdx, aReplicaSetConf; "Replica set config file not found. rgId"...
0x14006453e  lea     rcx, [rbp+0E0h+var_D8]
0x140064542  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140064547  lea     rcx, [rsp+1E0h+var_188]; struct FrsStatus **
0x14006454c  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140064551  test    r15, r15
0x140064554  jz      short loc_140064598
0x140064556  mov     rdx, [r15+28h]
0x14006455a  add     rdx, 12h
0x14006455e  lea     rcx, [rbp+0E0h+var_158]
0x140064562  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x140064567  nop
0x140064568  lea     rdx, Delimiter; "\\"
0x14006456f  lea     rcx, [rbp+0E0h+var_158]
0x140064573  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x140064578  lea     rdx, [rbp+0E0h+var_158]
0x14006457c  lea     rcx, [rbp+0E0h+var_150]
0x140064580  call    ?Set@Win32FilePath@@QEAAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@@Z; Win32FilePath::Set(FrsStringImpl<ushort,char> const &)
0x140064585  mov     rdi, rax
0x140064588  mov     [rsp+1E0h+var_188], rax
0x14006458d  lea     rcx, [rbp+0E0h+var_158]
0x140064591  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140064596  jmp     short loc_1400645C9
0x140064598  lea     rcx, [rbp+0E0h+var_48]
0x14006459f  call    ?GetSystemDriveRootDirectory@Util@@YA?AVWin32FilePath@@XZ; Util::GetSystemDriveRootDirectory(void)
0x1400645a4  lea     rdx, [rax+8]
0x1400645a8  lea     rcx, [rbp+0E0h+var_148]
0x1400645ac  call    ?Set@?$FrsStringImpl@GD@@QEAA_NAEBV1@@Z; FrsStringImpl<ushort,char>::Set(FrsStringImpl<ushort,char> const &)
0x1400645b1  mov     [rbp+0E0h+var_48], rdi
0x1400645b8  lea     rcx, [rbp+0E0h+var_40]
0x1400645bf  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400645c4  mov     rdi, [rsp+1E0h+var_188]
0x1400645c9  test    rdi, rdi
0x1400645cc  jnz     short loc_1400645E4
0x1400645ce  lea     rdx, [rbp+0E0h+var_150]; struct Win32FilePath *
0x1400645d2  call    ?CreateSviDfsrConfigDirectory@XmlWriter@Config@@IEAAPEAVFrsStatus@@AEBVWin32FilePath@@@Z; Config::XmlWriter::CreateSviDfsrConfigDirectory(Win32FilePath const &)
0x1400645d7  mov     rdi, rax
0x1400645da  mov     [rsp+1E0h+var_188], rax
0x1400645df  test    rax, rax
0x1400645e2  jz      short loc_14006463E
0x1400645e4  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400645eb  test    rax, rax
0x1400645ee  jz      short loc_14006462F
0x1400645f0  cmp     [rax+40h], ebx
0x1400645f3  jz      short loc_14006462F
0x1400645f5  cmp     dword ptr [rax+38h], 3
0x1400645f9  jl      short loc_14006462F
0x1400645fb  mov     [rbp+0E0h+var_C0], r13
0x1400645ff  mov     [rbp+0E0h+var_B8], 10A7h
0x140064606  mov     [rbp+0E0h+var_B4], 3
0x14006460d  lea     rax, aCxml; "CXML"
0x140064614  mov     [rbp+0E0h+var_B0], rax
0x140064618  mov     r9, rdi
0x14006461b  lea     r8, [rbp+0E0h+var_150]
0x14006461f  lea     rdx, aIgnoredFailedT_69; "(Ignored) Failed to create the volume's"...
0x140064626  lea     rcx, [rbp+0E0h+var_C0]
0x14006462a  call    ??$DbgPrint@GVWin32FilePath@@VFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVWin32FilePath@@AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,Win32FilePath,FrsStatus>(ushort const *,Win32FilePath const &,FrsStatus const &)
0x14006462f  lea     rcx, [rsp+1E0h+var_188]; struct FrsStatus **
0x140064634  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140064639  mov     rdi, [rsp+1E0h+var_188]
0x14006463e  mov     rdx, [rbp+0E0h+var_148]
0x140064642  add     rdx, 12h; unsigned __int16 *
0x140064646  lea     rcx, [rsp+1E0h+var_170]; this
0x14006464b  call    ?Set@FilePath@@QEAAXPEBG@Z; FilePath::Set(ushort const *)
0x140064650  lea     rdx, aSystemVolumeIn_0; "System Volume Information"
0x140064657  lea     rcx, [rsp+1E0h+var_170]; this
0x14006465c  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x140064661  lea     rdx, SourceName; "DFSR"
0x140064668  lea     rcx, [rsp+1E0h+var_170]; this
0x14006466d  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x140064672  lea     rdx, aConfig; "Config"
0x140064679  lea     rcx, [rsp+1E0h+var_170]; this
0x14006467e  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x140064683  lea     rdx, aReplica; "Replica_"
0x14006468a  lea     rcx, [rsp+1E0h+var_170]; this
0x14006468f  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x140064694  mov     rdx, [rsi+90h]
0x14006469b  add     rdx, 170h
0x1400646a2  lea     rcx, [rsp+1E0h+var_170]
0x1400646a7  call    ??YFilePath@@QEAAAEAV0@PEBG@Z; FilePath::operator+=(ushort const *)
0x1400646ac  lea     rdx, aXml; ".XML"
0x1400646b3  lea     rcx, [rsp+1E0h+var_170]
0x1400646b8  call    ??YFilePath@@QEAAAEAV0@PEBG@Z; FilePath::operator+=(ushort const *)
0x1400646bd  lea     r13, aConfigXmlwrite_15; "Config::XmlWriter::WriteReplicaSetConfi"...
0x1400646c4  test    rdi, rdi
0x1400646c7  jnz     loc_140064A24
0x1400646cd  mov     rax, [rsp+1E0h+var_190]
0x1400646d2  cmp     [rax+8], rbx
0x1400646d6  jbe     loc_140064A42
0x1400646dc  mov     rdi, [rsp+1E0h+var_168]
0x1400646e1  add     rdi, 12h
0x1400646e5  lea     rcx, [rax+12h]
0x1400646e9  mov     rdx, rdi
0x1400646ec  call    cs:__imp__o__wcsicmp
0x1400646f3  nop     dword ptr [rax+rax+00h]
0x1400646f8  test    eax, eax
0x1400646fa  jz      loc_140064A42
0x140064700  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140064707  test    rax, rax
0x14006470a  jz      short loc_140064778
0x14006470c  cmp     [rax+40h], ebx
0x14006470f  jz      short loc_140064778
0x140064711  cmp     dword ptr [rax+38h], 4
0x140064715  jl      short loc_140064778
0x140064717  lea     rax, aConfigXmlwrite_10; "Config::XmlWriter::WriteReplicaSetConfi"...
0x14006471e  mov     [rbp+0E0h+var_A8], rax
0x140064722  mov     [rbp+0E0h+var_A0], 10C9h
0x140064729  mov     [rbp+0E0h+var_9C], 4
0x140064730  lea     rax, aCxml; "CXML"
0x140064737  mov     [rbp+0E0h+var_98], rax
0x14006473b  mov     rax, [rsi+90h]
0x140064742  add     rax, 170h
0x140064748  mov     [rbp+0E0h+var_118], rax
0x14006474c  mov     [rbp+0E0h+var_110], rdi
0x140064750  mov     [rbp+0E0h+var_108], rax
0x140064754  lea     rax, [rbp+0E0h+var_118]
0x140064758  mov     [rsp+1E0h+var_1B8], rax
0x14006475d  lea     rax, [rsp+1E0h+var_190]
0x140064762  mov     [rsp+1E0h+var_1C0], rax
0x140064767  lea     r9, [rbp+0E0h+var_110]
0x14006476b  lea     r8, [rbp+0E0h+var_108]
0x14006476f  lea     rcx, [rbp+0E0h+var_A8]
0x140064773  call    ??$DbgPrint@GPEBGPEBGV?$FrsStringImpl@GD@@PEBG@dbgobj@@QEAA_KPEBGAEBQEBG1AEBV?$FrsStringImpl@GD@@1@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort const *,FrsStringImpl<ushort,char>,ushort const *>(ushort const *,ushort const * const &,ushort const * const &,FrsStringImpl<ushort,char> const &,ushort const * const &)
0x140064778  mov     rcx, [rsi+90h]
0x14006477f  add     rcx, 2E8h; this
0x140064786  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14006478b  test    eax, eax
0x14006478d  jz      loc_1400648D6
0x140064793  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x14006479a  mov     [rsp+1E0h+var_180], rax
0x14006479f  cmp     cs:byte_140315A80, bl
0x1400647a5  jnz     short loc_1400647AE
0x1400647a7  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400647ae  lea     rdx, aSystemCurrentc_11; "System\\CurrentControlSet\\Services\\DF"...
0x1400647b5  lea     rcx, [rsp+1E0h+var_180]
0x1400647ba  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1400647bf  lea     rdx, Delimiter; "\\"
0x1400647c6  lea     rcx, [rsp+1E0h+var_180]
0x1400647cb  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x1400647d0  mov     rdx, [rsi+90h]
0x1400647d7  add     rdx, 170h
0x1400647de  lea     rcx, [rsp+1E0h+var_180]
0x1400647e3  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x1400647e8  lea     rdx, [rsp+1E0h+var_180]
0x1400647ed  lea     rcx, [rsp+1E0h+var_190]
0x1400647f2  call    ?RemoveRegistryCheckPointForPath@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@0@Z; Cluster::ClusterUtil::RemoveRegistryCheckPointForPath(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x1400647f7  mov     rdi, rax
0x1400647fa  mov     [rsp+1E0h+var_188], rax
0x1400647ff  test    rax, rax
0x140064802  jnz     short loc_14006485A
0x140064804  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\DF"...
0x14006480b  lea     rcx, [rsp+1E0h+var_180]
0x140064810  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x140064815  lea     rdx, Delimiter; "\\"
0x14006481c  lea     rcx, [rsp+1E0h+var_180]
0x140064821  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x140064826  mov     rdx, [rsi+90h]
0x14006482d  add     rdx, 170h
0x140064834  lea     rcx, [rsp+1E0h+var_180]
0x140064839  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x14006483e  lea     rdx, [rsp+1E0h+var_180]
0x140064843  lea     rcx, [rsp+1E0h+var_190]
0x140064848  call    ?RemoveRegistryCheckPointForPath@ClusterUtil@Cluster@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@0@Z; Cluster::ClusterUtil::RemoveRegistryCheckPointForPath(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &)
0x14006484d  mov     rdi, rax
0x140064850  mov     [rsp+1E0h+var_188], rax
0x140064855  test    rax, rax
0x140064858  jz      short loc_1400648C3
0x14006485a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140064861  test    rax, rax
0x140064864  jz      short loc_1400648B4
0x140064866  cmp     [rax+40h], ebx
0x140064869  jz      short loc_1400648B4
0x14006486b  cmp     dword ptr [rax+38h], 3
0x14006486f  jl      short loc_1400648B4
0x140064871  lea     rax, aConfigXmlwrite_10; "Config::XmlWriter::WriteReplicaSetConfi"...
0x140064878  mov     [rbp+0E0h+var_90], rax
0x14006487c  mov     [rbp+0E0h+var_88], 10EBh
0x140064883  mov     [rbp+0E0h+var_84], 3
0x14006488a  lea     rax, aCxml; "CXML"
0x140064891  mov     [rbp+0E0h+var_80], rax
0x140064895  mov     [rsp+1E0h+var_1C0], rdi
0x14006489a  lea     r9, [rsp+1E0h+var_180]
0x14006489f  lea     r8, [rsp+1E0h+var_190]
0x1400648a4  lea     rdx, aClusterIgnored_41; "[CLUSTER] (Ignored) Failed to remove re"...
0x1400648ab  lea     rcx, [rbp+0E0h+var_90]
0x1400648af  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@V1@VFrsStatus@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@1AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,FrsStringImpl<ushort,char>,FrsStatus>(ushort const *,FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> const &,FrsStatus const &)
0x1400648b4  lea     rcx, [rsp+1E0h+var_188]; struct FrsStatus **
0x1400648b9  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400648be  mov     rdi, [rsp+1E0h+var_188]
0x1400648c3  lea     rcx, [rsp+1E0h+var_180]
0x1400648c8  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400648cd  test    rdi, rdi
0x1400648d0  jnz     loc_140064A24
0x1400648d6  mov     rcx, [rsp+1E0h+var_190]
0x1400648db  add     rcx, 12h; lpFileName
0x1400648df  call    cs:__imp_DeleteFileW
0x1400648e6  nop     dword ptr [rax+rax+00h]
0x1400648eb  test    eax, eax
0x1400648ed  jz      loc_140064975
0x1400648f3  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
  ... truncated ...
```
