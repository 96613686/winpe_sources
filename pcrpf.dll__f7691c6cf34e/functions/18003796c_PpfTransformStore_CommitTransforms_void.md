# PpfTransformStore::CommitTransforms(void)

- ea: `0x18003796c`
- end: `0x180038a43`
- name: `?CommitTransforms@PpfTransformStore@@QEAAJXZ`
- size: `4311`
- prototype: `__int64 __fastcall(PpfTransformStore *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000fec8`

## callees

- `0x180003270`
- `0x18000367c`
- `0x180009c64`
- `0x18000b5c8`
- `0x18000c6d0`
- `0x18000c73c`
- `0x18000dfe0`
- `0x18000ee8c`
- `0x18000f1e4`
- `0x18000f750`
- `0x1800181fc`
- `0x18001aff0`
- `0x18001c48c`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x180032cec`
- `0x180033ae4`
- `0x18003796c`
- `0x180039354`
- `0x1800395d4`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003894c`
- `ntdll!EtwEventWrite` at `0x18003894c`
- `ntdll!NtCreateRegistryTransaction` at `0x180037c1b`
- `ntdll!NtCreateRegistryTransaction` at `0x180037c1b`
- `ntdll!NtCommitRegistryTransaction` at `0x1800387d9`
- `ntdll!NtCommitRegistryTransaction` at `0x1800387d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037af2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037b2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037bfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003803f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038178`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037af2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037b2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037bfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003803f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038159`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037ae4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037bee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037c52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037cea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037de4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037ea2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800380f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038322`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800383ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038452`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800384ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038582`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038640`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800386d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038780`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003881d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800388b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003898a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037ae4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037bee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037c52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037cea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037de4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037ea2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800380f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038322`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800383ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038452`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800384ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038582`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038640`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800386d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038780`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003881d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800388b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003898a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037b1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037b98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037c67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037cff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037d5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037df9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037eb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037f90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038031`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800380d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003810e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003816a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800382c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038300`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038337`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038398`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800383cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038430`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800384c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800384ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038560`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038597`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038655`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800386e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038795`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038832`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800388cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003899f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037b1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037b98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037c67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037cff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037d5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037df9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037eb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037f90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038031`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800380d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003810e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003816a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800382c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038300`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038337`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038398`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800383cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038430`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800384c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800384ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038560`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038597`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038655`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800386e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038795`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038832`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800388cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003899f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038205`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003823e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038277`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800382b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800385fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038205`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003823e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038277`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800382b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800385fc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180037f24`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180037f24`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180038874`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180038874`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x1800380a0`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x1800381d0`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x1800380a0`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x1800381d0`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180037da0`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180037da0`

## string_xrefs

- `0x180037997`: `PpfTransformStore::CommitTransforms`
- `0x180037ba5`: `PpfTransformStore::CommitTransforms`
- `0x180037c74`: `PpfTransformStore::CommitTransforms`
- `0x180037d0c`: `PpfTransformStore::CommitTransforms`
- `0x180037e06`: `PpfTransformStore::CommitTransforms`
- `0x180037ec4`: `PpfTransformStore::CommitTransforms`
- `0x180037f9d`: `PpfTransformStore::CommitTransforms`
- `0x18003811b`: `PpfTransformStore::CommitTransforms`
- `0x180038344`: `PpfTransformStore::CommitTransforms`
- `0x1800383dc`: `PpfTransformStore::CommitTransforms`
- `0x180038474`: `PpfTransformStore::CommitTransforms`
- `0x18003850c`: `PpfTransformStore::CommitTransforms`
- `0x1800385a4`: `PpfTransformStore::CommitTransforms`
- `0x180038662`: `PpfTransformStore::CommitTransforms`
- `0x1800386f5`: `PpfTransformStore::CommitTransforms`
- `0x1800387a2`: `PpfTransformStore::CommitTransforms`
- `0x18003883f`: `PpfTransformStore::CommitTransforms`
- `0x1800388da`: `PpfTransformStore::CommitTransforms`
- `0x1800389ac`: `PpfTransformStore::CommitTransforms`

## pseudocode

```c
// Hidden C++ exception states: #wind=54
__int64 __fastcall PpfTransformStore::CommitTransforms(PpfTransformStore *this)
{
  const char *v1; // r9
  __int64 v2; // rdi
  _QWORD *i; // rbx
  const wchar_t *v4; // r14
  const char *v5; // r9
  __int64 v6; // rsi
  unsigned __int64 v7; // r12
  const wchar_t *v8; // rdx
  unsigned __int64 v9; // r15
  size_t v10; // r8
  int v11; // eax
  __int64 v12; // rax
  PpfTransformStore *v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  _QWORD *v20; // rax
  int SubKeyNamesFromRegKey; // eax
  _QWORD *v22; // rdi
  _QWORD *j; // rbx
  const WCHAR *v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // rdi
  _QWORD *k; // rbx
  const WCHAR *v28; // r15
  __int64 v29; // r13
  char IsEnabled; // al
  HKEY v31; // r12
  WCHAR *v32; // rcx
  DWORD LastError; // esi
  unsigned int v34; // eax
  WCHAR *v35; // rax
  DWORD v36; // esi
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  PpfTransformStore *v43; // rcx
  int v44; // eax
  const char *v45; // r9
  int v46; // eax
  int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  int phkResult; // [rsp+20h] [rbp-89h]
  unsigned int phkResulta; // [rsp+20h] [rbp-89h]
  unsigned int phkResultb; // [rsp+20h] [rbp-89h]
  unsigned int phkResultc; // [rsp+20h] [rbp-89h]
  unsigned int phkResultd; // [rsp+20h] [rbp-89h]
  unsigned int phkResulte; // [rsp+20h] [rbp-89h]
  unsigned int phkResultf; // [rsp+20h] [rbp-89h]
  unsigned int phkResultg; // [rsp+20h] [rbp-89h]
  unsigned int phkResulth; // [rsp+20h] [rbp-89h]
  HKEY hKey; // [rsp+60h] [rbp-49h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-41h] BYREF
  HKEY v61; // [rsp+70h] [rbp-39h] BYREF
  __int128 v62; // [rsp+78h] [rbp-31h] BYREF
  PpfTransformStore *v63; // [rsp+88h] [rbp-21h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v65; // [rsp+A0h] [rbp-9h]
  unsigned __int64 v66; // [rsp+A8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v63 = this;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfTransformStore::CommitTransforms");
  if ( dword_180072BF8 != 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      v1);
  if ( qword_180072C08 != qword_180072C18 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      v1);
  v2 = qword_180072C00;
  for ( i = *(_QWORD **)qword_180072C00; i != (_QWORD *)v2; i = (_QWORD *)*i )
  {
    v4 = (const wchar_t *)(i + 2);
    std::_Tree<std::_Tmap_traits<std::wstring,PpfTransformInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PpfTransformInfo>>,0>>::_Find_lower_bound<std::wstring>(
      &qword_180072C10,
      lpSubKey,
      i + 2);
    v6 = v65;
    if ( !*(_BYTE *)(v65 + 25) )
    {
      v7 = *(_QWORD *)(v65 + 48);
      v8 = (const wchar_t *)(v65 + 32);
      if ( *(_QWORD *)(v65 + 56) > 7u )
        v8 = *(const wchar_t **)v8;
      v9 = i[4];
      if ( i[5] > 7u )
        v4 = *(const wchar_t **)v4;
      v10 = *(_QWORD *)(v65 + 48);
      if ( v7 >= v9 )
        v10 = i[4];
      v11 = wmemcmp(v4, v8, v10);
      if ( v11 )
      {
        if ( v11 >= 0 )
          goto LABEL_16;
      }
      else if ( v9 >= v7 )
      {
LABEL_16:
        v12 = qword_180072C10;
        goto LABEL_18;
      }
    }
    v12 = qword_180072C10;
    v6 = qword_180072C10;
LABEL_18:
    if ( v6 == v12 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
        v5);
  }
  hKey = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
  {
    hObject = 0;
    v17 = NtCreateRegistryTransaction(&hObject, 2031679, 0, 0);
    if ( v17 >= 0 )
    {
      v61 = 0;
      v18 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)&v61);
      v15 = v18;
      if ( v18 >= 0 )
      {
        hKey = 0;
        v19 = RegOpenKeyTransactedW(v61, L"Control\\PCRPF\\Transforms", 0, 0x2001Fu, &hKey, hObject, 0);
        if ( !v19 )
        {
          PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)&v61);
          goto LABEL_43;
        }
        v15 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xC6,
                (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
                (const char *)v19,
                phkResulta);
        PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)&v61);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        if ( hKey )
          RegCloseKey(hKey);
LABEL_26:
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "PpfTransformStore::CommitTransforms");
        return v15;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
        (const char *)(unsigned int)v18,
        phkResult);
      PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)&v61);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
    }
    else
    {
      v15 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xC2,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
              (const char *)(unsigned int)v17,
              phkResult);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
    }
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTransformStore::CommitTransforms");
    return v15;
  }
  hObject = 0;
  hKey = 0;
  v14 = PpfTransformStore::OpenTransformsKey(v13, 0x2001Fu, 1, &hKey, &hObject);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)(unsigned int)v14,
      phkResulta);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_26;
  }
LABEL_43:
  v62 = 0;
  v20 = operator new(0x30u);
  *v20 = v20;
  v20[1] = v20;
  *(_QWORD *)&v62 = v20;
  SubKeyNamesFromRegKey = PpfhGetSubKeyNamesFromRegKey(hKey);
  v15 = SubKeyNamesFromRegKey;
  if ( SubKeyNamesFromRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)(unsigned int)SubKeyNamesFromRegKey,
      phkResulta);
    std::list<std::wstring>::~list<std::wstring>(&v62);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_26;
  }
  v22 = (_QWORD *)v62;
  for ( j = *(_QWORD **)v62; j != v22; j = (_QWORD *)*j )
  {
    std::wstring::wstring(lpSubKey, j + 2);
    v24 = (const WCHAR *)lpSubKey;
    if ( v66 > 7 )
      v24 = lpSubKey[0];
    v25 = RegDeleteTreeW(hKey, v24);
    if ( v25 )
    {
      v15 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xCC,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
              (const char *)v25,
              phkResulta);
      std::wstring::~wstring(lpSubKey);
      std::list<std::wstring>::~list<std::wstring>(&v62);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_26;
    }
    std::wstring::~wstring(lpSubKey);
  }
  v26 = qword_180072C00;
  for ( k = *(_QWORD **)qword_180072C00; k != (_QWORD *)v26; k = (_QWORD *)*k )
  {
    v28 = (const WCHAR *)(k + 2);
    v29 = std::map<std::wstring,PpfTransformInfo>::operator[](&qword_180072C10, k + 2);
    v61 = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl);
    v31 = v61;
    if ( IsEnabled )
    {
      v32 = (WCHAR *)hObject;
      lpSubKey[0] = (LPCWSTR)hObject;
      if ( v61 )
      {
        LastError = GetLastError();
        RegCloseKey(v31);
        SetLastError(LastError);
        v32 = (WCHAR *)lpSubKey[0];
      }
      v61 = 0;
      if ( k[5] > 7u )
        v28 = *(const WCHAR **)v28;
      v34 = RegCreateKeyTransactedW(hKey, v28, 0, 0, *(_DWORD *)v29 == 0, 0x20006u, 0, &v61, 0, v32, 0);
      if ( v34 )
      {
        v15 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xD9,
                (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
                (const char *)v34,
                phkResultb);
        if ( v61 )
          RegCloseKey(v61);
        std::list<std::wstring>::~list<std::wstring>(&v62);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_26;
      }
    }
    else
    {
      v35 = (WCHAR *)hObject;
      lpSubKey[0] = (LPCWSTR)hObject;
      if ( v61 )
      {
        v36 = GetLastError();
        RegCloseKey(v31);
        SetLastError(v36);
        v35 = (WCHAR *)lpSubKey[0];
      }
      v61 = 0;
      if ( k[5] > 7u )
        v28 = *(const WCHAR **)v28;
      v37 = RegCreateKeyTransactedW(hKey, v28, 0, 0, 0, 0x20006u, 0, &v61, 0, v35, 0);
      if ( v37 )
      {
        v15 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xDE,
                (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
                (const char *)v37,
                phkResultc);
        if ( v61 )
          RegCloseKey(v61);
        std::list<std::wstring>::~list<std::wstring>(&v62);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_26;
      }
    }
    v38 = RegSetValueExW(v61, L"Timeline", 0, 4u, (const BYTE *)v29, 4u);
    if ( v38 )
    {
      v15 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xE2,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
              (const char *)v38,
              phkResultd);
      if ( v61 )
        RegCloseKey(v61);
      std::list<std::wstring>::~list<std::wstring>(&v62);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_26;
    }
    v39 = RegSetValueExW(v61, L"Data", 0, 3u, *(const BYTE **)(v29 + 8), *(_DWORD *)(v29 + 16));
    if ( v39 )
    {
      v15 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xE4,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
              (const char *)v39,
              phkResulte);
      if ( v61 )
        RegCloseKey(v61);
      std::list<std::wstring>::~list<std::wstring>(&v62);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_26;
    }
    v40 = RegSetValueExW(v61, L"ImpactedEvents", 0, 3u, *(const BYTE **)(v29 + 24), *(_DWORD *)(v29 + 32));
    if ( v40 )
    {
      v15 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xE6,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
              (const char *)v40,
              phkResultf);
      if ( v61 )
        RegCloseKey(v61);
      std::list<std::wstring>::~list<std::wstring>(&v62);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_26;
    }
    v41 = RegSetValueExW(v61, L"ImpactedPcrBitmap", 0, 4u, (const BYTE *)(v29 + 36), 4u);
    if ( v41 )
    {
      v15 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xE8,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
              (const char *)v41,
              phkResultg);
      if ( v61 )
        RegCloseKey(v61);
      std::list<std::wstring>::~list<std::wstring>(&v62);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_26;
    }
    if ( v61 )
      RegCloseKey(v61);
  }
  v42 = RegSetValueExW(hKey, L"Usn", 0, 0xBu, &Data, 8u);
  if ( v42 )
  {
    v15 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xEC,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
            (const char *)v42,
            phkResulth);
    std::list<std::wstring>::~list<std::wstring>(&v62);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_26;
  }
  v44 = PpfTransformStore::MarkUpdateInProgress(v43, hKey, 0);
  v15 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)(unsigned int)v44,
      phkResulth);
    std::list<std::wstring>::~list<std::wstring>(&v62);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_26;
  }
  if ( !byte_180072C28 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      v45);
  v46 = PpfhSetVolatileRegBoolean(L"PerBootCleanupDone", hObject);
  v15 = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      (const char *)(unsigned int)v46,
      phkResulth);
    std::list<std::wstring>::~list<std::wstring>(&v62);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_26;
  }
  v47 = NtCommitRegistryTransaction(hObject, 0);
  if ( v47 < 0 )
  {
    v15 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0xFC,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
            (const char *)(unsigned int)v47,
            phkResulth);
    std::list<std::wstring>::~list<std::wstring>(&v62);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_26;
  }
  v48 = RegFlushKey(hKey);
  if ( v48 )
  {
    v15 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xFD,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
            (const char *)v48,
            phkResulth);
    std::list<std::wstring>::~list<std::wstring>(&v62);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_26;
  }
  dword_180072BF8 = 1;
  *((_BYTE *)v63 + 96) = 0;
  v63 = *(PpfTransformStore **)&Data;
  lpSubKey[0] = (LPCWSTR)&v63;
  lpSubKey[1] = (LPCWSTR)8;
  v49 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORMS_COMMITTED, 1, lpSubKey);
  if ( v49 )
    wil::details::in1diag3::Return_Win32(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)v49,
      phkResulth);
  std::list<std::wstring>::~list<std::wstring>(&v62);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( hKey )
    RegCloseKey(hKey);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfTransformStore::CommitTransforms");
  return 0;
}

```

## disassembly

```asm
0x18003796c  push    rbp
0x18003796e  push    rbx
0x18003796f  push    rsi
0x180037970  push    rdi
0x180037971  push    r12
0x180037973  push    r13
0x180037975  push    r14
0x180037977  push    r15
0x180037979  lea     rbp, [rsp-1Fh]
0x18003797e  sub     rsp, 0C8h
0x180037985  mov     rax, cs:__security_cookie
0x18003798c  xor     rax, rsp
0x18003798f  mov     [rbp+57h+var_50], rax
0x180037993  mov     [rbp+57h+var_78], rcx
0x180037997  lea     r15, aPpftransformst; "PpfTransformStore::CommitTransforms"
0x18003799e  mov     [rsp+100h+phkResult], r15; int
0x1800379a3  lea     r9, aEnteringHs; "Entering %hs"
0x1800379aa  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x1800379b1  mov     edx, 84h; unsigned int
0x1800379b6  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800379bd  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800379c2  cmp     cs:dword_180072BF8, 2
0x1800379c9  setnz   al
0x1800379cc  mov     rcx, [rbp+5Fh]; this
0x1800379d0  xor     r12d, r12d
0x1800379d3  test    al, al
0x1800379d5  jnz     loc_180038A0D
0x1800379db  mov     rax, cs:qword_180072C18
0x1800379e2  cmp     cs:qword_180072C08, rax
0x1800379e9  setnz   al
0x1800379ec  mov     rcx, [rbp+5Fh]; this
0x1800379f0  test    al, al
0x1800379f2  jnz     loc_180038A1F
0x1800379f8  mov     rdi, cs:qword_180072C00
0x1800379ff  mov     rbx, [rdi]
0x180037a02  cmp     rbx, rdi
0x180037a05  jz      loc_180037AA3
0x180037a0b  lea     r14, [rbx+10h]
0x180037a0f  mov     r8, r14
0x180037a12  lea     rdx, [rbp+57h+lpSubKey]
0x180037a16  lea     rcx, qword_180072C10
0x180037a1d  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPpfTransformInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPpfTransformInfo@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPpfTransformInfo@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PpfTransformInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PpfTransformInfo>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180037a22  mov     rsi, [rbp+57h+var_60]
0x180037a26  cmp     [rsi+19h], r12b
0x180037a2a  jnz     short loc_180037A7F
0x180037a2c  mov     r12, [rsi+30h]
0x180037a30  lea     rdx, [rsi+20h]
0x180037a34  cmp     qword ptr [rsi+38h], 7
0x180037a39  jbe     short loc_180037A3E
0x180037a3b  mov     rdx, [rdx]; S2
0x180037a3e  mov     r15, [rbx+20h]
0x180037a42  cmp     qword ptr [r14+18h], 7
0x180037a47  jbe     short loc_180037A4C
0x180037a49  mov     r14, [r14]
0x180037a4c  mov     r8, r12
0x180037a4f  cmp     r12, r15
0x180037a52  cmovnb  r8, r15; N
0x180037a56  mov     rcx, r14; S1
0x180037a59  call    wmemcmp
0x180037a5e  test    eax, eax
0x180037a60  jz      short loc_180037A6B
0x180037a62  xor     r12d, r12d
0x180037a65  test    eax, eax
0x180037a67  jns     short loc_180037A73
0x180037a69  jmp     short loc_180037A7F
0x180037a6b  cmp     r15, r12
0x180037a6e  jb      short loc_180037A7C
0x180037a70  xor     r12d, r12d
0x180037a73  mov     rax, cs:qword_180072C10
0x180037a7a  jmp     short loc_180037A89
0x180037a7c  xor     r12d, r12d
0x180037a7f  mov     rax, cs:qword_180072C10
0x180037a86  mov     rsi, rax
0x180037a89  cmp     rsi, rax
0x180037a8c  setz    al
0x180037a8f  mov     rcx, [rbp+5Fh]; this
0x180037a93  test    al, al
0x180037a95  jnz     loc_180038A31
0x180037a9b  mov     rbx, [rbx]
0x180037a9e  jmp     loc_180037A02
0x180037aa3  mov     [rbp+57h+hKey], r12
0x180037aa7  mov     [rbp+57h+hObject], r12
0x180037aab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x180037ab2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x180037ab7  mov     rdi, [rbp+57h+hObject]
0x180037abb  mov     r14, 0FFFFFFFFFFFFFFFDh
0x180037ac2  test    al, al
0x180037ac4  lea     rax, [rdi-1]
0x180037ac8  jz      loc_180037BD8
0x180037ace  cmp     rax, r14
0x180037ad1  ja      short loc_180037AFE
0x180037ad3  call    cs:__imp_GetLastError
0x180037ada  nop     dword ptr [rax+rax+00h]
0x180037adf  mov     ebx, eax
0x180037ae1  mov     rcx, rdi; hObject
0x180037ae4  call    cs:__imp_CloseHandle
0x180037aeb  nop     dword ptr [rax+rax+00h]
0x180037af0  mov     ecx, ebx; dwErrCode
0x180037af2  call    cs:__imp_SetLastError
0x180037af9  nop     dword ptr [rax+rax+00h]
0x180037afe  mov     [rbp+57h+hObject], r12
0x180037b02  mov     rdi, [rbp+57h+hKey]
0x180037b06  test    rdi, rdi
0x180037b09  jz      short loc_180037B36
0x180037b0b  call    cs:__imp_GetLastError
0x180037b12  nop     dword ptr [rax+rax+00h]
0x180037b17  mov     ebx, eax
0x180037b19  mov     rcx, rdi; hKey
0x180037b1c  call    cs:__imp_RegCloseKey
0x180037b23  nop     dword ptr [rax+rax+00h]
0x180037b28  mov     ecx, ebx; dwErrCode
0x180037b2a  call    cs:__imp_SetLastError
0x180037b31  nop     dword ptr [rax+rax+00h]
0x180037b36  mov     [rbp+57h+hKey], r12
0x180037b3a  lea     rax, [rbp+57h+hObject]
0x180037b3e  mov     [rsp+100h+phkResult], rax; int
0x180037b43  lea     r9, [rbp+57h+hKey]; HKEY *
0x180037b47  mov     r8b, 1; bool
0x180037b4a  mov     edx, 2001Fh; unsigned int
0x180037b4f  call    ?OpenTransformsKey@PpfTransformStore@@AEAAJK_NPEAPEAUHKEY__@@PEAPEAX@Z; PpfTransformStore::OpenTransformsKey(ulong,bool,HKEY__ * *,void * *)
0x180037b54  mov     ebx, eax
0x180037b56  test    eax, eax
0x180037b58  jns     loc_180037E40
0x180037b5e  mov     rcx, [rbp+5Fh]; this
0x180037b62  mov     r9d, eax; char *
0x180037b65  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037b6c  mov     edx, 0BEh; void *
0x180037b71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037b76  mov     rcx, [rbp+57h+hObject]; hObject
0x180037b7a  lea     rdx, [rcx-1]
0x180037b7e  cmp     rdx, r14
0x180037b81  ja      short loc_180037B8F
0x180037b83  call    cs:__imp_CloseHandle
0x180037b8a  nop     dword ptr [rax+rax+00h]
0x180037b8f  mov     rcx, [rbp+57h+hKey]; hKey
0x180037b93  test    rcx, rcx
0x180037b96  jz      short loc_180037BA5
0x180037b98  call    cs:__imp_RegCloseKey
0x180037b9f  nop     dword ptr [rax+rax+00h]
0x180037ba4  nop
0x180037ba5  lea     rax, aPpftransformst; "PpfTransformStore::CommitTransforms"
0x180037bac  mov     [rsp+100h+phkResult], rax
0x180037bb1  lea     r9, aLeavingHs; "Leaving %hs"
0x180037bb8  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180037bbf  mov     edx, 89h; unsigned int
0x180037bc4  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037bcb  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180037bd0  nop
0x180037bd1  mov     eax, ebx
0x180037bd3  jmp     loc_1800389DA
0x180037bd8  cmp     rax, r14
0x180037bdb  ja      short loc_180037C08
0x180037bdd  call    cs:__imp_GetLastError
0x180037be4  nop     dword ptr [rax+rax+00h]
0x180037be9  mov     ebx, eax
0x180037beb  mov     rcx, rdi; hObject
0x180037bee  call    cs:__imp_CloseHandle
0x180037bf5  nop     dword ptr [rax+rax+00h]
0x180037bfa  mov     ecx, ebx; dwErrCode
0x180037bfc  call    cs:__imp_SetLastError
0x180037c03  nop     dword ptr [rax+rax+00h]
0x180037c08  mov     [rbp+57h+hObject], r12
0x180037c0c  xor     r9d, r9d
0x180037c0f  xor     r8d, r8d
0x180037c12  mov     edx, 1F003Fh
0x180037c17  lea     rcx, [rbp+57h+hObject]
0x180037c1b  call    cs:__imp_NtCreateRegistryTransaction
0x180037c22  nop     dword ptr [rax+rax+00h]
0x180037c27  test    eax, eax
0x180037c29  jns     short loc_180037CA5
0x180037c2b  mov     rcx, [rbp+5Fh]; this
0x180037c2f  mov     r9d, eax; char *
0x180037c32  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037c39  mov     edx, 0C2h; void *
0x180037c3e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180037c43  mov     ebx, eax
0x180037c45  mov     rcx, [rbp+57h+hObject]; hObject
0x180037c49  lea     rdx, [rcx-1]
0x180037c4d  cmp     rdx, r14
0x180037c50  ja      short loc_180037C5E
0x180037c52  call    cs:__imp_CloseHandle
0x180037c59  nop     dword ptr [rax+rax+00h]
0x180037c5e  mov     rcx, [rbp+57h+hKey]; hKey
0x180037c62  test    rcx, rcx
0x180037c65  jz      short loc_180037C74
0x180037c67  call    cs:__imp_RegCloseKey
0x180037c6e  nop     dword ptr [rax+rax+00h]
0x180037c73  nop
0x180037c74  lea     rax, aPpftransformst; "PpfTransformStore::CommitTransforms"
0x180037c7b  mov     [rsp+100h+phkResult], rax
0x180037c80  lea     r9, aLeavingHs; "Leaving %hs"
0x180037c87  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180037c8e  mov     edx, 89h; unsigned int
0x180037c93  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037c9a  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180037c9f  nop
0x180037ca0  jmp     loc_180037BD1
0x180037ca5  mov     [rbp+57h+var_90], r12
0x180037ca9  lea     rcx, [rbp+57h+var_90]; this
0x180037cad  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x180037cb2  mov     ebx, eax
0x180037cb4  test    eax, eax
0x180037cb6  jns     loc_180037D3D
0x180037cbc  mov     rcx, [rbp+5Fh]; this
0x180037cc0  mov     r9d, eax; char *
0x180037cc3  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037cca  mov     edx, 0C4h; void *
0x180037ccf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037cd4  lea     rcx, [rbp+57h+var_90]; this
0x180037cd8  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180037cdd  mov     rcx, [rbp+57h+hObject]; hObject
0x180037ce1  lea     rdx, [rcx-1]
0x180037ce5  cmp     rdx, r14
0x180037ce8  ja      short loc_180037CF6
0x180037cea  call    cs:__imp_CloseHandle
0x180037cf1  nop     dword ptr [rax+rax+00h]
0x180037cf6  mov     rcx, [rbp+57h+hKey]; hKey
0x180037cfa  test    rcx, rcx
0x180037cfd  jz      short loc_180037D0C
0x180037cff  call    cs:__imp_RegCloseKey
0x180037d06  nop     dword ptr [rax+rax+00h]
0x180037d0b  nop
0x180037d0c  lea     rax, aPpftransformst; "PpfTransformStore::CommitTransforms"
0x180037d13  mov     [rsp+100h+phkResult], rax
0x180037d18  lea     r9, aLeavingHs; "Leaving %hs"
0x180037d1f  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180037d26  mov     edx, 89h; unsigned int
0x180037d2b  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037d32  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180037d37  nop
0x180037d38  jmp     loc_180037BD1
0x180037d3d  mov     rsi, [rbp+57h+hObject]
0x180037d41  mov     rdi, [rbp+57h+hKey]
0x180037d45  test    rdi, rdi
0x180037d48  jz      short loc_180037D75
0x180037d4a  call    cs:__imp_GetLastError
0x180037d51  nop     dword ptr [rax+rax+00h]
0x180037d56  mov     ebx, eax
0x180037d58  mov     rcx, rdi; hKey
0x180037d5b  call    cs:__imp_RegCloseKey
0x180037d62  nop     dword ptr [rax+rax+00h]
0x180037d67  mov     ecx, ebx; dwErrCode
0x180037d69  call    cs:__imp_SetLastError
0x180037d70  nop     dword ptr [rax+rax+00h]
0x180037d75  mov     [rbp+57h+hKey], r12
0x180037d79  mov     [rsp+100h+pExtendedParemeter], r12; pExtendedParemeter
0x180037d7e  mov     [rsp+100h+hTransaction], rsi; hTransaction
0x180037d83  lea     rax, [rbp+57h+hKey]
0x180037d87  mov     [rsp+100h+phkResult], rax; unsigned int
0x180037d8c  mov     r9d, 2001Fh; samDesired
0x180037d92  xor     r8d, r8d; ulOptions
0x180037d95  lea     rdx, aControlPcrpfTr; "Control\\PCRPF\\Transforms"
0x180037d9c  mov     rcx, [rbp+57h+var_90]; hKey
0x180037da0  call    cs:__imp_RegOpenKeyTransactedW
0x180037da7  nop     dword ptr [rax+rax+00h]
0x180037dac  test    eax, eax
0x180037dae  jz      loc_180037E37
0x180037db4  mov     rcx, [rbp+5Fh]; this
0x180037db8  mov     r9d, eax; char *
0x180037dbb  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037dc2  mov     edx, 0C6h; void *
0x180037dc7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180037dcc  mov     ebx, eax
0x180037dce  lea     rcx, [rbp+57h+var_90]; this
0x180037dd2  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180037dd7  mov     rcx, [rbp+57h+hObject]; hObject
0x180037ddb  lea     rdx, [rcx-1]
0x180037ddf  cmp     rdx, r14
0x180037de2  ja      short loc_180037DF0
0x180037de4  call    cs:__imp_CloseHandle
0x180037deb  nop     dword ptr [rax+rax+00h]
0x180037df0  mov     rcx, [rbp+57h+hKey]; hKey
0x180037df4  test    rcx, rcx
0x180037df7  jz      short loc_180037E06
0x180037df9  call    cs:__imp_RegCloseKey
0x180037e00  nop     dword ptr [rax+rax+00h]
0x180037e05  nop
0x180037e06  lea     rax, aPpftransformst; "PpfTransformStore::CommitTransforms"
0x180037e0d  mov     [rsp+100h+phkResult], rax
0x180037e12  lea     r9, aLeavingHs; "Leaving %hs"
0x180037e19  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180037e20  mov     edx, 89h; unsigned int
0x180037e25  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180037e2c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180037e31  nop
0x180037e32  jmp     loc_180037BD1
0x180037e37  lea     rcx, [rbp+57h+var_90]; this
0x180037e3b  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180037e40  xorps   xmm0, xmm0
0x180037e43  movdqu  [rbp+57h+var_88], xmm0
0x180037e48  mov     ecx, 30h ; '0'; Size
0x180037e4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037e52  mov     [rax], rax
0x180037e55  mov     [rax+8], rax
0x180037e59  mov     qword ptr [rbp+57h+var_88], rax
0x180037e5d  lea     rdx, [rbp+57h+var_88]
0x180037e61  mov     rcx, [rbp+57h+hKey]; hKey
0x180037e65  call    ?PpfhGetSubKeyNamesFromRegKey@@YAJPEAUHKEY__@@AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; PpfhGetSubKeyNamesFromRegKey(HKEY__ *,std::list<std::wstring> &)
0x180037e6a  mov     ebx, eax
0x180037e6c  test    eax, eax
  ... truncated ...
```
