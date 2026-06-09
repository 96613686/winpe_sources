# SLGetWindowsInformationDWORD

- ea: `0x18005c354`
- end: `0x18006674f`
- name: `SLGetWindowsInformationDWORD`
- size: `41979`
- prototype: `HRESULT __stdcall(PCWSTR pwszValueName, DWORD *pdwValue)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180043e64`

## callees

- `0x18002f39c`
- `0x18002f3c8`
- `0x18002fb50`
- `0x180030844`
- `0x18003ab38`
- `0x18005c244`
- `0x18005c270`
- `0x18005c2bc`
- `0x18005c2fc`
- `0x18005c328`
- `0x18005c354`
- `0x180066758`
- `0x180066774`
- `0x180066794`
- `0x18006bd50`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c97d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006120b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800614fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800615e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006191c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006206f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800625cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006298f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800634e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006559e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c97d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006120b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800614fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800615e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006191c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006206f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800625cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006298f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800634e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006559e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cb83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005cb83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ca65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ca65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005c80d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005eb1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800601ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800607ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180063dd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180065594`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005c80d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005eb1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800601ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800607ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180063dd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180065594`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18005d1a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18005d1a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005c8b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005eb68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060276`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060876`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063e8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800655ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005c8b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005eb68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060276`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060876`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063e8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800655ce`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005c77e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800600f1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800606f4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180061d2d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180062b1c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063d24`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063fbf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180066664`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005c77e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800600f1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800606f4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180061d2d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180062b1c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063d24`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063fbf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180066664`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cbff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cbff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d115`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d136`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d14f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d168`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005db38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e23a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e268`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e296`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e2b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e304`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e336`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e363`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e390`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e3b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e4ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e4f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e51e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e563`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e580`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e599`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e5c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e5e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e60b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e627`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e644`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e7d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ef39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ef65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005ef91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005efb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f042`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f06f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f09c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f0bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800602e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800608e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063ef9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800647be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064eec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064f1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064f48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064f69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064fbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064ff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006501d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006504a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006506b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800652aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065992`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800659bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800659ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065a0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065aa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065acd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065afa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065b1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066358`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066381`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800663a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800663c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800663e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066405`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066421`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006644e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066472`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066496`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800664b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800664ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800665a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800665c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800665dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800665f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d115`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d136`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d14f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d168`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005db38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e23a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e268`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e296`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e2b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e304`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e336`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e363`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e390`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e3b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e4ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e4f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e51e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e563`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e580`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e599`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e5c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e5e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e60b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e627`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e644`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e7d4`

## string_xrefs

- `0x18005eb01`: `ntdll.dll`
- `0x180065579`: `ntdll.dll`
- `0x18005d66a`: `WorkstationService-DomainJoinEnabled`

## pseudocode

```c
HRESULT __stdcall SLGetWindowsInformationDWORD(PCWSTR pwszValueName, DWORD *pdwValue)
{
  HRESULT v2; // ebx
  int v3; // eax
  _BYTE *v4; // rax
  _BYTE *v5; // rdi
  __int64 *v6; // rsi
  _BYTE *v7; // r14
  int v8; // r12d
  int v9; // r13d
  int v10; // r10d
  int v11; // r8d
  __int64 v12; // r15
  int v13; // ecx
  int v14; // ebx
  int v15; // r11d
  int v16; // ebx
  int v17; // edx
  int v18; // r11d
  unsigned int v19; // r8d
  int v20; // r9d
  unsigned int v21; // edx
  int v22; // r10d
  int v23; // r8d
  unsigned int v24; // r9d
  int v25; // r10d
  int v26; // edx
  int v27; // r8d
  unsigned int v28; // r9d
  int v29; // edx
  int v30; // r8d
  unsigned int v31; // r10d
  unsigned int v32; // r8d
  int v33; // r9d
  int v34; // edx
  unsigned int v35; // r8d
  int v36; // r9d
  int v37; // edx
  int v38; // r8d
  unsigned int v39; // r9d
  int v40; // r10d
  int v41; // ecx
  unsigned __int64 v42; // rcx
  char v43; // al
  __int64 i; // rbx
  HMODULE v45; // rcx
  int v46; // r13d
  int v47; // ebx
  unsigned int v48; // r12d
  __int64 v49; // rbx
  HMODULE *v50; // r14
  _BYTE *v51; // rdi
  __int64 v52; // rax
  char *v53; // rdx
  unsigned int v54; // eax
  unsigned int v55; // r15d
  __int64 v56; // rsi
  void **v57; // rax
  HANDLE v58; // rax
  const wchar_t *v59; // rsi
  const wchar_t *v60; // r14
  int v61; // r13d
  int v62; // r12d
  __int64 v63; // r15
  signed int LastError; // ebx
  bool v65; // sf
  __int64 v66; // r9
  void *j; // rdi
  void *v68; // r8
  unsigned int (__fastcall *v69)(WARBIRD_DELAY_LOAD *__hidden, int); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v71; // r15
  __int64 v72; // r9
  void *k; // rdi
  void *v74; // r8
  HANDLE CurrentProcess; // rax
  bool v76; // sf
  int v77; // edi
  HLOCAL v78; // rax
  _DWORD *v79; // rdi
  HANDLE ProcessHeap; // rax
  _OWORD *v81; // rax
  void *v82; // r12
  int v83; // r15d
  _QWORD *v84; // r13
  HANDLE v85; // rax
  int v86; // eax
  int v87; // ecx
  unsigned int v88; // r11d
  int v89; // eax
  unsigned int v90; // r11d
  int v91; // r9d
  int v92; // eax
  unsigned int v93; // r11d
  int v94; // r9d
  int v95; // eax
  size_t v96; // rdx
  const wchar_t *v97; // rcx
  int v98; // r9d
  int v99; // r10d
  unsigned int v100; // r11d
  int v101; // eax
  unsigned int v102; // r11d
  int v103; // eax
  unsigned int v104; // r11d
  int v105; // r9d
  int v106; // eax
  int v107; // r9d
  unsigned int v108; // ebx
  HANDLE v109; // rax
  _DWORD *v110; // rbx
  unsigned int v111; // r9d
  int v112; // r10d
  unsigned int v113; // r11d
  _DWORD *v114; // rax
  __int64 v115; // rbx
  unsigned int v116; // r10d
  void *v117; // rbx
  HANDLE v118; // rax
  HANDLE v119; // rax
  HANDLE v120; // rax
  HANDLE v121; // rax
  size_t v122; // r12
  DWORD ModuleFileNameW; // eax
  unsigned int *v124; // r9
  unsigned int i12; // ebx
  __int64 v126; // rdx
  __int64 v127; // r9
  unsigned int *v128; // r9
  unsigned int v129; // r11d
  unsigned int v130; // r10d
  unsigned int *v131; // r9
  unsigned int i13; // r11d
  __int64 v133; // rdx
  __int64 v134; // r9
  int v135; // r11d
  _DWORD *v136; // r9
  unsigned int *v137; // r9
  unsigned int v138; // r10d
  size_t v139; // rdx
  const wchar_t *v140; // rcx
  unsigned int i14; // r11d
  __int64 v142; // rdx
  __int64 v143; // r9
  int v144; // r11d
  _DWORD *v145; // r9
  const wchar_t **v146; // rax
  unsigned int v147; // r10d
  unsigned int *v148; // r9
  unsigned int i15; // ebx
  __int64 v150; // rdx
  __int64 v151; // r9
  _DWORD *v152; // r9
  __int64 v153; // r11
  void *v154; // rcx
  unsigned int *v155; // r9
  unsigned int v156; // r10d
  unsigned int i16; // r11d
  __int64 v158; // rdx
  __int64 v159; // r9
  int v160; // r11d
  _DWORD *v161; // r9
  _DWORD *v162; // rax
  int v163; // ecx
  unsigned int *v164; // r9
  unsigned int v165; // r10d
  unsigned int i20; // r11d
  __int64 v167; // rdx
  __int64 v168; // r9
  int v169; // r11d
  _DWORD *v170; // r9
  _DWORD *v171; // rax
  __int64 v172; // rcx
  unsigned int v173; // r9d
  int v174; // edi
  unsigned int v175; // r9d
  int v176; // r15d
  unsigned int v177; // eax
  unsigned int v178; // ebx
  HANDLE v179; // rax
  _DWORD *v180; // rbx
  unsigned int v181; // r10d
  size_t v182; // rcx
  HANDLE v183; // rax
  unsigned int *v184; // rbx
  _DWORD *v185; // rdi
  unsigned __int8 *v186; // r15
  void *v187; // rax
  unsigned int v188; // r9d
  size_t v189; // rdx
  SIZE_T v190; // r8
  unsigned __int8 v191; // al
  SIZE_T v192; // rcx
  unsigned __int8 *v193; // r11
  int v194; // edx
  int v195; // r10d
  int v196; // r14d
  int v197; // r8d
  unsigned int v198; // r10d
  unsigned int v199; // ecx
  unsigned int v200; // r11d
  _BYTE *v201; // r14
  char v202; // si
  int v203; // r10d
  SIZE_T v204; // r14
  int v205; // r13d
  _BYTE *v206; // r15
  int v207; // edi
  int v208; // eax
  int v209; // ebx
  int v210; // r11d
  int v211; // edx
  int v212; // r10d
  int v213; // r8d
  int v214; // r10d
  int v215; // r9d
  int v216; // r8d
  unsigned int v217; // edx
  int v218; // r9d
  int v219; // ecx
  int v220; // edx
  int v221; // r8d
  int v222; // r9d
  int v223; // edx
  unsigned int v224; // r8d
  unsigned int v225; // r9d
  int v226; // edx
  int v227; // r8d
  int v228; // r9d
  int v229; // edx
  int v230; // r8d
  int v231; // r10d
  int v232; // edx
  int v233; // r9d
  unsigned int v234; // r8d
  unsigned int v235; // r10d
  int v236; // edx
  HANDLE v237; // rax
  _DWORD *v238; // rax
  int v239; // r15d
  HANDLE v240; // rax
  void *v241; // rcx
  _DWORD *v242; // r15
  HANDLE v243; // rax
  _OWORD *v244; // rax
  HANDLE v245; // rax
  _QWORD *v246; // rax
  _QWORD *v247; // rax
  HANDLE v248; // rax
  HANDLE v249; // rax
  HANDLE v250; // rax
  HANDLE v251; // rax
  HANDLE v252; // rax
  _QWORD *v253; // rax
  HANDLE v254; // rax
  HANDLE v255; // rax
  HANDLE v256; // rax
  HANDLE v257; // rax
  __int64 v258; // rdx
  unsigned int v259; // r9d
  int v260; // r15d
  __int64 v261; // rdx
  unsigned int v262; // r9d
  __int64 v263; // rdx
  unsigned int v264; // ebx
  HANDLE v265; // rax
  _DWORD *v266; // rax
  _DWORD *v267; // rcx
  LPVOID v268; // rax
  HANDLE v269; // rax
  HANDLE v270; // rax
  HANDLE v271; // rax
  HANDLE v272; // rax
  HANDLE v273; // rax
  void *v274; // rbx
  HANDLE v275; // rax
  HANDLE v276; // rax
  _QWORD *v277; // rbx
  void *v278; // rdi
  HANDLE v279; // rax
  void *v280; // rdi
  HANDLE v281; // rax
  void *v282; // rdi
  HANDLE v283; // rax
  HANDLE v284; // rax
  void *v285; // rbx
  HANDLE v286; // rax
  int v287; // eax
  void *v288; // rcx
  void *v289; // r9
  int v290; // r10d
  void *v291; // rcx
  unsigned int *v292; // r9
  void *v293; // rcx
  unsigned int *v294; // r9
  HANDLE v295; // rax
  int v296; // eax
  __int64 v297; // rcx
  void *v298; // r9
  unsigned int v299; // r11d
  _DWORD *v300; // rcx
  unsigned int v301; // r10d
  unsigned int v302; // r9d
  int v303; // r11d
  LPVOID v304; // rcx
  unsigned int v305; // ebx
  HANDLE v306; // rax
  _DWORD *v307; // rax
  unsigned int i18; // r9d
  unsigned int v309; // r11d
  int v310; // r9d
  int v311; // r11d
  unsigned int v312; // ecx
  unsigned int v313; // r9d
  signed int v314; // eax
  FARPROC v315; // rax
  int v316; // eax
  unsigned int v317; // r9d
  SIZE_T v318; // rbx
  int v319; // r11d
  int v320; // r15d
  int v321; // r9d
  int v322; // r9d
  int v323; // r9d
  SIZE_T v324; // r11
  unsigned int v325; // r11d
  int v326; // r9d
  int v327; // r9d
  unsigned int v328; // r10d
  int v329; // r9d
  int v330; // r10d
  int v331; // r11d
  HANDLE v332; // rax
  void *v333; // rax
  bool v334; // zf
  _QWORD *v335; // rcx
  HANDLE v336; // rax
  void *v337; // rcx
  HANDLE v338; // rax
  void *v339; // rcx
  void *v340; // rax
  SIZE_T v341; // rax
  unsigned int v342; // r15d
  HANDLE v343; // rax
  void *v344; // rcx
  _QWORD *v345; // rax
  HANDLE v346; // rax
  HANDLE v347; // rax
  HANDLE v348; // rax
  HANDLE v349; // rax
  SIZE_T *v350; // rdx
  unsigned int *v351; // rcx
  HANDLE v352; // rax
  HANDLE v353; // rax
  HANDLE v354; // rax
  HANDLE v355; // rax
  unsigned __int64 v356; // r15
  _BYTE *v357; // r11
  unsigned __int8 v358; // al
  unsigned int v359; // r8d
  int v360; // r10d
  unsigned int v361; // r9d
  int v362; // r14d
  unsigned __int8 *v363; // rsi
  int v364; // eax
  int v365; // r8d
  int v366; // r8d
  unsigned int v367; // r10d
  unsigned int v368; // ebx
  unsigned int v369; // ecx
  int v370; // edx
  _BYTE *v371; // r14
  char v372; // si
  SIZE_T v373; // rcx
  int v374; // r11d
  unsigned __int8 *v375; // rsi
  _BYTE *v376; // r15
  int v377; // r13d
  int v378; // r12d
  SIZE_T v379; // rax
  int v380; // ecx
  int v381; // edi
  int v382; // ebx
  int v383; // edi
  int v384; // edx
  int v385; // ebx
  unsigned int v386; // r8d
  int v387; // r9d
  unsigned int v388; // edx
  int v389; // r8d
  int v390; // r9d
  unsigned int v391; // edx
  int v392; // r8d
  int v393; // r10d
  int v394; // r11d
  unsigned int v395; // r9d
  int v396; // r8d
  unsigned int v397; // r9d
  int v398; // r10d
  int v399; // r11d
  int v400; // edx
  int v401; // r8d
  unsigned int v402; // r9d
  int v403; // edx
  int v404; // r10d
  int v405; // r8d
  unsigned int v406; // edx
  int v407; // r8d
  unsigned __int64 i19; // rcx
  int v409; // r15d
  void *v410; // r9
  void *v411; // r10
  _DWORD *v412; // r11
  int v413; // ecx
  __int64 v414; // rdx
  const void *v415; // rcx
  SIZE_T v416; // rcx
  void *v417; // r11
  void *v418; // r10
  void *v419; // r9
  SIZE_T v420; // r10
  __int64 v421; // r11
  SIZE_T v422; // r9
  unsigned int *v423; // r9
  SIZE_T v424; // r10
  unsigned int v425; // r11d
  __int64 v426; // rdx
  __int64 v427; // r9
  unsigned int v428; // edx
  void *v429; // r9
  HANDLE v430; // rax
  void *v431; // rcx
  int v432; // r9d
  unsigned int v433; // r10d
  __int64 v434; // r11
  int *v435; // r15
  unsigned int i17; // r9d
  unsigned int v437; // r10d
  int v438; // r9d
  int v439; // r9d
  __int64 v440; // r11
  size_t *v441; // rdx
  size_t v442; // rax
  LPVOID v443; // rcx
  unsigned int v444; // r9d
  unsigned int v445; // r10d
  int v446; // r9d
  int v447; // r9d
  __int64 v448; // r11
  int *v449; // rdx
  int v450; // eax
  LPVOID v451; // rcx
  int v452; // eax
  unsigned int v453; // r10d
  unsigned int v454; // r9d
  unsigned int *v455; // rcx
  unsigned int v456; // r9d
  unsigned int v457; // ebx
  int v458; // r9d
  int v459; // r9d
  _DWORD *v460; // rdx
  unsigned int v461; // r9d
  unsigned int *v462; // rcx
  unsigned int v463; // ebx
  int v464; // r9d
  int v465; // eax
  int v466; // r9d
  size_t v467; // r10
  const void *v468; // r11
  int *v469; // rcx
  int v470; // ecx
  __int64 v471; // rax
  unsigned int v472; // edi
  int v473; // eax
  const wchar_t *v474; // rax
  __int64 *v475; // r12
  wchar_t *v476; // r14
  int v477; // edi
  int v478; // eax
  int v479; // r10d
  int v480; // r8d
  __int64 v481; // rsi
  int v482; // ecx
  int v483; // ebx
  int v484; // r11d
  int v485; // ebx
  int v486; // edx
  int v487; // r11d
  unsigned int v488; // r8d
  int v489; // r9d
  unsigned int v490; // edx
  int v491; // r10d
  int v492; // r8d
  unsigned int v493; // r9d
  int v494; // r10d
  int v495; // edx
  int v496; // r8d
  unsigned int v497; // r9d
  int v498; // edx
  int v499; // r8d
  unsigned int v500; // r10d
  unsigned int v501; // r8d
  int v502; // r9d
  int v503; // edx
  unsigned int v504; // r8d
  int v505; // r9d
  int v506; // edx
  int v507; // r8d
  unsigned int v508; // r9d
  int v509; // r10d
  int v510; // ecx
  const wchar_t *v511; // r13
  unsigned __int64 v512; // rcx
  char v513; // al
  __int64 kk; // rbx
  HMODULE v515; // rcx
  int v516; // ebx
  __int64 v517; // rbx
  __int64 v518; // rax
  HMODULE *v519; // r12
  const wchar_t *v520; // r13
  LPVOID v521; // rcx
  __int64 v522; // rax
  char *v523; // rdx
  unsigned int v524; // edx
  unsigned int v525; // eax
  __int64 v526; // r12
  void **v527; // rax
  wchar_t *v528; // r12
  HANDLE v529; // rax
  int v530; // eax
  const wchar_t *v531; // rax
  wchar_t *v532; // rsi
  __int64 *v533; // r12
  int v534; // edi
  int v535; // eax
  int v536; // r9d
  int v537; // r8d
  __int64 v538; // r14
  int v539; // ecx
  int v540; // ebx
  int v541; // r11d
  int v542; // ebx
  int v543; // edx
  int v544; // r11d
  unsigned int v545; // r8d
  int v546; // r9d
  unsigned int v547; // r10d
  int v548; // edx
  int v549; // r8d
  unsigned int v550; // r9d
  int v551; // r10d
  int v552; // edx
  int v553; // r8d
  unsigned int v554; // r9d
  int v555; // edx
  int v556; // r8d
  unsigned int v557; // r10d
  unsigned int v558; // r8d
  int v559; // r9d
  int v560; // edx
  unsigned int v561; // r8d
  int v562; // r9d
  int v563; // edx
  int v564; // r8d
  unsigned int v565; // r9d
  int v566; // edx
  int v567; // r8d
  char v568; // al
  unsigned __int64 v569; // rcx
  const wchar_t *v570; // r13
  __int64 mm; // rbx
  HMODULE v572; // rcx
  int v573; // ebx
  __int64 v574; // rbx
  __int64 v575; // rax
  HMODULE *v576; // r12
  const wchar_t *v577; // r13
  LPVOID v578; // rcx
  __int64 v579; // rax
  char *v580; // rdx
  unsigned int v581; // edx
  unsigned int v582; // eax
  __int64 v583; // r12
  void **v584; // rax
  wchar_t *v585; // r12
  HANDLE v586; // rax
  signed int v587; // eax
  signed int v588; // ebx
  unsigned int v589; // r13d
  bool v590; // sf
  void *v591; // rax
  WARBIRD_DELAY_LOAD *v592; // r12
  void *v593; // rax
  _DWORD *v594; // r13
  bool v595; // sf
  unsigned int i5; // r14d
  __int64 v597; // rax
  unsigned int v598; // eax
  unsigned int v599; // r8d
  unsigned int i6; // edx
  __int64 v601; // rbx
  __int64 v602; // rcx
  const wchar_t *v603; // rcx
  __int64 i7; // rdx
  __int64 v605; // rax
  char *v606; // rax
  char *v607; // r12
  __int64 *v608; // rbx
  char *v609; // r13
  int v610; // r14d
  int v611; // edi
  int v612; // r9d
  int v613; // edx
  __int64 v614; // rsi
  int v615; // eax
  int v616; // r11d
  int v617; // r10d
  int v618; // r11d
  int v619; // ecx
  int v620; // r10d
  unsigned int v621; // edx
  int v622; // r8d
  unsigned int v623; // r9d
  int v624; // ecx
  int v625; // edx
  unsigned int v626; // r8d
  int v627; // r9d
  int v628; // ecx
  int v629; // edx
  unsigned int v630; // r8d
  int v631; // ecx
  int v632; // edx
  unsigned int v633; // r9d
  unsigned int v634; // edx
  int v635; // r8d
  int v636; // ecx
  unsigned int v637; // edx
  int v638; // r8d
  int v639; // ecx
  int v640; // edx
  unsigned int v641; // r8d
  int v642; // r9d
  int v643; // eax
  unsigned __int64 v644; // rax
  __m128 v645; // xmm1
  __int64 v646; // r13
  __m128 v647; // xmm0
  __m128 v648; // xmm0
  __m128 v649; // xmm1
  __m128 v650; // xmm1
  __m128 v651; // xmm1
  int v652; // r8d
  unsigned int v653; // edx
  unsigned int i8; // ecx
  __int64 v655; // rax
  void *v656; // rax
  void **v657; // r12
  unsigned int v658; // eax
  unsigned int v659; // ecx
  __int64 v660; // r13
  __int64 v661; // r9
  signed int v662; // eax
  void *v663; // rax
  __int64 v664; // r9
  signed int v665; // eax
  __int64 i9; // r13
  _BYTE *v667; // rax
  __int64 v668; // rcx
  __int64 i10; // rcx
  _BYTE *v670; // rax
  signed int v671; // eax
  int v672; // r13d
  unsigned int v673; // ebx
  const wchar_t *v674; // rax
  int v675; // eax
  __int64 v676; // rax
  bool v677; // sf
  const unsigned __int16 *v678; // rbx
  int v679; // eax
  __int64 v680; // rax
  bool v681; // sf
  unsigned int v682; // eax
  int v683; // eax
  unsigned int v684; // r12d
  void *v685; // rbx
  void *v686; // rbx
  unsigned __int64 v687; // rdx
  signed int v688; // eax
  int v689; // eax
  __int64 v690; // rax
  bool v691; // sf
  void *v692; // rbx
  __int64 v693; // r12
  unsigned int v694; // ebx
  int v695; // eax
  unsigned __int64 v696; // rdx
  int v697; // edx
  int v698; // r12d
  int v699; // ebx
  int v700; // r13d
  int v701; // r13d
  __int64 v702; // rax
  int v703; // edx
  int v704; // ecx
  int v705; // r13d
  __int64 v706; // rax
  int v707; // r13d
  int v708; // eax
  HMODULE v709; // rcx
  unsigned int v710; // ebx
  __int64 v711; // rax
  int v712; // edi
  int v713; // r12d
  LPVOID v714; // rbx
  int v715; // eax
  signed int v716; // r13d
  __int64 v717; // rax
  size_t v718; // rax
  WARBIRD_DELAY_LOAD *v719; // rbx
  __int64 v720; // rax
  signed int v721; // eax
  signed int v722; // edi
  void *v723; // rax
  unsigned int (__fastcall *v724)(WARBIRD_DELAY_LOAD *__hidden, int); // rbx
  __int64 v725; // rax
  int v726; // eax
  int v727; // r10d
  int v728; // r9d
  int v729; // r8d
  int v730; // ecx
  int v731; // edx
  int v732; // edi
  unsigned __int8 v733; // r14
  signed int v734; // esi
  const wchar_t *v735; // rdx
  char *v736; // rax
  char v737; // r15
  signed int v738; // r9d
  char v739; // bl
  STRSAFE_PCNZWCH v740; // r8
  _BYTE *v741; // r10
  unsigned __int8 v742; // dl
  int v743; // r8d
  int v744; // r9d
  int v745; // edx
  int v746; // r8d
  int v747; // ecx
  LPVOID v748; // rbx
  __int64 v749; // rax
  size_t v750; // rax
  WARBIRD_DELAY_LOAD *v751; // r13
  LPVOID v752; // rbx
  signed int v753; // eax
  void *v754; // rax
  unsigned int (__fastcall *v755)(WARBIRD_DELAY_LOAD *__hidden, int); // rbx
  __int64 v756; // rax
  int v757; // r10d
  int v758; // r9d
  int v759; // r8d
  int v760; // ecx
  int v761; // r12d
  int v762; // ebx
  const wchar_t *v763; // rsi
  size_t v764; // rax
  char v765; // r13
  STRSAFE_PCNZWCH v766; // r8
  char v767; // r14
  _BYTE *v768; // r10
  unsigned __int8 v769; // bl
  int v770; // r9d
  unsigned __int8 v771; // dl
  int v772; // r8d
  int v773; // r9d
  int v774; // edx
  int v775; // r8d
  int v776; // ecx
  LPVOID v777; // rbx
  LPVOID v778; // r12
  _BYTE *v779; // rax
  __int64 v780; // rcx
  __int64 nn; // rcx
  _BYTE *v782; // rax
  __int64 v783; // rcx
  __int64 i1; // rcx
  _BYTE *v785; // rcx
  __int64 v786; // rax
  __int64 v787; // rax
  int v788; // eax
  __int64 i2; // rbx
  HMODULE v790; // rcx
  int v791; // r13d
  int v792; // ebx
  size_t v793; // r12
  char v794; // al
  int v795; // edi
  int v796; // r8d
  unsigned int v797; // r11d
  int v798; // ebx
  int v799; // eax
  int v800; // r10d
  int v801; // r13d
  int v802; // edx
  unsigned int v803; // eax
  void *v804; // rax
  LPVOID v805; // rax
  __int64 v806; // rax
  size_t v807; // rcx
  int v808; // eax
  int v809; // ebx
  signed int v810; // edi
  SIZE_T v811; // rax
  bool v812; // sf
  size_t v813; // rbx
  __int64 v814; // rax
  unsigned int (__fastcall *v815)(WARBIRD_DELAY_LOAD *__hidden, int); // rbx
  __int64 v816; // rax
  WARBIRD_DELAY_LOAD *v817; // rbx
  int v818; // eax
  int v819; // edx
  int v820; // r9d
  int v821; // r11d
  int v822; // r10d
  int v823; // ecx
  int v824; // r8d
  __int64 v825; // r8
  unsigned __int8 v826; // r14
  int v827; // esi
  const wchar_t *v828; // rbx
  size_t v829; // rax
  char v830; // r15
  int v831; // r9d
  char v832; // r13
  STRSAFE_PCNZWCH v833; // r8
  _BYTE *v834; // r10
  unsigned __int8 v835; // dl
  int v836; // r8d
  int v837; // r9d
  int v838; // edx
  int v839; // r8d
  int v840; // ecx
  signed int v841; // edi
  LPVOID v842; // rbx
  __int64 v843; // rax
  SIZE_T v844; // rax
  bool v845; // sf
  size_t v846; // rbx
  void *v847; // rax
  unsigned int (__fastcall *v848)(WARBIRD_DELAY_LOAD *__hidden, int); // rbx
  __int64 v849; // rax
  WARBIRD_DELAY_LOAD *v850; // rbx
  int v851; // r10d
  int v852; // r8d
  int v853; // r9d
  int v854; // ecx
  int v855; // edx
  signed int v856; // esi
  const wchar_t *v857; // rdx
  size_t v858; // rax
  char v859; // r13
  STRSAFE_PCNZWCH v860; // r8
  char v861; // bl
  _BYTE *v862; // r10
  unsigned __int8 v863; // r14
  signed int v864; // r9d
  unsigned __int8 v865; // dl
  int v866; // r8d
  int v867; // r9d
  int v868; // edx
  int v869; // r8d
  int v870; // ecx
  int v871; // eax
  _BYTE *v872; // rax
  int v873; // r8d
  _BYTE *v874; // r12
  __int64 *v875; // r14
  __int64 v876; // rax
  int v877; // r13d
  int v878; // esi
  int v879; // r10d
  int v880; // ecx
  int v881; // ebx
  int v882; // r11d
  int v883; // ebx
  int v884; // edx
  int v885; // r11d
  unsigned int v886; // r8d
  int v887; // r9d
  unsigned int v888; // edx
  int v889; // r10d
  int v890; // r8d
  unsigned int v891; // r9d
  int v892; // r10d
  int v893; // edx
  int v894; // r8d
  unsigned int v895; // r9d
  int v896; // edx
  int v897; // r8d
  unsigned int v898; // r10d
  unsigned int v899; // r8d
  int v900; // r9d
  int v901; // edx
  unsigned int v902; // r8d
  int v903; // r9d
  int v904; // edx
  int v905; // r8d
  unsigned int v906; // r9d
  int v907; // r10d
  int v908; // ecx
  const WCHAR *v909; // rdi
  unsigned __int64 v910; // rcx
  char v911; // al
  __int64 i3; // rbx
  HMODULE v913; // rcx
  int v914; // ebx
  unsigned int v915; // r12d
  __int64 v916; // rbx
  __int64 v917; // r12
  HMODULE *v918; // r13
  const WCHAR *v919; // rdi
  __int64 v920; // rax
  char *v921; // rdx
  unsigned int v922; // edx
  unsigned int v923; // eax
  int v924; // ecx
  __int64 v925; // r12
  void **v926; // rax
  void *v927; // rdi
  HANDLE v928; // rax
  int v929; // eax
  __int64 i4; // rbx
  HMODULE v931; // rcx
  void *v932; // r13
  _DWORD *v933; // rdi
  HANDLE v934; // rax
  _OWORD *v935; // rax
  void *v936; // r12
  HANDLE v937; // rax
  _QWORD *v938; // rax
  void *v939; // rdi
  unsigned int v940; // r10d
  unsigned int v941; // r11d
  int v942; // eax
  unsigned int v943; // r10d
  unsigned int v944; // r11d
  int v945; // r9d
  int v946; // eax
  unsigned int v947; // r10d
  unsigned int v948; // r11d
  int v949; // r9d
  int v950; // eax
  int v951; // r9d
  unsigned int v952; // ebx
  HANDLE v953; // rax
  const wchar_t *v954; // rax
  wchar_t *v955; // rbx
  unsigned int v956; // r10d
  unsigned int v957; // r11d
  unsigned int *v958; // rax
  unsigned int v959; // ebx
  unsigned int v960; // r10d
  STRSAFE_PCNZWCH v961; // r9
  unsigned int v962; // r11d
  unsigned int m; // ebx
  __int64 v964; // rdx
  __int64 v965; // r9
  unsigned int *v966; // r9
  unsigned int v967; // r11d
  size_t v968; // r8
  unsigned int v969; // r10d
  STRSAFE_PCNZWCH v970; // r9
  unsigned int v971; // r11d
  __int64 v972; // rdx
  __int64 v973; // r9
  int v974; // r11d
  _DWORD *v975; // r9
  STRSAFE_PCNZWCH v976; // r10
  unsigned int v977; // r9d
  unsigned int v978; // r10d
  unsigned int v979; // r11d
  __int64 v980; // rdx
  __int64 v981; // r10
  int v982; // r11d
  int v983; // eax
  _DWORD *v984; // r10
  _QWORD *v985; // rax
  LPVOID v986; // rcx
  __int64 v987; // rcx
  unsigned int v988; // r11d
  unsigned int v989; // r9d
  void *v990; // r11
  int v991; // edi
  int v992; // ecx
  void *v993; // r9
  unsigned int v994; // r10d
  unsigned int *v995; // r11
  unsigned int v996; // eax
  unsigned int v997; // ebx
  HANDLE v998; // rax
  char *v999; // rax
  char *v1000; // rbx
  unsigned int v1001; // r9d
  size_t v1002; // rcx
  HANDLE v1003; // rax
  int v1004; // ecx
  unsigned int *v1005; // rbx
  unsigned int *v1006; // rdi
  unsigned __int8 v1007; // al
  SIZE_T v1008; // r8
  SIZE_T v1009; // r11
  const wchar_t *v1010; // r9
  unsigned int v1011; // r10d
  unsigned int v1012; // r14d
  int v1013; // esi
  int v1014; // ebx
  int v1015; // r8d
  _BYTE *v1016; // rcx
  unsigned int v1017; // r8d
  unsigned int v1018; // r9d
  int v1019; // edx
  unsigned int v1020; // esi
  int v1021; // r14d
  char v1022; // di
  unsigned int v1023; // r9d
  STRSAFE_PCNZWCH v1024; // r14
  SIZE_T v1025; // r12
  _BYTE *v1026; // rdi
  int v1027; // r13d
  int v1028; // r10d
  int v1029; // r15d
  int v1030; // eax
  int v1031; // ecx
  int v1032; // ebx
  int v1033; // r11d
  int v1034; // ebx
  int v1035; // r11d
  int v1036; // edx
  int v1037; // r9d
  int v1038; // r10d
  int v1039; // r8d
  int v1040; // r9d
  unsigned int v1041; // edx
  int v1042; // r8d
  int v1043; // ecx
  int v1044; // edx
  int v1045; // r8d
  int v1046; // r9d
  int v1047; // edx
  unsigned int v1048; // r8d
  unsigned int v1049; // r9d
  int v1050; // edx
  int v1051; // r8d
  int v1052; // r9d
  int v1053; // edx
  int v1054; // r8d
  int v1055; // r9d
  int v1056; // edx
  int v1057; // r8d
  unsigned int v1058; // r9d
  int v1059; // edx
  HANDLE v1060; // rax
  _DWORD *v1061; // rax
  void *v1062; // rsi
  unsigned int v1063; // esi
  HANDLE v1064; // rax
  void *v1065; // rax
  HANDLE v1066; // rax
  _OWORD *v1067; // rcx
  _DWORD *v1068; // rax
  HANDLE v1069; // rax
  _QWORD *v1070; // rax
  LPVOID v1071; // rax
  HANDLE v1072; // rax
  HANDLE v1073; // rax
  HANDLE v1074; // rax
  HANDLE v1075; // rax
  void *v1076; // rcx
  HANDLE v1077; // rax
  LPVOID v1078; // rax
  HANDLE v1079; // rax
  HANDLE v1080; // rax
  HANDLE v1081; // rax
  HANDLE v1082; // rax
  int v1083; // eax
  __int64 v1084; // rdx
  unsigned int v1085; // r9d
  __int64 v1086; // rdx
  unsigned int v1087; // r9d
  __int64 v1088; // rdx
  unsigned int v1089; // ebx
  HANDLE v1090; // rax
  _DWORD *v1091; // rax
  void *v1092; // rcx
  int v1093; // r9d
  LPVOID v1094; // rcx
  unsigned int *v1095; // r9
  LPVOID v1096; // rcx
  unsigned int *v1097; // r9
  int v1098; // eax
  HANDLE v1099; // rax
  int v1100; // eax
  int v1101; // r9d
  __int64 v1102; // rcx
  _DWORD *v1103; // rcx
  int n; // r10d
  unsigned int v1105; // r11d
  int v1106; // r10d
  size_t v1107; // rcx
  unsigned int ii; // r10d
  unsigned int v1109; // r11d
  int v1110; // r10d
  unsigned int v1111; // ecx
  unsigned int v1112; // r10d
  unsigned int v1113; // ebx
  HANDLE v1114; // rax
  unsigned int *v1115; // rax
  int v1116; // eax
  bool v1117; // sf
  FARPROC ProcAddress; // rax
  unsigned int v1119; // r9d
  void *v1120; // r14
  const wchar_t *v1121; // rbx
  int v1122; // ecx
  int v1123; // r9d
  int v1124; // r9d
  int v1125; // r9d
  SIZE_T v1126; // r11
  unsigned int v1127; // r11d
  int v1128; // r9d
  int v1129; // r9d
  unsigned int v1130; // r10d
  int v1131; // r9d
  int v1132; // r10d
  int v1133; // r11d
  HANDLE v1134; // rax
  _QWORD *v1135; // rax
  SIZE_T v1136; // rcx
  HANDLE v1137; // rax
  void *v1138; // rcx
  SIZE_T v1139; // rax
  HANDLE v1140; // rax
  void *v1141; // rcx
  const wchar_t *v1142; // rax
  HANDLE v1143; // rax
  void *v1144; // rcx
  void *v1145; // rcx
  HANDLE v1146; // rax
  HANDLE v1147; // rax
  HANDLE v1148; // rax
  HANDLE v1149; // rax
  LPVOID *v1150; // rdx
  unsigned int *v1151; // rax
  HANDLE v1152; // rax
  HANDLE v1153; // rax
  HANDLE v1154; // rax
  HANDLE v1155; // rax
  void *v1156; // rax
  _BYTE *v1157; // r9
  size_t v1158; // r10
  unsigned __int8 v1159; // al
  unsigned __int8 *v1160; // r11
  int v1161; // r14d
  int v1162; // eax
  unsigned int v1163; // r10d
  int v1164; // ecx
  _BYTE *v1165; // rcx
  int v1166; // r8d
  unsigned int v1167; // edx
  unsigned int v1168; // r8d
  unsigned int v1169; // r11d
  unsigned int v1170; // ebx
  unsigned int v1171; // r10d
  int v1172; // r14d
  char v1173; // r9
  int v1174; // r11d
  int v1175; // r15d
  unsigned __int64 v1176; // r12
  _BYTE *v1177; // rsi
  int v1178; // r13d
  unsigned int v1179; // r10d
  unsigned __int8 *v1180; // rax
  int v1181; // ecx
  int v1182; // edi
  int v1183; // ebx
  int v1184; // edi
  int v1185; // edx
  int v1186; // ebx
  unsigned int v1187; // r8d
  int v1188; // r9d
  unsigned int v1189; // edx
  int v1190; // r8d
  int v1191; // r9d
  unsigned int v1192; // edx
  int v1193; // r8d
  int v1194; // r10d
  int v1195; // r11d
  unsigned int v1196; // r9d
  int v1197; // edx
  int v1198; // r8d
  unsigned int v1199; // r9d
  int v1200; // edx
  int v1201; // r8d
  int v1202; // r9d
  int v1203; // edx
  unsigned int v1204; // r8d
  int v1205; // r9d
  int v1206; // edx
  int v1207; // r8d
  unsigned int v1208; // r9d
  unsigned int v1209; // r11d
  int v1210; // edx
  int v1211; // r8d
  size_t jj; // rcx
  void *v1213; // r14
  int v1214; // ecx
  _DWORD *v1215; // r9
  int v1216; // r10d
  int v1217; // r10d
  unsigned int v1218; // r11d
  unsigned int v1219; // r10d
  size_t v1220; // r11
  size_t v1221; // r8
  const void *v1222; // r11
  SIZE_T v1223; // r10
  void *v1224; // r9
  STRSAFE_PCNZWCH v1225; // r9
  SIZE_T v1226; // r9
  unsigned int *v1227; // r10
  __int64 v1228; // rdx
  __int64 v1229; // r10
  void *v1230; // r14
  HANDLE v1231; // rax
  size_t v1232; // rsi
  LPVOID v1233; // rax
  int v1234; // eax
  void *v1235; // rsi
  HANDLE v1236; // rax
  void *v1237; // rsi
  HANDLE v1238; // rax
  void *v1239; // rsi
  HANDLE v1240; // rax
  void *v1241; // rsi
  HANDLE v1242; // rax
  HANDLE v1243; // rax
  void *v1244; // rbx
  HANDLE v1245; // rax
  HANDLE v1246; // rax
  _QWORD *v1247; // rbx
  void *v1248; // rdi
  HANDLE v1249; // rax
  void *v1250; // rdi
  HANDLE v1251; // rax
  void *v1252; // rdi
  HANDLE v1253; // rax
  HANDLE v1254; // rax
  HANDLE v1255; // rax
  unsigned int v1256; // r9d
  unsigned int v1257; // r10d
  const wchar_t *v1258; // r11
  STRSAFE_PCNZWCH v1259; // rcx
  size_t v1260; // rcx
  int v1261; // r9d
  __int64 v1262; // rbx
  unsigned int v1263; // r10d
  int v1264; // r9d
  void *v1265; // rbx
  HANDLE v1266; // rax
  HANDLE v1267; // rax
  HANDLE v1268; // rax
  HANDLE v1269; // rax
  unsigned int v1270; // edi
  int v1271; // eax
  __int64 i11; // rbx
  HMODULE v1273; // rcx
  SIZE_T dwBytes; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v1276; // [rsp+68h] [rbp-98h] BYREF
  int v1277; // [rsp+6Ch] [rbp-94h] BYREF
  char v1278; // [rsp+70h] [rbp-90h]
  SIZE_T v1279; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v1280; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v1281; // [rsp+88h] [rbp-78h]
  LPVOID v1282; // [rsp+90h] [rbp-70h]
  void *v1283; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v1284; // [rsp+A0h] [rbp-60h] BYREF
  SIZE_T v1285; // [rsp+A8h] [rbp-58h] BYREF
  size_t pcchLength; // [rsp+B0h] [rbp-50h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+B8h] [rbp-48h] BYREF
  void *v1288; // [rsp+C0h] [rbp-40h] BYREF
  size_t v1289; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID v1290; // [rsp+D0h] [rbp-30h]
  SIZE_T v1291; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v1292; // [rsp+E0h] [rbp-20h] BYREF
  void *v1293; // [rsp+E8h] [rbp-18h] BYREF
  LPVOID v1294; // [rsp+F0h] [rbp-10h]
  SIZE_T Size; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID v1296; // [rsp+100h] [rbp+0h]
  __int64 v1297; // [rsp+108h] [rbp+8h]
  SIZE_T v1298; // [rsp+110h] [rbp+10h]
  LPVOID Src[2]; // [rsp+118h] [rbp+18h] BYREF
  LPVOID v1300; // [rsp+128h] [rbp+28h] BYREF
  _DWORD *v1301; // [rsp+130h] [rbp+30h] BYREF
  SIZE_T v1302; // [rsp+138h] [rbp+38h] BYREF
  LPVOID v1303; // [rsp+140h] [rbp+40h]
  LPVOID v1304; // [rsp+148h] [rbp+48h]
  unsigned int v1305; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v1306; // [rsp+158h] [rbp+58h]
  size_t v1307[2]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v1308; // [rsp+170h] [rbp+70h] BYREF
  __int128 lpModuleName; // [rsp+178h] [rbp+78h] BYREF
  unsigned int v1310; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v1311; // [rsp+18Ch] [rbp+8Ch] BYREF
  unsigned int v1312; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v1313; // [rsp+194h] [rbp+94h]
  __int128 v1314; // [rsp+198h] [rbp+98h]
  __int64 v1315; // [rsp+1A8h] [rbp+A8h]
  unsigned int v1316; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned int v1317; // [rsp+1B4h] [rbp+B4h] BYREF
  unsigned int v1318; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned int v1319; // [rsp+1BCh] [rbp+BCh] BYREF
  unsigned int v1320; // [rsp+1C0h] [rbp+C0h] BYREF
  int v1321; // [rsp+1C4h] [rbp+C4h] BYREF
  unsigned int v1322; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned int v1323; // [rsp+1CCh] [rbp+CCh] BYREF
  LPVOID lpMem; // [rsp+1D0h] [rbp+D0h]
  _BYTE *v1325; // [rsp+1D8h] [rbp+D8h] BYREF
  DWORD *v1326; // [rsp+1E0h] [rbp+E0h] BYREF
  HMODULE phModule; // [rsp+1F0h] [rbp+F0h] BYREF
  HMODULE hModule; // [rsp+200h] [rbp+100h] BYREF
  __int128 v1329; // [rsp+208h] [rbp+108h] BYREF
  __int128 v1330; // [rsp+218h] [rbp+118h]
  __int128 v1331; // [rsp+228h] [rbp+128h] BYREF
  __int128 v1332; // [rsp+238h] [rbp+138h]
  __int64 v1333; // [rsp+248h] [rbp+148h] BYREF
  DWORD *v1334; // [rsp+258h] [rbp+158h]
  __int64 v1335; // [rsp+260h] [rbp+160h] BYREF
  __int64 v1336; // [rsp+268h] [rbp+168h] BYREF
  __int64 v1337; // [rsp+270h] [rbp+170h] BYREF
  __int128 v1338; // [rsp+278h] [rbp+178h] BYREF
  __int64 v1339[17]; // [rsp+288h] [rbp+188h] BYREF
  _OWORD v1340[3]; // [rsp+310h] [rbp+210h] BYREF
  _QWORD v1341[20]; // [rsp+340h] [rbp+240h] BYREF
  int v1342; // [rsp+3E0h] [rbp+2E0h] BYREF
  int v1343; // [rsp+3E4h] [rbp+2E4h]
  void *v1344; // [rsp+3E8h] [rbp+2E8h]
  void *v1345; // [rsp+3F0h] [rbp+2F0h]
  void *v1346; // [rsp+3F8h] [rbp+2F8h]
  SIZE_T v1347; // [rsp+400h] [rbp+300h]
  SIZE_T v1348; // [rsp+408h] [rbp+308h]
  __int64 v1349; // [rsp+410h] [rbp+310h]
  int v1350; // [rsp+418h] [rbp+318h]
  int v1351; // [rsp+41Ch] [rbp+31Ch] BYREF
  int v1352; // [rsp+420h] [rbp+320h]
  int v1353; // [rsp+424h] [rbp+324h]
  int v1354; // [rsp+428h] [rbp+328h]
  int v1355; // [rsp+42Ch] [rbp+32Ch] BYREF
  int v1356; // [rsp+430h] [rbp+330h]
  int v1357; // [rsp+434h] [rbp+334h]
  unsigned int v1358; // [rsp+438h] [rbp+338h]
  unsigned int v1359; // [rsp+43Ch] [rbp+33Ch] BYREF
  unsigned int v1360; // [rsp+440h] [rbp+340h]
  unsigned int v1361; // [rsp+444h] [rbp+344h]
  unsigned int v1362; // [rsp+448h] [rbp+348h]
  int v1363; // [rsp+450h] [rbp+350h] BYREF
  _DWORD v1364[3]; // [rsp+454h] [rbp+354h] BYREF
  __int16 v1365; // [rsp+462h] [rbp+362h]
  __int64 v1366; // [rsp+468h] [rbp+368h]
  int v1367; // [rsp+4C0h] [rbp+3C0h] BYREF
  _DWORD v1368[5]; // [rsp+4C4h] [rbp+3C4h] BYREF
  SIZE_T v1369; // [rsp+4D8h] [rbp+3D8h]
  int v1370; // [rsp+530h] [rbp+430h] BYREF
  _DWORD v1371[5]; // [rsp+534h] [rbp+434h] BYREF
  size_t v1372; // [rsp+548h] [rbp+448h]
  int v1373; // [rsp+5A0h] [rbp+4A0h] BYREF
  _DWORD v1374[5]; // [rsp+5A4h] [rbp+4A4h] BYREF
  size_t v1375; // [rsp+5B8h] [rbp+4B8h]
  int v1376; // [rsp+610h] [rbp+510h] BYREF
  _DWORD v1377[5]; // [rsp+614h] [rbp+514h] BYREF
  size_t v1378; // [rsp+628h] [rbp+528h]
  int v1379; // [rsp+680h] [rbp+580h] BYREF
  char v1380[20]; // [rsp+684h] [rbp+584h] BYREF
  const wchar_t *v1381; // [rsp+698h] [rbp+598h]
  int v1382; // [rsp+6F0h] [rbp+5F0h] BYREF
  char v1383[20]; // [rsp+6F4h] [rbp+5F4h] BYREF
  const wchar_t *v1384; // [rsp+708h] [rbp+608h]
  int v1385; // [rsp+760h] [rbp+660h] BYREF
  char v1386[20]; // [rsp+764h] [rbp+664h] BYREF
  const wchar_t *v1387; // [rsp+778h] [rbp+678h]
  int v1388; // [rsp+7D0h] [rbp+6D0h] BYREF
  char v1389[20]; // [rsp+7D4h] [rbp+6D4h] BYREF
  const wchar_t *v1390; // [rsp+7E8h] [rbp+6E8h]
  __int128 v1391; // [rsp+840h] [rbp+740h] BYREF
  __int128 v1392; // [rsp+850h] [rbp+750h] BYREF
  __int128 v1393; // [rsp+860h] [rbp+760h] BYREF
  __int128 v1394; // [rsp+870h] [rbp+770h] BYREF
  __int64 v1395; // [rsp+880h] [rbp+780h] BYREF
  int v1396; // [rsp+888h] [rbp+788h]
  int v1397; // [rsp+88Ch] [rbp+78Ch]
  _DWORD v1398[12]; // [rsp+890h] [rbp+790h] BYREF
  __int128 v1399; // [rsp+8C0h] [rbp+7C0h] BYREF
  __int128 v1400; // [rsp+8D0h] [rbp+7D0h] BYREF
  __int64 v1401; // [rsp+8E0h] [rbp+7E0h]
  __int128 v1402; // [rsp+8E8h] [rbp+7E8h] BYREF
  _OWORD v1403[2]; // [rsp+8F8h] [rbp+7F8h] BYREF
  __int128 v1404; // [rsp+918h] [rbp+818h] BYREF
  _OWORD v1405[2]; // [rsp+928h] [rbp+828h] BYREF
  __int128 v1406; // [rsp+948h] [rbp+848h] BYREF
  _OWORD v1407[2]; // [rsp+958h] [rbp+858h] BYREF
  __int128 v1408; // [rsp+978h] [rbp+878h] BYREF
  _OWORD v1409[2]; // [rsp+988h] [rbp+888h] BYREF
  __int128 v1410; // [rsp+9A8h] [rbp+8A8h] BYREF
  __int128 v1411; // [rsp+9B8h] [rbp+8B8h] BYREF
  __int64 v1412; // [rsp+9C8h] [rbp+8C8h]
  _OWORD v1413[2]; // [rsp+9D0h] [rbp+8D0h] BYREF
  _DWORD v1414[6]; // [rsp+9F0h] [rbp+8F0h] BYREF
  char v1415; // [rsp+A0Ah] [rbp+90Ah]
  unsigned __int16 v1416[34]; // [rsp+A0Ch] [rbp+90Ch] BYREF
  _DWORD v1417[6]; // [rsp+A50h] [rbp+950h] BYREF
  char v1418; // [rsp+A6Ah] [rbp+96Ah]
  unsigned __int16 v1419[34]; // [rsp+A6Ch] [rbp+96Ch] BYREF
  _DWORD v1420[6]; // [rsp+AB0h] [rbp+9B0h] BYREF
  char v1421; // [rsp+ACAh] [rbp+9CAh]
  unsigned __int16 v1422[34]; // [rsp+ACCh] [rbp+9CCh] BYREF
  _BYTE v1423[68]; // [rsp+B10h] [rbp+A10h] BYREF
  __int16 v1424; // [rsp+B54h] [rbp+A54h]
  unsigned __int16 v1425; // [rsp+BB6h] [rbp+AB6h]
  int v1426; // [rsp+BBCh] [rbp+ABCh]
  int v1427; // [rsp+BC0h] [rbp+AC0h]
  int v1428; // [rsp+BF0h] [rbp+AF0h] BYREF
  __int128 v1429; // [rsp+BF8h] [rbp+AF8h]
  __int128 v1430; // [rsp+C08h] [rbp+B08h]
  __int128 v1431; // [rsp+C18h] [rbp+B18h]
  __int64 v1432; // [rsp+C28h] [rbp+B28h]
  _BYTE v1433[176]; // [rsp+C30h] [rbp+B30h] BYREF
  WCHAR Filename[264]; // [rsp+CE0h] [rbp+BE0h] BYREF

  v1334 = pdwValue;
  v1326 = 0;
  if ( pdwValue )
  {
    v1276 = 0;
    v1308 = 0;
    while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
      ;
    v3 = g_WarbirdSecureFunctionsRefCount;
    v1305 = -1;
    if ( !g_WarbirdSecureFunctionsRefCount )
    {
      v4 = MemoryAlloc(0x338u);
      v5 = v4;
      if ( !v4 )
        goto LABEL_13;
      v6 = qword_180078760;
      v7 = v4;
      v8 = 0;
      v9 = -1;
      v10 = 0;
      v11 = 0;
      v12 = 103;
      do
      {
        v13 = *(unsigned __int8 *)v6 << 8;
        v14 = *((unsigned __int8 *)v6 + 1);
        v15 = *((unsigned __int8 *)v6++ + 4);
        v16 = *((unsigned __int8 *)v6 - 5) | ((*((unsigned __int8 *)v6 - 6) | ((v13 | v14) << 8)) << 8);
        v17 = v11 ^ v16;
        v18 = *((unsigned __int8 *)v6 - 1)
            | ((*((unsigned __int8 *)v6 - 2) | ((*((unsigned __int8 *)v6 - 3) | (v15 << 8)) << 8)) << 8);
        v19 = v10 ^ v18 ^ v11 ^ v16 ^ 0xAC987321;
        v20 = v17 ^ (__ROR4__(v19, 22) + 4991 * __ROR4__(v19 + 1419157410, 27));
        v21 = v19 ^ (43881 * __ROR4__(v20 + 133239679, 9) - __ROR4__(v20, 30));
        v22 = v20 ^ (24670 * v21 - (v21 >> 13) - 123127970);
        v23 = v21 ^ (2033 * __ROR4__(v22 ^ 0xAB69, 26) - __ROR4__(v22, 30));
        v24 = v22 ^ (133239679 - (v23 ^ 0xAB69605E));
        v25 = v23 ^ (43881 * (v24 ^ 0x137F)) ^ __ROR4__(v24, 6);
        v26 = v24 ^ (__ROR4__(v25, 30) + 24670 * __ROR4__(v25 + 133239679, 15));
        v27 = v25 ^ (2033 * __ROR4__(v26 + 1419157410, 14) - __ROR4__(v26, 24));
        v28 = v26 ^ __ROR4__(v27, 10) ^ (4991 * __ROR4__(v27 ^ 0xAB69605E, 12));
        v29 = v27 ^ (v28 >> 10) ^ (43881 * (v28 ^ 0x7F1));
        v30 = v28 ^ (2033 * (__ROR4__(~v29, 5) + 24670));
        v31 = v30 ^ (((v29 ^ (v30 - 2033) ^ 0xAB69605E) >> 2) + 4991 * __ROR4__(v29 ^ (v30 - 2033) ^ 0xAB6967AF, 30));
        v32 = v29 ^ (v30 - 2033) ^ 0xAB69605E ^ (__ROR4__(v31, 25) + 43881 * __ROR4__(v31 - 133239679, 6));
        v33 = v31 ^ (24670 * (v32 ^ 0x137F) + __ROR4__(v32, 9));
        v34 = v32 ^ (__ROR4__(v33, 25) + 2033 * __ROR4__(v33 ^ 0xAB69, 27));
        v35 = v33 ^ v34 ^ 0xAC987321;
        v36 = v34 ^ (4991 * __ROR4__(v35, 3) - 219010071);
        v37 = v35 ^ (24670 * __ROR4__(v36 - 133239679, 1) - __ROR4__(v36, 6));
        v38 = v36 ^ (__ROR4__(v37, 18) + 2033 * __ROR4__(v37 - 1419157410, 29));
        v39 = v37 ^ (4991 * __ROR4__(v38 - 1419157410, 17) - __ROR4__(v38, 14));
        v40 = v38 ^ (v39 >> 3) ^ (43881 * (v39 ^ 0x605E));
        v41 = __ROR4__(v40, 30);
        v10 = v9 ^ v40;
        v9 = v18;
        v11 = v8 ^ v39 ^ v41 ^ (24670 * __ROR4__(v38 ^ (v39 >> 3) ^ (43881 * (v39 ^ 0x605E)) ^ 0x7F1137F, 28));
        v8 = v16;
        v7[3] = v11;
        v7[7] = v10;
        v7[2] = __ROR4__(v11, 8);
        v7[6] = __ROR4__(v10, 8);
        v7[1] = __ROR4__(v11, 16);
        v7[5] = __ROR4__(v10, 16);
        *v7 = __ROR4__(v11, 24);
        v7[4] = __ROR4__(v10, 24);
        v7 += 8;
        --v12;
      }
      while ( v12 );
      v42 = 0;
      v43 = 0;
      do
        v43 ^= v5[v42++];
      while ( v42 < 0x338 );
      if ( v43 != 64 )
      {
        MemoryFree(v5);
LABEL_13:
        for ( i = 0; i != 4; ++i )
        {
          v45 = (HMODULE)*(&WARBIRD::g_arModuleInfo + 3 * i);
          if ( v45 )
            FreeLibrary(v45);
        }
        memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
        memcpy_0(&WARBIRD::g_FuncAddress, off_18006E730, 0x170u);
LABEL_46:
        _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
        v59 = 0;
        v1291 = 0;
        v60 = 0;
        pcchLength = 0;
        v61 = 0;
        if ( NtCurrentPeb()->SessionId )
        {
          v62 = 0;
          v63 = ((__int64 (*)(void))off_180086110[0])();
          if ( !v63 )
          {
LABEL_48:
            LastError = GetLastError();
            v65 = LastError < 0;
            if ( LastError > 0 )
            {
              LastError = (unsigned __int16)LastError | 0x80070000;
              v65 = LastError < 0;
            }
            if ( !v65 )
              LastError = -2147467259;
            goto LABEL_100;
          }
          v1318 = 0;
          v66 = 0;
          v1284 = 0;
          for ( j = 0; ; v1284 = j )
          {
            v68 = 0;
            if ( j )
              v68 = j;
            if ( ((unsigned int (__fastcall *)(__int64, __int64, void *, __int64, unsigned int *))off_180086130[0])(
                   v63,
                   2,
                   v68,
                   v66,
                   &v1318) )
            {
              v1291 = (SIZE_T)j;
              LastError = 0;
              v59 = (const wchar_t *)j;
              goto LABEL_67;
            }
            LastError = GetLastError();
            if ( LastError != 122 )
              break;
            if ( j )
              goto LABEL_62;
            j = MemoryAlloc(v1318);
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1284);
            if ( !j )
            {
              LastError = -2147024882;
LABEL_67:
              v1284 = 0;
              goto LABEL_68;
            }
            v66 = v1318;
          }
          if ( !LastError )
          {
LABEL_62:
            LastError = -2147467259;
            goto LABEL_68;
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_68:
          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1284);
          if ( LastError < 0 )
            goto LABEL_100;
          v69 = off_180086128[0];
          CurrentThreadId = GetCurrentThreadId();
          v71 = ((__int64 (__fastcall *)(_QWORD))v69)(CurrentThreadId);
          if ( !v71 )
            goto LABEL_48;
          v1317 = 0;
          v72 = 0;
          v1284 = 0;
          for ( k = 0; ; v1284 = k )
          {
            v74 = 0;
            if ( k )
              v74 = k;
            if ( ((unsigned int (__fastcall *)(__int64, __int64, void *, __int64, unsigned int *))off_180086130[0])(
                   v71,
                   2,
                   v74,
                   v72,
                   &v1317) )
            {
              pcchLength = (size_t)k;
              LastError = 0;
              v60 = (const wchar_t *)k;
              goto LABEL_84;
            }
            LastError = GetLastError();
            if ( LastError != 122 )
              break;
            if ( k )
              goto LABEL_79;
            k = MemoryAlloc(v1317);
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1284);
            if ( !k )
            {
              LastError = -2147024882;
LABEL_84:
              v1284 = 0;
              goto LABEL_85;
            }
            v72 = v1317;
          }
          if ( !LastError )
          {
LABEL_79:
            LastError = -2147467259;
            goto LABEL_85;
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_85:
          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1284);
          if ( LastError < 0 )
          {
LABEL_100:
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&pcchLength);
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1291);
            v77 = 0;
            if ( LastError >= 0 )
              v77 = v62;
            LODWORD(v1306) = v77;
            v78 = LocalAlloc(0x40u, 4u);
            SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v1308, v78);
            lpMem = (LPVOID)v1308;
            if ( !v1308 )
            {
              v83 = -2147024882;
              v1270 = 0;
              goto LABEL_1576;
            }
            v1313 = 0;
            v79 = 0;
            *(_OWORD *)Src = 0;
            v1304 = 0;
            ProcessHeap = GetProcessHeap();
            v81 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
            LODWORD(v1285) = -805306345;
            v82 = v81;
            v83 = -1073741801;
            if ( !v81 )
            {
              v84 = 0;
              LODWORD(dwBytes) = -1073741801;
LABEL_135:
              v117 = Src[1];
              Src[0] = 0;
              if ( Src[1] )
              {
                v118 = GetProcessHeap();
                HeapFree(v118, 0, v117);
                Src[1] = 0;
              }
              if ( v79 )
              {
                v119 = GetProcessHeap();
                HeapFree(v119, 0, v79);
              }
              if ( v82 )
              {
                v120 = GetProcessHeap();
                HeapFree(v120, 0, v82);
              }
              if ( v84 )
              {
                v121 = GetProcessHeap();
                HeapFree(v121, 0, v84);
              }
              v122 = 0;
              if ( v83 >= 0 )
              {
                if ( !(_DWORD)v1306 )
                {
LABEL_1573:
                  v1270 = v1313;
                  v1326 = (DWORD *)lpMem;
                  v1308 = 0;
                  goto LABEL_1576;
                }
                v1300 = 0;
                g_WarbirdNotificationInformation = v1306;
                ModuleFileNameW = GetModuleFileNameW(&_ImageBase, Filename, 0x104u);
                if ( !ModuleFileNameW || ModuleFileNameW == 260 && GetLastError() == 122 )
                {
LABEL_1193:
                  SH<void *,SH_HANDLE>::Reset(&v1300);
                  v1281 = 0;
                  *(_OWORD *)v1307 = 0;
                  v932 = 0;
                  v933 = 0;
                  v934 = GetProcessHeap();
                  v935 = HeapAlloc(v934, 8u, 0xA0u);
                  v936 = v935;
                  if ( !v935 )
                  {
                    v936 = 0;
LABEL_1565:
                    v1265 = (void *)v1307[1];
                    v1307[0] = 0;
                    if ( v1307[1] )
                    {
                      v1266 = GetProcessHeap();
                      HeapFree(v1266, 0, v1265);
                      v1307[1] = 0;
                    }
                    if ( v933 )
                    {
                      v1267 = GetProcessHeap();
                      HeapFree(v1267, 0, v933);
                    }
                    if ( v936 )
                    {
                      v1268 = GetProcessHeap();
                      HeapFree(v1268, 0, v936);
                    }
                    if ( v932 )
                    {
                      v1269 = GetProcessHeap();
                      HeapFree(v1269, 0, v932);
                    }
                    goto LABEL_1573;
                  }
                  *v935 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
                  v935[1] = xmmword_1800865D0;
                  v935[2] = xmmword_1800865E0;
                  v935[3] = xmmword_1800865F0;
                  v935[4] = xmmword_180086600;
                  v935[5] = xmmword_180086610;
                  v935[6] = xmmword_180086620;
                  v935[7] = xmmword_180086630;
                  v935[8] = xmmword_180086640;
                  v935[9] = xmmword_180086650;
                  v937 = GetProcessHeap();
                  v938 = HeapAlloc(v937, 8u, 8u);
                  v939 = v938;
                  if ( v938 )
                  {
                    *v938 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
                    v1300 = (LPVOID)__rdtsc();
                    v1277 = 0;
                    v1276 = 0;
                    if ( (int)RtlUIntAdd(4, 4, &v1276) < 0 )
                      goto LABEL_1563;
                    if ( (int)RtlUIntAdd(0, v1276, &v1277) < 0 )
                      goto LABEL_1563;
                    v1276 = v941;
                    if ( (int)RtlUIntAdd(v940, 160, &v1276) < 0 )
                      goto LABEL_1563;
                    v942 = RtlUIntAdd((unsigned int)v1277, v1276, &v1277);
                    if ( (v945 | v942) < 0 )
                      goto LABEL_1563;
                    v1276 = v944;
                    if ( (int)RtlUIntAdd(v943, 8, &v1276) < 0 )
                      goto LABEL_1563;
                    v946 = RtlUIntAdd((unsigned int)v1277, v1276, &v1277);
                    if ( (v949 | v946) < 0
                      || (v1276 = v948, (int)RtlUIntAdd(v947, 8, &v1276) < 0)
                      || (v950 = RtlUIntAdd((unsigned int)v1277, v1276, &v1277), (v951 | v950) < 0)
                      || (HIDWORD(v1307[0]) = v1277,
                          v952 = v1277,
                          v953 = GetProcessHeap(),
                          v954 = (const wchar_t *)HeapAlloc(v953, 8u, v952),
                          (v955 = (wchar_t *)v954) == 0) )
                    {
LABEL_1563:
                      v932 = v939;
                      goto LABEL_1564;
                    }
                    v1307[1] = (size_t)v954;
                    LODWORD(v1307[0]) = 0;
                    *(_QWORD *)((char *)&lpModuleName + 4) = 0;
                    psz = v954;
                    v932 = v939;
                    if ( (int)RtlULongLongAdd(v954, 4, (char *)&lpModuleName + 8) < 0
                      || (unsigned __int64)(v955 + 4) > v1307[1] + HIDWORD(v1307[0]) )
                    {
                      goto LABEL_1564;
                    }
                    v958 = (unsigned int *)*((_QWORD *)&lpModuleName + 1);
                    *(_DWORD *)v955 = v956;
                    v959 = v956;
                    *v958 = v956;
                    v960 = LODWORD(v1307[0]) + 1;
                    *(_QWORD *)((char *)&lpModuleName + 4) = 0;
                    ++LODWORD(v1307[0]);
                    if ( v936 )
                    {
                      if ( !v957 )
                        goto LABEL_1564;
                    }
                    else if ( v957 )
                    {
                      goto LABEL_1564;
                    }
                    v961 = (STRSAFE_PCNZWCH)v1307[1];
                    if ( v1307[1] )
                    {
                      psz = (STRSAFE_PCNZWCH)v1307[1];
                      for ( m = 0; m < v960; ++m )
                      {
                        v964 = *(unsigned int *)v961;
                        v1276 = 0;
                        if ( (int)RtlUIntAdd(4, v964, &v1276) < 0 || (int)RtlULongLongAdd(v965, v1276, &psz) < 0 )
                          goto LABEL_1564;
                        v961 = psz;
                      }
                      v959 = 4;
                      if ( (int)RtlULongLongAdd(v961, 4, (char *)&lpModuleName + 8) < 0 )
                        goto LABEL_1564;
                      v968 = v967;
                      if ( (unsigned __int64)v966 + v967 + 4 > v1307[1] + HIDWORD(v1307[0]) )
                        goto LABEL_1564;
                      *v966 = v967;
                      v962 = 0;
                      if ( v936 )
                      {
                        memcpy_0(*((void **)&lpModuleName + 1), v936, v968);
                        v962 = 0;
                      }
                    }
                    else
                    {
                      v1276 = 0;
                      if ( (int)RtlUIntAdd(v959, v957, &v1276) < 0
                        || (int)RtlUIntAdd(HIDWORD(v1307[0]), v1276, (char *)v1307 + 4) < 0 )
                      {
                        goto LABEL_1564;
                      }
                    }
                    v969 = LODWORD(v1307[0]) + 1;
                    *(_QWORD *)((char *)&lpModuleName + 4) = 0;
                    ++LODWORD(v1307[0]);
                    if ( v939 )
                    {
                      v970 = (STRSAFE_PCNZWCH)v1307[1];
                      if ( v1307[1] )
                      {
                        psz = (STRSAFE_PCNZWCH)v1307[1];
                        while ( v962 < v969 )
                        {
                          v972 = *(unsigned int *)v970;
                          v1276 = 0;
                          if ( (int)RtlUIntAdd(4, v972, &v1276) < 0 || (int)RtlULongLongAdd(v973, v1276, &psz) < 0 )
                            goto LABEL_1564;
                          v970 = psz;
                          v962 = v974 + 1;
                        }
                        if ( (int)RtlULongLongAdd(v970, 4, (char *)&lpModuleName + 8) < 0
                          || (unsigned __int64)(v975 + 3) > v1307[1] + HIDWORD(v1307[0]) )
                        {
                          goto LABEL_1564;
                        }
                        *v975 = 8;
                        memcpy_0(*((void **)&lpModuleName + 1), v939, 8u);
                        v971 = 0;
                      }
                      else
                      {
                        v1276 = v962;
                        if ( (int)RtlUIntAdd(v959, 8, &v1276) < 0
                          || (int)RtlUIntAdd(HIDWORD(v1307[0]), v1276, (char *)v1307 + 4) < 0 )
                        {
                          goto LABEL_1564;
                        }
                      }
                      v976 = (STRSAFE_PCNZWCH)v1307[1];
                      v977 = LODWORD(v1307[0]) + 1;
                      *(_QWORD *)((char *)&lpModuleName + 4) = 0;
                      ++LODWORD(v1307[0]);
                      if ( v1307[1] )
                      {
                        psz = (STRSAFE_PCNZWCH)v1307[1];
                        while ( v971 < v977 )
                        {
                          v980 = *(unsigned int *)v976;
                          v1276 = 0;
                          if ( (int)RtlUIntAdd(4, v980, &v1276) < 0 || (int)RtlULongLongAdd(v981, v1276, &psz) < 0 )
                            goto LABEL_1564;
                          v976 = psz;
                          v971 = v982 + 1;
                        }
                        v983 = RtlULongLongAdd(v976, 4, (char *)&lpModuleName + 8);
                        v979 = 0;
                        if ( v983 < 0 || (unsigned __int64)(v984 + 3) > v1307[1] + HIDWORD(v1307[0]) )
                          goto LABEL_1564;
                        v985 = (_QWORD *)*((_QWORD *)&lpModuleName + 1);
                        v986 = v1300;
                        *v984 = 8;
                        v978 = 4;
                        *v985 = v986;
                        ++LODWORD(v1307[0]);
                      }
                      else
                      {
                        v1276 = v971;
                        if ( (int)RtlUIntAdd(4, 8, &v1276) < 0
                          || (int)RtlUIntAdd(HIDWORD(v1307[0]), v1276, (char *)v1307 + 4) < 0 )
                        {
                          goto LABEL_1564;
                        }
                        ++LODWORD(v1307[0]);
                      }
                      v1276 = v979;
                      if ( (int)RtlUIntAdd(v978, v978, &v1276) >= 0 )
                      {
                        LODWORD(v1283) = v1276;
                        v1276 = v988;
                        if ( (int)RtlUIntAdd(v987, 8, &v1276) >= 0 && (int)RtlUIntAdd(v989, v1276, &v1283) >= 0 )
                        {
                          v991 = (int)v1283;
                          HIDWORD(dwBytes) = (_DWORD)v1283;
                          v1283 = v990;
                          LODWORD(v1303) = (_DWORD)v990;
                          v1300 = (LPVOID)__rdtsc();
                          v1312 = 8;
                          v992 = RtlUIntAdd(8, HIDWORD(v1307[0]), &v1312);
                          if ( v992 < 0 )
                          {
                            v1294 = v932;
                            v1280 = v936;
                          }
                          else
                          {
                            v996 = (v1312 + 7) & 0xFFFFFFF8;
                            if ( v996 < v1312 )
                              goto LABEL_1564;
                            v1312 = (v1312 + 7) & 0xFFFFFFF8;
                            v997 = v996;
                            v998 = GetProcessHeap();
                            v999 = (char *)HeapAlloc(v998, 8u, v997);
                            LODWORD(v995) = 0;
                            v1000 = v999;
                            if ( !v999 )
                              goto LABEL_1548;
                            v1289 = (size_t)v999;
                            v1280 = v936;
                            v1294 = v932;
                            HIDWORD(dwBytes) = v991;
                            *(_DWORD *)v999 = v1307[0];
                            LODWORD(v1279) = RtlULongLongAdd(v999, 4, &v1289);
                            if ( (v1279 & 0x80000000) != 0LL
                              || (v1002 = v1289,
                                  *(_DWORD *)v1289 = HIDWORD(v1307[0]),
                                  LODWORD(v1279) = RtlULongLongAdd(v1002, v1001, &v1289),
                                  (v1279 & 0x80000000) != 0LL) )
                            {
                              v1280 = v936;
                              v1294 = v932;
                              HIDWORD(dwBytes) = v991;
                              v1003 = GetProcessHeap();
                              HeapFree(v1003, 0, v1000);
                              v993 = v1283;
                              v994 = (unsigned int)v1283;
                            }
                            else
                            {
                              *(_QWORD *)&v1000[v1312 - 8] = v1300;
                              memcpy_0((void *)v1289, (const void *)v1307[1], HIDWORD(v1307[0]));
                              v994 = v1312;
                              v993 = v1000;
                              v1283 = v1000;
                            }
                            v992 = v1279;
                            v995 = 0;
                          }
                          v1004 = v992 | 0x10000000;
                          v1302 = (SIZE_T)v995;
                          v1005 = v995;
                          v1293 = v995;
                          v1006 = v995;
                          v1296 = v995;
                          v1288 = v995;
                          if ( v1004 < 0 )
                          {
                            v1120 = v995;
                            goto LABEL_1523;
                          }
                          if ( v993 )
                          {
                            v1291 = v994;
                            if ( !v994 || (v1289 = v994 + 8LL, (Size = (SIZE_T)MemoryAlloc(v1289)) == 0) )
                            {
                              v1235 = v1283;
                              v1120 = v1005;
                              LODWORD(v1285) = -805306367;
                              goto LABEL_1525;
                            }
                            v1007 = 0;
                            v1304 = 0;
                            v1008 = 0;
                            v1009 = v1291;
                            v1278 = 0;
                            if ( v1291 )
                            {
                              do
                                v1007 ^= *((_BYTE *)v1283 + v1008++);
                              while ( v1008 < v1291 );
                              v1278 = v1007;
                            }
                            v1306 = 0xC81ECB17B1B54A58uLL;
                            psz = (STRSAFE_PCNZWCH)v1283;
                            v1010 = (const wchar_t *)v1283;
                            pcchLength = Size;
                            v1011 = v1291 & 7;
                            if ( (v1291 & 7) != 0 )
                            {
                              LODWORD(v1297) = 0;
                              LODWORD(v1298) = 0;
                              v1012 = 0;
                              v1013 = 0;
                              v1014 = 0;
                              do
                              {
                                v1015 = *(unsigned __int8 *)v1010;
                                v1010 = (const wchar_t *)((char *)v1010 + 1);
                                v1276 = 8 * v1012;
                                if ( v1012 >= 4 )
                                  v1013 |= v1015 << (56 - v1276);
                                else
                                  v1014 |= v1015 << (24 - v1276);
                                ++v1012;
                              }
                              while ( (int)v1012 < (int)v1011 );
                              v1007 = v1278;
                              LODWORD(v1298) = v1014;
                              v1005 = v1006;
                              v1016 = (_BYTE *)pcchLength;
                              LODWORD(v1297) = v1013;
                              psz = v1010;
                              v1294 = v932;
                              v1280 = v936;
                              v1017 = v1298 ^ 0xB17A307A;
                              LODWORD(v1282) = 0;
                              v1018 = v1013 ^ 0x42F6B18D;
                              v1019 = v1298 ^ 0xB17A307A;
                              if ( (v1291 & 7) != 0 )
                              {
                                v1020 = (unsigned int)v1282;
                                v1021 = v1297 ^ 0x42F6B18D;
                                do
                                {
                                  v1300 = v1016 + 1;
                                  if ( v1020 >= 4 )
                                  {
                                    v1021 = __ROR4__(v1021, 24);
                                    v1022 = v1021;
                                  }
                                  else
                                  {
                                    v1019 = __ROR4__(v1019, 24);
                                    v1022 = v1019;
                                  }
                                  *v1016 = v1022;
                                  ++v1020;
                                  v1016 = v1300;
                                }
                                while ( (int)v1020 < (int)v1011 );
                                pcchLength = (size_t)v1300;
                                v1006 = (unsigned int *)v1293;
                                v1005 = (unsigned int *)v1293;
                              }
                              if ( v1011 <= 4 )
                              {
                                v1023 = 0;
                                if ( v1011 < 4 )
                                  v1017 = v1017 >> (8 * (4 - v1011)) << (8 * (4 - v1011));
                              }
                              else
                              {
                                v1023 = v1018 >> (8 * (8 - v1011)) << (8 * (8 - v1011));
                              }
                            }
                            else
                            {
                              v1017 = 0;
                              LODWORD(v1298) = 0;
                              v1023 = -1;
                              LODWORD(v1297) = 0;
                            }
                            if ( v1009 >> 3 )
                            {
                              v1024 = psz;
                              v1025 = v1009 >> 3;
                              v1026 = (_BYTE *)pcchLength;
                              v1027 = v1298;
                              v1277 = 19032;
                              LODWORD(v1292) = WORD1(v1306);
                              v1308 = 0;
                              v1028 = HIDWORD(v1306);
                              LODWORD(v1282) = WORD2(v1306);
                              v1029 = WORD2(v1306);
                              LODWORD(v1279) = HIWORD(v1306);
                              v1030 = v1297;
                              do
                              {
                                v1031 = *((unsigned __int8 *)v1024 + 1);
                                v1032 = *(unsigned __int8 *)v1024;
                                v1033 = *((unsigned __int8 *)v1024 + 4);
                                v1024 += 4;
                                v1034 = *((unsigned __int8 *)v1024 - 5)
                                      | ((*((unsigned __int8 *)v1024 - 6) | ((v1031 | (v1032 << 8)) << 8)) << 8);
                                v1035 = *((unsigned __int8 *)v1024 - 1)
                                      | ((*((unsigned __int8 *)v1024 - 2)
                                        | ((*((unsigned __int8 *)v1024 - 3) | (v1033 << 8)) << 8)) << 8);
                                v1036 = v1023 ^ v1035;
                                v1037 = v1017 ^ v1034 ^ v1028 ^ ((v1023 ^ v1035) - v1277);
                                v1038 = v1036
                                      ^ (__ROR4__(v1037, 7) + WORD1(v1306) * __ROR4__(HIDWORD(v1306) ^ v1037, 15));
                                v1039 = v1037 ^ (v1029 * __ROR4__(v1038 - 1313519016, 9) - __ROR4__(v1038, 10));
                                v1040 = v1038 ^ (__ROR4__(v1039, 27) + HIWORD(v1306) * __ROR4__(v1029 ^ v1039, 28));
                                v1028 = HIDWORD(v1306);
                                v1041 = v1039 ^ (HIDWORD(v1306) - (v1040 ^ 0xB1B54A58));
                                v1042 = v1040 ^ (WORD1(v1306) * (v1041 - v1277) - (v1041 >> 6));
                                v1043 = v1041 ^ (v1277 * (v1029 ^ __ROR4__(v1042, 15)));
                                v1044 = v1042 ^ (v1029 * (v1279 + __ROR4__(~v1043, 3)));
                                v1045 = v1043 ^ (v1044 - v1277 - HIDWORD(v1306));
                                v1046 = v1044 ^ (v1292 * (v1279 ^ v1045)) ^ __ROR4__(v1045, 10);
                                v1047 = v1045 ^ __ROR4__(v1046, 3) ^ (v1029 * __ROR4__(v1277 ^ v1046, 26));
                                v1048 = v1046 ^ (v1277 * (__ROR4__(v1047, 15) - HIWORD(v1306)));
                                v1049 = v1047
                                      ^ (v1277 * (v1279 ^ v1048))
                                      ^ ((v1048 ^ (v1048 >> 14)) >> 1)
                                      ^ (v1277 * (((v1048 - v1029) >> 29) | (8 * (v1048 - v1029))));
                                v1050 = v1048 ^ (WORD1(v1306) * (v1049 - v1029) - (v1049 >> 13));
                                v1051 = v1049 ^ __ROR4__(v1050, 11) ^ (v1029 * __ROR4__(-1313519016 - v1050, 9));
                                v1052 = v1050 ^ (v1051 - HIWORD(v1306) + 1313519016);
                                v1053 = v1051 ^ (v1277 * (v1052 ^ WORD1(v1306)) - __ROR4__(v1052, 7));
                                v1054 = v1052
                                      ^ (WORD1(v1306) * __ROR4__(v1053 ^ HIWORD(v1306), 28) - __ROR4__(v1053, 16));
                                v1055 = v1053 ^ (__ROR4__(v1054, 4) + v1029 * __ROR4__(-1313519016 - v1054, 10));
                                v1056 = v1054 ^ __ROR4__(v1055, 9) ^ (HIWORD(v1306) * __ROR4__(v1055 + 1313519016, 4));
                                v1057 = v1055 ^ (v1277 * __ROR4__(v1056 ^ HIDWORD(v1306), 24) - __ROR4__(v1056, 30));
                                v1058 = v1056
                                      ^ (WORD1(v1306) * __ROR4__(HIDWORD(v1306) - v1057, 11) - __ROR4__(v1057, 12));
                                v1059 = v1057 ^ (v1058 >> 8) ^ (v1029 * (WORD1(v1306) ^ v1058));
                                v1017 = v1027 ^ v1059;
                                v1023 = v1030 ^ v1059 ^ HIDWORD(v1306) ^ v1058 ^ 0xB1B54A58;
                                v1026[3] = v1027 ^ v1059;
                                LOBYTE(v1043) = __ROR4__(v1027 ^ v1059, 8);
                                v1027 = v1034;
                                v1026[7] = v1023;
                                v1030 = v1035;
                                v1026[2] = v1043;
                                v1026[6] = __ROR4__(v1023, 8);
                                v1026[1] = __ROR4__(v1017, 16);
                                v1026[5] = __ROR4__(v1023, 16);
                                *v1026 = __ROR4__(v1017, 24);
                                v1026[4] = __ROR4__(v1023, 24);
                                v1026 += 8;
                                ++v1308;
                              }
                              while ( v1308 < v1025 );
                              v1006 = (unsigned int *)v1293;
                              v1007 = v1278;
                              v1005 = (unsigned int *)v1293;
                              v83 = dwBytes;
                              v936 = v1280;
                              v932 = v1294;
                              v1009 = v1291;
                            }
                            *(_QWORD *)(Size + v1009) = v1007;
                            v1060 = GetProcessHeap();
                            v1061 = HeapAlloc(v1060, 8u, 0x30u);
                            v1280 = v1061;
                            if ( !v1061 )
                            {
                              v1062 = v1283;
                              v1277 = -1073741801;
                              goto LABEL_1307;
                            }
                            v1063 = v1289;
                            *v1061 = v1289;
                            v1064 = GetProcessHeap();
                            v1065 = HeapAlloc(v1064, 8u, v1063);
                            v1062 = v1283;
                            if ( v1065 )
                            {
                              *((_QWORD *)v1280 + 1) = v1065;
                              memcpy_0(v1065, (const void *)Size, (unsigned int)v1289);
                              *((_DWORD *)v1280 + 4) = 160;
                              v1066 = GetProcessHeap();
                              v1067 = HeapAlloc(v1066, 8u, 0xA0u);
                              v1068 = v1280;
                              if ( v1067 )
                              {
                                *((_QWORD *)v1280 + 3) = v1067;
                                *v1067 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                                v1067[1] = xmmword_180086520;
                                v1067[2] = xmmword_180086530;
                                v1067[3] = xmmword_180086540;
                                v1067[4] = xmmword_180086550;
                                v1067[5] = xmmword_180086560;
                                v1067[6] = xmmword_180086570;
                                v1067[7] = xmmword_180086580;
                                v1067[8] = xmmword_180086590;
                                v1067[9] = xmmword_1800865A0;
                                v1068[8] = 8;
                                v1069 = GetProcessHeap();
                                v1070 = HeapAlloc(v1069, 8u, 8u);
                                if ( v1070 )
                                {
                                  v1076 = v1280;
                                  *((_QWORD *)v1280 + 5) = v1070;
                                  *v1070 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                                  v1304 = v1076;
                                  v1277 = 0;
                                  v1283 = v1062;
                                  goto LABEL_1306;
                                }
                                v1068 = v1280;
                              }
                              v1280 = v1068;
                            }
                            v1071 = v1280;
                            v1277 = -1073741801;
                            v1283 = v1062;
                            v1300 = (LPVOID)*((_QWORD *)v1280 + 1);
                            if ( v1300 )
                            {
                              v1072 = GetProcessHeap();
                              HeapFree(v1072, 0, v1300);
                              v1071 = v1280;
                              *((_QWORD *)v1280 + 1) = 0;
                            }
                            v1300 = (LPVOID)*((_QWORD *)v1071 + 3);
                            if ( v1300 )
                            {
                              v1073 = GetProcessHeap();
                              HeapFree(v1073, 0, v1300);
                              v1071 = v1280;
                              *((_QWORD *)v1280 + 3) = 0;
                            }
                            v1300 = (LPVOID)*((_QWORD *)v1071 + 5);
                            if ( v1300 )
                            {
                              v1074 = GetProcessHeap();
                              HeapFree(v1074, 0, v1300);
                              *((_QWORD *)v1280 + 5) = 0;
                            }
                            v1075 = GetProcessHeap();
                            HeapFree(v1075, 0, v1280);
                            if ( v1277 < 0 )
                            {
LABEL_1307:
                              v1077 = GetProcessHeap();
                              HeapFree(v1077, 0, (LPVOID)Size);
                              v1078 = v1304;
                              LODWORD(v995) = 0;
                              if ( v1304 )
                              {
                                v1300 = (LPVOID)*((_QWORD *)v1304 + 1);
                                if ( v1300 )
                                {
                                  v1079 = GetProcessHeap();
                                  HeapFree(v1079, 0, v1300);
                                  v1078 = v1304;
                                  *((_QWORD *)v1304 + 1) = 0;
                                }
                                v1300 = (LPVOID)*((_QWORD *)v1078 + 3);
                                if ( v1300 )
                                {
                                  v1080 = GetProcessHeap();
                                  HeapFree(v1080, 0, v1300);
                                  v1078 = v1304;
                                  *((_QWORD *)v1304 + 3) = 0;
                                }
                                v1300 = (LPVOID)*((_QWORD *)v1078 + 5);
                                if ( v1300 )
                                {
                                  v1081 = GetProcessHeap();
                                  HeapFree(v1081, 0, v1300);
                                  *((_QWORD *)v1304 + 5) = 0;
                                }
                                v1082 = GetProcessHeap();
                                HeapFree(v1082, 0, v1304);
                                LODWORD(v995) = 0;
                              }
                              v1083 = v1277 | 0x10000000;
                              if ( v1277 < 0 )
                              {
                                v1283 = v1062;
                                goto LABEL_1340;
                              }
                              v1084 = *v1005;
                              v1276 = 0;
                              LODWORD(v1285) = 4;
                              v1277 = RtlUIntAdd(4, v1084, &v1285);
                              if ( v1277 < 0 )
                                goto LABEL_1334;
                              v1277 = RtlUIntAdd((unsigned int)v1285, v1085, &v1285);
                              if ( v1277 < 0
                                || (v1086 = v1005[4],
                                    psz = (STRSAFE_PCNZWCH)(v1005 + 4),
                                    v1277 = RtlUIntAdd((unsigned int)v1285, v1086, &v1285),
                                    v1277 < 0)
                                || (v1277 = RtlUIntAdd((unsigned int)v1285, v1087, &v1285), v1277 < 0)
                                || (v1088 = v1005[8],
                                    pcchLength = (size_t)(v1005 + 8),
                                    v1277 = RtlUIntAdd((unsigned int)v1285, v1088, &v1285),
                                    v1277 < 0) )
                              {
LABEL_1334:
                                v1283 = v1062;
                              }
                              else
                              {
                                v1290 = v1005;
                                v1089 = v1285;
                                v1090 = GetProcessHeap();
                                v1091 = HeapAlloc(v1090, 8u, v1089);
                                v1005 = (unsigned int *)v1290;
                                LODWORD(v995) = 0;
                                v1294 = v1091;
                                if ( !v1091 )
                                {
LABEL_1322:
                                  LODWORD(v1285) = -805306345;
LABEL_1383:
                                  v1120 = v1288;
                                  goto LABEL_1524;
                                }
                                *v1091 = *(_DWORD *)v1290;
                                v1283 = v1062;
                                v1280 = v1091;
                                v1277 = RtlULongLongAdd(v1091, 4, &v1280);
                                if ( v1277 < 0 )
                                {
                                  HIDWORD(dwBytes) = v1093;
                                  v1294 = v1092;
                                }
                                else
                                {
                                  memcpy_0(v1280, *((const void **)v1005 + 1), *v1005);
                                  v1277 = RtlULongLongAdd(v1280, *v1005, &v1280);
                                  if ( v1277 >= 0 )
                                  {
                                    v1094 = v1280;
                                    *(_DWORD *)v1280 = *(_DWORD *)psz;
                                    v1277 = RtlULongLongAdd(v1094, 4, &v1280);
                                    if ( v1277 >= 0 )
                                    {
                                      memcpy_0(v1280, *((const void **)v1005 + 3), *v1095);
                                      v1277 = RtlULongLongAdd(v1280, *(unsigned int *)psz, &v1280);
                                      if ( v1277 >= 0 )
                                      {
                                        v1096 = v1280;
                                        *(_DWORD *)v1280 = *(_DWORD *)pcchLength;
                                        v1277 = RtlULongLongAdd(v1096, 4, &v1280);
                                        if ( v1277 >= 0 )
                                        {
                                          memcpy_0(v1280, *((const void **)v1005 + 5), *v1097);
                                          v1098 = RtlULongLongAdd(v1280, *(unsigned int *)pcchLength, &v1280);
                                          LODWORD(v995) = 0;
                                          v1277 = v1098;
                                          if ( v1098 >= 0 )
                                          {
                                            v1302 = (SIZE_T)v1294;
                                            v1276 = v1285;
LABEL_1336:
                                            v1083 = v1098 | 0x10000000;
                                            if ( v1083 < 0 )
                                              goto LABEL_1340;
                                            v1319 = 8;
                                            v1100 = RtlUIntAdd(8, HIDWORD(dwBytes), &v1319);
                                            v1083 = v1101 | v1100;
                                            if ( v1083 < 0 )
                                              goto LABEL_1340;
                                            v1102 = (v1319 + 7) & 0xFFFFFFF8;
                                            if ( (unsigned int)v1102 < v1319 )
                                            {
                                              v1083 = -1073741675;
LABEL_1340:
                                              LODWORD(v1285) = v1083;
                                              goto LABEL_1383;
                                            }
                                            v1322 = (v1319 + 7) & 0xFFFFFFF8;
                                            v1083 = RtlUIntAdd(v1102, 8, &v1322);
                                            if ( v1083 < 0 )
                                              goto LABEL_1340;
                                            v1103 = (_DWORD *)v1307[1];
                                            v1280 = v936;
                                            v1294 = v932;
                                            v1283 = v1062;
                                            v1290 = v1005;
                                            LODWORD(v1293) = (_DWORD)v995;
                                            if ( !v1307[1] )
                                              goto LABEL_1343;
                                            v1290 = v1005;
                                            v1283 = v1062;
                                            v1294 = v932;
                                            v1280 = v936;
                                            if ( LODWORD(v1307[0]) <= 1 )
                                              goto LABEL_1343;
                                            v1289 = v1307[1];
                                            for ( n = (int)v995; !n; n = v1106 + 1 )
                                            {
                                              v1083 = RtlULongLongAdd(v1103, 4, &v1289);
                                              if ( v1083 < 0 )
                                              {
LABEL_1366:
                                                LODWORD(v995) = 0;
                                                goto LABEL_1340;
                                              }
                                              v1083 = RtlULongLongAdd(v1289, v1105, &v1289);
                                              LODWORD(v995) = 0;
                                              if ( v1083 < 0 )
                                                goto LABEL_1340;
                                              v1103 = (_DWORD *)v1289;
                                            }
                                            LODWORD(v1282) = *v1103;
                                            v1083 = RtlULongLongAdd(v1103, 4, &v1289);
                                            LODWORD(v995) = 0;
                                            if ( v1083 < 0 )
                                              goto LABEL_1340;
                                            v1107 = v1307[1];
                                            if ( !v1307[1] || LODWORD(v1307[0]) <= 2 )
                                            {
LABEL_1343:
                                              v1083 = -1073741811;
                                              goto LABEL_1340;
                                            }
                                            v1289 = v1307[1];
                                            for ( ii = 0; ii < 2; ii = v1110 + 1 )
                                            {
                                              v1083 = RtlULongLongAdd(v1107, 4, &v1289);
                                              if ( v1083 < 0 )
                                                goto LABEL_1366;
                                              v1083 = RtlULongLongAdd(v1289, v1109, &v1289);
                                              LODWORD(v995) = 0;
                                              if ( v1083 < 0 )
                                                goto LABEL_1340;
                                              v1107 = v1289;
                                            }
                                            v1083 = RtlULongLongAdd(v1107, 4, &v1289);
                                            if ( v1083 < 0 )
                                              goto LABEL_1340;
                                            LODWORD(v1293) = (_DWORD)v995;
                                            v1277 = 4;
                                            v1083 = RtlUIntAdd(4, v1322, &v1277);
                                            if ( v1083 < 0 )
                                              goto LABEL_1340;
                                            v1083 = RtlUIntAdd((unsigned int)v1277, v1111, &v1277);
                                            if ( v1083 < 0 )
                                              goto LABEL_1340;
                                            v1083 = RtlUIntAdd((unsigned int)v1277, (unsigned int)v1282, &v1277);
                                            if ( v1083 < 0 )
                                              goto LABEL_1340;
                                            v1083 = RtlUIntAdd((unsigned int)v1277, 4, &v1277);
                                            if ( v1083 < 0 )
                                              goto LABEL_1340;
                                            v1083 = RtlUIntAdd((unsigned int)v1277, v1112, &v1277);
                                            if ( v1083 < 0 )
                                              goto LABEL_1340;
                                            LODWORD(v1293) = v1277;
                                            if ( (unsigned int)v1277 > 0x400000 )
                                            {
                                              v1083 = -2147418113;
                                              goto LABEL_1340;
                                            }
                                            v1113 = v1277;
                                            v1114 = GetProcessHeap();
                                            v1115 = (unsigned int *)HeapAlloc(v1114, 8u, v1113);
                                            LODWORD(v995) = 0;
                                            v1006 = v1115;
                                            if ( !v1115 )
                                            {
                                              LODWORD(v1285) = -805306345;
                                              v1006 = 0;
LABEL_1382:
                                              v1005 = (unsigned int *)v1290;
                                              goto LABEL_1383;
                                            }
                                            hModule = 0;
                                            v1331 = 0;
                                            v1332 = 0;
                                            if ( !v1302 )
                                            {
                                              LODWORD(v1285) = -2147024809;
                                              goto LABEL_1382;
                                            }
                                            LODWORD(v1332) = v1276;
                                            *(_QWORD *)&v1331 = v1302;
                                            *(_QWORD *)((char *)&v1332 + 4) = (unsigned int)v1293;
                                            *((_QWORD *)&v1331 + 1) = v1115;
                                            if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                              && (ProcAddress = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                            {
                                              v1116 = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(
                                                        134,
                                                        &v1331)
                                                    | 0x10000000;
                                              if ( v1116 >= 0 )
                                              {
                                                v1119 = DWORD1(v1332);
                                                LODWORD(v995) = 0;
                                                goto LABEL_1386;
                                              }
                                              LODWORD(v995) = 0;
                                            }
                                            else
                                            {
                                              v1116 = GetLastError();
                                              LODWORD(v995) = 0;
                                              v1117 = v1116 < 0;
                                              if ( v1116 > 0 )
                                              {
                                                v1116 = (unsigned __int16)v1116 | 0x80070000;
                                                v1117 = v1116 < 0;
                                              }
                                              if ( !v1117 )
                                              {
                                                LODWORD(v1285) = -2147467259;
                                                goto LABEL_1382;
                                              }
                                            }
                                            if ( v1116 == -805306333 )
                                            {
                                              LODWORD(v1285) = -2147024774;
                                              goto LABEL_1382;
                                            }
                                            if ( v1116 < 0 )
                                            {
                                              LODWORD(v1285) = v1116;
                                              goto LABEL_1382;
                                            }
                                            v1119 = (unsigned int)v1293;
LABEL_1386:
                                            HIDWORD(dwBytes) = 0;
                                            v1293 = v1006;
                                            if ( v1119 < 4 )
                                            {
LABEL_1387:
                                              LODWORD(v1285) = -805306306;
                                              goto LABEL_1382;
                                            }
                                            v1121 = (const wchar_t *)*v1006;
                                            LODWORD(v1282) = *v1006;
                                            v1122 = RtlULongLongAdd(v1006, 4, &v1293);
                                            if ( v1122 >= 0 )
                                            {
                                              v1122 = RtlUIntAdd(0, 4, (char *)&dwBytes + 4);
                                              if ( v1122 >= 0 )
                                              {
                                                if ( v1123 - HIDWORD(dwBytes) < (unsigned int)v1121 )
                                                  goto LABEL_1387;
                                                pcchLength = (size_t)v1293;
                                                psz = v1121;
                                                v1122 = RtlULongLongAdd(v1293, (unsigned int)v1121, &v1293);
                                                if ( v1122 >= 0 )
                                                {
                                                  v1122 = RtlUIntAdd(
                                                            HIDWORD(dwBytes),
                                                            (unsigned int)v1121,
                                                            (char *)&dwBytes + 4);
                                                  if ( v1122 >= 0 )
                                                  {
                                                    if ( (unsigned int)(v1124 - HIDWORD(dwBytes)) < 4 )
                                                      goto LABEL_1387;
                                                    LODWORD(v1292) = *(_DWORD *)v1293;
                                                    v1122 = RtlULongLongAdd(v1293, 4, &v1293);
                                                    if ( v1122 >= 0 )
                                                    {
                                                      v1122 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                                      if ( v1122 >= 0 )
                                                      {
                                                        if ( v1125 - HIDWORD(dwBytes) < (unsigned int)v1126 )
                                                        {
LABEL_1397:
                                                          v1005 = (unsigned int *)v1290;
                                                          LODWORD(v995) = 0;
                                                          v1120 = v1288;
                                                          LODWORD(v1285) = -805306306;
                                                          goto LABEL_1524;
                                                        }
                                                        Size = (SIZE_T)v1293;
                                                        v1291 = v1126;
                                                        v1122 = RtlULongLongAdd(v1293, v1126, &v1293);
                                                        if ( v1122 >= 0 )
                                                        {
                                                          v1122 = RtlUIntAdd(
                                                                    HIDWORD(dwBytes),
                                                                    v1127,
                                                                    (char *)&dwBytes + 4);
                                                          if ( v1122 >= 0 )
                                                          {
                                                            if ( (unsigned int)(v1128 - HIDWORD(dwBytes)) < 4 )
                                                              goto LABEL_1397;
                                                            v1276 = *(_DWORD *)v1293;
                                                            v1122 = RtlULongLongAdd(v1293, 4, &v1293);
                                                            if ( v1122 >= 0 )
                                                            {
                                                              v1122 = RtlUIntAdd(
                                                                        HIDWORD(dwBytes),
                                                                        4,
                                                                        (char *)&dwBytes + 4);
                                                              if ( v1122 >= 0 )
                                                              {
                                                                if ( v1129 - HIDWORD(dwBytes) < v1130 )
                                                                  goto LABEL_1397;
                                                                v1122 = RtlUIntAdd(
                                                                          HIDWORD(dwBytes),
                                                                          v1130,
                                                                          (char *)&dwBytes + 4);
                                                                if ( v1122 >= 0 )
                                                                {
                                                                  if ( v1131 != HIDWORD(dwBytes)
                                                                    || (unsigned int)(v1132 + v1133 + (_DWORD)v1121)
                                                                     + 12LL != v1131 )
                                                                  {
                                                                    goto LABEL_1397;
                                                                  }
                                                                  v1134 = GetProcessHeap();
                                                                  v1135 = HeapAlloc(v1134, 8u, 0x30u);
                                                                  v1005 = (unsigned int *)v1290;
                                                                  LODWORD(v995) = 0;
                                                                  v1279 = (SIZE_T)v1135;
                                                                  v1136 = (SIZE_T)v1135;
                                                                  if ( !v1135 )
                                                                  {
                                                                    v1296 = 0;
                                                                    goto LABEL_1322;
                                                                  }
                                                                  v1280 = v936;
                                                                  v1294 = v932;
                                                                  v1283 = v1062;
                                                                  v1284 = 0;
                                                                  if ( pcchLength )
                                                                  {
                                                                    *(_DWORD *)v1135 = (_DWORD)v1282;
                                                                    v1137 = GetProcessHeap();
                                                                    v1138 = HeapAlloc(v1137, 8u, (SIZE_T)psz);
                                                                    v1139 = v1279;
                                                                    if ( !v1138 )
                                                                    {
LABEL_1420:
                                                                      v1145 = *(void **)(v1139 + 8);
                                                                      v1277 = -1073741801;
                                                                      v1293 = v1006;
                                                                      v1300 = v1145;
                                                                      if ( v1145 )
                                                                      {
                                                                        v1146 = GetProcessHeap();
                                                                        HeapFree(v1146, 0, v1300);
                                                                        v1139 = v1279;
                                                                        *(_QWORD *)(v1279 + 8) = 0;
                                                                      }
                                                                      v1300 = *(LPVOID *)(v1139 + 24);
                                                                      if ( v1300 )
                                                                      {
                                                                        v1147 = GetProcessHeap();
                                                                        HeapFree(v1147, 0, v1300);
                                                                        v1139 = v1279;
                                                                        *(_QWORD *)(v1279 + 24) = 0;
                                                                      }
                                                                      v1300 = *(LPVOID *)(v1139 + 40);
                                                                      if ( v1300 )
                                                                      {
                                                                        v1148 = GetProcessHeap();
                                                                        HeapFree(v1148, 0, v1300);
                                                                        *(_QWORD *)(v1279 + 40) = 0;
                                                                      }
                                                                      v1149 = GetProcessHeap();
                                                                      HeapFree(v1149, 0, (LPVOID)v1279);
                                                                      v1150 = (LPVOID *)v1284;
                                                                      LODWORD(v995) = 0;
                                                                      goto LABEL_1430;
                                                                    }
                                                                    *(_QWORD *)(v1279 + 8) = v1138;
                                                                    v1277 = 0;
                                                                    memcpy_0(
                                                                      v1138,
                                                                      (const void *)pcchLength,
                                                                      (size_t)psz);
                                                                    v1136 = v1279;
                                                                    LODWORD(v995) = 0;
                                                                  }
                                                                  else
                                                                  {
                                                                    *(_DWORD *)v1135 = 0;
                                                                    v1135[1] = 0;
                                                                    v1277 = 0;
                                                                  }
                                                                  if ( Size )
                                                                  {
                                                                    *(_DWORD *)(v1136 + 16) = v1292;
                                                                    v1140 = GetProcessHeap();
                                                                    v1141 = HeapAlloc(v1140, 8u, v1291);
                                                                    v1139 = v1279;
                                                                    if ( !v1141 )
                                                                    {
LABEL_1419:
                                                                      v1280 = v936;
                                                                      v1294 = v932;
                                                                      v1283 = v1062;
                                                                      v1290 = v1005;
                                                                      v1279 = v1139;
                                                                      goto LABEL_1420;
                                                                    }
                                                                    *(_QWORD *)(v1279 + 24) = v1141;
                                                                    v1277 = 0;
                                                                    memcpy_0(v1141, (const void *)Size, v1291);
                                                                    v1136 = v1279;
                                                                    LODWORD(v995) = 0;
                                                                  }
                                                                  else
                                                                  {
                                                                    *(_DWORD *)(v1136 + 16) = 0;
                                                                    *(_QWORD *)(v1136 + 24) = 0;
                                                                  }
                                                                  if ( v1293 )
                                                                  {
                                                                    v1142 = (const wchar_t *)v1276;
                                                                    *(_DWORD *)(v1136 + 32) = v1276;
                                                                    psz = v1142;
                                                                    v1143 = GetProcessHeap();
                                                                    v1144 = HeapAlloc(v1143, 8u, (SIZE_T)psz);
                                                                    v1139 = v1279;
                                                                    if ( !v1144 )
                                                                      goto LABEL_1419;
                                                                    *(_QWORD *)(v1279 + 40) = v1144;
                                                                    v1277 = 0;
                                                                    memcpy_0(v1144, v1293, (size_t)psz);
                                                                    v1136 = v1279;
                                                                    LODWORD(v995) = 0;
                                                                  }
                                                                  else
                                                                  {
                                                                    *(_DWORD *)(v1136 + 32) = 0;
                                                                    *(_QWORD *)(v1136 + 40) = 0;
                                                                  }
                                                                  v1150 = (LPVOID *)v1136;
                                                                  v1284 = (LPVOID)v1136;
                                                                  v1293 = v1006;
                                                                  v1290 = v1005;
                                                                  v1283 = v1062;
                                                                  v1294 = v932;
                                                                  v1280 = v936;
LABEL_1430:
                                                                  v1122 = v1277;
                                                                  if ( v1277 < 0 )
                                                                  {
                                                                    v1151 = 0;
                                                                    v1296 = 0;
                                                                    if ( v1150 )
                                                                    {
                                                                      v1300 = v1150[1];
                                                                      if ( v1300 )
                                                                      {
                                                                        v1152 = GetProcessHeap();
                                                                        HeapFree(v1152, 0, v1300);
                                                                        v1150 = (LPVOID *)v1284;
                                                                        *((_QWORD *)v1284 + 1) = 0;
                                                                      }
                                                                      v1300 = v1150[3];
                                                                      if ( v1300 )
                                                                      {
                                                                        v1153 = GetProcessHeap();
                                                                        HeapFree(v1153, 0, v1300);
                                                                        v1150 = (LPVOID *)v1284;
                                                                        *((_QWORD *)v1284 + 3) = 0;
                                                                      }
                                                                      v1300 = v1150[5];
                                                                      if ( v1300 )
                                                                      {
                                                                        v1154 = GetProcessHeap();
                                                                        HeapFree(v1154, 0, v1300);
                                                                        *((_QWORD *)v1284 + 5) = 0;
                                                                      }
                                                                      v1155 = GetProcessHeap();
                                                                      HeapFree(v1155, 0, v1284);
                                                                      v1122 = v1277;
                                                                      LODWORD(v995) = 0;
                                                                      v1151 = 0;
                                                                      v1296 = 0;
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    v1151 = (unsigned int *)v1150;
                                                                    v1296 = v1150;
                                                                  }
LABEL_1442:
                                                                  LODWORD(v1285) = v1122 | 0x10000000;
                                                                  if ( v1122 < 0 )
                                                                    goto LABEL_1383;
                                                                  if ( !v1151
                                                                    || (Size = *((_QWORD *)v1151 + 1)) == 0
                                                                    || *v1151 == (_DWORD)v995 )
                                                                  {
                                                                    v1120 = v1288;
                                                                    LODWORD(v1285) = -805306355;
LABEL_1475:
                                                                    v1005 = (unsigned int *)v1290;
                                                                    goto LABEL_1524;
                                                                  }
                                                                  v1289 = *v1151 - 8LL;
                                                                  v1156 = MemoryAlloc(v1289);
                                                                  LODWORD(v995) = 0;
                                                                  v1288 = v1156;
                                                                  v1157 = v1156;
                                                                  if ( !v1156 )
                                                                  {
LABEL_1474:
                                                                    LODWORD(v1285) = -805306367;
                                                                    v1120 = 0;
                                                                    goto LABEL_1475;
                                                                  }
                                                                  v1158 = v1289;
                                                                  v1159 = 0;
                                                                  v1160 = (unsigned __int8 *)Size;
                                                                  v1278 = 0;
                                                                  psz = (STRSAFE_PCNZWCH)(v1289 & 7);
                                                                  v1292 = 0x7F1137FAB69605ELL;
                                                                  pcchLength = Size;
                                                                  v1291 = (SIZE_T)v1157;
                                                                  if ( (v1289 & 7) != 0 )
                                                                  {
                                                                    v1305 = 0;
                                                                    LODWORD(v1297) = 0;
                                                                    LODWORD(v1282) = 0;
                                                                    v1161 = 0;
                                                                    v1162 = 0;
                                                                    v1163 = 0;
                                                                    do
                                                                    {
                                                                      v1164 = *v1160++;
                                                                      v1277 = v1164;
                                                                      v1276 = 8 * v1161;
                                                                      if ( (unsigned int)v1161 >= 4 )
                                                                      {
                                                                        v1277 <<= 56 - v1276;
                                                                        v1163 |= v1277;
                                                                      }
                                                                      else
                                                                      {
                                                                        v1277 <<= 24 - v1276;
                                                                        v1162 |= v1277;
                                                                      }
                                                                      ++v1161;
                                                                    }
                                                                    while ( v1161 < (int)psz );
                                                                    v83 = dwBytes;
                                                                    v1165 = v1157;
                                                                    LODWORD(v1297) = v1162;
                                                                    v1166 = v1162;
                                                                    v1159 = v1278;
                                                                    v1305 = v1163;
                                                                    v1158 = v1289;
                                                                    v1167 = (unsigned int)psz;
                                                                    pcchLength = (size_t)v1160;
                                                                    v1293 = v1006;
                                                                    v1290 = v1005;
                                                                    v1283 = v1062;
                                                                    v1294 = v932;
                                                                    v1280 = v936;
                                                                    v1168 = v1166 ^ 0x92F65A5;
                                                                    LODWORD(v1282) = 0;
                                                                    v1169 = v1305 ^ 0x699A899C;
                                                                    v1170 = v1168;
                                                                    if ( (_DWORD)psz )
                                                                    {
                                                                      v1171 = (unsigned int)v1282;
                                                                      v1172 = v1305 ^ 0x699A899C;
                                                                      do
                                                                      {
                                                                        v1300 = v1165 + 1;
                                                                        if ( v1171 >= 4 )
                                                                        {
                                                                          v1172 = __ROR4__(v1172, 24);
                                                                          v1173 = v1172;
                                                                        }
                                                                        else
                                                                        {
                                                                          v1170 = __ROR4__(v1170, 24);
                                                                          v1173 = v1170;
                                                                        }
                                                                        *v1165 = v1173;
                                                                        ++v1171;
                                                                        v1165 = v1300;
                                                                      }
                                                                      while ( (int)v1171 < (int)v1167 );
                                                                      v1159 = v1278;
                                                                      v1158 = v1289;
                                                                      v1291 = (SIZE_T)v1300;
                                                                      v1157 = v1288;
                                                                    }
                                                                    if ( v1167 <= 4 )
                                                                    {
                                                                      v1174 = 0;
                                                                      if ( v1167 < 4 )
                                                                        v1168 = v1168 >> (8 * (4 - v1167)) << (8 * (4 - v1167));
                                                                    }
                                                                    else
                                                                    {
                                                                      v1174 = v1169 >> (8 * (8 - v1167)) << (8 * (8 - v1167));
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    LODWORD(v1297) = 0;
                                                                    v1174 = 0;
                                                                    v1168 = 0;
                                                                  }
                                                                  if ( v1158 >> 3 )
                                                                  {
                                                                    v1175 = HIDWORD(v1292);
                                                                    v1176 = v1158 >> 3;
                                                                    v1177 = (_BYTE *)v1291;
                                                                    v1178 = v1297;
                                                                    v1179 = WORD2(v1292);
                                                                    v1277 = 24670;
                                                                    v1180 = (unsigned __int8 *)pcchLength;
                                                                    v1276 = WORD2(v1292);
                                                                    psz = 0;
                                                                    do
                                                                    {
                                                                      v1181 = *v1180;
                                                                      v1182 = v1180[1];
                                                                      v1183 = v1180[4];
                                                                      v1180 += 8;
                                                                      v1184 = *(v1180 - 5)
                                                                            | ((*(v1180 - 6)
                                                                              | (((v1181 << 8) | v1182) << 8)) << 8);
                                                                      v1185 = v1168 ^ v1184;
                                                                      v1186 = *(v1180 - 1)
                                                                            | ((*(v1180 - 2)
                                                                              | ((*(v1180 - 3) | (v1183 << 8)) << 8)) << 8);
                                                                      v1187 = v1175
                                                                            ^ v1168
                                                                            ^ v1184
                                                                            ^ v1174
                                                                            ^ v1186
                                                                            ^ 0xAB69605E;
                                                                      v1188 = v1185
                                                                            ^ (__ROR4__(v1187, 22)
                                                                             + v1179 * __ROR4__(v1187 + 1419157410, 27));
                                                                      v1189 = v1187
                                                                            ^ (WORD1(v1292) * __ROR4__(v1175 + v1188, 9)
                                                                             - __ROR4__(v1188, 30));
                                                                      v1190 = v1188
                                                                            ^ (v1277 * (v1189 - v1179) - (v1189 >> 13));
                                                                      v1191 = v1189
                                                                            ^ (HIWORD(v1292)
                                                                             * __ROR4__(v1190 ^ WORD1(v1292), 26)
                                                                             - __ROR4__(v1190, 30));
                                                                      v1192 = v1190 ^ (v1175 - (v1191 ^ 0xAB69605E));
                                                                      v1193 = v1191
                                                                            ^ (WORD1(v1292) * (v1179 ^ v1192))
                                                                            ^ __ROR4__(v1192, 6);
                                                                      v1194 = v1192
                                                                            ^ (__ROR4__(v1193, 30)
                                                                             + v1277 * __ROR4__(v1175 + v1193, 15));
                                                                      v1195 = v1193
                                                                            ^ (HIWORD(v1292)
                                                                             * __ROR4__(v1194 + 1419157410, 14)
                                                                             - __ROR4__(v1194, 24));
                                                                      v1196 = v1194
                                                                            ^ __ROR4__(v1195, 10)
                                                                            ^ (v1276 * __ROR4__(v1195 ^ 0xAB69605E, 12));
                                                                      v1197 = v1195
                                                                            ^ (v1196 >> 10)
                                                                            ^ (WORD1(v1292) * (HIWORD(v1292) ^ v1196));
                                                                      v1198 = v1196
                                                                            ^ (HIWORD(v1292)
                                                                             * (v1277 + __ROR4__(~v1197, 5)));
                                                                      v1199 = v1197
                                                                            ^ (v1198 - HIWORD(v1292))
                                                                            ^ 0xAB69605E;
                                                                      v1179 = v1276;
                                                                      v1200 = v1198
                                                                            ^ ((v1199 >> 2)
                                                                             + v1276
                                                                             * __ROR4__(HIWORD(v1292) ^ v1199, 30));
                                                                      v1201 = v1199
                                                                            ^ (__ROR4__(v1200, 25)
                                                                             + WORD1(v1292) * __ROR4__(v1200 - v1175, 6));
                                                                      v1202 = v1200
                                                                            ^ (v1277 * (v1276 ^ v1201)
                                                                             + __ROR4__(v1201, 9));
                                                                      v1203 = v1201
                                                                            ^ (__ROR4__(v1202, 25)
                                                                             + HIWORD(v1292)
                                                                             * __ROR4__(v1202 ^ WORD1(v1292), 27));
                                                                      v1204 = v1202 ^ v1203 ^ v1175 ^ 0xAB69605E;
                                                                      v1205 = v1203
                                                                            ^ (v1276
                                                                             * (__ROR4__(v1204, 3) - WORD1(v1292)));
                                                                      v1206 = v1204
                                                                            ^ (v1277 * __ROR4__(v1205 - v1175, 1)
                                                                             - __ROR4__(v1205, 6));
                                                                      v1207 = v1205
                                                                            ^ (__ROR4__(v1206, 18)
                                                                             + HIWORD(v1292)
                                                                             * __ROR4__(v1206 - 1419157410, 29));
                                                                      v1208 = v1206
                                                                            ^ (v1276 * __ROR4__(v1207 - 1419157410, 17)
                                                                             - __ROR4__(v1207, 14));
                                                                      v1209 = v1305;
                                                                      v1305 = v1186;
                                                                      v1210 = v1207
                                                                            ^ (v1208 >> 3)
                                                                            ^ (WORD1(v1292) * (v1208 ^ v1277));
                                                                      v1174 = v1210 ^ v1209;
                                                                      v1211 = v1178
                                                                            ^ __ROR4__(v1210, 30)
                                                                            ^ (v1277 * __ROR4__(v1210 ^ v1175, 28));
                                                                      v1178 = v1184;
                                                                      v1168 = v1208 ^ v1211;
                                                                      v1177[3] = v1168;
                                                                      v1177[7] = v1174;
                                                                      v1177[2] = __ROR4__(v1168, 8);
                                                                      v1177[6] = __ROR4__(v1174, 8);
                                                                      v1177[1] = __ROR4__(v1168, 16);
                                                                      v1177[5] = __ROR4__(v1174, 16);
                                                                      *v1177 = __ROR4__(v1168, 24);
                                                                      v1177[4] = __ROR4__(v1174, 24);
                                                                      v1177 += 8;
                                                                      psz = (STRSAFE_PCNZWCH)((char *)psz + 1);
                                                                    }
                                                                    while ( (unsigned __int64)psz < v1176 );
                                                                    v1159 = v1278;
                                                                    v83 = dwBytes;
                                                                    v936 = v1280;
                                                                    v932 = v1294;
                                                                    v1006 = (unsigned int *)v1293;
                                                                    v1062 = v1283;
                                                                    v1157 = v1288;
                                                                    v1158 = v1289;
                                                                  }
                                                                  LODWORD(v995) = 0;
                                                                  for ( jj = 0; jj < v1158; ++jj )
                                                                    v1159 ^= v1157[jj];
                                                                  if ( v1159 != *(_QWORD *)(v1158 + Size) )
                                                                  {
                                                                    MemoryFree(v1157);
                                                                    LODWORD(v995) = 0;
                                                                    goto LABEL_1474;
                                                                  }
                                                                  v1213 = v1296;
                                                                  v1005 = (unsigned int *)v1290;
                                                                  v1283 = v1062;
                                                                  v1305 = 0;
                                                                  v1289 = (size_t)v1157;
                                                                  if ( (unsigned int)v1158 < 4 )
                                                                  {
LABEL_1477:
                                                                    v1214 = -1073741762;
LABEL_1488:
                                                                    v1120 = v1288;
                                                                    v1004 = v1214 | 0x10000000;
LABEL_1523:
                                                                    LODWORD(v1285) = v1004;
LABEL_1524:
                                                                    v1235 = v1283;
                                                                    if ( !v1283 )
                                                                    {
LABEL_1526:
                                                                      if ( v1005 )
                                                                      {
                                                                        v1237 = (void *)*((_QWORD *)v1005 + 1);
                                                                        if ( v1237 )
                                                                        {
                                                                          v1238 = GetProcessHeap();
                                                                          HeapFree(v1238, 0, v1237);
                                                                          *((_QWORD *)v1005 + 1) = 0;
                                                                        }
                                                                        v1239 = (void *)*((_QWORD *)v1005 + 3);
                                                                        if ( v1239 )
                                                                        {
                                                                          v1240 = GetProcessHeap();
                                                                          HeapFree(v1240, 0, v1239);
                                                                          *((_QWORD *)v1005 + 3) = 0;
                                                                        }
                                                                        v1241 = (void *)*((_QWORD *)v1005 + 5);
                                                                        if ( v1241 )
                                                                        {
                                                                          v1242 = GetProcessHeap();
                                                                          HeapFree(v1242, 0, v1241);
                                                                          *((_QWORD *)v1005 + 5) = 0;
                                                                        }
                                                                        v1243 = GetProcessHeap();
                                                                        HeapFree(v1243, 0, v1005);
                                                                        LODWORD(v995) = 0;
                                                                      }
                                                                      v1244 = (void *)v1302;
                                                                      if ( v1302 )
                                                                      {
                                                                        v1245 = GetProcessHeap();
                                                                        HeapFree(v1245, 0, v1244);
                                                                        LODWORD(v995) = 0;
                                                                      }
                                                                      if ( v1006 )
                                                                      {
                                                                        v1246 = GetProcessHeap();
                                                                        HeapFree(v1246, 0, v1006);
                                                                        LODWORD(v995) = 0;
                                                                      }
                                                                      v1247 = v1296;
                                                                      if ( v1296 )
                                                                      {
                                                                        v1248 = (void *)*((_QWORD *)v1296 + 1);
                                                                        if ( v1248 )
                                                                        {
                                                                          v1249 = GetProcessHeap();
                                                                          HeapFree(v1249, 0, v1248);
                                                                          v1247[1] = 0;
                                                                        }
                                                                        v1250 = (void *)v1247[3];
                                                                        if ( v1250 )
                                                                        {
                                                                          v1251 = GetProcessHeap();
                                                                          HeapFree(v1251, 0, v1250);
                                                                          v1247[3] = 0;
                                                                        }
                                                                        v1252 = (void *)v1247[5];
                                                                        if ( v1252 )
                                                                        {
                                                                          v1253 = GetProcessHeap();
                                                                          HeapFree(v1253, 0, v1252);
                                                                          v1247[5] = 0;
                                                                        }
                                                                        v1254 = GetProcessHeap();
                                                                        HeapFree(v1254, 0, v1247);
                                                                        LODWORD(v995) = 0;
                                                                      }
                                                                      if ( v1120 )
                                                                      {
                                                                        v1255 = GetProcessHeap();
                                                                        HeapFree(v1255, 0, v1120);
                                                                        LODWORD(v995) = 0;
                                                                      }
LABEL_1548:
                                                                      if ( (int)v1285 >= (int)v995 )
                                                                      {
                                                                        v933 = v1281;
                                                                        if ( (_DWORD)v1303 )
                                                                        {
                                                                          if ( v1281 )
                                                                          {
                                                                            psz = (STRSAFE_PCNZWCH)v1281;
                                                                            if ( (int)RtlULongLongAdd(v1281, 4, &psz) >= 0 )
                                                                            {
                                                                              v1259 = psz;
                                                                              if ( *v933 == (_DWORD)v1258 )
                                                                                v1259 = v1258;
                                                                              if ( *v933 == v1257
                                                                                && *(_DWORD *)v1259 >= (int)v1258
                                                                                && v1256 > 1 )
                                                                              {
                                                                                v1260 = (size_t)v933;
                                                                                v1261 = (int)v1258;
                                                                                v1289 = (size_t)v933;
                                                                                v1262 = v1257;
                                                                                while ( !v1261 )
                                                                                {
                                                                                  if ( (int)RtlULongLongAdd(
                                                                                              v1260,
                                                                                              v1262,
                                                                                              &v1289) < 0
                                                                                    || (int)RtlULongLongAdd(
                                                                                              v1289,
                                                                                              v1263,
                                                                                              &v1289) < 0 )
                                                                                  {
                                                                                    goto LABEL_1565;
                                                                                  }
                                                                                  v1260 = v1289;
                                                                                  v1261 = v1264 + 1;
                                                                                }
                                                                                RtlULongLongAdd(v1260, v1262, &v1289);
                                                                              }
                                                                            }
                                                                          }
                                                                        }
                                                                        goto LABEL_1565;
                                                                      }
                                                                      goto LABEL_1564;
                                                                    }
LABEL_1525:
                                                                    v1236 = GetProcessHeap();
                                                                    HeapFree(v1236, 0, v1235);
                                                                    LODWORD(v995) = 0;
                                                                    goto LABEL_1526;
                                                                  }
                                                                  v1214 = RtlULongLongAdd(v1157, 4, &v1289);
                                                                  if ( v1214 < 0
                                                                    || (v1214 = RtlUIntAdd(0, 4, &v1305), v1214 < 0) )
                                                                  {
LABEL_1487:
                                                                    v1288 = v1215;
                                                                    v1283 = v1062;
                                                                    v1296 = v1213;
                                                                    goto LABEL_1488;
                                                                  }
                                                                  if ( v1216 - v1305 < 4 )
                                                                  {
                                                                    v1214 = -1073741762;
                                                                    goto LABEL_1487;
                                                                  }
                                                                  LODWORD(v1282) = *(_DWORD *)v1289;
                                                                  v1214 = RtlULongLongAdd(v1289, 4, &v1289);
                                                                  if ( v1214 >= 0 )
                                                                  {
                                                                    v1214 = RtlUIntAdd(v1305, 4, &v1305);
                                                                    if ( v1214 >= 0 )
                                                                    {
                                                                      if ( v1217 - v1305 >= v1218 )
                                                                      {
                                                                        v1214 = RtlUIntAdd(v1305, v1218, &v1305);
                                                                        if ( v1214 < 0 )
                                                                          goto LABEL_1486;
                                                                        v1221 = v1220;
                                                                        pcchLength = v1220;
                                                                        v1222 = (const void *)v1289;
                                                                        if ( (unsigned __int64)v1215 + v1219 >= v1221 + v1289
                                                                          && (unsigned __int64)v1215
                                                                           + v1219
                                                                           - v1221
                                                                           - v1289 < 8 )
                                                                        {
                                                                          LODWORD(v1292) = *v1215;
                                                                          psz = 0;
                                                                          v1291 = 0;
                                                                          Size = 0;
                                                                          LODWORD(v1279) = 0;
                                                                          if ( v1289 )
                                                                          {
                                                                            v1214 = RtlULongLongAdd(
                                                                                      v1289,
                                                                                      pcchLength,
                                                                                      &psz);
                                                                            LODWORD(v1285) = v1214;
                                                                            v1288 = v1224;
                                                                            v1296 = v1213;
                                                                            v1283 = v1062;
                                                                            if ( v1214 < 0 )
                                                                            {
LABEL_1515:
                                                                              v1234 = (int)v1303;
LABEL_1516:
                                                                              LODWORD(v995) = 0;
                                                                              if ( v1214 < 0 || (_DWORD)v1292 == v1234 )
                                                                                goto LABEL_1488;
                                                                              goto LABEL_1477;
                                                                            }
                                                                            v1225 = psz;
                                                                            while ( v1223 < (unsigned __int64)v1225 )
                                                                            {
                                                                              v1214 = RtlULongLongAdd(v1223, 4, &v1291);
                                                                              if ( v1214 < 0 )
                                                                                goto LABEL_1515;
                                                                              if ( v1291 > v1226 )
                                                                                goto LABEL_1502;
                                                                              v1228 = *v1227;
                                                                              v1276 = 0;
                                                                              v1214 = RtlUIntAdd(4, v1228, &v1276);
                                                                              if ( v1214 < 0 )
                                                                                goto LABEL_1503;
                                                                              v1214 = RtlULongLongAdd(
                                                                                        v1229,
                                                                                        v1276,
                                                                                        &Size);
                                                                              LODWORD(v1285) = v1214;
                                                                              if ( v1214 < 0 )
                                                                                goto LABEL_1515;
                                                                              v1223 = Size;
                                                                              if ( Size > (unsigned __int64)v1225 )
                                                                                goto LABEL_1502;
                                                                              LODWORD(v1279) = v1279 + 1;
                                                                            }
                                                                            if ( (STRSAFE_PCNZWCH)v1223 != v1225 )
                                                                            {
LABEL_1502:
                                                                              v1214 = -1073741811;
LABEL_1503:
                                                                              LODWORD(v995) = 0;
                                                                              goto LABEL_1488;
                                                                            }
                                                                          }
                                                                          else
                                                                          {
                                                                            v1214 = 0;
                                                                            LODWORD(v1285) = 0;
                                                                            v1288 = v1215;
                                                                            v1296 = v1213;
                                                                            v1283 = v1062;
                                                                          }
                                                                          v1230 = 0;
                                                                          if ( (_DWORD)v1282 )
                                                                          {
                                                                            v1231 = GetProcessHeap();
                                                                            v1232 = pcchLength;
                                                                            v1233 = HeapAlloc(v1231, 8u, pcchLength);
                                                                            LODWORD(v995) = 0;
                                                                            v1230 = v1233;
                                                                            if ( !v1233 )
                                                                            {
                                                                              v1214 = -1073741801;
                                                                              goto LABEL_1488;
                                                                            }
                                                                            v1214 = 0;
                                                                            v1222 = (const void *)v1289;
                                                                            LODWORD(v1285) = 0;
                                                                          }
                                                                          else
                                                                          {
                                                                            v1232 = pcchLength;
                                                                          }
                                                                          if ( v1222 )
                                                                          {
                                                                            memcpy_0(v1230, v1222, v1232);
                                                                            v1214 = v1285;
                                                                          }
                                                                          v1234 = v1279;
                                                                          LODWORD(v1303) = v1279;
                                                                          v1281 = v1230;
                                                                          goto LABEL_1516;
                                                                        }
                                                                      }
                                                                      v1214 = -1073741762;
                                                                    }
                                                                  }
LABEL_1486:
                                                                  LODWORD(v995) = 0;
                                                                  goto LABEL_1487;
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                    LODWORD(v995) = 0;
                                                  }
                                                }
                                              }
                                            }
                                            v1005 = (unsigned int *)v1290;
                                            v1151 = (unsigned int *)v1296;
                                            v1293 = v1006;
                                            goto LABEL_1442;
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                                v1283 = v1062;
                                v1099 = GetProcessHeap();
                                HeapFree(v1099, 0, v1294);
                                LODWORD(v995) = 0;
                              }
                              v1098 = v1277;
                              goto LABEL_1336;
                            }
LABEL_1306:
                            v1005 = (unsigned int *)v1304;
                            v1304 = 0;
                            goto LABEL_1307;
                          }
                        }
                      }
                    }
                  }
LABEL_1564:
                  v933 = v1281;
                  goto LABEL_1565;
                }
                v1284 = (LPVOID)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860F8[0])(0, 0, 1027);
                if ( !v1284 )
                {
                  GetLastError();
                  goto LABEL_1193;
                }
                v471 = ((__int64 (*)(void))off_180086098[0])();
                v472 = g_WarbirdNotificationInformation;
                g_WarbirdPaintInitTime = v471;
                LODWORD(v1297) = g_WarbirdNotificationInformation;
                memset_0(&v1342, 0, 0x70u);
                memset(v1398, 0, 44);
                v1314 = 0;
                while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
                  ;
                v473 = g_WarbirdSecureFunctionsRefCount;
                if ( !g_WarbirdSecureFunctionsRefCount )
                {
                  v474 = (const wchar_t *)MemoryAlloc(0x338u);
                  psz = v474;
                  if ( !v474 )
                    goto LABEL_600;
                  v475 = qword_180078760;
                  v476 = (wchar_t *)v474;
                  v477 = 0;
                  v478 = -1;
                  v479 = 0;
                  v480 = 0;
                  v481 = 103;
                  do
                  {
                    v482 = *((unsigned __int8 *)v475 + 1);
                    v483 = *(unsigned __int8 *)v475;
                    v484 = *((unsigned __int8 *)v475++ + 4);
                    v485 = *((unsigned __int8 *)v475 - 5)
                         | ((*((unsigned __int8 *)v475 - 6) | ((v482 | (v483 << 8)) << 8)) << 8);
                    v486 = v480 ^ v485;
                    v487 = *((unsigned __int8 *)v475 - 1)
                         | ((*((unsigned __int8 *)v475 - 2) | ((*((unsigned __int8 *)v475 - 3) | (v484 << 8)) << 8)) << 8);
                    v488 = v479 ^ v487 ^ v480 ^ v485 ^ 0xAC987321;
                    v489 = v486 ^ (__ROR4__(v488, 22) + 4991 * __ROR4__(v488 + 1419157410, 27));
                    v490 = v488 ^ (43881 * __ROR4__(v489 + 133239679, 9) - __ROR4__(v489, 30));
                    v491 = v489 ^ (24670 * v490 - (v490 >> 13) - 123127970);
                    v492 = v490 ^ (2033 * __ROR4__(v491 ^ 0xAB69, 26) - __ROR4__(v491, 30));
                    v493 = v491 ^ (133239679 - (v492 ^ 0xAB69605E));
                    v494 = v492 ^ (43881 * (v493 ^ 0x137F)) ^ __ROR4__(v493, 6);
                    v495 = v493 ^ (__ROR4__(v494, 30) + 24670 * __ROR4__(v494 + 133239679, 15));
                    v496 = v494 ^ (2033 * __ROR4__(v495 + 1419157410, 14) - __ROR4__(v495, 24));
                    v497 = v495 ^ __ROR4__(v496, 10) ^ (4991 * __ROR4__(v496 ^ 0xAB69605E, 12));
                    v498 = v496 ^ (v497 >> 10) ^ (43881 * (v497 ^ 0x7F1));
                    v499 = v497 ^ (2033 * (__ROR4__(~v498, 5) + 24670));
                    v500 = v499
                         ^ (((v498 ^ (v499 - 2033) ^ 0xAB69605E) >> 2)
                          + 4991 * __ROR4__(v498 ^ (v499 - 2033) ^ 0xAB6967AF, 30));
                    v501 = v498
                         ^ (v499 - 2033)
                         ^ 0xAB69605E
                         ^ (__ROR4__(v500, 25) + 43881 * __ROR4__(v500 - 133239679, 6));
                    v502 = v500 ^ (24670 * (v501 ^ 0x137F) + __ROR4__(v501, 9));
                    v503 = v501 ^ (__ROR4__(v502, 25) + 2033 * __ROR4__(v502 ^ 0xAB69, 27));
                    v504 = v502 ^ v503 ^ 0xAC987321;
                    v505 = v503 ^ (4991 * __ROR4__(v504, 3) - 219010071);
                    v506 = v504 ^ (24670 * __ROR4__(v505 - 133239679, 1) - __ROR4__(v505, 6));
                    v507 = v505 ^ (__ROR4__(v506, 18) + 2033 * __ROR4__(v506 - 1419157410, 29));
                    v508 = v506 ^ (4991 * __ROR4__(v507 - 1419157410, 17) - __ROR4__(v507, 14));
                    v509 = v507 ^ (v508 >> 3) ^ (43881 * (v508 ^ 0x605E));
                    v510 = __ROR4__(v509, 30);
                    v479 = v478 ^ v509;
                    v478 = v487;
                    v480 = v477
                         ^ v508
                         ^ v510
                         ^ (24670 * __ROR4__(v507 ^ (v508 >> 3) ^ (43881 * (v508 ^ 0x605E)) ^ 0x7F1137F, 28));
                    v477 = v485;
                    *((_BYTE *)v476 + 3) = v480;
                    *((_BYTE *)v476 + 7) = v479;
                    *((_BYTE *)v476 + 2) = __ROR4__(v480, 8);
                    *((_BYTE *)v476 + 6) = __ROR4__(v479, 8);
                    *((_BYTE *)v476 + 1) = __ROR4__(v480, 16);
                    *((_BYTE *)v476 + 5) = __ROR4__(v479, 16);
                    *(_BYTE *)v476 = __ROR4__(v480, 24);
                    *((_BYTE *)v476 + 4) = __ROR4__(v479, 24);
                    v476 += 4;
                    --v481;
                  }
                  while ( v481 );
                  v472 = v1297;
                  v122 = 0;
                  v511 = psz;
                  v512 = 0;
                  v513 = 0;
                  do
                    v513 ^= *((_BYTE *)psz + v512++);
                  while ( v512 < 0x338 );
                  if ( v513 != 64 )
                  {
                    MemoryFree((void *)psz);
LABEL_600:
                    for ( kk = 0; kk != 4; ++kk )
                    {
                      v515 = (HMODULE)*(&WARBIRD::g_arModuleInfo + 3 * kk);
                      if ( v515 )
                        FreeLibrary(v515);
                    }
                    memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
                    memcpy_0(&WARBIRD::g_FuncAddress, off_18006E730, 0x170u);
LABEL_633:
                    _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
                    LODWORD(v1282) = 0;
                    v1294 = 0;
                    v1302 = 0;
                    WORD2(v1282) = 0;
                    while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
                      ;
                    v530 = g_WarbirdSecureFunctionsRefCount;
                    if ( !g_WarbirdSecureFunctionsRefCount )
                    {
                      v531 = (const wchar_t *)MemoryAlloc(0x338u);
                      psz = v531;
                      if ( !v531 )
                        goto LABEL_643;
                      v1278 = 0;
                      v532 = (wchar_t *)v531;
                      v533 = qword_180078760;
                      v534 = 0;
                      v535 = -1;
                      v536 = 0;
                      v537 = 0;
                      v538 = 103;
                      do
                      {
                        v539 = *((unsigned __int8 *)v533 + 1);
                        v540 = *(unsigned __int8 *)v533;
                        v541 = *((unsigned __int8 *)v533++ + 4);
                        v542 = *((unsigned __int8 *)v533 - 5)
                             | ((*((unsigned __int8 *)v533 - 6) | ((v539 | (v540 << 8)) << 8)) << 8);
                        v543 = v537 ^ v542;
                        v544 = *((unsigned __int8 *)v533 - 1)
                             | ((*((unsigned __int8 *)v533 - 2) | ((*((unsigned __int8 *)v533 - 3) | (v541 << 8)) << 8)) << 8);
                        v545 = v537 ^ v542 ^ v536 ^ v544 ^ 0xAC987321;
                        v546 = v543 ^ (__ROR4__(v545, 22) + 4991 * __ROR4__(v545 + 1419157410, 27));
                        v547 = v545 ^ (43881 * __ROR4__(v546 + 133239679, 9) - __ROR4__(v546, 30));
                        v548 = v546 ^ (24670 * v547 - (v547 >> 13) - 123127970);
                        v549 = v547 ^ (2033 * __ROR4__(v548 ^ 0xAB69, 26) - __ROR4__(v548, 30));
                        v550 = v548 ^ (133239679 - (v549 ^ 0xAB69605E));
                        v551 = v549 ^ (43881 * (v550 ^ 0x137F)) ^ __ROR4__(v550, 6);
                        v552 = v550 ^ (__ROR4__(v551, 30) + 24670 * __ROR4__(v551 + 133239679, 15));
                        v553 = v551 ^ (2033 * __ROR4__(v552 + 1419157410, 14) - __ROR4__(v552, 24));
                        v554 = v552 ^ __ROR4__(v553, 10) ^ (4991 * __ROR4__(v553 ^ 0xAB69605E, 12));
                        v555 = v553 ^ (v554 >> 10) ^ (43881 * (v554 ^ 0x7F1));
                        v556 = v554 ^ (2033 * (__ROR4__(~v555, 5) + 24670));
                        v557 = v556
                             ^ (((v555 ^ (v556 - 2033) ^ 0xAB69605E) >> 2)
                              + 4991 * __ROR4__(v555 ^ (v556 - 2033) ^ 0xAB6967AF, 30));
                        v558 = v555
                             ^ (v556 - 2033)
                             ^ 0xAB69605E
                             ^ (__ROR4__(v557, 25) + 43881 * __ROR4__(v557 - 133239679, 6));
                        v559 = v557 ^ (24670 * (v558 ^ 0x137F) + __ROR4__(v558, 9));
                        v560 = v558 ^ (__ROR4__(v559, 25) + 2033 * __ROR4__(v559 ^ 0xAB69, 27));
                        v561 = v559 ^ v560 ^ 0xAC987321;
                        v562 = v560 ^ (4991 * __ROR4__(v561, 3) - 219010071);
                        v563 = v561 ^ (24670 * __ROR4__(v562 - 133239679, 1) - __ROR4__(v562, 6));
                        v564 = v562 ^ (__ROR4__(v563, 18) + 2033 * __ROR4__(v563 - 1419157410, 29));
                        v565 = v563 ^ (4991 * __ROR4__(v564 - 1419157410, 17) - __ROR4__(v564, 14));
                        v566 = v564 ^ (v565 >> 3) ^ (43881 * (v565 ^ 0x605E));
                        v567 = v534 ^ __ROR4__(v566, 30) ^ (24670 * __ROR4__(v566 ^ 0x7F1137F, 28));
                        v534 = v542;
                        v537 = v565 ^ v567;
                        *((_BYTE *)v532 + 3) = v537;
                        v536 = v566 ^ v535;
                        *((_BYTE *)v532 + 7) = v566 ^ v535;
                        v535 = v544;
                        *((_BYTE *)v532 + 2) = __ROR4__(v537, 8);
                        *((_BYTE *)v532 + 6) = __ROR4__(v536, 8);
                        *((_BYTE *)v532 + 1) = __ROR4__(v537, 16);
                        *((_BYTE *)v532 + 5) = __ROR4__(v536, 16);
                        *(_BYTE *)v532 = __ROR4__(v537, 24);
                        *((_BYTE *)v532 + 4) = __ROR4__(v536, 24);
                        v532 += 4;
                        --v538;
                      }
                      while ( v538 );
                      v568 = v1278;
                      v122 = 0;
                      v472 = v1297;
                      v569 = 0;
                      v570 = psz;
                      do
                        v568 ^= *((_BYTE *)psz + v569++);
                      while ( v569 < 0x338 );
                      if ( v568 != 64 )
                      {
                        MemoryFree((void *)psz);
LABEL_643:
                        for ( mm = 0; mm != 4; ++mm )
                        {
                          v572 = (HMODULE)*(&WARBIRD::g_arModuleInfo + 3 * mm);
                          if ( v572 )
                            FreeLibrary(v572);
                        }
                        memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
                        memcpy_0(&WARBIRD::g_FuncAddress, off_18006E730, 0x170u);
LABEL_676:
                        _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
                        memset_0(&v1342, 0, 0x70u);
                        LOWORD(v1282) = (v472 >> 4) & 0xF;
                        WORD1(v1282) = (v472 >> 8) & 0xF;
                        WORD2(v1282) = (v472 >> 12) & 0xF;
                        v1314 = 0;
                        v1280 = (LPVOID)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860F8[0])(0, 0, 1027);
                        v1277 = 0xFFFFFF;
                        if ( !v1280 )
                        {
                          v587 = GetLastError();
                          v588 = v587;
                          if ( v587 > 0 )
                            v588 = (unsigned __int16)v587 | 0x80070000;
                          if ( v588 >= 0 )
                            v588 = -2147467259;
LABEL_889:
                          v707 = 1;
                          while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
                            ;
                          v708 = g_WarbirdSecureFunctionsRefCount;
                          if ( g_WarbirdSecureFunctionsRefCount > 0 )
                          {
                            --g_WarbirdSecureFunctionsRefCount;
                            if ( v708 == 1 )
                            {
                              do
                              {
                                v709 = (HMODULE)*(&WARBIRD::g_arModuleInfo + 3 * v122);
                                if ( v709 )
                                  FreeLibrary(v709);
                                ++v122;
                              }
                              while ( v122 != 4 );
                              memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
                              memcpy_0(&WARBIRD::g_FuncAddress, off_18006E730, 0x170u);
                            }
                          }
                          _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
                          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1302);
                          if ( v588 < 0 )
                          {
LABEL_997:
                            v779 = v1344;
                            if ( v1344 )
                            {
                              v780 = -1;
                              do
                                ++v780;
                              while ( *((_WORD *)v1344 + v780) );
                              for ( nn = 2 * v780 + 2; nn; --nn )
                                *v779++ = 0;
                              MemoryFree(v1344);
                              v1344 = 0;
                            }
                            v782 = v1345;
                            if ( v1345 )
                            {
                              v783 = -1;
                              do
                                ++v783;
                              while ( *((_WORD *)v1345 + v783) );
                              for ( i1 = 2 * v783 + 2; i1; --i1 )
                                *v782++ = 0;
                              MemoryFree(v1345);
                              v1345 = 0;
                            }
                            v785 = v1346;
                            if ( v1346 )
                            {
                              v786 = -1;
                              do
                                ++v786;
                              while ( *((_WORD *)v1346 + v786) );
                              v787 = 2 * v786 + 2;
                              if ( v787 )
                              {
                                do
                                {
                                  *v785++ = 0;
                                  --v787;
                                }
                                while ( v787 );
                                v785 = v1346;
                              }
                              MemoryFree(v785);
                              v1346 = 0;
                            }
                            if ( v1347 )
                            {
                              ((void (*)(void))off_180086038)();
                              v1347 = 0;
                            }
                            if ( v1348 )
                            {
                              ((void (*)(void))off_180086038)();
                              v1348 = 0;
                            }
                            if ( v1349 )
                            {
                              ((void (*)(void))off_180086038)();
                              v1349 = 0;
                            }
                            while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
                              ;
                            v788 = g_WarbirdSecureFunctionsRefCount;
                            if ( g_WarbirdSecureFunctionsRefCount > 0 )
                            {
                              --g_WarbirdSecureFunctionsRefCount;
                              if ( v788 == 1 )
                              {
                                for ( i2 = 0; i2 != 4; ++i2 )
                                {
                                  v790 = (HMODULE)*(&WARBIRD::g_arModuleInfo + 3 * i2);
                                  if ( v790 )
                                    FreeLibrary(v790);
                                }
                                memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
                                memcpy_0(&WARBIRD::g_FuncAddress, off_18006E730, 0x170u);
                              }
                            }
                            _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
                            v791 = g_WarbirdNotificationInformation;
                            v792 = g_WarbirdPaintInitTime;
                            LODWORD(v1281) = g_WarbirdNotificationInformation;
                            v793 = ((unsigned int (*)(void))off_180086098[0])() - v792;
                            pcchLength = v793;
                            v1428 = 0;
                            v1429 = 0;
                            v1432 = 0;
                            v1430 = 0;
                            v1431 = 0;
                            while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
                              ;
                            v871 = g_WarbirdSecureFunctionsRefCount;
                            if ( !g_WarbirdSecureFunctionsRefCount )
                            {
                              v872 = MemoryAlloc(0x338u);
                              v873 = 0;
                              *(_QWORD *)&lpModuleName = v872;
                              if ( !v872 )
                                goto LABEL_1150;
                              v874 = v872;
                              v875 = qword_180078760;
                              v876 = 103;
                              v877 = 0;
                              v878 = -1;
                              v879 = 0;
                              do
                              {
                                v880 = *((unsigned __int8 *)v875 + 1);
                                v881 = *(unsigned __int8 *)v875;
                                v882 = *((unsigned __int8 *)v875++ + 4);
                                v883 = *((unsigned __int8 *)v875 - 5)
                                     | ((*((unsigned __int8 *)v875 - 6) | ((v880 | (v881 << 8)) << 8)) << 8);
                                v884 = v873 ^ v883;
                                v885 = *((unsigned __int8 *)v875 - 1)
                                     | ((*((unsigned __int8 *)v875 - 2)
                                       | ((*((unsigned __int8 *)v875 - 3) | (v882 << 8)) << 8)) << 8);
                                v886 = v879 ^ v885 ^ v873 ^ v883 ^ 0xAC987321;
                                v887 = v884 ^ (__ROR4__(v886, 22) + 4991 * __ROR4__(v886 + 1419157410, 27));
                                v888 = v886 ^ (43881 * __ROR4__(v887 + 133239679, 9) - __ROR4__(v887, 30));
                                v889 = v887 ^ (24670 * v888 - (v888 >> 13) - 123127970);
                                v890 = v888 ^ (2033 * __ROR4__(v889 ^ 0xAB69, 26) - __ROR4__(v889, 30));
                                v891 = v889 ^ (133239679 - (v890 ^ 0xAB69605E));
                                v892 = v890 ^ (43881 * (v891 ^ 0x137F)) ^ __ROR4__(v891, 6);
                                v893 = v891 ^ (__ROR4__(v892, 30) + 24670 * __ROR4__(v892 + 133239679, 15));
                                v894 = v892 ^ (2033 * __ROR4__(v893 + 1419157410, 14) - __ROR4__(v893, 24));
                                v895 = v893 ^ __ROR4__(v894, 10) ^ (4991 * __ROR4__(v894 ^ 0xAB69605E, 12));
                                v896 = v894 ^ (v895 >> 10) ^ (43881 * (v895 ^ 0x7F1));
                                v897 = v895 ^ (2033 * (__ROR4__(~v896, 5) + 24670));
                                v898 = v897
                                     ^ (((v896 ^ (v897 - 2033) ^ 0xAB69605E) >> 2)
                                      + 4991 * __ROR4__(v896 ^ (v897 - 2033) ^ 0xAB6967AF, 30));
                                v899 = v896
                                     ^ (v897 - 2033)
                                     ^ 0xAB69605E
                                     ^ (__ROR4__(v898, 25) + 43881 * __ROR4__(v898 - 133239679, 6));
                                v900 = v898 ^ (24670 * (v899 ^ 0x137F) + __ROR4__(v899, 9));
                                v901 = v899 ^ (__ROR4__(v900, 25) + 2033 * __ROR4__(v900 ^ 0xAB69, 27));
                                v902 = v900 ^ v901 ^ 0xAC987321;
                                v903 = v901 ^ (4991 * __ROR4__(v902, 3) - 219010071);
                                v904 = v902 ^ (24670 * __ROR4__(v903 - 133239679, 1) - __ROR4__(v903, 6));
                                v905 = v903 ^ (__ROR4__(v904, 18) + 2033 * __ROR4__(v904 - 1419157410, 29));
                                v906 = v904 ^ (4991 * __ROR4__(v905 - 1419157410, 17) - __ROR4__(v905, 14));
                                v907 = v905 ^ (v906 >> 3) ^ (43881 * (v906 ^ 0x605E));
                                v908 = __ROR4__(v907, 30);
                                v879 = v878 ^ v907;
                                v878 = v885;
                                v873 = v877
                                     ^ v906
                                     ^ v908
                                     ^ (24670 * __ROR4__(v905 ^ (v906 >> 3) ^ (43881 * (v906 ^ 0x605E)) ^ 0x7F1137F, 28));
                                v877 = v883;
                                v874[3] = v873;
                                v874[7] = v879;
                                v874[2] = __ROR4__(v873, 8);
                                v874[6] = __ROR4__(v879, 8);
                                v874[1] = __ROR4__(v873, 16);
                                v874[5] = __ROR4__(v879, 16);
                                *v874 = __ROR4__(v873, 24);
                                v874[4] = __ROR4__(v879, 24);
                                v874 += 8;
                                --v876;
                              }
                              while ( v876 );
                              v909 = (const WCHAR *)lpModuleName;
                              v910 = 0;
                              v911 = 0;
                              do
                                v911 ^= *(_BYTE *)(lpModuleName + v910++);
                              while ( v910 < 0x338 );
                              if ( v911 != 64 )
                              {
                                MemoryFree((void *)lpModuleName);
LABEL_1149:
                                v791 = (int)v1281;
                                LODWORD(v793) = pcchLength;
LABEL_1150:
                                for ( i3 = 0; i3 != 4; ++i3 )
                                {
                                  v913 = (HMODULE)*(&WARBIRD::g_arModuleInfo + 3 * i3);
                                  if ( v913 )
                                    FreeLibrary(v913);
                                }
                                memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
                                memcpy_0(&WARBIRD::g_FuncAddress, off_18006E730, 0x170u);
                                goto LABEL_1183;
                              }
                              LODWORD(v1279) = 0;
                              LODWORD(v1283) = 0;
                              *(_BYTE *)(lpModuleName + 823) = 0;
                              v914 = 0;
                              v915 = 0;
                              memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
                              *(_QWORD *)&lpModuleName = v909;
                              while ( *(_BYTE *)v909 )
                              {
                                v916 = -1;
                                do
                                  ++v916;
                                while ( v909[v916] );
                                v917 = 3LL * v915;
                                v918 = (HMODULE *)(&WARBIRD::g_arModuleInfo + v917);
                                if ( !GetModuleHandleExW(0, v909, v918) )
                                {
                                  v914 = -1073741702;
                                  break;
                                }
                                v919 = &v909[v916];
                                if ( *(_WORD *)*v918 == 23117
                                  && (v920 = *((int *)*v918 + 15), (unsigned int)v920 < 0x10000000)
                                  && (v921 = (char *)*v918 + v920, v921 >= (char *)*v918)
                                  && *(_DWORD *)v921 == 17744 )
                                {
                                  if ( ((*((_WORD *)v921 + 12) - 267) & 0xFEFF) != 0 )
                                  {
                                    v914 = -1073741811;
                                  }
                                  else
                                  {
                                    *(struct WARBIRD::_MODULE_INFO near **)((char *)&WARBIRD::g_arModuleInfo
                                                                          + 8 * v917
                                                                          + 12) = (struct WARBIRD::_MODULE_INFO near *)*((_QWORD *)v921 + 17);
                                    v914 = 0;
                                    *((_DWORD *)&WARBIRD::g_arModuleInfo + 2 * v917 + 2) = *((_DWORD *)v921 + 20);
                                  }
                                }
                                else
                                {
                                  v914 = -1073741701;
                                }
                                v922 = *(_DWORD *)(v919 + 1);
                                v923 = 0;
                                v924 = v1279;
                                v909 = v919 + 3;
                                LODWORD(v1282) = v922;
                                while ( 1 )
                                {
                                  v1276 = v923;
                                  if ( v923 >= v922 )
                                    break;
                                  v925 = -1;
                                  do
                                    ++v925;
                                  while ( *((_BYTE *)v909 + v925) );
                                  if ( v914 >= 0 )
                                  {
                                    v926 = (void **)GetProcAddress(*v918, (LPCSTR)v909);
                                    if ( !v926 )
                                      goto LABEL_1178;
                                    v924 = v1279;
                                    v922 = (unsigned int)v1282;
                                    (&WARBIRD::g_FuncAddress)[(unsigned int)v1279] = v926;
                                    v923 = v1276;
                                  }
                                  ++v924;
                                  v909 = (const WCHAR *)((char *)v909 + v925 + 1);
                                  LODWORD(v1279) = v924;
                                  ++v923;
                                }
                                v915 = (_DWORD)v1283 + 1;
                                LODWORD(v1283) = (_DWORD)v1283 + 1;
                              }
LABEL_1178:
                              v927 = (void *)lpModuleName;
                              if ( (_QWORD)lpModuleName )
                              {
                                v928 = GetProcessHeap();
                                HeapFree(v928, 0, v927);
                              }
                              if ( v914 < 0 )
                                goto LABEL_1149;
                              v871 = g_WarbirdSecureFunctionsRefCount;
                              LODWORD(v793) = pcchLength;
                              v791 = (int)v1281;
                            }
                            g_WarbirdSecureFunctionsRefCount = v871 + 1;
LABEL_1183:
                            _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
                            LODWORD(v1429) = v793;
                            v1428 = 1;
                            LODWORD(v1430) = -1721306479;
                            DWORD2(v1429) = 1;
                            LODWORD(v1431) = 1;
                            DWORD2(v1430) = 1;
                            LODWORD(v1432) = v791;
                            DWORD2(v1431) = 1;
                            ((void (__fastcall *)(_QWORD, __int64, __int64, int *))qword_1800860D0)(0, 8225, 4, &v1428);
                            while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
                              ;
                            v929 = g_WarbirdSecureFunctionsRefCount;
                            if ( g_WarbirdSecureFunctionsRefCount > 0 )
                            {
                              --g_WarbirdSecureFunctionsRefCount;
                              if ( v929 == 1 )
                              {
                                for ( i4 = 0; i4 != 4; ++i4 )
                                {
                                  v931 = (HMODULE)*(&WARBIRD::g_arModuleInfo + 3 * i4);
                                  if ( v931 )
                                    FreeLibrary(v931);
                                }
                                memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
                                memcpy_0(&WARBIRD::g_FuncAddress, off_18006E730, 0x170u);
                              }
                            }
                            _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
                            off_180086160[0](0, (int)v1284);
                            goto LABEL_1193;
                          }
                          v710 = v1314;
                          v1291 = 0;
                          psz = (STRSAFE_PCNZWCH)v1314;
                          v1363 = 0;
                          memset_0(v1364, 0, 0x64u);
                          v711 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180086050[0])(v1284, 7);
                          if ( v711
                            && ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180086068[0])(
                                 v711,
                                 104,
                                 &v1363) )
                          {
                            if ( v1365 != 32 || !v1366 || v1364[0] <= 0 || v1364[1] <= 0 )
                              v707 = 0;
                            v712 = v472 & 0xF;
                            v713 = v712;
                            if ( v707 )
                            {
LABEL_909:
                              off_180086150((WARBIRD_DELAY_LOAD *)&v1351, (HDC)v710, HIDWORD(psz));
                              off_180086150((WARBIRD_DELAY_LOAD *)&v1355, (HDC)v710, HIDWORD(psz));
                              if ( v712 == 1 )
                                v1291 = ((__int64 (__fastcall *)(_QWORD))off_180086028[0])(v1343 == 0 ? 0xB26720 : 0);
LABEL_911:
                              v714 = v1284;
                              LODWORD(v1282) = ((__int64 (__fastcall *)(LPVOID, __int64))off_180086080)(v1284, 1);
                              v715 = 2064;
                              if ( v1342 )
                                v715 = 133138;
                              LODWORD(v1303) = v715;
                              if ( v707 )
                              {
                                v716 = 0;
                                v1367 = 0;
                                memset_0(v1368, 0, 0x64u);
                                v1379 = 0;
                                memset_0(v1380, 0, 0x64u);
                                v1289 = (size_t)v1344;
                                memset(v1403, 0, 28);
                                v1402 = 0;
                                v1391 = 0;
                                if ( !v1344 )
                                  goto LABEL_995;
                                v1276 = v1343;
                                v1302 = v1347;
                                v717 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180086050[0])(v714, 7);
                                if ( v717 )
                                {
                                  if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180086068[0])(
                                         v717,
                                         104,
                                         &v1367) )
                                  {
                                    LODWORD(v1279) = v1368[0];
                                    Size = v1369;
                                    v716 = 0;
                                    LODWORD(v1281) = v1368[1];
                                  }
                                  else
                                  {
                                    Size = 0;
                                    LODWORD(v1281) = 0;
                                    LODWORD(v1279) = 0;
                                  }
                                  v718 = ((__int64 (__fastcall *)(LPVOID))off_180086010[0])(v714);
                                  pcchLength = v718;
                                  v719 = (WARBIRD_DELAY_LOAD *)v718;
                                  if ( v718 )
                                  {
                                    DWORD1(v1402) = v1353 - v1351;
                                    DWORD2(v1402) = v1352 - v1354;
                                    v1335 = 0;
                                    memset(v1403, 0, 28);
                                    LODWORD(v1402) = 40;
                                    HIDWORD(v1402) = 2097153;
                                    v720 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180086018[0])(
                                             v718,
                                             &v1402,
                                             0,
                                             &v1335,
                                             0,
                                             0);
                                    v1308 = v720;
                                    if ( v720 )
                                    {
                                      if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180086068[0])(
                                             v720,
                                             104,
                                             &v1379) )
                                      {
                                        psz = v1381;
                                      }
                                      else
                                      {
                                        psz = 0;
                                      }
                                      DWORD2(v1391) = v1353 - v1351;
                                      HIDWORD(v1391) = v1354 - v1352;
                                      off_180086078(v719, v1308);
                                      ((void (__fastcall *)(WARBIRD_DELAY_LOAD *, __int64))off_180086080)(v719, 1);
                                      v723 = (void *)((__int64 (__fastcall *)(WARBIRD_DELAY_LOAD *, SIZE_T))off_180086078)(
                                                       v719,
                                                       v1302);
                                      v724 = off_1800860E8[0];
                                      v1294 = v723;
                                      v725 = ((__int64 (__fastcall *)(_QWORD))off_180086070[0])(0);
                                      ((void (__fastcall *)(size_t, __int128 *, __int64))v724)(pcchLength, &v1391, v725);
                                      v719 = (WARBIRD_DELAY_LOAD *)pcchLength;
                                      ((void (__fastcall *)(size_t, size_t, __int64, __int128 *, _DWORD, _QWORD))off_1800860D8)(
                                        pcchLength,
                                        v1289,
                                        0xFFFFFFFFLL,
                                        &v1391,
                                        (_DWORD)v1303,
                                        0);
                                      if ( v712 == 1 )
                                      {
                                        if ( v1276 )
                                          v726 = ((__int64 (__fastcall *)(__int64))off_180086118[0])(8);
                                        else
                                          v726 = 0xFFFFFF;
                                      }
                                      else
                                      {
                                        v726 = -5723992;
                                      }
                                      v727 = 0;
                                      v728 = -v1351;
                                      LODWORD(v1293) = v726;
                                      v729 = 0;
                                      if ( v1351 >= 0 )
                                      {
                                        v727 = v1351;
                                        v728 = 0;
                                      }
                                      v730 = -v1352;
                                      if ( v1352 >= 0 )
                                      {
                                        v729 = v1352;
                                        v730 = 0;
                                      }
                                      v731 = DWORD2(v1391) - v728;
                                      if ( DWORD2(v1391) - v728 >= (int)v1279 - v727 )
                                        v731 = v1279 - v727;
                                      v1276 = v731;
                                      v732 = HIDWORD(v1391) - v730;
                                      if ( HIDWORD(v1391) - v730 >= (int)v1281 - v729 )
                                        v732 = (_DWORD)v1281 - v729;
                                      LODWORD(v1288) = v732;
                                      if ( v731 > 0 && v732 > 0 )
                                      {
                                        v733 = (unsigned __int8)v1293;
                                        v734 = v1276;
                                        LODWORD(v1281) = 0;
                                        v735 = &psz[2 * v728 + 2 * (__int64)(DWORD2(v1391) * v730)];
                                        v1302 = (SIZE_T)v735;
                                        v736 = (char *)(Size + 4 * (v727 + (__int64)((int)v1279 * v729)));
                                        LODWORD(v1283) = (unsigned int)v1293 >> 8;
                                        LODWORD(v1290) = (unsigned int)v1293 >> 16;
                                        v1289 = 4LL * SDWORD2(v1391);
                                        v1280 = (LPVOID)(4LL * (int)v1279);
                                        Size = (SIZE_T)v736;
                                        do
                                        {
                                          v737 = (char)v1283;
                                          v738 = 0;
                                          v739 = (char)v1290;
                                          v740 = v735;
                                          psz = v735;
                                          v741 = v736;
                                          LODWORD(v1279) = 0;
                                          do
                                          {
                                            v742 = ~(unsigned __int8)((*(unsigned __int8 *)v740
                                                                     + *((unsigned __int8 *)v740 + 2)
                                                                     + 2 * (unsigned int)*((unsigned __int8 *)v740 + 1)) >> 2);
                                            if ( (unsigned __int8)((*(unsigned __int8 *)v740
                                                                  + *((unsigned __int8 *)v740 + 2)
                                                                  + 2 * (unsigned int)*((unsigned __int8 *)v740 + 1)) >> 2) != 0xFF )
                                            {
                                              v743 = (unsigned __int8)v741[2];
                                              v744 = v742;
                                              v745 = (int)((unsigned __int64)(2155905153LL * v742 * (v733 - v743)) >> 32) >> 7;
                                              v741[2] = v743 + (v745 < 0) + v745;
                                              v741[1] -= v744 * (v737 - v741[1]);
                                              *v741 -= v744 * (v739 - *v741);
                                              v746 = (unsigned __int8)v741[3];
                                              v747 = v744 * (255 - v746);
                                              v738 = v1279;
                                              LOBYTE(v745) = v746 + v747 / 255;
                                              v740 = psz;
                                              v741[3] = v745;
                                            }
                                            ++v738;
                                            v740 += 2;
                                            LODWORD(v1279) = v738;
                                            v741 += 4;
                                            psz = v740;
                                          }
                                          while ( v738 < v734 );
                                          v735 = (const wchar_t *)(v1289 + v1302);
                                          v736 = (char *)v1280 + Size;
                                          v1302 += v1289;
                                          Size += (SIZE_T)v1280;
                                          LODWORD(v1281) = (_DWORD)v1281 + 1;
                                        }
                                        while ( (int)v1281 < (int)v1288 );
                                        v83 = dwBytes;
                                        v719 = (WARBIRD_DELAY_LOAD *)pcchLength;
                                      }
                                      ((void (__fastcall *)(unsigned __int64))off_180086038)(v1308);
                                      v722 = 0;
                                      if ( v1294 )
                                        off_180086078(v719, (int)v1294);
                                    }
                                    else
                                    {
                                      v721 = GetLastError();
                                      v722 = 0;
                                      v716 = v721;
                                      if ( v721 > 0 )
                                        v716 = (unsigned __int16)v721 | 0x80070000;
                                      if ( v716 >= 0 )
                                        v716 = -2147467259;
                                    }
                                    ((void (__fastcall *)(WARBIRD_DELAY_LOAD *))off_180086030[0])(v719);
                                    if ( v716 < 0 )
                                      goto LABEL_995;
                                    v1370 = 0;
                                    memset_0(v1371, 0, 0x64u);
                                    v1382 = 0;
                                    memset_0(v1383, 0, 0x64u);
                                    v1302 = (SIZE_T)v1345;
                                    memset(v1405, 0, 28);
                                    v1404 = 0;
                                    v1394 = 0;
                                    if ( !v1345 )
                                      goto LABEL_995;
                                    v748 = v1284;
                                    v1276 = v1343;
                                    Size = v1348;
                                    v749 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180086050[0])(v1284, 7);
                                    if ( v749 )
                                    {
                                      if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180086068[0])(
                                             v749,
                                             104,
                                             &v1370) )
                                      {
                                        LODWORD(v1279) = v1371[0];
                                        pcchLength = v1372;
                                        v748 = v1284;
                                        LODWORD(v1281) = v1371[1];
                                      }
                                      else
                                      {
                                        pcchLength = 0;
                                        LODWORD(v1281) = 0;
                                        LODWORD(v1279) = 0;
                                      }
                                      v750 = ((__int64 (__fastcall *)(LPVOID))off_180086010[0])(v748);
                                      v1289 = v750;
                                      v751 = (WARBIRD_DELAY_LOAD *)v750;
                                      if ( v750 )
                                      {
                                        DWORD1(v1404) = v1357 - v1355;
                                        DWORD2(v1404) = v1356 - v1358;
                                        v1336 = 0;
                                        memset(v1405, 0, 28);
                                        LODWORD(v1404) = 40;
                                        HIDWORD(v1404) = 2097153;
                                        v1280 = (LPVOID)((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180086018[0])(
                                                          v750,
                                                          &v1404,
                                                          0,
                                                          &v1336,
                                                          0,
                                                          0);
                                        v752 = v1280;
                                        if ( v1280 )
                                        {
                                          if ( ((unsigned int (__fastcall *)(LPVOID, __int64, int *))off_180086068[0])(
                                                 v1280,
                                                 104,
                                                 &v1382) )
                                          {
                                            psz = v1384;
                                          }
                                          else
                                          {
                                            psz = 0;
                                          }
                                          DWORD2(v1394) = v1357 - v1355;
                                          HIDWORD(v1394) = v1358 - v1356;
                                          off_180086078(v751, (int)v752);
                                          ((void (__fastcall *)(WARBIRD_DELAY_LOAD *, __int64))off_180086080)(v751, 1);
                                          v754 = (void *)((__int64 (__fastcall *)(WARBIRD_DELAY_LOAD *, SIZE_T))off_180086078)(
                                                           v751,
                                                           Size);
                                          v755 = off_1800860E8[0];
                                          v1294 = v754;
                                          v756 = ((__int64 (__fastcall *)(_QWORD))off_180086070[0])(0);
                                          ((void (__fastcall *)(WARBIRD_DELAY_LOAD *, __int128 *, __int64))v755)(
                                            v751,
                                            &v1394,
                                            v756);
                                          ((void (__fastcall *)(WARBIRD_DELAY_LOAD *, SIZE_T, __int64, __int128 *, _DWORD, _QWORD))off_1800860D8)(
                                            v751,
                                            v1302,
                                            0xFFFFFFFFLL,
                                            &v1394,
                                            (_DWORD)v1303,
                                            0);
                                          if ( v713 == 1 )
                                          {
                                            if ( v1276 )
                                              v1277 = ((__int64 (__fastcall *)(__int64))off_180086118[0])(8);
                                          }
                                          else
                                          {
                                            v1277 = -5723992;
                                          }
                                          v757 = 0;
                                          v758 = -v1355;
                                          v759 = 0;
                                          if ( v1355 >= 0 )
                                          {
                                            v757 = v1355;
                                            v758 = 0;
                                          }
                                          v760 = -v1356;
                                          if ( v1356 >= 0 )
                                          {
                                            v760 = 0;
                                            v759 = v1356;
                                          }
                                          v761 = DWORD2(v1394) - v758;
                                          if ( DWORD2(v1394) - v758 >= (int)v1279 - v757 )
                                            v761 = v1279 - v757;
                                          v762 = HIDWORD(v1394) - v760;
                                          if ( HIDWORD(v1394) - v760 >= (int)v1281 - v759 )
                                            v762 = (_DWORD)v1281 - v759;
                                          LODWORD(v1290) = v762;
                                          if ( v761 > 0 && v762 > 0 )
                                          {
                                            LODWORD(v1281) = 0;
                                            v763 = &psz[2 * v758 + 2 * (__int64)(DWORD2(v1394) * v760)];
                                            Size = (SIZE_T)v763;
                                            v764 = pcchLength + 4 * (v757 + (__int64)((int)v1279 * v759));
                                            v1276 = (unsigned int)v1277 >> 8;
                                            LODWORD(v1283) = HIWORD(v1277);
                                            v1302 = 4LL * SDWORD2(v1394);
                                            v1308 = 4LL * (int)v1279;
                                            pcchLength = v764;
                                            do
                                            {
                                              v765 = v1276;
                                              v766 = v763;
                                              v767 = (char)v1283;
                                              v768 = (_BYTE *)v764;
                                              v769 = v1277;
                                              v770 = 0;
                                              psz = v763;
                                              LODWORD(v1279) = 0;
                                              do
                                              {
                                                v771 = ~(unsigned __int8)((*(unsigned __int8 *)v766
                                                                         + *((unsigned __int8 *)v766 + 2)
                                                                         + 2
                                                                         * (unsigned int)*((unsigned __int8 *)v766 + 1)) >> 2);
                                                if ( (unsigned __int8)((*(unsigned __int8 *)v766
                                                                      + *((unsigned __int8 *)v766 + 2)
                                                                      + 2 * (unsigned int)*((unsigned __int8 *)v766 + 1)) >> 2) != 0xFF )
                                                {
                                                  v772 = (unsigned __int8)v768[2];
                                                  v773 = v771;
                                                  v774 = (int)((unsigned __int64)(2155905153LL * v771 * (v769 - v772)) >> 32) >> 7;
                                                  v768[2] = v772 + (v774 < 0) + v774;
                                                  v768[1] -= v773 * (v765 - v768[1]);
                                                  *v768 -= v773 * (v767 - *v768);
                                                  v775 = (unsigned __int8)v768[3];
                                                  v776 = v773 * (255 - v775);
                                                  v770 = v1279;
                                                  LOBYTE(v774) = v775 + v776 / 255;
                                                  v766 = psz;
                                                  v768[3] = v774;
                                                }
                                                v766 += 2;
                                                ++v770;
                                                v768 += 4;
                                                psz = v766;
                                                LODWORD(v1279) = v770;
                                              }
                                              while ( v770 < v761 );
                                              v763 = (const wchar_t *)(v1302 + Size);
                                              v764 = v1308 + pcchLength;
                                              Size += v1302;
                                              pcchLength += v1308;
                                              LODWORD(v1281) = (_DWORD)v1281 + 1;
                                            }
                                            while ( (int)v1281 < (int)v1290 );
                                            v83 = dwBytes;
                                            v751 = (WARBIRD_DELAY_LOAD *)v1289;
                                          }
                                          ((void (__fastcall *)(LPVOID))off_180086038)(v1280);
                                          if ( v1294 )
                                            off_180086078(v751, (int)v1294);
                                        }
                                        else
                                        {
                                          v753 = GetLastError();
                                          v722 = v753;
                                          if ( v753 > 0 )
                                            v722 = (unsigned __int16)v753 | 0x80070000;
                                          if ( v722 >= 0 )
                                            v722 = -2147467259;
                                        }
                                        ((void (__fastcall *)(WARBIRD_DELAY_LOAD *))off_180086030[0])(v751);
                                        if ( v722 < 0 )
                                          goto LABEL_995;
                                        v1294 = 0;
                                        v777 = 0;
                                        v778 = v1284;
LABEL_1138:
                                        ((void (__fastcall *)(LPVOID, _QWORD))off_180086080)(v778, (unsigned int)v1282);
                                        if ( !v777 )
                                        {
LABEL_1053:
                                          v805 = v1294;
                                          if ( !v1294 )
                                            goto LABEL_995;
                                          goto LABEL_1054;
                                        }
LABEL_1052:
                                        ((void (__fastcall *)(LPVOID))off_180086038)(v777);
                                        goto LABEL_1053;
                                      }
                                    }
                                  }
                                }
LABEL_994:
                                GetLastError();
                                goto LABEL_995;
                              }
                              if ( v1343 || (v794 = -64, v713 == 1) )
                                v794 = -1;
                              BYTE2(v1304) = v794;
                              LOWORD(v1304) = 0;
                              BYTE3(v1304) = 1;
                              v1294 = (LPVOID)((__int64 (__fastcall *)(LPVOID))off_180086010[0])(v714);
                              if ( !v1294 )
                                goto LABEL_994;
                              if ( v713 == 1 )
                              {
                                v795 = 0;
                                v796 = v1357 - v1355;
                                LODWORD(v1288) = 0;
                                if ( v1357 - v1355 <= v1353 - v1351 )
                                  v796 = v1353 - v1351;
                                v797 = v1358 - v1352;
                                LODWORD(v1293) = v796;
                                LODWORD(v1306) = v1358 - v1352;
                                if ( v1342 )
                                {
                                  v798 = v1351 + v796 - v1353;
                                  v799 = v796 + v1355 - v1357;
                                }
                                else
                                {
                                  v798 = 0;
                                  v799 = 0;
                                }
                                v800 = v798 + v1353 - v1351;
                                v801 = v1356 - v1352;
                                HIDWORD(dwBytes) = v799;
                                LODWORD(v1290) = v1354 - v1352;
                                v802 = v799 + v1357 - v1355;
                                v803 = v1358 - v1352;
                              }
                              else
                              {
                                v796 = DWORD2(v1314);
                                v797 = HIDWORD(v1314);
                                v795 = v1352;
                                v798 = v1351;
                                v800 = v1353;
                                v801 = v1356;
                                v802 = v1357;
                                LODWORD(v1290) = v1354;
                                HIDWORD(dwBytes) = v1355;
                                v803 = v1358;
                                LODWORD(v1306) = HIDWORD(v1314);
                                LODWORD(v1293) = DWORD2(v1314);
                                LODWORD(v1288) = v1352;
                              }
                              LODWORD(v1298) = v802;
                              LODWORD(v1279) = v803;
                              v1337 = 0;
                              v1398[1] = v796;
                              v1276 = v801;
                              LODWORD(v1297) = v800;
                              LODWORD(v1296) = v798;
                              memset(&v1398[4], 0, 28);
                              v1398[0] = 40;
                              v1398[2] = -v797;
                              v1398[3] = 2097153;
                              v804 = (void *)((__int64 (__fastcall *)(LPVOID, _DWORD *, _QWORD, __int64 *, _QWORD, _DWORD))off_180086018[0])(
                                               v1294,
                                               v1398,
                                               0,
                                               &v1337,
                                               0,
                                               0);
                              v1280 = v804;
                              if ( !v804 )
                              {
                                GetLastError();
                                v805 = v1294;
LABEL_1054:
                                ((void (__fastcall *)(LPVOID))off_180086030[0])(v805);
LABEL_995:
                                if ( v1291 )
                                  ((void (__fastcall *)(SIZE_T))off_180086038)(v1291);
                                goto LABEL_997;
                              }
                              off_180086078((WARBIRD_DELAY_LOAD *)v1294, (int)v804);
                              if ( v713 == 1 && v1291 )
                              {
                                v1395 = 0;
                                v1396 = (int)v1293;
                                v1397 = v1306;
                                off_1800860E8[0]((WARBIRD_DELAY_LOAD *)v1294, (int)&v1395);
                              }
                              v1373 = 0;
                              memset_0(v1374, 0, 0x64u);
                              v1385 = 0;
                              memset_0(v1386, 0, 0x64u);
                              v1308 = (unsigned __int64)v1344;
                              memset(v1407, 0, 28);
                              v1406 = 0;
                              v1392 = 0;
                              if ( v1344 )
                              {
                                LODWORD(v1292) = v1343;
                                Size = v1347;
                                v806 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180086050[0])(v1294, 7);
                                if ( !v806 )
                                  goto LABEL_1050;
                                if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180086068[0])(
                                       v806,
                                       104,
                                       &v1373) )
                                {
                                  pcchLength = v1375;
                                  LODWORD(v1281) = v1374[0];
                                  LODWORD(v1283) = v1374[1];
                                }
                                else
                                {
                                  pcchLength = 0;
                                  LODWORD(v1283) = 0;
                                  LODWORD(v1281) = 0;
                                }
                                v807 = ((__int64 (__fastcall *)(LPVOID))off_180086010[0])(v1294);
                                v1289 = v807;
                                if ( !v807 )
                                  goto LABEL_1050;
                                v1339[0] = 0;
                                v808 = v1297 - v798;
                                LODWORD(v1406) = 40;
                                v809 = (int)v1290;
                                DWORD2(v1406) = v795 - (_DWORD)v1290;
                                v810 = 0;
                                LODWORD(v1297) = v808;
                                DWORD1(v1406) = v808;
                                memset(v1407, 0, 28);
                                HIDWORD(v1406) = 2097153;
                                v811 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180086018[0])(
                                         v807,
                                         &v1406,
                                         0,
                                         v1339,
                                         0,
                                         0);
                                v1302 = v811;
                                if ( v811 )
                                {
                                  if ( ((unsigned int (__fastcall *)(SIZE_T, __int64, int *))off_180086068[0])(
                                         v811,
                                         104,
                                         &v1385) )
                                  {
                                    psz = v1387;
                                  }
                                  else
                                  {
                                    psz = 0;
                                  }
                                  HIDWORD(v1392) = v809 - (_DWORD)v1288;
                                  v813 = v1289;
                                  DWORD2(v1392) = v1297;
                                  off_180086078((WARBIRD_DELAY_LOAD *)v1289, v1302);
                                  ((void (__fastcall *)(size_t, __int64))off_180086080)(v813, 1);
                                  v814 = ((__int64 (__fastcall *)(size_t, SIZE_T))off_180086078)(v813, Size);
                                  v815 = off_1800860E8[0];
                                  *(_QWORD *)&lpModuleName = v814;
                                  v816 = ((__int64 (__fastcall *)(_QWORD))off_180086070[0])(0);
                                  ((void (__fastcall *)(size_t, __int128 *, __int64))v815)(v1289, &v1392, v816);
                                  v817 = (WARBIRD_DELAY_LOAD *)v1289;
                                  ((void (__fastcall *)(size_t, unsigned __int64, __int64, __int128 *, _DWORD, _QWORD))off_1800860D8)(
                                    v1289,
                                    v1308,
                                    0xFFFFFFFFLL,
                                    &v1392,
                                    (_DWORD)v1303,
                                    0);
                                  if ( v713 == 1 )
                                  {
                                    if ( (_DWORD)v1292 )
                                      v818 = ((__int64 (__fastcall *)(__int64))off_180086118[0])(8);
                                    else
                                      v818 = 0xFFFFFF;
                                  }
                                  else
                                  {
                                    v818 = -5723992;
                                  }
                                  v819 = (int)v1288;
                                  v820 = -(int)v1296;
                                  LODWORD(v1297) = v818;
                                  v821 = 0;
                                  if ( (int)v1296 >= 0 )
                                  {
                                    v820 = 0;
                                    v821 = (int)v1296;
                                  }
                                  if ( (int)v1288 >= 0 )
                                  {
                                    v822 = 0;
                                  }
                                  else
                                  {
                                    v822 = -(int)v1288;
                                    v819 = 0;
                                  }
                                  v823 = DWORD2(v1392) - v820;
                                  if ( DWORD2(v1392) - v820 >= (int)v1281 - v821 )
                                    v823 = (_DWORD)v1281 - v821;
                                  LODWORD(v1292) = v823;
                                  v824 = HIDWORD(v1392) - v822;
                                  if ( HIDWORD(v1392) - v822 >= (int)v1283 - v819 )
                                    v824 = (_DWORD)v1283 - v819;
                                  LODWORD(v1296) = v824;
                                  if ( v823 > 0 && v824 > 0 )
                                  {
                                    v825 = (int)v1281;
                                    v826 = v1297;
                                    v827 = v1292;
                                    LODWORD(v1290) = 0;
                                    v828 = &psz[2 * v820 + 2 * (__int64)(DWORD2(v1392) * v822)];
                                    Size = (SIZE_T)v828;
                                    v829 = pcchLength + 4 * (v821 + (__int64)((int)v1281 * v819));
                                    LODWORD(v1281) = (unsigned int)v1297 >> 8;
                                    LODWORD(v1288) = WORD1(v1297);
                                    v1308 = 4LL * SDWORD2(v1392);
                                    v1297 = 4 * v825;
                                    pcchLength = v829;
                                    do
                                    {
                                      v830 = (char)v1281;
                                      v831 = 0;
                                      v832 = (char)v1288;
                                      v833 = v828;
                                      LODWORD(v1283) = 0;
                                      v834 = (_BYTE *)v829;
                                      psz = v828;
                                      do
                                      {
                                        v835 = ~(unsigned __int8)((*(unsigned __int8 *)v833
                                                                 + *((unsigned __int8 *)v833 + 2)
                                                                 + 2 * (unsigned int)*((unsigned __int8 *)v833 + 1)) >> 2);
                                        if ( (unsigned __int8)((*(unsigned __int8 *)v833
                                                              + *((unsigned __int8 *)v833 + 2)
                                                              + 2 * (unsigned int)*((unsigned __int8 *)v833 + 1)) >> 2) != 0xFF )
                                        {
                                          v836 = (unsigned __int8)v834[2];
                                          v837 = v835;
                                          v838 = (int)((unsigned __int64)(2155905153LL * v835 * (v826 - v836)) >> 32) >> 7;
                                          v834[2] = v836 + (v838 < 0) + v838;
                                          v834[1] -= v837 * (v830 - v834[1]);
                                          *v834 -= v837 * (v832 - *v834);
                                          v839 = (unsigned __int8)v834[3];
                                          v840 = v837 * (255 - v839);
                                          v831 = (int)v1283;
                                          LOBYTE(v838) = v839 + v840 / 255;
                                          v833 = psz;
                                          v834[3] = v838;
                                        }
                                        ++v831;
                                        v833 += 2;
                                        LODWORD(v1283) = v831;
                                        v834 += 4;
                                        psz = v833;
                                      }
                                      while ( v831 < v827 );
                                      v828 = (const wchar_t *)(v1308 + Size);
                                      v829 = v1297 + pcchLength;
                                      Size += v1308;
                                      pcchLength += v1297;
                                      LODWORD(v1290) = (_DWORD)v1290 + 1;
                                    }
                                    while ( (int)v1290 < (int)v1296 );
                                    v83 = dwBytes;
                                    v801 = v1276;
                                    v817 = (WARBIRD_DELAY_LOAD *)v1289;
                                  }
                                  ((void (__fastcall *)(SIZE_T))off_180086038)(v1302);
                                  if ( (_QWORD)lpModuleName )
                                    off_180086078(v817, lpModuleName);
                                }
                                else
                                {
                                  v810 = GetLastError();
                                  v812 = v810 < 0;
                                  if ( v810 > 0 )
                                  {
                                    v810 = (unsigned __int16)v810 | 0x80070000;
                                    v812 = v810 < 0;
                                  }
                                  if ( !v812 )
                                    v810 = -2147467259;
                                }
                                ((void (__fastcall *)(size_t))off_180086030[0])(v1289);
                                if ( v810 < 0 )
                                  goto LABEL_1051;
                                v841 = 0;
                                v1376 = 0;
                                memset_0(v1377, 0, 0x64u);
                                v1388 = 0;
                                memset_0(v1389, 0, 0x64u);
                                Size = (SIZE_T)v1345;
                                memset(v1409, 0, 28);
                                v1408 = 0;
                                v1393 = 0;
                                if ( !v1345 )
                                  goto LABEL_1051;
                                v842 = v1294;
                                LODWORD(v1292) = v1343;
                                *(_QWORD *)&lpModuleName = v1348;
                                v843 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180086050[0])(v1294, 7);
                                if ( !v843 )
                                  goto LABEL_1050;
                                if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180086068[0])(
                                       v843,
                                       104,
                                       &v1376) )
                                {
                                  v1276 = v1377[0];
                                  pcchLength = v1378;
                                  v841 = 0;
                                  LODWORD(v1283) = v1377[1];
                                }
                                else
                                {
                                  pcchLength = 0;
                                  LODWORD(v1283) = 0;
                                  v1276 = 0;
                                }
                                v1289 = ((__int64 (__fastcall *)(LPVOID))off_180086010[0])(v842);
                                if ( v1289 )
                                {
                                  LODWORD(v1298) = v1298 - HIDWORD(dwBytes);
                                  DWORD1(v1408) = v1298;
                                  DWORD2(v1408) = v801 - v1279;
                                  v1333 = 0;
                                  memset(v1409, 0, 28);
                                  LODWORD(v1408) = 40;
                                  HIDWORD(v1408) = 2097153;
                                  v844 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180086018[0])(
                                           v1289,
                                           &v1408,
                                           0,
                                           &v1333,
                                           0,
                                           0);
                                  v1302 = v844;
                                  if ( v844 )
                                  {
                                    if ( ((unsigned int (__fastcall *)(SIZE_T, __int64, int *))off_180086068[0])(
                                           v844,
                                           104,
                                           &v1388) )
                                    {
                                      psz = v1390;
                                    }
                                    else
                                    {
                                      psz = 0;
                                    }
                                    v846 = v1289;
                                    HIDWORD(v1393) = v1279 - v801;
                                    DWORD2(v1393) = v1298;
                                    off_180086078((WARBIRD_DELAY_LOAD *)v1289, v1302);
                                    ((void (__fastcall *)(size_t, __int64))off_180086080)(v846, 1);
                                    v847 = (void *)((__int64 (__fastcall *)(size_t, _QWORD))off_180086078)(
                                                     v846,
                                                     lpModuleName);
                                    v848 = off_1800860E8[0];
                                    v1288 = v847;
                                    v849 = ((__int64 (__fastcall *)(_QWORD))off_180086070[0])(0);
                                    ((void (__fastcall *)(size_t, __int128 *, __int64))v848)(v1289, &v1393, v849);
                                    v850 = (WARBIRD_DELAY_LOAD *)v1289;
                                    ((void (__fastcall *)(size_t, SIZE_T, __int64, __int128 *, _DWORD, _QWORD))off_1800860D8)(
                                      v1289,
                                      Size,
                                      0xFFFFFFFFLL,
                                      &v1393,
                                      (_DWORD)v1303,
                                      0);
                                    if ( v713 == 1 )
                                    {
                                      if ( (_DWORD)v1292 )
                                        v1277 = ((__int64 (__fastcall *)(__int64))off_180086118[0])(8);
                                    }
                                    else
                                    {
                                      v1277 = -5723992;
                                    }
                                    v851 = 0;
                                    v852 = -HIDWORD(dwBytes);
                                    if ( (dwBytes & 0x8000000000000000uLL) == 0LL )
                                    {
                                      v852 = 0;
                                      v851 = HIDWORD(dwBytes);
                                    }
                                    if ( v801 >= 0 )
                                    {
                                      v853 = 0;
                                    }
                                    else
                                    {
                                      v853 = -v801;
                                      v801 = 0;
                                    }
                                    v854 = DWORD2(v1393) - v852;
                                    if ( DWORD2(v1393) - v852 >= (int)(v1276 - v851) )
                                      v854 = v1276 - v851;
                                    LODWORD(v1292) = v854;
                                    v855 = HIDWORD(v1393) - v853;
                                    if ( HIDWORD(v1393) - v853 >= (int)v1283 - v801 )
                                      v855 = (_DWORD)v1283 - v801;
                                    LODWORD(v1281) = v855;
                                    if ( v854 > 0 && v855 > 0 )
                                    {
                                      v856 = v1292;
                                      LODWORD(v1283) = 0;
                                      v857 = &psz[2 * v852 + 2 * (__int64)(DWORD2(v1393) * v853)];
                                      Size = (SIZE_T)v857;
                                      v858 = pcchLength + 4 * (v851 + (__int64)(int)(v1276 * v801));
                                      LODWORD(v1290) = (unsigned int)v1277 >> 8;
                                      LODWORD(v1279) = HIWORD(v1277);
                                      *(_QWORD *)&lpModuleName = 4LL * SDWORD2(v1393);
                                      v1308 = 4LL * (int)v1276;
                                      pcchLength = v858;
                                      do
                                      {
                                        v859 = (char)v1290;
                                        v860 = v857;
                                        v861 = v1279;
                                        v862 = (_BYTE *)v858;
                                        v863 = v1277;
                                        v864 = 0;
                                        psz = v857;
                                        v1276 = 0;
                                        do
                                        {
                                          v865 = ~(unsigned __int8)((*(unsigned __int8 *)v860
                                                                   + *((unsigned __int8 *)v860 + 2)
                                                                   + 2 * (unsigned int)*((unsigned __int8 *)v860 + 1)) >> 2);
                                          if ( (unsigned __int8)((*(unsigned __int8 *)v860
                                                                + *((unsigned __int8 *)v860 + 2)
                                                                + 2 * (unsigned int)*((unsigned __int8 *)v860 + 1)) >> 2) != 0xFF )
                                          {
                                            v866 = (unsigned __int8)v862[2];
                                            v867 = v865;
                                            v868 = (int)((unsigned __int64)(2155905153LL * v865 * (v863 - v866)) >> 32) >> 7;
                                            v862[2] = v866 + (v868 < 0) + v868;
                                            v862[1] -= v867 * (v859 - v862[1]);
                                            *v862 -= v867 * (v861 - *v862);
                                            v869 = (unsigned __int8)v862[3];
                                            v870 = v867 * (255 - v869);
                                            v864 = v1276;
                                            LOBYTE(v868) = v869 + v870 / 255;
                                            v860 = psz;
                                            v862[3] = v868;
                                          }
                                          ++v864;
                                          v860 += 2;
                                          v1276 = v864;
                                          v862 += 4;
                                          psz = v860;
                                        }
                                        while ( v864 < v856 );
                                        v857 = (const wchar_t *)(lpModuleName + Size);
                                        v858 = v1308 + pcchLength;
                                        Size += lpModuleName;
                                        pcchLength += v1308;
                                        LODWORD(v1283) = (_DWORD)v1283 + 1;
                                      }
                                      while ( (int)v1283 < (int)v1281 );
                                      v83 = dwBytes;
                                      v850 = (WARBIRD_DELAY_LOAD *)v1289;
                                    }
                                    ((void (__fastcall *)(SIZE_T))off_180086038)(v1302);
                                    if ( v1288 )
                                      off_180086078(v850, (int)v1288);
                                    v842 = v1294;
                                  }
                                  else
                                  {
                                    v841 = GetLastError();
                                    v845 = v841 < 0;
                                    if ( v841 > 0 )
                                    {
                                      v841 = (unsigned __int16)v841 | 0x80070000;
                                      v845 = v841 < 0;
                                    }
                                    if ( !v845 )
                                      v841 = -2147467259;
                                  }
                                  ((void (__fastcall *)(size_t))off_180086030[0])(v1289);
                                  if ( v841 >= 0 )
                                  {
                                    v334 = v713 == 1;
                                    v778 = v1284;
                                    if ( v334 )
                                      ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, LPVOID, _DWORD, _DWORD, int))WARBIRD::g_FuncAddress)(
                                        v1284,
                                        (unsigned int)v1351,
                                        (unsigned int)v1352,
                                        (unsigned int)v1293,
                                        v1306,
                                        v842,
                                        0,
                                        0,
                                        13369376);
                                    else
                                      ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, LPVOID, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))off_180086040[0])(
                                        v1284,
                                        (unsigned int)v1314,
                                        DWORD1(v1314),
                                        (unsigned int)v1293,
                                        v1306,
                                        v842,
                                        0,
                                        0,
                                        (_DWORD)v1293,
                                        v1306,
                                        (_DWORD)v1304);
                                    v777 = v1280;
                                    goto LABEL_1138;
                                  }
                                }
                                else
                                {
LABEL_1050:
                                  GetLastError();
                                }
                              }
LABEL_1051:
                              v777 = v1280;
                              goto LABEL_1052;
                            }
                          }
                          else
                          {
                            v707 = 0;
                            v713 = v472 & 0xF;
                            v712 = v713;
                          }
                          if ( v712 != 1 )
                            goto LABEL_911;
                          goto LABEL_909;
                        }
                        v588 = 0;
                        pcchLength = 0;
                        psz = 0;
                        LODWORD(v1279) = 0;
                        v1325 = 0;
                        v1289 = 0;
                        v589 = 0;
                        v1291 = 0;
                        memset(v1340, 0, sizeof(v1340));
                        v1311 = 0;
                        v1292 = 0;
                        v1320 = 0;
                        if ( !((unsigned int (__fastcall *)(__int64, unsigned int *, _QWORD, unsigned int *))off_1800860A0[0])(
                                8,
                                &v1311,
                                0,
                                &v1320) )
                        {
                          v588 = GetLastError();
                          v590 = v588 < 0;
                          if ( v588 > 0 )
                          {
                            v588 = (unsigned __int16)v588 | 0x80070000;
                            v590 = v588 < 0;
                          }
                          if ( !v590 )
                            v588 = -2147467259;
                          goto LABEL_706;
                        }
                        v591 = MemoryAlloc(2LL * v1320);
                        SP<unsigned long,SP_MEM<unsigned long>>::operator=(&v1291, v591);
                        v592 = (WARBIRD_DELAY_LOAD *)v1291;
                        if ( v1291 )
                        {
                          v593 = MemoryAlloc(4LL * (v1311 + 1));
                          SP<unsigned long,SP_MEM<unsigned long>>::operator=(&v1292, v593);
                          v594 = (_DWORD *)v1292;
                          if ( v1292 )
                          {
                            if ( ((unsigned int (__fastcall *)(__int64, unsigned int *, WARBIRD_DELAY_LOAD *, unsigned int *))off_1800860A0[0])(
                                   8,
                                   &v1311,
                                   v592,
                                   &v1320) )
                            {
                              if ( v1311 )
                              {
                                for ( i5 = 0; i5 < v1311; ++i5 )
                                {
                                  *v594 = off_1800860B0(v592, 0);
                                  v597 = -1;
                                  do
                                    ++v597;
                                  while ( *((_WORD *)v592 + v597) );
                                  ++v594;
                                  v592 = (WARBIRD_DELAY_LOAD *)((char *)v592 + 2 * v597 + 2);
                                }
                                LOBYTE(v472) = v1297;
                              }
                              v122 = v1292;
                              *v594 = 1033;
                              v589 = v1311 + 1;
                              v1292 = 0;
                              psz = (STRSAFE_PCNZWCH)v122;
LABEL_706:
                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1292);
                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1291);
                              if ( v588 < 0 )
                              {
                                v1291 = 0;
                                Size = 0;
                                pcchLength = 0;
                                goto LABEL_772;
                              }
                              v598 = 0;
                              v599 = 0;
                              LODWORD(v1293) = 0;
                              if ( v589 )
                              {
                                while ( 2 )
                                {
                                  for ( i6 = 0; i6 < 0x26; ++i6 )
                                  {
                                    if ( *(_DWORD *)(v122 + 4LL * v599) == `CUxDisplayStringsT<CEmptyType>::GetAllPreferredStrings'::`2'::uLanguageArray[i6] )
                                    {
                                      v598 = i6;
                                      LODWORD(v1293) = i6;
                                      goto LABEL_714;
                                    }
                                  }
                                  if ( ++v599 < v589 )
                                    continue;
                                  break;
                                }
                                v598 = 0;
                              }
LABEL_714:
                              v601 = v598;
                              LODWORD(v1281) = 0;
                              v602 = (unsigned int)`CUxDisplayStringsT<CEmptyType>::GetAllPreferredStrings'::`2'::uLanguageArray[v598];
                              memset(v1413, 0, sizeof(v1413));
                              if ( ((unsigned int (__fastcall *)(__int64, _BYTE *, __int64))off_1800860A8[0])(
                                     v602,
                                     v1433,
                                     85)
                                && ((int (__fastcall *)(_BYTE *, __int64, _OWORD *, __int64))off_180086090[0])(
                                     v1433,
                                     88,
                                     v1413,
                                     16) > 0 )
                              {
                                LODWORD(v1281) = (HIDWORD(v1413[0]) >> 27) & 1;
                              }
                              memset_0(v1341, 0, 0x98u);
                              v603 = L"Segoe UI Light";
                              for ( i7 = 0; i7 != 19; ++i7 )
                              {
                                v1341[i7] = v603;
                                v605 = -1;
                                do
                                  ++v605;
                                while ( v603[v605] );
                                v603 += v605 + 1;
                              }
                              v1291 = v1341[*((unsigned __int8 *)`CUxDisplayStringsT<CEmptyType>::GetFontsForLCIDIndex'::`2'::LangFontIndexMapping
                                            + 3 * v601)];
                              Size = v1341[*((unsigned __int8 *)`CUxDisplayStringsT<CEmptyType>::GetFontsForLCIDIndex'::`2'::LangFontIndexMapping
                                           + 3 * v601
                                           + 1)];
                              pcchLength = v1341[*((unsigned __int8 *)`CUxDisplayStringsT<CEmptyType>::GetFontsForLCIDIndex'::`2'::LangFontIndexMapping
                                                 + 3 * v601
                                                 + 2)];
                              v606 = (char *)MemoryAlloc(0x1C90u);
                              v607 = v606;
                              if ( !v606 )
                              {
                                v588 = -2147024882;
LABEL_772:
                                v646 = 0;
LABEL_773:
                                v657 = (void **)v1294;
                                goto LABEL_774;
                              }
                              v608 = `CUxDisplayStringsT<CEmptyType>::GetAllPreferredStrings'::`2'::bEncryptedStringBuffer;
                              v609 = v606;
                              v610 = 0;
                              v611 = -1;
                              v612 = 0;
                              v613 = 0;
                              v614 = 914;
                              do
                              {
                                v615 = *((unsigned __int8 *)v608 + 1);
                                v616 = *(unsigned __int8 *)v608;
                                v617 = *((unsigned __int8 *)v608++ + 4);
                                v618 = *((unsigned __int8 *)v608 - 5)
                                     | ((*((unsigned __int8 *)v608 - 6) | ((v615 | (v616 << 8)) << 8)) << 8);
                                v619 = v613 ^ v618;
                                v620 = *((unsigned __int8 *)v608 - 1)
                                     | ((*((unsigned __int8 *)v608 - 2)
                                       | ((*((unsigned __int8 *)v608 - 3) | (v617 << 8)) << 8)) << 8);
                                v621 = v613 ^ v618 ^ v612 ^ v620 ^ 0xAC987321;
                                v622 = v619 ^ (__ROR4__(v621, 22) + 4991 * __ROR4__(v621 + 1419157410, 27));
                                v623 = v621 ^ (43881 * __ROR4__(v622 + 133239679, 9) - __ROR4__(v622, 30));
                                v624 = v622 ^ (24670 * v623 - (v623 >> 13) - 123127970);
                                v625 = v623 ^ (2033 * __ROR4__(v624 ^ 0xAB69, 26) - __ROR4__(v624, 30));
                                v626 = v624 ^ (133239679 - (v625 ^ 0xAB69605E));
                                v627 = v625 ^ (43881 * (v626 ^ 0x137F)) ^ __ROR4__(v626, 6);
                                v628 = v626 ^ (__ROR4__(v627, 30) + 24670 * __ROR4__(v627 + 133239679, 15));
                                v629 = v627 ^ (2033 * __ROR4__(v628 + 1419157410, 14) - __ROR4__(v628, 24));
                                v630 = v628 ^ __ROR4__(v629, 10) ^ (4991 * __ROR4__(v629 ^ 0xAB69605E, 12));
                                v631 = v629 ^ (v630 >> 10) ^ (43881 * (v630 ^ 0x7F1));
                                v632 = v630 ^ (2033 * (__ROR4__(~v631, 5) + 24670));
                                v633 = v632
                                     ^ (((v631 ^ (v632 - 2033) ^ 0xAB69605E) >> 2)
                                      + 4991 * __ROR4__(v631 ^ (v632 - 2033) ^ 0xAB6967AF, 30));
                                v634 = v631
                                     ^ (v632 - 2033)
                                     ^ 0xAB69605E
                                     ^ (__ROR4__(v633, 25) + 43881 * __ROR4__(v633 - 133239679, 6));
                                v635 = v633 ^ (24670 * (v634 ^ 0x137F) + __ROR4__(v634, 9));
                                v636 = v634 ^ (__ROR4__(v635, 25) + 2033 * __ROR4__(v635 ^ 0xAB69, 27));
                                v637 = v635 ^ v636 ^ 0xAC987321;
                                v638 = v636 ^ (4991 * __ROR4__(v637, 3) - 219010071);
                                v639 = v637 ^ (24670 * __ROR4__(v638 - 133239679, 1) - __ROR4__(v638, 6));
                                v640 = v638 ^ (__ROR4__(v639, 18) + 2033 * __ROR4__(v639 - 1419157410, 29));
                                v641 = v639 ^ (4991 * __ROR4__(v640 - 1419157410, 17) - __ROR4__(v640, 14));
                                v642 = v640 ^ (v641 >> 3) ^ (43881 * (v641 ^ 0x605E));
                                v643 = __ROR4__(v642, 30);
                                v612 = v611 ^ v642;
                                v611 = v620;
                                v613 = v610
                                     ^ v641
                                     ^ v643
                                     ^ (24670 * __ROR4__(v640 ^ (v641 >> 3) ^ (43881 * (v641 ^ 0x605E)) ^ 0x7F1137F, 28));
                                v610 = v618;
                                v609[3] = v613;
                                v609[7] = v612;
                                v609[2] = __ROR4__(v613, 8);
                                v609[6] = __ROR4__(v612, 8);
                                v609[1] = __ROR4__(v613, 16);
                                v609[5] = __ROR4__(v612, 16);
                                *v609 = __ROR4__(v613, 24);
                                v609[4] = __ROR4__(v612, 24);
                                v609 += 8;
                                --v614;
                              }
                              while ( v614 );
                              LOBYTE(v472) = v1297;
                              v644 = 0;
                              v645 = 0;
                              v646 = 7312;
                              do
                              {
                                v647 = (__m128)_mm_loadu_si128((const __m128i *)&v607[v644]);
                                v644 += 16LL;
                                v648 = _mm_xor_ps(v647, v645);
                                v645 = v648;
                              }
                              while ( v644 < 0x1C90 );
                              v649 = _mm_xor_ps(v648, (__m128)_mm_srli_si128((__m128i)v648, 8));
                              v650 = _mm_xor_ps(v649, (__m128)_mm_srli_si128((__m128i)v649, 4));
                              v651 = _mm_xor_ps(v650, (__m128)_mm_srli_si128((__m128i)v650, 2));
                              if ( (unsigned __int8)_mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                                 v651,
                                                                                 (__m128)_mm_srli_si128(
                                                                                           (__m128i)v651,
                                                                                           1))) != 127 )
                              {
                                MemoryFree(v607);
                                v588 = -1073425151;
                                goto LABEL_772;
                              }
                              v652 = (int)v1293;
                              v588 = 0;
                              v1325 = v607;
                              v653 = 0;
                              v1315 = 7312;
                              do
                              {
                                for ( i8 = 0; i8 < 0x26; ++i8 )
                                {
                                  if ( v652 == i8 )
                                    *((_QWORD *)v1340 + v653) = v607;
                                  v655 = -1;
                                  do
                                    ++v655;
                                  while ( v607[v655] );
                                  v607 += v655 + 1;
                                }
                                ++v653;
                              }
                              while ( v653 < 6 );
                              v656 = MemoryAlloc(0x18u);
                              SP<unsigned long,SP_MEM<unsigned long>>::operator=(&v1289, v656);
                              v657 = (void **)v1289;
                              if ( v1289 )
                              {
                                v658 = 0;
                                *(_OWORD *)v1289 = 0;
                                v657[2] = 0;
                                while ( 2 )
                                {
                                  LODWORD(v1279) = v658;
                                  if ( v658 >= 3 )
                                  {
                                    v646 = v1315;
                                    v1342 = (int)v1281;
                                    v1289 = 0;
                                    v1302 = (SIZE_T)v657;
LABEL_774:
                                    v670 = v1325;
                                    if ( v1325 && v646 )
                                    {
                                      do
                                      {
                                        *v670++ = 0;
                                        --v646;
                                      }
                                      while ( v646 );
                                    }
                                    SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1289);
                                    SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1325);
                                    SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&psz);
                                    if ( v588 < 0 )
                                      goto LABEL_887;
                                    v1344 = *v657;
                                    v1345 = v657[1];
                                    v1346 = v657[2];
                                    v1338 = 0;
                                    LODWORD(v1338) = 16;
                                    v122 = 0;
                                    if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int128 *, _QWORD))off_180086168)(
                                                          66,
                                                          0,
                                                          &v1338,
                                                          0) )
                                    {
                                      v671 = GetLastError();
                                      v588 = v671;
                                      if ( v671 > 0 )
                                        v588 = (unsigned __int16)v671 | 0x80070000;
                                      v1343 = 0;
                                      if ( v588 >= 0 )
                                        v588 = -2147467259;
                                      goto LABEL_888;
                                    }
                                    v672 = v472 & 0xF;
                                    v1343 = BYTE4(v1338) & 1;
                                    LODWORD(v1303) = 42;
                                    if ( v672 == 1 )
                                    {
                                      LODWORD(v1297) = 42;
                                    }
                                    else
                                    {
                                      if ( (v472 & 0xF) != 2 )
                                      {
                                        if ( (v472 & 0xF) == 3 )
                                        {
                                          LODWORD(v1297) = 225;
                                          LODWORD(v1298) = 225;
                                        }
                                        else
                                        {
                                          LODWORD(v1297) = 0;
                                          LODWORD(v1298) = 0;
                                        }
                                        goto LABEL_792;
                                      }
                                      LODWORD(v1297) = 15;
                                    }
                                    LODWORD(v1298) = 11;
LABEL_792:
                                    memset_0(v1423, 0, 0xDCu);
                                    v1424 = 220;
                                    if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _BYTE *))off_1800860E0[0])(
                                           0,
                                           0xFFFFFFFFLL,
                                           v1423) )
                                    {
                                      v673 = v1425;
                                      LODWORD(v122) = v1426;
                                      LODWORD(v1279) = v1427;
                                      if ( v1425 < 0x60u )
                                        v673 = 96;
                                    }
                                    else
                                    {
                                      LODWORD(v1279) = 0;
                                      v673 = 96;
                                    }
                                    HIDWORD(dwBytes) = v673;
                                    v674 = (const wchar_t *)pcchLength;
                                    if ( v672 == 1 )
                                      v674 = (const wchar_t *)v1291;
                                    psz = v674;
                                    memset_0(v1414, 0, 0x5Cu);
                                    v1308 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860F8[0])(
                                              0,
                                              0,
                                              1027);
                                    if ( !v1308 )
                                      goto LABEL_847;
                                    v675 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860B8)(
                                             (unsigned int)v1297,
                                             v673,
                                             72);
                                    v1414[4] = 400;
                                    v1414[0] = -v675;
                                    v1415 = 5;
                                    StringCchCopyW(v1416, 0x20u, psz);
                                    v676 = ((__int64 (__fastcall *)(_DWORD *))off_180086020[0])(v1414);
                                    if ( v676 )
                                    {
                                      v588 = 0;
                                      v1347 = v676;
                                    }
                                    else
                                    {
                                      v588 = GetLastError();
                                      v677 = v588 < 0;
                                      if ( v588 > 0 )
                                      {
                                        v588 = (unsigned __int16)v588 | 0x80070000;
                                        v677 = v588 < 0;
                                      }
                                      if ( !v677 )
                                        v588 = -2147467259;
                                    }
                                    off_180086160[0](0, v1308);
                                    if ( v588 < 0 )
                                      goto LABEL_887;
                                    v678 = (const unsigned __int16 *)pcchLength;
                                    if ( v672 == 1 )
                                      v678 = (const unsigned __int16 *)v1291;
                                    memset_0(v1417, 0, 0x5Cu);
                                    psz = (STRSAFE_PCNZWCH)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860F8[0])(
                                                             0,
                                                             0,
                                                             1027);
                                    if ( !psz )
                                      goto LABEL_847;
                                    v679 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860B8)(
                                             (unsigned int)v1298,
                                             HIDWORD(dwBytes),
                                             72);
                                    v1417[4] = 400;
                                    v1417[0] = -v679;
                                    v1418 = 5;
                                    StringCchCopyW(v1419, 0x20u, v678);
                                    v680 = ((__int64 (__fastcall *)(_DWORD *))off_180086020[0])(v1417);
                                    if ( v680 )
                                    {
                                      v588 = 0;
                                      v1348 = v680;
                                    }
                                    else
                                    {
                                      v588 = GetLastError();
                                      v681 = v588 < 0;
                                      if ( v588 > 0 )
                                      {
                                        v588 = (unsigned __int16)v588 | 0x80070000;
                                        v681 = v588 < 0;
                                      }
                                      if ( !v681 )
                                        v588 = -2147467259;
                                    }
                                    off_180086160[0](0, (int)psz);
                                    if ( v588 < 0 )
                                      goto LABEL_887;
                                    if ( v672 != 1 )
                                    {
                                      if ( v672 == 2 )
                                      {
                                        LODWORD(v122) = (int)v122 / 4;
                                        goto LABEL_824;
                                      }
                                      if ( v672 != 3 )
                                      {
                                        LODWORD(v122) = 0;
LABEL_824:
                                        v682 = 0;
                                        goto LABEL_826;
                                      }
                                    }
                                    v682 = v1279;
LABEL_826:
                                    *((_QWORD *)&v1314 + 1) = __PAIR64__(v682, v122);
                                    if ( v672 == 1 )
                                    {
                                      v683 = 150;
                                      LODWORD(v1297) = 32;
                                    }
                                    else
                                    {
                                      v683 = 0;
                                      if ( (unsigned int)(v672 - 2) < 2 )
                                      {
                                        LODWORD(v1303) = 0;
                                        LODWORD(v1297) = 0;
                                      }
                                      else
                                      {
                                        LODWORD(v1297) = 0;
                                        LODWORD(v1303) = 0;
                                      }
                                    }
                                    LODWORD(v1293) = v683;
                                    v684 = v122 - v683;
                                    v685 = v1344;
                                    v1357 = v684;
                                    v1353 = v684;
                                    psz = (STRSAFE_PCNZWCH)((__int64 (__fastcall *)(LPVOID, SIZE_T, _QWORD))off_180086078)(
                                                             v1280,
                                                             v1347,
                                                             0);
                                    v1276 = ((__int64 (__fastcall *)(LPVOID, void *, __int64, int *, int, _QWORD))off_1800860D8)(
                                              v1280,
                                              v685,
                                              0xFFFFFFFFLL,
                                              &v1351,
                                              3152,
                                              0);
                                    v588 = v1276 != 0 ? 0 : 0x80004005;
                                    if ( psz )
                                      off_180086078((WARBIRD_DELAY_LOAD *)v1280, (int)psz);
                                    if ( v1276 )
                                    {
                                      v686 = v1345;
                                      psz = (STRSAFE_PCNZWCH)((__int64 (__fastcall *)(LPVOID, SIZE_T))off_180086078)(
                                                               v1280,
                                                               v1348);
                                      v1276 = ((__int64 (__fastcall *)(LPVOID, void *, __int64, int *, int, _QWORD))off_1800860D8)(
                                                v1280,
                                                v686,
                                                0xFFFFFFFFLL,
                                                &v1355,
                                                3152,
                                                0);
                                      v588 = v1276 != 0 ? 0 : 0x80004005;
                                      if ( psz )
                                        off_180086078((WARBIRD_DELAY_LOAD *)v1280, (int)psz);
                                      if ( v1276 )
                                      {
                                        if ( v672 == 2 || v672 == 3 )
                                        {
                                          v684 = v1357;
                                          if ( v1353 > v1357 )
                                            v684 = v1353;
                                        }
                                        v588 = 0;
                                        if ( v1342 )
                                        {
                                          off_180086150((WARBIRD_DELAY_LOAD *)&v1351, (HDC)(v684 - v1353), (int)v1303);
                                          v687 = v684 - v1357;
                                        }
                                        else
                                        {
                                          off_180086150(
                                            (WARBIRD_DELAY_LOAD *)&v1351,
                                            (HDC)(unsigned int)v1293,
                                            (int)v1303);
                                          v687 = (unsigned int)v1293;
                                        }
                                        off_180086150((WARBIRD_DELAY_LOAD *)&v1355, (HDC)v687, v1354 + v1297);
                                        if ( (unsigned int)(v672 - 2) <= 1 )
                                        {
                                          *((_QWORD *)&v1314 + 1) = __PAIR64__(v1358, v684);
                                          v1350 = -5723992;
                                          goto LABEL_873;
                                        }
                                        if ( v672 != 1 )
                                          goto LABEL_873;
                                        v1350 = 0xFFFFFF;
                                        memset_0(v1420, 0, 0x5Cu);
                                        psz = (STRSAFE_PCNZWCH)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860F8[0])(
                                                                 0,
                                                                 0,
                                                                 1027);
                                        if ( !psz )
                                        {
LABEL_847:
                                          v688 = GetLastError();
                                          v122 = 0;
                                          v588 = v688;
                                          if ( v688 > 0 )
                                            v588 = (unsigned __int16)v688 | 0x80070000;
                                          if ( v588 >= 0 )
                                            v588 = -2147467259;
                                          goto LABEL_888;
                                        }
                                        v689 = ((__int64 (__fastcall *)(__int64, _QWORD))off_1800860B8)(
                                                 11,
                                                 HIDWORD(dwBytes));
                                        v1420[4] = 400;
                                        v1420[0] = -v689;
                                        v1421 = 5;
                                        StringCchCopyW(v1422, 0x20u, (const unsigned __int16 *)Size);
                                        v690 = ((__int64 (__fastcall *)(_DWORD *))off_180086020[0])(v1420);
                                        if ( v690 )
                                        {
                                          v1349 = v690;
                                        }
                                        else
                                        {
                                          v588 = GetLastError();
                                          v691 = v588 < 0;
                                          if ( v588 > 0 )
                                          {
                                            v588 = (unsigned __int16)v588 | 0x80070000;
                                            v691 = v588 < 0;
                                          }
                                          if ( !v691 )
                                            v588 = -2147467259;
                                        }
                                        off_180086160[0](0, (int)psz);
                                        if ( v588 >= 0 )
                                        {
                                          v692 = v1346;
                                          v1361 = v684;
                                          v693 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180086078)(v1280, v1349);
                                          v1276 = ((__int64 (__fastcall *)(LPVOID, void *, __int64, unsigned int *, int, _QWORD))off_1800860D8)(
                                                    v1280,
                                                    v692,
                                                    0xFFFFFFFFLL,
                                                    &v1359,
                                                    1120,
                                                    0);
                                          v588 = v1276 == 0 ? 0x80004005 : 0;
                                          if ( v693 )
                                            off_180086078((WARBIRD_DELAY_LOAD *)v1280, v693);
                                          v122 = 0;
                                          if ( !v1276 )
                                            goto LABEL_888;
                                          v694 = HIDWORD(dwBytes);
                                          v695 = v1361 + 24;
                                          v1362 = 32;
                                          if ( (int)(v1361 + 24) < 90 )
                                            v695 = 90;
                                          v1361 = v695;
                                          v1359 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860B8)(
                                                    v1359,
                                                    HIDWORD(dwBytes),
                                                    96);
                                          v1360 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860B8)(
                                                    v1360,
                                                    v694,
                                                    96);
                                          v1361 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860B8)(
                                                    v1361,
                                                    v694,
                                                    96);
                                          v1362 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800860B8)(
                                                    v1362,
                                                    v694,
                                                    96);
                                          if ( v1342 )
                                          {
                                            v696 = (unsigned int)v1351;
                                            if ( v1351 >= v1355 )
                                              v696 = (unsigned int)v1355;
                                          }
                                          else
                                          {
                                            v697 = v1353;
                                            if ( v1353 <= v1357 )
                                              v697 = v1357;
                                            v696 = v1359 + v697 - v1361;
                                          }
                                          off_180086150((WARBIRD_DELAY_LOAD *)&v1359, (HDC)v696, v1358 + 36);
LABEL_873:
                                          v698 = HIDWORD(v1314);
                                          v699 = DWORD2(v1314);
                                          v700 = v672 - 1;
                                          if ( !v700 )
                                          {
                                            v122 = 0;
                                            *(_QWORD *)&v1314 = 0;
                                            goto LABEL_880;
                                          }
                                          v701 = v700 - 1;
                                          if ( v701 )
                                          {
                                            if ( v701 != 1 )
                                              goto LABEL_879;
                                            v1412 = 0;
                                            v1410 = 0;
                                            v1411 = 0;
                                            v702 = ((__int64 (__fastcall *)(_QWORD, __int64))off_180086148[0])(0, 1);
                                            LODWORD(v1410) = 40;
                                            if ( !(unsigned int)((__int64 (__fastcall *)(__int64, __int128 *))off_180086108)(
                                                                  v702,
                                                                  &v1410) )
                                              goto LABEL_879;
                                            ((void (__fastcall *)(_QWORD, char *))off_180086140[0])(
                                              0,
                                              (char *)&v1411 + 4);
                                            ((void (__fastcall *)(_QWORD, char *))off_180086140[0])(
                                              0,
                                              (char *)&v1411 + 12);
                                            v703 = 50 * (HIDWORD(v1411) - v699) / 100;
                                            v704 = 50 * (v1412 - v698);
                                          }
                                          else
                                          {
                                            v705 = v1342;
                                            v1401 = 0;
                                            v1399 = 0;
                                            v1400 = 0;
                                            v706 = ((__int64 (__fastcall *)(_QWORD, __int64))off_180086148[0])(0, 1);
                                            LODWORD(v1399) = 40;
                                            if ( !(unsigned int)((__int64 (__fastcall *)(__int64, __int128 *))off_180086108)(
                                                                  v706,
                                                                  &v1399) )
                                              goto LABEL_879;
                                            ((void (__fastcall *)(_QWORD, char *))off_180086140[0])(
                                              0,
                                              (char *)&v1400 + 4);
                                            ((void (__fastcall *)(_QWORD, char *))off_180086140[0])(
                                              0,
                                              (char *)&v1400 + 12);
                                            if ( v705 )
                                              v703 = DWORD1(v1400) + 5 * HIDWORD(v1400) / 100;
                                            else
                                              v703 = 95 * (HIDWORD(v1400) - v699) / 100;
                                            v704 = 95 * (v1401 - v698);
                                          }
                                          LODWORD(v1314) = v703;
                                          DWORD1(v1314) = v704 / 100;
LABEL_879:
                                          v122 = 0;
LABEL_880:
                                          v588 = 0;
LABEL_888:
                                          off_180086160[0](0, (int)v1280);
                                          goto LABEL_889;
                                        }
                                      }
                                    }
LABEL_887:
                                    v122 = 0;
                                    goto LABEL_888;
                                  }
                                  v659 = 0;
                                  v1308 = v658;
                                  while ( 1 )
                                  {
                                    if ( v659 >= 6 )
                                      goto LABEL_752;
                                    if ( *((_WORD *)&v1282 + v658) == `CUxDisplayStringsT<CEmptyType>::GetAllPreferredStrings'::`2'::wStringIds[v659] )
                                      break;
                                    ++v659;
                                  }
                                  v660 = *((_QWORD *)v1340 + v659);
                                  v661 = -1;
                                  do
                                    ++v661;
                                  while ( *(_BYTE *)(v661 + v660) );
                                  v662 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, _QWORD, _DWORD))off_1800860C0[0])(
                                           65001,
                                           0,
                                           v660,
                                           (unsigned int)(v661 + 1),
                                           0,
                                           0);
                                  v1276 = v662;
                                  if ( !v662 )
                                    goto LABEL_753;
                                  v663 = MemoryAlloc(2LL * v662);
                                  v657[v1308] = v663;
                                  if ( v663 )
                                  {
                                    v664 = -1;
                                    do
                                      ++v664;
                                    while ( *(_BYTE *)(v664 + v660) );
                                    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, __int64, _QWORD, void *, unsigned int))off_1800860C0[0])(
                                           65001,
                                           0,
                                           v660,
                                           (unsigned int)(v664 + 1),
                                           v663,
                                           v1276) )
                                    {
LABEL_752:
                                      v658 = v1279 + 1;
                                      continue;
                                    }
LABEL_753:
                                    v665 = GetLastError();
                                    v588 = v665;
                                    if ( v665 > 0 )
                                      v588 = (unsigned __int16)v665 | 0x80070000;
                                    v646 = v1315;
                                    if ( v588 >= 0 )
                                      v588 = -2147467259;
                                    goto LABEL_760;
                                  }
                                  break;
                                }
                                v646 = v1315;
                              }
                              v588 = -2147024882;
LABEL_760:
                              if ( v657 )
                              {
                                for ( i9 = 0; i9 != 3; ++i9 )
                                {
                                  v667 = v657[i9];
                                  if ( v667 )
                                  {
                                    v668 = -1;
                                    do
                                      ++v668;
                                    while ( *(_WORD *)&v667[2 * v668] );
                                    for ( i10 = 2 * v668 + 2; i10; --i10 )
                                      *v667++ = 0;
                                    MemoryFree(v657[i9]);
                                  }
                                }
                                v646 = v1315;
                              }
                              goto LABEL_773;
                            }
                            v588 = GetLastError();
                            v595 = v588 < 0;
                            if ( v588 > 0 )
                            {
                              v588 = (unsigned __int16)v588 | 0x80070000;
                              v595 = v588 < 0;
                            }
                            v589 = v1279;
                            if ( !v595 )
                              v588 = -2147467259;
LABEL_705:
                            v122 = pcchLength;
                            goto LABEL_706;
                          }
                          v589 = v1279;
                        }
                        v588 = -2147024882;
                        goto LABEL_705;
                      }
                      LODWORD(v1293) = 0;
                      v573 = 0;
                      LODWORD(v1281) = 0;
                      *((_BYTE *)psz + 823) = 0;
                      memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
                      psz = v570;
                      while ( *(_BYTE *)v570 )
                      {
                        v574 = -1;
                        do
                          ++v574;
                        while ( v570[v574] );
                        v575 = 3LL * (unsigned int)v122;
                        v576 = (HMODULE *)(&WARBIRD::g_arModuleInfo + 3 * (unsigned int)v122);
                        v1280 = (LPVOID)v575;
                        if ( !GetModuleHandleExW(0, v570, v576) )
                        {
                          v573 = -1073741702;
                          break;
                        }
                        v577 = &v570[v574];
                        if ( *(_WORD *)*v576 == 23117
                          && (v579 = *((int *)*v576 + 15), (unsigned int)v579 < 0x10000000)
                          && (v580 = (char *)*v576 + v579, v580 >= (char *)*v576)
                          && *(_DWORD *)v580 == 17744 )
                        {
                          v578 = v1280;
                          if ( ((*((_WORD *)v580 + 12) - 267) & 0xFEFF) != 0 )
                          {
                            v573 = -1073741811;
                          }
                          else
                          {
                            v573 = 0;
                            *(struct WARBIRD::_MODULE_INFO near **)((char *)&WARBIRD::g_arModuleInfo
                                                                  + 8 * (_QWORD)v1280
                                                                  + 12) = (struct WARBIRD::_MODULE_INFO near *)*((_QWORD *)v580 + 17);
                            *((_DWORD *)&WARBIRD::g_arModuleInfo + 2 * (_QWORD)v578 + 2) = *((_DWORD *)v580 + 20);
                          }
                        }
                        else
                        {
                          v578 = v1280;
                          v573 = -1073741701;
                        }
                        v581 = *(_DWORD *)(v577 + 1);
                        v582 = 0;
                        v1276 = v581;
                        v570 = v577 + 3;
                        while ( 1 )
                        {
                          LODWORD(v1279) = v582;
                          if ( v582 >= v581 )
                            break;
                          v583 = -1;
                          do
                            ++v583;
                          while ( *((_BYTE *)v570 + v583) );
                          if ( v573 >= 0 )
                          {
                            v584 = (void **)GetProcAddress(
                                              (HMODULE)*(&WARBIRD::g_arModuleInfo + (_QWORD)v578),
                                              (LPCSTR)v570);
                            if ( !v584 )
                              goto LABEL_671;
                            (&WARBIRD::g_FuncAddress)[(unsigned int)v1293] = v584;
                            v582 = v1279;
                            v581 = v1276;
                          }
                          LODWORD(v1293) = (_DWORD)v1293 + 1;
                          v578 = v1280;
                          v570 = (const wchar_t *)((char *)v570 + v583 + 1);
                          ++v582;
                        }
                        LODWORD(v122) = (_DWORD)v1281 + 1;
                        LODWORD(v1281) = (_DWORD)v1281 + 1;
                      }
LABEL_671:
                      v585 = (wchar_t *)psz;
                      if ( psz )
                      {
                        v586 = GetProcessHeap();
                        HeapFree(v586, 0, v585);
                      }
                      v122 = 0;
                      if ( v573 < 0 )
                        goto LABEL_643;
                      v530 = g_WarbirdSecureFunctionsRefCount;
                    }
                    g_WarbirdSecureFunctionsRefCount = v530 + 1;
                    goto LABEL_676;
                  }
                  LODWORD(v1293) = 0;
                  v516 = 0;
                  LODWORD(v1281) = 0;
                  *((_BYTE *)psz + 823) = 0;
                  memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
                  psz = v511;
                  while ( *(_BYTE *)v511 )
                  {
                    v517 = -1;
                    do
                      ++v517;
                    while ( v511[v517] );
                    v518 = 3LL * (unsigned int)v122;
                    v519 = (HMODULE *)(&WARBIRD::g_arModuleInfo + 3 * (unsigned int)v122);
                    v1280 = (LPVOID)v518;
                    if ( !GetModuleHandleExW(0, v511, v519) )
                    {
                      v516 = -1073741702;
                      break;
                    }
                    v520 = &v511[v517];
                    if ( *(_WORD *)*v519 == 23117
                      && (v522 = *((int *)*v519 + 15), (unsigned int)v522 < 0x10000000)
                      && (v523 = (char *)*v519 + v522, v523 >= (char *)*v519)
                      && *(_DWORD *)v523 == 17744 )
                    {
                      v521 = v1280;
                      if ( ((*((_WORD *)v523 + 12) - 267) & 0xFEFF) != 0 )
                      {
                        v516 = -1073741811;
                      }
                      else
                      {
                        v516 = 0;
                        *(struct WARBIRD::_MODULE_INFO near **)((char *)&WARBIRD::g_arModuleInfo + 8 * (_QWORD)v1280
                                                                                                 + 12) = (struct WARBIRD::_MODULE_INFO near *)*((_QWORD *)v523 + 17);
                        *((_DWORD *)&WARBIRD::g_arModuleInfo + 2 * (_QWORD)v521 + 2) = *((_DWORD *)v523 + 20);
                      }
                    }
                    else
                    {
                      v521 = v1280;
                      v516 = -1073741701;
                    }
                    v524 = *(_DWORD *)(v520 + 1);
                    v525 = 0;
                    v1276 = v524;
                    v511 = v520 + 3;
                    while ( 1 )
                    {
                      LODWORD(v1279) = v525;
                      if ( v525 >= v524 )
                        break;
                      v526 = -1;
                      do
                        ++v526;
                      while ( *((_BYTE *)v511 + v526) );
                      if ( v516 >= 0 )
                      {
                        v527 = (void **)GetProcAddress(
                                          (HMODULE)*(&WARBIRD::g_arModuleInfo + (_QWORD)v521),
                                          (LPCSTR)v511);
                        if ( !v527 )
                          goto LABEL_628;
                        (&WARBIRD::g_FuncAddress)[(unsigned int)v1293] = v527;
                        v525 = v1279;
                        v524 = v1276;
                      }
                      LODWORD(v1293) = (_DWORD)v1293 + 1;
                      v521 = v1280;
                      v511 = (const wchar_t *)((char *)v511 + v526 + 1);
                      ++v525;
                    }
                    LODWORD(v122) = (_DWORD)v1281 + 1;
                    LODWORD(v1281) = (_DWORD)v1281 + 1;
                  }
LABEL_628:
                  v528 = (wchar_t *)psz;
                  if ( psz )
                  {
                    v529 = GetProcessHeap();
                    HeapFree(v529, 0, v528);
                  }
                  v122 = 0;
                  if ( v516 < 0 )
                    goto LABEL_600;
                  v473 = g_WarbirdSecureFunctionsRefCount;
                }
                g_WarbirdSecureFunctionsRefCount = v473 + 1;
                goto LABEL_633;
              }
              v1270 = v1276;
LABEL_1576:
              while ( _InterlockedCompareExchange(&g_WarbirdSecureFunctionsLock, 1, 0) )
                ;
              v1271 = g_WarbirdSecureFunctionsRefCount;
              if ( g_WarbirdSecureFunctionsRefCount > 0 )
              {
                --g_WarbirdSecureFunctionsRefCount;
                if ( v1271 == 1 )
                {
                  for ( i11 = 0; i11 != 4; ++i11 )
                  {
                    v1273 = (HMODULE)*(&WARBIRD::g_arModuleInfo + 3 * i11);
                    if ( v1273 )
                      FreeLibrary(v1273);
                  }
                  memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
                  memcpy_0(&WARBIRD::g_FuncAddress, off_18006E730, 0x170u);
                }
              }
              _InterlockedExchange(&g_WarbirdSecureFunctionsLock, 0);
              SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1308);
              if ( v83 >= 0 )
              {
                if ( v1270 == 4 )
                {
                  v2 = 0;
                  *v1334 = *v1326;
                  goto LABEL_1596;
                }
              }
              else
              {
                switch ( v83 )
                {
                  case -805306316:
                    v2 = -1073418222;
                    goto LABEL_1596;
                  case -805306139:
                  case -1073425151:
                    v2 = -1073418201;
                    goto LABEL_1596;
                  case -805306306:
                    v2 = -1073418200;
                    goto LABEL_1596;
                }
                v2 = v83;
                if ( v83 != -2147024774 )
                  goto LABEL_1596;
              }
              v2 = -1073418210;
              goto LABEL_1596;
            }
            *v81 = `WarbirdUmGetDecryptionCipher'::`2'::DecryptionCipher;
            v81[1] = xmmword_1800865D0;
            v81[2] = xmmword_1800865E0;
            v81[3] = xmmword_1800865F0;
            v81[4] = xmmword_180086600;
            v81[5] = xmmword_180086610;
            v81[6] = xmmword_180086620;
            v81[7] = xmmword_180086630;
            v81[8] = xmmword_180086640;
            v81[9] = xmmword_180086650;
            v85 = GetProcessHeap();
            v84 = HeapAlloc(v85, 8u, 8u);
            if ( !v84 )
            {
              LODWORD(dwBytes) = -1073741801;
              v84 = 0;
              goto LABEL_135;
            }
            *v84 = `WarbirdUmGetDecryptionKey'::`2'::nDecryptionKey;
            psz = (STRSAFE_PCNZWCH)__rdtsc();
            LODWORD(v1279) = 0;
            dwBytes = (unsigned int)RtlUIntAdd(4, 4, &v1279);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_135;
            v86 = RtlUIntAdd(0, (unsigned int)v1279, (char *)&dwBytes + 4);
            v83 = v86 | 0x10000000;
            LODWORD(dwBytes) = v86 | 0x10000000;
            if ( v86 < 0 )
              goto LABEL_135;
            LODWORD(v1279) = v87;
            LODWORD(dwBytes) = RtlUIntAdd(v88, 160, &v1279);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_135;
            v89 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1279, (char *)&dwBytes + 4);
            v83 = v91 | v89;
            LODWORD(dwBytes) = v91 | v89;
            if ( (v91 | v89) < 0 )
              goto LABEL_135;
            LODWORD(v1279) = 0;
            LODWORD(dwBytes) = RtlUIntAdd(v90, 8, &v1279);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_135;
            v92 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1279, (char *)&dwBytes + 4);
            v83 = v94 | v92;
            LODWORD(dwBytes) = v94 | v92;
            if ( (v94 | v92) < 0 )
              goto LABEL_135;
            LODWORD(v1279) = 0;
            LODWORD(dwBytes) = RtlUIntAdd(v93, 8, &v1279);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_135;
            v95 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1279, (char *)&dwBytes + 4);
            v83 = v98 | v95;
            LODWORD(dwBytes) = v98 | v95;
            if ( (v98 | v95) < 0 )
              goto LABEL_135;
            pcchLength = 0;
            if ( StringCchLengthW(v97, v96, &pcchLength) < 0 )
            {
              v83 = -1073741762;
LABEL_340:
              LODWORD(dwBytes) = v83;
              goto LABEL_135;
            }
            LODWORD(v1279) = v99;
            LODWORD(dwBytes) = RtlUIntAdd(v100, (unsigned int)(2 * (pcchLength + 1)), &v1279);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_135;
            v101 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1279, (char *)&dwBytes + 4);
            v83 = v101 | 0x10000000;
            LODWORD(dwBytes) = v101 | 0x10000000;
            if ( v101 < 0 )
              goto LABEL_135;
            LODWORD(v1279) = 0;
            LODWORD(dwBytes) = RtlUIntAdd(v102, v102, &v1279);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_135;
            v103 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1279, (char *)&dwBytes + 4);
            v83 = v105 | v103;
            LODWORD(dwBytes) = v105 | v103;
            if ( (v105 | v103) < 0 )
              goto LABEL_135;
            LODWORD(v1279) = 0;
            LODWORD(dwBytes) = RtlUIntAdd(v104, v104, &v1279);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_135;
            v106 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1279, (char *)&dwBytes + 4);
            v83 = v107 | v106;
            LODWORD(dwBytes) = v107 | v106;
            if ( (v107 | v106) < 0 )
              goto LABEL_135;
            HIDWORD(Src[0]) = HIDWORD(dwBytes);
            v108 = HIDWORD(dwBytes);
            v109 = GetProcessHeap();
            v110 = HeapAlloc(v109, 8u, v108);
            if ( !v110 )
            {
              v83 = -1073741801;
              goto LABEL_340;
            }
            LODWORD(v1301) = 0;
            v1300 = 0;
            v1277 = 0;
            Src[1] = v110;
            LODWORD(Src[0]) = 0;
            pcchLength = (size_t)v110;
            LODWORD(dwBytes) = RtlULongLongAdd(v110, 4, &v1301);
            v83 = dwBytes;
            if ( (dwBytes & 0x80000000) != 0LL )
              goto LABEL_131;
            if ( v110 + 2 <= (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
            {
              v114 = v1301;
              *v110 = v111;
              v115 = v111;
              *v114 = v112;
              v116 = LODWORD(Src[0]) + 1;
              LODWORD(v1301) = 0;
              ++LODWORD(Src[0]);
              v1300 = 0;
              if ( v82 )
              {
                if ( !v113 )
                  goto LABEL_129;
              }
              else if ( v113 )
              {
LABEL_129:
                v83 = -1073741811;
LABEL_130:
                LODWORD(dwBytes) = v83;
LABEL_131:
                v79 = v1304;
                goto LABEL_132;
              }
              v124 = (unsigned int *)Src[1];
              if ( Src[1] )
              {
                pcchLength = (size_t)Src[1];
                for ( i12 = 0; i12 < v116; ++i12 )
                {
                  v126 = *v124;
                  LODWORD(v1279) = 0;
                  LODWORD(dwBytes) = RtlUIntAdd(4, v126, &v1279);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_131;
                  LODWORD(dwBytes) = RtlULongLongAdd(v127, (unsigned int)v1279, &pcchLength);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_131;
                  v124 = (unsigned int *)pcchLength;
                }
                v115 = 4;
                LODWORD(dwBytes) = RtlULongLongAdd(v124, 4, &v1301);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                if ( (char *)v128 + v129 + 4 > (char *)Src[1] + HIDWORD(Src[0]) )
                  goto LABEL_162;
                *v128 = v129;
                if ( v82 )
                  memcpy_0(v1301, v82, v129);
              }
              else
              {
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, v113, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1279, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
              }
              v130 = LODWORD(Src[0]) + 1;
              LODWORD(v1301) = 0;
              ++LODWORD(Src[0]);
              v1300 = 0;
              v131 = (unsigned int *)Src[1];
              if ( Src[1] )
              {
                pcchLength = (size_t)Src[1];
                for ( i13 = 0; i13 < v130; i13 = v135 + 1 )
                {
                  v133 = *v131;
                  LODWORD(v1279) = 0;
                  LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, v133, &v1279);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_131;
                  LODWORD(dwBytes) = RtlULongLongAdd(v134, (unsigned int)v1279, &pcchLength);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_131;
                  v131 = (unsigned int *)pcchLength;
                }
                LODWORD(dwBytes) = RtlULongLongAdd(v131, v115, &v1301);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                if ( v136 + 3 > (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
                  goto LABEL_162;
                *v136 = 8;
                memcpy_0(v1301, v84, 8u);
              }
              else
              {
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, 8, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1279, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
              }
              v137 = (unsigned int *)Src[1];
              v138 = LODWORD(Src[0]) + 1;
              LODWORD(v1301) = 0;
              ++LODWORD(Src[0]);
              v1300 = 0;
              if ( Src[1] )
              {
                pcchLength = (size_t)Src[1];
                for ( i14 = 0; i14 < v138; i14 = v144 + 1 )
                {
                  v142 = *v137;
                  LODWORD(v1279) = 0;
                  LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, v142, &v1279);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_131;
                  LODWORD(dwBytes) = RtlULongLongAdd(v143, (unsigned int)v1279, &pcchLength);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_131;
                  v137 = (unsigned int *)pcchLength;
                }
                LODWORD(dwBytes) = RtlULongLongAdd(v137, v115, &v1301);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                if ( v145 + 3 > (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
                  goto LABEL_162;
                v146 = (const wchar_t **)v1301;
                v140 = psz;
                *v145 = 8;
                *v146 = v140;
              }
              else
              {
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, 8, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1279, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
              }
              v1289 = 0;
              ++LODWORD(Src[0]);
              if ( StringCchLengthW(v140, v139, &v1289) < 0 )
              {
                v83 = -1073741762;
                goto LABEL_130;
              }
              LODWORD(dwBytes) = RtlULongLongAdd(v1289, 1, &v1289);
              v83 = dwBytes;
              if ( (dwBytes & 0x80000000) != 0LL )
                goto LABEL_131;
              LODWORD(v1301) = 0;
              v1300 = 0;
              if ( !(2 * (_DWORD)v1289) )
                goto LABEL_129;
              v148 = (unsigned int *)Src[1];
              if ( Src[1] )
              {
                pcchLength = (size_t)Src[1];
                for ( i15 = 0; i15 < v147; ++i15 )
                {
                  v150 = *v148;
                  LODWORD(v1279) = 0;
                  LODWORD(dwBytes) = RtlUIntAdd(4, v150, &v1279);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_131;
                  LODWORD(dwBytes) = RtlULongLongAdd(v151, (unsigned int)v1279, &pcchLength);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_131;
                  v148 = (unsigned int *)pcchLength;
                }
                v115 = 4;
                LODWORD(dwBytes) = RtlULongLongAdd(v148, 4, &v1301);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                if ( (char *)v152 + v153 + 4 > (char *)Src[1] + HIDWORD(Src[0]) )
                  goto LABEL_162;
                v154 = v1301;
                *v152 = v153;
                memcpy_0(v154, L"WorkstationService-DomainJoinEnabled", (unsigned int)v153);
              }
              else
              {
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, (unsigned int)(2 * v1289), &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1279, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
              }
              v155 = (unsigned int *)Src[1];
              v156 = LODWORD(Src[0]) + 1;
              LODWORD(v1301) = 0;
              ++LODWORD(Src[0]);
              v1300 = 0;
              if ( Src[1] )
              {
                pcchLength = (size_t)Src[1];
                for ( i16 = 0; i16 < v156; i16 = v160 + 1 )
                {
                  v158 = *v155;
                  LODWORD(v1279) = 0;
                  LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, v158, &v1279);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_131;
                  LODWORD(dwBytes) = RtlULongLongAdd(v159, (unsigned int)v1279, &pcchLength);
                  v83 = dwBytes;
                  if ( (dwBytes & 0x80000000) != 0LL )
                    goto LABEL_131;
                  v155 = (unsigned int *)pcchLength;
                }
                LODWORD(dwBytes) = RtlULongLongAdd(v155, v115, &v1301);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                if ( v161 + 2 > (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
                  goto LABEL_162;
                v162 = v1301;
                v163 = v1306;
                *v161 = v115;
                *v162 = v163;
              }
              else
              {
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, (unsigned int)v115, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1279, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
              }
              v164 = (unsigned int *)Src[1];
              v165 = LODWORD(Src[0]) + 1;
              LODWORD(v1301) = 0;
              ++LODWORD(Src[0]);
              v1300 = 0;
              if ( !Src[1] )
              {
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, (unsigned int)v115, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(Src[0]), (unsigned int)v1279, (char *)Src + 4);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
LABEL_229:
                ++LODWORD(Src[0]);
                LODWORD(v1279) = 0;
                v83 = RtlUIntAdd((unsigned int)v115, (unsigned int)v115, &v1279);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_131;
                HIDWORD(dwBytes) = v1279;
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd(v172, 8, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                v83 = RtlUIntAdd(v173, (unsigned int)v1279, (char *)&dwBytes + 4);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_131;
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, (unsigned int)v115, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                v83 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1279, (char *)&dwBytes + 4);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_131;
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, (unsigned int)v115, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                v83 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1279, (char *)&dwBytes + 4);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_131;
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, (unsigned int)v115, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                v83 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1279, (char *)&dwBytes + 4);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_131;
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, (unsigned int)v115, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                v83 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1279, (char *)&dwBytes + 4);
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_131;
                v174 = HIDWORD(dwBytes);
                LODWORD(v1297) = 0;
                v1282 = 0;
                pcchLength = __rdtsc();
                v1310 = 8;
                LODWORD(v1283) = 0;
                v176 = RtlUIntAdd(8, HIDWORD(Src[0]), &v1310);
                if ( v176 < 0 )
                {
                  v1280 = v84;
                  v1294 = v82;
                }
                else
                {
                  v177 = (v1310 + 7) & 0xFFFFFFF8;
                  if ( v177 < v1310 )
                  {
                    v83 = -805306219;
LABEL_243:
                    LODWORD(dwBytes) = v83;
LABEL_244:
                    v79 = v1304;
                    goto LABEL_135;
                  }
                  v1310 = (v1310 + 7) & 0xFFFFFFF8;
                  v178 = v177;
                  v179 = GetProcessHeap();
                  v180 = HeapAlloc(v179, 8u, v178);
                  if ( !v180 )
                  {
                    v83 = -805306345;
                    LODWORD(dwBytes) = -805306345;
LABEL_337:
                    if ( v83 < 0 )
                      goto LABEL_244;
                    v79 = v1304;
                    if ( !(_DWORD)v1297 )
                    {
LABEL_339:
                      v83 = -1073425151;
                      goto LABEL_340;
                    }
                    if ( !v1304 )
                      goto LABEL_547;
                    pcchLength = (size_t)v1304;
                    LODWORD(dwBytes) = RtlULongLongAdd(v1304, 4, &pcchLength);
                    v83 = dwBytes;
                    if ( (dwBytes & 0x80000000) != 0LL )
                      goto LABEL_132;
                    v435 = (int *)pcchLength;
                    if ( !*v79 )
                      v435 = 0;
                    if ( *v79 == (_DWORD)v434 )
                    {
                      v83 = *v435;
                      LODWORD(dwBytes) = v83;
                      if ( v83 == -805306333 )
                      {
                        v1277 = -2147024774;
                      }
                      else
                      {
                        v1277 = v83;
                        if ( v83 != -2147024774 && v83 < 0 )
                          goto LABEL_135;
                      }
                      if ( v432 != 6 )
                        goto LABEL_339;
                      v1284 = v431;
                      for ( i17 = 0; i17 < v433; i17 = v438 + 1 )
                      {
                        LODWORD(dwBytes) = RtlULongLongAdd(v431, v434, &v1284);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_132;
                        LODWORD(dwBytes) = RtlULongLongAdd(v1284, v437, &v1284);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_132;
                        v431 = v1284;
                        v433 = 1;
                      }
                      LODWORD(dwBytes) = RtlULongLongAdd(v431, v434, &v1284);
                      v83 = dwBytes;
                      if ( (dwBytes & 0x80000000) != 0LL )
                        goto LABEL_132;
                      v441 = (size_t *)v1284;
                      if ( !v439 )
                        v441 = 0;
                      if ( v439 == 8 )
                      {
                        if ( !v79 )
                        {
LABEL_547:
                          v83 = -1073741811;
LABEL_573:
                          LODWORD(dwBytes) = v83;
                          goto LABEL_132;
                        }
                        v442 = *v441;
                        v443 = v79;
                        v1284 = v79;
                        v444 = 0;
                        pcchLength = v442;
                        while ( v444 < 2 )
                        {
                          LODWORD(dwBytes) = RtlULongLongAdd(v443, v440, &v1284);
                          v83 = dwBytes;
                          if ( (dwBytes & 0x80000000) != 0LL )
                            goto LABEL_132;
                          LODWORD(dwBytes) = RtlULongLongAdd(v1284, v445, &v1284);
                          v83 = dwBytes;
                          if ( (dwBytes & 0x80000000) != 0LL )
                            goto LABEL_132;
                          v443 = v1284;
                          v444 = v446 + 1;
                        }
                        LODWORD(dwBytes) = RtlULongLongAdd(v443, v440, &v1284);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_132;
                        v449 = (int *)v1284;
                        if ( !v447 )
                          v449 = 0;
                        if ( v447 == (_DWORD)v448 )
                        {
                          v450 = *v449;
                          v451 = v79;
                          v1284 = v79;
                          LODWORD(v1283) = v450;
                          while ( 1 )
                          {
                            v452 = RtlULongLongAdd(v451, v448, &v1284);
                            LODWORD(dwBytes) = v452;
                            v83 = v452;
                            if ( v454 >= 3 )
                              break;
                            if ( v452 < 0 )
                              goto LABEL_132;
                            LODWORD(dwBytes) = RtlULongLongAdd(v1284, v453, &v1284);
                            v83 = dwBytes;
                            if ( (dwBytes & 0x80000000) != 0LL )
                              goto LABEL_132;
                            v451 = v1284;
                          }
                          if ( v452 >= 0 )
                          {
                            v455 = v79;
                            v456 = 0;
                            v1284 = v79;
                            while ( v456 < 4 )
                            {
                              v457 = *v455;
                              LODWORD(dwBytes) = RtlULongLongAdd(v455, 4, &v1284);
                              v83 = dwBytes;
                              if ( (dwBytes & 0x80000000) != 0LL )
                                goto LABEL_132;
                              LODWORD(dwBytes) = RtlULongLongAdd(v1284, v457, &v1284);
                              v83 = dwBytes;
                              if ( (dwBytes & 0x80000000) != 0LL )
                                goto LABEL_132;
                              v455 = (unsigned int *)v1284;
                              v456 = v458 + 1;
                            }
                            LODWORD(dwBytes) = RtlULongLongAdd(v455, 4, &v1284);
                            v83 = dwBytes;
                            if ( (dwBytes & 0x80000000) == 0LL )
                            {
                              v460 = v1284;
                              if ( !v459 )
                                v460 = 0;
                              if ( v459 == 4 )
                              {
                                v461 = 0;
                                v462 = v79;
                                LODWORD(v1290) = *v460;
                                v1284 = v79;
                                while ( v461 < 5 )
                                {
                                  v463 = *v462;
                                  LODWORD(dwBytes) = RtlULongLongAdd(v462, 4, &v1284);
                                  v83 = dwBytes;
                                  if ( (dwBytes & 0x80000000) != 0LL )
                                    goto LABEL_135;
                                  LODWORD(dwBytes) = RtlULongLongAdd(v1284, v463, &v1284);
                                  v83 = dwBytes;
                                  if ( (dwBytes & 0x80000000) != 0LL )
                                    goto LABEL_135;
                                  v462 = (unsigned int *)v1284;
                                  v461 = v464 + 1;
                                }
                                v465 = RtlULongLongAdd(v462, 4, &v1284);
                                LODWORD(dwBytes) = v465;
                                v83 = v465;
                                if ( v465 < 0 )
                                {
                                  LODWORD(dwBytes) = v465;
                                  goto LABEL_135;
                                }
                                v469 = (int *)v1284;
                                if ( !v466 )
                                  v469 = 0;
                                if ( v466 != 4 )
                                {
                                  v83 = -1073741789;
                                  goto LABEL_340;
                                }
                                if ( psz == (STRSAFE_PCNZWCH)pcchLength )
                                {
                                  v470 = *v469;
                                  v1313 = (unsigned int)v1283;
                                  LODWORD(v1306) = v470;
                                  if ( (unsigned int)v1290 > 4 || (unsigned int)v467 > 4 )
                                  {
                                    v83 = -2147024774;
                                    goto LABEL_340;
                                  }
                                  memcpy_0(lpMem, v468, v467);
LABEL_133:
                                  if ( v1277 )
                                  {
                                    v83 = v1277;
                                    LODWORD(dwBytes) = v1277;
                                  }
                                  goto LABEL_135;
                                }
                                goto LABEL_339;
                              }
                              goto LABEL_572;
                            }
                          }
LABEL_132:
                          if ( v83 < 0 )
                            goto LABEL_135;
                          goto LABEL_133;
                        }
                      }
                    }
LABEL_572:
                    v83 = -1073741789;
                    goto LABEL_573;
                  }
                  v1294 = v82;
                  v1280 = v84;
                  HIDWORD(dwBytes) = v174;
                  v1289 = (size_t)v180;
                  *v180 = Src[0];
                  v176 = RtlULongLongAdd(v180, 4, &v1289);
                  if ( v176 < 0
                    || (v182 = v1289,
                        *(_DWORD *)v1289 = HIDWORD(Src[0]),
                        v176 = RtlULongLongAdd(v182, v181, &v1289),
                        v176 < 0) )
                  {
                    v1294 = v82;
                    v1280 = v84;
                    HIDWORD(dwBytes) = v174;
                    v183 = GetProcessHeap();
                    HeapFree(v183, 0, v180);
                    v175 = (unsigned int)v1283;
                  }
                  else
                  {
                    *(_QWORD *)((char *)v180 + v1310 - 8) = pcchLength;
                    memcpy_0((void *)v1289, Src[1], HIDWORD(Src[0]));
                    v175 = v1310;
                    v1282 = v180;
                  }
                }
                v83 = v176 | 0x10000000;
                pcchLength = 0;
                LODWORD(dwBytes) = v83;
                v184 = 0;
                v185 = 0;
                v1290 = 0;
                v1281 = 0;
                v1296 = 0;
                if ( v83 < 0 )
                  goto LABEL_312;
                v186 = (unsigned __int8 *)v1282;
                if ( !v1282 )
                {
                  v83 = -805306355;
                  goto LABEL_243;
                }
                v1302 = v175;
                if ( !v175
                  || (Size = v175 + 8LL,
                      v187 = MemoryAlloc(Size),
                      v188 = 0,
                      v1291 = (SIZE_T)v187,
                      (v189 = (size_t)v187) == 0) )
                {
                  v83 = -805306367;
                  LODWORD(dwBytes) = -805306367;
                  goto LABEL_314;
                }
                v190 = v1302;
                v191 = 0;
                v1303 = 0;
                v192 = 0;
                v1278 = 0;
                if ( v1302 )
                {
                  do
                    v191 ^= v186[v192++];
                  while ( v192 < v1302 );
                  v1278 = v191;
                }
                v1289 = v189;
                v193 = v186;
                v1288 = (void *)0xC81ECB17B1B54A58LL;
                v1284 = v186;
                v194 = v1302 & 7;
                if ( (v1302 & 7) != 0 )
                {
                  LODWORD(v1293) = 0;
                  LODWORD(dwBytes) = 0;
                  v195 = 0;
                  v196 = 0;
                  do
                  {
                    v197 = *v193++;
                    LODWORD(v1279) = 8 * v188;
                    if ( v188 >= 4 )
                      v195 |= v197 << (56 - v1279);
                    else
                      v196 |= v197 << (24 - v1279);
                    ++v188;
                  }
                  while ( (int)v188 < v194 );
                  v190 = v1302;
                  LODWORD(dwBytes) = v196;
                  LODWORD(v1293) = v195;
                  v1284 = v193;
                  v1282 = v186;
                  v1280 = v84;
                  v1294 = v82;
                  LODWORD(v1298) = 0;
                  v188 = v196 ^ 0xB17A307A;
                  v198 = v195 ^ 0x42F6B18D;
                  v199 = v196 ^ 0xB17A307A;
                  v200 = v198;
                  if ( (v1302 & 7) != 0 )
                  {
                    v201 = (_BYTE *)v1289;
                    do
                    {
                      v1289 = (size_t)(v201 + 1);
                      if ( (unsigned int)v1298 >= 4 )
                      {
                        v200 = __ROR4__(v200, 24);
                        v202 = v200;
                      }
                      else
                      {
                        v199 = __ROR4__(v199, 24);
                        v202 = v199;
                      }
                      LODWORD(v1298) = v1298 + 1;
                      *v201 = v202;
                      v201 = (_BYTE *)v1289;
                    }
                    while ( (int)v1298 < v194 );
                  }
                  if ( (unsigned int)v194 <= 4 )
                  {
                    v203 = 0;
                    if ( (unsigned int)v194 < 4 )
                      v188 = v188 >> (8 * (4 - v194)) << (8 * (4 - v194));
                  }
                  else
                  {
                    v203 = v198 >> (8 * (8 - v194)) << (8 * (8 - v194));
                  }
                  v193 = (unsigned __int8 *)v1284;
                }
                else
                {
                  v203 = -1;
                  LODWORD(dwBytes) = 0;
                  LODWORD(v1293) = 0;
                }
                if ( v190 >> 3 )
                {
                  v204 = v190 >> 3;
                  v205 = WORD2(v1288);
                  v206 = (_BYTE *)v1289;
                  v207 = (int)v1293;
                  LODWORD(v1283) = WORD1(v1288);
                  v208 = dwBytes;
                  v1279 = 0;
                  do
                  {
                    v209 = v193[3] | ((v193[2] | ((v193[1] | (*v193 << 8)) << 8)) << 8);
                    v210 = *((unsigned __int8 *)v1284 + 7)
                         | ((*((unsigned __int8 *)v1284 + 6) | ((*((unsigned __int8 *)v1284 + 5) | (v193[4] << 8)) << 8)) << 8);
                    v1284 = (char *)v1284 + 8;
                    v211 = v203 ^ v210;
                    v212 = v188 ^ v209 ^ ((v203 ^ v210) - 19032);
                    v213 = v212 ^ HIDWORD(v1288);
                    v214 = v211 ^ (__ROR4__(v212 ^ HIDWORD(v1288), 7) + WORD1(v1288) * __ROR4__(v212, 15));
                    v215 = v213 ^ (v205 * __ROR4__(v214 - 1313519016, 9) - __ROR4__(v214, 10));
                    v216 = v214 ^ (__ROR4__(v215, 27) + HIWORD(v1288) * __ROR4__(v215 ^ v205, 28));
                    v217 = v215 ^ (HIDWORD(v1288) - (v216 ^ 0xB1B54A58));
                    v218 = v216 ^ (WORD1(v1288) * (v217 - 19032) - (v217 >> 6));
                    v219 = v217 ^ (19032 * (v205 ^ __ROR4__(v218, 15)));
                    v220 = v218 ^ (v205 * (HIWORD(v1288) + __ROR4__(~v219, 3)));
                    v221 = v219 ^ (v220 - 19032 - HIDWORD(v1288));
                    v222 = v220 ^ ((_DWORD)v1283 * (v221 ^ HIWORD(v1288))) ^ __ROR4__(v221, 10);
                    v223 = v221 ^ __ROR4__(v222, 3) ^ (v205 * __ROR4__(v222 ^ 0x4A58, 26));
                    v224 = v222 ^ (19032 * (__ROR4__(v223, 15) - HIWORD(v1288)));
                    v225 = v223
                         ^ (19032 * (HIWORD(v1288) ^ v224))
                         ^ ((v224 ^ (v224 >> 14)) >> 1)
                         ^ (19032 * ((8 * (v224 - v205)) | ((v224 - v205) >> 29)));
                    v226 = v224 ^ (WORD1(v1288) * (v225 - v205) - (v225 >> 13));
                    v227 = v225 ^ __ROR4__(v226, 11) ^ (v205 * __ROR4__(-1313519016 - v226, 9));
                    v228 = v226 ^ (v227 - HIWORD(v1288) + 1313519016);
                    v229 = v227 ^ (19032 * (v228 ^ WORD1(v1288)) - __ROR4__(v228, 7));
                    v230 = v228 ^ (WORD1(v1288) * __ROR4__(HIWORD(v1288) ^ v229, 28) - __ROR4__(v229, 16));
                    v231 = v229 ^ (__ROR4__(v230, 4) + v205 * __ROR4__(-1313519016 - v230, 10));
                    v232 = v230 ^ __ROR4__(v231, 9) ^ (HIWORD(v1288) * __ROR4__(v231 + 1313519016, 4));
                    v233 = v231 ^ (19032 * __ROR4__(HIDWORD(v1288) ^ v232, 24) - __ROR4__(v232, 30));
                    v234 = v232 ^ (WORD1(v1288) * __ROR4__(HIDWORD(v1288) - v233, 11) - __ROR4__(v233, 12));
                    v235 = v207 ^ v234 ^ HIDWORD(v1288) ^ 0xB1B54A58;
                    v207 = v210;
                    v193 = (unsigned __int8 *)v1284;
                    v236 = v233 ^ (v234 >> 8) ^ (v205 * (v234 ^ WORD1(v1288)));
                    v188 = v236 ^ v208;
                    v203 = v236 ^ v235;
                    v206[3] = v236 ^ v208;
                    LOBYTE(v219) = __ROR4__(v236 ^ v208, 8);
                    v208 = v209;
                    v206[7] = v203;
                    v206[2] = v219;
                    v206[6] = __ROR4__(v203, 8);
                    v206[1] = __ROR4__(v188, 16);
                    v206[5] = __ROR4__(v203, 16);
                    *v206 = __ROR4__(v188, 24);
                    v206[4] = __ROR4__(v203, 24);
                    v206 += 8;
                    ++v1279;
                  }
                  while ( v1279 < v204 );
                  v185 = v1290;
                  v191 = v1278;
                  v184 = (unsigned int *)v1290;
                  v82 = v1294;
                  v84 = v1280;
                  v186 = (unsigned __int8 *)v1282;
                  v190 = v1302;
                }
                *(_QWORD *)(v1291 + v190) = v191;
                v237 = GetProcessHeap();
                v238 = HeapAlloc(v237, 8u, 0x30u);
                v1280 = v238;
                if ( v238 )
                {
                  *v238 = Size;
                  v240 = GetProcessHeap();
                  v241 = HeapAlloc(v240, 8u, (unsigned int)Size);
                  if ( !v241 )
                    goto LABEL_287;
                  v1282 = v186;
                  v242 = v1280;
                  *((_QWORD *)v1280 + 1) = v241;
                  memcpy_0(v241, (const void *)v1291, (unsigned int)Size);
                  v242[4] = 160;
                  v243 = GetProcessHeap();
                  v244 = HeapAlloc(v243, 8u, 0xA0u);
                  if ( !v244 )
                    goto LABEL_287;
                  *((_QWORD *)v242 + 3) = v244;
                  *v244 = `WarbirdUmGetEncryptionCipher'::`2'::EncryptionCipher;
                  v244[1] = xmmword_180086520;
                  v244[2] = xmmword_180086530;
                  v244[3] = xmmword_180086540;
                  v244[4] = xmmword_180086550;
                  v244[5] = xmmword_180086560;
                  v244[6] = xmmword_180086570;
                  v244[7] = xmmword_180086580;
                  v244[8] = xmmword_180086590;
                  v244[9] = xmmword_1800865A0;
                  v242[8] = 8;
                  v245 = GetProcessHeap();
                  v246 = HeapAlloc(v245, 8u, 8u);
                  if ( v246 )
                  {
                    *((_QWORD *)v242 + 5) = v246;
                    *v246 = `WarbirdUmGetEncryptionKey'::`2'::nEncryptionKey;
                    v1303 = v242;
                    v239 = 0;
                    v184 = (unsigned int *)v1303;
                    v1303 = 0;
                  }
                  else
                  {
LABEL_287:
                    v239 = -1073741801;
                    v247 = v1280;
                    Size = *((_QWORD *)v1280 + 1);
                    if ( Size )
                    {
                      v248 = GetProcessHeap();
                      HeapFree(v248, 0, (LPVOID)Size);
                      v247 = v1280;
                      *((_QWORD *)v1280 + 1) = 0;
                    }
                    Size = v247[3];
                    if ( Size )
                    {
                      v249 = GetProcessHeap();
                      HeapFree(v249, 0, (LPVOID)Size);
                      v247 = v1280;
                      *((_QWORD *)v1280 + 3) = 0;
                    }
                    Size = v247[5];
                    if ( Size )
                    {
                      v250 = GetProcessHeap();
                      HeapFree(v250, 0, (LPVOID)Size);
                      *((_QWORD *)v1280 + 5) = 0;
                    }
                    v251 = GetProcessHeap();
                    HeapFree(v251, 0, v1280);
                  }
                }
                else
                {
                  v239 = -1073741801;
                }
                v252 = GetProcessHeap();
                HeapFree(v252, 0, (LPVOID)v1291);
                v253 = v1303;
                if ( v1303 )
                {
                  v1291 = *((_QWORD *)v1303 + 1);
                  if ( v1291 )
                  {
                    v254 = GetProcessHeap();
                    HeapFree(v254, 0, (LPVOID)v1291);
                    v253 = v1303;
                    *((_QWORD *)v1303 + 1) = 0;
                  }
                  v1291 = v253[3];
                  if ( v1291 )
                  {
                    v255 = GetProcessHeap();
                    HeapFree(v255, 0, (LPVOID)v1291);
                    v253 = v1303;
                    *((_QWORD *)v1303 + 3) = 0;
                  }
                  v1291 = v253[5];
                  if ( v1291 )
                  {
                    v256 = GetProcessHeap();
                    HeapFree(v256, 0, (LPVOID)v1291);
                    *((_QWORD *)v1303 + 5) = 0;
                  }
                  v257 = GetProcessHeap();
                  HeapFree(v257, 0, v1303);
                }
                v83 = v239 | 0x10000000;
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                {
                  v268 = v1282;
LABEL_313:
                  if ( !v268 )
                  {
LABEL_315:
                    if ( v184 )
                    {
                      v1291 = *((_QWORD *)v184 + 1);
                      if ( v1291 )
                      {
                        v270 = GetProcessHeap();
                        HeapFree(v270, 0, (LPVOID)v1291);
                        *((_QWORD *)v184 + 1) = 0;
                      }
                      v1291 = *((_QWORD *)v184 + 3);
                      if ( v1291 )
                      {
                        v271 = GetProcessHeap();
                        HeapFree(v271, 0, (LPVOID)v1291);
                        *((_QWORD *)v184 + 3) = 0;
                      }
                      v1291 = *((_QWORD *)v184 + 5);
                      if ( v1291 )
                      {
                        v272 = GetProcessHeap();
                        HeapFree(v272, 0, (LPVOID)v1291);
                        *((_QWORD *)v184 + 5) = 0;
                      }
                      v273 = GetProcessHeap();
                      HeapFree(v273, 0, v184);
                    }
                    v274 = (void *)pcchLength;
                    if ( pcchLength )
                    {
                      v275 = GetProcessHeap();
                      HeapFree(v275, 0, v274);
                    }
                    if ( v185 )
                    {
                      v276 = GetProcessHeap();
                      HeapFree(v276, 0, v185);
                    }
                    v277 = v1281;
                    if ( v1281 )
                    {
                      v278 = (void *)*((_QWORD *)v1281 + 1);
                      if ( v278 )
                      {
                        v279 = GetProcessHeap();
                        HeapFree(v279, 0, v278);
                        v277[1] = 0;
                      }
                      v280 = (void *)v277[3];
                      if ( v280 )
                      {
                        v281 = GetProcessHeap();
                        HeapFree(v281, 0, v280);
                        v277[3] = 0;
                      }
                      v282 = (void *)v277[5];
                      if ( v282 )
                      {
                        v283 = GetProcessHeap();
                        HeapFree(v283, 0, v282);
                        v277[5] = 0;
                      }
                      v284 = GetProcessHeap();
                      HeapFree(v284, 0, v277);
                    }
                    v285 = v1296;
                    if ( v1296 )
                    {
                      v286 = GetProcessHeap();
                      HeapFree(v286, 0, v285);
                    }
                    goto LABEL_337;
                  }
LABEL_314:
                  v269 = GetProcessHeap();
                  HeapFree(v269, 0, v1282);
                  goto LABEL_315;
                }
                v258 = *v184;
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = 4;
                v260 = RtlUIntAdd(4, v258, &dwBytes);
                if ( v260 >= 0 )
                {
                  v260 = RtlUIntAdd((unsigned int)dwBytes, v259, &dwBytes);
                  if ( v260 >= 0 )
                  {
                    v261 = v184[4];
                    v1291 = (SIZE_T)(v184 + 4);
                    v260 = RtlUIntAdd((unsigned int)dwBytes, v261, &dwBytes);
                    if ( v260 >= 0 )
                    {
                      v260 = RtlUIntAdd((unsigned int)dwBytes, v262, &dwBytes);
                      if ( v260 >= 0 )
                      {
                        v263 = v184[8];
                        Size = (SIZE_T)(v184 + 8);
                        v260 = RtlUIntAdd((unsigned int)dwBytes, v263, &dwBytes);
                        if ( v260 >= 0 )
                        {
                          v1292 = (__int64)v184;
                          v264 = dwBytes;
                          v265 = GetProcessHeap();
                          v266 = HeapAlloc(v265, 8u, v264);
                          v184 = (unsigned int *)v1292;
                          v267 = v266;
                          v1280 = v266;
                          if ( !v266 )
                          {
                            v83 = -805306345;
LABEL_311:
                            LODWORD(dwBytes) = v83;
LABEL_312:
                            v268 = v1282;
                            goto LABEL_313;
                          }
                          v287 = *(_DWORD *)v1292;
                          v1283 = v267;
                          *v267 = v287;
                          v260 = RtlULongLongAdd(v267, 4, &v1283);
                          if ( v260 < 0 )
                          {
                            v1282 = v289;
                            HIDWORD(dwBytes) = v290;
                            v1280 = v288;
                          }
                          else
                          {
                            memcpy_0(v1283, *((const void **)v184 + 1), *v184);
                            v260 = RtlULongLongAdd(v1283, *v184, &v1283);
                            if ( v260 >= 0 )
                            {
                              v291 = v1283;
                              *(_DWORD *)v1283 = *(_DWORD *)v1291;
                              v260 = RtlULongLongAdd(v291, 4, &v1283);
                              if ( v260 >= 0 )
                              {
                                memcpy_0(v1283, *((const void **)v184 + 3), *v292);
                                v260 = RtlULongLongAdd(v1283, *(unsigned int *)v1291, &v1283);
                                if ( v260 >= 0 )
                                {
                                  v293 = v1283;
                                  *(_DWORD *)v1283 = *(_DWORD *)Size;
                                  v260 = RtlULongLongAdd(v293, 4, &v1283);
                                  if ( v260 >= 0 )
                                  {
                                    memcpy_0(v1283, *((const void **)v184 + 5), *v294);
                                    v260 = RtlULongLongAdd(v1283, *(unsigned int *)Size, &v1283);
                                    if ( v260 >= 0 )
                                    {
                                      pcchLength = (size_t)v1280;
                                      LODWORD(v1279) = dwBytes;
                                      goto LABEL_352;
                                    }
                                  }
                                }
                              }
                            }
                          }
                          v295 = GetProcessHeap();
                          HeapFree(v295, 0, v1280);
                        }
                      }
                    }
                  }
                }
LABEL_352:
                v83 = v260 | 0x10000000;
                LODWORD(dwBytes) = v83;
                if ( v83 < 0 )
                  goto LABEL_312;
                v1316 = 8;
                v296 = RtlUIntAdd(8, HIDWORD(dwBytes), &v1316);
                v83 = v296 | 0x10000000;
                LODWORD(dwBytes) = v296 | 0x10000000;
                if ( v296 < 0 )
                  goto LABEL_312;
                v297 = (v1316 + 7) & 0xFFFFFFF8;
                if ( (unsigned int)v297 < v1316 )
                {
                  v83 = -1073741675;
                  goto LABEL_311;
                }
                v1323 = (v1316 + 7) & 0xFFFFFFF8;
                LODWORD(dwBytes) = RtlUIntAdd(v297, 8, &v1323);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_312;
                v300 = Src[1];
                v301 = v299;
                v1294 = v82;
                v1280 = v84;
                v1282 = v298;
                v1292 = (__int64)v184;
                LODWORD(v1298) = v299;
                if ( Src[1] )
                {
                  v1292 = (__int64)v184;
                  v1282 = v298;
                  v1280 = v84;
                  v1294 = v82;
                  if ( LODWORD(Src[0]) > 1 )
                  {
                    v1284 = Src[1];
                    while ( !v299 )
                    {
                      LODWORD(dwBytes) = RtlULongLongAdd(v300, 4, &v1284);
                      v83 = dwBytes;
                      if ( (dwBytes & 0x80000000) != 0LL )
                        goto LABEL_367;
                      LODWORD(dwBytes) = RtlULongLongAdd(v1284, v302, &v1284);
                      v83 = dwBytes;
                      if ( (dwBytes & 0x80000000) != 0LL )
                        goto LABEL_367;
                      v300 = v1284;
                      v299 = v303 + 1;
                    }
                    LODWORD(v1283) = *v300;
                    LODWORD(dwBytes) = RtlULongLongAdd(v300, 4, &v1284);
                    v83 = dwBytes;
                    if ( (dwBytes & 0x80000000) != 0LL )
                      goto LABEL_367;
                    v304 = Src[1];
                    if ( Src[1] && LODWORD(Src[0]) > 2 )
                    {
                      v1284 = Src[1];
                      for ( i18 = 0; i18 < 2; i18 = v310 + 1 )
                      {
                        LODWORD(dwBytes) = RtlULongLongAdd(v304, 4, &v1284);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_367;
                        LODWORD(dwBytes) = RtlULongLongAdd(v1284, v309, &v1284);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_367;
                        v304 = v1284;
                      }
                      LODWORD(dwBytes) = RtlULongLongAdd(v304, 4, &v1284);
                      v83 = dwBytes;
                      if ( (dwBytes & 0x80000000) == 0LL )
                      {
                        LODWORD(v1298) = v311;
                        HIDWORD(dwBytes) = 4;
                        LODWORD(dwBytes) = RtlUIntAdd(4, v1323, (char *)&dwBytes + 4);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL )
                          goto LABEL_385;
                        LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v312, (char *)&dwBytes + 4);
                        v83 = dwBytes;
                        if ( (dwBytes & 0x80000000) != 0LL
                          || (LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1283, (char *)&dwBytes + 4),
                              v83 = dwBytes,
                              (dwBytes & 0x80000000) != 0LL)
                          || (LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4),
                              v83 = dwBytes,
                              (dwBytes & 0x80000000) != 0LL)
                          || (LODWORD(dwBytes) = RtlUIntAdd(HIDWORD(dwBytes), v313, (char *)&dwBytes + 4),
                              v83 = dwBytes,
                              (dwBytes & 0x80000000) != 0LL) )
                        {
LABEL_385:
                          if ( v83 < 0 )
                            goto LABEL_312;
                        }
                        else
                        {
                          v301 = HIDWORD(dwBytes);
                          LODWORD(v1298) = HIDWORD(dwBytes);
                        }
                        if ( v301 > 0x400000 )
                        {
                          v83 = -2147418113;
                          goto LABEL_311;
                        }
LABEL_368:
                        v305 = v301;
                        v306 = GetProcessHeap();
                        v307 = HeapAlloc(v306, 8u, v305);
                        v185 = v307;
                        if ( !v307 )
                        {
                          v83 = -805306345;
                          v185 = 0;
LABEL_370:
                          LODWORD(dwBytes) = v83;
LABEL_371:
                          v184 = (unsigned int *)v1292;
                          goto LABEL_312;
                        }
                        phModule = 0;
                        v1329 = 0;
                        v1330 = 0;
                        if ( !pcchLength )
                        {
                          v83 = -2147024809;
                          goto LABEL_370;
                        }
                        LODWORD(v1330) = v1279;
                        *(_QWORD *)&v1329 = pcchLength;
                        *(_QWORD *)((char *)&v1330 + 4) = (unsigned int)v1298;
                        *((_QWORD *)&v1329 + 1) = v307;
                        if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                          && (v315 = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                        {
                          v316 = ((__int64 (__fastcall *)(__int64, __int128 *))v315)(134, &v1329);
                          v83 = v316 | 0x10000000;
                          LODWORD(dwBytes) = v316 | 0x10000000;
                          if ( v316 >= 0 )
                          {
                            v317 = DWORD1(v1330);
                            goto LABEL_402;
                          }
                        }
                        else
                        {
                          v314 = GetLastError();
                          LODWORD(dwBytes) = v314;
                          v83 = v314;
                          if ( v314 > 0 )
                          {
                            v83 = (unsigned __int16)v314 | 0x80070000;
                            LODWORD(dwBytes) = v83;
                          }
                          if ( v83 >= 0 )
                          {
                            v83 = -2147467259;
                            goto LABEL_370;
                          }
                        }
                        if ( v83 == -805306333 )
                        {
                          v83 = -2147024774;
                          goto LABEL_370;
                        }
                        if ( v83 < 0 )
                          goto LABEL_371;
                        v317 = v1298;
LABEL_402:
                        HIDWORD(dwBytes) = 0;
                        v1288 = v185;
                        if ( v317 < 4 )
                        {
LABEL_403:
                          v83 = -805306306;
                          goto LABEL_370;
                        }
                        v318 = (unsigned int)*v185;
                        LODWORD(v1283) = *v185;
                        v320 = RtlULongLongAdd(v185, 4, &v1288);
                        if ( v320 >= 0 )
                        {
                          v320 = RtlUIntAdd(0, 4, (char *)&dwBytes + 4);
                          if ( v320 >= 0 )
                          {
                            if ( v321 - HIDWORD(dwBytes) < (unsigned int)v318 )
                              goto LABEL_403;
                            Size = (SIZE_T)v1288;
                            v1291 = v318;
                            v320 = RtlULongLongAdd(v1288, (unsigned int)v318, &v1288);
                            if ( v320 >= 0 )
                            {
                              v320 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v318, (char *)&dwBytes + 4);
                              if ( v320 >= 0 )
                              {
                                if ( (unsigned int)(v322 - HIDWORD(dwBytes)) < 4 )
                                  goto LABEL_403;
                                LODWORD(v1290) = *(_DWORD *)v1288;
                                v320 = RtlULongLongAdd(v1288, 4, &v1288);
                                if ( v320 >= 0 )
                                {
                                  v320 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                  if ( v320 >= 0 )
                                  {
                                    if ( v323 - HIDWORD(dwBytes) < (unsigned int)v324 )
                                      goto LABEL_403;
                                    v1289 = (size_t)v1288;
                                    v1302 = v324;
                                    v320 = RtlULongLongAdd(v1288, (unsigned int)v324, &v1288);
                                    if ( v320 >= 0 )
                                    {
                                      v320 = RtlUIntAdd(HIDWORD(dwBytes), v325, (char *)&dwBytes + 4);
                                      if ( v320 >= 0 )
                                      {
                                        if ( (unsigned int)(v326 - HIDWORD(dwBytes)) < 4 )
                                          goto LABEL_403;
                                        LODWORD(v1279) = *(_DWORD *)v1288;
                                        v320 = RtlULongLongAdd(v1288, 4, &v1288);
                                        if ( v320 >= 0 )
                                        {
                                          v320 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                          if ( v320 >= 0 )
                                          {
                                            if ( v327 - HIDWORD(dwBytes) < v328 )
                                              goto LABEL_403;
                                            v320 = RtlUIntAdd(HIDWORD(dwBytes), v328, (char *)&dwBytes + 4);
                                            if ( v320 >= 0 )
                                            {
                                              if ( v329 != HIDWORD(dwBytes)
                                                || (unsigned int)(v318 + v330 + v331) + 12LL != v329 )
                                              {
                                                goto LABEL_403;
                                              }
                                              v332 = GetProcessHeap();
                                              v333 = HeapAlloc(v332, 8u, 0x30u);
                                              v184 = (unsigned int *)v1292;
                                              v319 = 0;
                                              v334 = v333 == 0;
                                              v1281 = v333;
                                              v335 = v333;
                                              v268 = v1282;
                                              if ( v334 )
                                              {
                                                v83 = -805306345;
                                                v1281 = 0;
                                                LODWORD(dwBytes) = -805306345;
                                                goto LABEL_313;
                                              }
                                              v1294 = v82;
                                              v1280 = v84;
                                              v1284 = 0;
                                              if ( Size )
                                              {
                                                *(_DWORD *)v335 = (_DWORD)v1283;
                                                v336 = GetProcessHeap();
                                                v337 = HeapAlloc(v336, 8u, v1291);
                                                if ( !v337 )
                                                {
LABEL_435:
                                                  v345 = v1281;
                                                  v320 = -1073741801;
                                                  v1290 = v185;
                                                  v1291 = *((_QWORD *)v1281 + 1);
                                                  if ( v1291 )
                                                  {
                                                    v346 = GetProcessHeap();
                                                    HeapFree(v346, 0, (LPVOID)v1291);
                                                    v345 = v1281;
                                                    *((_QWORD *)v1281 + 1) = 0;
                                                  }
                                                  v1291 = v345[3];
                                                  if ( v1291 )
                                                  {
                                                    v347 = GetProcessHeap();
                                                    HeapFree(v347, 0, (LPVOID)v1291);
                                                    v345 = v1281;
                                                    *((_QWORD *)v1281 + 3) = 0;
                                                  }
                                                  v1291 = v345[5];
                                                  if ( v1291 )
                                                  {
                                                    v348 = GetProcessHeap();
                                                    HeapFree(v348, 0, (LPVOID)v1291);
                                                    *((_QWORD *)v1281 + 5) = 0;
                                                  }
                                                  v349 = GetProcessHeap();
                                                  HeapFree(v349, 0, v1281);
                                                  v350 = (SIZE_T *)v1284;
                                                  v319 = 0;
                                                  goto LABEL_445;
                                                }
                                                *((_QWORD *)v1281 + 1) = v337;
                                                v320 = 0;
                                                memcpy_0(v337, (const void *)Size, v1291);
                                                v335 = v1281;
                                                v319 = 0;
                                              }
                                              else
                                              {
                                                *(_DWORD *)v335 = 0;
                                                v320 = 0;
                                                v335[1] = 0;
                                              }
                                              if ( v1289 )
                                              {
                                                *((_DWORD *)v335 + 4) = (_DWORD)v1290;
                                                v338 = GetProcessHeap();
                                                v339 = HeapAlloc(v338, 8u, v1302);
                                                v340 = v1281;
                                                if ( !v339 )
                                                {
LABEL_434:
                                                  v1281 = v340;
                                                  v1294 = v82;
                                                  v1280 = v84;
                                                  v1292 = (__int64)v184;
                                                  goto LABEL_435;
                                                }
                                                *((_QWORD *)v1281 + 3) = v339;
                                                v320 = 0;
                                                memcpy_0(v339, (const void *)v1289, v1302);
                                                v335 = v1281;
                                                v319 = 0;
                                              }
                                              else
                                              {
                                                *((_DWORD *)v335 + 4) = 0;
                                                v335[3] = 0;
                                              }
                                              if ( v1288 )
                                              {
                                                v341 = (unsigned int)v1279;
                                                *((_DWORD *)v335 + 8) = v1279;
                                                v342 = v341;
                                                v1291 = v341;
                                                v343 = GetProcessHeap();
                                                v344 = HeapAlloc(v343, 8u, v342);
                                                v340 = v1281;
                                                if ( !v344 )
                                                  goto LABEL_434;
                                                *((_QWORD *)v1281 + 5) = v344;
                                                v320 = 0;
                                                memcpy_0(v344, v1288, v1291);
                                                v335 = v1281;
                                                v319 = 0;
                                              }
                                              else
                                              {
                                                *((_DWORD *)v335 + 8) = 0;
                                                v335[5] = 0;
                                              }
                                              v350 = v335;
                                              v1284 = v335;
                                              v1290 = v185;
                                              v1292 = (__int64)v184;
                                              v1280 = v84;
                                              v1294 = v82;
LABEL_445:
                                              if ( v320 < 0 )
                                              {
                                                v351 = 0;
                                                v1281 = 0;
                                                if ( v350 )
                                                {
                                                  v1291 = v350[1];
                                                  if ( v1291 )
                                                  {
                                                    v352 = GetProcessHeap();
                                                    HeapFree(v352, 0, (LPVOID)v1291);
                                                    v350 = (SIZE_T *)v1284;
                                                    *((_QWORD *)v1284 + 1) = 0;
                                                  }
                                                  v1291 = v350[3];
                                                  if ( v1291 )
                                                  {
                                                    v353 = GetProcessHeap();
                                                    HeapFree(v353, 0, (LPVOID)v1291);
                                                    v350 = (SIZE_T *)v1284;
                                                    *((_QWORD *)v1284 + 3) = 0;
                                                  }
                                                  v1291 = v350[5];
                                                  if ( v1291 )
                                                  {
                                                    v354 = GetProcessHeap();
                                                    HeapFree(v354, 0, (LPVOID)v1291);
                                                    *((_QWORD *)v1284 + 5) = 0;
                                                  }
                                                  v355 = GetProcessHeap();
                                                  HeapFree(v355, 0, v1284);
                                                  v319 = 0;
                                                  v351 = 0;
                                                  v1281 = 0;
                                                }
                                              }
                                              else
                                              {
                                                v351 = (unsigned int *)v350;
                                                v1281 = v350;
                                              }
LABEL_457:
                                              v83 = v320 | 0x10000000;
                                              LODWORD(dwBytes) = v83;
                                              if ( v83 < 0 )
                                                goto LABEL_312;
                                              if ( !v351 || (v1289 = *((_QWORD *)v351 + 1)) == 0 || *v351 == v319 )
                                              {
                                                v83 = -805306355;
                                                goto LABEL_370;
                                              }
                                              v356 = *v351 - 8LL;
                                              v1288 = (void *)v356;
                                              v1296 = MemoryAlloc(v356);
                                              v357 = v1296;
                                              if ( !v1296 )
                                              {
LABEL_488:
                                                v83 = -805306367;
                                                v1296 = 0;
                                                goto LABEL_370;
                                              }
                                              v1278 = 0;
                                              v358 = 0;
                                              v1283 = (void *)0x7F1137FAB69605ELL;
                                              v359 = 0;
                                              v1291 = v1289;
                                              v360 = 0;
                                              Size = (SIZE_T)v1296;
                                              LODWORD(v1298) = 0;
                                              v361 = v356 & 7;
                                              if ( (v356 & 7) != 0 )
                                              {
                                                LODWORD(v1303) = 0;
                                                v362 = 0;
                                                v363 = (unsigned __int8 *)v1291;
                                                v364 = 0;
                                                do
                                                {
                                                  v365 = *v363++;
                                                  LODWORD(v1279) = 8 * v360;
                                                  if ( (unsigned int)v360 >= 4 )
                                                    v362 |= v365 << (56 - v1279);
                                                  else
                                                    v364 |= v365 << (24 - v1279);
                                                  ++v360;
                                                }
                                                while ( v360 < (int)v361 );
                                                v356 = (unsigned __int64)v1288;
                                                LODWORD(v1298) = v364;
                                                v366 = v364;
                                                v358 = v1278;
                                                LODWORD(v1303) = v362;
                                                v1291 = (SIZE_T)v363;
                                                v1290 = v185;
                                                v1292 = (__int64)v184;
                                                v1280 = v84;
                                                v1294 = v82;
                                                v359 = v366 ^ 0x92F65A5;
                                                v367 = v362 ^ 0x699A899C;
                                                v368 = 0;
                                                v369 = v359;
                                                v370 = v362 ^ 0x699A899C;
                                                if ( v361 )
                                                {
                                                  v371 = v1296;
                                                  do
                                                  {
                                                    Size = (SIZE_T)(v371 + 1);
                                                    if ( v368 >= 4 )
                                                    {
                                                      v370 = __ROR4__(v370, 24);
                                                      v372 = v370;
                                                    }
                                                    else
                                                    {
                                                      v369 = __ROR4__(v369, 24);
                                                      v372 = v369;
                                                    }
                                                    *v371 = v372;
                                                    ++v368;
                                                    v371 = (_BYTE *)Size;
                                                  }
                                                  while ( (int)v368 < (int)v361 );
                                                }
                                                if ( v361 <= 4 )
                                                {
                                                  v360 = 0;
                                                  if ( v361 < 4 )
                                                    v359 = v359 >> (8 * (4 - v361)) << (8 * (4 - v361));
                                                }
                                                else
                                                {
                                                  v360 = v367 >> (8 * (8 - v361)) << (8 * (8 - v361));
                                                }
                                              }
                                              else
                                              {
                                                LODWORD(v1303) = -1;
                                              }
                                              v373 = v356 >> 3;
                                              if ( v356 >> 3 )
                                              {
                                                v374 = HIDWORD(v1283);
                                                v375 = (unsigned __int8 *)v1291;
                                                v376 = (_BYTE *)Size;
                                                v377 = (int)v1303;
                                                v378 = v1298;
                                                HIDWORD(dwBytes) = WORD2(v1283);
                                                LODWORD(dwBytes) = 24670;
                                                v379 = v373;
                                                v1302 = 0;
                                                do
                                                {
                                                  v380 = *v375;
                                                  v381 = v375[1];
                                                  v382 = v375[4];
                                                  v375 += 8;
                                                  v383 = *(v375 - 5)
                                                       | ((*(v375 - 6) | (((v380 << 8) | v381) << 8)) << 8);
                                                  v384 = v359 ^ v383;
                                                  v385 = *(v375 - 1)
                                                       | ((*(v375 - 2) | ((*(v375 - 3) | (v382 << 8)) << 8)) << 8);
                                                  v386 = v360 ^ v385 ^ v374 ^ v359 ^ v383 ^ 0xAB69605E;
                                                  v387 = v384
                                                       ^ (__ROR4__(v386, 22)
                                                        + HIDWORD(dwBytes) * __ROR4__(v386 + 1419157410, 27));
                                                  v388 = v386
                                                       ^ (WORD1(v1283) * __ROR4__(v387 + v374, 9) - __ROR4__(v387, 30));
                                                  v389 = v387 ^ (dwBytes * (v388 - HIDWORD(dwBytes)) - (v388 >> 13));
                                                  v390 = v388
                                                       ^ (HIWORD(v1283) * __ROR4__(WORD1(v1283) ^ v389, 26)
                                                        - __ROR4__(v389, 30));
                                                  v391 = v389 ^ (v374 - (v390 ^ 0xAB69605E));
                                                  v392 = v390
                                                       ^ (WORD1(v1283) * (HIDWORD(dwBytes) ^ v391))
                                                       ^ __ROR4__(v391, 6);
                                                  v393 = v391
                                                       ^ (__ROR4__(v392, 30) + dwBytes * __ROR4__(v392 + v374, 15));
                                                  v394 = v392
                                                       ^ (HIWORD(v1283) * __ROR4__(v393 + 1419157410, 14)
                                                        - __ROR4__(v393, 24));
                                                  v395 = v393
                                                       ^ __ROR4__(v394, 10)
                                                       ^ (HIDWORD(dwBytes) * __ROR4__(v394 ^ 0xAB69605E, 12));
                                                  v396 = v395
                                                       ^ (HIWORD(v1283)
                                                        * (dwBytes
                                                         + __ROR4__(
                                                             ~(v394
                                                             ^ (v395 >> 10)
                                                             ^ (WORD1(v1283) * (HIWORD(v1283) ^ v395))),
                                                             5)));
                                                  v397 = v394
                                                       ^ (v395 >> 10)
                                                       ^ (WORD1(v1283) * (HIWORD(v1283) ^ v395))
                                                       ^ (v396 - HIWORD(v1283))
                                                       ^ 0xAB69605E;
                                                  v398 = v396
                                                       ^ ((v397 >> 2)
                                                        + HIDWORD(dwBytes) * __ROR4__(HIWORD(v1283) ^ v397, 30));
                                                  v399 = v397
                                                       ^ (__ROR4__(v398, 25)
                                                        + WORD1(v1283) * __ROR4__(v398 - HIDWORD(v1283), 6));
                                                  v400 = v398
                                                       ^ (dwBytes * (HIDWORD(dwBytes) ^ v399) + __ROR4__(v399, 9));
                                                  v401 = v399
                                                       ^ (__ROR4__(v400, 25)
                                                        + HIWORD(v1283) * __ROR4__(WORD1(v1283) ^ v400, 27));
                                                  v374 = HIDWORD(v1283);
                                                  v402 = HIDWORD(v1283) ^ v400 ^ v401 ^ 0xAB69605E;
                                                  v403 = v401 ^ (HIDWORD(dwBytes) * (__ROR4__(v402, 3) - WORD1(v1283)));
                                                  v404 = v402
                                                       ^ (dwBytes * __ROR4__(v403 - HIDWORD(v1283), 1)
                                                        - __ROR4__(v403, 6));
                                                  v405 = v403
                                                       ^ (__ROR4__(v404, 18)
                                                        + HIWORD(v1283) * __ROR4__(v404 - 1419157410, 29));
                                                  v406 = v404
                                                       ^ (HIDWORD(dwBytes) * __ROR4__(v405 - 1419157410, 17)
                                                        - __ROR4__(v405, 14));
                                                  v407 = v405 ^ (v406 >> 3) ^ (WORD1(v1283) * (dwBytes ^ v406));
                                                  v360 = v377 ^ v407;
                                                  v377 = v385;
                                                  v359 = v378
                                                       ^ v406
                                                       ^ __ROR4__(v407, 30)
                                                       ^ (dwBytes * __ROR4__(HIDWORD(v1283) ^ v407, 28));
                                                  v378 = v383;
                                                  v376[3] = v359;
                                                  v376[7] = v360;
                                                  v376[2] = __ROR4__(v359, 8);
                                                  v376[6] = __ROR4__(v360, 8);
                                                  v376[1] = __ROR4__(v359, 16);
                                                  v376[5] = __ROR4__(v360, 16);
                                                  *v376 = __ROR4__(v359, 24);
                                                  v376[4] = __ROR4__(v360, 24);
                                                  v376 += 8;
                                                  ++v1302;
                                                }
                                                while ( v1302 < v379 );
                                                v358 = v1278;
                                                v82 = v1294;
                                                v84 = v1280;
                                                v185 = v1290;
                                                v357 = v1296;
                                                v356 = (unsigned __int64)v1288;
                                              }
                                              for ( i19 = 0; i19 < v356; ++i19 )
                                                v358 ^= v357[i19];
                                              if ( v358 != *(_QWORD *)(v356 + v1289) )
                                              {
                                                MemoryFree(v357);
                                                goto LABEL_488;
                                              }
                                              v184 = (unsigned int *)v1292;
                                              HIDWORD(dwBytes) = 0;
                                              v1284 = v357;
                                              if ( (unsigned int)v356 < 4 )
                                                goto LABEL_490;
                                              v409 = RtlULongLongAdd(v357, 4, &v1284);
                                              if ( v409 >= 0 )
                                              {
                                                v409 = RtlUIntAdd(0, 4, (char *)&dwBytes + 4);
                                                if ( v409 >= 0 )
                                                {
                                                  v414 = (unsigned int)(v413 + 4);
                                                  if ( (int)v1288 - HIDWORD(dwBytes) < (unsigned int)v414 )
                                                    goto LABEL_522;
                                                  LODWORD(v1298) = *(_DWORD *)v1284;
                                                  v409 = RtlULongLongAdd(v1284, v414, &v1284);
                                                  if ( v409 < 0 )
                                                    goto LABEL_523;
                                                  v409 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                                  if ( v409 < 0 )
                                                    goto LABEL_523;
                                                  if ( (int)v1288 - HIDWORD(dwBytes) < (unsigned int)v1298 )
                                                    goto LABEL_522;
                                                  v409 = RtlUIntAdd(
                                                           HIDWORD(dwBytes),
                                                           (unsigned int)v1298,
                                                           (char *)&dwBytes + 4);
                                                  if ( v409 >= 0 )
                                                  {
                                                    if ( (char *)v412 + (unsigned int)v1288 >= (char *)v1284
                                                                                             + (unsigned int)v1298 )
                                                    {
                                                      v415 = v1284;
                                                      if ( (unsigned int)v1288
                                                         + (char *)v412
                                                         - (_BYTE *)v1284
                                                         - (unsigned __int64)(unsigned int)v1298 < 8 )
                                                      {
                                                        LODWORD(v1283) = *v412;
                                                        v1291 = 0;
                                                        Size = 0;
                                                        v1302 = 0;
                                                        LODWORD(v1293) = 0;
                                                        if ( v1284 )
                                                        {
                                                          v409 = RtlULongLongAdd(v1284, (unsigned int)v1298, &v1291);
                                                          v1296 = v417;
                                                          v1281 = v418;
                                                          v1282 = v419;
                                                          if ( v409 < 0 )
                                                            goto LABEL_524;
                                                          v420 = v1291;
                                                          v421 = 4;
                                                          v422 = v416;
                                                          while ( v422 < v420 )
                                                          {
                                                            v409 = RtlULongLongAdd(v422, v421, &Size);
                                                            if ( v409 < 0 )
                                                              goto LABEL_524;
                                                            if ( Size > v424 )
                                                              goto LABEL_510;
                                                            v426 = *v423;
                                                            LODWORD(v1279) = 0;
                                                            v409 = RtlUIntAdd(v425, v426, &v1279);
                                                            if ( v409 < 0 )
                                                              goto LABEL_524;
                                                            v409 = RtlULongLongAdd(v427, (unsigned int)v1279, &v1302);
                                                            if ( v409 < 0 )
                                                              goto LABEL_524;
                                                            v422 = v1302;
                                                            if ( v1302 > v420 )
                                                              goto LABEL_510;
                                                            LODWORD(v1293) = (_DWORD)v1293 + 1;
                                                          }
                                                          if ( v422 != v420 )
                                                          {
LABEL_510:
                                                            v409 = -1073741811;
                                                            goto LABEL_524;
                                                          }
                                                          v415 = v1284;
                                                        }
                                                        else
                                                        {
                                                          v409 = 0;
                                                          v1296 = v412;
                                                          v1281 = v411;
                                                          v1282 = v410;
                                                        }
                                                        v428 = v1298;
                                                        v429 = 0;
                                                        v1291 = 0;
                                                        if ( (_DWORD)v1298 )
                                                        {
                                                          v430 = GetProcessHeap();
                                                          v429 = HeapAlloc(v430, 8u, (unsigned int)v1298);
                                                          v1291 = (SIZE_T)v429;
                                                          if ( !v429 )
                                                          {
                                                            v409 = -1073741801;
                                                            goto LABEL_524;
                                                          }
                                                          v415 = v1284;
                                                          v409 = 0;
                                                          v428 = v1298;
                                                        }
                                                        if ( v415 )
                                                          memcpy_0(v429, v415, v428);
                                                        v1304 = (LPVOID)v1291;
                                                        LODWORD(v1297) = (_DWORD)v1293;
                                                        if ( (_DWORD)v1283 == (_DWORD)v1293 )
                                                          goto LABEL_524;
LABEL_490:
                                                        v409 = -1073741762;
LABEL_524:
                                                        v83 = v409 | 0x10000000;
                                                        goto LABEL_311;
                                                      }
                                                    }
LABEL_522:
                                                    v409 = -1073741762;
                                                  }
                                                }
                                              }
LABEL_523:
                                              v1296 = v412;
                                              v1282 = v410;
                                              v1281 = v411;
                                              goto LABEL_524;
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                                v319 = 0;
                              }
                            }
                          }
                        }
                        v184 = (unsigned int *)v1292;
                        v351 = (unsigned int *)v1281;
                        v1290 = v185;
                        goto LABEL_457;
                      }
LABEL_367:
                      if ( v83 < 0 )
                        goto LABEL_312;
                      goto LABEL_368;
                    }
                  }
                }
                v83 = -1073741811;
                LODWORD(dwBytes) = -1073741811;
                goto LABEL_367;
              }
              pcchLength = (size_t)Src[1];
              for ( i20 = 0; i20 < v165; i20 = v169 + 1 )
              {
                v167 = *v164;
                LODWORD(v1279) = 0;
                LODWORD(dwBytes) = RtlUIntAdd((unsigned int)v115, v167, &v1279);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                LODWORD(dwBytes) = RtlULongLongAdd(v168, (unsigned int)v1279, &pcchLength);
                v83 = dwBytes;
                if ( (dwBytes & 0x80000000) != 0LL )
                  goto LABEL_131;
                v164 = (unsigned int *)pcchLength;
              }
              LODWORD(dwBytes) = RtlULongLongAdd(v164, v115, &v1301);
              v83 = dwBytes;
              if ( (dwBytes & 0x80000000) != 0LL )
                goto LABEL_131;
              if ( v170 + 2 <= (_DWORD *)((char *)Src[1] + HIDWORD(Src[0])) )
              {
                v171 = v1301;
                *v170 = v115;
                *v171 = v115;
                goto LABEL_229;
              }
            }
LABEL_162:
            v83 = -1073741789;
            goto LABEL_130;
          }
          if ( v59 && !wcscmp_0(v59, L"WinSta0") && v60 && !wcscmp_0(v60, L"Default") )
          {
            v1321 = 0;
            CurrentProcess = GetCurrentProcess();
            if ( !(unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v1321) )
            {
              LastError = GetLastError();
              v76 = LastError < 0;
              if ( LastError > 0 )
              {
                LastError = (unsigned __int16)LastError | 0x80070000;
                v76 = LastError < 0;
              }
              if ( !v76 )
                LastError = -2147467259;
              goto LABEL_100;
            }
            if ( (v1321 & 0xF) == 0 )
              v61 = 1;
          }
        }
        else
        {
          LastError = 0;
        }
        v62 = v61;
        goto LABEL_100;
      }
      v5[823] = 0;
      v46 = 0;
      v47 = 0;
      v48 = 0;
      memset_0(&WARBIRD::g_arModuleInfo, 0, 0x60u);
      lpMem = v5;
      while ( *v5 )
      {
        v49 = -1;
        do
          ++v49;
        while ( *(_WORD *)&v5[2 * v49] );
        v50 = (HMODULE *)(&WARBIRD::g_arModuleInfo + 3 * v48);
        if ( !GetModuleHandleExW(0, (LPCWSTR)v5, v50) )
        {
          v47 = -1073741702;
          break;
        }
        v51 = &v5[2 * v49];
        if ( *(_WORD *)*v50 == 23117
          && (v52 = *((int *)*v50 + 15), (unsigned int)v52 < 0x10000000)
          && (v53 = (char *)*v50 + v52, v53 >= (char *)*v50)
          && *(_DWORD *)v53 == 17744 )
        {
          if ( ((*((_WORD *)v53 + 12) - 267) & 0xFEFF) != 0 )
          {
            v47 = -1073741811;
          }
          else
          {
            v47 = 0;
            *(struct WARBIRD::_MODULE_INFO near **)((char *)&WARBIRD::g_arModuleInfo + 24 * v48 + 12) = (struct WARBIRD::_MODULE_INFO near *)*((_QWORD *)v53 + 17);
            *((_DWORD *)&WARBIRD::g_arModuleInfo + 6 * v48 + 2) = *((_DWORD *)v53 + 20);
          }
        }
        else
        {
          v47 = -1073741701;
        }
        v54 = *(_DWORD *)(v51 + 2);
        v55 = 0;
        LODWORD(v1283) = v54;
        v5 = v51 + 6;
        while ( v55 < v54 )
        {
          v56 = -1;
          do
            ++v56;
          while ( v5[v56] );
          if ( v47 >= 0 )
          {
            v57 = (void **)GetProcAddress(*v50, v5);
            if ( !v57 )
              goto LABEL_41;
            (&WARBIRD::g_FuncAddress)[v46] = v57;
            v54 = (unsigned int)v1283;
          }
          ++v46;
          v5 += v56 + 1;
          ++v55;
        }
        ++v48;
      }
LABEL_41:
      if ( lpMem )
      {
        v58 = GetProcessHeap();
        HeapFree(v58, 0, lpMem);
      }
      if ( v47 < 0 )
        goto LABEL_13;
      v3 = g_WarbirdSecureFunctionsRefCount;
    }
    g_WarbirdSecureFunctionsRefCount = v3 + 1;
    goto LABEL_46;
  }
  v2 = -2147024809;
LABEL_1596:
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1326);
  return v2;
}

```

## disassembly

```asm
0x18005c354  push    rbp
0x18005c356  push    rbx
0x18005c357  push    rsi
0x18005c358  push    rdi
0x18005c359  push    r12
0x18005c35b  push    r13
0x18005c35d  push    r14
0x18005c35f  push    r15
0x18005c361  lea     rbp, [rsp-0E08h]
0x18005c369  sub     rsp, 0F08h
0x18005c370  mov     rax, cs:__security_cookie
0x18005c377  xor     rax, rsp
0x18005c37a  mov     [rbp+0E40h+var_50], rax
0x18005c381  xor     ecx, ecx
0x18005c383  mov     [rbp+0E40h+var_CE8], rdx
0x18005c38a  mov     [rbp+0E40h+var_D60], rcx
0x18005c391  test    rdx, rdx
0x18005c394  jnz     short loc_18005C3A0
0x18005c396  mov     ebx, 80070057h
0x18005c39b  jmp     loc_18006671E
0x18005c3a0  xor     eax, eax
0x18005c3a2  mov     [rsp+0F40h+var_ED8], eax
0x18005c3a6  mov     [rbp+0E40h+var_DD0], rax
0x18005c3aa  lea     r14d, [rax+1]
0x18005c3ae  jmp     short loc_18005C3B2
0x18005c3b0  xor     eax, eax
0x18005c3b2  lock cmpxchg cs:g_WarbirdSecureFunctionsLock, r14d
0x18005c3bb  jnz     short loc_18005C3B0
0x18005c3bd  mov     eax, cs:g_WarbirdSecureFunctionsRefCount
0x18005c3c3  lea     r15, ?g_arModuleInfo@WARBIRD@@3PAU_MODULE_INFO@1@A; WARBIRD::_MODULE_INFO near * WARBIRD::g_arModuleInfo
0x18005c3ca  or      ebx, 0FFFFFFFFh
0x18005c3cd  lea     r13, ?g_FuncAddress@WARBIRD@@3PAPEAXA; void * near * WARBIRD::g_FuncAddress
0x18005c3d4  mov     [rbp+0E40h+var_DF0], ebx
0x18005c3d7  mov     esi, 4
0x18005c3dc  lea     r12d, [rsi+5Ch]
0x18005c3e0  test    eax, eax
0x18005c3e2  jnz     loc_18005C927
0x18005c3e8  mov     ecx, 338h; unsigned __int64
0x18005c3ed  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18005c3f2  mov     rdi, rax
0x18005c3f5  test    rax, rax
0x18005c3f8  jz      loc_18005C76F
0x18005c3fe  xor     ecx, ecx
0x18005c400  lea     rsi, qword_180078760
0x18005c407  mov     r14, rax
0x18005c40a  mov     r12d, ecx
0x18005c40d  mov     r13d, ebx
0x18005c410  mov     r10d, ecx
0x18005c413  mov     r8d, ecx
0x18005c416  mov     eax, 0AB69605Eh
0x18005c41b  lea     r15d, [rcx+67h]
0x18005c41f  movzx   ecx, byte ptr [rsi]
0x18005c422  shl     ecx, 8
0x18005c425  movzx   ebx, byte ptr [rsi+1]
0x18005c429  movzx   r11d, byte ptr [rsi+4]
0x18005c42e  lea     rsi, [rsi+8]
0x18005c432  or      ebx, ecx
0x18005c434  shl     r11d, 8
0x18005c438  movzx   ecx, byte ptr [rsi-6]
0x18005c43c  shl     ebx, 8
0x18005c43f  or      ebx, ecx
0x18005c441  movzx   ecx, byte ptr [rsi-5]
0x18005c445  shl     ebx, 8
0x18005c448  or      ebx, ecx
0x18005c44a  movzx   ecx, byte ptr [rsi-3]
0x18005c44e  or      r11d, ecx
0x18005c451  mov     edx, ebx
0x18005c453  movzx   ecx, byte ptr [rsi-2]
0x18005c457  xor     edx, r8d
0x18005c45a  mov     r8d, edx
0x18005c45d  shl     r11d, 8
0x18005c461  or      r11d, ecx
0x18005c464  movzx   ecx, byte ptr [rsi-1]
0x18005c468  shl     r11d, 8
0x18005c46c  or      r11d, ecx
0x18005c46f  xor     r8d, r11d
0x18005c472  xor     r8d, r10d
0x18005c475  xor     r8d, 0AC987321h
0x18005c47c  lea     ecx, [r8+54969FA2h]
0x18005c483  ror     ecx, 1Bh
0x18005c486  imul    r9d, ecx, 137Fh
0x18005c48d  mov     ecx, r8d
0x18005c490  ror     ecx, 16h
0x18005c493  add     r9d, ecx
0x18005c496  xor     r9d, edx
0x18005c499  lea     ecx, [r9+7F1137Fh]
0x18005c4a0  ror     ecx, 9
0x18005c4a3  imul    edx, ecx, 0AB69h
0x18005c4a9  mov     ecx, r9d
0x18005c4ac  ror     ecx, 1Eh
0x18005c4af  sub     edx, ecx
0x18005c4b1  xor     edx, r8d
0x18005c4b4  imul    r10d, edx, 605Eh
0x18005c4bb  mov     ecx, edx
0x18005c4bd  shr     ecx, 0Dh
0x18005c4c0  sub     r10d, ecx
0x18005c4c3  sub     r10d, 756C8A2h
0x18005c4ca  xor     r10d, r9d
0x18005c4cd  mov     r9d, 7F1137Fh
0x18005c4d3  mov     ecx, r10d
0x18005c4d6  xor     ecx, 0AB69h
0x18005c4dc  ror     ecx, 1Ah
0x18005c4df  imul    r8d, ecx, 7F1h
0x18005c4e6  mov     ecx, r10d
0x18005c4e9  ror     ecx, 1Eh
0x18005c4ec  sub     r8d, ecx
0x18005c4ef  xor     r8d, edx
0x18005c4f2  mov     ecx, r8d
0x18005c4f5  xor     ecx, eax
0x18005c4f7  sub     r9d, ecx
0x18005c4fa  xor     r9d, r10d
0x18005c4fd  mov     ecx, r9d
0x18005c500  mov     r10d, r9d
0x18005c503  xor     ecx, 137Fh
0x18005c509  ror     r10d, 6
0x18005c50d  imul    edx, ecx, 0AB69h
0x18005c513  xor     r10d, edx
0x18005c516  xor     r10d, r8d
0x18005c519  lea     ecx, [r10+7F1137Fh]
0x18005c520  ror     ecx, 0Fh
0x18005c523  imul    edx, ecx, 605Eh
0x18005c529  mov     ecx, r10d
0x18005c52c  ror     ecx, 1Eh
0x18005c52f  add     edx, ecx
0x18005c531  xor     edx, r9d
0x18005c534  lea     ecx, [rdx+54969FA2h]
0x18005c53a  ror     ecx, 0Eh
0x18005c53d  imul    r8d, ecx, 7F1h
0x18005c544  mov     ecx, edx
0x18005c546  ror     ecx, 18h
0x18005c549  sub     r8d, ecx
0x18005c54c  xor     r8d, r10d
0x18005c54f  mov     ecx, r8d
0x18005c552  mov     r10d, 7F1h
0x18005c558  xor     ecx, eax
0x18005c55a  ror     ecx, 0Ch
0x18005c55d  imul    r9d, ecx, 137Fh
0x18005c564  mov     ecx, r8d
0x18005c567  ror     ecx, 0Ah
0x18005c56a  xor     r9d, ecx
0x18005c56d  xor     r9d, edx
0x18005c570  mov     ecx, r9d
0x18005c573  xor     ecx, r10d
0x18005c576  imul    edx, ecx, 0AB69h
0x18005c57c  mov     ecx, r9d
0x18005c57f  shr     ecx, 0Ah
0x18005c582  xor     edx, ecx
0x18005c584  xor     edx, r8d
0x18005c587  mov     ecx, edx
0x18005c589  not     ecx
0x18005c58b  ror     ecx, 5
0x18005c58e  add     ecx, 605Eh
0x18005c594  imul    r8d, ecx, 7F1h
0x18005c59b  xor     r8d, r9d
0x18005c59e  lea     r9d, [r8-7F1h]
0x18005c5a5  xor     r9d, edx
0x18005c5a8  xor     r9d, eax
0x18005c5ab  mov     ecx, r9d
0x18005c5ae  xor     ecx, r10d
0x18005c5b1  ror     ecx, 1Eh
0x18005c5b4  imul    r10d, ecx, 137Fh
0x18005c5bb  mov     ecx, r9d
0x18005c5be  shr     ecx, 2
0x18005c5c1  add     r10d, ecx
0x18005c5c4  xor     r10d, r8d
0x18005c5c7  lea     ecx, [r10-7F1137Fh]
0x18005c5ce  ror     ecx, 6
0x18005c5d1  imul    r8d, ecx, 0AB69h
0x18005c5d8  mov     ecx, r10d
0x18005c5db  ror     ecx, 19h
0x18005c5de  add     r8d, ecx
0x18005c5e1  xor     r8d, r9d
0x18005c5e4  mov     ecx, r8d
0x18005c5e7  mov     r9d, r8d
0x18005c5ea  xor     ecx, 137Fh
0x18005c5f0  ror     r9d, 9
0x18005c5f4  imul    edx, ecx, 605Eh
0x18005c5fa  add     r9d, edx
0x18005c5fd  xor     r9d, r10d
0x18005c600  mov     ecx, r9d
0x18005c603  xor     ecx, 0AB69h
0x18005c609  ror     ecx, 1Bh
0x18005c60c  imul    edx, ecx, 7F1h
0x18005c612  mov     ecx, r9d
0x18005c615  ror     ecx, 19h
0x18005c618  add     edx, ecx
0x18005c61a  xor     edx, r8d
0x18005c61d  mov     r8d, edx
0x18005c620  xor     r8d, r9d
0x18005c623  xor     r8d, 0AC987321h
0x18005c62a  mov     ecx, r8d
0x18005c62d  ror     ecx, 3
0x18005c630  imul    r9d, ecx, 137Fh
0x18005c637  sub     r9d, 0D0DD417h
0x18005c63e  xor     r9d, edx
0x18005c641  lea     ecx, [r9-7F1137Fh]
0x18005c648  ror     ecx, 1
0x18005c64a  imul    edx, ecx, 605Eh
0x18005c650  mov     ecx, r9d
0x18005c653  ror     ecx, 6
0x18005c656  sub     edx, ecx
0x18005c658  xor     edx, r8d
0x18005c65b  lea     ecx, [rdx-54969FA2h]
0x18005c661  ror     ecx, 1Dh
0x18005c664  imul    r8d, ecx, 7F1h
0x18005c66b  mov     ecx, edx
0x18005c66d  ror     ecx, 12h
0x18005c670  add     r8d, ecx
0x18005c673  xor     r8d, r9d
0x18005c676  lea     ecx, [r8-54969FA2h]
0x18005c67d  ror     ecx, 11h
0x18005c680  imul    r9d, ecx, 137Fh
0x18005c687  mov     ecx, r8d
0x18005c68a  ror     ecx, 0Eh
0x18005c68d  sub     r9d, ecx
0x18005c690  xor     r9d, edx
0x18005c693  mov     ecx, r9d
0x18005c696  xor     ecx, 605Eh
0x18005c69c  imul    r10d, ecx, 0AB69h
0x18005c6a3  mov     ecx, r9d
0x18005c6a6  shr     ecx, 3
0x18005c6a9  xor     r10d, ecx
0x18005c6ac  xor     r10d, r8d
0x18005c6af  mov     ecx, r10d
0x18005c6b2  xor     ecx, 7F1137Fh
0x18005c6b8  ror     ecx, 1Ch
0x18005c6bb  imul    r8d, ecx, 605Eh
0x18005c6c2  mov     ecx, r10d
0x18005c6c5  ror     ecx, 1Eh
0x18005c6c8  xor     r10d, r13d
0x18005c6cb  mov     r13d, r11d
0x18005c6ce  xor     r8d, ecx
0x18005c6d1  xor     r8d, r9d
0x18005c6d4  xor     r8d, r12d
0x18005c6d7  mov     r12d, ebx
0x18005c6da  mov     [r14+3], r8b
0x18005c6de  mov     ecx, r8d
0x18005c6e1  ror     ecx, 8
0x18005c6e4  mov     [r14+7], r10b
0x18005c6e8  mov     [r14+2], cl
0x18005c6ec  mov     ecx, r10d
0x18005c6ef  ror     ecx, 8
0x18005c6f2  mov     [r14+6], cl
0x18005c6f6  mov     ecx, r8d
0x18005c6f9  ror     ecx, 10h
0x18005c6fc  mov     [r14+1], cl
0x18005c700  mov     ecx, r10d
0x18005c703  ror     ecx, 10h
0x18005c706  mov     [r14+5], cl
0x18005c70a  mov     ecx, r8d
0x18005c70d  ror     ecx, 18h
0x18005c710  mov     [r14], cl
0x18005c713  mov     ecx, r10d
0x18005c716  ror     ecx, 18h
0x18005c719  mov     [r14+4], cl
0x18005c71d  lea     r14, [r14+8]
0x18005c721  sub     r15, 1
0x18005c725  jnz     loc_18005C41F
0x18005c72b  xor     ecx, ecx
0x18005c72d  lea     r14d, [r15+1]
0x18005c731  mov     al, cl
0x18005c733  xor     al, [rdi+rcx]
0x18005c736  add     rcx, r14
0x18005c739  cmp     rcx, 338h
0x18005c740  jb      short loc_18005C733
0x18005c742  movzx   ecx, al
0x18005c745  cmp     rcx, cs:qword_180078A98
0x18005c74c  jz      short loc_18005C7B3
0x18005c74e  mov     rcx, rdi; void *
0x18005c751  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18005c756  mov     r12d, 60h ; '`'
0x18005c75c  lea     r13, ?g_FuncAddress@WARBIRD@@3PAPEAXA; void * near * WARBIRD::g_FuncAddress
0x18005c763  lea     r15, ?g_arModuleInfo@WARBIRD@@3PAU_MODULE_INFO@1@A; WARBIRD::_MODULE_INFO near * WARBIRD::g_arModuleInfo
0x18005c76a  lea     esi, [r12-5Ch]
0x18005c76f  xor     ebx, ebx
0x18005c771  lea     rax, [rbx+rbx*2]
0x18005c775  mov     rcx, [r15+rax*8]; hLibModule
0x18005c779  test    rcx, rcx
0x18005c77c  jz      short loc_18005C784
0x18005c77e  call    cs:__imp_FreeLibrary
0x18005c784  add     rbx, r14
0x18005c787  cmp     rbx, rsi
0x18005c78a  jnz     short loc_18005C771
0x18005c78c  mov     r8, r12; Size
0x18005c78f  xor     edx, edx; Val
0x18005c791  mov     rcx, r15; void *
0x18005c794  call    memset_0
0x18005c799  mov     r8d, 170h; Size
0x18005c79f  lea     rdx, off_18006E730; Src
0x18005c7a6  mov     rcx, r13; void *
0x18005c7a9  call    memcpy_0
0x18005c7ae  jmp     loc_18005C930
0x18005c7b3  xor     eax, eax
0x18005c7b5  lea     rcx, ?g_arModuleInfo@WARBIRD@@3PAU_MODULE_INFO@1@A; void *
0x18005c7bc  xor     edx, edx; Val
0x18005c7be  mov     [rdi+337h], al
0x18005c7c4  mov     r13d, eax
0x18005c7c7  mov     ebx, eax
0x18005c7c9  mov     r12d, eax
0x18005c7cc  lea     r8d, [rax+60h]; Size
  ... truncated ...
```
