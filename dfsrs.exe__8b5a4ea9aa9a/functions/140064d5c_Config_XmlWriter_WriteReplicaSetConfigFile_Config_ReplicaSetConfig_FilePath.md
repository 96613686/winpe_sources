# Config::XmlWriter::WriteReplicaSetConfigFile(Config::ReplicaSetConfig *,FilePath *)

- ea: `0x140064d5c`
- end: `0x1400651c1`
- name: `?WriteReplicaSetConfigFile@XmlWriter@Config@@QEAAPEAVFrsStatus@@PEAVReplicaSetConfig@2@PEAVFilePath@@@Z`
- size: `1125`
- prototype: `struct FrsStatus *__fastcall(Config::XmlWriter *__hidden this, struct Config::ReplicaSetConfig *, struct FilePath *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140064360`

## callees

- `0x14000be44`
- `0x14000cd1c`
- `0x14000e34c`
- `0x14000ee94`
- `0x14001a5cc`
- `0x14001a940`
- `0x14001cfa0`
- `0x1400255c8`
- `0x140047e14`
- `0x140048b44`
- `0x140048f2c`
- `0x14004d52c`
- `0x14005cb30`
- `0x14005e8ac`
- `0x1400615b8`
- `0x140062770`
- `0x140063ec8`
- `0x140064d5c`
- `0x1400c0a7c`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140064fb6`
- `KERNEL32!DeleteFileW` at `0x140064fb6`
- `KERNEL32!MoveFileExW` at `0x140064f4c`
- `KERNEL32!MoveFileExW` at `0x140064f4c`
- `KERNEL32!GetLastError` at `0x140064f6e`
- `KERNEL32!GetLastError` at `0x140064f6e`
- `KERNEL32!GetCurrentThreadId` at `0x140064f60`
- `KERNEL32!GetCurrentThreadId` at `0x14006506d`
- `KERNEL32!GetCurrentThreadId` at `0x140065169`
- `KERNEL32!GetCurrentThreadId` at `0x140064f60`
- `KERNEL32!GetCurrentThreadId` at `0x14006506d`
- `KERNEL32!GetCurrentThreadId` at `0x140065169`

## string_xrefs

- `0x140064dcf`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140064f97`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140065039`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140065192`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140065158`: `Failed to stamp default ACLs on %?`
- `0x140065016`: `Failed to SaveFileEx(). filePath:%?`
- `0x140064dfe`: `Config::XmlWriter::WriteReplicaSetConfigFile`
- `0x140064e53`: `Reading old replica config file at path:%?`
- `0x140064dc8`: `Config::XmlWriter::WriteReplicaSetConfigFile`
- `0x140064f8b`: `Config::XmlWriter::WriteReplicaSetConfigFile`
- `0x140065061`: `Config::XmlWriter::WriteReplicaSetConfigFile`
- `0x140065186`: `Config::XmlWriter::WriteReplicaSetConfigFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct FrsStatus *__fastcall Config::XmlWriter::WriteReplicaSetConfigFile(
        Config::XmlWriter *this,
        struct Config::ReplicaSetConfig *a2,
        struct FilePath *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rdx
  const unsigned __int16 *v8; // rdx
  struct FrsStatus *Document; // rbx
  struct FrsStatus *ReplicaSetConfigFile; // rax
  int v11; // eax
  int v12; // edx
  const WCHAR *v13; // r14
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  DWORD v16; // eax
  __int64 v17; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  struct FrsStatus *v21; // rax
  const unsigned __int16 *v22; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v23; // [rsp+28h] [rbp-D8h]
  const wchar_t *v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v27; // [rsp+60h] [rbp-A0h]
  void **v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  void **v30; // [rsp+78h] [rbp-88h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  void **v32; // [rsp+88h] [rbp-78h] BYREF
  int v33; // [rsp+90h] [rbp-70h]
  _BYTE v34[144]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+130h] [rbp+30h]
  __int64 v36; // [rsp+188h] [rbp+88h] BYREF
  struct FrsStatus *v37; // [rsp+198h] [rbp+98h] BYREF

  v6 = 0;
  v31 = 0;
  v30 = &Config::XmlDocument::`vftable';
  v29 = 0;
  v28 = &Config::XmlElement::`vftable';
  v7 = *((_QWORD *)a2 + 2);
  if ( v7 )
    v8 = *(const unsigned __int16 **)(v7 + 8);
  else
    v8 = 0;
  Document = Config::XmlConfig::CreateDocument(
               this,
               v8,
               (struct Config::XmlDocument *)&v30,
               (struct Config::XmlElement *)&v28,
               v22,
               v23);
  if ( !Document )
  {
    Config::ReplicaSetConfig::ReplicaSetConfig(v34, 0);
    v33 = 1;
    v32 = &Config::XmlReader::`vftable';
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v24 = L"Config::XmlWriter::WriteReplicaSetConfigFile";
      v25 = 4460;
      v26 = 4;
      v27 = L"CXML";
      v36 = *((_QWORD *)a3 + 1) + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v24, L"Reading old replica config file at path:%?", &v36);
    }
    ReplicaSetConfigFile = Config::XmlReader::ReadReplicaSetConfigFile(
                             (Config::XmlReader *)&v32,
                             (struct Config::ReplicaSetConfig *)v34,
                             a3);
    v37 = ReplicaSetConfigFile;
    if ( !ReplicaSetConfigFile || (unsigned int)IsConfigParamFrsStatusError(ReplicaSetConfigFile) )
    {
      v11 = Config::BoolParam::Get((Config::BoolParam *)(v35 + 112));
      Config::DWordParam::Set((Config::DWordParam *)(*((_QWORD *)a2 + 18) + 112LL), v11 + 1);
    }
    Config::DateTimeParam::SetCurrentTime((Config::DateTimeParam *)(*((_QWORD *)a2 + 18) + 152LL));
    Config::XmlConfig::WriteParamList(
      this,
      (struct Config::ReplicaSetConfig *)((char *)a2 + 32),
      (struct Config::XmlElement *)&v28);
    CLEAR_ERROR(&v37);
    FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(&v36, *((_QWORD *)a3 + 1) + 18LL);
    FrsStringImpl<unsigned short,char>::Append(&v36, L".TMP");
    Document = v37;
    if ( !v37 )
    {
      v13 = (const WCHAR *)(v36 + 18);
      Document = Config::XmlDocument::SaveFileEx((Config::XmlDocument *)&v30, (const unsigned __int16 *)(v36 + 18));
      if ( !Document )
      {
        if ( MoveFileExW(v13, (LPCWSTR)(*((_QWORD *)a3 + 1) + 18LL), 1u) )
          goto LABEL_25;
        CurrentThreadId = GetCurrentThreadId();
        LastError = GetLastError();
        Document = (struct FrsStatus *)FrsStatusList::PushNewError(
                                         "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                         LastError,
                                         0,
                                         1,
                                         "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                         "Config::XmlWriter::WriteReplicaSetConfigFile",
                                         4501,
                                         CurrentThreadId,
                                         0);
        DeleteFileW(v13);
        if ( !Document )
          goto LABEL_25;
      }
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v24 = L"Config::XmlWriter::WriteReplicaSetConfigFile";
      v25 = 4507;
      v26 = 2;
      v27 = L"CXML";
      v37 = (struct FrsStatus *)(*((_QWORD *)a3 + 1) + 18LL);
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v24, L"Failed to SaveFileEx(). filePath:%?", &v37);
    }
    if ( !Document )
    {
LABEL_25:
      Document = FileUtil::RestrictAccessToFileOrDirectory(
                   (const unsigned __int16 *)(*((_QWORD *)a3 + 1) + 18LL),
                   v12,
                   0);
      if ( Document )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v24 = L"Config::XmlWriter::WriteReplicaSetConfigFile";
          v25 = 4521;
          v26 = 2;
          v27 = L"CXML";
          v37 = (struct FrsStatus *)(*((_QWORD *)a3 + 1) + 18LL);
          dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v24, L"Failed to stamp default ACLs on %?", &v37);
        }
        v19 = GetCurrentThreadId();
        v21 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v20,
                                    5,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                    "Config::XmlWriter::WriteReplicaSetConfigFile",
                                    4522,
                                    v19,
                                    0);
        Document = PROPAGATE_ERROR_WITH_NEW_STATUS(Document, v21);
      }
    }
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v36);
    v32 = &Config::XmlConfig::`vftable';
    Config::ReplicaSetConfig::~ReplicaSetConfig((Config::ReplicaSetConfig *)v34);
  }
  if ( Document )
  {
    v16 = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v17,
           *((unsigned int *)Document + 1),
           *((unsigned int *)Document + 2),
           *(unsigned int *)Document,
           "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
           "Config::XmlWriter::WriteReplicaSetConfigFile",
           4528,
           v16,
           Document);
  }
  v28 = &Config::XmlNodeType<IXMLDOMElement>::`vftable';
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  v30 = &Config::XmlNodeType<IXMLDOMDocument>::`vftable';
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x140064d5c  mov     [rsp-8+arg_0], rbx
0x140064d61  push    rbp
0x140064d62  push    rsi
0x140064d63  push    rdi
0x140064d64  push    r12
0x140064d66  push    r13
0x140064d68  push    r14
0x140064d6a  push    r15
0x140064d6c  lea     rbp, [rsp-40h]
0x140064d71  sub     rsp, 140h
0x140064d78  mov     rsi, r8
0x140064d7b  mov     r14, rdx
0x140064d7e  mov     r15, rcx
0x140064d81  xor     edi, edi
0x140064d83  mov     [rbp+70h+var_F0], rdi
0x140064d87  lea     rax, ??_7XmlDocument@Config@@6B@; const Config::XmlDocument::`vftable'
0x140064d8e  mov     [rsp+170h+var_F8], rax
0x140064d93  mov     [rsp+170h+var_100], rdi
0x140064d98  lea     rax, ??_7XmlElement@Config@@6B@; const Config::XmlElement::`vftable'
0x140064d9f  mov     [rsp+170h+var_108], rax
0x140064da4  mov     rdx, [rdx+10h]
0x140064da8  test    rdx, rdx
0x140064dab  jz      short loc_140064DB3
0x140064dad  mov     rdx, [rdx+8]
0x140064db1  jmp     short loc_140064DB6
0x140064db3  mov     rdx, rdi; unsigned __int16 *
0x140064db6  lea     r9, [rsp+170h+var_108]; struct Config::XmlElement *
0x140064dbb  lea     r8, [rsp+170h+var_F8]; struct Config::XmlDocument *
0x140064dc0  call    ?CreateDocument@XmlConfig@Config@@QEAAPEAVFrsStatus@@PEBGAEAVXmlDocument@2@AEAVXmlElement@2@00@Z; Config::XmlConfig::CreateDocument(ushort const *,Config::XmlDocument &,Config::XmlElement &,ushort const *,ushort const *)
0x140064dc5  mov     rbx, rax
0x140064dc8  lea     r12, aConfigXmlwrite_11; "Config::XmlWriter::WriteReplicaSetConfi"...
0x140064dcf  lea     r13, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140064dd6  test    rax, rax
0x140064dd9  jnz     loc_140065068
0x140064ddf  xor     edx, edx
0x140064de1  lea     rcx, [rbp+70h+var_D0]
0x140064de5  call    ??0ReplicaSetConfig@Config@@QEAA@W4_FRS_CONFIG_SOURCE@@@Z; Config::ReplicaSetConfig::ReplicaSetConfig(_FRS_CONFIG_SOURCE)
0x140064dea  nop
0x140064deb  lea     r12d, [rbx+1]
0x140064def  mov     [rbp+70h+var_E0], r12d
0x140064df3  lea     rax, ??_7XmlReader@Config@@6B@; const Config::XmlReader::`vftable'
0x140064dfa  mov     [rbp+70h+var_E8], rax
0x140064dfe  lea     r13, aConfigXmlwrite; "Config::XmlWriter::WriteReplicaSetConfi"...
0x140064e05  lea     rcx, aCxml; "CXML"
0x140064e0c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140064e13  test    rax, rax
0x140064e16  jz      short loc_140064E64
0x140064e18  cmp     [rax+40h], edi
0x140064e1b  jz      short loc_140064E64
0x140064e1d  cmp     dword ptr [rax+38h], 4
0x140064e21  jl      short loc_140064E64
0x140064e23  mov     [rsp+170h+var_120], r13
0x140064e28  mov     [rsp+170h+var_118], 116Ch
0x140064e30  mov     [rsp+170h+var_114], 4
0x140064e38  mov     [rsp+170h+var_110], rcx
0x140064e3d  mov     rax, [rsi+8]
0x140064e41  add     rax, 12h
0x140064e45  mov     [rbp+70h+arg_8], rax
0x140064e4c  lea     r8, [rbp+70h+arg_8]
0x140064e53  lea     rdx, aReadingOldRepl; "Reading old replica config file at path"...
0x140064e5a  lea     rcx, [rsp+170h+var_120]
0x140064e5f  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140064e64  mov     r8, rsi; struct FilePath *
0x140064e67  lea     rdx, [rbp+70h+var_D0]; struct Config::ReplicaSetConfig *
0x140064e6b  lea     rcx, [rbp+70h+var_E8]; this
0x140064e6f  call    ?ReadReplicaSetConfigFile@XmlReader@Config@@QEAAPEAVFrsStatus@@PEAVReplicaSetConfig@2@PEAVFilePath@@@Z; Config::XmlReader::ReadReplicaSetConfigFile(Config::ReplicaSetConfig *,FilePath *)
0x140064e74  mov     [rbp+70h+arg_18], rax
0x140064e7b  test    rax, rax
0x140064e7e  jz      short loc_140064E8C
0x140064e80  mov     rcx, rax; struct FrsStatus *
0x140064e83  call    ?IsConfigParamFrsStatusError@@YAHPEAVFrsStatus@@@Z; IsConfigParamFrsStatusError(FrsStatus *)
0x140064e88  test    eax, eax
0x140064e8a  jz      short loc_140064EAC
0x140064e8c  mov     rcx, [rbp+70h+var_40]
0x140064e90  add     rcx, 70h ; 'p'; this
0x140064e94  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140064e99  lea     edx, [rax+1]; unsigned int
0x140064e9c  mov     rcx, [r14+90h]
0x140064ea3  add     rcx, 70h ; 'p'; this
0x140064ea7  call    ?Set@DWordParam@Config@@QEAAHK@Z; Config::DWordParam::Set(ulong)
0x140064eac  mov     rcx, [r14+90h]
0x140064eb3  add     rcx, 98h; this
0x140064eba  call    ?SetCurrentTime@DateTimeParam@Config@@QEAAXXZ; Config::DateTimeParam::SetCurrentTime(void)
0x140064ebf  lea     rdx, [r14+20h]; struct Config::ParamList *
0x140064ec3  lea     r8, [rsp+170h+var_108]; struct Config::XmlElement *
0x140064ec8  mov     rcx, r15; this
0x140064ecb  call    ?WriteParamList@XmlConfig@Config@@IEAAXPEBVParamList@2@AEAVXmlElement@2@@Z; Config::XmlConfig::WriteParamList(Config::ParamList const *,Config::XmlElement &)
0x140064ed0  lea     rcx, [rbp+70h+arg_18]; struct FrsStatus **
0x140064ed7  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140064edc  mov     rdx, [rsi+8]
0x140064ee0  add     rdx, 12h
0x140064ee4  lea     rcx, [rbp+70h+arg_8]
0x140064eeb  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x140064ef0  nop
0x140064ef1  lea     rdx, aTmp_0; ".TMP"
0x140064ef8  lea     rcx, [rbp+70h+arg_8]
0x140064eff  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x140064f04  mov     r15d, 2
0x140064f0a  mov     rbx, [rbp+70h+arg_18]
0x140064f11  test    rbx, rbx
0x140064f14  jnz     loc_140064FCB
0x140064f1a  mov     r14, [rbp+70h+arg_8]
0x140064f21  add     r14, 12h
0x140064f25  mov     rdx, r14; unsigned __int16 *
0x140064f28  lea     rcx, [rsp+170h+var_F8]; this
0x140064f2d  call    ?SaveFileEx@XmlDocument@Config@@QEAAPEAVFrsStatus@@PEBG@Z; Config::XmlDocument::SaveFileEx(ushort const *)
0x140064f32  mov     rbx, rax
0x140064f35  test    rax, rax
0x140064f38  jnz     loc_140064FCB
0x140064f3e  mov     rdx, [rsi+8]
0x140064f42  add     rdx, 12h; lpNewFileName
0x140064f46  mov     r8d, r12d; dwFlags
0x140064f49  mov     rcx, r14; lpExistingFileName
0x140064f4c  call    cs:__imp_MoveFileExW
0x140064f53  nop     dword ptr [rax+rax+00h]
0x140064f58  test    eax, eax
0x140064f5a  jnz     loc_1400650F1
0x140064f60  call    cs:__imp_GetCurrentThreadId
0x140064f67  nop     dword ptr [rax+rax+00h]
0x140064f6c  mov     ebx, eax
0x140064f6e  call    cs:__imp_GetLastError
0x140064f75  nop     dword ptr [rax+rax+00h]
0x140064f7a  mov     [rsp+170h+var_130], rdi
0x140064f7f  mov     [rsp+170h+var_138], ebx
0x140064f83  mov     [rsp+170h+var_140], 1195h
0x140064f8b  lea     rcx, aConfigXmlwrite_11; "Config::XmlWriter::WriteReplicaSetConfi"...
0x140064f92  mov     [rsp+170h+var_148], rcx
0x140064f97  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140064f9e  mov     [rsp+170h+var_150], rcx
0x140064fa3  mov     r9d, r12d
0x140064fa6  xor     r8d, r8d
0x140064fa9  mov     edx, eax
0x140064fab  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140064fb0  mov     rbx, rax
0x140064fb3  mov     rcx, r14; lpFileName
0x140064fb6  call    cs:__imp_DeleteFileW
0x140064fbd  nop     dword ptr [rax+rax+00h]
0x140064fc2  test    rbx, rbx
0x140064fc5  jz      loc_1400650F1
0x140064fcb  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140064fd2  test    rax, rax
0x140064fd5  jz      short loc_140065029
0x140064fd7  cmp     [rax+40h], edi
0x140064fda  jz      short loc_140065029
0x140064fdc  lea     r14, aCxml; "CXML"
0x140064fe3  cmp     [rax+38h], r15d
0x140064fe7  jl      short loc_140065030
0x140064fe9  mov     [rsp+170h+var_120], r13
0x140064fee  mov     [rsp+170h+var_118], 119Bh
0x140064ff6  mov     [rsp+170h+var_114], r15d
0x140064ffb  mov     [rsp+170h+var_110], r14
0x140065000  mov     rax, [rsi+8]
0x140065004  add     rax, 12h
0x140065008  mov     [rbp+70h+arg_18], rax
0x14006500f  lea     r8, [rbp+70h+arg_18]
0x140065016  lea     rdx, aFailedToSavefi; "Failed to SaveFileEx(). filePath:%?"
0x14006501d  lea     rcx, [rsp+170h+var_120]
0x140065022  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140065027  jmp     short loc_140065030
0x140065029  lea     r14, aCxml; "CXML"
0x140065030  test    rbx, rbx
0x140065033  jz      loc_1400650F8
0x140065039  lea     r13, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140065040  lea     rcx, [rbp+70h+arg_8]
0x140065047  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14006504c  nop
0x14006504d  lea     rax, ??_7XmlConfig@Config@@6B@; const Config::XmlConfig::`vftable'
0x140065054  mov     [rbp+70h+var_E8], rax
0x140065058  lea     rcx, [rbp+70h+var_D0]; this
0x14006505c  call    ??1ReplicaSetConfig@Config@@UEAA@XZ; Config::ReplicaSetConfig::~ReplicaSetConfig(void)
0x140065061  lea     r12, aConfigXmlwrite_11; "Config::XmlWriter::WriteReplicaSetConfi"...
0x140065068  test    rbx, rbx
0x14006506b  jz      short loc_1400650A6
0x14006506d  call    cs:__imp_GetCurrentThreadId
0x140065074  nop     dword ptr [rax+rax+00h]
0x140065079  mov     [rsp+170h+var_130], rbx
0x14006507e  mov     [rsp+170h+var_138], eax
0x140065082  mov     [rsp+170h+var_140], 11B0h
0x14006508a  mov     [rsp+170h+var_148], r12
0x14006508f  mov     [rsp+170h+var_150], r13
0x140065094  mov     r9d, [rbx]
0x140065097  mov     r8d, [rbx+8]
0x14006509b  mov     edx, [rbx+4]
0x14006509e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400650a3  mov     rdi, rax
0x1400650a6  lea     rax, ??_7?$XmlNodeType@UIXMLDOMElement@@@Config@@6B@; const Config::XmlNodeType<IXMLDOMElement>::`vftable'
0x1400650ad  mov     [rsp+170h+var_108], rax
0x1400650b2  lea     rcx, [rsp+170h+var_100]
0x1400650b7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400650bc  nop
0x1400650bd  lea     rax, ??_7?$XmlNodeType@UIXMLDOMDocument@@@Config@@6B@; const Config::XmlNodeType<IXMLDOMDocument>::`vftable'
0x1400650c4  mov     [rsp+170h+var_F8], rax
0x1400650c9  lea     rcx, [rbp+70h+var_F0]
0x1400650cd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400650d2  mov     rax, rdi
0x1400650d5  mov     rbx, [rsp+170h+arg_0]
0x1400650dd  add     rsp, 140h
0x1400650e4  pop     r15
0x1400650e6  pop     r14
0x1400650e8  pop     r13
0x1400650ea  pop     r12
0x1400650ec  pop     rdi
0x1400650ed  pop     rsi
0x1400650ee  pop     rbp
0x1400650ef  retn
0x1400650f1  lea     r14, aCxml; "CXML"
0x1400650f8  mov     rcx, [rsi+8]
0x1400650fc  add     rcx, 12h; unsigned __int16 *
0x140065100  xor     r8d, r8d; int
0x140065103  call    ?RestrictAccessToFileOrDirectory@FileUtil@@SAPEAVFrsStatus@@PEBGHH@Z; FileUtil::RestrictAccessToFileOrDirectory(ushort const *,int,int)
0x140065108  mov     rbx, rax
0x14006510b  test    rax, rax
0x14006510e  jz      loc_140065039
0x140065114  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14006511b  test    rax, rax
0x14006511e  jz      short loc_140065169
0x140065120  cmp     [rax+40h], edi
0x140065123  jz      short loc_140065169
0x140065125  cmp     [rax+38h], r15d
0x140065129  jl      short loc_140065169
0x14006512b  mov     [rsp+170h+var_120], r13
0x140065130  mov     [rsp+170h+var_118], 11A9h
0x140065138  mov     [rsp+170h+var_114], r15d
0x14006513d  mov     [rsp+170h+var_110], r14
0x140065142  mov     rax, [rsi+8]
0x140065146  add     rax, 12h
0x14006514a  mov     [rbp+70h+arg_18], rax
0x140065151  lea     r8, [rbp+70h+arg_18]
0x140065158  lea     rdx, aFailedToStampD_0; "Failed to stamp default ACLs on %?"
0x14006515f  lea     rcx, [rsp+170h+var_120]
0x140065164  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140065169  call    cs:__imp_GetCurrentThreadId
0x140065170  nop     dword ptr [rax+rax+00h]
0x140065175  mov     [rsp+170h+var_130], rdi
0x14006517a  mov     [rsp+170h+var_138], eax
0x14006517e  mov     [rsp+170h+var_140], 11AAh
0x140065186  lea     rax, aConfigXmlwrite_11; "Config::XmlWriter::WriteReplicaSetConfi"...
0x14006518d  mov     [rsp+170h+var_148], rax
0x140065192  lea     r13, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140065199  mov     [rsp+170h+var_150], r13
0x14006519e  mov     r9d, r12d
0x1400651a1  xor     r8d, r8d
0x1400651a4  lea     edx, [r8+5]
0x1400651a8  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400651ad  mov     rdx, rax; this
0x1400651b0  mov     rcx, rbx; struct FrsStatus *
0x1400651b3  call    ?PROPAGATE_ERROR_WITH_NEW_STATUS@@YAPEAVFrsStatus@@PEAV1@0@Z; PROPAGATE_ERROR_WITH_NEW_STATUS(FrsStatus *,FrsStatus *)
0x1400651b8  mov     rbx, rax
0x1400651bb  jmp     loc_140065040
```
