# Config::XmlWriter::WriteVolumeConfigFile(Config::VolumeConfig *,FilePath *,_FRS_CONFIG_SOURCE)

- ea: `0x140065a7c`
- end: `0x140065f6d`
- name: `?WriteVolumeConfigFile@XmlWriter@Config@@QEAAPEAVFrsStatus@@PEAVVolumeConfig@2@PEAVFilePath@@W4_FRS_CONFIG_SOURCE@@@Z`
- size: `1265`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140036d50`
- `0x1400655ec`

## callees

- `0x14000be44`
- `0x14000cd1c`
- `0x14000e34c`
- `0x14000ee94`
- `0x14001a634`
- `0x14001a9a0`
- `0x14001cfa0`
- `0x1400255c8`
- `0x140047200`
- `0x140047e14`
- `0x140048b44`
- `0x140048f2c`
- `0x14004d52c`
- `0x14005cb30`
- `0x14005e8ac`
- `0x140062468`
- `0x140062770`
- `0x140063ec8`
- `0x140065a7c`
- `0x1400c0a7c`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140065d6b`
- `KERNEL32!DeleteFileW` at `0x140065d6b`
- `KERNEL32!MoveFileExW` at `0x140065d00`
- `KERNEL32!MoveFileExW` at `0x140065d00`
- `KERNEL32!GetLastError` at `0x140065d22`
- `KERNEL32!GetLastError` at `0x140065d22`
- `KERNEL32!GetCurrentThreadId` at `0x140065d14`
- `KERNEL32!GetCurrentThreadId` at `0x140065e63`
- `KERNEL32!GetCurrentThreadId` at `0x140065ede`
- `KERNEL32!GetCurrentThreadId` at `0x140065d14`
- `KERNEL32!GetCurrentThreadId` at `0x140065e63`
- `KERNEL32!GetCurrentThreadId` at `0x140065ede`

## string_xrefs

- `0x140065d4b`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140065e85`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140065f00`: `base\fs\remotefs\frs\src\config\xml.cpp`
- `0x140065e52`: `Failed to stamp default ACLs on %?`
- `0x140065dcc`: `Failed to SaveFileEx(). filePath:%?`
- `0x140065ab1`: `Config::XmlWriter::WriteVolumeConfigFile`
- `0x140065b8b`: `Config::XmlWriter::WriteVolumeConfigFile`
- `0x140065d9c`: `Config::XmlWriter::WriteVolumeConfigFile`
- `0x140065e22`: `Config::XmlWriter::WriteVolumeConfigFile`
- `0x140065afd`: `Write volume configure file:%?`
- `0x140065bc2`: `Reading old volume config file at path:%?`
- `0x140065d3f`: `Config::XmlWriter::WriteVolumeConfigFile`
- `0x140065d7e`: `Config::XmlWriter::WriteVolumeConfigFile`
- `0x140065de8`: `Config::XmlWriter::WriteVolumeConfigFile`
- `0x140065ed2`: `Config::XmlWriter::WriteVolumeConfigFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Config::XmlWriter::WriteVolumeConfigFile(
        Config::XmlConfig *a1,
        _QWORD *a2,
        struct FilePath *a3,
        int a4)
{
  Config::XmlConfig *v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rax
  const unsigned __int16 *v11; // rdx
  struct FrsStatus *Document; // rbx
  struct FrsStatus *VolumeConfigFile; // rax
  int v14; // eax
  int v15; // edx
  const WCHAR *v16; // r14
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  DWORD v19; // eax
  __int64 v20; // rcx
  struct FrsStatus *v21; // rax
  DWORD v22; // eax
  __int64 v23; // rcx
  const unsigned __int16 *v25; // [rsp+28h] [rbp-E0h]
  const unsigned __int16 *v26; // [rsp+30h] [rbp-D8h]
  struct FrsStatus *v27; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *v28; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+68h] [rbp-A0h]
  const wchar_t *v30; // [rsp+70h] [rbp-98h]
  __int64 v31; // [rsp+78h] [rbp-90h] BYREF
  void **v32; // [rsp+80h] [rbp-88h] BYREF
  __int64 v33; // [rsp+88h] [rbp-80h] BYREF
  void **v34; // [rsp+90h] [rbp-78h] BYREF
  __int64 v35; // [rsp+98h] [rbp-70h] BYREF
  void **v36; // [rsp+A0h] [rbp-68h] BYREF
  int v37; // [rsp+A8h] [rbp-60h]
  int v38; // [rsp+ACh] [rbp-5Ch]
  const wchar_t *v39; // [rsp+B0h] [rbp-58h]
  _BYTE v40[144]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v41; // [rsp+148h] [rbp+40h]

  v8 = (Config::XmlConfig *)L"Config::XmlWriter::WriteVolumeConfigFile";
  v9 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v36 = (void **)L"Config::XmlWriter::WriteVolumeConfigFile";
    v37 = 3784;
    v38 = 4;
    v39 = L"CXML";
    v27 = (struct FrsStatus *)(*((_QWORD *)a3 + 1) + 18LL);
    dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v36, L"Write volume configure file:%?", &v27);
  }
  v35 = 0;
  v34 = &Config::XmlDocument::`vftable';
  v33 = 0;
  v32 = &Config::XmlElement::`vftable';
  v10 = a2[2];
  if ( v10 )
    v11 = *(const unsigned __int16 **)(v10 + 8);
  else
    v11 = 0;
  Document = Config::XmlConfig::CreateDocument(
               v8,
               v11,
               (struct Config::XmlDocument *)&v34,
               (struct Config::XmlElement *)&v32,
               v25,
               v26);
  if ( !Document )
  {
    Config::VolumeConfig::VolumeConfig((Config::VolumeConfig *)v40);
    v37 = 1;
    v36 = &Config::XmlReader::`vftable';
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v28 = L"Config::XmlWriter::WriteVolumeConfigFile";
      v29 = 0x400000EDFLL;
      v30 = L"CXML";
      v27 = (struct FrsStatus *)(*((_QWORD *)a3 + 1) + 18LL);
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v28, L"Reading old volume config file at path:%?", &v27);
    }
    VolumeConfigFile = Config::XmlReader::ReadVolumeConfigFile(
                         (Config::XmlReader *)&v36,
                         (struct Config::VolumeConfig *)v40,
                         a3);
    v27 = VolumeConfigFile;
    if ( !VolumeConfigFile || (unsigned int)IsConfigParamFrsStatusError(VolumeConfigFile) )
    {
      if ( a4 == 1 )
      {
        Config::DWordParam::operator=(a2[18] + 624LL, v41 + 624);
        Config::DWordParam::operator=(a2[18] + 544LL, v41 + 544);
      }
      v14 = Config::BoolParam::Get((Config::BoolParam *)(v41 + 328));
      Config::DWordParam::Set((Config::DWordParam *)(a2[18] + 328LL), v14 + 1);
    }
    Config::DateTimeParam::SetCurrentTime((Config::DateTimeParam *)(a2[18] + 368LL));
    Config::XmlConfig::WriteParamList(a1, (const struct Config::ParamList *)(a2 + 4), (struct Config::XmlElement *)&v32);
    CLEAR_ERROR(&v27);
    FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(&v31, *((_QWORD *)a3 + 1) + 18LL);
    FrsStringImpl<unsigned short,char>::Append(&v31, L".TMP");
    Document = v27;
    if ( !v27 )
    {
      v16 = (const WCHAR *)(v31 + 18);
      Document = Config::XmlDocument::SaveFileEx((Config::XmlDocument *)&v34, (const unsigned __int16 *)(v31 + 18));
      if ( !Document )
      {
        if ( MoveFileExW(v16, (LPCWSTR)(*((_QWORD *)a3 + 1) + 18LL), 1u) )
          goto LABEL_27;
        CurrentThreadId = GetCurrentThreadId();
        LastError = GetLastError();
        Document = (struct FrsStatus *)FrsStatusList::PushNewError(
                                         "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                         LastError,
                                         0,
                                         1,
                                         "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                         "Config::XmlWriter::WriteVolumeConfigFile",
                                         3857,
                                         CurrentThreadId,
                                         0);
        DeleteFileW(v16);
        if ( !Document )
          goto LABEL_27;
      }
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v28 = L"Config::XmlWriter::WriteVolumeConfigFile";
      v29 = 0x200000F17LL;
      v30 = L"CXML";
      v27 = (struct FrsStatus *)(*((_QWORD *)a3 + 1) + 18LL);
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v28, L"Failed to SaveFileEx(). filePath:%?", &v27);
    }
    if ( !Document )
    {
LABEL_27:
      Document = FileUtil::RestrictAccessToFileOrDirectory(
                   (const unsigned __int16 *)(*((_QWORD *)a3 + 1) + 18LL),
                   v15,
                   0);
      if ( Document )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v28 = L"Config::XmlWriter::WriteVolumeConfigFile";
          v29 = 0x200000F25LL;
          v30 = L"CXML";
          v27 = (struct FrsStatus *)(*((_QWORD *)a3 + 1) + 18LL);
          dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v28, L"Failed to stamp default ACLs on %?", &v27);
        }
        v19 = GetCurrentThreadId();
        v21 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v20,
                                    5,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
                                    "Config::XmlWriter::WriteVolumeConfigFile",
                                    3878,
                                    v19,
                                    0);
        Document = PROPAGATE_ERROR_WITH_NEW_STATUS(Document, v21);
      }
    }
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v31);
    v36 = &Config::XmlConfig::`vftable';
    Config::VolumeConfig::~VolumeConfig((Config::VolumeConfig *)v40);
  }
  if ( Document )
  {
    v22 = GetCurrentThreadId();
    v9 = FrsStatusList::PushNewError(
           v23,
           *((unsigned int *)Document + 1),
           *((unsigned int *)Document + 2),
           *(unsigned int *)Document,
           "base\\fs\\remotefs\\frs\\src\\config\\xml.cpp",
           "Config::XmlWriter::WriteVolumeConfigFile",
           3884,
           v22,
           Document);
  }
  v32 = &Config::XmlNodeType<IXMLDOMElement>::`vftable';
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  v34 = &Config::XmlNodeType<IXMLDOMDocument>::`vftable';
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  return v9;
}

```

## disassembly

```asm
0x140065a7c  mov     rax, rsp
0x140065a7f  mov     [rax+8], rbx
0x140065a83  mov     [rax+10h], rsi
0x140065a87  mov     [rax+18h], rdi
0x140065a8b  push    rbp
0x140065a8c  push    r12
0x140065a8e  push    r13
0x140065a90  push    r14
0x140065a92  push    r15
0x140065a94  lea     rbp, [rax-78h]
0x140065a98  sub     rsp, 150h
0x140065a9f  mov     r15d, r9d
0x140065aa2  mov     rsi, r8
0x140065aa5  mov     r14, rdx
0x140065aa8  mov     r12, rcx
0x140065aab  mov     r13d, 4
0x140065ab1  lea     rcx, aConfigXmlwrite_9; "Config::XmlWriter::WriteVolumeConfigFil"...
0x140065ab8  lea     rdx, aCxml; "CXML"
0x140065abf  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140065ac6  xor     edi, edi
0x140065ac8  test    rax, rax
0x140065acb  jz      short loc_140065B0D
0x140065acd  cmp     [rax+40h], edi
0x140065ad0  jz      short loc_140065B0D
0x140065ad2  cmp     [rax+38h], r13d
0x140065ad6  jl      short loc_140065B0D
0x140065ad8  mov     [rbp+70h+var_D8], rcx
0x140065adc  mov     [rbp+70h+var_D0], 0EC8h
0x140065ae3  mov     [rbp+70h+var_CC], r13d
0x140065ae7  mov     [rbp+70h+var_C8], rdx
0x140065aeb  mov     rax, [r8+8]
0x140065aef  add     rax, 12h
0x140065af3  mov     [rsp+170h+var_120], rax
0x140065af8  lea     r8, [rsp+170h+var_120]
0x140065afd  lea     rdx, aWriteVolumeCon; "Write volume configure file:%?"
0x140065b04  lea     rcx, [rbp+70h+var_D8]
0x140065b08  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140065b0d  mov     [rbp+70h+var_E0], rdi
0x140065b11  lea     rax, ??_7XmlDocument@Config@@6B@; const Config::XmlDocument::`vftable'
0x140065b18  mov     [rbp+70h+var_E8], rax
0x140065b1c  mov     [rbp+70h+var_F0], rdi
0x140065b20  lea     rax, ??_7XmlElement@Config@@6B@; const Config::XmlElement::`vftable'
0x140065b27  mov     [rsp+170h+var_F8], rax
0x140065b2c  mov     rax, [r14+10h]
0x140065b30  test    rax, rax
0x140065b33  jz      short loc_140065B3B
0x140065b35  mov     rdx, [rax+8]
0x140065b39  jmp     short loc_140065B3E
0x140065b3b  mov     rdx, rdi; unsigned __int16 *
0x140065b3e  lea     r9, [rsp+170h+var_F8]; struct Config::XmlElement *
0x140065b43  lea     r8, [rbp+70h+var_E8]; struct Config::XmlDocument *
0x140065b47  call    ?CreateDocument@XmlConfig@Config@@QEAAPEAVFrsStatus@@PEBGAEAVXmlDocument@2@AEAVXmlElement@2@00@Z; Config::XmlConfig::CreateDocument(ushort const *,Config::XmlDocument &,Config::XmlElement &,ushort const *,ushort const *)
0x140065b4c  mov     rbx, rax
0x140065b4f  test    rax, rax
0x140065b52  jnz     loc_140065ED2
0x140065b58  lea     rcx, [rbp+70h+var_C0]; this
0x140065b5c  call    ??0VolumeConfig@Config@@QEAA@XZ; Config::VolumeConfig::VolumeConfig(void)
0x140065b61  nop
0x140065b62  mov     [rbp+70h+var_D0], 1
0x140065b69  lea     rax, ??_7XmlReader@Config@@6B@; const Config::XmlReader::`vftable'
0x140065b70  mov     [rbp+70h+var_D8], rax
0x140065b74  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140065b7b  test    rax, rax
0x140065b7e  jz      short loc_140065BD5
0x140065b80  cmp     [rax+40h], edi
0x140065b83  jz      short loc_140065BD5
0x140065b85  cmp     [rax+38h], r13d
0x140065b89  jl      short loc_140065BD5
0x140065b8b  lea     rax, aConfigXmlwrite_9; "Config::XmlWriter::WriteVolumeConfigFil"...
0x140065b92  mov     [rsp+170h+var_118], rax
0x140065b97  mov     dword ptr [rsp+170h+var_110], 0EDFh
0x140065b9f  mov     dword ptr [rsp+170h+var_110+4], r13d
0x140065ba4  lea     r13, aCxml; "CXML"
0x140065bab  mov     [rsp+170h+var_108], r13
0x140065bb0  mov     rax, [rsi+8]
0x140065bb4  add     rax, 12h
0x140065bb8  mov     [rsp+170h+var_120], rax
0x140065bbd  lea     r8, [rsp+170h+var_120]
0x140065bc2  lea     rdx, aReadingOldVolu; "Reading old volume config file at path:"...
0x140065bc9  lea     rcx, [rsp+170h+var_118]
0x140065bce  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140065bd3  jmp     short loc_140065BDC
0x140065bd5  lea     r13, aCxml; "CXML"
0x140065bdc  mov     r8, rsi; struct FilePath *
0x140065bdf  lea     rdx, [rbp+70h+var_C0]; struct Config::VolumeConfig *
0x140065be3  lea     rcx, [rbp+70h+var_D8]; this
0x140065be7  call    ?ReadVolumeConfigFile@XmlReader@Config@@QEAAPEAVFrsStatus@@PEAVVolumeConfig@2@PEAVFilePath@@@Z; Config::XmlReader::ReadVolumeConfigFile(Config::VolumeConfig *,FilePath *)
0x140065bec  mov     [rsp+170h+var_120], rax
0x140065bf1  test    rax, rax
0x140065bf4  jz      short loc_140065C02
0x140065bf6  mov     rcx, rax; struct FrsStatus *
0x140065bf9  call    ?IsConfigParamFrsStatusError@@YAHPEAVFrsStatus@@@Z; IsConfigParamFrsStatusError(FrsStatus *)
0x140065bfe  test    eax, eax
0x140065c00  jz      short loc_140065C6A
0x140065c02  cmp     r15d, 1
0x140065c06  jnz     short loc_140065C44
0x140065c08  mov     rdx, [rbp+70h+var_30]
0x140065c0c  add     rdx, 270h
0x140065c13  mov     rcx, [r14+90h]
0x140065c1a  add     rcx, 270h
0x140065c21  call    ??4DWordParam@Config@@QEAAAEAV01@AEBV01@@Z; Config::DWordParam::operator=(Config::DWordParam const &)
0x140065c26  mov     rdx, [rbp+70h+var_30]
0x140065c2a  add     rdx, 220h
0x140065c31  mov     rcx, [r14+90h]
0x140065c38  add     rcx, 220h
0x140065c3f  call    ??4DWordParam@Config@@QEAAAEAV01@AEBV01@@Z; Config::DWordParam::operator=(Config::DWordParam const &)
0x140065c44  mov     rcx, [rbp+70h+var_30]
0x140065c48  add     rcx, 148h; this
0x140065c4f  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140065c54  lea     edx, [rax+1]; unsigned int
0x140065c57  mov     rcx, [r14+90h]
0x140065c5e  add     rcx, 148h; this
0x140065c65  call    ?Set@DWordParam@Config@@QEAAHK@Z; Config::DWordParam::Set(ulong)
0x140065c6a  mov     rcx, [r14+90h]
0x140065c71  add     rcx, 170h; this
0x140065c78  call    ?SetCurrentTime@DateTimeParam@Config@@QEAAXXZ; Config::DateTimeParam::SetCurrentTime(void)
0x140065c7d  lea     rdx, [r14+20h]; struct Config::ParamList *
0x140065c81  lea     r8, [rsp+170h+var_F8]; struct Config::XmlElement *
0x140065c86  mov     rcx, r12; this
0x140065c89  call    ?WriteParamList@XmlConfig@Config@@IEAAXPEBVParamList@2@AEAVXmlElement@2@@Z; Config::XmlConfig::WriteParamList(Config::ParamList const *,Config::XmlElement &)
0x140065c8e  lea     rcx, [rsp+170h+var_120]; struct FrsStatus **
0x140065c93  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140065c98  mov     rdx, [rsi+8]
0x140065c9c  add     rdx, 12h
0x140065ca0  lea     rcx, [rsp+170h+var_100]
0x140065ca5  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x140065caa  nop
0x140065cab  lea     rdx, aTmp_0; ".TMP"
0x140065cb2  lea     rcx, [rsp+170h+var_100]
0x140065cb7  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x140065cbc  mov     r15d, 2
0x140065cc2  mov     rbx, [rsp+170h+var_120]
0x140065cc7  test    rbx, rbx
0x140065cca  jnz     loc_140065D7E
0x140065cd0  mov     r14, [rsp+170h+var_100]
0x140065cd5  add     r14, 12h
0x140065cd9  mov     rdx, r14; unsigned __int16 *
0x140065cdc  lea     rcx, [rbp+70h+var_E8]; this
0x140065ce0  call    ?SaveFileEx@XmlDocument@Config@@QEAAPEAVFrsStatus@@PEBG@Z; Config::XmlDocument::SaveFileEx(ushort const *)
0x140065ce5  mov     rbx, rax
0x140065ce8  test    rax, rax
0x140065ceb  jnz     loc_140065D7E
0x140065cf1  mov     rdx, [rsi+8]
0x140065cf5  add     rdx, 12h; lpNewFileName
0x140065cf9  lea     r8d, [r15-1]; dwFlags
0x140065cfd  mov     rcx, r14; lpExistingFileName
0x140065d00  call    cs:__imp_MoveFileExW
0x140065d07  nop     dword ptr [rax+rax+00h]
0x140065d0c  test    eax, eax
0x140065d0e  jnz     loc_140065DE8
0x140065d14  call    cs:__imp_GetCurrentThreadId
0x140065d1b  nop     dword ptr [rax+rax+00h]
0x140065d20  mov     ebx, eax
0x140065d22  call    cs:__imp_GetLastError
0x140065d29  nop     dword ptr [rax+rax+00h]
0x140065d2e  mov     [rsp+170h+var_130], rdi
0x140065d33  mov     dword ptr [rsp+170h+var_138], ebx
0x140065d37  mov     [rsp+170h+var_140], 0F11h
0x140065d3f  lea     r12, aConfigXmlwrite_12; "Config::XmlWriter::WriteVolumeConfigFil"...
0x140065d46  mov     [rsp+170h+var_148], r12
0x140065d4b  lea     rcx, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140065d52  mov     [rsp+170h+var_150], rcx
0x140065d57  lea     r9d, [r15-1]
0x140065d5b  xor     r8d, r8d
0x140065d5e  mov     edx, eax
0x140065d60  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140065d65  mov     rbx, rax
0x140065d68  mov     rcx, r14; lpFileName
0x140065d6b  call    cs:__imp_DeleteFileW
0x140065d72  nop     dword ptr [rax+rax+00h]
0x140065d77  test    rbx, rbx
0x140065d7a  jz      short loc_140065DEF
0x140065d7c  jmp     short loc_140065D85
0x140065d7e  lea     r12, aConfigXmlwrite_12; "Config::XmlWriter::WriteVolumeConfigFil"...
0x140065d85  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140065d8c  test    rax, rax
0x140065d8f  jz      short loc_140065DDD
0x140065d91  cmp     [rax+40h], edi
0x140065d94  jz      short loc_140065DDD
0x140065d96  cmp     [rax+38h], r15d
0x140065d9a  jl      short loc_140065DDD
0x140065d9c  lea     rax, aConfigXmlwrite_9; "Config::XmlWriter::WriteVolumeConfigFil"...
0x140065da3  mov     [rsp+170h+var_118], rax
0x140065da8  mov     dword ptr [rsp+170h+var_110], 0F17h
0x140065db0  mov     dword ptr [rsp+170h+var_110+4], r15d
0x140065db5  mov     [rsp+170h+var_108], r13
0x140065dba  mov     rax, [rsi+8]
0x140065dbe  add     rax, 12h
0x140065dc2  mov     [rsp+170h+var_120], rax
0x140065dc7  lea     r8, [rsp+170h+var_120]
0x140065dcc  lea     rdx, aFailedToSavefi; "Failed to SaveFileEx(). filePath:%?"
0x140065dd3  lea     rcx, [rsp+170h+var_118]
0x140065dd8  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140065ddd  test    rbx, rbx
0x140065de0  jnz     loc_140065EB1
0x140065de6  jmp     short loc_140065DEF
0x140065de8  lea     r12, aConfigXmlwrite_12; "Config::XmlWriter::WriteVolumeConfigFil"...
0x140065def  mov     rcx, [rsi+8]
0x140065df3  add     rcx, 12h; unsigned __int16 *
0x140065df7  xor     r8d, r8d; int
0x140065dfa  call    ?RestrictAccessToFileOrDirectory@FileUtil@@SAPEAVFrsStatus@@PEBGHH@Z; FileUtil::RestrictAccessToFileOrDirectory(ushort const *,int,int)
0x140065dff  mov     rbx, rax
0x140065e02  test    rax, rax
0x140065e05  jz      loc_140065EB1
0x140065e0b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140065e12  test    rax, rax
0x140065e15  jz      short loc_140065E63
0x140065e17  cmp     [rax+40h], edi
0x140065e1a  jz      short loc_140065E63
0x140065e1c  cmp     [rax+38h], r15d
0x140065e20  jl      short loc_140065E63
0x140065e22  lea     rax, aConfigXmlwrite_9; "Config::XmlWriter::WriteVolumeConfigFil"...
0x140065e29  mov     [rsp+170h+var_118], rax
0x140065e2e  mov     dword ptr [rsp+170h+var_110], 0F25h
0x140065e36  mov     dword ptr [rsp+170h+var_110+4], r15d
0x140065e3b  mov     [rsp+170h+var_108], r13
0x140065e40  mov     rax, [rsi+8]
0x140065e44  add     rax, 12h
0x140065e48  mov     [rsp+170h+var_120], rax
0x140065e4d  lea     r8, [rsp+170h+var_120]
0x140065e52  lea     rdx, aFailedToStampD_0; "Failed to stamp default ACLs on %?"
0x140065e59  lea     rcx, [rsp+170h+var_118]
0x140065e5e  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140065e63  call    cs:__imp_GetCurrentThreadId
0x140065e6a  nop     dword ptr [rax+rax+00h]
0x140065e6f  mov     [rsp+170h+var_130], rdi
0x140065e74  mov     dword ptr [rsp+170h+var_138], eax
0x140065e78  mov     [rsp+170h+var_140], 0F26h
0x140065e80  mov     [rsp+170h+var_148], r12
0x140065e85  lea     rax, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140065e8c  mov     [rsp+170h+var_150], rax
0x140065e91  mov     r9d, 1
0x140065e97  xor     r8d, r8d
0x140065e9a  lea     edx, [r9+4]
0x140065e9e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140065ea3  mov     rdx, rax; this
0x140065ea6  mov     rcx, rbx; struct FrsStatus *
0x140065ea9  call    ?PROPAGATE_ERROR_WITH_NEW_STATUS@@YAPEAVFrsStatus@@PEAV1@0@Z; PROPAGATE_ERROR_WITH_NEW_STATUS(FrsStatus *,FrsStatus *)
0x140065eae  mov     rbx, rax
0x140065eb1  lea     rcx, [rsp+170h+var_100]
0x140065eb6  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140065ebb  nop
0x140065ebc  lea     rax, ??_7XmlConfig@Config@@6B@; const Config::XmlConfig::`vftable'
0x140065ec3  mov     [rbp+70h+var_D8], rax
0x140065ec7  lea     rcx, [rbp+70h+var_C0]; this
0x140065ecb  call    ??1VolumeConfig@Config@@UEAA@XZ; Config::VolumeConfig::~VolumeConfig(void)
0x140065ed0  jmp     short loc_140065ED9
0x140065ed2  lea     r12, aConfigXmlwrite_12; "Config::XmlWriter::WriteVolumeConfigFil"...
0x140065ed9  test    rbx, rbx
0x140065edc  jz      short loc_140065F1E
0x140065ede  call    cs:__imp_GetCurrentThreadId
0x140065ee5  nop     dword ptr [rax+rax+00h]
0x140065eea  mov     [rsp+170h+var_130], rbx
0x140065eef  mov     dword ptr [rsp+170h+var_138], eax
0x140065ef3  mov     [rsp+170h+var_140], 0F2Ch
0x140065efb  mov     [rsp+170h+var_148], r12
0x140065f00  lea     rax, aBaseFsRemotefs_64; "base\\fs\\remotefs\\frs\\src\\config\\x"...
0x140065f07  mov     [rsp+170h+var_150], rax
0x140065f0c  mov     r9d, [rbx]
0x140065f0f  mov     r8d, [rbx+8]
0x140065f13  mov     edx, [rbx+4]
0x140065f16  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140065f1b  mov     rdi, rax
0x140065f1e  lea     rax, ??_7?$XmlNodeType@UIXMLDOMElement@@@Config@@6B@; const Config::XmlNodeType<IXMLDOMElement>::`vftable'
0x140065f25  mov     [rsp+170h+var_F8], rax
0x140065f2a  lea     rcx, [rbp+70h+var_F0]
0x140065f2e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140065f33  nop
0x140065f34  lea     rax, ??_7?$XmlNodeType@UIXMLDOMDocument@@@Config@@6B@; const Config::XmlNodeType<IXMLDOMDocument>::`vftable'
0x140065f3b  mov     [rbp+70h+var_E8], rax
0x140065f3f  lea     rcx, [rbp+70h+var_E0]
0x140065f43  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140065f48  mov     rax, rdi
0x140065f4b  lea     r11, [rsp+170h+var_20]
0x140065f53  mov     rbx, [r11+30h]
0x140065f57  mov     rsi, [r11+38h]
0x140065f5b  mov     rdi, [r11+40h]
0x140065f5f  mov     rsp, r11
0x140065f62  pop     r15
0x140065f64  pop     r14
0x140065f66  pop     r13
0x140065f68  pop     r12
0x140065f6a  pop     rbp
0x140065f6b  retn
```
