# Microsoft::Diagnostics::SettingsDownloader::ConvertScenariosToXml(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,void *,ulong)

- ea: `0x1800629d0`
- end: `0x180064c20`
- name: `?ConvertScenariosToXml@SettingsDownloader@Diagnostics@Microsoft@@CAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAXK@Z`
- size: `8784`
- prototype: ``
- caller_count: `1`
- callee_count: `69`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180121fa0`

## callees

- `0x18001df2c`
- `0x18002110c`
- `0x180024e08`
- `0x18002afd8`
- `0x18002b318`
- `0x18002b7c0`
- `0x18002b95c`
- `0x18002be90`
- `0x18002cae0`
- `0x18002cb04`
- `0x18002df00`
- `0x18003119c`
- `0x180038010`
- `0x180038524`
- `0x180061180`
- `0x1800624ac`
- `0x18006266c`
- `0x1800626a8`
- `0x1800629d0`
- `0x180064c28`
- `0x180064e34`
- `0x180064e6c`
- `0x180064e8c`
- `0x180064eb0`
- `0x180064ee4`
- `0x180064f58`
- `0x18006509c`
- `0x18006a7a0`
- `0x180094c38`
- `0x180097b6c`
- `0x18009c7e4`
- `0x1800bc658`
- `0x1800d3790`
- `0x1800f7eb8`
- `0x18011bf68`
- `0x18019cf74`
- `0x18019ec8c`
- `0x18019ede0`
- `0x1801a0848`
- `0x1801a0af0`
- `0x1801a0b30`
- `0x1801a0c18`
- `0x1801a0c94`
- `0x1801a0d40`
- `0x1801a1010`
- `0x1801a1b34`
- `0x1801a1b7c`
- `0x1801a2510`
- `0x1801a2a98`
- `0x1801a3548`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180062dd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180062dd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063871`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006387c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063871`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006387c`
- `ntdll!NtSetInformationFile` at `0x180063825`
- `ntdll!NtSetInformationFile` at `0x180063866`
- `ntdll!NtSetInformationFile` at `0x180063825`
- `ntdll!NtSetInformationFile` at `0x180063866`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062afd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063b03`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062afd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063b03`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180062b94`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006375b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180064058`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006470a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180062b94`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006375b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180064058`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006470a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180062ba5`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006376c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180064101`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800647cf`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180062ba5`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006376c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180064101`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800647cf`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800638fd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800648b4`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800638fd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800648b4`
- `CRYPT32!CryptStringToBinaryA` at `0x180063666`
- `CRYPT32!CryptStringToBinaryA` at `0x180063666`

## string_xrefs

- `0x180062a81`: `.temp`
- `0x180062a90`: `.temp`
- `0x180063aa0`: `.temp`
- `0x180062b2c`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180062f2e`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180062ff7`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063782`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063998`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063b45`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063c4f`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063c7a`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063cbf`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063d07`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063d59`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063dae`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180063ecf`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x18006406e`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064117`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1800641e2`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1800642c5`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x18006437b`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064496`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x18006457b`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x18006463f`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064720`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1800647e5`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1800648d9`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1800649dd`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064a50`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064ac3`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064b40`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180064bae`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x180062c11`: `<?xml version="1.0" encoding="utf-8" ?><diagrules><scenarios>`
- `0x180063fc9`: `.json`
- `0x18006400b`: `.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall Microsoft::Diagnostics::SettingsDownloader::ConvertScenariosToXml(
        const void **a1,
        void *a2,
        unsigned int a3)
{
  __int64 v3; // rsi
  int v5; // r14d
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  const WCHAR *v9; // rcx
  HANDLE FileW; // rax
  const char *v11; // r9
  unsigned int LastError; // ebx
  const char *v13; // r9
  __int64 result; // rax
  const char *v15; // r9
  const char *v16; // r9
  int v17; // eax
  unsigned int v18; // ebx
  _QWORD *v19; // r13
  unsigned int v20; // r15d
  int v21; // eax
  unsigned int v22; // ebx
  unsigned __int8 v23; // r12
  unsigned __int8 v24; // di
  DWORD v25; // esi
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  unsigned __int8 v29; // al
  unsigned __int64 v30; // rdx
  char **v31; // rcx
  unsigned __int64 v32; // rax
  char **v33; // rcx
  int v34; // ebx
  int v35; // edi
  __int64 v36; // r8
  unsigned __int64 v37; // rcx
  __int128 *v38; // rax
  unsigned __int8 *v39; // rax
  unsigned __int8 v40; // dl
  __int64 v41; // r8
  struct Microsoft::Diagnostics::MemoryMappedStream *v42; // rdi
  struct Microsoft::Diagnostics::MemoryMappedStream *v43; // rbx
  char *v44; // r8
  unsigned int v45; // edi
  char *v46; // rcx
  char *v47; // rdx
  __int64 v48; // rbx
  __int64 v49; // rdx
  __int64 v50; // r9
  __int64 v51; // rax
  unsigned __int8 *v52; // rbx
  _QWORD *v53; // rax
  __int64 v54; // r8
  __int64 v55; // rax
  unsigned __int8 v56; // dl
  __int64 v57; // r8
  _QWORD *v58; // rax
  __int64 v59; // r8
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 v66; // r8
  const char *v67; // r9
  int v68; // eax
  unsigned int v69; // ebx
  char *v70; // rax
  const void **v71; // r12
  int v72; // eax
  __int64 v73; // rcx
  unsigned int v74; // ebx
  HANDLE v75; // rdi
  const char *v76; // r9
  const char *v77; // r9
  unsigned int v78; // ebx
  __int64 v79; // rcx
  const WCHAR *v80; // rdx
  const WCHAR *v81; // rcx
  BOOL v82; // ebx
  const char *v83; // r9
  __int64 v84; // rcx
  unsigned int v85; // ebx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rax
  const WCHAR *v89; // rcx
  HANDLE v90; // rax
  const char *v91; // r9
  __int64 v92; // rdi
  unsigned int v93; // ebx
  __int64 v94; // r9
  __int64 v95; // rax
  unsigned int v96; // ebx
  unsigned int v97; // ebx
  __int64 v98; // rbx
  __int64 v99; // rax
  __int64 last_of; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  unsigned __int8 **v103; // rcx
  __int64 v104; // rax
  const char *v105; // r9
  unsigned int v106; // ebx
  const char *v107; // r9
  unsigned int v108; // ebx
  int v109; // eax
  unsigned int v110; // ebx
  struct Microsoft::Diagnostics::MemoryMappedStream *v111; // rdi
  int v112; // eax
  unsigned int v113; // ebx
  __int64 v114; // rax
  __int128 *v115; // rdx
  int v116; // eax
  unsigned int v117; // ebx
  __int64 v118; // rsi
  int v119; // eax
  __int64 v120; // rcx
  unsigned int v121; // ebx
  HANDLE v122; // rdi
  const char *v123; // r9
  unsigned int v124; // ebx
  const char *v125; // r9
  unsigned int v126; // ebx
  const WCHAR *v127; // rcx
  BOOL v128; // ebx
  const char *v129; // r9
  unsigned int v130; // ebx
  unsigned int v131; // ebx
  unsigned int v132; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-508h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-508h]
  char v135[8]; // [rsp+40h] [rbp-4E8h] BYREF
  char v136[8]; // [rsp+48h] [rbp-4E0h] BYREF
  __int64 v137; // [rsp+50h] [rbp-4D8h] BYREF
  struct Microsoft::Diagnostics::MemoryMappedStream *v138; // [rsp+58h] [rbp-4D0h] BYREF
  unsigned int v139; // [rsp+60h] [rbp-4C8h] BYREF
  _QWORD *v140; // [rsp+68h] [rbp-4C0h] BYREF
  char v141[8]; // [rsp+70h] [rbp-4B8h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp-4B0h] BYREF
  DWORD pcbBinary[2]; // [rsp+80h] [rbp-4A8h] BYREF
  unsigned int v144; // [rsp+88h] [rbp-4A0h]
  struct Microsoft::Diagnostics::MemoryMappedStream *v145; // [rsp+90h] [rbp-498h] BYREF
  char v146[8]; // [rsp+98h] [rbp-490h] BYREF
  __int64 v147; // [rsp+A0h] [rbp-488h] BYREF
  int v148; // [rsp+A8h] [rbp-480h] BYREF
  int v149; // [rsp+ACh] [rbp-47Ch]
  int v150; // [rsp+B0h] [rbp-478h]
  _BYTE *v151; // [rsp+B8h] [rbp-470h]
  struct Microsoft::Diagnostics::MemoryMappedStream *v152; // [rsp+C0h] [rbp-468h] BYREF
  const void **v153; // [rsp+C8h] [rbp-460h]
  _BYTE *v154; // [rsp+D0h] [rbp-458h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-448h] BYREF
  _IO_STATUS_BLOCK *p_IoStatusBlock; // [rsp+F0h] [rbp-438h]
  char v157[8]; // [rsp+F8h] [rbp-430h] BYREF
  char v158[8]; // [rsp+100h] [rbp-428h] BYREF
  HANDLE v159; // [rsp+108h] [rbp-420h]
  __int128 v160; // [rsp+110h] [rbp-418h] BYREF
  __int64 v161; // [rsp+120h] [rbp-408h]
  __int64 v162; // [rsp+128h] [rbp-400h]
  unsigned __int8 *v163[4]; // [rsp+130h] [rbp-3F8h] BYREF
  _QWORD v164[2]; // [rsp+150h] [rbp-3D8h] BYREF
  _BYTE v165[56]; // [rsp+170h] [rbp-3B8h] BYREF
  __int64 (__fastcall ***v166)(_QWORD, _BYTE *); // [rsp+1A8h] [rbp-380h]
  _BYTE v167[56]; // [rsp+1B0h] [rbp-378h] BYREF
  _BYTE v168[56]; // [rsp+1E8h] [rbp-340h] BYREF
  _BYTE v169[56]; // [rsp+220h] [rbp-308h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+258h] [rbp-2D0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+290h] [rbp-298h] BYREF
  __int128 v172; // [rsp+2A0h] [rbp-288h]
  char *v173[2]; // [rsp+2B0h] [rbp-278h] BYREF
  unsigned __int64 v174; // [rsp+2C0h] [rbp-268h]
  unsigned __int64 v175; // [rsp+2C8h] [rbp-260h]
  __int128 v176; // [rsp+2D0h] [rbp-258h] BYREF
  unsigned __int64 v177; // [rsp+2E0h] [rbp-248h]
  unsigned __int64 v178; // [rsp+2E8h] [rbp-240h]
  LPCWSTR lpExistingFileName[3]; // [rsp+2F0h] [rbp-238h] BYREF
  unsigned __int64 v180; // [rsp+308h] [rbp-220h]
  char *v181[4]; // [rsp+310h] [rbp-218h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+330h] [rbp-1F8h] BYREF
  __int128 v183; // [rsp+340h] [rbp-1E8h]
  unsigned __int8 *v184[8]; // [rsp+350h] [rbp-1D8h] BYREF
  _QWORD v185[2]; // [rsp+390h] [rbp-198h] BYREF
  _BYTE Src[56]; // [rsp+3B0h] [rbp-178h] BYREF
  __int64 v187; // [rsp+3E8h] [rbp-140h]
  _BYTE v188[64]; // [rsp+3F0h] [rbp-138h] BYREF
  int v189; // [rsp+430h] [rbp-F8h]
  _BYTE v190[168]; // [rsp+438h] [rbp-F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+0h]

  v3 = a3;
  v144 = a3;
  v153 = a1;
  v5 = 0;
  LODWORD(v151) = 0;
  v149 = 0;
  v138 = 0;
  v145 = 0;
  try
  {
    v6 = Microsoft::Diagnostics::MemoryMappedStream::Create(&v145, a2, 2u);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D3,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
        (const char *)(unsigned int)v6,
        dwCreationDisposition);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
      return v7;
    }
    v138 = v145;
    *(_OWORD *)lpFileName = 0;
    v172 = 0;
    std::wstring::_Construct<1,wchar_t *>(lpFileName, *a1, (unsigned __int64)a1[1]);
    std::_WChar_traits<wchar_t>::length(L".temp");
    std::wstring::_Append<wchar_t>(lpFileName);
    v141[0] = 0;
    v159 = (HANDLE)-1LL;
    v8 = -1;
    hFile = (HANDLE)-1LL;
    v9 = (const WCHAR *)lpFileName;
    if ( *((_QWORD *)&v172 + 1) > 7u )
      v9 = lpFileName[0];
    FileW = CreateFileW(v9, 0xC0010000, 1u, 0, 2u, 0x100u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        FileW);
      v8 = (__int64)hFile;
    }
    if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2E3,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                    v11);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
      return LastError;
    }
    if ( !SetFilePointerEx((HANDLE)v8, (LARGE_INTEGER)(v3 + 87), 0, 0) )
    {
      v96 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2EC,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
              v15);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
      return v96;
    }
    if ( !SetEndOfFile((HANDLE)v8) )
    {
      v97 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2ED,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
              v16);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
      return v97;
    }
    v140 = 0;
    *(_QWORD *)pcbBinary = 0;
    v17 = Microsoft::Diagnostics::MemoryMappedStream::Create(
            (struct Microsoft::Diagnostics::MemoryMappedStream **)pcbBinary,
            (void *)v8,
            4u);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F2,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
        (const char *)(unsigned int)v17,
        dwCreationDispositiona);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
      return v18;
    }
    v19 = *(_QWORD **)pcbBinary;
    v140 = *(_QWORD **)pcbBinary;
    v135[0] = 0;
    v148 = 0;
    v139 = 0;
    v20 = 61;
    v21 = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64, unsigned int *))(**(_QWORD **)pcbBinary + 32LL))(
            *(_QWORD *)pcbBinary,
            "<?xml version=\"1.0\" encoding=\"utf-8\" ?><diagrules><scenarios>",
            61,
            &v139);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x300,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
        (const char *)(unsigned int)v21,
        dwCreationDispositiona);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
      return v22;
    }
    if ( v139 != 61 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x301,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
        (const char *)0x8007000DLL,
        dwCreationDispositiona);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
      return 2147942413LL;
    }
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 61;
    v150 = 61;
    std::wstring::wstring(v173);
    LODWORD(v152) = 0;
    v136[0] = 0;
    nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
      &v137,
      0);
    while ( !(*(unsigned int (__fastcall **)(struct Microsoft::Diagnostics::MemoryMappedStream *, char *, __int64, int *))(*(_QWORD *)v145 + 24LL))(
               v145,
               v135,
               1,
               &v148) )
    {
      v5 += v148;
      if ( v23 < 2u )
      {
        if ( v135[0] == 123 )
          ++v23;
      }
      else if ( v24 == 2 )
      {
        v29 = v135[0];
        if ( v135[0] != 123 )
          goto LABEL_26;
        v32 = std::_WChar_traits<wchar_t>::length(L"UtcSetting:");
        v33 = v173;
        if ( v175 > 7 )
          v33 = (char **)v173[0];
        if ( v174 >= v32 )
        {
          if ( (unsigned int)_o__wcsnicmp(v33, L"UtcSetting:", v32) )
            goto LABEL_25;
          v34 = 1;
          v35 = 0;
          v176 = 0;
          v177 = 0;
          v178 = 0;
          std::string::_Construct<1,char const *>(&v176, "{", 1);
          do
          {
            if ( (*(unsigned int (__fastcall **)(struct Microsoft::Diagnostics::MemoryMappedStream *, char *, __int64, int *))(*(_QWORD *)v145 + 24LL))(
                   v145,
                   v135,
                   1,
                   &v148) )
            {
              break;
            }
            v37 = v177;
            if ( v177 >= v178 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(
                &v176,
                v178,
                v36,
                (unsigned __int8)v135[0]);
            }
            else
            {
              ++v177;
              v38 = &v176;
              if ( v178 > 0xF )
                v38 = (__int128 *)v176;
              *((_BYTE *)v38 + v37) = v135[0];
              *((_BYTE *)v38 + v37 + 1) = 0;
            }
            LODWORD(v152) = (_DWORD)v152 + 1;
            ++v5;
            if ( v135[0] == 123 )
            {
              ++v34;
            }
            else if ( v135[0] == 125 )
            {
              ++v35;
            }
          }
          while ( v34 != v35 );
          if ( nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::size(v136) )
          {
            v166 = 0;
            v154 = v165;
            v157[0] = 0;
            nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
              v158,
              0);
            v45 = (unsigned int)v151 | 1;
            v149 = (unsigned int)v151 | 1;
            v151 = Src;
            v187 = 0;
            if ( v166 )
              v187 = (**v166)(v166, Src);
            v151 = Src;
            if ( v178 <= 0xF )
            {
              v47 = (char *)&v176 + v177;
              v46 = (char *)&v176;
            }
            else
            {
              v46 = (char *)v176;
              v47 = (char *)(v176 + v177);
            }
            v181[0] = v46;
            v181[1] = v47;
            v48 = std::function<void (unsigned long)>::function<void (unsigned long)>(v184, Src);
            p_IoStatusBlock = (_IO_STATUS_BLOCK *)v48;
            std::function<bool (int,enum nlohmann::json_abi_v3_11_2::detail::parse_event_t,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> &)>::function<bool (int,enum nlohmann::json_abi_v3_11_2::detail::parse_event_t,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> &)>(
              v188,
              v48);
            v189 = 0;
            nlohmann::json_abi_v3_11_2::detail::lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>(
              v190,
              v181);
            v190[152] = 1;
            v189 = nlohmann::json_abi_v3_11_2::detail::lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v190);
            std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(v48);
            LODWORD(v151) = v45 | 2;
            v149 = v45 | 2;
            std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(Src);
            nlohmann::json_abi_v3_11_2::detail::parser<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::parse(
              v188,
              v49,
              v157);
            nlohmann::json_abi_v3_11_2::detail::lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::~lexer<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,nlohmann::json_abi_v3_11_2::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>(v190);
            std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(v188);
            std::function<bool (_GUID const &)>::~function<bool (_GUID const &)>(v165);
            nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
              lpNewFileName,
              v157);
            nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_begin(lpNewFileName);
            while ( 1 )
            {
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                v184,
                v157);
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_end(v184);
              if ( nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator==<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>,0>(
                     (unsigned __int8 **)lpNewFileName,
                     v184) )
              {
                break;
              }
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::key(lpNewFileName);
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                v163,
                v136);
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_end(v163);
              if ( v136[0] == 1 )
                v163[1] = *(unsigned __int8 **)std::_Tree<std::_Tmap_traits<std::string,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>>,0>>::find(
                                                 v137,
                                                 v146,
                                                 v50);
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                v184,
                v136);
              nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_end(v184);
              if ( nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator==<nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>,0>(
                     v163,
                     v184) )
              {
                p_IoStatusBlock = &IoStatusBlock;
                v51 = nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator*(lpNewFileName);
                v52 = (unsigned __int8 *)nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>(
                                           &IoStatusBlock,
                                           v51);
                v53 = (_QWORD *)nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::key(lpNewFileName);
                v160 = 0;
                v161 = 0;
                v162 = 0;
                v54 = v53[2];
                if ( v53[3] > 0xFu )
                  v53 = (_QWORD *)*v53;
                std::string::_Construct<2,char const *>(&v160, v53, v54);
                v55 = nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::operator[](
                        v136,
                        &v160);
                v56 = *(_BYTE *)v55;
                *(_BYTE *)v55 = *v52;
                *v52 = v56;
                v57 = *(_QWORD *)(v55 + 8);
                *(_QWORD *)(v55 + 8) = *((_QWORD *)v52 + 1);
                *((_QWORD *)v52 + 1) = v57;
                nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
                  v52 + 8,
                  *v52);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator++(lpNewFileName);
              }
              else
              {
                v58 = (_QWORD *)nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::key(lpNewFileName);
                v160 = 0;
                v161 = 0;
                v162 = 0;
                v59 = v58[2];
                if ( v58[3] > 0xFu )
                  v58 = (_QWORD *)*v58;
                std::string::_Construct<2,char const *>(&v160, v58, v59);
                v60 = nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::operator[](
                        v136,
                        &v160);
                v61 = nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator->(lpNewFileName);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                  v164,
                  v61);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_end(v164);
                v62 = nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator->(lpNewFileName);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                  v185,
                  v62);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_begin(v185);
                v63 = nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator->(v163);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                  v184,
                  v63);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::set_end(v184);
                if ( *(_BYTE *)v60 != 2 )
                {
                  v153 = (const void **)nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::type_name(v60);
                  nlohmann::json_abi_v3_11_2::detail::concat<std::string,char const (&)[26],char const *>(Src);
                  nlohmann::json_abi_v3_11_2::detail::type_error::create<std::nullptr_t,0>(
                    (nlohmann::json_abi_v3_11_2::detail::type_error *)pExceptionObject,
                    309);
                  throw (nlohmann::json_abi_v3_11_2::detail::type_error *)pExceptionObject;
                }
                if ( v184[0] != (unsigned __int8 *)v60 )
                {
                  std::string::string(v184, "iterator does not fit current value", v64);
                  nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,0>(
                    (nlohmann::json_abi_v3_11_2::detail::exception *)v167,
                    202);
                  throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)v167;
                }
                if ( v185[0] != v164[0] )
                {
                  std::string::string(v184, "iterators do not fit", v64);
                  nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,0>(
                    (nlohmann::json_abi_v3_11_2::detail::exception *)v168,
                    210);
                  throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)v168;
                }
                if ( v185[0] == v60 )
                {
                  std::string::string(v184, "passed iterators may not belong to container", v64);
                  nlohmann::json_abi_v3_11_2::detail::invalid_iterator::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,0>(
                    (nlohmann::json_abi_v3_11_2::detail::exception *)v169,
                    211);
                  throw (nlohmann::json_abi_v3_11_2::detail::invalid_iterator *)v169;
                }
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const>(
                  Src,
                  v60);
                std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::_Insert_counted_range<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>(
                  *(_QWORD *)(v60 + 8),
                  v184[2],
                  v66,
                  (v65 - v66) >> 4);
                nlohmann::json_abi_v3_11_2::detail::iter_impl<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>>::operator++(lpNewFileName);
              }
            }
            LODWORD(v151) = (unsigned int)v151 & 0xFFFFFFFE;
            v149 = (int)v151;
            nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
              v158,
              (unsigned __int8)v157[0]);
          }
          else
          {
            v166 = 0;
            v39 = (unsigned __int8 *)nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::parse<std::string &>(
                                       lpExistingFileName,
                                       &v176,
                                       v165);
            v40 = v136[0];
            v136[0] = *v39;
            *v39 = v40;
            v41 = v137;
            v137 = *((_QWORD *)v39 + 1);
            *((_QWORD *)v39 + 1) = v41;
            nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
              v39 + 8,
              *v39);
          }
          v24 = 0;
          v44 = (char *)std::_WChar_traits<wchar_t>::length(&::Src);
          std::wstring::_Assign<wchar_t>(v173, &::Src, v44);
          std::string::_Tidy_deallocate(&v176);
          v26 = v150;
        }
      }
      else if ( v24 < 3u )
      {
LABEL_25:
        v29 = v135[0];
LABEL_26:
        if ( v29 == 34 )
        {
          ++v24;
        }
        else if ( v24 == 1 )
        {
          v30 = v174;
          v31 = v173;
          if ( v174 >= v175 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(
              v173,
              v174,
              v175,
              (unsigned int)(char)v29);
          }
          else
          {
            ++v174;
            if ( v175 > 7 )
              v31 = (char **)v173[0];
            *(_DWORD *)((char *)v31 + 2 * v30) = (unsigned __int16)(char)v29;
          }
        }
      }
      else if ( v135[0] == 34 )
      {
        pcbBinary[0] = v25;
        if ( !CryptStringToBinaryA((LPCSTR)(v19[1] + v26), v25, 1u, (BYTE *)(v19[1] + v26), pcbBinary, 0, 0) )
        {
          v85 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x38D,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                  v67);
          nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            &v137,
            (unsigned __int8)v136[0]);
          std::wstring::_Tidy_deallocate(v173);
          if ( v19 )
            std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v86, v19);
          AutoDeleteFile::Close((AutoDeleteFile *)v141);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          std::wstring::_Tidy_deallocate(lpFileName);
          if ( v145 )
            std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v87, v145);
          return v85;
        }
        v20 += pcbBinary[0] - v25;
        v68 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD))(*v19 + 40LL))(v19, v20, 0, 0);
        v69 = v68;
        if ( v68 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x394,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
            (const char *)(unsigned int)v68,
            dwCreationDispositiona);
          nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            &v137,
            (unsigned __int8)v136[0]);
          std::wstring::_Tidy_deallocate(v173);
          std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
          AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
          std::wstring::_Tidy_deallocate(lpFileName);
          std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
          return v69;
        }
        v26 = v20;
        v150 = v20;
        v24 = 0;
        v25 = 0;
        v70 = (char *)std::_WChar_traits<wchar_t>::length(&::Src);
        std::wstring::_Assign<wchar_t>(v173, &::Src, v70);
      }
      else
      {
        v27 = (*(__int64 (__fastcall **)(_QWORD *, char *, __int64, unsigned int *))(*v19 + 32LL))(v19, v135, 1, &v139);
        v28 = v27;
        if ( v27 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x378,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
            (const char *)(unsigned int)v27,
            dwCreationDispositiona);
          nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            &v137,
            (unsigned __int8)v136[0]);
          std::wstring::_Tidy_deallocate(v173);
          if ( v19 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v19 + 1);
            operator delete(v19, (const struct std::nothrow_t *)0x20);
          }
          if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && !v141[0] )
          {
            IoStatusBlock = 0;
            NtSetInformationFile(
              hFile,
              &IoStatusBlock,
              `AutoDeleteFile::MarkFileForDelete'::`2'::disposition,
              1u,
              FileDispositionInformation);
          }
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hFile,
            -1);
          if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hFile);
          std::wstring::_Tidy_deallocate(lpFileName);
          v42 = v145;
          if ( v145 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)v145 + 8);
            operator delete(v42, (const struct std::nothrow_t *)0x20);
          }
          return v28;
        }
        if ( v139 != 1 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x379,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
            (const char *)0x8007000DLL,
            dwCreationDispositiona);
          nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            &v137,
            (unsigned __int8)v136[0]);
          std::wstring::_Tidy_deallocate(v173);
          if ( v19 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v19 + 1);
            operator delete(v19, (const struct std::nothrow_t *)0x20);
          }
          if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && !v141[0] )
          {
            IoStatusBlock = 0;
            NtSetInformationFile(
              hFile,
              &IoStatusBlock,
              `AutoDeleteFile::MarkFileForDelete'::`2'::disposition,
              1u,
              FileDispositionInformation);
          }
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hFile,
            -1);
          if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hFile);
          std::wstring::_Tidy_deallocate(lpFileName);
          v43 = v145;
          if ( v145 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (void const *),&int UnmapViewOfFile(void const *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)v145 + 8);
            operator delete(v43, (const struct std::nothrow_t *)0x20);
          }
          return 2147942413LL;
        }
        ++v20;
        ++v25;
        v26 = v150;
      }
    }
    v71 = v153;
    if ( (_DWORD)v152 )
    {
      v92 = -1;
      v98 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(*v153, v153[1], -1, 92);
      std::wstring::wstring((__int64)v181, v71);
      if ( v98 != -1 )
      {
        v99 = std::wstring_view::substr(v71, &IoStatusBlock, v98);
        std::wstring::_Assign<wchar_t>(v181, *(const void **)v99, *(char **)(v99 + 8));
      }
      last_of = std::wstring::find_last_of(v181, 46);
      if ( last_of == -1 )
      {
        v104 = std::operator+<wchar_t>(v184, v181, L".json");
        std::wstring::operator=(v181, v104);
        v103 = v184;
      }
      else
      {
        v101 = std::wstring::substr(v181, v185, 0, last_of);
        v102 = std::operator+<wchar_t>(v184, v101, L".json");
        std::wstring::operator=(v181, v102);
        std::wstring::_Tidy_deallocate(v184);
        v103 = (unsigned __int8 **)v185;
      }
      std::wstring::_Tidy_deallocate(v103);
      std::wstring::wstring(v184);
      IoStatusBlock = *(_IO_STATUS_BLOCK *)&off_1803857F0;
      v88 = Microsoft::Diagnostics::operator+(v185);
      std::operator+<wchar_t>(lpExistingFileName, v88, v181);
      std::wstring::_Tidy_deallocate(v185);
      std::wstring::_Tidy_deallocate(v184);
      Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpExistingFileName);
      std::wstring::append(lpExistingFileName, L".temp");
      v146[0] = 0;
      v147 = -1;
      v89 = (const WCHAR *)lpExistingFileName;
      if ( v180 > 7 )
        v89 = lpExistingFileName[0];
      v90 = CreateFileW(v89, 0xC0010000, 1u, 0, 2u, 0x100u, 0);
      if ( v90 != (HANDLE)-1LL )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v147,
          v90);
        v92 = v147;
        v159 = (HANDLE)v147;
      }
      if ( (unsigned __int64)(v92 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v93 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x3C2,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                v91);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return v93;
      }
      if ( !SetFilePointerEx((HANDLE)v92, (LARGE_INTEGER)(v144 + 62LL), 0, 0) )
      {
        v106 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3C5,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v105);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return v106;
      }
      if ( !SetEndOfFile((HANDLE)v92) )
      {
        v108 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3C6,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v107);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return v108;
      }
      *(_QWORD *)pcbBinary = 0;
      v152 = 0;
      v109 = Microsoft::Diagnostics::MemoryMappedStream::Create(&v152, (void *)v92, 4u);
      v110 = v109;
      if ( v109 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3CA,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)(unsigned int)v109,
          dwCreationDispositiona);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return v110;
      }
      v111 = v152;
      *(_QWORD *)pcbBinary = v152;
      v112 = (*(__int64 (__fastcall **)(struct Microsoft::Diagnostics::MemoryMappedStream *, const char *, __int64, unsigned int *))(*(_QWORD *)v152 + 32LL))(
               v152,
               "{ \"refreshInterval\": null, \"queryUrl\" : null, \"settings\" : ",
               59,
               &v139);
      v113 = v112;
      if ( v112 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3CF,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)(unsigned int)v112,
          dwCreationDispositiona);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return v113;
      }
      if ( v139 != 59 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D0,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)0x8007000DLL,
          dwCreationDispositiona);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return 2147942413LL;
      }
      v114 = nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::dump(
               v136,
               v184);
      std::string::string(&v176, v114);
      std::string::_Tidy_deallocate(v184);
      v115 = &v176;
      if ( v178 > 0xF )
        v115 = (__int128 *)v176;
      v116 = (*(__int64 (__fastcall **)(struct Microsoft::Diagnostics::MemoryMappedStream *, __int128 *, _QWORD, unsigned int *))(*(_QWORD *)v111 + 32LL))(
               v111,
               v115,
               (unsigned int)v177,
               &v139);
      v117 = v116;
      if ( v116 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D5,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)(unsigned int)v116,
          dwCreationDispositiona);
        std::string::_Tidy_deallocate(&v176);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return v117;
      }
      v118 = v139;
      v119 = (*(__int64 (__fastcall **)(struct Microsoft::Diagnostics::MemoryMappedStream *, const char *, __int64, unsigned int *))(*(_QWORD *)v111 + 32LL))(
               v111,
               "}",
               1,
               &v139);
      v121 = v119;
      if ( v119 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)(unsigned int)v119,
          dwCreationDispositiona);
        std::string::_Tidy_deallocate(&v176);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return v121;
      }
      if ( v139 != 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)0x8007000DLL,
          dwCreationDispositiona);
        std::string::_Tidy_deallocate(&v176);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return 2147942413LL;
      }
      *(_QWORD *)pcbBinary = 0;
      if ( v111 )
        std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v120, v111);
      v122 = v159;
      if ( !SetFilePointerEx(v159, (LARGE_INTEGER)(v118 + 60), 0, 0) )
      {
        v124 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3DD,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v123);
        std::string::_Tidy_deallocate(&v176);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return v124;
      }
      if ( !SetEndOfFile(v122) )
      {
        v126 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3DE,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v125);
        std::string::_Tidy_deallocate(&v176);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return v126;
      }
      v146[0] = 1;
      AutoDeleteFile::Close((AutoDeleteFile *)v146);
      v94 = std::wstring::find_last_of(lpExistingFileName, 46);
      v95 = std::wstring::substr(lpExistingFileName, v185, 0, v94);
      if ( *(_QWORD *)(v95 + 24) > 7u )
        v95 = *(_QWORD *)v95;
      v127 = (const WCHAR *)lpExistingFileName;
      if ( v180 > 7 )
        v127 = lpExistingFileName[0];
      v128 = MoveFileExW(v127, (LPCWSTR)v95, 1u);
      std::wstring::_Tidy_deallocate(v185);
      if ( !v128 )
      {
        v130 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x3E3,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                 v129);
        std::string::_Tidy_deallocate(&v176);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v181);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        return v130;
      }
      std::string::_Tidy_deallocate(&v176);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(pcbBinary);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v146);
      std::wstring::_Tidy_deallocate(lpExistingFileName);
      std::wstring::_Tidy_deallocate(v181);
    }
    if ( v5 == v144 )
    {
      v72 = (*(__int64 (__fastcall **)(_QWORD *, const char *, __int64, unsigned int *))(*v19 + 32LL))(
              v19,
              "</scenarios></diagrules>",
              24,
              &v139);
      v74 = v72;
      if ( v72 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3EA,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)(unsigned int)v72,
          dwCreationDispositiona);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        result = v74;
      }
      else if ( v139 == 24 )
      {
        v140 = 0;
        if ( v19 )
          std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v73, v19);
        v75 = hFile;
        if ( SetFilePointerEx(hFile, (LARGE_INTEGER)(v20 + 24), 0, 0) )
        {
          if ( SetEndOfFile(v75) )
          {
            v141[0] = 1;
            AutoDeleteFile::Close((AutoDeleteFile *)v141);
            *(_OWORD *)lpNewFileName = 0;
            v183 = 0;
            std::wstring::_Construct<1,wchar_t *>(lpNewFileName, *v71, (unsigned __int64)v71[1]);
            v80 = (const WCHAR *)lpNewFileName;
            if ( *((_QWORD *)&v183 + 1) > 7u )
              v80 = lpNewFileName[0];
            v81 = (const WCHAR *)lpFileName;
            if ( *((_QWORD *)&v172 + 1) > 7u )
              v81 = lpFileName[0];
            v82 = MoveFileExW(v81, v80, 1u);
            std::wstring::_Tidy_deallocate(lpNewFileName);
            if ( v82 )
            {
              nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
                &v137,
                (unsigned __int8)v136[0]);
              std::wstring::_Tidy_deallocate(v173);
              AutoDeleteFile::Close((AutoDeleteFile *)v141);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
              std::wstring::_Tidy_deallocate(lpFileName);
              if ( v145 )
                std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v84, v145);
              result = 0;
            }
            else
            {
              v132 = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x3F7,
                       (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                       v83);
              nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
                &v137,
                (unsigned __int8)v136[0]);
              std::wstring::_Tidy_deallocate(v173);
              std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
              AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
              result = v132;
            }
          }
          else
          {
            v78 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3F2,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                    v77);
            nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
              &v137,
              (unsigned __int8)v136[0]);
            std::wstring::_Tidy_deallocate(v173);
            AutoDeleteFile::Close((AutoDeleteFile *)v141);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
            std::wstring::_Tidy_deallocate(lpFileName);
            if ( v145 )
              std::default_delete<Microsoft::Diagnostics::MemoryMappedStream>::operator()(v79, v145);
            result = v78;
          }
        }
        else
        {
          v131 = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x3F1,
                   (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                   v76);
          nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            &v137,
            (unsigned __int8)v136[0]);
          std::wstring::_Tidy_deallocate(v173);
          std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
          AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
          std::wstring::_Tidy_deallocate(lpFileName);
          std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
          result = v131;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3EB,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
          (const char *)0x8007000DLL,
          dwCreationDispositiona);
        nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
          &v137,
          (unsigned __int8)v136[0]);
        std::wstring::_Tidy_deallocate(v173);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
        AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
        result = 2147942413LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E7,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
        (const char *)0x8007000DLL,
        dwCreationDispositiona);
      nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        &v137,
        (unsigned __int8)v136[0]);
      std::wstring::_Tidy_deallocate(v173);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v140);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)v141);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(&v138);
      result = 2147942413LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3FB,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800629d0  push    rbx
0x1800629d2  push    rsi
0x1800629d3  push    rdi
0x1800629d4  push    r12
0x1800629d6  push    r13
0x1800629d8  push    r14
0x1800629da  push    r15
0x1800629dc  sub     rsp, 4F0h
0x1800629e3  mov     rax, cs:__security_cookie
0x1800629ea  xor     rax, rsp
0x1800629ed  mov     [rsp+528h+var_48], rax
0x1800629f5  mov     esi, r8d
0x1800629f8  mov     [rsp+528h+var_4A0], esi
0x1800629ff  mov     rdi, rcx
0x180062a02  mov     [rsp+528h+var_460], rcx
0x180062a0a  xor     r14d, r14d
0x180062a0d  mov     eax, r14d
0x180062a10  mov     dword ptr [rsp+528h+var_470], eax
0x180062a17  mov     [rsp+528h+var_47C], eax
0x180062a1e  mov     [rsp+528h+var_4D0], r14
0x180062a23  mov     [rsp+528h+var_498], r14
0x180062a2b  mov     r8d, 2; unsigned int
0x180062a31  lea     rcx, [rsp+528h+var_498]; struct Microsoft::Diagnostics::MemoryMappedStream **
0x180062a39  call    ?Create@MemoryMappedStream@Diagnostics@Microsoft@@SAJPEAPEAV123@PEAXK@Z; Microsoft::Diagnostics::MemoryMappedStream::Create(Microsoft::Diagnostics::MemoryMappedStream * *,void *,ulong)
0x180062a3e  mov     ebx, eax
0x180062a40  test    eax, eax
0x180062a42  js      loc_180063C44
0x180062a48  mov     rdx, [rsp+528h+var_498]
0x180062a50  mov     [rsp+528h+var_4D0], rdx
0x180062a55  xorps   xmm0, xmm0
0x180062a58  movups  xmmword ptr [rsp+528h+lpFileName], xmm0
0x180062a60  xorps   xmm1, xmm1
0x180062a63  movdqu  [rsp+528h+var_288], xmm1
0x180062a6c  mov     r8, [rdi+8]
0x180062a70  mov     rdx, [rdi]
0x180062a73  lea     rcx, [rsp+528h+lpFileName]
0x180062a7b  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180062a80  nop
0x180062a81  lea     rcx, aTemp; ".temp"
0x180062a88  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180062a8d  mov     r8, rax
0x180062a90  lea     rdx, aTemp; ".temp"
0x180062a97  lea     rcx, [rsp+528h+lpFileName]; Src
0x180062a9f  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180062aa4  mov     [rsp+528h+var_4B8], r14b
0x180062aa9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180062ab0  mov     [rsp+528h+var_420], rax
0x180062ab8  mov     rbx, rax
0x180062abb  mov     [rsp+528h+hFile], rax
0x180062ac0  lea     rcx, [rsp+528h+lpFileName]
0x180062ac8  cmp     qword ptr [rsp+528h+var_288+8], 7
0x180062ad1  cmova   rcx, [rsp+528h+lpFileName]; lpFileName
0x180062ada  mov     [rsp+528h+hTemplateFile], r14; hTemplateFile
0x180062adf  mov     [rsp+528h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x180062ae7  mov     [rsp+528h+dwCreationDisposition], 2; int
0x180062aef  xor     r9d, r9d; lpSecurityAttributes
0x180062af2  mov     edx, 0C0010000h; dwDesiredAccess
0x180062af7  mov     r8d, 1; dwShareMode
0x180062afd  call    cs:__imp_CreateFileW
0x180062b03  cmp     rax, rbx
0x180062b06  jz      short loc_180062B1A
0x180062b08  mov     rdx, rax
0x180062b0b  lea     rcx, [rsp+528h+hFile]
0x180062b10  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180062b15  mov     rbx, [rsp+528h+hFile]
0x180062b1a  lea     rax, [rbx-1]
0x180062b1e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180062b22  jbe     short loc_180062B87
0x180062b24  mov     rcx, [rsp+528h]; this
0x180062b2c  lea     r8, aOnecoreBaseTel_259; "onecore\\base\\telemetry\\utc\\service"...
0x180062b33  mov     edx, 2E3h; void *
0x180062b38  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180062b3d  mov     ebx, eax
0x180062b3f  lea     rcx, [rsp+528h+var_4B8]; this
0x180062b44  call    ??1AutoDeleteFile@@QEAA@XZ; AutoDeleteFile::~AutoDeleteFile(void)
0x180062b49  nop
0x180062b4a  lea     rcx, [rsp+528h+lpFileName]
0x180062b52  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062b57  nop
0x180062b58  lea     rcx, [rsp+528h+var_4D0]
0x180062b5d  call    ??1?$unique_ptr@VMemoryMappedStream@Diagnostics@Microsoft@@U?$default_delete@VMemoryMappedStream@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>::~unique_ptr<Microsoft::Diagnostics::MemoryMappedStream>(void)
0x180062b62  mov     eax, ebx
0x180062b64  mov     rcx, [rsp+528h+var_48]
0x180062b6c  xor     rcx, rsp; StackCookie
0x180062b6f  call    __security_check_cookie
0x180062b74  add     rsp, 4F0h
0x180062b7b  pop     r15
0x180062b7d  pop     r14
0x180062b7f  pop     r13
0x180062b81  pop     r12
0x180062b83  pop     rdi
0x180062b84  pop     rsi
0x180062b85  pop     rbx
0x180062b86  retn
0x180062b87  lea     rdx, [rsi+57h]; liDistanceToMove
0x180062b8b  xor     r9d, r9d; dwMoveMethod
0x180062b8e  xor     r8d, r8d; lpNewFilePointer
0x180062b91  mov     rcx, rbx; hFile
0x180062b94  call    cs:__imp_SetFilePointerEx
0x180062b9a  test    eax, eax
0x180062b9c  jz      loc_180063C72
0x180062ba2  mov     rcx, rbx; hFile
0x180062ba5  call    cs:__imp_SetEndOfFile
0x180062bab  test    eax, eax
0x180062bad  jz      loc_180063CB7
0x180062bb3  mov     [rsp+528h+var_4C0], r14
0x180062bb8  mov     qword ptr [rsp+528h+pcbBinary], r14
0x180062bc0  mov     r8d, 4; unsigned int
0x180062bc6  mov     rdx, rbx; void *
0x180062bc9  lea     rcx, [rsp+528h+pcbBinary]; struct Microsoft::Diagnostics::MemoryMappedStream **
0x180062bd1  call    ?Create@MemoryMappedStream@Diagnostics@Microsoft@@SAJPEAPEAV123@PEAXK@Z; Microsoft::Diagnostics::MemoryMappedStream::Create(Microsoft::Diagnostics::MemoryMappedStream * *,void *,ulong)
0x180062bd6  mov     ebx, eax
0x180062bd8  test    eax, eax
0x180062bda  js      loc_180063CFC
0x180062be0  mov     r13, qword ptr [rsp+528h+pcbBinary]
0x180062be8  mov     [rsp+528h+var_4C0], r13
0x180062bed  mov     [rsp+528h+var_4E8], 0
0x180062bf2  mov     [rsp+528h+var_480], r14d
0x180062bfa  mov     [rsp+528h+var_4C8], r14d
0x180062bff  mov     rax, [r13+0]
0x180062c03  lea     r9, [rsp+528h+var_4C8]
0x180062c08  mov     r15d, 3Dh ; '='
0x180062c0e  mov     r8d, r15d
0x180062c11  lea     rdx, aXmlVersion10En_2; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180062c18  mov     rcx, r13
0x180062c1b  mov     rax, [rax+20h]
0x180062c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c24  mov     ebx, eax
0x180062c26  test    eax, eax
0x180062c28  js      loc_180063D4E
0x180062c2e  cmp     [rsp+528h+var_4C8], r15d
0x180062c33  jnz     loc_180063DA0
0x180062c39  xor     r12b, r12b
0x180062c3c  xor     dil, dil
0x180062c3f  xor     esi, esi
0x180062c41  mov     ebx, r15d
0x180062c44  mov     [rsp+528h+var_478], ebx
0x180062c4b  lea     rcx, [rsp+528h+var_278]; void *
0x180062c53  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180062c58  nop
0x180062c59  mov     dword ptr [rsp+528h+var_468], esi
0x180062c60  mov     [rsp+528h+var_4E0], sil
0x180062c65  xor     edx, edx
0x180062c67  lea     rcx, [rsp+528h+var_4D8]
0x180062c6c  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEAA@W4value_t@detail@23@@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::json_abi_v3_11_2::detail::value_t)
0x180062c71  nop
0x180062c72  mov     rcx, [rsp+528h+var_498]
0x180062c7a  mov     rax, [rcx]
0x180062c7d  lea     r9, [rsp+528h+var_480]
0x180062c85  mov     r8d, 1
0x180062c8b  lea     rdx, [rsp+528h+var_4E8]
0x180062c90  mov     rax, [rax+18h]
0x180062c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c99  test    eax, eax
0x180062c9b  jnz     loc_1800636DA
0x180062ca1  add     r14d, [rsp+528h+var_480]
0x180062ca9  cmp     r12b, 2
0x180062cad  jb      short loc_180062D10
0x180062caf  cmp     dil, 2
0x180062cb3  jz      loc_180062D89
0x180062cb9  cmp     dil, 3
0x180062cbd  jb      short loc_180062D23
0x180062cbf  mov     r8d, 1; dwFlags
0x180062cc5  cmp     [rsp+528h+var_4E8], 22h ; '"'
0x180062cca  jz      loc_18006363B
0x180062cd0  mov     rax, [r13+0]
0x180062cd4  lea     r9, [rsp+528h+var_4C8]
0x180062cd9  lea     rdx, [rsp+528h+var_4E8]
0x180062cde  mov     rcx, r13
0x180062ce1  mov     rax, [rax+20h]
0x180062ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062cea  mov     ebx, eax
0x180062cec  test    eax, eax
0x180062cee  js      loc_180062F23
0x180062cf4  cmp     [rsp+528h+var_4C8], 1
0x180062cf9  jnz     loc_180062FE9
0x180062cff  inc     r15d
0x180062d02  inc     esi
0x180062d04  mov     ebx, [rsp+528h+var_478]
0x180062d0b  jmp     loc_180062C72
0x180062d10  cmp     [rsp+528h+var_4E8], 7Bh ; '{'
0x180062d15  jnz     loc_180062C72
0x180062d1b  inc     r12b
0x180062d1e  jmp     loc_180062C72
0x180062d23  movzx   eax, [rsp+528h+var_4E8]
0x180062d28  cmp     al, 22h ; '"'
0x180062d2a  jz      loc_180062F1B
0x180062d30  cmp     dil, 1
0x180062d34  jnz     loc_180062C72
0x180062d3a  movsx   r9d, al
0x180062d3e  mov     rdx, [rsp+528h+var_268]
0x180062d46  mov     r8, [rsp+528h+var_260]
0x180062d4e  lea     rcx, [rsp+528h+var_278]
0x180062d56  cmp     rdx, r8
0x180062d59  jnb     loc_180063986
0x180062d5f  lea     rax, [rdx+1]
0x180062d63  mov     [rsp+528h+var_268], rax
0x180062d6b  cmp     r8, 7
0x180062d6f  cmova   rcx, [rsp+528h+var_278]
0x180062d78  mov     [rcx+rdx*2], r9w
0x180062d7d  xor     eax, eax
0x180062d7f  mov     [rcx+rdx*2+2], ax
0x180062d84  jmp     loc_180062C72
0x180062d89  movzx   eax, [rsp+528h+var_4E8]
0x180062d8e  cmp     al, 7Bh ; '{'
0x180062d90  jnz     short loc_180062D28
0x180062d92  lea     rcx, aUtcsetting; "UtcSetting:"
0x180062d99  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180062d9e  lea     rcx, [rsp+528h+var_278]
0x180062da6  cmp     [rsp+528h+var_260], 7
0x180062daf  cmova   rcx, [rsp+528h+var_278]
0x180062db8  cmp     [rsp+528h+var_268], rax
0x180062dc0  jb      loc_180062C72
0x180062dc6  mov     r8, rax
0x180062dc9  lea     rdx, aUtcsetting; "UtcSetting:"
0x180062dd0  call    cs:__imp__o__wcsnicmp
0x180062dd6  test    eax, eax
0x180062dd8  jnz     loc_180062D23
0x180062dde  mov     ebx, 1
0x180062de3  xor     eax, eax
0x180062de5  mov     edi, eax
0x180062de7  xorps   xmm0, xmm0
0x180062dea  movups  [rsp+528h+var_258], xmm0
0x180062df2  mov     [rsp+528h+var_248], rax
0x180062dfa  mov     [rsp+528h+var_240], rax
0x180062e02  mov     r8d, ebx
0x180062e05  lea     rdx, asc_180395B50; "{"
0x180062e0c  lea     rcx, [rsp+528h+var_258]
0x180062e14  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180062e19  nop
0x180062e1a  mov     rcx, [rsp+528h+var_498]
0x180062e22  mov     rax, [rcx]
0x180062e25  lea     r9, [rsp+528h+var_480]
0x180062e2d  mov     r8d, 1
0x180062e33  lea     rdx, [rsp+528h+var_4E8]
0x180062e38  mov     rax, [rax+18h]
0x180062e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e41  test    eax, eax
0x180062e43  jnz     short loc_180062EB3
0x180062e45  movzx   r9d, [rsp+528h+var_4E8]
0x180062e4b  mov     rcx, [rsp+528h+var_248]
0x180062e53  mov     rdx, [rsp+528h+var_240]
0x180062e5b  cmp     rcx, rdx
0x180062e5e  jnb     loc_180063974
0x180062e64  lea     rax, [rcx+1]
0x180062e68  mov     [rsp+528h+var_248], rax
0x180062e70  lea     rax, [rsp+528h+var_258]
0x180062e78  cmp     rdx, 0Fh
0x180062e7c  cmova   rax, qword ptr [rsp+528h+var_258]
0x180062e85  mov     [rcx+rax], r9b
0x180062e89  mov     byte ptr [rcx+rax+1], 0
0x180062e8e  inc     dword ptr [rsp+528h+var_468]
0x180062e95  inc     r14d
0x180062e98  movzx   eax, [rsp+528h+var_4E8]
0x180062e9d  cmp     al, 7Bh ; '{'
0x180062e9f  jz      loc_1800630B5
0x180062ea5  cmp     al, 7Dh ; '}'
0x180062ea7  jnz     short loc_180062EAB
0x180062ea9  inc     edi
0x180062eab  cmp     ebx, edi
0x180062ead  jnz     loc_180062E1A
0x180062eb3  lea     rcx, [rsp+528h+var_4E0]
0x180062eb8  call    ?size@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEBA_KXZ; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::size(void)
0x180062ebd  test    rax, rax
0x180062ec0  jnz     loc_18006312A
0x180062ec6  mov     [rsp+528h+var_380], rax
0x180062ece  lea     r8, [rsp+528h+var_3B8]
0x180062ed6  lea     rdx, [rsp+528h+var_258]
0x180062ede  lea     rcx, [rsp+528h+lpExistingFileName]
0x180062ee6  call    ??$parse@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@SA?AV012@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$function@$$A6A_NHW4parse_event_t@detail@json_abi_v3_11_2@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@34@@Z@4@_N2@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::parse<std::string &>(std::string &,std::function<bool (int,nlohmann::json_abi_v3_11_2::detail::parse_event_t,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> &)>,bool,bool)
0x180062eeb  movzx   edx, [rsp+528h+var_4E0]
0x180062ef0  movzx   ecx, byte ptr [rax]
0x180062ef3  mov     [rsp+528h+var_4E0], cl
0x180062ef7  mov     [rax], dl
0x180062ef9  mov     r8, [rsp+528h+var_4D8]
0x180062efe  lea     rcx, [rax+8]
0x180062f02  mov     rdx, [rcx]
0x180062f05  mov     [rsp+528h+var_4D8], rdx
0x180062f0a  mov     [rcx], r8
0x180062f0d  movzx   edx, byte ptr [rax]
0x180062f10  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEAAXW4value_t@detail@34@@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::json_abi_v3_11_2::detail::value_t)
0x180062f15  nop
0x180062f16  jmp     loc_1800630EA
0x180062f1b  inc     dil
0x180062f1e  jmp     loc_180062C72
0x180062f23  mov     rcx, [rsp+528h]; this
0x180062f2b  mov     r9d, ebx; char *
0x180062f2e  lea     r8, aOnecoreBaseTel_259; "onecore\\base\\telemetry\\utc\\service"...
0x180062f35  mov     edx, 378h; void *
0x180062f3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062f3f  nop
0x180062f40  movzx   edx, [rsp+528h+var_4E0]
0x180062f45  lea     rcx, [rsp+528h+var_4D8]
0x180062f4a  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEAAXW4value_t@detail@34@@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::json_abi_v3_11_2::detail::value_t)
0x180062f4f  nop
0x180062f50  lea     rcx, [rsp+528h+var_278]
0x180062f58  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062f5d  nop
0x180062f5e  test    r13, r13
0x180062f61  jz      short loc_180062F7A
  ... truncated ...
```
