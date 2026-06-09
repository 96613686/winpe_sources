# Config::XmlWriter::WriteMachineConfigFile(Config::MachineConfig *,FilePath *)

- ea: `0x140063940`
- end: `0x140063da3`
- name: `?WriteMachineConfigFile@XmlWriter@Config@@QEAAPEAVFrsStatus@@PEAVMachineConfig@2@PEAVFilePath@@@Z`
- size: `1123`
- prototype: `struct FrsStatus *(Config::XmlWriter *__hidden this, struct Config::MachineConfig *, struct FilePath *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140063744`

## callees

- `0x14000be44`
- `0x14000cd1c`
- `0x14000e34c`
- `0x14000ee94`
- `0x14001a584`
- `0x14001a87c`
- `0x14001cfa0`
- `0x1400255c8`
- `0x140047e14`
- `0x140048b44`
- `0x140048f2c`
- `0x14004d52c`
- `0x14005cb30`
- `0x14005e8ac`
- `0x140060380`
- `0x140062770`
- `0x140063940`
- `0x140063ec8`
- `0x1400c0a7c`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140063b98`
- `KERNEL32!DeleteFileW` at `0x140063b98`
- `KERNEL32!MoveFileExW` at `0x140063b2e`
- `KERNEL32!MoveFileExW` at `0x140063b2e`
- `KERNEL32!GetLastError` at `0x140063b50`
- `KERNEL32!GetLastError` at `0x140063b50`
- `KERNEL32!GetCurrentThreadId` at `0x140063b42`
- `KERNEL32!GetCurrentThreadId` at `0x140063c4f`
- `KERNEL32!GetCurrentThreadId` at `0x140063d4b`
- `KERNEL32!GetCurrentThreadId` at `0x140063b42`
- `KERNEL32!GetCurrentThreadId` at `0x140063c4f`
- `KERNEL32!GetCurrentThreadId` at `0x140063d4b`

## string_xrefs

- `0x1400639b3`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140063b79`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140063c1b`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140063d74`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140063d3a`: `Failed to stamp default ACLs on %?`
- `0x1400639e0`: `Config::XmlWriter::WriteMachineConfigFile`
- `0x140063a35`: `Reading old machine config file at path:%?`
- `0x1400639ac`: `Config::XmlWriter::WriteMachineConfigFile`
- `0x140063b6d`: `Config::XmlWriter::WriteMachineConfigFile`
- `0x140063c43`: `Config::XmlWriter::WriteMachineConfigFile`
- `0x140063d68`: `Config::XmlWriter::WriteMachineConfigFile`
- `0x140063bf8`: `Failed to SaveFileEx(). filePath:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct FrsStatus *__fastcall Config::XmlWriter::WriteMachineConfigFile(
        Config::XmlWriter *this,
        struct Config::MachineConfig *a2,
        struct FilePath *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rdx
  const unsigned __int16 *v8; // rdx
  struct FrsStatus *Document; // rbx
  struct FrsStatus *MachineConfigFile; // rax
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
    Config::MachineConfig::MachineConfig((Config::MachineConfig *)v34);
    v33 = 1;
    v32 = &Config::XmlReader::`vftable';
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v24 = L"Config::XmlWriter::WriteMachineConfigFile";
      v25 = 3590;
      v26 = 4;
      v27 = L"CXML";
      v36 = *((_QWORD *)a3 + 1) + 18LL;
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v24, L"Reading old machine config file at path:%?", &v36);
    }
    MachineConfigFile = Config::XmlReader::ReadMachineConfigFile(
                          (Config::XmlReader *)&v32,
                          (struct Config::MachineConfig *)v34,
                          a3);
    v37 = MachineConfigFile;
    if ( !MachineConfigFile || (unsigned int)IsConfigParamFrsStatusError(MachineConfigFile) )
    {
      v11 = Config::BoolParam::Get((Config::BoolParam *)(v35 + 112));
      Config::DWordParam::Set((Config::DWordParam *)(*((_QWORD *)a2 + 18) + 112LL), v11 + 1);
    }
    Config::DateTimeParam::SetCurrentTime((Config::DateTimeParam *)(*((_QWORD *)a2 + 18) + 152LL));
    Config::XmlConfig::WriteParamList(
      this,
      (struct Config::MachineConfig *)((char *)a2 + 32),
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
                                         "Config::XmlWriter::WriteMachineConfigFile",
                                         3629,
                                         CurrentThreadId,
                                         0);
        DeleteFileW(v13);
        if ( !Document )
          goto LABEL_25;
      }
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v24 = L"Config::XmlWriter::WriteMachineConfigFile";
      v25 = 3635;
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
          v24 = L"Config::XmlWriter::WriteMachineConfigFile";
          v25 = 3649;
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
                                    "Config::XmlWriter::WriteMachineConfigFile",
                                    3650,
                                    v19,
                                    0);
        Document = PROPAGATE_ERROR_WITH_NEW_STATUS(Document, v21);
      }
    }
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v36);
    v32 = &Config::XmlConfig::`vftable';
    Config::MachineConfig::~MachineConfig((Config::MachineConfig *)v34);
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
           "Config::XmlWriter::WriteMachineConfigFile",
           3656,
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
0x140063940  mov     [rsp-8+arg_0], rbx
0x140063945  push    rbp
0x140063946  push    rsi
0x140063947  push    rdi
0x140063948  push    r12
0x14006394a  push    r13
0x14006394c  push    r14
0x14006394e  push    r15
0x140063950  lea     rbp, [rsp-40h]
0x140063955  sub     rsp, 140h
0x14006395c  mov     rsi, r8
0x14006395f  mov     r14, rdx
0x140063962  mov     r15, rcx
0x140063965  xor     edi, edi
0x140063967  mov     [rbp+70h+var_F0], rdi
0x14006396b  lea     rax, ??_7XmlDocument@Config@@6B@; const Config::XmlDocument::`vftable'
0x140063972  mov     [rsp+170h+var_F8], rax
0x140063977  mov     [rsp+170h+var_100], rdi
0x14006397c  lea     rax, ??_7XmlElement@Config@@6B@; const Config::XmlElement::`vftable'
0x140063983  mov     [rsp+170h+var_108], rax
0x140063988  mov     rdx, [rdx+10h]
0x14006398c  test    rdx, rdx
0x14006398f  jz      short loc_140063997
0x140063991  mov     rdx, [rdx+8]
0x140063995  jmp     short loc_14006399A
0x140063997  mov     rdx, rdi; unsigned __int16 *
0x14006399a  lea     r9, [rsp+170h+var_108]; struct Config::XmlElement *
0x14006399f  lea     r8, [rsp+170h+var_F8]; struct Config::XmlDocument *
0x1400639a4  call    ?CreateDocument@XmlConfig@Config@@QEAAPEAVFrsStatus@@PEBGAEAVXmlDocument@2@AEAVXmlElement@2@00@Z; Config::XmlConfig::CreateDocument(ushort const *,Config::XmlDocument &,Config::XmlElement &,ushort const *,ushort const *)
0x1400639a9  mov     rbx, rax
0x1400639ac  lea     r12, aConfigXmlwrite_7; "Config::XmlWriter::WriteMachineConfigFi"...
0x1400639b3  lea     r13, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x1400639ba  test    rax, rax
0x1400639bd  jnz     loc_140063C4A
0x1400639c3  lea     rcx, [rbp+70h+var_D0]; this
0x1400639c7  call    ??0MachineConfig@Config@@QEAA@XZ; Config::MachineConfig::MachineConfig(void)
0x1400639cc  nop
0x1400639cd  lea     r12d, [rbx+1]
0x1400639d1  mov     [rbp+70h+var_E0], r12d
0x1400639d5  lea     rax, ??_7XmlReader@Config@@6B@; const Config::XmlReader::`vftable'
0x1400639dc  mov     [rbp+70h+var_E8], rax
0x1400639e0  lea     r13, aConfigXmlwrite_3; "Config::XmlWriter::WriteMachineConfigFi"...
0x1400639e7  lea     rcx, aCxml; "CXML"
0x1400639ee  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400639f5  test    rax, rax
0x1400639f8  jz      short loc_140063A46
0x1400639fa  cmp     [rax+40h], edi
0x1400639fd  jz      short loc_140063A46
0x1400639ff  cmp     dword ptr [rax+38h], 4
0x140063a03  jl      short loc_140063A46
0x140063a05  mov     [rsp+170h+var_120], r13
0x140063a0a  mov     [rsp+170h+var_118], 0E06h
0x140063a12  mov     [rsp+170h+var_114], 4
0x140063a1a  mov     [rsp+170h+var_110], rcx
0x140063a1f  mov     rax, [rsi+8]
0x140063a23  add     rax, 12h
0x140063a27  mov     [rbp+70h+arg_8], rax
0x140063a2e  lea     r8, [rbp+70h+arg_8]
0x140063a35  lea     rdx, aReadingOldMach; "Reading old machine config file at path"...
0x140063a3c  lea     rcx, [rsp+170h+var_120]
0x140063a41  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140063a46  mov     r8, rsi; struct FilePath *
0x140063a49  lea     rdx, [rbp+70h+var_D0]; struct Config::MachineConfig *
0x140063a4d  lea     rcx, [rbp+70h+var_E8]; this
0x140063a51  call    ?ReadMachineConfigFile@XmlReader@Config@@QEAAPEAVFrsStatus@@PEAVMachineConfig@2@PEAVFilePath@@@Z; Config::XmlReader::ReadMachineConfigFile(Config::MachineConfig *,FilePath *)
0x140063a56  mov     [rbp+70h+arg_18], rax
0x140063a5d  test    rax, rax
0x140063a60  jz      short loc_140063A6E
0x140063a62  mov     rcx, rax; struct FrsStatus *
0x140063a65  call    ?IsConfigParamFrsStatusError@@YAHPEAVFrsStatus@@@Z; IsConfigParamFrsStatusError(FrsStatus *)
0x140063a6a  test    eax, eax
0x140063a6c  jz      short loc_140063A8E
0x140063a6e  mov     rcx, [rbp+70h+var_40]
0x140063a72  add     rcx, 70h ; 'p'; this
0x140063a76  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140063a7b  lea     edx, [rax+1]; unsigned int
0x140063a7e  mov     rcx, [r14+90h]
0x140063a85  add     rcx, 70h ; 'p'; this
0x140063a89  call    ?Set@DWordParam@Config@@QEAAHK@Z; Config::DWordParam::Set(ulong)
0x140063a8e  mov     rcx, [r14+90h]
0x140063a95  add     rcx, 98h; this
0x140063a9c  call    ?SetCurrentTime@DateTimeParam@Config@@QEAAXXZ; Config::DateTimeParam::SetCurrentTime(void)
0x140063aa1  lea     rdx, [r14+20h]; struct Config::ParamList *
0x140063aa5  lea     r8, [rsp+170h+var_108]; struct Config::XmlElement *
0x140063aaa  mov     rcx, r15; this
0x140063aad  call    ?WriteParamList@XmlConfig@Config@@IEAAXPEBVParamList@2@AEAVXmlElement@2@@Z; Config::XmlConfig::WriteParamList(Config::ParamList const *,Config::XmlElement &)
0x140063ab2  lea     rcx, [rbp+70h+arg_18]; struct FrsStatus **
0x140063ab9  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140063abe  mov     rdx, [rsi+8]
0x140063ac2  add     rdx, 12h
0x140063ac6  lea     rcx, [rbp+70h+arg_8]
0x140063acd  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x140063ad2  nop
0x140063ad3  lea     rdx, aTmp_0; ".TMP"
0x140063ada  lea     rcx, [rbp+70h+arg_8]
0x140063ae1  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x140063ae6  mov     r15d, 2
0x140063aec  mov     rbx, [rbp+70h+arg_18]
0x140063af3  test    rbx, rbx
0x140063af6  jnz     loc_140063BAD
0x140063afc  mov     r14, [rbp+70h+arg_8]
0x140063b03  add     r14, 12h
0x140063b07  mov     rdx, r14; unsigned __int16 *
0x140063b0a  lea     rcx, [rsp+170h+var_F8]; this
0x140063b0f  call    ?SaveFileEx@XmlDocument@Config@@QEAAPEAVFrsStatus@@PEBG@Z; Config::XmlDocument::SaveFileEx(ushort const *)
0x140063b14  mov     rbx, rax
0x140063b17  test    rax, rax
0x140063b1a  jnz     loc_140063BAD
0x140063b20  mov     rdx, [rsi+8]
0x140063b24  add     rdx, 12h; lpNewFileName
0x140063b28  mov     r8d, r12d; dwFlags
0x140063b2b  mov     rcx, r14; lpExistingFileName
0x140063b2e  call    cs:__imp_MoveFileExW
0x140063b35  nop     dword ptr [rax+rax+00h]
0x140063b3a  test    eax, eax
0x140063b3c  jnz     loc_140063CD3
0x140063b42  call    cs:__imp_GetCurrentThreadId
0x140063b49  nop     dword ptr [rax+rax+00h]
0x140063b4e  mov     ebx, eax
0x140063b50  call    cs:__imp_GetLastError
0x140063b57  nop     dword ptr [rax+rax+00h]
0x140063b5c  mov     [rsp+170h+var_130], rdi
0x140063b61  mov     [rsp+170h+var_138], ebx
0x140063b65  mov     [rsp+170h+var_140], 0E2Dh
0x140063b6d  lea     rcx, aConfigXmlwrite_7; "Config::XmlWriter::WriteMachineConfigFi"...
0x140063b74  mov     [rsp+170h+var_148], rcx
0x140063b79  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140063b80  mov     [rsp+170h+var_150], rcx
0x140063b85  mov     r9d, r12d
0x140063b88  xor     r8d, r8d
0x140063b8b  mov     edx, eax
0x140063b8d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140063b92  mov     rbx, rax
0x140063b95  mov     rcx, r14; lpFileName
0x140063b98  call    cs:__imp_DeleteFileW
0x140063b9f  nop     dword ptr [rax+rax+00h]
0x140063ba4  test    rbx, rbx
0x140063ba7  jz      loc_140063CD3
0x140063bad  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140063bb4  test    rax, rax
0x140063bb7  jz      short loc_140063C0B
0x140063bb9  cmp     [rax+40h], edi
0x140063bbc  jz      short loc_140063C0B
0x140063bbe  lea     r14, aCxml; "CXML"
0x140063bc5  cmp     [rax+38h], r15d
0x140063bc9  jl      short loc_140063C12
0x140063bcb  mov     [rsp+170h+var_120], r13
0x140063bd0  mov     [rsp+170h+var_118], 0E33h
0x140063bd8  mov     [rsp+170h+var_114], r15d
0x140063bdd  mov     [rsp+170h+var_110], r14
0x140063be2  mov     rax, [rsi+8]
0x140063be6  add     rax, 12h
0x140063bea  mov     [rbp+70h+arg_18], rax
0x140063bf1  lea     r8, [rbp+70h+arg_18]
0x140063bf8  lea     rdx, aFailedToSavefi; "Failed to SaveFileEx(). filePath:%?"
0x140063bff  lea     rcx, [rsp+170h+var_120]
0x140063c04  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140063c09  jmp     short loc_140063C12
0x140063c0b  lea     r14, aCxml; "CXML"
0x140063c12  test    rbx, rbx
0x140063c15  jz      loc_140063CDA
0x140063c1b  lea     r13, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140063c22  lea     rcx, [rbp+70h+arg_8]
0x140063c29  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140063c2e  nop
0x140063c2f  lea     rax, ??_7XmlConfig@Config@@6B@; const Config::XmlConfig::`vftable'
0x140063c36  mov     [rbp+70h+var_E8], rax
0x140063c3a  lea     rcx, [rbp+70h+var_D0]; this
0x140063c3e  call    ??1MachineConfig@Config@@UEAA@XZ; Config::MachineConfig::~MachineConfig(void)
0x140063c43  lea     r12, aConfigXmlwrite_7; "Config::XmlWriter::WriteMachineConfigFi"...
0x140063c4a  test    rbx, rbx
0x140063c4d  jz      short loc_140063C88
0x140063c4f  call    cs:__imp_GetCurrentThreadId
0x140063c56  nop     dword ptr [rax+rax+00h]
0x140063c5b  mov     [rsp+170h+var_130], rbx
0x140063c60  mov     [rsp+170h+var_138], eax
0x140063c64  mov     [rsp+170h+var_140], 0E48h
0x140063c6c  mov     [rsp+170h+var_148], r12
0x140063c71  mov     [rsp+170h+var_150], r13
0x140063c76  mov     r9d, [rbx]
0x140063c79  mov     r8d, [rbx+8]
0x140063c7d  mov     edx, [rbx+4]
0x140063c80  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140063c85  mov     rdi, rax
0x140063c88  lea     rax, ??_7?$XmlNodeType@UIXMLDOMElement@@@Config@@6B@; const Config::XmlNodeType<IXMLDOMElement>::`vftable'
0x140063c8f  mov     [rsp+170h+var_108], rax
0x140063c94  lea     rcx, [rsp+170h+var_100]
0x140063c99  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140063c9e  nop
0x140063c9f  lea     rax, ??_7?$XmlNodeType@UIXMLDOMDocument@@@Config@@6B@; const Config::XmlNodeType<IXMLDOMDocument>::`vftable'
0x140063ca6  mov     [rsp+170h+var_F8], rax
0x140063cab  lea     rcx, [rbp+70h+var_F0]
0x140063caf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140063cb4  mov     rax, rdi
0x140063cb7  mov     rbx, [rsp+170h+arg_0]
0x140063cbf  add     rsp, 140h
0x140063cc6  pop     r15
0x140063cc8  pop     r14
0x140063cca  pop     r13
0x140063ccc  pop     r12
0x140063cce  pop     rdi
0x140063ccf  pop     rsi
0x140063cd0  pop     rbp
0x140063cd1  retn
0x140063cd3  lea     r14, aCxml; "CXML"
0x140063cda  mov     rcx, [rsi+8]
0x140063cde  add     rcx, 12h; unsigned __int16 *
0x140063ce2  xor     r8d, r8d; int
0x140063ce5  call    ?RestrictAccessToFileOrDirectory@FileUtil@@SAPEAVFrsStatus@@PEBGHH@Z; FileUtil::RestrictAccessToFileOrDirectory(ushort const *,int,int)
0x140063cea  mov     rbx, rax
0x140063ced  test    rax, rax
0x140063cf0  jz      loc_140063C1B
0x140063cf6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140063cfd  test    rax, rax
0x140063d00  jz      short loc_140063D4B
0x140063d02  cmp     [rax+40h], edi
0x140063d05  jz      short loc_140063D4B
0x140063d07  cmp     [rax+38h], r15d
0x140063d0b  jl      short loc_140063D4B
0x140063d0d  mov     [rsp+170h+var_120], r13
0x140063d12  mov     [rsp+170h+var_118], 0E41h
0x140063d1a  mov     [rsp+170h+var_114], r15d
0x140063d1f  mov     [rsp+170h+var_110], r14
0x140063d24  mov     rax, [rsi+8]
0x140063d28  add     rax, 12h
0x140063d2c  mov     [rbp+70h+arg_18], rax
0x140063d33  lea     r8, [rbp+70h+arg_18]
0x140063d3a  lea     rdx, aFailedToStampD_0; "Failed to stamp default ACLs on %?"
0x140063d41  lea     rcx, [rsp+170h+var_120]
0x140063d46  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140063d4b  call    cs:__imp_GetCurrentThreadId
0x140063d52  nop     dword ptr [rax+rax+00h]
0x140063d57  mov     [rsp+170h+var_130], rdi
0x140063d5c  mov     [rsp+170h+var_138], eax
0x140063d60  mov     [rsp+170h+var_140], 0E42h
0x140063d68  lea     rax, aConfigXmlwrite_7; "Config::XmlWriter::WriteMachineConfigFi"...
0x140063d6f  mov     [rsp+170h+var_148], rax
0x140063d74  lea     r13, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140063d7b  mov     [rsp+170h+var_150], r13
0x140063d80  mov     r9d, r12d
0x140063d83  xor     r8d, r8d
0x140063d86  lea     edx, [r8+5]
0x140063d8a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140063d8f  mov     rdx, rax; this
0x140063d92  mov     rcx, rbx; struct FrsStatus *
0x140063d95  call    ?PROPAGATE_ERROR_WITH_NEW_STATUS@@YAPEAVFrsStatus@@PEAV1@0@Z; PROPAGATE_ERROR_WITH_NEW_STATUS(FrsStatus *,FrsStatus *)
0x140063d9a  mov     rbx, rax
0x140063d9d  jmp     loc_140063C22
```
