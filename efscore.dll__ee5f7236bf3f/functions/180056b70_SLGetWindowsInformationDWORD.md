# SLGetWindowsInformationDWORD

- ea: `0x180056b70`
- end: `0x1800610a8`
- name: `SLGetWindowsInformationDWORD`
- size: `42296`
- prototype: `HRESULT __stdcall(PCWSTR pwszValueName, DWORD *pdwValue)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028d3c`

## callees

- `0x180004f86`
- `0x180005045`
- `0x180008a1c`
- `0x18000b884`
- `0x180056a2c`
- `0x180056a58`
- `0x180056aac`
- `0x180056aec`
- `0x180056b18`
- `0x180056b44`
- `0x180056b70`
- `0x1800610b0`
- `0x1800610cc`
- `0x1800610ec`
- `0x1800dddb6`
- `0x1800dddf0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800570c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180059387`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005aaa4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005b09b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005e6de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005feb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800570c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180059387`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005aaa4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005b09b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005e6de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005feb4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180056fa1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005aa01`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005aff8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005c659`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005d752`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005e645`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005e8d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180060fb5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180056fa1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005aa01`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005aff8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005c659`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005d752`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005e645`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005e8d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180060fb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800579b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800579b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057164`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800593d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005ab6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b161`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e798`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fef1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057164`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800593d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005ab6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b161`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005e798`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005fef1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800574a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005755d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800577e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800582e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058920`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058988`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800589da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058a7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058d22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800591c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059635`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059691`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800596ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059750`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a12f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005e953`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005e9ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005eb07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f049`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f6a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f6dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f732`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f7d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fa7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fe2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060148`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060199`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800601f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060256`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060c4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800574a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005755d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800577e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800582e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058920`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058988`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800589da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058a7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058d22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800591c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059635`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059691`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800596ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059750`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a12f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005e953`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005e9ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005eb07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f049`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f6a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f6dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f732`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f7d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fa7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fe2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060148`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060199`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800601f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060256`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060c4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057006`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005748c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005754f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800577d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057913`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057938`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057951`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005796a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800582d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058394`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005890e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058973`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800589c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058a68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058ac4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058af2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058b20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058b41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058b8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058bc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058bed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058c1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058c3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058d11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058d50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058d7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058da4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058dcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058dea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058e07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058e20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058e4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058e6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058e92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058eae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058ecb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059040`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800591b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059623`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059680`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800596dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005973f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005979c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800597c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800597f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059815`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800598a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800598d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059900`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059921`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a11d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005abe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b1df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e801`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e93f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e9df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005eaf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ec4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ec6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ec86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ec9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f038`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f0f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f696`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f6cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f71e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f7c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f821`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f84f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f87d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f89e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f8f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f955`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f983`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f9a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fa6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fbb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fe1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060187`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800601e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060244`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006029b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800602c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800602f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060314`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800603a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800603d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060401`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060423`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060c38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060cf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060d22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060d46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060d6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060d86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060da6`

## string_xrefs

- `0x18005936c`: `ntdll.dll`
- `0x18005fe99`: `ntdll.dll`

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
  unsigned int v46; // r12d
  void *v47; // r13
  int v48; // ebx
  HANDLE ProcessHeap; // rax
  const wchar_t *v50; // rsi
  const wchar_t *v51; // r14
  int v52; // r13d
  int v53; // r12d
  __int64 v54; // r15
  signed int LastError; // ebx
  bool v56; // sf
  __int64 v57; // rbx
  HMODULE *v58; // r14
  _BYTE *v59; // rdi
  __int64 v60; // rax
  char *v61; // rdx
  unsigned int v62; // eax
  unsigned int v63; // r15d
  __int64 v64; // rsi
  __int64 (__fastcall *ProcAddress)(); // rax
  __int64 v66; // r9
  void *j; // rdi
  void *v68; // r8
  __int64 (__fastcall *v69)(); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v71; // r15
  __int64 v72; // r9
  const wchar_t *k; // rdi
  const wchar_t *v74; // r8
  HANDLE CurrentProcess; // rax
  bool v76; // sf
  int v77; // edi
  HLOCAL v78; // rax
  HANDLE v79; // rax
  _OWORD *v80; // rax
  void *v81; // r12
  int v82; // r15d
  _QWORD *v83; // r13
  HANDLE v84; // rax
  int v85; // eax
  int v86; // ecx
  unsigned int v87; // r10d
  int v88; // eax
  unsigned int v89; // r10d
  int v90; // r9d
  int v91; // eax
  unsigned int v92; // r10d
  int v93; // r9d
  int v94; // eax
  size_t v95; // rdx
  int v96; // r9d
  int v97; // r11d
  int v98; // eax
  unsigned int v99; // r10d
  int v100; // r11d
  int v101; // eax
  unsigned int v102; // r10d
  int v103; // r11d
  int v104; // r9d
  int v105; // eax
  int v106; // r9d
  unsigned int v107; // ebx
  HANDLE v108; // rax
  _DWORD *v109; // rbx
  int v110; // r9d
  unsigned int v111; // r11d
  _DWORD *v112; // rax
  unsigned int v113; // ebx
  int v114; // r10d
  int v115; // eax
  void *v116; // rbx
  HANDLE v117; // rax
  void *v118; // rbx
  HANDLE v119; // rax
  HANDLE v120; // rax
  HANDLE v121; // rax
  DWORD ModuleFileNameW; // eax
  _BYTE *v123; // r13
  unsigned int *v124; // r9
  __int64 v125; // rdx
  __int64 v126; // r9
  unsigned int v127; // r10d
  unsigned int *v128; // r9
  unsigned int v129; // r11d
  int v130; // r10d
  unsigned int *v131; // r9
  int v132; // r11d
  int v133; // r10d
  __int64 v134; // rdx
  __int64 v135; // r9
  unsigned int v136; // r10d
  int v137; // r11d
  unsigned int *v138; // r9
  unsigned int *v139; // r9
  size_t v140; // rdx
  __int64 v141; // rdx
  __int64 v142; // r9
  unsigned int v143; // r10d
  int v144; // r11d
  _DWORD *v145; // r9
  SIZE_T *v146; // rax
  SIZE_T v147; // rcx
  int v148; // r11d
  unsigned int *v149; // r9
  int v150; // ebx
  __int64 v151; // rdx
  __int64 v152; // r9
  unsigned int v153; // r11d
  _DWORD *v154; // r9
  __int64 v155; // r10
  STRSAFE_PCNZWCH v156; // rdx
  void *v157; // rcx
  unsigned int *v158; // r9
  int v159; // r10d
  int v160; // r11d
  __int64 v161; // rdx
  __int64 v162; // r9
  unsigned int v163; // r10d
  int v164; // r11d
  _DWORD *v165; // r9
  int *v166; // rax
  unsigned int *v167; // r9
  int v168; // r10d
  int v169; // r11d
  __int64 v170; // rdx
  __int64 v171; // r9
  unsigned int v172; // r10d
  int v173; // r11d
  _DWORD *v174; // r9
  _DWORD *v175; // rax
  __int64 v176; // rcx
  unsigned int v177; // r9d
  unsigned int v178; // r9d
  int v179; // r15d
  unsigned int v180; // eax
  unsigned int v181; // ebx
  HANDLE v182; // rax
  _DWORD *v183; // rbx
  unsigned int v184; // r9d
  unsigned int v185; // r10d
  size_t v186; // rcx
  HANDLE v187; // rax
  unsigned int *v188; // rdi
  _DWORD *v189; // rbx
  unsigned __int8 *v190; // r15
  void *v191; // rdx
  unsigned __int8 v192; // al
  unsigned __int64 v193; // r8
  unsigned int v194; // r9d
  unsigned __int64 v195; // rcx
  unsigned __int8 *v196; // r11
  int v197; // edx
  unsigned int v198; // r10d
  unsigned int v199; // r14d
  int v200; // r8d
  unsigned int v201; // r10d
  unsigned int v202; // ecx
  unsigned int v203; // r11d
  _BYTE *v204; // r14
  char v205; // si
  int v206; // r10d
  int v207; // r12d
  unsigned __int64 v208; // r14
  _BYTE *v209; // r15
  unsigned int v210; // edi
  unsigned int v211; // eax
  unsigned int v212; // r13d
  int v213; // ebx
  int v214; // r11d
  int v215; // edx
  int v216; // r10d
  int v217; // r8d
  int v218; // r10d
  int v219; // r9d
  int v220; // r8d
  unsigned int v221; // edx
  int v222; // r9d
  int v223; // ecx
  int v224; // edx
  int v225; // r8d
  int v226; // r9d
  int v227; // edx
  unsigned int v228; // r8d
  unsigned int v229; // r9d
  int v230; // edx
  int v231; // r8d
  int v232; // r9d
  int v233; // edx
  int v234; // r8d
  int v235; // r10d
  int v236; // edx
  int v237; // r9d
  unsigned int v238; // r8d
  int v239; // r10d
  int v240; // edx
  HANDLE v241; // rax
  wchar_t *v242; // rax
  int v243; // r15d
  HANDLE v244; // rax
  void *v245; // rcx
  STRSAFE_PCNZWCH v246; // r15
  HANDLE v247; // rax
  _OWORD *v248; // rax
  HANDLE v249; // rax
  _QWORD *v250; // rax
  STRSAFE_PCNZWCH v251; // rax
  HANDLE v252; // rax
  HANDLE v253; // rax
  HANDLE v254; // rax
  HANDLE v255; // rax
  HANDLE v256; // rax
  SIZE_T v257; // rax
  HANDLE v258; // rax
  HANDLE v259; // rax
  HANDLE v260; // rax
  HANDLE v261; // rax
  __int64 v262; // rdx
  unsigned int v263; // r9d
  int v264; // r15d
  __int64 v265; // rdx
  unsigned int v266; // r9d
  __int64 v267; // rdx
  unsigned int v268; // ebx
  HANDLE v269; // rax
  STRSAFE_PCNZWCH v270; // rcx
  LPVOID v271; // rax
  HANDLE v272; // rax
  HANDLE v273; // rax
  HANDLE v274; // rax
  HANDLE v275; // rax
  HANDLE v276; // rax
  void *v277; // rdi
  HANDLE v278; // rax
  HANDLE v279; // rax
  _QWORD *v280; // rbx
  void *v281; // rdi
  HANDLE v282; // rax
  void *v283; // rdi
  HANDLE v284; // rax
  void *v285; // rdi
  HANDLE v286; // rax
  HANDLE v287; // rax
  void *v288; // rbx
  HANDLE v289; // rax
  int v290; // eax
  void *v291; // rbx
  const wchar_t *v292; // rcx
  unsigned int v293; // r9d
  SIZE_T v294; // rcx
  unsigned int *v295; // r9
  SIZE_T v296; // rcx
  unsigned int *v297; // r9
  HANDLE v298; // rax
  int v299; // eax
  int v300; // r9d
  __int64 v301; // rcx
  unsigned int v302; // r11d
  LPVOID v303; // rcx
  unsigned int v304; // r9d
  unsigned int v305; // r11d
  int v306; // r10d
  unsigned int v307; // ebx
  LPVOID v308; // rcx
  unsigned int v309; // ebx
  HANDLE v310; // rax
  unsigned int v311; // r11d
  int v312; // r10d
  int v313; // r11d
  unsigned int v314; // ecx
  int v315; // r11d
  unsigned int v316; // r10d
  signed int v317; // eax
  FARPROC v318; // rax
  int v319; // eax
  unsigned int v320; // r9d
  int v321; // r11d
  int v322; // r15d
  int v323; // r9d
  size_t v324; // r10
  unsigned int v325; // r10d
  int v326; // r9d
  int v327; // r9d
  SIZE_T v328; // r11
  unsigned int v329; // r11d
  int v330; // r9d
  int v331; // r9d
  unsigned int v332; // r10d
  int v333; // r9d
  int v334; // r10d
  int v335; // r11d
  SIZE_T v336; // r15
  HANDLE v337; // rax
  void *v338; // rax
  bool v339; // zf
  _QWORD *v340; // rcx
  HANDLE v341; // rax
  void *v342; // rcx
  HANDLE v343; // rax
  void *v344; // rcx
  void *v345; // rax
  size_t v346; // rax
  unsigned int v347; // r15d
  HANDLE v348; // rax
  void *v349; // rcx
  _QWORD *v350; // rax
  HANDLE v351; // rax
  HANDLE v352; // rax
  HANDLE v353; // rax
  HANDLE v354; // rax
  size_t *v355; // rdx
  unsigned int *v356; // rcx
  HANDLE v357; // rax
  HANDLE v358; // rax
  HANDLE v359; // rax
  HANDLE v360; // rax
  unsigned __int64 v361; // r15
  _BYTE *v362; // r11
  unsigned __int8 v363; // al
  unsigned int v364; // r8d
  int v365; // r10d
  int v366; // r9d
  int v367; // r14d
  unsigned __int8 *v368; // rsi
  int v369; // eax
  int v370; // r8d
  int v371; // r8d
  unsigned int v372; // r10d
  unsigned int v373; // ecx
  int v374; // edx
  _BYTE *v375; // r14
  char v376; // si
  unsigned __int64 v377; // rcx
  int v378; // r11d
  unsigned __int8 *v379; // rsi
  int v380; // r9d
  _BYTE *v381; // r15
  int v382; // r13d
  int v383; // r12d
  unsigned __int64 v384; // rax
  int v385; // ecx
  int v386; // edi
  int v387; // ebx
  int v388; // edi
  int v389; // edx
  int v390; // ebx
  int v391; // r8d
  int v392; // r9d
  unsigned int v393; // edx
  int v394; // r8d
  int v395; // r9d
  unsigned int v396; // edx
  int v397; // r8d
  int v398; // r10d
  int v399; // r11d
  unsigned int v400; // r9d
  int v401; // r8d
  unsigned int v402; // r9d
  int v403; // r10d
  int v404; // r11d
  int v405; // edx
  int v406; // r8d
  int v407; // r9d
  int v408; // edx
  int v409; // r10d
  int v410; // r8d
  unsigned int v411; // edx
  int v412; // r10d
  int v413; // r8d
  int v414; // ecx
  unsigned __int64 i10; // rcx
  int v416; // r15d
  void *v417; // r9
  void *v418; // r10
  _DWORD *v419; // r11
  int v420; // eax
  wchar_t *v421; // rcx
  void *v422; // r11
  void *v423; // r10
  void *v424; // r9
  STRSAFE_PCNZWCH v425; // rax
  int v426; // eax
  void *v427; // r9
  void *v428; // r10
  void *v429; // r11
  STRSAFE_PCNZWCH v430; // rcx
  unsigned int v431; // eax
  unsigned int v432; // ecx
  void *v433; // rax
  HANDLE v434; // rax
  size_t v435; // rcx
  _DWORD *v436; // r9
  int v437; // r10d
  int *v438; // r15
  int v439; // ebx
  unsigned int v440; // r11d
  int v441; // r10d
  void *v442; // r9
  int v443; // r10d
  size_t *v444; // rdx
  size_t v445; // rax
  size_t v446; // rcx
  unsigned int v447; // r11d
  int v448; // r10d
  void *v449; // r9
  int v450; // r10d
  int *v451; // rdx
  int v452; // eax
  size_t v453; // rcx
  const void *v454; // rbx
  unsigned int v455; // r11d
  int v456; // r10d
  size_t v457; // r9
  int v458; // r11d
  _DWORD *v459; // rcx
  int v460; // r10d
  void *v461; // r9
  int v462; // r10d
  _DWORD *v463; // rdx
  size_t v464; // rcx
  unsigned int v465; // r9d
  int v466; // r10d
  int v467; // r9d
  unsigned int v468; // r10d
  size_t v469; // r11
  int *v470; // rcx
  __int64 v471; // rax
  unsigned int v472; // edi
  int v473; // eax
  _BYTE *v474; // rax
  _BYTE *v475; // r14
  __int64 *v476; // r12
  int v477; // eax
  __int64 v478; // rsi
  int v479; // edi
  int v480; // r9d
  int v481; // r8d
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
  int v509; // edx
  int v510; // r8d
  unsigned __int64 v511; // rcx
  char v512; // al
  __int64 n; // rbx
  HMODULE v514; // rcx
  unsigned int v515; // r12d
  __int64 v516; // rbx
  size_t v517; // rax
  HMODULE *v518; // r12
  _BYTE *v519; // r13
  size_t v520; // rcx
  int v521; // ebx
  __int64 v522; // rax
  char *v523; // rdx
  unsigned int v524; // edx
  unsigned int v525; // eax
  __int64 v526; // r12
  __int64 (__fastcall *v527)(); // rax
  void *v528; // r12
  HANDLE v529; // rax
  int v530; // eax
  _BYTE *v531; // rax
  _BYTE *v532; // rsi
  __int64 *v533; // r12
  int v534; // eax
  __int64 v535; // r14
  int v536; // edi
  int v537; // r9d
  int v538; // r8d
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
  unsigned __int64 v568; // rcx
  char v569; // al
  __int64 ii; // rbx
  HMODULE v571; // rcx
  unsigned int v572; // r12d
  __int64 v573; // rbx
  size_t v574; // rax
  HMODULE *v575; // r12
  _BYTE *v576; // r13
  size_t v577; // rcx
  int v578; // ebx
  __int64 v579; // rax
  char *v580; // rdx
  unsigned int v581; // edx
  unsigned int v582; // eax
  __int64 v583; // r12
  __int64 (__fastcall *v584)(); // rax
  void *v585; // r12
  HANDLE v586; // rax
  signed int v587; // eax
  signed int v588; // ebx
  SIZE_T v589; // r12
  bool v590; // sf
  void *v591; // rax
  char *v592; // r12
  void *v593; // rax
  bool v594; // sf
  unsigned int i3; // r14d
  __int64 v596; // rax
  unsigned int v597; // r9d
  unsigned int v598; // edx
  unsigned int i4; // ecx
  __int64 v600; // r12
  const wchar_t *v601; // rcx
  __int64 i5; // rdx
  __int64 v603; // rax
  _BYTE *v604; // rax
  _BYTE *v605; // r12
  __int64 *v606; // rbx
  _BYTE *v607; // r13
  int v608; // r14d
  int v609; // edi
  int v610; // r9d
  int v611; // edx
  __int64 v612; // rsi
  int v613; // eax
  int v614; // r11d
  int v615; // r10d
  int v616; // r11d
  int v617; // ecx
  int v618; // r10d
  unsigned int v619; // edx
  int v620; // r8d
  unsigned int v621; // r9d
  int v622; // ecx
  int v623; // edx
  unsigned int v624; // r8d
  int v625; // r9d
  int v626; // ecx
  int v627; // edx
  unsigned int v628; // r8d
  int v629; // ecx
  int v630; // edx
  unsigned int v631; // r9d
  unsigned int v632; // edx
  int v633; // r8d
  int v634; // ecx
  unsigned int v635; // edx
  int v636; // r8d
  int v637; // ecx
  int v638; // edx
  unsigned int v639; // r8d
  int v640; // r9d
  int v641; // eax
  unsigned __int64 v642; // rax
  __m128 v643; // xmm1
  __int64 v644; // r13
  __m128 v645; // xmm0
  __m128 v646; // xmm0
  __m128 v647; // xmm1
  __m128 v648; // xmm1
  __m128 v649; // xmm1
  int v650; // r8d
  unsigned int v651; // edx
  unsigned int i6; // ecx
  __int64 v653; // rax
  void *v654; // rax
  void **v655; // r12
  unsigned int v656; // ecx
  unsigned int v657; // eax
  __int64 v658; // r13
  __int64 v659; // r9
  signed int v660; // eax
  void *v661; // rax
  __int64 v662; // r9
  signed int v663; // eax
  __int64 i7; // r13
  _BYTE *v665; // rax
  __int64 v666; // rcx
  __int64 i8; // rcx
  _BYTE *v668; // rax
  signed int v669; // eax
  int v670; // r13d
  int v671; // eax
  unsigned int v672; // ebx
  signed int v673; // r12d
  size_t v674; // rax
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
  __int64 v687; // rdx
  signed int v688; // eax
  int v689; // eax
  __int64 v690; // rax
  bool v691; // sf
  void *v692; // rbx
  __int64 v693; // r12
  unsigned int v694; // ebx
  int v695; // eax
  int v696; // r12d
  int v697; // ebx
  int v698; // r13d
  int v699; // r13d
  __int64 v700; // rax
  int v701; // r13d
  __int64 v702; // rax
  int v703; // edx
  int v704; // eax
  __int64 jj; // r12
  HMODULE v706; // rcx
  unsigned int v707; // ebx
  __int64 v708; // rax
  int v709; // edi
  int v710; // r12d
  STRSAFE_PCNZWCH v711; // rbx
  int v712; // eax
  signed int v713; // r13d
  __int64 v714; // rax
  size_t v715; // rax
  size_t v716; // rbx
  __int64 v717; // rax
  signed int v718; // eax
  signed int v719; // edi
  void *v720; // rax
  __int64 (__fastcall *v721)(); // rbx
  __int64 v722; // rax
  int v723; // eax
  int v724; // r10d
  int v725; // r9d
  int v726; // r8d
  int v727; // ecx
  int v728; // edx
  int v729; // edi
  unsigned __int8 v730; // r14
  signed int v731; // esi
  char *v732; // rdx
  SIZE_T v733; // rax
  char v734; // r15
  signed int v735; // r9d
  char v736; // bl
  unsigned __int8 *v737; // r8
  _BYTE *v738; // r10
  unsigned __int8 v739; // dl
  int v740; // r8d
  int v741; // r9d
  int v742; // edx
  int v743; // r8d
  int v744; // ecx
  STRSAFE_PCNZWCH v745; // rbx
  __int64 v746; // rax
  void *v747; // rax
  void *v748; // r13
  unsigned __int64 v749; // rbx
  bool v750; // sf
  size_t v751; // rax
  __int64 (__fastcall *v752)(); // rbx
  __int64 v753; // rax
  int v754; // r10d
  int v755; // r9d
  int v756; // r8d
  int v757; // ecx
  int v758; // r12d
  int v759; // ebx
  SIZE_T v760; // rsi
  size_t v761; // rax
  char v762; // r13
  unsigned __int8 *v763; // r8
  char v764; // r14
  _BYTE *v765; // r10
  unsigned __int8 v766; // bl
  int v767; // r9d
  unsigned __int8 v768; // dl
  int v769; // r8d
  int v770; // r9d
  int v771; // edx
  int v772; // r8d
  int v773; // ecx
  STRSAFE_PCNZWCH v774; // r12
  size_t v775; // rbx
  char v776; // al
  int v777; // edi
  unsigned int v778; // r8d
  unsigned int v779; // r11d
  int v780; // ebx
  unsigned int v781; // eax
  int v782; // r10d
  int v783; // r13d
  unsigned int v784; // edx
  unsigned int v785; // eax
  size_t v786; // rax
  LPVOID v787; // rax
  __int64 v788; // rax
  _BYTE *v789; // rax
  __int64 v790; // rcx
  __int64 kk; // rcx
  _BYTE *v792; // rax
  __int64 v793; // rcx
  __int64 mm; // rcx
  _BYTE *v795; // rcx
  __int64 v796; // rax
  __int64 v797; // rax
  int v798; // eax
  __int64 nn; // rbx
  HMODULE v800; // rcx
  int v801; // r13d
  int v802; // ebx
  void *v803; // r12
  SIZE_T v804; // rcx
  int v805; // eax
  int v806; // ebx
  signed int v807; // edi
  void *v808; // rax
  bool v809; // sf
  SIZE_T v810; // rbx
  void *v811; // rax
  __int64 (__fastcall *v812)(); // rbx
  __int64 v813; // rax
  SIZE_T v814; // rbx
  int v815; // eax
  int v816; // edx
  int v817; // r9d
  int v818; // r11d
  int v819; // r10d
  int v820; // ecx
  int v821; // r8d
  __int64 v822; // r8
  unsigned __int8 v823; // r14
  int v824; // esi
  SIZE_T v825; // rbx
  size_t v826; // rax
  char v827; // r15
  int v828; // r9d
  char v829; // r13
  unsigned __int8 *v830; // r8
  _BYTE *v831; // r10
  unsigned __int8 v832; // dl
  int v833; // r8d
  int v834; // r9d
  int v835; // edx
  int v836; // r8d
  int v837; // ecx
  signed int v838; // edi
  LPVOID v839; // rbx
  __int64 v840; // rax
  void *v841; // rax
  bool v842; // sf
  SIZE_T v843; // rbx
  void *v844; // rax
  __int64 (__fastcall *v845)(); // rbx
  __int64 v846; // rax
  SIZE_T v847; // rbx
  signed int v848; // r9d
  int v849; // edx
  int v850; // r8d
  int v851; // ecx
  int v852; // r11d
  signed int v853; // esi
  SIZE_T v854; // rdx
  size_t v855; // rax
  char v856; // bl
  unsigned __int8 *v857; // r8
  char v858; // r14
  _BYTE *v859; // r10
  unsigned __int8 v860; // r11
  signed int v861; // r9d
  unsigned __int8 v862; // dl
  int v863; // r8d
  int v864; // r9d
  int v865; // edx
  int v866; // r8d
  int v867; // ecx
  int v868; // eax
  _BYTE *v869; // rax
  int v870; // r8d
  _BYTE *v871; // r12
  __int64 *v872; // r14
  __int64 v873; // rax
  int v874; // r13d
  int v875; // esi
  int v876; // r10d
  int v877; // ecx
  int v878; // ebx
  int v879; // r11d
  int v880; // ebx
  int v881; // edx
  int v882; // r11d
  unsigned int v883; // r8d
  int v884; // r9d
  unsigned int v885; // edx
  int v886; // r10d
  int v887; // r8d
  unsigned int v888; // r9d
  int v889; // r10d
  int v890; // edx
  int v891; // r8d
  unsigned int v892; // r9d
  int v893; // edx
  int v894; // r8d
  unsigned int v895; // r10d
  unsigned int v896; // r8d
  int v897; // r9d
  int v898; // edx
  unsigned int v899; // r8d
  int v900; // r9d
  int v901; // edx
  int v902; // r8d
  unsigned int v903; // r9d
  int v904; // r10d
  int v905; // ecx
  WCHAR *v906; // rdi
  unsigned __int64 v907; // rcx
  char v908; // al
  __int64 i1; // rbx
  HMODULE v910; // rcx
  unsigned int v911; // r12d
  __int64 v912; // rbx
  __int64 v913; // r12
  HMODULE *v914; // r13
  WCHAR *v915; // rdi
  int v916; // ebx
  __int64 v917; // rax
  char *v918; // rdx
  unsigned int v919; // ecx
  unsigned int v920; // eax
  int v921; // ecx
  unsigned int v922; // edx
  __int64 v923; // r12
  __int64 (__fastcall *v924)(); // rax
  HANDLE v925; // rax
  int v926; // eax
  __int64 i2; // rbx
  HMODULE v928; // rcx
  _DWORD *v929; // rdi
  HANDLE v930; // rax
  _OWORD *v931; // rax
  void *v932; // r12
  HANDLE v933; // rax
  _QWORD *v934; // rax
  _DWORD *v935; // r11
  _BYTE *v936; // rdi
  _DWORD *v937; // rcx
  unsigned int v938; // r10d
  unsigned int v939; // r11d
  int v940; // eax
  unsigned int v941; // r10d
  int v942; // r9d
  int v943; // eax
  unsigned int v944; // r10d
  int v945; // r9d
  int v946; // eax
  int v947; // r9d
  unsigned int v948; // ebx
  HANDLE v949; // rax
  _DWORD *v950; // rax
  _DWORD *v951; // rbx
  int v952; // r10d
  unsigned int v953; // r11d
  _DWORD *v954; // rax
  unsigned int v955; // ebx
  int v956; // r10d
  unsigned int *v957; // r9
  int v958; // eax
  unsigned int v959; // r11d
  void *v960; // rbx
  HANDLE v961; // rax
  HANDLE v962; // rax
  HANDLE v963; // rax
  HANDLE v964; // rax
  unsigned int v965; // edi
  int v966; // edi
  __int64 v967; // rdx
  __int64 v968; // r9
  unsigned int v969; // r10d
  unsigned int *v970; // r9
  unsigned int v971; // r11d
  size_t v972; // r8
  int v973; // r10d
  unsigned int *v974; // r9
  __int64 v975; // rdx
  __int64 v976; // r9
  unsigned int v977; // r10d
  int v978; // r11d
  int v979; // eax
  unsigned int *v980; // r9
  unsigned int *v981; // r10
  int v982; // r9d
  unsigned int v983; // r10d
  unsigned int v984; // r11d
  __int64 v985; // rdx
  __int64 v986; // r10
  unsigned int v987; // r9d
  int v988; // r11d
  int v989; // eax
  _DWORD *v990; // r10
  _QWORD *v991; // rax
  LPVOID v992; // rcx
  __int64 v993; // rcx
  unsigned int v994; // r11d
  unsigned int v995; // r9d
  SIZE_T v996; // r11
  unsigned int v997; // edi
  int v998; // ecx
  SIZE_T v999; // r9
  unsigned int v1000; // r10d
  unsigned int *v1001; // r11
  unsigned int v1002; // eax
  unsigned int v1003; // ebx
  HANDLE v1004; // rax
  char *v1005; // rax
  char *v1006; // rbx
  unsigned int v1007; // r9d
  size_t v1008; // rcx
  HANDLE v1009; // rax
  int v1010; // ecx
  _DWORD *v1011; // rbx
  const void **v1012; // rdi
  unsigned __int8 v1013; // al
  unsigned __int64 v1014; // r8
  unsigned __int64 v1015; // r11
  unsigned __int8 *v1016; // r9
  int v1017; // r10d
  unsigned int v1018; // r14d
  unsigned int v1019; // esi
  int v1020; // edi
  int v1021; // r8d
  int v1022; // r8d
  _BYTE *v1023; // rcx
  unsigned int v1024; // r8d
  unsigned int v1025; // r9d
  unsigned int v1026; // edx
  unsigned int v1027; // esi
  int v1028; // r14d
  char v1029; // bl
  int v1030; // r9d
  unsigned __int8 *v1031; // r14
  unsigned __int64 v1032; // r13
  _BYTE *v1033; // rdi
  int v1034; // r15d
  int v1035; // r10d
  unsigned int v1036; // eax
  unsigned int v1037; // r12d
  int v1038; // ecx
  int v1039; // ebx
  int v1040; // r11d
  int v1041; // ebx
  int v1042; // r11d
  int v1043; // edx
  int v1044; // r9d
  int v1045; // r10d
  int v1046; // r8d
  int v1047; // r9d
  unsigned int v1048; // edx
  int v1049; // r8d
  int v1050; // ecx
  int v1051; // edx
  int v1052; // r8d
  int v1053; // r9d
  int v1054; // edx
  unsigned int v1055; // r8d
  unsigned int v1056; // r9d
  int v1057; // edx
  int v1058; // r8d
  int v1059; // r9d
  int v1060; // edx
  int v1061; // r8d
  int v1062; // r9d
  int v1063; // edx
  int v1064; // r8d
  unsigned int v1065; // ecx
  int v1066; // edx
  HANDLE v1067; // rax
  _DWORD *v1068; // rax
  void *v1069; // rsi
  unsigned int v1070; // esi
  HANDLE v1071; // rax
  LPVOID v1072; // rax
  void *v1073; // rcx
  unsigned int v1074; // eax
  HANDLE v1075; // rax
  _OWORD *v1076; // rcx
  _DWORD *v1077; // rax
  HANDLE v1078; // rax
  _QWORD *v1079; // rax
  LPVOID v1080; // rax
  HANDLE v1081; // rax
  HANDLE v1082; // rax
  HANDLE v1083; // rax
  HANDLE v1084; // rax
  LPVOID v1085; // rcx
  HANDLE v1086; // rax
  size_t v1087; // rax
  HANDLE v1088; // rax
  HANDLE v1089; // rax
  HANDLE v1090; // rax
  HANDLE v1091; // rax
  __int64 v1092; // rdx
  unsigned int v1093; // r9d
  __int64 v1094; // rdx
  unsigned int v1095; // r9d
  __int64 v1096; // rdx
  unsigned int v1097; // ebx
  HANDLE v1098; // rax
  wchar_t *v1099; // rax
  unsigned int v1100; // ebx
  const wchar_t *v1101; // rcx
  LPVOID v1102; // rcx
  unsigned int *v1103; // r9
  LPVOID v1104; // rcx
  unsigned int *v1105; // r9
  int v1106; // eax
  HANDLE v1107; // rax
  int v1108; // eax
  int v1109; // eax
  int v1110; // r9d
  __int64 v1111; // rcx
  size_t v1112; // rcx
  unsigned int v1113; // r11d
  int v1114; // r10d
  unsigned int v1115; // ebx
  size_t v1116; // rcx
  unsigned int v1117; // r11d
  int v1118; // r10d
  unsigned int v1119; // ecx
  unsigned int v1120; // r10d
  unsigned int v1121; // ebx
  HANDLE v1122; // rax
  _DWORD *v1123; // rax
  void *v1124; // r14
  int v1125; // eax
  bool v1126; // sf
  FARPROC v1127; // rax
  unsigned int v1128; // r9d
  int v1129; // ecx
  int v1130; // r9d
  SIZE_T v1131; // r10
  unsigned int v1132; // r10d
  int v1133; // r9d
  int v1134; // r9d
  void *v1135; // r11
  unsigned int v1136; // r11d
  int v1137; // r9d
  int v1138; // r9d
  unsigned int v1139; // r10d
  int v1140; // r9d
  int v1141; // r10d
  int v1142; // r11d
  HANDLE v1143; // rax
  _QWORD *v1144; // rax
  _DWORD *v1145; // rcx
  HANDLE v1146; // rax
  void *v1147; // rcx
  LPVOID v1148; // rax
  HANDLE v1149; // rax
  void *v1150; // rcx
  SIZE_T v1151; // rax
  HANDLE v1152; // rax
  void *v1153; // rcx
  void *v1154; // rcx
  HANDLE v1155; // rax
  HANDLE v1156; // rax
  HANDLE v1157; // rax
  HANDLE v1158; // rax
  LPVOID *v1159; // rdx
  unsigned int *v1160; // rax
  HANDLE v1161; // rax
  HANDLE v1162; // rax
  HANDLE v1163; // rax
  HANDLE v1164; // rax
  void *v1165; // rax
  void *v1166; // r9
  size_t v1167; // r10
  unsigned __int8 v1168; // al
  unsigned __int8 *v1169; // r11
  int v1170; // r14d
  unsigned int v1171; // r10d
  unsigned int v1172; // eax
  unsigned int v1173; // ecx
  _BYTE *v1174; // rcx
  unsigned int v1175; // r8d
  unsigned int v1176; // edx
  unsigned int v1177; // r11d
  unsigned int v1178; // r8d
  unsigned int v1179; // r9d
  unsigned int v1180; // r14d
  int v1181; // eax
  char v1182; // r10
  int v1183; // r11d
  int v1184; // r15d
  SIZE_T v1185; // r12
  _BYTE *v1186; // rsi
  unsigned int v1187; // r13d
  int v1188; // r10d
  unsigned __int8 *v1189; // rax
  int v1190; // ecx
  int v1191; // edi
  int v1192; // ebx
  int v1193; // edi
  int v1194; // edx
  int v1195; // ebx
  unsigned int v1196; // r8d
  int v1197; // r9d
  unsigned int v1198; // edx
  int v1199; // r8d
  int v1200; // r9d
  unsigned int v1201; // edx
  int v1202; // r8d
  int v1203; // r10d
  int v1204; // r11d
  unsigned int v1205; // r9d
  int v1206; // r8d
  unsigned int v1207; // r9d
  int v1208; // r10d
  int v1209; // r11d
  int v1210; // edx
  int v1211; // r8d
  unsigned int v1212; // r9d
  int v1213; // edx
  unsigned int v1214; // r11d
  int v1215; // r10d
  int v1216; // r8d
  unsigned int v1217; // r9d
  int v1218; // r8d
  size_t m; // rcx
  void *v1220; // r14
  int v1221; // edx
  void *v1222; // rcx
  void *v1223; // r9
  int v1224; // r10d
  _DWORD *v1225; // r9
  int v1226; // r10d
  unsigned int v1227; // r11d
  unsigned int v1228; // r10d
  __int64 v1229; // r11
  __int64 v1230; // r8
  void *v1231; // r10
  int v1232; // eax
  void *v1233; // r9
  LPVOID v1234; // rax
  LPVOID v1235; // r11
  unsigned int *v1236; // r11
  __int64 v1237; // rdx
  __int64 v1238; // r11
  int v1239; // eax
  void *v1240; // rcx
  HANDLE v1241; // rax
  LPVOID v1242; // rax
  int v1243; // eax
  HANDLE v1244; // rax
  void *v1245; // rsi
  HANDLE v1246; // rax
  void *v1247; // rsi
  HANDLE v1248; // rax
  void *v1249; // rsi
  HANDLE v1250; // rax
  HANDLE v1251; // rax
  void *v1252; // rdi
  HANDLE v1253; // rax
  HANDLE v1254; // rax
  _QWORD *v1255; // rbx
  void *v1256; // rdi
  HANDLE v1257; // rax
  void *v1258; // rdi
  HANDLE v1259; // rax
  void *v1260; // rdi
  HANDLE v1261; // rax
  HANDLE v1262; // rax
  HANDLE v1263; // rax
  unsigned int v1264; // r9d
  unsigned int v1265; // r10d
  _DWORD *v1266; // r11
  _DWORD *v1267; // rcx
  size_t v1268; // rcx
  __int64 v1269; // rbx
  unsigned int v1270; // r10d
  int v1271; // r9d
  int v1272; // eax
  __int64 i9; // rbx
  HMODULE v1274; // rcx
  unsigned int dwBytes; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int dwBytes_4; // [rsp+64h] [rbp-9Ch] BYREF
  size_t v1278; // [rsp+68h] [rbp-98h] BYREF
  SIZE_T v1279; // [rsp+70h] [rbp-90h] BYREF
  SIZE_T v1280; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v1281; // [rsp+80h] [rbp-80h]
  SIZE_T v1282; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v1283; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v1284; // [rsp+94h] [rbp-6Ch] BYREF
  LPVOID v1285; // [rsp+98h] [rbp-68h]
  int v1286; // [rsp+A0h] [rbp-60h]
  void *v1287; // [rsp+A8h] [rbp-58h] BYREF
  size_t pcchLength; // [rsp+B0h] [rbp-50h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID v1290; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID v1291; // [rsp+C8h] [rbp-38h] BYREF
  SIZE_T v1292; // [rsp+D0h] [rbp-30h]
  SIZE_T v1293; // [rsp+D8h] [rbp-28h] BYREF
  LPVOID v1294; // [rsp+E0h] [rbp-20h]
  LPVOID v1295; // [rsp+E8h] [rbp-18h] BYREF
  LPVOID v1296; // [rsp+F0h] [rbp-10h]
  SIZE_T v1297; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v1298; // [rsp+100h] [rbp+0h]
  void *Src; // [rsp+108h] [rbp+8h] BYREF
  SIZE_T Size; // [rsp+110h] [rbp+10h]
  unsigned int v1301; // [rsp+118h] [rbp+18h]
  size_t v1302; // [rsp+120h] [rbp+20h]
  void *v1303; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int64 v1304; // [rsp+130h] [rbp+30h]
  SIZE_T v1305; // [rsp+138h] [rbp+38h]
  LPVOID lpMem[2]; // [rsp+140h] [rbp+40h] BYREF
  LPVOID v1307; // [rsp+150h] [rbp+50h] BYREF
  _DWORD *v1308; // [rsp+158h] [rbp+58h] BYREF
  void *v1309; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v1310; // [rsp+168h] [rbp+68h] BYREF
  size_t v1311[2]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v1312; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v1313; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v1314; // [rsp+18Ch] [rbp+8Ch] BYREF
  unsigned int v1315; // [rsp+190h] [rbp+90h] BYREF
  int v1316; // [rsp+198h] [rbp+98h]
  unsigned int v1317; // [rsp+1A0h] [rbp+A0h]
  __int128 v1318; // [rsp+1A8h] [rbp+A8h]
  __int64 v1319; // [rsp+1B8h] [rbp+B8h]
  unsigned int v1320; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v1321; // [rsp+1C4h] [rbp+C4h] BYREF
  unsigned int v1322; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned int v1323; // [rsp+1CCh] [rbp+CCh] BYREF
  unsigned int v1324; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned int v1325; // [rsp+1D4h] [rbp+D4h] BYREF
  int v1326; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned int v1327[3]; // [rsp+1DCh] [rbp+DCh] BYREF
  _BYTE *v1328; // [rsp+1E8h] [rbp+E8h] BYREF
  DWORD *v1329; // [rsp+1F0h] [rbp+F0h] BYREF
  HMODULE hModule; // [rsp+1F8h] [rbp+F8h] BYREF
  void *v1331; // [rsp+200h] [rbp+100h]
  HMODULE phModule; // [rsp+208h] [rbp+108h] BYREF
  __int128 v1333; // [rsp+218h] [rbp+118h] BYREF
  __int128 v1334; // [rsp+228h] [rbp+128h]
  __int128 v1335; // [rsp+238h] [rbp+138h] BYREF
  __int128 v1336; // [rsp+248h] [rbp+148h]
  __int64 v1337; // [rsp+258h] [rbp+158h] BYREF
  __int64 v1338; // [rsp+260h] [rbp+160h] BYREF
  DWORD *v1339; // [rsp+270h] [rbp+170h]
  __int64 v1340; // [rsp+280h] [rbp+180h] BYREF
  __int128 v1341; // [rsp+288h] [rbp+188h] BYREF
  __int64 v1342; // [rsp+298h] [rbp+198h] BYREF
  __int64 v1343[16]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _OWORD v1344[3]; // [rsp+320h] [rbp+220h] BYREF
  _QWORD v1345[20]; // [rsp+350h] [rbp+250h] BYREF
  int v1346; // [rsp+3F0h] [rbp+2F0h] BYREF
  int v1347; // [rsp+3F4h] [rbp+2F4h]
  void *v1348; // [rsp+3F8h] [rbp+2F8h]
  void *v1349; // [rsp+400h] [rbp+300h]
  void *v1350; // [rsp+408h] [rbp+308h]
  size_t v1351; // [rsp+410h] [rbp+310h]
  size_t v1352; // [rsp+418h] [rbp+318h]
  __int64 v1353; // [rsp+420h] [rbp+320h]
  int v1354; // [rsp+428h] [rbp+328h]
  int v1355; // [rsp+42Ch] [rbp+32Ch] BYREF
  int v1356; // [rsp+430h] [rbp+330h]
  signed int v1357; // [rsp+434h] [rbp+334h]
  int v1358; // [rsp+438h] [rbp+338h]
  int v1359; // [rsp+43Ch] [rbp+33Ch] BYREF
  int v1360; // [rsp+440h] [rbp+340h]
  signed int v1361; // [rsp+444h] [rbp+344h]
  unsigned int v1362; // [rsp+448h] [rbp+348h]
  unsigned int v1363; // [rsp+44Ch] [rbp+34Ch] BYREF
  unsigned int v1364; // [rsp+450h] [rbp+350h]
  unsigned int v1365; // [rsp+454h] [rbp+354h]
  unsigned int v1366; // [rsp+458h] [rbp+358h]
  int v1367; // [rsp+460h] [rbp+360h] BYREF
  _DWORD v1368[3]; // [rsp+464h] [rbp+364h] BYREF
  __int16 v1369; // [rsp+472h] [rbp+372h]
  __int64 v1370; // [rsp+478h] [rbp+378h]
  int v1371; // [rsp+4D0h] [rbp+3D0h] BYREF
  _DWORD v1372[5]; // [rsp+4D4h] [rbp+3D4h] BYREF
  SIZE_T v1373; // [rsp+4E8h] [rbp+3E8h]
  int v1374; // [rsp+540h] [rbp+440h] BYREF
  _DWORD v1375[5]; // [rsp+544h] [rbp+444h] BYREF
  size_t v1376; // [rsp+558h] [rbp+458h]
  int v1377; // [rsp+5B0h] [rbp+4B0h] BYREF
  _DWORD v1378[5]; // [rsp+5B4h] [rbp+4B4h] BYREF
  size_t v1379; // [rsp+5C8h] [rbp+4C8h]
  int v1380; // [rsp+620h] [rbp+520h] BYREF
  _DWORD v1381[5]; // [rsp+624h] [rbp+524h] BYREF
  size_t v1382; // [rsp+638h] [rbp+538h]
  int v1383; // [rsp+690h] [rbp+590h] BYREF
  char v1384[20]; // [rsp+694h] [rbp+594h] BYREF
  SIZE_T v1385; // [rsp+6A8h] [rbp+5A8h]
  int v1386; // [rsp+700h] [rbp+600h] BYREF
  char v1387[20]; // [rsp+704h] [rbp+604h] BYREF
  SIZE_T v1388; // [rsp+718h] [rbp+618h]
  int v1389; // [rsp+770h] [rbp+670h] BYREF
  char v1390[20]; // [rsp+774h] [rbp+674h] BYREF
  SIZE_T v1391; // [rsp+788h] [rbp+688h]
  int v1392; // [rsp+7E0h] [rbp+6E0h] BYREF
  char v1393[20]; // [rsp+7E4h] [rbp+6E4h] BYREF
  SIZE_T v1394; // [rsp+7F8h] [rbp+6F8h]
  __int128 v1395; // [rsp+850h] [rbp+750h] BYREF
  __int128 v1396; // [rsp+860h] [rbp+760h] BYREF
  __int128 v1397; // [rsp+870h] [rbp+770h] BYREF
  __int128 v1398; // [rsp+880h] [rbp+780h] BYREF
  __int64 v1399; // [rsp+890h] [rbp+790h] BYREF
  unsigned int v1400; // [rsp+898h] [rbp+798h]
  int v1401; // [rsp+89Ch] [rbp+79Ch]
  _DWORD v1402[12]; // [rsp+8A0h] [rbp+7A0h] BYREF
  __int128 v1403; // [rsp+8D0h] [rbp+7D0h] BYREF
  __int128 v1404; // [rsp+8E0h] [rbp+7E0h] BYREF
  __int64 v1405; // [rsp+8F0h] [rbp+7F0h]
  __int128 v1406; // [rsp+8F8h] [rbp+7F8h] BYREF
  _OWORD v1407[2]; // [rsp+908h] [rbp+808h] BYREF
  __int128 v1408; // [rsp+928h] [rbp+828h] BYREF
  _OWORD v1409[2]; // [rsp+938h] [rbp+838h] BYREF
  __int128 v1410; // [rsp+958h] [rbp+858h] BYREF
  _OWORD v1411[2]; // [rsp+968h] [rbp+868h] BYREF
  __int128 v1412; // [rsp+988h] [rbp+888h] BYREF
  _OWORD v1413[2]; // [rsp+998h] [rbp+898h] BYREF
  __int128 v1414; // [rsp+9B8h] [rbp+8B8h] BYREF
  __int128 v1415; // [rsp+9C8h] [rbp+8C8h] BYREF
  __int64 v1416; // [rsp+9D8h] [rbp+8D8h]
  _OWORD v1417[2]; // [rsp+9E0h] [rbp+8E0h] BYREF
  _DWORD v1418[6]; // [rsp+A00h] [rbp+900h] BYREF
  char v1419; // [rsp+A1Ah] [rbp+91Ah]
  unsigned __int16 v1420[34]; // [rsp+A1Ch] [rbp+91Ch] BYREF
  _DWORD v1421[6]; // [rsp+A60h] [rbp+960h] BYREF
  char v1422; // [rsp+A7Ah] [rbp+97Ah]
  unsigned __int16 v1423[34]; // [rsp+A7Ch] [rbp+97Ch] BYREF
  _DWORD v1424[6]; // [rsp+AC0h] [rbp+9C0h] BYREF
  char v1425; // [rsp+ADAh] [rbp+9DAh]
  unsigned __int16 v1426[34]; // [rsp+ADCh] [rbp+9DCh] BYREF
  _BYTE v1427[68]; // [rsp+B20h] [rbp+A20h] BYREF
  __int16 v1428; // [rsp+B64h] [rbp+A64h]
  unsigned __int16 v1429; // [rsp+BC6h] [rbp+AC6h]
  int v1430; // [rsp+BCCh] [rbp+ACCh]
  int v1431; // [rsp+BD0h] [rbp+AD0h]
  int v1432; // [rsp+C00h] [rbp+B00h] BYREF
  __int128 v1433; // [rsp+C08h] [rbp+B08h]
  __int128 v1434; // [rsp+C18h] [rbp+B18h]
  __int128 v1435; // [rsp+C28h] [rbp+B28h]
  __int64 v1436; // [rsp+C38h] [rbp+B38h]
  _BYTE v1437[176]; // [rsp+C40h] [rbp+B40h] BYREF
  WCHAR Filename[264]; // [rsp+CF0h] [rbp+BF0h] BYREF

  psz = pwszValueName;
  v1339 = pdwValue;
  v1329 = 0;
  if ( pwszValueName && pdwValue )
  {
    dwBytes_4 = 0;
    v1312 = 0;
    while ( _InterlockedCompareExchange(&dword_1801173E4, 1, 0) )
      ;
    v3 = dword_1801173E0;
    v1310 = -1;
    if ( dword_1801173E0 )
      goto LABEL_24;
    v4 = MemoryAlloc(0x338u);
    v5 = v4;
    if ( !v4 )
      goto LABEL_14;
    v6 = qword_1800F4460;
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
      goto LABEL_14;
    }
    v1301 = 0;
    v5[823] = 0;
    v46 = 0;
    memset_0(qword_180116EF0, 0, 0x60u);
    v47 = v5;
    if ( *v5 )
    {
      while ( 1 )
      {
        v57 = -1;
        do
          ++v57;
        while ( *(_WORD *)&v5[2 * v57] );
        v58 = (HMODULE *)&qword_180116EF0[3 * v46];
        if ( !GetModuleHandleExW(0, (LPCWSTR)v5, v58) )
          break;
        v59 = &v5[2 * v57];
        if ( *(_WORD *)*v58 == 23117
          && (v60 = *((int *)*v58 + 15), (unsigned int)v60 < 0x10000000)
          && (v61 = (char *)*v58 + v60, v61 >= (char *)*v58)
          && *(_DWORD *)v61 == 17744 )
        {
          if ( ((*((_WORD *)v61 + 12) - 267) & 0xFEFF) != 0 )
          {
            v48 = -1073741811;
          }
          else
          {
            v48 = 0;
            *(__int64 *)((char *)&qword_180116EF0[3 * v46 + 1] + 4) = *((_QWORD *)v61 + 17);
            LODWORD(qword_180116EF0[3 * v46 + 1]) = *((_DWORD *)v61 + 20);
          }
        }
        else
        {
          v48 = -1073741701;
        }
        v62 = *(_DWORD *)(v59 + 2);
        v63 = 0;
        v5 = v59 + 6;
        for ( LODWORD(v1282) = v62; v63 < v62; ++v63 )
        {
          v64 = -1;
          do
            ++v64;
          while ( v5[v64] );
          if ( v48 >= 0 )
          {
            ProcAddress = GetProcAddress(*v58, v5);
            if ( !ProcAddress )
              goto LABEL_53;
            off_180114000[v1301] = ProcAddress;
            v62 = v1282;
          }
          v5 += v64 + 1;
          ++v1301;
        }
        ++v46;
        if ( !*v5 )
          goto LABEL_53;
      }
      v48 = -1073741702;
LABEL_53:
      if ( !v47 )
        goto LABEL_22;
    }
    else
    {
      v48 = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v47);
LABEL_22:
    if ( v48 < 0 )
    {
LABEL_14:
      for ( i = 0; i != 4; ++i )
      {
        v45 = (HMODULE)qword_180116EF0[3 * i];
        if ( v45 )
          FreeLibrary(v45);
      }
      memset_0(qword_180116EF0, 0, 0x60u);
      memcpy_0(off_180114000, off_1800E1E60, 0x170u);
LABEL_25:
      _InterlockedExchange(&dword_1801173E4, 0);
      v50 = 0;
      Src = 0;
      v51 = 0;
      pcchLength = 0;
      v52 = 0;
      if ( NtCurrentPeb()->SessionId )
      {
        v53 = 0;
        v54 = off_180114110[0]();
        if ( !v54 )
        {
LABEL_27:
          LastError = GetLastError();
          v56 = LastError < 0;
          if ( LastError > 0 )
          {
            LastError = (unsigned __int16)LastError | 0x80070000;
            v56 = LastError < 0;
          }
          if ( !v56 )
            LastError = -2147467259;
          goto LABEL_102;
        }
        v1324 = 0;
        v66 = 0;
        v1278 = 0;
        for ( j = 0; ; v1278 = (size_t)j )
        {
          v68 = 0;
          if ( j )
            v68 = j;
          if ( ((unsigned int (__fastcall *)(__int64, __int64, void *, __int64, unsigned int *))off_180114130[0])(
                 v54,
                 2,
                 v68,
                 v66,
                 &v1324) )
          {
            Src = j;
            LastError = 0;
            v50 = (const wchar_t *)j;
            goto LABEL_69;
          }
          LastError = GetLastError();
          if ( LastError != 122 )
            break;
          if ( j )
            goto LABEL_64;
          j = MemoryAlloc(v1324);
          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1278);
          if ( !j )
          {
            LastError = -2147024882;
LABEL_69:
            v1278 = 0;
            goto LABEL_70;
          }
          v66 = v1324;
        }
        if ( !LastError )
        {
LABEL_64:
          LastError = -2147467259;
          goto LABEL_70;
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_70:
        SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1278);
        if ( LastError < 0 )
          goto LABEL_102;
        v69 = off_180114128[0];
        CurrentThreadId = GetCurrentThreadId();
        v71 = ((__int64 (__fastcall *)(_QWORD))v69)(CurrentThreadId);
        if ( !v71 )
          goto LABEL_27;
        v1323 = 0;
        v72 = 0;
        v1278 = 0;
        for ( k = 0; ; v1278 = (size_t)k )
        {
          v74 = 0;
          if ( k )
            v74 = k;
          if ( ((unsigned int (__fastcall *)(__int64, __int64, const wchar_t *, __int64, unsigned int *))off_180114130[0])(
                 v71,
                 2,
                 v74,
                 v72,
                 &v1323) )
          {
            pcchLength = (size_t)k;
            LastError = 0;
            v51 = k;
            goto LABEL_86;
          }
          LastError = GetLastError();
          if ( LastError != 122 )
            break;
          if ( k )
            goto LABEL_81;
          k = (const wchar_t *)MemoryAlloc(v1323);
          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1278);
          if ( !k )
          {
            LastError = -2147024882;
LABEL_86:
            v1278 = 0;
            goto LABEL_87;
          }
          v72 = v1323;
        }
        if ( !LastError )
        {
LABEL_81:
          LastError = -2147467259;
          goto LABEL_87;
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_87:
        SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1278);
        if ( LastError < 0 )
        {
LABEL_102:
          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&pcchLength);
          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&Src);
          v77 = 0;
          if ( LastError >= 0 )
            v77 = v53;
          LODWORD(v1296) = v77;
          v78 = LocalAlloc(0x40u, 4u);
          SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v1312, v78);
          v1331 = (void *)v1312;
          if ( !v1312 )
          {
            v82 = -2147024882;
            v965 = 0;
            goto LABEL_1580;
          }
          v1317 = 0;
          *(_OWORD *)lpMem = 0;
          v1291 = 0;
          v79 = GetProcessHeap();
          v80 = HeapAlloc(v79, 8u, 0xA0u);
          v1286 = -805306345;
          v81 = v80;
          v82 = -1073741801;
          if ( !v80 )
          {
            v83 = 0;
            LODWORD(v1279) = -1073741801;
LABEL_138:
            v116 = lpMem[1];
            lpMem[0] = 0;
            if ( lpMem[1] )
            {
              v117 = GetProcessHeap();
              HeapFree(v117, 0, v116);
              lpMem[1] = 0;
            }
            v118 = v1291;
            if ( v1291 )
            {
              v119 = GetProcessHeap();
              HeapFree(v119, 0, v118);
            }
            if ( v81 )
            {
              v120 = GetProcessHeap();
              HeapFree(v120, 0, v81);
            }
            if ( v83 )
            {
              v121 = GetProcessHeap();
              HeapFree(v121, 0, v83);
            }
            if ( v82 >= 0 )
            {
              if ( !v77 )
              {
LABEL_1223:
                v965 = v1317;
                v1329 = (DWORD *)v1331;
                v1312 = 0;
                goto LABEL_1580;
              }
              v1307 = 0;
              dword_180116EE8 = v77;
              ModuleFileNameW = GetModuleFileNameW(&_ImageBase, Filename, 0x104u);
              v123 = 0;
              if ( !ModuleFileNameW || ModuleFileNameW == 260 && GetLastError() == 122 )
              {
LABEL_1191:
                SH<void *,SH_HANDLE>::Reset(&v1307);
                v929 = 0;
                *(_OWORD *)v1311 = 0;
                v1292 = 0;
                v930 = GetProcessHeap();
                v931 = HeapAlloc(v930, 8u, 0xA0u);
                v932 = v931;
                if ( !v931 )
                {
                  v932 = 0;
LABEL_1215:
                  v960 = (void *)v1311[1];
                  v1311[0] = 0;
                  if ( v1311[1] )
                  {
                    v961 = GetProcessHeap();
                    HeapFree(v961, 0, v960);
                    v1311[1] = 0;
                  }
                  if ( v929 )
                  {
                    v962 = GetProcessHeap();
                    HeapFree(v962, 0, v929);
                  }
                  if ( v932 )
                  {
                    v963 = GetProcessHeap();
                    HeapFree(v963, 0, v932);
                  }
                  if ( v123 )
                  {
                    v964 = GetProcessHeap();
                    HeapFree(v964, 0, v123);
                  }
                  goto LABEL_1223;
                }
                *v931 = xmmword_180115F40;
                v931[1] = xmmword_180115F50;
                v931[2] = xmmword_180115F60;
                v931[3] = xmmword_180115F70;
                v931[4] = xmmword_180115F80;
                v931[5] = xmmword_180115F90;
                v931[6] = xmmword_180115FA0;
                v931[7] = xmmword_180115FB0;
                v931[8] = xmmword_180115FC0;
                v931[9] = xmmword_180115FD0;
                v933 = GetProcessHeap();
                v934 = HeapAlloc(v933, 8u, 8u);
                v935 = 0;
                v936 = v934;
                if ( !v934 )
                {
LABEL_1204:
                  v929 = v935;
                  goto LABEL_1215;
                }
                *v934 = qword_180115E80;
                v1307 = (LPVOID)__rdtsc();
                v1283 = 0;
                dwBytes_4 = 0;
                if ( (int)RtlUIntAdd(4, 4, &dwBytes_4) < 0 )
                  goto LABEL_1203;
                if ( (int)RtlUIntAdd(0, dwBytes_4, &v1283) < 0 )
                {
                  v123 = v936;
                  v929 = v937;
                  goto LABEL_1215;
                }
                dwBytes_4 = v939;
                if ( (int)RtlUIntAdd(v938, 160, &dwBytes_4) < 0 )
                  goto LABEL_1203;
                v940 = RtlUIntAdd(v1283, dwBytes_4, &v1283);
                if ( (v942 | v940) < 0 )
                  goto LABEL_1203;
                dwBytes_4 = (unsigned int)v935;
                if ( (int)RtlUIntAdd(v941, 8, &dwBytes_4) < 0 )
                  goto LABEL_1203;
                v943 = RtlUIntAdd(v1283, dwBytes_4, &v1283);
                if ( (v945 | v943) < 0 )
                  goto LABEL_1203;
                dwBytes_4 = (unsigned int)v935;
                if ( (int)RtlUIntAdd(v944, 8, &dwBytes_4) < 0
                  || (v946 = RtlUIntAdd(v1283, dwBytes_4, &v1283), (v947 | v946) < 0)
                  || (HIDWORD(v1311[0]) = v1283,
                      v948 = v1283,
                      v949 = GetProcessHeap(),
                      v950 = HeapAlloc(v949, 8u, v948),
                      v935 = 0,
                      (v951 = v950) == 0) )
                {
LABEL_1203:
                  v123 = v936;
                  goto LABEL_1204;
                }
                v1311[1] = (size_t)v950;
                LODWORD(v1303) = 0;
                v1302 = 0;
                LODWORD(v1311[0]) = 0;
                v123 = v936;
                pcchLength = (size_t)v950;
                v929 = 0;
                LODWORD(v1282) = 8;
                if ( (int)RtlULongLongAdd(v950, 4, &v1303) < 0
                  || (unsigned __int64)(v951 + 2) > v1311[1] + HIDWORD(v1311[0]) )
                {
                  goto LABEL_1215;
                }
                v954 = v1303;
                *v951 = v952;
                v955 = v1282;
                *v954 = v952;
                v956 = LODWORD(v1311[0]) + 1;
                LODWORD(v1303) = 0;
                ++LODWORD(v1311[0]);
                v1302 = 0;
                if ( v932 )
                {
                  if ( !v953 )
                    goto LABEL_1214;
                }
                else if ( v953 )
                {
LABEL_1209:
                  v929 = 0;
                  goto LABEL_1215;
                }
                v957 = (unsigned int *)v1311[1];
                if ( v1311[1] )
                {
                  pcchLength = v1311[1];
                  v966 = 0;
                  if ( v956 )
                  {
                    do
                    {
                      v967 = *v957;
                      dwBytes_4 = 0;
                      if ( (int)RtlUIntAdd(4, v967, &dwBytes_4) < 0
                        || (int)RtlULongLongAdd(v968, dwBytes_4, &pcchLength) < 0 )
                      {
                        goto LABEL_1214;
                      }
                      v957 = (unsigned int *)pcchLength;
                    }
                    while ( ++v966 < v969 );
                  }
                  if ( (int)RtlULongLongAdd(v957, 4, &v1303) < 0
                    || (v972 = v971, (unsigned __int64)v970 + v971 + 4 > v1311[1] + HIDWORD(v1311[0])) )
                  {
LABEL_1214:
                    v929 = (_DWORD *)v1292;
                    goto LABEL_1215;
                  }
                  *v970 = v971;
                  v959 = 0;
                  if ( v932 )
                  {
                    memcpy_0(v1303, v932, v972);
                    v959 = 0;
                  }
                }
                else
                {
                  dwBytes_4 = 0;
                  v958 = RtlUIntAdd(4, v953, &dwBytes_4);
                  v935 = 0;
                  if ( v958 < 0 )
                    goto LABEL_1204;
                  if ( (int)RtlUIntAdd(HIDWORD(v1311[0]), dwBytes_4, (char *)v1311 + 4) < 0 )
                    goto LABEL_1214;
                }
                v973 = LODWORD(v1311[0]) + 1;
                LODWORD(v1303) = 0;
                ++LODWORD(v1311[0]);
                v1302 = 0;
                if ( v123 )
                {
                  if ( !v955 )
                    goto LABEL_1214;
                }
                else if ( v955 )
                {
                  goto LABEL_1209;
                }
                v974 = (unsigned int *)v1311[1];
                if ( v1311[1] )
                {
                  v929 = 0;
                  pcchLength = v1311[1];
                  if ( v973 )
                  {
                    do
                    {
                      v975 = *v974;
                      dwBytes_4 = 0;
                      if ( (int)RtlUIntAdd(4, v975, &dwBytes_4) < 0
                        || (int)RtlULongLongAdd(v976, dwBytes_4, &pcchLength) < 0 )
                      {
                        goto LABEL_1215;
                      }
                      v974 = (unsigned int *)pcchLength;
                    }
                    while ( v978 + 1 < v977 );
                  }
                  v979 = RtlULongLongAdd(v974, 4, &v1303);
                  v935 = 0;
                  if ( v979 < 0 || (unsigned __int64)v980 + v955 + 4 > v1311[1] + HIDWORD(v1311[0]) )
                    goto LABEL_1204;
                  *v980 = v955;
                  if ( v123 )
                  {
                    memcpy_0(v1303, v123, v955);
                    LODWORD(v935) = 0;
                  }
                }
                else
                {
                  dwBytes_4 = v959;
                  if ( (int)RtlUIntAdd(4, v955, &dwBytes_4) < 0
                    || (int)RtlUIntAdd(HIDWORD(v1311[0]), dwBytes_4, (char *)v1311 + 4) < 0 )
                  {
                    goto LABEL_1214;
                  }
                }
                v981 = (unsigned int *)v1311[1];
                v982 = LODWORD(v1311[0]) + 1;
                LODWORD(v1303) = 0;
                ++LODWORD(v1311[0]);
                v1302 = 0;
                if ( !v1311[1] )
                {
                  dwBytes_4 = (unsigned int)v935;
                  if ( (int)RtlUIntAdd(4, 8, &dwBytes_4) < 0
                    || (int)RtlUIntAdd(HIDWORD(v1311[0]), dwBytes_4, (char *)v1311 + 4) < 0 )
                  {
                    goto LABEL_1214;
                  }
                  ++LODWORD(v1311[0]);
LABEL_1259:
                  dwBytes_4 = v984;
                  if ( (int)RtlUIntAdd(v983, v983, &dwBytes_4) < 0 )
                    goto LABEL_1214;
                  LODWORD(v1282) = dwBytes_4;
                  dwBytes_4 = v994;
                  if ( (int)RtlUIntAdd(v993, 8, &dwBytes_4) < 0 || (int)RtlUIntAdd(v995, dwBytes_4, &v1282) < 0 )
                    goto LABEL_1214;
                  v997 = v1282;
                  dwBytes = v1282;
                  v1282 = v996;
                  LODWORD(v1304) = v996;
                  v1307 = (LPVOID)__rdtsc();
                  v1314 = 8;
                  v998 = RtlUIntAdd(8, HIDWORD(v1311[0]), &v1314);
                  if ( v998 < 0 )
                  {
                    psz = (STRSAFE_PCNZWCH)v123;
                    v1291 = v932;
                  }
                  else
                  {
                    v1002 = (v1314 + 7) & 0xFFFFFFF8;
                    if ( v1002 < v1314 )
                      goto LABEL_1214;
                    v1314 = (v1314 + 7) & 0xFFFFFFF8;
                    v1003 = v1002;
                    v1004 = GetProcessHeap();
                    v1005 = (char *)HeapAlloc(v1004, 8u, v1003);
                    LODWORD(v1001) = 0;
                    v1006 = v1005;
                    if ( !v1005 )
                    {
LABEL_1562:
                      if ( v1286 >= (int)v1001 )
                      {
                        v929 = (_DWORD *)v1292;
                        if ( (_DWORD)v1304 )
                        {
                          if ( v1292 )
                          {
                            v1297 = v1292;
                            if ( (int)RtlULongLongAdd(v1292, 4, &v1297) >= 0 )
                            {
                              v1267 = (_DWORD *)v1297;
                              if ( *v929 == (_DWORD)v1266 )
                                v1267 = v1266;
                              if ( *v929 == v1265 && *v1267 >= (int)v1266 && v1264 > 1 )
                              {
                                v1268 = (size_t)v929;
                                v1278 = (size_t)v929;
                                v1269 = v1265;
                                while ( (int)RtlULongLongAdd(v1268, v1269, &v1278) >= 0
                                     && (int)RtlULongLongAdd(v1278, v1270, &v1278) >= 0 )
                                {
                                  v1268 = v1278;
                                  if ( v1271 != -1 )
                                  {
                                    RtlULongLongAdd(v1278, v1269, &v1278);
                                    goto LABEL_1215;
                                  }
                                }
                              }
                            }
                          }
                        }
                        goto LABEL_1215;
                      }
                      goto LABEL_1214;
                    }
                    v1278 = (size_t)v1005;
                    v1291 = v932;
                    psz = (STRSAFE_PCNZWCH)v123;
                    dwBytes = v997;
                    *(_DWORD *)v1005 = v1311[0];
                    LODWORD(v1280) = RtlULongLongAdd(v1005, 4, &v1278);
                    if ( (v1280 & 0x80000000) != 0LL
                      || (v1008 = v1278,
                          *(_DWORD *)v1278 = HIDWORD(v1311[0]),
                          LODWORD(v1280) = RtlULongLongAdd(v1008, v1007, &v1278),
                          (v1280 & 0x80000000) != 0LL) )
                    {
                      v1291 = v932;
                      psz = (STRSAFE_PCNZWCH)v123;
                      dwBytes = v997;
                      v1009 = GetProcessHeap();
                      HeapFree(v1009, 0, v1006);
                      v999 = v1282;
                      v1000 = v1282;
                    }
                    else
                    {
                      *(_QWORD *)&v1006[v1314 - 8] = v1307;
                      memcpy_0((void *)v1278, (const void *)v1311[1], HIDWORD(v1311[0]));
                      v1000 = v1314;
                      v999 = (SIZE_T)v1006;
                      v1282 = (SIZE_T)v1006;
                    }
                    v998 = v1280;
                    v1001 = 0;
                  }
                  v1010 = v998 | 0x10000000;
                  v1309 = v1001;
                  v1011 = v1001;
                  v1296 = v1001;
                  v1280 = (SIZE_T)v1001;
                  v1012 = (const void **)v1001;
                  v1290 = v1001;
                  if ( v1010 < 0 )
                  {
                    v1286 = v1010;
                    goto LABEL_1536;
                  }
                  if ( !v999 )
                    goto LABEL_1214;
                  Src = (void *)v1000;
                  if ( !v1000 || (v1293 = v1000 + 8LL, (Size = (SIZE_T)MemoryAlloc(v1293)) == 0) )
                  {
                    v1069 = (void *)v1282;
                    v1124 = v1011;
                    v1286 = -805306367;
                    goto LABEL_1539;
                  }
                  v1013 = 0;
                  v1278 = 0;
                  v1014 = 0;
                  v1015 = (unsigned __int64)Src;
                  v1281 = 0;
                  if ( Src )
                  {
                    do
                      v1013 ^= *(_BYTE *)(v1282 + v1014++);
                    while ( v1014 < (unsigned __int64)Src );
                    v1281 = v1013;
                  }
                  v1295 = (LPVOID)0xC81ECB17B1B54A58LL;
                  v1297 = v1282;
                  v1016 = (unsigned __int8 *)v1282;
                  pcchLength = Size;
                  v1017 = (unsigned __int8)Src & 7;
                  if ( ((unsigned __int8)Src & 7) != 0 )
                  {
                    v1298 = 0;
                    LODWORD(v1305) = 0;
                    v1018 = 0;
                    v1019 = 0;
                    v1020 = 0;
                    do
                    {
                      v1021 = *v1016++;
                      dwBytes_4 = 8 * v1018;
                      if ( v1018 >= 4 )
                        v1019 |= v1021 << (56 - dwBytes_4);
                      else
                        v1020 |= v1021 << (24 - dwBytes_4);
                      ++v1018;
                    }
                    while ( (int)v1018 < v1017 );
                    LODWORD(v1305) = v1020;
                    v1022 = v1020;
                    v1012 = (const void **)v1011;
                    v1023 = (_BYTE *)pcchLength;
                    v1298 = v1019;
                    v1297 = (SIZE_T)v1016;
                    psz = (STRSAFE_PCNZWCH)v123;
                    v1291 = v932;
                    v1024 = v1022 ^ 0xB17A307A;
                    LODWORD(v1285) = 0;
                    v1025 = v1019 ^ 0x42F6B18D;
                    v1026 = v1024;
                    if ( ((unsigned __int8)Src & 7) != 0 )
                    {
                      v1027 = (unsigned int)v1285;
                      v1028 = v1298 ^ 0x42F6B18D;
                      do
                      {
                        v1307 = v1023 + 1;
                        if ( v1027 >= 4 )
                        {
                          v1028 = __ROR4__(v1028, 24);
                          v1029 = v1028;
                        }
                        else
                        {
                          v1026 = __ROR4__(v1026, 24);
                          v1029 = v1026;
                        }
                        *v1023 = v1029;
                        ++v1027;
                        v1023 = v1307;
                      }
                      while ( (int)v1027 < v1017 );
                      v1013 = v1281;
                      pcchLength = (size_t)v1307;
                      v1011 = (_DWORD *)v1280;
                    }
                    if ( (unsigned int)v1017 <= 4 )
                    {
                      v1030 = 0;
                      if ( (unsigned int)v1017 < 4 )
                        v1024 = v1024 >> (8 * (4 - v1017)) << (8 * (4 - v1017));
                    }
                    else
                    {
                      v1030 = v1025 >> (8 * (8 - v1017)) << (8 * (8 - v1017));
                    }
                  }
                  else
                  {
                    v1024 = 0;
                    LODWORD(v1305) = 0;
                    v1030 = -1;
                    v1298 = 0;
                  }
                  if ( v1015 >> 3 )
                  {
                    v1031 = (unsigned __int8 *)v1297;
                    v1032 = v1015 >> 3;
                    v1033 = (_BYTE *)pcchLength;
                    v1034 = v1305;
                    v1283 = 19032;
                    LODWORD(v1294) = WORD1(v1295);
                    v1312 = 0;
                    v1035 = HIDWORD(v1295);
                    v1284 = WORD2(v1295);
                    dwBytes_4 = HIWORD(v1295);
                    LODWORD(v1285) = HIDWORD(v1295) ^ 0xB1B54A58;
                    v1036 = v1298;
                    v1037 = HIDWORD(v1295) ^ 0xB1B54A58;
                    do
                    {
                      v1038 = v1031[1];
                      v1039 = *v1031;
                      v1040 = v1031[4];
                      v1031 += 8;
                      v1041 = *(v1031 - 5) | ((*(v1031 - 6) | ((v1038 | (v1039 << 8)) << 8)) << 8);
                      v1042 = *(v1031 - 1) | ((*(v1031 - 2) | ((*(v1031 - 3) | (v1040 << 8)) << 8)) << 8);
                      v1043 = v1030 ^ v1042;
                      v1044 = v1024 ^ v1041 ^ v1035 ^ ((v1030 ^ v1042) - v1283);
                      v1045 = v1043 ^ (__ROR4__(v1044, 7) + WORD1(v1295) * __ROR4__(v1044 ^ v1035, 15));
                      v1046 = v1044 ^ (v1284 * __ROR4__(v1045 - 1313519016, 9) - __ROR4__(v1045, 10));
                      v1047 = v1045 ^ (__ROR4__(v1046, 27) + HIWORD(v1295) * __ROR4__(v1284 ^ v1046, 28));
                      v1035 = HIDWORD(v1295);
                      v1048 = v1046 ^ (HIDWORD(v1295) - (v1047 ^ 0xB1B54A58));
                      v1049 = v1047 ^ (WORD1(v1295) * (v1048 - v1283) - (v1048 >> 6));
                      v1050 = v1048 ^ (v1283 * (v1284 ^ __ROR4__(v1049, 15)));
                      v1051 = v1049 ^ (v1284 * (dwBytes_4 + __ROR4__(~v1050, 3)));
                      v1052 = v1050 ^ (v1051 - HIDWORD(v1295) - v1283);
                      v1053 = v1051 ^ ((_DWORD)v1294 * (dwBytes_4 ^ v1052)) ^ __ROR4__(v1052, 10);
                      v1054 = v1052 ^ __ROR4__(v1053, 3) ^ (v1284 * __ROR4__(v1283 ^ v1053, 26));
                      v1055 = v1053 ^ (v1283 * (__ROR4__(v1054, 15) - HIWORD(v1295)));
                      v1056 = v1054
                            ^ ((v1055 ^ (v1055 >> 14)) >> 1)
                            ^ (v1283 * (v1055 ^ HIWORD(v1295)))
                            ^ (v1283 * (((v1055 - v1284) >> 29) | (8 * (v1055 - v1284))));
                      v1057 = v1055 ^ (WORD1(v1295) * (v1056 - v1284) - (v1056 >> 13));
                      v1058 = v1056 ^ __ROR4__(v1057, 11) ^ (v1284 * __ROR4__(-1313519016 - v1057, 9));
                      v1059 = v1057 ^ (v1058 + 1313519016 - HIWORD(v1295));
                      v1060 = v1058 ^ (v1283 * (v1059 ^ WORD1(v1295)) - __ROR4__(v1059, 7));
                      v1061 = v1059 ^ (WORD1(v1295) * __ROR4__(v1060 ^ HIWORD(v1295), 28) - __ROR4__(v1060, 16));
                      v1062 = v1060 ^ (__ROR4__(v1061, 4) + v1284 * __ROR4__(-1313519016 - v1061, 10));
                      v1063 = v1061 ^ __ROR4__(v1062, 9) ^ (HIWORD(v1295) * __ROR4__(v1062 + 1313519016, 4));
                      v1064 = v1062 ^ (v1283 * __ROR4__(v1063 ^ HIDWORD(v1295), 24) - __ROR4__(v1063, 30));
                      v1065 = v1063 ^ (WORD1(v1295) * __ROR4__(HIDWORD(v1295) - v1064, 11) - __ROR4__(v1064, 12));
                      v1066 = v1064 ^ (v1065 >> 8) ^ (v1284 * (WORD1(v1295) ^ v1065));
                      v1024 = v1034 ^ v1066;
                      v1030 = v1036 ^ v1066 ^ v1037 ^ v1065;
                      v1033[3] = v1034 ^ v1066;
                      LOBYTE(v1065) = __ROR4__(v1034 ^ v1066, 8);
                      v1034 = v1041;
                      v1033[7] = v1030;
                      v1036 = v1042;
                      v1033[2] = v1065;
                      v1033[6] = __ROR4__(v1030, 8);
                      v1033[1] = __ROR4__(v1024, 16);
                      v1033[5] = __ROR4__(v1030, 16);
                      *v1033 = __ROR4__(v1024, 24);
                      v1033[4] = __ROR4__(v1030, 24);
                      v1033 += 8;
                      ++v1312;
                    }
                    while ( v1312 < v1032 );
                    v1011 = (_DWORD *)v1280;
                    v1013 = v1281;
                    v1012 = (const void **)v1280;
                    v82 = v1279;
                    v932 = v1291;
                    v123 = psz;
                    v1015 = (unsigned __int64)Src;
                  }
                  *(_QWORD *)(Size + v1015) = v1013;
                  v1067 = GetProcessHeap();
                  v1068 = HeapAlloc(v1067, 8u, 0x30u);
                  v1291 = v1068;
                  if ( !v1068 )
                  {
                    v1069 = (void *)v1282;
                    v1283 = -1073741801;
                    goto LABEL_1317;
                  }
                  v1070 = v1293;
                  *v1068 = v1293;
                  v1071 = GetProcessHeap();
                  v1072 = HeapAlloc(v1071, 8u, v1070);
                  v1069 = (void *)v1282;
                  v1073 = v1072;
                  v339 = v1072 == 0;
                  v1074 = dwBytes;
                  if ( !v339 )
                  {
                    *((_QWORD *)v1291 + 1) = v1073;
                    memcpy_0(v1073, (const void *)Size, (unsigned int)v1293);
                    *((_DWORD *)v1291 + 4) = 160;
                    v1075 = GetProcessHeap();
                    v1076 = HeapAlloc(v1075, 8u, 0xA0u);
                    v1077 = v1291;
                    if ( v1076 )
                    {
                      *((_QWORD *)v1291 + 3) = v1076;
                      *v1076 = xmmword_180115E90;
                      v1076[1] = xmmword_180115EA0;
                      v1076[2] = xmmword_180115EB0;
                      v1076[3] = xmmword_180115EC0;
                      v1076[4] = xmmword_180115ED0;
                      v1076[5] = xmmword_180115EE0;
                      v1076[6] = xmmword_180115EF0;
                      v1076[7] = xmmword_180115F00;
                      v1076[8] = xmmword_180115F10;
                      v1076[9] = xmmword_180115F20;
                      v1077[8] = 8;
                      v1078 = GetProcessHeap();
                      v1079 = HeapAlloc(v1078, 8u, 8u);
                      if ( v1079 )
                      {
                        v1085 = v1291;
                        *((_QWORD *)v1291 + 5) = v1079;
                        *v1079 = qword_180115F30;
                        v1278 = (size_t)v1085;
                        v1283 = 0;
                        v1282 = (SIZE_T)v1069;
                        goto LABEL_1316;
                      }
                      v1077 = v1291;
                    }
                    v1291 = v1077;
                    v1074 = dwBytes;
                  }
                  dwBytes = v1074;
                  v1080 = v1291;
                  v1283 = -1073741801;
                  v1282 = (SIZE_T)v1069;
                  v1307 = (LPVOID)*((_QWORD *)v1291 + 1);
                  if ( v1307 )
                  {
                    v1081 = GetProcessHeap();
                    HeapFree(v1081, 0, v1307);
                    v1080 = v1291;
                    *((_QWORD *)v1291 + 1) = 0;
                  }
                  v1307 = (LPVOID)*((_QWORD *)v1080 + 3);
                  if ( v1307 )
                  {
                    v1082 = GetProcessHeap();
                    HeapFree(v1082, 0, v1307);
                    v1080 = v1291;
                    *((_QWORD *)v1291 + 3) = 0;
                  }
                  v1307 = (LPVOID)*((_QWORD *)v1080 + 5);
                  if ( v1307 )
                  {
                    v1083 = GetProcessHeap();
                    HeapFree(v1083, 0, v1307);
                    *((_QWORD *)v1291 + 5) = 0;
                  }
                  v1084 = GetProcessHeap();
                  HeapFree(v1084, 0, v1291);
                  if ( (v1283 & 0x80000000) != 0 )
                  {
LABEL_1317:
                    v1086 = GetProcessHeap();
                    HeapFree(v1086, 0, (LPVOID)Size);
                    v1087 = v1278;
                    LODWORD(v1001) = 0;
                    if ( v1278 )
                    {
                      v1307 = *(LPVOID *)(v1278 + 8);
                      if ( v1307 )
                      {
                        v1088 = GetProcessHeap();
                        HeapFree(v1088, 0, v1307);
                        v1087 = v1278;
                        *(_QWORD *)(v1278 + 8) = 0;
                      }
                      v1307 = *(LPVOID *)(v1087 + 24);
                      if ( v1307 )
                      {
                        v1089 = GetProcessHeap();
                        HeapFree(v1089, 0, v1307);
                        v1087 = v1278;
                        *(_QWORD *)(v1278 + 24) = 0;
                      }
                      v1307 = *(LPVOID *)(v1087 + 40);
                      if ( v1307 )
                      {
                        v1090 = GetProcessHeap();
                        HeapFree(v1090, 0, v1307);
                        *(_QWORD *)(v1278 + 40) = 0;
                      }
                      v1091 = GetProcessHeap();
                      HeapFree(v1091, 0, (LPVOID)v1278);
                      LODWORD(v1001) = 0;
                    }
                    if ( (v1283 & 0x80000000) != 0 )
                    {
                      v1124 = v1290;
                      v1286 = v1283 | 0x10000000;
                      goto LABEL_1538;
                    }
                    v1092 = *(unsigned int *)v1012;
                    dwBytes_4 = 0;
                    v1284 = 4;
                    v1286 = RtlUIntAdd(4, v1092, &v1284);
                    if ( v1286 < 0 )
                      goto LABEL_1344;
                    v1286 = RtlUIntAdd(v1284, v1093, &v1284);
                    if ( v1286 < 0
                      || (v1094 = *((unsigned int *)v1012 + 4),
                          v1297 = (SIZE_T)(v1012 + 2),
                          v1286 = RtlUIntAdd(v1284, v1094, &v1284),
                          v1286 < 0)
                      || (v1286 = RtlUIntAdd(v1284, v1095, &v1284), v1286 < 0)
                      || (v1096 = *((unsigned int *)v1012 + 8),
                          pcchLength = (size_t)(v1012 + 4),
                          v1286 = RtlUIntAdd(v1284, v1096, &v1284),
                          v1286 < 0) )
                    {
LABEL_1344:
                      v1100 = dwBytes;
                      v1282 = (SIZE_T)v1069;
                    }
                    else
                    {
                      v1097 = v1284;
                      v1098 = GetProcessHeap();
                      v1099 = (wchar_t *)HeapAlloc(v1098, 8u, v1097);
                      LODWORD(v1001) = 0;
                      psz = v1099;
                      if ( !v1099 )
                      {
                        v1286 = -805306345;
LABEL_1333:
                        v1011 = (_DWORD *)v1280;
LABEL_1536:
                        v1124 = v1011;
                        goto LABEL_1537;
                      }
                      v1100 = dwBytes;
                      *(_DWORD *)v1099 = *(_DWORD *)v1012;
                      v1282 = (SIZE_T)v1069;
                      v1291 = v1099;
                      v1286 = RtlULongLongAdd(v1099, 4, &v1291);
                      if ( v1286 < 0 )
                      {
                        psz = v1101;
                      }
                      else
                      {
                        memcpy_0(v1291, v1012[1], *(unsigned int *)v1012);
                        v1286 = RtlULongLongAdd(v1291, *(unsigned int *)v1012, &v1291);
                        if ( v1286 >= 0 )
                        {
                          v1102 = v1291;
                          *(_DWORD *)v1291 = *(_DWORD *)v1297;
                          v1286 = RtlULongLongAdd(v1102, 4, &v1291);
                          if ( v1286 >= 0 )
                          {
                            memcpy_0(v1291, v1012[3], *v1103);
                            v1286 = RtlULongLongAdd(v1291, *(unsigned int *)v1297, &v1291);
                            if ( v1286 >= 0 )
                            {
                              v1104 = v1291;
                              *(_DWORD *)v1291 = *(_DWORD *)pcchLength;
                              v1286 = RtlULongLongAdd(v1104, 4, &v1291);
                              if ( v1286 >= 0 )
                              {
                                memcpy_0(v1291, v1012[5], *v1105);
                                v1106 = RtlULongLongAdd(v1291, *(unsigned int *)pcchLength, &v1291);
                                LODWORD(v1001) = 0;
                                v1286 = v1106;
                                if ( v1106 >= 0 )
                                {
                                  v1309 = (void *)psz;
                                  dwBytes_4 = v1284;
LABEL_1346:
                                  v1108 = v1106 | 0x10000000;
                                  if ( v1108 < 0 )
                                    goto LABEL_1350;
                                  v1320 = 8;
                                  v1109 = RtlUIntAdd(8, v1100, &v1320);
                                  v1108 = v1110 | v1109;
                                  if ( v1108 < 0 )
                                    goto LABEL_1350;
                                  v1111 = (v1320 + 7) & 0xFFFFFFF8;
                                  if ( (unsigned int)v1111 < v1320 )
                                  {
                                    v1108 = -1073741675;
LABEL_1350:
                                    v1286 = v1108;
                                    goto LABEL_1333;
                                  }
                                  v1327[0] = (v1320 + 7) & 0xFFFFFFF8;
                                  v1108 = RtlUIntAdd(v1111, 8, v1327);
                                  if ( v1108 < 0 )
                                    goto LABEL_1350;
                                  v1112 = v1311[1];
                                  v1291 = v932;
                                  psz = (STRSAFE_PCNZWCH)v123;
                                  v1282 = (SIZE_T)v1069;
                                  v1287 = v1012;
                                  v1301 = (unsigned int)v1001;
                                  if ( !v1311[1] )
                                    goto LABEL_1353;
                                  v1287 = v1012;
                                  v1282 = (SIZE_T)v1069;
                                  psz = (STRSAFE_PCNZWCH)v123;
                                  v1291 = v932;
                                  if ( LODWORD(v1311[0]) <= 1 )
                                    goto LABEL_1353;
                                  v1278 = v1311[1];
                                  do
                                  {
                                    v1108 = RtlULongLongAdd(v1112, 4, &v1278);
                                    if ( v1108 < 0 )
                                    {
LABEL_1374:
                                      LODWORD(v1001) = 0;
                                      goto LABEL_1350;
                                    }
                                    v1108 = RtlULongLongAdd(v1278, v1113, &v1278);
                                    LODWORD(v1001) = 0;
                                    if ( v1108 < 0 )
                                      goto LABEL_1350;
                                    v1112 = v1278;
                                  }
                                  while ( v1114 == -1 );
                                  v1115 = *(_DWORD *)v1278;
                                  v1108 = RtlULongLongAdd(v1278, 4, &v1278);
                                  if ( v1108 < 0 )
                                    goto LABEL_1350;
                                  v1116 = v1311[1];
                                  if ( !v1311[1] || LODWORD(v1311[0]) <= 2 )
                                  {
LABEL_1353:
                                    v1108 = -1073741811;
                                    goto LABEL_1350;
                                  }
                                  v1278 = v1311[1];
                                  do
                                  {
                                    v1108 = RtlULongLongAdd(v1116, 4, &v1278);
                                    if ( v1108 < 0 )
                                      goto LABEL_1374;
                                    v1108 = RtlULongLongAdd(v1278, v1117, &v1278);
                                    LODWORD(v1001) = 0;
                                    if ( v1108 < 0 )
                                      goto LABEL_1350;
                                    v1116 = v1278;
                                  }
                                  while ( (unsigned int)(v1118 + 1) < 2 );
                                  v1108 = RtlULongLongAdd(v1278, 4, &v1278);
                                  if ( v1108 < 0 )
                                    goto LABEL_1350;
                                  v1301 = (unsigned int)v1001;
                                  v1283 = 4;
                                  v1108 = RtlUIntAdd((unsigned int)((_DWORD)v1001 + 4), v1327[0], &v1283);
                                  if ( v1108 < 0 )
                                    goto LABEL_1350;
                                  v1108 = RtlUIntAdd(v1283, v1119, &v1283);
                                  if ( v1108 < 0 )
                                    goto LABEL_1350;
                                  v1108 = RtlUIntAdd(v1283, v1115, &v1283);
                                  if ( v1108 < 0 )
                                    goto LABEL_1350;
                                  v1108 = RtlUIntAdd(v1283, (unsigned int)((_DWORD)v1001 + 4), &v1283);
                                  if ( v1108 < 0 )
                                    goto LABEL_1350;
                                  v1108 = RtlUIntAdd(v1283, v1120, &v1283);
                                  if ( v1108 < 0 )
                                    goto LABEL_1350;
                                  v1301 = v1283;
                                  if ( v1283 > 0x400000 )
                                  {
                                    v1108 = -2147418113;
                                    goto LABEL_1350;
                                  }
                                  v1121 = v1283;
                                  v1122 = GetProcessHeap();
                                  v1123 = HeapAlloc(v1122, 8u, v1121);
                                  LODWORD(v1001) = 0;
                                  v1011 = v1123;
                                  if ( !v1123 )
                                  {
                                    v1011 = 0;
                                    goto LABEL_1377;
                                  }
                                  hModule = 0;
                                  v1335 = 0;
                                  v1336 = 0;
                                  if ( !v1309 )
                                  {
                                    v1286 = -2147024809;
                                    goto LABEL_1378;
                                  }
                                  LODWORD(v1336) = dwBytes_4;
                                  *(_QWORD *)&v1335 = v1309;
                                  *(_QWORD *)((char *)&v1336 + 4) = v1301;
                                  *((_QWORD *)&v1335 + 1) = v1123;
                                  if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                    && (v1127 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                  {
                                    v1125 = ((__int64 (__fastcall *)(__int64, __int128 *))v1127)(134, &v1335)
                                          | 0x10000000;
                                    if ( v1125 >= 0 )
                                    {
                                      v1128 = DWORD1(v1336);
                                      LODWORD(v1001) = 0;
                                      goto LABEL_1394;
                                    }
                                    LODWORD(v1001) = 0;
                                  }
                                  else
                                  {
                                    v1125 = GetLastError();
                                    LODWORD(v1001) = 0;
                                    v1126 = v1125 < 0;
                                    if ( v1125 > 0 )
                                    {
                                      v1125 = (unsigned __int16)v1125 | 0x80070000;
                                      v1126 = v1125 < 0;
                                    }
                                    if ( !v1126 )
                                    {
                                      v1286 = -2147467259;
                                      goto LABEL_1378;
                                    }
                                  }
                                  if ( v1125 == -805306333 )
                                  {
                                    v1286 = -2147024774;
                                    goto LABEL_1378;
                                  }
                                  if ( v1125 < 0 )
                                  {
                                    v1286 = v1125;
                                    goto LABEL_1378;
                                  }
                                  v1128 = v1301;
LABEL_1394:
                                  dwBytes = 0;
                                  v1293 = (SIZE_T)v1011;
                                  if ( v1128 < 4 )
                                  {
LABEL_1395:
                                    v1286 = -805306306;
                                    goto LABEL_1378;
                                  }
                                  dwBytes_4 = *v1011;
                                  v1129 = RtlULongLongAdd(v1011, 4, &v1293);
                                  if ( v1129 >= 0 )
                                  {
                                    v1129 = RtlUIntAdd(0, 4, &dwBytes);
                                    if ( v1129 >= 0 )
                                    {
                                      if ( v1130 - dwBytes < (unsigned int)v1131 )
                                        goto LABEL_1395;
                                      pcchLength = v1293;
                                      v1297 = v1131;
                                      v1129 = RtlULongLongAdd(v1293, (unsigned int)v1131, &v1293);
                                      if ( v1129 >= 0 )
                                      {
                                        v1129 = RtlUIntAdd(dwBytes, v1132, &dwBytes);
                                        if ( v1129 >= 0 )
                                        {
                                          if ( v1133 - dwBytes < 4 )
                                            goto LABEL_1395;
                                          LODWORD(v1285) = *(_DWORD *)v1293;
                                          v1129 = RtlULongLongAdd(v1293, 4, &v1293);
                                          if ( v1129 >= 0 )
                                          {
                                            v1129 = RtlUIntAdd(dwBytes, 4, &dwBytes);
                                            if ( v1129 >= 0 )
                                            {
                                              if ( v1134 - dwBytes < (unsigned int)v1135 )
                                              {
LABEL_1405:
                                                v1124 = v1290;
                                                LODWORD(v1001) = 0;
                                                v1286 = -805306306;
LABEL_1537:
                                                v1069 = (void *)v1282;
LABEL_1538:
                                                if ( !v1069 )
                                                {
LABEL_1540:
                                                  if ( v1012 )
                                                  {
                                                    v1245 = (void *)v1012[1];
                                                    if ( v1245 )
                                                    {
                                                      v1246 = GetProcessHeap();
                                                      HeapFree(v1246, 0, v1245);
                                                      v1012[1] = 0;
                                                    }
                                                    v1247 = (void *)v1012[3];
                                                    if ( v1247 )
                                                    {
                                                      v1248 = GetProcessHeap();
                                                      HeapFree(v1248, 0, v1247);
                                                      v1012[3] = 0;
                                                    }
                                                    v1249 = (void *)v1012[5];
                                                    if ( v1249 )
                                                    {
                                                      v1250 = GetProcessHeap();
                                                      HeapFree(v1250, 0, v1249);
                                                      v1012[5] = 0;
                                                    }
                                                    v1251 = GetProcessHeap();
                                                    HeapFree(v1251, 0, v1012);
                                                    LODWORD(v1001) = 0;
                                                  }
                                                  v1252 = v1309;
                                                  if ( v1309 )
                                                  {
                                                    v1253 = GetProcessHeap();
                                                    HeapFree(v1253, 0, v1252);
                                                    LODWORD(v1001) = 0;
                                                  }
                                                  if ( v1011 )
                                                  {
                                                    v1254 = GetProcessHeap();
                                                    HeapFree(v1254, 0, v1011);
                                                    LODWORD(v1001) = 0;
                                                  }
                                                  v1255 = v1296;
                                                  if ( v1296 )
                                                  {
                                                    v1256 = (void *)*((_QWORD *)v1296 + 1);
                                                    if ( v1256 )
                                                    {
                                                      v1257 = GetProcessHeap();
                                                      HeapFree(v1257, 0, v1256);
                                                      v1255[1] = 0;
                                                    }
                                                    v1258 = (void *)v1255[3];
                                                    if ( v1258 )
                                                    {
                                                      v1259 = GetProcessHeap();
                                                      HeapFree(v1259, 0, v1258);
                                                      v1255[3] = 0;
                                                    }
                                                    v1260 = (void *)v1255[5];
                                                    if ( v1260 )
                                                    {
                                                      v1261 = GetProcessHeap();
                                                      HeapFree(v1261, 0, v1260);
                                                      v1255[5] = 0;
                                                    }
                                                    v1262 = GetProcessHeap();
                                                    HeapFree(v1262, 0, v1255);
                                                    LODWORD(v1001) = 0;
                                                  }
                                                  if ( v1124 )
                                                  {
                                                    v1263 = GetProcessHeap();
                                                    HeapFree(v1263, 0, v1124);
                                                    LODWORD(v1001) = 0;
                                                  }
                                                  goto LABEL_1562;
                                                }
LABEL_1539:
                                                v1244 = GetProcessHeap();
                                                HeapFree(v1244, 0, v1069);
                                                LODWORD(v1001) = 0;
                                                goto LABEL_1540;
                                              }
                                              Size = v1293;
                                              Src = v1135;
                                              v1129 = RtlULongLongAdd(v1293, v1135, &v1293);
                                              if ( v1129 >= 0 )
                                              {
                                                v1129 = RtlUIntAdd(dwBytes, v1136, &dwBytes);
                                                if ( v1129 >= 0 )
                                                {
                                                  if ( v1137 - dwBytes < 4 )
                                                    goto LABEL_1405;
                                                  LODWORD(v1294) = *(_DWORD *)v1293;
                                                  v1129 = RtlULongLongAdd(v1293, 4, &v1293);
                                                  if ( v1129 >= 0 )
                                                  {
                                                    v1129 = RtlUIntAdd(dwBytes, 4, &dwBytes);
                                                    if ( v1129 >= 0 )
                                                    {
                                                      if ( v1138 - dwBytes < v1139 )
                                                        goto LABEL_1405;
                                                      v1129 = RtlUIntAdd(dwBytes, v1139, &dwBytes);
                                                      if ( v1129 >= 0 )
                                                      {
                                                        if ( v1140 != dwBytes
                                                          || v1141 + v1142 + dwBytes_4 + 12LL != v1140 )
                                                        {
                                                          goto LABEL_1405;
                                                        }
                                                        v1143 = GetProcessHeap();
                                                        v1144 = HeapAlloc(v1143, 8u, 0x30u);
                                                        LODWORD(v1001) = 0;
                                                        v1295 = v1144;
                                                        v1145 = v1144;
                                                        if ( !v1144 )
                                                        {
                                                          v1296 = 0;
LABEL_1377:
                                                          v1286 = -805306345;
LABEL_1378:
                                                          v1124 = v1290;
                                                          goto LABEL_1537;
                                                        }
                                                        v1291 = v932;
                                                        psz = (STRSAFE_PCNZWCH)v123;
                                                        v1282 = (SIZE_T)v1069;
                                                        v1287 = v1012;
                                                        v1278 = 0;
                                                        if ( pcchLength )
                                                        {
                                                          *(_DWORD *)v1144 = dwBytes_4;
                                                          v1146 = GetProcessHeap();
                                                          v1147 = HeapAlloc(v1146, 8u, v1297);
                                                          v1148 = v1295;
                                                          if ( !v1147 )
                                                          {
LABEL_1428:
                                                            v1154 = (void *)*((_QWORD *)v1148 + 1);
                                                            v1283 = -1073741801;
                                                            v1280 = (SIZE_T)v1011;
                                                            v1307 = v1154;
                                                            if ( v1154 )
                                                            {
                                                              v1155 = GetProcessHeap();
                                                              HeapFree(v1155, 0, v1307);
                                                              v1148 = v1295;
                                                              *((_QWORD *)v1295 + 1) = 0;
                                                            }
                                                            v1307 = (LPVOID)*((_QWORD *)v1148 + 3);
                                                            if ( v1307 )
                                                            {
                                                              v1156 = GetProcessHeap();
                                                              HeapFree(v1156, 0, v1307);
                                                              v1148 = v1295;
                                                              *((_QWORD *)v1295 + 3) = 0;
                                                            }
                                                            v1307 = (LPVOID)*((_QWORD *)v1148 + 5);
                                                            if ( v1307 )
                                                            {
                                                              v1157 = GetProcessHeap();
                                                              HeapFree(v1157, 0, v1307);
                                                              *((_QWORD *)v1295 + 5) = 0;
                                                            }
                                                            v1158 = GetProcessHeap();
                                                            HeapFree(v1158, 0, v1295);
                                                            v1159 = (LPVOID *)v1278;
                                                            LODWORD(v1001) = 0;
                                                            goto LABEL_1438;
                                                          }
                                                          *((_QWORD *)v1295 + 1) = v1147;
                                                          v1283 = 0;
                                                          memcpy_0(v1147, (const void *)pcchLength, v1297);
                                                          v1145 = v1295;
                                                          LODWORD(v1001) = 0;
                                                        }
                                                        else
                                                        {
                                                          *(_DWORD *)v1144 = 0;
                                                          v1144[1] = 0;
                                                          v1283 = 0;
                                                        }
                                                        if ( Size )
                                                        {
                                                          v1145[4] = (_DWORD)v1285;
                                                          v1149 = GetProcessHeap();
                                                          v1150 = HeapAlloc(v1149, 8u, (SIZE_T)Src);
                                                          v1148 = v1295;
                                                          if ( !v1150 )
                                                          {
LABEL_1427:
                                                            v1291 = v932;
                                                            psz = (STRSAFE_PCNZWCH)v123;
                                                            v1282 = (SIZE_T)v1069;
                                                            v1287 = v1012;
                                                            v1295 = v1148;
                                                            goto LABEL_1428;
                                                          }
                                                          *((_QWORD *)v1295 + 3) = v1150;
                                                          v1283 = 0;
                                                          memcpy_0(v1150, (const void *)Size, (size_t)Src);
                                                          v1145 = v1295;
                                                          LODWORD(v1001) = 0;
                                                        }
                                                        else
                                                        {
                                                          v1145[4] = 0;
                                                          *((_QWORD *)v1145 + 3) = 0;
                                                        }
                                                        if ( v1293 )
                                                        {
                                                          v1151 = (unsigned int)v1294;
                                                          v1145[8] = (_DWORD)v1294;
                                                          v1297 = v1151;
                                                          v1152 = GetProcessHeap();
                                                          v1153 = HeapAlloc(v1152, 8u, v1297);
                                                          v1148 = v1295;
                                                          if ( !v1153 )
                                                            goto LABEL_1427;
                                                          *((_QWORD *)v1295 + 5) = v1153;
                                                          v1283 = 0;
                                                          memcpy_0(v1153, (const void *)v1293, v1297);
                                                          v1145 = v1295;
                                                          LODWORD(v1001) = 0;
                                                        }
                                                        else
                                                        {
                                                          v1145[8] = 0;
                                                          *((_QWORD *)v1145 + 5) = 0;
                                                        }
                                                        v1159 = (LPVOID *)v1145;
                                                        v1278 = (size_t)v1145;
                                                        v1280 = (SIZE_T)v1011;
                                                        v1287 = v1012;
                                                        v1282 = (SIZE_T)v1069;
                                                        psz = (STRSAFE_PCNZWCH)v123;
                                                        v1291 = v932;
LABEL_1438:
                                                        v1129 = v1283;
                                                        if ( (v1283 & 0x80000000) != 0 )
                                                        {
                                                          v1160 = 0;
                                                          v1296 = 0;
                                                          if ( v1159 )
                                                          {
                                                            v1307 = v1159[1];
                                                            if ( v1307 )
                                                            {
                                                              v1161 = GetProcessHeap();
                                                              HeapFree(v1161, 0, v1307);
                                                              v1159 = (LPVOID *)v1278;
                                                              *(_QWORD *)(v1278 + 8) = 0;
                                                            }
                                                            v1307 = v1159[3];
                                                            if ( v1307 )
                                                            {
                                                              v1162 = GetProcessHeap();
                                                              HeapFree(v1162, 0, v1307);
                                                              v1159 = (LPVOID *)v1278;
                                                              *(_QWORD *)(v1278 + 24) = 0;
                                                            }
                                                            v1307 = v1159[5];
                                                            if ( v1307 )
                                                            {
                                                              v1163 = GetProcessHeap();
                                                              HeapFree(v1163, 0, v1307);
                                                              *(_QWORD *)(v1278 + 40) = 0;
                                                            }
                                                            v1164 = GetProcessHeap();
                                                            HeapFree(v1164, 0, (LPVOID)v1278);
                                                            v1129 = v1283;
                                                            LODWORD(v1001) = 0;
                                                            v1160 = 0;
                                                            v1296 = 0;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v1160 = (unsigned int *)v1159;
                                                          v1296 = v1159;
                                                        }
                                                        goto LABEL_1450;
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                          LODWORD(v1001) = 0;
                                        }
                                      }
                                    }
                                  }
                                  v1160 = (unsigned int *)v1296;
                                  v1280 = (SIZE_T)v1011;
LABEL_1450:
                                  v1286 = v1129 | 0x10000000;
                                  if ( v1129 < 0 )
                                    goto LABEL_1378;
                                  if ( !v1160 || (Size = *((_QWORD *)v1160 + 1)) == 0 || *v1160 == (_DWORD)v1001 )
                                  {
                                    v1286 = -805306355;
                                    goto LABEL_1378;
                                  }
                                  v1278 = *v1160 - 8LL;
                                  v1165 = MemoryAlloc(v1278);
                                  LODWORD(v1001) = 0;
                                  v1290 = v1165;
                                  v1166 = v1165;
                                  if ( !v1165 )
                                    goto LABEL_1482;
                                  v1167 = v1278;
                                  v1168 = 0;
                                  v1169 = (unsigned __int8 *)Size;
                                  v1281 = 0;
                                  v1297 = v1278 & 7;
                                  v1293 = 0x7F1137FAB69605ELL;
                                  pcchLength = Size;
                                  Src = v1166;
                                  if ( (v1278 & 7) != 0 )
                                  {
                                    v1310 = 0;
                                    v1298 = 0;
                                    LODWORD(v1285) = 0;
                                    v1170 = 0;
                                    v1171 = 0;
                                    v1172 = 0;
                                    do
                                    {
                                      v1173 = *v1169++;
                                      v1283 = v1173;
                                      dwBytes_4 = 8 * v1170;
                                      if ( (unsigned int)v1170 >= 4 )
                                      {
                                        v1283 <<= 56 - dwBytes_4;
                                        v1172 |= v1283;
                                      }
                                      else
                                      {
                                        v1283 <<= 24 - dwBytes_4;
                                        v1171 |= v1283;
                                      }
                                      ++v1170;
                                    }
                                    while ( v1170 < (int)v1297 );
                                    v1298 = v1171;
                                    v1174 = v1166;
                                    v1175 = v1171;
                                    v1167 = v1278;
                                    v1310 = v1172;
                                    v1168 = v1281;
                                    v1176 = v1297;
                                    pcchLength = (size_t)v1169;
                                    v1280 = (SIZE_T)v1011;
                                    v1287 = v1012;
                                    v1282 = (SIZE_T)v1069;
                                    psz = (STRSAFE_PCNZWCH)v123;
                                    v1291 = v932;
                                    v1177 = v1310 ^ 0x699A899C;
                                    LODWORD(v1285) = 0;
                                    v1178 = v1175 ^ 0x92F65A5;
                                    if ( (_DWORD)v1297 )
                                    {
                                      v1179 = (unsigned int)v1285;
                                      v1180 = v1178;
                                      v1181 = v1310 ^ 0x699A899C;
                                      do
                                      {
                                        v1307 = v1174 + 1;
                                        if ( v1179 >= 4 )
                                        {
                                          v1181 = __ROR4__(v1181, 24);
                                          v1182 = v1181;
                                        }
                                        else
                                        {
                                          v1180 = __ROR4__(v1180, 24);
                                          v1182 = v1180;
                                        }
                                        *v1174 = v1182;
                                        ++v1179;
                                        v1174 = v1307;
                                      }
                                      while ( (int)v1179 < (int)v1176 );
                                      v1168 = v1281;
                                      v1011 = (_DWORD *)v1280;
                                      v1166 = v1290;
                                      Src = v1307;
                                      v1167 = v1278;
                                    }
                                    if ( v1176 <= 4 )
                                    {
                                      v1183 = 0;
                                      if ( v1176 < 4 )
                                        v1178 = v1178 >> (8 * (4 - v1176)) << (8 * (4 - v1176));
                                    }
                                    else
                                    {
                                      v1183 = v1177 >> (8 * (8 - v1176)) << (8 * (8 - v1176));
                                    }
                                  }
                                  else
                                  {
                                    v1298 = 0;
                                    v1183 = 0;
                                    v1178 = 0;
                                  }
                                  if ( v1167 >> 3 )
                                  {
                                    v1184 = HIDWORD(v1293);
                                    v1185 = v1167 >> 3;
                                    v1186 = Src;
                                    v1187 = v1298;
                                    v1188 = WORD2(v1293);
                                    v1283 = 24670;
                                    v1189 = (unsigned __int8 *)pcchLength;
                                    LODWORD(v1305) = WORD2(v1293);
                                    v1297 = 0;
                                    do
                                    {
                                      v1190 = *v1189;
                                      v1191 = v1189[1];
                                      v1192 = v1189[4];
                                      v1189 += 8;
                                      v1193 = *(v1189 - 5) | ((*(v1189 - 6) | (((v1190 << 8) | v1191) << 8)) << 8);
                                      v1194 = v1178 ^ v1193;
                                      v1195 = *(v1189 - 1)
                                            | ((*(v1189 - 2) | ((*(v1189 - 3) | (v1192 << 8)) << 8)) << 8);
                                      v1196 = v1184 ^ v1178 ^ v1193 ^ v1183 ^ v1195 ^ 0xAB69605E;
                                      v1197 = v1194 ^ (__ROR4__(v1196, 22) + v1188 * __ROR4__(v1196 + 1419157410, 27));
                                      v1198 = v1196 ^ (WORD1(v1293) * __ROR4__(v1184 + v1197, 9) - __ROR4__(v1197, 30));
                                      v1199 = v1197 ^ (v1283 * (v1198 - v1188) - (v1198 >> 13));
                                      v1200 = v1198
                                            ^ (HIWORD(v1293) * __ROR4__(v1199 ^ WORD1(v1293), 26) - __ROR4__(v1199, 30));
                                      v1201 = v1199 ^ (v1184 - (v1200 ^ 0xAB69605E));
                                      v1202 = v1200 ^ (WORD1(v1293) * (v1201 ^ v1188)) ^ __ROR4__(v1201, 6);
                                      v1203 = v1201 ^ (__ROR4__(v1202, 30) + v1283 * __ROR4__(v1202 + v1184, 15));
                                      v1204 = v1202
                                            ^ (HIWORD(v1293) * __ROR4__(v1203 + 1419157410, 14) - __ROR4__(v1203, 24));
                                      v1205 = v1203 ^ __ROR4__(v1204, 10) ^ (v1305 * __ROR4__(v1204 ^ 0xAB69605E, 12));
                                      v1206 = v1205
                                            ^ (HIWORD(v1293)
                                             * (v1283
                                              + __ROR4__(
                                                  ~(v1204 ^ (v1205 >> 10) ^ (WORD1(v1293) * (HIWORD(v1293) ^ v1205))),
                                                  5)));
                                      v1207 = v1204
                                            ^ (v1205 >> 10)
                                            ^ (WORD1(v1293) * (HIWORD(v1293) ^ v1205))
                                            ^ (v1206 - HIWORD(v1293))
                                            ^ 0xAB69605E;
                                      v1208 = v1206 ^ ((v1207 >> 2) + v1305 * __ROR4__(HIWORD(v1293) ^ v1207, 30));
                                      v1209 = v1207 ^ (__ROR4__(v1208, 25) + WORD1(v1293) * __ROR4__(v1208 - v1184, 6));
                                      v1210 = v1208 ^ (v1283 * (v1209 ^ v1305) + __ROR4__(v1209, 9));
                                      v1211 = v1209
                                            ^ (__ROR4__(v1210, 25) + HIWORD(v1293) * __ROR4__(v1210 ^ WORD1(v1293), 27));
                                      v1212 = v1184 ^ v1210 ^ v1211 ^ 0xAB69605E;
                                      v1213 = v1211 ^ (v1305 * (__ROR4__(v1212, 3) - WORD1(v1293)));
                                      v1214 = v1310;
                                      v1310 = v1195;
                                      v1215 = v1212 ^ (v1283 * __ROR4__(v1213 - v1184, 1) - __ROR4__(v1213, 6));
                                      v1216 = v1213
                                            ^ (__ROR4__(v1215, 18) + HIWORD(v1293) * __ROR4__(v1215 - 1419157410, 29));
                                      v1217 = v1215 ^ (v1305 * __ROR4__(v1216 - 1419157410, 17) - __ROR4__(v1216, 14));
                                      v1188 = v1305;
                                      v1183 = v1216 ^ (v1217 >> 3) ^ (WORD1(v1293) * (v1217 ^ v1283)) ^ v1214;
                                      v1218 = v1187
                                            ^ __ROR4__(v1216 ^ (v1217 >> 3) ^ (WORD1(v1293) * (v1217 ^ v1283)), 30)
                                            ^ (v1283
                                             * __ROR4__(
                                                 v1184 ^ v1216 ^ (v1217 >> 3) ^ (WORD1(v1293) * (v1217 ^ v1283)),
                                                 28));
                                      v1187 = v1193;
                                      v1178 = v1217 ^ v1218;
                                      v1186[3] = v1178;
                                      v1186[7] = v1183;
                                      v1186[2] = __ROR4__(v1178, 8);
                                      v1186[6] = __ROR4__(v1183, 8);
                                      v1186[1] = __ROR4__(v1178, 16);
                                      v1186[5] = __ROR4__(v1183, 16);
                                      *v1186 = __ROR4__(v1178, 24);
                                      v1186[4] = __ROR4__(v1183, 24);
                                      v1186 += 8;
                                      ++v1297;
                                    }
                                    while ( v1297 < v1185 );
                                    v1168 = v1281;
                                    v82 = v1279;
                                    v932 = v1291;
                                    v123 = psz;
                                    v1011 = (_DWORD *)v1280;
                                    v1012 = (const void **)v1287;
                                    v1069 = (void *)v1282;
                                    v1166 = v1290;
                                    v1167 = v1278;
                                  }
                                  LODWORD(v1001) = 0;
                                  for ( m = 0; m < v1167; ++m )
                                    v1168 ^= *((_BYTE *)v1166 + m);
                                  if ( v1168 != *(_QWORD *)(v1167 + Size) )
                                  {
                                    MemoryFree(v1166);
                                    LODWORD(v1001) = 0;
LABEL_1482:
                                    v1286 = -805306367;
                                    v1124 = 0;
                                    goto LABEL_1537;
                                  }
                                  v1220 = v1296;
                                  v1310 = 0;
                                  v1278 = (size_t)v1166;
                                  if ( (unsigned int)v1167 < 4 )
                                  {
                                    v1124 = v1290;
                                    v1221 = -1073741762;
LABEL_1531:
                                    v1286 = v1221 | 0x10000000;
                                    goto LABEL_1538;
                                  }
                                  v1221 = RtlULongLongAdd(v1166, 4, &v1278);
                                  if ( v1221 < 0 )
                                  {
                                    v1296 = v1220;
                                    v1124 = v1222;
                                    goto LABEL_1531;
                                  }
                                  v1221 = RtlUIntAdd(0, 4, &v1310);
                                  if ( v1221 < 0 )
                                  {
LABEL_1489:
                                    v1296 = v1220;
                                    v1124 = v1223;
                                    goto LABEL_1531;
                                  }
                                  if ( v1224 - v1310 < 4 )
                                  {
                                    v1221 = -1073741762;
                                    goto LABEL_1489;
                                  }
                                  LODWORD(v1280) = *(_DWORD *)v1278;
                                  v1221 = RtlULongLongAdd(v1278, 4, &v1278);
                                  if ( v1221 < 0 )
                                    goto LABEL_1494;
                                  v1221 = RtlUIntAdd(v1310, 4, &v1310);
                                  if ( v1221 < 0 )
                                    goto LABEL_1494;
                                  if ( v1226 - v1310 < v1227 )
                                    goto LABEL_1493;
                                  v1221 = RtlUIntAdd(v1310, v1227, &v1310);
                                  if ( v1221 < 0 )
                                    goto LABEL_1494;
                                  v1230 = v1228;
                                  v1231 = (void *)v1278;
                                  if ( (unsigned __int64)v1225 + v1230 < v1229 + v1278
                                    || (unsigned __int64)v1225 + v1230 - v1278 - v1229 >= 8 )
                                  {
LABEL_1493:
                                    v1221 = -1073741762;
LABEL_1494:
                                    v1296 = v1220;
                                    v1124 = v1225;
LABEL_1495:
                                    LODWORD(v1001) = 0;
                                    goto LABEL_1531;
                                  }
                                  LODWORD(v1285) = *v1225;
                                  v1291 = 0;
                                  v1297 = 0;
                                  v1312 = 0;
                                  LODWORD(v1287) = 0;
                                  if ( v1278 )
                                  {
                                    v1232 = RtlULongLongAdd(v1278, v1229, &v1291);
                                    LODWORD(v1001) = 0;
                                    v1286 = v1232;
                                    v1296 = v1220;
                                    v1221 = v1232;
                                    if ( v1232 < 0 )
                                    {
                                      v1124 = v1233;
LABEL_1526:
                                      v1243 = v1304;
                                      goto LABEL_1527;
                                    }
                                    v1234 = v1291;
                                    v1235 = v1231;
                                    if ( v1231 < v1291 )
                                    {
                                      v1290 = v1233;
                                      v1282 = (SIZE_T)v1069;
                                      while ( 1 )
                                      {
                                        v1221 = RtlULongLongAdd(v1235, 4, &v1297);
                                        if ( v1221 < 0 )
                                          break;
                                        if ( v1297 > (unsigned __int64)v1291 )
                                        {
                                          v1221 = -1073741811;
LABEL_1514:
                                          v1069 = (void *)v1282;
                                          v1124 = v1290;
                                          goto LABEL_1495;
                                        }
                                        v1237 = *v1236;
                                        dwBytes_4 = 0;
                                        v1221 = RtlUIntAdd(4, v1237, &dwBytes_4);
                                        if ( v1221 < 0 )
                                          goto LABEL_1514;
                                        v1302 = (size_t)v932;
                                        psz = (STRSAFE_PCNZWCH)v1220;
                                        v1239 = RtlULongLongAdd(v1238, dwBytes_4, &v1312);
                                        LODWORD(v1001) = 0;
                                        v1296 = v1220;
                                        v1124 = v1233;
                                        v1286 = v1239;
                                        v932 = (void *)v1302;
                                        v1221 = v1239;
                                        if ( v1239 < 0 )
                                          goto LABEL_1526;
                                        v1235 = (LPVOID)v1312;
                                        v1234 = v1291;
                                        if ( v1312 > (unsigned __int64)v1291 )
                                        {
                                          v1286 = -1073741811;
                                          v1296 = (LPVOID)psz;
                                          v1221 = -1073741811;
                                          goto LABEL_1495;
                                        }
                                        LODWORD(v1287) = (_DWORD)v1287 + 1;
                                        v1220 = (void *)psz;
                                        v1290 = v1233;
                                        v1296 = (LPVOID)psz;
                                        v1282 = (SIZE_T)v1069;
                                        if ( v1312 >= (unsigned __int64)v1291 )
                                        {
                                          v1296 = (LPVOID)psz;
                                          goto LABEL_1510;
                                        }
                                      }
                                      v1069 = (void *)v1282;
                                      LODWORD(v1001) = 0;
                                      v1124 = v1290;
                                      goto LABEL_1526;
                                    }
LABEL_1510:
                                    v1124 = v1233;
                                    if ( v1235 != v1234 )
                                    {
                                      v1221 = -1073741811;
                                      goto LABEL_1495;
                                    }
                                    LODWORD(v1229) = v1280;
                                  }
                                  else
                                  {
                                    v1296 = v1220;
                                    v1124 = v1225;
                                    v1286 = 0;
                                  }
                                  v1297 = 0;
                                  v1240 = 0;
                                  if ( (_DWORD)v1229 )
                                  {
                                    v1241 = GetProcessHeap();
                                    v1242 = HeapAlloc(v1241, 8u, (unsigned int)v1280);
                                    LODWORD(v1001) = 0;
                                    v1297 = (SIZE_T)v1242;
                                    v1240 = v1242;
                                    if ( !v1242 )
                                    {
                                      v1221 = -1073741801;
                                      goto LABEL_1531;
                                    }
                                    v1231 = (void *)v1278;
                                    v1286 = 0;
                                    LODWORD(v1229) = v1280;
                                  }
                                  if ( v1231 )
                                    memcpy_0(v1240, v1231, (unsigned int)v1229);
                                  LODWORD(v1001) = 0;
                                  v1221 = v1286;
                                  v1292 = v1297;
                                  v1243 = (int)v1287;
                                  LODWORD(v1304) = (_DWORD)v1287;
LABEL_1527:
                                  if ( v1221 >= 0 && (_DWORD)v1285 != v1243 )
                                    v1221 = -1073741762;
                                  goto LABEL_1531;
                                }
                              }
                            }
                          }
                        }
                      }
                      v1282 = (SIZE_T)v1069;
                      v1107 = GetProcessHeap();
                      HeapFree(v1107, 0, (LPVOID)psz);
                      LODWORD(v1001) = 0;
                    }
                    v1106 = v1286;
                    goto LABEL_1346;
                  }
LABEL_1316:
                  v1012 = (const void **)v1278;
                  v1278 = 0;
                  goto LABEL_1317;
                }
                pcchLength = v1311[1];
                if ( v982 )
                {
                  while ( 1 )
                  {
                    v985 = *v981;
                    dwBytes_4 = 0;
                    if ( (int)RtlUIntAdd(4, v985, &dwBytes_4) < 0
                      || (int)RtlULongLongAdd(v986, dwBytes_4, &pcchLength) < 0 )
                    {
                      break;
                    }
                    v981 = (unsigned int *)pcchLength;
                    if ( v988 + 1 >= v987 )
                      goto LABEL_1256;
                  }
                }
                else
                {
LABEL_1256:
                  v989 = RtlULongLongAdd(v981, 4, &v1303);
                  v984 = 0;
                  if ( v989 >= 0 && (unsigned __int64)(v990 + 3) <= v1311[1] + HIDWORD(v1311[0]) )
                  {
                    v991 = v1303;
                    v992 = v1307;
                    *v990 = 8;
                    v983 = 4;
                    *v991 = v992;
                    ++LODWORD(v1311[0]);
                    goto LABEL_1259;
                  }
                }
                v929 = 0;
                goto LABEL_1215;
              }
              psz = (STRSAFE_PCNZWCH)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140F8[0])(0, 0, 1027);
              if ( !psz )
              {
                GetLastError();
                goto LABEL_1191;
              }
              v471 = off_180114098[0]();
              v472 = dword_180116EE8;
              qword_1801173D8 = v471;
              v1301 = dword_180116EE8;
              memset_0(&v1346, 0, 0x70u);
              memset(v1402, 0, 44);
              v1318 = 0;
              while ( _InterlockedCompareExchange(&dword_1801173E4, 1, 0) )
                ;
              v473 = dword_1801173E0;
              if ( dword_1801173E0 )
                goto LABEL_633;
              v474 = MemoryAlloc(0x338u);
              v1302 = (size_t)v474;
              if ( !v474 )
                goto LABEL_599;
              v475 = v474;
              v476 = qword_1800F4460;
              v477 = -1;
              v478 = 103;
              v479 = 0;
              v480 = 0;
              v481 = 0;
              do
              {
                v482 = *((unsigned __int8 *)v476 + 1);
                v483 = *(unsigned __int8 *)v476;
                v484 = *((unsigned __int8 *)v476++ + 4);
                v485 = *((unsigned __int8 *)v476 - 5)
                     | ((*((unsigned __int8 *)v476 - 6) | ((v482 | (v483 << 8)) << 8)) << 8);
                v486 = v481 ^ v485;
                v487 = *((unsigned __int8 *)v476 - 1)
                     | ((*((unsigned __int8 *)v476 - 2) | ((*((unsigned __int8 *)v476 - 3) | (v484 << 8)) << 8)) << 8);
                v488 = v480 ^ v487 ^ v481 ^ v485 ^ 0xAC987321;
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
                v501 = v498 ^ (v499 - 2033) ^ 0xAB69605E ^ (__ROR4__(v500, 25) + 43881 * __ROR4__(v500 - 133239679, 6));
                v502 = v500 ^ (24670 * (v501 ^ 0x137F) + __ROR4__(v501, 9));
                v503 = v501 ^ (__ROR4__(v502, 25) + 2033 * __ROR4__(v502 ^ 0xAB69, 27));
                v504 = v502 ^ v503 ^ 0xAC987321;
                v505 = v503 ^ (4991 * __ROR4__(v504, 3) - 219010071);
                v506 = v504 ^ (24670 * __ROR4__(v505 - 133239679, 1) - __ROR4__(v505, 6));
                v507 = v505 ^ (__ROR4__(v506, 18) + 2033 * __ROR4__(v506 - 1419157410, 29));
                v508 = v506 ^ (4991 * __ROR4__(v507 - 1419157410, 17) - __ROR4__(v507, 14));
                v509 = v507 ^ (v508 >> 3) ^ (43881 * (v508 ^ 0x605E));
                v510 = v479 ^ __ROR4__(v509, 30) ^ (24670 * __ROR4__(v509 ^ 0x7F1137F, 28));
                v479 = v485;
                v481 = v508 ^ v510;
                v475[3] = v481;
                v480 = v509 ^ v477;
                v475[7] = v509 ^ v477;
                v477 = v487;
                v475[2] = __ROR4__(v481, 8);
                v475[6] = __ROR4__(v480, 8);
                v475[1] = __ROR4__(v481, 16);
                v475[5] = __ROR4__(v480, 16);
                *v475 = __ROR4__(v481, 24);
                v475[4] = __ROR4__(v480, 24);
                v475 += 8;
                --v478;
              }
              while ( v478 );
              v472 = v1301;
              v123 = (_BYTE *)v1302;
              v511 = 0;
              v512 = 0;
              do
              {
                v512 ^= *(_BYTE *)(v511 + v1302);
                ++v511;
              }
              while ( v511 < 0x338 );
              if ( v512 != 64 )
              {
                MemoryFree((void *)v1302);
                LODWORD(v123) = 0;
                goto LABEL_599;
              }
              LODWORD(v1296) = 0;
              LODWORD(v1287) = 0;
              v515 = 0;
              *(_BYTE *)(v1302 + 823) = 0;
              memset_0(qword_180116EF0, 0, 0x60u);
              if ( *v123 )
              {
                pcchLength = (size_t)v123;
                while ( 1 )
                {
                  v516 = -1;
                  do
                    ++v516;
                  while ( *(_WORD *)&v123[2 * v516] );
                  v517 = 3LL * v515;
                  v518 = (HMODULE *)&qword_180116EF0[3 * v515];
                  v1278 = v517;
                  if ( !GetModuleHandleExW(0, (LPCWSTR)v123, v518) )
                    break;
                  v519 = &v123[2 * v516];
                  if ( *(_WORD *)*v518 == 23117
                    && (v522 = *((int *)*v518 + 15), (unsigned int)v522 < 0x10000000)
                    && (v523 = (char *)*v518 + v522, v523 >= (char *)*v518)
                    && *(_DWORD *)v523 == 17744 )
                  {
                    v520 = v1278;
                    if ( ((*((_WORD *)v523 + 12) - 267) & 0xFEFF) != 0 )
                    {
                      v521 = -1073741811;
                    }
                    else
                    {
                      v521 = 0;
                      *(__int64 *)((char *)&qword_180116EF0[v1278 + 1] + 4) = *((_QWORD *)v523 + 17);
                      LODWORD(qword_180116EF0[v520 + 1]) = *((_DWORD *)v523 + 20);
                    }
                  }
                  else
                  {
                    v520 = v1278;
                    v521 = -1073741701;
                  }
                  v524 = *(_DWORD *)(v519 + 2);
                  v525 = 0;
                  v123 = v519 + 6;
                  dwBytes_4 = v524;
                  for ( LODWORD(v1280) = 0; v525 < v524; LODWORD(v1280) = v525 )
                  {
                    v526 = -1;
                    do
                      ++v526;
                    while ( v123[v526] );
                    if ( v521 >= 0 )
                    {
                      v527 = GetProcAddress((HMODULE)qword_180116EF0[v520], v123);
                      if ( !v527 )
                        goto LABEL_627;
                      off_180114000[(unsigned int)v1296] = v527;
                      v525 = v1280;
                      v524 = dwBytes_4;
                    }
                    LODWORD(v1296) = (_DWORD)v1296 + 1;
                    ++v525;
                    v520 = v1278;
                    v123 += v526 + 1;
                  }
                  v515 = (_DWORD)v1287 + 1;
                  LODWORD(v1287) = (_DWORD)v1287 + 1;
                  if ( !*v123 )
                    goto LABEL_627;
                }
                v521 = -1073741702;
LABEL_627:
                v528 = (void *)pcchLength;
                LODWORD(v123) = 0;
                if ( !pcchLength )
                  goto LABEL_631;
              }
              else
              {
                v528 = v123;
                v521 = 0;
                LODWORD(v123) = 0;
              }
              v529 = GetProcessHeap();
              HeapFree(v529, 0, v528);
LABEL_631:
              if ( v521 < 0 )
              {
LABEL_599:
                for ( n = 0; n != 4; ++n )
                {
                  v514 = (HMODULE)qword_180116EF0[3 * n];
                  if ( v514 )
                    FreeLibrary(v514);
                }
                memset_0(qword_180116EF0, 0, 0x60u);
                memcpy_0(off_180114000, off_1800E1E60, 0x170u);
LABEL_634:
                _InterlockedExchange(&dword_1801173E4, 0);
                v1291 = 0;
                v1309 = 0;
                while ( _InterlockedCompareExchange(&dword_1801173E4, 1, 0) )
                  ;
                v530 = dword_1801173E0;
                if ( dword_1801173E0 )
                  goto LABEL_679;
                v531 = MemoryAlloc(0x338u);
                v1302 = (size_t)v531;
                if ( !v531 )
                {
LABEL_644:
                  LODWORD(v123) = 0;
                  goto LABEL_645;
                }
                v532 = v531;
                v533 = qword_1800F4460;
                v534 = -1;
                v535 = 103;
                v536 = 0;
                v537 = 0;
                v538 = 0;
                do
                {
                  v539 = *((unsigned __int8 *)v533 + 1);
                  v540 = *(unsigned __int8 *)v533;
                  v541 = *((unsigned __int8 *)v533++ + 4);
                  v542 = *((unsigned __int8 *)v533 - 5)
                       | ((*((unsigned __int8 *)v533 - 6) | ((v539 | (v540 << 8)) << 8)) << 8);
                  v543 = v538 ^ v542;
                  v544 = *((unsigned __int8 *)v533 - 1)
                       | ((*((unsigned __int8 *)v533 - 2) | ((*((unsigned __int8 *)v533 - 3) | (v541 << 8)) << 8)) << 8);
                  v545 = v538 ^ v542 ^ v537 ^ v544 ^ 0xAC987321;
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
                  v567 = v536 ^ __ROR4__(v566, 30) ^ (24670 * __ROR4__(v566 ^ 0x7F1137F, 28));
                  v536 = v542;
                  v538 = v565 ^ v567;
                  v532[3] = v538;
                  v537 = v566 ^ v534;
                  v532[7] = v566 ^ v534;
                  v534 = v544;
                  v532[2] = __ROR4__(v538, 8);
                  v532[6] = __ROR4__(v537, 8);
                  v532[1] = __ROR4__(v538, 16);
                  v532[5] = __ROR4__(v537, 16);
                  *v532 = __ROR4__(v538, 24);
                  v532[4] = __ROR4__(v537, 24);
                  v532 += 8;
                  --v535;
                }
                while ( v535 );
                v472 = v1301;
                v123 = (_BYTE *)v1302;
                v568 = 0;
                v569 = 0;
                do
                {
                  v569 ^= *(_BYTE *)(v568 + v1302);
                  ++v568;
                }
                while ( v568 < 0x338 );
                if ( v569 != 64 )
                {
                  MemoryFree((void *)v1302);
                  goto LABEL_644;
                }
                LODWORD(v1296) = 0;
                LODWORD(v1287) = 0;
                v572 = 0;
                *(_BYTE *)(v1302 + 823) = 0;
                memset_0(qword_180116EF0, 0, 0x60u);
                if ( *v123 )
                {
                  pcchLength = (size_t)v123;
                  while ( 1 )
                  {
                    v573 = -1;
                    do
                      ++v573;
                    while ( *(_WORD *)&v123[2 * v573] );
                    v574 = 3LL * v572;
                    v575 = (HMODULE *)&qword_180116EF0[3 * v572];
                    v1278 = v574;
                    if ( !GetModuleHandleExW(0, (LPCWSTR)v123, v575) )
                      break;
                    v576 = &v123[2 * v573];
                    if ( *(_WORD *)*v575 == 23117
                      && (v579 = *((int *)*v575 + 15), (unsigned int)v579 < 0x10000000)
                      && (v580 = (char *)*v575 + v579, v580 >= (char *)*v575)
                      && *(_DWORD *)v580 == 17744 )
                    {
                      v577 = v1278;
                      if ( ((*((_WORD *)v580 + 12) - 267) & 0xFEFF) != 0 )
                      {
                        v578 = -1073741811;
                      }
                      else
                      {
                        v578 = 0;
                        *(__int64 *)((char *)&qword_180116EF0[v1278 + 1] + 4) = *((_QWORD *)v580 + 17);
                        LODWORD(qword_180116EF0[v577 + 1]) = *((_DWORD *)v580 + 20);
                      }
                    }
                    else
                    {
                      v577 = v1278;
                      v578 = -1073741701;
                    }
                    v581 = *(_DWORD *)(v576 + 2);
                    v582 = 0;
                    v123 = v576 + 6;
                    dwBytes_4 = v581;
                    for ( LODWORD(v1280) = 0; v582 < v581; LODWORD(v1280) = v582 )
                    {
                      v583 = -1;
                      do
                        ++v583;
                      while ( v123[v583] );
                      if ( v578 >= 0 )
                      {
                        v584 = GetProcAddress((HMODULE)qword_180116EF0[v577], v123);
                        if ( !v584 )
                          goto LABEL_673;
                        off_180114000[(unsigned int)v1296] = v584;
                        v582 = v1280;
                        v581 = dwBytes_4;
                      }
                      LODWORD(v1296) = (_DWORD)v1296 + 1;
                      ++v582;
                      v577 = v1278;
                      v123 += v583 + 1;
                    }
                    v572 = (_DWORD)v1287 + 1;
                    LODWORD(v1287) = (_DWORD)v1287 + 1;
                    if ( !*v123 )
                      goto LABEL_673;
                  }
                  v578 = -1073741702;
LABEL_673:
                  v585 = (void *)pcchLength;
                  LODWORD(v123) = 0;
                  if ( !pcchLength )
                    goto LABEL_677;
                }
                else
                {
                  v585 = v123;
                  v578 = 0;
                  LODWORD(v123) = 0;
                }
                v586 = GetProcessHeap();
                HeapFree(v586, 0, v585);
LABEL_677:
                if ( v578 < 0 )
                {
LABEL_645:
                  for ( ii = 0; ii != 4; ++ii )
                  {
                    v571 = (HMODULE)qword_180116EF0[3 * ii];
                    if ( v571 )
                      FreeLibrary(v571);
                  }
                  memset_0(qword_180116EF0, 0, 0x60u);
                  memcpy_0(off_180114000, off_1800E1E60, 0x170u);
LABEL_680:
                  _InterlockedExchange(&dword_1801173E4, 0);
                  memset_0(&v1346, 0, 0x70u);
                  LOWORD(v1285) = (v472 >> 4) & 0xF;
                  WORD1(v1285) = (v472 >> 8) & 0xF;
                  WORD2(v1285) = (v472 >> 12) & 0xF;
                  v1318 = 0;
                  v1278 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140F8[0])(0, 0, 1027);
                  v1283 = 0xFFFFFF;
                  if ( !v1278 )
                  {
                    v587 = GetLastError();
                    v588 = v587;
                    if ( v587 > 0 )
                      v588 = (unsigned __int16)v587 | 0x80070000;
                    if ( v588 >= 0 )
                      v588 = -2147467259;
LABEL_884:
                    while ( _InterlockedCompareExchange(&dword_1801173E4, 1, 0) )
                      ;
                    v704 = dword_1801173E0;
                    if ( dword_1801173E0 > 0 )
                    {
                      --dword_1801173E0;
                      if ( v704 == 1 )
                      {
                        for ( jj = 0; jj != 4; ++jj )
                        {
                          v706 = (HMODULE)qword_180116EF0[3 * jj];
                          if ( v706 )
                            FreeLibrary(v706);
                        }
                        memset_0(qword_180116EF0, 0, 0x60u);
                        memcpy_0(off_180114000, off_1800E1E60, 0x170u);
                      }
                    }
                    _InterlockedExchange(&dword_1801173E4, 0);
                    SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1309);
                    if ( v588 < 0 )
                    {
LABEL_1016:
                      v789 = v1348;
                      if ( v1348 )
                      {
                        v790 = -1;
                        do
                          ++v790;
                        while ( *((_WORD *)v1348 + v790) );
                        for ( kk = 2 * v790 + 2; kk; --kk )
                          *v789++ = 0;
                        MemoryFree(v1348);
                        v1348 = 0;
                      }
                      v792 = v1349;
                      if ( v1349 )
                      {
                        v793 = -1;
                        do
                          ++v793;
                        while ( *((_WORD *)v1349 + v793) );
                        for ( mm = 2 * v793 + 2; mm; --mm )
                          *v792++ = 0;
                        MemoryFree(v1349);
                        v1349 = 0;
                      }
                      v795 = v1350;
                      if ( v1350 )
                      {
                        v796 = -1;
                        do
                          ++v796;
                        while ( *((_WORD *)v1350 + v796) );
                        v797 = 2 * v796 + 2;
                        if ( v797 )
                        {
                          do
                          {
                            *v795++ = 0;
                            --v797;
                          }
                          while ( v797 );
                          v795 = v1350;
                        }
                        MemoryFree(v795);
                        v1350 = 0;
                      }
                      if ( v1351 )
                      {
                        off_180114038[0]();
                        v1351 = 0;
                      }
                      if ( v1352 )
                      {
                        off_180114038[0]();
                        v1352 = 0;
                      }
                      if ( v1353 )
                      {
                        off_180114038[0]();
                        v1353 = 0;
                      }
                      while ( _InterlockedCompareExchange(&dword_1801173E4, 1, 0) )
                        ;
                      v798 = dword_1801173E0;
                      if ( dword_1801173E0 > 0 )
                      {
                        --dword_1801173E0;
                        if ( v798 == 1 )
                        {
                          for ( nn = 0; nn != 4; ++nn )
                          {
                            v800 = (HMODULE)qword_180116EF0[3 * nn];
                            if ( v800 )
                              FreeLibrary(v800);
                          }
                          memset_0(qword_180116EF0, 0, 0x60u);
                          memcpy_0(off_180114000, off_1800E1E60, 0x170u);
                        }
                      }
                      _InterlockedExchange(&dword_1801173E4, 0);
                      v801 = dword_180116EE8;
                      v802 = qword_1801173D8;
                      LODWORD(v1287) = dword_180116EE8;
                      v803 = (void *)((unsigned int)off_180114098[0]() - v802);
                      Src = v803;
                      v1436 = 0;
                      v1432 = 0;
                      v1433 = 0;
                      v1434 = 0;
                      v1435 = 0;
                      while ( _InterlockedCompareExchange(&dword_1801173E4, 1, 0) )
                        ;
                      v868 = dword_1801173E0;
                      if ( dword_1801173E0 )
                        goto LABEL_1180;
                      v869 = MemoryAlloc(0x338u);
                      v870 = 0;
                      v1302 = (size_t)v869;
                      if ( !v869 )
                        goto LABEL_1145;
                      v871 = v869;
                      v872 = qword_1800F4460;
                      v873 = 103;
                      v874 = 0;
                      v875 = -1;
                      v876 = 0;
                      do
                      {
                        v877 = *((unsigned __int8 *)v872 + 1);
                        v878 = *(unsigned __int8 *)v872;
                        v879 = *((unsigned __int8 *)v872++ + 4);
                        v880 = *((unsigned __int8 *)v872 - 5)
                             | ((*((unsigned __int8 *)v872 - 6) | ((v877 | (v878 << 8)) << 8)) << 8);
                        v881 = v870 ^ v880;
                        v882 = *((unsigned __int8 *)v872 - 1)
                             | ((*((unsigned __int8 *)v872 - 2) | ((*((unsigned __int8 *)v872 - 3) | (v879 << 8)) << 8)) << 8);
                        v883 = v876 ^ v882 ^ v870 ^ v880 ^ 0xAC987321;
                        v884 = v881 ^ (__ROR4__(v883, 22) + 4991 * __ROR4__(v883 + 1419157410, 27));
                        v885 = v883 ^ (43881 * __ROR4__(v884 + 133239679, 9) - __ROR4__(v884, 30));
                        v886 = v884 ^ (24670 * v885 - (v885 >> 13) - 123127970);
                        v887 = v885 ^ (2033 * __ROR4__(v886 ^ 0xAB69, 26) - __ROR4__(v886, 30));
                        v888 = v886 ^ (133239679 - (v887 ^ 0xAB69605E));
                        v889 = v887 ^ (43881 * (v888 ^ 0x137F)) ^ __ROR4__(v888, 6);
                        v890 = v888 ^ (__ROR4__(v889, 30) + 24670 * __ROR4__(v889 + 133239679, 15));
                        v891 = v889 ^ (2033 * __ROR4__(v890 + 1419157410, 14) - __ROR4__(v890, 24));
                        v892 = v890 ^ __ROR4__(v891, 10) ^ (4991 * __ROR4__(v891 ^ 0xAB69605E, 12));
                        v893 = v891 ^ (v892 >> 10) ^ (43881 * (v892 ^ 0x7F1));
                        v894 = v892 ^ (2033 * (__ROR4__(~v893, 5) + 24670));
                        v895 = v894
                             ^ (((v893 ^ (v894 - 2033) ^ 0xAB69605E) >> 2)
                              + 4991 * __ROR4__(v893 ^ (v894 - 2033) ^ 0xAB6967AF, 30));
                        v896 = v893
                             ^ (v894 - 2033)
                             ^ 0xAB69605E
                             ^ (__ROR4__(v895, 25) + 43881 * __ROR4__(v895 - 133239679, 6));
                        v897 = v895 ^ (24670 * (v896 ^ 0x137F) + __ROR4__(v896, 9));
                        v898 = v896 ^ (__ROR4__(v897, 25) + 2033 * __ROR4__(v897 ^ 0xAB69, 27));
                        v899 = v897 ^ v898 ^ 0xAC987321;
                        v900 = v898 ^ (4991 * __ROR4__(v899, 3) - 219010071);
                        v901 = v899 ^ (24670 * __ROR4__(v900 - 133239679, 1) - __ROR4__(v900, 6));
                        v902 = v900 ^ (__ROR4__(v901, 18) + 2033 * __ROR4__(v901 - 1419157410, 29));
                        v903 = v901 ^ (4991 * __ROR4__(v902 - 1419157410, 17) - __ROR4__(v902, 14));
                        v904 = v902 ^ (v903 >> 3) ^ (43881 * (v903 ^ 0x605E));
                        v905 = __ROR4__(v904, 30);
                        v876 = v875 ^ v904;
                        v875 = v882;
                        v870 = v874
                             ^ v903
                             ^ v905
                             ^ (24670 * __ROR4__(v902 ^ (v903 >> 3) ^ (43881 * (v903 ^ 0x605E)) ^ 0x7F1137F, 28));
                        v874 = v880;
                        v871[3] = v870;
                        v871[7] = v876;
                        v871[2] = __ROR4__(v870, 8);
                        v871[6] = __ROR4__(v876, 8);
                        v871[1] = __ROR4__(v870, 16);
                        v871[5] = __ROR4__(v876, 16);
                        *v871 = __ROR4__(v870, 24);
                        v871[4] = __ROR4__(v876, 24);
                        v871 += 8;
                        --v873;
                      }
                      while ( v873 );
                      v906 = (WCHAR *)v1302;
                      v907 = 0;
                      v908 = 0;
                      do
                        v908 ^= *(_BYTE *)(v1302 + v907++);
                      while ( v907 < 0x338 );
                      if ( v908 != 64 )
                      {
                        MemoryFree((void *)v1302);
LABEL_1144:
                        v801 = (int)v1287;
                        LODWORD(v803) = (_DWORD)Src;
LABEL_1145:
                        for ( i1 = 0; i1 != 4; ++i1 )
                        {
                          v910 = (HMODULE)qword_180116EF0[3 * i1];
                          if ( v910 )
                            FreeLibrary(v910);
                        }
                        memset_0(qword_180116EF0, 0, 0x60u);
                        memcpy_0(off_180114000, off_1800E1E60, 0x170u);
                        goto LABEL_1181;
                      }
                      LODWORD(v1280) = 0;
                      LODWORD(v1290) = 0;
                      *(_BYTE *)(v1302 + 823) = 0;
                      v911 = 0;
                      memset_0(qword_180116EF0, 0, 0x60u);
                      if ( *(_BYTE *)v906 )
                      {
                        pcchLength = (size_t)v906;
                        while ( 1 )
                        {
                          v912 = -1;
                          do
                            ++v912;
                          while ( v906[v912] );
                          v913 = 3LL * v911;
                          v914 = (HMODULE *)&qword_180116EF0[v913];
                          if ( !GetModuleHandleExW(0, v906, v914) )
                            break;
                          v915 = &v906[v912];
                          if ( *(_WORD *)*v914 == 23117
                            && (v917 = *((int *)*v914 + 15), (unsigned int)v917 < 0x10000000)
                            && (v918 = (char *)*v914 + v917, v918 >= (char *)*v914)
                            && *(_DWORD *)v918 == 17744 )
                          {
                            if ( ((*((_WORD *)v918 + 12) - 267) & 0xFEFF) != 0 )
                            {
                              v916 = -1073741811;
                            }
                            else
                            {
                              *(__int64 *)((char *)&qword_180116EF0[v913 + 1] + 4) = *((_QWORD *)v918 + 17);
                              v916 = 0;
                              LODWORD(qword_180116EF0[v913 + 1]) = *((_DWORD *)v918 + 20);
                            }
                          }
                          else
                          {
                            v916 = -1073741701;
                          }
                          v919 = *(_DWORD *)(v915 + 1);
                          v920 = 0;
                          v906 = v915 + 3;
                          dwBytes_4 = v919;
                          LODWORD(v1282) = 0;
                          if ( v919 )
                          {
                            v921 = v1280;
                            v922 = dwBytes_4;
                            do
                            {
                              v923 = -1;
                              do
                                ++v923;
                              while ( *((_BYTE *)v906 + v923) );
                              if ( v916 >= 0 )
                              {
                                v924 = GetProcAddress(*v914, (LPCSTR)v906);
                                if ( !v924 )
                                  goto LABEL_1174;
                                v921 = v1280;
                                v922 = dwBytes_4;
                                off_180114000[(unsigned int)v1280] = v924;
                                v920 = v1282;
                              }
                              ++v921;
                              ++v920;
                              LODWORD(v1280) = v921;
                              v906 = (WCHAR *)((char *)v906 + v923 + 1);
                              LODWORD(v1282) = v920;
                            }
                            while ( v920 < v922 );
                          }
                          v911 = (_DWORD)v1290 + 1;
                          LODWORD(v1290) = (_DWORD)v1290 + 1;
                          if ( !*(_BYTE *)v906 )
                            goto LABEL_1174;
                        }
                        v916 = -1073741702;
LABEL_1174:
                        v906 = (WCHAR *)pcchLength;
                        if ( !pcchLength )
                          goto LABEL_1178;
                      }
                      else
                      {
                        v916 = 0;
                      }
                      v925 = GetProcessHeap();
                      HeapFree(v925, 0, v906);
LABEL_1178:
                      if ( v916 < 0 )
                        goto LABEL_1144;
                      v868 = dword_1801173E0;
                      LODWORD(v803) = (_DWORD)Src;
                      v801 = (int)v1287;
LABEL_1180:
                      dword_1801173E0 = v868 + 1;
LABEL_1181:
                      _InterlockedExchange(&dword_1801173E4, 0);
                      LODWORD(v1433) = (_DWORD)v803;
                      v1432 = 1;
                      LODWORD(v1434) = -1721306479;
                      DWORD2(v1433) = 1;
                      LODWORD(v1435) = 1;
                      DWORD2(v1434) = 1;
                      LODWORD(v1436) = v801;
                      DWORD2(v1435) = 1;
                      ((void (__fastcall *)(_QWORD, __int64, __int64, int *))qword_1801140D0)(0, 8225, 4, &v1432);
                      while ( _InterlockedCompareExchange(&dword_1801173E4, 1, 0) )
                        ;
                      v926 = dword_1801173E0;
                      v123 = 0;
                      if ( dword_1801173E0 > 0 )
                      {
                        --dword_1801173E0;
                        if ( v926 == 1 )
                        {
                          for ( i2 = 0; i2 != 4; ++i2 )
                          {
                            v928 = (HMODULE)qword_180116EF0[3 * i2];
                            if ( v928 )
                              FreeLibrary(v928);
                          }
                          memset_0(qword_180116EF0, 0, 0x60u);
                          memcpy_0(off_180114000, off_1800E1E60, 0x170u);
                        }
                      }
                      _InterlockedExchange(&dword_1801173E4, 0);
                      ((void (__fastcall *)(_QWORD, STRSAFE_PCNZWCH))off_180114160[0])(0, psz);
                      goto LABEL_1191;
                    }
                    v707 = v1318;
                    Src = 0;
                    v1297 = v1318;
                    v1367 = 0;
                    memset_0(v1368, 0, 0x64u);
                    v708 = ((__int64 (__fastcall *)(STRSAFE_PCNZWCH, __int64))off_180114050[0])(psz, 7);
                    if ( v708
                      && ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180114068[0])(v708, 104, &v1367) )
                    {
                      if ( v1369 == 32 && v1370 && v1368[0] > 0 )
                        LODWORD(v123) = v1368[1] > 0;
                      v709 = v472 & 0xF;
                      v710 = v709;
                      if ( (_DWORD)v123 )
                      {
LABEL_903:
                        ((void (__fastcall *)(int *, _QWORD, _QWORD))off_180114150)(&v1355, v707, HIDWORD(v1297));
                        ((void (__fastcall *)(int *, _QWORD, _QWORD))off_180114150)(&v1359, v707, HIDWORD(v1297));
                        if ( v709 == 1 )
                          Src = (void *)((__int64 (__fastcall *)(_QWORD))off_180114028[0])(v1347 == 0 ? 0xB26720 : 0);
LABEL_905:
                        v711 = psz;
                        LODWORD(v1285) = ((__int64 (__fastcall *)(STRSAFE_PCNZWCH, __int64))off_180114080[0])(psz, 1);
                        v712 = 2064;
                        if ( v1346 )
                          v712 = 133138;
                        LODWORD(v1305) = v712;
                        if ( (_DWORD)v123 )
                        {
                          v713 = 0;
                          v1371 = 0;
                          memset_0(v1372, 0, 0x64u);
                          v1383 = 0;
                          memset_0(v1384, 0, 0x64u);
                          v1309 = v1348;
                          memset(v1407, 0, 28);
                          v1406 = 0;
                          v1395 = 0;
                          if ( !v1348 )
                            goto LABEL_1014;
                          dwBytes_4 = v1347;
                          v1302 = v1351;
                          v714 = ((__int64 (__fastcall *)(STRSAFE_PCNZWCH, __int64))off_180114050[0])(v711, 7);
                          if ( v714 )
                          {
                            if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180114068[0])(
                                   v714,
                                   104,
                                   &v1371) )
                            {
                              LODWORD(v1280) = v1372[0];
                              Size = v1373;
                              v713 = 0;
                              LODWORD(v1287) = v1372[1];
                            }
                            else
                            {
                              Size = 0;
                              LODWORD(v1287) = 0;
                              LODWORD(v1280) = 0;
                            }
                            v715 = ((__int64 (__fastcall *)(STRSAFE_PCNZWCH))off_180114010[0])(v711);
                            pcchLength = v715;
                            v716 = v715;
                            if ( v715 )
                            {
                              DWORD1(v1406) = v1357 - v1355;
                              DWORD2(v1406) = v1356 - v1358;
                              v1340 = 0;
                              memset(v1407, 0, 28);
                              LODWORD(v1406) = 40;
                              HIDWORD(v1406) = 2097153;
                              v717 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180114018[0])(
                                       v715,
                                       &v1406,
                                       0,
                                       &v1340,
                                       0,
                                       0);
                              v1312 = v717;
                              if ( v717 )
                              {
                                if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180114068[0])(
                                       v717,
                                       104,
                                       &v1383) )
                                {
                                  v1297 = v1385;
                                }
                                else
                                {
                                  v1297 = 0;
                                }
                                DWORD2(v1395) = v1357 - v1355;
                                HIDWORD(v1395) = v1358 - v1356;
                                ((void (__fastcall *)(size_t, unsigned __int64))off_180114078[0])(v716, v1312);
                                ((void (__fastcall *)(size_t, __int64))off_180114080[0])(v716, 1);
                                v720 = (void *)((__int64 (__fastcall *)(size_t, size_t))off_180114078[0])(v716, v1302);
                                v721 = off_1801140E8[0];
                                v1291 = v720;
                                v722 = ((__int64 (__fastcall *)(_QWORD))off_180114070[0])(0);
                                ((void (__fastcall *)(size_t, __int128 *, __int64))v721)(pcchLength, &v1395, v722);
                                v716 = pcchLength;
                                ((void (__fastcall *)(size_t, void *, __int64, __int128 *, _DWORD, _QWORD))off_1801140D8[0])(
                                  pcchLength,
                                  v1309,
                                  0xFFFFFFFFLL,
                                  &v1395,
                                  v1305,
                                  0);
                                if ( v709 == 1 )
                                {
                                  if ( dwBytes_4 )
                                    v723 = ((__int64 (__fastcall *)(__int64))off_180114118[0])(8);
                                  else
                                    v723 = 0xFFFFFF;
                                }
                                else
                                {
                                  v723 = -5723992;
                                }
                                v724 = 0;
                                v725 = -v1355;
                                LODWORD(v1296) = v723;
                                v726 = 0;
                                if ( v1355 >= 0 )
                                {
                                  v724 = v1355;
                                  v725 = 0;
                                }
                                v727 = -v1356;
                                if ( v1356 >= 0 )
                                {
                                  v726 = v1356;
                                  v727 = 0;
                                }
                                v728 = DWORD2(v1395) - v725;
                                if ( DWORD2(v1395) - v725 >= (int)v1280 - v724 )
                                  v728 = v1280 - v724;
                                dwBytes_4 = v728;
                                v729 = HIDWORD(v1395) - v727;
                                if ( HIDWORD(v1395) - v727 >= (int)v1287 - v726 )
                                  v729 = (_DWORD)v1287 - v726;
                                LODWORD(v1292) = v729;
                                if ( v728 > 0 && v729 > 0 )
                                {
                                  v730 = (unsigned __int8)v1296;
                                  v731 = dwBytes_4;
                                  LODWORD(v1287) = 0;
                                  v732 = (char *)(v1297 + 4 * (v725 + (__int64)(DWORD2(v1395) * v727)));
                                  v1309 = v732;
                                  v733 = Size + 4 * (v724 + (__int64)((int)v1280 * v726));
                                  LODWORD(v1282) = (unsigned int)v1296 >> 8;
                                  LODWORD(v1290) = (unsigned int)v1296 >> 16;
                                  v1302 = 4LL * SDWORD2(v1395);
                                  v1278 = 4LL * (int)v1280;
                                  Size = v733;
                                  do
                                  {
                                    v734 = v1282;
                                    v735 = 0;
                                    v736 = (char)v1290;
                                    v737 = (unsigned __int8 *)v732;
                                    v1297 = (SIZE_T)v732;
                                    v738 = (_BYTE *)v733;
                                    LODWORD(v1280) = 0;
                                    do
                                    {
                                      v739 = ~(unsigned __int8)((*v737 + v737[2] + 2 * (unsigned int)v737[1]) >> 2);
                                      if ( (unsigned __int8)((*v737 + v737[2] + 2 * (unsigned int)v737[1]) >> 2) != 0xFF )
                                      {
                                        v740 = (unsigned __int8)v738[2];
                                        v741 = v739;
                                        v742 = (int)((unsigned __int64)(2155905153LL * v739 * (v730 - v740)) >> 32) >> 7;
                                        v738[2] = v740 + (v742 < 0) + v742;
                                        v738[1] -= v741 * (v734 - v738[1]);
                                        *v738 -= v741 * (v736 - *v738);
                                        v743 = (unsigned __int8)v738[3];
                                        v744 = v741 * (255 - v743);
                                        v735 = v1280;
                                        LOBYTE(v742) = v743 + v744 / 255;
                                        v737 = (unsigned __int8 *)v1297;
                                        v738[3] = v742;
                                      }
                                      v737 += 4;
                                      ++v735;
                                      v738 += 4;
                                      v1297 = (SIZE_T)v737;
                                      LODWORD(v1280) = v735;
                                    }
                                    while ( v735 < v731 );
                                    v732 = (char *)v1309 + v1302;
                                    v733 = v1278 + Size;
                                    v1309 = (char *)v1309 + v1302;
                                    Size += v1278;
                                    LODWORD(v1287) = (_DWORD)v1287 + 1;
                                  }
                                  while ( (int)v1287 < (int)v1292 );
                                  v82 = v1279;
                                  v716 = pcchLength;
                                }
                                ((void (__fastcall *)(unsigned __int64))off_180114038[0])(v1312);
                                v719 = 0;
                                if ( v1291 )
                                  ((void (__fastcall *)(size_t, LPVOID))off_180114078[0])(v716, v1291);
                              }
                              else
                              {
                                v718 = GetLastError();
                                v719 = 0;
                                v713 = v718;
                                if ( v718 > 0 )
                                  v713 = (unsigned __int16)v718 | 0x80070000;
                                if ( v713 >= 0 )
                                  v713 = -2147467259;
                              }
                              ((void (__fastcall *)(size_t))off_180114030[0])(v716);
                              if ( v713 < 0 )
                                goto LABEL_1014;
                              v1374 = 0;
                              memset_0(v1375, 0, 0x64u);
                              v1386 = 0;
                              memset_0(v1387, 0, 0x64u);
                              Size = (SIZE_T)v1349;
                              memset(v1409, 0, 28);
                              v1408 = 0;
                              v1398 = 0;
                              if ( !v1349 )
                                goto LABEL_1014;
                              v745 = psz;
                              dwBytes_4 = v1347;
                              v1302 = v1352;
                              v746 = ((__int64 (__fastcall *)(STRSAFE_PCNZWCH, __int64))off_180114050[0])(psz, 7);
                              if ( v746 )
                              {
                                if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180114068[0])(
                                       v746,
                                       104,
                                       &v1374) )
                                {
                                  LODWORD(v1280) = v1375[0];
                                  pcchLength = v1376;
                                  v745 = psz;
                                  LODWORD(v1287) = v1375[1];
                                }
                                else
                                {
                                  pcchLength = 0;
                                  LODWORD(v1287) = 0;
                                  LODWORD(v1280) = 0;
                                }
                                v747 = (void *)((__int64 (__fastcall *)(STRSAFE_PCNZWCH))off_180114010[0])(v745);
                                v1309 = v747;
                                v748 = v747;
                                if ( v747 )
                                {
                                  DWORD1(v1408) = v1361 - v1359;
                                  DWORD2(v1408) = v1360 - v1362;
                                  v1342 = 0;
                                  memset(v1409, 0, 28);
                                  LODWORD(v1408) = 40;
                                  HIDWORD(v1408) = 2097153;
                                  v1312 = ((__int64 (__fastcall *)(void *, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180114018[0])(
                                            v747,
                                            &v1408,
                                            0,
                                            &v1342,
                                            0,
                                            0);
                                  v749 = v1312;
                                  if ( v1312 )
                                  {
                                    if ( ((unsigned int (__fastcall *)(unsigned __int64, __int64, int *))off_180114068[0])(
                                           v1312,
                                           104,
                                           &v1386) )
                                    {
                                      v1297 = v1388;
                                    }
                                    else
                                    {
                                      v1297 = 0;
                                    }
                                    DWORD2(v1398) = v1361 - v1359;
                                    HIDWORD(v1398) = v1362 - v1360;
                                    ((void (__fastcall *)(void *, unsigned __int64))off_180114078[0])(v748, v749);
                                    ((void (__fastcall *)(void *, __int64))off_180114080[0])(v748, 1);
                                    v751 = ((__int64 (__fastcall *)(void *, size_t))off_180114078[0])(v748, v1302);
                                    v752 = off_1801140E8[0];
                                    v1278 = v751;
                                    v753 = ((__int64 (__fastcall *)(_QWORD))off_180114070[0])(0);
                                    ((void (__fastcall *)(void *, __int128 *, __int64))v752)(v748, &v1398, v753);
                                    ((void (__fastcall *)(void *, SIZE_T, __int64, __int128 *, _DWORD, _QWORD))off_1801140D8[0])(
                                      v748,
                                      Size,
                                      0xFFFFFFFFLL,
                                      &v1398,
                                      v1305,
                                      0);
                                    if ( v710 == 1 )
                                    {
                                      if ( dwBytes_4 )
                                        v1283 = ((__int64 (__fastcall *)(__int64))off_180114118[0])(8);
                                    }
                                    else
                                    {
                                      v1283 = -5723992;
                                    }
                                    v754 = 0;
                                    v755 = -v1359;
                                    v756 = 0;
                                    if ( v1359 >= 0 )
                                    {
                                      v754 = v1359;
                                      v755 = 0;
                                    }
                                    v757 = -v1360;
                                    if ( v1360 >= 0 )
                                    {
                                      v757 = 0;
                                      v756 = v1360;
                                    }
                                    v758 = DWORD2(v1398) - v755;
                                    if ( DWORD2(v1398) - v755 >= (int)v1280 - v754 )
                                      v758 = v1280 - v754;
                                    v759 = HIDWORD(v1398) - v757;
                                    if ( HIDWORD(v1398) - v757 >= (int)v1287 - v756 )
                                      v759 = (_DWORD)v1287 - v756;
                                    LODWORD(v1290) = v759;
                                    if ( v758 > 0 && v759 > 0 )
                                    {
                                      LODWORD(v1287) = 0;
                                      v760 = v1297 + 4 * (v755 + (__int64)(v757 * DWORD2(v1398)));
                                      v761 = pcchLength + 4 * (v754 + (__int64)((int)v1280 * v756));
                                      dwBytes_4 = v1283 >> 8;
                                      LODWORD(v1282) = HIWORD(v1283);
                                      v1302 = 4LL * SDWORD2(v1398);
                                      Size = 4LL * (int)v1280;
                                      pcchLength = v761;
                                      do
                                      {
                                        v762 = dwBytes_4;
                                        v763 = (unsigned __int8 *)v760;
                                        v764 = v1282;
                                        v765 = (_BYTE *)v761;
                                        v766 = v1283;
                                        v767 = 0;
                                        v1297 = v760;
                                        LODWORD(v1280) = 0;
                                        do
                                        {
                                          v768 = ~(unsigned __int8)((*v763 + v763[2] + 2 * (unsigned int)v763[1]) >> 2);
                                          if ( (unsigned __int8)((*v763 + v763[2] + 2 * (unsigned int)v763[1]) >> 2) != 0xFF )
                                          {
                                            v769 = (unsigned __int8)v765[2];
                                            v770 = v768;
                                            v771 = (int)((unsigned __int64)(2155905153LL * v768 * (v766 - v769)) >> 32) >> 7;
                                            v765[2] = v769 + (v771 < 0) + v771;
                                            v765[1] -= v770 * (v762 - v765[1]);
                                            *v765 -= v770 * (v764 - *v765);
                                            v772 = (unsigned __int8)v765[3];
                                            v773 = v770 * (255 - v772);
                                            v767 = v1280;
                                            LOBYTE(v771) = v772 + v773 / 255;
                                            v763 = (unsigned __int8 *)v1297;
                                            v765[3] = v771;
                                          }
                                          v763 += 4;
                                          ++v767;
                                          v765 += 4;
                                          v1297 = (SIZE_T)v763;
                                          LODWORD(v1280) = v767;
                                        }
                                        while ( v767 < v758 );
                                        v761 = Size + pcchLength;
                                        v760 += v1302;
                                        pcchLength += Size;
                                        LODWORD(v1287) = (_DWORD)v1287 + 1;
                                      }
                                      while ( (int)v1287 < (int)v1290 );
                                      v82 = v1279;
                                      v748 = v1309;
                                    }
                                    ((void (__fastcall *)(unsigned __int64))off_180114038[0])(v1312);
                                    if ( v1278 )
                                      ((void (__fastcall *)(void *, size_t))off_180114078[0])(v748, v1278);
                                  }
                                  else
                                  {
                                    v719 = GetLastError();
                                    v750 = v719 < 0;
                                    if ( v719 > 0 )
                                    {
                                      v719 = (unsigned __int16)v719 | 0x80070000;
                                      v750 = v719 < 0;
                                    }
                                    if ( !v750 )
                                      v719 = -2147467259;
                                  }
                                  ((void (__fastcall *)(void *))off_180114030[0])(v748);
                                  if ( v719 < 0 )
                                    goto LABEL_1014;
                                  v774 = psz;
                                  v1291 = 0;
                                  v775 = 0;
LABEL_1133:
                                  ((void (__fastcall *)(STRSAFE_PCNZWCH, _QWORD))off_180114080[0])(
                                    v774,
                                    (unsigned int)v1285);
                                  if ( !v775 )
                                  {
LABEL_1012:
                                    v787 = v1291;
                                    if ( !v1291 )
                                      goto LABEL_1014;
                                    goto LABEL_1013;
                                  }
LABEL_1011:
                                  ((void (__fastcall *)(size_t))off_180114038[0])(v775);
                                  goto LABEL_1012;
                                }
                              }
                            }
                          }
LABEL_993:
                          GetLastError();
                          goto LABEL_1014;
                        }
                        if ( v1347 || (v776 = -64, v710 == 1) )
                          v776 = -1;
                        BYTE2(dwBytes) = v776;
                        LOWORD(dwBytes) = 0;
                        HIBYTE(dwBytes) = 1;
                        v1291 = (LPVOID)((__int64 (__fastcall *)(STRSAFE_PCNZWCH))off_180114010[0])(v711);
                        if ( !v1291 )
                          goto LABEL_993;
                        if ( v710 == 1 )
                        {
                          v777 = 0;
                          v778 = v1361 - v1359;
                          LODWORD(v1292) = 0;
                          if ( v1361 - v1359 <= v1357 - v1355 )
                            v778 = v1357 - v1355;
                          v779 = v1362 - v1356;
                          v1301 = v778;
                          v1316 = v1362 - v1356;
                          if ( v1346 )
                          {
                            v780 = v1355 + v778 - v1357;
                            v781 = v778 + v1359 - v1361;
                          }
                          else
                          {
                            v780 = 0;
                            v781 = 0;
                          }
                          v782 = v780 + v1357 - v1355;
                          v783 = v1360 - v1356;
                          v1284 = v781;
                          LODWORD(v1290) = v1358 - v1356;
                          v784 = v781 + v1361 - v1359;
                          v785 = v1362 - v1356;
                        }
                        else
                        {
                          v778 = DWORD2(v1318);
                          v779 = HIDWORD(v1318);
                          v777 = v1356;
                          v780 = v1355;
                          v782 = v1357;
                          v783 = v1360;
                          v784 = v1361;
                          LODWORD(v1290) = v1358;
                          v1284 = v1359;
                          v785 = v1362;
                          v1316 = HIDWORD(v1318);
                          v1301 = DWORD2(v1318);
                          LODWORD(v1292) = v1356;
                        }
                        v1298 = v784;
                        LODWORD(v1280) = v785;
                        v1343[0] = 0;
                        v1402[1] = v778;
                        dwBytes_4 = v783;
                        LODWORD(v1304) = v782;
                        LODWORD(v1296) = v780;
                        memset(&v1402[4], 0, 28);
                        v1402[0] = 40;
                        v1402[2] = -v779;
                        v1402[3] = 2097153;
                        v786 = ((__int64 (__fastcall *)(LPVOID, _DWORD *, _QWORD, __int64 *, _QWORD, _DWORD))off_180114018[0])(
                                 v1291,
                                 v1402,
                                 0,
                                 v1343,
                                 0,
                                 0);
                        v1278 = v786;
                        if ( !v786 )
                        {
                          GetLastError();
                          v787 = v1291;
LABEL_1013:
                          ((void (__fastcall *)(LPVOID))off_180114030[0])(v787);
LABEL_1014:
                          if ( Src )
                            ((void (__fastcall *)(void *))off_180114038[0])(Src);
                          goto LABEL_1016;
                        }
                        ((void (__fastcall *)(LPVOID, size_t))off_180114078[0])(v1291, v786);
                        if ( v710 == 1 && Src )
                        {
                          v1399 = 0;
                          v1400 = v1301;
                          v1401 = v1316;
                          ((void (__fastcall *)(LPVOID, __int64 *))off_1801140E8[0])(v1291, &v1399);
                        }
                        v1377 = 0;
                        memset_0(v1378, 0, 0x64u);
                        v1389 = 0;
                        memset_0(v1390, 0, 0x64u);
                        Size = (SIZE_T)v1348;
                        memset(v1411, 0, 28);
                        v1410 = 0;
                        v1396 = 0;
                        if ( v1348 )
                        {
                          LODWORD(v1294) = v1347;
                          v1302 = v1351;
                          v788 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180114050[0])(v1291, 7);
                          if ( !v788 )
                            goto LABEL_1009;
                          if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180114068[0])(
                                 v788,
                                 104,
                                 &v1377) )
                          {
                            pcchLength = v1379;
                            LODWORD(v1287) = v1378[0];
                            LODWORD(v1282) = v1378[1];
                          }
                          else
                          {
                            pcchLength = 0;
                            LODWORD(v1282) = 0;
                            LODWORD(v1287) = 0;
                          }
                          v804 = ((__int64 (__fastcall *)(LPVOID))off_180114010[0])(v1291);
                          v1293 = v804;
                          if ( !v804 )
                            goto LABEL_1009;
                          v1337 = 0;
                          v805 = v1304 - v780;
                          LODWORD(v1410) = 40;
                          v806 = (int)v1290;
                          DWORD2(v1410) = v777 - (_DWORD)v1290;
                          v807 = 0;
                          LODWORD(v1304) = v805;
                          DWORD1(v1410) = v805;
                          memset(v1411, 0, 28);
                          HIDWORD(v1410) = 2097153;
                          v808 = (void *)((__int64 (__fastcall *)(SIZE_T, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180114018[0])(
                                           v804,
                                           &v1410,
                                           0,
                                           &v1337,
                                           0,
                                           0);
                          v1309 = v808;
                          if ( v808 )
                          {
                            if ( ((unsigned int (__fastcall *)(void *, __int64, int *))off_180114068[0])(
                                   v808,
                                   104,
                                   &v1389) )
                            {
                              v1297 = v1391;
                            }
                            else
                            {
                              v1297 = 0;
                            }
                            HIDWORD(v1396) = v806 - v1292;
                            v810 = v1293;
                            DWORD2(v1396) = v1304;
                            ((void (__fastcall *)(SIZE_T, void *))off_180114078[0])(v1293, v1309);
                            ((void (__fastcall *)(SIZE_T, __int64))off_180114080[0])(v810, 1);
                            v811 = (void *)((__int64 (__fastcall *)(SIZE_T, size_t))off_180114078[0])(v810, v1302);
                            v812 = off_1801140E8[0];
                            v1295 = v811;
                            v813 = ((__int64 (__fastcall *)(_QWORD))off_180114070[0])(0);
                            ((void (__fastcall *)(SIZE_T, __int128 *, __int64))v812)(v1293, &v1396, v813);
                            v814 = v1293;
                            ((void (__fastcall *)(SIZE_T, SIZE_T, __int64, __int128 *, _DWORD, _QWORD))off_1801140D8[0])(
                              v1293,
                              Size,
                              0xFFFFFFFFLL,
                              &v1396,
                              v1305,
                              0);
                            if ( v710 == 1 )
                            {
                              if ( (_DWORD)v1294 )
                                v815 = ((__int64 (__fastcall *)(__int64))off_180114118[0])(8);
                              else
                                v815 = 0xFFFFFF;
                            }
                            else
                            {
                              v815 = -5723992;
                            }
                            v816 = v1292;
                            v817 = -(int)v1296;
                            LODWORD(v1304) = v815;
                            v818 = 0;
                            if ( (int)v1296 >= 0 )
                            {
                              v817 = 0;
                              v818 = (int)v1296;
                            }
                            if ( (v1292 & 0x80000000) == 0LL )
                            {
                              v819 = 0;
                            }
                            else
                            {
                              v819 = -(int)v1292;
                              v816 = 0;
                            }
                            v820 = DWORD2(v1396) - v817;
                            if ( DWORD2(v1396) - v817 >= (int)v1287 - v818 )
                              v820 = (_DWORD)v1287 - v818;
                            LODWORD(v1294) = v820;
                            v821 = HIDWORD(v1396) - v819;
                            if ( HIDWORD(v1396) - v819 >= (int)v1282 - v816 )
                              v821 = v1282 - v816;
                            LODWORD(v1296) = v821;
                            if ( v820 > 0 && v821 > 0 )
                            {
                              v822 = (int)v1287;
                              v823 = v1304;
                              v824 = (int)v1294;
                              LODWORD(v1290) = 0;
                              v825 = v1297 + 4 * (v817 + (__int64)(DWORD2(v1396) * v819));
                              Size = v825;
                              v826 = pcchLength + 4 * (v818 + (__int64)((int)v1287 * v816));
                              LODWORD(v1287) = (unsigned int)v1304 >> 8;
                              LODWORD(v1292) = WORD1(v1304);
                              v1302 = 4LL * SDWORD2(v1396);
                              v1312 = 4 * v822;
                              pcchLength = v826;
                              do
                              {
                                v827 = (char)v1287;
                                v828 = 0;
                                v829 = v1292;
                                v830 = (unsigned __int8 *)v825;
                                LODWORD(v1282) = 0;
                                v831 = (_BYTE *)v826;
                                v1297 = v825;
                                do
                                {
                                  v832 = ~(unsigned __int8)((*v830 + v830[2] + 2 * (unsigned int)v830[1]) >> 2);
                                  if ( (unsigned __int8)((*v830 + v830[2] + 2 * (unsigned int)v830[1]) >> 2) != 0xFF )
                                  {
                                    v833 = (unsigned __int8)v831[2];
                                    v834 = v832;
                                    v835 = (int)((unsigned __int64)(2155905153LL * v832 * (v823 - v833)) >> 32) >> 7;
                                    v831[2] = v833 + (v835 < 0) + v835;
                                    v831[1] -= v834 * (v827 - v831[1]);
                                    *v831 -= v834 * (v829 - *v831);
                                    v836 = (unsigned __int8)v831[3];
                                    v837 = v834 * (255 - v836);
                                    v828 = v1282;
                                    LOBYTE(v835) = v836 + v837 / 255;
                                    v830 = (unsigned __int8 *)v1297;
                                    v831[3] = v835;
                                  }
                                  v830 += 4;
                                  ++v828;
                                  v831 += 4;
                                  v1297 = (SIZE_T)v830;
                                  LODWORD(v1282) = v828;
                                }
                                while ( v828 < v824 );
                                v825 = v1302 + Size;
                                v826 = v1312 + pcchLength;
                                Size += v1302;
                                pcchLength += v1312;
                                LODWORD(v1290) = (_DWORD)v1290 + 1;
                              }
                              while ( (int)v1290 < (int)v1296 );
                              v82 = v1279;
                              v783 = dwBytes_4;
                              v814 = v1293;
                            }
                            ((void (__fastcall *)(void *))off_180114038[0])(v1309);
                            if ( v1295 )
                              ((void (__fastcall *)(SIZE_T, LPVOID))off_180114078[0])(v814, v1295);
                          }
                          else
                          {
                            v807 = GetLastError();
                            v809 = v807 < 0;
                            if ( v807 > 0 )
                            {
                              v807 = (unsigned __int16)v807 | 0x80070000;
                              v809 = v807 < 0;
                            }
                            if ( !v809 )
                              v807 = -2147467259;
                          }
                          ((void (__fastcall *)(SIZE_T))off_180114030[0])(v1293);
                          if ( v807 < 0 )
                            goto LABEL_1010;
                          v838 = 0;
                          v1380 = 0;
                          memset_0(v1381, 0, 0x64u);
                          v1392 = 0;
                          memset_0(v1393, 0, 0x64u);
                          Size = (SIZE_T)v1349;
                          memset(v1413, 0, 28);
                          v1412 = 0;
                          v1397 = 0;
                          if ( !v1349 )
                            goto LABEL_1010;
                          v839 = v1291;
                          LODWORD(v1294) = v1347;
                          v1302 = v1352;
                          v840 = ((__int64 (__fastcall *)(LPVOID, __int64))off_180114050[0])(v1291, 7);
                          if ( !v840 )
                            goto LABEL_1009;
                          if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_180114068[0])(
                                 v840,
                                 104,
                                 &v1380) )
                          {
                            dwBytes_4 = v1381[0];
                            pcchLength = v1382;
                            v838 = 0;
                            LODWORD(v1282) = v1381[1];
                          }
                          else
                          {
                            pcchLength = 0;
                            LODWORD(v1282) = 0;
                            dwBytes_4 = 0;
                          }
                          v1293 = ((__int64 (__fastcall *)(LPVOID))off_180114010[0])(v839);
                          if ( v1293 )
                          {
                            v1298 -= v1284;
                            DWORD1(v1412) = v1298;
                            DWORD2(v1412) = v783 - v1280;
                            v1338 = 0;
                            memset(v1413, 0, 28);
                            LODWORD(v1412) = 40;
                            HIDWORD(v1412) = 2097153;
                            v841 = (void *)((__int64 (__fastcall *)(SIZE_T, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_180114018[0])(
                                             v1293,
                                             &v1412,
                                             0,
                                             &v1338,
                                             0,
                                             0);
                            v1309 = v841;
                            if ( v841 )
                            {
                              if ( ((unsigned int (__fastcall *)(void *, __int64, int *))off_180114068[0])(
                                     v841,
                                     104,
                                     &v1392) )
                              {
                                v1297 = v1394;
                              }
                              else
                              {
                                v1297 = 0;
                              }
                              v843 = v1293;
                              HIDWORD(v1397) = v1280 - v783;
                              DWORD2(v1397) = v1298;
                              ((void (__fastcall *)(SIZE_T, void *))off_180114078[0])(v1293, v1309);
                              ((void (__fastcall *)(SIZE_T, __int64))off_180114080[0])(v843, 1);
                              v844 = (void *)((__int64 (__fastcall *)(SIZE_T, size_t))off_180114078[0])(v843, v1302);
                              v845 = off_1801140E8[0];
                              v1295 = v844;
                              v846 = ((__int64 (__fastcall *)(_QWORD))off_180114070[0])(0);
                              ((void (__fastcall *)(SIZE_T, __int128 *, __int64))v845)(v1293, &v1397, v846);
                              v847 = v1293;
                              ((void (__fastcall *)(SIZE_T, SIZE_T, __int64, __int128 *, _DWORD, _QWORD))off_1801140D8[0])(
                                v1293,
                                Size,
                                0xFFFFFFFFLL,
                                &v1397,
                                v1305,
                                0);
                              if ( v710 == 1 )
                              {
                                if ( (_DWORD)v1294 )
                                  v1283 = ((__int64 (__fastcall *)(__int64))off_180114118[0])(8);
                              }
                              else
                              {
                                v1283 = -5723992;
                              }
                              v848 = 0;
                              v849 = -v1284;
                              if ( (v1284 & 0x80000000) == 0 )
                              {
                                v849 = 0;
                                v848 = v1284;
                              }
                              if ( v783 >= 0 )
                              {
                                v850 = 0;
                              }
                              else
                              {
                                v850 = -v783;
                                v783 = 0;
                              }
                              v851 = DWORD2(v1397) - v849;
                              if ( DWORD2(v1397) - v849 >= (int)(dwBytes_4 - v848) )
                                v851 = dwBytes_4 - v848;
                              LODWORD(v1294) = v851;
                              v852 = HIDWORD(v1397) - v850;
                              if ( HIDWORD(v1397) - v850 >= (int)v1282 - v783 )
                                v852 = v1282 - v783;
                              LODWORD(v1287) = v852;
                              if ( v851 > 0 && v852 > 0 )
                              {
                                v853 = (int)v1294;
                                LODWORD(v1282) = 0;
                                v854 = v1297 + 4 * (v849 + (__int64)(DWORD2(v1397) * v850));
                                Size = v854;
                                v855 = pcchLength + 4 * (v848 + (__int64)(int)(dwBytes_4 * v783));
                                LODWORD(v1290) = v1283 >> 8;
                                LODWORD(v1280) = HIWORD(v1283);
                                v1302 = 4LL * SDWORD2(v1397);
                                v1312 = 4LL * (int)dwBytes_4;
                                pcchLength = v855;
                                do
                                {
                                  v856 = (char)v1290;
                                  v857 = (unsigned __int8 *)v854;
                                  v858 = v1280;
                                  v859 = (_BYTE *)v855;
                                  v860 = v1283;
                                  v861 = 0;
                                  v1297 = v854;
                                  dwBytes_4 = 0;
                                  do
                                  {
                                    v862 = ~(unsigned __int8)((*v857 + v857[2] + 2 * (unsigned int)v857[1]) >> 2);
                                    if ( (unsigned __int8)((*v857 + v857[2] + 2 * (unsigned int)v857[1]) >> 2) != 0xFF )
                                    {
                                      v863 = (unsigned __int8)v859[2];
                                      v864 = v862;
                                      v865 = (int)((unsigned __int64)(2155905153LL * v862 * (v860 - v863)) >> 32) >> 7;
                                      v859[2] = v863 + (v865 < 0) + v865;
                                      v859[1] -= v864 * (v856 - v859[1]);
                                      *v859 -= v864 * (v858 - *v859);
                                      v866 = (unsigned __int8)v859[3];
                                      v867 = v864 * (255 - v866);
                                      v861 = dwBytes_4;
                                      LOBYTE(v865) = v866 + v867 / 255;
                                      v857 = (unsigned __int8 *)v1297;
                                      v859[3] = v865;
                                    }
                                    v857 += 4;
                                    ++v861;
                                    v859 += 4;
                                    v1297 = (SIZE_T)v857;
                                    dwBytes_4 = v861;
                                  }
                                  while ( v861 < v853 );
                                  v854 = v1302 + Size;
                                  v855 = v1312 + pcchLength;
                                  Size += v1302;
                                  pcchLength += v1312;
                                  LODWORD(v1282) = v1282 + 1;
                                }
                                while ( (int)v1282 < (int)v1287 );
                                v82 = v1279;
                                v847 = v1293;
                              }
                              ((void (__fastcall *)(void *))off_180114038[0])(v1309);
                              if ( v1295 )
                                ((void (__fastcall *)(SIZE_T, LPVOID))off_180114078[0])(v847, v1295);
                              v839 = v1291;
                            }
                            else
                            {
                              v838 = GetLastError();
                              v842 = v838 < 0;
                              if ( v838 > 0 )
                              {
                                v838 = (unsigned __int16)v838 | 0x80070000;
                                v842 = v838 < 0;
                              }
                              if ( !v842 )
                                v838 = -2147467259;
                            }
                            ((void (__fastcall *)(SIZE_T))off_180114030[0])(v1293);
                            if ( v838 >= 0 )
                            {
                              v339 = v710 == 1;
                              v774 = psz;
                              if ( v339 )
                                ((void (__fastcall *)(STRSAFE_PCNZWCH, _QWORD, _QWORD, _QWORD, int, LPVOID, _DWORD, _DWORD, int))off_180114000[0])(
                                  psz,
                                  (unsigned int)v1355,
                                  (unsigned int)v1356,
                                  v1301,
                                  v1316,
                                  v839,
                                  0,
                                  0,
                                  13369376);
                              else
                                ((void (__fastcall *)(STRSAFE_PCNZWCH, _QWORD, _QWORD, _QWORD, int, LPVOID, _DWORD, _DWORD, unsigned int, int, unsigned int))off_180114040[0])(
                                  psz,
                                  (unsigned int)v1318,
                                  DWORD1(v1318),
                                  v1301,
                                  v1316,
                                  v839,
                                  0,
                                  0,
                                  v1301,
                                  v1316,
                                  dwBytes);
                              v775 = v1278;
                              goto LABEL_1133;
                            }
                          }
                          else
                          {
LABEL_1009:
                            GetLastError();
                          }
                        }
LABEL_1010:
                        v775 = v1278;
                        goto LABEL_1011;
                      }
                    }
                    else
                    {
                      v710 = v472 & 0xF;
                      v709 = v710;
                    }
                    if ( v709 != 1 )
                      goto LABEL_905;
                    goto LABEL_903;
                  }
                  v588 = 0;
                  pcchLength = 0;
                  v1297 = 0;
                  v1328 = 0;
                  v1295 = 0;
                  Src = 0;
                  v589 = 0;
                  v1315 = 0;
                  memset(v1344, 0, sizeof(v1344));
                  v1293 = 0;
                  v1321 = 0;
                  if ( !((unsigned int (__fastcall *)(__int64, unsigned int *, _QWORD, unsigned int *))off_1801140A0[0])(
                          8,
                          &v1315,
                          0,
                          &v1321) )
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
                    goto LABEL_709;
                  }
                  v591 = MemoryAlloc(2LL * v1321);
                  SP<unsigned long,SP_MEM<unsigned long>>::operator=(&Src, v591);
                  v592 = (char *)Src;
                  if ( Src )
                  {
                    v593 = MemoryAlloc(4LL * (v1315 + 1));
                    SP<unsigned long,SP_MEM<unsigned long>>::operator=(&v1293, v593);
                    v123 = (_BYTE *)v1293;
                    if ( v1293 )
                    {
                      if ( ((unsigned int (__fastcall *)(__int64, unsigned int *, char *, unsigned int *))off_1801140A0[0])(
                             8,
                             &v1315,
                             v592,
                             &v1321) )
                      {
                        if ( v1315 )
                        {
                          for ( i3 = 0; i3 < v1315; ++i3 )
                          {
                            *(_DWORD *)v123 = ((__int64 (__fastcall *)(char *, _QWORD))off_1801140B0[0])(v592, 0);
                            v596 = -1;
                            do
                              ++v596;
                            while ( *(_WORD *)&v592[2 * v596] );
                            v123 += 4;
                            v592 += 2 * v596 + 2;
                          }
                        }
                        v589 = v1293;
                        *(_DWORD *)v123 = 1033;
                        LODWORD(v123) = v1315 + 1;
                        v1293 = 0;
                        v1297 = v589;
                      }
                      else
                      {
                        v588 = GetLastError();
                        v594 = v588 < 0;
                        if ( v588 > 0 )
                        {
                          v588 = (unsigned __int16)v588 | 0x80070000;
                          v594 = v588 < 0;
                        }
                        v589 = pcchLength;
                        if ( !v594 )
                          v588 = -2147467259;
                        LODWORD(v123) = pcchLength;
                      }
LABEL_709:
                      SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1293);
                      SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&Src);
                      if ( v588 < 0 )
                      {
                        Src = 0;
                        Size = 0;
                        pcchLength = 0;
                      }
                      else
                      {
                        LODWORD(v1280) = 0;
                        v597 = 0;
                        v598 = 0;
                        if ( (_DWORD)v123 )
                        {
                          while ( 2 )
                          {
                            for ( i4 = 0; i4 < 0x26; ++i4 )
                            {
                              if ( *(_DWORD *)(v589 + 4LL * v598) == dword_1800F4330[i4] )
                              {
                                v597 = i4;
                                LODWORD(v1280) = i4;
                                goto LABEL_717;
                              }
                            }
                            if ( ++v598 < (unsigned int)v123 )
                              continue;
                            break;
                          }
                        }
LABEL_717:
                        v600 = v597;
                        LODWORD(v1287) = 0;
                        memset(v1417, 0, sizeof(v1417));
                        if ( ((unsigned int (__fastcall *)(_QWORD, _BYTE *, __int64))off_1801140A8[0])(
                               (unsigned int)dword_1800F4330[v597],
                               v1437,
                               85)
                          && ((int (__fastcall *)(_BYTE *, __int64, _OWORD *, __int64))off_180114090[0])(
                               v1437,
                               88,
                               v1417,
                               16) > 0 )
                        {
                          LODWORD(v1287) = (HIDWORD(v1417[0]) >> 27) & 1;
                        }
                        memset_0(v1345, 0, 0x98u);
                        v601 = L"Segoe UI Light";
                        for ( i5 = 0; i5 != 19; ++i5 )
                        {
                          v1345[i5] = v601;
                          v603 = -1;
                          do
                            ++v603;
                          while ( v601[v603] );
                          v601 += v603 + 1;
                        }
                        Src = (void *)v1345[*((unsigned __int8 *)qword_1800F43D0 + 3 * v600)];
                        Size = v1345[*((unsigned __int8 *)qword_1800F43D0 + 3 * v600 + 1)];
                        pcchLength = v1345[*((unsigned __int8 *)qword_1800F43D0 + 3 * v600 + 2)];
                        v604 = MemoryAlloc(0x1C90u);
                        v605 = v604;
                        if ( v604 )
                        {
                          v606 = qword_1800F2690;
                          v607 = v604;
                          v608 = 0;
                          v609 = -1;
                          v610 = 0;
                          v611 = 0;
                          v612 = 914;
                          do
                          {
                            v613 = *((unsigned __int8 *)v606 + 1);
                            v614 = *(unsigned __int8 *)v606;
                            v615 = *((unsigned __int8 *)v606++ + 4);
                            v616 = *((unsigned __int8 *)v606 - 5)
                                 | ((*((unsigned __int8 *)v606 - 6) | ((v613 | (v614 << 8)) << 8)) << 8);
                            v617 = v611 ^ v616;
                            v618 = *((unsigned __int8 *)v606 - 1)
                                 | ((*((unsigned __int8 *)v606 - 2)
                                   | ((*((unsigned __int8 *)v606 - 3) | (v615 << 8)) << 8)) << 8);
                            v619 = v611 ^ v616 ^ v610 ^ v618 ^ 0xAC987321;
                            v620 = v617 ^ (__ROR4__(v619, 22) + 4991 * __ROR4__(v619 + 1419157410, 27));
                            v621 = v619 ^ (43881 * __ROR4__(v620 + 133239679, 9) - __ROR4__(v620, 30));
                            v622 = v620 ^ (24670 * v621 - (v621 >> 13) - 123127970);
                            v623 = v621 ^ (2033 * __ROR4__(v622 ^ 0xAB69, 26) - __ROR4__(v622, 30));
                            v624 = v622 ^ (133239679 - (v623 ^ 0xAB69605E));
                            v625 = v623 ^ (43881 * (v624 ^ 0x137F)) ^ __ROR4__(v624, 6);
                            v626 = v624 ^ (__ROR4__(v625, 30) + 24670 * __ROR4__(v625 + 133239679, 15));
                            v627 = v625 ^ (2033 * __ROR4__(v626 + 1419157410, 14) - __ROR4__(v626, 24));
                            v628 = v626 ^ __ROR4__(v627, 10) ^ (4991 * __ROR4__(v627 ^ 0xAB69605E, 12));
                            v629 = v627 ^ (v628 >> 10) ^ (43881 * (v628 ^ 0x7F1));
                            v630 = v628 ^ (2033 * (__ROR4__(~v629, 5) + 24670));
                            v631 = v630
                                 ^ (((v629 ^ (v630 - 2033) ^ 0xAB69605E) >> 2)
                                  + 4991 * __ROR4__(v629 ^ (v630 - 2033) ^ 0xAB6967AF, 30));
                            v632 = v629
                                 ^ (v630 - 2033)
                                 ^ 0xAB69605E
                                 ^ (__ROR4__(v631, 25) + 43881 * __ROR4__(v631 - 133239679, 6));
                            v633 = v631 ^ (24670 * (v632 ^ 0x137F) + __ROR4__(v632, 9));
                            v634 = v632 ^ (__ROR4__(v633, 25) + 2033 * __ROR4__(v633 ^ 0xAB69, 27));
                            v635 = v633 ^ v634 ^ 0xAC987321;
                            v636 = v634 ^ (4991 * __ROR4__(v635, 3) - 219010071);
                            v637 = v635 ^ (24670 * __ROR4__(v636 - 133239679, 1) - __ROR4__(v636, 6));
                            v638 = v636 ^ (__ROR4__(v637, 18) + 2033 * __ROR4__(v637 - 1419157410, 29));
                            v639 = v637 ^ (4991 * __ROR4__(v638 - 1419157410, 17) - __ROR4__(v638, 14));
                            v640 = v638 ^ (v639 >> 3) ^ (43881 * (v639 ^ 0x605E));
                            v641 = __ROR4__(v640, 30);
                            v610 = v609 ^ v640;
                            v609 = v618;
                            v611 = v608
                                 ^ v639
                                 ^ v641
                                 ^ (24670 * __ROR4__(v638 ^ (v639 >> 3) ^ (43881 * (v639 ^ 0x605E)) ^ 0x7F1137F, 28));
                            v608 = v616;
                            v607[3] = v611;
                            v607[7] = v610;
                            v607[2] = __ROR4__(v611, 8);
                            v607[6] = __ROR4__(v610, 8);
                            v607[1] = __ROR4__(v611, 16);
                            v607[5] = __ROR4__(v610, 16);
                            *v607 = __ROR4__(v611, 24);
                            v607[4] = __ROR4__(v610, 24);
                            v607 += 8;
                            --v612;
                          }
                          while ( v612 );
                          LOBYTE(v472) = v1301;
                          v642 = 0;
                          v643 = 0;
                          v644 = 7312;
                          do
                          {
                            v645 = (__m128)_mm_loadu_si128((const __m128i *)&v605[v642]);
                            v642 += 16LL;
                            v646 = _mm_xor_ps(v645, v643);
                            v643 = v646;
                          }
                          while ( v642 < 0x1C90 );
                          v647 = _mm_xor_ps(v646, (__m128)_mm_srli_si128((__m128i)v646, 8));
                          v648 = _mm_xor_ps(v647, (__m128)_mm_srli_si128((__m128i)v647, 4));
                          v649 = _mm_xor_ps(v648, (__m128)_mm_srli_si128((__m128i)v648, 2));
                          if ( (unsigned __int8)_mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                             v649,
                                                                             (__m128)_mm_srli_si128((__m128i)v649, 1))) == 127 )
                          {
                            v650 = v1280;
                            v588 = 0;
                            v1328 = v605;
                            v651 = 0;
                            v1319 = 7312;
                            do
                            {
                              for ( i6 = 0; i6 < 0x26; ++i6 )
                              {
                                if ( v650 == i6 )
                                  *((_QWORD *)v1344 + v651) = v605;
                                v653 = -1;
                                do
                                  ++v653;
                                while ( v605[v653] );
                                v605 += v653 + 1;
                              }
                              ++v651;
                            }
                            while ( v651 < 6 );
                            v654 = MemoryAlloc(0x18u);
                            SP<unsigned long,SP_MEM<unsigned long>>::operator=(&v1295, v654);
                            v655 = (void **)v1295;
                            if ( v1295 )
                            {
                              v656 = 0;
                              *(_OWORD *)v1295 = 0;
                              v655[2] = 0;
                              LODWORD(v1280) = 0;
                              while ( 2 )
                              {
                                v657 = 0;
                                v1302 = v656;
                                while ( *((_WORD *)&v1285 + v656) != word_1800F4448[v657] )
                                {
                                  if ( ++v657 >= 6 )
                                    goto LABEL_754;
                                }
                                v658 = *((_QWORD *)v1344 + v657);
                                v659 = -1;
                                do
                                  ++v659;
                                while ( *(_BYTE *)(v659 + v658) );
                                v660 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, _QWORD, _DWORD))off_1801140C0[0])(
                                         65001,
                                         0,
                                         v658,
                                         (unsigned int)(v659 + 1),
                                         0,
                                         0);
                                dwBytes_4 = v660;
                                if ( !v660 )
                                  goto LABEL_756;
                                v661 = MemoryAlloc(2LL * v660);
                                v655[v1302] = v661;
                                if ( !v661 )
                                {
                                  v644 = v1319;
                                  goto LABEL_762;
                                }
                                v662 = -1;
                                do
                                  ++v662;
                                while ( *(_BYTE *)(v662 + v658) );
                                if ( !((unsigned int (__fastcall *)(__int64, _QWORD, __int64, _QWORD, void *, unsigned int))off_1801140C0[0])(
                                        65001,
                                        0,
                                        v658,
                                        (unsigned int)(v662 + 1),
                                        v661,
                                        dwBytes_4) )
                                {
LABEL_756:
                                  v663 = GetLastError();
                                  v588 = v663;
                                  if ( v663 > 0 )
                                    v588 = (unsigned __int16)v663 | 0x80070000;
                                  v644 = v1319;
                                  if ( v588 >= 0 )
                                    v588 = -2147467259;
                                  goto LABEL_763;
                                }
                                v656 = v1280;
LABEL_754:
                                LODWORD(v1280) = ++v656;
                                if ( v656 < 3 )
                                  continue;
                                break;
                              }
                              v644 = v1319;
                              v1346 = (int)v1287;
                              v1295 = 0;
                              v1309 = v655;
LABEL_776:
                              v668 = v1328;
                              if ( v1328 && v644 )
                              {
                                do
                                {
                                  *v668++ = 0;
                                  --v644;
                                }
                                while ( v644 );
                              }
                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1295);
                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1328);
                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1297);
                              LODWORD(v123) = 0;
                              if ( v588 < 0 )
                                goto LABEL_883;
                              v1348 = *v655;
                              v1349 = v655[1];
                              v1350 = v655[2];
                              v1341 = 0;
                              LODWORD(v1341) = 16;
                              if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int128 *, _QWORD))off_180114168)(
                                                    66,
                                                    0,
                                                    &v1341,
                                                    0) )
                              {
                                v669 = GetLastError();
                                v588 = v669;
                                if ( v669 > 0 )
                                  v588 = (unsigned __int16)v669 | 0x80070000;
                                v1347 = 0;
                                if ( v588 >= 0 )
                                  v588 = -2147467259;
                                goto LABEL_883;
                              }
                              v670 = v472 & 0xF;
                              v1347 = BYTE4(v1341) & 1;
                              v671 = 42;
                              LODWORD(v1305) = 42;
                              if ( v670 != 1 )
                              {
                                if ( (v472 & 0xF) == 2 )
                                {
                                  LODWORD(v1304) = 15;
                                  v1298 = 11;
                                }
                                else
                                {
                                  if ( (v472 & 0xF) != 3 )
                                  {
                                    v671 = 0;
                                    v1298 = 0;
LABEL_793:
                                    LODWORD(v1304) = v671;
                                    goto LABEL_794;
                                  }
                                  LODWORD(v1304) = 225;
                                  v1298 = 225;
                                }
LABEL_794:
                                memset_0(v1427, 0, 0xDCu);
                                v1428 = 220;
                                if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _BYTE *))off_1801140E0[0])(
                                       0,
                                       0xFFFFFFFFLL,
                                       v1427) )
                                {
                                  v672 = v1429;
                                  v673 = v1430;
                                  LODWORD(v1280) = v1431;
                                  if ( v1429 < 0x60u )
                                    v672 = 96;
                                }
                                else
                                {
                                  v673 = 0;
                                  LODWORD(v1280) = 0;
                                  v672 = 96;
                                }
                                v1284 = v672;
                                v674 = pcchLength;
                                if ( v670 == 1 )
                                  v674 = (size_t)Src;
                                v1302 = v674;
                                memset_0(v1418, 0, 0x5Cu);
                                v1297 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140F8[0])(0, 0, 1027);
                                if ( !v1297 )
                                  goto LABEL_849;
                                v675 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140B8[0])(
                                         (unsigned int)v1304,
                                         v672,
                                         72);
                                v1418[4] = 400;
                                v1418[0] = -v675;
                                v1419 = 5;
                                StringCchCopyW(v1420, 0x20u, (const unsigned __int16 *)v1302);
                                v676 = ((__int64 (__fastcall *)(_DWORD *))off_180114020[0])(v1418);
                                if ( v676 )
                                {
                                  v588 = 0;
                                  v1351 = v676;
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
                                ((void (__fastcall *)(_QWORD, SIZE_T))off_180114160[0])(0, v1297);
                                if ( v588 < 0 )
                                  goto LABEL_882;
                                v678 = (const unsigned __int16 *)pcchLength;
                                if ( v670 == 1 )
                                  v678 = (const unsigned __int16 *)Src;
                                memset_0(v1421, 0, 0x5Cu);
                                v1302 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140F8[0])(0, 0, 1027);
                                if ( !v1302 )
                                  goto LABEL_849;
                                v679 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140B8[0])(
                                         v1298,
                                         v1284,
                                         72);
                                v1421[4] = 400;
                                v1421[0] = -v679;
                                v1422 = 5;
                                StringCchCopyW(v1423, 0x20u, v678);
                                v680 = ((__int64 (__fastcall *)(_DWORD *))off_180114020[0])(v1421);
                                if ( v680 )
                                {
                                  v588 = 0;
                                  v1352 = v680;
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
                                ((void (__fastcall *)(_QWORD, size_t))off_180114160[0])(0, v1302);
                                if ( v588 < 0 )
                                  goto LABEL_882;
                                if ( v670 != 1 )
                                {
                                  if ( v670 == 2 )
                                  {
                                    v673 /= 4;
                                    goto LABEL_826;
                                  }
                                  if ( v670 != 3 )
                                  {
                                    v673 = 0;
LABEL_826:
                                    v682 = 0;
                                    goto LABEL_828;
                                  }
                                }
                                v682 = v1280;
LABEL_828:
                                *((_QWORD *)&v1318 + 1) = __PAIR64__(v682, v673);
                                if ( v670 == 1 )
                                {
                                  v683 = 150;
                                  LODWORD(v1304) = 32;
                                }
                                else
                                {
                                  v683 = 0;
                                  if ( (unsigned int)(v670 - 2) < 2 )
                                  {
                                    LODWORD(v1305) = 0;
                                    LODWORD(v1304) = 0;
                                  }
                                  else
                                  {
                                    LODWORD(v1304) = 0;
                                    LODWORD(v1305) = 0;
                                  }
                                }
                                LODWORD(v1296) = v683;
                                v684 = v673 - v683;
                                v685 = v1348;
                                v1361 = v684;
                                v1357 = v684;
                                v1302 = ((__int64 (__fastcall *)(size_t, size_t, _QWORD))off_180114078[0])(
                                          v1278,
                                          v1351,
                                          0);
                                dwBytes_4 = ((__int64 (__fastcall *)(size_t, void *, __int64, int *, int, _QWORD))off_1801140D8[0])(
                                              v1278,
                                              v685,
                                              0xFFFFFFFFLL,
                                              &v1355,
                                              3152,
                                              0);
                                v588 = dwBytes_4 != 0 ? 0 : 0x80004005;
                                if ( v1302 )
                                  ((void (__fastcall *)(size_t, size_t))off_180114078[0])(v1278, v1302);
                                if ( dwBytes_4 )
                                {
                                  v686 = v1349;
                                  v1302 = ((__int64 (__fastcall *)(size_t, size_t))off_180114078[0])(v1278, v1352);
                                  dwBytes_4 = ((__int64 (__fastcall *)(size_t, void *, __int64, int *, int, _QWORD))off_1801140D8[0])(
                                                v1278,
                                                v686,
                                                0xFFFFFFFFLL,
                                                &v1359,
                                                3152,
                                                0);
                                  v588 = dwBytes_4 != 0 ? 0 : 0x80004005;
                                  if ( v1302 )
                                    ((void (__fastcall *)(size_t, size_t))off_180114078[0])(v1278, v1302);
                                  if ( dwBytes_4 )
                                  {
                                    if ( v670 == 2 || v670 == 3 )
                                    {
                                      v684 = v1361;
                                      if ( v1357 > v1361 )
                                        v684 = v1357;
                                    }
                                    v588 = 0;
                                    if ( v1346 )
                                    {
                                      ((void (__fastcall *)(int *, _QWORD, _QWORD))off_180114150)(
                                        &v1355,
                                        v684 - v1357,
                                        (unsigned int)v1305);
                                      v687 = v684 - v1361;
                                    }
                                    else
                                    {
                                      ((void (__fastcall *)(int *, _QWORD, _QWORD))off_180114150)(
                                        &v1355,
                                        (unsigned int)v1296,
                                        (unsigned int)v1305);
                                      v687 = (unsigned int)v1296;
                                    }
                                    ((void (__fastcall *)(int *, __int64, _QWORD))off_180114150)(
                                      &v1359,
                                      v687,
                                      (unsigned int)(v1358 + v1304));
                                    if ( (unsigned int)(v670 - 2) <= 1 )
                                    {
                                      *((_QWORD *)&v1318 + 1) = __PAIR64__(v1362, v684);
                                      v1354 = -5723992;
                                      goto LABEL_869;
                                    }
                                    if ( v670 != 1 )
                                      goto LABEL_869;
                                    v1354 = 0xFFFFFF;
                                    memset_0(v1424, 0, 0x5Cu);
                                    v1302 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140F8[0])(
                                              0,
                                              0,
                                              1027);
                                    if ( !v1302 )
                                    {
LABEL_849:
                                      v688 = GetLastError();
                                      LODWORD(v123) = 0;
                                      v588 = v688;
                                      if ( v688 > 0 )
                                        v588 = (unsigned __int16)v688 | 0x80070000;
                                      if ( v588 >= 0 )
                                        v588 = -2147467259;
                                      goto LABEL_883;
                                    }
                                    v689 = ((__int64 (__fastcall *)(__int64, _QWORD))off_1801140B8[0])(11, v1284);
                                    v1424[4] = 400;
                                    v1424[0] = -v689;
                                    v1425 = 5;
                                    StringCchCopyW(v1426, 0x20u, (const unsigned __int16 *)Size);
                                    v690 = ((__int64 (__fastcall *)(_DWORD *))off_180114020[0])(v1424);
                                    if ( v690 )
                                    {
                                      v1353 = v690;
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
                                    ((void (__fastcall *)(_QWORD, size_t))off_180114160[0])(0, v1302);
                                    if ( v588 >= 0 )
                                    {
                                      v692 = v1350;
                                      v1365 = v684;
                                      v693 = ((__int64 (__fastcall *)(size_t, __int64))off_180114078[0])(v1278, v1353);
                                      dwBytes_4 = ((__int64 (__fastcall *)(size_t, void *, __int64, unsigned int *, int, _QWORD))off_1801140D8[0])(
                                                    v1278,
                                                    v692,
                                                    0xFFFFFFFFLL,
                                                    &v1363,
                                                    1120,
                                                    0);
                                      v588 = dwBytes_4 == 0 ? 0x80004005 : 0;
                                      if ( v693 )
                                        ((void (__fastcall *)(size_t, __int64))off_180114078[0])(v1278, v693);
                                      if ( dwBytes_4 )
                                      {
                                        v694 = v1284;
                                        v695 = v1365 + 24;
                                        v1366 = 32;
                                        if ( (int)(v1365 + 24) < 90 )
                                          v695 = 90;
                                        v1365 = v695;
                                        v1363 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140B8[0])(
                                                  v1363,
                                                  v1284,
                                                  96);
                                        v1364 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140B8[0])(
                                                  v1364,
                                                  v694,
                                                  96);
                                        v1365 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140B8[0])(
                                                  v1365,
                                                  v694,
                                                  96);
                                        v1366 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1801140B8[0])(
                                                  v1366,
                                                  v694,
                                                  96);
                                        off_180114150();
LABEL_869:
                                        v696 = HIDWORD(v1318);
                                        v697 = DWORD2(v1318);
                                        v698 = v670 - 1;
                                        if ( v698 )
                                        {
                                          v699 = v698 - 1;
                                          if ( v699 )
                                          {
                                            if ( v699 == 1 )
                                            {
                                              v1416 = 0;
                                              v1414 = 0;
                                              v1415 = 0;
                                              v700 = ((__int64 (__fastcall *)(_QWORD, __int64))off_180114148[0])(0, 1);
                                              LODWORD(v1414) = 40;
                                              LODWORD(v123) = 0;
                                              if ( ((unsigned int (__fastcall *)(__int64, __int128 *))off_180114108[0])(
                                                     v700,
                                                     &v1414) )
                                              {
                                                ((void (__fastcall *)(_QWORD, char *))off_180114140[0])(
                                                  0,
                                                  (char *)&v1415 + 4);
                                                ((void (__fastcall *)(_QWORD, char *))off_180114140[0])(
                                                  0,
                                                  (char *)&v1415 + 12);
                                                LODWORD(v1318) = 50 * (HIDWORD(v1415) - v697) / 100;
                                                DWORD1(v1318) = 50 * ((int)v1416 - v696) / 100;
                                              }
                                              goto LABEL_880;
                                            }
                                          }
                                          else
                                          {
                                            v701 = v1346;
                                            v1405 = 0;
                                            v1403 = 0;
                                            v1404 = 0;
                                            v702 = ((__int64 (__fastcall *)(_QWORD, __int64))off_180114148[0])(0, 1);
                                            LODWORD(v1403) = 40;
                                            if ( ((unsigned int (__fastcall *)(__int64, __int128 *))off_180114108[0])(
                                                   v702,
                                                   &v1403) )
                                            {
                                              ((void (__fastcall *)(_QWORD, char *))off_180114140[0])(
                                                0,
                                                (char *)&v1404 + 4);
                                              ((void (__fastcall *)(_QWORD, char *))off_180114140[0])(
                                                0,
                                                (char *)&v1404 + 12);
                                              if ( v701 )
                                                v703 = DWORD1(v1404) + 5 * HIDWORD(v1404) / 100;
                                              else
                                                v703 = 95 * (HIDWORD(v1404) - v697) / 100;
                                              LODWORD(v1318) = v703;
                                              DWORD1(v1318) = 95 * ((int)v1405 - v696) / 100;
                                            }
                                          }
                                          LODWORD(v123) = 0;
                                        }
                                        else
                                        {
                                          LODWORD(v123) = 0;
                                          *(_QWORD *)&v1318 = 0;
                                        }
LABEL_880:
                                        v588 = 0;
LABEL_883:
                                        ((void (__fastcall *)(_QWORD, size_t))off_180114160[0])(0, v1278);
                                        goto LABEL_884;
                                      }
                                    }
                                  }
                                }
LABEL_882:
                                LODWORD(v123) = 0;
                                goto LABEL_883;
                              }
                              v1298 = 11;
                              goto LABEL_793;
                            }
LABEL_762:
                            v588 = -2147024882;
LABEL_763:
                            if ( v655 )
                            {
                              for ( i7 = 0; i7 != 3; ++i7 )
                              {
                                v665 = v655[i7];
                                if ( v665 )
                                {
                                  v666 = -1;
                                  do
                                    ++v666;
                                  while ( *(_WORD *)&v665[2 * v666] );
                                  for ( i8 = 2 * v666 + 2; i8; --i8 )
                                    *v665++ = 0;
                                  MemoryFree(v655[i7]);
                                }
                              }
                              v644 = v1319;
                            }
LABEL_775:
                            v655 = (void **)v1291;
                            goto LABEL_776;
                          }
                          MemoryFree(v605);
                          v588 = -1073425151;
                        }
                        else
                        {
                          v588 = -2147024882;
                        }
                      }
                      v644 = 0;
                      goto LABEL_775;
                    }
                    v589 = pcchLength;
                    LODWORD(v123) = pcchLength;
                  }
                  else
                  {
                    v589 = 0;
                  }
                  v588 = -2147024882;
                  goto LABEL_709;
                }
                v530 = dword_1801173E0;
LABEL_679:
                dword_1801173E0 = v530 + 1;
                goto LABEL_680;
              }
              v473 = dword_1801173E0;
LABEL_633:
              dword_1801173E0 = v473 + 1;
              goto LABEL_634;
            }
            v965 = dwBytes_4;
LABEL_1580:
            while ( _InterlockedCompareExchange(&dword_1801173E4, 1, 0) )
              ;
            v1272 = dword_1801173E0;
            if ( dword_1801173E0 > 0 )
            {
              --dword_1801173E0;
              if ( v1272 == 1 )
              {
                for ( i9 = 0; i9 != 4; ++i9 )
                {
                  v1274 = (HMODULE)qword_180116EF0[3 * i9];
                  if ( v1274 )
                    FreeLibrary(v1274);
                }
                memset_0(qword_180116EF0, 0, 0x60u);
                memcpy_0(off_180114000, off_1800E1E60, 0x170u);
              }
            }
            _InterlockedExchange(&dword_1801173E4, 0);
            SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1312);
            if ( v82 >= 0 )
            {
              if ( v965 == 4 )
              {
                v2 = 0;
                *v1339 = *v1329;
                goto LABEL_1600;
              }
            }
            else
            {
              switch ( v82 )
              {
                case -805306316:
                  v2 = -1073418222;
                  goto LABEL_1600;
                case -805306139:
                case -1073425151:
                  v2 = -1073418201;
                  goto LABEL_1600;
                case -805306306:
                  v2 = -1073418200;
                  goto LABEL_1600;
              }
              v2 = v82;
              if ( v82 != -2147024774 )
                goto LABEL_1600;
            }
            v2 = -1073418210;
            goto LABEL_1600;
          }
          *v80 = xmmword_180115F40;
          v80[1] = xmmword_180115F50;
          v80[2] = xmmword_180115F60;
          v80[3] = xmmword_180115F70;
          v80[4] = xmmword_180115F80;
          v80[5] = xmmword_180115F90;
          v80[6] = xmmword_180115FA0;
          v80[7] = xmmword_180115FB0;
          v80[8] = xmmword_180115FC0;
          v80[9] = xmmword_180115FD0;
          v84 = GetProcessHeap();
          v83 = HeapAlloc(v84, 8u, 8u);
          if ( !v83 )
          {
            LODWORD(v1279) = -1073741801;
            v83 = 0;
            goto LABEL_138;
          }
          *v83 = qword_180115E80;
          v1297 = __rdtsc();
          dwBytes = 0;
          LODWORD(v1280) = 0;
          LODWORD(v1279) = RtlUIntAdd(4, 4, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_138;
          v85 = RtlUIntAdd(0, (unsigned int)v1280, &dwBytes);
          v82 = v85 | 0x10000000;
          LODWORD(v1279) = v85 | 0x10000000;
          if ( v85 < 0 )
            goto LABEL_138;
          LODWORD(v1280) = v86;
          LODWORD(v1279) = RtlUIntAdd(v87, 160, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_138;
          v88 = RtlUIntAdd(dwBytes, (unsigned int)v1280, &dwBytes);
          v82 = v90 | v88;
          LODWORD(v1279) = v90 | v88;
          if ( (v90 | v88) < 0 )
            goto LABEL_138;
          LODWORD(v1280) = 0;
          LODWORD(v1279) = RtlUIntAdd(v89, 8, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_138;
          v91 = RtlUIntAdd(dwBytes, (unsigned int)v1280, &dwBytes);
          v82 = v93 | v91;
          LODWORD(v1279) = v93 | v91;
          if ( (v93 | v91) < 0 )
            goto LABEL_138;
          LODWORD(v1280) = 0;
          LODWORD(v1279) = RtlUIntAdd(v92, 8, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_138;
          v94 = RtlUIntAdd(dwBytes, (unsigned int)v1280, &dwBytes);
          v82 = v96 | v94;
          LODWORD(v1279) = v96 | v94;
          if ( (v96 | v94) < 0 )
            goto LABEL_138;
          pcchLength = 0;
          if ( StringCchLengthW(psz, v95, &pcchLength) < 0 )
          {
            v82 = -1073741762;
LABEL_338:
            LODWORD(v1279) = v82;
            goto LABEL_138;
          }
          LODWORD(v1280) = v97;
          LODWORD(v1279) = RtlUIntAdd(4, (unsigned int)(2 * (pcchLength + 1)), &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_138;
          v98 = RtlUIntAdd(dwBytes, (unsigned int)v1280, &dwBytes);
          v82 = v98 | 0x10000000;
          LODWORD(v1279) = v98 | 0x10000000;
          if ( v98 < 0 )
            goto LABEL_138;
          LODWORD(v1280) = v100;
          LODWORD(v1279) = RtlUIntAdd(v99, v99, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_138;
          v101 = RtlUIntAdd(dwBytes, (unsigned int)v1280, &dwBytes);
          v82 = v104 | v101;
          LODWORD(v1279) = v104 | v101;
          if ( (v104 | v101) < 0 )
            goto LABEL_138;
          LODWORD(v1280) = v103;
          LODWORD(v1279) = RtlUIntAdd(v102, v102, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_138;
          v105 = RtlUIntAdd(dwBytes, (unsigned int)v1280, &dwBytes);
          v82 = v106 | v105;
          LODWORD(v1279) = v106 | v105;
          if ( (v106 | v105) < 0 )
            goto LABEL_138;
          HIDWORD(lpMem[0]) = dwBytes;
          v107 = dwBytes;
          v108 = GetProcessHeap();
          v109 = HeapAlloc(v108, 8u, v107);
          if ( !v109 )
          {
            v82 = -1073741801;
            goto LABEL_338;
          }
          LODWORD(v1308) = 0;
          v1283 = 0;
          lpMem[1] = v109;
          LODWORD(lpMem[0]) = 0;
          v1307 = 0;
          v1278 = (size_t)v109;
          LODWORD(v1287) = 8;
          LODWORD(v1279) = RtlULongLongAdd(v109, 4, &v1308);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_134;
          if ( v109 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
          {
LABEL_129:
            v82 = -1073741789;
LABEL_133:
            LODWORD(v1279) = v82;
            goto LABEL_134;
          }
          v112 = v1308;
          *v109 = 4;
          v113 = (unsigned int)v1287;
          *v112 = v110;
          v114 = LODWORD(lpMem[0]) + 1;
          LODWORD(v1308) = 0;
          ++LODWORD(lpMem[0]);
          v1307 = 0;
          if ( v81 )
          {
            if ( !v111 )
              goto LABEL_132;
          }
          else if ( v111 )
          {
LABEL_132:
            v82 = -1073741811;
            goto LABEL_133;
          }
          v124 = (unsigned int *)lpMem[1];
          if ( lpMem[1] )
          {
            v1278 = (size_t)lpMem[1];
            LODWORD(v1287) = 0;
            if ( v114 )
            {
              do
              {
                v125 = *v124;
                LODWORD(v1280) = 0;
                LODWORD(v1279) = RtlUIntAdd(4, v125, &v1280);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                LODWORD(v1279) = RtlULongLongAdd(v126, (unsigned int)v1280, &v1278);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                v124 = (unsigned int *)v1278;
                LODWORD(v1287) = (_DWORD)v1287 + 1;
              }
              while ( (unsigned int)v1287 < v127 );
            }
            LODWORD(v1279) = RtlULongLongAdd(v124, 4, &v1308);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            if ( (char *)v128 + v129 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
              goto LABEL_129;
            *v128 = v129;
            if ( v81 )
              memcpy_0(v1308, v81, v129);
          }
          else
          {
            LODWORD(v1280) = 0;
            LODWORD(v1279) = RtlUIntAdd(4, v111, &v1280);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            LODWORD(v1279) = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1280, (char *)lpMem + 4);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
          }
          LODWORD(v1308) = 0;
          v130 = LODWORD(lpMem[0]) + 1;
          v1307 = 0;
          ++LODWORD(lpMem[0]);
          if ( !v113 )
            goto LABEL_132;
          v131 = (unsigned int *)lpMem[1];
          if ( lpMem[1] )
          {
            v1278 = (size_t)lpMem[1];
            if ( v130 )
            {
              do
              {
                v134 = *v131;
                LODWORD(v1280) = 0;
                LODWORD(v1279) = RtlUIntAdd(4, v134, &v1280);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                LODWORD(v1279) = RtlULongLongAdd(v135, (unsigned int)v1280, &v1278);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                v131 = (unsigned int *)v1278;
              }
              while ( v137 + 1 < v136 );
            }
            LODWORD(v1279) = RtlULongLongAdd(v131, 4, &v1308);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            if ( (char *)v138 + v113 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
              goto LABEL_129;
            *v138 = v113;
            memcpy_0(v1308, v83, v113);
            v133 = LODWORD(lpMem[0]) + 1;
          }
          else
          {
            LODWORD(v1280) = 0;
            LODWORD(v1279) = RtlUIntAdd(4, v113, &v1280);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            LODWORD(v1279) = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1280, (char *)lpMem + 4);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            v133 = v132 + LODWORD(lpMem[0]);
          }
          v139 = (unsigned int *)lpMem[1];
          LODWORD(v1308) = 0;
          v1307 = 0;
          LODWORD(lpMem[0]) = v133;
          if ( lpMem[1] )
          {
            v1278 = (size_t)lpMem[1];
            if ( v133 )
            {
              do
              {
                v141 = *v139;
                LODWORD(v1280) = 0;
                LODWORD(v1279) = RtlUIntAdd(4, v141, &v1280);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                LODWORD(v1279) = RtlULongLongAdd(v142, (unsigned int)v1280, &v1278);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                v139 = (unsigned int *)v1278;
              }
              while ( v144 + 1 < v143 );
            }
            LODWORD(v1279) = RtlULongLongAdd(v139, 4, &v1308);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            if ( v145 + 3 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
              goto LABEL_129;
            v146 = (SIZE_T *)v1308;
            v147 = v1297;
            *v145 = 8;
            *v146 = v147;
          }
          else
          {
            LODWORD(v1280) = 0;
            LODWORD(v1279) = RtlUIntAdd(4, 8, &v1280);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            LODWORD(v1279) = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1280, (char *)lpMem + 4);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
          }
          v1278 = 0;
          ++LODWORD(lpMem[0]);
          if ( StringCchLengthW(psz, v140, &v1278) < 0 )
          {
            v82 = -1073741762;
            goto LABEL_133;
          }
          LODWORD(v1279) = RtlULongLongAdd(v1278, 1, &v1278);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
          {
LABEL_134:
            if ( v82 >= 0 )
            {
LABEL_135:
              v115 = v1283;
              if ( v1283 )
              {
                v82 = v1283;
LABEL_137:
                LODWORD(v1279) = v115;
              }
            }
            goto LABEL_138;
          }
          LODWORD(v1308) = 0;
          v1307 = 0;
          if ( !(2 * (_DWORD)v1278) )
            goto LABEL_132;
          v149 = (unsigned int *)lpMem[1];
          if ( lpMem[1] )
          {
            v1278 = (size_t)lpMem[1];
            v150 = 0;
            if ( v148 )
            {
              do
              {
                v151 = *v149;
                LODWORD(v1280) = 0;
                LODWORD(v1279) = RtlUIntAdd(4, v151, &v1280);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                LODWORD(v1279) = RtlULongLongAdd(v152, (unsigned int)v1280, &v1278);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                v149 = (unsigned int *)v1278;
              }
              while ( ++v150 < v153 );
            }
            LODWORD(v1279) = RtlULongLongAdd(v149, 4, &v1308);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            if ( (char *)v154 + v155 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
              goto LABEL_129;
            v156 = psz;
            v157 = v1308;
            *v154 = v155;
            memcpy_0(v157, v156, (unsigned int)v155);
          }
          else
          {
            LODWORD(v1280) = 0;
            LODWORD(v1279) = RtlUIntAdd(4, (unsigned int)(2 * v1278), &v1280);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            LODWORD(v1279) = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1280, (char *)lpMem + 4);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
          }
          v158 = (unsigned int *)lpMem[1];
          v159 = LODWORD(lpMem[0]) + 1;
          LODWORD(v1308) = 0;
          ++LODWORD(lpMem[0]);
          v1307 = 0;
          if ( lpMem[1] )
          {
            v1278 = (size_t)lpMem[1];
            if ( v159 )
            {
              do
              {
                v161 = *v158;
                LODWORD(v1280) = 0;
                LODWORD(v1279) = RtlUIntAdd(4, v161, &v1280);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                LODWORD(v1279) = RtlULongLongAdd(v162, (unsigned int)v1280, &v1278);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                v158 = (unsigned int *)v1278;
              }
              while ( v164 + 1 < v163 );
            }
            LODWORD(v1279) = RtlULongLongAdd(v158, 4, &v1308);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            if ( v165 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
              goto LABEL_129;
            v166 = v1308;
            v160 = 1;
            *v165 = 4;
            *v166 = v77;
          }
          else
          {
            LODWORD(v1280) = 0;
            LODWORD(v1279) = RtlUIntAdd(4, 4, &v1280);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            LODWORD(v1279) = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1280, (char *)lpMem + 4);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
          }
          v167 = (unsigned int *)lpMem[1];
          v168 = v160 + LODWORD(lpMem[0]);
          LODWORD(v1308) = 0;
          LODWORD(lpMem[0]) += v160;
          v1307 = 0;
          if ( lpMem[1] )
          {
            v1278 = (size_t)lpMem[1];
            if ( v168 )
            {
              do
              {
                v170 = *v167;
                LODWORD(v1280) = 0;
                LODWORD(v1279) = RtlUIntAdd(4, v170, &v1280);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                LODWORD(v1279) = RtlULongLongAdd(v171, (unsigned int)v1280, &v1278);
                v82 = v1279;
                if ( (v1279 & 0x80000000) != 0LL )
                  goto LABEL_134;
                v167 = (unsigned int *)v1278;
              }
              while ( v173 + 1 < v172 );
            }
            LODWORD(v1279) = RtlULongLongAdd(v167, 4, &v1308);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            if ( v174 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
              goto LABEL_129;
            v175 = v1308;
            *v174 = 4;
            *v175 = 4;
            ++LODWORD(lpMem[0]);
          }
          else
          {
            LODWORD(v1280) = 0;
            LODWORD(v1279) = RtlUIntAdd(4, 4, &v1280);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            LODWORD(v1279) = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1280, (char *)lpMem + 4);
            v82 = v1279;
            if ( (v1279 & 0x80000000) != 0LL )
              goto LABEL_134;
            LODWORD(lpMem[0]) += v169;
          }
          LODWORD(v1280) = 0;
          v82 = RtlUIntAdd(4, 4, &v1280);
          LODWORD(v1279) = v82;
          if ( v82 < 0 )
            goto LABEL_138;
          v1284 = v1280;
          LODWORD(v1280) = 0;
          LODWORD(v1279) = RtlUIntAdd(v176, 8, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_134;
          v82 = RtlUIntAdd(v177, (unsigned int)v1280, &v1284);
          LODWORD(v1279) = v82;
          if ( v82 < 0 )
            goto LABEL_138;
          LODWORD(v1280) = 0;
          LODWORD(v1279) = RtlUIntAdd(4, 4, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_134;
          v82 = RtlUIntAdd(v1284, (unsigned int)v1280, &v1284);
          LODWORD(v1279) = v82;
          if ( v82 < 0 )
            goto LABEL_138;
          LODWORD(v1280) = 0;
          LODWORD(v1279) = RtlUIntAdd(4, 4, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_134;
          v82 = RtlUIntAdd(v1284, (unsigned int)v1280, &v1284);
          LODWORD(v1279) = v82;
          if ( v82 < 0 )
            goto LABEL_138;
          LODWORD(v1280) = 0;
          LODWORD(v1279) = RtlUIntAdd(4, 4, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_134;
          v82 = RtlUIntAdd(v1284, (unsigned int)v1280, &v1284);
          LODWORD(v1279) = v82;
          if ( v82 < 0 )
            goto LABEL_138;
          LODWORD(v1280) = 0;
          LODWORD(v1279) = RtlUIntAdd(4, 4, &v1280);
          v82 = v1279;
          if ( (v1279 & 0x80000000) != 0LL )
            goto LABEL_134;
          v82 = RtlUIntAdd(v1284, (unsigned int)v1280, &v1284);
          LODWORD(v1279) = v82;
          if ( v82 < 0 )
            goto LABEL_138;
          v1298 = 0;
          dwBytes = v1284;
          v1285 = 0;
          pcchLength = __rdtsc();
          LODWORD(v1282) = 0;
          v1313 = 8;
          v179 = RtlUIntAdd(8, HIDWORD(lpMem[0]), &v1313);
          if ( v179 < 0 )
          {
            psz = (STRSAFE_PCNZWCH)v83;
            v1293 = (SIZE_T)v81;
          }
          else
          {
            v180 = (v1313 + 7) & 0xFFFFFFF8;
            if ( v180 < v1313 )
            {
              v82 = -805306219;
              goto LABEL_338;
            }
            v1313 = (v1313 + 7) & 0xFFFFFFF8;
            v181 = v180;
            v182 = GetProcessHeap();
            v183 = HeapAlloc(v182, 8u, v181);
            if ( !v183 )
            {
              v82 = -805306345;
              LODWORD(v1279) = -805306345;
              goto LABEL_335;
            }
            v1293 = (SIZE_T)v81;
            psz = (STRSAFE_PCNZWCH)v83;
            v1278 = (size_t)v183;
            *v183 = lpMem[0];
            v179 = RtlULongLongAdd(v183, 4, &v1278);
            if ( v179 < 0
              || (v186 = v1278,
                  *(_DWORD *)v1278 = HIDWORD(lpMem[0]),
                  v179 = RtlULongLongAdd(v186, v185, &v1278),
                  v179 < 0) )
            {
              v1293 = (SIZE_T)v81;
              psz = (STRSAFE_PCNZWCH)v83;
              dwBytes = v184;
              v187 = GetProcessHeap();
              HeapFree(v187, 0, v183);
              v178 = v1282;
            }
            else
            {
              *(_QWORD *)((char *)v183 + v1313 - 8) = pcchLength;
              memcpy_0((void *)v1278, lpMem[1], HIDWORD(lpMem[0]));
              v178 = v1313;
              v1285 = v183;
            }
          }
          v82 = v179 | 0x10000000;
          pcchLength = 0;
          LODWORD(v1279) = v82;
          v188 = 0;
          v189 = 0;
          v1292 = 0;
          v1294 = 0;
          v1295 = 0;
          if ( v82 < 0 )
            goto LABEL_309;
          v190 = (unsigned __int8 *)v1285;
          if ( !v1285 )
          {
            v77 = (int)v1296;
            v82 = -805306355;
            LODWORD(v1279) = -805306355;
            goto LABEL_138;
          }
          v1309 = (void *)v178;
          if ( !v178 || (Size = v178 + 8LL, v191 = MemoryAlloc(Size), Src = v191, v192 = 0, !v191) )
          {
            v82 = -805306367;
            LODWORD(v1279) = -805306367;
            goto LABEL_311;
          }
          v193 = (unsigned __int64)v1309;
          v194 = 0;
          v1305 = 0;
          v195 = 0;
          v1281 = 0;
          if ( v1309 )
          {
            do
              v192 ^= v190[v195++];
            while ( v195 < (unsigned __int64)v1309 );
            v1281 = v192;
          }
          v1279 = (SIZE_T)v191;
          v196 = v190;
          v1287 = (void *)0xC81ECB17B1B54A58LL;
          v1280 = (SIZE_T)v190;
          v197 = (unsigned __int8)v1309 & 7;
          if ( ((unsigned __int8)v1309 & 7) != 0 )
          {
            v1301 = 0;
            v1284 = 0;
            v198 = 0;
            v199 = 0;
            do
            {
              v200 = *v196++;
              LODWORD(v1280) = 8 * v194;
              if ( v194 >= 4 )
                v198 |= v200 << (56 - v1280);
              else
                v199 |= v200 << (24 - v1280);
              ++v194;
            }
            while ( (int)v194 < v197 );
            v193 = (unsigned __int64)v1309;
            v1284 = v199;
            v1301 = v198;
            v1280 = (SIZE_T)v196;
            v1285 = v190;
            psz = (STRSAFE_PCNZWCH)v83;
            v1293 = (SIZE_T)v81;
            LODWORD(v1304) = 0;
            v194 = v199 ^ 0xB17A307A;
            v201 = v198 ^ 0x42F6B18D;
            v202 = v199 ^ 0xB17A307A;
            v203 = v201;
            if ( ((unsigned __int8)v1309 & 7) != 0 )
            {
              v204 = (_BYTE *)v1279;
              do
              {
                v1282 = (SIZE_T)(v204 + 1);
                if ( (unsigned int)v1304 >= 4 )
                {
                  v203 = __ROR4__(v203, 24);
                  v205 = v203;
                }
                else
                {
                  v202 = __ROR4__(v202, 24);
                  v205 = v202;
                }
                LODWORD(v1304) = v1304 + 1;
                *v204 = v205;
                v204 = (_BYTE *)v1282;
              }
              while ( (int)v1304 < v197 );
              v1279 = v1282;
            }
            if ( (unsigned int)v197 <= 4 )
            {
              v206 = 0;
              if ( (unsigned int)v197 < 4 )
                v194 = v194 >> (8 * (4 - v197)) << (8 * (4 - v197));
            }
            else
            {
              v206 = v201 >> (8 * (8 - v197)) << (8 * (8 - v197));
            }
            v196 = (unsigned __int8 *)v1280;
          }
          else
          {
            v206 = -1;
            v1284 = 0;
            v1301 = 0;
          }
          if ( v193 >> 3 )
          {
            v207 = WORD2(v1287);
            v208 = v193 >> 3;
            v209 = (_BYTE *)v1279;
            v210 = v1301;
            v1316 = 19032;
            LODWORD(v1290) = WORD1(v1287);
            LODWORD(v1282) = HIDWORD(v1287) ^ 0xB1B54A58;
            v211 = v1284;
            v212 = HIDWORD(v1287) ^ 0xB1B54A58;
            v1304 = 0;
            do
            {
              v213 = v196[3] | ((v196[2] | ((v196[1] | (*v196 << 8)) << 8)) << 8);
              v214 = *(unsigned __int8 *)(v1280 + 7)
                   | ((*(unsigned __int8 *)(v1280 + 6) | ((*(unsigned __int8 *)(v1280 + 5) | (v196[4] << 8)) << 8)) << 8);
              v1280 += 8LL;
              v215 = v206 ^ v214;
              v216 = v194 ^ v213 ^ ((v206 ^ v214) - v1316);
              v217 = v216 ^ HIDWORD(v1287);
              v218 = v215 ^ (__ROR4__(v216 ^ HIDWORD(v1287), 7) + WORD1(v1287) * __ROR4__(v216, 15));
              v219 = v217 ^ (v207 * __ROR4__(v218 - 1313519016, 9) - __ROR4__(v218, 10));
              v220 = v218 ^ (__ROR4__(v219, 27) + HIWORD(v1287) * __ROR4__(v219 ^ v207, 28));
              v221 = v219 ^ (HIDWORD(v1287) - (v220 ^ 0xB1B54A58));
              v222 = v220 ^ (WORD1(v1287) * (v221 - v1316) - (v221 >> 6));
              v223 = v221 ^ (v1316 * (v207 ^ __ROR4__(v222, 15)));
              v224 = v222 ^ (v207 * (HIWORD(v1287) + __ROR4__(~v223, 3)));
              v225 = v223 ^ (v224 - v1316 - HIDWORD(v1287));
              v226 = v224 ^ ((_DWORD)v1290 * (v225 ^ HIWORD(v1287))) ^ __ROR4__(v225, 10);
              v227 = v225 ^ __ROR4__(v226, 3) ^ (v207 * __ROR4__(v226 ^ v1316, 26));
              v228 = v226 ^ (v1316 * (__ROR4__(v227, 15) - HIWORD(v1287)));
              v229 = v227
                   ^ (v1316 * (v228 ^ HIWORD(v1287)))
                   ^ ((v228 ^ (v228 >> 14)) >> 1)
                   ^ (v1316 * (((v228 - v207) >> 29) | (8 * (v228 - v207))));
              v230 = v228 ^ (WORD1(v1287) * (v229 - v207) - (v229 >> 13));
              v231 = v229 ^ __ROR4__(v230, 11) ^ (v207 * __ROR4__(-1313519016 - v230, 9));
              v232 = v230 ^ (v231 + 1313519016 - HIWORD(v1287));
              v233 = v231 ^ (v1316 * (v232 ^ WORD1(v1287)) - __ROR4__(v232, 7));
              v234 = v232 ^ (WORD1(v1287) * __ROR4__(v233 ^ HIWORD(v1287), 28) - __ROR4__(v233, 16));
              v235 = v233 ^ (__ROR4__(v234, 4) + v207 * __ROR4__(-1313519016 - v234, 10));
              v236 = v234 ^ __ROR4__(v235, 9) ^ (HIWORD(v1287) * __ROR4__(v235 + 1313519016, 4));
              v237 = v235 ^ (v1316 * __ROR4__(HIDWORD(v1287) ^ v236, 24) - __ROR4__(v236, 30));
              v238 = v236 ^ (WORD1(v1287) * __ROR4__(HIDWORD(v1287) - v237, 11) - __ROR4__(v237, 12));
              v239 = v210 ^ v238 ^ v212;
              v210 = v214;
              v196 = (unsigned __int8 *)v1280;
              v240 = v237 ^ (v238 >> 8) ^ (v207 * (v238 ^ WORD1(v1287)));
              v194 = v240 ^ v211;
              v206 = v240 ^ v239;
              v209[3] = v240 ^ v211;
              LOBYTE(v223) = __ROR4__(v240 ^ v211, 8);
              v211 = v213;
              v209[7] = v206;
              v209[2] = v223;
              v209[6] = __ROR4__(v206, 8);
              v209[1] = __ROR4__(v194, 16);
              v209[5] = __ROR4__(v206, 16);
              *v209 = __ROR4__(v194, 24);
              v209[4] = __ROR4__(v206, 24);
              v209 += 8;
              ++v1304;
            }
            while ( v1304 < v208 );
            v189 = (_DWORD *)v1292;
            v192 = v1281;
            v188 = (unsigned int *)v1292;
            v81 = (void *)v1293;
            v83 = psz;
            v190 = (unsigned __int8 *)v1285;
            v193 = (unsigned __int64)v1309;
          }
          *(_QWORD *)((char *)Src + v193) = v192;
          v241 = GetProcessHeap();
          v242 = (wchar_t *)HeapAlloc(v241, 8u, 0x30u);
          psz = v242;
          if ( v242 )
          {
            *(_DWORD *)v242 = Size;
            v244 = GetProcessHeap();
            v245 = HeapAlloc(v244, 8u, (unsigned int)Size);
            if ( !v245 )
              goto LABEL_283;
            v1285 = v190;
            v246 = psz;
            *((_QWORD *)psz + 1) = v245;
            memcpy_0(v245, Src, (unsigned int)Size);
            *((_DWORD *)v246 + 4) = 160;
            v247 = GetProcessHeap();
            v248 = HeapAlloc(v247, 8u, 0xA0u);
            if ( !v248 )
              goto LABEL_283;
            *((_QWORD *)v246 + 3) = v248;
            *v248 = xmmword_180115E90;
            v248[1] = xmmword_180115EA0;
            v248[2] = xmmword_180115EB0;
            v248[3] = xmmword_180115EC0;
            v248[4] = xmmword_180115ED0;
            v248[5] = xmmword_180115EE0;
            v248[6] = xmmword_180115EF0;
            v248[7] = xmmword_180115F00;
            v248[8] = xmmword_180115F10;
            v248[9] = xmmword_180115F20;
            *((_DWORD *)v246 + 8) = 8;
            v249 = GetProcessHeap();
            v250 = HeapAlloc(v249, 8u, 8u);
            if ( v250 )
            {
              *((_QWORD *)v246 + 5) = v250;
              *v250 = qword_180115F30;
              v1305 = (SIZE_T)v246;
              v243 = 0;
              v188 = (unsigned int *)v1305;
              v1305 = 0;
            }
            else
            {
LABEL_283:
              v243 = -1073741801;
              v251 = psz;
              v1302 = *((_QWORD *)psz + 1);
              if ( v1302 )
              {
                v252 = GetProcessHeap();
                HeapFree(v252, 0, (LPVOID)v1302);
                v251 = psz;
                *((_QWORD *)psz + 1) = 0;
              }
              v1302 = *((_QWORD *)v251 + 3);
              if ( v1302 )
              {
                v253 = GetProcessHeap();
                HeapFree(v253, 0, (LPVOID)v1302);
                v251 = psz;
                *((_QWORD *)psz + 3) = 0;
              }
              v1302 = *((_QWORD *)v251 + 5);
              if ( v1302 )
              {
                v254 = GetProcessHeap();
                HeapFree(v254, 0, (LPVOID)v1302);
                *((_QWORD *)psz + 5) = 0;
              }
              v255 = GetProcessHeap();
              HeapFree(v255, 0, (LPVOID)psz);
            }
          }
          else
          {
            v243 = -1073741801;
          }
          v256 = GetProcessHeap();
          HeapFree(v256, 0, Src);
          v257 = v1305;
          if ( v1305 )
          {
            v1302 = *(_QWORD *)(v1305 + 8);
            if ( v1302 )
            {
              v258 = GetProcessHeap();
              HeapFree(v258, 0, (LPVOID)v1302);
              v257 = v1305;
              *(_QWORD *)(v1305 + 8) = 0;
            }
            v1302 = *(_QWORD *)(v257 + 24);
            if ( v1302 )
            {
              v259 = GetProcessHeap();
              HeapFree(v259, 0, (LPVOID)v1302);
              v257 = v1305;
              *(_QWORD *)(v1305 + 24) = 0;
            }
            v1302 = *(_QWORD *)(v257 + 40);
            if ( v1302 )
            {
              v260 = GetProcessHeap();
              HeapFree(v260, 0, (LPVOID)v1302);
              *(_QWORD *)(v1305 + 40) = 0;
            }
            v261 = GetProcessHeap();
            HeapFree(v261, 0, (LPVOID)v1305);
          }
          v82 = v243 | 0x10000000;
          LODWORD(v1279) = v82;
          if ( v82 < 0 )
          {
            v271 = v1285;
LABEL_310:
            if ( !v271 )
            {
LABEL_312:
              if ( v188 )
              {
                v1302 = *((_QWORD *)v188 + 1);
                if ( v1302 )
                {
                  v273 = GetProcessHeap();
                  HeapFree(v273, 0, (LPVOID)v1302);
                  *((_QWORD *)v188 + 1) = 0;
                }
                v1302 = *((_QWORD *)v188 + 3);
                if ( v1302 )
                {
                  v274 = GetProcessHeap();
                  HeapFree(v274, 0, (LPVOID)v1302);
                  *((_QWORD *)v188 + 3) = 0;
                }
                v1302 = *((_QWORD *)v188 + 5);
                if ( v1302 )
                {
                  v275 = GetProcessHeap();
                  HeapFree(v275, 0, (LPVOID)v1302);
                  *((_QWORD *)v188 + 5) = 0;
                }
                v276 = GetProcessHeap();
                HeapFree(v276, 0, v188);
              }
              v277 = (void *)pcchLength;
              if ( pcchLength )
              {
                v278 = GetProcessHeap();
                HeapFree(v278, 0, v277);
              }
              if ( v189 )
              {
                v279 = GetProcessHeap();
                HeapFree(v279, 0, v189);
              }
              v280 = v1294;
              if ( v1294 )
              {
                v281 = (void *)*((_QWORD *)v1294 + 1);
                if ( v281 )
                {
                  v282 = GetProcessHeap();
                  HeapFree(v282, 0, v281);
                  v280[1] = 0;
                }
                v283 = (void *)v280[3];
                if ( v283 )
                {
                  v284 = GetProcessHeap();
                  HeapFree(v284, 0, v283);
                  v280[3] = 0;
                }
                v285 = (void *)v280[5];
                if ( v285 )
                {
                  v286 = GetProcessHeap();
                  HeapFree(v286, 0, v285);
                  v280[5] = 0;
                }
                v287 = GetProcessHeap();
                HeapFree(v287, 0, v280);
              }
              v288 = v1295;
              if ( v1295 )
              {
                v289 = GetProcessHeap();
                HeapFree(v289, 0, v288);
              }
              v77 = (int)v1296;
LABEL_335:
              if ( v82 < 0 )
                goto LABEL_138;
              if ( !v1298 )
                goto LABEL_337;
              if ( !v1291 )
                goto LABEL_132;
              pcchLength = (size_t)v1291;
              LODWORD(v1279) = RtlULongLongAdd(v1291, 4, &pcchLength);
              v1291 = v436;
              v82 = v1279;
              if ( (v1279 & 0x80000000) == 0LL )
              {
                v438 = (int *)pcchLength;
                if ( !*v436 )
                  v438 = 0;
                if ( *v436 != 4 )
                  goto LABEL_129;
                v82 = *v438;
                LODWORD(v1279) = v82;
                if ( v82 == -805306333 )
                {
                  v439 = -2147024774;
                }
                else
                {
                  v439 = v82;
                  if ( v82 != -2147024774 )
                  {
                    v1283 = v82;
                    if ( v82 < 0 )
                      goto LABEL_138;
LABEL_536:
                    v1291 = v436;
                    if ( v437 == 6 )
                    {
                      v1278 = v435;
                      while ( 1 )
                      {
                        LODWORD(v1279) = RtlULongLongAdd(v435, 4, &v1278);
                        v82 = v1279;
                        if ( (v1279 & 0x80000000) != 0LL )
                          goto LABEL_134;
                        LODWORD(v1279) = RtlULongLongAdd(v1278, v440, &v1278);
                        v82 = v1279;
                        if ( (v1279 & 0x80000000) != 0LL )
                          goto LABEL_134;
                        v435 = v1278;
                        if ( v441 != -1 )
                        {
                          LODWORD(v1279) = RtlULongLongAdd(v1278, 4, &v1278);
                          v82 = v1279;
                          if ( (v1279 & 0x80000000) != 0LL )
                            goto LABEL_134;
                          v444 = (size_t *)v1278;
                          if ( !v443 )
                            v444 = 0;
                          if ( v443 != 8 )
                            goto LABEL_129;
                          v1283 = v439;
                          v1291 = v442;
                          if ( !v442 )
                            goto LABEL_132;
                          v445 = *v444;
                          v446 = (size_t)v442;
                          v1278 = (size_t)v442;
                          v1302 = v445;
                          while ( 1 )
                          {
                            LODWORD(v1279) = RtlULongLongAdd(v446, 4, &v1278);
                            v82 = v1279;
                            if ( (v1279 & 0x80000000) != 0LL )
                              goto LABEL_134;
                            LODWORD(v1279) = RtlULongLongAdd(v1278, v447, &v1278);
                            v82 = v1279;
                            if ( (v1279 & 0x80000000) != 0LL )
                              goto LABEL_134;
                            v446 = v1278;
                            if ( (unsigned int)(v448 + 1) >= 2 )
                            {
                              LODWORD(v1279) = RtlULongLongAdd(v1278, 4, &v1278);
                              v82 = v1279;
                              if ( (v1279 & 0x80000000) != 0LL )
                                goto LABEL_134;
                              v451 = (int *)v1278;
                              if ( !v450 )
                                v451 = 0;
                              if ( v450 != 4 )
                                goto LABEL_129;
                              v1283 = v439;
                              v1291 = v449;
                              if ( !v449 )
                                goto LABEL_132;
                              v452 = *v451;
                              v453 = (size_t)v449;
                              v1278 = (size_t)v449;
                              LODWORD(v1290) = v452;
                              v454 = 0;
                              while ( 1 )
                              {
                                LODWORD(v1279) = RtlULongLongAdd(v453, 4, &v1278);
                                v82 = v1279;
                                if ( (v1279 & 0x80000000) != 0LL )
                                  goto LABEL_134;
                                LODWORD(v1279) = RtlULongLongAdd(v1278, v455, &v1278);
                                v82 = v1279;
                                if ( (v1279 & 0x80000000) != 0LL )
                                  goto LABEL_134;
                                v453 = v1278;
                                if ( (unsigned int)(v456 + 1) >= 3 )
                                {
                                  LODWORD(v1279) = RtlULongLongAdd(v1278, 4, &v1278);
                                  v82 = v1279;
                                  if ( (v1279 & 0x80000000) == 0LL )
                                  {
                                    if ( v458 )
                                      v454 = (const void *)v1278;
                                    v459 = (_DWORD *)v457;
                                    v1278 = v457;
                                    while ( 1 )
                                    {
                                      LODWORD(v1282) = *v459;
                                      LODWORD(v1279) = RtlULongLongAdd(v459, 4, &v1278);
                                      v82 = v1279;
                                      if ( (v1279 & 0x80000000) != 0LL )
                                        break;
                                      LODWORD(v1279) = RtlULongLongAdd(v1278, (unsigned int)v1282, &v1278);
                                      v82 = v1279;
                                      if ( (v1279 & 0x80000000) != 0LL )
                                        break;
                                      v459 = (_DWORD *)v1278;
                                      if ( (unsigned int)(v460 + 1) >= 4 )
                                      {
                                        LODWORD(v1279) = RtlULongLongAdd(v1278, 4, &v1278);
                                        v82 = v1279;
                                        if ( (v1279 & 0x80000000) != 0LL )
                                          goto LABEL_134;
                                        v463 = (_DWORD *)v1278;
                                        if ( !v462 )
                                          v463 = 0;
                                        if ( v462 != 4 )
                                          goto LABEL_129;
                                        v1291 = v461;
                                        if ( !v461 )
                                        {
                                          v82 = -1073741811;
                                          goto LABEL_338;
                                        }
                                        v464 = (size_t)v461;
                                        LODWORD(v1282) = *v463;
                                        v1278 = (size_t)v461;
                                        while ( 1 )
                                        {
                                          LODWORD(v1279) = RtlULongLongAdd(v464, 4, &v1278);
                                          v82 = v1279;
                                          if ( (v1279 & 0x80000000) != 0LL )
                                            goto LABEL_138;
                                          LODWORD(v1279) = RtlULongLongAdd(v1278, v465, &v1278);
                                          v82 = v1279;
                                          if ( (v1279 & 0x80000000) != 0LL )
                                            goto LABEL_138;
                                          v464 = v1278;
                                          if ( (unsigned int)(v466 + 1) >= 5 )
                                          {
                                            v115 = RtlULongLongAdd(v1278, 4, &v1278);
                                            LODWORD(v1279) = v115;
                                            v82 = v115;
                                            if ( v115 < 0 )
                                              goto LABEL_137;
                                            v470 = (int *)v1278;
                                            if ( !v467 )
                                              v470 = 0;
                                            if ( v467 != v468 )
                                            {
                                              v82 = -1073741789;
                                              goto LABEL_338;
                                            }
                                            if ( v1297 != v1302 )
                                              goto LABEL_337;
                                            v77 = *v470;
                                            v1317 = (unsigned int)v1290;
                                            if ( (unsigned int)v1282 > v468 || (unsigned int)v469 > v468 )
                                            {
                                              v82 = -2147024774;
                                              goto LABEL_338;
                                            }
                                            memcpy_0(v1331, v454, v469);
                                            goto LABEL_135;
                                          }
                                        }
                                      }
                                    }
                                  }
                                  goto LABEL_134;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
LABEL_337:
                    v82 = -1073425151;
                    goto LABEL_338;
                  }
                }
                v1283 = v439;
                goto LABEL_536;
              }
              goto LABEL_134;
            }
LABEL_311:
            v272 = GetProcessHeap();
            HeapFree(v272, 0, v1285);
            goto LABEL_312;
          }
          v262 = *v188;
          LODWORD(v1280) = 0;
          LODWORD(v1279) = 4;
          v264 = RtlUIntAdd(4, v262, &v1279);
          if ( v264 < 0 )
            goto LABEL_350;
          v264 = RtlUIntAdd((unsigned int)v1279, v263, &v1279);
          if ( v264 < 0
            || (v265 = v188[4], Src = v188 + 4, v264 = RtlUIntAdd((unsigned int)v1279, v265, &v1279), v264 < 0)
            || (v264 = RtlUIntAdd((unsigned int)v1279, v266, &v1279), v264 < 0)
            || (v267 = v188[8], Size = (SIZE_T)(v188 + 8),
                                v264 = RtlUIntAdd((unsigned int)v1279, v267, &v1279),
                                v264 < 0) )
          {
LABEL_350:
            v291 = v1285;
            goto LABEL_351;
          }
          v268 = v1279;
          v269 = GetProcessHeap();
          psz = (STRSAFE_PCNZWCH)HeapAlloc(v269, 8u, v268);
          v270 = psz;
          if ( !psz )
          {
            v82 = -805306345;
LABEL_307:
            LODWORD(v1279) = v82;
LABEL_308:
            v189 = (_DWORD *)v1292;
LABEL_309:
            v271 = v1285;
            goto LABEL_310;
          }
          v290 = *v188;
          v291 = v1285;
          v1282 = (SIZE_T)psz;
          *(_DWORD *)psz = v290;
          v264 = RtlULongLongAdd(v270, 4, &v1282);
          if ( v264 < 0 )
          {
            dwBytes = v293;
            psz = v292;
          }
          else
          {
            memcpy_0((void *)v1282, *((const void **)v188 + 1), *v188);
            v264 = RtlULongLongAdd(v1282, *v188, &v1282);
            if ( v264 >= 0 )
            {
              v294 = v1282;
              *(_DWORD *)v1282 = *(_DWORD *)Src;
              v264 = RtlULongLongAdd(v294, 4, &v1282);
              if ( v264 >= 0 )
              {
                memcpy_0((void *)v1282, *((const void **)v188 + 3), *v295);
                v264 = RtlULongLongAdd(v1282, *(unsigned int *)Src, &v1282);
                if ( v264 >= 0 )
                {
                  v296 = v1282;
                  *(_DWORD *)v1282 = *(_DWORD *)Size;
                  v264 = RtlULongLongAdd(v296, 4, &v1282);
                  if ( v264 >= 0 )
                  {
                    memcpy_0((void *)v1282, *((const void **)v188 + 5), *v297);
                    v264 = RtlULongLongAdd(v1282, *(unsigned int *)Size, &v1282);
                    if ( v264 >= 0 )
                    {
                      pcchLength = (size_t)psz;
                      LODWORD(v1280) = v1279;
LABEL_351:
                      v82 = v264 | 0x10000000;
                      LODWORD(v1279) = v82;
                      if ( v82 < 0 )
                        goto LABEL_308;
                      v1322 = 8;
                      v299 = RtlUIntAdd(8, dwBytes, &v1322);
                      v82 = v300 | v299;
                      LODWORD(v1279) = v300 | v299;
                      if ( (v300 | v299) < 0 )
                        goto LABEL_308;
                      v301 = (v1322 + 7) & 0xFFFFFFF8;
                      if ( (unsigned int)v301 < v1322 )
                      {
                        v82 = -1073741675;
                        goto LABEL_307;
                      }
                      v1325 = (v1322 + 7) & 0xFFFFFFF8;
                      LODWORD(v1279) = RtlUIntAdd(v301, 8, &v1325);
                      v82 = v1279;
                      if ( (v1279 & 0x80000000) != 0LL )
                        goto LABEL_308;
                      v303 = lpMem[1];
                      v304 = v302;
                      v1293 = (SIZE_T)v81;
                      psz = (STRSAFE_PCNZWCH)v83;
                      v1285 = v291;
                      v1278 = (size_t)v188;
                      LODWORD(v1304) = v302;
                      if ( !lpMem[1] )
                        goto LABEL_364;
                      v1278 = (size_t)v188;
                      v1285 = v291;
                      psz = (STRSAFE_PCNZWCH)v83;
                      v1293 = (SIZE_T)v81;
                      if ( LODWORD(lpMem[0]) > 1 )
                      {
                        v1282 = (SIZE_T)lpMem[1];
                        while ( 1 )
                        {
                          LODWORD(v1279) = RtlULongLongAdd(v303, 4, &v1282);
                          v82 = v1279;
                          if ( (v1279 & 0x80000000) != 0LL )
                            break;
                          LODWORD(v1279) = RtlULongLongAdd(v1282, v305, &v1282);
                          v82 = v1279;
                          if ( (v1279 & 0x80000000) != 0LL )
                            break;
                          v303 = (LPVOID)v1282;
                          if ( v306 != -1 )
                          {
                            v307 = *(_DWORD *)v1282;
                            LODWORD(v1279) = RtlULongLongAdd(v1282, 4, &v1282);
                            v82 = v1279;
                            if ( (v1279 & 0x80000000) != 0LL )
                              break;
                            v308 = lpMem[1];
                            if ( lpMem[1] && LODWORD(lpMem[0]) > 2 )
                            {
                              v1282 = (SIZE_T)lpMem[1];
                              while ( 1 )
                              {
                                LODWORD(v1279) = RtlULongLongAdd(v308, 4, &v1282);
                                v82 = v1279;
                                if ( (v1279 & 0x80000000) != 0LL )
                                  goto LABEL_365;
                                LODWORD(v1279) = RtlULongLongAdd(v1282, v311, &v1282);
                                v82 = v1279;
                                if ( (v1279 & 0x80000000) != 0LL )
                                  goto LABEL_365;
                                v308 = (LPVOID)v1282;
                                if ( (unsigned int)(v312 + 1) >= 2 )
                                {
                                  LODWORD(v1279) = RtlULongLongAdd(v1282, 4, &v1282);
                                  v82 = v1279;
                                  if ( (v1279 & 0x80000000) != 0LL )
                                    goto LABEL_365;
                                  LODWORD(v1304) = v313;
                                  v1284 = 4;
                                  LODWORD(v1279) = RtlUIntAdd((unsigned int)(v313 + 4), v1325, &v1284);
                                  v82 = v1279;
                                  if ( (v1279 & 0x80000000) != 0LL )
                                    goto LABEL_380;
                                  LODWORD(v1279) = RtlUIntAdd(v1284, v314, &v1284);
                                  v82 = v1279;
                                  if ( (v1279 & 0x80000000) != 0LL
                                    || (LODWORD(v1279) = RtlUIntAdd(v1284, v307, &v1284),
                                        v82 = v1279,
                                        (v1279 & 0x80000000) != 0LL)
                                    || (LODWORD(v1279) = RtlUIntAdd(v1284, (unsigned int)(v315 + 4), &v1284),
                                        v82 = v1279,
                                        (v1279 & 0x80000000) != 0LL)
                                    || (LODWORD(v1279) = RtlUIntAdd(v1284, v316, &v1284),
                                        v82 = v1279,
                                        (v1279 & 0x80000000) != 0LL) )
                                  {
LABEL_380:
                                    if ( v82 < 0 )
                                      goto LABEL_308;
                                  }
                                  else
                                  {
                                    v304 = v1284;
                                    LODWORD(v1304) = v1284;
                                  }
                                  if ( v304 > 0x400000 )
                                  {
                                    v82 = -2147418113;
                                    goto LABEL_307;
                                  }
                                  goto LABEL_366;
                                }
                              }
                            }
                            goto LABEL_364;
                          }
                        }
                      }
                      else
                      {
LABEL_364:
                        v82 = -1073741811;
                        LODWORD(v1279) = -1073741811;
                      }
LABEL_365:
                      if ( v82 < 0 )
                        goto LABEL_308;
LABEL_366:
                      v309 = v304;
                      v310 = GetProcessHeap();
                      v189 = HeapAlloc(v310, 8u, v309);
                      if ( !v189 )
                      {
                        v82 = -805306345;
                        v189 = 0;
                        LODWORD(v1279) = -805306345;
                        goto LABEL_309;
                      }
                      phModule = 0;
                      v1333 = 0;
                      v1334 = 0;
                      if ( !pcchLength )
                      {
                        v82 = -2147024809;
LABEL_395:
                        LODWORD(v1279) = v82;
                        goto LABEL_309;
                      }
                      LODWORD(v1334) = v1280;
                      *(_QWORD *)&v1333 = pcchLength;
                      *(_QWORD *)((char *)&v1334 + 4) = (unsigned int)v1304;
                      *((_QWORD *)&v1333 + 1) = v189;
                      if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                        && (v318 = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                      {
                        v319 = ((__int64 (__fastcall *)(__int64, __int128 *))v318)(134, &v1333);
                        v82 = v319 | 0x10000000;
                        LODWORD(v1279) = v319 | 0x10000000;
                        if ( v319 >= 0 )
                        {
                          v320 = DWORD1(v1334);
                          goto LABEL_398;
                        }
                      }
                      else
                      {
                        v317 = GetLastError();
                        LODWORD(v1279) = v317;
                        v82 = v317;
                        if ( v317 > 0 )
                        {
                          v82 = (unsigned __int16)v317 | 0x80070000;
                          LODWORD(v1279) = v82;
                        }
                        if ( v82 >= 0 )
                        {
                          v82 = -2147467259;
                          goto LABEL_395;
                        }
                      }
                      if ( v82 == -805306333 )
                      {
                        v82 = -2147024774;
                        goto LABEL_395;
                      }
                      if ( v82 < 0 )
                        goto LABEL_309;
                      v320 = v1304;
LABEL_398:
                      dwBytes = 0;
                      v1287 = v189;
                      if ( v320 < 4 )
                      {
LABEL_399:
                        v82 = -805306306;
                        goto LABEL_395;
                      }
                      LODWORD(v1282) = *v189;
                      v322 = RtlULongLongAdd(v189, 4, &v1287);
                      if ( v322 >= 0 )
                      {
                        v322 = RtlUIntAdd(0, 4, &dwBytes);
                        if ( v322 >= 0 )
                        {
                          if ( v323 - dwBytes < (unsigned int)v324 )
                            goto LABEL_399;
                          Src = v1287;
                          v1302 = v324;
                          v322 = RtlULongLongAdd(v1287, (unsigned int)v324, &v1287);
                          if ( v322 >= 0 )
                          {
                            v322 = RtlUIntAdd(dwBytes, v325, &dwBytes);
                            if ( v322 >= 0 )
                            {
                              if ( v326 - dwBytes < 4 )
                                goto LABEL_399;
                              LODWORD(v1290) = *(_DWORD *)v1287;
                              v322 = RtlULongLongAdd(v1287, 4, &v1287);
                              if ( v322 >= 0 )
                              {
                                v322 = RtlUIntAdd(dwBytes, 4, &dwBytes);
                                if ( v322 >= 0 )
                                {
                                  if ( v327 - dwBytes < (unsigned int)v328 )
                                    goto LABEL_399;
                                  v1309 = v1287;
                                  Size = v328;
                                  v322 = RtlULongLongAdd(v1287, (unsigned int)v328, &v1287);
                                  if ( v322 >= 0 )
                                  {
                                    v322 = RtlUIntAdd(dwBytes, v329, &dwBytes);
                                    if ( v322 >= 0 )
                                    {
                                      if ( v330 - dwBytes < 4 )
                                        goto LABEL_399;
                                      LODWORD(v1280) = *(_DWORD *)v1287;
                                      v322 = RtlULongLongAdd(v1287, 4, &v1287);
                                      if ( v322 >= 0 )
                                      {
                                        v322 = RtlUIntAdd(dwBytes, 4, &dwBytes);
                                        if ( v322 >= 0 )
                                        {
                                          if ( v331 - dwBytes < v332 )
                                            goto LABEL_399;
                                          v322 = RtlUIntAdd(dwBytes, v332, &dwBytes);
                                          if ( v322 >= 0 )
                                          {
                                            if ( v333 != dwBytes )
                                              goto LABEL_399;
                                            v336 = (unsigned int)v1282;
                                            if ( (unsigned int)(v1282 + v334 + v335) + 12LL != v333 )
                                              goto LABEL_399;
                                            v337 = GetProcessHeap();
                                            v338 = HeapAlloc(v337, 8u, 0x30u);
                                            v321 = 0;
                                            v1294 = v338;
                                            v339 = v338 == 0;
                                            v340 = v338;
                                            v271 = v1285;
                                            if ( v339 )
                                            {
                                              v82 = -805306345;
                                              v1294 = 0;
                                              LODWORD(v1279) = -805306345;
                                              goto LABEL_310;
                                            }
                                            v1293 = (SIZE_T)v81;
                                            psz = (STRSAFE_PCNZWCH)v83;
                                            v1278 = (size_t)v188;
                                            v1282 = 0;
                                            if ( Src )
                                            {
                                              *(_DWORD *)v340 = v336;
                                              v341 = GetProcessHeap();
                                              v342 = HeapAlloc(v341, 8u, v336);
                                              if ( !v342 )
                                              {
LABEL_431:
                                                v350 = v1294;
                                                v322 = -1073741801;
                                                v1292 = (SIZE_T)v189;
                                                v1302 = *((_QWORD *)v1294 + 1);
                                                if ( v1302 )
                                                {
                                                  v351 = GetProcessHeap();
                                                  HeapFree(v351, 0, (LPVOID)v1302);
                                                  v350 = v1294;
                                                  *((_QWORD *)v1294 + 1) = 0;
                                                }
                                                v1302 = v350[3];
                                                if ( v1302 )
                                                {
                                                  v352 = GetProcessHeap();
                                                  HeapFree(v352, 0, (LPVOID)v1302);
                                                  v350 = v1294;
                                                  *((_QWORD *)v1294 + 3) = 0;
                                                }
                                                v1302 = v350[5];
                                                if ( v1302 )
                                                {
                                                  v353 = GetProcessHeap();
                                                  HeapFree(v353, 0, (LPVOID)v1302);
                                                  *((_QWORD *)v1294 + 5) = 0;
                                                }
                                                v354 = GetProcessHeap();
                                                HeapFree(v354, 0, v1294);
                                                v355 = (size_t *)v1282;
                                                v321 = 0;
                                                goto LABEL_441;
                                              }
                                              *((_QWORD *)v1294 + 1) = v342;
                                              v322 = 0;
                                              memcpy_0(v342, Src, v1302);
                                              v340 = v1294;
                                              v321 = 0;
                                            }
                                            else
                                            {
                                              *(_DWORD *)v340 = 0;
                                              v322 = 0;
                                              v340[1] = 0;
                                            }
                                            if ( v1309 )
                                            {
                                              *((_DWORD *)v340 + 4) = (_DWORD)v1290;
                                              v343 = GetProcessHeap();
                                              v344 = HeapAlloc(v343, 8u, Size);
                                              v345 = v1294;
                                              if ( !v344 )
                                              {
LABEL_430:
                                                v1294 = v345;
                                                v1293 = (SIZE_T)v81;
                                                psz = (STRSAFE_PCNZWCH)v83;
                                                v1278 = (size_t)v188;
                                                goto LABEL_431;
                                              }
                                              *((_QWORD *)v1294 + 3) = v344;
                                              v322 = 0;
                                              memcpy_0(v344, v1309, Size);
                                              v340 = v1294;
                                              v321 = 0;
                                            }
                                            else
                                            {
                                              *((_DWORD *)v340 + 4) = 0;
                                              v340[3] = 0;
                                            }
                                            if ( v1287 )
                                            {
                                              v346 = (unsigned int)v1280;
                                              *((_DWORD *)v340 + 8) = v1280;
                                              v347 = v346;
                                              v1302 = v346;
                                              v348 = GetProcessHeap();
                                              v349 = HeapAlloc(v348, 8u, v347);
                                              v345 = v1294;
                                              if ( !v349 )
                                                goto LABEL_430;
                                              *((_QWORD *)v1294 + 5) = v349;
                                              v322 = 0;
                                              memcpy_0(v349, v1287, v1302);
                                              v340 = v1294;
                                              v321 = 0;
                                            }
                                            else
                                            {
                                              *((_DWORD *)v340 + 8) = 0;
                                              v340[5] = 0;
                                            }
                                            v355 = v340;
                                            v1282 = (SIZE_T)v340;
                                            v1292 = (SIZE_T)v189;
                                            v1278 = (size_t)v188;
                                            psz = (STRSAFE_PCNZWCH)v83;
                                            v1293 = (SIZE_T)v81;
LABEL_441:
                                            if ( v322 < 0 )
                                            {
                                              v356 = 0;
                                              v1294 = 0;
                                              if ( v355 )
                                              {
                                                v1302 = v355[1];
                                                if ( v1302 )
                                                {
                                                  v357 = GetProcessHeap();
                                                  HeapFree(v357, 0, (LPVOID)v1302);
                                                  v355 = (size_t *)v1282;
                                                  *(_QWORD *)(v1282 + 8) = 0;
                                                }
                                                v1302 = v355[3];
                                                if ( v1302 )
                                                {
                                                  v358 = GetProcessHeap();
                                                  HeapFree(v358, 0, (LPVOID)v1302);
                                                  v355 = (size_t *)v1282;
                                                  *(_QWORD *)(v1282 + 24) = 0;
                                                }
                                                v1302 = v355[5];
                                                if ( v1302 )
                                                {
                                                  v359 = GetProcessHeap();
                                                  HeapFree(v359, 0, (LPVOID)v1302);
                                                  *(_QWORD *)(v1282 + 40) = 0;
                                                }
                                                v360 = GetProcessHeap();
                                                HeapFree(v360, 0, (LPVOID)v1282);
                                                v321 = 0;
                                                v356 = 0;
                                                v1294 = 0;
                                              }
                                            }
                                            else
                                            {
                                              v356 = (unsigned int *)v355;
                                              v1294 = v355;
                                            }
LABEL_453:
                                            v82 = v322 | 0x10000000;
                                            LODWORD(v1279) = v82;
                                            if ( v82 < 0 )
                                              goto LABEL_309;
                                            if ( !v356 || (v1287 = (void *)*((_QWORD *)v356 + 1)) == 0 || *v356 == v321 )
                                            {
                                              v82 = -805306355;
                                              goto LABEL_395;
                                            }
                                            v361 = *v356 - 8LL;
                                            v1290 = (LPVOID)v361;
                                            v1295 = MemoryAlloc(v361);
                                            v362 = v1295;
                                            if ( !v1295 )
                                            {
LABEL_485:
                                              v82 = -805306367;
                                              v1295 = 0;
                                              goto LABEL_395;
                                            }
                                            v1281 = 0;
                                            v363 = 0;
                                            v1282 = 0x7F1137FAB69605ELL;
                                            v364 = 0;
                                            Src = v1287;
                                            v365 = 0;
                                            Size = (SIZE_T)v1295;
                                            LODWORD(v1305) = 0;
                                            v366 = v361 & 7;
                                            if ( (v361 & 7) != 0 )
                                            {
                                              LODWORD(v1279) = 0;
                                              v367 = 0;
                                              v368 = (unsigned __int8 *)Src;
                                              v369 = 0;
                                              do
                                              {
                                                v370 = *v368++;
                                                LODWORD(v1280) = 8 * v365;
                                                if ( (unsigned int)v365 >= 4 )
                                                  v367 |= v370 << (56 - v1280);
                                                else
                                                  v369 |= v370 << (24 - v1280);
                                                ++v365;
                                              }
                                              while ( v365 < v366 );
                                              v361 = (unsigned __int64)v1290;
                                              LODWORD(v1305) = v369;
                                              v371 = v369;
                                              v363 = v1281;
                                              LODWORD(v1279) = v367;
                                              Src = v368;
                                              v1292 = (SIZE_T)v189;
                                              v1278 = (size_t)v188;
                                              psz = (STRSAFE_PCNZWCH)v83;
                                              v1293 = (SIZE_T)v81;
                                              LODWORD(v1304) = 0;
                                              v372 = v367 ^ 0x699A899C;
                                              v364 = v371 ^ 0x92F65A5;
                                              v373 = v364;
                                              v374 = v367 ^ 0x699A899C;
                                              if ( v366 )
                                              {
                                                v375 = v1295;
                                                do
                                                {
                                                  v1302 = (size_t)(v375 + 1);
                                                  if ( (unsigned int)v1304 >= 4 )
                                                  {
                                                    v374 = __ROR4__(v374, 24);
                                                    v376 = v374;
                                                  }
                                                  else
                                                  {
                                                    v373 = __ROR4__(v373, 24);
                                                    v376 = v373;
                                                  }
                                                  LODWORD(v1304) = v1304 + 1;
                                                  *v375 = v376;
                                                  v375 = (_BYTE *)v1302;
                                                }
                                                while ( (int)v1304 < v366 );
                                                Size = v1302;
                                              }
                                              if ( (unsigned int)v366 <= 4 )
                                              {
                                                v365 = 0;
                                                if ( (unsigned int)v366 < 4 )
                                                  v364 = v364 >> (8 * (4 - v366)) << (8 * (4 - v366));
                                              }
                                              else
                                              {
                                                v365 = v372 >> (8 * (8 - v366)) << (8 * (8 - v366));
                                              }
                                            }
                                            else
                                            {
                                              LODWORD(v1279) = -1;
                                            }
                                            v377 = v361 >> 3;
                                            if ( v361 >> 3 )
                                            {
                                              v378 = HIDWORD(v1282);
                                              v379 = (unsigned __int8 *)Src;
                                              v380 = HIDWORD(v1282) ^ 0xAB69605E;
                                              v381 = (_BYTE *)Size;
                                              v382 = v1279;
                                              v383 = v1305;
                                              v1284 = WORD2(v1282);
                                              dwBytes = 24670;
                                              v384 = v377;
                                              v1309 = 0;
                                              LODWORD(v1280) = HIDWORD(v1282) ^ 0xAB69605E;
                                              do
                                              {
                                                v385 = *v379;
                                                v386 = v379[1];
                                                v387 = v379[4];
                                                v379 += 8;
                                                v388 = *(v379 - 5) | ((*(v379 - 6) | (((v385 << 8) | v386) << 8)) << 8);
                                                v389 = v364 ^ v388;
                                                v390 = *(v379 - 1)
                                                     | ((*(v379 - 2) | ((*(v379 - 3) | (v387 << 8)) << 8)) << 8);
                                                v391 = v380 ^ v365 ^ v390 ^ v364 ^ v388;
                                                v392 = v389
                                                     ^ (__ROR4__(v391, 22) + v1284 * __ROR4__(v391 + 1419157410, 27));
                                                v393 = v391
                                                     ^ (WORD1(v1282) * __ROR4__(v378 + v392, 9) - __ROR4__(v392, 30));
                                                v394 = v392 ^ (dwBytes * (v393 - v1284) - (v393 >> 13));
                                                v395 = v393
                                                     ^ (HIWORD(v1282) * __ROR4__(WORD1(v1282) ^ v394, 26)
                                                      - __ROR4__(v394, 30));
                                                v396 = v394 ^ (v378 - (v395 ^ 0xAB69605E));
                                                v397 = v395 ^ (WORD1(v1282) * (v1284 ^ v396)) ^ __ROR4__(v396, 6);
                                                v398 = v396 ^ (__ROR4__(v397, 30) + dwBytes * __ROR4__(v378 + v397, 15));
                                                v399 = v397
                                                     ^ (HIWORD(v1282) * __ROR4__(v398 + 1419157410, 14)
                                                      - __ROR4__(v398, 24));
                                                v400 = v398
                                                     ^ __ROR4__(v399, 10)
                                                     ^ (v1284 * __ROR4__(v399 ^ 0xAB69605E, 12));
                                                v401 = v400
                                                     ^ (HIWORD(v1282)
                                                      * (dwBytes
                                                       + __ROR4__(
                                                           ~(v399
                                                           ^ (v400 >> 10)
                                                           ^ (WORD1(v1282) * (HIWORD(v1282) ^ v400))),
                                                           5)));
                                                v402 = v399
                                                     ^ (v400 >> 10)
                                                     ^ (WORD1(v1282) * (HIWORD(v1282) ^ v400))
                                                     ^ (v401 - HIWORD(v1282))
                                                     ^ 0xAB69605E;
                                                v403 = v401 ^ ((v402 >> 2) + v1284 * __ROR4__(HIWORD(v1282) ^ v402, 30));
                                                v404 = v402
                                                     ^ (__ROR4__(v403, 25)
                                                      + WORD1(v1282) * __ROR4__(v403 - HIDWORD(v1282), 6));
                                                v405 = v403 ^ (dwBytes * (v1284 ^ v404) + __ROR4__(v404, 9));
                                                v406 = v404
                                                     ^ (__ROR4__(v405, 25)
                                                      + HIWORD(v1282) * __ROR4__(WORD1(v1282) ^ v405, 27));
                                                v378 = HIDWORD(v1282);
                                                v407 = v1280 ^ v405 ^ v406;
                                                v408 = v406 ^ (v1284 * (__ROR4__(v407, 3) - WORD1(v1282)));
                                                v409 = v407
                                                     ^ (dwBytes * __ROR4__(v408 - HIDWORD(v1282), 1) - __ROR4__(v408, 6));
                                                v380 = v1280;
                                                v410 = v408
                                                     ^ (__ROR4__(v409, 18)
                                                      + HIWORD(v1282) * __ROR4__(v409 - 1419157410, 29));
                                                v411 = v409
                                                     ^ (v1284 * __ROR4__(v410 - 1419157410, 17) - __ROR4__(v410, 14));
                                                v412 = v410 ^ (v411 >> 3) ^ (WORD1(v1282) * (v411 ^ dwBytes));
                                                v413 = v412 ^ HIDWORD(v1282);
                                                v414 = __ROR4__(v412, 30);
                                                v365 = v382 ^ v412;
                                                v382 = v390;
                                                v364 = v383 ^ v411 ^ v414 ^ (dwBytes * __ROR4__(v413, 28));
                                                v383 = v388;
                                                v381[3] = v364;
                                                v381[7] = v365;
                                                v381[2] = __ROR4__(v364, 8);
                                                v381[6] = __ROR4__(v365, 8);
                                                v381[1] = __ROR4__(v364, 16);
                                                v381[5] = __ROR4__(v365, 16);
                                                *v381 = __ROR4__(v364, 24);
                                                v381[4] = __ROR4__(v365, 24);
                                                v381 += 8;
                                                v1309 = (char *)v1309 + 1;
                                              }
                                              while ( (unsigned __int64)v1309 < v384 );
                                              v363 = v1281;
                                              v81 = (void *)v1293;
                                              v83 = psz;
                                              v189 = (_DWORD *)v1292;
                                              v188 = (unsigned int *)v1278;
                                              v362 = v1295;
                                              v361 = (unsigned __int64)v1290;
                                            }
                                            for ( i10 = 0; i10 < v361; ++i10 )
                                              v363 ^= v362[i10];
                                            if ( v363 != *(_QWORD *)((char *)v1287 + v361) )
                                            {
                                              MemoryFree(v362);
                                              goto LABEL_485;
                                            }
                                            v1284 = 0;
                                            v1278 = (size_t)v362;
                                            if ( (unsigned int)v361 < 4 )
                                            {
LABEL_487:
                                              v416 = -1073741762;
LABEL_525:
                                              v82 = v416 | 0x10000000;
                                              goto LABEL_395;
                                            }
                                            v416 = RtlULongLongAdd(v362, 4, &v1278);
                                            if ( v416 >= 0 )
                                            {
                                              v416 = RtlUIntAdd(0, 4, &v1284);
                                              if ( v416 >= 0 )
                                              {
                                                if ( (unsigned int)v1290 - v1284 < 4 )
                                                  goto LABEL_523;
                                                LODWORD(v1305) = *(_DWORD *)v1278;
                                                v416 = RtlULongLongAdd(v1278, 4, &v1278);
                                                if ( v416 < 0 )
                                                  goto LABEL_524;
                                                v416 = RtlUIntAdd(v1284, 4, &v1284);
                                                if ( v416 < 0 )
                                                  goto LABEL_524;
                                                if ( (unsigned int)v1290 - v1284 < (unsigned int)v1305 )
                                                  goto LABEL_523;
                                                v416 = RtlUIntAdd(v1284, (unsigned int)v1305, &v1284);
                                                if ( v416 >= 0 )
                                                {
                                                  if ( (unsigned __int64)v419 + (unsigned int)v1290 >= (unsigned int)v1305 + v1278
                                                    && (unsigned __int64)v419
                                                     + (unsigned int)v1290
                                                     - (unsigned int)v1305
                                                     - v1278 < 8 )
                                                  {
                                                    LODWORD(v1282) = *v419;
                                                    psz = 0;
                                                    v1290 = 0;
                                                    v1287 = 0;
                                                    v1301 = 0;
                                                    if ( v1278 )
                                                    {
                                                      v420 = RtlULongLongAdd(v1278, (unsigned int)v1305, &psz);
                                                      v1295 = v422;
                                                      v416 = v420;
                                                      v1294 = v423;
                                                      v1285 = v424;
                                                      if ( v420 < 0 )
                                                      {
LABEL_510:
                                                        v431 = v1298;
                                                        goto LABEL_520;
                                                      }
                                                      v425 = v421;
                                                      Src = v421;
                                                      if ( v421 < psz )
                                                      {
                                                        while ( 1 )
                                                        {
                                                          v416 = RtlULongLongAdd(v425, 4, &v1290);
                                                          if ( v416 < 0 )
                                                            break;
                                                          if ( v1290 > psz )
                                                            goto LABEL_509;
                                                          LODWORD(v1280) = 0;
                                                          v416 = RtlUIntAdd(4, *(unsigned int *)Src, &v1280);
                                                          if ( v416 < 0 )
                                                            goto LABEL_525;
                                                          v426 = RtlULongLongAdd(Src, (unsigned int)v1280, &v1287);
                                                          v1295 = v429;
                                                          v416 = v426;
                                                          v1294 = v428;
                                                          v1285 = v427;
                                                          if ( v426 < 0 )
                                                            goto LABEL_510;
                                                          v425 = (STRSAFE_PCNZWCH)v1287;
                                                          v430 = psz;
                                                          Src = v1287;
                                                          v1295 = v429;
                                                          v1294 = v428;
                                                          v1285 = v427;
                                                          if ( v1287 > psz )
                                                            goto LABEL_509;
                                                          ++v1301;
                                                          if ( v1287 >= psz )
                                                          {
                                                            v1295 = v429;
                                                            v1294 = v428;
                                                            v1285 = v427;
                                                            goto LABEL_508;
                                                          }
                                                        }
                                                        v431 = 0;
LABEL_520:
                                                        if ( v416 < 0 || (_DWORD)v1282 == v431 )
                                                          goto LABEL_525;
                                                        goto LABEL_487;
                                                      }
                                                      v430 = psz;
LABEL_508:
                                                      if ( v425 != v430 )
                                                      {
LABEL_509:
                                                        v416 = -1073741811;
                                                        goto LABEL_525;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v416 = 0;
                                                      v1295 = v419;
                                                      v1294 = v418;
                                                      v1285 = v417;
                                                    }
                                                    v432 = v1305;
                                                    v433 = 0;
                                                    Src = 0;
                                                    if ( (_DWORD)v1305 )
                                                    {
                                                      v434 = GetProcessHeap();
                                                      v433 = HeapAlloc(v434, 8u, (unsigned int)v1305);
                                                      Src = v433;
                                                      if ( !v433 )
                                                      {
                                                        v416 = -1073741801;
                                                        goto LABEL_525;
                                                      }
                                                      v432 = v1305;
                                                      v416 = 0;
                                                    }
                                                    if ( v1278 )
                                                      memcpy_0(v433, (const void *)v1278, v432);
                                                    v1291 = Src;
                                                    v431 = v1301;
                                                    v1298 = v1301;
                                                    goto LABEL_520;
                                                  }
LABEL_523:
                                                  v416 = -1073741762;
                                                }
                                              }
                                            }
LABEL_524:
                                            v1295 = v419;
                                            v1285 = v417;
                                            v1294 = v418;
                                            goto LABEL_525;
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                              v321 = 0;
                            }
                          }
                        }
                      }
                      v356 = (unsigned int *)v1294;
                      v1292 = (SIZE_T)v189;
                      goto LABEL_453;
                    }
                  }
                }
              }
            }
          }
          v1285 = v291;
          v298 = GetProcessHeap();
          HeapFree(v298, 0, (LPVOID)psz);
          goto LABEL_351;
        }
        if ( v50 && !wcscmp_0(v50, L"WinSta0") && v51 && !wcscmp_0(v51, L"Default") )
        {
          v1326 = 0;
          CurrentProcess = GetCurrentProcess();
          if ( !(unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v1326, 4) )
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
            goto LABEL_102;
          }
          if ( (v1326 & 0xF) == 0 )
            v52 = 1;
        }
      }
      else
      {
        LastError = 0;
      }
      v53 = v52;
      goto LABEL_102;
    }
    v3 = dword_1801173E0;
LABEL_24:
    dword_1801173E0 = v3 + 1;
    goto LABEL_25;
  }
  v2 = -2147024809;
LABEL_1600:
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1329);
  return v2;
}

```

## disassembly

```asm
0x180056b70  mov     [rsp-8+arg_10], rbx
0x180056b75  push    rbp
0x180056b76  push    rsi
0x180056b77  push    rdi
0x180056b78  push    r12
0x180056b7a  push    r13
0x180056b7c  push    r14
0x180056b7e  push    r15
0x180056b80  lea     rbp, [rsp-0E10h]
0x180056b88  sub     rsp, 0F10h
0x180056b8f  mov     rax, cs:__security_cookie
0x180056b96  xor     rax, rsp
0x180056b99  mov     [rbp+0E40h+var_40], rax
0x180056ba0  mov     rax, rcx
0x180056ba3  mov     [rbp+0E40h+psz], rcx
0x180056ba7  xor     ecx, ecx
0x180056ba9  mov     [rbp+0E40h+var_CD0], rdx
0x180056bb0  mov     [rbp+0E40h+var_D50], rcx
0x180056bb7  test    rax, rax
0x180056bba  jnz     short loc_180056BC6
0x180056bbc  mov     ebx, 80070057h
0x180056bc1  jmp     loc_180061070
0x180056bc6  xor     eax, eax
0x180056bc8  test    rdx, rdx
0x180056bcb  jz      short loc_180056BBC
0x180056bcd  mov     dword ptr [rsp+0F40h+dwBytes+4], eax
0x180056bd1  lea     esi, [rax+1]
0x180056bd4  mov     [rbp+0E40h+var_DC0], rax
0x180056bdb  jmp     short loc_180056BDF
0x180056bdd  xor     eax, eax
0x180056bdf  lock cmpxchg cs:dword_1801173E4, esi
0x180056be7  jnz     short loc_180056BDD
0x180056be9  mov     eax, cs:dword_1801173E0
0x180056bef  lea     r15, qword_180116EF0
0x180056bf6  or      ebx, 0FFFFFFFFh
0x180056bf9  lea     r12, off_180114000
0x180056c00  mov     [rbp+0E40h+var_DD8], ebx
0x180056c03  mov     r14d, 60h ; '`'
0x180056c09  test    eax, eax
0x180056c0b  jnz     loc_180057028
0x180056c11  mov     ecx, 338h; unsigned __int64
0x180056c16  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x180056c1b  mov     rdi, rax
0x180056c1e  test    rax, rax
0x180056c21  jz      loc_180056F92
0x180056c27  xor     ecx, ecx
0x180056c29  lea     rsi, qword_1800F4460
0x180056c30  mov     r14, rax
0x180056c33  mov     r12d, ecx
0x180056c36  mov     r13d, ebx
0x180056c39  mov     r10d, ecx
0x180056c3c  mov     r8d, ecx
0x180056c3f  mov     eax, 0AB69605Eh
0x180056c44  lea     r15d, [rcx+67h]
0x180056c48  movzx   ecx, byte ptr [rsi]
0x180056c4b  shl     ecx, 8
0x180056c4e  movzx   ebx, byte ptr [rsi+1]
0x180056c52  movzx   r11d, byte ptr [rsi+4]
0x180056c57  lea     rsi, [rsi+8]
0x180056c5b  or      ebx, ecx
0x180056c5d  shl     r11d, 8
0x180056c61  movzx   ecx, byte ptr [rsi-6]
0x180056c65  shl     ebx, 8
0x180056c68  or      ebx, ecx
0x180056c6a  movzx   ecx, byte ptr [rsi-5]
0x180056c6e  shl     ebx, 8
0x180056c71  or      ebx, ecx
0x180056c73  movzx   ecx, byte ptr [rsi-3]
0x180056c77  or      r11d, ecx
0x180056c7a  mov     edx, ebx
0x180056c7c  movzx   ecx, byte ptr [rsi-2]
0x180056c80  xor     edx, r8d
0x180056c83  mov     r8d, edx
0x180056c86  shl     r11d, 8
0x180056c8a  or      r11d, ecx
0x180056c8d  movzx   ecx, byte ptr [rsi-1]
0x180056c91  shl     r11d, 8
0x180056c95  or      r11d, ecx
0x180056c98  xor     r8d, r11d
0x180056c9b  xor     r8d, r10d
0x180056c9e  xor     r8d, 0AC987321h
0x180056ca5  lea     ecx, [r8+54969FA2h]
0x180056cac  ror     ecx, 1Bh
0x180056caf  imul    r9d, ecx, 137Fh
0x180056cb6  mov     ecx, r8d
0x180056cb9  ror     ecx, 16h
0x180056cbc  add     r9d, ecx
0x180056cbf  xor     r9d, edx
0x180056cc2  lea     ecx, [r9+7F1137Fh]
0x180056cc9  ror     ecx, 9
0x180056ccc  imul    edx, ecx, 0AB69h
0x180056cd2  mov     ecx, r9d
0x180056cd5  ror     ecx, 1Eh
0x180056cd8  sub     edx, ecx
0x180056cda  xor     edx, r8d
0x180056cdd  imul    r10d, edx, 605Eh
0x180056ce4  mov     ecx, edx
0x180056ce6  shr     ecx, 0Dh
0x180056ce9  sub     r10d, ecx
0x180056cec  sub     r10d, 756C8A2h
0x180056cf3  xor     r10d, r9d
0x180056cf6  mov     r9d, 7F1137Fh
0x180056cfc  mov     ecx, r10d
0x180056cff  xor     ecx, 0AB69h
0x180056d05  ror     ecx, 1Ah
0x180056d08  imul    r8d, ecx, 7F1h
0x180056d0f  mov     ecx, r10d
0x180056d12  ror     ecx, 1Eh
0x180056d15  sub     r8d, ecx
0x180056d18  xor     r8d, edx
0x180056d1b  mov     ecx, r8d
0x180056d1e  xor     ecx, eax
0x180056d20  sub     r9d, ecx
0x180056d23  xor     r9d, r10d
0x180056d26  mov     ecx, r9d
0x180056d29  mov     r10d, r9d
0x180056d2c  xor     ecx, 137Fh
0x180056d32  ror     r10d, 6
0x180056d36  imul    edx, ecx, 0AB69h
0x180056d3c  xor     r10d, edx
0x180056d3f  xor     r10d, r8d
0x180056d42  lea     ecx, [r10+7F1137Fh]
0x180056d49  ror     ecx, 0Fh
0x180056d4c  imul    edx, ecx, 605Eh
0x180056d52  mov     ecx, r10d
0x180056d55  ror     ecx, 1Eh
0x180056d58  add     edx, ecx
0x180056d5a  xor     edx, r9d
0x180056d5d  lea     ecx, [rdx+54969FA2h]
0x180056d63  ror     ecx, 0Eh
0x180056d66  imul    r8d, ecx, 7F1h
0x180056d6d  mov     ecx, edx
0x180056d6f  ror     ecx, 18h
0x180056d72  sub     r8d, ecx
0x180056d75  xor     r8d, r10d
0x180056d78  mov     ecx, r8d
0x180056d7b  mov     r10d, 7F1h
0x180056d81  xor     ecx, eax
0x180056d83  ror     ecx, 0Ch
0x180056d86  imul    r9d, ecx, 137Fh
0x180056d8d  mov     ecx, r8d
0x180056d90  ror     ecx, 0Ah
0x180056d93  xor     r9d, ecx
0x180056d96  xor     r9d, edx
0x180056d99  mov     ecx, r9d
0x180056d9c  xor     ecx, r10d
0x180056d9f  imul    edx, ecx, 0AB69h
0x180056da5  mov     ecx, r9d
0x180056da8  shr     ecx, 0Ah
0x180056dab  xor     edx, ecx
0x180056dad  xor     edx, r8d
0x180056db0  mov     ecx, edx
0x180056db2  not     ecx
0x180056db4  ror     ecx, 5
0x180056db7  add     ecx, 605Eh
0x180056dbd  imul    r8d, ecx, 7F1h
0x180056dc4  xor     r8d, r9d
0x180056dc7  lea     r9d, [r8-7F1h]
0x180056dce  xor     r9d, edx
0x180056dd1  xor     r9d, eax
0x180056dd4  mov     ecx, r9d
0x180056dd7  xor     ecx, r10d
0x180056dda  ror     ecx, 1Eh
0x180056ddd  imul    r10d, ecx, 137Fh
0x180056de4  mov     ecx, r9d
0x180056de7  shr     ecx, 2
0x180056dea  add     r10d, ecx
0x180056ded  xor     r10d, r8d
0x180056df0  lea     ecx, [r10-7F1137Fh]
0x180056df7  ror     ecx, 6
0x180056dfa  imul    r8d, ecx, 0AB69h
0x180056e01  mov     ecx, r10d
0x180056e04  ror     ecx, 19h
0x180056e07  add     r8d, ecx
0x180056e0a  xor     r8d, r9d
0x180056e0d  mov     ecx, r8d
0x180056e10  mov     r9d, r8d
0x180056e13  xor     ecx, 137Fh
0x180056e19  ror     r9d, 9
0x180056e1d  imul    edx, ecx, 605Eh
0x180056e23  add     r9d, edx
0x180056e26  xor     r9d, r10d
0x180056e29  mov     ecx, r9d
0x180056e2c  xor     ecx, 0AB69h
0x180056e32  ror     ecx, 1Bh
0x180056e35  imul    edx, ecx, 7F1h
0x180056e3b  mov     ecx, r9d
0x180056e3e  ror     ecx, 19h
0x180056e41  add     edx, ecx
0x180056e43  xor     edx, r8d
0x180056e46  mov     r8d, edx
0x180056e49  xor     r8d, r9d
0x180056e4c  xor     r8d, 0AC987321h
0x180056e53  mov     ecx, r8d
0x180056e56  ror     ecx, 3
0x180056e59  imul    r9d, ecx, 137Fh
0x180056e60  sub     r9d, 0D0DD417h
0x180056e67  xor     r9d, edx
0x180056e6a  lea     ecx, [r9-7F1137Fh]
0x180056e71  ror     ecx, 1
0x180056e73  imul    edx, ecx, 605Eh
0x180056e79  mov     ecx, r9d
0x180056e7c  ror     ecx, 6
0x180056e7f  sub     edx, ecx
0x180056e81  xor     edx, r8d
0x180056e84  lea     ecx, [rdx-54969FA2h]
0x180056e8a  ror     ecx, 1Dh
0x180056e8d  imul    r8d, ecx, 7F1h
0x180056e94  mov     ecx, edx
0x180056e96  ror     ecx, 12h
0x180056e99  add     r8d, ecx
0x180056e9c  xor     r8d, r9d
0x180056e9f  lea     ecx, [r8-54969FA2h]
0x180056ea6  ror     ecx, 11h
0x180056ea9  imul    r9d, ecx, 137Fh
0x180056eb0  mov     ecx, r8d
0x180056eb3  ror     ecx, 0Eh
0x180056eb6  sub     r9d, ecx
0x180056eb9  xor     r9d, edx
0x180056ebc  mov     ecx, r9d
0x180056ebf  xor     ecx, 605Eh
0x180056ec5  imul    r10d, ecx, 0AB69h
0x180056ecc  mov     ecx, r9d
0x180056ecf  shr     ecx, 3
0x180056ed2  xor     r10d, ecx
0x180056ed5  xor     r10d, r8d
0x180056ed8  mov     ecx, r10d
0x180056edb  xor     ecx, 7F1137Fh
0x180056ee1  ror     ecx, 1Ch
0x180056ee4  imul    r8d, ecx, 605Eh
0x180056eeb  mov     ecx, r10d
0x180056eee  ror     ecx, 1Eh
0x180056ef1  xor     r10d, r13d
0x180056ef4  mov     r13d, r11d
0x180056ef7  xor     r8d, ecx
0x180056efa  xor     r8d, r9d
0x180056efd  xor     r8d, r12d
0x180056f00  mov     r12d, ebx
0x180056f03  mov     [r14+3], r8b
0x180056f07  mov     ecx, r8d
0x180056f0a  ror     ecx, 8
0x180056f0d  mov     [r14+7], r10b
0x180056f11  mov     [r14+2], cl
0x180056f15  mov     ecx, r10d
0x180056f18  ror     ecx, 8
0x180056f1b  mov     [r14+6], cl
0x180056f1f  mov     ecx, r8d
0x180056f22  ror     ecx, 10h
0x180056f25  mov     [r14+1], cl
0x180056f29  mov     ecx, r10d
0x180056f2c  ror     ecx, 10h
0x180056f2f  mov     [r14+5], cl
0x180056f33  mov     ecx, r8d
0x180056f36  ror     ecx, 18h
0x180056f39  mov     [r14], cl
0x180056f3c  mov     ecx, r10d
0x180056f3f  ror     ecx, 18h
0x180056f42  mov     [r14+4], cl
0x180056f46  lea     r14, [r14+8]
0x180056f4a  sub     r15, 1
0x180056f4e  jnz     loc_180056C48
0x180056f54  xor     ecx, ecx
0x180056f56  mov     al, cl
0x180056f58  lea     esi, [rcx+1]
0x180056f5b  xor     al, [rdi+rcx]
0x180056f5e  add     rcx, rsi
0x180056f61  cmp     rcx, 338h
0x180056f68  jb      short loc_180056F5B
0x180056f6a  movzx   ecx, al
0x180056f6d  cmp     rcx, cs:qword_1800F4798
0x180056f74  jz      short loc_180056FD4
0x180056f76  mov     rcx, rdi; void *
0x180056f79  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180056f7e  lea     r15, qword_180116EF0
0x180056f85  lea     r12, off_180114000
0x180056f8c  mov     r14d, 60h ; '`'
0x180056f92  xor     ebx, ebx
0x180056f94  lea     rax, [rbx+rbx*2]
0x180056f98  mov     rcx, [r15+rax*8]; hLibModule
0x180056f9c  test    rcx, rcx
0x180056f9f  jz      short loc_180056FA7
0x180056fa1  call    cs:__imp_FreeLibrary
0x180056fa7  add     rbx, rsi
0x180056faa  cmp     rbx, 4
0x180056fae  jnz     short loc_180056F94
0x180056fb0  mov     r8, r14; Size
0x180056fb3  xor     edx, edx; Val
0x180056fb5  mov     rcx, r15; void *
0x180056fb8  call    memset_0
0x180056fbd  mov     r8d, 170h; Size
0x180056fc3  lea     rdx, off_1800E1E60; Src
0x180056fca  mov     rcx, r12; void *
0x180056fcd  call    memcpy_0
0x180056fd2  jmp     short loc_180057030
0x180056fd4  xor     eax, eax
0x180056fd6  lea     r15, qword_180116EF0
0x180056fdd  xor     edx, edx; Val
0x180056fdf  mov     [rbp+0E40h+var_E28], eax
0x180056fe2  mov     rcx, r15; void *
0x180056fe5  mov     [rdi+337h], al
  ... truncated ...
```
